# WinHvReleaseSparseGpaPageHostAccess

- ea: `0x1400052b0`
- end: `0x140005325`
- name: `WinHvReleaseSparseGpaPageHostAccess`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvReleaseSparseGpaPageHostAccess(__int64 a1, char a2, unsigned __int64 a3, char *a4, _QWORD *a5)
{
  __int64 v6; // [rsp+80h] [rbp-18h] BYREF
  int v7; // [rsp+88h] [rbp-10h]
  int v8; // [rsp+8Ch] [rbp-Ch]

  v8 = 0;
  v6 = a1;
  v7 = a2 & 7;
  return WinHvpSpecialListRepHypercall(211, a3, &v6, 0x10u, 0, 0, a4, 8u, 0, 0, 0, 0, 0, 0, a5);
}

```

## disassembly

```asm
0x1400052b0  mov     r11, rsp
0x1400052b3  sub     rsp, 98h
0x1400052ba  mov     rax, [rsp+98h+arg_20]
0x1400052c2  mov     r10, r8
0x1400052c5  xor     r8d, r8d
0x1400052c8  mov     [r11-28h], rax
0x1400052cc  mov     [r11-30h], r8
0x1400052d0  and     edx, 7
0x1400052d3  mov     [r11-38h], r8
0x1400052d7  mov     [r11-40h], r8d
0x1400052db  mov     [r11-48h], r8
0x1400052df  mov     [r11-50h], r8
0x1400052e3  mov     [r11-58h], r8
0x1400052e7  mov     [rsp+98h+var_60], 8
0x1400052ef  mov     [r11-68h], r9
0x1400052f3  lea     r9d, [r8+10h]
0x1400052f7  mov     [r11-70h], r8
0x1400052fb  mov     [r11-78h], r8
0x1400052ff  mov     [r11-0Ch], r8d
0x140005303  lea     r8, [r11-18h]
0x140005307  mov     [r11-18h], rcx
0x14000530b  mov     ecx, 0D3h
0x140005310  mov     [r11-10h], edx
0x140005314  mov     rdx, r10
0x140005317  call    WinHvpSpecialListRepHypercall
0x14000531c  add     rsp, 98h
0x140005323  retn
```
