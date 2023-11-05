<h1>hw3</h1>
<table>
  <tr>
    <td>
      <img src="https://raw.githubusercontent.com/ldhejlvfl/yzu-swiftui-1101412/main/hw3_1101412.jpg" style="width: 300px; height: 600px;">
    </td>
    <td>
      ```swift
      
        import SwiftUI

        struct ContentView: View {
            var body: some View {
                TitleView()
                ZStack{
                    PlayerView(imageName:"curry")
                    Text("Let's Go Warriors~~")
                        .font(.system(size:13))
                        .foregroundColor(Color(red:245/255,green:228/255,blue:72/255))
                        .padding(.all, 3)
                        .background(Color(red:49/255,green:63/255,blue:173/255))
                        .opacity(0.85)
                        .offset(x:90, y:15)
                }
                HStack{
                    PlayerView(imageName: "green")
                    PlayerView(imageName: "wiggins")
                }
                HStack{
                    PlayerView(imageName: "klay")
                    PlayerView(imageName: "looney")
                    PlayerView(imageName: "cp3")
                }
                HStack{
                    PlayerView(imageName: "gp2")
                    PlayerView(imageName: "kuminga")
                    PlayerView(imageName: "moody")
                }
            }
        }
        
        struct TitleView: View {
            var body: some View {
                VStack(alignment:.center, spacing:2) {
                    Text("Team Warriors")
                        .font(.system(size:40))
                        .foregroundColor(.white)
                        .fontWeight(/*@START_MENU_TOKEN@*/.bold/*@END_MENU_TOKEN@*/)
                    Text("2024")
                        .font(.system(size:30))
                        .foregroundColor(.white)
                        .fontWeight(/*@START_MENU_TOKEN@*/.bold/*@END_MENU_TOKEN@*/)
                }
            }
        }
        
        struct PlayerView: View {
            var imageName:String
            var body: some View {
                VStack {
                    Image(imageName)
                        .resizable()
                        .aspectRatio(contentMode:.fit)
                        .frame(width:120, alignment: .center)
                        .cornerRadius(10.0)
                    Text(imageName.capitalized)
                        .fontWeight(.bold)
                        .font(.system(size:20))
                        .foregroundColor(.gray)
                }.padding(.all, 1)
        //            .frame(minWidth:0, idealWidth: 120,
        //                   maxWidth: .infinity,minHeight: 0,
        //                   idealHeight: 100,maxHeight: .infinity,
        //                   alignment: .center)
            }
        }
        
        //extension UIScreen{
        //    static let screenWidth = UIScreen.main.bounds.size.width
        //    static let screenHeight = UIScreen.main.bounds.size.height
        //    static let screenSize = UIScreen.main.bounds.size
        //}

    ```
  </td>
  </tr>
</table>
