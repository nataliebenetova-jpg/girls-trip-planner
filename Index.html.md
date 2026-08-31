<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8" />  
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0" />  
<title>Girls Getaway</title>  
<link rel="preconnect" href="https://fonts.googleapis.com">  
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,500;0,9..144,600;1,9..144,500;1,9..144,600&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">  
<style>  
  :root{  
    --blush:#F7D6DF;  
    --hot:#E85D8A;  
    --hot-deep:#D6467A;  
    --cream:#FFF9F5;  
    --ink:#242124;  
    --lavender:#DCD4F7;  
    --peach:#FFD9C7;  
    --white:#FFFFFF;  
    --ink-soft:rgba(36,33,36,0.6);  
    --ink-faint:rgba(36,33,36,0.38);  
    --line:rgba(36,33,36,0.08);  
    --shadow-soft: 0 8px 24px rgba(232,93,138,0.14);  
    --shadow-card: 0 2px 10px rgba(36,33,36,0.06);  
    --radius-lg: 26px;  
    --radius-md: 18px;  
    --radius-sm: 12px;  
  }  
  *{box-sizing:border-box; -webkit-tap-highlight-color:transparent;}  
  html,body{margin:0;padding:0;}  
  body{  
    font-family:'DM Sans', sans-serif;  
    background:var(--cream);  
    color:var(--ink);  
    overscroll-behavior:none;  
  }  
  h1,h2,h3,.display{  
    font-family:'Fraunces', serif;  
    font-weight:500;  
    letter-spacing:-0.01em;  
  }  
  button{font-family:inherit; cursor:pointer;}  
  input,textarea{font-family:inherit;}  
  ::-webkit-scrollbar{display:none;}  
  *{scrollbar-width:none;}  
  
  #root{  
    max-width:460px;  
    margin:0 auto;  
    min-height:100vh;  
    background:var(--cream);  
    position:relative;  
    display:flex;  
    flex-direction:column;  
    box-shadow:0 0 60px rgba(0,0,0,0.06);  
  }  
  
  .screen{  
    flex:1;  
    padding-bottom:104px;  
    animation:fadeIn .35s ease;  
  }  
  @keyframes fadeIn{from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);}}  
  
  /* ---------- top bar ---------- */  
  .topbar{  
    padding:22px 20px 8px;  
  }  
  .eyebrow-row{display:flex; justify-content:space-between; align-items:center;}  
  .hello{font-size:13px; color:var(--ink-soft);}  
  .avatar-btn{width:38px;height:38px;border-radius:50%;background:linear-gradient(135deg,var(--peach),var(--hot)); border:none; display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:14px;}  
  
  .headline{  
    font-size:30px;  
    line-height:1.15;  
    margin:14px 0 4px;  
  }  
  .headline i{font-style:italic; color:var(--hot);}  
  .subtext{font-size:14.5px; color:var(--ink-soft); margin:0 0 18px;}  
  
  .search-bar{  
    display:flex;align-items:center;gap:10px;  
    background:var(--white);  
    border:1px solid var(--line);  
    border-radius:100px;  
    padding:14px 18px;  
    margin-bottom:26px;  
    box-shadow:var(--shadow-card);  
  }  
  .search-bar input{  
    border:none;outline:none;background:transparent;flex:1;font-size:14.5px;color:var(--ink);  
  }  
  .search-bar input::placeholder{color:var(--ink-faint);}  
  
  .section-head{  
    display:flex;justify-content:space-between;align-items:baseline;  
    padding:0 20px; margin:28px 0 14px;  
  }  
  .section-title{font-size:19px;}  
  .section-link{font-size:12.5px;color:var(--hot);font-weight:600;background:none;border:none;}  
  
  /* ---------- horizontal scroller ---------- */  
  .hscroll{  
    display:flex; gap:14px; overflow-x:auto; padding:0 20px 6px;  
  }  
  
  .dest-card{  
    position:relative; flex:0 0 auto; width:168px; height:220px;  
    border-radius:var(--radius-md); overflow:hidden; background-size:cover; background-position:center;  
    box-shadow:var(--shadow-card);  
  }  
  .dest-card .overlay{  
    position:absolute; inset:0;  
    background:linear-gradient(180deg, rgba(0,0,0,0) 40%, rgba(20,10,15,0.72) 100%);  
  }  
  .dest-card .info{position:absolute; left:14px; right:14px; bottom:12px; color:white;}  
  .dest-card .info .name{font-size:16px; font-family:'Fraunces',serif; font-weight:500;}  
  .dest-card .info .sub{font-size:11.5px; opacity:.88; margin-top:2px;}  
  .heart-btn{  
    position:absolute; top:10px; right:10px; width:30px;height:30px;border-radius:50%;  
    background:rgba(255,255,255,0.85); border:none; display:flex;align-items:center;justify-content:center;  
    font-size:14px; transition:transform .18s ease;  
  }  
  .heart-btn.pop{animation:heartPop .4s ease;}  
  @keyframes heartPop{0%{transform:scale(1);}35%{transform:scale(1.4);}100%{transform:scale(1);}}  
  
  /* ---------- chips ---------- */  
  .chip-row{display:flex; gap:9px; overflow-x:auto; padding:0 20px 4px;}  
  .chip{  
    flex:0 0 auto; padding:9px 16px; border-radius:100px; border:1px solid var(--line);  
    background:var(--white); font-size:13px; font-weight:600; color:var(--ink); display:flex; gap:6px; align-items:center;  
    transition:all .16s ease;  
  }  
  .chip.active{background:var(--ink); color:var(--white); border-color:var(--ink);}  
  
  /* ---------- popular cards (vertical) ---------- */  
  .pop-card{  
    margin:0 20px 14px; background:var(--white); border-radius:var(--radius-md);  
    display:flex; overflow:hidden; box-shadow:var(--shadow-card); border:1px solid var(--line);  
  }  
  .pop-card .thumb{width:104px; background-size:cover; background-position:center; flex:0 0 104px;}  
  .pop-card .body{padding:13px 14px; flex:1; display:flex; flex-direction:column;}  
  .pop-card .name{font-family:'Fraunces',serif; font-size:16.5px;}  
  .pop-card .meta{font-size:11.5px; color:var(--ink-soft); margin:3px 0 8px;}  
  .pop-card .foot{display:flex; justify-content:space-between; align-items:center; margin-top:auto;}  
  .pop-card .price{font-size:12.5px; font-weight:700; color:var(--hot-deep);}  
  .btn-mini{background:var(--ink); color:white; border:none; border-radius:100px; padding:7px 14px; font-size:11.5px; font-weight:600;}  
  
  /* generic buttons */  
  .btn-primary{  
    width:100%; background:linear-gradient(135deg,var(--hot),var(--hot-deep)); color:white; border:none;  
    padding:16px; border-radius:100px; font-size:15px; font-weight:700; box-shadow:var(--shadow-soft);  
    transition:transform .12s ease;  
  }  
  .btn-primary:active{transform:scale(0.97);}  
  .btn-secondary{  
    width:100%; background:var(--white); color:var(--ink); border:1px solid var(--line);  
    padding:15px; border-radius:100px; font-size:14.5px; font-weight:700;  
  }  
  .btn-outline-pink{  
    background:var(--white); color:var(--hot-deep); border:1.4px solid var(--hot); border-radius:100px;  
    padding:10px 16px; font-size:13px; font-weight:700;  
  }  
  
  /* ---------- upcoming trip card (home) ---------- */  
  .upcoming-card{  
    margin:0 20px; border-radius:var(--radius-lg); overflow:hidden; position:relative; height:200px;  
    background-size:cover; background-position:center; box-shadow:var(--shadow-soft);  
  }  
  .upcoming-card .overlay{position:absolute; inset:0; background:linear-gradient(180deg, rgba(20,10,15,0.05) 30%, rgba(20,10,15,0.78) 100%);}  
  .upcoming-card .tag{  
    position:absolute; top:14px; left:14px; background:rgba(255,255,255,0.92); color:var(--hot-deep);  
    padding:5px 12px; border-radius:100px; font-size:11px; font-weight:700;  
  }  
  .upcoming-card .content{position:absolute; left:18px; right:18px; bottom:16px; color:white;}  
  .upcoming-card .name{font-size:22px; font-family:'Fraunces',serif;}  
  .upcoming-card .dates{font-size:12.5px; opacity:.9; margin-top:3px;}  
  .upcoming-card .avatars{display:flex; margin-top:10px;}  
  .mini-avatar{width:26px;height:26px;border-radius:50%; border:2px solid white; margin-left:-8px; display:flex;align-items:center;justify-content:center; font-size:10px; font-weight:700; color:white;}  
  .mini-avatar:first-child{margin-left:0;}  
  
  .next-up{  
    margin:14px 20px 0; background:var(--white); border-radius:var(--radius-md); padding:14px 16px;  
    display:flex; align-items:center; gap:12px; box-shadow:var(--shadow-card); border:1px solid var(--line);  
  }  
  .next-up .emoji{font-size:22px;}  
  .next-up .txt .t{font-size:13.5px; font-weight:700;}  
  .next-up .txt .s{font-size:11.5px; color:var(--ink-soft);}  
  
  /* ---------- bottom nav ---------- */  
  .bottomnav{  
    position:fixed; bottom:0; left:50%; transform:translateX(-50%); width:100%; max-width:460px;  
    background:rgba(255,249,245,0.92); backdrop-filter:blur(14px);  
    border-top:1px solid var(--line);  
    display:flex; justify-content:space-around; align-items:center;  
    padding:10px 6px calc(10px + env(safe-area-inset-bottom));  
    z-index:50;  
  }  
  .navbtn{background:none;border:none;display:flex;flex-direction:column;align-items:center;gap:3px; color:var(--ink-faint); font-size:10px; font-weight:600; padding:4px 10px;}  
  .navbtn .ic{font-size:19px;}  
  .navbtn.active{color:var(--hot-deep);}  
  .navbtn.create .ic{  
    width:46px;height:46px;border-radius:50%; background:linear-gradient(135deg,var(--hot),var(--hot-deep));  
    display:flex;align-items:center;justify-content:center; color:white; font-size:22px; margin-top:-22px;  
    box-shadow:0 6px 16px rgba(232,93,138,0.45); border:4px solid var(--cream);  
  }  
  
  /* ---------- overlay / modal shell for create flow & detail pages ---------- */  
  .overlay-screen{  
    position:fixed; inset:0; max-width:460px; margin:0 auto; background:var(--cream); z-index:100;  
    display:flex; flex-direction:column; animation:slideUp .32s cubic-bezier(.22,1,.36,1);  
  }  
  @keyframes slideUp{from{transform:translateY(100%);} to{transform:translateY(0);}}  
  .overlay-head{  
    display:flex; align-items:center; gap:12px; padding:18px 20px 8px;  
  }  
  .close-btn, .back-btn{  
    width:34px;height:34px;border-radius:50%; background:var(--white); border:1px solid var(--line);  
    display:flex;align-items:center;justify-content:center; font-size:15px; flex:0 0 34px;  
  }  
  .progress-track{flex:1; height:5px; background:var(--line); border-radius:10px; overflow:hidden; display:flex; gap:4px;}  
  .progress-seg{flex:1; background:var(--line); border-radius:10px;}  
  .progress-seg.done{background:var(--hot);}  
  .overlay-body{flex:1; overflow-y:auto; padding:18px 20px 20px;}  
  .overlay-foot{padding:14px 20px calc(18px + env(safe-area-inset-bottom)); border-top:1px solid var(--line); background:var(--cream);}  
  
  .step-q{font-size:24px; margin:6px 0 8px; line-height:1.2;}  
  .step-hint{font-size:13.5px; color:var(--ink-soft); margin-bottom:22px;}  
  .field-input{  
    width:100%; border:1.5px solid var(--line); background:var(--white); border-radius:var(--radius-sm);  
    padding:15px 16px; font-size:16px; outline:none; margin-bottom:12px;  
  }  
  .field-input:focus{border-color:var(--hot);}  
  
  .select-card{  
    display:flex; align-items:center; gap:12px; padding:14px 16px; border-radius:var(--radius-sm);  
    border:1.6px solid var(--line); background:var(--white); margin-bottom:10px; transition:all .15s ease;  
  }  
  .select-card.active{border-color:var(--hot); background:linear-gradient(135deg,rgba(247,214,223,0.55),rgba(255,255,255,0.9));}  
  .select-card .emoji{font-size:20px;}  
  .select-card .label{font-size:14.5px;font-weight:600; flex:1;}  
  .select-card .check{width:20px;height:20px;border-radius:50%;border:1.6px solid var(--line); flex:0 0 20px;}  
  .select-card.active .check{background:var(--hot); border-color:var(--hot); position:relative;}  
  .select-card.active .check::after{content:"✓"; color:white; font-size:11px; position:absolute; inset:0; display:flex; align-items:center; justify-content:center;}  
  
  .grid2{display:grid; grid-template-columns:1fr 1fr; gap:10px;}  
  
  .friend-row{display:flex; align-items:center; gap:12px; padding:10px 4px;}  
  .friend-row .fav{width:40px;height:40px;border-radius:50%; display:flex;align-items:center;justify-content:center; color:white; font-weight:700; font-size:14px;}  
  .friend-row .name{flex:1; font-size:14.5px; font-weight:600;}  
  
  /* ---------- dashboard ---------- */  
  .hero{  
    height:250px; background-size:cover; background-position:center; position:relative;  
  }  
  .hero .overlay{position:absolute; inset:0; background:linear-gradient(180deg, rgba(20,10,15,0.15) 0%, rgba(20,10,15,0.15) 45%, rgba(20,10,15,0.82) 100%);}  
  .hero-topbar{position:absolute; top:18px; left:18px; right:18px; display:flex; justify-content:space-between;}  
  .round-btn{width:36px;height:36px;border-radius:50%; background:rgba(255,255,255,0.9); border:none; display:flex; align-items:center; justify-content:center; font-size:15px;}  
  .hero-content{position:absolute; left:20px; right:20px; bottom:18px; color:white;}  
  .hero-content .title{font-size:27px; font-family:'Fraunces',serif;}  
  .hero-content .dates{font-size:13px; opacity:.92; margin:4px 0 12px;}  
  .hero-content .members-row{display:flex; align-items:center; justify-content:space-between;}  
  .hero-content .avatars{display:flex;}  
  
  .tabbar{  
    display:flex; gap:8px; overflow-x:auto; padding:16px 20px 10px; position:sticky; top:0; background:var(--cream); z-index:5;  
  }  
  .tabbtn{  
    flex:0 0 auto; padding:9px 15px; border-radius:100px; border:1.4px solid var(--line); background:var(--white);  
    font-size:13px; font-weight:700; color:var(--ink-soft);  
  }  
  .tabbtn.active{background:var(--ink); color:white; border-color:var(--ink);}  
  
  .tabcontent{padding:4px 20px 30px;}  
  
  .day-label{font-size:12.5px; font-weight:700; color:var(--hot-deep); letter-spacing:.02em; margin:20px 0 12px;}  
  .day-label:first-child{margin-top:4px;}  
  
  .activity-card{  
    display:flex; gap:12px; background:var(--white); border:1px solid var(--line); border-radius:var(--radius-md);  
    padding:13px 14px; margin-bottom:10px; box-shadow:var(--shadow-card);  
  }  
  .activity-time{font-size:12px; font-weight:700; color:var(--ink-soft); width:44px; flex:0 0 44px; padding-top:2px;}  
  .activity-icon{width:38px;height:38px;border-radius:12px; background:var(--blush); display:flex; align-items:center; justify-content:center; font-size:17px; flex:0 0 38px;}  
  .activity-main{flex:1;}  
  .activity-main .t{font-size:14.5px; font-weight:700;}  
  .activity-main .loc{font-size:12px; color:var(--ink-soft); margin-top:2px;}  
  .activity-main .cost{font-size:12px; color:var(--hot-deep); font-weight:700; margin-top:4px;}  
  
  .add-row-btn{  
    display:flex; align-items:center; justify-content:center; gap:6px; width:100%; padding:13px;  
    border:1.6px dashed var(--hot); border-radius:var(--radius-md); background:rgba(247,214,223,0.25);  
    color:var(--hot-deep); font-weight:700; font-size:13.5px; margin-top:6px;  
  }  
  
  /* discover */  
  .disc-card{  
    background:var(--white); border-radius:var(--radius-md); overflow:hidden; margin-bottom:14px; border:1px solid var(--line); box-shadow:var(--shadow-card);  
  }  
  .disc-card .img{height:130px; background-size:cover; background-position:center;}  
  .disc-card .info{padding:12px 14px;}  
  .disc-card .row1{display:flex; justify-content:space-between; align-items:center;}  
  .disc-card .name{font-family:'Fraunces',serif; font-size:16px;}  
  .disc-card .rating{font-size:12px; font-weight:700;}  
  .disc-card .meta{font-size:11.5px; color:var(--ink-soft); margin:3px 0 10px;}  
  
  /* voting */  
  .vote-card-wrap{margin-bottom:22px;}  
  .vote-q{font-family:'Fraunces',serif; font-size:19px; margin-bottom:4px;}  
  .vote-sub{font-size:12.5px; color:var(--ink-soft); margin-bottom:14px;}  
  .vote-option{  
    background:var(--white); border-radius:var(--radius-md); overflow:hidden; margin-bottom:12px; border:1px solid var(--line);  
    box-shadow:var(--shadow-card); position:relative;  
  }  
  .vote-option .img{height:110px; background-size:cover; background-position:center; position:relative;}  
  .vote-option .bar{position:absolute; left:0; bottom:0; top:0; background:rgba(232,93,138,0.28); transition:width .5s ease;}  
  .vote-option .info{padding:11px 14px; display:flex; justify-content:space-between; align-items:center;}  
  .vote-option .name{font-size:14.5px; font-weight:700;}  
  .vote-option .pct{font-size:13px; font-weight:800; color:var(--hot-deep);}  
  .vote-btns{display:flex; gap:10px; margin-top:10px;}  
  .vote-btn{flex:1; padding:11px; border-radius:100px; border:1.6px solid var(--line); background:var(--white); font-weight:700; font-size:13.5px;}  
  .vote-btn.yes{border-color:var(--hot); color:var(--hot-deep);}  
  .vote-btn.chosen-yes{background:var(--hot); color:white;}  
  .vote-btn.chosen-no{background:var(--ink); color:white;}  
  .winner-banner{  
    background:linear-gradient(135deg,var(--hot),var(--hot-deep)); color:white; border-radius:var(--radius-md);  
    padding:16px; text-align:center; margin-bottom:16px; font-weight:700;  
  }  
  
  /* budget */  
  .budget-hero{background:var(--white); border-radius:var(--radius-lg); padding:20px; border:1px solid var(--line); box-shadow:var(--shadow-card); margin-bottom:18px;}  
  .budget-nums{display:flex; justify-content:space-between; margin-bottom:12px;}  
  .budget-nums .b{font-size:22px; font-family:'Fraunces',serif;}  
  .budget-nums .l{font-size:11.5px; color:var(--ink-soft);}  
  .prog-bar{height:9px; background:var(--blush); border-radius:10px; overflow:hidden;}  
  .prog-fill{height:100%; background:linear-gradient(90deg,var(--hot),var(--hot-deep)); border-radius:10px; transition:width .5s ease;}  
  
  .expense-row{display:flex; align-items:center; gap:12px; padding:12px 0; border-bottom:1px solid var(--line);}  
  .expense-row:last-child{border-bottom:none;}  
  .exp-icon{width:38px;height:38px;border-radius:12px; background:var(--lavender); display:flex;align-items:center;justify-content:center; font-size:16px; flex:0 0 38px;}  
  .exp-main{flex:1;}  
  .exp-main .t{font-size:14px; font-weight:700;}  
  .exp-main .s{font-size:11.5px; color:var(--ink-soft);}  
  .exp-amt{font-size:14.5px; font-weight:800;}  
  
  .settle-row{display:flex; align-items:center; gap:10px; padding:10px 0; font-size:13.5px;}  
  .settle-row b{color:var(--hot-deep);}  
  
  /* packing */  
  .pack-cat{margin-bottom:22px;}  
  .pack-cat h4{font-size:14px; margin:0 0 10px; color:var(--ink-soft); text-transform:uppercase; letter-spacing:.03em; font-family:'DM Sans'; font-weight:700;}  
  .pack-item{  
    display:flex; align-items:center; gap:12px; padding:11px 14px; background:var(--white); border-radius:var(--radius-sm);  
    border:1px solid var(--line); margin-bottom:8px;  
  }  
  .pack-check{width:22px;height:22px;border-radius:7px; border:1.8px solid var(--line); flex:0 0 22px; display:flex;align-items:center;justify-content:center;}  
  .pack-check.done{background:var(--hot); border-color:var(--hot); color:white; font-size:12px;}  
  .pack-item .lbl{flex:1; font-size:14px;}  
  .pack-item.checked .lbl{text-decoration:line-through; color:var(--ink-faint);}  
  .pack-item .who{font-size:11px; color:var(--hot-deep); font-weight:700; background:var(--blush); padding:3px 9px; border-radius:100px;}  
  
  /* chat */  
  .chat-wrap{display:flex; flex-direction:column; height:calc(100vh - 260px); min-height:400px;}  
  .chat-msgs{flex:1; overflow-y:auto; padding:10px 20px;}  
  .msg-row{display:flex; gap:10px; margin-bottom:16px;}  
  .msg-av{width:32px;height:32px;border-radius:50%; flex:0 0 32px; display:flex;align-items:center;justify-content:center; color:white; font-size:12px; font-weight:700;}  
  .msg-bubble{background:var(--white); border-radius:16px 16px 16px 4px; padding:10px 14px; max-width:78%; border:1px solid var(--line);}  
  .msg-name{font-size:11px; font-weight:700; color:var(--hot-deep); margin-bottom:2px;}  
  .msg-text{font-size:14px; line-height:1.4;}  
  .msg-time{font-size:10px; color:var(--ink-faint); margin-top:4px;}  
  .msg-row.me{flex-direction:row-reverse;}  
  .msg-row.me .msg-bubble{background:linear-gradient(135deg,var(--hot),var(--hot-deep)); color:white; border-radius:16px 16px 4px 16px; border:none;}  
  .msg-row.me .msg-name{display:none;}  
  .msg-row.me .msg-time{text-align:right;}  
  .quick-actions{display:flex; gap:8px; padding:8px 20px; overflow-x:auto;}  
  .qa-btn{flex:0 0 auto; padding:8px 13px; border-radius:100px; background:var(--blush); border:none; font-size:12px; font-weight:700; color:var(--hot-deep);}  
  .chat-input-row{display:flex; align-items:center; gap:8px; padding:10px 16px calc(10px + env(safe-area-inset-bottom)); border-top:1px solid var(--line); background:var(--cream);}  
  .icon-btn{background:none; border:none; font-size:18px; padding:6px;}  
  .chat-input-row input{flex:1; border:1px solid var(--line); background:var(--white); border-radius:100px; padding:11px 16px; font-size:14px; outline:none;}  
  .send-btn{width:36px;height:36px;border-radius:50%; background:var(--hot-deep); color:white; border:none; font-size:15px; flex:0 0 36px;}  
  
  /* memories */  
  .mem-grid{columns:2; column-gap:10px; padding:0 0;}  
  .mem-item{break-inside:avoid; margin-bottom:10px; border-radius:var(--radius-sm); overflow:hidden; background-size:cover; background-position:center;}  
  
  /* profile */  
  .profile-head{text-align:center; padding:30px 20px 10px;}  
  .profile-avatar{width:88px;height:88px;border-radius:50%; margin:0 auto 14px; background:linear-gradient(135deg,var(--peach),var(--hot)); display:flex;align-items:center;justify-content:center; color:white; font-size:30px; font-weight:700; border:4px solid white; box-shadow:var(--shadow-soft);}  
  .profile-stats{display:flex; justify-content:center; gap:30px; margin:18px 0 8px;}  
  .pstat b{display:block; font-size:20px; font-family:'Fraunces',serif;}  
  .pstat span{font-size:11px; color:var(--ink-soft);}  
  .profile-section{margin:22px 20px 0; background:var(--white); border-radius:var(--radius-md); border:1px solid var(--line); overflow:hidden; box-shadow:var(--shadow-card);}  
  .profile-row{display:flex; align-items:center; gap:13px; padding:15px 16px; border-bottom:1px solid var(--line); font-size:14.5px; font-weight:600;}  
  .profile-row:last-child{border-bottom:none;}  
  .profile-row .arrow{margin-left:auto; color:var(--ink-faint);}  
  
  /* onboarding */  
  .onb-screen{  
    position:fixed; inset:0; max-width:460px; margin:0 auto; z-index:200; display:flex; flex-direction:column;  
    background-size:cover; background-position:center; color:white;  
  }  
  .onb-scrim{position:absolute; inset:0; background:linear-gradient(180deg, rgba(20,10,15,0.35) 0%, rgba(20,10,15,0.55) 55%, rgba(20,10,15,0.92) 100%);}  
  .onb-content{position:relative; z-index:2; margin-top:auto; padding:32px 26px calc(40px + env(safe-area-inset-bottom));}  
  .onb-skip{position:relative; z-index:2; align-self:flex-end; margin:20px 20px 0; background:rgba(255,255,255,0.18); border:none; color:white; padding:8px 15px; border-radius:100px; font-size:12px; font-weight:600;}  
  .onb-title{font-size:34px; line-height:1.1; margin-bottom:10px;}  
  .onb-sub{font-size:14.5px; opacity:.9; margin-bottom:26px;}  
  .onb-dots{display:flex; gap:6px; margin-bottom:20px;}  
  .onb-dot{width:22px; height:4px; border-radius:10px; background:rgba(255,255,255,0.35);}  
  .onb-dot.active{background:white;}  
  .onb-plain{background:var(--cream); color:var(--ink);}  
  .onb-plain .onb-title{color:var(--ink);}  
  .onb-plain .onb-sub{color:var(--ink-soft); opacity:1;}  
  
  .toast{  
    position:fixed; bottom:110px; left:50%; transform:translateX(-50%); background:var(--ink); color:white;  
    padding:12px 20px; border-radius:100px; font-size:13.5px; font-weight:600; z-index:300; box-shadow:0 8px 24px rgba(0,0,0,0.25);  
    animation:toastIn .3s ease;  
  }  
  @keyframes toastIn{from{opacity:0; transform:translate(-50%,10px);} to{opacity:1; transform:translate(-50%,0);}}  
  
  .confetti-piece{position:fixed; top:-10px; z-index:400; border-radius:2px; pointer-events:none;}  
  
  .empty-state{text-align:center; padding:50px 30px; color:var(--ink-soft);}  
  .empty-state .em{font-size:36px; margin-bottom:12px;}  
  
  ::placeholder{color:var(--ink-faint);}  
