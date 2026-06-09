# RemoveStaleCardStatesFromCache(unsigned __int64,_RTL_CRITICAL_SECTION *,ulong,_LARGE_INTEGER)

- ea: `0x180034aa0`
- end: `0x180034deb`
- name: `?RemoveStaleCardStatesFromCache@@YAK_KPEAU_RTL_CRITICAL_SECTION@@KT_LARGE_INTEGER@@@Z`
- size: `843`
- prototype: `unsigned int __fastcall(unsigned __int64, struct _RTL_CRITICAL_SECTION *, unsigned int, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180035d6c`

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x180030950`
- `0x180030a84`
- `0x180030ba8`
- `0x1800321f8`
- `0x180034aa0`
- `0x18003ae44`
- `0x18003aec8`
- `0x18003c240`

## pseudocode

```c
__int64 __fastcall RemoveStaleCardStatesFromCache(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2,
        int a3,
        union _LARGE_INTEGER a4)
{
  int v4; // r15d
  __int64 v6; // rsi
  __int64 v8; // rcx
  unsigned int v9; // eax
  PVOID v10; // rcx
  void **v11; // r13
  unsigned int CardLookupName; // edi
  unsigned int i; // r14d
  __int64 *v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rax
  __int64 v19; // rcx
  void *v20; // r12
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  void **v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v28[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = a3;
  v26 = a3;
  v27 = a2;
  v6 = a1;
  v24 = 0;
  v23 = 0;
  memset_0(v28, 0, 0x208u);
  WppTraceIndent(v8, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v9 = ScCacheEnumCardStates(a2, v6, &v24, &v23);
  v11 = v24;
  CardLookupName = v9;
  if ( v9 )
    goto LABEL_30;
  for ( i = 0; ; ++i )
  {
    if ( i >= v23 )
      goto LABEL_29;
    v14 = (__int64 *)v11[2 * i + 1];
    v15 = *v14;
    if ( v4 != *(_DWORD *)(*v14 + 716) )
      continue;
    CardLookupName = CspEnterCriticalSection(v15 + 624);
    if ( CardLookupName )
      break;
    v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    v25 = v15 + 624;
    if ( a4.QuadPart != *(_QWORD *)(v15 + 720) )
    {
      CardLookupName = GetCardLookupName((struct _CARD_STATE *)v15, v28);
      if ( CardLookupName )
      {
        WppTraceIndent(v17, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
            (_DWORD)WPP_pszIndent,
            CardLookupName);
        }
        goto LABEL_20;
      }
      v18 = MIDL_user_allocate(*(unsigned int *)(v15 + 560));
      v20 = v18;
      if ( !v18 )
      {
        WppTraceIndent(v19, 2u);
        CardLookupName = 8;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
            WPP_pszIndent);
        }
LABEL_20:
        v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v24);
        goto LABEL_29;
      }
      memcpy_0(v18, *(const void **)(v15 + 552), *(unsigned int *)(v15 + 560));
      v25 = 0;
      CspLeaveCriticalSection(v15 + 624);
      ScCacheDeleteCardState(v27, a1, v20, v28);
      CspFreeH(v20);
      v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v24);
    v4 = v26;
  }
  WppTraceIndent(v16, 2u);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardLookupName);
  }
LABEL_29:
  v6 = a1;
LABEL_30:
  if ( v11 )
    ScCacheFreeEnumCardStates(v6, v11, v23);
  WppTraceIndent((__int64)v10, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardLookupName);
  }
  return CardLookupName;
}

