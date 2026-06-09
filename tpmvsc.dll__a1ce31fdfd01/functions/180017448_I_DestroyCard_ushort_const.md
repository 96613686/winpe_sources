# I_DestroyCard(ushort const *)

- ea: `0x180017448`
- end: `0x180017829`
- name: `?I_DestroyCard@@YAKPEBG@Z`
- size: `993`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800259c8`
- `0x18002c51c`

## callees

- `0x180001ec0`
- `0x180009154`
- `0x18000bc48`
- `0x18000c0c8`
- `0x18000c198`
- `0x1800162b4`
- `0x180016378`
- `0x1800163e8`
- `0x180016740`
- `0x18001679c`
- `0x18001690c`
- `0x180017448`
- `0x18001fd8c`
- `0x1800201f0`
- `0x1800291ec`
- `0x1800292e8`
- `0x1800297cc`
- `0x1800348a0`

## string_xrefs

- `0x180017638`: `The channel cannot be opened`

## pseudocode

```c
__int64 __fastcall I_DestroyCard(const unsigned __int16 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned __int8 i; // di
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v14; // [rsp+30h] [rbp-39h] BYREF
  struct VCHANNEL_DATA *v15; // [rsp+38h] [rbp-31h] BYREF
  int v16; // [rsp+40h] [rbp-29h] BYREF
  struct VCARD_DATA *v17; // [rsp+48h] [rbp-21h] BYREF
  struct VCARD_DATA **v18; // [rsp+50h] [rbp-19h] BYREF
  __int16 v19; // [rsp+58h] [rbp-11h]
  struct VCARD_DATA **v20; // [rsp+60h] [rbp-9h] BYREF
  __int16 v21; // [rsp+68h] [rbp-1h]
  struct VCHANNEL_DATA **v22; // [rsp+70h] [rbp+7h] BYREF
  _QWORD *v23; // [rsp+78h] [rbp+Fh] BYREF
  struct VCHANNEL_DATA **v24; // [rsp+80h] [rbp+17h] BYREF
  __int16 v25; // [rsp+88h] [rbp+1Fh]
  _QWORD v26[3]; // [rsp+90h] [rbp+27h] BYREF
  char v27[16]; // [rsp+A8h] [rbp+3Fh] BYREF

  v14 = 0;
  v16 = 0;
  strcpy(v27, "I_DestroyCard");
  v26[0] = v27;
  v26[1] = &v16;
  v26[2] = &v14;
  lambda_8f3c3355ceaca74c92f9c41a25916dc0_::operator()(v26);
  v16 = 1;
  v23 = v26;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  v17 = 0;
  v14 = I_VCardDataInitialize((void *(*)(unsigned __int64))I_InternalAlloc, (void (*)(void *))I_InternalFree, &v17);
  if ( v14 )
  {
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        v14,
        (__int64)"The card cannot be initialized");
    }
    v5 = v14;
    goto LABEL_45;
  }
  v18 = &v17;
  v19 = 258;
  v14 = I_VCardDataOpenLocking(v17, a1);
  if ( v14 )
  {
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        v14,
        (__int64)"The card cannot be loaded");
    }
    v5 = v14;