</style>  
</head>  
<body>  
<div id="root"></div>  
  
<script>  
/* ============ SAMPLE DATA ============ */  
const PHOTOS = {  
  santorini: "https://images.unsplash.com/photo-1570077188670-e3a8d69ac5ff?w=800&q=80",  
  paris: "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?w=800&q=80",  
  dubai: "https://images.unsplash.com/photo-1512453979798-5ea266f8880c?w=800&q=80",  
  barcelona: "https://images.unsplash.com/photo-1583422409516-2895a77efded?w=800&q=80",  
  ibiza: "https://images.unsplash.com/photo-1533656166322-aa439a49a10a?w=800&q=80",  
  mykonos: "https://images.unsplash.com/photo-1601581875039-e899893d520c?w=800&q=80",  
  bali: "https://images.unsplash.com/photo-1537996194471-e657df975ab4?w=800&q=80",  
  rooftop: "https://images.unsplash.com/photo-1544148103-0773bf10d330?w=800&q=80",  
  beachclub: "https://images.unsplash.com/photo-1519046904884-53103b34b206?w=800&q=80",  
  resto: "https://images.unsplash.com/photo-1550966871-3ed3cdb5ed0c?w=800&q=80",  
  boat: "https://images.unsplash.com/photo-1548574505-5e239809ee19?w=800&q=80",  
  spa: "https://images.unsplash.com/photo-1540555700478-4be289fbecef?w=800&q=80",  
  photospot: "https://images.unsplash.com/photo-1533105079780-92b9be482077?w=800&q=80",  
  club: "https://images.unsplash.com/photo-1571266028243-d220c9c3b31f?w=800&q=80",  
  onb1: "https://images.unsplash.com/photo-1519046904884-53103b34b206?w=1000&q=80",  
  onb3: "https://images.unsplash.com/photo-1533105079780-92b9be482077?w=1000&q=80",  
  mem1: "https://images.unsplash.com/photo-1570077188670-e3a8d69ac5ff?w=500&q=80",  
  mem2: "https://images.unsplash.com/photo-1533656166322-aa439a49a10a?w=500&q=80",  
  mem3: "https://images.unsplash.com/photo-1601581875039-e899893d520c?w=500&q=80",  
  mem4: "https://images.unsplash.com/photo-1519046904884-53103b34b206?w=500&q=80",  
  mem5: "https://images.unsplash.com/photo-1544148103-0773bf10d330?w=500&q=80",  
  mem6: "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?w=500&q=80",  
};  
  
