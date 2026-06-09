# VCompPFramesPerKeyFrameGetHandler

- ea: `0x14002b7f0`
- end: `0x14002b8d7`
- name: `VCompPFramesPerKeyFrameGetHandler`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x140023a88`
- `0x14002b7f0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002b8a9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002b8a9`
- `ks!KsReleaseControl` at `0x14002b8b8`
- `ks!KsReleaseControl` at `0x14002b8b8`
- `ks!KsAcquireControl` at `0x14002b838`
- `ks!KsAcquireControl` at `0x14002b838`
- `ks!KsGetFilterFromIrp` at `0x14002b81d`
- `ks!KsGetFilterFromIrp` at `0x14002b81d`
- `ks!KsGetDevice` at `0x14002b847`
- `ks!KsGetDevice` at `0x14002b847`

## pseudocode

```c
__int64 __fastcall VCompPFramesPerKeyFrameGetHandler(IRP *a1, __int64 a2, __int64 a3)
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
            *(_DWORD *)(a3 + 28) = WORD5(v12[0]);
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
0x14002b7f0  push    rbx
0x14002b7f2  push    rbp
0x14002b7f3  push    rsi
0x14002b7f4  push    rdi
0x14002b7f5  push    r14
0x14002b7f7  push    r15
0x14002b7f9  sub     rsp, 58h
0x14002b7fd  xorps   xmm0, xmm0
0x14002b800  mov     r15, r8
0x14002b803  movups  [rsp+88h+var_68], xmm0
0x14002b808  mov     r14, rdx
0x14002b80b  mov     rsi, rcx
0x14002b80e  movups  [rsp+88h+var_58], xmm0
0x14002b813  mov     ebx, 0C0000001h
0x14002b818  movups  [rsp+88h+var_48], xmm0
0x14002b81d  call    cs:__imp_KsGetFilterFromIrp
0x14002b824  nop     dword ptr [rax+rax+00h]
0x14002b829  mov     rdi, rax
0x14002b82c  test    rax, rax
0x14002b82f  jz      loc_14002B8C4
0x14002b835  mov     rcx, rax; Object
0x14002b838  call    cs:__imp_KsAcquireControl
0x14002b83f  nop     dword ptr [rax+rax+00h]
0x14002b844  mov     rcx, rdi; Object
0x14002b847  call    cs:__imp_KsGetDevice
0x14002b84e  nop     dword ptr [rax+rax+00h]
0x14002b853  mov     rbp, rax
0x14002b856  test    rax, rax
0x14002b859  jz      short loc_14002B8B5
0x14002b85b  mov     rax, [rdi]
0x14002b85e  mov     ecx, [rax+20h]
0x14002b861  cmp     [r14+18h], ecx
0x14002b865  jnb     short loc_14002B8B5
0x14002b867  mov     rbp, [rbp+10h]
0x14002b86b  mov     rcx, rbp
0x14002b86e  call    AcquireProbeCommitLock
0x14002b873  mov     ebx, eax
0x14002b875  test    eax, eax
0x14002b877  js      short loc_14002B8B5
0x14002b879  mov     edx, [r14+18h]
0x14002b87d  lea     r8, [rsp+88h+var_68]
0x14002b882  mov     rcx, rsi
0x14002b885  call    ProbeCommitGetHandler
0x14002b88a  mov     ebx, eax
0x14002b88c  test    eax, eax
0x14002b88e  js      short loc_14002B899
0x14002b890  movzx   eax, word ptr [rsp+88h+var_68+0Ah]
0x14002b895  mov     [r15+1Ch], eax
0x14002b899  mov     rcx, [rbp+1A8h]; Semaphore
0x14002b8a0  xor     r9d, r9d; Wait
0x14002b8a3  xor     edx, edx; Increment
0x14002b8a5  lea     r8d, [r9+1]; Adjustment
0x14002b8a9  call    cs:__imp_KeReleaseSemaphore
0x14002b8b0  nop     dword ptr [rax+rax+00h]
0x14002b8b5  mov     rcx, rdi; Object
0x14002b8b8  call    cs:__imp_KsReleaseControl
0x14002b8bf  nop     dword ptr [rax+rax+00h]
0x14002b8c4  mov     [rsi+30h], ebx
0x14002b8c7  mov     eax, ebx
0x14002b8c9  add     rsp, 58h
0x14002b8cd  pop     r15
0x14002b8cf  pop     r14
0x14002b8d1  pop     rdi
0x14002b8d2  pop     rsi
0x14002b8d3  pop     rbp
0x14002b8d4  pop     rbx
0x14002b8d5  retn
```
