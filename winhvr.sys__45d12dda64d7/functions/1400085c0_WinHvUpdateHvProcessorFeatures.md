# WinHvUpdateHvProcessorFeatures

- ea: `0x1400085c0`
- end: `0x140008608`
- name: `WinHvUpdateHvProcessorFeatures`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140001ef0`

## pseudocode

```c
__int64 __fastcall WinHvUpdateHvProcessorFeatures(int a1, __int64 a2)
{
  _DWORD v3[2]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v4; // [rsp+48h] [rbp-10h]

  v3[0] = a1;
  v3[1] = 0;
  v4 = a2;
  return WinHvpAllocatingHypercall(-1, 0x8000FFFF, 5, 0, v3, 0x10u, 0, 0);
}

```

## disassembly

```asm
0x1400085c0  mov     r11, rsp
0x1400085c3  sub     rsp, 58h
0x1400085c7  xor     eax, eax
0x1400085c9  mov     [rsp+58h+var_18], ecx
0x1400085cd  mov     [r11-20h], rax
0x1400085d1  xor     r9d, r9d; int
0x1400085d4  mov     [r11-28h], rax
0x1400085d8  or      rcx, 0FFFFFFFFFFFFFFFFh; int
0x1400085dc  mov     [rsp+58h+var_14], eax
0x1400085e0  lea     rax, [r11-18h]
0x1400085e4  mov     [r11-10h], rdx
0x1400085e8  mov     edx, 8000FFFFh; int
0x1400085ed  mov     qword ptr [r11-30h], 10h
0x1400085f5  lea     r8d, [r9+5]; int
0x1400085f9  mov     [r11-38h], rax
0x1400085fd  call    WinHvpAllocatingHypercall
0x140008602  add     rsp, 58h
0x140008606  retn
```
