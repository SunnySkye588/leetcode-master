<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <title>正在连接客服...</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font Awesome -->
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css" rel="stylesheet">
  
  <!-- 配置Tailwind -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            whatsapp: {
              primary: '#25D366',
              secondary: '#128C7E',
              dark: '#075E54',
              light: '#DCF8C6'
            },
            neutral: {
              100: '#F5F5F5',
              200: '#E5E5E5',
              300: '#D4D4D4',
              400: '#A3A3A3',
              500: '#737373',
              600: '#525252',
              700: '#404040',
              800: '#262626',
              900: '#171717'
            }
          },
          fontFamily: {
            inter: ['Inter', 'sans-serif'],
          },
        },
      }
    }
  </script>
  
  <style type="text/tailwindcss">
    @layer utilities {
      .content-auto {
        content-visibility: auto;
      }
      .bg-whatsapp-gradient {
        background: linear-gradient(135deg, #25D366 0%, #128C7E 100%);
      }
      .animate-pulse-slow {
        animation: pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite;
      }
      .shadow-whatsapp {
        box-shadow: 0 4px 20px rgba(37, 211, 102, 0.2);
      }
      .transition-all-300 {
        transition: all 0.3s ease;
      }
    }
  </style>
</head>
<body class="font-inter bg-gray-50 min-h-screen">
  <!-- 顶部导航 -->
  <header class="bg-white shadow-sm fixed top-0 left-0 right-0 z-50">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <div class="flex items-center">
        <div class="text-whatsapp-primary text-2xl mr-2">
          <i class="fa-brands fa-whatsapp"></i>
        </div>
        <h1 class="text-xl font-bold text-neutral-800">客服分流系统</h1>
      </div>
      <nav class="hidden md:flex space-x-6">
        <a href="#" class="text-neutral-600 hover:text-whatsapp-primary transition-colors">首页</a>
        <a href="#" class="text-neutral-600 hover:text-whatsapp-primary transition-colors">关于我们</a>
        <a href="#" class="text-neutral-600 hover:text-whatsapp-primary transition-colors">帮助中心</a>
      </nav>
      <button class="md:hidden text-neutral-600 text-xl">
        <i class="fa fa-bars"></i>
      </button>
    </div>
  </header>

  <!-- 主内容区 -->
  <main class="container mx-auto px-4 pt-24 pb-16">
    <div class="max-w-3xl mx-auto">
      <!-- 欢迎卡片 -->
      <div class="bg-white rounded-2xl shadow-lg overflow-hidden mb-8 transform hover:shadow-xl transition-all duration-300">
        <div class="bg-whatsapp-gradient p-6 text-white">
          <h2 class="text-2xl font-bold mb-2">智能客服分配</h2>
          <p class="opacity-90">我们正在为您分配最合适的客服人员，请稍候...</p>
        </div>
        
        <div class="p-6">
          <div class="flex flex-col md:flex-row gap-6 items-center">
            <div class="w-full md:w-2/3">
              <div id="agentInfo" class="mb-6">
                <h3 class="text-xl font-semibold mb-4">您的专属客服</h3>
                <div class="flex items-center mb-4">
                  <div id="agentAvatar" class="w-16 h-16 rounded-full bg-whatsapp-primary/10 flex items-center justify-center text-whatsapp-primary text-2xl">
                    <i class="fa fa-user"></i>
                  </div>
                  <div class="ml-4">
                    <h4 id="agentName" class="text-lg font-bold">客服人员</h4>
                    <p id="agentTitle" class="text-sm text-neutral-500">客户服务专员</p>
                  </div>
                </div>
                
                <div class="bg-gray-50 rounded-lg p-4 mb-6">
                  <div class="flex justify-between items-center mb-2">
                    <span class="text-sm text-neutral-600">匹配度</span>
                    <span class="text-whatsapp-primary font-bold">96%</span>
                  </div>
                  <div class="w-full bg-gray-200 rounded-full h-2">
                    <div id="matchProgress" class="bg-whatsapp-primary h-2 rounded-full" style="width: 0%"></div>
                  </div>
                </div>
                
                <div class="grid grid-cols-2 gap-4 mb-6">
                  <div class="bg-green-50 p-3 rounded-lg">
                    <p class="text-xs text-neutral-500">响应时间</p>
                    <p class="text-lg font-semibold">平均30秒</p>
                  </div>
                  <div class="bg-blue-50 p-3 rounded-lg">
                    <p class="text-xs text-neutral-500">满意度</p>
                    <p class="text-lg font-semibold">98%</p>
                  </div>
                </div>
              </div>
              
              <div class="flex flex-col sm:flex-row gap-3">
                <a id="whatsappBtn" href="#" target="_blank" class="bg-whatsapp-primary hover:bg-whatsapp-dark text-white font-semibold py-3 px-6 rounded-lg transition-all duration-300 transform hover:scale-105 shadow-whatsapp flex-1 flex items-center justify-center">
                  <i class="fa-brands fa-whatsapp mr-2"></i> 通过 WhatsApp 联系
                </a>
                <button id="changeAgentBtn" class="bg-gray-200 hover:bg-gray-300 text-neutral-700 font-semibold py-3 px-6 rounded-lg transition-all duration-300 flex-1 flex items-center justify-center">
                  <i class="fa fa-random mr-2"></i> 更换客服
                </button>
              </div>
            </div>
            
            <div class="w-full md:w-1/3">
              <div class="bg-gray-50 rounded-xl p-5 shadow-inner">
                <h3 class="text-center font-semibold mb-4">连接倒计时</h3>
                <div class="flex justify-center items-center">
                  <div id="countdown" class="text-5xl font-bold text-whatsapp-primary animate-pulse-slow">3</div>
                  <span class="ml-2 text-xl">秒</span>
                </div>
                <p class="text-center mt-4 text-sm text-neutral-500">若不操作，将自动跳转到 WhatsApp</p>
                
                <div class="mt-6">
                  <div class="flex justify-between items-center mb-2">
                    <span class="text-xs text-neutral-600">推荐理由</span>
                  </div>
                  <ul class="text-xs space-y-2">
                    <li class="flex items-start">
                      <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                      <span>精通您的业务领域</span>
                    </li>
                    <li class="flex items-start">
                      <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                      <span>当前在线并可立即服务</span>
                    </li>
                    <li class="flex items-start">
                      <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                      <span>流利使用您的母语</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- 其他联系方式 -->
      <div class="bg-white rounded-2xl shadow-lg p-6 mb-8">
        <h3 class="text-xl font-semibold mb-4">其他联系方式</h3>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <a href="#" class="flex items-center p-3 border border-gray-200 rounded-lg hover:border-whatsapp-primary hover:bg-whatsapp-primary/5 transition-all duration-300">
            <div class="w-10 h-10 rounded-full bg-blue-100 flex items-center justify-center text-blue-600">
              <i class="fa fa-phone"></i>
            </div>
            <div class="ml-3">
              <p class="text-sm text-neutral-500">电话咨询</p>
              <p class="font-medium">400-123-4567</p>
            </div>
          </a>
          
          <a href="#" class="flex items-center p-3 border border-gray-200 rounded-lg hover:border-whatsapp-primary hover:bg-whatsapp-primary/5 transition-all duration-300">
            <div class="w-10 h-10 rounded-full bg-purple-100 flex items-center justify-center text-purple-600">
              <i class="fa fa-envelope"></i>
            </div>
            <div class="ml-3">
              <p class="text-sm text-neutral-500">电子邮件</p>
              <p class="font-medium">support@example.com</p>
            </div>
          </a>
          
          <a href="#" class="flex items-center p-3 border border-gray-200 rounded-lg hover:border-whatsapp-primary hover:bg-whatsapp-primary/5 transition-all duration-300">
            <div class="w-10 h-10 rounded-full bg-orange-100 flex items-center justify-center text-orange-600">
              <i class="fa fa-comments"></i>
            </div>
            <div class="ml-3">
              <p class="text-sm text-neutral-500">在线聊天</p>
              <p class="font-medium">立即咨询</p>
            </div>
          </a>
        </div>
      </div>
      
      <!-- 常见问题 -->
      <div class="bg-white rounded-2xl shadow-lg p-6">
        <h3 class="text-xl font-semibold mb-4">常见问题</h3>
        <div class="space-y-4">
          <div class="border-b border-gray-100 pb-4">
            <button class="flex justify-between items-center w-full text-left font-medium">
              <span>为什么需要分配客服？</span>
              <i class="fa fa-chevron-down text-neutral-400"></i>
            </button>
            <div class="mt-2 text-sm text-neutral-600">
              我们根据您的问题类型、语言偏好和客服人员的专业领域进行智能匹配，以确保您获得最专业的帮助。
            </div>
          </div>
          
          <div class="border-b border-gray-100 pb-4">
            <button class="flex justify-between items-center w-full text-left font-medium">
              <span>我可以选择特定的客服人员吗？</span>
              <i class="fa fa-chevron-down text-neutral-400"></i>
            </button>
            <div class="mt-2 text-sm text-neutral-600 hidden">
              是的，您可以在分配后点击"更换客服"按钮选择其他可用的客服人员，或在下次访问时重新随机分配。
            </div>
          </div>
          
          <div class="border-b border-gray-100 pb-4">
            <button class="flex justify-between items-center w-full text-left font-medium">
              <span>客服的工作时间是什么？</span>
              <i class="fa fa-chevron-down text-neutral-400"></i>
            </button>
            <div class="mt-2 text-sm text-neutral-600 hidden">
              我们的客服团队工作时间为周一至周日 9:00-21:00，国家法定节假日除外。非工作时间您可以留言，我们将尽快回复。
            </div>
          </div>
          
          <div>
            <button class="flex justify-between items-center w-full text-left font-medium">
              <span>如何查看历史聊天记录？</span>
              <i class="fa fa-chevron-down text-neutral-400"></i>
            </button>
            <div class="mt-2 text-sm text-neutral-600 hidden">
              您可以在 WhatsApp 聊天界面中查看与客服的历史对话。我们不会存储您的聊天内容，确保您的信息安全。
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>

  <!-- 页脚 -->
  <footer class="bg-neutral-800 text-white py-8">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
        <div>
          <h3 class="text-lg font-semibold mb-4">客服分流系统</h3>
          <p class="text-neutral-400 text-sm">为您提供高效、专业的客户服务体验</p>
          <div class="mt-4 flex space-x-4">
            <a href="#" class="text-neutral-400 hover:text-white transition-colors">
              <i class="fa-brands fa-facebook"></i>
            </a>
            <a href="#" class="text-neutral-400 hover:text-white transition-colors">
              <i class="fa-brands fa-twitter"></i>
            </a>
            <a href="#" class="text-neutral-400 hover:text-white transition-colors">
              <i class="fa-brands fa-instagram"></i>
            </a>
            <a href="#" class="text-neutral-400 hover:text-white transition-colors">
              <i class="fa-brands fa-linkedin"></i>
            </a>
          </div>
        </div>
        
        <div>
          <h3 class="text-lg font-semibold mb-4">快速链接</h3>
          <ul class="space-y-2 text-sm">
            <li><a href="#" class="text-neutral-400 hover:text-white transition-colors">首页</a></li>
            <li><a href="#" class="text-neutral-400 hover:text-white transition-colors">关于我们</a></li>
            <li><a href="#" class="text-neutral-400 hover:text-white transition-colors">服务条款</a></li>
            <li><a href="#" class="text-neutral-400 hover:text-white transition-colors">隐私政策</a></li>
          </ul>
        </div>
        
        <div>
          <h3 class="text-lg font-semibold mb-4">联系我们</h3>
          <ul class="space-y-2 text-sm">
            <li class="flex items-start">
              <i class="fa fa-map-marker text-neutral-400 mt-1 mr-2"></i>
              <span class="text-neutral-400">北京市朝阳区建国路88号</span>
            </li>
            <li class="flex items-start">
              <i class="fa fa-phone text-neutral-400 mt-1 mr-2"></i>
              <span class="text-neutral-400">400-123-4567</span>
            </li>
            <li class="flex items-start">
              <i class="fa fa-envelope text-neutral-400 mt-1 mr-2"></i>
              <span class="text-neutral-400">support@example.com</span>
            </li>
          </ul>
        </div>
        
        <div>
          <h3 class="text-lg font-semibold mb-4">下载我们的应用</h3>
          <p class="text-neutral-400 text-sm mb-3">随时随地获取支持</p>
          <div class="space-y-2">
            <a href="#" class="flex items-center bg-neutral-700 hover:bg-neutral-600 transition-colors p-2 rounded">
              <i class="fa-brands fa-apple text-xl mr-2"></i>
              <div>
                <div class="text-xs">下载</div>
                <div class="font-medium">App Store</div>
              </div>
            </a>
            <a href="#" class="flex items-center bg-neutral-700 hover:bg-neutral-600 transition-colors p-2 rounded">
              <i class="fa-brands fa-google-play text-xl mr-2"></i>
              <div>
                <div class="text-xs">下载</div>
                <div class="font-medium">Google Play</div>
              </div>
            </a>
          </div>
        </div>
      </div>
      
      <div class="border-t border-neutral-700 mt-8 pt-6 text-center text-neutral-500 text-sm">
        <p>&copy; 2025 客服分流系统. 保留所有权利.</p>
      </div>
    </div>
  </footer>

  <!-- JavaScript -->
  <script>
    // 客服人员数据
    const agents = [
      { 
        name: "张明", 
        title: "高级客户顾问", 
        avatar: "https://picsum.photos/id/1005/200/200",
        whatsapp: "https://wa.me/447565073441",
        responseTime: "平均25秒",
        satisfaction: "98%"
      },
      { 
        name: "李婷", 
        title: "技术支持专家", 
        avatar: "https://picsum.photos/id/1006/200/200",
        whatsapp: "https://wa.me/447541099927",
        responseTime: "平均35秒",
        satisfaction: "99%"
      },
      { 
        name: "王强", 
        title: "销售顾问", 
        avatar: "https://picsum.photos/id/1012/200/200",
        whatsapp: "https://wa.me/447563733902",
        responseTime: "平均30秒",
        satisfaction: "97%"
      }
    ];

    const LOCAL_KEY = "waAssignedIndex";

    // 获取分配的客服索引
    function getAssignedIndex() {
      let saved = localStorage.getItem(LOCAL_KEY);
      if (saved !== null) {
        return parseInt(saved, 10);
      }

      const params = new URLSearchParams(window.location.search);
      const testIndex = parseInt(params.get("test"), 10);
      if (!isNaN(testIndex) && testIndex >= 0 && testIndex < agents.length) {
        localStorage.setItem(LOCAL_KEY, testIndex);
        return testIndex;
      }

      const randomIndex = Math.floor(Math.random() * agents.length);
      localStorage.setItem(LOCAL_KEY, randomIndex);
      return randomIndex;
    }

    // 更新客服信息显示
    function updateAgentDisplay(index) {
      const agent = agents[index];
      document.getElementById('agentName').textContent = agent.name;
      document.getElementById('agentTitle').textContent = agent.title;
      document.getElementById('whatsappBtn').href = agent.whatsapp;
      
      // 更新头像
      const avatarElement = document.getElementById('agentAvatar');
      avatarElement.innerHTML = `<img src="${agent.avatar}" alt="${agent.name}" class="w-full h-full rounded-full object-cover">`;
      
      // 更新匹配进度条动画
      const matchProgress = document.getElementById('matchProgress');
      matchProgress.style.width = '0%';
      setTimeout(() => {
        matchProgress.style.width = '96%';
        matchProgress.style.transition = 'width 1.5s ease-in-out';
      }, 100);
      
      // 更新响应时间和满意度
      document.querySelectorAll('.grid-cols-2 .bg-green-50 p.text-lg')[0].textContent = agent.responseTime;
      document.querySelectorAll('.grid-cols-2 .bg-blue-50 p.text-lg')[0].textContent = agent.satisfaction;
    }

    // 倒计时和跳转
    function startCountdown() {
      let countdown = 3;
      const countdownEl = document.getElementById('countdown');
      countdownEl.textContent = countdown;
      
      const timer = setInterval(() => {
        countdown--;
        countdownEl.textContent = countdown;
        
        if (countdown <= 0) {
          clearInterval(timer);
          redirectToWhatsApp();
        }
      }, 1000);
      
      // 立即联系按钮
      document.getElementById('whatsappBtn').addEventListener('click', () => {
        clearInterval(timer);
        redirectToWhatsApp();
      });
      
      // 更换客服按钮
      document.getElementById('changeAgentBtn').addEventListener('click', () => {
        clearInterval(timer);
        // 移除已分配的客服，下次将随机选择新的
        localStorage.removeItem(LOCAL_KEY);
        // 刷新页面
        location.reload();
      });
    }

    // 跳转到WhatsApp
    function redirectToWhatsApp() {
      const index = getAssignedIndex();
      const agent = agents[index];
      window.location.href = agent.whatsapp;
    }

    // 常见问题折叠功能
    function setupFAQ() {
      const faqButtons = document.querySelectorAll('.space-y-4 button');
      faqButtons.forEach(button => {
        button.addEventListener('click', () => {
          const content = button.nextElementSibling;
          const icon = button.querySelector('i');
          
          if (content.classList.contains('hidden')) {
            content.classList.remove('hidden');
            icon.classList.remove('fa-chevron-down');
            icon.classList.add('fa-chevron-up');
          } else {
            content.classList.add('hidden');
            icon.classList.remove('fa-chevron-up');
            icon.classList.add('fa-chevron-down');
          }
        });
      });
    }

    // 页面加载完成后执行
    window.onload = () => {
      const index = getAssignedIndex();
      updateAgentDisplay(index);
      startCountdown();
      setupFAQ();
      
      // 添加滚动监听，使导航栏在滚动时变化
      window.addEventListener('scroll', () => {
        const header = document.querySelector('header');
        if (window.scrollY > 10) {
          header.classList.add('shadow-md');
        } else {
          header.classList.remove('shadow-md');
        }
      });
    };
  </script>
</body>
</html>
