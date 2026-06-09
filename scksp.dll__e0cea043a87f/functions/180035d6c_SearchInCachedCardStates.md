# SearchInCachedCardStates

- ea: `0x180035d6c`
- end: `0x1800361b9`
- name: `SearchInCachedCardStates`
- size: `1101`
- prototype: `__int64 __fastcall(struct _CARD_MATCH_DATA *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800354b8`

## callees

- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x180013734`
- `0x18002b1f8`
- `0x18002e034`
- `0x18002e7a0`
- `0x180030a84`
- `0x180030ba8`
- `0x180032b58`
- `0x180033794`
- `0x180033dec`
- `0x180034694`
- `0x180034aa0`
- `0x180035d6c`
- `0x18003ae44`
- `0x18003b788`
- `0x18003b858`

## pseudocode

```c
__int64 __fastcall SearchInCachedCardStates(struct _CARD_MATCH_DATA *a1, _QWORD *a2)
{
  __int64 v3; // rcx
  unsigned int SessionID; // ebx
  _QWORD *v5; // rcx
  int v6; // edx
  __int64 v7; // rcx
  unsigned int v8; // r15d
  unsigned int v9; // eax
  void **v10; // r13
  unsigned int i; // r12d
  __int64 v12; // rdi
  __int64 v13; // rcx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rcx
  int v16; // r9d
  _QWORD *v17; // rcx
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rcx
  union _LARGE_INTEGER v22; // [rsp+38h] [rbp-18h] BYREF
  void **v23; // [rsp+40h] [rbp-10h] BYREF
  __int64 v24; // [rsp+48h] [rbp-8h]
  unsigned int TokenInformation; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+58h] BYREF

  TokenInformation = 0;
  v22.QuadPart = 0;
  v27 = 0;
  v23 = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  SessionID = GetSessionID(&TokenInformation, &v22);
  if ( SessionID )
  {
    WppTraceIndent(v3, 2u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 121;
LABEL_10:
      WPP_SF_sd(
        v5[2],
        v6,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        SessionID);
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  SessionID = RemoveStaleCardStatesFromCache(
                *((_QWORD *)a1 + 3),
                *((struct _RTL_CRITICAL_SECTION **)a1 + 2),
                TokenInformation,
                v22);
  if ( !SessionID )
  {
    v8 = 1168;
    v9 = ScCacheEnumCardStates(*((_QWORD *)a1 + 2), *((_QWORD *)a1 + 3), &v23, &v27);
    v10 = v23;
    SessionID = v9;
    if ( v9 )
    {
LABEL_51:
      if ( v10 )
        ScCacheFreeEnumCardStates(*((_QWORD *)a1 + 3), v10, v27);
      if ( v8 && !SessionID )
        SessionID = v8;
      goto LABEL_56;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v27 || !v8 )
        goto LABEL_51;
      v12 = *(_QWORD *)v10[2 * i + 1];
      if ( TokenInformation == *(_DWORD *)(v12 + 716) )
        break;
LABEL_46:
      ;
    }
    SessionID = CspEnterCriticalSection(v12 + 624);
    if ( SessionID )
    {
      WppTraceIndent(v13, 2u);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          SessionID);
      }
      goto LABEL_51;
    }
    v14 = (unsigned __int16 *)*((_QWORD *)a1 + 145);
    v23 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    v24 = v12 + 624;
    if ( (unsigned int)MatchesRequiredReaderName(v14, (unsigned __int16 *)(v12 + 32))
      && (unsigned int)MatchesRequiredContainerNameInKnownContainers(
                         *((unsigned __int16 **)a1 + 146),
                         *(struct _CONTAINER_MAP_RECORD **)(v12 + 568),
                         *(_DWORD *)(v12 + 576)) )
    {
      if ( *(_QWORD *)(v12 + 8) )
        SessionID = ValidateCardHandle((struct _CARD_STATE *)v12);
      if ( !SessionID )
      {
        SessionID = TransactionManagerBegin((struct _CARD_STATE *)v12);
        if ( SessionID )
        {
          WppTraceIndent(v15, 2u);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_45;
          }
          v18 = 124;
          goto LABEL_32;
        }
        v8 = MatchBySerialAndUserParameters(a1, (struct _CARD_STATE *)v12);
        if ( v8 )
        {
          WppTraceIndent(v19, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              125,
              (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
              (_DWORD)WPP_pszIndent,
              v8);
          }
          SessionID = TransactionManagerEnd((struct _CARD_STATE *)v12);
          if ( !SessionID )
            goto LABEL_45;
          WppTraceIndent(v20, 2u);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_45;
          }
          v18 = 126;
LABEL_32:
          WPP_SF_sDq(v17[2], v18, (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, v16, SessionID, v12);
          goto LABEL_45;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 692));
        v24 = 0;
        *a2 = v12;
      }
    }
