# WanpTransmitQueuedPackets

- ea: `0x1400142dc`
- end: `0x1400143dc`
- name: `WanpTransmitQueuedPackets`
- size: `256`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400048d0`
- `0x140010448`

## callees

- `0x1400142dc`
- `0x140015b80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140014314`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001435c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140014314`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001435c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014327`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001439b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014327`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001439b`
- `NDIS!NdisSendNetBufferLists` at `0x1400143c2`
- `NDIS!NdisSendNetBufferLists` at `0x1400143c2`

## pseudocode

```c
void __fastcall WanpTransmitQueuedPackets(__int64 a1, KIRQL a2, char a3)
{
  __int64 v6; // r10
  KSPIN_LOCK *v7; // rcx
  __int64 v8; // rsi
  struct _NET_BUFFER_LIST *v9; // r15
  SLIST_HEADER *Alignment; // rbx
  NDIS_HANDLE v11; // rcx

  v6 = *(_QWORD *)((-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + a1 + 176);
  v7 = (KSPIN_LOCK *)(v6 + 56);
  if ( *(_DWORD *)(v6 + 136) )
  {
    v8 = *(_QWORD *)(v6 + 40);
    v9 = *(struct _NET_BUFFER_LIST **)(v6 + 120);
    *(_QWORD *)(v6 + 120) = 0;
    *(_QWORD *)(v6 + 128) = v6 + 120;
    *(_DWORD *)(v6 + 136) = 0;
    KeReleaseSpinLockFromDpcLevel(v7);
    Alignment = (SLIST_HEADER *)v9;
    if ( v9 )
    {
      do
      {
        *(_QWORD *)(*(unsigned __int16 *)(Alignment[1].Alignment + 10) + Alignment[1].Alignment + 16) = v8;
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 96));
        WanpPreparePacketsForSend((__int64)Alignment, v8);
        Alignment = (SLIST_HEADER *)Alignment->Alignment;
      }
      while ( Alignment );
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 120), a2);
    v11 = (NDIS_HANDLE)qword_1400099E8;
    if ( !a3 )
      v11 = NdisBindingHandle;
    NdisSendNetBufferLists(v11, v9, 0, 0);
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel(v7);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 120), a2);
  }
}

```

## disassembly

```asm
0x1400142dc  push    rbx
0x1400142de  push    rbp
0x1400142df  push    rsi
0x1400142e0  push    rdi
0x1400142e1  push    r14
0x1400142e3  push    r15
0x1400142e5  sub     rsp, 28h
0x1400142e9  mov     al, r8b
0x1400142ec  mov     rdi, rcx
0x1400142ef  neg     al
0x1400142f1  mov     r14b, r8b
0x1400142f4  mov     bpl, dl
0x1400142f7  sbb     r9, r9
0x1400142fa  and     r9, 0FFFFFFFFFFFFFFF8h
0x1400142fe  mov     r10, [r9+rcx+0B0h]
0x140014306  cmp     dword ptr [r10+88h], 0
0x14001430e  lea     rcx, [r10+38h]; SpinLock
0x140014312  jnz     short loc_140014338
0x140014314  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001431b  nop     dword ptr [rax+rax+00h]
0x140014320  lea     rcx, [rdi+78h]; SpinLock
0x140014324  mov     dl, bpl; NewIrql
0x140014327  call    cs:__imp_KeReleaseSpinLock
0x14001432e  nop     dword ptr [rax+rax+00h]
0x140014333  jmp     loc_1400143CE
0x140014338  mov     rsi, [r10+28h]
0x14001433c  lea     rax, [r10+78h]
0x140014340  mov     r15, [rax]
0x140014343  mov     qword ptr [rax], 0
0x14001434a  mov     [r10+80h], rax
0x140014351  mov     dword ptr [r10+88h], 0
0x14001435c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140014363  nop     dword ptr [rax+rax+00h]
0x140014368  mov     rbx, r15
0x14001436b  test    r15, r15
0x14001436e  jz      short loc_140014394
0x140014370  mov     rcx, [rbx+10h]
0x140014374  movzx   eax, word ptr [rcx+0Ah]
0x140014378  mov     [rax+rcx+10h], rsi
0x14001437d  lock inc dword ptr [rsi+60h]
0x140014381  mov     rdx, rsi
0x140014384  mov     rcx, rbx
0x140014387  call    WanpPreparePacketsForSend
0x14001438c  mov     rbx, [rbx]
0x14001438f  test    rbx, rbx
0x140014392  jnz     short loc_140014370
0x140014394  lea     rcx, [rdi+78h]; SpinLock
0x140014398  mov     dl, bpl; NewIrql
0x14001439b  call    cs:__imp_KeReleaseSpinLock
0x1400143a2  nop     dword ptr [rax+rax+00h]
0x1400143a7  mov     rcx, cs:qword_1400099E8
0x1400143ae  test    r14b, r14b
0x1400143b1  mov     rdx, r15; NetBufferLists
0x1400143b4  cmovz   rcx, cs:NdisBindingHandle; NdisBindingHandle
0x1400143bc  xor     r9d, r9d; SendFlags
0x1400143bf  xor     r8d, r8d; PortNumber
0x1400143c2  call    cs:__imp_NdisSendNetBufferLists
0x1400143c9  nop     dword ptr [rax+rax+00h]
0x1400143ce  add     rsp, 28h
0x1400143d2  pop     r15
0x1400143d4  pop     r14
0x1400143d6  pop     rdi
0x1400143d7  pop     rsi
0x1400143d8  pop     rbp
0x1400143d9  pop     rbx
0x1400143da  retn
```
