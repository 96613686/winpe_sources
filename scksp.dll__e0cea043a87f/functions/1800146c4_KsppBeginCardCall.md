# KsppBeginCardCall

- ea: `0x1800146c4`
- end: `0x180014850`
- name: `KsppBeginCardCall`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180013b5c`
- `0x180016624`
- `0x180017f6c`
- `0x180018774`
- `0x180018968`
- `0x1800199b0`
- `0x18001a59c`
- `0x18001b6f8`
- `0x18001c818`
- `0x18001d4e0`
- `0x18001dbc8`
- `0x18001e590`
- `0x18001e92c`
- `0x180020ed4`
- `0x1800253c0`
- `0x180028a30`

## callees

- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x180013734`
- `0x180013aac`
- `0x1800146c4`
- `0x180017b24`
- `0x18002e034`
- `0x18002e7a0`
- `0x18003af5c`
- `0x18003afc0`
- `0x18003b788`

## pseudocode

```c
__int64 __fastcall KsppBeginCardCall(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int CardBySerialNumber; // ebx
  int v4; // ebx
  struct _CARD_STATE *v5; // rcx
  void **v7; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+38h] [rbp-20h]

  v7 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v8 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, WPP_pszIndent);
  }
  CardBySerialNumber = KspEnterCriticalSection(*(_QWORD *)(a1 + 16) + 624LL);
  if ( !CardBySerialNumber )
  {
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v7, *(_QWORD *)(a1 + 16) + 624LL);
    v4 = ValidateCardHandle(*(struct _CARD_STATE **)(a1 + 16));
    v5 = *(struct _CARD_STATE **)(a1 + 16);
    if ( v4 )
    {
      v8 = 0;
      KspLeaveCriticalSection((char *)v5 + 624);
      CardBySerialNumber = KsppFindCardBySerialNumber(a1);
      if ( CardBySerialNumber )
        goto LABEL_11;
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v7, *(_QWORD *)(a1 + 16) + 624LL);
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 688LL) = 0;
      v5 = *(struct _CARD_STATE **)(a1 + 16);
    }
    CardBySerialNumber = TransactionManagerBegin(v5);
    if ( !CardBySerialNumber )
      v8 = 0;
  }
LABEL_11:
  WppTraceIndent(v2, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardBySerialNumber);
  }
  v7 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v7);
  return CardBySerialNumber;
}

```

## disassembly

```asm
0x1800146c4  mov     rax, rsp
0x1800146c7  mov     [rax+8], rbx
0x1800146cb  mov     [rax+18h], rbp
0x1800146cf  mov     [rax+10h], edx
0x1800146d2  push    rdi
0x1800146d3  push    r12
0x1800146d5  push    r15
0x1800146d7  sub     rsp, 40h
0x1800146db  lea     r15, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x1800146e2  mov     dword ptr [rax+10h], 0
0x1800146e9  xor     edx, edx
0x1800146eb  mov     [rax-28h], r15
0x1800146ef  mov     rdi, rcx
0x1800146f2  mov     qword ptr [rax-20h], 0
0x1800146fa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800146ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180014706  lea     r12, WPP_GLOBAL_Control
0x18001470d  cmp     rcx, r12
0x180014710  jz      short loc_18001473A
0x180014712  test    byte ptr [rcx+1Ch], 2
0x180014716  jz      short loc_18001473A
0x180014718  cmp     byte ptr [rcx+19h], 5
0x18001471c  jb      short loc_18001473A
0x18001471e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180014725  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001472c  mov     rcx, [rcx+10h]
0x180014730  mov     edx, 1Bh
0x180014735  call    WPP_SF_s
0x18001473a  mov     rcx, [rdi+10h]
0x18001473e  mov     ebp, 270h
0x180014743  add     rcx, rbp
0x180014746  call    KspEnterCriticalSection
0x18001474b  mov     ebx, eax
0x18001474d  test    eax, eax
0x18001474f  jnz     loc_1800147E9
0x180014755  mov     rdx, [rdi+10h]
0x180014759  lea     rcx, [rsp+58h+var_28]
0x18001475e  add     rdx, rbp
0x180014761  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180014766  mov     rcx, [rdi+10h]; struct _CARD_STATE *
0x18001476a  lea     r8, [rsp+58h+arg_8]
0x18001476f  call    ValidateCardHandle
0x180014774  cmp     [rsp+58h+arg_8], 1
0x180014779  mov     ebx, eax
0x18001477b  jnz     short loc_18001478F
0x18001477d  mov     edx, [rdi+38h]
0x180014780  mov     r8d, 1
0x180014786  mov     rcx, [rdi+10h]
0x18001478a  call    CspRemoveCachedPin
0x18001478f  mov     rcx, [rdi+10h]
0x180014793  test    ebx, ebx
0x180014795  jz      short loc_1800147D5
0x180014797  add     rcx, rbp
0x18001479a  mov     [rsp+58h+var_20], 0
0x1800147a3  call    KspLeaveCriticalSection
0x1800147a8  mov     rcx, rdi
0x1800147ab  call    KsppFindCardBySerialNumber
0x1800147b0  mov     ebx, eax
0x1800147b2  test    eax, eax
0x1800147b4  jnz     short loc_1800147E9
0x1800147b6  mov     rdx, [rdi+10h]
0x1800147ba  lea     rcx, [rsp+58h+var_28]
0x1800147bf  add     rdx, rbp
0x1800147c2  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x1800147c7  mov     rax, [rdi+10h]
0x1800147cb  mov     [rax+2B0h], ebx
0x1800147d1  mov     rcx, [rdi+10h]; struct _CARD_STATE *
0x1800147d5  call    TransactionManagerBegin
0x1800147da  mov     ebx, eax
0x1800147dc  test    eax, eax
0x1800147de  jnz     short loc_1800147E9
0x1800147e0  mov     [rsp+58h+var_20], 0
0x1800147e9  mov     edx, 1
0x1800147ee  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800147f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147fa  cmp     rcx, r12
0x1800147fd  jz      short loc_18001482B
0x1800147ff  test    byte ptr [rcx+1Ch], 2
0x180014803  jz      short loc_18001482B
0x180014805  cmp     byte ptr [rcx+19h], 5
0x180014809  jb      short loc_18001482B
0x18001480b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180014812  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180014819  mov     rcx, [rcx+10h]
0x18001481d  mov     edx, 1Ch
0x180014822  mov     [rsp+58h+var_38], ebx
0x180014826  call    WPP_SF_sd
0x18001482b  lea     rcx, [rsp+58h+var_28]
0x180014830  mov     [rsp+58h+var_28], r15
0x180014835  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18001483a  mov     rbp, [rsp+58h+arg_10]
0x18001483f  mov     eax, ebx
0x180014841  mov     rbx, [rsp+58h+arg_0]
0x180014846  add     rsp, 40h
0x18001484a  pop     r15
0x18001484c  pop     r12
0x18001484e  pop     rdi
0x18001484f  retn
```
