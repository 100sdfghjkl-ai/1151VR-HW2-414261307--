一、 專案建立與場景佈置
在 Unity 中開啟一個 2D 專案，並載入準備好的 2D 人物圖片至場景中。   
利用 2D Object 建立長條形的地板物件（Square）與終點物件（紅色 Triangle），並放置於場景中適當的位置。
將地板物件的 Tag 設定為 Ground，並將紅色三角形的 Tag 設定為 Finish，以便後續的程式邏輯能正確識別目標。
二、 物理系統與碰撞設定
玩家角色 (Player)：在 Inspector 中新增 Rigidbody 2D 元件，並在 Constraints 勾選 Freeze Rotation Z（防止角色滾動傾倒）。接著新增 Box Collider 2D 提供邊界碰撞。
地形 (Ground)：為地板新增 Box Collider 2D，確保角色能確實踩踏。
終點 (Finish)：為紅色三角形新增 Polygon Collider 2D，並務必勾選 Is Trigger，使其變為觸發區域，讓人物碰到時不會被物理反彈卡住。
三、 程式實作與作業要求
在玩家物件上掛載 PlayerPath.cs 腳本，透過以下邏輯達成「往前走、上跳並下跳到終點」的目標：   
陣列與 Vector 的應用：宣告 Vector3[] checkpoints 陣列來記錄玩家的起始與終點座標，並使用 Vector2 處理移動方向與跳躍力道，滿足作業必須使用 vector 和陣列的功能規定。
WASD 控制：擷取 Input.GetAxis("Horizontal") 數值推動 Rigidbody2D.velocity 實作 A/D 鍵移動；按下 W 鍵且 isGrounded 為 true 時執行上跳。
下跳穿透機制：按下 S 鍵時呼叫協程（Coroutine），短暫使用 Physics2D.IgnoreCollision 關閉玩家與當前地板的碰撞，達到下跳穿過地板的效果。   