const FRIEND_COLORS = ["#E85D8A","#B79CED","#F6A56B","#5EC3B0","#E88A9A","#8CA6E0"];  
function colorFor(name){ let h=0; for(const c of name) h+=c.charCodeAt(0); return FRIEND_COLORS[h%FRIEND_COLORS.length]; }  
function initials(name){ return name.split(" ").map(w=>w[0]).slice(0,2).join("").toUpperCase(); }  
  
const TRENDING = [  
  {id:"santorini", name:"Santorini", country:"Greece 🇬🇷", tag:"beach days + sunsets", img:PHOTOS.santorini},  
  {id:"paris", name:"Paris", country:"France 🇫🇷", tag:"cafés + shopping", img:PHOTOS.paris},  
  {id:"dubai", name:"Dubai", country:"UAE 🇦🇪", tag:"luxury + nightlife", img:PHOTOS.dubai},  
  {id:"barcelona", name:"Barcelona", country:"Spain 🇪🇸", tag:"beaches + partying", img:PHOTOS.barcelona},  
  {id:"ibiza", name:"Ibiza", country:"Spain 🇪🇸", tag:"clubs + boat days", img:PHOTOS.ibiza},  
  {id:"mykonos", name:"Mykonos", country:"Greece 🇬🇷", tag:"beach clubs + views", img:PHOTOS.mykonos},  
];  
  
