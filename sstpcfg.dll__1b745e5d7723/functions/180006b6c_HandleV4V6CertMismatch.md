# HandleV4V6CertMismatch

- ea: `0x180006b6c`
- end: `0x1800070e2`
- name: `HandleV4V6CertMismatch`
- size: `1398`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007450`

## callees

- `0x180004f10`
- `0x180006b6c`
- `0x180008968`
- `0x180008be4`
- `0x180009b34`
- `0x180009ee4`
- `0x18000a014`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertCompareCertificate` at `0x180006d72`
- `CRYPT32!CertCompareCertificate` at `0x180006d72`
- `rtutils!RouterLogEventStringW` at `0x1800070a2`
- `rtutils!RouterLogEventStringW` at `0x1800070a2`
- `rtutils!RouterLogEventW` at `0x180006f78`
- `rtutils!RouterLogEventW` at `0x180006f78`

## string_xrefs

- `0x180006c34`: `Certificate is configured for V6 but not for V4, attempting to configure V4.`
- `0x180006cfa`: `Certificate is configured for V4 but not for V6, attempting to configure V6`

## pseudocode

```c
__int64 __fastcall HandleV4V6CertMismatch(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 v7; // r14
  __int64 v11; // rdx
  DWORD v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  const wchar_t *v16; // r8
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  bool v21; // bl
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  DWORD dwErrorCode; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  bool v28; // [rsp+42h] [rbp-6Fh]
  __int128 v31; // [rsp+68h] [rbp-49h] BYREF
  int v32; // [rsp+78h] [rbp-39h]
  _OWORD v33[2]; // [rsp+80h] [rbp-31h] BYREF

  v7 = a7;
  v32 = 0;
  v31 = 0;
  memset(v33, 0, sizeof(v33));
  if ( !a4 )
  {
    if ( !a7 )
      return 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90);
    }
    if ( (_QWORD)xmmword_1800146E0 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        xmmword_1800146E0,
        L"Certificate is configured for V6 but not for V4, attempting to configure V4.");
    v12 = SetSslCertificateToHttpV4(a1, a7);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v14 = 91;
LABEL_15:
        WPP_SF_(v13[2], v14);
        goto LABEL_16;
      }
      goto LABEL_16;
    }
LABEL_92:
    LOBYTE(v11) = 3;
    dwErrorCode = GetHashFromCertificate(v7, v11, &v31, v33);
    v12 = dwErrorCode;
    if ( dwErrorCode )
      RouterLogEventStringW(EventSource, 1u, 0x15u, 0, 0, dwErrorCode, 0);
    else
      StoreCertHash(0, v25, v26, (const BYTE *)&v31, (BYTE *)v33, 0);
    return v12;
  }
  if ( !a7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92);
    }
    if ( (_QWORD)xmmword_1800146E0 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        xmmword_1800146E0,
        L"Certificate is configured for V4 but not for V6, attempting to configure V6");
    v12 = SetSslCertificateToHttpV6(a1, a4);
    if ( v12 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_32;
      }
      v18 = 93;
LABEL_31:
      WPP_SF_(v17[2], v18);
LABEL_32:
      v15 = xmmword_1800146E0;
      if ( !(_QWORD)xmmword_1800146E0 )
        return v12;
      v16 = L"Failed to bind V6 binding, bail out";
      goto LABEL_18;
    }
    goto LABEL_91;
  }
  if ( CertCompareCertificate(0x10001u, *(PCERT_INFO *)(a4 + 24), *(PCERT_INFO *)(a7 + 24)) )
    goto LABEL_91;
  v19 = *(_QWORD *)(a5 + 24) - 0x458BCD49BA195980LL;
  if ( *(_QWORD *)(a5 + 24) == 0x458BCD49BA195980LL )
    v19 = *(_QWORD *)(a5 + 32) - 0x75CDADE04EC8239ELL;
  v28 = v19 == 0;
  v20 = *(_QWORD *)(a2 + 24) - 0x458BCD49BA195980LL;
  if ( *(_QWORD *)(a2 + 24) == 0x458BCD49BA195980LL )
    v20 = *(_QWORD *)(a2 + 32) - 0x75CDADE04EC8239ELL;
  v21 = v20 == 0;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94);
    v22 = WPP_GLOBAL_Control;
  }
  v23 = *((_QWORD *)&xmmword_1800146E0 + 1);
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      L"Current V4 and V6 SSL binding does not matches, Trying to correct it");
    v22 = WPP_GLOBAL_Control;
    v23 = *((_QWORD *)&xmmword_1800146E0 + 1);
  }
  if ( v28 )
  {
    if ( !v21 )
    {
      if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x40) != 0 && *((_BYTE *)v22 + 25) >= 3u )
      {
        WPP_SF_(v22[2], 96);
        v23 = *((_QWORD *)&xmmword_1800146E0 + 1);
      }
      if ( v23 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          v23,
          L"Current V6 SSL binding does not matches, Trying to correct it");
      v12 = UnbindSslCertificate(0, a5, a6);
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98);
        }
        v15 = xmmword_1800146E0;
        if ( !(_QWORD)xmmword_1800146E0 )
          return v12;
        v16 = L"Failed to unbind V6 binding, bail out";
        goto LABEL_18;
      }
      v12 = SetSslCertificateToHttpV6(a1, a4);
      if ( v12 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_32;
        }
        v18 = 97;
        goto LABEL_31;
      }
LABEL_91:
      v7 = a4;
      goto LABEL_92;
    }
LABEL_66:
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x40) != 0 && *((_BYTE *)v22 + 25) )
      WPP_SF_(v22[2], 95);
    if ( (_QWORD)xmmword_1800146E0 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        xmmword_1800146E0,
        L"Current V4 and V6 SSL binding does not matches, bail out");
    RouterLogEventW(EventSource, 1u, 0x18u, 0, 0, 0);
    return 13;
  }
  if ( !v21 )
    goto LABEL_66;
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x40) != 0 && *((_BYTE *)v22 + 25) >= 3u )
  {
    WPP_SF_(v22[2], 99);
    v23 = *((_QWORD *)&xmmword_1800146E0 + 1);
  }
  if ( v23 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      v23,
      L"Current V4 SSL binding does not matches, Trying to correct it");
  LOBYTE(v22) = 1;
  v12 = UnbindSslCertificate(v22, a2, a3);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101);
    }
    v15 = xmmword_1800146E0;
    if ( !(_QWORD)xmmword_1800146E0 )
      return v12;
    v16 = L"Failed to unbind V4 binding, bail out";
    goto LABEL_18;
  }
  v12 = SetSslCertificateToHttpV4(a1, a7);
  if ( !v12 )
    goto LABEL_92;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v14 = 100;
    goto LABEL_15;
  }
LABEL_16:
  v15 = xmmword_1800146E0;
  if ( (_QWORD)xmmword_1800146E0 )
  {
    v16 = L"Failed to bind V4 binding, bail out";
LABEL_18:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v15, v16);
  }
  return v12;
}

```

