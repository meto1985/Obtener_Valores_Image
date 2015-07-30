package CODIGO;

import java.awt.image.BufferedImage;
import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;
import com.sun.org.apache.xerces.internal.impl.dv.util.Base64;

public class HU {

    public static void main(String[] args) throws IOException {

        String dirName = "C:\\";
        ByteArrayOutputStream baos = new ByteArrayOutputStream(1000);
        BufferedImage img = ImageIO.read(new File(dirName, "FigurasBlancas.bmp"));
        ImageIO.write(img, "bmp", baos);
        baos.flush();

        String base64String = Base64.encode(baos.toByteArray());
        baos.close();

        byte[] bytearray = Base64.decode(base64String);

        for (int i = 0; i < bytearray.length; i++) {
            System.out.println(bytearray[i] + ",");

        }
    }
}