const POPULAR = [  
  {name:"Santorini", img:PHOTOS.santorini, budget:"€900–1400", length:"5–6 nights", rating:4.9},  
  {name:"Ibiza", img:PHOTOS.ibiza, budget:"€700–1200", length:"4–5 nights", rating:4.8},  
  {name:"Mykonos", img:PHOTOS.mykonos, budget:"€850–1300", length:"5 nights", rating:4.9},  
  {name:"Bali", img:PHOTOS.bali, budget:"€1100–1800", length:"7–8 nights", rating:4.7},  
];  
  
const MOODS = ["🏖 Beach","🎉 Party","🛍 Shopping","💅 Spa","🍸 Nightlife","🌴 Luxury","📸 Instagrammable","🏔 Adventure"];  
const TRIP_TYPES = [  
  {emoji:"🏖", label:"Relaxing"}, {emoji:"🎉", label:"Party"}, {emoji:"💅", label:"Wellness"},  
  {emoji:"🛍", label:"Shopping"}, {emoji:"📸", label:"Content trip"}, {emoji:"🏔", label:"Adventure"},  
  {emoji:"🍸", label:"Luxury"}, {emoji:"❤", label:"Romantic-ish getaway"}  
];  
  
const DISCOVER_ITEMS = [  
  {cat:"🍸 Rooftop bars", name:"Sunset & Vine Rooftop", img:PHOTOS.rooftop, rating:4.8, price:"€€€", dist:"0.6 km"},  
  {cat:"🏖 Beach clubs", name:"Nammos Beach Club", img:PHOTOS.beachclub, rating:4.7, price:"€€€€", dist:"1.2 km"},  
  {cat:"🍝 Restaurants", name:"La Maison Bleue", img:PHOTOS.resto, rating:4.9, price:"€€€", dist:"0.4 km"},  
  {cat:"🚤 Boat trips", name:"Caldera Sunset Cruise", img:PHOTOS.boat, rating:4.9, price:"€€€", dist:"2.1 km"},  
  {cat:"💅 Spas", name:"Bloom Wellness Spa", img:PHOTOS.spa, rating:4.6, price:"€€", dist:"0.9 km"},  
  {cat:"📸 Photo spots", name:"Oia Blue Domes", img:PHOTOS.photospot, rating:5.0, price:"Free", dist:"1.5 km"},  
  {cat:"🎉 Clubs", name:"Cavo Paradiso", img:PHOTOS.club, rating:4.7, price:"€€€", dist:"3.4 km"},  
];  
  
function makeDefaultTrip(){  
  const members = ["Natalie","Sarah","Emma","Mia","Priya","Zoe"].map(n=>({name:n, color:colorFor(n)}));  
  return {  
    id:"trip-greece",  
    name:"Girls in Greece 🇬🇷",  
    destination:"Santorini",  
    country:"Greece",  
    img:PHOTOS.santorini,  
    startDate:"2026-06-14", endDate:"2026-06-20", nights:6,  
    members,  
    moods:["🏖 Beach","📸 Instagrammable","🍸 Nightlife"],  
    budgetCap:5000,  
    itinerary:{  
      "Day 1 — Arrival ✈":[  
        {time:"14:00", icon:"✈", title:"Arrive in Santorini", loc:"JTR Airport", cost:"—"},  
        {time:"16:00", icon:"🏨", title:"Check into hotel", loc:"Oia Cliffside Suites", cost:"€900"},  
        {time:"18:30", icon:"📸", title:"Sunset at Oia", loc:"Oia Castle", cost:"Free"},  
        {time:"20:30", icon:"🍝", title:"Dinner", loc:"La Maison Bleue", cost:"€120"},  
      ],  
      "Day 2 — Beach Day 🏖":[  
        {time:"11:00", icon:"🏖", title:"Beach club day", loc:"Nammos Beach Club", cost:"€180"},  
        {time:"20:00", icon:"🍸", title:"Cocktails at rooftop", loc:"Sunset & Vine", cost:"€90"},  
      ],  
      "Day 3 — Boat Day ⛵":[  
        {time:"10:00", icon:"🚤", title:"Caldera sunset cruise", loc:"Ammoudi Bay", cost:"€280"},  
      ],  
    },  
    expenses:[  
      {desc:"Hotel", cat:"🏨", amount:900, paidBy:"Sarah", split:["Natalie","Sarah","Emma","Mia","Priya","Zoe"]},  
      {desc:"Dinner", cat:"🍝", amount:120, paidBy:"Emma", split:["Natalie","Sarah","Emma","Mia"]},  
      {desc:"Boat trip", cat:"🚤", amount:280, paidBy:"Mia", split:["Natalie","Sarah","Emma","Mia","Priya","Zoe"]},  
    ],  
    packing:{  
      "Essentials":[{item:"Passport", who:null, done:false},{item:"ID", who:null, done:true},{item:"Wallet", who:null, done:false},{item:"Phone charger", who:null, done:false}],  
      "Beach":[{item:"Bikini", who:null, done:false},{item:"Sunglasses", who:null, done:true},{item:"Sunscreen", who:null, done:false},{item:"Beach bag", who:null, done:false}],  
      "Night Out":[{item:"Dress", who:null, done:false},{item:"Heels", who:null, done:false},{item:"Makeup", who:null, done:false},{item:"Portable speaker", who:"Emma", done:true}],  
    },  
    chat:[  
      {name:"Sarah", text:"omg I just booked the hotel!! 🏨✨", time:"9:14 AM", me:false},  
      {name:"Emma", text:"YESSS this view is unreal", time:"9:15 AM", me:false},  
      {name:"Mia", text:"can we do the boat trip on day 3?? I'll add it", time:"9:20 AM", me:false},  
      {name:"Natalie", text:"obsessed. adding it to the itinerary now", time:"9:22 AM", me:true},  
      {name:"Priya", text:"who's paying for dinner tonight lol", time:"9:24 AM", me:false},  
    ],  
    votes:[  
      {  
        question:"Where should we eat tonight?",  
        sub:"Everyone gets one vote — majority wins",  
        options:[  
          {name:"La Maison Bleue", img:PHOTOS.resto, votes:{}},  
          {name:"Ammos Taverna", img:PHOTOS.beachclub, votes:{}},  
          {name:"Sunset & Vine", img:PHOTOS.rooftop, votes:{}},  
        ],  
        myVote:null, revealed:false,  
      }  
    ],  
    memories:[PHOTOS.mem1,PHOTOS.mem2,PHOTOS.mem3,PHOTOS.mem4,PHOTOS.mem5,PHOTOS.mem6],  
  };  
}  
  
/* ============ STATE ============ */  
const state = {  
  screen:"onboarding",  
  onbStep:0,  
  onbMoods:new Set(),  
  home:{ query:"", moodFilter:null, saved:new Set(["santorini","mykonos"]) },  
  trips:[makeDefaultTrip()],  
  currentTripId:"trip-greece",  
  dashTab:"plan",  
  createFlow:null,  
  chatDraft:"",  
  toastMsg:null,  
  addExpenseOpen:false,  
  addPackOpen:{cat:null},  
  discoverFilter:null,  
};  
  
function currentTrip(){ return state.trips.find(t=>t.id===state.currentTripId); }  
  
/* ============ RENDER HELPERS ============ */  
const root = document.getElementById("root");  
function render(){ root.innerHTML = renderApp(); attachHandlers(); }  
  
function showToast(msg){  
  state.toastMsg = msg;  
  render();  
  setTimeout(()=>{ state.toastMsg=null; render(); }, 1800);  
}  
  
function confettiBurst(n=44){  
  const colors=["#E85D8A","#DCD4F7","#FFD9C7","#F7D6DF","#ffffff"];  
  for(let i=0;i<n;i++){  
    const el = document.createElement("div");  
    el.className="confetti-piece";  
    const size = 6+Math.random()*6;  
    el.style.width=size+"px"; el.style.height=(size*1.4)+"px";  
    el.style.background = colors[Math.floor(Math.random()*colors.length)];  
    el.style.left = (Math.random()*100)+"vw";  
    el.style.transform = `rotate(${Math.random()*360}deg)`;  
    document.body.appendChild(el);  
    const duration = 1600+Math.random()*900;  
    el.animate([  
      {transform:el.style.transform, top:"-10px", opacity:1},  
      {transform:`rotate(${Math.random()*720}deg)`, top:"100vh", opacity:0.9}  
    ], {duration, easing:"cubic-bezier(.25,.46,.45,.94)"});  
    setTimeout(()=>el.remove(), duration+50);  
  }  
}  
  
/* ============ APP SHELL ============ */  
function renderApp(){  
  let html = "";  
  if(state.screen==="onboarding"){ return renderOnboarding(); }  
  
  html += `<div class="screen">`;  
  if(state.screen==="home") html += renderHome();  
  else if(state.screen==="trips") html += renderTrips();  
  else if(state.screen==="dashboard") html += renderDashboard();  
  else if(state.screen==="chatlist") html += renderChatList();  
  else if(state.screen==="profile") html += renderProfile();  
  html += `</div>`;  
  
  html += renderBottomNav();  
  
  if(state.createFlow) html += renderCreateFlow();  
  if(state.toastMsg) html += `<div class="toast">${state.toastMsg}</div>`;  
  
  return html;  
}  
  
