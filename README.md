# TubeInsulatorManagement
package com.mycompany.tubeinsulatormanagement;

public class TubeInsulator {

    private Tube tube;
    private Insulator insulator;

    private Cork leftCork;
    private Cork rightCork;

    public Tube getTube() {
        return tube;
    }

    public void setTube(Tube tube) {
        this.tube = tube;
    }

    public Insulator getInsulator() {
        return insulator;
    }

    public void setInsulator(Insulator insulator) {
        this.insulator = insulator;
    }

    public Cork getLeftCork() {
        return leftCork;
    }

    public void setLeftCork(Cork leftCork) {
        this.leftCork = leftCork;
    }

    public Cork getRightCork() {
        return rightCork;
    }

    public void setRightCork(Cork rightCork) {
        this.rightCork = rightCork;
    }

    public TubeInsulator(double tubeRadius, double tubeHeight, double insulatorRadius, double insulatorHeight) {
        tube = new Tube(tubeRadius, tubeHeight);
        insulator = new Insulator(tubeRadius, tubeHeight, insulatorRadius, insulatorHeight);
        double leftCorkHeight = ((tubeHeight - insulatorHeight) / 2);
        double rightCorkHeight = ((tubeHeight - insulatorHeight) / 2);
        leftCork = new Cork(tubeRadius, leftCorkHeight);
        rightCork = new Cork(tubeRadius, rightCorkHeight);
    }

    public double getLeftCorkCapacity() {
        return leftCork.getCorkCapacity();
    }

    public double getRightCorkCapacity() {
        return rightCork.getCorkCapacity();
    }

    public double getTubeFillingCapacity() {
        return tube.getTubeCapacity() - leftCork.getCorkCapacity() - rightCork.getCorkCapacity();
    }

    public double getInsulationVolume() {
        return insulator.getOuterBoundryCapacity();
    }

}
package com.mycompany.tubeinsulatormanagement;

public class TubeInsulator {

    private Tube tube;
    private Insulator insulator;

    private Cork leftCork;
    private Cork rightCork;

    public Tube getTube() {
        return tube;
    }

    public void setTube(Tube tube) {
        this.tube = tube;
    }

    public Insulator getInsulator() {
        return insulator;
    }

    public void setInsulator(Insulator insulator) {
        this.insulator = insulator;
    }

    public Cork getLeftCork() {
        return leftCork;
    }

    public void setLeftCork(Cork leftCork) {
        this.leftCork = leftCork;
    }

    public Cork getRightCork() {
        return rightCork;
    }

    public void setRightCork(Cork rightCork) {
        this.rightCork = rightCork;
    }

    public TubeInsulator(double tubeRadius, double tubeHeight, double insulatorRadius, double insulatorHeight) {
        tube = new Tube(tubeRadius, tubeHeight);
        insulator = new Insulator(tubeRadius, tubeHeight, insulatorRadius, insulatorHeight);
        double leftCorkHeight = ((tubeHeight - insulatorHeight) / 2);
        double rightCorkHeight = ((tubeHeight - insulatorHeight) / 2);
        leftCork = new Cork(tubeRadius, leftCorkHeight);
        rightCork = new Cork(tubeRadius, rightCorkHeight);
    }

    public double getLeftCorkCapacity() {
        return leftCork.getCorkCapacity();
    }

    public double getRightCorkCapacity() {
        return rightCork.getCorkCapacity();
    }

    public double getTubeFillingCapacity() {
        return tube.getTubeCapacity() - leftCork.getCorkCapacity() - rightCork.getCorkCapacity();
    }

    public double getInsulationVolume() {
        return insulator.getOuterBoundryCapacity();
    }

}
package com.mycompany.tubeinsulatormanagement;

public class TubeInsulator {

    private Tube tube;
    private Insulator insulator;

    private Cork leftCork;
    private Cork rightCork;

    public Tube getTube() {
        return tube;
    }

    public void setTube(Tube tube) {
        this.tube = tube;
    }

    public Insulator getInsulator() {
        return insulator;
    }

    public void setInsulator(Insulator insulator) {
        this.insulator = insulator;
    }

    public Cork getLeftCork() {
        return leftCork;
    }

    public void setLeftCork(Cork leftCork) {
        this.leftCork = leftCork;
    }

    public Cork getRightCork() {
        return rightCork;
    }

    public void setRightCork(Cork rightCork) {
        this.rightCork = rightCork;
    }

    public TubeInsulator(double tubeRadius, double tubeHeight, double insulatorRadius, double insulatorHeight) {
        tube = new Tube(tubeRadius, tubeHeight);
        insulator = new Insulator(tubeRadius, tubeHeight, insulatorRadius, insulatorHeight);
        double leftCorkHeight = ((tubeHeight - insulatorHeight) / 2);
        double rightCorkHeight = ((tubeHeight - insulatorHeight) / 2);
        leftCork = new Cork(tubeRadius, leftCorkHeight);
        rightCork = new Cork(tubeRadius, rightCorkHeight);
    }

