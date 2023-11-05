<h1>hw2</h1>
<table>
  <tr>
    <td>
      <img src="https://raw.githubusercontent.com/ldhejlvfl/yzu-swiftui-1101412/main/hw2_1101412.gif" style="width: 300px; height: 600px;">
    </td>
    <td>
        ```swift
      
        import SwiftUI

        struct ContentView: View {
          @State var random_num:Int = 0
          @State var move:String = ""
          @State var img:String = ""
          var body: some View{
            VStack{
              Image(img)
                  .resizable()
                  .frame(width:300, height:300)
              Text(String(move))
                  .padding(.all, 10)
                  .font(.system(size:100))
              Button(action:{
                   random_num = Int.random(in: 0...2)
                  if(random_num==0){
                      move = "剪刀"
                      img = "scissors"
                  }
                  else if(random_num==1){
                      move = "石頭"
                      img = "rock"
                  }
                  else{
                      move = "布"
                      img = "paper"
                  }
              }, label:{
                  Text("Go")
                      .padding(.all, 10)
                      .font(.system(size:50))
                      .background(Color.blue)
                      .foregroundColor(Color.white)
                      .border(Color.blue, width:5)
                      .cornerRadius(20)
              })
          }
        }
    }  

      ```
  </td>
  </tr>
</table>