function renderBottomNav(){  
  const items = [  
    {id:"home", ic:"🏠", label:"Home"},  
    {id:"trips", ic:"✈", label:"Trips"},  
    {id:"create", ic:"+", label:"", create:true},  
    {id:"chatlist", ic:"💬", label:"Chat"},  
    {id:"profile", ic:"👤", label:"Profile"},  
  ];  
  return `<div class="bottomnav">  
    ${items.map(it=>{  
      if(it.create){  
        return `<button class="navbtn create" onclick="openCreateFlow()"><span class="ic">+</span></button>`;  
      }  
      const active = state.screen===it.id ? "active":"";  
      return `<button class="navbtn ${active}" onclick="goScreen('${it.id}')"><span class="ic">${it.ic}</span><span>${it.label}</span></button>`;  
    }).join("")}  
  </div>`;  
}  
  
function goScreen(s){ state.screen=s; state.dashTab="plan"; window.scrollTo(0,0); render(); }  
  
/* ============ ONBOARDING ============ */  
function renderOnboarding(){  
  const step = state.onbStep;  
  if(step===0){  
    return `<div class="onb-screen" style="background-image:url('${PHOTOS.onb1}')">  
      <div class="onb-scrim"></div>  
      <button class="onb-skip" onclick="skipOnboarding()">Skip</button>  
      <div class="onb-content">  
        <div class="onb-title">Travel is better with <i style="font-style:italic;color:var(--peach)">your girls.</i> 💕</div>  
        <div class="onb-sub">Plan. Vote. Split. Pack. Make memories.</div>  
        <button class="btn-primary" onclick="onbNext()">Let's go ✨</button>  
      </div>  
    </div>`;  
  }  
  if(step===1){  
    const moods = ["🏖 Beach","🎉 Party","🌴 Luxury","🏔 Adventure","🛍 Shopping","💅 Wellness","🍝 Food","🎭 Culture"];  
    return `<div class="onb-screen onb-plain">  
      <button class="onb-skip" style="color:var(--ink); background:var(--white); border:1px solid var(--line)" onclick="skipOnboarding()">Skip</button>  
      <div class="onb-content" style="margin-top:60px; padding-top:0;">  
        <div class="onb-dots">${[0,1,2].map(i=>`<div class="onb-dot ${i===1?'active':''}"></div>`).join("")}</div>  
        <div class="onb-title">What kind of trips do you love?</div>  
        <div class="onb-sub">Pick a few — we'll use these to recommend destinations.</div>  
        <div class="grid2" style="margin-bottom:22px;">  
          ${moods.map(m=>`<button class="select-card ${state.onbMoods.has(m)?'active':''}" style="margin-bottom:0" onclick="toggleOnbMood('${m}')">  
            <span class="emoji">${m.split(" ")[0]}</span><span class="label">${m.split(" ").slice(1).join(" ")}</span>  
          </button>`).join("")}  
        </div>  
        <button class="btn-primary" onclick="onbNext()">Continue</button>  
      </div>  
    </div>`;  
  }  
  return `<div class="onb-screen" style="background-image:url('${PHOTOS.onb3}')">  
    <div class="onb-scrim"></div>  
    <button class="onb-skip" onclick="skipOnboarding()">Skip</button>  
    <div class="onb-content">  
      <div class="onb-dots">${[0,1,2].map(i=>`<div class="onb-dot ${i===2?'active':''}"></div>`).join("")}</div>  
      <div class="onb-title">Where do you want to go?</div>  
      <div class="onb-sub" style="margin-bottom:18px;">A few favorites based on your vibe:</div>  
      <div class="hscroll" style="padding:0 0 18px; margin:0 -4px;">  
        ${TRENDING.slice(0,4).map(d=>`<div class="dest-card" style="width:120px;height:150px;background-image:url('${d.img}')"><div class="overlay"></div><div class="info"><div class="name" style="font-size:13px">${d.name}</div></div></div>`).join("")}  
      </div>  
      <button class="btn-primary" onclick="finishOnboarding()">Start planning ✈</button>  
    </div>  
  </div>`;  
}  
function toggleOnbMood(m){ state.onbMoods.has(m) ? state.onbMoods.delete(m) : state.onbMoods.add(m); render(); }  
function onbNext(){ state.onbStep++; render(); }  
function skipOnboarding(){ finishOnboarding(); }  
function finishOnboarding(){ state.screen="home"; render(); }  
  
/* ============ HOME ============ */  
function renderHome(){  
  const trip = currentTrip();  
  const filteredTrending = state.home.query  
    ? TRENDING.filter(d=>d.name.toLowerCase().includes(state.home.query.toLowerCase()))  
    : TRENDING;  
  
  return `  
    <div class="topbar">  
      <div class="eyebrow-row">  
        <div class="hello">Hey Natalie 👋</div>  
        <button class="avatar-btn" onclick="goScreen('profile')">N</button>  
      </div>  
      <div class="headline">Where are we going, <i>girls?</i> ✈</div>  
      <div class="subtext">Plan your next unforgettable trip together.</div>  
      <div class="search-bar">  
        <span>🔍</span>  
        <input placeholder="Search destinations…" value="${state.home.query}" oninput="onSearchInput(this.value)"/>  
      </div>  
    </div>  
  
    ${trip ? `  
    <div class="section-head" style="margin-top:0;"><div class="section-title">Upcoming trip</div></div>  
    <div class="upcoming-card" style="background-image:url('${trip.img}')" onclick="openTrip('${trip.id}')">  
      <div class="overlay"></div>  
      <div class="tag">${fmtDateRange(trip.startDate,trip.endDate)}</div>  
      <div class="content">  
        <div class="name">${trip.name}</div>  
        <div class="dates">${trip.members.length} girls · ${trip.nights} nights</div>  
        <div class="avatars">${trip.members.slice(0,5).map(m=>`<div class="mini-avatar" style="background:${m.color}">${initials(m.name)}</div>`).join("")}</div>  
      </div>  
    </div>  
    <div class="next-up">  
      <div class="emoji">🌅</div>  
      <div class="txt"><div class="t">Sunset dinner in Oia</div><div class="s">Tomorrow · 19:30</div></div>  
    </div>  
    ` : ``}  
  
    <div class="section-head">  
      <div class="section-title">Trending Girls Trips</div>  
    </div>  
    <div class="hscroll">  
      ${filteredTrending.map(d=>renderDestCard(d)).join("")}  
    </div>  
  
    <div class="section-head"><div class="section-title">What are you in the mood for?</div></div>  
    <div class="chip-row">  
      ${MOODS.map(m=>`<button class="chip ${state.home.moodFilter===m?'active':''}" onclick="toggleMoodFilter('${m}')">${m}</button>`).join("")}  
    </div>  
  
    <div class="section-head"><div class="section-title">Popular with girls right now</div></div>  
    ${POPULAR.map(p=>`  
      <div class="pop-card">  
        <div class="thumb" style="background-image:url('${p.img}')"></div>  
        <div class="body">  
          <div class="name">${p.name}</div>  
          <div class="meta">${p.budget} · ${p.length} · ⭐ ${p.rating}</div>  
          <div class="foot"><span class="price">${p.budget.split("–")[0]}+</span><button class="btn-mini" onclick="viewTripSuggestion('${p.name}')">View trip</button></div>  
        </div>  
      </div>  
    `).join("")}  
  `;  
}  
  
function renderDestCard(d){  
  const saved = state.home.saved.has(d.id);  
  return `<div class="dest-card" style="background-image:url('${d.img}')">  
    <div class="overlay"></div>  
    <button class="heart-btn" id="heart-${d.id}" onclick="toggleSave('${d.id}', event)">${saved?"❤":"🤍"}</button>  
    <div class="info" onclick="viewTripSuggestion('${d.name}')">  
      <div class="name">${d.name}</div>  
      <div class="sub">${d.tag}</div>  
    </div>  
  </div>`;  
}  
function onSearchInput(v){ state.home.query=v; render(); }  
function toggleSave(id, e){  
  if(e) e.stopPropagation();  
  state.home.saved.has(id) ? state.home.saved.delete(id) : state.home.saved.add(id);  
  render();  
  const btn = document.getElementById("heart-"+id);  
  if(btn){ btn.classList.add("pop"); setTimeout(()=>btn.classList.remove("pop"),400); }  
}  
function toggleMoodFilter(m){ state.home.moodFilter = state.home.moodFilter===m ? null : m; render(); showToast(`Showing trips for ${m}`); }  
function viewTripSuggestion(name){ showToast(`✨ Exploring ${name} — tap + to plan a trip there`); }  
  
function fmtDateRange(a,b){  
  const opts={month:"short", day:"numeric"};  
  const da=new Date(a), db=new Date(b);  
  return `${da.toLocaleDateString('en-US',opts)}–${db.toLocaleDateString('en-US',{day:'numeric'})}`;  
}  
  
/* ============ TRIPS LIST ============ */  
function renderTrips(){  
  const trips = state.trips;  
  return `  
    <div class="topbar"><div class="eyebrow-row"><div class="headline" style="margin-bottom:0;">Your trips ✈</div></div></div>  
    <div class="section-head" style="margin-top:6px;"><div class="section-title">Upcoming</div></div>  
    ${trips.map(t=>`  
      <div class="pop-card" style="height:auto;" onclick="openTrip('${t.id}')">  
        <div class="thumb" style="background-image:url('${t.img}')"></div>  
        <div class="body">  
          <div class="name">${t.name}</div>  
          <div class="meta">${fmtDateRange(t.startDate,t.endDate)} · ${t.members.length} girls</div>  
          <div class="foot"><div class="avatars" style="display:flex;">${t.members.slice(0,4).map(m=>`<div class="mini-avatar" style="background:${m.color}">${initials(m.name)}</div>`).join("")}</div><button class="btn-mini">Open</button></div>  
        </div>  
      </div>  
    `).join("")}  
    <div class="section-head"><div class="section-title">Past trips</div></div>  
    <div class="pop-card" style="opacity:.7;">  
      <div class="thumb" style="background-image:url('${PHOTOS.barcelona}')"></div>  
      <div class="body"><div class="name">Barcelona Bachelorette</div><div class="meta">Sep 2025 · 5 girls</div>  
      <div class="foot"><span class="price">Memories saved</span><button class="btn-mini" onclick="event.stopPropagation(); showToast('Opening memories 📸')">View</button></div></div>  
    </div>  
    <div style="padding:10px 20px 0;"><button class="btn-secondary" onclick="openCreateFlow()">+ Plan a new trip</button></div>  
  `;  
}  
function openTrip(id){ state.currentTripId=id; state.dashTab="plan"; state.screen="dashboard"; render(); window.scrollTo(0,0); }  
  
