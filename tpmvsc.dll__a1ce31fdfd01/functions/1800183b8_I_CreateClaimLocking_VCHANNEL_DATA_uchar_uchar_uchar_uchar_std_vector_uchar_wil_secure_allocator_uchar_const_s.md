# I_CreateClaimLocking(VCHANNEL_DATA *,uchar,uchar,uchar,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)

- ea: `0x1800183b8`
- end: `0x1800188a4`
- name: `?I_CreateClaimLocking@@YAKPEAUVCHANNEL_DATA@@EEEEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV23@@Z`
- size: `1260`
- prototype: `__int64 __fastcall(struct VCHANNEL_DATA *, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18002cd7c`

## callees

- `0x180001ec0`
- `0x1800079e4`
- `0x18000a110`
- `0x18000bc48`
- `0x18000c198`
- `0x1800179f4`
- `0x180017b2c`
- `0x180017be4`
- `0x180017c3c`
- `0x180017c50`
- `0x180017ccc`
- `0x180017f50`
- `0x1800183b8`
- `0x18001a31c`
- `0x180022ad8`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018579`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001858c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001863c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001864f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018579`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001858c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001863c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001864f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800184e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800185b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800184e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800185b1`
- `ncrypt!NCryptCreateClaim` at `0x1800186c0`
- `ncrypt!NCryptCreateClaim` at `0x1800187b9`
- `ncrypt!NCryptCreateClaim` at `0x1800186c0`
- `ncrypt!NCryptCreateClaim` at `0x1800187b9`

## string_xrefs

- `0x180018404`: `I_CreateClaimLocking`
- `0x180018718`: `Unable to create the claim`

## pseudocode

```c
__int64 __fastcall I_CreateClaimLocking(
        struct VCHANNEL_DATA *a1,
        unsigned __int8 a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        __int64 *a6,
        _QWORD *a7)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  RTL_SRWLOCK *v16; // rsi
  __int64 v17; // rcx
  unsigned int v18; // ebx
  RTL_SRWLOCK *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  char v23; // r8
  _QWORD *v24; // rcx
  int v25; // edx
  __int64 v26; // r8
  unsigned __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  unsigned __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v34; // [rsp+40h] [rbp-B1h] BYREF
  int v35; // [rsp+44h] [rbp-ADh] BYREF
  unsigned int v36; // [rsp+48h] [rbp-A9h] BYREF
  int v37; // [rsp+4Ch] [rbp-A5h] BYREF
  unsigned __int64 v38; // [rsp+50h] [rbp-A1h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-99h] BYREF
  unsigned __int64 *v40; // [rsp+60h] [rbp-91h] BYREF
  __int16 v41; // [rsp+68h] [rbp-89h]
  unsigned __int64 *v42; // [rsp+70h] [rbp-81h] BYREF
  __int16 v43; // [rsp+78h] [rbp-79h]
  _DWORD v44[2]; // [rsp+80h] [rbp-71h] BYREF
  _DWORD *v45; // [rsp+88h] [rbp-69h]
  _QWORD *v46; // [rsp+90h] [rbp-61h] BYREF
  _DWORD v47[2]; // [rsp+98h] [rbp-59h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-51h]
  _QWORD v49[3]; // [rsp+A8h] [rbp-49h] BYREF
  _BYTE v50[24]; // [rsp+C0h] [rbp-31h] BYREF
  char v51[24]; // [rsp+D8h] [rbp-19h] BYREF

  v34 = 0;
  v35 = 0;
  v37 = 0;
  strcpy(v51, "I_CreateClaimLocking");
  v49[0] = v51;
  v49[1] = &v37;
  v49[2] = &v34;
  lambda_496c3dc0ecfbed512afae305a88075c1_::operator()(v49);
  v37 = 1;
  v46 = v49;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
  if ( !(unsigned int)I_IsRoleAuthenticated(a1, 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13);
  if ( (unsigned __int8)(a4 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13);
  if ( (unsigned __int8)((a3 & 0xF) - 6) > 3u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13);
  if ( (unsigned __int8)(a2 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13);
  if ( (unsigned __int8)((a5 & 0xF) - 6) > 3u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13);
  v38 = 0;
  v39 = 0;
  v15 = lambda_803e9900112de776bddc00e9978beff3_::_lambda_803e9900112de776bddc00e9978beff3_(
          &v42,
          (__int64)&v34,
          (__int64)&v35);
  wil::ScopeExitNoExcept__lambda_73bdf23f9c00f0528e018ca4aa2f4a8b___(v50, v15);
  v16 = (RTL_SRWLOCK *)(*(_QWORD *)a1 + 56LL);
  AcquireSRWLockShared(v16);
  v40 = (unsigned __int64 *)v16;
  v34 = I_LoadAsymKey(a1, a2, a3, &v38);
  if ( !v34 )
  {
    if ( v16 )
      ReleaseSRWLockShared(v16);
    v42 = &v38;
    v43 = 258;
    v19 = (RTL_SRWLOCK *)(*(_QWORD *)a1 + 56LL);
    AcquireSRWLockShared(v19);
    v40 = (unsigned __int64 *)v19;
    v34 = I_LoadAsymKey(a1, a4, a5, &v39);
    if ( v34 )
    {
      WppTraceIndent(v20, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          (unsigned int)WPP_b1753b5f523035523139d18de184cf7c_Traceguids,
          (_DWORD)WPP_pszIndent,
          v34,
          (__int64)"Unable to load the requested RSA key");
      }
      v18 = v34;
      if ( v19 )
        ReleaseSRWLockShared(v19);
      goto LABEL_60;
    }
    if ( v19 )
      ReleaseSRWLockShared(v19);
    v40 = &v39;
    v41 = 258;
    v21 = *a6;
    v47[0] = *((_DWORD *)a6 + 2) - *a6;
    v47[1] = 49;
    v48 = v21;
    v44[0] = 0;
    v44[1] = 1;
    v45 = v47;
    v36 = 0;
    v35 = NCryptCreateClaim(v39, v38, 2, v44, 0, 0, &v36, 0);
    if ( v35 )
    {
      WppTraceIndent(v22, 2);
      v18 = I_MapSecurityStatusToWinError(v35);
      v34 = v18;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v25 = 63;
      goto LABEL_38;
    }
    v26 = *a7;
    v27 = a7[1] - *a7;
    if ( v36 < v27 )
    {
      v28 = v26 + v36;
LABEL_45:
      a7[1] = v28;
      goto LABEL_46;
    }
    if ( v36 > v27 )
    {
      if ( v36 <= (unsigned __int64)(a7[2] - v26) )
      {
        v28 = std::_Uninitialized_value_construct_n<wil::secure_allocator<unsigned char>>(a7[1], v36 - v27, (__int64)a7);
        goto LABEL_45;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(a7, v36);
    }
LABEL_46:
    v35 = NCryptCreateClaim(v39, v38, 2, v44, *a7, v36, &v36, 0);
    if ( !v35 )
    {
      v30 = *a7;
      v31 = a7[1] - *a7;
      if ( v36 >= v31 )
      {
        if ( v36 <= v31 )
          goto LABEL_58;
        if ( v36 > (unsigned __int64)(a7[2] - v30) )
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
            a7,
            v36);
          goto LABEL_58;
        }
        v32 = std::_Uninitialized_value_construct_n<wil::secure_allocator<unsigned char>>(a7[1], v36 - v31, (__int64)a7);
      }
      else
      {
        v32 = v30 + v36;
      }
      a7[1] = v32;
      goto LABEL_58;
    }
    WppTraceIndent(v29, 2);
    v18 = I_MapSecurityStatusToWinError(v35);
    v34 = v18;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v25 = 64;
LABEL_38:
    WPP_SF_sDs(
      v24[2],
      v25,
      (unsigned int)WPP_b1753b5f523035523139d18de184cf7c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v23,
      (__int64)"Unable to create the claim");
LABEL_58:
    v18 = v34;
LABEL_59:
    wil::details::ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741___::operator()(&v40);
LABEL_60:
    wil::details::ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741___::operator()(&v42);
    goto LABEL_61;
  }
  WppTraceIndent(v17, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      (unsigned int)WPP_b1753b5f523035523139d18de184cf7c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v34,
      (__int64)"Unable to load the requested RSA key");
  }
  v18 = v34;
  if ( v16 )
    ReleaseSRWLockShared(v16);
