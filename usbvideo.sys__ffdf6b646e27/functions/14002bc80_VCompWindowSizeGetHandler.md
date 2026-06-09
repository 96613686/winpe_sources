# VCompWindowSizeGetHandler

- ea: `0x14002bc80`
- end: `0x14002bd58`
- name: `VCompWindowSizeGetHandler`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x140023a88`
- `0x14002bc80`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002bd2a`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002bd2a`
- `ks!KsReleaseControl` at `0x14002bd39`
- `ks!KsReleaseControl` at `0x14002bd39`
- `ks!KsAcquireControl` at `0x14002bcc8`
- `ks!KsAcquireControl` at `0x14002bcc8`
- `ks!KsGetFilterFromIrp` at `0x14002bcad`
- `ks!KsGetFilterFromIrp` at `0x14002bcad`
- `ks!KsGetDevice` at `0x14002bcd7`
- `ks!KsGetDevice` at `0x14002bcd7`

## pseudocode

```c
__int64 __fastcall VCompWindowSizeGetHandler(IRP *a1, __int64 a2, __int64 a3)
{
  int Handler; // ebx
  PKSFILTER FilterFromIrp; // rax
  PKSFILTER v8; // rdi
  PKSDEVICE Device; // rax
  __int64 Context; // rbp
  _OWORD v12[6]; // [rsp+20h] [rbp-68h] BYREF

  memset(v12, 0, 48);
  Handler = -1073741823;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  v8 = FilterFromIrp;
  if ( FilterFromIrp )
  {
    KsAcquireControl(FilterFromIrp);
    Device = KsGetDevice(v8);
    if ( Device )
    {
      Context = (__int64)Device->Context;
      Handler = AcquireProbeCommitLock(Context);
      if ( Handler >= 0 )
      {
        Handler = ProbeCommitGetHandler(a1, *(_DWORD *)(a2 + 24), v12);
        if ( Handler >= 0 )
          *(_DWORD *)(a3 + 28) = HIWORD(v12[0]);
        KeReleaseSemaphore(*(PRKSEMAPHORE *)(Context + 424), 0, 1, 0);
      }
    }
    KsReleaseControl(v8);
  }
  a1->IoStatus.Status = Handler;
  return (unsigned int)Handler;
}

```

## disassembly

```asm
0x14002bc80  push    rbx
0x14002bc82  push    rbp
0x14002bc83  push    rsi
0x14002bc84  push    rdi
0x14002bc85  push    r14
0x14002bc87  push    r15
0x14002bc89  sub     rsp, 58h
0x14002bc8d  xorps   xmm0, xmm0
0x14002bc90  mov     r14, r8
0x14002bc93  movups  [rsp+88h+var_68], xmm0
0x14002bc98  mov     r15, rdx
0x14002bc9b  mov     rsi, rcx
0x14002bc9e  movups  [rsp+88h+var_58], xmm0
0x14002bca3  mov     ebx, 0C0000001h
0x14002bca8  movups  [rsp+88h+var_48], xmm0
0x14002bcad  call    cs:__imp_KsGetFilterFromIrp
0x14002bcb4  nop     dword ptr [rax+rax+00h]
0x14002bcb9  mov     rdi, rax
0x14002bcbc  test    rax, rax
0x14002bcbf  jz      loc_14002BD45
0x14002bcc5  mov     rcx, rax; Object
0x14002bcc8  call    cs:__imp_KsAcquireControl
0x14002bccf  nop     dword ptr [rax+rax+00h]
0x14002bcd4  mov     rcx, rdi; Object
0x14002bcd7  call    cs:__imp_KsGetDevice
0x14002bcde  nop     dword ptr [rax+rax+00h]
0x14002bce3  test    rax, rax
0x14002bce6  jz      short loc_14002BD36
0x14002bce8  mov     rbp, [rax+10h]
0x14002bcec  mov     rcx, rbp
0x14002bcef  call    AcquireProbeCommitLock
0x14002bcf4  mov     ebx, eax
0x14002bcf6  test    eax, eax
0x14002bcf8  js      short loc_14002BD36
0x14002bcfa  mov     edx, [r15+18h]
0x14002bcfe  lea     r8, [rsp+88h+var_68]
0x14002bd03  mov     rcx, rsi
0x14002bd06  call    ProbeCommitGetHandler
0x14002bd0b  mov     ebx, eax
0x14002bd0d  test    eax, eax
0x14002bd0f  js      short loc_14002BD1A
0x14002bd11  movzx   eax, word ptr [rsp+88h+var_68+0Eh]
0x14002bd16  mov     [r14+1Ch], eax
0x14002bd1a  mov     rcx, [rbp+1A8h]; Semaphore
0x14002bd21  xor     r9d, r9d; Wait
0x14002bd24  xor     edx, edx; Increment
0x14002bd26  lea     r8d, [r9+1]; Adjustment
0x14002bd2a  call    cs:__imp_KeReleaseSemaphore
0x14002bd31  nop     dword ptr [rax+rax+00h]
0x14002bd36  mov     rcx, rdi; Object
0x14002bd39  call    cs:__imp_KsReleaseControl
0x14002bd40  nop     dword ptr [rax+rax+00h]
0x14002bd45  mov     [rsi+30h], ebx
0x14002bd48  mov     eax, ebx
0x14002bd4a  add     rsp, 58h
0x14002bd4e  pop     r15
0x14002bd50  pop     r14
0x14002bd52  pop     rdi
0x14002bd53  pop     rsi
0x14002bd54  pop     rbp
0x14002bd55  pop     rbx
0x14002bd56  retn
```
