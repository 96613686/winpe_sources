# NativeHelper::GetWindowsFunction

- ea: `0x137c0`
- end: `0x13850`
- name: `NativeHelper::GetWindowsFunction`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x137c0`

## string_xrefs

- `0x13804`: `AddDllDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x137c0  ldtoken  [mscorlib]System.Delegate
0x137c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137ca  ldtoken  mvar<u1>
0x137cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137d4  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x137d9  brtrue.s loc_137F0
0x137db  ldtoken  mvar<u1>
0x137e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137e5  callvirt instance string [mscorlib]System.Type::get_FullName()
0x137ea  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x137ef  throw
0x137f0  ldarg.0
0x137f1  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x137f6  ldstr    aKernel32// "Kernel32"
0x137fb  ldc.i4.5
0x137fc  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x13801  brfalse.s loc_13811
0x13803  ldarg.1
0x13804  ldstr    aAdddlldirector// "AddDllDirectory"
0x13809  ldc.i4.5
0x1380a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1380f  brtrue.s loc_13818
0x13811  ldc.i4   0x800
0x13816  br.s     loc_13819
0x13818  ldc.i4.0
0x13819  stloc.0
0x1381a  ldarg.0
0x1381b  ldloc.0
0x1381c  ldarg.1
0x1381d  call     T0x2B000047
0x13822  stloc.1
0x13823  leave.s  loc_1384E
0x13825  isinst   [mscorlib]System.Exception
0x1382a  dup
0x1382b  brtrue.s loc_13831
0x1382d  pop
0x1382e  ldc.i4.0
0x1382f  br.s     loc_1383F
0x13831  isinst   [mscorlib]System.ArgumentException
0x13836  ldnull
0x13837  cgt.un
0x13839  ldc.i4.0
0x1383a  ceq
0x1383c  ldc.i4.0
0x1383d  cgt.un
0x1383f  endfilter
0x13841  pop
0x13842  ldloca.s 2
0x13844  initobj  mvar<u1>
0x1384a  ldloc.2
0x1384b  stloc.1
0x1384c  leave.s  loc_1384E
0x1384e  ldloc.1
0x1384f  ret
```