## disassembly

```asm
0x180006b6c  push    rbp
0x180006b6e  push    rbx
0x180006b6f  push    rsi
0x180006b70  push    r12
0x180006b72  push    r13
0x180006b74  push    r14
0x180006b76  lea     rbp, [rsp-7]
0x180006b7b  sub     rsp, 0B8h
0x180006b82  mov     rax, cs:__security_cookie
0x180006b89  xor     rax, rsp
0x180006b8c  mov     [rbp+2Fh+var_40], rax
0x180006b90  mov     r12, [rbp+2Fh+arg_20]
0x180006b94  xor     eax, eax
0x180006b96  mov     r14, [rbp+2Fh+arg_30]
0x180006b9a  xorps   xmm1, xmm1
0x180006b9d  mov     [rbp+2Fh+var_88], r8d
0x180006ba1  xorps   xmm0, xmm0
0x180006ba4  mov     [rbp+2Fh+var_80], rdx
0x180006ba8  mov     r13, r9
0x180006bab  mov     [rbp+2Fh+var_A0], cx
0x180006baf  mov     rbx, rdx
0x180006bb2  mov     dword ptr [rbp+2Fh+var_98], 0BA195980h
0x180006bb9  mov     dword ptr [rbp+2Fh+var_98+4], 458BCD49h
0x180006bc0  mov     dword ptr [rbp+2Fh+var_90], 4EC8239Eh
0x180006bc7  mov     dword ptr [rbp+2Fh+var_90+4], 75CDADE0h
0x180006bce  mov     [rbp+2Fh+var_68], eax
0x180006bd1  movups  [rbp+2Fh+var_78], xmm0
0x180006bd5  movups  [rbp+2Fh+var_60], xmm1
0x180006bd9  movups  [rbp+2Fh+var_50], xmm1
0x180006bdd  test    r9, r9
0x180006be0  jnz     loc_180006CB2
0x180006be6  test    r14, r14
0x180006be9  jnz     short loc_180006BF4
0x180006beb  lea     eax, [r9+57h]
0x180006bef  jmp     loc_1800070C5
0x180006bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bfb  lea     rsi, WPP_GLOBAL_Control
0x180006c02  cmp     rcx, rsi
0x180006c05  jz      short loc_180006C21
0x180006c07  test    byte ptr [rcx+1Ch], 40h
0x180006c0b  jz      short loc_180006C21
0x180006c0d  cmp     byte ptr [rcx+19h], 2
0x180006c11  jb      short loc_180006C21
0x180006c13  mov     rcx, [rcx+10h]
0x180006c17  mov     edx, 5Ah ; 'Z'
0x180006c1c  call    WPP_SF_
0x180006c21  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006c28  test    rdx, rdx
0x180006c2b  jz      short loc_180006C47
0x180006c2d  mov     rcx, cs:gSstpCfgEtwContext
0x180006c34  lea     r8, aCertificateIsC_0; "Certificate is configured for V6 but no"...
0x180006c3b  mov     rax, cs:gSstpCfgTemplateFunc
0x180006c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c47  movzx   ecx, [rbp+2Fh+var_A0]
0x180006c4b  mov     rdx, r14
0x180006c4e  call    SetSslCertificateToHttpV4
0x180006c53  mov     ebx, eax
0x180006c55  test    eax, eax
0x180006c57  jz      loc_180007063
0x180006c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c64  cmp     rcx, rsi
0x180006c67  jz      short loc_180006C83
0x180006c69  test    byte ptr [rcx+1Ch], 40h
0x180006c6d  jz      short loc_180006C83
0x180006c6f  cmp     byte ptr [rcx+19h], 1
0x180006c73  jb      short loc_180006C83
0x180006c75  mov     edx, 5Bh ; '['
0x180006c7a  mov     rcx, [rcx+10h]
0x180006c7e  call    WPP_SF_
0x180006c83  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006c8a  test    rdx, rdx
0x180006c8d  jz      loc_1800070C3
0x180006c93  lea     r8, aFailedToBindV4; "Failed to bind V4 binding, bail out"
0x180006c9a  mov     rcx, cs:gSstpCfgEtwContext
0x180006ca1  mov     rax, cs:gSstpCfgTemplateFunc
0x180006ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cad  jmp     loc_1800070C3
0x180006cb2  test    r14, r14
0x180006cb5  jnz     loc_180006D65
0x180006cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cc2  lea     rsi, WPP_GLOBAL_Control
0x180006cc9  cmp     rcx, rsi
0x180006ccc  jz      short loc_180006CE7
0x180006cce  test    byte ptr [rcx+1Ch], 40h
0x180006cd2  jz      short loc_180006CE7
0x180006cd4  cmp     byte ptr [rcx+19h], 2
0x180006cd8  jb      short loc_180006CE7
0x180006cda  mov     rcx, [rcx+10h]
0x180006cde  lea     edx, [r14+5Ch]
0x180006ce2  call    WPP_SF_
0x180006ce7  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006cee  test    rdx, rdx
0x180006cf1  jz      short loc_180006D0D
0x180006cf3  mov     rcx, cs:gSstpCfgEtwContext
0x180006cfa  lea     r8, aCertificateIsC; "Certificate is configured for V4 but no"...
0x180006d01  mov     rax, cs:gSstpCfgTemplateFunc
0x180006d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d0d  movzx   ecx, [rbp+2Fh+var_A0]
0x180006d11  mov     rdx, r13
0x180006d14  call    SetSslCertificateToHttpV6
0x180006d19  mov     ebx, eax
0x180006d1b  test    eax, eax
0x180006d1d  jz      loc_180007060
0x180006d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d2a  cmp     rcx, rsi
0x180006d2d  jz      short loc_180006D49
0x180006d2f  test    byte ptr [rcx+1Ch], 40h
0x180006d33  jz      short loc_180006D49
0x180006d35  cmp     byte ptr [rcx+19h], 1
0x180006d39  jb      short loc_180006D49
0x180006d3b  mov     edx, 5Dh ; ']'
0x180006d40  mov     rcx, [rcx+10h]
0x180006d44  call    WPP_SF_
0x180006d49  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006d50  test    rdx, rdx
0x180006d53  jz      loc_1800070C3
0x180006d59  lea     r8, aFailedToBindV6; "Failed to bind V6 binding, bail out"
0x180006d60  jmp     loc_180006C9A
0x180006d65  mov     r8, [r14+18h]; pCertId2
0x180006d69  mov     ecx, 10001h; dwCertEncodingType
0x180006d6e  mov     rdx, [r9+18h]; pCertId1
0x180006d72  call    cs:__imp_CertCompareCertificate
0x180006d78  test    eax, eax
0x180006d7a  jnz     loc_180007060
0x180006d80  mov     rax, [r12+18h]
0x180006d85  sub     rax, [rbp+2Fh+var_98]
0x180006d89  jnz     short loc_180006D94
0x180006d8b  mov     rax, [r12+20h]
0x180006d90  sub     rax, [rbp+2Fh+var_90]
0x180006d94  test    rax, rax
0x180006d97  mov     rax, [rbx+18h]
0x180006d9b  setz    [rbp+2Fh+var_9E]
0x180006d9f  sub     rax, [rbp+2Fh+var_98]
0x180006da3  jnz     short loc_180006DAD
0x180006da5  mov     rax, [rbx+20h]
0x180006da9  sub     rax, [rbp+2Fh+var_90]
0x180006dad  test    rax, rax
0x180006db0  setz    bl
0x180006db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dba  lea     rsi, WPP_GLOBAL_Control
0x180006dc1  cmp     rcx, rsi
0x180006dc4  jz      short loc_180006DE7
0x180006dc6  test    byte ptr [rcx+1Ch], 40h
0x180006dca  jz      short loc_180006DE7
0x180006dcc  cmp     byte ptr [rcx+19h], 3
0x180006dd0  jb      short loc_180006DE7
0x180006dd2  mov     rcx, [rcx+10h]
0x180006dd6  mov     edx, 5Eh ; '^'
0x180006ddb  call    WPP_SF_
0x180006de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006de7  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180006dee  test    rdx, rdx
0x180006df1  jz      short loc_180006E1B
0x180006df3  mov     rcx, cs:gSstpCfgEtwContext
0x180006dfa  lea     r8, aCurrentV4AndV6_1; "Current V4 and V6 SSL binding does not "...
0x180006e01  mov     rax, cs:gSstpCfgTemplateFunc
0x180006e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e14  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180006e1b  cmp     [rbp+2Fh+var_9E], 0
0x180006e1f  jz      loc_180006F0C
0x180006e25  test    bl, bl
0x180006e27  jnz     loc_180006F10
0x180006e2d  cmp     rcx, rsi
0x180006e30  jz      short loc_180006E53
0x180006e32  test    byte ptr [rcx+1Ch], 40h
0x180006e36  jz      short loc_180006E53
0x180006e38  cmp     byte ptr [rcx+19h], 3
0x180006e3c  jb      short loc_180006E53
0x180006e3e  mov     rcx, [rcx+10h]
0x180006e42  mov     edx, 60h ; '`'
0x180006e47  call    WPP_SF_
0x180006e4c  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180006e53  test    rdx, rdx
0x180006e56  jz      short loc_180006E72
0x180006e58  mov     rcx, cs:gSstpCfgEtwContext
0x180006e5f  lea     r8, aCurrentV6SslBi; "Current V6 SSL binding does not matches"...
0x180006e66  mov     rax, cs:gSstpCfgTemplateFunc
0x180006e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e72  mov     r8d, [rbp+2Fh+arg_28]
0x180006e76  mov     rdx, r12
0x180006e79  xor     ecx, ecx
0x180006e7b  call    UnbindSslCertificate
0x180006e80  mov     ebx, eax
0x180006e82  test    eax, eax
0x180006e84  jnz     short loc_180006ECA
0x180006e86  movzx   ecx, [rbp+2Fh+var_A0]
0x180006e8a  mov     rdx, r13
0x180006e8d  call    SetSslCertificateToHttpV6
0x180006e92  mov     ebx, eax
0x180006e94  test    eax, eax
0x180006e96  jz      loc_180007060
0x180006e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ea3  cmp     rcx, rsi
0x180006ea6  jz      loc_180006D49
0x180006eac  test    byte ptr [rcx+1Ch], 40h
0x180006eb0  jz      loc_180006D49
0x180006eb6  cmp     byte ptr [rcx+19h], 1
0x180006eba  jb      loc_180006D49
0x180006ec0  mov     edx, 61h ; 'a'
0x180006ec5  jmp     loc_180006D40
0x180006eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ed1  cmp     rcx, rsi
0x180006ed4  jz      short loc_180006EF0
0x180006ed6  test    byte ptr [rcx+1Ch], 40h
0x180006eda  jz      short loc_180006EF0
0x180006edc  cmp     byte ptr [rcx+19h], 1
0x180006ee0  jb      short loc_180006EF0
0x180006ee2  mov     rcx, [rcx+10h]
0x180006ee6  mov     edx, 62h ; 'b'
0x180006eeb  call    WPP_SF_
0x180006ef0  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006ef7  test    rdx, rdx
0x180006efa  jz      loc_1800070C3
0x180006f00  lea     r8, aFailedToUnbind; "Failed to unbind V6 binding, bail out"
0x180006f07  jmp     loc_180006C9A
0x180006f0c  test    bl, bl
0x180006f0e  jnz     short loc_180006F88
0x180006f10  cmp     rcx, rsi
0x180006f13  jz      short loc_180006F2F
0x180006f15  test    byte ptr [rcx+1Ch], 40h
0x180006f19  jz      short loc_180006F2F
0x180006f1b  cmp     byte ptr [rcx+19h], 1
0x180006f1f  jb      short loc_180006F2F
0x180006f21  mov     rcx, [rcx+10h]
0x180006f25  mov     edx, 5Fh ; '_'
0x180006f2a  call    WPP_SF_
0x180006f2f  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006f36  test    rdx, rdx
0x180006f39  jz      short loc_180006F55
0x180006f3b  mov     rcx, cs:gSstpCfgEtwContext
0x180006f42  lea     r8, aCurrentV4AndV6_0; "Current V4 and V6 SSL binding does not "...
0x180006f49  mov     rax, cs:gSstpCfgTemplateFunc
0x180006f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f55  mov     rcx, cs:EventSource; hLogHandle
0x180006f5c  xor     r9d, r9d; dwSubStringCount
0x180006f5f  mov     [rsp+0E0h+dwErrorCode], 0; dwErrorCode
0x180006f67  mov     [rsp+0E0h+plpszSubStringArray], 0; plpszSubStringArray
0x180006f70  lea     edx, [r9+1]; dwEventType
0x180006f74  lea     r8d, [r9+18h]; dwMessageId
0x180006f78  call    cs:__imp_RouterLogEventW
0x180006f7e  mov     ebx, 0Dh
0x180006f83  jmp     loc_1800070C3
0x180006f88  cmp     rcx, rsi
0x180006f8b  jz      short loc_180006FAE
0x180006f8d  test    byte ptr [rcx+1Ch], 40h
0x180006f91  jz      short loc_180006FAE
0x180006f93  cmp     byte ptr [rcx+19h], 3
0x180006f97  jb      short loc_180006FAE
0x180006f99  mov     rcx, [rcx+10h]
0x180006f9d  mov     edx, 63h ; 'c'
0x180006fa2  call    WPP_SF_
0x180006fa7  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180006fae  test    rdx, rdx
0x180006fb1  jz      short loc_180006FCD
0x180006fb3  mov     rcx, cs:gSstpCfgEtwContext
0x180006fba  lea     r8, aCurrentV4SslBi_0; "Current V4 SSL binding does not matches"...
0x180006fc1  mov     rax, cs:gSstpCfgTemplateFunc
0x180006fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fcd  mov     r8d, [rbp+2Fh+var_88]
0x180006fd1  mov     cl, 1
0x180006fd3  mov     rdx, [rbp+2Fh+var_80]
0x180006fd7  call    UnbindSslCertificate
0x180006fdc  mov     ebx, eax
0x180006fde  test    eax, eax
0x180006fe0  jnz     short loc_180007022
0x180006fe2  movzx   ecx, [rbp+2Fh+var_A0]
0x180006fe6  mov     rdx, r14
0x180006fe9  call    SetSslCertificateToHttpV4
0x180006fee  mov     ebx, eax
0x180006ff0  test    eax, eax
0x180006ff2  jz      short loc_180007063
0x180006ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ffb  cmp     rcx, rsi
0x180006ffe  jz      loc_180006C83
0x180007004  test    byte ptr [rcx+1Ch], 40h
0x180007008  jz      loc_180006C83
0x18000700e  cmp     byte ptr [rcx+19h], 1
0x180007012  jb      loc_180006C83
0x180007018  mov     edx, 64h ; 'd'
0x18000701d  jmp     loc_180006C7A
0x180007022  mov     rcx, cs:WPP_GLOBAL_Control
0x180007029  cmp     rcx, rsi
0x18000702c  jz      short loc_180007048
0x18000702e  test    byte ptr [rcx+1Ch], 40h
0x180007032  jz      short loc_180007048
0x180007034  cmp     byte ptr [rcx+19h], 1
0x180007038  jb      short loc_180007048
0x18000703a  mov     rcx, [rcx+10h]
0x18000703e  mov     edx, 65h ; 'e'
0x180007043  call    WPP_SF_
0x180007048  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000704f  test    rdx, rdx
0x180007052  jz      short loc_1800070C3
0x180007054  lea     r8, aFailedToUnbind_0; "Failed to unbind V4 binding, bail out"
0x18000705b  jmp     loc_180006C9A
0x180007060  mov     r14, r13
0x180007063  lea     r9, [rbp+2Fh+var_60]
0x180007067  mov     dl, 3
0x180007069  lea     r8, [rbp+2Fh+var_78]
  ... truncated ...
```
