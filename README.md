<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>風格策展所 | 您的精品風格夥伴</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8f8f8; /* 輕柔的背景色 */
            color: #333;
        }
        .product-card {
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        .btn-primary {
            background-color: #4a5568; /* 深灰色按鈕 */
            color: white;
            padding: 10px 20px;
            border-radius: 8px;
            transition: background-color 0.2s ease-in-out;
        }
        .btn-primary:hover {
            background-color: #2d3748; /* 更深的灰色 */
        }
        .filter-checkbox:checked + label {
            background-color: #4a5568;
            color: white;
            border-color: #4a5568;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col">

    <!-- Header -->
    <header class="bg-white shadow-sm py-4 px-6 md:px-12 flex justify-between items-center sticky top-0 z-50">
        <div class="flex items-center">
            <a href="#" class="text-2xl font-bold text-gray-800 tracking-tight">風格策展所</a>
        </div>
        <nav class="hidden md:flex space-x-8">
            <a href="#" class="text-gray-600 hover:text-gray-900 font-medium">包款</a>
            <a href="#" class="text-gray-600 hover:text-gray-900 font-medium">飾品</a>
            <a href="#" class="text-gray-600 hover:text-gray-900 font-medium">鞋履</a>
            <a href="#" class="text-gray-600 hover:text-gray-900 font-medium">風格誌</a>
        </nav>
        <div class="flex items-center space-x-4">
            <button class="text-gray-600 hover:text-gray-900 focus:outline-none">
                <!-- Search Icon (Lucide React equivalent: <Search />) -->
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-search"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.3-4.3"/></svg>
            </button>
            <button class="text-gray-600 hover:text-gray-900 focus:outline-none">
                <!-- User Icon (Lucide React equivalent: <User />) -->
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-user"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
            </button>
            <button class="text-gray-600 hover:text-gray-900 focus:outline-none">
                <!-- Shopping Cart Icon (Lucide React equivalent: <ShoppingCart />) -->
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-shopping-cart"><circle cx="8" cy="21" r="1"/><circle cx="19" cy="21" r="1"/><path d="M2.05 2.05h2l2.66 12.42a2 2 0 0 0 2 1.58h9.78a2 2 0 0 0 1.95-1.57l1.65-7.43H5.12"/></svg>
            </button>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="flex-grow container mx-auto px-4 py-8 md:py-12 flex flex-col md:flex-row">
        <!-- Sidebar for Filters -->
        <aside class="w-full md:w-1/4 lg:w-1/5 bg-white p-6 rounded-lg shadow-sm mb-8 md:mb-0 md:mr-8">
            <h3 class="text-xl font-semibold mb-6 text-gray-800">篩選商品</h3>

            <!-- Category Filter -->
            <div class="mb-6">
                <h4 class="font-medium text-gray-700 mb-3">品類</h4>
                <div class="space-y-2">
                    <div class="flex items-center">
                        <input type="checkbox" id="cat-bag" value="包款" class="hidden filter-checkbox" checked>
                        <label for="cat-bag" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">包款</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="cat-accessory" value="飾品" class="hidden filter-checkbox">
                        <label for="cat-accessory" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">飾品</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="cat-shoe" value="鞋履" class="hidden filter-checkbox">
                        <label for="cat-shoe" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">鞋履</label>
                    </div>
                </div>
            </div>
            <!-- Style Filter -->
            <div class="mb-6">
                <h4 class="font-medium text-gray-700 mb-3">風格</h4>
                <div class="flex flex-wrap gap-2">
                    <div class="flex items-center">
                        <input type="checkbox" id="style-classic" value="經典" class="hidden filter-checkbox" checked>
                        <label for="style-classic" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">經典</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="style-minimalist" value="極簡主義" class="hidden filter-checkbox">
                        <label for="style-minimalist" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">極簡主義</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="style-retro" value="Y2K復古" class="hidden filter-checkbox">
                        <label for="style-retro" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">Y2K復古</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="style-professional" value="職場專業" class="hidden filter-checkbox">
                        <label for="style-professional" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">職場專業</label>
                    </div>
                </div>
            </div>

            <!-- Features Filter -->
            <div class="mb-6">
                <h4 class="font-medium text-gray-700 mb-3">實用性與特性</h4>
                <div class="flex flex-wrap gap-2">
                    <div class="flex items-center">
                        <input type="checkbox" id="feat-durable" value="耐磨防潑水" class="hidden filter-checkbox" checked>
                        <label for="feat-durable" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">耐磨防潑水</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="feat-multi" value="多功能內袋" class="hidden filter-checkbox">
                        <label for="feat-multi" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">多功能內袋</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="feat-lightweight" value="輕巧便攜" class="hidden filter-checkbox">
                        <label for="feat-lightweight" class="cursor-pointer px-3 py-1 rounded-full border border-gray-300 text-sm text-gray-600 hover:bg-gray-100 transition-colors">輕巧便攜</label>
                    </div>
                </div>
            </div>

            <!-- Price Range (Simplified) -->
            <div class="mb-6">
                <h4 class="font-medium text-gray-700 mb-3">價格範圍</h4>
                <select id="price-filter" class="w-full p-2 border border-gray-300 rounded-md text-gray-700 focus:ring-blue-500 focus:border-blue-500">
                    <option value="all">所有價格</option>
                    <option value="0-5000">NT$ 5,000 以下</option>
                    <option value="5001-15000">NT$ 5,001 - 15,000</option>
                    <option value="15001-30000">NT$ 15,001 - 30,000</option>
                    <option value="30001-above">NT$ 30,001 以上</option>
                </select>
            </div>

            <button onclick="applyFilters()" class="btn-primary w-full text-center">套用篩選</button>
        </aside>

        <!-- Product Grid -->
        <section class="w-full md:w-3/4 lg:w-4/5">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-2xl font-semibold text-gray-800">所有精品</h2>
                <div class="flex items-center space-x-2">
                    <span class="text-gray-600 text-sm">排序依據:</span>
                    <select id="sort-by" class="p-2 border border-gray-300 rounded-md text-gray-700 focus:ring-blue-500 focus:border-blue-500">
                        <option value="featured">推薦</option>
                        <option value="price-asc">價格：由低到高</option>
                        <option value="price-desc">價格：由高到低</option>
                        <option value="newest">最新上架</option>
                    </select>
                </div>
            </div>

            <!-- Products will be rendered here -->
            <div id="product-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
                <!-- Product cards will be dynamically inserted here by JavaScript -->
            </div>

            <!-- No products found message -->
            <div id="no-products-message" class="hidden text-center py-12 text-gray-500 text-lg">
                找不到符合條件的商品。請嘗試調整您的篩選條件。
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-8 px-6 md:px-12 mt-12">
        <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-8">
            <div>
                <h3 class="text-lg font-semibold mb-4">風格策展所</h3>
                <p class="text-sm text-gray-400">
                    在這裡，精品不只是商品，更是您個人風格的延伸與自我價值的肯定。
                </p>
            </div>
            <div>
                <h3 class="text-lg font-semibold mb-4">快速連結</h3>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="text-gray-400 hover:text-white">關於我們</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white">常見問題</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white">售後服務</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white">隱私權政策</a></li>
                </ul>
            </div>
            <div>
                <h3 class="text-lg font-semibold mb-4">聯繫我們</h3>
                <p class="text-sm text-gray-400">Email: info@yourcurator.com</p>
                <p class="text-sm text-gray-400">電話: +886 123 4567</p>
                <div class="flex space-x-4 mt-4">
                    <!-- Social Media Icons (placeholders) -->
                    <a href="#" class="text-gray-400 hover:text-white">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-instagram"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.5" y1="6.5" y2="6.5"/></svg>
                    </a>
                    <a href="#" class="text-gray-400 hover:text-white">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-facebook"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg>
                    </a>
                    <a href="#" class="text-gray-400 hover:text-white">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-tiktok"><path d="M9 12v10a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V12a2 2 0 0 1 2-2h3a2 2 0 0 1 2 2z"/><path d="M15 2h3a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2h-3a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2z"/><path d="M12 22V12a2 2 0 0 1 2-2h3a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2h-3a2 2 0 0 1-2-2z"/></svg>
                    </a>
                </div>
            </div>
        </div>
        <div class="text-center text-gray-500 text-sm mt-8">
            &copy; 2024 風格策展所. All rights reserved.
        </div>
    </footer>

    <script>
        // 產品資料 (模擬後端資料)
        const products = [
            {
                id: 'bag-001',
                name: '經典都會手提包',
                brand: 'Elegance Luxe',
                price: 28000,
                image: 'https://placehold.co/400x400/D4D4D4/333333?text=經典都會手提包',
                category: '包款',
                styles: ['經典', '職場專業'],
                features: ['耐磨防潑水', '多功能內袋'],
                description: '這款經典都會手提包採用頂級印壓牛皮製成，兼具耐用性與優雅外觀。多功能內袋設計，讓您的物品井然有序。是您職場與日常的完美夥伴。',
                newArrival: true
            },
            {
                id: 'bag-002',
                name: '輕奢迷你斜背包',
                brand: 'Chic Essence',
                price: 12500,
                image: 'https://placehold.co/400x400/C0C0C0/333333?text=輕奢迷你斜背包',
                category: '包款',
                styles: ['極簡主義', '日常休閒'],
                features: ['輕巧便攜'],
                description: '小巧精緻的迷你斜背包，適合日常輕裝出行。簡約設計搭配柔和色彩，輕鬆融入您的各種風格。',
                newArrival: false
            },
            {
                id: 'acc-001',
                name: '星辰系列手鍊',
                brand: 'Glimmer Craft',
                price: 5800,
                image: 'https://placehold.co/400x400/B0B0B0/333333?text=星辰系列手鍊',
                category: '飾品',
                styles: ['經典', '優雅'],
                features: [],
                description: '以璀璨星辰為靈感，精緻的純銀手鍊點綴施華洛世奇水晶，為您的手腕增添一抹光彩。',
                newArrival: true
            },
            {
                id: 'shoe-001',
                name: '法式優雅低跟鞋',
                brand: 'Pied de Rêve',
                price: 9200,
                image: 'https://placehold.co/400x400/A0A0A0/333333?text=法式優雅低跟鞋',
                category: '鞋履',
                styles: ['經典', '優雅'],
                features: [],
                description: '舒適的低跟設計，搭配柔軟羊皮內裡，讓您全天舒適。經典的法式風格，適合各種場合。',
                newArrival: false
            },
            {
                id: 'bag-003',
                name: '復古Y2K腋下包',
                brand: 'Vibe Vintage',
                price: 7500,
                image: 'https://placehold.co/400x400/E0E0E0/333333?text=復古Y2K腋下包',
                category: '包款',
                styles: ['Y2K復古', '個性'],
                features: ['耐磨防潑水'],
                description: '重現千禧年代的時尚潮流，這款腋下包是您展現個性的最佳單品。輕巧且百搭。',
                newArrival: true
            },
            {
                id: 'acc-002',
                name: '幾何造型耳環',
                brand: 'Modern Artistry',
                price: 3200,
                image: 'https://placehold.co/400x400/D0D0D0/333333?text=幾何造型耳環',
                category: '飾品',
                styles: ['極簡主義', '現代'],
                features: [],
                description: '簡約而不失設計感的幾何造型耳環，為您的日常穿搭增添藝術氣息。',
                newArrival: false
            },
            {
                id: 'bag-004',
                name: '知性公事包',
                brand: 'Professional Edge',
                price: 35000,
                image: 'https://placehold.co/400x400/B8B8B8/333333?text=知性公事包',
                category: '包款',
                styles: ['職場專業'],
                features: ['多功能內袋', '筆電隔層'],
                description: '專為職場精英設計，內含多個隔層與筆電空間，完美收納您的工作必需品。',
                newArrival: false
            },
            {
                id: 'shoe-002',
                name: '舒適休閒小白鞋',
                brand: 'Urban Comfort',
                price: 6500,
                image: 'https://placehold.co/400x400/A8A8A8/333333?text=舒適休閒小白鞋',
                category: '鞋履',
                styles: ['日常休閒'],
                features: ['輕巧便攜'],
                description: '經典小白鞋，採用透氣材質與輕量鞋底，提供全天候的舒適體驗。',
                newArrival: true
            }
        ];

        // 獲取 DOM 元素
        const productGrid = document.getElementById('product-grid');
        const noProductsMessage = document.getElementById('no-products-message');
        const filterCheckboxes = document.querySelectorAll('.filter-checkbox');
        const priceFilter = document.getElementById('price-filter');
        const sortBySelect = document.getElementById('sort-by');

        /**
         * 渲染產品卡片到頁面
         * @param {Array} productsToRender - 要渲染的產品陣列
         */
        function renderProducts(productsToRender) {
            productGrid.innerHTML = ''; // 清空現有產品
            if (productsToRender.length === 0) {
                noProductsMessage.classList.remove('hidden');
            } else {
                noProductsMessage.classList.add('hidden');
                productsToRender.forEach(product => {
                    const productCard = `
                        <div class="product-card bg-white rounded-lg shadow-md overflow-hidden transform hover:scale-105 transition duration-300">
                            <img src="${product.image}" alt="${product.name}" class="w-full h-64 object-cover">
                            <div class="p-4">
                                <h3 class="text-lg font-semibold text-gray-800 mb-1">${product.name}</h3>
                                <p class="text-sm text-gray-500 mb-2">${product.brand}</p>
                                <p class="text-xl font-bold text-gray-900 mb-4">NT$ ${product.price.toLocaleString()}</p>
                                <button class="btn-primary w-full text-center text-sm" onclick="addToCart('${product.id}')">加入購物車</button>
                            </div>
                        </div>
                    `;
                    productGrid.innerHTML += productCard;
                });
            }
        }

        /**
         * 應用篩選和排序邏輯
         */
        function applyFilters() {
            let filteredProducts = [...products]; // 複製一份產品資料，避免修改原始資料

            // 1. 類別篩選
            const selectedCategories = Array.from(document.querySelectorAll('#cat-bag:checked, #cat-accessory:checked, #cat-shoe:checked'))
                                            .map(cb => cb.value);
            if (selectedCategories.length > 0) {
                filteredProducts = filteredProducts.filter(product => selectedCategories.includes(product.category));
            }

            // 2. 風格篩選
            const selectedStyles = Array.from(document.querySelectorAll('#style-classic:checked, #style-minimalist:checked, #style-retro:checked, #style-professional:checked'))
                                        .map(cb => cb.value);
            if (selectedStyles.length > 0) {
                filteredProducts = filteredProducts.filter(product =>
                    product.styles.some(style => selectedStyles.includes(style))
                );
            }

            // 3. 特性篩選
            const selectedFeatures = Array.from(document.querySelectorAll('#feat-durable:checked, #feat-multi:checked, #feat-lightweight:checked'))
                                            .map(cb => cb.value);
            if (selectedFeatures.length > 0) {
                filteredProducts = filteredProducts.filter(product =>
                    product.features.some(feature => selectedFeatures.includes(feature))
                );
            }

            // 4. 價格篩選
            const priceRange = priceFilter.value;
            if (priceRange !== 'all') {
                const [min, max] = priceRange.split('-').map(Number);
                filteredProducts = filteredProducts.filter(product => {
                    if (priceRange === '30001-above') {
                        return product.price >= min;
                    }
                    return product.price >= min && product.price <= max;
                });
            }

            // 5. 排序
            const sortBy = sortBySelect.value;
            if (sortBy === 'price-asc') {
                filteredProducts.sort((a, b) => a.price - b.price);
            } else if (sortBy === 'price-desc') {
                filteredProducts.sort((a, b) => b.price - a.price);
            } else if (sortBy === 'newest') {
                filteredProducts.sort((a, b) => (b.newArrival ? 1 : 0) - (a.newArrival ? 1 : 0)); // 簡單模擬最新上架
            }
            // 'featured' 保持原始順序或可自定義邏輯

            renderProducts(filteredProducts); // 渲染篩選後的產品
        }

        /**
         * 模擬加入購物車功能
         * @param {string} productId - 產品ID
         */
        function addToCart(productId) {
            console.log(`產品 ID: ${productId} 已加入購物車！ (此為模擬功能)`);
            // 在實際應用中，這裡會是加入購物車的邏輯，例如更新購物車狀態或發送請求到後端
            alert('商品已成功加入購物車！'); // 使用模擬提示，實際應用中會是自定義的訊息框
        }

        // 初始化：頁面載入時渲染所有產品
        document.addEventListener('DOMContentLoaded', () => {
            applyFilters(); // 初始載入時應用預設篩選（所有產品）

            // 為篩選器和排序選項添加事件監聽器，以便即時更新
            filterCheckboxes.forEach(checkbox => {
                checkbox.addEventListener('change', applyFilters);
            });
            priceFilter.addEventListener('change', applyFilters);
            sortBySelect.addEventListener('change', applyFilters);
        });
    </script>
</body>
</html>