LABEL_15:
    wil::details::ScopeExitFnGuard__lambda_e9556ca6e1f6dd63825a5e6d49f7fe19___::operator()(&v18);
    goto LABEL_45;
  }
  v20 = &v17;
  v21 = 258;
  v15 = 0;
  v14 = I_VChannelOpen(v17, &v15);
  if ( v14 )
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids,
        (_DWORD)WPP_pszIndent,
        v14,
        (__int64)"The channel cannot be opened");
    }
    v5 = v14;
    wil::details::ScopeExitFnGuard__lambda_7afff1fa9c927d39bc73e8aff8adf638___::operator()(&v20);
    goto LABEL_15;
  }
  v24 = &v15;
  v25 = 258;
  *((_DWORD *)v15 + 16) = 3;
  for ( i = 0x80; i <= 0xA0u; ++i )
    I_DeleteKeyLocking(v15, i);
  v14 = I_DeleteReferenceData(*(_QWORD *)v15, 1);
  if ( v14 )
  {
    WppTraceIndent(v9, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids);
    }
  }
  v14 = I_DeleteReferenceData(*(_QWORD *)v15, 2);
  if ( v14 )
  {
    WppTraceIndent(v10, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids);
    }
  }
  v14 = I_DeleteKspKey(*(const struct VCARD_DATA **)v15, *(const unsigned __int16 **)(*(_QWORD *)v15 + 64LL));
  if ( v14 )
  {
    WppTraceIndent(v11, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids);
    }
  }
  v22 = &v15;
  v14 = lambda_b98ee528412eb1b785800fdcf16eb8d7_::operator()(&v22);
  if ( v14 )
  {
    WppTraceIndent(v12, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids);
    }
  }
  v14 = 0;
  wil::details::ScopeExitFnGuard__lambda_8df077a85f71db72a9008d311a7eeac9___::operator()(&v24);
  wil::details::ScopeExitFnGuard__lambda_7afff1fa9c927d39bc73e8aff8adf638___::operator()(&v20);
  wil::details::ScopeExitFnGuard__lambda_e9556ca6e1f6dd63825a5e6d49f7fe19___::operator()(&v18);
  v5 = 0;
LABEL_45:
  WppTraceUnwinder__lambda_8f3c3355ceaca74c92f9c41a25916dc0____::_WppTraceUnwinder__lambda_8f3c3355ceaca74c92f9c41a25916dc0____(&v23);
  return v5;
}

