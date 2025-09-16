import React, { useState } from 'react';

const App = () => {
  const [activePage, setActivePage] = useState('home');

  const pages = [
    { id: 'home', name: '首頁', icon: '🏠' },
    { id: 'server', name: '伺服器', icon: '🎮' },
    { id: 'rules', name: '規則', icon: '📜' },
    { id: 'store', name: '商城', icon: '💰' },
    { id: 'community', name: '社群', icon: '👥' },
    { id: 'contact', name: '聯絡', icon: '📞' }
  ];

  const serverStats = {
    players: 147,
    uptime: '99.9%',
    version: '1.20.1',
    ping: '23ms'
  };

  const storeItems = [
    { name: 'VIP權限', price: '¥99/月', description: '獨特標籤、自定義前綴、專屬坐騎', icon: '👑' },
    { name: '資源包', price: '¥49', description: '高解析度材質包 + 專屬特效', icon: '🎨' },
    { name: '建築工具', price: '¥199', description: '即時建築套件 + 自動生成器', icon: '🏗️' },
    { name: '寵物系統', price: '¥129', description: '稀有寵物 + 設定功能', icon: '🐾' }
  ];

  const communityPosts = [
    { title: '龍域核心冬季活動預告', author: '管理員小龍', date: '2023-12-15', image: 'https://placehold.co/400x200/2c3e50/ffffff?text=冬季活動' },
    { title: '玩家建造競賽結果公布', author: '社區團隊', date: '2023-12-10', image: 'https://placehold.co/400x200/3498db/ffffff?text=建造競賽' },
    { title: '新地圖「龍之遺跡」開放', author: '開發組', date: '2023-12-05', image: 'https://placehold.co/400x200/e74c3c/ffffff?text=龍之遺跡' }
  ];

  const renderHomePage = () => (
    <div className="relative h-full w-full overflow-hidden">
      {/* Animated background */}
      <div className="absolute inset-0 bg-gradient-to-br from-gray-900 via-purple-900 to-black">
        <div className="absolute inset-0 opacity-10">
          {[...Array(50)].map((_, i) => (
            <div
              key={i}
              className="absolute w-1 h-1 bg-blue-400 rounded-full animate-pulse"
              style={{
                left: `${Math.random() * 100}%`,
                top: `${Math.random() * 100}%`,
                animationDelay: `${Math.random() * 3}s`
              }}
            />
          ))}
        </div>
        
        {/* Floating particles */}
        {[...Array(20)].map((_, i) => (
          <div
            key={i}
            className="absolute w-2 h-2 bg-cyan-400 rounded-full animate-bounce"
            style={{
              left: `${Math.random() * 100}%`,
              top: `${Math.random() * 100}%`,
              animationDuration: `${3 + Math.random() * 4}s`,
              animationDelay: `${Math.random() * 2}s`
            }}
          />
        ))}
      </div>

      {/* Main content */}
      <div className="relative z-10 flex flex-col items-center justify-center h-full text-center px-8">
        <div className="mb-8">
          <h1 className="text-6xl md:text-8xl font-bold mb-4 bg-gradient-to-r from-blue-400 via-purple-500 to-pink-500 bg-clip-text text-transparent animate-pulse">
            龍域核心
          </h1>
          <p className="text-xl md:text-2xl text-gray-300 mb-8 font-light">
            挑戰極限，締造傳奇
          </p>
          
          <div className="flex flex-wrap justify-center gap-6 mb-12">
            <div className="bg-black/30 backdrop-blur-sm border border-blue-500/30 rounded-lg p-6 min-w-48">
              <div className="text-3xl font-bold text-blue-400">{serverStats.players}</div>
              <div className="text-gray-300">在線玩家</div>
            </div>
            <div className="bg-black/30 backdrop-blur-sm border border-green-500/30 rounded-lg p-6 min-w-48">
              <div className="text-3xl font-bold text-green-400">{serverStats.uptime}</div>
              <div className="text-gray-300">穩定性</div>
            </div>
            <div className="bg-black/30 backdrop-blur-sm border border-purple-500/30 rounded-lg p-6 min-w-48">
              <div className="text-3xl font-bold text-purple-400">{serverStats.ping}</div>
              <div className="text-gray-300">延遲</div>
            </div>
          </div>
        </div>

        <button 
          onClick={() => setActivePage('server')}
          className="px-12 py-4 bg-gradient-to-r from-blue-600 to-purple-600 text-white font-bold text-xl rounded-full shadow-2xl hover:from-blue-700 hover:to-purple-700 transform hover:scale-105 transition-all duration-300 border border-blue-500/50"
        >
          進入伺服器
        </button>
        
        <div className="mt-16 text-gray-400 text-sm">
          <p>龍域核心 - 經驗豐富的Minecraft伺服器，已運行超過1000天</p>
        </div>
      </div>
    </div>
  );

  const renderServerPage = () => (
    <div className="relative h-full w-full overflow-hidden bg-gradient-to-br from-gray-900 to-black">
      {/* Grid pattern background */}
      <div className="absolute inset-0 opacity-5">
        <svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
          <defs>
            <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
              <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#3b82f6" strokeWidth="1"/>
            </pattern>
          </defs>
          <rect width="100%" height="100%" fill="url(#grid)" />
        </svg>
      </div>

      {/* Floating elements */}
      <div className="absolute top-20 left-10 w-20 h-20 bg-blue-500/20 rounded-full blur-xl animate-pulse"></div>
      <div className="absolute bottom-20 right-10 w-32 h-32 bg-purple-500/20 rounded-full blur-xl animate-pulse delay-1000"></div>
      
      <div className="relative z-10 container mx-auto px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-blue-400 via-purple-500 to-pink-500 bg-clip-text text-transparent">
            伺服器資訊
          </h1>
          <p className="text-xl text-gray-300 max-w-3xl mx-auto">
            龍域核心是專為頂尖玩家打造的Minecraft伺服器，擁有獨特的插件系統與精心設計的地圖生態。
          </p>
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8 mb-16">
          <div className="bg-black/40 backdrop-blur-sm border border-blue-500/30 rounded-xl p-8 text-center hover:border-blue-400/50 transition-all duration-300 transform hover:scale-105">
            <div className="text-4xl mb-4">🌐</div>
            <h3 className="text-xl font-bold text-white mb-2">IP地址</h3>
            <p className="text-blue-300 font-mono text-lg">longyu-core.com</p>
          </div>
          
          <div className="bg-black/40 backdrop-blur-sm border border-green-500/30 rounded-xl p-8 text-center hover:border-green-400/50 transition-all duration-300 transform hover:scale-105">
            <div className="text-4xl mb-4">⚙️</div>
            <h3 className="text-xl font-bold text-white mb-2">版本</h3>
            <p className="text-green-300 font-mono text-lg">{serverStats.version}</p>
          </div>
          
          <div className="bg-black/40 backdrop-blur-sm border border-yellow-500/30 rounded-xl p-8 text-center hover:border-yellow-400/50 transition-all duration-300 transform hover:scale-105">
            <div className="text-4xl mb-4">⏱️</div>
            <h3 className="text-xl font-bold text-white mb-2">運行時間</h3>
            <p className="text-yellow-300 font-mono text-lg">1027天</p>
          </div>
          
          <div className="bg-black/40 backdrop-blur-sm border border-red-500/30 rounded-xl p-8 text-center hover:border-red-400/50 transition-all duration-300 transform hover:scale-105">
            <div className="text-4xl mb-4">⚡</div>
            <h3 className="text-xl font-bold text-white mb-2">電力供應</h3>
            <p className="text-red-300 font-mono text-lg">24/7 UPS</p>
          </div>
        </div>

        <div className="bg-black/40 backdrop-blur-sm border border-purple-500/30 rounded-xl p-8 mb-16">
          <h2 className="text-3xl font-bold text-white mb-6 text-center">特色功能</h2>
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            {[
              '自定義生物群系與地形生成',
              '獨家魔法與科技插件系統',
              'PvP競技場與生存模式雙重體驗',
              '自動化經濟系統與交易市場',
              '玩家投票決定地圖更新',
              '專業技術支持與快速響應'
            ].map((feature, index) => (
              <div key={index} className="bg-gradient-to-r from-gray-800 to-gray-900 p-6 rounded-lg border border-gray-700 hover:border-purple-500/50 transition-all duration-300">
                <div className="text-purple-400 text-2xl mb-3">✦</div>
                <p className="text-gray-300">{feature}</p>
              </div>
            ))}
          </div>
        </div>

        <div className="text-center">
          <button 
            onClick={() => setActivePage('store')}
            className="px-10 py-4 bg-gradient-to-r from-purple-600 to-pink-600 text-white font-bold text-xl rounded-full shadow-2xl hover:from-purple-700 hover:to-pink-700 transform hover:scale-105 transition-all duration-300 border border-purple-500/50"
          >
            探索商城
          </button>
        </div>
      </div>
    </div>
  );

  const renderRulesPage = () => (
    <div className="relative h-full w-full overflow-hidden bg-gradient-to-br from-gray-900 to-indigo-900">
      {/* Decorative elements */}
      <div className="absolute top-10 left-10 w-32 h-32 bg-blue-500/10 rounded-full blur-3xl animate-pulse"></div>
      <div className="absolute bottom-10 right-10 w-40 h-40 bg-purple-500/10 rounded-full blur-3xl animate-pulse delay-1000"></div>
      
      <div className="relative z-10 container mx-auto px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-blue-400 via-purple-500 to-pink-500 bg-clip-text text-transparent">
            伺服器規則
          </h1>
          <p className="text-xl text-gray-300 max-w-3xl mx-auto">
            為了維護龍域核心的公平與秩序，所有玩家必須遵守以下規則。違反者將受到相應懲罰。
          </p>
        </div>

        <div className="max-w-4xl mx-auto space-y-8">
          <div className="bg-black/40 backdrop-blur-sm border border-red-500/30 rounded-xl p-8">
            <h2 className="text-3xl font-bold text-red-400 mb-6 flex items-center">
              <span className="mr-3">⚠️</span> 核心規則
            </h2>
            <div className="space-y-4">
              {[
                '禁止使用任何作弊軟體或外掛（包括X-Ray、Fly、AutoClicker等）',
                '禁止任何形式的Griefing（破壞他人建築）',
                '禁止廣告推廣其他伺服器或商業網站',
                '禁止使用不當語言、種族歧視或人身攻擊',
                '禁止刷怪或利用漏洞獲取不當利益'
              ].map((rule, index) => (
                <div key={index} className="bg-red-900/30 p-4 rounded-lg border border-red-500/20">
                  <span className="text-red-400 font-bold mr-2">#{index + 1}</span>
                  {rule}
                </div>
              ))}
            </div>
          </div>

          <div className="bg-black/40 backdrop-blur-sm border border-yellow-500/30 rounded-xl p-8">
            <h2 className="text-3xl font-bold text-yellow-400 mb-6 flex items-center">
              <span className="mr-3">⭐</span> 建議行為
            </h2>
            <div className="space-y-4">
              {[
                '積極參與伺服器活動與競賽',
                '幫助新手玩家並分享經驗',
                '尊重其他玩家與管理人員',
                '主動報告違規行為',
                '保持友善和建設性的交流環境'
              ].map((rule, index) => (
                <div key={index} className="bg-yellow-900/30 p-4 rounded-lg border border-yellow-500/20">
                  <span className="text-yellow-400 font-bold mr-2">✓</span>
                  {rule}
                </div>
              ))}
            </div>
          </div>

          <div className="bg-black/40 backdrop-blur-sm border border-green-500/30 rounded-xl p-8">
            <h2 className="text-3xl font-bold text-green-400 mb-6 flex items-center">
              <span className="mr-3">🔒</span> 懲罰系統
            </h2>
            <div className="grid md:grid-cols-3 gap-6">
              <div className="text-center">
                <div className="text-4xl mb-3">🟠</div>
                <h3 className="text-xl font-bold text-white mb-2">警告</h3>
                <p className="text-gray-300">首次輕微違規</p>
              </div>
              <div className="text-center">
                <div className="text-4xl mb-3">🔴</div>
                <h3 className="text-xl font-bold text-white mb-2">暫時封禁</h3>
                <p className="text-gray-300">多次違規或嚴重違規</p>
              </div>
              <div className="text-center">
                <div className="text-4xl mb-3">⚫</div>
                <h3 className="text-xl font-bold text-white mb-2">永久封禁</h3>
                <p className="text-gray-300">惡意破壞、作弊、騷擾</p>
              </div>
            </div>
          </div>

          <div className="bg-black/40 backdrop-blur-sm border border-blue-500/30 rounded-xl p-8">
            <h2 className="text-3xl font-bold text-blue-400 mb-6 flex items-center">
              <span className="mr-3">📝</span> 上訴流程
            </h2>
            <p className="text-gray-300 mb-4">
              如果您認為自己被錯誤地處罰，請按照以下步驟上訴：
            </p>
            <ol className="list-decimal list-inside space-y-2 text-gray-300 ml-4">
              <li>訪問我們的官方Discord伺服器</li>
              <li>前往#appeals頻道</li>
              <li>提供您的遊戲ID、處罰時間和具體情況</li>
              <li>等待管理團隊審核（通常在24-72小時內回覆）</li>
              <li>接受最終決定並尊重管理團隊的判斷</li>
            </ol>
          </div>
        </div>
      </div>
    </div>
  );

  const renderStorePage = () => (
    <div className="relative h-full w-full overflow-hidden bg-gradient-to-br from-gray-900 to-purple-900">
      {/* Animated grid background */}
      <div className="absolute inset-0 opacity-10">
        {[...Array(100)].map((_, i) => (
          <div
            key={i}
            className="absolute w-px h-px bg-cyan-400 animate-pulse"
            style={{
              left: `${Math.random() * 100}%`,
              top: `${Math.random() * 100}%`,
              animationDelay: `${Math.random() * 2}s`
            }}
          />
        ))}
      </div>

      {/* Floating gems */}
      {[...Array(8)].map((_, i) => (
        <div
          key={i}
          className="absolute w-8 h-8 bg-gradient-to-br from-blue-400 to-purple-500 rounded-full animate-bounce"
          style={{
            left: `${10 + i * 10}%`,
            top: `${20 + (i % 3) * 20}%`,
            animationDuration: `${3 + i * 0.5}s`,
            animationDelay: `${i * 0.3}s`
          }}
        />
      ))}

      <div className="relative z-10 container mx-auto px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-yellow-400 via-orange-500 to-red-500 bg-clip-text text-transparent">
            商城中心
          </h1>
          <p className="text-xl text-gray-300 max-w-3xl mx-auto">
            支持龍域核心發展，獲得獨家特權與裝備。所有收益都用於伺服器維護與升級。
          </p>
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8 mb-16">
          {storeItems.map((item, index) => (
            <div 
              key={index}
              className="bg-gradient-to-br from-gray-800 to-gray-900 backdrop-blur-sm border border-purple-500/30 rounded-xl p-8 hover:border-purple-400/50 transition-all duration-300 transform hover:scale-105 cursor-pointer group"
            >
              <div className="text-5xl mb-4">{item.icon}</div>
              <h3 className="text-2xl font-bold text-white mb-2">{item.name}</h3>
              <div className="text-2xl font-bold text-yellow-400 mb-4">{item.price}</div>
              <p className="text-gray-300 mb-6">{item.description}</p>
              <button className="w-full bg-gradient-to-r from-purple-600 to-pink-600 text-white font-bold py-3 rounded-lg hover:from-purple-700 hover:to-pink-700 transition-all duration-300 transform hover:scale-105">
                購買
              </button>
            </div>
          ))}
        </div>

        <div className="bg-black/40 backdrop-blur-sm border border-blue-500/30 rounded-xl p-8 mb-16">
          <h2 className="text-3xl font-bold text-white mb-6 text-center">尊貴會員權益</h2>
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            {[
              '獨特VIP標籤與前綴',
              '專屬坐騎與寵物',
              '優先支援服務',
              '每月免費資源包',
              '私人領地擴展',
              '伺服器活動優先權',
              '自定義名稱顏色',
              '特殊技能與道具',
              '個人統計面板'
            ].map((benefit, index) => (
              <div key={index} className="flex items-center text-gray-300">
                <div className="w-2 h-2 bg-green-400 rounded-full mr-3 animate-pulse"></div>
                {benefit}
              </div>
            ))}
          </div>
        </div>

        <div className="text-center">
          <button 
            onClick={() => setActivePage('community')}
            className="px-10 py-4 bg-gradient-to-r from-blue-600 to-cyan-600 text-white font-bold text-xl rounded-full shadow-2xl hover:from-blue-700 hover:to-cyan-700 transform hover:scale-105 transition-all duration-300 border border-blue-500/50"
          >
            加入社群
          </button>
        </div>
      </div>
    </div>
  );

  const renderCommunityPage = () => (
    <div className="relative h-full w-full overflow-hidden bg-gradient-to-br from-gray-900 to-blue-900">
      {/* Particle background */}
      <div className="absolute inset-0 opacity-10">
        {[...Array(80)].map((_, i) => (
          <div
            key={i}
            className="absolute w-1 h-1 bg-cyan-400 rounded-full animate-pulse"
            style={{
              left: `${Math.random() * 100}%`,
              top: `${Math.random() * 100}%`,
              animationDelay: `${Math.random() * 3}s`
            }}
          />
        ))}
      </div>

      {/* Floating circles */}
      <div className="absolute top-20 right-20 w-40 h-40 bg-blue-500/20 rounded-full blur-3xl animate-pulse"></div>
      <div className="absolute bottom-20 left-20 w-60 h-60 bg-purple-500/20 rounded-full blur-3xl animate-pulse delay-1000"></div>

      <div className="relative z-10 container mx-auto px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-cyan-400 via-blue-500 to-purple-500 bg-clip-text text-transparent">
            社群中心
          </h1>
          <p className="text-xl text-gray-300 max-w-3xl mx-auto">
            加入我們的熱情玩家社群，分享你的創造，結識志同道合的朋友！
          </p>
        </div>

        <div className="grid md:grid-cols-3 gap-8 mb-16">
          {communityPosts.map((post, index) => (
            <div 
              key={index}
              className="bg-black/40 backdrop-blur-sm border border-blue-500/30 rounded-xl overflow-hidden hover:border-blue-400/50 transition-all duration-300 transform hover:scale-105 cursor-pointer"
            >
              <img src={post.image} alt={post.title} className="w-full h-48 object-cover" />
              <div className="p-6">
                <h3 className="text-xl font-bold text-white mb-2">{post.title}</h3>
                <div className="flex items-center text-gray-400 text-sm mb-3">
                  <span className="mr-2">👤</span>
                  {post.author} • {post.date}
                </div>
                <button className="text-blue-400 hover:text-blue-300 font-medium transition-colors">
                  查看詳情 →
                </button>
              </div>
            </div>
          ))}
        </div>

        <div className="bg-black/40 backdrop-blur-sm border border-purple-500/30 rounded-xl p-8 mb-16">
          <h2 className="text-3xl font-bold text-white mb-6 text-center">社群連結</h2>
          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            {[
              { name: 'Discord', icon: '💬', color: 'bg-blue-600', link: '#discord' },
              { name: 'YouTube', icon: '▶️', color: 'bg-red-600', link: '#youtube' },
              { name: 'Twitter', icon: '🐦', color: 'bg-cyan-500', link: '#twitter' },
              { name: 'Twitch', icon: '🎬', color: 'bg-purple-600', link: '#twitch' }
            ].map((social, index) => (
              <a
                key={index}
                href={social.link}
                className={`${social.color} p-6 rounded-xl text-center text-white hover:scale-110 transition-transform duration-300`}
              >
                <div className="text-4xl mb-3">{social.icon}</div>
                <div className="font-bold">{social.name}</div>
              </a>
            ))}
          </div>
        </div>

        <div className="bg-black/40 backdrop-blur-sm border border-green-500/30 rounded-xl p-8">
          <h2 className="text-3xl font-bold text-white mb-6 text-center">線上玩家排行榜</h2>
          <div className="space-y-4">
            {[
              { rank: 1, name: '龍王陛下', level: 287, playtime: '1284小時', icon: '👑' },
              { rank: 2, name: '建築大師', level: 265, playtime: '1156小時', icon: '🏗️' },
              { rank: 3, name: '礦工之神', level: 243, playtime: '1098小時', icon: '⛏️' },
              { rank: 4, name: '紅石天才', level: 231, playtime: '987小時', icon: '⚡' },
              { rank: 5, name: '龍域新星', level: 219, playtime: '876小時', icon: '🌟' }
            ].map((player, index) => (
              <div key={index} className="flex items-center justify-between bg-gray-800/50 p-4 rounded-lg border border-gray-700">
                <div className="flex items-center">
                  <span className="text-2xl font-bold text-yellow-400 mr-4">{player.rank}</span>
                  <span className="text-3xl mr-3">{player.icon}</span>
                  <span className="text-white font-bold">{player.name}</span>
                </div>
                <div className="text-right">
                  <div className="text-gray-300">等級 {player.level}</div>
                  <div className="text-gray-400 text-sm">{player.playtime}</div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );

  const renderContactPage = () => (
    <div className="relative h-full w-full overflow-hidden bg-gradient-to-br from-gray-900 to-indigo-900">
      {/* Abstract lines background */}
      <div className="absolute inset-0 opacity-5">
        <svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
          <defs>
            <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="100%">
              <stop offset="0%" stopColor="#3b82f6" />
              <stop offset="100%" stopColor="#8b5cf6" />
            </linearGradient>
          </defs>
          <path d="M0,0 L100,100 L200,0 L300,100 L400,0 L500,100 L600,0 L700,100 L800,0 L900,100 L1000,0" fill="none" stroke="url(#gradient)" strokeWidth="1" opacity="0.3"/>
          <path d="M0,100 L100,0 L200,100 L300,0 L400,100 L500,0 L600,100 L700,0 L800,100 L900,0 L1000,100" fill="none" stroke="url(#gradient)" strokeWidth="1" opacity="0.3"/>
        </svg>
      </div>

      <div className="relative z-10 container mx-auto px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-purple-400 via-pink-500 to-red-500 bg-clip-text text-transparent">
            聯絡我們
          </h1>
          <p className="text-xl text-gray-300 max-w-3xl mx-auto">
            有任何問題？歡迎隨時聯繫我們的管理團隊。我們會盡快回覆每一位玩家。
          </p>
        </div>

        <div className="grid md:grid-cols-2 gap-16">
          <div>
            <h2 className="text-3xl font-bold text-white mb-8">聯絡資訊</h2>
            
            <div className="space-y-6 mb-8">
              <div className="flex items-start">
                <div className="text-3xl mr-4 text-blue-400">📧</div>
                <div>
                  <h3 className="text-xl font-bold text-white">電子郵件</h3>
                  <p className="text-gray-300">support@longyu-core.com</p>
                </div>
              </div>
              
              <div className="flex items-start">
                <div className="text-3xl mr-4 text-green-400">🌐</div>
                <div>
                  <h3 className="text-xl font-bold text-white">官方網站</h3>
                  <p className="text-gray-300">https://longyu-core.com</p>
                </div>
              </div>
              
              <div className="flex items-start">
                <div className="text-3xl mr-4 text-purple-400">📱</div>
                <div>
                  <h3 className="text-xl font-bold text-white">Discord</h3>
                  <p className="text-gray-300">discord.gg/longyucore</p>
                </div>
              </div>
              
              <div className="flex items-start">
                <div className="text-3xl mr-4 text-yellow-400">⏰</div>
                <div>
                  <h3 className="text-xl font-bold text-white">支援時間</h3>
                  <p className="text-gray-300">24/7 全天候服務</p>
                </div>
              </div>
            </div>

            <div className="bg-black/40 backdrop-blur-sm border border-purple-500/30 rounded-xl p-6">
              <h3 className="text-xl font-bold text-white mb-4">營運團隊</h3>
              <p className="text-gray-300 mb-4">
                我們的管理團隊由資深Minecraft玩家與專業技術人員組成，致力於提供最佳遊戲體驗。
              </p>
              <div className="flex items-center text-gray-400">
                <span className="mr-2">👨‍💻</span>
                <span>總監：龍王陛下</span>
              </div>
              <div className="flex items-center text-gray-400">
                <span className="mr-2">🛠️</span>
                <span>技術主管：紅石工程師</span>
              </div>
              <div className="flex items-center text-gray-400">
                <span className="mr-2">🎨</span>
                <span>內容設計：藝術之魂</span>
              </div>
            </div>
          </div>

          <div>
            <h2 className="text-3xl font-bold text-white mb-8">傳送訊息</h2>
            
            <form className="space-y-6">
              <div>
                <label className="block text-gray-300 mb-2">姓名</label>
                <input 
                  type="text" 
                  className="w-full bg-gray-800/50 border border-gray-700 rounded-lg px-4 py-3 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500"
                  placeholder="輸入您的遊戲名稱"
                />
              </div>
              
              <div>
                <label className="block text-gray-300 mb-2">電子郵件</label>
                <input 
                  type="email" 
                  className="w-full bg-gray-800/50 border border-gray-700 rounded-lg px-4 py-3 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500"
                  placeholder="example@email.com"
                />
              </div>
              
              <div>
                <label className="block text-gray-300 mb-2">主題</label>
                <select className="w-full bg-gray-800/50 border border-gray-700 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-blue-500">
                  <option value="">選擇主題</option>
                  <option value="bug">遊戲漏洞報告</option>
                  <option value="support">技術支援</option>
                  <option value="suggestion">建議與反饋</option>
                  <option value="other">其他</option>
                </select>
              </div>
              
              <div>
                <label className="block text-gray-300 mb-2">訊息內容</label>
                <textarea 
                  rows="6" 
                  className="w-full bg-gray-800/50 border border-gray-700 rounded-lg px-4 py-3 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500 resize-none"
                  placeholder="請詳細描述您的問題或建議..."
                ></textarea>
              </div>
              
              <button 
                type="submit"
                className="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white font-bold py-4 rounded-lg hover:from-blue-700 hover:to-purple-700 transform hover:scale-105 transition-all duration-300 shadow-lg"
              >
                發送訊息
              </button>
            </form>

            <div className="mt-12 text-center">
              <div className="inline-flex items-center bg-black/40 backdrop-blur-sm border border-blue-500/30 rounded-full px-6 py-3">
                <div className="w-3 h-3 bg-green-400 rounded-full animate-pulse mr-3"></div>
                <span className="text-gray-300">目前狀態：線上</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  );

  const renderContent = () => {
    switch(activePage) {
      case 'server': return renderServerPage();
      case 'rules': return renderRulesPage();
      case 'store': return renderStorePage();
      case 'community': return renderCommunityPage();
      case 'contact': return renderContactPage();
      default: return renderHomePage();
    }
  };

  return (
    <div className="h-screen w-screen bg-black text-white overflow-hidden">
      {/* Navigation */}
      <nav className="fixed top-0 left-0 right-0 z-50 bg-black/20 backdrop-blur-md border-b border-white/10">
        <div className="container mx-auto px-8 flex items-center justify-between h-16">
          <div className="flex items-center">
            <div className="text-2xl font-bold bg-gradient-to-r from-blue-400 via-purple-500 to-pink-500 bg-clip-text text-transparent">
              龍域核心
            </div>
          </div>
          
          <div className="hidden md:flex space-x-1">
            {pages.map((page) => (
              <button
                key={page.id}
                onClick={() => setActivePage(page.id)}
                className={`px-6 py-3 rounded-full font-medium transition-all duration-300 relative overflow-hidden ${
                  activePage === page.id 
                    ? 'bg-gradient-to-r from-blue-500 to-purple-500 text-white shadow-lg' 
                    : 'text-gray-300 hover:text-white hover:bg-white/10'
                }`}
              >
                <span className="relative z-10 flex items-center">
                  <span className="mr-2">{page.icon}</span>
                  {page.name}
                </span>
                {activePage === page.id && (
                  <div className="absolute inset-0 bg-gradient-to-r from-blue-500 to-purple-500 opacity-20 rounded-full animate-pulse"></div>
                )}
              </button>
            ))}
          </div>

          <div className="md:hidden">
            <button className="text-gray-300 hover:text-white">
              ☰
            </button>
          </div>
        </div>
      </nav>

      {/* Main Content */}
      <main className="h-screen pt-16">
        {renderContent()}
      </main>

      {/* Mobile Navigation */}
      <div className="md:hidden fixed bottom-0 left-0 right-0 bg-black/20 backdrop-blur-md border-t border-white/10 z-50">
        <div className="flex justify-around py-2">
          {pages.map((page) => (
            <button
              key={page.id}
              onClick={() => setActivePage(page.id)}
              className={`p-3 rounded-lg transition-all duration-300 ${
                activePage === page.id 
                  ? 'bg-gradient-to-r from-blue-500 to-purple-500 text-white' 
                  : 'text-gray-400'
              }`}
            >
              <div className="text-2xl mb-1">{page.icon}</div>
              <div className="text-xs">{page.name}</div>
            </button>
          ))}
        </div>
      </div>
    </div>
  );
};

export default App;
