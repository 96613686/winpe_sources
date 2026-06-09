# WinHvWithdrawAllMemoryWithCount

- ea: `0x140022af0`
- end: `0x140022b3b`
- name: `WinHvWithdrawAllMemoryWithCount`
- size: `75`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f2d0`
- `0x140022ad0`
- `0x140022bc0`
- `0x140023920`

## callees

- `0x1400231a4`

## pseudocode

```c
__int64 __fastcall WinHvWithdrawAllMemoryWithCount(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rax
  unsigned int v3; // ecx
  __int64 result; // rax
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  v2 = &v5;
  v5 = 0;
  if ( a2 )
    v2 = a2;
  v3 = WinHvpWithdrawMemory(a1, 0xFFFFFFFFFFFFFFFFuLL, 0x80000000, 0, v2, 0);
  result = 0;
  if ( v3 != -1070268387 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x140022af0  mov     r11, rsp
0x140022af3  sub     rsp, 38h
0x140022af7  test    rdx, rdx
0x140022afa  mov     qword ptr [r11-10h], 0
0x140022b02  lea     rax, [r11+10h]
0x140022b06  mov     qword ptr [r11+10h], 0
0x140022b0e  cmovnz  rax, rdx
0x140022b12  mov     r8d, 80000000h
0x140022b18  xor     r9d, r9d
0x140022b1b  mov     [r11-18h], rax
0x140022b1f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140022b23  call    WinHvpWithdrawMemory
0x140022b28  mov     ecx, eax
0x140022b2a  xor     eax, eax
0x140022b2c  cmp     ecx, 0C035001Dh
0x140022b32  cmovnz  eax, ecx
0x140022b35  add     rsp, 38h
0x140022b39  retn
```
