<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Showcase</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: "Quintessential", serif;
            
        }
        .name1{
          font-size: 35px;
         
        }
        .container{
          display: flex;
          flex-direction: column;
        }
        /* Styles for the modal transition */
        .modal {
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        .modal.hidden {
            opacity: 0;
            visibility: hidden;
        }
        .modal-content {
            transition: transform 0.3s ease;
        }
        .modal.hidden .modal-content {
            transform: scale(0.95);
        }
        /* Basic markdown-like styling for rendered HTML */
        .prose {
            max-width: 65ch;
            color: #d1d5db;
        }
        .prose h1, .prose h2, .prose h3 { color: #fff; }
        .prose a { color: #a78bfa; text-decoration: none; }
        .prose a:hover { color: #c4b5fd; }
        .prose img { border-radius: 0.75rem; margin-left: auto; margin-right: auto; }
        .prose code { background-color: #374151; padding: 0.2em 0.4em; margin: 0; font-size: 85%; border-radius: 3px; }
        .prose pre { background-color: #1f2937; padding: 1rem; border-radius: 0.5rem; overflow-x: auto;}
        .prose ul { list-style-position: inside; }
        .prose li { margin-top: 0.25em; }
    </style>
</head>
<body class="bg-gray-900 text-white">

    <div class="relative min-h-screen p-4 sm:p-8">
        <div class="absolute top-0 left-0 w-full h-full bg-cover bg-center opacity-10" style="background-image: url('https://www.transparenttextures.com/patterns/cubes.png')"></div>
        <div class="container mx-auto max-w-7xl relative z-10">
            
            <header class="text-center mb-12">
                <div class="inline-flex items-center justify-center bg-purple-500/10 text-purple-300 rounded-full p-4 mb-4">
                    <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
                </div>
                <h1 class="text-4xl sm:text-5xl md:text-6xl font-extrabold tracking-tight"> Profile Showcase</h1>
                <p class="mt-4 text-lg text-gray-400 max-w-2xl mx-auto">A collection of creative and impressive developer profiles from across the community.</p>
            </header>

            <main>
                <!-- How to Add Section -->
                <div class="bg-gray-900/50 border border-gray-700 rounded-xl p-8 mb-12 backdrop-blur-sm">
                    <h2 class="text-2xl font-bold text-white mb-4 flex items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mr-3 text-purple-400"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><line x1="19" x2="19" y1="8" y2="14"></line><line x1="22" x2="16" y1="11" y2="11"></line></svg>
                        How to Add Your Profile
                    </h2>
                    <div class="space-y-4 text-gray-300">
                      <p><strong class="text-purple-400">Step 1:</strong> Make sure you have a public GitHub repository named exactly like your username (e.g., <code class="bg-gray-700 px-1 rounded">GihanIT/GihanIT</code>).</p>
                      <p><strong class="text-purple-400">Step 2:</strong> Create a <code class="bg-gray-700 px-1 rounded">README.md</code> file in that repository with your desired profile content.</p>
                      <p><strong class="text-purple-400">Step 3:</strong> To add it to this website, you'll need to edit this HTML file. Find the <code class="bg-gray-700 px-1 rounded">profilesData</code> array inside the <code class="bg-gray-700 px-1 rounded">&lt;script&gt;</code> tag at the bottom.</p>
                      <p><strong class="text-purple-400">Step 4:</strong> Copy the raw content of your <code class="bg-gray-700 px-1 rounded">README.md</code> file and add a new object to the array in the specified format.</p>
                    </div>
                </div>

                <!-- Profile Cards Grid -->
                <div id="profiles-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Profile cards will be injected here by JavaScript -->
                </div>
            </main>
            
            <footer class="text-center mt-16 text-gray-500">
                <p>Built with HTML, Tailwind CSS & JavaScript.</p>
            </footer>

        </div>
    </div>

    <!-- Modal for displaying profile -->
    <div id="profile-modal" class="modal hidden fixed inset-0 bg-black bg-opacity-70 z-50 flex justify-center items-center p-4 backdrop-blur-sm">
        <div id="modal-content" class="modal-content relative bg-gray-900 border border-gray-700 rounded-2xl w-full max-w-4xl max-h-[90vh] overflow-y-auto shadow-2xl shadow-purple-500/10">
            <button id="modal-close-btn" class="sticky top-4 right-4 float-right text-gray-400 hover:text-white bg-gray-800 rounded-full p-2 transition-colors z-10" aria-label="Close profile view">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
            </button>
            <div id="modal-body" class="p-8 prose">
                <!-- Profile content will be injected here -->
            </div>
        </div>
    </div>

    <script>
        // --- PROFILE DATA ---
        const profilesData = [
            {
                username: 'avinash201199',
                readmeContent: `
                  <h1 class="name1">Avinash</h1> 

                  <hr>

                  <p align="center">
                    <img alt="GIF" src="https://media.giphy.com/media/Cmr1OMJ2FN0B2/giphy.gif" width="200"/>
                  </p>
                  <h1>Hello world, I'm Avinash 👋</h1> 

                  <hr>

                  <p>
                    <img src="https://komarev.com/ghpvc/?username=avinash201199&color=red" alt="profile count"/>&nbsp;
                    <a href="https://github.com/avinash201199"><img src="https://img.shields.io/github/followers/avinash201199?label=follow&style=social" alt="GitHub followers"/></a>&nbsp;
                  </p>

                  <h3>👨🏻‍💻 &nbsp;About Me</h3>

                  <p>
                    💡 &nbsp; Hello everyone,I'm engineering student. Love to code , exploring Data Science these days. I enjoy collaborating with people on works of similar interest. 
                  </p>
                  <p>
                    🌱 &nbsp;I'm on track for learning more about Artificial Intelligence, Machine learning and Data Science.<br>
                    ✍️ &nbsp;Apart from technical interests, I like dancing,watching movies, reading novels, playing Chess and badminton.<br>
                    💬 &nbsp;Feel free to reach out to me for general consulting, or discussions <br>
                    ✉️ &nbsp;You can email me at avinash201199@gmail.com. I'll try to respond as soon as possible!<br>
                    📄 &nbsp;You can check my <a href="https://drive.google.com/file/d/1K4-g2LlUJFHv-JzBtrBBSeBOUiRN1-iQ/view?usp=sharing">Resume</a> for more details about work experience.
                  </p>

                  <hr>

                  <h3>📫 &nbsp; How to reach me:</h3>
                  <p>
                    <a href="https://www.linkedin.com/in/avinash-singh-071b79175/"><img alt="LinkedIn" src="https://img.shields.io/badge/linkedin%20-%230077B5.svg?&style=flat&logo=linkedin&logoColor=white"/></a> &nbsp;
                    <a href="https://instagram.com/michael201199/"><img src="https://img.shields.io/badge/-@michael201199-E4405F?style=flat&logo=Instagram&logoColor=white"/></a> &nbsp;
                    <a href="mailto:avinash201199@gmail.com"><img alt="Gmail" src="https://img.shields.io/badge/Gmail-D14836?style=flat&logo=gmail&logoColor=white" /></a> &nbsp;
                    <a href="https://www.hackerrank.com/avinash201199"><img src="https://img.shields.io/badge/-HackerRank-E4405F?style=flat&logo=HackerRank&logoColor=white"/></a> &nbsp;
                    <a href="https://leetcode.com/avinash201199/"><img src="https://img.shields.io/badge/-LeetCode-E4405F?style=flat&logo=LeetCode&logoColor=white"/></a> &nbsp;
                  </p>

                  <hr>  

                  <h1 align="center">Projects</h1>
                  <table>
                    <thead>
                      <tr>
                        <th>Project Name</th>
                        <th>Description</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td><a href="http://arisesociety.org/">Dynamic Website</a></td>
                        <td>Project on developing a fully working dynamic website using PHP and MySQL for the NGO. <a href="http://arisesociety.org/">http://arisesociety.org/</a></td>
                      </tr>
                      <tr>
                        <td><a href="https://avinash201199.github.io/MemeGenerator/">Meme Generator</a></td>
                        <td>This is a React js project , using this website you can create famouse memes only by adding words and you cat download it to your system.</td>
                      </tr>
                      <tr>
                        <td><a href="https://github.com/avinash201199/Python-Projects/blob/main/Tic_Tac_Toe.py">Tic Tac Toe</a></td>
                        <td>A game in which two players alternately put Xs and Os in compartments of a figure formed by two vertical lines crossing two horizontal lines and each tries to get a row of three Xs or three Os before the opponent does</td>
                      </tr>
                      <tr>
                        <td><a href="https://avinash201199.github.io/Portfolio/">Personal Portfolio</a></td>
                        <td>This is my personal personal-portfolio website. Have a look <a href="https://avinash201199.github.io/Portfolio/">https://avinash201199.github.io/Portfolio/</a></td>
                      </tr>
                    </tbody>
                  </table>

                  <hr>

                  <h1 align="center">Repositories to contribute in Hacktoberfest🤩</h1>
                  <table>
                    <thead>
                      <tr>
                        <th>Repository Name</th>
                        <th>Description</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td><a href="https://github.com/avinash201199/Hacktoberfest-Guide">Hacktoberfest Guide</a></td>
                        <td>Beginner's guide to Hacktoberfest and contains list of repositories where you can contribute.</td>
                      </tr>
                      <tr>
                        <td><a href="https://github.com/avinash201199/To-Do-List">To-Do-List</a></td>
                        <td>This is a javascript TO-Do-List app , you can contribute to this project by adding some extra feature or by improving UI/UX.</td>
                      </tr>
                      <tr>
                        <td><a href="https://github.com/avinash201199/Portfolio-Collection">Portfolio Collection</a></td>
                        <td>This repository contains collection of portfolio's . You can add your own repository.</td>
                      </tr>
                      <tr>
                        <td><a href="https://github.com/avinash201199/Competitions-and-Programs-List">Competition List</a></td>
                        <td>List of competitions for college students to participate and to enhance their skills.</td>
                      </tr>
                      <tr>
                        <td><a href="https://github.com/avinash201199/Free-courses-with-Certificates">Free courses with certificate</a></td>
                        <td>This repository contains list of free courses with certificates. Go ahead and add more courses in your knowledge.</td>
                      </tr>
                      <tr>
                        <td><a href="https://github.com/avinash201199/Python-projects-">Python-Projects</a></td>
                        <td>This repository contains Python project to contribute</td>
                      </tr>
                    </tbody>
                  </table>

                  <h3>Languages and Tools</h3>
                  <div class=container1>
                    <p>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/python/python-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/java/java-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/google_cloud/google_cloud-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/kaggle/kaggle-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/numpy/numpy-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/quora/quora-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/w3_html5/w3_html5-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/w3_css/w3_css-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/javascript/javascript-horizontal.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/getbootstrap/getbootstrap-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/djangoproject/djangoproject-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/pocoo_flask/pocoo_flask-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/jupyter/jupyter-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/mysql/mysql-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/docker/docker-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/kubernetes/kubernetes-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/amazon_aws/amazon_aws-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/git-scm/git-scm-ar21.svg"></code>
                      <code><img width="15%" src="https://www.vectorlogo.zone/logos/ubuntu/ubuntu-ar21.svg"></code>
                    </p>
                </div>

                  <hr>
                    
                  <h1 align="center">Github Stats</h1>

                  <div align="center">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=avinash201199&theme=highcontrast" alt="GitHub streak"/>
                  </div>

                  <img align="left" alt="Avinash's Github Stats" src="https://github-readme-stats.vercel.app/api?username=avinash201199&&show_icons=true&theme=dark" width="50%" />
                  <img alt="Top Languages used" src="https://github-readme-stats.vercel.app/api/top-langs/?username=avinash201199&layout=compact&theme=dark" width="46%" />
                  <br>
                  <img src="https://activity-graph.herokuapp.com/graph?username=avinash201199&theme=xcode" alt="Activity Graph">
    `
            },
            {
                username: 'GihanIT',
                readmeContent: `
                <h1 class="name1">Gihan Harindra </h1>
                   <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1 align="center">Hi , I'm Gihan Harindra <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="35"></h1>
                  <div align="center">
                    <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?lines=ICT+Teacher/Instructor;Cyber+Security+Researcher;Developer;IT+Administrator;Blogger;Always+learning+new+things&center=true&width=700&height=70" alt="Typing SVG"></a>
                  </div>
                  <p><img align="right" src="https://raw.githubusercontent.com/SubhadeepZilong/SubhadeepZilong/main/icons/animation_500_kxa883sd.gif" alt="Animation" /></p>
                  
                  <h2>👀 Interests</h2>
                  <ul>
                    <li>ICT teaching and tutoring</li>
                    <li>Creating engaging and practical educational content for learners</li>  
                    <li>Building ICT courses for students aged 10 and above</li>
                  </ul>
                  
                  <h2>🌱 Currently Learning</h2>
                  <ul>
                    <li>Programming, Cyber Security, Computer Networks and Tutoring</li>
                    <li>Exploring other tech-related topics to improve teaching skills</li>
                  </ul>
                  
                  <h2>💞️ Looking to Collaborate On</h2>  
                  <ul>
                    <li>Developing ICT educational resources</li>
                    <li>Enhancing teaching methodologies for young learners</li>
                  </ul>
                  
                  <hr>
                  <h1>Languages and Tools</h1>
                  
                  <p align="center">
                    <a href="https://skillicons.dev">
                      <img src="https://skillicons.dev/icons?i=git,aws,cpp,css,discord,docker,postgres,prisma,pug,dynamodb,express,figma,firebase,redis,github,html,java,js,linux,md,materialui,nginx,mongodb,mysql,nextjs,nodejs,postman,py,react,redux,tailwind,ts,vscode,kubernetes&perline=14" alt="Skills"/>
                    </a>
                  </p>
                  
                  <hr>
                  <h1>My GitHub Stats</h1>
                  <table align="center" style="width:100%">
                  <tr border="none">
                  <td width="50%" align="center" style="vertical-align: top;">
                    <img align="center" src="https://github-readme-stats.vercel.app/api?username=GihanIT&theme=dark&show_icons=true&count_private=true" />
                    <br><br>
                    <img title="🔥 Get streak stats for your profile at git.io/streak-stats" alt="Mark streak" src="https://github-readme-streak-stats.herokuapp.com/?user=GihanIT&theme=dark&hide_border=false" /> 
                  </td>
                  <td width="50%" align="center" style="vertical-align: top;">
                    <img align="center" src="https://github-readme-stats.anuraghazra1.vercel.app/api/top-langs/?username=GihanIT&theme=dark&hide_border=false&no-bg=true&no-frame=true&langs_count=10"/>
                  </td>
                  </tr>
                  </table>
                  
                  <hr>
                  <div align=center>
                    <a href="https://github.com/ryo-ma/github-profile-trophy" title="Go to Source">
                        <img align="center" width=84% src="https://github-profile-trophy.vercel.app/?username=GihanIT&theme=radical&row=1&column=7&margin-h=15&margin-w=5&no-bg=true" alt="TROPHY" />
                      </a>
                  </div>
                  <hr>
                  <h2 align="center">Connect With Me🤝</h2>
                  <p align="center">
                  <a href="https://www.linkedin.com/in/gharindra/" target="blank"><img align="center" src="https://user-images.githubusercontent.com/88904952/234979284-68c11d7f-1acc-4f0c-ac78-044e1037d7b0.png" alt="linkedin" height="50" width="50" /></a>
                  <a href="https://x.com/gihan_harindra" target="blank"><img align="center" src="https://user-images.githubusercontent.com/88904952/234980676-61bfb021-ecc8-48f7-88e6-34c1b06c4a58.png" alt="twitter" height="50" width="50" /></a> 
                  <a href="" target="blank"><img align="center" src="https://user-images.githubusercontent.com/88904952/234981169-2dd1e58f-4b7e-468c-8213-034ba62156c3.png" alt="instagram" height="50" width="50" /></a>
                  <a href="https://about.me/gihanharindra" target="blank"><img align="center" src="https://user-images.githubusercontent.com/88904952/234982196-562aea17-5532-4550-8c08-1c7cb994a541.png" alt="hashnode" height="50" width="50" /></a>
                  <a href="https://web.facebook.com/ICTDiff" target="blank"><img align="center" src="https://user-images.githubusercontent.com/88904952/234982627-019fd336-6248-453c-9b05-97c13fd1d207.png" alt="discord" height="50" width="50" /></a>
                  </p>
                  <hr>
                  <div align="center">
                    <p>Feel free to update this profile as your interests and projects grow! 😊</p>
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Footer GIF">
                  </div>
                `
            },
            {
                username: 'Dhruva Bhat',
                readmeContent: `
                  <h1 class="name1">Dhruva Bhat</h1>
                   <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <br></br>
                <div allign="center">
                  <h1 align="center">Hi 👋, I'm Dhruva Bhat S N</h1>
                  <h1 allign="center">A passionate web-developer from India</h1>

                  <p align="left"> <img src="https://komarev.com/ghpvc/?username=dhruvabhat24&label=Profile%20views&color=00ff00&style=plastic" alt="dhruvabhat24" /> </p>

                  <p align="left"> 
                    <a href="https://github.com/ryo-ma/github-profile-trophy">
                      <img src="https://github-profile-trophy.vercel.app/?username=dhruvabhat24&theme=radical" alt="dhruvabhat24" />
                    </a>
                  </p>

                  <p align="left"> 
                    <a href="https://twitter.com/dhruvabhat9" target="blank">
                      <img src="https://img.shields.io/twitter/follow/dhruvabhat9?logo=twitter&style=for-the-badge" alt="dhruvabhat9" />
                    </a>
                  </p>

                  - 🔭 I’m currently working on **Autonomous Telemetry Hub**
                  - 🌱 I’m currently learning **ReactJs, Node.js, DSA, Threejs**
                  - 👨‍💻 All of my projects are available at [https://dhruvabhat.netlify.app/](https://dhruvabhat.netlify.app/)
                  - 💬 Ask me about **Java HTML CSS JavaScript**
                  - 📫 How to reach me **dhruvabhat24@gmail.com dhruvabhat2003@gmail.com**
                  - ⚡ Fun fact **I am not only a man behind the computer.**

                  ### Connect with me:
                  <p align="left">
                    <a href="https://codepen.io/dhruvabhat24" target="blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/codepen.svg" alt="dhruvabhat24" height="30" width="40" />
                    </a>
                    <a href="https://twitter.com/dhruvabhat9" target="blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="dhruvabhat9" height="30" width="40" />
                    </a>
                    <a href="https://linkedin.com/in/dhruva bhat" target="blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="dhruva bhat" height="30" width="40" />
                    </a>
                    <a href="https://instagram.com/dhruv__bhat_05" target="blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="dhruv__bhat_05" height="30" width="40" />
                    </a>
                  </p>
                </div>
                `
            },
            {
                username: 'Sagar Chhabriya',
                readmeContent: `
                <h1 class="name1">Sagar Chhabriya</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
             <img width="100%" src="https://github.com/user-attachments/assets/2af29d74-629a-45c2-9f8b-bb3551138679" alt="Sagar Chhabriya Banner">
      
                  <h1>✨ About Me:</h1> 
                  <ul>
                    <li>👋 Yo, I’m @SagarChhabriya</li>
                    <li>👀 I’m interested in Machine Learning, AI, Data Science, Data Structures and Python.</li>
                    <li>🌱 I’m currently learning GenAI and AgenticAI.</li>
                    <li>💞️ Let’s build something epic in AI!</li>
                    <li>📫 How to reach me? Good question!</li>
                    <li>😄 Pronouns: He/Him</li>  
                    <li>⚡ Fun fact: I come from the decoits’ domain!</li>
                  </ul>

                  <p>Proud to share that I have successfully passed the <a href="https://www.credly.com/badges/ad76b653-1048-4090-bcf6-605bf97148ad/print"><strong>GitHub Foundations Exam</strong></a>, validating my proficiency in core GitHub workflows and best practices.</p>

                  <br><br>

                  <h2>My Project Portfolio</h2>

                  <h3>🤖 AI & Machine Learning</h3>
                  <table>
                    <thead>
                      <tr>
                        <th>Project</th> <th>Tech Stack</th> <th>Description</th> <th>Live Demo</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td><strong>CallRag</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/Google_Gemini-4285F4?logo=google&logoColor=white" alt="Gemini"> <img src="https://img.shields.io/badge/LlamaIndex-FF6B00" alt="LlamaIndex"> <img src="https://img.shields.io/badge/PyMuPDF-1.7.0-blue" alt="PyMuPDF"> <img src="https://img.shields.io/badge/PDFPlumber-0.9.0-orange" alt="PDFPlumber"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>RAG-powered chatbot</td> <td><a href="https://callrag.streamlit.app/"><img src="https://static.streamlit.io/badges/streamlit_badge_black_white.svg" alt="Streamlit"></a></td>
                      </tr>
                      <tr>
                        <td><strong>IRIS Classifier</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white" alt="Scikit-learn"> <img src="https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white" alt="Pandas"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Flower species predictor</td> <td><a href="https://irislab.streamlit.app/"><img src="https://static.streamlit.io/badges/streamlit_badge_black_white.svg" alt="Streamlit"></a></td>
                      </tr>
                    </tbody>
                  </table>

                  <h3>📊 Data Applications</h3>
                  <table>
                    <thead>
                      <tr>
                        <th>Project</th> <th>Tech Stack</th> <th>Description</th> <th>Live Demo</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td><strong>Up Stock</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/yFinance-00A86B?logo=yahoo&logoColor=white" alt="yFinance"> <img src="https://img.shields.io/badge/Matplotlib-11557C" alt="Matplotlib"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Stock market tracker</td> <td><a href="https://upstok.streamlit.app/"><img src="https://static.streamlit.io/badges/streamlit_badge_black_white.svg" alt="Streamlit"></a></td>
                      </tr>
                      <tr>
                        <td><strong>Salary Predictor</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white" alt="Scikit-learn"> <img src="https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white" alt="NumPy"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Salary estimation tool</td> <td><a href="https://sal-pred.streamlit.app/"><img src="https://static.streamlit.io/badges/streamlit_badge_black_white.svg" alt="Streamlit"></a></td>
                      </tr>
                      <tr>
                        <td><strong>California Housing</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white" alt="Pandas"> <img src="https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white" alt="Scikit-learn"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Housing price predictor</td> <td><a href="https://calihouse.streamlit.app/"><img src="https://static.streamlit.io/badges/streamlit_badge_black_white.svg" alt="Streamlit"></a></td>
                      </tr>
                    </tbody>
                  </table>

                  <h3>Python</h3>
                  <table>
                    <thead>
                      <tr>
                        <th>Project</th> <th>Tech Stack</th> <th>Description</th> <th>Source</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td><strong>Email Automator</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/SMTP-1AB394?logo=mail.ru&logoColor=white" alt="SMTP"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Bulk email sender</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_python-automation-emailmarketing-activity-7187093664467247106-e7xZ"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                      <tr>
                        <td><strong>Expense Tracker</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white" alt="SQLite"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Personal finance manager</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_python-codealpha-expensetracker-activity-7183180948593590273-duvj"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                      <tr>
                        <td><strong>Jarvis AI</strong></td> <td><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/Speech_Recognition-3776AB" alt="SpeechRecognition"> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></td> <td>Voice-controlled assistant</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_gratitude-thankyou-techcommunity-activity-7180446935051288577-c2Sw"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                    </tbody>
                  </table>

                  <h3>☕ Java Applications</h3>
                  <table>
                    <thead>
                      <tr>
                        <th>Project</th> <th>Tech Stack</th> <th>Description</th> <th>Source</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td><strong>Currency Converter</strong></td> <td><img src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white" alt="Java"></td> <td>Forex conversion tool</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_currencyconverter-softwaredevelopment-codealpha-activity-7120795865622953984-EQMX"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                      <tr>
                        <td><strong>Attendance System</strong></td> <td><img src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white" alt="Java"> <img src="https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white" alt="MySQL"></td> <td>College attendance manager</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_codealphatriumphs-activity-7124734439116447744-jdnA"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                      <tr>
                        <td><strong>Word Counter</strong></td> <td><img src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white" alt="Java"></td> <td>Text analysis tool</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_codealpha-javainternship-progressmade-activity-7114224780936945667-Y97o"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                      <tr>
                        <td><strong>Health Keeper</strong></td> <td><img src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white" alt="Java"></td> <td>Fitness tracking app</td> <td><a href="https://www.linkedin.com/posts/sagar-chhabriya_secondsemester-javaprogramming-objectoriented-activity-7095314588090441731-GSjU"><img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" alt="LinkedIn"></a></td>
                      </tr>
                    </tbody>
                  </table>

                  <h2>My Tech Stack</h2>
                  <p>
                    <img src="https://img.shields.io/badge/c++-%2300599C.svg?style=plastic&logo=c%2B%2B&logoColor=white" alt="C++">
                    <img src="https://img.shields.io/badge/css3-%231572B6.svg?style=plastic&logo=css3&logoColor=white" alt="CSS3">
                    <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=plastic&logo=html5&logoColor=white" alt="HTML5">
                    <img src="https://img.shields.io/badge/java-%23ED8B00.svg?style=plastic&logo=openjdk&logoColor=white" alt="Java">
                    <img src="https://img.shields.io/badge/python-3670A0?style=plastic&logo=python&logoColor=ffdd54" alt="Python">
                    <img src="https://img.shields.io/badge/mysql-%2300000f.svg?style=plastic&logo=mysql&logoColor=white" alt="MySQL">
                    <img src="https://img.shields.io/badge/MongoDB-%234EA94B.svg?style=plastic&logo=mongodb&logoColor=white" alt="MongoDB">
                    <img src="https://img.shields.io/badge/SQLite-%2307405E.svg?style=plastic&logo=sqlite&logoColor=white" alt="SQLite">
                    <img src="https://img.shields.io/badge/NumPy-%23013243.svg?style=plastic&logo=numpy&logoColor=white" alt="NumPy">
                    <img src="https://img.shields.io/badge/Pandas-%23150458.svg?style=plastic&logo=pandas&logoColor=white" alt="Pandas">
                    <img src="https://img.shields.io/badge/SciPy-%230C55A5.svg?style=plastic&logo=scipy&logoColor=white" alt="SciPy">
                    <img src="https://img.shields.io/badge/Seaborn-%2343B02A.svg?style=plastic&logoColor=white" alt="Seaborn">
                    <img src="https://img.shields.io/badge/Matplotlib-%23F37626.svg?style=plastic&logo=matplotlib&logoColor=white" alt="Matplotlib">
                    <img src="https://img.shields.io/badge/Plotly-%233F4F75.svg?style=plastic&logo=plotly&logoColor=white" alt="Plotly">
                    <img src="https://img.shields.io/badge/Flask-%23000.svg?style=plastic&logo=flask&logoColor=white" alt="Flask">
                    <img src="https://img.shields.io/badge/Beautiful%20Soup-%234EAA25.svg?style=plastic&logoColor=white" alt="Beautiful Soup">
                    <img src="https://img.shields.io/badge/Selenium-%2343B02A.svg?style=plastic&logo=selenium&logoColor=white" alt="Selenium">
                    <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=plastic&logo=scikit-learn&logoColor=white" alt="scikit-learn">
                    <img src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=plastic&logo=tensorflow&logoColor=white" alt="TensorFlow">
                    <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=plastic&logo=pytorch&logoColor=white" alt="PyTorch">
                    <img src="https://img.shields.io/badge/PyPDF2-%23FFD43B.svg?style=plastic&logoColor=white" alt="PyPDF2">
                    <img src="https://img.shields.io/badge/Streamlit-%23FF4B4B.svg?style=plastic&logo=streamlit&logoColor=white" alt="Streamlit">
                    <img src="https://img.shields.io/badge/FastAPI-%2307405E.svg?style=plastic&logoColor=white" alt="FastAPI">
                    <img src="https://img.shields.io/badge/Django-%23092E20.svg?style=plastic&logo=django&logoColor=white" alt="Django">
                    <img src="https://img.shields.io/badge/Docker-%230db7ed.svg?style=plastic&logo=docker&logoColor=white" alt="Docker">
                    <img src="https://img.shields.io/badge/Postman-%23FF6C37.svg?style=plastic&logo=postman&logoColor=white" alt="Postman">
                    <img src="https://img.shields.io/badge/Git-%23F05032.svg?style=plastic&logo=git&logoColor=white" alt="Git">
                    <img src="https://img.shields.io/badge/GitHub%20Actions-%232671E5.svg?style=plastic&logo=githubactions&logoColor=white" alt="GitHub Actions">
                    <img src="https://img.shields.io/badge/GitHub%20Codespaces-%23000000.svg?style=plastic&logo=github&logoColor=white" alt="GitHub Codespaces">
                    <img src="https://img.shields.io/badge/GitLab-%23FC6D26.svg?style=plastic&logo=gitlab&logoColor=white" alt="GitLab">
                    <img src="https://img.shields.io/badge/Bitbucket-%230047B3.svg?style=plastic&logo=bitbucket&logoColor=white" alt="Bitbucket">
                    <img src="https://img.shields.io/badge/Linux-%23FCC624.svg?style=plastic&logo=linux&logoColor=black" alt="Linux">
                    <img src="https://img.shields.io/badge/Ubuntu-%23E95420.svg?style=plastic&logo=ubuntu&logoColor=white" alt="Ubuntu">
                    <img src="https://img.shields.io/badge/Kali%20Linux-%2300ADEE.svg?style=plastic&logo=kalilinux&logoColor=white" alt="Kali Linux">
                    <img src="https://img.shields.io/badge/Windows-%230078D6.svg?style=plastic&logo=windows&logoColor=white" alt="Windows">
                    <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=plastic&logo=langchain&logoColor=white" alt="LangChain">
                    <img src="https://img.shields.io/badge/OpenAI-000000?style=plastic&logo=openai&logoColor=white" alt="OpenAI">
                    <img src="https://img.shields.io/badge/Hugging%20Face-FF4F75?style=plastic&logo=huggingface&logoColor=white" alt="Hugging Face">
                    <img src="https://img.shields.io/badge/Faiss-1C3C3C?style=plastic&logo=faiss&logoColor=white" alt="Faiss">
                    <img src="https://img.shields.io/badge/Chroma-FF6F00?style=plastic&logo=chroma&logoColor=white" alt="Chroma">
                    <img src="https://img.shields.io/badge/LlamaIndex-FF6F00?style=plastic&logo=llamaindex&logoColor=white" alt="LlamaIndex">
                    <img src="https://img.shields.io/badge/GoogleGenAI-4285F4?style=plastic&logo=google&logoColor=white" alt="GoogleGenai">
                  </p>
                `
            },
            {
                username: 'PravasMohanty',
                readmeContent: `
                  <h1 class="name1">Pravas Mohanty</h1>
                   <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1 align="center">Hello world , Pravas this side ⚔️</h1>
                  <p align="center">
                    <img src="https://github.com/PravasMohanty/PravasMohanty/blob/main/banner.png?raw=true" alt="banner" width="800">
                  </p>

                  <h2>💫 About Me:</h2>
                  <p>I’m a student at the <strong>Indian Institute of Information Technology, Tiruchirappalli (IIIT Trichy)</strong>, passionate about technology and problem-solving. <br><br> I enjoy building <strong>full-stack applications</strong> and exploring <strong>machine learning</strong> and <strong>AI-based projects</strong>. <br><br> I’m skilled in <strong>C, C++, Python, and JavaScript</strong>, with experience in <strong>MySQL</strong> and <strong>MongoDB</strong>. <br><br> In my free time, I practice <strong>data structures and algorithms</strong> and enjoy <strong>digital art and design</strong>. <br><br> I’m currently open to <strong>internship opportunities</strong> where I can learn, grow, and contribute meaningfully. 🚀</p>

                  <h2>🌐 Socials:</h2>
                  <p>
                    <a href="https://instagram.com/pravas.mohanty.99"><img src="https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white" alt="Instagram"></a>
                    <a href="https://linkedin.com/in/pravas-mohanty"><img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" alt="LinkedIn"></a>
                    <a href="mailto:pravasmohanty1000@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"></a>
                  </p>

                  <h1>💻 Tech Stack:</h1>
                  <p>
                    <img src="https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white" alt="C">
                    <img src="https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++">
                    <img src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
                    <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
                    <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript">
                    <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python">
                    <img src="https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript">
                    <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS">
                    <img src="https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase" alt="Firebase">
                    <img src="https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel">
                    <img src="https://img.shields.io/badge/netlify-%23000000.svg?style=for-the-badge&logo=netlify&logoColor=%2300C7B7" alt="Netlify">
                    <img src="https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB" alt="Express.js">
                    <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React">
                    <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="NodeJS">
                    <img src="https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white" alt="Vite">
                    <img src="https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white" alt="React Router">
                    <img src="https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB">
                    <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
                    <img src="https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white" alt="Figma">
                    <img src="https://img.shields.io/badge/adobe%20illustrator-%23FF9A00.svg?style=for-the-badge&logo=adobe%20illustrator&logoColor=white" alt="Adobe Illustrator">
                    <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="PyTorch">
                    <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn">
                    <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
                    <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
                    <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" alt="Matplotlib">
                    <img src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white" alt="TensorFlow">
                    <img src="https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white" alt="Git">
                    <img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
                  </p>
                  
                  <h1>📊 GitHub Stats:</h1>
                  <img src="https://github-readme-stats.vercel.app/api?username=PravasMohanty&theme=dark&hide_border=false&include_all_commits=false&count_private=false"><br>
                  <img src="https://nirzak-streak-stats.vercel.app/?user=PravasMohanty&theme=dark&hide_border=false"><br>
                  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=PravasMohanty&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact">

                  <h3>🔝 Top Contributed Repo</h3>
                  <img src="https://github-contributor-stats.vercel.app/api?username=PravasMohanty&limit=5&theme=dark&combine_all_yearly_contributions=true">

                  <hr>
                  <a href="https://visitcount.itsvg.in">
                    <img src="https://visitcount.itsvg.in/api?id=PravasMohanty&icon=0&color=6" alt="Visitor Count">
                  </a>
                `
            },
            {
                username: 'saurabhm6341',
                readmeContent: `
                <h1 class="name1">Saurabh Mishra</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <div align="center">
                    <img src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" width="150px" />
                  </div>

                  <div align="center">
                    <a href="https://git.io/typing-svg">
                      <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=700&size=24&pause=1000&color=00B894&center=true&vCenter=true&width=600&lines=Hi+there%2C+I'm+Saurabh+Mishra+👋;A+Passionate+MERN+Developer+Problem+Solver;Building+the+Web%2C+One+Pixel+at+a+Time." alt="Typing SVG" />
                    </a>
                  </div>

                  <hr>

                  <table>
                    <tr>
                      <td width="65%" valign="top">

                  <h3>🚀 About Me</h3>

                  <p>
                  I'm a <strong>MERN Developer</strong> and <strong>Problem Solver</strong> from <strong>Bhagalpur, India</strong>, passionate about creating beautiful, functional, and user-centric web experiences. I love solving complex problems and learning new technologies to bring ideas to life.
                  </p>

                  <ul>
                    <li>🌱 I’m currently exploring <strong>Advanced React Patterns</strong> & <strong>Backend Optimization</strong>.</li>
                    <li>💬 Ask me about <strong>MERN Stack, C++, and DSA</strong>.</li>
                    <li>📫 Reach me at: <a href="mailto:saurabhmishra6341@gmail.com"><strong>saurabhmishra6341@gmail.com</strong></a></li>
                    <li>👨‍💻 My portfolio is under construction 🏗️ — stay tuned!</li>
                  </ul>

                  <h3>🌐 Connect with Me</h3>

                  <p align="left">
                    <a href="https://linkedin.com/in/saurabh-mishra-57b08128b/" target="_blank">
                      <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn" height="30" width="40" />
                    </a>
                    <a href="https://www.codechef.com/users/saurabm6341" target="_blank">
                      <img src="https://cdn.jsdelivr.net/npm/simple-icons@3.1.0/icons/codechef.svg" alt="CodeChef" height="30" width="40" />
                    </a>
                    <a href="https://codeforces.com/profile/saurabhm116" target="_blank">
                      <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/codeforces.svg" alt="Codeforces" height="30" width="40" />
                    </a>
                    <a href="https://www.leetcode.com/nelxxbdfwo" target="_blank">
                      <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" alt="LeetCode" height="30" width="40" />
                    </a>
                    <a href="https://discord.gg/saurabhm6341_84759" target="_blank">
                      <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/discord.svg" alt="Discord" height="30" width="40" />
                    </a>
                  </p>

                  </td>
                  <td width="35%" align="center" valign="top">
                    <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" alt="Coding GIF" width="100%" />
                  </td>
                    </tr>
                  </table>

                  <hr>

                  <h3>🛠️ My Tech Stack</h3>

                  <p align="center">
                    <strong>Languages:</strong><br />
                    <img alt="C" src="https://img.shields.io/badge/C-%23A8B9CC.svg?style=for-the-badge&logo=c&logoColor=white" />
                    <img alt="C++" src="https://img.shields.io/badge/C++%20-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" />
                    <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
                    <img alt="HTML5" src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
                    <img alt="CSS3" src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" />
                    <br /><br />
                    <strong>Frontend Development:</strong><br />
                    <img alt="React" src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
                    <img alt="Tailwind CSS" src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" />
                    <br /><br />
                    <strong>Backend & Database:</strong><br />
                    <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" />
                    <img alt="Express.js" src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" />
                    <img alt="MongoDB" src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" />
                    <br /><br />
                    <strong>Tools & Platforms:</strong><br />
                    <img alt="Git" src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
                    <img alt="GitHub" src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
                    <img alt="Vercel" src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" />
                  </p>

                  <hr>

                  <h3>📊 My GitHub Stats & Activity</h3>

                  <div align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=saurabhm6341&show_icons=true&theme=vision-friendly-dark&include_all_commits=true&count_private=true" alt="GitHub Stats" width="49%" />
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=saurabhm6341&layout=compact&theme=vision-friendly-dark" alt="Top Languages" width="49%" />
                    <br /><br />
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=saurabhm6341&theme=dark&hide_border=true" alt="GitHub Streak" width="65%" />
                    <br /><br />
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=saurabhm6341&theme=react-dark&hide_border=true&area=true" alt="Activity Graph" />
                  </div>

                  <hr>

                  <h3>🏆 GitHub Trophies</h3>

                  <div align="center">
                    <img src="https://github-profile-trophy.vercel.app/?username=saurabhm6341&theme=dracula&column=7&margin-w=15&margin-h=15&no-frame=true" alt="GitHub Trophies" />
                  </div>

                  <hr>

                  <h3>✨ Open Source Contributions</h3>

                  <div align="center">
                    <details open>
                      <summary><strong>GirlScript Summer of Code '24 Contributor</strong></summary>
                      <br>
                      <img src="https://gssoc-dynamic-badges.vercel.app/api/saurabhm6341?year=2024Extd" alt="GSSOC '24 Badge"/>
                    </details>
                  </div>

                  <hr>

                  <h3>🐍 Watch my contributions slither!</h3>

                  <div align="center">
                    <img src="https://github.com/saurabhm6341/saurabhm6341/raw/output/github-contribution-grid-snake.svg" alt="Contribution Snake" />
                  </div>

                  <hr>

                  <div align="center">
                    <img src="https://komarev.com/ghpvc/?username=saurabhm6341&label=Profile%20Visitors&color=0e75b6&style=flat-square" alt="Profile Views" />
                    <br /><br />
                    <p>✨ Crafted with passion by <strong>Saurabh Mishra</strong> ✨</p>
                  </div>
                `
            },
            {
                username: 'Benji918',
                readmeContent: `
                <h1 class="name1">Benji</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h2>To known more about me:</h2>
                  <div id="header" align="center">
                    <div id="badges">
                  <a href="https://www.linkedin.com/in/ugobenjamin/">
                      <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/>
                    </a> 
                  <a href="https://twitter.com/code_benji">
                      <img src="https://img.shields.io/badge/Twitter-blue?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter Badge"/>
                    </a>
                  <a href="https://medium.com/@kodiugos">
                      <img src="https://img.shields.io/badge/Medium-black?style=for-the-badge&logo=medium&logoColor=white" alt="Medium Badge"/>
                    </a>
                  <a href="https://bencodes.framer.website">
                      <img src="https://img.shields.io/badge/Portfolio-yellow?style=for-the-badge&logo=portfolio&logoColor=white" alt="Portfolio Badge"/>
                    </a>
                  <a href="https://docs.google.com/document/d/1YiJdcXkQ1W4n66HVHGtJxICdUhMcuSwo/edit?usp=sharing&ouid=109017764854576173797&rtpof=true&sd=true">
                      <img src="https://img.shields.io/badge/Resume-red?style=for-the-badge&logo=resume&logoColor=white" alt="Resume Badge"/>
                    </a>
                  </div>
                  <br>

                    <img src="https://komarev.com/ghpvc/?username=Benji918&style=flat-square&color=blue" alt=""/>
                    <a href="https://wakatime.com/@959b7910-df4f-43db-8577-468cee8fbaff"><img src="https://wakatime.com/badge/user/959b7910-df4f-43db-8577-468cee8fbaff.svg" alt="Total time coded since Apr 1 2022" /></a>


                  <a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Source+Code+Pro&weight=500&pause=1000&color=0DBEF7&width=435&lines=API's+rule+the+world+%E2%9C%8C%EF%B8%8F" alt="Typing SVG"></a>

                    
                  <h3>💪 My Skill Set</h3>
                  <table><tr><td valign="top" width="33%">



                  ### Frontend  
                  <div align="center">  
                  <a href="https://getbootstrap.com/docs/3.4/javascript/" target="_blank"><img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/bootstrap-plain.svg" alt="Bootstrap" height="50" /></a> 

                  </div>

                  </td><td valign="top" width="33%">



                  ### Backend  
                  <div align="center">  
                  <a href="https://www.python.org/" target="_blank"><img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/python-original.svg" alt="Python" height="50" /></a>  
                  <a href="https://www.djangoproject.com/" target="_blank"><img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/django-original.svg" alt="Django" height="50" /></a>  
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/git-scm-icon.svg" alt="Git" height="50" /></a>
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/192108374-8da61ba1-99ec-41d7-80b8-fb2f7c0a4948.png" alt="Github" height="50" /></a> 
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/117207330-263ba280-adf4-11eb-9b97-0ac5b40bc3be.png" alt="Docker" height="50" /></a>  
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/192107854-765620d7-f909-4953-a6da-36e1ef69eea6.png" alt="HTTP" height="50" /></a>  
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/192107858-fe19f043-c502-4009-8c47-476fc89718ad.png" alt="REST" height="50" /></a>  
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/184117132-9e89a93b-65fb-47c3-91e7-7d0f99e7c066.png" alt="Pytest" height="50" /></a>  
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/182534006-037f08b5-8e7b-4e5f-96b6-5d2a5558fa85.png" alt="Kubernetes" height="50" /></a> 
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/192109061-e138ca71-337c-4019-8d42-4792fdaa7128.png" alt="Postman" height="50" /></a> 
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/183423775-2276e25d-d43d-4e58-890b-edbc88e915f7.png" alt="Flask" height="50" /></a> 
                  <a href="https://github.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/183868728-b2e11072-00a5-47e2-8a4e-4ebbb2b8c554.png" alt="CI/CD" height="50" /></a> 
                  </div>

                  </td><td valign="top" width="33%">



                  ### Databases  
                  <div align="center">  
                  <a href="https://www.postgresql.org/" target="_blank"><img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/postgresql-original-wordmark.svg" alt="PostgreSQL" height="50" /></a>  
                  <a href="https://www.mongodb.com/" target="_blank"><img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/mongodb-original-wordmark.svg" alt="MongoDB" height="50" /></a>
                  <a href="https://www.mongodb.com/" target="_blank"><img style="margin: 10px" src="https://github.com/marwin1991/profile-technology-icons/assets/136815194/82df4543-236b-4e45-9604-5434e3faab17" alt="SQlite" height="50" /></a>
                  <a href="https://www.mongodb.com/" target="_blank"><img style="margin: 10px" src="https://user-images.githubusercontent.com/25181517/182884894-d3fa6ee0-f2b4-4960-9961-64740f533f2a.png" alt="Redis" height="50" /></a>
                  </div>

                  </td></tr></table>  
                  
                  ### 💹 Stats 

                  <table>
                    <tr>
                      <td>
                        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Benji918&theme=vue-dark&hide_border=true" />
                      </td>
                      <td>
                        <a href="https://app.daily.dev/benji_code">
                          <img src="https://api.daily.dev/devcards/v2/wBpUa0kq5p8gmU93eVBuf.png?type=wide&r=vhi" width="652" alt="Ugochukwu Chukwukodinaka Benjamin's Dev Card"/>
                        </a>
                      </td>
                    </tr>
                  </table>

                  <img src="https://wakatime.com/share/@benji_codes/4eb31a48-2070-4743-af9d-5681c3ed1949.png" />

                  <br>

                  <a href="https://holopin.io/@benji918">
                    <img src="https://holopin.me/benji918" alt="An image of @benji918's Holopin badges, which is a link to view their full Holopin profile">
                  </a>
                  </div>
                `
            },
            {
                username: 'dakshgopani',
                readmeContent: `
                <h1 class="name1">Daksh Gopani</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1 align="center">
                    <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=28&pause=1000&color=2E9EF7&center=true&vCenter=true&width=600&lines=Hello+%F0%9F%91%8B+I'm+Daksh+Gopani;Computer+Engineering+Student;Backend+Developer;Problem+Solver" alt="Typing SVG" />
                  </h1>

                  <p align="center">
                    <em>A curious computer geek and lifelong learner from India 🇮🇳</em>
                  </p>

                  <p align="center">
                    <img src="https://komarev.com/ghpvc/?username=dakshgopani&label=Profile%20Views&color=0e75b6&style=flat-square" alt="Profile views" />
                    <a href="https://twitter.com/daksh79282672">
                      <img src="https://img.shields.io/twitter/follow/daksh79282672?logo=twitter&style=flat-square&color=1DA1F2" alt="Twitter Follow" />
                    </a>
                  </p>

                  <hr>

                  <h2>👨‍💻 About Me</h2>

                  <pre><code>name: Daksh Gopani
            located_in: India
            current_education: B.Tech in Computer Engineering
            institution: Dwarkadas J Sanghvi College of Engineering
            currently_learning: Backend Web Development
            interests: ["Web Development", "Problem Solving", "Open Source"]
            fun_fact: "I think I can't crack a funny joke 😄"
                  </code></pre>

                  <img align="right" alt="Coding" width="400" src="https://www.wingstechsolutions.com/wp-content/uploads/2022/03/full-stack-development.gif">

                  <h3>🚀 Quick Facts</h3>

                  <ul>
                    <li>🌱 Currently diving deep into <strong>Backend Web Development</strong></li>
                    <li>💼 Check out my portfolio: <a href="https://daksh36portfolio.netlify.app/">daksh36portfolio.netlify.app</a></li>
                    <li>📧 Reach me at: <strong>dakshgopani0123@gmail.com</strong></li>
                    <li>📄 View my <a href="https://drive.google.com/file/d/1A1szbjKNLho90SB-uRUtHQ8oI0-evmxy/view?usp=share_link">Resume</a></li>
                    <li>💡 Always open to collaborating on interesting projects</li>
                    <li>⚡ Fun fact: I think I can't crack a funny joke</li>
                  </ul>

                  <br clear="right"/>

                  <hr>

                  <h2>🛠️ Tech Stack</h2>

                  <h3>Languages</h3>
                  <p align="left">
                    <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" alt="C"/>
                    <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++"/>
                    <img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP"/>
                    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
                    <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
                  </p>

                  <h3>Databases & Tools</h3>
                  <p align="left">
                    <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL"/>
                    <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git"/>
                    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
                  </p>

                  <hr>

                  <h2>🌐 Connect With Me</h2>

                  <p align="left">
                    <a href="https://linkedin.com/in/daksh-gopani-a13993251" target="_blank">
                      <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
                    </a>
                    <a href="https://twitter.com/daksh79282672" target="_blank">
                      <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter"/>
                    </a>
                    <a href="https://www.hackerrank.com/dakshgopani0123" target="_blank">
                      <img src="https://img.shields.io/badge/HackerRank-2EC866?style=for-the-badge&logo=hackerrank&logoColor=white" alt="HackerRank"/>
                    </a>
                    <a href="mailto:dakshgopani0123@gmail.com">
                      <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
                    </a>
                  </p>

                  <hr>

                  <h2>📊 GitHub Statistics</h2>

                  <div align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=dakshgopani&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="GitHub Stats" height="170"/>
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=dakshgopani&theme=tokyonight&hide_border=true" alt="GitHub Streak" height="170"/>
                  </div>

                  <div align="center">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=dakshgopani&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages" height="170"/>
                  </div>

                  <hr>

                  <h2>🏆 GitHub Trophies</h2>

                  <div align="center">
                    <img src="https://github-profile-trophy.vercel.app/?username=dakshgopani&theme=tokyonight&no-frame=true&no-bg=true&row=1&column=7" alt="Trophies"/>
                  </div>

                  <hr>

                  <h2>📈 Contribution Graph</h2>

                  <div align="center">
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=dakshgopani&theme=tokyo-night&hide_border=true" alt="Contribution Graph"/>
                  </div>

                  <hr>

                  <div align="center">
                    <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight" alt="Random Dev Quote"/>
                  </div>

                  <div align="center">
                    <p>⭐️ From <a href="https://github.com/dakshgopani">dakshgopani</a> with ❤️</p>
                  </div>
                `
            },
            {
                username: 'debasish5452v',
                readmeContent: `
                <h1 class="name1">Debasish</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1 align="center">👋 Hi there, I'm Debasish!</h1> 

                  <div align="center">
                    <a href="https://git.io/typing-svg">
                      <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=2E9EF7&center=true&vCenter=true&width=435&lines=Full+Stack+Developer;Open+Source+Enthusiast;Always+Learning+New+Things;Building+Amazing+Projects" alt="Typing SVG"/>
                    </a>
                  </div>

                  <hr>

                  <h2>🚀 About Me</h2>

                  <pre><code>const debasish = {
                name: "Debasish",
                location: "India 🇮🇳",
                role: "Full Stack Developer",
                passion: ["Coding", "Open Source", "Innovation"],
                currentFocus: "Building impactful web applications",
                funFact: "I debug with console.log() and I'm not ashamed! 😄"
            };
                  </code></pre>

                  <h2>🛠️ Tech Stack</h2>

                  <div align="center">

                  <h3>💻 Languages</h3>
                  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
                  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
                  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java">
                  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
                  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">

                  <h3>🚀 Frameworks & Libraries</h3>
                  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React">
                  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js">
                  <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express.js">
                  <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django">
                  <img src="https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap">

                  <h3>🗄️ Databases</h3>
                  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB">
                  <img src="https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
                  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL">

                  <h3>☁️ Cloud & Tools</h3>
                  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
                  <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
                  <img src="https://img.shields.io/badge/VS_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white" alt="VS Code">
                  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS">
                  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">

                  </div>

                  <hr>

                  <h2>📊 GitHub Stats</h2>

                  <div align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=debasish5452v&show_icons=true&theme=radical&hide_border=true&count_private=true" alt="GitHub Stats" />
                    <br>
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=debasish5452v&theme=radical&hide_border=true" alt="GitHub Streak" />
                    <br>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=debasish5452v&layout=compact&theme=radical&hide_border=true" alt="Top Languages" />
                  </div>

                  <hr>

                  <h2>🏆 Achievements</h2>

                  <div align="center">
                    <img src="https://github-profile-trophy.vercel.app/?username=debasish5452v&theme=radical&no-frame=true&no-bg=false&margin-w=4" alt="GitHub Trophies" />
                  </div>

                  <hr>

                  <h2>🎯 Current Goals</h2>
                  <ul>
                    <li>🔭 Working on <strong>Full Stack Web Development</strong></li>
                    <li>🌱 Learning <strong>Advanced React Patterns</strong> and <strong>Cloud Architecture</strong></li>
                    <li>👯 Looking to collaborate on <strong>Open Source Projects</strong></li>
                    <li>💬 Ask me about <strong>JavaScript, React, Node.js, Python</strong></li>
                    <li>⚡ Fun fact: <strong>I love contributing to Hacktoberfest!</strong></li>
                  </ul>

                  <hr>

                  <h2>📈 Contribution Graph</h2>

                  <div align="center">
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=debasish5452v&theme=react-dark&hide_border=true&area=true" alt="Contribution Graph" />
                  </div>

                  <hr>

                  <h2>🌟 Featured Projects</h2>

                  <div align="center">

                  <h3>🎯 <a href="https://github.com/debasish5452v/To-Do-List">To-Do List Application</a></h3>
                  <p><em>Modern, interactive task management app with enhanced UI/UX</em></p>
                  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
                  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5">
                  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white" alt="CSS3">

                  <h3>📚 <a href="https://github.com/debasish5452v/dsa-code">DSA Code Collection</a></h3>
                  <p><em>Comprehensive collection of Data Structures and Algorithms implementations</em></p>
                  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
                  <img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=java&logoColor=white" alt="Java">
                  <img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++">
                  </div>

                  <hr>

                  <h2>🤝 Connect with Me</h2>
                  <div align="center">
                    <a href="https://github.com/debasish5452v"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"></a>
                    <a href="https://linkedin.com/in/debasish5452v"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
                    <a href="https://twitter.com/debasish5452v"><img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter"></a>
                    <a href="https://instagram.com/debasish5452v"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram"></a>
                    <a href="https://debasish5452v.github.io"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=About.me&logoColor=white" alt="Portfolio"></a>
                  </div>

                  <hr>

                  <h2>💭 Random Dev Quote</h2>

                  <div align="center">
                    <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical" alt="Quote">
                  </div>

                  <hr>

                  <div align="center">
                    <h3>🎯 Profile Views</h3>
                    <img src="https://komarev.com/ghpvc/?username=debasish5452v&color=brightgreen&style=flat-square&label=Profile+Views" alt="Profile Views">
                    <h3>⭐ If you like my work, please consider giving my repositories a star!</h3>
                  </div>

                  <hr>

                  <div align="center">
                    <p><strong>"Code is like humor. When you have to explain it, it's bad."</strong> – Cory House</p>
                    <p><em>Thanks for visiting my profile! Have a great day! 😊</em></p>
                  </div>
                `
            },
            {
                username: 'Elango-Kannan-00',
                readmeContent: `
                <h1 class="name1">Elango Kannan</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1>Hi 👋, I'm Elango K 👨‍💻</h1>

                  <img src="https://user-images.githubusercontent.com/74038190/212750147-854a394f-fee9-4080-9770-78a4b7ece53f.gif" width="500">

                  <h2>About Me 🙋‍♂️</h2>

                  <p>
                    🎓 CSE undergrad @ KIOT <br>
                    💻 Tech Enthusiast  <br>
                    🚀 Exploring emerging tech & trends  <br>
                    🌴 Based in Salem, Tamil Nadu  <br>
                    🔁 Learning, growing, and coding every day!  
                  </p>

                  <h2>Currently 🔍</h2>
                  <ul>
                    <li>🌱 Learning: <strong>Web Development</strong></li>
                    <li>👯 Looking to collaborate on: <strong>AI Tools & Development</strong></li>
                    <li>📫 Reach me at: <strong>elango.kiot@gmail.com</strong></li>
                    <li>⚡ Fun Fact: <em>The first computer bug was an actual bug! 🐛 — In 1947, a moth got trapped in the Harvard Mark II computer, causing a malfunction.</em></li>
                  </ul>

                  <h2>Languages 🌐</h2>

                  <p align="left">
                    <img src="https://skillicons.dev/icons?i=py,java,html,css,js" alt="Languages"/>
                  </p>

                  <h2>Tools 🛠</h2>  
                  <p align="left">
                    <img src="https://skillicons.dev/icons?i=vscode,git,github" alt="Tools"/>
                  </p>

                  <h2>Featured Projects 🚀</h2>

                  <a href="https://github.com/Logic-Loom-00/Article_Recommendation">
                    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Logic-Loom-00&repo=Article_Recommendation&theme=highcontrast" alt="Article Recommendation Project"/>
                  </a>
                  
                  <h2>GitHub Stats 📈</h2>  

                  <p align="center">
                    <img src="http://github-profile-summary-cards.vercel.app/api/cards/stats?username=Elango-Kannan-00&theme=highcontrast" height="180em" />
                    <img src="http://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Elango-Kannan-00&theme=highcontrast" height="180em" />
                    <img src="https://streak-stats.demolab.com?user=Elango-Kannan-00&theme=highcontrast&ring=yellow&fire=yellow&currStreakNum=yellow&sideNums=yellow&currStreakLabel=white&hide_border=true" height="180em" />
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=Elango-Kannan-00&theme=high-contrast&line=FFD700&point=FFD700" alt="Contribution Graph" />
                  </p>

                  <h2>Connect with Me 🤝</h2>  

                  <p align="left">
                    <a href="https://www.linkedin.com/in/elango-kannan-bbaa3928b" target="_blank">
                      <img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn"/>
                    </a> 
                    <a href="mailto:elango.kiot@gmail.com">
                      <img src="https://skillicons.dev/icons?i=gmail" alt="Gmail"/>
                    </a> 
                    <a href="https://x.com/Elango_Kannan_0">
                      <img src="https://skillicons.dev/icons?i=twitter" alt="Twitter"/>
                    </a>
                  </p>

                  <h1>✨ That's All Folks! ✨</h1>
                `
            },
            {
                username: 'Rylin31',
                readmeContent: `
                <h1 class="name1">Rylin</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1>💫 About Me:</h1>
                  <p>
                    🔭 I’m currently working on: Building an AI assistant that can read documents and images to answer questions.<br>
                    👯 I’m looking to collaborate on: Fun projects in AI, apps, or anything that makes life easier.<br><br>
                    🤝 I’m looking for help with: Learning new AI tricks, coding tips, and building scalable projects.<br><br>
                    🌱 I’m currently learning: AI, entrepreneurship, and exploring new technologies.<br><br>
                    💬 Ask me about: Cool project ideas, coding, or travel adventures.<br><br>
                    ⚡ Fun fact: I’ve never seen snow but I want to try skiing and skydiving someday.
                  </p>

                  <h2>🌐 Socials:</h2>
                  <p>
                    <a href="https://www.linkedin.com/in/rahul-s-355a3131b/"><img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" alt="LinkedIn"></a> 
                    <a href="mailto:rahul.s.31.08.2006@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"></a> 
                  </p>

                  <h1>💻 Tech Stack:</h1>
                  <p>
                    <img src="https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white" alt="C"> 
                    <img src="https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++"> 
                    <img src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"> 
                    <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"> 
                    <img src="https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java"> 
                    <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"> 
                    <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python"> 
                    <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS"> 
                    <img src="https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure"> 
                    <img src="https://img.shields.io/badge/netlify-%23000000.svg?style=for-the-badge&logo=netlify&logoColor=#00C7B7" alt="Netlify"> 
                    <img src="https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white" alt="Google Cloud"> 
                    <img src="https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase" alt="Firebase"> 
                    <img src="https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel"> 
                    <img src="https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap"> 
                    <img src="https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white" alt="Flask"> 
                    <img src="https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi" alt="FastAPI"> 
                    <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React"> 
                    <img src="https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="TailwindCSS"> 
                    <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL"> 
                    <img src="https://img.shields.io/badge/firebase-a08021?style=for-the-badge&logo=firebase&logoColor=ffcd34" alt="Firebase"> 
                    <img src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white" alt="Supabase"> 
                    <img src="https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white" alt="Figma"> 
                    <img src="https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white" alt="Canva"> 
                    <img src="https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white" alt="Keras"> 
                    <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" alt="Matplotlib"> 
                    <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"> 
                    <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"> 
                    <img src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white" alt="TensorFlow"> 
                    <img src="https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes">
                  </p>

                  <h1>📊 GitHub Stats:</h1>
                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=Rylin31&theme=dark&hide_border=false&include_all_commits=true&count_private=true"><br/>
                    <img src="https://nirzak-streak-stats.vercel.app/?user=Rylin31&theme=dark&hide_border=false"><br/>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Rylin31&theme=dark&hide_border=false&include_all_commits=true&count_private=true&layout=compact">
                  </p>

                  <h2>🏆 GitHub Trophies</h2>
                  <p align="center">
                    <img src="https://github-profile-trophy.vercel.app/?username=Rylin31&theme=radical&no-frame=true&no-bg=true&margin-w=4">
                  </p>

                  <h3>🔝 Top Contributed Repo</h3>
                  <p align="center">
                    <img src="https://github-contributor-stats.vercel.app/api?username=Rylin31&limit=5&theme=dark&combine_all_yearly_contributions=true">
                  </p>

                  <hr>
                  <p align="center">
                    <a href="https://visitcount.itsvg.in">
                        <img src="https://visitcount.itsvg.in/api?id=Rylin31&icon=0&color=0">
                    </a>
                  </p>
                `
            },
            {
                username: 'Subratkb02',
                readmeContent: `
                <h1 class="name1">Subrat Kumar Behera</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <a href="https://www.youtube.com/watch?v=SDkAGkd4NLc" target="_blank">
                      <img src="https://raw.githubusercontent.com/rodrigograca31/rodrigograca31/master/matrix.svg" alt="Matrix SVG"/>
                  </a> 
                  <h1 align="center" style="font-size: 50px; color: #DC143C; text-shadow: 0 0 10px #DC143C; font-family: 'Segoe UI', sans-serif;">
                    Hello, I'm Subrat Kumar Behera
                  </h1>

                  <h3 align="center" style="font-family: 'Segoe UI', sans-serif; background-color:#000000; padding: 15px; border-radius: 10px; color: #DC143C; text-shadow: 0 0 10px #DC143C;">
                    Frontend Developer | UI/UX Designer | MERN & DevOps Enthusiast | AIT Pune 
                  </h3>

                  <p align="center">
                    <img src="https://komarev.com/ghpvc/?username=Subratkb02&label=Profile%20views&color=DC143C&style=flat" alt="Profile Views" />
                    <img src="https://img.shields.io/github/followers/Subratkb02?label=Follow%20Me&color=DC143C&style=flat-square" alt="Followers">
                    <img src="https://img.shields.io/github/stars/Subratkb02?label=Stars&color=DC143C&style=flat-square" alt="Stars">
                  </p>

                  <div align="center">
                    <img src="https://readme-typing-svg.herokuapp.com?font=Black+Ops+One&color=DC143C&size=26&center=true&vCenter=true&width=600&lines=Frontend+Developer;UI%2FUX+Designer;Graphic+Designer;MERN+Stack+Enthusiast;AWS+%26+DevOps+Learner;ESP32+%7C+IoT+Builder;Open+Source+Contributor" alt="Typing SVG" />
                  </div>

                  <hr>

                  <h3 align="center" style="font-family: 'Segoe UI', sans-serif; background-color:#000000; padding: 10px; border-radius: 10px; color: #DC143C; text-shadow: 0 0 10px #DC143C;">
                    🔗 Connect with me:
                  </h3>
                  <p align="center">
                    <a href="https://linkedin.com/in/subratkb02" target="_blank">
                      <img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
                    </a>
                    <a href="https://www.hackerrank.com/subratk1802" target="_blank">
                      <img src="https://img.shields.io/badge/Hackerrank-2EC866.svg?style=for-the-badge&logo=hackerrank&logoColor=white" alt="HackerRank">
                    </a>
                    <a href="https://codeforces.com/profile/subrat_kb" target="_blank">
                      <img src="https://img.shields.io/badge/Codeforces-%231E1E2E.svg?style=for-the-badge&logo=codeforces&logoColor=white" alt="Codeforces">
                    </a>
                    <a href="https://auth.geeksforgeeks.org/user/captain_nimbus/" target="_blank">
                      <img src="https://img.shields.io/badge/GFG-%2300C853.svg?style=for-the-badge&logo=geeksforgeeks&logoColor=white" alt="GFG">
                    </a>
                    <a href="https://github.com/Subratkb02" target="_blank">
                      <img src="https://img.shields.io/badge/GitHub-171515.svg?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
                    </a>
                  </p>

                  <hr>

                  <h3 align="center" style="font-family: 'Segoe UI', sans-serif; background-color:#000000; padding: 10px; border-radius: 10px; color: #DC143C; text-shadow: 0 0 10px #DC143C;">
                    🛠️ Tech Stack
                  </h3>

                  <p align="Center">
                    <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" alt="C">
                    <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++">
                    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
                    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
                    <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
                    <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
                    <img src="https://img.shields.io/badge/ReactJS-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="ReactJS">
                    <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js">
                    <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask">
                    <img src="https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap">
                    <img src="https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socket.io&logoColor=white" alt="Socket.io">
                    <img src="https://img.shields.io/badge/MATLAB-0076A8?style=for-the-badge&logo=mathworks&logoColor=white" alt="MATLAB">
                    <img src="https://img.shields.io/badge/Proteus-009688?style=for-the-badge" alt="Proteus">
                    <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
                    <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
                    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
                    <img src="https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" alt="VS Code">
                    <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
                    <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" alt="Figma">
                    <img src="https://img.shields.io/badge/Canva-00C4CC?style=for-the-badge&logo=canva&logoColor=white" alt="Canva">
                    <img src="https://img.shields.io/badge/Adobe%20Illustrator-FF9A00?style=for-the-badge&logo=adobe-illustrator&logoColor=white" alt="Illustrator">
                    <img src="https://img.shields.io/badge/Adobe%20Photoshop-31A8FF?style=for-the-badge&logo=adobe-photoshop&logoColor=white" alt="Photoshop">
                    <img src="https://img.shields.io/badge/ESP32-323330?style=for-the-badge" alt="ESP32">
                    <img src="https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Arduino">
                  </p>

                  <hr>

                  <h3 align="center" style="font-family: 'Segoe UI', sans-serif; background-color:#000000; padding: 10px; border-radius: 10px; color: #DC143C; text-shadow: 0 0 10px #DC143C;">📊 GitHub Stats & Contributions</h3>

                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs?username=Subratkb02&show_icons=true&locale=en&layout=compact&bg_color=000000&title_color=DC143C&text_color=FFFFFF&icon_color=DC143C&hide_border=true" alt="Top Languages"/>
                    <img src="https://github-readme-stats.vercel.app/api?username=Subratkb02&show_icons=true&locale=en&bg_color=000000&title_color=DC143C&text_color=FFFFFF&icon_color=DC143C&hide_border=true" alt="GitHub Stats"/>
                  </p>

                  <div align="center">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=Subratkb02&theme=dark&background=000000&stroke=FFFFFF&ring=DC143C&fire=DC143C&currStreakNum=DC143C&sideNums=DC143C&currStreakLabel=DC143C&sideLabels=DC143C&dates=DC143C&hide_border=true" alt="GitHub Streak Stats"/>
                  </div>

                  <p align="center">
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=Subratkb02&custom_title=Subrat's%20Contribution%20Graph&bg_color=000000&color=DC143C&line=FFFFFF&point=DC143C&area=true&hide_border=true" alt="GitHub Contribution Graph"/>
                  </p>
                `
            },
            {
                username: 'xurde24',
                readmeContent: `
                   <h1 class="name1">Shreyansh Anand</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <img src="https://camo.githubusercontent.com/4c3fd71b359cd5dfadc21247cde8f16ecbe5d41db8ac79ef28e3091ab02a8bef/68747470733a2f2f6d69722d73332d63646e2d63662e626568616e63652e6e65742f70726f6a6563745f6d6f64756c65732f6d61785f313230302f3831626234623136353638343031392e363430623630333864313333652e676966" alt="MasterHead GIF">
                  <h1 align="center">Hi 👋, I'm Shreyansh Anand</h1>
                  <h3 align="center">A passionate Software Developer from India</h3>
                  <img align="right" alt="Coding" width="335" src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif">

                  <ul>
                    <li>🔭 I’m a <strong>Software Developer</strong></li>
                    <li>🌱 I’m currently learning <strong>Generative AI, System Design</strong></li>
                    <li>💬 Ask me about <strong>MERN, NextJS, DSA</strong></li>
                    <li>📫 How to reach me <strong>anandshreyansh25@gmail.com</strong></li>
                  </ul>

                  <h3 align="left">Connect with me:</h3>
                  <p align="left">
                    <a href="https://x.com/ShreyanshA41331" target="_blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="twitter" height="30" width="40" />
                    </a>&nbsp;
                    <a href="https://www.linkedin.com/in/shreyansh-anand-751761283" target="_blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="linkedin" height="30" width="40" />
                    </a>&nbsp;
                    <a href="https://www.instagram.com/anand_24993/" target="_blank">
                      <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="instagram" height="30" width="40" />
                    </a>
                  </p>

                  <hr>

                  <h1>💻 Tech Stack:</h1>
                  <p>
                    <img src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"> 
                    <img src="https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++"> 
                    <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"> 
                    <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"> 
                    <img src="https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase" alt="Firebase"> 
                    <img src="https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel"> 
                    <img src="https://img.shields.io/badge/netlify-%23000000.svg?style=for-the-badge&logo=netlify&logoColor=#00C7B7" alt="Netlify"> 
                    <img src="https://img.shields.io/badge/Context--Api-000000?style=for-the-badge&logo=react" alt="Context-API"> 
                    <img src="https://img.shields.io/badge/ejs-%23B4CA65.svg?style=for-the-badge&logo=ejs&logoColor=black" alt="EJS"> 
                    <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="NodeJS"> 
                    <img src="https://img.shields.io/badge/NPM-%23CB3837.svg?style=for-the-badge&logo=npm&logoColor=white" alt="NPM"> 
                    <img src="https://img.shields.io/badge/NODEMON-%23323330.svg?style=for-the-badge&logo=nodemon&logoColor=%BBDEAD" alt="Nodemon"> 
                    <img src="https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="TailwindCSS"> 
                    <img src="https://img.shields.io/badge/Socket.io-black?style=for-the-badge&logo=socket.io&badgeColor=010101" alt="Socket.io"> 
                    <img src="https://img.shields.io/badge/SASS-hotpink.svg?style=for-the-badge&logo=SASS&logoColor=white" alt="SASS"> 
                    <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React"> 
                    <img src="https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB" alt="Express.js"> 
                    <img src="https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"> 
                    <img src="https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white" alt="Canva"> 
                    <img src="https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white" alt="Figma"> 
                    <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" alt="Matplotlib"> 
                    <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"> 
                    <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"> 
                    <img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"> 
                    <img src="https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white" alt="Git"> 
                    <img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman"> 
                    <img src="https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white" alt="Notion">
                  </p>

                  <h3 align="center">📊 Statistics</h3>

                  <div align="center">
                      <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=xurde24&theme=2077" height="180em" />
                      <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=xurde24&theme=2077" height="180em" />
                      <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=xurde24&theme=2077" height="180em" />
                      <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=xurde24&theme=2077" height="180em" />
                      <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=xurde24&theme=2077" height="180em" />
                  </div>

                  <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="decorative gif">

                  <hr>

                  <h2 align="left">⚡ Activity Graph</h2>
                  <div align="center">
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=xurde24&theme=react-dark" alt="Activity Graph"/>
                  </div>

                  <hr>

                  <h1>📊 GitHub Stats:</h1>
                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=xurde24&theme=radical&hide_border=false&include_all_commits=false&count_private=false"><br/>
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=xurde24&theme=radical&hide_border=false"><br/>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=xurde24&theme=radical&hide_border=false&include_all_commits=false&count_private=false&layout=compact">
                  </p>

                  <img src="https://komarev.com/ghpvc/?username=xurde24" alt="Profile Views">
                `
            },
            {
                username: 'rictorsp',
                readmeContent: `
                   <h1 class="name1">Ricardo Victor</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h2>👨🏻‍💻 <strong>Ricardo Victor Marques Sampaio Pinheiro</strong></h2>

                  <pre><code>Neurotechnology & AI</code></pre>

                  <p>
                    Studying a Bachelor's Degree in Software Engineering (7th/8th semester) at FUCAPI University, passionate about gym, purpose, neurotechnology, gaming, and taking ideas off paper through code.
                  </p>

                  <p>
                    Reach me out here: <a href="mailto:ricardovictor737@gmail.com" target="__blank">ricardovictor737@gmail.com</a>
                  </p>

                  <h3>Stacks</h3>
                  <a href="https://skillicons.dev" target="_blank">
                      <img src="https://skillicons.dev/icons?i=ts,python,net,nestjs,angular,nodejs,mongodb,postgres,rabbitmq,bootstrap,aws,docker,git" alt="My Skills"/>
                  </a>

                  <h3>Contacts</h3>
                  <p>
                      <a href="https://www.instagram.com/rictor_dev" target="_blank">
                          <img src="https://skillicons.dev/icons?i=instagram" alt="Instagram"/>
                      </a>
                      <a href="https://www.linkedin.com/in/rictorsp/" target="_blank">
                          <img src="https://go-skill-icons.vercel.app/api/icons?i=linkedin" alt="LinkedIn"/>
                      </a>
                  </p>

                  <h3>Languages</h3>
                  <p>
                    <img src="https://raw.githubusercontent.com/stevenrskelton/flag-icon/master/png/16/country-4x3/br.png" alt="Brazil Flag" width="16" /> Native Portuguese<br>
                    <img src="https://raw.githubusercontent.com/stevenrskelton/flag-icon/master/png/16/country-4x3/us.png" alt="United States Flag" width="16" /> Advanced English
                  </p>
                `
            },
            {
                username: 'samim29',
                readmeContent: `
                 <h1 class="name1">Sk Samim Ali</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1>💫 Hi 👋, I'm Sk Samim Ali</h1>
                  <p><strong>A passionate FullStack Developer || ML Enthusiast</strong></p>

                  <p>Email Me 👉 ✉️ <strong>samimalisk000@gmail.com</strong> For Collaboration/Project or Anything Else. 😊😊</p>

                  <ul>
                    <li>🔭 <strong>Top 25 at OpenSource Apertre 2.0</strong> | <strong>HacktoberFest 2024</strong></li>
                    <li>👯 <strong>Branch Topper</strong></li>
                    <li>💬 <strong>Ask me about:</strong> Collaboration, Tech Support</li>
                    <li>📫 <strong>How to reach me:</strong> samimalisk000@gmail.com</li>
                    <li>😄 <strong>Pronouns:</strong> He/Him</li>
                    <li>⚡ <strong>Fun fact:</strong> I debug my dreams</li>
                  </ul>

                  <h2>🌐 Socials:</h2>
                  <p>
                    <a href="https://discord.gg/samim29"><img src="https://img.shields.io/badge/Discord-%237289DA.svg?logo=discord&logoColor=white" alt="Discord"></a> 
                    <a href="https://linkedin.com/in/sksamimali"><img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" alt="LinkedIn"></a> 
                    <a href="mailto:samimalisk000@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"></a> 
                  </p>

                  <h1>💻 Tech Stack:</h1>
                  <p>
                    <img src="https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white" alt="C"> 
                    <img src="https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++"> 
                    <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"> 
                    <img src="https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java"> 
                    <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"> 
                    <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python"> 
                    <img src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS"> 
                    <img src="https://img.shields.io/badge/netlify-%23000000.svg?style=for-the-badge&logo=netlify&logoColor=#00C7B7" alt="Netlify"> 
                    <img src="https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel"> 
                    <img src="https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white" alt="Google Cloud"> 
                    <img src="https://img.shields.io/badge/Anaconda-%2344A833.svg?style=for-the-badge&logo=anaconda&logoColor=white" alt="Anaconda"> 
                    <img src="https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap"> 
                    <img src="https://img.shields.io/badge/ejs-%23B4CA65.svg?style=for-the-badge&logo=ejs&logoColor=black" alt="EJS"> 
                    <img src="https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB" alt="Express.js"> 
                    <img src="https://img.shields.io/badge/NPM-%23CB3837.svg?style=for-the-badge&logo=npm&logoColor=white" alt="NPM"> 
                    <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="NodeJS"> 
                    <img src="https://img.shields.io/badge/NODEMON-%23323330.svg?style=for-the-badge&logo=nodemon&logoColor=%BBDEAD" alt="Nodemon"> 
                    <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React"> 
                    <img src="https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="TailwindCSS"> 
                    <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL"> 
                    <img src="https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"> 
                    <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"> 
                    <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" alt="Matplotlib"> 
                    <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"> 
                    <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn">
                  </p>

                  <div align="center">
                    <img src="https://profile-readme-generator.com/assets/snake.svg" alt="Snake animation" />
                  </div>

                  <h1>📊 GitHub Stats:</h1>
                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=samim29&theme=dark&hide_border=false&include_all_commits=true&count_private=false"><br/>
                    <img src="https://nirzak-streak-stats.vercel.app/?user=samim29&theme=dark&hide_border=false"><br/>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=samim29&theme=dark&hide_border=false&include_all_commits=true&count_private=false&layout=compact">
                  </p>

                  <h3>🔝 Top Contributed Repo</h3>
                  <p align="center">
                    <img src="https://github-contributor-stats.vercel.app/api?username=samim29&limit=5&theme=dark&combine_all_yearly_contributions=true">
                  </p>

                  <h2>🏆 GitHub Trophies</h2>
                  <p align="center">
                    <img src="https://github-profile-trophy.vercel.app/?username=samim29&theme=radical&no-frame=false&no-bg=true&margin-w=4">
                  </p>

                  <h3>✍️ Random Dev Quote</h3>
                  <p align="center">
                    <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical">
                  </p>
      `
            },
            {
                username: 'shivaram-repo',
                readmeContent: `
                  <h1 class="name1">👋 Hi, I'm Shivaram</h1>

                  <h2>💫 About Me</h2>
                  <p>I'm a passionate <strong>Application developer</strong> with a love for creating intuitive and beautiful app experiences.</p>
                  <ul>
                    <li>🌱 I'm currently learning <strong>Kotlin</strong> and <strong>React Native</strong>.</li>
                    <li>👯 I'm looking to collaborate on <strong>open-source projects</strong> and projects related to <strong>AI</strong>.</li>
                    <li>💬 Ask me about Application development.</li>
                  </ul>

                  <hr>

                  <h2>🚀 My Skills</h2>
                  <ul>
                    <li><strong>Languages:</strong> Java, Kotlin, MySQL, C, Python, Javascript, Mongodb</li>
                    <li><strong>Frameworks & Libraries:</strong> Java Swing & AWT, Ktor, React, React Native</li>
                    <li><strong>Tools:</strong> Git, VS Code, Eclipse, Android Studio</li>
                  </ul>

                  <hr>

                  <h2>💻 Tech Stack:</h2>
                  <p>
                    <img src="https://img.shields.io/badge/c-%2300599C.svg?style=flat-square&logo=c&logoColor=white" alt="C"> 
                    <img src="https://img.shields.io/badge/java-%23ED8B00.svg?style=flat-square&logo=openjdk&logoColor=white" alt="Java"> 
                    <img src="https://img.shields.io/badge/kotlin-%237F52FF.svg?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin"> 
                    <img src="https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=ffdd54" alt="Python"> 
                    <img src="https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB">
                    <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=flat-square&logo=mysql&logoColor=white" alt="MySQL"> 
                    <img src="https://img.shields.io/badge/react-%2320232a.svg?style=flat-square&logo=react&logoColor=%2361DAFB" alt="React">
                    <img src="https://img.shields.io/badge/react_native-%2320232a.svg?style=flat-square&logo=react&logoColor=%2361DAFB" alt="React Native">
                  </p>

                  <hr>

                  <h2>📧 Contact Me:</h2>
                  <p>
                    <a href="mailto:shivaramshiva370@gmail.com" target="_blank">
                      <img src="https://skillicons.dev/icons?i=gmail" width="47" height="35" alt="Gmail logo" />
                    </a>
                    <a href="https://www.linkedin.com/in/shivaram-t-s-b32b90288/" target="_blank">
                      <img src="https://skillicons.dev/icons?i=linkedin" width="47" height="35" alt="LinkedIn logo" />
                    </a>
                  </p>

                  <hr>

                  <h2>🌐 Portfolio:</h2>
                  <p><a href="https://shivaram-repo.github.io/" target="_blank">https://shivaram-repo.github.io/</a></p>

                  <hr>

                  <h2>📊 GitHub Stats:</h2>
                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=shivaram-repo&theme=rose_pine&hide_border=false&include_all_commits=true&count_private=false"><br/>
                    <img src="https://nirzak-streak-stats.vercel.app/?user=shivaram-repo&theme=rose_pine&hide_border=false"><br/>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=shivaram-repo&theme=rose_pine&hide_border=false&include_all_commits=true&count_private=true&layout=compact">
                  </p>
                  <p align="center">
                    <img src="https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2Fshivaram-repo&countColor=%23263759" alt="Visitor Badge">
                  </p>
                `
            },
            {
                username: 'son-of-zeus',
                readmeContent: `
                  <h1 align="Left" class="name1">Pranav Vijay</h1>

                  <h2>🌐 Socials:</h2>
                  <p>
                    <a href="https://instagram.com/pranav_with_a_v"><img src="https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white" alt="Instagram"></a> 
                    <a href="https://linkedin.com/in/pranav-v-524410329"><img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" alt="LinkedIn"></a> 
                    <a href="https://x.com/build_with_vp"><img src="https://img.shields.io/badge/X-black.svg?logo=X&logoColor=white" alt="X"></a> 
                    <a href="mailto:pranav.vjc@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" alt="Email"></a> 
                  </p>

                  <h1>💻 Tech Stack:</h1>
                  <p>
                    <img src="https://img.shields.io/badge/assembly%20script-%23000000.svg?style=for-the-badge&logo=assemblyscript&logoColor=white" alt="AssemblyScript"> 
                    <img src="https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white" alt="C"> 
                    <img src="https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=csharp&logoColor=white" alt="C#"> 
                    <img src="https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white" alt="Dart"> 
                    <img src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"> 
                    <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"> 
                    <img src="https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java"> 
                    <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"> 
                    <img src="https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white" alt="Markdown"> 
                    <img src="https://img.shields.io/badge/PowerShell-%235391FE.svg?style=for-the-badge&logo=powershell&logoColor=white" alt="PowerShell"> 
                    <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python"> 
                    <img src="https://img.shields.io/badge/rust-%23000000.svg?style=for-the-badge&logo=rust&logoColor=white" alt="Rust"> 
                    <img src="https://img.shields.io/badge/bash_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Bash Script"> 
                    <img src="https://img.shields.io/badge/swift-F54A2A?style=for-the-badge&logo=swift&logoColor=white" alt="Swift"> 
                    <img src="https://img.shields.io/badge/Windows%20Terminal-%234D4D4D.svg?style=for-the-badge&logo=windows-terminal&logoColor=white" alt="Windows Terminal"> 
                    <img src="https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase" alt="Firebase"> 
                    <img src="https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap"> 
                    <img src="https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white" alt="Flask"> 
                    <img src="https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white" alt="Flutter"> 
                    <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="NodeJS">
                    <img src="https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="TailwindCSS"> 
                    <img src="https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white" alt="Vite"> 
                    <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React"> 
                    <img src="https://img.shields.io/badge/firebase-a08021?style=for-the-badge&logo=firebase&logoColor=ffcd34" alt="Firebase"> 
                    <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL"> 
                    <img src="https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite"> 
                    <img src="https://img.shields.io/badge/Adobe%20After%20Effects-9999FF.svg?style=for-the-badge&logo=Adobe%20After%20Effects&logoColor=white" alt="Adobe After Effects"> 
                    <img src="https://img.shields.io/badge/Adobe%20Lightroom-31A8FF.svg?style=for-the-badge&logo=Adobe%20Lightroom&logoColor=white" alt="Adobe Lightroom"> 
                    <img src="https://img.shields.io/badge/adobe%20photoshop-%2331A8FF.svg?style=for-the-badge&logo=adobe%20photoshop&logoColor=white" alt="Adobe Photoshop"> 
                    <img src="https://img.shields.io/badge/Adobe%20Premiere%20Pro-9999FF.svg?style=for-the-badge&logo=Adobe%20Premiere%20Pro&logoColor=white" alt="Adobe Premiere Pro"> 
                    <img src="https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white" alt="Keras"> 
                    <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="PyTorch"> 
                    <img src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white" alt="TensorFlow"> 
                    <img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman"> 
                    <img src="https://img.shields.io/badge/-Raspberry_Pi-C51A4A?style=for-the-badge&logo=Raspberry-Pi" alt="Raspberry Pi"> 
                    <img src="https://img.shields.io/badge/unity-%23000000.svg?style=for-the-badge&logo=unity&logoColor=white" alt="Unity"> 
                    <img src="https://img.shields.io/badge/unrealengine-%23313131.svg?style=for-the-badge&logo=unrealengine&logoColor=white" alt="Unreal Engine">
                  </p>

                  <h1>📊 GitHub Stats:</h1>
                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=son-of-zeus&theme=dark&hide_border=false&include_all_commits=true&count_private=true&layout=compact">
                  </p>
                  <p align="left"> 
                    <img src="https://komarev.com/ghpvc/?username=son-of-zeus&label=Profile%20views&color=0e75b6&style=flat" alt="son-of-zeus" /> 
                  </p>
                `
            },
            {
                username: 'Venkat5599',
                readmeContent: `
                <h1 class="name1">Venkat</h1>
                 <div align="center">
                    <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="Header GIF">
                  </div>
                  <h1>💫 About Me:</h1>
                  <h2>Hi there 👋, I'm Venkat</h2>
                  <p>
                    🚀 Passionate about <strong>Web Development</strong>, <strong>Cybersecurity</strong>, and <strong>Open Source</strong><br>
                    💻 Love building projects that combine creativity and security<br>
                    🔐 Exploring secure coding practices, ethical hacking, and modern web technologies<br>
                    🌱 Actively contributing to <strong>Open Source</strong> communities and projects
                  </p>

                  <hr>

                  <h2>🌐 Web Development</h2>
                  <ul>
                    <li>Skilled in <strong>HTML, CSS, JavaScript</strong></li>
                    <li>Learning <strong>React, Node.js, Express, MongoDB</strong></li>
                    <li>Interested in creating <strong>scalable and secure web applications</strong></li>
                  </ul>

                  <h2>🛡️ Cybersecurity</h2>
                  <ul>
                    <li>Enthusiastic about <strong>ethical hacking & penetration testing</strong></li>
                    <li>Exploring <strong>OWASP Top 10, web vulnerabilities, and secure coding</strong></li>
                    <li>Love participating in <strong>CTFs and security challenges</strong></li>
                  </ul>

                  <h2>🤝 Open Source Contributions</h2>
                  <ul>
                    <li>Actively exploring projects to contribute to on GitHub</li>
                    <li>Interested in <strong>security-focused projects</strong> and <strong>developer tools</strong></li>
                    <li>Goal: Contribute to <strong>OWASP</strong> and other communities via <strong>Google Summer of Code (GSoC)</strong> or similar programs</li>
                  </ul>

                  <hr>

                  <h2>📚 Currently Learning</h2>
                  <ul>
                    <li>Advanced <strong>JavaScript & Backend frameworks</strong></li>
                    <li><strong>Application Security</strong> & Secure Development Lifecycle (SDLC)</li>
                    <li>Automation tools for <strong>web security testing</strong></li>
                    <li>Best practices for <strong>open source collaboration</strong></li>
                  </ul>

                  <h1>💻 Tech Stack:</h1>
                  <p>
                    <img src="https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++"> 
                    <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"> 
                    <img src="https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white" alt="C"> 
                    <img src="https://img.shields.io/badge/crystal-%23000000.svg?style=for-the-badge&logo=crystal&logoColor=white" alt="Crystal"> 
                    <img src="https://img.shields.io/badge/assembly%20script-%23000000.svg?style=for-the-badge&logo=assemblyscript&logoColor=white" alt="AssemblyScript"> 
                    <img src="https://img.shields.io/badge/bash_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Bash Script"> 
                    <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python"> 
                    <img src="https://img.shields.io/badge/OCTAVE-darkblue?style=for-the-badge&logo=octave&logoColor=fcd683" alt="Octave"> 
                    <img src="https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white" alt="Markdown"> 
                    <img src="https://img.shields.io/badge/nim-%23FFE953.svg?style=for-the-badge&logo=nim&logoColor=white" alt="Nim"> 
                    <img src="https://img.shields.io/badge/orgmode-%2377AA99.svg?style=for-the-badge&logo=org&logoColor=white" alt="Org Mode"> 
                    <img src="https://img.shields.io/badge/r-%23276DC3.svg?style=for-the-badge&logo=r&logoColor=white" alt="R"> 
                    <img src="https://img.shields.io/badge/Solidity-%23363636.svg?style=for-the-badge&logo=solidity&logoColor=white" alt="Solidity"> 
                    <img src="https://img.shields.io/badge/swift-F54A2A?style=for-the-badge&logo=swift&logoColor=white" alt="Swift"> 
                    <img src="https://img.shields.io/badge/rescript-%2314162c?style=for-the-badge&logo=rescript&logoColor=e34c4c" alt="ReScript"> 
                    <img src="https://img.shields.io/badge/ruby-%23CC342D.svg?style=for-the-badge&logo=ruby&logoColor=white" alt="Ruby"> 
                    <img src="https://img.shields.io/badge/NIX-5277C3.svg?style=for-the-badge&logo=NixOS&logoColor=white" alt="Nix"> 
                    <img src="https://img.shields.io/badge/OBJECTIVE--C-%233A95E3.svg?style=for-the-badge&logo=apple&logoColor=white" alt="Objective-C"> 
                    <img src="https://img.shields.io/badge/-Julia-9558B2?style=for-the-badge&logo=julia&logoColor=white" alt="Julia">
                  </p>

                  <h1>📊 GitHub Stats:</h1>
                  <p align="center">
                    <img src="https://github-readme-stats.vercel.app/api?username=Venkat5599&theme=dark&hide_border=false&include_all_commits=false&count_private=false"><br/>
                    <img src="https://nirzak-streak-stats.vercel.app/?user=Venkat5599&theme=dark&hide_border=false"><br/>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Venkat5599&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact">
                  </p>

                  <hr>
                  <p align="center">
                    <a href="https://visitcount.itsvg.in">
                        <img src="https://visitcount.itsvg.in/api?id=Venkat5599&icon=0&color=0">
                    </a>
                    <a href="https://holopin.io/@venkat5599">
                        <img src="https://holopin.me/venkat5599" alt="An image of @venkat5599's Holopin badges, which is a link to view their full Holopin profile">
                    </a>
                  </p>
                `
            },
            
               
 
        ];

        // --- DOM ELEMENTS ---
        const grid = document.getElementById('profiles-grid');
        const modal = document.getElementById('profile-modal');
        const modalBody = document.getElementById('modal-body');
        const modalCloseBtn = document.getElementById('modal-close-btn');

        // --- FUNCTIONS ---

        function extractName(htmlContent) {
            if (!htmlContent) return 'Unknown User';
            const match = htmlContent.match(/<h1.*?>(.*?)<\/h1>/);
            if (match && match[1]) {
                const tempDiv = document.createElement('div');
                tempDiv.innerHTML = match[1];
                return tempDiv.textContent.replace(/Hi\s*,\s*I'm/i, '').trim() || 'Unknown User';
            }
            return 'Unknown User';
        }

        function createProfileCard(profile) {
            const name = extractName(profile.readmeContent);
            const card = document.createElement('div');
            card.className = "bg-gray-800 border border-gray-700 rounded-xl p-6 cursor-pointer group hover:border-purple-500 transition-all duration-300 transform hover:-translate-y-1 hover:shadow-2xl hover:shadow-purple-500/20";
            card.innerHTML = `
                <div class="flex items-center space-x-4">
                    <img 
                        src="https://github.com/${profile.username}.png" 
                        onerror="this.onerror=null; this.src='https://placehold.co/64x64/1F2937/7C3AED?text=${profile.username.charAt(0)}'"
                        alt="${profile.username}'s avatar" 
                        class="w-16 h-16 rounded-full border-2 border-gray-600 group-hover:border-purple-500 transition-colors"
                    />
                    <div>
                        <h3 class="text-xl font-bold text-white">${name}</h3>
                        <p class="text-gray-400">@${profile.username}</p>
                    </div>
                </div>
                <p class="text-gray-400 mt-4 text-sm">Click to view full profile...</p>
            `;
            card.addEventListener('click', () => showProfileModal(profile));
            return card;
        }

        function showProfileModal(profile) {
            // WARNING: Setting innerHTML from a string can be risky if the content is not trusted.
            // Here we are trusting the content from the `profilesData` array.
            modalBody.innerHTML = profile.readmeContent;
            modal.classList.remove('hidden');
        }

        function hideProfileModal() {
            modal.classList.add('hidden');
            modalBody.innerHTML = ''; // Clear content
        }

        // --- INITIALIZATION ---

        // Render all profile cards on page load
        profilesData.forEach(profile => {
            const card = createProfileCard(profile);
            grid.appendChild(card);
        });

        // Add event listeners for the modal
        modal.addEventListener('click', hideProfileModal);
        modalCloseBtn.addEventListener('click', hideProfileModal);
        // Prevent modal from closing when clicking on its content
        modal.querySelector('.modal-content').addEventListener('click', (e) => e.stopPropagation());

    </script>
</body>
</html>