    public double getLeftCorkCapacity() {
        return leftCork.getCorkCapacity();
    }

    public double getRightCorkCapacity() {
        return rightCork.getCorkCapacity();
    }

    public double getTubeFillingCapacity() {
        return tube.getTubeCapacity() - leftCork.getCorkCapacity() - rightCork.getCorkCapacity();
    }

    public double getInsulationVolume() {
        return insulator.getOuterBoundryCapacity();
    }

}package com.mycompany.tubeinsulatormanagement;

public class Tube {

    private Cylinder cylinder;

    public Tube(double radius, double height) {
        cylinder = new Cylinder(radius, height);
    }

    public double getTubeCapacity() {
        return cylinder.getCylinderVolume();
    }

    public double getTubeRadius() {
        return cylinder.getRadius();
    }

    public double getTubeHeight() {
        return cylinder.getHeight();
    }

}
package com.mycompany.tubeinsulatormanagement;

public class Operations {

    public static double getGlycerineCapacity(double capacity) {
        return capacity * Dencity.glycerineDencity;
    }

    public static double getWoodenDustCapacity(double capacity) {
        return capacity * Dencity.woodenDust;
    }

}package com.mycompany.tubeinsulatormanagement;

public class Insulator {

    private Cylinder tunnel;
    private Cylinder outerBoundry;

    public Insulator(double tunnelRadius, double tunnelHeight, double totalRadius, double totalHeight) {
        tunnel = new Cylinder(tunnelRadius, tunnelHeight);
        outerBoundry = new Cylinder(totalRadius, totalHeight);
    }

    public double getTunnelCapacity() {
        return tunnel.getCylinderVolume();
    }

    public double getOuterBoundryCapacity() {
        return outerBoundry.getCylinderVolume() - getTunnelCapacity();
    }

    public double getTunnelRadius() {
        return tunnel.getRadius();
    }

    public double getTunnelHeight() {
        return tunnel.getHeight();
    }

    public double getOuterBoundryRadius() {
        return outerBoundry.getRadius();
    }

    public double getOuterBoundryHeight() {
        return outerBoundry.getHeight();
    }

    public double getInsulationRadius() {
        return outerBoundry.getRadius() - tunnel.getRadius();
    }

    public double getInsulationHeight() {
        return outerBoundry.getHeight();
    }

}
package com.mycompany.tubeinsulatormanagement;

public class Estimator {

    public static void printTubeInsulation(TubeInsulator tubeInsulator) {
        System.out.println(" ============= Property Description ============= \n");
        System.out.println("Tube Radius " + tubeInsulator.getTube().getTubeRadius());
        System.out.println("Tube Height " + tubeInsulator.getTube().getTubeHeight());
        System.out.println("Insulator Radius " + tubeInsulator.getInsulator().getInsulationRadius());
        System.out.println("Insulator Height " + tubeInsulator.getInsulator().getInsulationHeight());
        System.out.println("Left Cork Height " + tubeInsulator.getLeftCork().corkCylinder.getHeight());
        System.out.println("Left Cork Radius " + tubeInsulator.getLeftCork().corkCylinder.getRadius());
        System.out.println("Right Cork Height " + tubeInsulator.getRightCork().corkCylinder.getHeight());
        System.out.println("Right Cork Radius " + tubeInsulator.getRightCork().corkCylinder.getRadius());

        System.out.println(" ============= Capacity Description =============  \n");
        System.out.println("Tube Filling Capacity "+tubeInsulator.getTubeFillingCapacity());
        System.out.println("Insulation Area Volume "+tubeInsulator.getInsulationVolume());
        System.out.println("Left Cork Capacity "+tubeInsulator.getLeftCorkCapacity());
        System.out.println("Right Cork Capacity "+tubeInsulator.getRightCorkCapacity());
        System.out.println("Glycerine Weight "+Operations.getGlycerineCapacity(tubeInsulator.getTubeFillingCapacity()));
        System.out.println("Dust Weight "+Operations.getWoodenDustCapacity(tubeInsulator.getTubeFillingCapacity()));
    }
}
package com.mycompany.tubeinsulatormanagement;

public class Dencity {

    final public static double glycerineDencity = 1.26;
    final public static double woodenDust = 0.3556;

package com.mycompany.tubeinsulatormanagement;

import static java.lang.Math.PI;

public class Cylinder {

    private double radius;
    private double height;

    public Cylinder(double radius, double height) {
        this.radius = radius;
        this.height = height;
    }

    public double getRadius() {
        return radius;
    }

    public void setRadius(double radius) {
        this.radius = radius;
    }

    public double getHeight() {
        return height;
    }

    public void setHeight(double height) {
        this.height = height;
    }

    public double getCylinderVolume() {
        return PI * radius * radius * height;
    }

}
package com.mycompany.tubeinsulatormanagement;

public class Cork {

    public Cylinder corkCylinder;

    public Cork(double radius, double height) {
        corkCylinder = new Cylinder(radius, height);
    }

    public double getCorkCapacity() {
        return corkCylinder.getCylinderVolume();
   }

}







