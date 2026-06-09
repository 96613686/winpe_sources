# WinHvInstallIntercept

- ea: `0x140025ed0`
- end: `0x140025f25`
- name: `WinHvInstallIntercept`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140001ef0`

## pseudocode

```c
__int64 __fastcall WinHvInstallIntercept(__int64 a1, int a2, int *a3)
{
  int v3; // eax
  __int64 v4; // rax
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+4Ch] [rbp-1Ch]
  __int64 v9; // [rsp+50h] [rbp-18h]

  v3 = *a3;
  v6 = a1;
  v8 = v3;
  v4 = *((_QWORD *)a3 + 1);
  v7 = a2;
  v9 = v4;
  return WinHvpAllocatingHypercall(a1, 0x8000FFFF, 77, 0, &v6, 0x18u, 0, 0);
}

```

## disassembly

```asm
0x140025ed0  mov     r11, rsp
0x140025ed3  sub     rsp, 68h
0x140025ed7  mov     eax, [r8]
0x140025eda  xor     r9d, r9d; int
0x140025edd  mov     qword ptr [r11-30h], 0
0x140025ee5  mov     [r11-28h], rcx
0x140025ee9  mov     [rsp+68h+var_1C], eax
0x140025eed  mov     rax, [r8+8]
0x140025ef1  lea     r8d, [r9+4Dh]; int
0x140025ef5  mov     [rsp+68h+var_20], edx
0x140025ef9  mov     edx, 8000FFFFh; int
0x140025efe  mov     qword ptr [r11-38h], 0
0x140025f06  mov     [r11-18h], rax
0x140025f0a  lea     rax, [r11-28h]
0x140025f0e  mov     qword ptr [r11-40h], 18h
0x140025f16  mov     [r11-48h], rax
0x140025f1a  call    WinHvpAllocatingHypercall
0x140025f1f  add     rsp, 68h
0x140025f23  retn
```