/* ============ DASHBOARD ============ */  
function renderDashboard(){  
  const t = currentTrip();  
  if(!t) return `<div class="empty-state"><div class="em">✈</div>No trip selected yet.</div>`;  
  const tabs = [  
    {id:"plan", label:"Plan"},  
    {id:"discover", label:"Discover"},  
    {id:"vote", label:"Vote"},  
    {id:"budget", label:"Budget"},  
    {id:"packing", label:"Packing"},  
    {id:"chat", label:"Chat"},  
    {id:"memories", label:"Memories"},  
  ];  
  let body="";  
  if(state.dashTab==="plan") body=renderPlanTab(t);  
  else if(state.dashTab==="discover") body=renderDiscoverTab(t);  
  else if(state.dashTab==="vote") body=renderVoteTab(t);  
  else if(state.dashTab==="budget") body=renderBudgetTab(t);  
  else if(state.dashTab==="packing") body=renderPackingTab(t);  
  else if(state.dashTab==="chat") body=renderChatTab(t);  
  else if(state.dashTab==="memories") body=renderMemoriesTab(t);  
  
  return `  
    <div class="hero" style="background-image:url('${t.img}')">  
      <div class="overlay"></div>  
      <div class="hero-topbar">  
        <button class="round-btn" onclick="goScreen('trips')">←</button>  
        <button class="round-btn" onclick="showToast('Trip settings coming soon')">**⋯**</button>  
      </div>  
      <div class="hero-content">  
        <div class="title">${t.name}</div>  
        <div class="dates">${fmtDateRange(t.startDate,t.endDate)} · ${t.nights} nights</div>  
        <div class="members-row">  
          <div class="avatars">${t.members.slice(0,5).map(m=>`<div class="mini-avatar" style="background:${m.color}">${initials(m.name)}</div>`).join("")}</div>  
          <button class="btn-outline-pink" style="background:rgba(255,255,255,0.92)" onclick="inviteFriends()">Invite friends</button>  
        </div>  
      </div>  
    </div>  
    <div class="tabbar">  
      ${tabs.map(tb=>`<button class="tabbtn ${state.dashTab===tb.id?'active':''}" onclick="setDashTab('${tb.id}')">${tb.label}</button>`).join("")}  
    </div>  
    <div class="tabcontent">${body}</div>  
  `;  
}  
function setDashTab(id){ state.dashTab=id; render(); }  
function inviteFriends(){ showToast("🔗 Invite link copied!"); }  
  
/* ---- Plan tab ---- */  
function renderPlanTab(t){  
  let html="";  
  for(const day in t.itinerary){  
    html += `<div class="day-label">${day.toUpperCase()}</div>`;  
    t.itinerary[day].forEach((a,i)=>{  
      html += `<div class="activity-card">  
        <div class="activity-time">${a.time}</div>  
        <div class="activity-icon">${a.icon}</div>  
        <div class="activity-main">  
          <div class="t">${a.title}</div>  
          <div class="loc">📍 ${a.loc}</div>  
          <div class="cost">${a.cost}</div>  
        </div>  
      </div>`;  
    });  
  }  
  html += `<button class="add-row-btn" onclick="addActivity()">+ Add activity</button>`;  
  return html;  
}  
function addActivity(){  
  const t=currentTrip();  
  const days = Object.keys(t.itinerary);  
  const lastDay = days[days.length-1];  
  t.itinerary[lastDay].push({time:"21:30", icon:"✨", title:"New activity", loc:"Tap to edit", cost:"€—"});  
  render();  
  showToast("Activity added to itinerary ✨");  
}  
  
/* ---- Discover tab ---- */  
function renderDiscoverTab(t){  
  const cats = [...new Set(DISCOVER_ITEMS.map(i=>i.cat))];  
  const filtered = state.discoverFilter ? DISCOVER_ITEMS.filter(i=>i.cat===state.discoverFilter) : DISCOVER_ITEMS;  
  return `  
    <div class="section-title" style="margin-bottom:10px;">You might love these 💕</div>  
    <div class="chip-row" style="padding:0 0 14px; margin:0 -0px;">  
      <button class="chip ${!state.discoverFilter?'active':''}" onclick="setDiscoverFilter(null)">All</button>  
      ${cats.map(c=>`<button class="chip ${state.discoverFilter===c?'active':''}" onclick="setDiscoverFilter('${c}')">${c}</button>`).join("")}  
    </div>  
    ${filtered.map((it,idx)=>`  
      <div class="disc-card">  
        <div class="img" style="background-image:url('${it.img}')"></div>  
        <div class="info">  
          <div class="row1"><div class="name">${it.name}</div><div class="rating">⭐ ${it.rating}</div></div>  
          <div class="meta">${it.cat} · ${it.price} · ${it.dist}</div>  
          <button class="btn-mini" style="width:100%; padding:9px;" onclick="addToItinerary('${it.name.replace(/'/g,"\\'")}')">+ Add to trip</button>  
        </div>  
      </div>  
    `).join("")}  
  `;  
}  
function setDiscoverFilter(c){ state.discoverFilter=c; render(); }  
function addToItinerary(name){  
  const t=currentTrip();  
  const days=Object.keys(t.itinerary);  
  const lastDay=days[days.length-1];  
  t.itinerary[lastDay].push({time:"22:00", icon:"✨", title:name, loc:t.destination, cost:"€—"});  
  showToast(`${name} added to itinerary ✨`);  
}  
  
/* ---- Vote tab ---- */  
function renderVoteTab(t){  
  const v = t.votes[0];  
  const totalVotes = Object.keys(v.votes||{}).length + t.members.reduce((n,m)=>n + (v.options.some(o=>o.votes[m.name])?1:0),0);  
  const counts = v.options.map(o=>Object.values(o.votes).length);  
  const grand = counts.reduce((a,b)=>a+b,0) || 1;  
  const winnerIdx = counts.indexOf(Math.max(...counts));  
  
  return `  
    <div class="vote-card-wrap">  
      <div class="vote-q">Girls, vote! 💅</div>  
      <div class="vote-sub">${v.question}</div>  
      ${v.revealed ? `<div class="winner-banner">🎉 The girls have decided! Winner: ${v.options[winnerIdx].name}</div>` : ``}  
      ${v.options.map((o,i)=>{  
        const pct = v.revealed ? Math.round((counts[i]/grand)*100) : 0;  
        const myChoice = v.myVote===i;  
        return `  
        <div class="vote-option">  
          <div class="img" style="background-image:url('${o.img}')">  
            ${v.revealed ? `<div class="bar" style="width:${pct}%"></div>` : ``}  
          </div>  
          <div class="info">  
            <div class="name">${o.name}</div>  
            ${v.revealed ? `<div class="pct">${pct}%</div>` : `  
            <div class="vote-btns" style="margin-top:0;">  
              <button class="vote-btn yes ${myChoice?'chosen-yes':''}" onclick="castVote(0,${i})">❤ Yes</button>  
            </div>`}  
          </div>  
        </div>`;  
      }).join("")}  
      ${!v.revealed ? `<button class="btn-primary" onclick="revealVote(0)" style="margin-top:6px;">Reveal results 🎉</button>` : `<button class="btn-secondary" onclick="resetVote(0)">Start a new vote</button>`}  
    </div>  
  `;  
}  
function castVote(vIdx, optIdx){  
  const t=currentTrip(); const v=t.votes[vIdx];  
  v.options.forEach(o=>delete o.votes["Natalie"]);  
  v.options[optIdx].votes["Natalie"]=true;  
  // simulate friends voting too  
  t.members.filter(m=>m.name!=="Natalie").forEach(m=>{  
    v.options.forEach(o=>delete o.votes[m.name]);  
    const pick = Math.random()<0.55 ? optIdx : Math.floor(Math.random()*v.options.length);  
    v.options[pick].votes[m.name]=true;  
  });  
  v.myVote=optIdx;  
  render();  
}  
function revealVote(vIdx){  
  const t=currentTrip(); t.votes[vIdx].revealed=true; render(); confettiBurst(50);  
}  
function resetVote(vIdx){  
  const t=currentTrip(); const v=t.votes[vIdx];  
  v.options.forEach(o=>o.votes={}); v.revealed=false; v.myVote=null; render();  
}  
  
