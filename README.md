<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tabungan ZalStecu🫧</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        
        * {
            font-family: 'Inter', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #334155 100%);
            min-height: 100vh;
        }
        
        .glass-effect {
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(59, 130, 246, 0.2);
        }
        
        .luxury-card {
            background: linear-gradient(145deg, rgba(30, 41, 59, 0.9), rgba(51, 65, 85, 0.9));
            backdrop-filter: blur(20px);
            border: 1px solid rgba(59, 130, 246, 0.3);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }
        
        .progress-ring {
            transform: rotate(-90deg);
        }
        
        .progress-ring-circle {
            transition: stroke-dashoffset 0.35s ease-in-out;
        }
        
        .floating-animation {
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .notification {
            animation: slideIn 0.5s ease-out;
        }
        
        @keyframes slideIn {
            from { transform: translateX(100%); }
            to { transform: translateX(0); }
        }
        
        .btn-luxury {
            background: linear-gradient(135deg, #3b82f6, #1d4ed8);
            transition: all 0.3s ease;
            box-shadow: 0 10px 25px rgba(59, 130, 246, 0.3);
        }
        
        .btn-luxury:hover {
            background: linear-gradient(135deg, #2563eb, #1e40af);
            transform: translateY(-2px);
            box-shadow: 0 15px 35px rgba(59, 130, 246, 0.4);
        }
        
        .input-luxury {
            background: rgba(15, 23, 42, 0.6);
            border: 2px solid rgba(59, 130, 246, 0.3);
            transition: all 0.3s ease;
        }
        
        .input-luxury:focus {
            border-color: #3b82f6;
            box-shadow: 0 0 20px rgba(59, 130, 246, 0.2);
        }
        
        .sparkle {
            position: absolute;
            animation: sparkle 2s linear infinite;
        }
        
        @keyframes sparkle {
            0%, 100% { opacity: 0; transform: scale(0); }
            50% { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body class="min-h-screen text-white">
    <div class="fixed inset-0 overflow-hidden pointer-events-none">
        <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-blue-600 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-pulse"></div>
        <div class="absolute top-3/4 right-1/4 w-96 h-96 bg-indigo-600 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-pulse"></div>
    </div>
    <header class="relative z-10 pt-8 pb-6">
        <div class="container mx-auto px-6">
            <div class="text-center">
                <h1 class="text-5xl font-bold bg-gradient-to-r from-blue-400 to-white bg-clip-text text-transparent mb-2">
                    <i class="fas fa-piggy-bank mr-4"></i>ZalOfficial
                </h1>
            </div>
        </div>
    </header>
    <main class="relative z-10 container mx-auto px-6 pb-12">
        <div class="max-w-6xl mx-auto">
            <div class="grid lg:grid-cols-2 gap-8">
                <div class="luxury-card rounded-3xl p-8 floating-animation">
                    <div class="flex items-center mb-6">
                        <div class="w-12 h-12 bg-gradient-to-r from-blue-500 to-blue-600 rounded-full flex items-center justify-center mr-4">
                            <i class="fas fa-wallet text-white text-xl"></i>
                        </div>
                        <h2 class="text-2xl font-bold">Kelola Tabungan</h2>
                    </div>
                    
                    <!-- Target Setting -->
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-blue-200 mb-2">Target Tabungan (Rp)</label>
                        <input type="number" id="targetInput" class="input-luxury w-full px-4 py-3 rounded-xl text-white placeholder-gray-400 focus:outline-none" placeholder="Masukkan target tabungan">
                        <button id="setTargetBtn" class="btn-luxury w-full mt-3 px-6 py-3 rounded-xl text-white font-semibold focus:outline-none">
                            <i class="fas fa-target mr-2"></i>Set Target
                        </button>
                    </div>
                    
                    <!-- Add Money -->
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-blue-200 mb-2">Tambah Uang (Rp)</label>
                        <input type="number" id="amountInput" class="input-luxury w-full px-4 py-3 rounded-xl text-white placeholder-gray-400 focus:outline-none" placeholder="Masukkan jumlah uang">
                        <button id="addMoneyBtn" class="btn-luxury w-full mt-3 px-6 py-3 rounded-xl text-white font-semibold focus:outline-none">
                            <i class="fas fa-plus-circle mr-2"></i>Tambah Uang
                        </button>
                    </div>
                    
                    <!-- Withdraw Money -->
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-blue-200 mb-2">Tarik Uang (Rp)</label>
                        <input type="number" id="withdrawInput" class="input-luxury w-full px-4 py-3 rounded-xl text-white placeholder-gray-400 focus:outline-none" placeholder="Masukkan jumlah penarikan">
                        <button id="withdrawBtn" class="w-full mt-3 px-6 py-3 rounded-xl text-white font-semibold focus:outline-none bg-gradient-to-r from-red-500 to-red-600 hover:from-red-600 hover:to-red-700 transition-all duration-300">
                            <i class="fas fa-minus-circle mr-2"></i>Tarik Uang
                        </button>
                    </div>
                    
                    <!-- Reset Button -->
                    <button id="resetBtn" class="w-full px-6 py-3 rounded-xl text-white font-semibold focus:outline-none bg-gradient-to-r from-gray-600 to-gray-700 hover:from-gray-700 hover:to-gray-800 transition-all duration-300">
                        <i class="fas fa-refresh mr-2"></i>Reset Tabungan
                    </button>
                </div>
                
                <!-- Progress Display Section -->
                <div class="luxury-card rounded-3xl p-8">
                    <div class="text-center">
                        <!-- Circular Progress -->
                        <div class="relative mb-8">
                            <svg class="progress-ring w-48 h-48 mx-auto" width="192" height="192">
                                <defs>
                                    <linearGradient id="progressGradient" x1="0%" y1="0%" x2="100%" y2="0%">
                                        <stop offset="0%" style="stop-color:#3b82f6"/>
                                        <stop offset="100%" style="stop-color:#1d4ed8"/>
                                    </linearGradient>
                                </defs>
                                <circle class="progress-ring-circle bg-stroke" stroke="rgba(59, 130, 246, 0.2)" stroke-width="8" fill="transparent" r="88" cx="96" cy="96"/>
                                <circle id="progressCircle" class="progress-ring-circle" stroke="url(#progressGradient)" stroke-width="8" fill="transparent" r="88" cx="96" cy="96" stroke-linecap="round"/>
                            </svg>
                            <div class="absolute inset-0 flex items-center justify-center flex-col">
                                <span id="progressPercentage" class="text-4xl font-bold text-blue-400">0%</span>
                                <span class="text-sm text-gray-300">Tercapai</span>
                            </div>
                            <!-- Sparkle effects -->
                            <div class="sparkle top-4 left-4 text-yellow-400 text-xl"><i class="fas fa-star"></i></div>
                            <div class="sparkle top-4 right-4 text-yellow-400 text-xl"><i class="fas fa-star"></i></div>
                            <div class="sparkle bottom-4 left-4 text-yellow-400 text-xl"><i class="fas fa-star"></i></div>
                            <div class="sparkle bottom-4 right-4 text-yellow-400 text-xl"><i class="fas fa-star"></i></div>
                        </div>
                        
                        <!-- Stats Display -->
                        <div class="grid grid-cols-1 gap-6">
                            <div class="glass-effect rounded-2xl p-6">
                                <div class="flex items-center justify-between">
                                    <div>
                                        <p class="text-sm text-blue-200">Tabungan Saat Ini</p>
                                        <p id="currentSavings" class="text-3xl font-bold text-white">Rp 0</p>
                                    </div>
                                    <div class="w-12 h-12 bg-gradient-to-r from-green-500 to-green-600 rounded-full flex items-center justify-center">
                                        <i class="fas fa-coins text-white"></i>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="glass-effect rounded-2xl p-6">
                                <div class="flex items-center justify-between">
                                    <div>
                                        <p class="text-sm text-blue-200">Target Tabungan</p>
                                        <p id="targetSavings" class="text-3xl font-bold text-white">Rp 0</p>
                                    </div>
                                    <div class="w-12 h-12 bg-gradient-to-r from-blue-500 to-blue-600 rounded-full flex items-center justify-center">
                                        <i class="fas fa-bullseye text-white"></i>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="glass-effect rounded-2xl p-6">
                                <div class="flex items-center justify-between">
                                    <div>
                                        <p class="text-sm text-blue-200">Sisa Target</p>
                                        <p id="remainingAmount" class="text-3xl font-bold text-white">Rp 0</p>
                                    </div>
                                    <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-purple-600 rounded-full flex items-center justify-center">
                                        <i class="fas fa-chart-line text-white"></i>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Transaction History -->
            <div class="luxury-card rounded-3xl p-8 mt-8">
                <div class="flex items-center justify-between mb-6">
                    <h3 class="text-2xl font-bold flex items-center">
                        <i class="fas fa-history mr-3 text-blue-400"></i>
                        Riwayat Transaksi
                    </h3>
                    <button id="clearHistoryBtn" class="px-4 py-2 bg-red-600 hover:bg-red-700 rounded-lg text-sm transition-colors">
                        <i class="fas fa-trash mr-2"></i>Hapus Riwayat
                    </button>
                </div>
                <div id="transactionHistory" class="space-y-3 max-h-96 overflow-y-auto">
                    <!-- Transaction items will be added here -->
                </div>
            </div>
        </div>
    </main>
    
    <!-- Notification Container -->
    <div id="notificationContainer" class="fixed top-4 right-4 z-50 space-y-2"></div>
    
    <!-- Success Modal -->
    <div id="successModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="luxury-card rounded-3xl p-8 max-w-md mx-4 text-center">
            <div class="mb-6">
                <div class="w-20 h-20 bg-gradient-to-r from-green-400 to-green-600 rounded-full flex items-center justify-center mx-auto mb-4">
                    <i class="fas fa-trophy text-white text-3xl"></i>
                </div>
                <h3 class="text-2xl font-bold text-white mb-2">Selamat!</h3>
                <p class="text-gray-300">Target tabungan Anda telah tercapai!</p>
            </div>
            <button id="closeModal" class="btn-luxury px-8 py-3 rounded-xl text-white font-semibold focus:outline-none">
                <i class="fas fa-check mr-2"></i>Tutup
            </button>
        </div>
    </div>

    <script>
        class SavingsTracker {
            constructor() {
                this.currentAmount = parseFloat(localStorage.getItem('currentAmount')) || 0;
                this.targetAmount = parseFloat(localStorage.getItem('targetAmount')) || 0;
                this.transactions = JSON.parse(localStorage.getItem('transactions')) || [];
                this.targetReached = localStorage.getItem('targetReached') === 'true';
                
                this.initializeElements();
                this.attachEventListeners();
                this.updateDisplay();
                this.renderTransactionHistory();
            }
            
            initializeElements() {
                this.elements = {
                    targetInput: document.getElementById('targetInput'),
                    amountInput: document.getElementById('amountInput'),
                    withdrawInput: document.getElementById('withdrawInput'),
                    setTargetBtn: document.getElementById('setTargetBtn'),
                    addMoneyBtn: document.getElementById('addMoneyBtn'),
                    withdrawBtn: document.getElementById('withdrawBtn'),
                    resetBtn: document.getElementById('resetBtn'),
                    clearHistoryBtn: document.getElementById('clearHistoryBtn'),
                    currentSavings: document.getElementById('currentSavings'),
                    targetSavings: document.getElementById('targetSavings'),
                    remainingAmount: document.getElementById('remainingAmount'),
                    progressPercentage: document.getElementById('progressPercentage'),
                    progressCircle: document.getElementById('progressCircle'),
                    transactionHistory: document.getElementById('transactionHistory'),
                    successModal: document.getElementById('successModal'),
                    closeModal: document.getElementById('closeModal'),
                    notificationContainer: document.getElementById('notificationContainer')
                };
            }
            
            attachEventListeners() {
                this.elements.setTargetBtn.addEventListener('click', () => this.setTarget());
                this.elements.addMoneyBtn.addEventListener('click', () => this.addMoney());
                this.elements.withdrawBtn.addEventListener('click', () => this.withdrawMoney());
                this.elements.resetBtn.addEventListener('click', () => this.resetSavings());
                this.elements.clearHistoryBtn.addEventListener('click', () => this.clearHistory());
                this.elements.closeModal.addEventListener('click', () => this.closeSuccessModal());
                
                // Enter key support
                this.elements.targetInput.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter') this.setTarget();
                });
                this.elements.amountInput.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter') this.addMoney();
                });
                this.elements.withdrawInput.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter') this.withdrawMoney();
                });
            }
            
            setTarget() {
                const target = parseFloat(this.elements.targetInput.value);
                if (target && target > 0) {
                    this.targetAmount = target;
                    this.targetReached = false;
                    this.saveToLocalStorage();
                    this.updateDisplay();
                    this.elements.targetInput.value = '';
                    this.showNotification('Target berhasil ditetapkan!', 'success');
                    this.addTransaction('set_target', target, `Target ditetapkan: ${this.formatCurrency(target)}`);
                } else {
                    this.showNotification('Masukkan target yang valid!', 'error');
                }
            }
            
            addMoney() {
                const amount = parseFloat(this.elements.amountInput.value);
                if (amount && amount > 0) {
                    const previousAmount = this.currentAmount;
                    this.currentAmount += amount;
                    this.saveToLocalStorage();
                    this.updateDisplay();
                    this.elements.amountInput.value = '';
                    this.showNotification(`Berhasil menambah ${this.formatCurrency(amount)}!`, 'success');
                    this.addTransaction('add', amount, `Menabung ${this.formatCurrency(amount)}`);
                    
                    // Check if target reached
                    if (this.targetAmount > 0 && previousAmount < this.targetAmount && this.currentAmount >= this.targetAmount && !this.targetReached) {
                        this.targetReached = true;
                        this.saveToLocalStorage();
                        setTimeout(() => this.showSuccessModal(), 500);
                    }
                } else {
                    this.showNotification('Masukkan jumlah yang valid!', 'error');
                }
            }
            
            withdrawMoney() {
                const amount = parseFloat(this.elements.withdrawInput.value);
                if (amount && amount > 0) {
                    if (amount <= this.currentAmount) {
                        this.currentAmount -= amount;
                        this.saveToLocalStorage();
                        this.updateDisplay();
                        this.elements.withdrawInput.value = '';
                        this.showNotification(`Berhasil menarik ${this.formatCurrency(amount)}!`, 'info');
                        this.addTransaction('withdraw', amount, `Menarik ${this.formatCurrency(amount)}`);
                    } else {
                        this.showNotification('Saldo tidak mencukupi!', 'error');
                    }
                } else {
                    this.showNotification('Masukkan jumlah yang valid!', 'error');
                }
            }
            
            resetSavings() {
                if (confirm('Apakah Anda yakin ingin mereset semua data tabungan?')) {
                    this.currentAmount = 0;
                    this.targetAmount = 0;
                    this.targetReached = false;
                    this.transactions = [];
                    this.saveToLocalStorage();
                    this.updateDisplay();
                    this.renderTransactionHistory();
                    this.showNotification('Tabungan berhasil direset!', 'info');
                }
            }
            
            clearHistory() {
                if (confirm('Apakah Anda yakin ingin menghapus riwayat transaksi?')) {
                    this.transactions = [];
                    this.saveToLocalStorage();
                    this.renderTransactionHistory();
                    this.showNotification('Riwayat transaksi berhasil dihapus!', 'info');
                }
            }
            
            addTransaction(type, amount, description) {
                const transaction = {
                    id: Date.now(),
                    type: type,
                    amount: amount,
                    description: description,
                    timestamp: new Date().toLocaleString('id-ID'),
                    balance: this.currentAmount
                };
                this.transactions.unshift(transaction);
                
                // Keep only last 50 transactions
                if (this.transactions.length > 50) {
                    this.transactions = this.transactions.slice(0, 50);
                }
                
                this.saveToLocalStorage();
                this.renderTransactionHistory();
            }
            
            renderTransactionHistory() {
                if (this.transactions.length === 0) {
                    this.elements.transactionHistory.innerHTML = `
                        <div class="text-center py-8 text-gray-400">
                            <i class="fas fa-history text-4xl mb-3 opacity-50"></i>
                            <p>Belum ada transaksi</p>
                        </div>
                    `;
                    return;
                }
                
                this.elements.transactionHistory.innerHTML = this.transactions.map(transaction => {
                    const typeConfig = {
                        add: { icon: 'fas fa-plus-circle', color: 'text-green-400', bg: 'bg-green-500' },
                        withdraw: { icon: 'fas fa-minus-circle', color: 'text-red-400', bg: 'bg-red-500' },
                        set_target: { icon: 'fas fa-target', color: 'text-blue-400', bg: 'bg-blue-500' }
                    };
                    
                    const config = typeConfig[transaction.type] || typeConfig.add;
                    
                    return `
                        <div class="glass-effect rounded-xl p-4 flex items-center justify-between hover:bg-opacity-80 transition-all">
                            <div class="flex items-center">
                                <div class="w-10 h-10 ${config.bg} bg-opacity-20 rounded-full flex items-center justify-center mr-4">
                                    <i class="${config.icon} ${config.color}"></i>
                                </div>
                                <div>
                                    <p class="font-medium text-white">${transaction.description}</p>
                                    <p class="text-sm text-gray-400">${transaction.timestamp}</p>
                                </div>
                            </div>
                            <div class="text-right">
                                <p class="font-bold ${config.color}">
                                    ${transaction.type === 'withdraw' ? '-' : transaction.type === 'add' ? '+' : ''}${this.formatCurrency(transaction.amount)}
                                </p>
                                <p class="text-sm text-gray-400">Saldo: ${this.formatCurrency(transaction.balance)}</p>
                            </div>
                        </div>
                    `;
                }).join('');
            }
            
            updateDisplay() {
                this.elements.currentSavings.textContent = this.formatCurrency(this.currentAmount);
                this.elements.targetSavings.textContent = this.formatCurrency(this.targetAmount);
                
                const remaining = Math.max(0, this.targetAmount - this.currentAmount);
                this.elements.remainingAmount.textContent = this.formatCurrency(remaining);
                
                // Update progress
                const percentage = this.targetAmount > 0 ? Math.min(100, (this.currentAmount / this.targetAmount) * 100) : 0;
                this.elements.progressPercentage.textContent = `${Math.round(percentage)}%`;
                
                // Update circular progress
                const circumference = 2 * Math.PI * 88;
                const offset = circumference - (percentage / 100) * circumference;
                this.elements.progressCircle.style.strokeDasharray = circumference;
                this.elements.progressCircle.style.strokeDashoffset = offset;
            }
            
            showNotification(message, type = 'info') {
                const colors = {
                    success: 'from-green-500 to-green-600',
                    error: 'from-red-500 to-red-600',
                    info: 'from-blue-500 to-blue-600'
                };
                
                const icons = {
                    success: 'fas fa-check-circle',
                    error: 'fas fa-exclamation-circle',
                    info: 'fas fa-info-circle'
                };
                
                const notification = document.createElement('div');
                notification.className = `notification glass-effect rounded-xl p-4 text-white max-w-sm bg-gradient-to-r ${colors[type]} shadow-lg`;
                notification.innerHTML = `
                    <div class="flex items-center">
                        <i class="${icons[type]} mr-3"></i>
                        <span>${message}</span>
                        <button class="ml-auto text-white hover:text-gray-200" onclick="this.parentElement.parentElement.remove()">
                            <i class="fas fa-times"></i>
                        </button>
                    </div>
                `;
                
                this.elements.notificationContainer.appendChild(notification);
                
                setTimeout(() => {
                    if (notification.parentElement) {
                        notification.remove();
                    }
                }, 5000);
            }
            
            showSuccessModal() {
                this.elements.successModal.classList.remove('hidden');
                this.showNotification('Target tabungan tercapai! Selamat!', 'success');
            }
            
            closeSuccessModal() {
                this.elements.successModal.classList.add('hidden');
            }
            
            formatCurrency(amount) {
                return new Intl.NumberFormat('id-ID', {
                    style: 'currency',
                    currency: 'IDR',
                    minimumFractionDigits: 0
                }).format(amount);
            }
            
            saveToLocalStorage() {
                localStorage.setItem('currentAmount', this.currentAmount.toString());
                localStorage.setItem('targetAmount', this.targetAmount.toString());
                localStorage.setItem('targetReached', this.targetReached.toString());
                localStorage.setItem('transactions', JSON.stringify(this.transactions));
            }
        }
        
        // Initialize the savings tracker when the page loads
        document.addEventListener('DOMContentLoaded', () => {
            new SavingsTracker();
        });
    </script>
</body>
</html>
