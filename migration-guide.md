akka-kryo-serialization - migration guide
=====================================================================

Migration from 0.5.x/0.6.x to 1.0.x
-----------------------------------

* Move serializer configuration from `akka.actor.kryo` to `akka-kryo-serialization`
* Change akka serialization configuration to the new package name: 
    ```hocon
    akka {
      extensions = ["io.altoo.akka.serialization.kryo.KryoSerializationExtension$"]
      actor {
        serializers {
          kryo = "io.altoo.akka.serialization.kryo.KryoSerializer"
        }
      }
    }
    ```
* If you were using the scala serializers independently adapt imports from `com.romix.scala.serialization.kryo` to `io.altoo.akka.serialization.kryo.serializer.scala`