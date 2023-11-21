<h1>hw1</h1>

```swift

import SwiftUI
  
  struct ContentView: View {
    var body: some View {
    Image("IMG_7683")
      .resizable()
      .aspectRatio(contentMode: .fill)
      .overlay(
          Image(systemName: "battery.25")
              .font(.system(size:40))
              .foregroundColor(.black)
              .opacity(0.75)
              .frame(width:180, height:60, alignment:.centerLastTextBaseline)
          ,
          alignment: .topTrailing
      )
      .overlay(
          Text("1101412  李東樺\n月底又要吃土了:(")
              .fontWeight(.heavy)
              .lineSpacing(15)
              .font(.system(size:24))
              .foregroundColor(.black)
              .frame(width:320, height:100
                     , alignment:.center)
              .background(Color.gray)
              .cornerRadius(35)
              .opacity(0.85)
          ,
          alignment: .bottom
      )
  
  }
}
  
```

<img width="40%" src="https://raw.githubusercontent.com/ldhejlvfl/yzu-swiftui-1101412/main/hw1_1101412.jpg">
