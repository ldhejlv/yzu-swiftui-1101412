<h1>hw1</h1>
<table>
  <tr>
    <td>
      <img src="https://raw.githubusercontent.com/ldhejlv/yzu-swiftui-1101412/main/screenshot 2023-10-02 13.50.01.jpg">
    </td>
    <td>
      ```
      
      import SwiftUI
      struct ContentView: View {
          var body: some View {
              Image("Image")
                  .resizable()
                  .aspectRatio(contentMode: .fill)
                  .overlay( 
                      Text("原神，啟動！\n我最喜歡玩原神了")
                          .fontWeight(.heavy)
                          .lineSpacing(20)
                          .font(.system(size:32.0))
                          .foregroundColor(.white)
                          .frame(width:350,height:150, alignment: .center)
                          .background(Color.blue)
                          .cornerRadius(30.0)
                          .opacity(0.8)
                      ,
                      alignment: .bottom
                  )
              
          }
      }
      
      ```
    </td>
  </tr>
</table>
