<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GamePulse - Your Source for Gaming Updates</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #0f0f0f;
            color: #e0e0e0;
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: color 0.3s ease;
        }

        /* Header & Navigation */
        header {
            background-color: #1a1a2e;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid #e94560;
        }

        .header-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            color: #e94560;
        }

        .logo span {
            color: #ffffff;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav ul li a {
            color: #ffffff;
            font-weight: 500;
            padding: 8px 16px;
            border-radius: 4px;
            transition: all 0.3s ease;
        }

        nav ul li a:hover, nav ul li a.active {
            background-color: #e94560;
            color: #ffffff;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            padding: 80px 20px;
            text-align: center;
        }

        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: #ffffff;
        }

        .hero h1 span {
            color: #e94560;
        }

        .hero p {
            font-size: 20px;
            color: #b0b0b0;
            max-width: 600px;
            margin: 0 auto 30px;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
        }

        .btn {
            padding: 12px 30px;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
        }

        .btn-primary {
            background-color: #e94560;
            color: #ffffff;
        }

        .btn-primary:hover {
            background-color: #ff6b6b;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background-color: transparent;
            border: 2px solid #e94560;
            color: #e94560;
        }

        .btn-secondary:hover {
            background-color: #e94560;
            color: #ffffff;
        }

        /* Main Content */
        .main-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 40px;
        }

        /* Section Titles */
        .section-title {
            font-size: 28px;
            color: #ffffff;
            margin-bottom: 25px;
            padding-bottom: 10px;
            border-bottom: 3px solid #e94560;
            display: inline-block;
        }

        /* Featured Update */
        .featured-update {
            background-color: #1a1a2e;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 40px;
            transition: transform 0.3s ease;
        }

        .featured-update:hover {
            transform: translateY(-5px);
        }

        .featured-image {
            height: 300px;
            background: linear-gradient(45deg, #e94560, #0f3460);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            color: rgba(255,255,255,0.3);
        }

        .featured-content {
            padding: 25px;
        }

        .update-badge {
            display: inline-block;
            background-color: #e94560;
            color: #ffffff;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .featured-content h3 {
            font-size: 24px;
            color: #ffffff;
            margin-bottom: 15px;
        }

        .featured-content p {
            color: #b0b0b0;
            margin-bottom: 15px;
        }

        .update-meta {
            display: flex;
            gap: 20px;
            color: #888;
            font-size: 14px;
        }

        .update-meta span {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* Update Categories */
        .category-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }

        .category-tab {
            padding: 10px 20px;
            background-color: #1a1a2e;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
            color: #b0b0b0;
            font-weight: 500;
        }

        .category-tab:hover, .category-tab.active {
            background-color: #e94560;
            color: #ffffff;
        }

        /* Update Cards */
        .updates-grid {
            display: grid;
            gap: 20px;
        }

        .update-card {
            background-color: #1a1a2e;
            border-radius: 10px;
            padding: 20px;
            display: flex;
            gap: 20px;
            transition: all 0.3s ease;
        }

        .update-card:hover {
            transform: translateX(5px);
            border-left: 4px solid #e94560;
        }

        .update-card-image {
            width: 120px;
            height: 90px;
            background: linear-gradient(135deg, #0f3460, #e94560);
            border-radius: 8px;
            flex-shrink: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgba(255,255,255,0.3);
            font-size: 24px;
        }

        .update-card-content h4 {
            color: #ffffff;
            font-size: 18px;
            margin-bottom: 8px;
        }

        .update-card-content p {
            color: #888;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .update-card-meta {
            display: flex;
            gap: 15px;
            font-size: 12px;
            color: #666;
        }

        /* Sidebar */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .sidebar-section {
            background-color: #1a1a2e;
            border-radius: 10px;
            padding: 20px;
        }

        .sidebar-section h3 {
            color: #ffffff;
            font-size: 20px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e94560;
        }

        /* Trending List */
        .trending-list {
            list-style: none;
        }

        .trending-list li {
            padding: 12px 0;
            border-bottom: 1px solid #2a2a4e;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .trending-list li:last-child {
            border-bottom: none;
        }

        .trending-number {
            width: 30px;
            height: 30px;
            background-color: #e94560;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 14px;
        }

        .trending-list li a {
            flex: 1;
        }

        .trending-list li a:hover {
            color: #e94560;
        }

        .trending-meta {
            font-size: 12px;
            color: #666;
        }

        /* Upcoming Updates */
        .upcoming-list {
            list-style: none;
        }

        .upcoming-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 12px 0;
            border-bottom: 1px solid #2a2a4e;
        }

        .upcoming-item:last-child {
            border-bottom: none;
        }

        .upcoming-date {
            background-color: #0f3460;
            padding: 10px;
            border-radius: 8px;
            text-align: center;
            min-width: 60px;
        }

        .upcoming-date .day {
            font-size: 20px;
            font-weight: bold;
            color: #e94560;
        }

        .upcoming-date .month {
            font-size: 12px;
            color: #888;
        }

        .upcoming-item a:hover {
            color: #e94560;
        }

        /* Newsletter */
        .newsletter {
            background: linear-gradient(135deg, #e94560, #0f3460);
            border-radius: 10px;
            padding: 30px;
            text-align: center;
        }

        .newsletter h3 {
            color: #ffffff;
            margin-bottom: 10px;
        }

        .newsletter p {
            color: rgba(255,255,255,0.8);
            margin-bottom: 20px;
        }

        .newsletter-form {
            display: flex;
            gap: 10px;
        }

        .newsletter-form input {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            background-color: rgba(255,255,255,0.9);
        }

        .newsletter-form button {
            padding: 12px 25px;
            background-color: #1a1a2e;
            color: #ffffff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: background-color 0.3s ease;
        }

        .newsletter-form button:hover {
            background-color: #2a2a4e;
        }

        /* Footer */
        footer {
            background-color: #1a1a2e;
            padding: 60px 20px 20px;
            margin-top: 60px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h4 {
            color: #ffffff;
            font-size: 18px;
            margin-bottom: 20px;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 10px;
        }

        .footer-section ul li a {
            color: #888;
        }

        .footer-section ul li a:hover {
            color: #e94560;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background-color: #2a2a4e;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background-color: #e94560;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #2a2a4e;
            color: #666;
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 15px;
