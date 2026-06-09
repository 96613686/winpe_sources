# HrValidateAllowedValueRange(IXMLDOMNode *,ushort * *)

- ea: `0x1800289ac`
- end: `0x1800292ca`
- name: `?HrValidateAllowedValueRange@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `2334`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800020f0`

## callees

- `0x1800200f4`
- `0x1800289ac`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180028f85`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180029018`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x1800290ab`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180028f85`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180029018`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x1800290ab`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180028fa2`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180029035`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x1800290c8`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180028fa2`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180029035`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x1800290c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028f3e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028f5a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028fd1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028fed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180029064`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180029080`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028f3e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028f5a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028fd1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028fed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180029064`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180029080`
- `OLEAUT32!__imp_SysFreeString` at `0x180028b8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180028b9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180028d25`
- `OLEAUT32!__imp_SysFreeString` at `0x180028d36`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ed0`
- `OLEAUT32!__imp_SysFreeString` at `0x180028b8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180028b9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180028d25`
- `OLEAUT32!__imp_SysFreeString` at `0x180028d36`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ed0`

## string_xrefs

- `0x180028ad7`: `urn:schemas-upnp-org:service-1-`
- `0x180028c71`: `urn:schemas-upnp-org:service-1-`
- `0x180028e0b`: `urn:schemas-upnp-org:service-1-`

## pseudocode

```c
__int64 __fastcall HrValidateAllowedValueRange(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v3; // r13d
  int v4; // r12d
  int v5; // r15d
  int v6; // eax
  int v7; // ecx
  __int64 *v8; // rdi
  int v9; // ebx
  bool v10; // zf
  __int64 v11; // rax
  int v12; // r14d
  signed int v13; // ebx
  OLECHAR *v14; // r8
  BSTR v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rdx
  const wchar_t *v20; // rcx
  WCHAR *v21; // r9
  WCHAR *v22; // rcx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  OLECHAR *v25; // r9
  __int64 v26; // rdx
  WCHAR *v27; // rcx
  __int64 *v28; // rdi
  int v29; // r14d
  signed int v30; // ebx
  OLECHAR *v31; // r8
  BSTR v32; // rax
  __int64 v33; // rdx
  unsigned __int64 v34; // rsi
  __int64 v35; // rax
  __int64 v36; // rdx
  const wchar_t *v37; // rcx
  WCHAR *v38; // r9
  WCHAR *v39; // rcx
  __int64 v40; // rcx
  WCHAR *v41; // rax
  OLECHAR *v42; // r9
  __int64 v43; // rdx
  WCHAR *v44; // rcx
  __int64 *v45; // rdi
  int v46; // r14d
  signed int v47; // ebx
  OLECHAR *v48; // r8
  BSTR v49; // rax
  __int64 v50; // rdx
  unsigned __int64 v51; // rsi
  __int64 v52; // rax
  __int64 v53; // rdx
  const wchar_t *v54; // rcx
  WCHAR *v55; // r9
  WCHAR *v56; // rcx
  __int64 v57; // rcx
  WCHAR *v58; // rax
  OLECHAR *v59; // r9
  __int64 v60; // rdx
  WCHAR *v61; // rcx
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rdi
  unsigned __int64 k; // rdi
  const unsigned __int16 *v66; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v68; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v69; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v70; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v71; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v72; // [rsp+58h] [rbp-A8h]
  WCHAR String2[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String1[256]; // [rsp+260h] [rbp+160h] BYREF

  lpVtbl = a1->lpVtbl;
  v72 = a2;
  v3 = 0;
  v70 = 0;
  v69 = 0;
  v4 = 0;
  v5 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 **))lpVtbl->get_firstChild)(a1, &v69);
  v8 = v69;
  v9 = v6;
  while ( 1 )
  {
    v10 = v9 == 0;
    if ( v9 < 0 )
      break;
    if ( !v8 )
    {
      if ( v3 != 1 )
      {
        v66 = L"<allowedValueRange> did not contain exactly one <minimum> element";
        goto LABEL_136;
      }
      if ( v4 != 1 )
      {
        v66 = L"<allowedValueRange> did not contain exactly one <maximum> element";
        goto LABEL_136;
      }
      if ( v5 <= 1 )
      {
        v9 = 0;
      }
      else
      {
        v66 = L"<allowedValueRange> contained multiple <step> elements";
LABEL_136:
        v9 = HrAllocErrorStringAndReturnHr(v7, v66, 0, &v70);
      }
      if ( v70 )
        *v72 = v70;
      v10 = v9 == 0;
      break;
    }
    v71 = 0;
    v11 = *v8;
    v68 = 0;
    v12 = 0;
    bstrString = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v11 + 328))(v8, &v68);
    if ( v13 >= 0 && v68 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v8 + 312))(v8, &bstrString);
      if ( v13 >= 0 )
      {
        v14 = bstrString;
        if ( bstrString )
        {
          v15 = bstrString;
          v16 = 0x7FFFFFFF;
          do
          {
            if ( !*v15 )
              break;
            ++v15;
            --v16;
          }
          while ( v16 );
          v13 = v16 == 0 ? 0x80070057 : 0;
          v17 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
          if ( v16 )
          {
            v18 = 31;
            v19 = 256;
            v20 = L"urn:schemas-upnp-org:service-1-";
            v21 = String1;
            do
            {
              if ( !v18 )
                break;
              if ( !*v20 )
                break;
              *v21++ = *v20++;
              --v18;
              --v19;
            }
            while ( v19 );
            v22 = v21 - 1;
            v13 = v19 == 0 ? 0x8007007A : 0;
            if ( v19 )
              v22 = v21;
            *v22 = 0;
            if ( v19 )
            {
              v23 = 31;
              v24 = String2;
              v25 = v14;
              v26 = 256;
              do
              {
                if ( !v23 )
                  break;
                if ( !*v25 )
                  break;
                *v24++ = *v25++;
                --v23;
                --v26;
              }
              while ( v26 );
              v27 = v24 - 1;
              if ( v26 )
                v27 = v24;
              *v27 = 0;
              v13 = v26 == 0 ? 0x8007007A : 0;
              if ( v26 )
              {
                if ( !lstrcmpW(v68, L"minimum") && !lstrcmpW(String1, String2) )
                {
                  v12 = 1;
                  if ( v17 > 0x1F )
                  {
                    for ( i = 31; i < v17; ++i )
                    {
                      if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                      {
                        v14 = bstrString;
                        v12 = 0;
                        goto LABEL_26;
                      }
                    }
                  }
                }
                v14 = bstrString;
              }
            }
          }
LABEL_26:
          SysFreeString(v14);
        }
      }
      SysFreeString(v68);
    }
    if ( v13 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
        v13);
    if ( v12 )
    {
      ++v3;
    }
    else
    {
      v28 = v69;
      v68 = 0;
      bstrString = 0;
      v29 = 0;
      v30 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v69 + 328))(v69, &v68);
      if ( v30 >= 0 && v68 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v28 + 312))(v28, &bstrString);
        if ( v30 >= 0 )
        {
          v31 = bstrString;
          if ( bstrString )
          {
            v32 = bstrString;
            v33 = 0x7FFFFFFF;
            do
            {
              if ( !*v32 )
                break;
              ++v32;
              --v33;
            }
            while ( v33 );
            v30 = v33 == 0 ? 0x80070057 : 0;
            v34 = (0x7FFFFFFF - v33) & -(__int64)(v33 != 0);
            if ( v33 )
            {
              v35 = 31;
              v36 = 256;
              v37 = L"urn:schemas-upnp-org:service-1-";
              v38 = String2;
              do
              {
                if ( !v35 )
                  break;
                if ( !*v37 )
                  break;
                *v38++ = *v37++;
                --v35;
                --v36;
              }
              while ( v36 );
              v39 = v38 - 1;
              v30 = v36 == 0 ? 0x8007007A : 0;
              if ( v36 )
                v39 = v38;
              *v39 = 0;
              if ( v36 )
              {
                v40 = 31;
                v41 = String1;
                v42 = v31;
                v43 = 256;
                do
                {
                  if ( !v40 )
                    break;
                  if ( !*v42 )
                    break;
                  *v41++ = *v42++;
                  --v40;
                  --v43;
                }
                while ( v43 );
                v44 = v41 - 1;
                if ( v43 )
                  v44 = v41;
                *v44 = 0;
                v30 = v43 == 0 ? 0x8007007A : 0;
                if ( v43 )
                {
                  if ( !lstrcmpW(v68, L"maximum") && !lstrcmpW(String2, String1) )
                  {
                    v29 = 1;
                    if ( v34 > 0x1F )
                    {
                      for ( j = 31; j < v34; ++j )
                      {
                        if ( !IsCharAlphaNumericW(bstrString[j]) || IsCharAlphaW(bstrString[j]) )
                        {
                          v31 = bstrString;
                          v29 = 0;
                          goto LABEL_52;
                        }
                      }
                    }
                  }
                  v31 = bstrString;
                }
              }
            }
LABEL_52:
            SysFreeString(v31);
          }
        }
        SysFreeString(v68);
      }
      if ( v30 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
          v30);
      if ( v29 )
      {
        ++v4;
      }
      else
      {
        v45 = v69;
        v68 = 0;
        bstrString = 0;
        v46 = 0;
        v47 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v69 + 328))(v69, &v68);
        if ( v47 >= 0 && v68 )
        {
          v47 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v45 + 312))(v45, &bstrString);
          if ( v47 >= 0 )
          {
            v48 = bstrString;
            if ( bstrString )
            {
              v49 = bstrString;
              v50 = 0x7FFFFFFF;
              do
              {
                if ( !*v49 )
                  break;
                ++v49;
                --v50;
              }
              while ( v50 );
              v47 = v50 == 0 ? 0x80070057 : 0;
              v51 = (0x7FFFFFFF - v50) & -(__int64)(v50 != 0);
              if ( v50 )
              {
                v52 = 31;
                v53 = 256;
                v54 = L"urn:schemas-upnp-org:service-1-";
                v55 = String2;
                do
                {
                  if ( !v52 )
                    break;
                  if ( !*v54 )
                    break;
                  *v55++ = *v54++;
                  --v52;
                  --v53;
                }
                while ( v53 );
                v56 = v55 - 1;
                v47 = v53 == 0 ? 0x8007007A : 0;
                if ( v53 )
                  v56 = v55;
                *v56 = 0;
                if ( v53 )
                {
                  v57 = 31;
                  v58 = String1;
                  v59 = v48;
                  v60 = 256;
                  do
                  {
                    if ( !v57 )
                      break;
                    if ( !*v59 )
                      break;
                    *v58++ = *v59++;
                    --v57;
                    --v60;
                  }
                  while ( v60 );
                  v61 = v58 - 1;
                  if ( v60 )
                    v61 = v58;
                  *v61 = 0;
                  v47 = v60 == 0 ? 0x8007007A : 0;
                  if ( v60 )
                  {
                    if ( !lstrcmpW(v68, L"step") && !lstrcmpW(String2, String1) )
                    {
                      v46 = 1;
                      if ( v51 > 0x1F )
                      {
                        for ( k = 31; k < v51; ++k )
                        {
                          if ( !IsCharAlphaNumericW(bstrString[k]) || IsCharAlphaW(bstrString[k]) )
                          {
                            v48 = bstrString;
                            v46 = 0;
                            goto LABEL_78;
                          }
                        }
                      }
                    }
                    v48 = bstrString;
                  }
                }
              }
LABEL_78:
              SysFreeString(v48);
            }
          }
          SysFreeString(v68);
        }
        if ( v47 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
            (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
            v47);
        if ( v46 )
          ++v5;
      }
    }
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v69 + 128))(v69, &v71);
    (*(void (__fastcall **)(__int64 *))(*v69 + 16))(v69);
    v8 = v71;
    v69 = v71;
  }
  if ( !v10 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateAllowedValueRange(): Exiting",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800289ac  mov     [rsp-8+arg_10], rbx
0x1800289b1  push    rbp
0x1800289b2  push    rsi
0x1800289b3  push    rdi
0x1800289b4  push    r12
0x1800289b6  push    r13
0x1800289b8  push    r14
0x1800289ba  push    r15
0x1800289bc  lea     rbp, [rsp-370h]
0x1800289c4  sub     rsp, 470h
0x1800289cb  mov     rax, cs:__security_cookie
0x1800289d2  xor     rax, rsp
0x1800289d5  mov     [rbp+3A0h+var_40], rax
0x1800289dc  mov     rax, [rcx]
0x1800289df  xor     esi, esi
0x1800289e1  mov     [rsp+4A0h+var_448], rdx
0x1800289e6  mov     r13d, esi
0x1800289e9  lea     rdx, [rsp+4A0h+var_460]
0x1800289ee  mov     [rsp+4A0h+var_458], rsi
0x1800289f3  mov     [rsp+4A0h+var_460], rsi
0x1800289f8  mov     r12d, esi
0x1800289fb  mov     rax, [rax+68h]
0x1800289ff  mov     r15d, esi
0x180028a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a07  mov     rdi, [rsp+4A0h+var_460]
0x180028a0c  mov     ebx, eax
0x180028a0e  test    ebx, ebx
0x180028a10  js      loc_1800290F7
0x180028a16  test    rdi, rdi
0x180028a19  jz      loc_180029231
0x180028a1f  mov     [rsp+4A0h+var_450], rsi
0x180028a24  lea     rdx, [rsp+4A0h+var_468]
0x180028a29  mov     rax, [rdi]
0x180028a2c  mov     rcx, rdi
0x180028a2f  mov     [rsp+4A0h+var_468], rsi
0x180028a34  mov     r14d, esi
0x180028a37  mov     [rsp+4A0h+bstrString], rsi
0x180028a3c  mov     rax, [rax+148h]
0x180028a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a48  mov     ebx, eax
0x180028a4a  test    eax, eax
0x180028a4c  js      loc_180028BA8
0x180028a52  cmp     [rsp+4A0h+var_468], rsi
0x180028a57  jz      loc_180028BA8
0x180028a5d  mov     rax, [rdi]
0x180028a60  lea     rdx, [rsp+4A0h+bstrString]
0x180028a65  mov     rcx, rdi
0x180028a68  mov     rax, [rax+138h]
0x180028a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a74  mov     ebx, eax
0x180028a76  test    eax, eax
0x180028a78  js      loc_180028B97
0x180028a7e  mov     r8, [rsp+4A0h+bstrString]
0x180028a83  test    r8, r8
0x180028a86  jz      loc_180028B97
0x180028a8c  mov     ecx, 7FFFFFFFh
0x180028a91  mov     rax, r8
0x180028a94  mov     edx, ecx
0x180028a96  cmp     [rax], si
0x180028a99  jz      short loc_180028AA5
0x180028a9b  add     rax, 2
0x180028a9f  sub     rdx, 1
0x180028aa3  jnz     short loc_180028A96
0x180028aa5  mov     rax, rdx
0x180028aa8  neg     rax
0x180028aab  mov     rax, rdx
0x180028aae  sbb     ebx, ebx
0x180028ab0  sub     rcx, rdx
0x180028ab3  not     ebx
0x180028ab5  and     ebx, 80070057h
0x180028abb  neg     rax
0x180028abe  sbb     rsi, rsi
0x180028ac1  xor     edi, edi
0x180028ac3  and     rsi, rcx
0x180028ac6  test    rdx, rdx
0x180028ac9  jz      loc_180028B86
0x180028acf  lea     eax, [rdi+1Fh]
0x180028ad2  mov     edx, 100h
0x180028ad7  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180028ade  lea     r9, [rbp+3A0h+String1]
0x180028ae5  test    rax, rax
0x180028ae8  jz      short loc_180028B09
0x180028aea  movzx   r10d, word ptr [rcx]
0x180028aee  test    r10w, r10w
0x180028af2  jz      short loc_180028B09
0x180028af4  mov     [r9], r10w
0x180028af8  add     rcx, 2
0x180028afc  add     r9, 2
0x180028b00  dec     rax
0x180028b03  sub     rdx, 1
0x180028b07  jnz     short loc_180028AE5
0x180028b09  mov     rax, rdx
0x180028b0c  lea     rcx, [r9-2]
0x180028b10  neg     rax
0x180028b13  mov     r11d, 8007007Ah
0x180028b19  sbb     ebx, ebx
0x180028b1b  not     ebx
0x180028b1d  and     ebx, r11d
0x180028b20  test    rdx, rdx
0x180028b23  cmovnz  rcx, r9
0x180028b27  mov     [rcx], di
0x180028b2a  jz      short loc_180028B86
0x180028b2c  mov     ecx, 1Fh
0x180028b31  lea     rax, [rsp+4A0h+String2]
0x180028b36  mov     r9, r8
0x180028b39  mov     edx, 100h
0x180028b3e  test    rcx, rcx
0x180028b41  jz      short loc_180028B62
0x180028b43  movzx   r10d, word ptr [r9]
0x180028b47  test    r10w, r10w
0x180028b4b  jz      short loc_180028B62
0x180028b4d  mov     [rax], r10w
0x180028b51  add     r9, 2
0x180028b55  add     rax, 2
0x180028b59  dec     rcx
0x180028b5c  sub     rdx, 1
0x180028b60  jnz     short loc_180028B3E
0x180028b62  test    rdx, rdx
0x180028b65  lea     rcx, [rax-2]
0x180028b69  cmovnz  rcx, rax
0x180028b6d  mov     rax, rdx
0x180028b70  neg     rax
0x180028b73  sbb     ebx, ebx
0x180028b75  not     ebx
0x180028b77  mov     [rcx], di
0x180028b7a  and     ebx, r11d
0x180028b7d  test    rdx, rdx
0x180028b80  jnz     loc_180028F32
0x180028b86  xor     esi, esi
0x180028b88  mov     rcx, r8; bstrString
0x180028b8b  call    cs:__imp_SysFreeString
0x180028b92  nop     dword ptr [rax+rax+00h]
0x180028b97  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x180028b9c  call    cs:__imp_SysFreeString
0x180028ba3  nop     dword ptr [rax+rax+00h]
0x180028ba8  test    ebx, ebx
0x180028baa  jnz     loc_180029157
0x180028bb0  test    r14d, r14d
0x180028bb3  jnz     loc_180028F28
0x180028bb9  mov     rdi, [rsp+4A0h+var_460]
0x180028bbe  lea     rdx, [rsp+4A0h+var_468]
0x180028bc3  mov     rcx, rdi
0x180028bc6  mov     [rsp+4A0h+var_468], rsi
0x180028bcb  mov     [rsp+4A0h+bstrString], rsi
0x180028bd0  mov     r14d, esi
0x180028bd3  mov     rax, [rdi]
0x180028bd6  mov     rax, [rax+148h]
0x180028bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028be2  mov     ebx, eax
0x180028be4  test    eax, eax
0x180028be6  js      loc_180028D42
0x180028bec  cmp     [rsp+4A0h+var_468], rsi
0x180028bf1  jz      loc_180028D42
0x180028bf7  mov     rax, [rdi]
0x180028bfa  lea     rdx, [rsp+4A0h+bstrString]
0x180028bff  mov     rcx, rdi
0x180028c02  mov     rax, [rax+138h]
0x180028c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c0e  mov     ebx, eax
0x180028c10  test    eax, eax
0x180028c12  js      loc_180028D31
0x180028c18  mov     r8, [rsp+4A0h+bstrString]
0x180028c1d  test    r8, r8
0x180028c20  jz      loc_180028D31
0x180028c26  mov     ecx, 7FFFFFFFh
0x180028c2b  mov     rax, r8
0x180028c2e  mov     edx, ecx
0x180028c30  cmp     [rax], si
0x180028c33  jz      short loc_180028C3F
0x180028c35  add     rax, 2
0x180028c39  sub     rdx, 1
0x180028c3d  jnz     short loc_180028C30
0x180028c3f  mov     rax, rdx
0x180028c42  neg     rax
0x180028c45  mov     rax, rdx
0x180028c48  sbb     ebx, ebx
0x180028c4a  sub     rcx, rdx
0x180028c4d  not     ebx
0x180028c4f  and     ebx, 80070057h
0x180028c55  neg     rax
0x180028c58  sbb     rsi, rsi
0x180028c5b  xor     edi, edi
0x180028c5d  and     rsi, rcx
0x180028c60  test    rdx, rdx
0x180028c63  jz      loc_180028D20
0x180028c69  lea     eax, [rdi+1Fh]
0x180028c6c  mov     edx, 100h
0x180028c71  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180028c78  lea     r9, [rsp+4A0h+String2]
0x180028c7d  test    rax, rax
0x180028c80  jz      short loc_180028CA1
0x180028c82  movzx   r10d, word ptr [rcx]
0x180028c86  test    r10w, r10w
0x180028c8a  jz      short loc_180028CA1
0x180028c8c  mov     [r9], r10w
0x180028c90  add     rcx, 2
0x180028c94  add     r9, 2
0x180028c98  dec     rax
0x180028c9b  sub     rdx, 1
0x180028c9f  jnz     short loc_180028C7D
0x180028ca1  mov     rax, rdx
0x180028ca4  lea     rcx, [r9-2]
0x180028ca8  neg     rax
0x180028cab  mov     r11d, 8007007Ah
0x180028cb1  sbb     ebx, ebx
0x180028cb3  not     ebx
0x180028cb5  and     ebx, r11d
0x180028cb8  test    rdx, rdx
0x180028cbb  cmovnz  rcx, r9
0x180028cbf  mov     [rcx], di
0x180028cc2  jz      short loc_180028D20
0x180028cc4  mov     ecx, 1Fh
0x180028cc9  lea     rax, [rbp+3A0h+String1]
0x180028cd0  mov     r9, r8
0x180028cd3  mov     edx, 100h
0x180028cd8  test    rcx, rcx
0x180028cdb  jz      short loc_180028CFC
0x180028cdd  movzx   r10d, word ptr [r9]
0x180028ce1  test    r10w, r10w
0x180028ce5  jz      short loc_180028CFC
0x180028ce7  mov     [rax], r10w
0x180028ceb  add     r9, 2
0x180028cef  add     rax, 2
0x180028cf3  dec     rcx
0x180028cf6  sub     rdx, 1
0x180028cfa  jnz     short loc_180028CD8
0x180028cfc  test    rdx, rdx
0x180028cff  lea     rcx, [rax-2]
0x180028d03  cmovnz  rcx, rax
0x180028d07  mov     rax, rdx
0x180028d0a  neg     rax
0x180028d0d  sbb     ebx, ebx
0x180028d0f  not     ebx
0x180028d11  mov     [rcx], di
0x180028d14  and     ebx, r11d
0x180028d17  test    rdx, rdx
0x180028d1a  jnz     loc_180028FC5
0x180028d20  xor     esi, esi
0x180028d22  mov     rcx, r8; bstrString
0x180028d25  call    cs:__imp_SysFreeString
0x180028d2c  nop     dword ptr [rax+rax+00h]
0x180028d31  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x180028d36  call    cs:__imp_SysFreeString
0x180028d3d  nop     dword ptr [rax+rax+00h]
0x180028d42  test    ebx, ebx
0x180028d44  jnz     loc_18002919D
0x180028d4a  test    r14d, r14d
0x180028d4d  jnz     loc_180028F2D
0x180028d53  mov     rdi, [rsp+4A0h+var_460]
0x180028d58  lea     rdx, [rsp+4A0h+var_468]
0x180028d5d  mov     rcx, rdi
0x180028d60  mov     [rsp+4A0h+var_468], rsi
0x180028d65  mov     [rsp+4A0h+bstrString], rsi
0x180028d6a  mov     r14d, esi
0x180028d6d  mov     rax, [rdi]
0x180028d70  mov     rax, [rax+148h]
0x180028d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d7c  mov     ebx, eax
0x180028d7e  test    eax, eax
0x180028d80  js      loc_180028EDC
0x180028d86  cmp     [rsp+4A0h+var_468], rsi
0x180028d8b  jz      loc_180028EDC
0x180028d91  mov     rax, [rdi]
0x180028d94  lea     rdx, [rsp+4A0h+bstrString]
0x180028d99  mov     rcx, rdi
0x180028d9c  mov     rax, [rax+138h]
0x180028da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028da8  mov     ebx, eax
0x180028daa  test    eax, eax
0x180028dac  js      loc_180028ECB
0x180028db2  mov     r8, [rsp+4A0h+bstrString]
0x180028db7  test    r8, r8
0x180028dba  jz      loc_180028ECB
0x180028dc0  mov     ecx, 7FFFFFFFh
0x180028dc5  mov     rax, r8
0x180028dc8  mov     edx, ecx
0x180028dca  cmp     [rax], si
0x180028dcd  jz      short loc_180028DD9
0x180028dcf  add     rax, 2
0x180028dd3  sub     rdx, 1
0x180028dd7  jnz     short loc_180028DCA
0x180028dd9  mov     rax, rdx
0x180028ddc  neg     rax
0x180028ddf  mov     rax, rdx
0x180028de2  sbb     ebx, ebx
0x180028de4  sub     rcx, rdx
0x180028de7  not     ebx
0x180028de9  and     ebx, 80070057h
0x180028def  neg     rax
0x180028df2  sbb     rsi, rsi
0x180028df5  xor     edi, edi
0x180028df7  and     rsi, rcx
0x180028dfa  test    rdx, rdx
0x180028dfd  jz      loc_180028EBA
0x180028e03  lea     eax, [rdi+1Fh]
0x180028e06  mov     edx, 100h
0x180028e0b  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180028e12  lea     r9, [rsp+4A0h+String2]
0x180028e17  test    rax, rax
0x180028e1a  jz      short loc_180028E3B
  ... truncated ...
```
