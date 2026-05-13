# amalgame-math

Pure-Amalgame Math facade for [Amalgame](https://github.com/amalgame-lang/Amalgame).
Constants (PI/E/TAU/SQRT2/LN2/LN10), basic functions (Sqrt/Pow/Exp/Log),
rounding, trigonometry, min/max/clamp, sign, integer math (Gcd/Lcm/
IsPrime), float checks (IsNaN/IsInf/IsFinite/ApproxEq).

Originally bundled in amc's `src/stdlib/math.am`; extracted into
this external package as part of the framework split (post-v0.7.5).
Companion package: [`amalgame-math-vec`](https://github.com/amalgame-lang/amalgame-math-vec)
ships Vec3/Vec4/Mat4 under `Amalgame.Math.Vec`.

## Install

```bash
amc package add math                 # via curated index
amc package add github.com/amalgame-lang/amalgame-math@v0.1.0
```

Requires **amc 0.7.6+** for the facade pre-compile pipeline.

## Surface

```amalgame
import Amalgame.Math

class Program {
    public static void Main() {
        Console.WriteLine(String_FromInt(Math.PowI(2, 10)))    // 1024
        Console.WriteLine(String_FromInt(Math.Gcd(48, 18)))    // 6
        let s: float = Math.Sqrt(16.0)                          // 4.0
        let t: float = Math.Sin(Math.PI() / 2.0)                // 1.0
        if (Math.IsPrime(17)) { Console.WriteLine("17 is prime") }
    }
}
```

## Tests

```bash
./tests/run_tests.sh /path/to/amc
```

## License

Apache-2.0 — see `LICENSE`. No vendored third-party code.
