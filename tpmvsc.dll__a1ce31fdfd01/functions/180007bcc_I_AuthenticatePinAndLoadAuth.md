# I_AuthenticatePinAndLoadAuth

- ea: `0x180007bcc`
- end: `0x1800081b9`
- name: `I_AuthenticatePinAndLoadAuth`
- size: `1517`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180007a78`
- `0x18000b85c`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000653c`
- `0x180006740`
- `0x1800069b8`
- `0x180006a54`
- `0x1800072ec`
- `0x1800079e4`
- `0x180007bcc`
- `0x180008c3c`
- `0x180008d28`
- `0x18000a46c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c0c8`
- `0x18000c198`
- `0x1800121dc`
- `0x180012580`
- `0x18001280c`
- `0x1800128c4`
- `0x18001e9a8`
- `0x18002b378`
- `0x1800348a0`

## string_xrefs

- `0x1800080f6`: `Unable to cache auth key`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall I_AuthenticatePinAndLoadAuth(struct VCHANNEL_DATA *a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // r8d
  _QWORD *v10; // rcx
  int v11; // edx
  const char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // edi
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  int v18; // edx
  const char *v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  int v24; // edx
  const char *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int Handle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-C8h] BYREF
  struct VCHANNEL_DATA *v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v35[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v36; // [rsp+88h] [rbp-78h] BYREF
  NCRYPT_HANDLE *p_hObject; // [rsp+90h] [rbp-70h] BYREF
  __int16 v38; // [rsp+98h] [rbp-68h]
  _QWORD v39[3]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v40[5]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v41[96]; // [rsp+E0h] [rbp-20h] BYREF
  char v42[32]; // [rsp+140h] [rbp+40h] BYREF

  v31 = a1;
  v30 = a2;
  Handle = 0;
  v32 = 0;
  strcpy(v42, "I_AuthenticatePinAndLoadAuth");
  v39[0] = v42;
  v39[1] = &v32;
  v39[2] = &Handle;
  lambda_8c0f4360a795fd7a3fc8b19cc4faff7d_::operator()(v39);
  v32 = 1;
  v36 = v39;
  if ( !v31 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( v30 - 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  Handle = I_Deauthenticate(v31);
  if ( Handle )
  {
    WppTraceIndent(v6, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle,
        (__int64)"Unable to deauthenticate the card");
    }
    v7 = Handle;
    goto LABEL_72;
  }
  memset_0(v41, 0, 0x5Cu);
  I_PinMapGetRecord(*(_QWORD *)v31, v30, v41);
  if ( !I_PinMapIsActive((const struct PIN_MAP_RECORD *)v41) )
  {
    WppTraceIndent(v8, 2u);
    v9 = -2146435038;
    Handle = -2146435038;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v11 = 55;
    v12 = "Role is not active";
LABEL_16:
    WPP_SF_sDs(
      v10[2],
      v11,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      v9,
      (__int64)v12);
    v9 = Handle;
LABEL_17:
    v7 = v9;
    goto LABEL_72;
  }
  if ( I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v41) )
  {
    WppTraceIndent(v13, 2u);
    v9 = -2146434964;
    Handle = -2146434964;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v11 = 56;
    v12 = "The role has been blocked";
    goto LABEL_16;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v34);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v35);
  v15 = -2146434965;
  if ( *a3 == a3[1] )
  {
    v21 = -2146434965;
    Handle = -2146434965;
  }
  else
  {
    hObject = 0;
    Handle = I_PinMapGetHandle(*(_QWORD *)v31, v30, &hObject);
    if ( Handle )
    {
      WppTraceIndent(v16, 2u);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v18 = 57;
      v19 = "Unable to get smart card key";
LABEL_29:
      WPP_SF_sDs(
        v17[2],
        v18,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle,
        (__int64)v19);
LABEL_30:
      v7 = Handle;
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v35);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v34);
      goto LABEL_72;
    }
    Handle = I_AuthenticateKspKey(hObject);
    if ( Handle )
    {
      WppTraceIndent(v20, 2u);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v18 = 58;
      v19 = "Unable to authenticate smart card key";
      goto LABEL_29;
    }
    p_hObject = &hObject;
    v38 = 258;
    v40[0] = &v31;
    v40[1] = &v30;
    v40[2] = &hObject;
    v40[3] = v34;
    Handle = lambda_0f9619d07a780b343d51de9d26b7adda_::operator()(v40);
    wil::details::ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741___::operator()(&p_hObject);
    v21 = Handle;
  }
  if ( v21 == -2146434965 )
  {
    Handle = I_DecreaseRemainingRetryCount(*(_QWORD *)v31, v30);
    if ( Handle )
    {
      WppTraceIndent(v22, 2u);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v18 = 60;
      v19 = "Failed to reduce remaining retry count";
      goto LABEL_29;
    }
    WppTraceIndent(v22, 2u);
    Handle = -2146434965;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_49:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v35);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v34);
      v7 = v15;
      goto LABEL_72;
    }
    v24 = 61;
    v25 = "Role authentication failed";
