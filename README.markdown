# Multibody XML

A language for describing a physical multibody scene, including the actual bodies and their interactions.

There have already been many attempts to make such declarative language for physics, such as [X3D](http://www.web3d.org/x3d/), [COLLADA](https://collada.org/) and [OPAL](http://opal.sourceforge.net/). None of them are complete from a physics simulation perspective and they are hard to extend. So here comes our attempt to fix.

## Sample
See all samples in the [samples/ folder](https://github.com/schteppe/multibody-xml/tree/master/samples).

```
<multiBodySystem>

  <head>
    <title>Ball on plane 2D</title>
    <description>A simple scene with a ball on a plane.</description>
    <author>Stefan Hedman</author>
    <company>UMIT Research Lab</company>
    <time>2012-04-02T14:11:00</time>
    <units>si</units>
  </head>

  <cartesian2dSystem>
    <rigidBody>
      <coordinates position="0 0" orientation="0"/>
      <velocities angular="1" linear="10 0"/>
    </rigidBody>

    <rigidBody state="static">
      <coordinates transform="1 0 0
                              0 1 0
                              0 0 1"/>
      <velocities linear="10 0"/>
    </rigidBody>
  </cartesian2dSystem>

  <stepper>
    <param name="solver" value="nlgs"/>
    <param name="iterations" value="10"/>
  </stepper>

</multiBodySystem>
```