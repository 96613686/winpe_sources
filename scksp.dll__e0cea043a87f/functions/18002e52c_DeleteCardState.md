# DeleteCardState

- ea: `0x18002e52c`
- end: `0x18002e656`
- name: `DeleteCardState`
- size: `298`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002ce34`
- `0x180032cf4`

## callees

- `0x18000d2a8`
- `0x18000d9d0`
- `0x180013aac`
- `0x18002ce58`
- `0x18002e52c`
- `0x180037070`
- `0x1800395f4`
- `0x18003ae44`
- `0x18003b920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e595`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e595`

## pseudocode

```c
__int64 __fastcall DeleteCardState(struct _CARD_STATE *a1, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD v11[7]; // [rsp+20h] [rbp-38h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 624);
  v11[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v11[1] = 0;
  if ( *((_DWORD *)a1 + 166) )
  {
    CspEnterCriticalSection(v2);
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v11, v2);
  }
  TransactionManagerForceEndTransaction(a1);
  v11[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v11);
  if ( *((_DWORD *)a1 + 166) )
    DeleteCriticalSection(v2);
  v5 = *((_QWORD *)a1 + 69);
  if ( v5 )
  {
    CspFreeH(v5);
    *((_QWORD *)a1 + 69) = 0;
  }
  v6 = *((_QWORD *)a1 + 71);
  if ( v6 )
  {
    CspFreeH(v6);
    *((_QWORD *)a1 + 71) = 0;
  }
  v7 = *((_QWORD *)a1 + 84);
  if ( v7 )
  {
    ScCacheDeleteCache(v7);
    *((_QWORD *)a1 + 84) = 0;
  }
  v8 = *((_QWORD *)a1 + 85);
  if ( v8 )
  {
    ScCacheDeleteCache(v8);
    *((_QWORD *)a1 + 85) = 0;
  }
  if ( *((_QWORD *)a1 + 1) )
    CleanupCardData((char *)a1 + 8, a2);
  if ( *((_QWORD *)a1 + 2) )
    *((_QWORD *)a1 + 2) = 0;
  v9 = *((_QWORD *)a1 + 76);
  if ( v9 )
  {
    CspFreeH(v9);
    *((_QWORD *)a1 + 76) = 0;
  }
  if ( *((_QWORD *)a1 + 73) )
    PinCacheFlush((char *)a1 + 584, 0, 1);
  return CspFreeH(a1);
}

```

## disassembly

```asm
0x18002e52c  push    rbx
0x18002e52e  push    rbp
0x18002e52f  push    rsi
0x18002e530  push    rdi
0x18002e531  push    r14
0x18002e533  sub     rsp, 30h
0x18002e537  xor     ebp, ebp
0x18002e539  lea     r14, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002e540  lea     rdi, [rcx+270h]
0x18002e547  mov     esi, edx
0x18002e549  mov     rbx, rcx
0x18002e54c  mov     [rsp+58h+var_38], r14
0x18002e551  mov     [rsp+58h+var_30], rbp
0x18002e556  cmp     [rcx+298h], ebp
0x18002e55c  jz      short loc_18002E573
0x18002e55e  mov     rcx, rdi
0x18002e561  call    CspEnterCriticalSection
0x18002e566  mov     rdx, rdi
0x18002e569  lea     rcx, [rsp+58h+var_38]
0x18002e56e  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18002e573  mov     rcx, rbx; struct _CARD_STATE *
0x18002e576  call    TransactionManagerForceEndTransaction
0x18002e57b  lea     rcx, [rsp+58h+var_38]
0x18002e580  mov     [rsp+58h+var_38], r14
0x18002e585  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18002e58a  cmp     [rbx+298h], ebp
0x18002e590  jz      short loc_18002E59B
0x18002e592  mov     rcx, rdi; lpCriticalSection
0x18002e595  call    cs:__imp_DeleteCriticalSection
0x18002e59b  mov     rcx, [rbx+228h]
0x18002e5a2  test    rcx, rcx
0x18002e5a5  jz      short loc_18002E5B3
0x18002e5a7  call    CspFreeH
0x18002e5ac  mov     [rbx+228h], rbp
0x18002e5b3  mov     rcx, [rbx+238h]
0x18002e5ba  test    rcx, rcx
0x18002e5bd  jz      short loc_18002E5CB
0x18002e5bf  call    CspFreeH
0x18002e5c4  mov     [rbx+238h], rbp
0x18002e5cb  mov     rcx, [rbx+2A0h]
0x18002e5d2  test    rcx, rcx
0x18002e5d5  jz      short loc_18002E5E3
0x18002e5d7  call    ScCacheDeleteCache
0x18002e5dc  mov     [rbx+2A0h], rbp
0x18002e5e3  mov     rcx, [rbx+2A8h]
0x18002e5ea  test    rcx, rcx
0x18002e5ed  jz      short loc_18002E5FB
0x18002e5ef  call    ScCacheDeleteCache
0x18002e5f4  mov     [rbx+2A8h], rbp
0x18002e5fb  lea     rcx, [rbx+8]
0x18002e5ff  cmp     [rcx], rbp
0x18002e602  jz      short loc_18002E60B
0x18002e604  mov     edx, esi
0x18002e606  call    CleanupCardData
0x18002e60b  cmp     [rbx+10h], rbp
0x18002e60f  jz      short loc_18002E615
0x18002e611  mov     [rbx+10h], rbp
0x18002e615  mov     rcx, [rbx+260h]
0x18002e61c  test    rcx, rcx
0x18002e61f  jz      short loc_18002E62D
0x18002e621  call    CspFreeH
0x18002e626  mov     [rbx+260h], rbp
0x18002e62d  lea     rcx, [rbx+248h]
0x18002e634  cmp     [rcx], rbp
0x18002e637  jz      short loc_18002E644
0x18002e639  xor     edx, edx
0x18002e63b  lea     r8d, [rdx+1]
0x18002e63f  call    PinCacheFlush
0x18002e644  mov     rcx, rbx
0x18002e647  add     rsp, 30h
0x18002e64b  pop     r14
0x18002e64d  pop     rdi
0x18002e64e  pop     rsi
0x18002e64f  pop     rbp
0x18002e650  pop     rbx
0x18002e651  jmp     CspFreeH
```
