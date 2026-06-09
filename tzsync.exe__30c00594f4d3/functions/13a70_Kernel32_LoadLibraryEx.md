# Kernel32::LoadLibraryEx

- ea: `0x13a70`
- end: `0x13a8d`
- name: `Kernel32::LoadLibraryEx`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x13540`
- `0x153d0`

## callees

- `0xe70`
- `0x13a70`
- `0x15390`

## pseudocode

```c

```

## disassembly

```asm
0x13a70  ldarg.0
0x13a71  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x13a76  ldarg.1
0x13a77  call     class SafeLibraryHandle NativeMethods::LoadLibraryExW(string lpLibFileName, native int hFile, valuetype LOAD_LIBRARY_EX_FLAGS dwFlags)
0x13a7c  stloc.0
0x13a7d  ldloc.0
0x13a7e  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x13a83  brfalse.s loc_13A8B
0x13a85  newobj   instance void Microsoft.Internal.PInvoke.Util.Win32Error::.ctor()
0x13a8a  throw
0x13a8b  ldloc.0
0x13a8c  ret
```
