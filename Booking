package models;
import java.util.Date;

public class Booking {
    private static int lastId;
    private int roomNumber;
    private String roomType;
    private String startTime; // use date category 
    private String endTime;
    private final int Id;

    public Booking (int roomNumber,  String roomType, String startTime, String endTime) {//wege Date nachschaun
        this.roomNumber = roomNumber;
        this.roomType = roomType;
        this.startTime = startTime;
        this.endTime = endTime;
        Id = ++lastId;
    }

    public long getId() {
        return Id;
    }
    public int getRoomNumber() {
        return roomNumber;
    }
    public String getRoomType() {
        return roomType;
    }
    public String getStartTime() {
        return startTime;
    }
    public String getEndTime() {
        return endTime;
    }
	
}
