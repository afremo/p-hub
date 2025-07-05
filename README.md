![hero_bg](https://github.com/user-attachments/assets/a4f5553c-83a9-46e6-bb06-bc9dbcb702f7)
![edu_thumbl](https://github.com/user-attachments/assets/8b9af937-66cb-48ee-adca-a2fd55f37fb6)
![comedy_thumbl](https://github.com/user-attachments/assets/053b9637-069d-47b9-be8f-55eac61807d4)
![adults_thumbl](https://github.com/user-attachments/assets/7b54b7a5-e398-41f7-a354-120ff340b8a4)
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>p-hub - আপনার পছন্দের ভিডিও খুঁজুন</title>
    <link rel="icon" href="favicon.ico" type="image/x-icon"> 
    
    <style>
        /* বেসিক রিসেট */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f4f4f4;
            color: #333;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: auto;
            overflow: hidden;
            padding: 0 20px;
        }

        /* হেডার */
        header {
            background: #333;
            color: #fff;
            padding: 1rem 0;
            border-bottom: #77aaff 3px solid;
        }

        header .logo {
            float: left;
            color: #fff;
            text-decoration: none;
            font-size: 1.8rem;
            font-weight: bold;
        }

        header nav {
            float: right;
            margin-top: 10px;
        }

        header ul {
            list-style: none;
        }

        header ul li {
            display: inline;
            padding: 0 15px;
        }

        header ul li a {
            color: #fff;
            text-decoration: none;
            text-transform: uppercase;
            font-size: 16px;
        }

        header ul li a:hover,
        header ul li a.warning-link:hover {
            color: #77aaff;
            font-weight: bold;
        }

        /* হিরো সেকশন */
        .hero {
            min-height: 400px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: #fff;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('images/hero_bg.jpg') no-repeat center center/cover; /* একটি ব্যাকগ্রাউন্ড ইমেজ যোগ করুন */
            padding: 40px 0;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 10px;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 20px;
        }

        .search-bar {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }

        .search-bar input[type="text"] {
            padding: 10px;
            font-size: 1rem;
            border: none;
            border-radius: 5px 0 0 5px;
            width: 60%;
            max-width: 400px;
        }

        .search-bar button {
            padding: 10px 20px;
            font-size: 1rem;
            background: #77aaff;
            color: #fff;
            border: none;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .search-bar button:hover {
            background: #5588cc;
        }

        /* ক্যাটাগরি সেকশন */
        .categories-section {
            padding: 40px 0;
            background-color: #eee;
            text-align: center;
        }

        .categories-section h2 {
            margin-bottom: 20px;
            font-size: 2rem;
            color: #333;
        }

        .category-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }

        .category-btn {
            background: #555;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background 0.3s ease;
        }

        .category-btn:hover,
        .category-btn.active {
            background: #77aaff;
        }

        /* ভিডিও গ্রিড সেকশন */
        .video-grid-section {
            padding: 40px 0;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .video-item {
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .video-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        .video-item a {
            text-decoration: none;
            color: inherit;
            display: block;
            padding-bottom: 15px; /* নিচের টেক্সটের জন্য প্যাডিং */
        }

        .video-item img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            display: block;
            border-bottom: 1px solid #eee;
        }

        .video-item h3 {
            font-size: 1.2rem;
            padding: 15px 15px 5px;
            color: #333;
        }

        .video-item p {
            font-size: 0.9rem;
            color: #666;
            padding: 0 15px;
        }
        
        .no-videos {
            text-align: center;
            grid-column: 1 / -1; /* গ্রিডের সব কলাম জুড়ে দেখানোর জন্য */
            color: #666;
            font-size: 1.1rem;
            padding: 30px;
        }

        /* ফুটার */
        footer {
            background: #333;
            color: #fff;
            text-align: center;
            padding: 20px 0;
            margin-top: 40px;
            font-size: 0.9rem;
        }

        /* অ্যাডাল্ট ওয়ার্নিং মডাল */
        .modal {
            display: none; /* ডিফল্টভাবে লুকানো */
            position: fixed; /* স্ক্রিনের উপরে */
            z-index: 1000; /* অন্য সবকিছুর উপরে */
            left: 0;
            top: 0;
            width: 100%; /* পুরো স্ক্রিন কভার করবে */
            height: 100%; /* পুরো স্ক্রিন কভার করবে */
            overflow: auto; /* স্ক্রল করার প্রয়োজন হলে */
            background-color: rgba(0, 0, 0, 0.7); /* সেমি-ট্রান্সপারেন্ট ব্যাকগ্রাউন্ড */
            display: flex; /* কন্টেন্টকে কেন্দ্রে আনার জন্য */
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: #fefefe;
            margin: auto;
            padding: 30px;
            border: 1px solid #888;
            width: 80%;
            max-width: 500px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            text-align: center;
            border-radius: 8px;
        }

        .modal-content h2 {
            color: #d9534f; /* লাল রং এর সতর্কতা */
            margin-bottom: 15px;
            font-size: 1.8rem;
        }

        .modal-content p {
            margin-bottom: 25px;
            font-size: 1.1rem;
            line-height: 1.5;
        }

        .modal-content button {
            background-color: #77aaff;
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            margin: 0 10px;
            transition: background-color 0.3s ease;
        }

        .modal-content button#cancelAdultBtn {
            background-color: #f0ad4e;
        }

        .modal-content button:hover {
            background-color: #5588cc;
        }

        .modal-content button#cancelAdultBtn:hover {
            background-color: #ec971f;
        }

        /* মোবাইল রেসপনসিভনেস */
        @media (max-width: 768px) {
            header .logo,
            header nav {
                float: none;
                text-align: center;
            }

            header nav ul li {
                display: block;
                padding: 5px 0;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .search-bar input[type="text"] {
                width: 80%;
            }

            .video-grid {
                grid-template-columns: 1fr; /* ছোট স্ক্রিনে একটি কলাম */
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <a href="index.html" class="logo">আমার ভিডিও</a>
            <nav>
                <ul>
                    <li><a href="#home">হোম</a></li>
                    <li><a href="#categories">ক্যাটাগরি</a></li>
                    <li><a href="#about">আমাদের সম্পর্কে</a></li>
                    <li><a href="#" id="adultContentLink" class="warning-link">১৮+ ভিডিও</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="hero-section" class="hero">
            <div class="container">
                <h1>আপনার পছন্দের ভিডিও সংগ্রহশালা</h1>
                <p>বিভিন্ন ক্যাটাগরি থেকে আপনার পছন্দের ভিডিওগুলি খুঁজুন এবং উপভোগ করুন!</p>
                <div class="search-bar">
                    <input type="text" id="searchInput" placeholder="ভিডিও খুঁজুন...">
                    <button id="searchButton">অনুসন্ধান</button>
                </div>
            </div>
        </section>

        <section id="categories" class="categories-section">
            <div class="container">
                <h2>ভিডিও ক্যাটাগরি</h2>
                <div class="category-list">
                    <button class="category-btn active" data-category="all">সব</button>
                    <button class="category-btn" data-category="comedy">কমেডি</button>
                    <button class="category-btn" data-category="drama">ড্রামা</button>
                    <button class="category-btn" data-category="educational">শিক্ষামূলক</button>
                    <button class="category-btn" data-category="tech">প্রযুক্তি</button>
                    <button class="category-btn" data-category="documentary">ডকুমেন্টারি</button>
                    <button class="category-btn" data-category="adult">১৮+ অ্যাডাল্ট</button>
                </div>
            </div>
        </section>

        <section id="video-grid-section" class="video-grid-section">
            <div class="container">
                <div class="video-grid" id="videoGrid">
                    </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>&copy; ২০২৫ p-hub। সর্বস্বত্ব সংরক্ষিত।</p>
            <p>আপনার জিমেইল: afrbook920@gmail.com (শুধুমাত্র মালিকের জন্য)</p>
        </div>
    </footer>

    <div id="adultWarningModal" class="modal">
        <div class="modal-content">
            <h2>সতর্কতা!</h2>
            <p>এই বিভাগে প্রাপ্তবয়স্কদের জন্য উপযুক্ত কন্টেন্ট থাকতে পারে। আপনি কি নিশ্চিত যে আপনার বয়স ১৮ বছরের বেশি?</p>
            <button id="confirmAdultBtn">হ্যাঁ, আমার বয়স ১৮+ বছর</button>
            <button id="cancelAdultBtn">না, আমি ফিরে যেতে চাই</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const videoGrid = document.getElementById('videoGrid');
            const categoryButtons = document.querySelectorAll('.category-btn');
            const searchInput = document.getElementById('searchInput');
            const searchButton = document.getElementById('searchButton');
            const adultContentLink = document.getElementById('adultContentLink');
            const adultWarningModal = document.getElementById('adultWarningModal');
            const confirmAdultBtn = document.getElementById('confirmAdultBtn');
            const cancelAdultBtn = document.getElementById('cancelAdultBtn');

            // ভিডিও ডেটা (আপনার ভিডিওর লিঙ্ক, থাম্বনেইল, বিবরণ এখানে যোগ করুন)
            // এটি একটি উদাহরণ মাত্র। আপনাকে আপনার আসল ভিডিও ডেটা দিয়ে এটি পূরণ করতে হবে।
            const videos = [
                {
                    id: 'v1',
                    title: 'আমার কমেডি ভিডিও ১',
                    description: 'এটি আমার তৈরি একটি হাসির ভিডিও।',
                    thumbnail: 'images/comedy_thumb1.jpg', // আপনার থাম্বনেইল ইমেজ পাথ
                    link: '-https://www.reddit.com/r/funnyvideos/comments/1lrpojf/ooops/Link-1', // মূল ভিডিওর ওয়েবসাইটের লিঙ্ক
                    category: 'comedy'
                },
                {
                    id: 'v2',
                    title: 'শিক্ষামূলক ডক্যুমেন্টারি: প্রকৃতির বিস্ময়',
                    description: 'প্রকৃতির রহস্য নিয়ে একটি দারুণ শিক্ষামূলক ডক্যুমেন্টারি।',
                    thumbnail: 'images/edu_thumb1.jpg',
                    link: 'https://alb.reddit.com/cr?za=i5wsnYIO7ylkdzas6aVnASuAkPwbpZNtUdYv9w_V0Qe6Tiz_iUyt5d4RS_lxcQTBFU2xYZPdoqw2fItZ91H-JrixKbQkAADX3itO11d-MRYPZA6FMEZOxeTN5Sd6CydjZzEJv6sRaydxA2K7LRHJ6LDMWxvwQ_TS58JoNoIj6Os38ynUbhN8pwhRwFoU0K-2x6f-z1YTj4MYEsvSYPVXgkbY-U0bu9DhLKoJGVGWExj6Dirx43OFcR365NAr8JZJM1Vttf9Oh_AJfqbn1O_kCmzzP7x8NgoUMxUQqwMIcTBPVLqaucSVoWtNGeWOEVFO9kuyPW9_6mXJNl_0NZ_VYpeXMOAStB0ZbEO-lVzES5VgjRQR5F0iPo0gKRtWigJt4KYrBNMFojIf4hB5OaGaQ0IPctucxb8RmC0NhGCD_NNL4kseB6DqEqRFQLTfUflQddHNYYiqA2ylz24g5kJ4HcL8joOcbLnnQPwsCdUoY6V_dCqRSf4LPU0znDewAgBx7SoLhaRycyPgrFwBoaSBJbGyg8eC29VZYBTuX4_2oYhf1A7NjzyeroWp_EAWpyWkUCbvBhvFBmZ0jG6XXJQzV2Wl6tR5MoJ_aOqvd6glHn9-PE8YihtAXk0IqdTdELsHWDJKshbE6rafeQ&zp=_69rDufrCMaOuWR_lh5T8fHL1D46ewpVq-G-ziLpmKnNHZtM_8pFwB8UF6pnl-DIK7ZZjJLDLz_FkZtsd2TIqctdtqM8LO_TfWTnaFmJFs_71TVzPcc2imURTKSI2c428wEPcXsa3AqwJl059nCxnyDwi_cDrNvqLMknMjjZSh2JnS_hNU4cxDUf9n7_xRUioI1J41QRaCB-XjgKOyYyrDsEppne7bTL1ZSXFk3gUUA20Y3ysN6JDElMJazdJQRH0m19e6YXusalGmdZIDqPpgIMhcf03JWNChE7JQ_wT2ZlYS_CUEOR93MvxMCHDfqyOCYQ1DeiBpzwk3GdQUFfMg5NZHqHX4b1qT8vpSFlZ1MLnnva2HQyzr6yb-oBk-TTIqCL-yOv6g&a=7286&b=7274&be=7274&c=7035&d=7286&e=7274&ea=7274&eb=7274&f=7035&r=6&g=1&i=1751677625997&t=1751677633283&o=1&q=1&h=616&w=607&sh=1076&sw=485',
                    category: 'educational'
                },
                {
                    id: 'v3',
                    title: 'ড্রামা: গল্পের শেষ',
                    description: 'একটি মর্মস্পর্শী ছোট ড্রামা ফিল্ম।',
                    thumbnail: 'images/drama_thumb1.jpg',
                    link: 'https://www.reddit.com/r/funnyvideos/comments/1lr44o8/not_one_single_argument',
                    category: 'drama'
                },
                {
                    id: 'v4',
                    title: 'স্মার্টফোন রিভিউ: নতুন যা এলো',
                    description: 'সর্বশেষ স্মার্টফোনটির বিস্তারিত রিভিউ।',
                    thumbnail: 'images/tech_thumb1.jpg',
                    link: 'https://www.reddit.com/r/funnyvideos/comments/1lnkgtm/my_cell_0/',
                    category: 'tech'
                },
                // অ্যাডাল্ট কন্টেন্টের উদাহরণ (শুধুমাত্র ডিজাইনের জন্য, প্রকৃত কন্টেন্ট নয়)
                {
                    id: 'v5',
                    title: 'Sis Lover',
                    description: 'Stepsister Want Her Bro',
                    thumbnail: 'images/adult_thumb1.jpg',
                    link: 'https://www.familystrokes.com/?nats=z3itg3ist.2.72.5242.0.0.0.0.0/movies/stepsisters-growing-pains',
                    category: 'adult'
                },
                {
                    id: 'v6',
                    title: 'Stepdaughter Little P*ssy২',
                    description: 'প্রাপ্তবয়স্কদের জন্য আরেকটি কন্টেন্ট।',
                    thumbnail: 'images/adult_thumb2.jpg',
                    link: 'https://www.teamskeet.com/?nats=chardbros.2.15.6662.11.0.0.0.0&switched=1&strack=0&amp%3Bstrack=0/movies/sneaky-mias-fourth-of-july-discipline',
                    category: 'adult'
                },
                // আরও ভিডিও এখানে যোগ করুন...
            ];

            // ভিডিও গ্রিডে ভিডিও লোড করার ফাংশন
            const loadVideos = (filterCategory = 'all', searchTerm = '') => {
                videoGrid.innerHTML = ''; // পূর্বের ভিডিওগুলো সাফ করা

                const filteredVideos = videos.filter(video => {
                    const matchesCategory = (filterCategory === 'all' || video.category === filterCategory);
                    const matchesSearch = video.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
                                          video.description.toLowerCase().includes(searchTerm.toLowerCase());
                    return matchesCategory && matchesSearch;
                });

                if (filteredVideos.length === 0) {
                    videoGrid.innerHTML = '<p class="no-videos">কোনো ভিডিও পাওয়া যায়নি।</p>';
                    return;
                }

                filteredVideos.forEach(video => {
                    const videoItem = document.createElement('div');
                    videoItem.classList.add('video-item');
                    videoItem.setAttribute('data-category', video.category);

                    let videoLink = video.link;
                    // অ্যাডাল্ট কন্টেন্টের জন্য ভিন্ন আচরণ (সরাসরি লিঙ্ক নয়)
                    if (video.category === 'adult') {
                        videoLink = '#'; // আপাতত ডামি লিংক, জাভাস্ক্রিপ্ট এটি হ্যান্ডেল করবে
                        videoItem.classList.add('adult-content-item'); 
                    }

                    videoItem.innerHTML = `
                        <a href="${videoLink}" target="_blank">
                            <img src="${video.thumbnail}" alt="${video.title} থাম্বনেইল">
                            <h3>${video.title}</h3>
                            <p>${video.description}</p>
                        </a>
                    `;

                    videoGrid.appendChild(videoItem);
                });

                // অ্যাডাল্ট কন্টেন্ট আইটেমগুলির জন্য ইভেন্ট লিসেনার সেট করা
                document.querySelectorAll('.adult-content-item').forEach(item => {
                    item.querySelector('a').addEventListener('click', (e) => {
                        e.preventDefault(); // ডিফল্ট লিঙ্কের আচরণ বন্ধ করুন
                        showAdultWarning(item.querySelector('a').href); // ওয়ার্নিং দেখান
                    });
                });
            };

            // ক্যাটাগরি ফিল্টারিং
            categoryButtons.forEach(button => {
                button.addEventListener('click', () => {
                    // সক্রিয় বাটন আপডেট করা
                    categoryButtons.forEach(btn => btn.classList.remove('active'));
                    button.classList.add('active');

                    const category = button.dataset.category;
                    if (category === 'adult') {
                        // অ্যাডাল্ট ক্যাটাগরিতে ক্লিক করলে ওয়ার্নিং পপ-আপ দেখান
                        showAdultWarning('adult-category-view'); // বিশেষ ফ্ল্যাগ
                    } else {
                        loadVideos(category, searchInput.value);
                    }
                });
            });

            // সার্চ ফাংশনালিটি
            searchButton.addEventListener('click', () => {
                const currentCategory = document.querySelector('.category-btn.active').dataset.category;
                loadVideos(currentCategory, searchInput.value);
            });

            searchInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    searchButton.click();
                }
            });

            // অ্যাডাল্ট ওয়ার্নিং পপ-আপ লজিক
            let intendedAdultLink = ''; // যে লিঙ্কে ব্যবহারকারী যেতে চেয়েছিল

            function showAdultWarning(destination) {
                intendedAdultLink = destination;
                adultWarningModal.style.display = 'flex'; // মডাল দেখান
            }

            adultContentLink.addEventListener('click', (e) => {
                e.preventDefault();
                showAdultWarning('adult-category-view'); // সরাসরি ১৮+ লিঙ্কে ক্লিক করলে
            });

            confirmAdultBtn.addEventListener('click', () => {
                adultWarningModal.style.display = 'none'; // মডাল লুকান
                if (intendedAdultLink === 'adult-category-view') {
                    loadVideos('adult', searchInput.value); // অ্যাডাল্ট ক্যাটাগরির ভিডিও লোড করুন
                } else if (intendedAdultLink && intendedAdultLink !== '#') { // '#'-কে এড়িয়ে যান
                    window.open(intendedAdultLink, '_blank'); // মূল লিঙ্কে পুনঃনির্দেশ করুন
                }
                intendedAdultLink = ''; // রিসেট
            });

            cancelAdultBtn.addEventListener('click', () => {
                adultWarningModal.style.display = 'none'; // মডাল লুকান
                intendedAdultLink = ''; // রিসেট
                // ব্যবহারকারীকে হোমে বা অন্য কোনো নিরাপদ ক্যাটাগরিতে নিয়ে যেতে পারেন
                const allCategoryButton = document.querySelector('.category-btn[data-category="all"]');
                if (allCategoryButton) {
                    allCategoryButton.click();
                }
            });

            // প্রথমবার পেজ লোড হওয়ার সময় সব ভিডিও লোড করুন
            loadVideos('all');
        });
    </script>
</body>
</html>
