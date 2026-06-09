# handleV4V6RegCertMismatch

- ea: `0x18000a414`
- end: `0x18000ac73`
- name: `handleV4V6RegCertMismatch`
- size: `2143`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d10`
- `0x180007450`

## callees

- `0x18000a014`
- `0x18000a414`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000af10`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x18000a516`
- `CRYPT32!CertNameToStrW` at `0x18000a56a`
- `CRYPT32!CertNameToStrW` at `0x18000a5c2`
- `CRYPT32!CertNameToStrW` at `0x18000a516`
- `CRYPT32!CertNameToStrW` at `0x18000a56a`
- `CRYPT32!CertNameToStrW` at `0x18000a5c2`
- `CRYPT32!CertCompareCertificate` at `0x18000a529`
- `CRYPT32!CertCompareCertificate` at `0x18000a57d`
- `CRYPT32!CertCompareCertificate` at `0x18000a529`
- `CRYPT32!CertCompareCertificate` at `0x18000a57d`
- `rtutils!RouterLogEventW` at `0x18000a7eb`
- `rtutils!RouterLogEventW` at `0x18000a7eb`

## string_xrefs

- `0x18000a626`: `No SSL binding exist currently, plumb the SSTP configured certificate`
- `0x18000a6e6`: `No SSL binding exist currently for V4, plumb the SSTP configured cert which is same as current V6 binding`
- `0x18000a7aa`: `Current V6 SSL binding does not matches with the current SSTP configuration, bail out`
- `0x18000a749`: `Current V6 SSL binding does not matches with the current SSTP configuration, Trying to correct it`
- `0x18000abb5`: `Current V6 SSL binding does not matches with the current SSTP configuration, Trying to correct it`
- `0x18000a8a7`: `No SSL binding exist currently for V6, plumb the SSTP configured cert which is same as current V4 binding`
- `0x18000a95a`: `Current V4 SSL binding does not matches with the current SSTP configuration, bail out`
- `0x18000a903`: `Current V4 SSL binding does not matches with the current SSTP configuration, Trying to correct it`
- `0x18000ab10`: `Current V4 SSL binding does not matches with the current SSTP configuration, Trying to correct it`
- `0x18000aa60`: `Current V4 and V6 SSL binding does not matches with the current SSTP configuration, Trying to correct it`
- `0x18000aabd`: `Current V4 and/or V6 SSL binding does not matches with the current SSTP configuration, bail out`
- `0x18000ac34`: `Certificates currently Configured as same as the SSL certificates binding`

## pseudocode

```c
__int64 __fastcall handleV4V6RegCertMismatch(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6,
        _BYTE *a7,
        _BYTE *a8,
        _BYTE *a9)
{
  bool v13; // r12
  bool v14; // r14
  struct _CRYPTOAPI_BLOB *v15; // rdx
  unsigned int v16; // esi
  _BYTE *v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  WCHAR *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  const wchar_t *v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rax
  bool v28; // al
  LPWSTR plpszSubStringArray[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h]
  WCHAR psz[1024]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v34[1024]; // [rsp+880h] [rbp+780h] BYREF
  WCHAR v35[1024]; // [rsp+1080h] [rbp+F80h] BYREF

  v32 = 0;
  v13 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  memset_0(psz, 0, sizeof(psz));
  memset_0(v34, 0, sizeof(v34));
  memset_0(v35, 0, sizeof(v35));
  if ( a2 )
  {
    CertNameToStrW(0x10001u, (PCERT_NAME_BLOB)(*(_QWORD *)(a2 + 24) + 80LL), 3u, psz, 0x400u);
    v13 = CertCompareCertificate(0x10001u, *(PCERT_INFO *)(a2 + 24), *(PCERT_INFO *)(a1 + 24));
  }
  v14 = 0;
  if ( a4 )
  {
    v15 = (struct _CRYPTOAPI_BLOB *)(*(_QWORD *)(a4 + 24) + 80LL);
    v34[0] = 0;
    CertNameToStrW(0x10001u, v15, 3u, v34, 0x400u);
    v14 = CertCompareCertificate(0x10001u, *(PCERT_INFO *)(a4 + 24), *(PCERT_INFO *)(a1 + 24));
  }
  v16 = 0;
  v35[0] = 0;
  CertNameToStrW(0x10001u, (PCERT_NAME_BLOB)(*(_QWORD *)(a1 + 24) + 80LL), 3u, v35, 0x400u);
  v32 = 0;
  plpszSubStringArray[1] = v35;
  if ( !a2 )
  {
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73);
      }
      if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          *((_QWORD *)&xmmword_1800146E0 + 1),
          L"No SSL binding exist currently, plumb the SSTP configured certificate");
      v17 = a7;
