# WinHvAcquireSparseSpaPageHostAccess

- ea: `0x140004c40`
- end: `0x140004cb7`
- name: `WinHvAcquireSparseSpaPageHostAccess`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvAcquireSparseSpaPageHostAccess(char a1, int a2, unsigned __int64 a3, char *a4, _QWORD *a5)
{
  _DWORD v6[2]; // [rsp+80h] [rbp-18h] BYREF
  __int64 v7; // [rsp+88h] [rbp-10h]

  v6[1] = a2;
  v6[0] = a1 & 3;
  v7 = 0;
  return WinHvpSpecialListRepHypercall(215, a3, v6, 0x10u, 0, 0, a4, 8u, 0, 0, 0, 0, 0, 0, a5);
}

```

## disassembly

```asm
0x140004c40  mov     r11, rsp
0x140004c43  sub     rsp, 98h
0x140004c4a  mov     al, cl
0x140004c4c  mov     [r11-14h], edx
0x140004c50  mov     r10, r8
0x140004c53  and     eax, 3
0x140004c56  xor     r8d, r8d
0x140004c59  mov     [r11-18h], eax
0x140004c5d  mov     rax, [rsp+98h+arg_20]
0x140004c65  mov     rdx, r10
0x140004c68  mov     [r11-28h], rax
0x140004c6c  mov     ecx, 0D7h
0x140004c71  mov     [r11-30h], r8
0x140004c75  mov     [r11-38h], r8
0x140004c79  mov     [r11-40h], r8d
0x140004c7d  mov     [r11-48h], r8
0x140004c81  mov     [r11-50h], r8
0x140004c85  mov     [r11-58h], r8
0x140004c89  mov     [rsp+98h+var_60], 8
0x140004c91  mov     [r11-68h], r9
0x140004c95  lea     r9d, [r8+10h]
0x140004c99  mov     [r11-70h], r8
0x140004c9d  mov     [r11-78h], r8
0x140004ca1  mov     [r11-10h], r8
0x140004ca5  lea     r8, [r11-18h]
0x140004ca9  call    WinHvpSpecialListRepHypercall
0x140004cae  add     rsp, 98h
0x140004cb5  retn
```