LABEL_61:
  wil::details::ScopeExitFnGuard__lambda_73bdf23f9c00f0528e018ca4aa2f4a8b___::_ScopeExitFnGuard__lambda_73bdf23f9c00f0528e018ca4aa2f4a8b___(v50);
  WppTraceUnwinder__lambda_496c3dc0ecfbed512afae305a88075c1____::_WppTraceUnwinder__lambda_496c3dc0ecfbed512afae305a88075c1____(&v46);
  return v18;
}

```

## disassembly

```asm
0x1800183b8  mov     [rsp-8+arg_10], rbx
0x1800183bd  push    rbp
0x1800183be  push    rsi
0x1800183bf  push    rdi
0x1800183c0  push    r12
0x1800183c2  push    r13
0x1800183c4  push    r14
0x1800183c6  push    r15
0x1800183c8  lea     rbp, [rsp-0Fh]
0x1800183cd  sub     rsp, 100h
0x1800183d4  mov     rax, cs:__security_cookie
0x1800183db  xor     rax, rsp
0x1800183de  mov     [rbp+3Fh+var_40], rax
0x1800183e2  mov     r15b, r9b
0x1800183e5  mov     r12b, r8b
0x1800183e8  mov     dil, dl
0x1800183eb  mov     r14, rcx
0x1800183ee  mov     r13, [rbp+3Fh+arg_28]
0x1800183f2  mov     rbx, [rbp+3Fh+arg_30]
0x1800183f6  xor     esi, esi
0x1800183f8  mov     [rsp+130h+var_F0], esi
0x1800183fc  mov     [rsp+130h+var_EC], esi
0x180018400  mov     [rsp+130h+var_E4], esi
0x180018404  movups  xmm0, xmmword ptr cs:aICreateclaimlo; "I_CreateClaimLocking"
0x18001840b  movups  xmmword ptr [rbp+3Fh+var_58], xmm0
0x18001840f  movsd   xmm1, qword ptr cs:aICreateclaimlo+0Dh; "Locking"
0x180018417  movsd   qword ptr [rbp+3Fh+var_58+0Dh], xmm1
0x18001841c  lea     rax, [rbp+3Fh+var_58]
0x180018420  mov     [rbp+3Fh+var_88], rax
0x180018424  lea     rax, [rsp+130h+var_E4]
0x180018429  mov     [rbp+3Fh+var_80], rax
0x18001842d  lea     rax, [rsp+130h+var_F0]
0x180018432  mov     [rbp+3Fh+var_78], rax
0x180018436  lea     rcx, [rbp+3Fh+var_88]
0x18001843a  call    _lambda_496c3dc0ecfbed512afae305a88075c1___operator__
0x18001843f  mov     [rsp+130h+var_E4], 1
0x180018447  lea     rax, [rbp+3Fh+var_88]
0x18001844b  mov     [rbp+3Fh+var_A0], rax
0x18001844f  test    r14, r14
0x180018452  jnz     short loc_180018459
0x180018454  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018459  test    rbx, rbx
0x18001845c  jnz     short loc_180018463
0x18001845e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018463  mov     edx, 1
0x180018468  mov     rcx, r14
0x18001846b  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x180018470  test    eax, eax
0x180018472  jnz     short loc_180018479
0x180018474  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018479  lea     eax, [r15-80h]
0x18001847d  cmp     al, 20h ; ' '
0x18001847f  jbe     short loc_180018486
0x180018481  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018486  mov     al, r12b
0x180018489  and     al, 0Fh
0x18001848b  sub     al, 6
0x18001848d  cmp     al, 3
0x18001848f  jbe     short loc_180018496
0x180018491  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018496  lea     eax, [rdi-80h]
0x180018499  cmp     al, 20h ; ' '
0x18001849b  jbe     short loc_1800184A2
0x18001849d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800184a2  mov     al, [rbp+3Fh+arg_20]
0x1800184a5  and     al, 0Fh
0x1800184a7  sub     al, 6
0x1800184a9  cmp     al, 3
0x1800184ab  jbe     short loc_1800184B2
0x1800184ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800184b2  mov     [rsp+130h+var_E0], rsi
0x1800184b7  mov     [rsp+130h+var_D8], rsi
0x1800184bc  lea     r8, [rsp+130h+var_EC]
0x1800184c1  lea     rdx, [rsp+130h+var_F0]
0x1800184c6  lea     rcx, [rsp+130h+var_C0]
0x1800184cb  call    _lambda_803e9900112de776bddc00e9978beff3____lambda_803e9900112de776bddc00e9978beff3_
0x1800184d0  mov     rdx, rax
0x1800184d3  lea     rcx, [rbp+3Fh+var_70]
0x1800184d7  call    wil__ScopeExitNoExcept__lambda_73bdf23f9c00f0528e018ca4aa2f4a8b___
0x1800184dc  nop
0x1800184dd  mov     rsi, [r14]
0x1800184e0  add     rsi, 38h ; '8'
0x1800184e4  mov     rcx, rsi; SRWLock
0x1800184e7  call    cs:__imp_AcquireSRWLockShared
0x1800184ed  mov     [rsp+130h+var_D0], rsi
0x1800184f2  lea     r9, [rsp+130h+var_E0]; unsigned __int64 *
0x1800184f7  mov     r8b, r12b; unsigned __int8
0x1800184fa  mov     dl, dil; unsigned __int8
0x1800184fd  mov     rcx, r14; struct VCHANNEL_DATA *
0x180018500  call    ?I_LoadAsymKey@@YAKPEAUVCHANNEL_DATA@@EEPEA_K@Z; I_LoadAsymKey(VCHANNEL_DATA *,uchar,uchar,unsigned __int64 *)
0x180018505  mov     [rsp+130h+var_F0], eax
0x180018509  xor     r12d, r12d
0x18001850c  test    eax, eax
0x18001850e  jz      short loc_180018584
0x180018510  lea     edi, [r12+2]
0x180018515  mov     edx, edi
0x180018517  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001851c  lea     rax, WPP_GLOBAL_Control
0x180018523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001852a  cmp     rcx, rax
0x18001852d  jz      short loc_180018569
0x18001852f  test    byte ptr [rcx+1Ch], 1
0x180018533  jz      short loc_180018569
0x180018535  cmp     [rcx+19h], dil
0x180018539  jb      short loc_180018569
0x18001853b  lea     edx, [rdi+3Bh]
0x18001853e  lea     rax, aUnableToLoadTh_0; "Unable to load the requested RSA key"
0x180018545  mov     [rsp+130h+var_108], rax
0x18001854a  mov     eax, [rsp+130h+var_F0]
0x18001854e  mov     dword ptr [rsp+130h+var_110], eax
0x180018552  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180018559  lea     r8, WPP_b1753b5f523035523139d18de184cf7c_Traceguids
0x180018560  mov     rcx, [rcx+10h]
0x180018564  call    WPP_SF_sDs
0x180018569  mov     ebx, [rsp+130h+var_F0]
0x18001856d  test    rsi, rsi
0x180018570  jz      loc_180018868
0x180018576  mov     rcx, rsi; SRWLock
0x180018579  call    cs:__imp_ReleaseSRWLockShared
0x18001857f  jmp     loc_180018868
0x180018584  test    rsi, rsi
0x180018587  jz      short loc_180018592
0x180018589  mov     rcx, rsi; SRWLock
0x18001858c  call    cs:__imp_ReleaseSRWLockShared
0x180018592  lea     rax, [rsp+130h+var_E0]
0x180018597  mov     [rsp+130h+var_C0], rax
0x18001859c  mov     edi, 2
0x1800185a1  mov     [rbp+3Fh+var_B8], 102h
0x1800185a7  mov     rsi, [r14]
0x1800185aa  add     rsi, 38h ; '8'
0x1800185ae  mov     rcx, rsi; SRWLock
0x1800185b1  call    cs:__imp_AcquireSRWLockShared
0x1800185b7  mov     [rsp+130h+var_D0], rsi
0x1800185bc  lea     r9, [rsp+130h+var_D8]; unsigned __int64 *
0x1800185c1  mov     r8b, [rbp+3Fh+arg_20]; unsigned __int8
0x1800185c5  mov     dl, r15b; unsigned __int8
0x1800185c8  mov     rcx, r14; struct VCHANNEL_DATA *
0x1800185cb  call    ?I_LoadAsymKey@@YAKPEAUVCHANNEL_DATA@@EEPEA_K@Z; I_LoadAsymKey(VCHANNEL_DATA *,uchar,uchar,unsigned __int64 *)
0x1800185d0  mov     [rsp+130h+var_F0], eax
0x1800185d4  test    eax, eax
0x1800185d6  jz      short loc_180018647
0x1800185d8  mov     edx, edi
0x1800185da  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800185df  lea     rax, WPP_GLOBAL_Control
0x1800185e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185ed  cmp     rcx, rax
0x1800185f0  jz      short loc_18001862C
0x1800185f2  test    byte ptr [rcx+1Ch], 1
0x1800185f6  jz      short loc_18001862C
0x1800185f8  cmp     [rcx+19h], dil
0x1800185fc  jb      short loc_18001862C
0x1800185fe  lea     edx, [rdi+3Ch]
0x180018601  lea     rax, aUnableToLoadTh_0; "Unable to load the requested RSA key"
0x180018608  mov     [rsp+130h+var_108], rax
0x18001860d  mov     eax, [rsp+130h+var_F0]
0x180018611  mov     dword ptr [rsp+130h+var_110], eax
0x180018615  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001861c  lea     r8, WPP_b1753b5f523035523139d18de184cf7c_Traceguids
0x180018623  mov     rcx, [rcx+10h]
0x180018627  call    WPP_SF_sDs
0x18001862c  mov     ebx, [rsp+130h+var_F0]
0x180018630  test    rsi, rsi
0x180018633  jz      loc_18001885D
0x180018639  mov     rcx, rsi; SRWLock
0x18001863c  call    cs:__imp_ReleaseSRWLockShared
0x180018642  jmp     loc_18001885D
0x180018647  test    rsi, rsi
0x18001864a  jz      short loc_180018655
0x18001864c  mov     rcx, rsi; SRWLock
0x18001864f  call    cs:__imp_ReleaseSRWLockShared
0x180018655  lea     rax, [rsp+130h+var_D8]
0x18001865a  mov     [rsp+130h+var_D0], rax
0x18001865f  mov     [rsp+130h+var_C8], 102h
0x180018666  mov     rcx, [r13+0]
0x18001866a  mov     eax, [r13+8]
0x18001866e  sub     eax, ecx
0x180018670  mov     [rbp+3Fh+var_98], eax
0x180018673  mov     [rbp+3Fh+var_94], 31h ; '1'
0x18001867a  mov     [rbp+3Fh+var_90], rcx
0x18001867e  mov     [rbp+3Fh+var_B0], r12d
0x180018682  mov     [rbp+3Fh+var_AC], 1
0x180018689  lea     rax, [rbp+3Fh+var_98]
0x18001868d  mov     [rbp+3Fh+var_A8], rax
0x180018691  mov     [rsp+130h+var_E8], r12d
0x180018696  mov     [rsp+130h+var_F8], r12d
0x18001869b  lea     rax, [rsp+130h+var_E8]
0x1800186a0  mov     [rsp+130h+var_100], rax
0x1800186a5  mov     dword ptr [rsp+130h+var_108], r12d
0x1800186aa  mov     [rsp+130h+var_110], r12
0x1800186af  lea     r9, [rbp+3Fh+var_B0]
0x1800186b3  mov     r8d, edi
0x1800186b6  mov     rdx, [rsp+130h+var_E0]
0x1800186bb  mov     rcx, [rsp+130h+var_D8]
0x1800186c0  call    cs:__imp_NCryptCreateClaim
0x1800186c6  mov     [rsp+130h+var_EC], eax
0x1800186ca  test    eax, eax
0x1800186cc  jz      short loc_180018745
0x1800186ce  mov     edx, edi
0x1800186d0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800186d5  mov     r8d, [rsp+130h+var_EC]
0x1800186da  mov     ecx, r8d; int
0x1800186dd  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x1800186e2  mov     ebx, eax
0x1800186e4  mov     [rsp+130h+var_F0], eax
0x1800186e8  lea     rax, WPP_GLOBAL_Control
0x1800186ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186f6  cmp     rcx, rax
0x1800186f9  jz      loc_180018852
0x1800186ff  test    byte ptr [rcx+1Ch], 1
0x180018703  jz      loc_180018852
0x180018709  cmp     [rcx+19h], dil
0x18001870d  jb      loc_180018852
0x180018713  mov     edx, 3Fh ; '?'
0x180018718  lea     rax, aUnableToCreate_2; "Unable to create the claim"
0x18001871f  mov     [rsp+130h+var_108], rax
0x180018724  mov     dword ptr [rsp+130h+var_110], r8d
0x180018729  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180018730  lea     r8, WPP_b1753b5f523035523139d18de184cf7c_Traceguids
0x180018737  mov     rcx, [rcx+10h]
0x18001873b  call    WPP_SF_sDs
0x180018740  jmp     loc_18001884E
0x180018745  mov     edx, [rsp+130h+var_E8]
0x180018749  mov     r8, [rbx]
0x18001874c  mov     rcx, [rbx+8]
0x180018750  sub     rcx, r8
0x180018753  cmp     rdx, rcx
0x180018756  jnb     short loc_18001875E
0x180018758  lea     rax, [r8+rdx]
0x18001875c  jmp     short loc_180018785
0x18001875e  jbe     short loc_180018789
0x180018760  mov     rax, [rbx+10h]
0x180018764  sub     rax, r8
0x180018767  cmp     rdx, rax
0x18001876a  jbe     short loc_180018776
0x18001876c  mov     rcx, rbx
0x18001876f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180018774  jmp     short loc_180018789
0x180018776  sub     rdx, rcx
0x180018779  mov     r8, rbx
0x18001877c  mov     rcx, [rbx+8]
0x180018780  call    ??$_Uninitialized_value_construct_n@U?$secure_allocator@E@wil@@@std@@YAPEAEPEAE_KAEAU?$secure_allocator@E@wil@@@Z; std::_Uninitialized_value_construct_n<wil::secure_allocator<uchar>>(uchar *,unsigned __int64,wil::secure_allocator<uchar> &)
0x180018785  mov     [rbx+8], rax
0x180018789  mov     [rsp+130h+var_F8], r12d
0x18001878e  lea     rax, [rsp+130h+var_E8]
0x180018793  mov     [rsp+130h+var_100], rax
0x180018798  mov     eax, [rsp+130h+var_E8]
0x18001879c  mov     dword ptr [rsp+130h+var_108], eax
0x1800187a0  mov     rax, [rbx]
0x1800187a3  mov     [rsp+130h+var_110], rax
0x1800187a8  lea     r9, [rbp+3Fh+var_B0]
0x1800187ac  mov     r8d, edi
0x1800187af  mov     rdx, [rsp+130h+var_E0]
0x1800187b4  mov     rcx, [rsp+130h+var_D8]
0x1800187b9  call    cs:__imp_NCryptCreateClaim
0x1800187bf  mov     [rsp+130h+var_EC], eax
0x1800187c3  test    eax, eax
0x1800187c5  jz      short loc_18001880A
0x1800187c7  mov     edx, edi
0x1800187c9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800187ce  mov     r8d, [rsp+130h+var_EC]
0x1800187d3  mov     ecx, r8d; int
0x1800187d6  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x1800187db  mov     ebx, eax
0x1800187dd  mov     [rsp+130h+var_F0], eax
0x1800187e1  lea     rax, WPP_GLOBAL_Control
0x1800187e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187ef  cmp     rcx, rax
0x1800187f2  jz      short loc_180018852
0x1800187f4  test    byte ptr [rcx+1Ch], 1
0x1800187f8  jz      short loc_180018852
0x1800187fa  cmp     [rcx+19h], dil
0x1800187fe  jb      short loc_180018852
0x180018800  mov     edx, 40h ; '@'
0x180018805  jmp     loc_180018718
0x18001880a  mov     edx, [rsp+130h+var_E8]
0x18001880e  mov     r8, [rbx]
0x180018811  mov     rcx, [rbx+8]
0x180018815  sub     rcx, r8
0x180018818  cmp     rdx, rcx
0x18001881b  jnb     short loc_180018823
0x18001881d  lea     rax, [r8+rdx]
0x180018821  jmp     short loc_18001884A
0x180018823  jbe     short loc_18001884E
0x180018825  mov     rax, [rbx+10h]
0x180018829  sub     rax, r8
0x18001882c  cmp     rdx, rax
0x18001882f  jbe     short loc_18001883B
0x180018831  mov     rcx, rbx
0x180018834  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180018839  jmp     short loc_18001884E
0x18001883b  sub     rdx, rcx
0x18001883e  mov     r8, rbx
0x180018841  mov     rcx, [rbx+8]
0x180018845  call    ??$_Uninitialized_value_construct_n@U?$secure_allocator@E@wil@@@std@@YAPEAEPEAE_KAEAU?$secure_allocator@E@wil@@@Z; std::_Uninitialized_value_construct_n<wil::secure_allocator<uchar>>(uchar *,unsigned __int64,wil::secure_allocator<uchar> &)
0x18001884a  mov     [rbx+8], rax
0x18001884e  mov     ebx, [rsp+130h+var_F0]
0x180018852  lea     rcx, [rsp+130h+var_D0]
0x180018857  call    wil__details__ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741_____operator__
0x18001885c  nop
0x18001885d  lea     rcx, [rsp+130h+var_C0]
  ... truncated ...
```