```

## disassembly

```asm
0x180017448  mov     [rsp-8+arg_8], rbx
0x18001744d  mov     [rsp-8+arg_10], rdi
0x180017452  push    rbp
0x180017453  lea     rbp, [rsp-57h]
0x180017458  sub     rsp, 0C0h
0x18001745f  mov     rax, cs:__security_cookie
0x180017466  xor     rax, rsp
0x180017469  mov     [rbp+57h+var_8], rax
0x18001746d  mov     rdi, rcx
0x180017470  mov     [rbp+57h+var_90], 0
0x180017477  mov     [rbp+57h+var_80], 0
0x18001747e  movsd   xmm0, qword ptr cs:aIDestroycard; "I_DestroyCard"
0x180017486  movsd   qword ptr [rbp+57h+var_18], xmm0
0x18001748b  mov     eax, dword ptr cs:aIDestroycard+8; "yCard"
0x180017491  mov     dword ptr [rbp+57h+var_18+8], eax
0x180017494  movzx   eax, word ptr cs:aIDestroycard+0Ch; "d"
0x18001749b  mov     word ptr [rbp+57h+var_18+0Ch], ax
0x18001749f  lea     rax, [rbp+57h+var_18]
0x1800174a3  mov     [rbp+57h+var_30], rax
0x1800174a7  lea     rax, [rbp+57h+var_80]
0x1800174ab  mov     [rbp+57h+var_28], rax
0x1800174af  lea     rax, [rbp+57h+var_90]
0x1800174b3  mov     [rbp+57h+var_20], rax
0x1800174b7  lea     rcx, [rbp+57h+var_30]
0x1800174bb  call    _lambda_8f3c3355ceaca74c92f9c41a25916dc0___operator__
0x1800174c0  mov     [rbp+57h+var_80], 1
0x1800174c7  lea     rax, [rbp+57h+var_30]
0x1800174cb  mov     [rbp+57h+var_48], rax
0x1800174cf  test    rdi, rdi
0x1800174d2  jnz     short loc_1800174D9
0x1800174d4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800174d9  mov     [rbp+57h+var_78], 0
0x1800174e1  lea     r8, [rbp+57h+var_78]; struct VCARD_DATA **
0x1800174e5  lea     rdx, ?I_InternalFree@@YAXPEAX@Z; void (*)(void *)
0x1800174ec  lea     rcx, ?I_InternalAlloc@@YAPEAX_K@Z; void *(*)(unsigned __int64)
0x1800174f3  call    ?I_VCardDataInitialize@@YAKP6APEAX_K@ZP6AXPEAX@ZPEAPEAUVCARD_DATA@@@Z; I_VCardDataInitialize(void * (*)(unsigned __int64),void (*)(void *),VCARD_DATA * *)
0x1800174f8  mov     [rbp+57h+var_90], eax
0x1800174fb  mov     ebx, 2
0x180017500  test    eax, eax
0x180017502  jz      short loc_18001755E
0x180017504  mov     edx, ebx
0x180017506  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001750b  lea     rdi, WPP_GLOBAL_Control
0x180017512  mov     rcx, cs:WPP_GLOBAL_Control
0x180017519  cmp     rcx, rdi
0x18001751c  jz      short loc_180017556
0x18001751e  test    byte ptr [rcx+1Ch], 1
0x180017522  jz      short loc_180017556
0x180017524  cmp     [rcx+19h], bl
0x180017527  jb      short loc_180017556
0x180017529  lea     edx, [rbx+20h]
0x18001752c  lea     rax, aTheCardCannotB; "The card cannot be initialized"
0x180017533  mov     [rsp+0C0h+var_98], rax
0x180017538  mov     eax, [rbp+57h+var_90]
0x18001753b  mov     [rsp+0C0h+var_A0], eax
0x18001753f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180017546  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x18001754d  mov     rcx, [rcx+10h]
0x180017551  call    WPP_SF_sDs
0x180017556  mov     ebx, [rbp+57h+var_90]
0x180017559  jmp     loc_1800177FD
0x18001755e  lea     rax, [rbp+57h+var_78]
0x180017562  mov     [rbp+57h+var_70], rax
0x180017566  mov     [rbp+57h+var_68], 102h
0x18001756c  mov     rdx, rdi; unsigned __int16 *
0x18001756f  mov     rcx, [rbp+57h+var_78]; struct VCARD_DATA *
0x180017573  call    ?I_VCardDataOpenLocking@@YAKPEAUVCARD_DATA@@PEBG@Z; I_VCardDataOpenLocking(VCARD_DATA *,ushort const *)
0x180017578  mov     [rbp+57h+var_90], eax
0x18001757b  test    eax, eax
0x18001757d  jz      short loc_1800175E4
0x18001757f  mov     edx, ebx
0x180017581  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180017586  lea     rdi, WPP_GLOBAL_Control
0x18001758d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017594  cmp     rcx, rdi
0x180017597  jz      short loc_1800175D3
0x180017599  test    byte ptr [rcx+1Ch], 1
0x18001759d  jz      short loc_1800175D3
0x18001759f  cmp     [rcx+19h], bl
0x1800175a2  jb      short loc_1800175D3
0x1800175a4  mov     edx, 23h ; '#'
0x1800175a9  lea     rax, aTheCardCannotB_0; "The card cannot be loaded"
0x1800175b0  mov     [rsp+0C0h+var_98], rax
0x1800175b5  mov     eax, [rbp+57h+var_90]
0x1800175b8  mov     [rsp+0C0h+var_A0], eax
0x1800175bc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800175c3  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x1800175ca  mov     rcx, [rcx+10h]
0x1800175ce  call    WPP_SF_sDs
0x1800175d3  mov     ebx, [rbp+57h+var_90]
0x1800175d6  lea     rcx, [rbp+57h+var_70]
0x1800175da  call    wil__details__ScopeExitFnGuard__lambda_e9556ca6e1f6dd63825a5e6d49f7fe19_____operator__
0x1800175df  jmp     loc_1800177FD
0x1800175e4  lea     rax, [rbp+57h+var_78]
0x1800175e8  mov     [rbp+57h+var_60], rax
0x1800175ec  mov     [rbp+57h+var_58], 102h
0x1800175f2  mov     [rbp+57h+var_88], 0
0x1800175fa  lea     rdx, [rbp+57h+var_88]; struct VCHANNEL_DATA **
0x1800175fe  mov     rcx, [rbp+57h+var_78]; struct VCARD_DATA *
0x180017602  call    ?I_VChannelOpen@@YAKPEAUVCARD_DATA@@PEAPEAUVCHANNEL_DATA@@@Z; I_VChannelOpen(VCARD_DATA *,VCHANNEL_DATA * *)
0x180017607  mov     [rbp+57h+var_90], eax
0x18001760a  test    eax, eax
0x18001760c  jz      short loc_180017673
0x18001760e  mov     edx, ebx
0x180017610  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180017615  lea     rdi, WPP_GLOBAL_Control
0x18001761c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017623  cmp     rcx, rdi
0x180017626  jz      short loc_180017662
0x180017628  test    byte ptr [rcx+1Ch], 1
0x18001762c  jz      short loc_180017662
0x18001762e  cmp     [rcx+19h], bl
0x180017631  jb      short loc_180017662
0x180017633  mov     edx, 24h ; '$'
0x180017638  lea     rax, aTheChannelCann; "The channel cannot be opened"
0x18001763f  mov     [rsp+0C0h+var_98], rax
0x180017644  mov     eax, [rbp+57h+var_90]
0x180017647  mov     [rsp+0C0h+var_A0], eax
0x18001764b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180017652  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x180017659  mov     rcx, [rcx+10h]
0x18001765d  call    WPP_SF_sDs
0x180017662  mov     ebx, [rbp+57h+var_90]
0x180017665  lea     rcx, [rbp+57h+var_60]
0x180017669  call    wil__details__ScopeExitFnGuard__lambda_7afff1fa9c927d39bc73e8aff8adf638_____operator__
0x18001766e  jmp     loc_1800175D6
0x180017673  lea     rax, [rbp+57h+var_88]
0x180017677  mov     [rbp+57h+var_40], rax
0x18001767b  mov     [rbp+57h+var_38], 102h
0x180017681  mov     rax, [rbp+57h+var_88]
0x180017685  mov     dword ptr [rax+40h], 3
0x18001768c  mov     dil, 80h
0x18001768f  mov     dl, dil; unsigned __int8
0x180017692  mov     rcx, [rbp+57h+var_88]; struct VCHANNEL_DATA *
0x180017696  call    ?I_DeleteKeyLocking@@YAKPEAUVCHANNEL_DATA@@E@Z; I_DeleteKeyLocking(VCHANNEL_DATA *,uchar)
0x18001769b  inc     dil
0x18001769e  cmp     dil, 0A0h
0x1800176a2  jbe     short loc_18001768F
0x1800176a4  mov     edx, 1
0x1800176a9  mov     rcx, [rbp+57h+var_88]
0x1800176ad  mov     rcx, [rcx]
0x1800176b0  call    ?I_DeleteReferenceData@@YAKPEAUVCARD_DATA@@W4_CARD_ROLE@@@Z; I_DeleteReferenceData(VCARD_DATA *,_CARD_ROLE)
0x1800176b5  mov     [rbp+57h+var_90], eax
0x1800176b8  lea     rdi, WPP_GLOBAL_Control
0x1800176bf  test    eax, eax
0x1800176c1  jz      short loc_1800176F7
0x1800176c3  mov     edx, ebx
0x1800176c5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800176ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176d1  cmp     rcx, rdi
0x1800176d4  jz      short loc_1800176F7
0x1800176d6  test    byte ptr [rcx+1Ch], 1
0x1800176da  jz      short loc_1800176F7
0x1800176dc  cmp     byte ptr [rcx+19h], 3
0x1800176e0  jb      short loc_1800176F7
0x1800176e2  mov     edx, 25h ; '%'
0x1800176e7  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x1800176ee  mov     rcx, [rcx+10h]
0x1800176f2  call    WPP_SF_s
0x1800176f7  mov     edx, ebx
0x1800176f9  mov     rcx, [rbp+57h+var_88]
0x1800176fd  mov     rcx, [rcx]
0x180017700  call    ?I_DeleteReferenceData@@YAKPEAUVCARD_DATA@@W4_CARD_ROLE@@@Z; I_DeleteReferenceData(VCARD_DATA *,_CARD_ROLE)
0x180017705  mov     [rbp+57h+var_90], eax
0x180017708  test    eax, eax
0x18001770a  jz      short loc_180017740
0x18001770c  mov     edx, ebx
0x18001770e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180017713  mov     rcx, cs:WPP_GLOBAL_Control
0x18001771a  cmp     rcx, rdi
0x18001771d  jz      short loc_180017740
0x18001771f  test    byte ptr [rcx+1Ch], 1
0x180017723  jz      short loc_180017740
0x180017725  cmp     byte ptr [rcx+19h], 3
0x180017729  jb      short loc_180017740
0x18001772b  mov     edx, 26h ; '&'
0x180017730  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x180017737  mov     rcx, [rcx+10h]
0x18001773b  call    WPP_SF_s
0x180017740  mov     rax, [rbp+57h+var_88]
0x180017744  mov     rcx, [rax]; struct VCARD_DATA *
0x180017747  mov     rdx, [rcx+40h]; unsigned __int16 *
0x18001774b  call    ?I_DeleteKspKey@@YAKPEBUVCARD_DATA@@PEBG@Z; I_DeleteKspKey(VCARD_DATA const *,ushort const *)
0x180017750  mov     [rbp+57h+var_90], eax
0x180017753  test    eax, eax
0x180017755  jz      short loc_18001778B
0x180017757  mov     edx, ebx
0x180017759  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001775e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017765  cmp     rcx, rdi
0x180017768  jz      short loc_18001778B
0x18001776a  test    byte ptr [rcx+1Ch], 1
0x18001776e  jz      short loc_18001778B
0x180017770  cmp     byte ptr [rcx+19h], 3
0x180017774  jb      short loc_18001778B
0x180017776  mov     edx, 27h ; '''
0x18001777b  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x180017782  mov     rcx, [rcx+10h]
0x180017786  call    WPP_SF_s
0x18001778b  lea     rax, [rbp+57h+var_88]
0x18001778f  mov     [rbp+57h+var_50], rax
0x180017793  lea     rcx, [rbp+57h+var_50]
0x180017797  call    _lambda_b98ee528412eb1b785800fdcf16eb8d7___operator__
0x18001779c  mov     [rbp+57h+var_90], eax
0x18001779f  test    eax, eax
0x1800177a1  jz      short loc_1800177D7
0x1800177a3  mov     edx, ebx
0x1800177a5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800177aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177b1  cmp     rcx, rdi
0x1800177b4  jz      short loc_1800177D7
0x1800177b6  test    byte ptr [rcx+1Ch], 1
0x1800177ba  jz      short loc_1800177D7
0x1800177bc  cmp     byte ptr [rcx+19h], 3
0x1800177c0  jb      short loc_1800177D7
0x1800177c2  mov     edx, 2Ch ; ','
0x1800177c7  lea     r8, WPP_4187a0ba95213a1543aad9a0409240ad_Traceguids
0x1800177ce  mov     rcx, [rcx+10h]
0x1800177d2  call    WPP_SF_s
0x1800177d7  mov     [rbp+57h+var_90], 0
0x1800177de  lea     rcx, [rbp+57h+var_40]
0x1800177e2  call    wil__details__ScopeExitFnGuard__lambda_8df077a85f71db72a9008d311a7eeac9_____operator__
0x1800177e7  nop
0x1800177e8  lea     rcx, [rbp+57h+var_60]
0x1800177ec  call    wil__details__ScopeExitFnGuard__lambda_7afff1fa9c927d39bc73e8aff8adf638_____operator__
0x1800177f1  nop
0x1800177f2  lea     rcx, [rbp+57h+var_70]
0x1800177f6  call    wil__details__ScopeExitFnGuard__lambda_e9556ca6e1f6dd63825a5e6d49f7fe19_____operator__
0x1800177fb  xor     ebx, ebx
0x1800177fd  lea     rcx, [rbp+57h+var_48]
0x180017801  call    WppTraceUnwinder__lambda_8f3c3355ceaca74c92f9c41a25916dc0_______WppTraceUnwinder__lambda_8f3c3355ceaca74c92f9c41a25916dc0____
0x180017806  mov     eax, ebx
0x180017808  mov     rcx, [rbp+57h+var_8]
0x18001780c  xor     rcx, rsp; StackCookie
0x18001780f  call    __security_check_cookie
0x180017814  lea     r11, [rsp+0C0h+var_s0]
0x18001781c  mov     rbx, [r11+18h]
0x180017820  mov     rdi, [r11+20h]
0x180017824  mov     rsp, r11
0x180017827  pop     rbp
0x180017828  retn
```
