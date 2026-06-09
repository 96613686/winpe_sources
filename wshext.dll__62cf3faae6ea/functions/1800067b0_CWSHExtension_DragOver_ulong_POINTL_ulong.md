# CWSHExtension::DragOver(ulong,_POINTL,ulong *)

- ea: `0x1800067b0`
- end: `0x1800067ba`
- name: `?DragOver@CWSHExtension@@UEAAJKU_POINTL@@PEAK@Z`
- size: `10`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall CWSHExtension::DragOver(CWSHExtension *this, __int64 a2, struct _POINTL a3, unsigned int *a4)
{
  *a4 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800067b0  mov     dword ptr [r9], 1
0x1800067b7  xor     eax, eax
0x1800067b9  retn
```
