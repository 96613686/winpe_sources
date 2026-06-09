# VCompKeyFrameRateGetHandler

- ea: `0x14002b5a0`
- end: `0x14002b687`
- name: `VCompKeyFrameRateGetHandler`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a468`
- `0x140023a88`
- `0x14002b5a0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002b659`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002b659`
- `ks!KsReleaseControl` at `0x14002b668`
- `ks!KsReleaseControl` at `0x14002b668`
- `ks!KsAcquireControl` at `0x14002b5e8`
- `ks!KsAcquireControl` at `0x14002b5e8`
- `ks!KsGetFilterFromIrp` at `0x14002b5cd`
- `ks!KsGetFilterFromIrp` at `0x14002b5cd`
- `ks!KsGetDevice` at `0x14002b5f7`
- `ks!KsGetDevice` at `0x14002b5f7`

## pseudocode

```c
__int64 __fastcall VCompKeyFrameRateGetHandler(IRP *a1, __int64 a2, __int64 a3)
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
            *(_DWORD *)(a3 + 28) = WORD4(v12[0]);
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
0x14002b5a0  push    rbx
0x14002b5a2  push    rbp
0x14002b5a3  push    rsi
0x14002b5a4  push    rdi
0x14002b5a5  push    r14
0x14002b5a7  push    r15
0x14002b5a9  sub     rsp, 58h
0x14002b5ad  xorps   xmm0, xmm0
0x14002b5b0  mov     r15, r8
0x14002b5b3  movups  [rsp+88h+var_68], xmm0
0x14002b5b8  mov     r14, rdx
0x14002b5bb  mov     rsi, rcx
0x14002b5be  movups  [rsp+88h+var_58], xmm0
0x14002b5c3  mov     ebx, 0C0000001h
0x14002b5c8  movups  [rsp+88h+var_48], xmm0
0x14002b5cd  call    cs:__imp_KsGetFilterFromIrp
0x14002b5d4  nop     dword ptr [rax+rax+00h]
0x14002b5d9  mov     rdi, rax
0x14002b5dc  test    rax, rax
0x14002b5df  jz      loc_14002B674
0x14002b5e5  mov     rcx, rax; Object
0x14002b5e8  call    cs:__imp_KsAcquireControl
0x14002b5ef  nop     dword ptr [rax+rax+00h]
0x14002b5f4  mov     rcx, rdi; Object
0x14002b5f7  call    cs:__imp_KsGetDevice
0x14002b5fe  nop     dword ptr [rax+rax+00h]
0x14002b603  mov     rbp, rax
0x14002b606  test    rax, rax
0x14002b609  jz      short loc_14002B665
0x14002b60b  mov     rax, [rdi]
0x14002b60e  mov     ecx, [rax+20h]
0x14002b611  cmp     [r14+18h], ecx
0x14002b615  jnb     short loc_14002B665
0x14002b617  mov     rbp, [rbp+10h]
0x14002b61b  mov     rcx, rbp
0x14002b61e  call    AcquireProbeCommitLock
0x14002b623  mov     ebx, eax
0x14002b625  test    eax, eax
0x14002b627  js      short loc_14002B665
0x14002b629  mov     edx, [r14+18h]
0x14002b62d  lea     r8, [rsp+88h+var_68]
0x14002b632  mov     rcx, rsi
0x14002b635  call    ProbeCommitGetHandler
0x14002b63a  mov     ebx, eax
0x14002b63c  test    eax, eax
0x14002b63e  js      short loc_14002B649
0x14002b640  movzx   eax, word ptr [rsp+88h+var_68+8]
0x14002b645  mov     [r15+1Ch], eax
0x14002b649  mov     rcx, [rbp+1A8h]; Semaphore
0x14002b650  xor     r9d, r9d; Wait
0x14002b653  xor     edx, edx; Increment
0x14002b655  lea     r8d, [r9+1]; Adjustment
0x14002b659  call    cs:__imp_KeReleaseSemaphore
0x14002b660  nop     dword ptr [rax+rax+00h]
0x14002b665  mov     rcx, rdi; Object
0x14002b668  call    cs:__imp_KsReleaseControl
0x14002b66f  nop     dword ptr [rax+rax+00h]
0x14002b674  mov     [rsi+30h], ebx
0x14002b677  mov     eax, ebx
0x14002b679  add     rsp, 58h
0x14002b67d  pop     r15
0x14002b67f  pop     r14
0x14002b681  pop     rdi
0x14002b682  pop     rsi
0x14002b683  pop     rbp
0x14002b684  pop     rbx
0x14002b685  retn
```
