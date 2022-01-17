
<html lang="en">
    <head>
        <title>XRP NFT: {{noble-nft}}</title>
        <meta name="viewport" content="width=device-width, initial-scale=1">
    {% if meta.staticILPAddress %}
        <meta name="monetization" content="{{ meta.staticILPAddress }}">
    {% endif %}
    </head>
    <style>
        body,html {
            margin: 0;
            padding: 0;
            font-family: "Helvetica", sans-serif;
            background: linear-gradient(-45deg, #d34d24, #ac1d54, #2e8fb3, #40b499);
            background-size: 500% 500%;
            animation: gradient 60s ease infinite;
            height: 100%;
        }
        @keyframes gradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
        h1 {
            font-size: 36px;
            margin: 10px 0 0 0;
            font-weight: lighter;
            text-transform: uppercase;
            color: #ffffff;
        }
        p {
            font-size: 16px;
            font-family: sans-serif;
            font-weight: bolder;
            color: #f8f8f8;
            max-width: 50%;
            text-align: left;
        }
        #header {
            position: absolute;
            left: 0;
            top: 0;
            padding:10px 20px;
            font-size: 24px;
            width: 100%;
            background-color: #ffffff;
            background: #ffff;
            border-bottom: 1px solid #1f1209;
            box-shadow: 0 10px 20px -10px rgb(0, 0, 0);
            box-sizing:border-box;
            -moz-box-sizing:border-box;
            -webkit-box-sizing:border-box;
            -ms-box-sizing:border-box; 
        }
        #canvas {
            min-height: 100%;
            position: absolute;
        }
        #container {
            padding-top: 120px;
            display: flex;
            justify-content: center;
            flex-direction: column;
            align-items: center;
            transform: translatey(0px);
        }
        #card {
            transform: translatey(0px);
            animation: float 5s ease-in-out infinite;
            text-align: center;
            padding: 100px;
            border-radius: 10px;
            background: -webkit-radial-gradient(center center, rgb(35, 37, 38, 0.85) 0%, rgb(65, 67, 69, 0.75) 100%);
        }
        @keyframes float {
            0% {
                box-shadow: 0 5px 15px 0px rgba(0, 0, 0, 0.6);
                transform: translatey(0px);
            }
            50% {
                box-shadow: 0 25px 15px 0px rgba(0, 0, 0, 0.2);
                transform: translatey(-20px);
            }
            100% {
                box-shadow: 0 5px 15px 0px rgba(0, 0, 0, 0.6);
                transform: translatey(0px);
            }
        }
        #content {
            padding-top: 20px;
            text-align: center;
            display: flex;
            justify-content: center;
            flex-direction: column;
            align-items: center;
        }
        .styled-table {
            border-collapse:collapse;
            margin: 25px 0;
            font-size: 16px;
            font-family: sans-serif;
            box-shadow: 0 25px 15px 0px rgba(0, 0, 0, 0.2);
            max-width: 75%;
        }
        .styled-table thead tr {
            background-color: #030833;
            color: #ffffff;
            text-align: center;
            font-size: 18px;
        }
        .styled-table th, .styled-table td {
            padding: 14px 16px;
        }
        .styled-table tbody tr {
            border-bottom: 1px solid #dddddd;
        }
        .styled-table tbody tr:nth-of-type(even) {
            background-color: rgb(255, 255, 255, 0.75);
        }
        .styled-table tbody tr:nth-of-type(odd) {
            background-color: rgb(255, 255, 255, 0.85);
        }
        .styled-table tbody tr.active-row {
            font-weight: bold;
            color: #180141;

        }
        .styled-table thead {
            display: table-header-group;
            vertical-align: middle;
            border-color: inherit;
            border-collapse: separate;
        }
        th:first-of-type {
            border-top-left-radius: 10px;
        }
        th:last-of-type {
            border-top-right-radius: 10px;
        }
    </style>
    <canvas id="canvas"></canvas>
    <div id="header">
        <svg height="36" viewBox="0 0 512 143" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g id="Canvas" fill="none">
                <g id="xrp-text-mark-black">
                    <g id="Group">
                        <path id="Vector" d="M 143.928 0L 168.372 0L 117.518 51.4245C 99.1086 70.0395 69.2627 70.0395 50.8541 51.4245L 8.30456e-09 0L 24.4431 0L 63.0757 39.0659C 74.7345 50.8554 93.6366 50.8554 105.295 39.0659L 143.928 0Z" transform="translate(0.311646 0)" fill="#23292F"/>
                        <path id="Vector_2" d="M 24.4432 65.7034L 0 65.7034L 51.1682 13.9612C 69.5768 -4.65374 99.4227 -4.65374 117.832 13.9612L 169 65.7034L 144.557 65.7034L 105.61 26.3196C 93.9508 14.53 75.0486 14.53 63.3899 26.3196L 24.4432 65.7034Z" transform="translate(0 77.2965)" fill="#23292F"/>
                    </g>
                    <path id="Union" fill-rule="evenodd" clip-rule="evenodd" d="M 73.1365 0L 73.1637 0.000372426C 79.4083 0.129969 85.2723 1.35704 90.7291 3.69537C 96.275 5.8933 101.147 8.93696 105.324 12.8252C 109.518 16.7277 112.793 21.3388 115.154 26.6325C 117.528 31.8339 118.71 37.3548 118.71 43.1721C 118.71 49.1231 117.457 54.7736 114.946 60.102C 112.58 65.2803 109.236 69.8798 104.928 73.8884C 100.742 77.7837 95.8004 80.8874 90.1272 83.2056L 90.1005 83.2164C 84.5016 85.4307 78.4991 86.5289 72.1193 86.5289L 18.7701 86.5289L 18.7701 142.515L 0 142.515L 0 0.000372426L 73.1365 0ZM 72.1193 69.2464C 75.8827 69.2464 79.4447 68.5705 82.8275 67.2212C 86.2414 65.8594 89.2106 63.9962 91.7548 61.6288C 94.2985 59.2618 96.3007 56.4982 97.7642 53.3212C 99.2095 50.1826 99.9402 46.8071 99.9402 43.1721C 99.9402 39.6704 99.2138 36.356 97.7642 33.2077C 96.3007 30.0307 94.2985 27.2671 91.7548 24.9001C 89.2106 22.5331 86.2414 20.6696 82.8275 19.3077C 79.4447 17.9588 75.8827 17.2829 72.1193 17.2829L 18.7701 17.2829L 18.7701 69.2464L 72.1193 69.2464Z" transform="translate(393.29 0)" fill="#23292F"/>
                    <path id="Union_2" d="M 45.7768 86.8257C 55.1828 86.8257 64.0833 90.7999 69.9857 97.6349L 108.742 142.515L 132.871 142.515L 79.8436 80.2913C 73.9448 73.3694 64.9858 69.3359 55.5094 69.3359L 18.7701 69.3359L 18.7701 17.4902L 72.1198 17.4902C 75.8827 17.4902 79.4447 18.167 82.8275 19.5176C 86.2419 20.8809 89.2111 22.7468 91.7548 25.1172L 91.7976 25.156C 94.315 27.3903 96.3055 30.0792 97.7642 33.2513C 99.2095 36.394 99.9401 39.7731 99.9401 43.4129C 99.9401 47.0474 99.2116 50.422 97.7706 53.5606C 96.8962 55.3918 95.8268 57.0993 94.5605 58.6863L 106.774 72.3171C 106.927 72.1564 107.078 71.9946 107.229 71.8316C 110.84 67.9484 113.623 63.6069 115.572 58.8164C 117.669 53.9875 118.71 48.8462 118.71 43.4129C 118.71 37.5873 117.528 32.06 115.154 26.8519C 112.794 21.5506 109.518 16.9342 105.324 13.026C 101.151 9.13794 96.2879 6.03255 90.7526 3.71021C 85.2895 1.36215 79.418 0.130137 73.1637 0.000745722L 73.1365 0L 9.3853 0C 6.81059 0 4.55556 0.969876 2.69921 2.69932C 0.924157 4.35344 0 6.40953 0 8.74492L 0 142.515L 18.7701 142.515L 18.7701 86.8257L 45.7768 86.8257Z" transform="translate(211.163 0)" fill="#23292F"/>
                </g>
            </g>
        </svg> NFT
    </div>
    <div id="container">
        <div id="card">
            <video controls src="{{ meta.details.link }}" poster="{{ meta.details.cover }}" width="620">
                Sorry, your browser doesn't support embedded video :-(
                <a href="{{ meta.details.link }}"><img src="{{ meta.details.cover }}"/>click here to play directly</a>
            </video>
        </div>
        <div id="content">
            <h1>{{ meta.details.title }}</h1>
            <p> {{ meta.details.description | nl2br }}</p>
            <table class="styled-table">
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Value</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Author</td>
                        <td>{{ meta.author.name }}</td>
                    </tr>
                    <tr>
                        <td>Author Wallet</td>
                        <td>{{ meta.author.wallet }}</td>
                    </tr>
                    <tr>
                        <td>Author Email</td>
                        <td>{{ meta.author.email }}</td>
                    </tr>
                    <tr>
                        <td>Author Twitter</td>
                        <td>{{ meta.author.twitter | nl2br }}</td>
                    </tr>
                    <tr>
                        <td>Author Website</td>
                        <td>{{ meta.author.website }}</td>
                    </tr>
                    <tr>
                        <td>Author Bio</td>
                        <td>{{ meta.author.bio | nl2br }}</td>
                    </tr>
                    {% if meta.author.payId %}
                    <tr>
                        <td>Author PayString</td>
                        <td>{{ meta.author.payId}}</td>
                    </tr>
                    {% endif %}
                    {% if meta.staticILPAddress %}
                    <tr>
                        <td>Payment Pointer</td>
                        <td>{{ meta.staticILPAddress }}</td>
                    </tr>
                    {% endif %}
                    {% if meta.honorDynamicILPAddress %}
                    <tr>
                        <td>Allow Dynamic Payment Pointer</td>
                        <td>{{ meta.honorDynamicILPAddress }}</td>
                    </tr>
                    {% endif %}
                    <tr>
                        <td>Title</td>
                        <td>{{ meta.details.title }}</td>
                    </tr>
                    <tr>
                        <td>Description</td>
                        <td>{{ meta.details.description | nl2br}}</td>
                    </tr>
                    <tr>
                        <td>NFT X Address</td>
                        <td>{{ meta.details.NFTWalletXAddress }}</td>
                    </tr>
                    <tr>
                        <td>NFT Classic Address</td>
                        <td>{{ meta.details.NFTWalletAddress }}</td>
                    </tr>
                    {% if meta.webHostingURI %}
                    <tr>
                        <td>WebSeed Base URI</td>
                        <td>{{ meta.webHostingURI }}</td>
                    </tr>
                    {% endif %}
                    <tr>
                        <td>Legal Notice</td>
                        <td>{{ meta.details.legal | nl2br}}</td>
                    </tr>
                    {% asyncEach obj in meta.hashes %}
                        <tr>
                            <td>{{ obj.file }}</td>
                            <td>SHA256: {{ obj.sha256 }} <br/>CID: {{ obj.cid }}</td>
                        </tr>
                    {% endeach %}
                    <tr>
                        <td>Created at</td>
                        <td>{{ meta.created }}</td>
                    </tr>
                    <tr>
                        <td>NFT Builder</td>
                        <td>{{ meta.framework }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
    <script>
        //Stop video moving on play
        const video = document.querySelector('video');
        video.addEventListener('play', (event) => {
            document.getElementById("card").getAnimations()[0].pause();
        });
        //Start video moving on pause
        video.addEventListener('pause', (event) => {
            document.getElementById("card").getAnimations()[0].play();
        });

        //Floaters
        var canvas = document.getElementById("canvas");
        var ctx = canvas.getContext("2d");
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        var particles = [];

        var Particle = function () {
            this.x = canvas.width * Math.random();
            this.y = canvas.height * Math.random();
            this.vx = 4 * Math.random() - 2;
            this.vy = 4 * Math.random() - 2;
            this.Color = "rgb(255, 255, 255)";
        }
        Particle.prototype.Draw = function (ctx) {
            ctx.fillStyle = this.Color;
            ctx.fillRect(this.x, this.y, 2, 2);
        }
        Particle.prototype.Update = function () {
            this.x += this.vx;
            this.y += this.vy;
        
            if (this.x<0 || this.x > canvas.width)
                this.vx = -this.vx;
        
            if (this.y < 0 || this.y > canvas.height)
                this.vy = -this.vy;
        }
        function loop() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (var i = 0; i < 45; i++) {
                particles[i].Update();
                particles[i].Draw(ctx);
            }
            requestAnimationFrame(loop);
        }
        //Create particles
        for (var i = 0; i < 45; i++)
            particles.push(new Particle());
        loop();
    </script>
</html>
