<h1>HW4</h1>

``` swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            HStack{
                Image(systemName: "cup.and.saucer.fill")
                Text("Coffee Shop")
                    .font(.largeTitle)
                    .fontWeight(.heavy)
                    .foregroundStyle(.primary)
                Image(systemName: "cup.and.saucer.fill")
            }
            TabView{
                Group{
                    HomeView()
                        .tabItem { 
                            Image(systemName: "house")
                            Text("Home")
                        }
                    CourseListView()
                        .tabItem { 
                            Image(systemName: "list.dash")
                            Text("Menu")
                        }
                    CardView()
                        .tabItem { 
                            Image(systemName: "questionmark.app")
                            Text("Random")
                        }
                }
                .toolbarBackground(Color.black, for: .tabBar)
                .toolbarBackground(.visible, for: .tabBar)
            }
            .tint(.yellow)
        }
    }
}


//-------------------------separate line-------------------------


import SwiftUI

struct HomeView: View{
    var body: some View{
        VStack{
            Image("coffee shop")
                .resizable()
                .aspectRatio(contentMode: .fit)
            Text("In shop / straight to your home")
                .fontWeight(.heavy)
                .lineSpacing(10)
                .font(.system(size: 22))
                .foregroundStyle(.white)
                .frame(width:350, height: 50, alignment: .center)
                .background(Color.orange)
                .cornerRadius(18)
                .multilineTextAlignment(.center)
        }
    }
}


//-------------------------separate line-------------------------


import SwiftUI

struct Course:Identifiable {
    var id = UUID()
    var name:String
    var image:String
    var description:String
}

var courses = [
    Course(name:"coffee", image:"coffee", description: "xxxxxxx"),
    Course(name:"cheese burger", image:"cheese burger", description: "xxxxxxx"),
    Course(name:"french fries", image:"french fries", description: "xxxxxxx"),
    Course(name:"waffle", image:"waffle", description: "xxxxxxx"),
    Course(name:"cake", image:"cake", description: "xxxxxxx"),
    Course(name:"lemon pie", image:"lemon pie", description: "xxxxxxx"),
    Course(name:"donut", image:"donut", description: "xxxxxxx"),
    Course(name:"marcaron", image:"marcaron", description: "xxxxxxx"),
    Course(name:"juice", image:"juice", description: "xxxxxxx"),
    Course(name:"cocktail", image:"cocktail", description: "xxxxxxx")
]

struct BasicImageRow: View{
    var thisCourse:Course
    var body: some View{
        HStack{
            Image(thisCourse.image)
                .resizable()
                .frame(width:40, height: 40)
                .cornerRadius(5)
            Text(thisCourse.name)
        }
    }
}

struct CourseDetailView: View{
    @Environment(\.presentationMode) var presentationMode
    var thisCourse:Course
    var body: some View{
        ScrollView{
            VStack{
                Image(thisCourse.image)
                    .resizable()
                    .aspectRatio(contentMode: .fill)
                    .clipped()
                Text(thisCourse.name)
                    .font(.system(.title,  design: .rounded))
                    .fontWeight(.black)
                Spacer()
                Text(thisCourse.description)
                    .font(.system(.subheadline,design: .rounded))
                    .fontWeight(.light)
                Spacer()
            }
        }
        .overlay(
            HStack{
                Spacer()
                VStack{
                    Button(action:{
                        self.presentationMode.wrappedValue.dismiss()
                    },label:{
                        Image(systemName:"chevron.down.circle.fill")
                            .font(.largeTitle)
                            .foregroundColor(.white)
                    })
                    .padding(.trailing, 20)
                    .padding(.top, 40)
                    Spacer()
                }
            }
        )
    }
}

struct CourseListView: View{
    @State var showDetailView = false
    @State var selectedCourse:Course?
    var body: some View{
        NavigationView{
            List(courses){
                courseItem in BasicImageRow(thisCourse: courseItem)
                    .onTapGesture{
                        self.showDetailView = true
                        self.selectedCourse = courseItem
                    }
            }
            .sheet(item:self.$selectedCourse){
                thisCourse in CourseDetailView(thisCourse: thisCourse)
            }
            .navigationTitle("菜單列表")
        }
    }
}


```

<p><a href = "https://youtu.be/DW5lZyzQ_4Y?si=O3v1hfX653fBeuCg"</a>hw4 demo video</p>