LABEL_48:
    WPP_SF_sDs(
      v23[2],
      v24,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      v15,
      (__int64)v25);
    v15 = Handle;
    goto LABEL_49;
  }
  if ( v21 )
  {
    WppTraceIndent(v14, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    v18 = 62;
    v19 = "Loading auth key failed";
    goto LABEL_29;
  }
  if ( v34[1] - v34[0] != 20 )
  {
    WppTraceIndent(v14, 2u);
    v15 = 13;
    Handle = 13;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v24 = 63;
    v25 = "Auth blob is corrupted";
    goto LABEL_48;
  }
  Handle = I_ProtectMemory(v34, v35);
  if ( Handle )
  {
    WppTraceIndent(v26, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    v18 = 64;
    v19 = "Unable to cache auth key";
    goto LABEL_29;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=((_QWORD *)v31 + 16, (__int64)v35);
  *((_DWORD *)v31 + 16) = v30;
  Handle = I_ResetRemainingRetryCount(*(_QWORD *)v31, v30);
  if ( Handle )
  {
    WppTraceIndent(v27, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids);
    }
    Handle = 0;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v35);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v34);
  v7 = 0;
LABEL_72:
  WppTraceUnwinder__lambda_8c0f4360a795fd7a3fc8b19cc4faff7d____::_WppTraceUnwinder__lambda_8c0f4360a795fd7a3fc8b19cc4faff7d____(&v36);
  return v7;
}