LABEL_114:
      *v17 = 1;
      *a6 = 1;
      return v16;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74);
      v18 = WPP_GLOBAL_Control;
    }
    v19 = *((_QWORD *)&xmmword_1800146E0 + 1);
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        L"V6 SSL binding exist but No SSL binding exist for V4 currently");
      v18 = WPP_GLOBAL_Control;
      v19 = *((_QWORD *)&xmmword_1800146E0 + 1);
    }
    if ( v14 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
      {
        WPP_SF_(v18[2], 75);
        v19 = *((_QWORD *)&xmmword_1800146E0 + 1);
      }
      if ( v19 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          v19,
          L"No SSL binding exist currently for V4, plumb the SSTP configured cert which is same as current V6 binding");
LABEL_36:
      *a6 = 1;
      return v16;
    }
    if ( *(_QWORD *)(a5 + 24) == 0x458BCD49BA195980LL && *(_QWORD *)(a5 + 32) == 0x75CDADE04EC8239ELL )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
      {
        WPP_SF_(v18[2], 77);
        v19 = *((_QWORD *)&xmmword_1800146E0 + 1);
      }
      if ( v19 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          v19,
          L"Current V6 SSL binding does not matches with the current SSTP configuration, Trying to correct it");
      *a9 = 1;
      *a7 = 1;
      goto LABEL_36;
    }
    if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 0x40) == 0 || !*((_BYTE *)v18 + 25) )
      goto LABEL_42;
    v20 = 76;
    goto LABEL_41;
  }
  if ( !a4 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78);
      v18 = WPP_GLOBAL_Control;
    }
    v22 = *((_QWORD *)&xmmword_1800146E0 + 1);
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        L"V6 SSL binding exist but No SSL binding exist for V4 currently");
      v18 = WPP_GLOBAL_Control;
      v22 = *((_QWORD *)&xmmword_1800146E0 + 1);
    }
    if ( v13 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) )
        WPP_SF_(v18[2], 79);
      if ( (_QWORD)xmmword_1800146E0 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          xmmword_1800146E0,
          L"No SSL binding exist currently for V6, plumb the SSTP configured cert which is same as current V4 binding");
LABEL_69:
      *a7 = 1;
      return v16;
    }
    if ( *(_QWORD *)(a3 + 24) == 0x458BCD49BA195980LL && *(_QWORD *)(a3 + 32) == 0x75CDADE04EC8239ELL )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
      {
        WPP_SF_(v18[2], 81);
        v22 = *((_QWORD *)&xmmword_1800146E0 + 1);
      }
      if ( v22 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          v22,
          L"Current V4 SSL binding does not matches with the current SSTP configuration, Trying to correct it");
      *a8 = 1;
      *a6 = 1;
      goto LABEL_69;
    }
    if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 0x40) == 0 || !*((_BYTE *)v18 + 25) )
      goto LABEL_75;
    v23 = 80;
    goto LABEL_74;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82);
    v18 = WPP_GLOBAL_Control;
  }
  v26 = *((_QWORD *)&xmmword_1800146E0 + 1);
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      L"Both V4 and V6 SSL binding exist");
    v18 = WPP_GLOBAL_Control;
    v26 = *((_QWORD *)&xmmword_1800146E0 + 1);
  }
  if ( !v13 )
  {
    if ( v14 )
    {
      if ( *(_QWORD *)(a3 + 24) == 0x458BCD49BA195980LL && *(_QWORD *)(a3 + 32) == 0x75CDADE04EC8239ELL )
      {
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
        {
          WPP_SF_(v18[2], 85);
          v26 = *((_QWORD *)&xmmword_1800146E0 + 1);
        }
        if ( v26 )
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            v26,
            L"Current V4 SSL binding does not matches with the current SSTP configuration, Trying to correct it");
        v17 = a8;
        goto LABEL_114;
      }
      if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 0x40) == 0 || !*((_BYTE *)v18 + 25) )
        goto LABEL_75;
      v23 = 86;
