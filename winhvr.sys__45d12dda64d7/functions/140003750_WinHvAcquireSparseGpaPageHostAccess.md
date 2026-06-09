# WinHvAcquireSparseGpaPageHostAccess

- ea: `0x140003750`
- end: `0x1400037c5`
- name: `WinHvAcquireSparseGpaPageHostAccess`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvAcquireSparseGpaPageHostAccess(__int64 a1, char a2, unsigned __int64 a3, char *a4, _QWORD *a5)
{
  __int64 v6; // [rsp+80h] [rbp-18h] BYREF
  int v7; // [rsp+88h] [rbp-10h]
  int v8; // [rsp+8Ch] [rbp-Ch]

  v8 = 0;
  v6 = a1;
  v7 = a2 & 7;
  return WinHvpSpecialListRepHypercall(210, a3, &v6, 0x10u, 0, 0, a4, 8u, 0, 0, 0, 0, 0, 0, a5);
}

```

## disassembly

```asm
0x140003750  mov     r11, rsp
0x140003753  sub     rsp, 98h
0x14000375a  mov     rax, [rsp+98h+arg_20]
0x140003762  mov     r10, r8
0x140003765  xor     r8d, r8d
0x140003768  mov     [r11-28h], rax
0x14000376c  mov     [r11-30h], r8
0x140003770  and     edx, 7
0x140003773  mov     [r11-38h], r8
0x140003777  mov     [r11-40h], r8d
0x14000377b  mov     [r11-48h], r8
0x14000377f  mov     [r11-50h], r8
0x140003783  mov     [r11-58h], r8
0x140003787  mov     [rsp+98h+var_60], 8
0x14000378f  mov     [r11-68h], r9
0x140003793  lea     r9d, [r8+10h]
0x140003797  mov     [r11-70h], r8
0x14000379b  mov     [r11-78h], r8
0x14000379f  mov     [r11-0Ch], r8d
0x1400037a3  lea     r8, [r11-18h]
0x1400037a7  mov     [r11-18h], rcx
0x1400037ab  mov     ecx, 0D2h
0x1400037b0  mov     [r11-10h], edx
0x1400037b4  mov     rdx, r10
0x1400037b7  call    WinHvpSpecialListRepHypercall
0x1400037bc  add     rsp, 98h
0x1400037c3  retn
```