```

## disassembly

```asm
0x180034aa0  mov     [rsp-8+arg_10], rbx
0x180034aa5  push    rbp
0x180034aa6  push    rsi
0x180034aa7  push    rdi
0x180034aa8  push    r12
0x180034aaa  push    r13
0x180034aac  push    r14
0x180034aae  push    r15
0x180034ab0  lea     rbp, [rsp-180h]
0x180034ab8  sub     rsp, 280h
0x180034abf  mov     rax, cs:__security_cookie
0x180034ac6  xor     rax, rsp
0x180034ac9  mov     [rbp+1B0h+var_40], rax
0x180034ad0  mov     r15d, r8d
0x180034ad3  mov     [rsp+2B0h+var_260], r8d
0x180034ad8  mov     rdi, rdx
0x180034adb  mov     [rsp+2B0h+var_258], rdx
0x180034ae0  mov     rsi, rcx
0x180034ae3  mov     [rsp+2B0h+var_280], rcx
0x180034ae8  xor     edx, edx; Val
0x180034aea  mov     [rsp+2B0h+var_270], 0
0x180034af3  mov     r8d, 208h; Size
0x180034af9  mov     [rsp+2B0h+var_278], 0
0x180034b01  lea     rcx, [rsp+2B0h+var_250]; void *
0x180034b06  mov     rbx, r9
0x180034b09  call    memset_0
0x180034b0e  xor     edx, edx
0x180034b10  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b1c  lea     r12, WPP_GLOBAL_Control
0x180034b23  cmp     rcx, r12
0x180034b26  jz      short loc_180034B50
0x180034b28  test    byte ptr [rcx+1Ch], 2
0x180034b2c  jz      short loc_180034B50
0x180034b2e  cmp     byte ptr [rcx+19h], 5
0x180034b32  jb      short loc_180034B50
0x180034b34  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034b3b  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034b42  mov     rcx, [rcx+10h]
0x180034b46  mov     edx, 12h
0x180034b4b  call    WPP_SF_s
0x180034b50  lea     r9, [rsp+2B0h+var_278]
0x180034b55  mov     rdx, rsi
0x180034b58  lea     r8, [rsp+2B0h+var_270]
0x180034b5d  mov     rcx, rdi
0x180034b60  call    ScCacheEnumCardStates
0x180034b65  mov     r13, [rsp+2B0h+var_270]
0x180034b6a  mov     edi, eax
0x180034b6c  test    eax, eax
0x180034b6e  jnz     loc_180034D68
0x180034b74  xor     r14d, r14d
0x180034b77  lea     r12, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180034b7e  cmp     r14d, [rsp+2B0h+var_278]
0x180034b83  jnb     loc_180034D5C
0x180034b89  mov     eax, r14d
0x180034b8c  add     rax, rax
0x180034b8f  mov     rax, [r13+rax*8+8]
0x180034b94  mov     rsi, [rax]
0x180034b97  cmp     r15d, [rsi+2CCh]
0x180034b9e  jnz     loc_180034C5B
0x180034ba4  lea     r15, [rsi+270h]
0x180034bab  mov     rcx, r15
0x180034bae  call    CspEnterCriticalSection
0x180034bb3  mov     edi, eax
0x180034bb5  test    eax, eax
0x180034bb7  jnz     loc_180034D11
0x180034bbd  mov     [rsp+2B0h+var_270], r12
0x180034bc2  mov     [rsp+2B0h+var_268], r15
0x180034bc7  cmp     rbx, [rsi+2D0h]
0x180034bce  jz      short loc_180034C4C
0x180034bd0  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180034bd5  mov     rcx, rsi; struct _CARD_STATE *
0x180034bd8  call    ?GetCardLookupName@@YAKPEAU_CARD_STATE@@PEAGK@Z; GetCardLookupName(_CARD_STATE *,ushort *,ulong)
0x180034bdd  mov     edi, eax
0x180034bdf  test    eax, eax
0x180034be1  jnz     loc_180034CC6
0x180034be7  mov     ecx, [rsi+230h]; size
0x180034bed  call    MIDL_user_allocate
0x180034bf2  mov     r12, rax
0x180034bf5  test    rax, rax
0x180034bf8  jz      short loc_180034C63
0x180034bfa  mov     r8d, [rsi+230h]; Size
0x180034c01  mov     rcx, rax; void *
0x180034c04  mov     rdx, [rsi+228h]; Src
0x180034c0b  call    memcpy_0
0x180034c10  mov     rcx, r15
0x180034c13  mov     [rsp+2B0h+var_268], 0
0x180034c1c  call    CspLeaveCriticalSection
0x180034c21  mov     rdx, [rsp+2B0h+var_280]
0x180034c26  lea     r9, [rsp+2B0h+var_250]
0x180034c2b  mov     rcx, [rsp+2B0h+var_258]
0x180034c30  mov     r8, r12
0x180034c33  call    ScCacheDeleteCardState
0x180034c38  mov     rcx, r12
0x180034c3b  call    CspFreeH
0x180034c40  lea     r12, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180034c47  mov     [rsp+2B0h+var_270], r12
0x180034c4c  lea     rcx, [rsp+2B0h+var_270]
0x180034c51  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180034c56  mov     r15d, [rsp+2B0h+var_260]
0x180034c5b  inc     r14d
0x180034c5e  jmp     loc_180034B7E
0x180034c63  mov     edx, 2
0x180034c68  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034c6d  mov     edi, 8
0x180034c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c79  lea     r12, WPP_GLOBAL_Control
0x180034c80  cmp     rcx, r12
0x180034c83  jz      short loc_180034CAB
0x180034c85  test    byte ptr [rcx+1Ch], 1
0x180034c89  jz      short loc_180034CAB
0x180034c8b  cmp     byte ptr [rcx+19h], 2
0x180034c8f  jb      short loc_180034CAB
0x180034c91  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034c98  lea     edx, [rdi+0Dh]
0x180034c9b  mov     rcx, [rcx+10h]
0x180034c9f  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034ca6  call    WPP_SF_s
0x180034cab  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180034cb2  lea     rcx, [rsp+2B0h+var_270]
0x180034cb7  mov     [rsp+2B0h+var_270], rax
0x180034cbc  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180034cc1  jmp     loc_180034D63
0x180034cc6  mov     edx, 2
0x180034ccb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180034cd7  lea     r12, WPP_GLOBAL_Control
0x180034cde  cmp     rcx, r12
0x180034ce1  jz      short loc_180034CAB
0x180034ce3  test    byte ptr [rcx+1Ch], 1
0x180034ce7  jz      short loc_180034CAB
0x180034ce9  cmp     byte ptr [rcx+19h], 2
0x180034ced  jb      short loc_180034CAB
0x180034cef  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034cf6  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034cfd  mov     rcx, [rcx+10h]
0x180034d01  mov     edx, 14h
0x180034d06  mov     [rsp+2B0h+var_290], edi
0x180034d0a  call    WPP_SF_sd
0x180034d0f  jmp     short loc_180034CAB
0x180034d11  mov     edx, 2
0x180034d16  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d22  lea     r12, WPP_GLOBAL_Control
0x180034d29  cmp     rcx, r12
0x180034d2c  jz      short loc_180034D63
0x180034d2e  test    byte ptr [rcx+1Ch], 1
0x180034d32  jz      short loc_180034D63
0x180034d34  cmp     byte ptr [rcx+19h], 2
0x180034d38  jb      short loc_180034D63
0x180034d3a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034d41  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034d48  mov     rcx, [rcx+10h]
0x180034d4c  mov     edx, 13h
0x180034d51  mov     [rsp+2B0h+var_290], edi
0x180034d55  call    WPP_SF_sd
0x180034d5a  jmp     short loc_180034D63
0x180034d5c  lea     r12, WPP_GLOBAL_Control
0x180034d63  mov     rsi, [rsp+2B0h+var_280]
0x180034d68  test    r13, r13
0x180034d6b  jz      short loc_180034D7D
0x180034d6d  mov     r8d, [rsp+2B0h+var_278]
0x180034d72  mov     rdx, r13
0x180034d75  mov     rcx, rsi
0x180034d78  call    ScCacheFreeEnumCardStates
0x180034d7d  mov     edx, 1
0x180034d82  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034d87  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d8e  cmp     rcx, r12
0x180034d91  jz      short loc_180034DBF
0x180034d93  test    byte ptr [rcx+1Ch], 2
0x180034d97  jz      short loc_180034DBF
0x180034d99  cmp     byte ptr [rcx+19h], 5
0x180034d9d  jb      short loc_180034DBF
0x180034d9f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034da6  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034dad  mov     rcx, [rcx+10h]
0x180034db1  mov     edx, 16h
0x180034db6  mov     [rsp+2B0h+var_290], edi
0x180034dba  call    WPP_SF_sd
0x180034dbf  mov     eax, edi
0x180034dc1  mov     rcx, [rbp+1B0h+var_40]
0x180034dc8  xor     rcx, rsp; StackCookie
0x180034dcb  call    __security_check_cookie
0x180034dd0  mov     rbx, [rsp+2B0h+arg_10]
0x180034dd8  add     rsp, 280h
0x180034ddf  pop     r15
0x180034de1  pop     r14
0x180034de3  pop     r13
0x180034de5  pop     r12
0x180034de7  pop     rdi
0x180034de8  pop     rsi
0x180034de9  pop     rbp
0x180034dea  retn
```