LABEL_74:
      WPP_SF_(v18[2], v23);
LABEL_75:
      v24 = xmmword_1800146E0;
      if ( !(_QWORD)xmmword_1800146E0 )
      {
LABEL_78:
        v21 = psz;
LABEL_45:
        plpszSubStringArray[0] = v21;
        RouterLogEventW(EventSource, 1u, 0x20u, 2u, plpszSubStringArray, 0);
        return 13;
      }
      v25 = L"Current V4 SSL binding does not matches with the current SSTP configuration, bail out";
LABEL_77:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v24, v25);
      goto LABEL_78;
    }
    v27 = *(_QWORD *)(a5 + 24) - 0x458BCD49BA195980LL;
    if ( *(_QWORD *)(a5 + 24) == 0x458BCD49BA195980LL )
      v27 = *(_QWORD *)(a5 + 32) - 0x75CDADE04EC8239ELL;
    v28 = v27 == 0;
    if ( *(_QWORD *)(a3 + 24) != 0x458BCD49BA195980LL || *(_QWORD *)(a3 + 32) != 0x75CDADE04EC8239ELL || !v28 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) )
        WPP_SF_(v18[2], 84);
      v24 = xmmword_1800146E0;
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_78;
      v25 = L"Current V4 and/or V6 SSL binding does not matches with the current SSTP configuration, bail out";
      goto LABEL_77;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
    {
      WPP_SF_(v18[2], 83);
      v26 = *((_QWORD *)&xmmword_1800146E0 + 1);
    }
    if ( v26 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        v26,
        L"Current V4 and V6 SSL binding does not matches with the current SSTP configuration, Trying to correct it");
    *a8 = 1;
    *a9 = 1;
    *a6 = 1;
LABEL_129:
    *a7 = 1;
    return v16;
  }
  if ( !v14 )
  {
    if ( *(_QWORD *)(a5 + 24) != 0x458BCD49BA195980LL || *(_QWORD *)(a5 + 32) != 0x75CDADE04EC8239ELL )
    {
      if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 0x40) == 0 || !*((_BYTE *)v18 + 25) )
        goto LABEL_42;
      v20 = 88;
LABEL_41:
      WPP_SF_(v18[2], v20);
LABEL_42:
      if ( (_QWORD)xmmword_1800146E0 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
          gSstpCfgEtwContext,
          xmmword_1800146E0,
          L"Current V6 SSL binding does not matches with the current SSTP configuration, bail out");
      v21 = v34;
      goto LABEL_45;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
    {
      WPP_SF_(v18[2], 87);
      v26 = *((_QWORD *)&xmmword_1800146E0 + 1);
    }
    if ( v26 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        v26,
        L"Current V6 SSL binding does not matches with the current SSTP configuration, Trying to correct it");
    *a9 = 1;
    goto LABEL_129;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 3u )
  {
    WPP_SF_(v18[2], 89);
    v26 = *((_QWORD *)&xmmword_1800146E0 + 1);
  }
  if ( v26 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      v26,
      L"Certificates currently Configured as same as the SSL certificates binding");
  return v16;
}

