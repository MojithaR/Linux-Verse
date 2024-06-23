<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Introduction to Linux</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 0;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        header {
            background: #50b3a2;
            color: #fff;
            padding-top: 30px;
            min-height: 70px;
            border-bottom: #e8491d 3px solid;
        }
        header h1 {
            text-align: center;
            text-transform: uppercase;
            margin: 0;
        }
        nav {
            margin: 20px 0;
            background: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        nav ul {
            padding: 0;
            list-style: none;
        }
        nav ul li {
            display: inline;
            margin: 0 10px;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
        }
        section {
            padding: 20px;
            background: #fff;
            margin-bottom: 20px;
            border: 1px solid #ddd;
        }
        section h2 {
            border-bottom: 2px solid #50b3a2;
            padding-bottom: 10px;
        }
        footer {
            text-align: center;
            padding: 20px;
            background: #333;
            color: #fff;
        }
        .active {
            font-weight: bold;
        }
    </style>
    <script src="https://cdn.jsdelivr.net/npm/kotlin@1.4.32/kotlin.js"></script>
</head>
<body>
    <div class="container">
        <header>
            <h1>Introduction to Linux</h1>
        </header>
        <nav>
            <ul>
                <li><a href="#history">History and Evolution of Linux</a></li>
                <li><a href="#distributions">Distributions and Flavors</a></li>
                <li><a href="#installation">Installation of Linux</a></li>
            </ul>
        </nav>
        <section id="history">
            <h2>History and Evolution of Linux</h2>
            <p>Linux is an open-source operating system that was created by Linus Torvalds in 1991. It has since evolved into one of the most important platforms for servers, desktops, and embedded systems. Its development is driven by a community of developers and companies that contribute to its code and documentation.</p>
        </section>
        <section id="distributions">
            <h2>Distributions and Flavors</h2>
            <p>There are many different distributions (or "distros") of Linux, each tailored for different uses and preferences. Some of the most popular include:</p>
            <ul>
                <li>Ubuntu</li>
                <li>CentOS</li>
                <li>Fedora</li>
            </ul>
        </section>
        <section id="installation">
            <h2>Installation of Linux</h2>
            <p>Installing Linux can be done in several ways, including:</p>
            <ul>
                <li>Dual Boot</li>
                <li>Virtual Machines</li>
            </ul>
        </section>
        <footer>
            <p>&copy; 2024 Your Name</p>
        </footer>
    </div>
    <script type="text/kotlin">
        import kotlinx.browser.document
        import kotlinx.browser.window

        fun main() {
            val navLinks = document.querySelectorAll("nav ul li a")
            val sections = document.querySelectorAll("section")

            window.addEventListener("scroll", {
                var current = ""
                sections.forEach { section ->
                    val sectionTop = section.asDynamic().offsetTop
                    if (window.pageYOffset >= sectionTop - 50) {
                        current = section.id
                    }
                }

                navLinks.forEach { link ->
                    link.classList.remove("active")
                    if (link.getAttribute("href")?.contains(current) == true) {
                        link.classList.add("active")
                    }
                }
            })
        }

        // Initialize Kotlin application
        main()
    </script>
</body>
</html>

