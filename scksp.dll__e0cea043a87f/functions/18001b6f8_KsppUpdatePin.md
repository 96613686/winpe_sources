# KsppUpdatePin

- ea: `0x18001b6f8`
- end: `0x18001bdf2`
- name: `KsppUpdatePin`
- size: `1786`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025ff0`
- `0x180027054`

## callees

- `0x180009e76`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180013aac`
- `0x1800146c4`
- `0x180014ecc`
- `0x18001594c`
- `0x180019514`
- `0x18001b6f8`
- `0x18001c6ec`
- `0x18002b140`
- `0x18002e034`
- `0x18002e270`
- `0x1800391c4`
- `0x180039d7c`
- `0x18003afc0`
- `0x18003b920`
- `0x18003c1f6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9c0`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18001b9af`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18001b9af`
- `api-ms-win-security-credentials-l1-1-0!CredIsMarshaledCredentialW` at `0x18001b995`
- `api-ms-win-security-credentials-l1-1-0!CredIsMarshaledCredentialW` at `0x18001b995`

## pseudocode

```c
__int64 __fastcall KsppUpdatePin(__int64 a1, __int64 a2, const WCHAR *a3, unsigned int a4, int a5)
{
  size_t v5; // r14
  __int64 v6; // r12
  __int64 v7; // r15
  bool v11; // zf
  __int64 v12; // r8
  __int64 v13; // rcx
  unsigned int PinFromNgcPinCache; // ebx
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rcx
  DWORD LastError; // eax
  _QWORD *v20; // rsi
  void *v21; // rcx
  __int64 v22; // rdx
  size_t v23; // r8
  const WCHAR *v24; // rdx
  void *v25; // rax
  int v26; // ebx
  const void *v27; // r14
  int v28; // eax
  void *v29; // rsi
  BOOL v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  char v35; // si
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rcx
  _BYTE *v39; // rax
  __int64 v40; // rcx
  PVOID Credential; // [rsp+30h] [rbp-51h] BYREF
  void *Buf1; // [rsp+38h] [rbp-49h]
  void **v44; // [rsp+40h] [rbp-41h] BYREF
  __int64 v45; // [rsp+48h] [rbp-39h]
  __int128 v46; // [rsp+50h] [rbp-31h] BYREF
  __int128 v47; // [rsp+60h] [rbp-21h] BYREF
  void *Buf2[2]; // [rsp+70h] [rbp-11h]
  __int128 v49; // [rsp+80h] [rbp-1h]
  __int64 v50; // [rsp+90h] [rbp+Fh]
  _CRED_MARSHAL_TYPE CredType; // [rsp+E8h] [rbp+67h] BYREF

  v5 = a4;
  v50 = 0;
  v6 = a2 + 1072;
  Credential = 0;
  v7 = *(_QWORD *)(a2 + 1136);
  CredType = 0;
  v45 = 0;
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v47 = 0;
  *(_OWORD *)Buf2 = 0;
  v49 = 0;
  v46 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, WPP_pszIndent);
  }
  v11 = *(_QWORD *)(a2 + 1088) == 0;
  v50 = 0;
  DWORD2(v46) = *(_DWORD *)(a1 + 60);
  v47 = 0;
  *(_OWORD *)Buf2 = 0;
  v49 = 0;
  if ( v11 )
  {
    LODWORD(v12) = a2 + 520;
    if ( !*(_WORD *)(a2 + 520) )
      v12 = *(_QWORD *)(a1 + 144);
    PinFromNgcPinCache = KsppCardConnect(a1, 0, v12, v6, *(_DWORD *)(a2 + 1064) | 0x80u, *(_QWORD *)(a2 + 1104));
    if ( PinFromNgcPinCache )
    {
      WppTraceIndent(v13, 2u);
      v15 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 213;
LABEL_13:
        WPP_SF_sd(
          *(_QWORD *)(v15 + 16),
          v16,
          (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
          (_DWORD)WPP_pszIndent,
          PinFromNgcPinCache);
        goto LABEL_82;
      }
      goto LABEL_82;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v44, *(_QWORD *)(a2 + 1088) + 624LL);
    if ( !*(_QWORD *)(a2 + 1088) )
    {
      WppTraceIndent(v17, 2u);
      PinFromNgcPinCache = -2146893792;
      v15 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          214,
          &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
          2148073504LL);
      }
      goto LABEL_82;
    }
LABEL_26:
    if ( !a3 )
      goto LABEL_27;
    if ( a5 )
    {
      v25 = MIDL_user_allocate(v5);
      Buf2[0] = v25;
      if ( !v25 )
      {
        PinFromNgcPinCache = -2146893810;
        v15 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_82;
        }
        v22 = 219;
LABEL_45:
        WPP_SF_s(*(_QWORD *)(v15 + 16), v22, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, WPP_pszIndent);
        goto LABEL_82;
      }
      HIDWORD(v47) = v5;
      v23 = v5;
      v24 = a3;
      v21 = v25;
    }
    else
    {
      if ( (unsigned int)v5 <= 6 || *a3 != 35 || a3[1] != 35 || !CredIsMarshaledCredentialW(a3 + 2) )
      {
        PinFromNgcPinCache = PinStringToBytesW(a3);
        if ( PinFromNgcPinCache )
        {
          WppTraceIndent(v15, 2u);
          v15 = (__int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 218;
            goto LABEL_13;
          }
          goto LABEL_82;
        }
        goto LABEL_59;
      }
      if ( !CredUnmarshalCredentialW(a3 + 2, &CredType, &Credential) )
      {
        WppTraceIndent(v15, 2u);
        LastError = GetLastError();
        PinFromNgcPinCache = LastError;
        v15 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            216,
            (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
            (_DWORD)WPP_pszIndent,
            LastError);
        }
        goto LABEL_82;
      }
      if ( CredType != BinaryBlobCredential )
      {
        PinFromNgcPinCache = -2146893819;
        goto LABEL_82;
      }
      v20 = Credential;
      Buf2[0] = MIDL_user_allocate(*(unsigned int *)Credential);
      v21 = Buf2[0];
      if ( !Buf2[0] )
      {
        PinFromNgcPinCache = -2146893810;
        v15 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_82;
        }
        v22 = 217;
        goto LABEL_45;
      }
      HIDWORD(v47) = *(_DWORD *)v20;
      v23 = HIDWORD(v47);
      v24 = (const WCHAR *)v20[1];
    }
    memcpy_0(v21, v24, v23);
    DWORD1(v47) = 1;
LABEL_59:
    if ( v7 )
    {
      if ( *(_DWORD *)(v7 + 4) == 3 )
      {
        if ( HIDWORD(v47) )
          PinFromNgcPinCache = -2146435030;
        goto LABEL_82;
      }
      if ( *(_DWORD *)(v7 + 4) == 2 )
      {
        PinFromNgcPinCache = -2146435038;
        goto LABEL_82;
      }
    }
    if ( (unsigned int)CspVerifyCachedPinConsistency(*(_QWORD *)(a2 + 1088), *(_DWORD *)(a2 + 1128)) )
      CspRemoveCachedPin(*(_QWORD *)(a2 + 1088), *(_DWORD *)(a2 + 1128), 0);
    v26 = HIDWORD(v47);
    v27 = Buf2[0];
    Buf1 = 0;
    v28 = PinStringToBytesW(L"_$_5bb789f2-9e37-401b-965e-e4de9804aca1");
    v29 = Buf1;
    v30 = !v28 && !v26 && memcmp_0(Buf1, v27, 0) == 0;
    if ( v29 )
      CspFreeH(v29);
    if ( v30 )
    {
      PinFromNgcPinCache = KsppGetPinFromNgcPinCache(a2, (__int64)&v47);
      if ( PinFromNgcPinCache )
      {
        WppTraceIndent(v31, 2u);
        v15 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 220;
          goto LABEL_13;
        }
        goto LABEL_82;
      }
    }
    v32 = *(_QWORD *)(a2 + 1088);
    LODWORD(v47) = *(_DWORD *)(a2 + 1128);
    *(_QWORD *)&v46 = v32;
    PinFromNgcPinCache = PinCacheAdd(
                           (int)v32 + 584,
                           255,
                           v7,
                           (unsigned int)&v47,
                           (__int64)VerifyCachedPinCallback,
                           (__int64)&v46);
    if ( !PinFromNgcPinCache )
    {
      if ( HIDWORD(v46) == 1 )
      {
        v15 = *(unsigned int *)(a2 + 1128);
        *(_DWORD *)(*(_QWORD *)(a2 + 1088) + 712LL) |= 1 << v15;
      }
      goto LABEL_82;
    }
LABEL_27:
    CspRemoveCachedPin(*(_QWORD *)(a2 + 1088), *(_DWORD *)(a2 + 1128), 0);
    goto LABEL_82;
  }
  PinFromNgcPinCache = KsppBeginCardCall(v6);
  if ( !PinFromNgcPinCache )
  {
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v44, *(_QWORD *)(a2 + 1088) + 624LL);
    goto LABEL_26;
  }
  WppTraceIndent(v18, 2u);
  v15 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 215;
    goto LABEL_13;
  }
LABEL_82:
  if ( v45 )
  {
    if ( a3 )
    {
      v45 = 0;
      KsppEndCardCall(v6);
    }
    else
    {
      v33 = TransactionManagerForceEndTransaction(*(struct _CARD_STATE **)(v6 + 16));
      v35 = v33;
      if ( v33 )
      {
        WppTraceIndent(v34, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            221,
            v36,
            v37,
            v35,
            *(_DWORD *)(*(_QWORD *)(a2 + 1088) + 592LL));
        }
      }
      v38 = *(_QWORD *)(a2 + 1088) + 624LL;
      v45 = 0;
      KspLeaveCriticalSection(v38);
    }
  }
  v39 = Buf2[0];
  if ( Buf2[0] )
  {
    v40 = HIDWORD(v47);
    if ( HIDWORD(v47) )
    {
      do
      {
        *v39++ = 0;
        --v40;
      }
      while ( v40 );
    }
    CspFreeH(Buf2[0]);
  }
  WppTraceIndent(v15, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      222,
      (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
      (_DWORD)WPP_pszIndent,
      PinFromNgcPinCache);
  }
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v44);
  return PinFromNgcPinCache;
}

```

