# UnInitializePassiveCompletionThread

- ea: `0x14003a1c8`
- end: `0x14003a343`
- name: `UnInitializePassiveCompletionThread`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018814`

## callees

- `0x14001ab4c`
- `0x14001b15c`
- `0x14003a1c8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003a2f1`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a2f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a2b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a2b1`
- `ntoskrnl!KeReleaseSemaphore` at `0x14003a245`
- `ntoskrnl!KeReleaseSemaphore` at `0x14003a245`

## pseudocode

```c
__int64 __fastcall UnInitializePassiveCompletionThread(__int64 a1)
{
  unsigned int v2; // esi
  PVOID *v3; // rdi
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  Timeout.QuadPart = -50000000;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1);
  v3 = (PVOID *)(a1 + 448);
  if ( *(_QWORD *)(a1 + 448) )
  {
    *(_BYTE *)(a1 + 441) = 1;
    KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 464), 0, 1, 1u);
    v2 = KeWaitForSingleObject(*v3, Executive, 0, 0, &Timeout);
    if ( v2 == 258
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1);
    }
    ObfDereferenceObject(*v3);
    *v3 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1, v2);
  return v2;
}

```

## disassembly

```asm
0x14003a1c8  mov     [rsp+arg_18], rbx
0x14003a1cd  mov     [rsp+arg_0], rcx
0x14003a1d2  push    rsi
0x14003a1d3  push    rdi
0x14003a1d4  push    r14
0x14003a1d6  sub     rsp, 30h
0x14003a1da  mov     rbx, rcx
0x14003a1dd  xor     esi, esi
0x14003a1df  mov     qword ptr [rsp+48h+arg_10], 0FFFFFFFFFD050F80h
0x14003a1e8  lea     r14, WPP_GLOBAL_Control
0x14003a1ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1f6  cmp     rcx, r14
0x14003a1f9  jz      short loc_14003A219
0x14003a1fb  cmp     byte ptr [rcx+29h], 5
0x14003a1ff  jb      short loc_14003A219
0x14003a201  mov     edx, 81h
0x14003a206  mov     r9, rbx
0x14003a209  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14003a210  mov     rcx, [rcx+18h]
0x14003a214  call    WPP_SF_q
0x14003a219  lea     rdi, [rbx+1C0h]
0x14003a220  mov     [rsp+48h+arg_8], rdi
0x14003a225  cmp     [rdi], rsi
0x14003a228  jz      loc_14003A304
0x14003a22e  mov     byte ptr [rbx+1B9h], 1
0x14003a235  lea     rcx, [rbx+1D0h]; Semaphore
0x14003a23c  mov     r9b, 1; Wait
0x14003a23f  xor     edx, edx; Increment
0x14003a241  lea     r8d, [rdx+1]; Adjustment
0x14003a245  call    cs:__imp_KeReleaseSemaphore
0x14003a24c  nop     dword ptr [rax+rax+00h]
0x14003a251  jmp     short loc_14003A29C
0x14003a253  lea     rax, WPP_GLOBAL_Control
0x14003a25a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a261  cmp     rcx, rax
0x14003a264  jz      short loc_14003A28B
0x14003a266  cmp     byte ptr [rcx+29h], 2
0x14003a26a  jb      short loc_14003A28B
0x14003a26c  mov     edx, 82h
0x14003a271  mov     rbx, [rsp+48h+arg_0]
0x14003a276  mov     r9, rbx
0x14003a279  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14003a280  mov     rcx, [rcx+18h]
0x14003a284  call    WPP_SF_q
0x14003a289  jmp     short loc_14003A290
0x14003a28b  mov     rbx, [rsp+48h+arg_0]
0x14003a290  lea     r14, WPP_GLOBAL_Control
0x14003a297  mov     rdi, [rsp+48h+arg_8]
0x14003a29c  lea     rax, [rsp+48h+arg_10]
0x14003a2a1  mov     [rsp+48h+Timeout], rax; Timeout
0x14003a2a6  xor     r9d, r9d; Alertable
0x14003a2a9  xor     r8d, r8d; WaitMode
0x14003a2ac  xor     edx, edx; WaitReason
0x14003a2ae  mov     rcx, [rdi]; Object
0x14003a2b1  call    cs:__imp_KeWaitForSingleObject
0x14003a2b8  nop     dword ptr [rax+rax+00h]
0x14003a2bd  mov     esi, eax
0x14003a2bf  cmp     eax, 102h
0x14003a2c4  jnz     short loc_14003A2EE
0x14003a2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a2cd  cmp     rcx, r14
0x14003a2d0  jz      short loc_14003A2EE
0x14003a2d2  cmp     byte ptr [rcx+29h], 2
0x14003a2d6  jb      short loc_14003A2EE
0x14003a2d8  lea     edx, [rax-7Fh]
0x14003a2db  mov     r9, rbx
0x14003a2de  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14003a2e5  mov     rcx, [rcx+18h]
0x14003a2e9  call    WPP_SF_q
0x14003a2ee  mov     rcx, [rdi]; Object
0x14003a2f1  call    cs:__imp_ObfDereferenceObject
0x14003a2f8  nop     dword ptr [rax+rax+00h]
0x14003a2fd  mov     qword ptr [rdi], 0
0x14003a304  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a30b  cmp     rcx, r14
0x14003a30e  jz      short loc_14003A332
0x14003a310  cmp     byte ptr [rcx+29h], 5
0x14003a314  jb      short loc_14003A332
0x14003a316  mov     edx, 84h
0x14003a31b  mov     dword ptr [rsp+48h+Timeout], esi
0x14003a31f  mov     r9, rbx
0x14003a322  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14003a329  mov     rcx, [rcx+18h]
0x14003a32d  call    WPP_SF_qD
0x14003a332  mov     eax, esi
0x14003a334  mov     rbx, [rsp+48h+arg_18]
0x14003a339  add     rsp, 30h
0x14003a33d  pop     r14
0x14003a33f  pop     rdi
0x14003a340  pop     rsi
0x14003a341  retn
0x140041389  push    rbp
0x14004138b  sub     rsp, 30h
0x14004138f  mov     rbp, rdx
0x140041392  mov     rax, [rcx]
0x140041395  mov     ecx, [rax]
0x140041397  xor     eax, eax
0x140041399  cmp     ecx, 0C0000047h
0x14004139f  setz    al
0x1400413a2  add     rsp, 30h
0x1400413a6  pop     rbp
0x1400413a7  retn
```
