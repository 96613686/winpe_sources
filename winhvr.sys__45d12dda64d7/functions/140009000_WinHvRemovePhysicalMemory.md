# WinHvRemovePhysicalMemory

- ea: `0x140009000`
- end: `0x14000901e`
- name: `WinHvRemovePhysicalMemory`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140022bc0`

## pseudocode

```c
__int64 __fastcall WinHvRemovePhysicalMemory(char a1, __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  __int64 v5; // r8

  v5 = a2;
  LOBYTE(a2) = a1;
  return WinHvpAddRemovePhysicalMemory(0, a2, v5, a3, a4);
}

```

## disassembly

```asm
0x140009000  sub     rsp, 38h
0x140009004  mov     [rsp+38h+var_18], r9
0x140009009  mov     r9, r8
0x14000900c  mov     r8, rdx
0x14000900f  mov     dl, cl
0x140009011  xor     ecx, ecx
0x140009013  call    WinHvpAddRemovePhysicalMemory
0x140009018  add     rsp, 38h
0x14000901c  retn
```
