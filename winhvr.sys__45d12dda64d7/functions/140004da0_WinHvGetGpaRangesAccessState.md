# WinHvGetGpaRangesAccessState

- ea: `0x140004da0`
- end: `0x140004e33`
- name: `WinHvGetGpaRangesAccessState`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvGetGpaRangesAccessState(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int64 a5,
        char *a6,
        _QWORD *a7)
{
  _QWORD v8[2]; // [rsp+80h] [rbp-28h] BYREF
  __int64 v9; // [rsp+90h] [rbp-18h] BYREF
  int v10; // [rsp+98h] [rbp-10h]
  int v11; // [rsp+9Ch] [rbp-Ch]

  v8[1] = a2;
  v9 = a3;
  v8[0] = a1;
  v10 = a4;
  v11 = 0;
  return WinHvpSpecialListRepHypercall(
           258,
           a5,
           v8,
           0x20u,
           &v9,
           1LL << (9 * (unsigned __int8)a4),
           0,
           0,
           0,
           0,
           a6,
           1u,
           0,
           0,
           a7);
}

```

## disassembly

```asm
0x140004da0  mov     r11, rsp
0x140004da3  sub     rsp, 0A8h
0x140004daa  mov     rax, [rsp+0A8h+arg_30]
0x140004db2  xor     r10d, r10d
0x140004db5  mov     [r11-38h], rax
0x140004db9  mov     rax, [rsp+0A8h+arg_28]
0x140004dc1  mov     [r11-40h], r10
0x140004dc5  mov     [r11-48h], r10
0x140004dc9  mov     [r11-20h], rdx
0x140004dcd  mov     [r11-18h], r8
0x140004dd1  lea     r8d, [r10+1]
0x140004dd5  mov     [r11-50h], r8d
0x140004dd9  mov     edx, r8d
0x140004ddc  mov     [r11-58h], rax
0x140004de0  lea     r8, [r11-28h]
0x140004de4  mov     [r11-60h], r10
0x140004de8  lea     rax, [r11-18h]
0x140004dec  mov     [r11-68h], r10
0x140004df0  mov     [r11-70h], r10d
0x140004df4  mov     [r11-28h], rcx
0x140004df8  lea     ecx, [r9+r9*8]
0x140004dfc  shl     rdx, cl
0x140004dff  mov     ecx, 102h
0x140004e04  mov     [r11-78h], r10
0x140004e08  mov     [r11-80h], rdx
0x140004e0c  mov     rdx, [rsp+0A8h+arg_20]
0x140004e14  mov     [r11-10h], r9d
0x140004e18  lea     r9d, [r10+20h]
0x140004e1c  mov     [r11-0Ch], r10d
0x140004e20  mov     [rsp+0A8h+var_88], rax
0x140004e25  call    WinHvpSpecialListRepHypercall
0x140004e2a  add     rsp, 0A8h
0x140004e31  retn
```