```

## disassembly

```asm
0x18000a414  mov     [rsp-8+arg_10], rbx
0x18000a419  push    rbp
0x18000a41a  push    rsi
0x18000a41b  push    rdi
0x18000a41c  push    r12
0x18000a41e  push    r13
0x18000a420  push    r14
0x18000a422  push    r15
0x18000a424  lea     rbp, [rsp-1790h]
0x18000a42c  mov     eax, 1890h
0x18000a431  call    _alloca_probe
0x18000a436  sub     rsp, rax
0x18000a439  mov     rax, cs:__security_cookie
0x18000a440  xor     rax, rsp
0x18000a443  mov     [rbp+17C0h+var_40], rax
0x18000a44a  mov     rax, [rbp+17C0h+arg_30]
0x18000a451  mov     r15, r8
0x18000a454  mov     r13, [rbp+17C0h+arg_28]
0x18000a45b  mov     rdi, rdx
0x18000a45e  mov     [rsp+18C0h+var_1880], rax
0x18000a463  mov     rsi, rcx
0x18000a466  mov     rax, [rbp+17C0h+arg_38]
0x18000a46d  xorps   xmm0, xmm0
0x18000a470  mov     [rsp+18C0h+var_1878], rax
0x18000a475  mov     r14d, 800h
0x18000a47b  mov     rax, [rbp+17C0h+arg_40]
0x18000a482  mov     r8d, r14d; Size
0x18000a485  mov     [rsp+18C0h+var_1870], rax
0x18000a48a  xor     edx, edx; Val
0x18000a48c  xor     eax, eax
0x18000a48e  mov     [rsp+18C0h+var_1868], rcx
0x18000a493  lea     rcx, [rbp+17C0h+psz]; void *
0x18000a497  mov     [rsp+18C0h+var_1850], rax
0x18000a49c  mov     rbx, r9
0x18000a49f  mov     dword ptr [rsp+18C0h+var_1890], 0BA195980h
0x18000a4a7  xor     r12b, r12b
0x18000a4aa  mov     dword ptr [rsp+18C0h+var_1890+4], 458BCD49h
0x18000a4b2  mov     dword ptr [rsp+18C0h+var_1888], 4EC8239Eh
0x18000a4ba  mov     dword ptr [rsp+18C0h+var_1888+4], 75CDADE0h
0x18000a4c2  movups  xmmword ptr [rsp+18C0h+plpszSubStringArray], xmm0
0x18000a4c7  call    memset_0
0x18000a4cc  mov     r8d, r14d; Size
0x18000a4cf  lea     rcx, [rbp+17C0h+var_1040]; void *
0x18000a4d6  xor     edx, edx; Val
0x18000a4d8  call    memset_0
0x18000a4dd  mov     r8d, r14d; Size
0x18000a4e0  lea     rcx, [rbp+17C0h+var_840]; void *
0x18000a4e7  xor     edx, edx; Val
0x18000a4e9  call    memset_0
0x18000a4ee  mov     r14d, 1
0x18000a4f4  test    rdi, rdi
0x18000a4f7  jz      short loc_18000A539
0x18000a4f9  mov     rdx, [rdi+18h]
0x18000a4fd  lea     r9, [rbp+17C0h+psz]; psz
0x18000a501  add     rdx, 50h ; 'P'; pName
0x18000a505  mov     [rsp+18C0h+csz], 400h; csz
0x18000a50d  mov     ecx, 10001h; dwCertEncodingType
0x18000a512  lea     r8d, [r14+2]; dwStrType
0x18000a516  call    cs:__imp_CertNameToStrW
0x18000a51c  mov     r8, [rsi+18h]; pCertId2
0x18000a520  mov     ecx, 10001h; dwCertEncodingType
0x18000a525  mov     rdx, [rdi+18h]; pCertId1
0x18000a529  call    cs:__imp_CertCompareCertificate
0x18000a52f  test    eax, eax
0x18000a531  movzx   r12d, r12b
0x18000a535  cmovnz  r12d, r14d
0x18000a539  xor     r14b, r14b
0x18000a53c  test    rbx, rbx
0x18000a53f  jz      short loc_18000A592
0x18000a541  mov     rdx, [rbx+18h]
0x18000a545  lea     r9, [rbp+17C0h+var_1040]; psz
0x18000a54c  xor     eax, eax
0x18000a54e  mov     [rsp+18C0h+csz], 400h; csz
0x18000a556  add     rdx, 50h ; 'P'; pName
0x18000a55a  mov     [rbp+17C0h+var_1040], ax
0x18000a561  mov     ecx, 10001h; dwCertEncodingType
0x18000a566  lea     r8d, [rax+3]; dwStrType
0x18000a56a  call    cs:__imp_CertNameToStrW
0x18000a570  mov     r8, [rsi+18h]; pCertId2
0x18000a574  mov     ecx, 10001h; dwCertEncodingType
0x18000a579  mov     rdx, [rbx+18h]; pCertId1
0x18000a57d  call    cs:__imp_CertCompareCertificate
0x18000a583  test    eax, eax
0x18000a585  movzx   r14d, r14b
0x18000a589  mov     eax, 1
0x18000a58e  cmovnz  r14d, eax
0x18000a592  mov     rdx, [rsp+18C0h+var_1868]
0x18000a597  lea     r9, [rbp+17C0h+var_840]; psz
0x18000a59e  xor     eax, eax
0x18000a5a0  mov     [rsp+18C0h+csz], 400h; csz
0x18000a5a8  xor     esi, esi
0x18000a5aa  mov     [rbp+17C0h+var_840], ax
0x18000a5b1  mov     ecx, 10001h; dwCertEncodingType
0x18000a5b6  mov     rdx, [rdx+18h]
0x18000a5ba  add     rdx, 50h ; 'P'; pName
0x18000a5be  lea     r8d, [rsi+3]; dwStrType
0x18000a5c2  call    cs:__imp_CertNameToStrW
0x18000a5c8  mov     [rsp+18C0h+var_1850], rsi
0x18000a5cd  lea     rax, [rbp+17C0h+var_840]
0x18000a5d4  mov     [rsp+18C0h+plpszSubStringArray+8], rax
0x18000a5d9  test    rdi, rdi
0x18000a5dc  jnz     loc_18000A7FB
0x18000a5e2  test    rbx, rbx
0x18000a5e5  jnz     short loc_18000A643
0x18000a5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5ee  lea     rdi, WPP_GLOBAL_Control
0x18000a5f5  cmp     rcx, rdi
0x18000a5f8  jz      short loc_18000A613
0x18000a5fa  mov     bl, 40h ; '@'
0x18000a5fc  test    [rcx+1Ch], bl
0x18000a5ff  jz      short loc_18000A613
0x18000a601  cmp     byte ptr [rcx+19h], 3
0x18000a605  jb      short loc_18000A613
0x18000a607  mov     rcx, [rcx+10h]
0x18000a60b  lea     edx, [rsi+49h]
0x18000a60e  call    WPP_SF_
0x18000a613  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a61a  test    rdx, rdx
0x18000a61d  jz      short loc_18000A639
0x18000a61f  mov     rcx, cs:gSstpCfgEtwContext
0x18000a626  lea     r8, aNoSslBindingEx; "No SSL binding exist currently, plumb t"...
0x18000a62d  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a639  mov     rax, [rsp+18C0h+var_1880]
0x18000a63e  jmp     loc_18000AB28
0x18000a643  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a64a  lea     rdi, WPP_GLOBAL_Control
0x18000a651  mov     bl, 40h ; '@'
0x18000a653  cmp     rcx, rdi
0x18000a656  jz      short loc_18000A678
0x18000a658  test    [rcx+1Ch], bl
0x18000a65b  jz      short loc_18000A678
0x18000a65d  cmp     byte ptr [rcx+19h], 3
0x18000a661  jb      short loc_18000A678
0x18000a663  mov     rcx, [rcx+10h]
0x18000a667  mov     edx, 4Ah ; 'J'
0x18000a66c  call    WPP_SF_
0x18000a671  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a678  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a67f  test    rdx, rdx
0x18000a682  jz      short loc_18000A6AC
0x18000a684  mov     rcx, cs:gSstpCfgEtwContext
0x18000a68b  lea     r8, aV6SslBindingEx; "V6 SSL binding exist but No SSL binding"...
0x18000a692  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a69e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6a5  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a6ac  test    r14b, r14b
0x18000a6af  jz      short loc_18000A6FB
0x18000a6b1  cmp     rcx, rdi
0x18000a6b4  jz      short loc_18000A6D6
0x18000a6b6  test    [rcx+1Ch], bl
0x18000a6b9  jz      short loc_18000A6D6
0x18000a6bb  cmp     byte ptr [rcx+19h], 3
0x18000a6bf  jb      short loc_18000A6D6
0x18000a6c1  mov     rcx, [rcx+10h]
0x18000a6c5  mov     edx, 4Bh ; 'K'
0x18000a6ca  call    WPP_SF_
0x18000a6cf  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a6d6  test    rdx, rdx
0x18000a6d9  jz      loc_18000A76F
0x18000a6df  mov     rcx, cs:gSstpCfgEtwContext
0x18000a6e6  lea     r8, aNoSslBindingEx_1; "No SSL binding exist currently for V4, "...
0x18000a6ed  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f9  jmp     short loc_18000A76F
0x18000a6fb  mov     r8, [rbp+17C0h+arg_20]
0x18000a702  mov     rax, [r8+18h]
0x18000a706  cmp     rax, [rsp+18C0h+var_1890]
0x18000a70b  jnz     short loc_18000A779
0x18000a70d  mov     rax, [r8+20h]
0x18000a711  cmp     rax, [rsp+18C0h+var_1888]
0x18000a716  jnz     short loc_18000A779
0x18000a718  cmp     rcx, rdi
0x18000a71b  jz      short loc_18000A73D
0x18000a71d  test    [rcx+1Ch], bl
0x18000a720  jz      short loc_18000A73D
0x18000a722  cmp     byte ptr [rcx+19h], 3
0x18000a726  jb      short loc_18000A73D
0x18000a728  mov     rcx, [rcx+10h]
0x18000a72c  mov     edx, 4Dh ; 'M'
0x18000a731  call    WPP_SF_
0x18000a736  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a73d  test    rdx, rdx
0x18000a740  jz      short loc_18000A75C
0x18000a742  mov     rcx, cs:gSstpCfgEtwContext
0x18000a749  lea     r8, aCurrentV6SslBi_0; "Current V6 SSL binding does not matches"...
0x18000a750  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75c  mov     rax, [rsp+18C0h+var_1870]
0x18000a761  mov     ecx, 1
0x18000a766  mov     [rax], cl
0x18000a768  mov     rax, [rsp+18C0h+var_1880]
0x18000a76d  mov     [rax], cl
0x18000a76f  mov     byte ptr [r13+0], 1
0x18000a774  jmp     loc_18000AC47
0x18000a779  cmp     rcx, rdi
0x18000a77c  jz      short loc_18000A797
0x18000a77e  test    [rcx+1Ch], bl
0x18000a781  jz      short loc_18000A797
0x18000a783  cmp     byte ptr [rcx+19h], 1
0x18000a787  jb      short loc_18000A797
0x18000a789  mov     edx, 4Ch ; 'L'
0x18000a78e  mov     rcx, [rcx+10h]
0x18000a792  call    WPP_SF_
0x18000a797  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000a79e  test    rdx, rdx
0x18000a7a1  jz      short loc_18000A7BD
0x18000a7a3  mov     rcx, cs:gSstpCfgEtwContext
0x18000a7aa  lea     r8, aCurrentV6SslBi_1; "Current V6 SSL binding does not matches"...
0x18000a7b1  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7bd  lea     rax, [rbp+17C0h+var_1040]
0x18000a7c4  mov     rcx, cs:EventSource; hLogHandle
0x18000a7cb  mov     edx, 1; dwEventType
0x18000a7d0  mov     [rsp+18C0h+plpszSubStringArray], rax
0x18000a7d5  lea     rax, [rsp+18C0h+plpszSubStringArray]
0x18000a7da  mov     [rsp+18C0h+dwErrorCode], esi; dwErrorCode
0x18000a7de  mov     qword ptr [rsp+18C0h+csz], rax; plpszSubStringArray
0x18000a7e3  lea     r9d, [rdx+1]; dwSubStringCount
0x18000a7e7  lea     r8d, [rdx+1Fh]; dwMessageId
0x18000a7eb  call    cs:__imp_RouterLogEventW
0x18000a7f1  mov     esi, 0Dh
0x18000a7f6  jmp     loc_18000AC47
0x18000a7fb  test    rbx, rbx
0x18000a7fe  jnz     loc_18000A97D
0x18000a804  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a80b  lea     rdi, WPP_GLOBAL_Control
0x18000a812  mov     bl, 40h ; '@'
0x18000a814  cmp     rcx, rdi
0x18000a817  jz      short loc_18000A839
0x18000a819  test    [rcx+1Ch], bl
0x18000a81c  jz      short loc_18000A839
0x18000a81e  cmp     byte ptr [rcx+19h], 3
0x18000a822  jb      short loc_18000A839
0x18000a824  mov     rcx, [rcx+10h]
0x18000a828  mov     edx, 4Eh ; 'N'
0x18000a82d  call    WPP_SF_
0x18000a832  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a839  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a840  test    rdx, rdx
0x18000a843  jz      short loc_18000A86D
0x18000a845  mov     rcx, cs:gSstpCfgEtwContext
0x18000a84c  lea     r8, aV6SslBindingEx; "V6 SSL binding exist but No SSL binding"...
0x18000a853  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a866  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a86d  test    r12b, r12b
0x18000a870  jz      short loc_18000A8BC
0x18000a872  cmp     rcx, rdi
0x18000a875  jz      short loc_18000A890
0x18000a877  test    [rcx+1Ch], bl
0x18000a87a  jz      short loc_18000A890
0x18000a87c  cmp     byte ptr [rcx+19h], 1
0x18000a880  jb      short loc_18000A890
0x18000a882  mov     rcx, [rcx+10h]
0x18000a886  mov     edx, 4Fh ; 'O'
0x18000a88b  call    WPP_SF_
0x18000a890  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000a897  test    rdx, rdx
0x18000a89a  jz      loc_18000A923
0x18000a8a0  mov     rcx, cs:gSstpCfgEtwContext
0x18000a8a7  lea     r8, aNoSslBindingEx_0; "No SSL binding exist currently for V6, "...
0x18000a8ae  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ba  jmp     short loc_18000A923
0x18000a8bc  mov     rax, [r15+18h]
0x18000a8c0  cmp     rax, [rsp+18C0h+var_1890]
0x18000a8c5  jnz     short loc_18000A930
0x18000a8c7  mov     rax, [r15+20h]
0x18000a8cb  cmp     rax, [rsp+18C0h+var_1888]
0x18000a8d0  jnz     short loc_18000A930
0x18000a8d2  cmp     rcx, rdi
0x18000a8d5  jz      short loc_18000A8F7
0x18000a8d7  test    [rcx+1Ch], bl
0x18000a8da  jz      short loc_18000A8F7
0x18000a8dc  cmp     byte ptr [rcx+19h], 3
0x18000a8e0  jb      short loc_18000A8F7
0x18000a8e2  mov     rcx, [rcx+10h]
0x18000a8e6  mov     edx, 51h ; 'Q'
0x18000a8eb  call    WPP_SF_
0x18000a8f0  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x18000a8f7  test    rdx, rdx
0x18000a8fa  jz      short loc_18000A916
0x18000a8fc  mov     rcx, cs:gSstpCfgEtwContext
0x18000a903  lea     r8, aCurrentV4SslBi_1; "Current V4 SSL binding does not matches"...
0x18000a90a  mov     rax, cs:gSstpCfgTemplateFunc
0x18000a911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a916  mov     rax, [rsp+18C0h+var_1878]
0x18000a91b  mov     byte ptr [rax], 1
0x18000a91e  mov     byte ptr [r13+0], 1
0x18000a923  mov     rax, [rsp+18C0h+var_1880]
0x18000a928  mov     byte ptr [rax], 1
0x18000a92b  jmp     loc_18000AC47
0x18000a930  cmp     rcx, rdi
0x18000a933  jz      short loc_18000A94E
0x18000a935  test    [rcx+1Ch], bl
0x18000a938  jz      short loc_18000A94E
0x18000a93a  cmp     byte ptr [rcx+19h], 1
  ... truncated ...
```
