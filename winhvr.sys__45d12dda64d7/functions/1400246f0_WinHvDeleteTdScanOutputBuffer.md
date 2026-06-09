# WinHvDeleteTdScanOutputBuffer

- ea: `0x1400246f0`
- end: `0x14002476a`
- name: `WinHvDeleteTdScanOutputBuffer`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140024570`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvDeleteTdScanOutputBuffer(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  _QWORD v6[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v7; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  memset(v6, 0, 0x40u);
  WinHvpSetupHypercall(&v7, 0, (__int64)v6);
  v4 = v7;
  *(_OWORD *)v7 = 0;
  *v4 = a1;
  v4[1] = a2;
  LODWORD(a1) = WinHvpSimplePoolHypercall_CallViaMacro(v6[0], 330);
  ((void (__fastcall *)(_QWORD))v6[7])(v6[0]);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1400246f0  mov     [rsp+arg_8], rbx
0x1400246f5  push    rdi
0x1400246f6  sub     rsp, 60h
0x1400246fa  mov     rdi, rdx
0x1400246fd  mov     [rsp+68h+arg_0], 0
0x140024706  xor     edx, edx; Val
0x140024708  mov     rbx, rcx
0x14002470b  lea     rcx, [rsp+68h+var_48]; void *
0x140024710  lea     r8d, [rdx+40h]; Size
0x140024714  call    memset
0x140024719  lea     r8, [rsp+68h+var_48]
0x14002471e  xor     edx, edx
0x140024720  lea     rcx, [rsp+68h+arg_0]
0x140024725  call    WinHvpSetupHypercall
0x14002472a  mov     rax, [rsp+68h+arg_0]
0x14002472f  xorps   xmm0, xmm0
0x140024732  mov     edx, 14Ah
0x140024737  movups  xmmword ptr [rax], xmm0
0x14002473a  mov     [rax], rbx
0x14002473d  mov     [rax+8], rdi
0x140024741  mov     rcx, [rsp+68h+var_48]
0x140024746  call    WinHvpSimplePoolHypercall_CallViaMacro
0x14002474b  mov     rcx, [rsp+68h+var_48]
0x140024750  mov     ebx, eax
0x140024752  mov     rax, [rsp+68h+var_10]
0x140024757  call    _guard_dispatch_icall
0x14002475c  mov     eax, ebx
0x14002475e  mov     rbx, [rsp+68h+arg_8]
0x140024763  add     rsp, 60h
0x140024767  pop     rdi
0x140024768  retn
```