```

## disassembly

```asm
0x180007bcc  push    rbp
0x180007bce  push    rbx
0x180007bcf  push    rsi
0x180007bd0  push    rdi
0x180007bd1  push    r14
0x180007bd3  lea     rbp, [rsp-70h]
0x180007bd8  sub     rsp, 170h
0x180007bdf  mov     rax, cs:__security_cookie
0x180007be6  xor     rax, rsp
0x180007be9  mov     [rbp+90h+var_30], rax
0x180007bed  mov     rsi, r8
0x180007bf0  mov     [rsp+190h+var_150], rcx
0x180007bf5  mov     [rsp+190h+var_158], edx
0x180007bf9  mov     [rsp+190h+var_160], 0
0x180007c01  mov     [rsp+190h+var_148], 0
0x180007c09  movups  xmm0, xmmword ptr cs:aIAuthenticatep; "I_AuthenticatePinAndLoadAuth"
0x180007c10  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x180007c14  movups  xmm1, xmmword ptr cs:aIAuthenticatep+0Dh; "ePinAndLoadAuth"
0x180007c1b  movups  xmmword ptr [rbp+90h+var_50+0Dh], xmm1
0x180007c1f  lea     rax, [rbp+90h+var_50]
0x180007c23  mov     [rbp+90h+var_F0], rax
0x180007c27  lea     rax, [rsp+190h+var_148]
0x180007c2c  mov     [rbp+90h+var_E8], rax
0x180007c30  lea     rax, [rsp+190h+var_160]
0x180007c35  mov     [rbp+90h+var_E0], rax
0x180007c39  lea     rcx, [rbp+90h+var_F0]
0x180007c3d  call    _lambda_8c0f4360a795fd7a3fc8b19cc4faff7d___operator__
0x180007c42  mov     r14d, 1
0x180007c48  mov     [rsp+190h+var_148], r14d
0x180007c4d  lea     rax, [rbp+90h+var_F0]
0x180007c51  mov     [rbp+90h+var_108], rax
0x180007c55  cmp     [rsp+190h+var_150], 0
0x180007c5b  jnz     short loc_180007C62
0x180007c5d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007c62  mov     eax, [rsp+190h+var_158]
0x180007c66  dec     eax
0x180007c68  cmp     eax, r14d
0x180007c6b  jbe     short loc_180007C72
0x180007c6d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007c72  mov     rcx, [rsp+190h+var_150]; struct VCHANNEL_DATA *
0x180007c77  call    ?I_Deauthenticate@@YAKPEAUVCHANNEL_DATA@@@Z; I_Deauthenticate(VCHANNEL_DATA *)
0x180007c7c  mov     [rsp+190h+var_160], eax
0x180007c80  test    eax, eax
0x180007c82  jz      short loc_180007CE5
0x180007c84  mov     ebx, 2
0x180007c89  mov     edx, ebx
0x180007c8b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007c90  lea     rax, WPP_GLOBAL_Control
0x180007c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c9e  cmp     rcx, rax
0x180007ca1  jz      short loc_180007CDC
0x180007ca3  test    [rcx+1Ch], r14b
0x180007ca7  jz      short loc_180007CDC
0x180007ca9  cmp     [rcx+19h], bl
0x180007cac  jb      short loc_180007CDC
0x180007cae  lea     edx, [rbx+34h]
0x180007cb1  lea     rax, aUnableToDeauth; "Unable to deauthenticate the card"
0x180007cb8  mov     [rsp+190h+var_168], rax
0x180007cbd  mov     eax, [rsp+190h+var_160]
0x180007cc1  mov     [rsp+190h+var_170], eax
0x180007cc5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180007ccc  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180007cd3  mov     rcx, [rcx+10h]
0x180007cd7  call    WPP_SF_sDs
0x180007cdc  mov     ebx, [rsp+190h+var_160]
0x180007ce0  jmp     loc_180008194
0x180007ce5  xor     edx, edx; Val
0x180007ce7  lea     r8d, [rdx+5Ch]; Size
0x180007ceb  lea     rcx, [rbp+90h+var_B0]; void *
0x180007cef  call    memset_0
0x180007cf4  lea     r8, [rbp+90h+var_B0]
0x180007cf8  mov     edx, [rsp+190h+var_158]
0x180007cfc  mov     rcx, [rsp+190h+var_150]
0x180007d01  mov     rcx, [rcx]
0x180007d04  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x180007d09  lea     rcx, [rbp+90h+var_B0]; struct PIN_MAP_RECORD *
0x180007d0d  call    ?I_PinMapIsActive@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsActive(PIN_MAP_RECORD const *)
0x180007d12  test    eax, eax
0x180007d14  jnz     short loc_180007D81
0x180007d16  lea     ebx, [rax+2]
0x180007d19  mov     edx, ebx
0x180007d1b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007d20  mov     r8d, 80100022h
0x180007d26  mov     [rsp+190h+var_160], r8d
0x180007d2b  lea     rax, WPP_GLOBAL_Control
0x180007d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d39  cmp     rcx, rax
0x180007d3c  jz      short loc_180007D79
0x180007d3e  test    [rcx+1Ch], r14b
0x180007d42  jz      short loc_180007D79
0x180007d44  cmp     [rcx+19h], bl
0x180007d47  jb      short loc_180007D79
0x180007d49  lea     edx, [rbx+35h]
0x180007d4c  lea     rax, aRoleIsNotActiv; "Role is not active"
0x180007d53  mov     [rsp+190h+var_168], rax
0x180007d58  mov     [rsp+190h+var_170], r8d
0x180007d5d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180007d64  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180007d6b  mov     rcx, [rcx+10h]
0x180007d6f  call    WPP_SF_sDs
0x180007d74  mov     r8d, [rsp+190h+var_160]
0x180007d79  mov     ebx, r8d
0x180007d7c  jmp     loc_180008194
0x180007d81  lea     rcx, [rbp+90h+var_B0]; struct PIN_MAP_RECORD *
0x180007d85  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x180007d8a  test    eax, eax
0x180007d8c  jz      short loc_180007DCF
0x180007d8e  mov     ebx, 2
0x180007d93  mov     edx, ebx
0x180007d95  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007d9a  mov     r8d, 8010006Ch
0x180007da0  mov     [rsp+190h+var_160], r8d
0x180007da5  lea     rax, WPP_GLOBAL_Control
0x180007dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180007db3  cmp     rcx, rax
0x180007db6  jz      short loc_180007D79
0x180007db8  test    [rcx+1Ch], r14b
0x180007dbc  jz      short loc_180007D79
0x180007dbe  cmp     [rcx+19h], bl
0x180007dc1  jb      short loc_180007D79
0x180007dc3  lea     edx, [rbx+36h]
0x180007dc6  lea     rax, aTheRoleHasBeen; "The role has been blocked"
0x180007dcd  jmp     short loc_180007D53
0x180007dcf  lea     rcx, [rsp+190h+var_138]
0x180007dd4  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180007dd9  nop
0x180007dda  lea     rcx, [rsp+190h+var_120]
0x180007ddf  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180007de4  nop
0x180007de5  mov     rax, [rsi+8]
0x180007de9  mov     edi, 8010006Bh
0x180007dee  mov     ebx, 2
0x180007df3  cmp     [rsi], rax
0x180007df6  jz      loc_180007F2E
0x180007dfc  mov     [rsp+190h+hObject], 0
0x180007e05  lea     r8, [rsp+190h+hObject]
0x180007e0a  mov     edx, [rsp+190h+var_158]
0x180007e0e  mov     rcx, [rsp+190h+var_150]
0x180007e13  mov     rcx, [rcx]
0x180007e16  call    ?I_PinMapGetHandle@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEA_K@Z; I_PinMapGetHandle(VCARD_DATA const *,_CARD_ROLE,unsigned __int64 *)
0x180007e1b  mov     [rsp+190h+var_160], eax
0x180007e1f  test    eax, eax
0x180007e21  jz      short loc_180007E94
0x180007e23  mov     edx, ebx
0x180007e25  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007e2a  lea     rax, WPP_GLOBAL_Control
0x180007e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e38  cmp     rcx, rax
0x180007e3b  jz      short loc_180007E76
0x180007e3d  test    [rcx+1Ch], r14b
0x180007e41  jz      short loc_180007E76
0x180007e43  cmp     [rcx+19h], bl
0x180007e46  jb      short loc_180007E76
0x180007e48  lea     edx, [rbx+37h]
0x180007e4b  lea     rax, aUnableToGetSma_0; "Unable to get smart card key"
0x180007e52  mov     [rsp+190h+var_168], rax
0x180007e57  mov     eax, [rsp+190h+var_160]
0x180007e5b  mov     [rsp+190h+var_170], eax
0x180007e5f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180007e66  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180007e6d  mov     rcx, [rcx+10h]
0x180007e71  call    WPP_SF_sDs
0x180007e76  mov     ebx, [rsp+190h+var_160]
0x180007e7a  lea     rcx, [rsp+190h+var_120]
0x180007e7f  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180007e84  nop
0x180007e85  lea     rcx, [rsp+190h+var_138]
0x180007e8a  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180007e8f  jmp     loc_180008194
0x180007e94  mov     rdx, rsi
0x180007e97  mov     rcx, [rsp+190h+hObject]; hObject
0x180007e9c  call    ?I_AuthenticateKspKey@@YAK_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_AuthenticateKspKey(unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x180007ea1  mov     [rsp+190h+var_160], eax
0x180007ea5  test    eax, eax
0x180007ea7  jz      short loc_180007EDF
0x180007ea9  mov     edx, ebx
0x180007eab  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007eb0  lea     rax, WPP_GLOBAL_Control
0x180007eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ebe  cmp     rcx, rax
0x180007ec1  jz      short loc_180007E76
0x180007ec3  test    [rcx+1Ch], r14b
0x180007ec7  jz      short loc_180007E76
0x180007ec9  cmp     [rcx+19h], bl
0x180007ecc  jb      short loc_180007E76
0x180007ece  mov     edx, 3Ah ; ':'
0x180007ed3  lea     rax, aUnableToAuthen_4; "Unable to authenticate smart card key"
0x180007eda  jmp     loc_180007E52
0x180007edf  lea     rax, [rsp+190h+hObject]
0x180007ee4  mov     [rbp+90h+var_100], rax
0x180007ee8  mov     [rbp+90h+var_F8], 102h
0x180007eee  lea     rax, [rsp+190h+var_150]
0x180007ef3  mov     [rbp+90h+var_D8], rax
0x180007ef7  lea     rax, [rsp+190h+var_158]
0x180007efc  mov     [rbp+90h+var_D0], rax
0x180007f00  lea     rax, [rsp+190h+hObject]
0x180007f05  mov     [rbp+90h+var_C8], rax
0x180007f09  lea     rax, [rsp+190h+var_138]
0x180007f0e  mov     [rbp+90h+var_C0], rax
0x180007f12  lea     rcx, [rbp+90h+var_D8]
0x180007f16  call    _lambda_0f9619d07a780b343d51de9d26b7adda___operator__
0x180007f1b  mov     [rsp+190h+var_160], eax
0x180007f1f  lea     rcx, [rbp+90h+var_100]
0x180007f23  call    wil__details__ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741_____operator__
0x180007f28  mov     eax, [rsp+190h+var_160]
0x180007f2c  jmp     short loc_180007F34
0x180007f2e  mov     eax, edi
0x180007f30  mov     [rsp+190h+var_160], eax
0x180007f34  cmp     eax, edi
0x180007f36  jnz     loc_18000800A
0x180007f3c  mov     edx, [rsp+190h+var_158]
0x180007f40  mov     rcx, [rsp+190h+var_150]
0x180007f45  mov     rcx, [rcx]
0x180007f48  call    I_DecreaseRemainingRetryCount
0x180007f4d  mov     [rsp+190h+var_160], eax
0x180007f51  mov     edx, ebx
0x180007f53  test    eax, eax
0x180007f55  jz      short loc_180007F97
0x180007f57  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007f5c  lea     rax, WPP_GLOBAL_Control
0x180007f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f6a  cmp     rcx, rax
0x180007f6d  jz      loc_180007E76
0x180007f73  test    [rcx+1Ch], r14b
0x180007f77  jz      loc_180007E76
0x180007f7d  cmp     [rcx+19h], bl
0x180007f80  jb      loc_180007E76
0x180007f86  mov     edx, 3Ch ; '<'
0x180007f8b  lea     rax, aFailedToReduce; "Failed to reduce remaining retry count"
0x180007f92  jmp     loc_180007E52
0x180007f97  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007f9c  mov     [rsp+190h+var_160], edi
0x180007fa0  lea     rax, WPP_GLOBAL_Control
0x180007fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fae  cmp     rcx, rax
0x180007fb1  jz      short loc_180007FEE
0x180007fb3  test    [rcx+1Ch], r14b
0x180007fb7  jz      short loc_180007FEE
0x180007fb9  cmp     [rcx+19h], bl
0x180007fbc  jb      short loc_180007FEE
0x180007fbe  mov     edx, 3Dh ; '='
0x180007fc3  lea     rax, aRoleAuthentica; "Role authentication failed"
0x180007fca  mov     [rsp+190h+var_168], rax
0x180007fcf  mov     [rsp+190h+var_170], edi
0x180007fd3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180007fda  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180007fe1  mov     rcx, [rcx+10h]
0x180007fe5  call    WPP_SF_sDs
0x180007fea  mov     edi, [rsp+190h+var_160]
0x180007fee  lea     rcx, [rsp+190h+var_120]
0x180007ff3  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180007ff8  nop
0x180007ff9  lea     rcx, [rsp+190h+var_138]
0x180007ffe  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180008003  mov     ebx, edi
0x180008005  jmp     loc_180008194
0x18000800a  test    eax, eax
0x18000800c  jz      short loc_180008050
0x18000800e  mov     edx, ebx
0x180008010  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008015  lea     rax, WPP_GLOBAL_Control
0x18000801c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008023  cmp     rcx, rax
0x180008026  jz      loc_180007E76
0x18000802c  test    [rcx+1Ch], r14b
0x180008030  jz      loc_180007E76
0x180008036  cmp     [rcx+19h], bl
0x180008039  jb      loc_180007E76
0x18000803f  mov     edx, 3Eh ; '>'
0x180008044  lea     rax, aLoadingAuthKey; "Loading auth key failed"
0x18000804b  jmp     loc_180007E52
0x180008050  mov     rax, [rsp+190h+var_130]
0x180008055  sub     rax, [rsp+190h+var_138]
0x18000805a  cmp     rax, 14h
0x18000805e  jz      short loc_1800080A9
0x180008060  mov     edx, ebx
0x180008062  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008067  mov     edi, 0Dh
0x18000806c  mov     [rsp+190h+var_160], edi
0x180008070  lea     rax, WPP_GLOBAL_Control
0x180008077  mov     rcx, cs:WPP_GLOBAL_Control
0x18000807e  cmp     rcx, rax
0x180008081  jz      loc_180007FEE
0x180008087  test    [rcx+1Ch], r14b
0x18000808b  jz      loc_180007FEE
0x180008091  cmp     [rcx+19h], bl
0x180008094  jb      loc_180007FEE
0x18000809a  lea     edx, [rdi+32h]
0x18000809d  lea     rax, aAuthBlobIsCorr; "Auth blob is corrupted"
0x1800080a4  jmp     loc_180007FCA
0x1800080a9  lea     rdx, [rsp+190h+var_120]
0x1800080ae  lea     rcx, [rsp+190h+var_138]
0x1800080b3  call    ?I_ProtectMemory@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_ProtectMemory(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x1800080b8  mov     [rsp+190h+var_160], eax
0x1800080bc  test    eax, eax
0x1800080be  jz      short loc_180008102
0x1800080c0  mov     edx, ebx
0x1800080c2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800080c7  lea     rax, WPP_GLOBAL_Control
0x1800080ce  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
