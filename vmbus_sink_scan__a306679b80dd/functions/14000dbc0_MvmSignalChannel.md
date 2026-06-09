# MvmSignalChannel

- ea: `0x14000dbc0`
- end: `0x14000dc18`
- name: `MvmSignalChannel`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000e0a0`
- `0x14000e7d4`
- `0x14000e8ec`

## pseudocode

```c
__int64 __fastcall MvmSignalChannel(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  __int64 v3; // rdi
  int v4; // r9d

  v1 = *(_QWORD *)(a1 + 40);
  v2 = *(unsigned int *)(a1 + 52);
  v3 = MvmpEstablishGhcbPage(v1);
  MvmpIssueHypercall(v1, v3, 93, v4, 1, v2);
  return MvmpReleaseGhcbPage(v1, v3);
}

```

## disassembly

```asm
0x14000dbc0  mov     [rsp+arg_0], rbx
0x14000dbc5  mov     [rsp+arg_8], rsi
0x14000dbca  push    rdi
0x14000dbcb  sub     rsp, 40h
0x14000dbcf  mov     rsi, [rcx+28h]
0x14000dbd3  mov     ebx, [rcx+34h]
0x14000dbd6  mov     rcx, rsi
0x14000dbd9  call    MvmpEstablishGhcbPage
0x14000dbde  mov     r8d, 5Dh ; ']'
0x14000dbe4  mov     [rsp+48h+var_20], rbx
0x14000dbe9  mov     rdx, rax
0x14000dbec  mov     [rsp+48h+var_28], 1
0x14000dbf1  mov     rcx, rsi
0x14000dbf4  mov     rdi, rax
0x14000dbf7  call    MvmpIssueHypercall
0x14000dbfc  mov     rdx, rdi
0x14000dbff  mov     rcx, rsi
0x14000dc02  call    MvmpReleaseGhcbPage
0x14000dc07  mov     rbx, [rsp+48h+arg_0]
0x14000dc0c  mov     rsi, [rsp+48h+arg_8]
0x14000dc11  add     rsp, 40h
0x14000dc15  pop     rdi
0x14000dc16  retn
```
