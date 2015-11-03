package controllers;
import play.*;
import play.mvc.*;
import play.mvc.Http.Request;
import models.Hotel;
import models.Hotelmanager;
import models.Personal;
import views.html.user;
import views.html.empl;
import views.html.edit;
import views.html.*;
import play.data.*;
import play.data.DynamicForm;
import java.util.*;
import java.util.Date;
import java.time.LocalDate;
import static play.data.Form.*;

public class Application extends Controller {

    public Result index() {
        return ok(index.render("Your new application is ready."));
    }
    public Result Mountain_Resorts(){
        return ok( test.render());
    }
 
    public Result guestLogin(){
        return ok(user.render(Hotelmanager.getInstance().getHotels()));
    }
    public Result workLogin(){
        DynamicForm requestData = form().bindFromRequest();
         String name= requestData.get("Pname");
         String pas= requestData.get("passwort");
         
        if (name == null || name.length() <= 0) {
		return ok(test.render());
	}
	if (pas == null || pas.length() <= 0) {
		return ok(test.render());
	}
		return ok(empl.render(Hotelmanager.getInstance().getHotels()));
    }
    
     public Result Delete(){    //muss noch überarbeitet werden !!!
        return ok(delete.render(Hotelmanager.getInstance().getHotels()));
    }
    
     public Result Edit(){ 
        DynamicForm requestData = form().bindFromRequest();
        String id = requestData.get("edit");
        return ok( edit.render(Hotelmanager.getInstance().getHotel(id)));
    }
     public Result Add(){ 
        return ok( add.render());
    }
    public Result addHotel(){                       // überarbeiten sonst wie edit Hotel !!
         DynamicForm requestData = form().bindFromRequest();
         String id = requestData.get("HotlId");
         String name = requestData.get("Hotlname");
         String loc = requestData.get("HotlLoc");
         String str = requestData.get("Hotstr");
         
         Hotelmanager.getInstance().makeHotel(id,name,loc,str);
         
         return ok(add.render());
         
    }
    public Result Addroom(){
         DynamicForm requestData = form().bindFromRequest();
         String Roomtyp= requestData.get("addroomType");
         String hid=requestData.get("id");
         Hotelmanager.getInstance().getHotel(hid).addRoom(Roomtyp);
         
         return ok(test.render());
         
    }
    public Result Home(){
        return ok(test.render());
    }
    public Result Booking(){
         DynamicForm requestData = form().bindFromRequest();
         String id= requestData.get("book");
        return ok(book.render(Hotelmanager.getInstance().getHotel(id).get_all_Rooms(),Hotelmanager.getInstance().getHotel(id)));
    }
    
    public Result ChangeHotel(){
         DynamicForm requestData = form().bindFromRequest();
         String n=requestData.get("hotelname");
         String lo=requestData.get("hotelLocation");
         String st=requestData.get("hotelstreet");

         Hotelmanager.getInstance().getHotel("85068").setHotelname(n);
         Hotelmanager.getInstance().getHotel("85068").setLocation(lo);
         Hotelmanager.getInstance().getHotel("85068").setStreet(st);

         return ok(edit.render(Hotelmanager.getInstance().getHotel("85068")));
    }
    
    public Result DeleteHotel(){
        DynamicForm requestData = form().bindFromRequest();
         String id=requestData.get("Delete_num");
         Hotelmanager.getInstance().removeHotel(id);
         return ok(test.render());
         }
         
         
    
    public Result Submit(){
         DynamicForm requestData = form().bindFromRequest();
         String dSt=requestData.get("dateStart");
         String dEn=requestData.get("dateEnd");
         /*if (dst == null || dst.length() <= 0) {
		return ok(book.render(Hotelmanager.getInstance().getHotel("85068").get_all_Rooms(),Hotelmanager.getInstance().getHotel("85068")));
            }*/
            if(Hotelmanager.getInstance().getHotel("85068").checkRoom("Standard").isAvailableBetween(dSt,dEn)){
                return ok(successBook.render());
            }
         return ok(book.render(Hotelmanager.getInstance().getHotel("85068").get_all_Rooms(),Hotelmanager.getInstance().getHotel("85068")));
    }
     public Result SuccessBooking(){
        return ok(successBook.render());
    }
    
     public Result User_Mountain_Resorts(){
        return ok( user.render(Hotelmanager.getInstance().getHotels()));
    }
    public Result Empl_Mountain_Resorts(){
        return ok( empl.render(Hotelmanager.getInstance().getHotels()));
    }
    public Result Book_Mountain_Resorts(){
        return ok( book.render(Hotelmanager.getInstance().getHotel("85068").get_all_Rooms(),Hotelmanager.getInstance().getHotel("85068")));
    }
 
}
