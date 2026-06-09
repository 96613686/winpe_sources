# VCompQualityGetHandler

- ea: `0x14002ba30`
- end: `0x14002bb17`
- name: `VCompQualityGetHandler`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x140023a88`
- `0x14002ba30`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002bae9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002bae9`
- `ks!KsReleaseControl` at `0x14002baf8`
- `ks!KsReleaseControl` at `0x14002baf8`
- `ks!KsAcquireControl` at `0x14002ba78`
- `ks!KsAcquireControl` at `0x14002ba78`
- `ks!KsGetFilterFromIrp` at `0x14002ba5d`
- `ks!KsGetFilterFromIrp` at `0x14002ba5d`
- `ks!KsGetDevice` at `0x14002ba87`
- `ks!KsGetDevice` at `0x14002ba87`

## pseudocode

```c
__int64 __fastcall VCompQualityGetHandler(IRP *a1, __int64 a2, __int64 a3)
{
  int Handler; // ebx
  PKSFILTER FilterFromIrp; // rax
  PKSFILTER v8; // rdi
  PKSDEVICE Device; // rbp
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
      if ( *(_DWORD *)(a2 + 24) < v8->Descriptor->PinDescriptorsCount )
      {
        Context = (__int64)Device->Context;
        Handler = AcquireProbeCommitLock(Context);
        if ( Handler >= 0 )
        {
          Handler = ProbeCommitGetHandler(a1, *(_DWORD *)(a2 + 24), v12);
          if ( Handler >= 0 )
            *(_DWORD *)(a3 + 28) = WORD6(v12[0]);
          KeReleaseSemaphore(*(PRKSEMAPHORE *)(Context + 424), 0, 1, 0);
        }
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
0x14002ba30  push    rbx
0x14002ba32  push    rbp
0x14002ba33  push    rsi
0x14002ba34  push    rdi
0x14002ba35  push    r14
0x14002ba37  push    r15
0x14002ba39  sub     rsp, 58h
0x14002ba3d  xorps   xmm0, xmm0
0x14002ba40  mov     r15, r8
0x14002ba43  movups  [rsp+88h+var_68], xmm0
0x14002ba48  mov     r14, rdx
0x14002ba4b  mov     rsi, rcx
0x14002ba4e  movups  [rsp+88h+var_58], xmm0
0x14002ba53  mov     ebx, 0C0000001h
0x14002ba58  movups  [rsp+88h+var_48], xmm0
0x14002ba5d  call    cs:__imp_KsGetFilterFromIrp
0x14002ba64  nop     dword ptr [rax+rax+00h]
0x14002ba69  mov     rdi, rax
0x14002ba6c  test    rax, rax
0x14002ba6f  jz      loc_14002BB04
0x14002ba75  mov     rcx, rax; Object
0x14002ba78  call    cs:__imp_KsAcquireControl
0x14002ba7f  nop     dword ptr [rax+rax+00h]
0x14002ba84  mov     rcx, rdi; Object
0x14002ba87  call    cs:__imp_KsGetDevice
0x14002ba8e  nop     dword ptr [rax+rax+00h]
0x14002ba93  mov     rbp, rax
0x14002ba96  test    rax, rax
0x14002ba99  jz      short loc_14002BAF5
0x14002ba9b  mov     rax, [rdi]
0x14002ba9e  mov     ecx, [rax+20h]
0x14002baa1  cmp     [r14+18h], ecx
0x14002baa5  jnb     short loc_14002BAF5
0x14002baa7  mov     rbp, [rbp+10h]
0x14002baab  mov     rcx, rbp
0x14002baae  call    AcquireProbeCommitLock
0x14002bab3  mov     ebx, eax
0x14002bab5  test    eax, eax
0x14002bab7  js      short loc_14002BAF5
0x14002bab9  mov     edx, [r14+18h]
0x14002babd  lea     r8, [rsp+88h+var_68]
0x14002bac2  mov     rcx, rsi
0x14002bac5  call    ProbeCommitGetHandler
0x14002baca  mov     ebx, eax
0x14002bacc  test    eax, eax
0x14002bace  js      short loc_14002BAD9
0x14002bad0  movzx   eax, word ptr [rsp+88h+var_68+0Ch]
0x14002bad5  mov     [r15+1Ch], eax
0x14002bad9  mov     rcx, [rbp+1A8h]; Semaphore
0x14002bae0  xor     r9d, r9d; Wait
0x14002bae3  xor     edx, edx; Increment
0x14002bae5  lea     r8d, [r9+1]; Adjustment
0x14002bae9  call    cs:__imp_KeReleaseSemaphore
0x14002baf0  nop     dword ptr [rax+rax+00h]
0x14002baf5  mov     rcx, rdi; Object
0x14002baf8  call    cs:__imp_KsReleaseControl
0x14002baff  nop     dword ptr [rax+rax+00h]
0x14002bb04  mov     [rsi+30h], ebx
0x14002bb07  mov     eax, ebx
0x14002bb09  add     rsp, 58h
0x14002bb0d  pop     r15
0x14002bb0f  pop     r14
0x14002bb11  pop     rdi
0x14002bb12  pop     rsi
0x14002bb13  pop     rbp
0x14002bb14  pop     rbx
0x14002bb15  retn
```
