# Unit-6-Tutorial-Cube

Name : Vanessa
Partner : Cherry

#Cube class 
public class Cube {
    private int side;

    public Cube(){
        side = 1;
    }

    public Cube(int side){
        this.side = side;
    }

    public int getSide(){return side;}

    public int setSide(int side){return side;}

    public int getSurfaceArea(){ return 6*side*side; }

    public int getVolume(){return side*side*side;}

    public String toString(){ return "Cube{side ="+side+"}";}
}

#CubeTester class
import org.junit.Test;
import static org.junit.Assert.assertThrows;
import static org.junit.Assert.assertTrue;

public class CubeTester {
    @Test
    public void TestNoArgumentConstructorNoException() {
        Cube cube = new Cube();
        assertTrue("Ensure that your no argument constructor has been implemented correctly!", cube.getSide() == 1);
    }

    @Test
    public void TestSingleArgumentConstructorNoException() {
        Cube cube = new Cube(5);
        assertTrue("Ensure that your single argument constructor has been implemented correctly!", cube.getSide() == 5);
    }

    @Test
    public void TestSingleArgumentConstructorNegative() {
        Throwable exception = assertThrows(IllegalArgumentException.class, ()->{ new Cube(-1);});
    }

    @Test
    public void TestSingleArgumentConstructorZero() {
        Throwable exception = assertThrows(IllegalArgumentException.class, ()->{ new Cube(0);});
    }

    @Test
    public void TestSetter() {
        Cube cube = new Cube(5);
        cube.setSide(7);
        assertTrue("Ensure that your setter method has been implemented correctly!", cube.getSide() == 7);
    }

    @Test
    public void TestSetterNegative() {
        Cube cube = new Cube(5);
        Throwable exception = assertThrows(IllegalArgumentException.class, ()->{ cube.setSide(-1);});
    }

    @Test
    public void TestSetterZero() {
        Cube cube = new Cube(5);
        Throwable exception = assertThrows(IllegalArgumentException.class, ()->{ cube.setSide(0);});
    }

    @Test
    public void TestVolume() {
        Cube cube = new Cube(5);
        int volume = cube.getVolume();
        assertTrue("Ensure that your getVolume method has been implemented correctly!", volume == 125);
    }

    @Test
    public void TestVolumeTwo() {
        Cube cube = new Cube(7);
        int volume = cube.getVolume();
        assertTrue("Ensure that your getVolume method has been implemented correctly!", volume == 343);
    }

    @Test
    public void TestSurfaceArea() {
        Cube cube = new Cube(5);
        int surfaceArea = cube.getSurfaceArea();
        assertTrue("Ensure that your getSurfaceArea method has been implemented correctly!", surfaceArea == 150);
    }

    @Test
    public void TestSurfaceAreaTwo() {
        Cube cube = new Cube(7);
        int surfaceArea = cube.getSurfaceArea();
        assertTrue("Ensure that your getSurfaceArea method has been implemented correctly!", surfaceArea == 294);
    }
}
