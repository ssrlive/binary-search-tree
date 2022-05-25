
# 平衡二叉樹

搜遍網絡找不到可用的 平衡二叉樹 的 C 語言實現。

於是自己寫了一個。

性能強勁，代碼簡潔、健壯。產品級工業水準通用性代碼構建。

# 節點刪除

平衡二叉樹的節點刪除比較複雜。具體步驟爲

找到試圖刪除的 *目標節點* ，比較左右兩個子樹的高度,找出最高樹，
如果是 *左子樹* 高些，就找出左子樹的 *最大節點* ，命名爲 *替換節點* ；
同時記下這個節點的父節點，命名爲上溯節點。

用 *替換節點* 取代 *目標節點* ，然後從 *上溯節點* 開始進行平衡性質檢查，
如果發現某節點的 *平衡因子* 爲 ±2，則進行 左左 右右 右左 左右 四種方式之一的
旋轉，完成以後 再檢查，再上溯，直到 根節點，纔算完畢。

（有人曾說過只要上溯到父子孫連續三個節點的平衡因子都爲0時，整個樹就算平衡了，
可以提前跳出，我沒有試過，不知真假）

如果是 *右子樹* 高些，就找出右子樹的 *最小節點* 進行替換，其餘操作與 *左子樹* 類似。

由於 平衡二叉樹 的刪除操作這麼複雜 —— 比 *紅黑樹* 複雜 —— 性能還比 *紅黑樹* 差，
沒幾人願意碰這玩意兒， 因此產品級的強悍通用代碼 網上找不到，
老夫不才，閒得蛋疼，就寫了一個，也算是查漏補缺吧，耗時兩天。


![img](https://user-images.githubusercontent.com/30760636/170172988-37879984-88c8-4711-bd65-308a2219692c.png)