## disassembly

```asm
0x18001b6f8  mov     [rsp-8+arg_10], rbx
0x18001b6fd  push    rbp
0x18001b6fe  push    rsi
0x18001b6ff  push    rdi
0x18001b700  push    r12
0x18001b702  push    r13
0x18001b704  push    r14
0x18001b706  push    r15
0x18001b708  lea     rbp, [rsp-1Fh]
0x18001b70d  sub     rsp, 0A0h
0x18001b714  xor     eax, eax
0x18001b716  mov     r14d, r9d
0x18001b719  xorps   xmm0, xmm0
0x18001b71c  mov     [rbp+4Fh+var_40], rax
0x18001b720  lea     r12, [rdx+430h]
0x18001b727  mov     [rbp+4Fh+Credential], rax
0x18001b72b  mov     r15, [r12+40h]
0x18001b730  mov     rdi, rdx
0x18001b733  mov     [rbp+4Fh+CredType], eax
0x18001b736  xor     edx, edx
0x18001b738  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001b73f  mov     [rbp+4Fh+var_88], 0
0x18001b747  mov     [rbp+4Fh+var_90], rax
0x18001b74b  mov     r13, r8
0x18001b74e  mov     rbx, rcx
0x18001b751  movups  [rbp+4Fh+var_70], xmm0
0x18001b755  movups  xmmword ptr [rbp+4Fh+Buf2], xmm0
0x18001b759  movups  [rbp+4Fh+var_50], xmm0
0x18001b75d  movups  [rbp+4Fh+var_80], xmm0
0x18001b761  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001b766  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b76d  lea     rax, WPP_GLOBAL_Control
0x18001b774  mov     esi, 2
0x18001b779  cmp     rcx, rax
0x18001b77c  jz      short loc_18001B7A6
0x18001b77e  test    [rcx+1Ch], sil
0x18001b782  jz      short loc_18001B7A6
0x18001b784  cmp     byte ptr [rcx+19h], 5
0x18001b788  jb      short loc_18001B7A6
0x18001b78a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001b791  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001b798  mov     rcx, [rcx+10h]
0x18001b79c  mov     edx, 0D4h
0x18001b7a1  call    WPP_SF_s
0x18001b7a6  xor     eax, eax
0x18001b7a8  xorps   xmm0, xmm0
0x18001b7ab  cmp     qword ptr [rdi+440h], 0
0x18001b7b3  mov     [rbp+4Fh+var_40], rax
0x18001b7b7  mov     eax, [rbx+3Ch]
0x18001b7ba  mov     dword ptr [rbp+4Fh+var_80+8], eax
0x18001b7bd  movups  [rbp+4Fh+var_70], xmm0
0x18001b7c1  movups  xmmword ptr [rbp+4Fh+Buf2], xmm0
0x18001b7c5  movups  [rbp+4Fh+var_50], xmm0
0x18001b7c9  jnz     loc_18001B8E2
0x18001b7cf  lea     r8, [rdi+208h]
0x18001b7d6  xor     eax, eax
0x18001b7d8  cmp     ax, [r8]
0x18001b7dc  jnz     short loc_18001B7E5
0x18001b7de  mov     r8, [rbx+90h]
0x18001b7e5  mov     ecx, [rdi+428h]
0x18001b7eb  mov     r9, r12
0x18001b7ee  mov     rax, [rdi+450h]
0x18001b7f5  bts     ecx, 7
0x18001b7f9  mov     [rsp+0D0h+var_A8], rax
0x18001b7fe  xor     edx, edx
0x18001b800  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x18001b804  mov     rcx, rbx
0x18001b807  call    KsppCardConnect
0x18001b80c  mov     ebx, eax
0x18001b80e  test    eax, eax
0x18001b810  jz      short loc_18001B869
0x18001b812  mov     edx, esi
0x18001b814  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001b819  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b820  lea     r14, WPP_GLOBAL_Control
0x18001b827  cmp     rcx, r14
0x18001b82a  jz      loc_18001BCC8
0x18001b830  test    byte ptr [rcx+1Ch], 1
0x18001b834  jz      loc_18001BCC8
0x18001b83a  cmp     [rcx+19h], sil
0x18001b83e  jb      loc_18001BCC8
0x18001b844  mov     edx, 0D5h
0x18001b849  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18001b84d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001b854  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001b85b  mov     rcx, [rcx+10h]
0x18001b85f  call    WPP_SF_sd
0x18001b864  jmp     loc_18001BCC8
0x18001b869  mov     rdx, [rdi+440h]
0x18001b870  lea     rcx, [rbp+4Fh+var_90]
0x18001b874  add     rdx, 270h
0x18001b87b  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001b880  cmp     qword ptr [rdi+440h], 0
0x18001b888  jnz     loc_18001B943
0x18001b88e  mov     edx, esi
0x18001b890  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001b895  mov     ebx, 80090020h
0x18001b89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8a1  lea     r14, WPP_GLOBAL_Control
0x18001b8a8  cmp     rcx, r14
0x18001b8ab  jz      loc_18001BCC8
0x18001b8b1  test    byte ptr [rcx+1Ch], 1
0x18001b8b5  jz      loc_18001BCC8
0x18001b8bb  cmp     [rcx+19h], sil
0x18001b8bf  jb      loc_18001BCC8
0x18001b8c5  mov     rcx, [rcx+10h]
0x18001b8c9  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001b8d0  mov     edx, 0D6h
0x18001b8d5  mov     r9d, ebx
0x18001b8d8  call    WPP_SF_d
0x18001b8dd  jmp     loc_18001BCC8
0x18001b8e2  mov     rcx, r12
0x18001b8e5  call    KsppBeginCardCall
0x18001b8ea  mov     ebx, eax
0x18001b8ec  test    eax, eax
0x18001b8ee  jz      short loc_18001B92C
0x18001b8f0  mov     edx, esi
0x18001b8f2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001b8f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8fe  lea     r14, WPP_GLOBAL_Control
0x18001b905  cmp     rcx, r14
0x18001b908  jz      loc_18001BCC8
0x18001b90e  test    byte ptr [rcx+1Ch], 1
0x18001b912  jz      loc_18001BCC8
0x18001b918  cmp     [rcx+19h], sil
0x18001b91c  jb      loc_18001BCC8
0x18001b922  mov     edx, 0D7h
0x18001b927  jmp     loc_18001B849
0x18001b92c  mov     rdx, [rdi+440h]
0x18001b933  lea     rcx, [rbp+4Fh+var_90]
0x18001b937  add     rdx, 270h
0x18001b93e  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001b943  test    r13, r13
0x18001b946  jnz     short loc_18001B962
0x18001b948  mov     edx, [rdi+468h]
0x18001b94e  xor     r8d, r8d
0x18001b951  mov     rcx, [rdi+440h]
0x18001b958  call    CspRemoveCachedPin
0x18001b95d  jmp     loc_18001BCC1
0x18001b962  cmp     [rbp+4Fh+arg_20], 0
0x18001b966  jnz     loc_18001BAE0
0x18001b96c  cmp     r14d, 6
0x18001b970  jbe     loc_18001BA8A
0x18001b976  mov     eax, 23h ; '#'
0x18001b97b  cmp     ax, [r13+0]
0x18001b980  jnz     loc_18001BA8A
0x18001b986  cmp     ax, [r13+2]
0x18001b98b  jnz     loc_18001BA8A
0x18001b991  lea     rcx, [r13+4]; MarshaledCredential
0x18001b995  call    cs:__imp_CredIsMarshaledCredentialW
0x18001b99b  test    eax, eax
0x18001b99d  jz      loc_18001BA8A
0x18001b9a3  lea     r8, [rbp+4Fh+Credential]; Credential
0x18001b9a7  lea     rdx, [rbp+4Fh+CredType]; CredType
0x18001b9ab  lea     rcx, [r13+4]; MarshaledCredential
0x18001b9af  call    cs:__imp_CredUnmarshalCredentialW
0x18001b9b5  test    eax, eax
0x18001b9b7  jnz     short loc_18001BA01
0x18001b9b9  mov     edx, esi
0x18001b9bb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001b9c0  call    cs:__imp_GetLastError
0x18001b9c6  mov     ebx, eax
0x18001b9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9cf  lea     r14, WPP_GLOBAL_Control
0x18001b9d6  cmp     rcx, r14
0x18001b9d9  jz      loc_18001BCC8
0x18001b9df  test    byte ptr [rcx+1Ch], 1
0x18001b9e3  jz      loc_18001BCC8
0x18001b9e9  cmp     [rcx+19h], sil
0x18001b9ed  jb      loc_18001BCC8
0x18001b9f3  mov     edx, 0D8h
0x18001b9f8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18001b9fc  jmp     loc_18001B84D
0x18001ba01  cmp     [rbp+4Fh+CredType], 3
0x18001ba05  jz      short loc_18001BA11
0x18001ba07  mov     ebx, 80090005h
0x18001ba0c  jmp     loc_18001BCC1
0x18001ba11  mov     rsi, [rbp+4Fh+Credential]
0x18001ba15  mov     ecx, [rsi]; size
0x18001ba17  call    MIDL_user_allocate
0x18001ba1c  mov     [rbp+4Fh+Buf2], rax
0x18001ba20  mov     rcx, rax
0x18001ba23  test    rax, rax
0x18001ba26  jnz     short loc_18001BA79
0x18001ba28  mov     ebx, 8009000Eh
0x18001ba2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba34  lea     r14, WPP_GLOBAL_Control
0x18001ba3b  cmp     rcx, r14
0x18001ba3e  jz      loc_18001BCC8
0x18001ba44  test    byte ptr [rcx+1Ch], 1
0x18001ba48  jz      loc_18001BCC8
0x18001ba4e  cmp     byte ptr [rcx+19h], 2
0x18001ba52  jb      loc_18001BCC8
0x18001ba58  mov     edx, 0D9h
0x18001ba5d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ba64  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001ba6b  mov     rcx, [rcx+10h]
0x18001ba6f  call    WPP_SF_s
0x18001ba74  jmp     loc_18001BCC8
0x18001ba79  mov     eax, [rsi]
0x18001ba7b  mov     dword ptr [rbp+4Fh+var_70+0Ch], eax
0x18001ba7e  mov     r8d, eax
0x18001ba81  mov     rdx, [rsi+8]
0x18001ba85  jmp     loc_18001BB38
0x18001ba8a  lea     r8, [rbp+4Fh+Buf2]
0x18001ba8e  mov     rcx, r13; SourceString
0x18001ba91  lea     rdx, [rbp+4Fh+var_70+0Ch]
0x18001ba95  call    PinStringToBytesW
0x18001ba9a  mov     ebx, eax
0x18001ba9c  test    eax, eax
0x18001ba9e  jz      loc_18001BB44
0x18001baa4  mov     edx, esi
0x18001baa6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001baab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bab2  lea     r14, WPP_GLOBAL_Control
0x18001bab9  cmp     rcx, r14
0x18001babc  jz      loc_18001BCC8
0x18001bac2  test    byte ptr [rcx+1Ch], 1
0x18001bac6  jz      loc_18001BCC8
0x18001bacc  cmp     [rcx+19h], sil
0x18001bad0  jb      loc_18001BCC8
0x18001bad6  mov     edx, 0DAh
0x18001badb  jmp     loc_18001B849
0x18001bae0  mov     rcx, r14; size
0x18001bae3  call    MIDL_user_allocate
0x18001bae8  mov     [rbp+4Fh+Buf2], rax
0x18001baec  test    rax, rax
0x18001baef  jnz     short loc_18001BB2B
0x18001baf1  mov     ebx, 8009000Eh
0x18001baf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bafd  lea     r14, WPP_GLOBAL_Control
0x18001bb04  cmp     rcx, r14
0x18001bb07  jz      loc_18001BCC8
0x18001bb0d  test    byte ptr [rcx+1Ch], 1
0x18001bb11  jz      loc_18001BCC8
0x18001bb17  cmp     [rcx+19h], sil
0x18001bb1b  jb      loc_18001BCC8
0x18001bb21  mov     edx, 0DBh
0x18001bb26  jmp     loc_18001BA5D
0x18001bb2b  mov     dword ptr [rbp+4Fh+var_70+0Ch], r14d
0x18001bb2f  mov     r8, r14; Size
0x18001bb32  mov     rdx, r13; Src
0x18001bb35  mov     rcx, rax; void *
0x18001bb38  call    memcpy_0
0x18001bb3d  mov     dword ptr [rbp+4Fh+var_70+4], 1
0x18001bb44  test    r15, r15
0x18001bb47  jz      short loc_18001BB7C
0x18001bb49  cmp     dword ptr [r15+4], 3
0x18001bb4e  jnz     short loc_18001BB6B
0x18001bb50  cmp     dword ptr [rbp+4Fh+var_70+0Ch], 0
0x18001bb54  lea     r14, WPP_GLOBAL_Control
0x18001bb5b  jz      loc_18001BCC8
0x18001bb61  mov     ebx, 8010002Ah
0x18001bb66  jmp     loc_18001BCC8
0x18001bb6b  cmp     dword ptr [r15+4], 2
0x18001bb70  jnz     short loc_18001BB7C
0x18001bb72  mov     ebx, 80100022h
0x18001bb77  jmp     loc_18001BCC1
0x18001bb7c  mov     edx, [rdi+468h]
0x18001bb82  mov     rcx, [rdi+440h]
0x18001bb89  call    CspVerifyCachedPinConsistency
0x18001bb8e  test    eax, eax
0x18001bb90  jz      short loc_18001BBA7
0x18001bb92  mov     edx, [rdi+468h]
0x18001bb98  xor     r8d, r8d
0x18001bb9b  mov     rcx, [rdi+440h]
0x18001bba2  call    CspRemoveCachedPin
0x18001bba7  mov     ebx, dword ptr [rbp+4Fh+var_70+0Ch]
0x18001bbaa  lea     r8, [rbp+4Fh+Buf1]
0x18001bbae  mov     r14, [rbp+4Fh+Buf2]
0x18001bbb2  lea     rdx, [rbp+4Fh+Size]
0x18001bbb6  lea     rcx, SourceString; "_$_5bb789f2-9e37-401b-965e-e4de9804aca1"
0x18001bbbd  mov     [rbp+4Fh+Buf1], 0
0x18001bbc5  mov     dword ptr [rbp+4Fh+Size], 0
0x18001bbcc  call    PinStringToBytesW
0x18001bbd1  mov     rsi, [rbp+4Fh+Buf1]
0x18001bbd5  test    eax, eax
0x18001bbd7  jz      short loc_18001BBDD
0x18001bbd9  xor     ebx, ebx
0x18001bbdb  jmp     short loc_18001BBF8
0x18001bbdd  cmp     dword ptr [rbp+4Fh+Size], ebx
0x18001bbe0  jnz     short loc_18001BBD9
0x18001bbe2  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x18001bbe6  mov     rdx, r14; Buf2
0x18001bbe9  mov     rcx, rsi; Buf1
0x18001bbec  call    memcmp_0
0x18001bbf1  xor     ebx, ebx
0x18001bbf3  test    eax, eax
0x18001bbf5  setz    bl
0x18001bbf8  test    rsi, rsi
0x18001bbfb  jz      short loc_18001BC05
0x18001bbfd  mov     rcx, rsi
0x18001bc00  call    CspFreeH
0x18001bc05  test    ebx, ebx
0x18001bc07  jz      short loc_18001BC58
0x18001bc09  lea     rdx, [rbp+4Fh+var_70]
0x18001bc0d  mov     rcx, rdi
0x18001bc10  call    KsppGetPinFromNgcPinCache
0x18001bc15  mov     ebx, eax
0x18001bc17  test    eax, eax
  ... truncated ...
```