LABEL_45:
    v23 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v23);
    goto LABEL_46;
  }
  WppTraceIndent(v7, 2u);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 122;
    goto LABEL_10;
  }
LABEL_56:
  WppTraceIndent((__int64)v5, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      127,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      SessionID);
  }
  return SessionID;
}

```

## disassembly

```asm
0x180035d6c  mov     [rsp-38h+arg_0], rbx
0x180035d71  mov     [rsp-38h+arg_8], rdx
0x180035d76  push    rbp
0x180035d77  push    rsi
0x180035d78  push    rdi
0x180035d79  push    r12
0x180035d7b  push    r13
0x180035d7d  push    r14
0x180035d7f  push    r15
0x180035d81  mov     rbp, rsp
0x180035d84  sub     rsp, 50h
0x180035d88  xor     edx, edx
0x180035d8a  mov     [rbp+TokenInformation], 0
0x180035d91  mov     r14, rcx
0x180035d94  mov     qword ptr [rbp+var_18], 0
0x180035d9c  mov     [rbp+arg_18], 0
0x180035da3  mov     [rbp+var_10], 0
0x180035dab  mov     [rbp+var_20], 0
0x180035db2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180035dbe  lea     rsi, WPP_GLOBAL_Control
0x180035dc5  cmp     rcx, rsi
0x180035dc8  jz      short loc_180035DF2
0x180035dca  test    byte ptr [rcx+1Ch], 2
0x180035dce  jz      short loc_180035DF2
0x180035dd0  cmp     byte ptr [rcx+19h], 5
0x180035dd4  jb      short loc_180035DF2
0x180035dd6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180035ddd  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180035de4  mov     rcx, [rcx+10h]
0x180035de8  mov     edx, 78h ; 'x'
0x180035ded  call    WPP_SF_s
0x180035df2  lea     rdx, [rbp+var_18]; union _LARGE_INTEGER *
0x180035df6  lea     rcx, [rbp+TokenInformation]; TokenInformation
0x180035dfa  call    ?GetSessionID@@YAKPEAKPEAT_LARGE_INTEGER@@@Z; GetSessionID(ulong *,_LARGE_INTEGER *)
0x180035dff  mov     ebx, eax
0x180035e01  test    eax, eax
0x180035e03  jz      short loc_180035E58
0x180035e05  mov     edx, 2
0x180035e0a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e16  cmp     rcx, rsi
0x180035e19  jz      loc_18003615D
0x180035e1f  test    byte ptr [rcx+1Ch], 1
0x180035e23  jz      loc_18003615D
0x180035e29  cmp     byte ptr [rcx+19h], 2
0x180035e2d  jb      loc_18003615D
0x180035e33  mov     edx, 79h ; 'y'
0x180035e38  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180035e3f  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180035e46  mov     rcx, [rcx+10h]
0x180035e4a  mov     [rsp+50h+var_30], ebx
0x180035e4e  call    WPP_SF_sd
0x180035e53  jmp     loc_18003615D
0x180035e58  mov     r9, qword ptr [rbp+var_18]; union _LARGE_INTEGER
0x180035e5c  mov     r8d, [rbp+TokenInformation]; unsigned int
0x180035e60  mov     rdx, [r14+10h]; struct _RTL_CRITICAL_SECTION *
0x180035e64  mov     rcx, [r14+18h]; unsigned __int64
0x180035e68  call    ?RemoveStaleCardStatesFromCache@@YAK_KPEAU_RTL_CRITICAL_SECTION@@KT_LARGE_INTEGER@@@Z; RemoveStaleCardStatesFromCache(unsigned __int64,_RTL_CRITICAL_SECTION *,ulong,_LARGE_INTEGER)
0x180035e6d  mov     ebx, eax
0x180035e6f  test    eax, eax
0x180035e71  jz      short loc_180035EA8
0x180035e73  mov     edx, 2
0x180035e78  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e84  cmp     rcx, rsi
0x180035e87  jz      loc_18003615D
0x180035e8d  test    byte ptr [rcx+1Ch], 1
0x180035e91  jz      loc_18003615D
0x180035e97  cmp     byte ptr [rcx+19h], 2
0x180035e9b  jb      loc_18003615D
0x180035ea1  mov     edx, 7Ah ; 'z'
0x180035ea6  jmp     short loc_180035E38
0x180035ea8  mov     rdx, [r14+18h]
0x180035eac  lea     r9, [rbp+arg_18]
0x180035eb0  mov     rcx, [r14+10h]
0x180035eb4  lea     r8, [rbp+var_10]
0x180035eb8  mov     r15d, 490h
0x180035ebe  call    ScCacheEnumCardStates
0x180035ec3  mov     r13, [rbp+var_10]
0x180035ec7  mov     ebx, eax
0x180035ec9  test    eax, eax
0x180035ecb  jnz     loc_18003613D
0x180035ed1  xor     r12d, r12d
0x180035ed4  cmp     r12d, [rbp+arg_18]
0x180035ed8  jnb     loc_18003613D
0x180035ede  test    r15d, r15d
0x180035ee1  jz      loc_18003613D
0x180035ee7  mov     eax, r12d
0x180035eea  add     rax, rax
0x180035eed  mov     rax, [r13+rax*8+8]
0x180035ef2  mov     rdi, [rax]
0x180035ef5  mov     eax, [rdi+2CCh]
0x180035efb  cmp     [rbp+TokenInformation], eax
0x180035efe  jnz     loc_1800360EC
0x180035f04  lea     rsi, [rdi+270h]
0x180035f0b  mov     rcx, rsi
0x180035f0e  call    CspEnterCriticalSection
0x180035f13  mov     ebx, eax
0x180035f15  test    eax, eax
0x180035f17  jnz     loc_1800360F4
0x180035f1d  mov     rcx, [r14+488h]; unsigned __int16 *
0x180035f24  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180035f2b  lea     rdx, [rdi+20h]; unsigned __int16 *
0x180035f2f  mov     [rbp+var_10], rax
0x180035f33  mov     [rbp+var_8], rsi
0x180035f37  call    ?MatchesRequiredReaderName@@YAHPEAG0@Z; MatchesRequiredReaderName(ushort *,ushort *)
0x180035f3c  test    eax, eax
0x180035f3e  jz      loc_1800360D1
0x180035f44  mov     r8d, [rdi+240h]; unsigned int
0x180035f4b  mov     rdx, [rdi+238h]; struct _CONTAINER_MAP_RECORD *
0x180035f52  mov     rcx, [r14+490h]; Buf1
0x180035f59  call    ?MatchesRequiredContainerNameInKnownContainers@@YAHPEAGPEAU_CONTAINER_MAP_RECORD@@K@Z; MatchesRequiredContainerNameInKnownContainers(ushort *,_CONTAINER_MAP_RECORD *,ulong)
0x180035f5e  test    eax, eax
0x180035f60  jz      loc_1800360D1
0x180035f66  cmp     qword ptr [rdi+8], 0
0x180035f6b  jz      short loc_180035F7B
0x180035f6d  lea     r8, [rbp+var_20]
0x180035f71  mov     rcx, rdi; struct _CARD_STATE *
0x180035f74  call    ValidateCardHandle
0x180035f79  mov     ebx, eax
0x180035f7b  cmp     [rbp+var_20], 1
0x180035f7f  jnz     short loc_180035F9B
0x180035f81  cmp     qword ptr [rdi+248h], 0
0x180035f89  jz      short loc_180035F9B
0x180035f8b  mov     edx, 1
0x180035f90  mov     rcx, rdi
0x180035f93  mov     r8d, edx
0x180035f96  call    CspRemoveCachedPin
0x180035f9b  test    ebx, ebx
0x180035f9d  jnz     loc_1800360D1
0x180035fa3  mov     rcx, rdi; struct _CARD_STATE *
0x180035fa6  call    TransactionManagerBegin
0x180035fab  mov     ebx, eax
0x180035fad  test    eax, eax
0x180035faf  jz      short loc_180036011
0x180035fb1  mov     edx, 2
0x180035fb6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fc2  lea     rsi, WPP_GLOBAL_Control
0x180035fc9  cmp     rcx, rsi
0x180035fcc  jz      short loc_180035FF8
0x180035fce  test    byte ptr [rcx+1Ch], 1
0x180035fd2  jz      short loc_180035FF8
0x180035fd4  cmp     byte ptr [rcx+19h], 4
0x180035fd8  jb      short loc_180035FF8
0x180035fda  mov     edx, 7Ch ; '|'
0x180035fdf  mov     rcx, [rcx+10h]
0x180035fe3  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180035fea  mov     [rsp+50h+var_28], rdi
0x180035fef  mov     [rsp+50h+var_30], ebx
0x180035ff3  call    WPP_SF_sDq
0x180035ff8  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180035fff  lea     rcx, [rbp+var_10]
0x180036003  mov     [rbp+var_10], rax
0x180036007  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18003600c  jmp     loc_1800360EC
0x180036011  mov     rdx, rdi; struct _CARD_STATE *
0x180036014  mov     rcx, r14; struct _CARD_MATCH_DATA *
0x180036017  call    ?MatchBySerialAndUserParameters@@YAKPEAU_CARD_MATCH_DATA@@PEAU_CARD_STATE@@@Z; MatchBySerialAndUserParameters(_CARD_MATCH_DATA *,_CARD_STATE *)
0x18003601c  mov     r15d, eax
0x18003601f  test    eax, eax
0x180036021  jz      loc_1800360BB
0x180036027  mov     edx, 2
0x18003602c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180036031  mov     rcx, cs:WPP_GLOBAL_Control
0x180036038  lea     rsi, WPP_GLOBAL_Control
0x18003603f  cmp     rcx, rsi
0x180036042  jz      short loc_180036071
0x180036044  test    byte ptr [rcx+1Ch], 1
0x180036048  jz      short loc_180036071
0x18003604a  cmp     byte ptr [rcx+19h], 4
0x18003604e  jb      short loc_180036071
0x180036050  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180036057  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003605e  mov     rcx, [rcx+10h]
0x180036062  mov     edx, 7Dh ; '}'
0x180036067  mov     [rsp+50h+var_30], r15d
0x18003606c  call    WPP_SF_sd
0x180036071  mov     rcx, rdi; struct _CARD_STATE *
0x180036074  call    TransactionManagerEnd
0x180036079  mov     ebx, eax
0x18003607b  test    eax, eax
0x18003607d  jz      loc_180035FF8
0x180036083  mov     edx, 2
0x180036088  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003608d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036094  cmp     rcx, rsi
0x180036097  jz      loc_180035FF8
0x18003609d  test    byte ptr [rcx+1Ch], 1
0x1800360a1  jz      loc_180035FF8
0x1800360a7  cmp     byte ptr [rcx+19h], 4
0x1800360ab  jb      loc_180035FF8
0x1800360b1  mov     edx, 7Eh ; '~'
0x1800360b6  jmp     loc_180035FDF
0x1800360bb  lock inc dword ptr [rdi+2B4h]
0x1800360c2  mov     rax, [rbp+arg_8]
0x1800360c6  mov     [rbp+var_8], 0
0x1800360ce  mov     [rax], rdi
0x1800360d1  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x1800360d8  lea     rcx, [rbp+var_10]
0x1800360dc  mov     [rbp+var_10], rax
0x1800360e0  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x1800360e5  lea     rsi, WPP_GLOBAL_Control
0x1800360ec  inc     r12d
0x1800360ef  jmp     loc_180035ED4
0x1800360f4  mov     edx, 2
0x1800360f9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800360fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180036105  lea     rsi, WPP_GLOBAL_Control
0x18003610c  cmp     rcx, rsi
0x18003610f  jz      short loc_18003613D
0x180036111  test    byte ptr [rcx+1Ch], 1
0x180036115  jz      short loc_18003613D
0x180036117  cmp     byte ptr [rcx+19h], 2
0x18003611b  jb      short loc_18003613D
0x18003611d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180036124  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003612b  mov     rcx, [rcx+10h]
0x18003612f  mov     edx, 7Bh ; '{'
0x180036134  mov     [rsp+50h+var_30], ebx
0x180036138  call    WPP_SF_sd
0x18003613d  test    r13, r13
0x180036140  jz      short loc_180036152
0x180036142  mov     r8d, [rbp+arg_18]
0x180036146  mov     rdx, r13
0x180036149  mov     rcx, [r14+18h]
0x18003614d  call    ScCacheFreeEnumCardStates
0x180036152  test    r15d, r15d
0x180036155  jz      short loc_18003615D
0x180036157  test    ebx, ebx
0x180036159  cmovz   ebx, r15d
0x18003615d  mov     edx, 1
0x180036162  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180036167  mov     rcx, cs:WPP_GLOBAL_Control
0x18003616e  cmp     rcx, rsi
0x180036171  jz      short loc_18003619F
0x180036173  test    byte ptr [rcx+1Ch], 2
0x180036177  jz      short loc_18003619F
0x180036179  cmp     byte ptr [rcx+19h], 5
0x18003617d  jb      short loc_18003619F
0x18003617f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180036186  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003618d  mov     rcx, [rcx+10h]
0x180036191  mov     edx, 7Fh
0x180036196  mov     [rsp+50h+var_30], ebx
0x18003619a  call    WPP_SF_sd
0x18003619f  mov     eax, ebx
0x1800361a1  mov     rbx, [rsp+50h+arg_0]
0x1800361a9  add     rsp, 50h
0x1800361ad  pop     r15
0x1800361af  pop     r14
0x1800361b1  pop     r13
0x1800361b3  pop     r12
0x1800361b5  pop     rdi
0x1800361b6  pop     rsi
0x1800361b7  pop     rbp
0x1800361b8  retn
```
