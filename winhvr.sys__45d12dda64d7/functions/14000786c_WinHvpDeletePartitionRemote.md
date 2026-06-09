# WinHvpDeletePartitionRemote

- ea: `0x14000786c`
- end: `0x1400078d5`
- name: `WinHvpDeletePartitionRemote`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140021c40`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvpDeletePartitionRemote(__int64 a1)
{
  _QWORD v3[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v4; // [rsp+70h] [rbp+8h] BYREF

  memset(v3, 0, 0x40u);
  v4 = 0;
  LOBYTE(v3[3]) = 1;
  WinHvpSetupHypercall(&v4, 0, (__int64)v3);
  *v4 = a1;
  LODWORD(a1) = WinHvpSimplePoolHypercall_CallViaMacro(v3, 67);
  ((void (__fastcall *)(_QWORD))v3[7])(v3[0]);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x14000786c  push    rbx
0x14000786e  sub     rsp, 60h
0x140007872  xor     edx, edx; Val
0x140007874  mov     rbx, rcx
0x140007877  lea     rcx, [rsp+68h+var_48]; void *
0x14000787c  lea     r8d, [rdx+40h]; Size
0x140007880  call    memset
0x140007885  lea     r8, [rsp+68h+var_48]
0x14000788a  mov     [rsp+68h+arg_0], 0
0x140007893  xor     edx, edx
0x140007895  mov     [rsp+68h+var_30], 1
0x14000789a  lea     rcx, [rsp+68h+arg_0]
0x14000789f  call    WinHvpSetupHypercall
0x1400078a4  mov     rax, [rsp+68h+arg_0]
0x1400078a9  lea     rcx, [rsp+68h+var_48]
0x1400078ae  mov     edx, 43h ; 'C'
0x1400078b3  mov     [rax], rbx
0x1400078b6  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400078bb  mov     rcx, [rsp+68h+var_48]
0x1400078c0  mov     ebx, eax
0x1400078c2  mov     rax, [rsp+68h+var_10]
0x1400078c7  call    _guard_dispatch_icall
0x1400078cc  mov     eax, ebx
0x1400078ce  add     rsp, 60h
0x1400078d2  pop     rbx
0x1400078d3  retn
```