/* ---- Budget tab ---- */  
function renderBudgetTab(t){  
  const spent = t.expenses.reduce((s,e)=>s+e.amount,0);  
  const remaining = Math.max(t.budgetCap-spent,0);  
  const pct = Math.min((spent/t.budgetCap)*100,100);  
  const settle = computeSettleUp(t);  
  
  return `  
    <div class="budget-hero">  
      <div class="budget-nums">  
        <div><div class="b">€${spent.toLocaleString()}</div><div class="l">spent</div></div>  
        <div style="text-align:right;"><div class="b">€${remaining.toLocaleString()}</div><div class="l">remaining</div></div>  
      </div>  
      <div class="prog-bar"><div class="prog-fill" style="width:${pct}%"></div></div>  
    </div>  
  
    <div class="section-title" style="margin-bottom:6px;">Expenses</div>  
    <div class="budget-hero" style="padding:6px 20px;">  
      ${t.expenses.map(e=>`  
        <div class="expense-row">  
          <div class="exp-icon">${e.cat}</div>  
          <div class="exp-main"><div class="t">${e.desc}</div><div class="s">${e.paidBy} paid · split ${e.split.length} ways</div></div>  
          <div class="exp-amt">€${e.amount}</div>  
        </div>  
      `).join("")}  
    </div>  
    <button class="add-row-btn" onclick="openAddExpense()">+ Add expense</button>  
  
    <div class="section-title" style="margin:26px 0 6px;">Settle up</div>  
    <div class="budget-hero">  
      ${settle.length ? settle.map(s=>`<div class="settle-row">💸 <b>${s.from}</b> owes <b>${s.to}</b> <b>€${s.amount.toFixed(2)}</b></div>`).join("")  
        : `<div style="color:var(--ink-soft); font-size:13.5px;">Everyone's settled up! 🎉</div>`}  
    </div>  
  
    ${state.addExpenseOpen ? renderAddExpenseModal(t) : ""}  
  `;  
}  
function computeSettleUp(t){  
  const balances = {}; t.members.forEach(m=>balances[m.name]=0);  
  t.expenses.forEach(e=>{  
    const share = e.amount/e.split.length;  
    e.split.forEach(name=>{ balances[name]-=share; });  
    balances[e.paidBy]+=e.amount;  
  });  
  const debtors = Object.entries(balances).filter(([,v])=>v<-0.01).map(([n,v])=>({n,v:-v}));  
  const creditors = Object.entries(balances).filter(([,v])=>v>0.01).map(([n,v])=>({n,v}));  
  const res=[];  
  let di=0, ci=0;  
  debtors.sort((a,b)=>b.v-a.v); creditors.sort((a,b)=>b.v-a.v);  
  while(di<debtors.length && ci<creditors.length){  
    const amt = Math.min(debtors[di].v, creditors[ci].v);  
    if(amt>0.01) res.push({from:debtors[di].n, to:creditors[ci].n, amount:amt});  
    debtors[di].v-=amt; creditors[ci].v-=amt;  
    if(debtors[di].v<0.01) di++;  
    if(creditors[ci].v<0.01) ci++;  
  }  
  return res;  
}  
function openAddExpense(){ state.addExpenseOpen=true; state.newExpense={desc:"",amount:"",cat:"🍽",paidBy:currentTrip().members[0].name, split:currentTrip().members.map(m=>m.name)}; render(); }  
function closeAddExpense(){ state.addExpenseOpen=false; render(); }  
function renderAddExpenseModal(t){  
  const ne = state.newExpense;  
  return `  
  <div class="overlay-screen" style="z-index:150;">  
    <div class="overlay-head"><button class="close-btn" onclick="closeAddExpense()">✕</button><div style="font-weight:700; font-size:15px;">Add expense</div></div>  
    <div class="overlay-body">  
      <input class="field-input" placeholder="Description" value="${ne.desc}" oninput="ne_update('desc', this.value)"/>  
      <input class="field-input" type="number" placeholder="Amount (€)" value="${ne.amount}" oninput="ne_update('amount', this.value)"/>  
      <div class="step-hint" style="margin-bottom:8px;">Category</div>  
      <div class="chip-row" style="padding:0 0 14px;">  
        ${["🍽","🏨","🚤","🍸","🛍","🚕"].map(c=>`<button class="chip ${ne.cat===c?'active':''}" onclick="ne_update('cat','${c}')">${c}</button>`).join("")}  
      </div>  
      <div class="step-hint" style="margin-bottom:8px;">Who paid?</div>  
      ${t.members.map(m=>`<div class="select-card ${ne.paidBy===m.name?'active':''}" onclick="ne_update('paidBy','${m.name}')">  
        <span class="fav" style="width:26px;height:26px;border-radius:50%;background:${m.color};display:flex;align-items:center;justify-content:center;color:white;font-size:11px;font-weight:700;">${initials(m.name)}</span>  
        <span class="label">${m.name}</span><span class="check ${ne.paidBy===m.name?'active-radio':''}"></span>  
      </div>`).join("")}  
      <div class="step-hint" style="margin:14px 0 8px;">Split between</div>  
      ${t.members.map(m=>`<div class="select-card ${ne.split.includes(m.name)?'active':''}" onclick="ne_toggleSplit('${m.name}')">  
        <span class="fav" style="width:26px;height:26px;border-radius:50%;background:${m.color};display:flex;align-items:center;justify-content:center;color:white;font-size:11px;font-weight:700;">${initials(m.name)}</span>  
        <span class="label">${m.name}</span><span class="check"></span>  
      </div>`).join("")}  
    </div>  
    <div class="overlay-foot"><button class="btn-primary" onclick="submitExpense()">Add expense</button></div>  
  </div>`;  
}  
function ne_update(k,v){ state.newExpense[k]=v; render(); }  
function ne_toggleSplit(name){  
  const s=state.newExpense.split;  
  const idx=s.indexOf(name);  
  idx>-1 ? s.splice(idx,1) : s.push(name);  
  render();  
}  
function submitExpense(){  
  const ne=state.newExpense;  
  if(!ne.desc || !ne.amount || ne.split.length===0){ showToast("Fill in all fields first"); return; }  
  currentTrip().expenses.push({desc:ne.desc, cat:ne.cat, amount:parseFloat(ne.amount), paidBy:ne.paidBy, split:ne.split});  
  state.addExpenseOpen=false;  
  render();  
  showToast("Expense added 💸");  
}  
  
/* ---- Packing tab ---- */  
function renderPackingTab(t){  
  let html="";  
  for(const cat in t.packing){  
    html += `<div class="pack-cat"><h4>${cat}</h4>`;  
    t.packing[cat].forEach((it,idx)=>{  
      html += `<div class="pack-item ${it.done?'checked':''}">  
        <button class="pack-check ${it.done?'done':''}" onclick="togglePack('${cat}',${idx})">${it.done?'✓':''}</button>  
        <div class="lbl">${it.item}</div>  
        ${it.who ? `<div class="who">${it.who}</div>` : `<button class="btn-mini" style="background:var(--lavender); color:var(--ink);" onclick="assignPack('${cat}',${idx})">Assign</button>`}  
      </div>`;  
    });  
    html += `<button class="add-row-btn" style="padding:10px;" onclick="addPackItem('${cat}')">+ Add item</button>`;  
    html += `</div>`;  
  }  
  return html;  
}  
function togglePack(cat, idx){ const t=currentTrip(); t.packing[cat][idx].done=!t.packing[cat][idx].done; render(); }  
function assignPack(cat, idx){  
  const t=currentTrip();  
  const names=t.members.map(m=>m.name);  
  const current=t.packing[cat][idx].who;  
  const next = names[(names.indexOf(current)+1)%names.length];  
  t.packing[cat][idx].who = next;  
  render();  
}  
function addPackItem(cat){  
  const t=currentTrip();  
  t.packing[cat].push({item:"New item", who:null, done:false});  
  render();  
}  
  
/* ---- Chat tab (within trip) ---- */  
function renderChatTab(t){  
  return `  
    <div class="chat-wrap" style="height:auto; min-height:440px;">  
      <div class="chat-msgs" style="max-height:420px;">  
        ${t.chat.map(m=>`  
          <div class="msg-row ${m.me?'me':''}">  
            <div class="msg-av" style="background:${colorFor(m.name)}">${initials(m.name)}</div>  
            <div>  
              <div class="msg-bubble"><div class="msg-name">${m.name}</div><div class="msg-text">${m.text}</div></div>  
              <div class="msg-time">${m.time}</div>  
            </div>  
          </div>  
        `).join("")}  
      </div>  
      <div class="quick-actions">  
        <button class="qa-btn" onclick="setDashTab('vote')">🗳 Vote</button>  
        <button class="qa-btn" onclick="setDashTab('discover')">📍 Share activity</button>  
        <button class="qa-btn" onclick="openAddExpense()">💸 Split expense</button>  
      </div>  
      <div class="chat-input-row">  
        <button class="icon-btn">📎</button>  
        <button class="icon-btn">📷</button>  
        <input placeholder="Message the girls…" value="${state.chatDraft}" oninput="state.chatDraft=this.value" onkeydown="if(event.key==='Enter') sendChat()"/>  
        <button class="send-btn" onclick="sendChat()">➤</button>  
      </div>  
      ${state.addExpenseOpen ? renderAddExpenseModal(t) : ""}  
    </div>  
  `;  
}  
function sendChat(){  
  const text = state.chatDraft.trim();  
  if(!text) return;  
  const t=currentTrip();  
  t.chat.push({name:"Natalie", text, time:"now", me:true});  
  state.chatDraft="";  
  render();  
  const box=document.querySelector(".chat-msgs");  
  if(box) box.scrollTop=box.scrollHeight;  
  setTimeout(()=>{  
    const replies=["haha yes let's do it 😂","omg love that","adding it to the plan now!","can't wait for this trip 💕"];  
    t.chat.push({name:t.members[1].name, text:replies[Math.floor(Math.random()*replies.length)], time:"now", me:false});  
    render();  
  }, 1200);  
}  
  
/* ---- Memories tab ---- */  
function renderMemoriesTab(t){  
  return `  
    <div class="section-title" style="margin-bottom:12px;">Our Memories 📸</div>  
    <button class="add-row-btn" style="margin-bottom:14px;" onclick="addMemory()">+ Add photos</button>  
    <div class="mem-grid">  
      ${t.memories.map((m,i)=>`<div class="mem-item" style="height:${i%3===0?180:130}px; background-image:url('${m}')"></div>`).join("")}  
    </div>  
    <button class="btn-secondary" style="margin-top:18px;" onclick="createRecap()">✨ Create trip recap</button>  
  `;  
}  
function addMemory(){  
  const t=currentTrip();  
  const pool=[PHOTOS.mem1,PHOTOS.mem2,PHOTOS.mem3,PHOTOS.mem4,PHOTOS.mem5,PHOTOS.mem6];  
  t.memories.unshift(pool[Math.floor(Math.random()*pool.length)]);  
  render();  
  showToast("Photo added to memories 📸");  
}  
function createRecap(){ showToast("✨ Building your trip recap…"); }  
  
/* ============ CHAT LIST (global) ============ */  
function renderChatList(){  
  return `  
    <div class="topbar"><div class="headline" style="margin-bottom:14px;">Chats 💬</div></div>  
    ${state.trips.map(t=>`  
      <div class="pop-card" style="height:auto;" onclick="openTripChat('${t.id}')">  
        <div class="thumb" style="background-image:url('${t.img}'); flex:0 0 78px;"></div>  
        <div class="body" style="padding:12px 14px;">  
          <div class="name" style="font-size:15px;">${t.name}</div>  
          <div class="meta">${t.chat[t.chat.length-1].name}: ${t.chat[t.chat.length-1].text}</div>  
        </div>  
      </div>  
    `).join("")}  
  `;  
}  
function openTripChat(id){ state.currentTripId=id; state.dashTab="chat"; state.screen="dashboard"; render(); }  
  
/* ============ PROFILE ============ */  
function renderProfile(){  
  return `  
    <div class="profile-head">  
      <div class="profile-avatar">N</div>  
      <div class="headline" style="font-size:22px; margin-bottom:0;">Hey, Natalie 👋</div>  
      <div class="profile-stats">  
        <div class="pstat"><b>${state.trips.length + 11}</b><span>trips</span></div>  
        <div class="pstat"><b>38</b><span>places</span></div>  
        <div class="pstat"><b>${state.home.saved.size}</b><span>saved</span></div>  
      </div>  
    </div>  
    <div class="profile-section">  
      <div class="profile-row" onclick="goScreen('home')">❤ Saved destinations <span class="arrow">›</span></div>  
      <div class="profile-row" onclick="goScreen('trips')">✈ Past trips <span class="arrow">›</span></div>  
      <div class="profile-row" onclick="showToast('Friends list coming soon')">👯 Friends <span class="arrow">›</span></div>  
      <div class="profile-row" onclick="showToast('Settings coming soon')">⚙ Settings <span class="arrow">›</span></div>  
    </div>  
  `;  
}  
  
/* ============ CREATE TRIP FLOW ============ */  
function openCreateFlow(){  
  state.createFlow = {  
    step:1, name:"", destination:"", destImg:PHOTOS.santorini, startDate:"", endDate:"",  
    friends:[], types:[], budget:1500,  
  };  
  render();  
}  
function closeCreateFlow(){ state.createFlow=null; render(); }  
function cfUpdate(k,v){ state.createFlow[k]=v; render(); }  
function cfNext(){  
  if(state.createFlow.step<6){ state.createFlow.step++; render(); }  
  else finishCreateFlow();  
}  
function cfBack(){  
  if(state.createFlow.step>1) state.createFlow.step--;  
  else { closeCreateFlow(); return; }  
  render();  
}  
function cfSelectDest(name, img){ state.createFlow.destination=name; state.createFlow.destImg=img; render(); }  
function cfAddFriend(name){  
  if(!state.createFlow.friends.includes(name)) state.createFlow.friends.push(name);  
  render();  
}  
function cfToggleType(label){  
  const arr=state.createFlow.types;  
  const idx=arr.indexOf(label);  
  idx>-1 ? arr.splice(idx,1) : arr.push(label);  
  render();  
}  
function cfBudget(v){ state.createFlow.budget=v; render(); }  
  
function finishCreateFlow(){  
  const cf = state.createFlow;  
  const id = "trip-"+Date.now();  
  const chosenFriends = cf.friends.length ? cf.friends : ["Sarah","Emma"];  
  const members = ["Natalie", ...chosenFriends].map(n=>({name:n, color:colorFor(n)}));  
  const newTrip = {  
    id, name: cf.name || `Girls in ${cf.destination||'Paradise'} 💕`,  
    destination: cf.destination||"Somewhere amazing", country:"", img: cf.destImg,  
    startDate: cf.startDate || "2026-08-10", endDate: cf.endDate || "2026-08-15", nights:5,  
    members, moods: cf.types.map(t=>t), budgetCap: cf.budget,  
    itinerary:{ "Day 1 — Arrival ✈":[{time:"15:00", icon:"✈", title:"Arrive & check in", loc:cf.destination||"Hotel", cost:"—"}] },  
    expenses:[], packing:{"Essentials":[{item:"Passport",who:null,done:false},{item:"Phone charger",who:null,done:false}]},  
    chat:[{name:"Natalie", text:"so excited for this trip!! 💕", time:"now", me:true}],  
    votes:[{question:"Where should we eat on arrival night?", sub:"Everyone gets one vote", options:[  
      {name:"Local favorite", img:PHOTOS.resto, votes:{}},{name:"Beach club", img:PHOTOS.beachclub, votes:{}},{name:"Rooftop", img:PHOTOS.rooftop, votes:{}}  
    ], myVote:null, revealed:false}],  
    memories:[],  
  };  
  state.trips.push(newTrip);  
  state.currentTripId=id;  
  state.createFlow=null;  
  state.screen="dashboard";  
  state.dashTab="plan";  
  render();  
  confettiBurst(60);  
  showToast("Trip created! ✨");  
}  
  
function renderCreateFlow(){  
  const cf = state.createFlow;  
  const steps = 6;  
  let body="", canNext=true, nextLabel="Continue";  
  
  if(cf.step===1){  
    body = `  
      <div class="step-q">What should we call the trip?</div>  
      <div class="step-hint">e.g. "Girls in Greece 💕"</div>  
      <input class="field-input" placeholder="Girls in Greece 💕" value="${cf.name}" oninput="cfUpdate('name', this.value)" autofocus/>  
    `;  
  } else if(cf.step===2){  
    body = `  
      <div class="step-q">Where are you going?</div>  
      <div class="step-hint">Search a destination or pick a suggestion</div>  
      <input class="field-input" placeholder="Search destination…" value="${cf.destination}" oninput="cfUpdate('destination', this.value)"/>  
      <div style="display:flex; flex-direction:column; gap:10px; margin-top:6px;">  
        ${TRENDING.map(d=>`<div class="select-card ${cf.destination===d.name?'active':''}" onclick="cfSelectDest('${d.name}','${d.img}')">  
          <div style="width:44px;height:44px;border-radius:12px;background-image:url('${d.img}');background-size:cover;"></div>  
          <span class="label">${d.name}, ${d.country}</span><span class="check"></span>  
        </div>`).join("")}  
      </div>  
    `;  
  } else if(cf.step===3){  
    body = `  
      <div class="step-q">When are you going?</div>  
      <div class="step-hint">Pick your travel dates</div>  
      <div class="step-hint" style="margin-bottom:4px; font-weight:700; color:var(--ink);">Departure date</div>  
      <input class="field-input" type="date" value="${cf.startDate}" oninput="cfUpdate('startDate', this.value)"/>  
      <div class="step-hint" style="margin-bottom:4px; font-weight:700; color:var(--ink);">Return date</div>  
      <input class="field-input" type="date" value="${cf.endDate}" oninput="cfUpdate('endDate', this.value)"/>  
    `;  
  } else if(cf.step===4){  
    const pool=["Sarah","Emma","Mia","Priya","Zoe","Chloe","Jade"];  
    body = `  
      <div class="step-q">Who's coming?</div>  
      <div class="step-hint">Add your girls to the trip</div>  
      <div style="display:flex; gap:-8px; margin-bottom:16px;">  
        ${cf.friends.map(f=>`<div class="mini-avatar" style="background:${colorFor(f)}; width:38px;height:38px;font-size:13px;">${initials(f)}</div>`).join("")}  
      </div>  
      ${pool.map(f=>`<div class="friend-row">  
        <div class="fav" style="background:${colorFor(f)}">${initials(f)}</div>  
        <div class="name">${f}</div>  
        <button class="btn-mini" style="background:${cf.friends.includes(f)?'var(--ink)':'var(--hot-deep)'}" onclick="cfAddFriend('${f}')">${cf.friends.includes(f)?'Added ✓':'+ Invite'}</button>  
      </div>`).join("")}  
      <div style="display:flex; gap:8px; margin-top:14px;">  
        <button class="btn-outline-pink" style="flex:1;" onclick="showToast('🔗 Invite link copied!')">Copy invite link</button>  
        <button class="btn-outline-pink" style="flex:1;" onclick="showToast('Opening share sheet…')">Share</button>  
      </div>  
    `;  
  } else if(cf.step===5){  
    body = `  
      <div class="step-q">What kind of trip is this?</div>  
      <div class="step-hint">Select all that apply</div>  
      ${TRIP_TYPES.map(tt=>`<div class="select-card ${cf.types.includes(tt.label)?'active':''}" onclick="cfToggleType('${tt.label}')">  
        <span class="emoji">${tt.emoji}</span><span class="label">${tt.label}</span><span class="check"></span>  
      </div>`).join("")}  
    `;  
  } else if(cf.step===6){  
    body = `  
      <div class="step-q">What's your budget?</div>  
      <div class="step-hint">Per person, total trip budget</div>  
      <div style="text-align:center; font-family:'Fraunces',serif; font-size:32px; margin:24px 0 10px; color:var(--hot-deep);">€${Number(cf.budget).toLocaleString()}${cf.budget>=5000?'+':''}</div>  
      <input type="range" min="200" max="5000" step="50" value="${cf.budget}" oninput="cfBudget(this.value)" style="width:100%; accent-color:var(--hot-deep);"/>  
      <div style="display:flex; justify-content:space-between; font-size:11.5px; color:var(--ink-soft); margin-top:4px;"><span>€200</span><span>€5,000+</span></div>  
    `;  
    nextLabel="Create my trip ✨";  
  }  
  
  return `  
  <div class="overlay-screen">  
    <div class="overlay-head">  
      <button class="back-btn" onclick="cfBack()">←</button>  
      <div class="progress-track">${Array.from({length:steps}).map((_,i)=>`<div class="progress-seg ${i<cf.step?'done':''}"></div>`).join("")}</div>  
      <button class="close-btn" onclick="closeCreateFlow()">✕</button>  
    </div>  
    <div class="overlay-body">${body}</div>  
    <div class="overlay-foot"><button class="btn-primary" onclick="cfNext()">${nextLabel}</button></div>  
  </div>`;  
}  
  
/* ============ EVENT DELEGATION (none needed, using inline onclick) ============ */  
function attachHandlers(){ /* inline handlers used throughout */ }  
  
/* ============ INIT ============ */  
render();  
</script>  
</body>  
</html>  
