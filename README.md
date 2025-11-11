# r-d-mobile
LinkTree
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>System1 - Monetizing Content for Creators</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            background-attachment: fixed;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .solar-flow-section .container {
            background: transparent;
        }

        .header {
            text-align: center;
            padding: 60px 20px 40px;
            color: white;
        }

        .header h1 {
            font-size: 48px;
            font-weight: 700;
            margin-bottom: 20px;
            letter-spacing: -1px;
        }

        .system1-logo {
            font-size: 24px;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .tab-container {
            display: flex;
            justify-content: center;
            gap: 10px;
            padding: 20px;
            flex-wrap: wrap;
        }

        .tab-button {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
            padding: 12px 32px;
            border-radius: 25px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            backdrop-filter: blur(10px);
            -webkit-tap-highlight-color: transparent;
        }

        .tab-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        .tab-button.active {
            background: white;
            color: #667eea;
            border-color: white;
        }

        .flow-section {
            min-height: 400vh;
            position: relative;
            display: none;
        }

        .flow-section.active {
            display: block;
        }

        .solar-flow-section .flow-section {
            background: transparent;
        }

        .sticky-container {
            position: sticky;
            top: 0;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .solar-flow-section .sticky-container {
            background: transparent;
        }

        .phone-container {
            display: flex;
            gap: 80px;
            align-items: center;
            justify-content: center;
        }

        .phone-container-wrapper {
            display: flex;
            align-items: center;
            gap: 80px;
            justify-content: center;
        }

        .phone-with-controls {
            display: flex;
            align-items: center;
            gap: 40px;
        }

        .phone {
            width: 320px;
            height: 650px;
            background: #1a1a1a;
            border-radius: 40px;
            padding: 12px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.4);
            position: relative;
            opacity: 0;
            transform: translateY(100px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .phone.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .phone-screen {
            width: 100%;
            height: 100%;
            background: white;
            border-radius: 32px;
            overflow: hidden;
            position: relative;
        }

        .phone-notch {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 150px;
            height: 28px;
            background: #1a1a1a;
            border-radius: 0 0 20px 20px;
            z-index: 10;
        }

        .arrow {
            font-size: 60px;
            color: white;
            opacity: 0;
            transform: scale(0);
            transition: all 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .arrow.visible {
            opacity: 1;
            transform: scale(1);
        }

        .phone-content {
            padding: 40px 20px 20px;
            height: 100%;
            overflow-y: auto;
        }

        .phone-content::-webkit-scrollbar {
            width: 4px;
        }

        .phone-content::-webkit-scrollbar-thumb {
            background: #ccc;
            border-radius: 2px;
        }

        .linktree {
            background: linear-gradient(180deg, #FFB6D9 0%, #FFC9E3 100%);
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .linktree.blue {
            background: linear-gradient(180deg, #a8edea 0%, #fed6e3 100%);
        }

        .linktree.purple {
            background: linear-gradient(180deg, #d4a5ff 0%, #e8c4ff 100%);
        }

        .linktree.green {
            background: linear-gradient(180deg, #a8e6cf 0%, #dcedc1 100%);
        }

        .profile-pic {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: #FFD93D;
            margin: 20px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            font-weight: 700;
            color: #333;
        }

        .username {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .bio {
            font-size: 12px;
            text-align: center;
            margin-bottom: 20px;
            padding: 0 20px;
            color: #333;
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
        }

        .social-icon {
            width: 30px;
            height: 30px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 14px;
        }

        .link-button {
            width: 260px;
            padding: 15px;
            background: white;
            border-radius: 25px;
            margin: 8px 0;
            text-align: center;
            font-size: 13px;
            font-weight: 500;
            cursor: pointer;
            transition: transform 0.2s;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }

        .link-button:hover {
            transform: scale(1.05);
        }

        .link-button.highlight {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            font-weight: 600;
        }

        .link-button.highlight-alt1 {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            font-weight: 600;
        }

        .link-button.highlight-alt2 {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            color: white;
            font-weight: 600;
        }

        .link-button.highlight-alt3 {
            background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
            color: white;
            font-weight: 600;
        }

        .article {
            padding: 40px 20px 20px;
            background: linear-gradient(180deg, #FFB6D9 0%, #FFC9E3 100%);
            height: 100%;
        }

        .article.blue {
            background: linear-gradient(180deg, #a8edea 0%, #fed6e3 100%);
        }

        .article.purple {
            background: linear-gradient(180deg, #d4a5ff 0%, #e8c4ff 100%);
        }

        .article.green {
            background: linear-gradient(180deg, #a8e6cf 0%, #dcedc1 100%);
        }

        .article.solar {
            background: linear-gradient(180deg, #ffeaa7 0%, #fdcb6e 100%);
        }

        .article-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 20px;
            background: white;
            padding: 15px;
            border-radius: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .article-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: #FFD93D;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            font-weight: 700;
            color: #333;
        }

        .author-info h3 {
            font-size: 16px;
            margin-bottom: 3px;
        }

        .author-link {
            font-size: 12px;
            color: #667eea;
        }

        .article-title {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 15px;
            line-height: 1.3;
        }

        .article-content-block .article-title {
            margin-top: 0;
        }

        .article-text {
            font-size: 13px;
            line-height: 1.6;
            color: #444;
            margin-bottom: 15px;
        }

        .article-content-block {
            background: white;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            margin-bottom: 20px;
        }

        .article-content-block .article-text:last-child {
            margin-bottom: 0;
        }

        .related-searches {
            background: white;
            border-radius: 20px;
            padding: 15px;
            margin-bottom: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .search-title {
            font-size: 12px;
            color: #666;
            margin-bottom: 12px;
            font-weight: 600;
        }

        .search-chip {
            display: inline-block;
            background: #f8f9fa;
            padding: 8px 16px;
            border-radius: 20px;
            margin: 4px;
            font-size: 13px;
            cursor: pointer;
            border: 1px solid #e0e0e0;
            transition: all 0.2s;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }

        .search-chip:hover {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: transparent;
            transform: scale(1.05);
        }

        .search-chip.alt1:hover {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .search-chip.alt2:hover {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
        }

        .search-chip.alt3:hover {
            background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
        }

        .serp {
            padding: 40px 20px 20px;
            background: linear-gradient(180deg, #FFB6D9 0%, #FFC9E3 100%);
            height: 100%;
        }

        .serp.blue {
            background: linear-gradient(180deg, #a8edea 0%, #fed6e3 100%);
        }

        .serp.purple {
            background: linear-gradient(180deg, #d4a5ff 0%, #e8c4ff 100%);
        }

        .serp.green {
            background: linear-gradient(180deg, #a8e6cf 0%, #dcedc1 100%);
        }

        .serp.solar {
            background: linear-gradient(180deg, #ffeaa7 0%, #fdcb6e 100%);
        }

        .search-bar {
            background: white;
            padding: 12px 16px;
            border-radius: 24px;
            font-size: 14px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .sponsored-badge {
            display: inline-block;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 10px;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .sponsored-badge.alt1 {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .sponsored-badge.alt2 {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
        }

        .sponsored-badge.alt3 {
            background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
        }

        .serp-result {
            padding: 20px;
            border-radius: 25px;
            margin-bottom: 16px;
            background: white;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .result-url {
            font-size: 11px;
            color: #5f6368;
            margin-bottom: 4px;
        }

        .result-link {
            color: #1a73e8;
            font-size: 13px;
            text-decoration: none;
            display: block;
            margin-bottom: 6px;
        }

        .result-title {
            font-size: 16px;
            font-weight: 600;
            color: #1a0dab;
            margin-bottom: 6px;
        }

        .result-description {
            font-size: 12px;
            color: #4d5156;
            line-height: 1.5;
        }

        .visit-button {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 24px;
            border-radius: 25px;
            border: none;
            font-size: 14px;
            font-weight: 600;
            margin-top: 12px;
            cursor: pointer;
            transition: all 0.2s;
            width: 100%;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }

        .visit-button:hover {
            transform: scale(1.02);
            box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
        }

        .visit-button.alt1 {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .visit-button.alt1:hover {
            box-shadow: 0 4px 12px rgba(240, 147, 251, 0.4);
        }

        .visit-button.alt2 {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
        }

        .visit-button.alt2:hover {
            box-shadow: 0 4px 12px rgba(79, 172, 254, 0.4);
        }

        .visit-button.alt3 {
            background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
        }

        .visit-button.alt3:hover {
            box-shadow: 0 4px 12px rgba(67, 233, 123, 0.4);
        }

        .stage-label {
            position: absolute;
            top: -60px;
            left: 50%;
            transform: translateX(-50%);
            background: white;
            padding: 12px 24px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 600;
            color: #667eea;
            white-space: nowrap;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            opacity: 0;
            transition: opacity 0.6s;
        }

        .phone.visible .stage-label {
            opacity: 1;
        }

        .solar-flow-section {
            background: transparent;
            padding: 80px 20px;
            border-top: 3px solid rgba(255, 255, 255, 0.2);
        }

        .solar-flow-header {
            text-align: center;
            color: white;
            margin-bottom: 60px;
        }

        .solar-flow-header h2 {
            font-size: 42px;
            margin-bottom: 15px;
        }

        .solar-flow-header p {
            font-size: 18px;
            opacity: 0.9;
        }

        .solar-entry-controls {
            text-align: center;
            margin-bottom: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .solar-entry-label {
            background: white;
            padding: 10px 20px;
            border-radius: 20px;
            font-size: 13px;
            font-weight: 600;
            color: #667eea;
            display: inline-block;
            margin-bottom: 15px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            white-space: nowrap;
        }

        .solar-toggle-container {
            display: flex;
            justify-content: center;
            gap: 8px;
            flex-wrap: wrap;
        }

        .toggle-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.5);
            padding: 10px 16px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 12px;
            font-weight: 600;
            color: white;
            backdrop-filter: blur(10px);
            text-align: center;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }

        .toggle-btn.active {
            background: white;
            color: #667eea;
            border-color: white;
        }

        .toggle-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        .footer {
            text-align: center;
            padding: 80px 20px;
            color: white;
        }

        .footer h2 {
            font-size: 32px;
            margin-bottom: 20px;
        }

        .footer p {
            font-size: 18px;
            opacity: 0.9;
        }

        @media (max-width: 1200px) {
            .phone-container {
                gap: 40px;
            }
            .phone-container-wrapper {
                gap: 40px;
            }
            .phone-with-controls {
                gap: 20px;
            }
            .phone {
                width: 280px;
                height: 570px;
            }
        }

        @media (max-width: 900px) {
            .header h1 {
                font-size: 32px;
            }

            .system1-logo {
                font-size: 20px;
            }

            .tab-container {
                gap: 8px;
                padding: 15px 10px;
            }

            .tab-button {
                padding: 10px 20px;
                font-size: 14px;
            }

            .phone-container {
                flex-direction: column;
                gap: 40px;
            }

            .phone-container-wrapper {
                flex-direction: column;
                gap: 40px;
                align-items: center;
            }

            .phone-with-controls {
                flex-direction: column;
                gap: 25px;
                width: 100%;
                align-items: center;
            }

            .solar-entry-controls {
                width: 100%;
                max-width: 320px;
            }

            .solar-toggle-container {
                flex-direction: column !important;
                width: 100%;
                gap: 10px;
            }

            .toggle-btn {
                width: 100% !important;
                padding: 12px 20px;
                font-size: 14px;
            }

            .phone {
                width: 320px;
                height: 650px;
            }

            .arrow {
                transform: rotate(90deg);
                font-size: 50px;
            }

            .solar-flow-header h2 {
                font-size: 32px;
            }

            .solar-flow-header p {
                font-size: 16px;
            }

            .footer h2 {
                font-size: 28px;
            }

            .footer p {
                font-size: 16px;
            }

            .stage-label {
                font-size: 12px;
                padding: 10px 20px;
            }
        }

        @media (max-width: 600px) {
            .header {
                padding: 40px 15px 30px;
            }

            .header h1 {
                font-size: 24px;
            }

            .system1-logo {
                font-size: 18px;
            }

            .tab-button {
                padding: 8px 16px;
                font-size: 13px;
            }

            .phone {
                width: 280px;
                height: 570px;
            }

            .arrow {
                font-size: 40px;
            }

            .solar-flow-header h2 {
                font-size: 26px;
            }

            .solar-flow-header p {
                font-size: 14px;
            }

            .solar-flow-section {
                padding: 60px 15px;
            }

            .footer {
                padding: 60px 15px;
            }

            .footer h2 {
                font-size: 24px;
            }

            .footer p {
                font-size: 14px;
            }

            .container {
                padding: 0 10px;
            }

            .flow-section {
                min-height: 250vh;
            }

            .solar-flow-section .flow-section {
                min-height: 250vh;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <div class="system1-logo">SYSTEM1</div>
        <h1>MONETIZING CONTENT FOR CREATORS</h1>
    </div>

    <div class="tab-container">
        <button class="tab-button active" onclick="switchTab('linktree1')">Linktree 1</button>
        <button class="tab-button" onclick="switchTab('linktree2')">Linktree 2</button>
        <button class="tab-button" onclick="switchTab('linktree3')">Linktree 3</button>
        <button class="tab-button" onclick="switchTab('linktree4')">Linktree 4</button>
    </div>

    <div class="container">
        <!-- Linktree 1 - Position 4 -->
        <div class="flow-section active" id="linktree1">
            <div class="sticky-container">
                <div class="phone-container">
                    <div class="phone phone1">
                        <div class="stage-label">CREATOR'S LINKTREE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="linktree">
                                <div class="profile-pic">KD</div>
                                <div class="username">Katy_Delma</div>
                                <div class="bio">💼💰 | Exploring the intersection of tech and finance | Sharing insights, guides, and tools ✨</div>
                                <div class="social-icons">
                                    <div class="social-icon">🎵</div>
                                    <div class="social-icon">▶️</div>
                                    <div class="social-icon">💻</div>
                                    <div class="social-icon">📷</div>
                                </div>
                                <div class="link-button">Instagram</div>
                                <div class="link-button">TikTok</div>
                                <div class="link-button">YouTube</div>
                                <div class="link-button highlight">How Google Pixel 10 Transforms Smartphone Tech</div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow1">→</div>

                    <div class="phone phone2">
                        <div class="stage-label">ARTICLE WITH RELATED SEARCHES</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="article phone-content">
                                <div class="article-header">
                                    <div class="article-avatar">KD</div>
                                    <div class="author-info">
                                        <h3>Katy Delma</h3>
                                        <div class="author-link">Linktree ✨</div>
                                    </div>
                                </div>
                                <div class="article-content-block">
                                    <h1 class="article-title">How Google Pixel 10 Transforms Smartphone Tech</h1>
                                    <div class="article-text">
                                        The Google Pixel 10 smartphone represents a leap forward in technology with its advanced AI capabilities and innovative features. Powered by the Google Tensor G5 chip, it enhances on-device AI tasks, revolutionizes photography, and provides seamless language translation.
                                    </div>
                                    <div class="article-text">
                                        This chip doesn't just enhance performance; it opens up new possibilities for on-device AI applications by providing power for features like the Gemini Nano model, enabling complex and generative AI tasks.
                                    </div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">Related Searches</div>
                                    <div class="search-chip">Google Pixel Pro</div>
                                    <div class="search-chip">Google Tensor G5</div>
                                    <div class="search-chip">Gemini Nano AI</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">
                                        One of the standout features is the Magic Cue, which seamlessly integrates with popular apps such as Gmail and Calendar to offer proactive suggestions and display relevant information at a glance. This feature not only enhances user convenience and efficiency but also upholds privacy.
                                    </div>
                                    <div class="article-text">
                                        Photography has been taken up a notch with a 5x telephoto lens and Super Res Zoom, boasting up to 20x zoom for capturing distant details. The Google Pixel 10 does not disappoint in the camera department, improving on past success with higher-quality photos achievable with faster autofocusing and advanced AI features.
                                    </div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">More Related Searches</div>
                                    <div class="search-chip">Pixel 10 Camera</div>
                                    <div class="search-chip">5x Telephoto Lens</div>
                                    <div class="search-chip">Magic Cue Features</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">
                                        The Pixel 10's unique AI-driven experiences do not stop at picture-taking. With the Pixel 10, AI takes on an even more comprehensive role, supporting real-time call translations through Voice Translate which allows conversations to flow naturally across different languages.
                                    </div>
                                    <div class="article-text">
                                        The visual and tactile appeal of the Pixel 10 cannot be understated. The series comes with a modern design incorporating a satin-finish metal frame and polished glass back, available in four distinct color options: Obsidian, Frost, Indigo, and Lemongrass.
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow2">→</div>

                    <div class="phone phone3">
                        <div class="stage-label">BRANDED SEARCH RESULTS PAGE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="serp phone-content">
                                <div class="search-bar">🔍 Google Pixel Pro</div>
                                
                                <div class="serp-result">
                                    <div class="sponsored-badge">Sponsored</div>
                                    <div class="result-url">google.com</div>
                                    <div class="result-title">Get Google One Premium Storage</div>
                                    <div class="result-description">Shop Online - 2 TB of storage w/ VPN & Premium features on $9.99/mo plan w/AutoPay.</div>
                                    <button class="visit-button">Visit Website</button>
                                </div>

                                <div class="serp-result">
                                    <div class="sponsored-badge">Sponsored</div>
                                    <div class="result-url">t-mobile.com</div>
                                    <div class="result-title">Get Google Pixel 10 Pro On Us</div>
                                    <div class="result-description">Shop Online or In-Store - On us via 24 mo crdt w/ new line on $100+/mo plan w/AutoPay.</div>
                                    <button class="visit-button">Visit Website</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Linktree 2 - Position 1 -->
        <div class="flow-section" id="linktree2">
            <div class="sticky-container">
                <div class="phone-container">
                    <div class="phone phone1">
                        <div class="stage-label">CREATOR'S LINKTREE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="linktree blue">
                                <div class="profile-pic">KD</div>
                                <div class="username">Katy_Delma</div>
                                <div class="bio">💼💰 | Exploring the intersection of tech and finance | Sharing insights, guides, and tools ✨</div>
                                <div class="social-icons">
                                    <div class="social-icon">🎵</div>
                                    <div class="social-icon">▶️</div>
                                    <div class="social-icon">💻</div>
                                    <div class="social-icon">📷</div>
                                </div>
                                <div class="link-button highlight-alt1">How Google Pixel 10 Transforms Smartphone Tech</div>
                                <div class="link-button">YouTube</div>
                                <div class="link-button">Instagram</div>
                                <div class="link-button">TikTok</div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow1">→</div>

                    <div class="phone phone2">
                        <div class="stage-label">ARTICLE WITH RELATED SEARCHES</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="article blue phone-content">
                                <div class="article-header">
                                    <div class="article-avatar">KD</div>
                                    <div class="author-info">
                                        <h3>Katy Delma</h3>
                                        <div class="author-link">Linktree ✨</div>
                                    </div>
                                </div>
                                <div class="article-content-block">
                                    <h1 class="article-title">How Google Pixel 10 Transforms Smartphone Tech</h1>
                                    <div class="article-text">Revolutionary AI-powered photography meets stunning design. The Pixel 10 introduces breakthrough features that redefine mobile computing for 2025 with the powerful Tensor G5 chip.</div>
                                    <div class="article-text">This chip doesn't just enhance performance; it opens up new possibilities for on-device AI applications by providing power for features like the Gemini Nano model, enabling complex and generative AI tasks without cloud dependency.</div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">Related Searches</div>
                                    <div class="search-chip alt1">Best Smartphone 2025</div>
                                    <div class="search-chip alt1">Pixel 10 Camera</div>
                                    <div class="search-chip alt1">On-Device AI</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">Adding to these innovative features is Pixel Journal, providing a private space for user reflection and well-being with personalized writing prompts and pattern insights, enhanced with AI.</div>
                                    <div class="article-text">The AI enhancements also extend to the sound experience. The Pixel 10 Recorder can now transform vocal recordings into music tracks, allowing for a thriving environment for creative expression.</div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">More Related Searches</div>
                                    <div class="search-chip alt1">Pixel Journal App</div>
                                    <div class="search-chip alt1">AI Music Creation</div>
                                    <div class="search-chip alt1">Gboard AI Tools</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">Writing Tools in Gboard have been improved with style-specific rewrites and suggestions boosted by voice commands.</div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow2">→</div>

                    <div class="phone phone3">
                        <div class="stage-label">BRANDED SEARCH RESULTS PAGE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="serp blue phone-content">
                                <div class="search-bar">🔍 Best Smartphone 2025</div>
                                
                                <div class="serp-result">
                                    <div class="sponsored-badge alt1">Sponsored</div>
                                    <div class="result-url">bestbuy.com</div>
                                    <div class="result-title">Google Pixel 10 - Save $200</div>
                                    <div class="result-description">Limited time offer on the latest Pixel with AI features. Free shipping + trade-in credit.</div>
                                    <button class="visit-button alt1">Visit Website</button>
                                </div>

                                <div class="serp-result">
                                    <div class="sponsored-badge alt1">Sponsored</div>
                                    <div class="result-url">verizon.com</div>
                                    <div class="result-title">Switch to Verizon - Get Pixel 10 Free</div>
                                    <div class="result-description">When you switch and trade in. Plus unlimited data for your whole family.</div>
                                    <button class="visit-button alt1">Visit Website</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Linktree 3 - Position 2 -->
        <div class="flow-section" id="linktree3">
            <div class="sticky-container">
                <div class="phone-container">
                    <div class="phone phone1">
                        <div class="stage-label">CREATOR'S LINKTREE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="linktree purple">
                                <div class="profile-pic">KD</div>
                                <div class="username">Katy_Delma</div>
                                <div class="bio">💼💰 | Exploring the intersection of tech and finance | Sharing insights, guides, and tools ✨</div>
                                <div class="social-icons">
                                    <div class="social-icon">🎵</div>
                                    <div class="social-icon">▶️</div>
                                    <div class="social-icon">💻</div>
                                    <div class="social-icon">📷</div>
                                </div>
                                <div class="link-button">TikTok</div>
                                <div class="link-button highlight-alt2">How Google Pixel 10 Transforms Smartphone Tech</div>
                                <div class="link-button">Instagram</div>
                                <div class="link-button">YouTube</div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow1">→</div>

                    <div class="phone phone2">
                        <div class="stage-label">ARTICLE WITH RELATED SEARCHES</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="article purple phone-content">
                                <div class="article-header">
                                    <div class="article-avatar">KD</div>
                                    <div class="author-info">
                                        <h3>Katy Delma</h3>
                                        <div class="author-link">Linktree ✨</div>
                                    </div>
                                </div>
                                <div class="article-content-block">
                                    <h1 class="article-title">How Google Pixel 10 Transforms Smartphone Tech</h1>
                                    <div class="article-text">Experience the future with Tensor G5 chip. Advanced machine learning brings unprecedented speed and intelligence to every interaction, from photography to real-time translation.</div>
                                    <div class="article-text">This chip doesn't just enhance performance; it opens up new possibilities for on-device AI applications by providing power for features like the Gemini Nano model.</div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">Related Searches</div>
                                    <div class="search-chip alt2">Pixel 10 vs iPhone</div>
                                    <div class="search-chip alt2">Tensor G5 Chip</div>
                                    <div class="search-chip alt2">Real-Time Translation</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">The Pixel 10's unique AI-driven experiences support real-time call translations through Voice Translate which allows conversations to flow naturally across different languages, including English, Spanish, and French.</div>
                                    <div class="article-text">In a move supporting long-term value, Google ensures that every Pixel 10 smartphone experience will be continually enhanced through software updates for seven years delivering sustained performance.</div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">More Related Searches</div>
                                    <div class="search-chip alt2">Voice Translate</div>
                                    <div class="search-chip alt2">7 Years Updates</div>
                                    <div class="search-chip alt2">Android 15 Features</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">This 'never-aging' promise is a significant leap toward longevity and sustainability in smartphone usage.</div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow2">→</div>

                    <div class="phone phone3">
                        <div class="stage-label">BRANDED SEARCH RESULTS PAGE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="serp purple phone-content">
                                <div class="search-bar">🔍 Tensor G5 Chip</div>
                                
                                <div class="serp-result">
                                    <div class="sponsored-badge alt2">Sponsored</div>
                                    <div class="result-url">google.com</div>
                                    <div class="result-title">Tensor G5 - The Brain Behind Pixel 10</div>
                                    <div class="result-description">Discover how Google's custom chip revolutionizes mobile AI. Learn more about Pixel 10.</div>
                                    <button class="visit-button alt2">Visit Website</button>
                                </div>

                                <div class="serp-result">
                                    <div class="sponsored-badge alt2">Sponsored</div>
                                    <div class="result-url">amazon.com</div>
                                    <div class="result-title">Google Pixel 10 Unlocked</div>
                                    <div class="result-description">Prime members get exclusive pricing. Free returns and fast shipping available.</div>
                                    <button class="visit-button alt2">Visit Website</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Linktree 4 - Position 3 -->
        <div class="flow-section" id="linktree4">
            <div class="sticky-container">
                <div class="phone-container">
                    <div class="phone phone1">
                        <div class="stage-label">CREATOR'S LINKTREE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="linktree green">
                                <div class="profile-pic">KD</div>
                                <div class="username">Katy_Delma</div>
                                <div class="bio">💼💰 | Exploring the intersection of tech and finance | Sharing insights, guides, and tools ✨</div>
                                <div class="social-icons">
                                    <div class="social-icon">🎵</div>
                                    <div class="social-icon">▶️</div>
                                    <div class="social-icon">💻</div>
                                    <div class="social-icon">📷</div>
                                </div>
                                <div class="link-button">YouTube</div>
                                <div class="link-button">TikTok</div>
                                <div class="link-button highlight-alt3">How Google Pixel 10 Transforms Smartphone Tech</div>
                                <div class="link-button">Instagram</div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow1">→</div>

                    <div class="phone phone2">
                        <div class="stage-label">ARTICLE WITH RELATED SEARCHES</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="article green phone-content">
                                <div class="article-header">
                                    <div class="article-avatar">KD</div>
                                    <div class="author-info">
                                        <h3>Katy Delma</h3>
                                        <div class="author-link">Linktree ✨</div>
                                    </div>
                                </div>
                                <div class="article-content-block">
                                    <h1 class="article-title">How Google Pixel 10 Transforms Smartphone Tech</h1>
                                    <div class="article-text">Sustainability meets innovation. The Pixel 10 features recycled materials and energy-efficient design while delivering flagship performance powered by the revolutionary Tensor G5 chip.</div>
                                    <div class="article-text">This chip doesn't just enhance performance; it opens up new possibilities for on-device AI applications while maintaining exceptional battery efficiency.</div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">Related Searches</div>
                                    <div class="search-chip alt3">Eco-Friendly Phone</div>
                                    <div class="search-chip alt3">Pixel 10 Battery Life</div>
                                    <div class="search-chip alt3">Sustainable Tech</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">The visual and tactile appeal of the Pixel 10 cannot be understated. The series comes with a modern design incorporating a satin-finish metal frame and polished glass back, available in four distinct color options.</div>
                                    <div class="article-text">Furthermore, switching to Google Pixel has been streamlined, as it offers compatible experiences with popular devices, ensuring that users do not feel isolated from other ecosystems.</div>
                                </div>

                                <div class="related-searches">
                                    <div class="search-title">More Related Searches</div>
                                    <div class="search-chip alt3">Pixel Watch 3</div>
                                    <div class="search-chip alt3">Pixel Buds Pro 2</div>
                                    <div class="search-chip alt3">3000 Nits Display</div>
                                </div>

                                <div class="article-content-block">
                                    <div class="article-text">Additional seamless integrations are evident with accessories like the Pixel Watch and Pixel Buds with dynamic spatial audio.</div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="arrow arrow2">→</div>

                    <div class="phone phone3">
                        <div class="stage-label">BRANDED SEARCH RESULTS PAGE</div>
                        <div class="phone-screen">
                            <div class="phone-notch"></div>
                            <div class="serp green phone-content">
                                <div class="search-bar">🔍 Eco-Friendly Phone</div>
                                
                                <div class="serp-result">
                                    <div class="sponsored-badge alt3">Sponsored</div>
                                    <div class="result-url">google.com</div>
                                    <div class="result-title">Pixel 10 - Built with 70% Recycled Materials</div>
                                    <div class="result-description">Our most sustainable phone yet. Carbon neutral shipping and energy efficient design.</div>
                                    <button class="visit-button alt3">Visit Website</button>
                                </div>

                                <div class="serp-result">
                                    <div class="sponsored-badge alt3">Sponsored</div>
                                    <div class="result-url">att.com</div>
                                    <div class="result-title">AT&T - Trade In & Go Green</div>
                                    <div class="result-description">Recycle your old device and get the new Pixel 10. We'll plant a tree with every purchase.</div>
                                    <button class="visit-button alt3">Visit Website</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Solar Flow Section -->
    <div class="solar-flow-section">
        <div class="container">
            <div class="solar-flow-header">
                <h2>Solar Flow - User Journey</h2>
                <p>Multiple entry points → Content with keyword block → SERP monetization</p>
            </div>

            <div class="flow-section" style="display: block; min-height: 300vh;">
                <div class="sticky-container">
                    <div class="phone-container-wrapper">
                        <div class="phone-with-controls">
                            <div class="solar-entry-controls" style="margin-right: 20px;">
                                <div class="solar-entry-label">ENTRY POINT OPTIONS</div>
                                <div class="solar-toggle-container" style="flex-direction: column; gap: 10px;">
                                    <button class="toggle-btn active" onclick="showSolarSocial()" style="width: 100%;">Socials</button>
                                    <button class="toggle-btn" onclick="showSolarThankYou()" style="width: 100%;">Thank You Page</button>
                                    <button class="toggle-btn" onclick="showSolarDisqualify()" style="width: 100%;">Disqualifying Offer</button>
                                    <button class="toggle-btn" onclick="showSolarLinktree()" style="width: 100%;">Linktree</button>
                                </div>
                            </div>

                            <div class="phone phone1-solar">
                                <div class="phone-screen">
                                    <div class="phone-notch"></div>

                                    <!-- Facebook Ad -->
                                    <div id="solar-social" class="phone-content" style="display: block; background: #f0f2f5;">
                                        <!-- Facebook Header -->
                                        <div style="background: white; padding: 8px 12px; border-bottom: 1px solid #e4e6ea; display: flex; align-items: center; justify-content: space-between;">
                                            <div style="font-size: 24px; font-weight: 700; color: #1877f2;">facebook</div>
                                            <div style="display: flex; gap: 12px;">
                                                <div style="width: 36px; height: 36px; background: #e4e6ea; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 18px;">🔍</div>
                                                <div style="width: 36px; height: 36px; background: #e4e6ea; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 18px;">💬</div>
                                            </div>
                                        </div>

                                        <!-- Ad Post -->
                                        <div style="background: white; border-radius: 0; margin-top: 8px; box-shadow: 0 1px 2px rgba(0,0,0,0.1);">
                                            <div style="padding: 12px 16px;">
                                                <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 12px;">
                                                    <div style="width: 40px; height: 40px; border-radius: 50%; background: linear-gradient(135deg, #f5a623, #4CAF50); display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; font-size: 14px;">ST</div>
                                                    <div style="flex: 1;">
                                                        <div style="font-weight: 600; font-size: 15px; color: #050505;">SolarTech Solutions</div>
                                                        <div style="font-size: 12px; color: #65676b; display: flex; align-items: center; gap: 4px;">
                                                            <span>Sponsored</span>
                                                            <span>•</span>
                                                            <span>🌍</span>
                                                        </div>
                                                    </div>
                                                    <div style="color: #65676b; font-size: 24px; cursor: pointer; line-height: 1;">⋯</div>
                                                </div>
                                                <p style="font-size: 14px; margin-bottom: 12px; line-height: 1.4; color: #050505;">Ready to lower your energy bills? 🌞 Discover how solar panels can save you thousands while helping the planet. Get a free quote today!</p>
                                            </div>
                                            
                                            <!-- Solar Panel Image -->
                                            <div style="width: 100%; height: 200px; background: linear-gradient(135deg, #1e3c72 0%, #2a5298 50%, #7e8ba3 100%); position: relative; overflow: hidden;">
                                                <!-- Solar Panel Grid -->
                                                <div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 3px; padding: 15px; height: 100%;">
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                    <div style="background: linear-gradient(135deg, #1a237e 0%, #283593 50%, #3949ab 100%); border: 1px solid #5c6bc0; border-radius: 2px; box-shadow: inset 0 0 20px rgba(255,255,255,0.1);"></div>
                                                </div>
                                                
                                                <!-- Sun/Light Effect -->
                                                <div style="position: absolute; top: -30px; right: -30px; width: 100px; height: 100px; background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%); border-radius: 50%;"></div>
                                                
                                                <!-- Play Button -->
                                                <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 60px; height: 60px; background: rgba(255,255,255,0.95); border-radius: 50%; display: flex; align-items: center; justify-content: center; box-shadow: 0 4px 12px rgba(0,0,0,0.3);">
                                                    <div style="width: 0; height: 0; border-left: 18px solid #1877f2; border-top: 12px solid transparent; border-bottom: 12px solid transparent; margin-left: 4px;"></div>
                                                </div>
                                            </div>

                                            <div style="padding: 12px 16px; background: #f7f8fa;">
                                                <div style="font-size: 12px; color: #65676b; text-transform: uppercase; margin-bottom: 2px; letter-spacing: 0.5px;">SOLARTECHSOLUTIONS.COM</div>
                                                <div style="font-size: 16px; font-weight: 600; color: #050505; margin-bottom: 8px; line-height: 1.3;">How Solar Panels Reduce Your Energy Costs</div>
                                                <div style="font-size: 13px; color: #65676b; line-height: 1.4;">Save money and go green with residential solar installation.</div>
                                            </div>

                                            <!-- Facebook Engagement Bar -->
                                            <div style="padding: 12px 16px; border-top: 1px solid #e4e6ea;">
                                                <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; font-size: 13px; color: #65676b;">
                                                    <div>👍❤️ 342</div>
                                                    <div>28 comments · 15 shares</div>
                                                </div>
                                                <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 4px; padding-top: 8px; border-top: 1px solid #e4e6ea;">
                                                    <button style="background: none; border: none; padding: 6px; color: #65676b; font-size: 13px; font-weight: 600; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 6px;">
                                                        <span style="font-size: 18px;">👍</span> Like
                                                    </button>
                                                    <button style="background: none; border: none; padding: 6px; color: #65676b; font-size: 13px; font-weight: 600; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 6px;">
                                                        <span style="font-size: 18px;">💬</span> Comment
                                                    </button>
                                                    <button style="background: none; border: none; padding: 6px; color: #65676b; font-size: 13px; font-weight: 600; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 6px;">
                                                        <span style="font-size: 18px;">↗️</span> Share
                                                    </button>
                                                </div>
                                            </div>

                                            <!-- Learn More Button -->
                                            <div style="padding: 0 16px 12px;">
                                                <button style="background: #1877f2; color: white; border: none; padding: 10px 16px; border-radius: 6px; font-weight: 600; font-size: 15px; width: 100%; cursor: pointer;">Learn More</button>
                                            </div>
                                        </div>
                                    </div>

                                    <!-- Thank You Page -->
                                    <div id="solar-thankyou" class="phone-content" style="display: none; background: linear-gradient(180deg, #f5f7fa 0%, #e8ecf1 100%);">
                                        <div style="text-align: center; padding: 50px 30px;">
                                            <div style="width: 90px; height: 90px; background: linear-gradient(135deg, #4CAF50, #45a049); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 25px; font-size: 50px; box-shadow: 0 4px 12px rgba(76, 175, 80, 0.3);">✓</div>
                                            <h2 style="font-size: 26px; font-weight: 700; margin-bottom: 12px; color: #1a1a1a;">Thank You!</h2>
                                            <p style="font-size: 15px; color: #666; margin-bottom: 30px; line-height: 1.5;">Your request has been received. A solar expert will contact you within 24 hours to discuss your customized solar solution.</p>
                                            
                                            <div style="background: white; border-radius: 12px; padding: 20px; margin-bottom: 20px; text-align: left; box-shadow: 0 2px 8px rgba(0,0,0,0.08);">
                                                <h3 style="font-size: 16px; font-weight: 600; margin-bottom: 12px; color: #1a1a1a;">What Happens Next?</h3>
                                                <ul style="font-size: 14px; color: #555; line-height: 2; padding-left: 20px;">
                                                    <li>Free consultation call</li>
                                                    <li>Home energy assessment</li>
                                                    <li>Custom savings estimate</li>
                                                    <li>Financing options review</li>
                                                </ul>
                                            </div>

                                            <div style="background: #f8f9fa; border-radius: 12px; padding: 18px; text-align: left;">
                                                <h4 style="font-size: 14px; font-weight: 600; margin-bottom: 12px; color: #1a1a1a;">While you wait, explore:</h4>
                                                <button style="background: linear-gradient(135deg, #4CAF50, #45a049); color: white; border: none; padding: 12px; border-radius: 8px; width: 100%; font-size: 14px; font-weight: 600; margin-bottom: 10px; cursor: pointer;">Solar Panel Types Guide</button>
                                                <button style="background: linear-gradient(135deg, #4CAF50, #45a049); color: white; border: none; padding: 12px; border-radius: 8px; width: 100%; font-size: 14px; font-weight: 600; cursor: pointer;">Tax Credit Calculator</button>
                                            </div>
                                        </div>
                                    </div>

                                    <!-- Disqualifying Offer Popup -->
                                    <div id="solar-disqualify" class="phone-content" style="display: none; background: rgba(0,0,0,0.7); display: flex; align-items: center; justify-content: center; padding: 20px;">
                                        <div style="background: white; border-radius: 16px; padding: 30px 24px; max-width: 280px; text-align: center; box-shadow: 0 8px 24px rgba(0,0,0,0.2);">
                                            <div style="font-size: 40px; margin-bottom: 15px;">⚠️</div>
                                            <h2 style="font-size: 20px; font-weight: 700; margin-bottom: 12px; color: #1a1a1a;">Wait! Don't Go Yet</h2>
                                            <p style="font-size: 14px; color: #666; margin-bottom: 20px; line-height: 1.5;">Your home may not be ideal for solar panels, but we found other great energy solutions for you:</p>
                                            
                                            <div style="background: #f8f9fa; border-radius: 10px; padding: 16px; margin-bottom: 12px; text-align: left;">
                                                <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 8px;">
                                                    <div style="width: 40px; height: 40px; background: linear-gradient(135deg, #667eea, #764ba2); border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 20px;">🌲</div>
                                                    <h3 style="font-size: 15px; font-weight: 600; color: #1a1a1a;">Tree Trimming Services</h3>
                                                </div>
                                                <p style="font-size: 12px; color: #666; margin-bottom: 10px;">Professional tree care to optimize sunlight and reduce energy costs.</p>
                                                <button style="background: linear-gradient(135deg, #667eea, #764ba2); color: white; border: none; padding: 10px; border-radius: 8px; font-size: 13px; font-weight: 600; width: 100%; cursor: pointer;">Get Quote</button>
                                            </div>

                                            <div style="background: #f8f9fa; border-radius: 10px; padding: 16px; text-align: left;">
                                                <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 8px;">
                                                    <div style="width: 40px; height: 40px; background: linear-gradient(135deg, #f5a623, #f57c00); border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 20px;">🏠</div>
                                                    <h3 style="font-size: 15px; font-weight: 600; color: #1a1a1a;">Home Energy Audit</h3>
                                                </div>
                                                <p style="font-size: 12px; color: #666; margin-bottom: 10px;">Find hidden energy waste and save hundreds per year.</p>
                                                <button style="background: linear-gradient(135deg, #f5a623, #f57c00); color: white; border: none; padding: 10px; border-radius: 8px; font-size: 13px; font-weight: 600; width: 100%; cursor: pointer;">Schedule Audit</button>
                                            </div>
                                        </div>
                                    </div>

                                    <!-- Business Linktree -->
                                    <div id="solar-linktree" class="phone-content" style="display: none; background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);">
                                        <div style="text-align: center; padding: 40px 24px;">
                                            <div style="width: 90px; height: 90px; border-radius: 20px; background: linear-gradient(135deg, #f5a623, #4CAF50); display: flex; align-items: center; justify-content: center; margin: 0 auto 20px; font-size: 40px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">☀️</div>
                                            <h2 style="font-size: 22px; font-weight: 700; margin-bottom: 8px; color: #1a1a1a;">SolarTech Solutions</h2>
                                            <p style="font-size: 13px; color: #666; margin-bottom: 30px;">Leading Provider of Residential Solar Energy</p>
                                            
                                            <div style="display: flex; flex-direction: column; gap: 12px;">
                                                <button style="background: white; color: #1a1a1a; border: 2px solid #e0e0e0; padding: 16px; border-radius: 12px; font-size: 14px; font-weight: 600; box-shadow: 0 2px 4px rgba(0,0,0,0.05); cursor: pointer; text-align: left;">
                                                    <div style="display: flex; align-items: center; justify-content: space-between;">
                                                        <div>
                                                            <div style="font-size: 15px; margin-bottom: 4px;">📊 Free Energy Assessment</div>
                                                            <div style="font-size: 11px; color: #666; font-weight: 400;">Calculate your potential savings</div>
                                                        </div>
                                                        <div style="color: #667eea;">→</div>
                                                    </div>
                                                </button>

                                                <button style="background: white; color: #1a1a1a; border: 2px solid #e0e0e0; padding: 16px; border-radius: 12px; font-size: 14px; font-weight: 600; box-shadow: 0 2px 4px rgba(0,0,0,0.05); cursor: pointer; text-align: left;">
                                                    <div style="display: flex; align-items: center; justify-content: space-between;">
                                                        <div>
                                                            <div style="font-size: 15px; margin-bottom: 4px;">💰 Financing Options</div>
                                                            <div style="font-size: 11px; color: #666; font-weight: 400;">Flexible payment plans available</div>
                                                        </div>
                                                        <div style="color: #667eea;">→</div>
                                                    </div>
                                                </button>

                                                <button style="background: white; color: #1a1a1a; border: 2px solid #e0e0e0; padding: 16px; border-radius: 12px; font-size: 14px; font-weight: 600; box-shadow: 0 2px 4px rgba(0,0,0,0.05); cursor: pointer; text-align: left;">
                                                    <div style="display: flex; align-items: center; justify-content: space-between;">
                                                        <div>
                                                            <div style="font-size: 15px; margin-bottom: 4px;">📞 Schedule Consultation</div>
                                                            <div style="font-size: 11px; color: #666; font-weight: 400;">Talk to a solar expert</div>
                                                        </div>
                                                        <div style="color: #667eea;">→</div>
                                                    </div>
                                                </button>

                                                <button style="background: linear-gradient(135deg, #4CAF50, #45a049); color: white; border: none; padding: 16px; border-radius: 12px; font-size: 14px; font-weight: 600; box-shadow: 0 2px 8px rgba(76, 175, 80, 0.3); cursor: pointer;">
                                                    📖 How Solar Reduces Costs & Boosts Home Value
                                                </button>
                                            </div>

                                            <div style="display: flex; gap: 20px; justify-content: center; margin-top: 30px; padding-top: 20px; border-top: 1px solid #e0e0e0;">
                                                <a href="#" style="color: #666; text-decoration: none; font-size: 13px;">About</a>
                                                <a href="#" style="color: #666; text-decoration: none; font-size: 13px;">Contact</a>
                                                <a href="#" style="color: #666; text-decoration: none; font-size: 13px;">Reviews</a>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="arrow arrow1">→</div>

                        <div class="phone phone2-solar">
                           <div class="phone phone2-solar">
    <div class="stage-label">CONTENT WITH KEYWORD BLOCK</div>
    <div class="phone-screen">
        <div class="phone-notch"></div>
        <div class="article solar phone-content" style="background: white; padding: 0;">
            <!-- Header -->
            <div style="display: flex; align-items: center; justify-between; padding: 15px; border-bottom: 1px solid #e0e0e0;">
                <div style="font-size: 20px;">☰</div>
                <div style="display: flex; align-items: center; gap: 8px;">
                    <div style="width: 24px; height: 24px; background: #ff9500; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                        <span style="color: white; font-weight: bold; font-size: 12px;">N</span>
                    </div>
                    <span style="font-weight: 700; font-size: 16px;">Nation</span>
                </div>
                <div style="width: 20px;"></div>
            </div>

            <div style="padding: 20px;">
                <!-- Article Title -->
                <h1 style="font-size: 22px; font-weight: 700; line-height: 1.3; margin-bottom: 10px; color: #1a1a1a;">
                    How Solar Energy Reduces Costs and Boosts Home Value
                </h1>
                
                <div style="font-size: 12px; color: #999; margin-bottom: 20px;">By Nikki Cross • Jan 9, 2025</div>
                
                <!-- Article Body -->
                <p style="font-size: 14px; color: #333; line-height: 1.6; margin-bottom: 20px;">
                    Solar energy presents an exceptional opportunity for American homeowners to realize significant financial savings alongside environmental benefits. By reducing electricity bills and potentially increasing property values, solar panels offer a versatile solution to lower energy consumption. With incentives available to mitigate initial costs and community solar projects providing accessible alternatives, solar power serves as an efficient and sustainable choice for diverse households. Examine the factors shaping solar's appeal and discover its transformative impact on energy use and household economics.
                </p>

                <!-- Related Searches -->
                <div style="margin-bottom: 20px;">
                    <div style="font-size: 11px; color: #666; font-weight: 600; margin-bottom: 12px;">Related searches</div>
                    <div style="display: flex; flex-direction: column; gap: 8px;">
                        <button style="background: #5856d6; color: white; border: none; padding: 14px 16px; border-radius: 8px; font-size: 14px; font-weight: 600; text-align: left; display: flex; align-items: center; justify-between; cursor: pointer;">
                            <span style="display: flex; align-items: center; gap: 8px;">
                                <span>›</span>
                                <span>Solar Panel Installation</span>
                            </span>
                            <span>›</span>
                        </button>
                        <button style="background: #5856d6; color: white; border: none; padding: 14px 16px; border-radius: 8px; font-size: 14px; font-weight: 600; text-align: left; display: flex; align-items: center; justify-between; cursor: pointer;">
                            <span style="display: flex; align-items: center; gap: 8px;">
                                <span>›</span>
                                <span>Residential Solar Panels Near Me</span>
                            </span>
                            <span>›</span>
                        </button>
                        <button style="background: #5856d6; color: white; border: none; padding: 14px 16px; border-radius: 8px; font-size: 14px; font-weight: 600; text-align: left; display: flex; align-items: center; justify-between; cursor: pointer;">
                            <span style="display: flex; align-items: center; gap: 8px;">
                                <span>›</span>
                                <span>Solar Panel Energy Savings</span>
                            </span>
                            <span>›</span>
                        </button>
                    </div>
                </div>

                <!-- Read More -->
                <div style="text-align: center; margin-bottom: 25px;">
                    <button style="color: #ff9500; background: none; border: none; font-weight: 600; font-size: 14px; cursor: pointer;">
                        Read More...
                    </button>
                </div>

                <!-- Author Bio -->
                <div style="background: #f8f9fa; border-radius: 12px; padding: 16px; margin-bottom: 20px;">
                    <div style="display: flex; gap: 12px;">
                        <div style="width: 48px; height: 48px; background: #ff9500; border-radius: 50%; display: flex; align-items: center; justify-content: center; flex-shrink: 0;">
                            <span style="color: white; font-weight: bold; font-size: 20px;">N</span>
                        </div>
                        <div>
                            <h3 style="font-weight: 700; font-size: 16px; margin-bottom: 4px;">Nikki Cross</h3>
                            <p style="font-size: 11px; color: #666; margin-bottom: 8px;">Contributor</p>
                            <p style="font-size: 12px; color: #555; line-height: 1.5;">
                                Nikki Cross is a versatile writer with a passion for uncovering insightful stories and delivering practical advice. Covering a wide range of topics—from finance and technology to travel and lifestyle—she strives to provide readers with clear, engaging, and informative content. When she's not writing, Nikki enjoys exploring new cities, trying out the latest tech gadgets, and hunting for the best coffee spots.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Footer -->
                <div style="border-top: 1px solid #e0e0e0; padding-top: 16px; text-align: center;">
                    <div style="display: flex; align-items: center; justify-content: center; gap: 8px; margin-bottom: 12px;">
                        <div style="width: 24px; height: 24px; background: #ff9500; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                            <span style="color: white; font-weight: bold; font-size: 12px;">N</span>
                        </div>
                        <span style="font-weight: 700; font-size: 16px;">Nation</span>
                    </div>
                    <div style="display: flex; justify-content: center; gap: 16px; font-size: 11px; color: #666;">
                        <a href="#" style="color: #666; text-decoration: none;">About</a>
                        <a href="#" style="color: #666; text-decoration: none;">Contact Us</a>
                        <a href="#" style="color: #666; text-decoration: none;">Privacy Policy</a>
                        <a href="#" style="color: #666; text-decoration: none;">Terms</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
                        <div class="arrow arrow2">→</div>

                        <div class="phone phone3-solar">
                           <div class="phone phone3-solar">
    <div class="stage-label">SERP (SEARCH ENGINE RESULTS PAGE)</div>
    <div class="phone-screen">
        <div class="phone-notch"></div>
        <div class="serp solar phone-content" style="background: white; padding: 20px;">
            <!-- Search Bar -->
            <div style="background: #f1f3f4; padding: 12px 16px; border-radius: 24px; display: flex; align-items: center; gap: 10px; margin-bottom: 20px;">
                <span style="font-size: 16px;">🔍</span>
                <span style="font-size: 14px; color: #5f6368;">Results for "Solar Panel Installation"</span>
            </div>
            
            <!-- Ads Section -->
            <h2 style="font-size: 16px; font-weight: 600; margin-bottom: 16px; color: #202124;">Ads</h2>
            
            <!-- Ad 1 -->
            <div style="background: #fff; border: 1px solid #dadce0; border-radius: 8px; padding: 16px; margin-bottom: 12px;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">acelenrenovaveis.com.br</div>
                <div style="font-size: 16px; font-weight: 500; color: #1a0dab; margin-bottom: 8px;">Macauba: 90,000 more jobs</div>
                <div style="font-size: 13px; color: #4d5156; margin-bottom: 2px;">Aceleri boosts careers - Commitment to the future</div>
            </div>

            <!-- Ad 2 -->
            <div style="background: #fff; border: 1px solid #dadce0; border-radius: 8px; padding: 16px; margin-bottom: 12px;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">homeadvisor.com</div>
                <div style="font-size: 16px; font-weight: 500; color: #1a0dab; margin-bottom: 8px;">Just Enter Your Zip Code</div>
                <div style="font-size: 13px; color: #4d5156; margin-bottom: 2px;">Lighting Experts</div>
            </div>

            <!-- Ad 3 -->
            <div style="background: #fff; border: 1px solid #dadce0; border-radius: 8px; padding: 16px; margin-bottom: 12px;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">energysavings.com</div>
                <div style="font-size: 16px; font-weight: 500; color: #1a0dab; margin-bottom: 8px;">Why Homes Need Energy Audits</div>
                <div style="font-size: 13px; color: #4d5156; margin-bottom: 2px;">Boost Home Energy Savings Tips</div>
            </div>

            <!-- Ad 4 -->
            <div style="background: #fff; border: 1px solid #dadce0; border-radius: 8px; padding: 16px; margin-bottom: 20px;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">sungoldpower.com</div>
                <div style="font-size: 16px; font-weight: 500; color: #1a0dab; margin-bottom: 8px;">Home & Residential Solar Kits</div>
                <div style="font-size: 13px; color: #4d5156;">Shop online at SunGoldPower for complete solar power kits for homes. Explore our selection of solar panel kits and bring renewable energy to your home with ...</div>
            </div>

            <!-- Organic Results -->
            <!-- Organic 1 -->
            <div style="background: #fff; padding: 12px 0; margin-bottom: 16px; border-bottom: 1px solid #f0f0f0;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">www.gogreensolar.com</div>
                <div style="font-size: 18px; font-weight: 500; color: #1a0dab; margin-bottom: 6px;">Shop Solar Panels for Home | GoGreenSolar</div>
                <div style="font-size: 13px; color: #4d5156; line-height: 1.5;">Our solar panels cost between $300 to $400 per panel, which is a competitive price considering the brands' top-tier quality and high standards. Some solar ...</div>
            </div>

            <!-- Organic 2 -->
            <div style="background: #fff; padding: 12px 0; margin-bottom: 16px; border-bottom: 1px solid #f0f0f0;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">www.energy.gov</div>
                <div style="font-size: 18px; font-weight: 500; color: #1a0dab; margin-bottom: 6px;">Homeowner's Guide to Going Solar - Department of Energy</div>
                <div style="font-size: 13px; color: #4d5156; line-height: 1.5;">Buying a solar energy system will likely increase your home's value. A recent study found that solar panels are viewed as upgrades, just like a renovated ...</div>
            </div>

            <!-- Organic 3 -->
            <div style="background: #fff; padding: 12px 0;">
                <div style="font-size: 11px; color: #5f6368; margin-bottom: 4px;">www.tesla.com</div>
                <div style="font-size: 18px; font-weight: 500; color: #1a0dab; margin-bottom: 6px;">Home Solar Panels and Systems | Tesla</div>
                <div style="font-size: 13px; color: #4d5156; line-height: 1.5;">Tesla uses solar panels that offer a sleek and modern take on traditional panels. With our proprietary mounting hardware, panels can be installed close to your ...</div>
            </div>
        </div>
    </div>
</div>

    <div class="footer">
        <h2>Multiple Paths to Monetization</h2>
        <p>System1 provides flexible content monetization solutions for every creator</p>
    </div>

    <script>
        function animatePhones(tabId) {
            const section = document.getElementById(tabId);
            if (!section) return;
            
            const phone1 = section.querySelector('.phone1');
            const phone2 = section.querySelector('.phone2');
            const phone3 = section.querySelector('.phone3');
            const arrow1 = section.querySelector('.arrow1');
            const arrow2 = section.querySelector('.arrow2');
            
            [phone1, phone2, phone3, arrow1, arrow2].forEach(el => {
                if (el) el.classList.remove('visible');
            });
            
            setTimeout(() => phone1?.classList.add('visible'), 200);
            setTimeout(() => arrow1?.classList.add('visible'), 1000);
            setTimeout(() => phone2?.classList.add('visible'), 1000);
            setTimeout(() => arrow2?.classList.add('visible'), 1800);
            setTimeout(() => phone3?.classList.add('visible'), 1800);
        }

        function animateSolarPhones() {
            const solarPhone1 = document.querySelector('.phone1-solar');
            const solarPhone2 = document.querySelector('.phone2-solar');
            const solarPhone3 = document.querySelector('.phone3-solar');
            const solarArrow1 = document.querySelector('.solar-flow-section .arrow1');
            const solarArrow2 = document.querySelector('.solar-flow-section .arrow2');
            
            [solarPhone1, solarPhone2, solarPhone3, solarArrow1, solarArrow2].forEach(el => {
                if (el) el.classList.remove('visible');
            });
            
            setTimeout(() => solarPhone1?.classList.add('visible'), 200);
            setTimeout(() => solarArrow1?.classList.add('visible'), 1000);
            setTimeout(() => solarPhone2?.classList.add('visible'), 1000);
            setTimeout(() => solarArrow2?.classList.add('visible'), 1800);
            setTimeout(() => solarPhone3?.classList.add('visible'), 1800);
        }

        function switchTab(tabId) {
            document.querySelectorAll('.flow-section').forEach(s => s.classList.remove('active'));
            document.querySelectorAll('.tab-button').forEach(b => b.classList.remove('active'));
            document.getElementById(tabId).classList.add('active');
            event.target.classList.add('active');
            window.scrollTo(0, 0);
            
            setTimeout(() => animatePhones(tabId), 100);
        }

        document.addEventListener('DOMContentLoaded', () => {
            animatePhones('linktree1');
        });

        let solarAnimated = false;
        window.addEventListener('scroll', () => {
            if (solarAnimated) return;
            
            const solarSection = document.querySelector('.solar-flow-section');
            if (solarSection) {
                const rect = solarSection.getBoundingClientRect();
                if (rect.top < window.innerHeight * 0.8) {
                    solarAnimated = true;
                    animateSolarPhones();
                }
            }
        });

        function showSolarSocial() {
            document.getElementById('solar-social').style.display = 'block';
            document.getElementById('solar-thankyou').style.display = 'none';
            document.getElementById('solar-disqualify').style.display = 'none';
            document.getElementById('solar-linktree').style.display = 'none';
            const buttons = document.querySelectorAll('.solar-toggle-container .toggle-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            buttons[0].classList.add('active');
        }

        function showSolarThankYou() {
            document.getElementById('solar-social').style.display = 'none';
            document.getElementById('solar-thankyou').style.display = 'block';
            document.getElementById('solar-disqualify').style.display = 'none';
            document.getElementById('solar-linktree').style.display = 'none';
            const buttons = document.querySelectorAll('.solar-toggle-container .toggle-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            buttons[1].classList.add('active');
        }

        function showSolarDisqualify() {
            document.getElementById('solar-social').style.display = 'none';
            document.getElementById('solar-thankyou').style.display = 'none';
            document.getElementById('solar-disqualify').style.display = 'flex';
            document.getElementById('solar-linktree').style.display = 'none';
            const buttons = document.querySelectorAll('.solar-toggle-container .toggle-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            buttons[2].classList.add('active');
        }

        function showSolarLinktree() {
            document.getElementById('solar-social').style.display = 'none';
            document.getElementById('solar-thankyou').style.display = 'none';
            document.getElementById('solar-disqualify').style.display = 'none';
            document.getElementById('solar-linktree').style.display = 'block';
            const buttons = document.querySelectorAll('.solar-toggle-container .toggle-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            buttons[3].classList.add('active');
        }
    </script>
</body>
</html>
