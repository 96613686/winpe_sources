# HrValidateAllowedValueRange(IXMLDOMNode *,ushort * *)

- ea: `0x180027808`
- end: `0x1800280b9`
- name: `?HrValidateAllowedValueRange@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `2225`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007f30`

## callees

- `0x18000db4c`
- `0x180027808`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027db1`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027e2c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027ea7`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027db1`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027e2c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027ea7`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027dc8`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027e43`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027ebe`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027dc8`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027e43`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027ebe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027d76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027d8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027df1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027e07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027e6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027e82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027d76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027d8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027df1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027e07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027e6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027e82`
- `OLEAUT32!__imp_SysFreeString` at `0x1800279e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800279f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b80`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d03`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800279e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800279f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b80`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d03`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d0e`

## string_xrefs

- `0x180027933`: `urn:schemas-upnp-org:service-1-`
- `0x180027ac1`: `urn:schemas-upnp-org:service-1-`
- `0x180027c4f`: `urn:schemas-upnp-org:service-1-`

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
0x180027808  mov     [rsp-8+arg_10], rbx
0x18002780d  push    rbp
0x18002780e  push    rsi
0x18002780f  push    rdi
0x180027810  push    r12
0x180027812  push    r13
0x180027814  push    r14
0x180027816  push    r15
0x180027818  lea     rbp, [rsp-370h]
0x180027820  sub     rsp, 470h
0x180027827  mov     rax, cs:__security_cookie
0x18002782e  xor     rax, rsp
0x180027831  mov     [rbp+3A0h+var_40], rax
0x180027838  mov     rax, [rcx]
0x18002783b  xor     esi, esi
0x18002783d  mov     [rsp+4A0h+var_448], rdx
0x180027842  mov     r13d, esi
0x180027845  lea     rdx, [rsp+4A0h+var_460]
0x18002784a  mov     [rsp+4A0h+var_458], rsi
0x18002784f  mov     [rsp+4A0h+var_460], rsi
0x180027854  mov     r12d, esi
0x180027857  mov     rax, [rax+68h]
0x18002785b  mov     r15d, esi
0x18002785e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027863  mov     rdi, [rsp+4A0h+var_460]
0x180027868  mov     ebx, eax
0x18002786a  test    ebx, ebx
0x18002786c  js      loc_180027EE7
0x180027872  test    rdi, rdi
0x180027875  jz      loc_180028020
0x18002787b  mov     [rsp+4A0h+var_450], rsi
0x180027880  lea     rdx, [rsp+4A0h+var_468]
0x180027885  mov     rax, [rdi]
0x180027888  mov     rcx, rdi
0x18002788b  mov     [rsp+4A0h+var_468], rsi
0x180027890  mov     r14d, esi
0x180027893  mov     [rsp+4A0h+bstrString], rsi
0x180027898  mov     rax, [rax+148h]
0x18002789f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278a4  mov     ebx, eax
0x1800278a6  test    eax, eax
0x1800278a8  js      loc_1800279F8
0x1800278ae  cmp     [rsp+4A0h+var_468], rsi
0x1800278b3  jz      loc_1800279F8
0x1800278b9  mov     rax, [rdi]
0x1800278bc  lea     rdx, [rsp+4A0h+bstrString]
0x1800278c1  mov     rcx, rdi
0x1800278c4  mov     rax, [rax+138h]
0x1800278cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278d0  mov     ebx, eax
0x1800278d2  test    eax, eax
0x1800278d4  js      loc_1800279ED
0x1800278da  mov     r8, [rsp+4A0h+bstrString]
0x1800278df  test    r8, r8
0x1800278e2  jz      loc_1800279ED
0x1800278e8  mov     ecx, 7FFFFFFFh
0x1800278ed  mov     rax, r8
0x1800278f0  mov     edx, ecx
0x1800278f2  cmp     [rax], si
0x1800278f5  jz      short loc_180027901
0x1800278f7  add     rax, 2
0x1800278fb  sub     rdx, 1
0x1800278ff  jnz     short loc_1800278F2
0x180027901  mov     rax, rdx
0x180027904  neg     rax
0x180027907  mov     rax, rdx
0x18002790a  sbb     ebx, ebx
0x18002790c  sub     rcx, rdx
0x18002790f  not     ebx
0x180027911  and     ebx, 80070057h
0x180027917  neg     rax
0x18002791a  sbb     rsi, rsi
0x18002791d  xor     edi, edi
0x18002791f  and     rsi, rcx
0x180027922  test    rdx, rdx
0x180027925  jz      loc_1800279E2
0x18002792b  lea     eax, [rdi+1Fh]
0x18002792e  mov     edx, 100h
0x180027933  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18002793a  lea     r9, [rbp+3A0h+String1]
0x180027941  test    rax, rax
0x180027944  jz      short loc_180027965
0x180027946  movzx   r10d, word ptr [rcx]
0x18002794a  test    r10w, r10w
0x18002794e  jz      short loc_180027965
0x180027950  mov     [r9], r10w
0x180027954  add     rcx, 2
0x180027958  add     r9, 2
0x18002795c  dec     rax
0x18002795f  sub     rdx, 1
0x180027963  jnz     short loc_180027941
0x180027965  mov     rax, rdx
0x180027968  lea     rcx, [r9-2]
0x18002796c  neg     rax
0x18002796f  mov     r11d, 8007007Ah
0x180027975  sbb     ebx, ebx
0x180027977  not     ebx
0x180027979  and     ebx, r11d
0x18002797c  test    rdx, rdx
0x18002797f  cmovnz  rcx, r9
0x180027983  mov     [rcx], di
0x180027986  jz      short loc_1800279E2
0x180027988  mov     ecx, 1Fh
0x18002798d  lea     rax, [rsp+4A0h+String2]
0x180027992  mov     r9, r8
0x180027995  mov     edx, 100h
0x18002799a  test    rcx, rcx
0x18002799d  jz      short loc_1800279BE
0x18002799f  movzx   r10d, word ptr [r9]
0x1800279a3  test    r10w, r10w
0x1800279a7  jz      short loc_1800279BE
0x1800279a9  mov     [rax], r10w
0x1800279ad  add     r9, 2
0x1800279b1  add     rax, 2
0x1800279b5  dec     rcx
0x1800279b8  sub     rdx, 1
0x1800279bc  jnz     short loc_18002799A
0x1800279be  test    rdx, rdx
0x1800279c1  lea     rcx, [rax-2]
0x1800279c5  cmovnz  rcx, rax
0x1800279c9  mov     rax, rdx
0x1800279cc  neg     rax
0x1800279cf  sbb     ebx, ebx
0x1800279d1  not     ebx
0x1800279d3  mov     [rcx], di
0x1800279d6  and     ebx, r11d
0x1800279d9  test    rdx, rdx
0x1800279dc  jnz     loc_180027D6A
0x1800279e2  xor     esi, esi
0x1800279e4  mov     rcx, r8; bstrString
0x1800279e7  call    cs:__imp_SysFreeString
0x1800279ed  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x1800279f2  call    cs:__imp_SysFreeString
0x1800279f8  test    ebx, ebx
0x1800279fa  jnz     loc_180027F46
0x180027a00  test    r14d, r14d
0x180027a03  jnz     loc_180027D60
0x180027a09  mov     rdi, [rsp+4A0h+var_460]
0x180027a0e  lea     rdx, [rsp+4A0h+var_468]
0x180027a13  mov     rcx, rdi
0x180027a16  mov     [rsp+4A0h+var_468], rsi
0x180027a1b  mov     [rsp+4A0h+bstrString], rsi
0x180027a20  mov     r14d, esi
0x180027a23  mov     rax, [rdi]
0x180027a26  mov     rax, [rax+148h]
0x180027a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a32  mov     ebx, eax
0x180027a34  test    eax, eax
0x180027a36  js      loc_180027B86
0x180027a3c  cmp     [rsp+4A0h+var_468], rsi
0x180027a41  jz      loc_180027B86
0x180027a47  mov     rax, [rdi]
0x180027a4a  lea     rdx, [rsp+4A0h+bstrString]
0x180027a4f  mov     rcx, rdi
0x180027a52  mov     rax, [rax+138h]
0x180027a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a5e  mov     ebx, eax
0x180027a60  test    eax, eax
0x180027a62  js      loc_180027B7B
0x180027a68  mov     r8, [rsp+4A0h+bstrString]
0x180027a6d  test    r8, r8
0x180027a70  jz      loc_180027B7B
0x180027a76  mov     ecx, 7FFFFFFFh
0x180027a7b  mov     rax, r8
0x180027a7e  mov     edx, ecx
0x180027a80  cmp     [rax], si
0x180027a83  jz      short loc_180027A8F
0x180027a85  add     rax, 2
0x180027a89  sub     rdx, 1
0x180027a8d  jnz     short loc_180027A80
0x180027a8f  mov     rax, rdx
0x180027a92  neg     rax
0x180027a95  mov     rax, rdx
0x180027a98  sbb     ebx, ebx
0x180027a9a  sub     rcx, rdx
0x180027a9d  not     ebx
0x180027a9f  and     ebx, 80070057h
0x180027aa5  neg     rax
0x180027aa8  sbb     rsi, rsi
0x180027aab  xor     edi, edi
0x180027aad  and     rsi, rcx
0x180027ab0  test    rdx, rdx
0x180027ab3  jz      loc_180027B70
0x180027ab9  lea     eax, [rdi+1Fh]
0x180027abc  mov     edx, 100h
0x180027ac1  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180027ac8  lea     r9, [rsp+4A0h+String2]
0x180027acd  test    rax, rax
0x180027ad0  jz      short loc_180027AF1
0x180027ad2  movzx   r10d, word ptr [rcx]
0x180027ad6  test    r10w, r10w
0x180027ada  jz      short loc_180027AF1
0x180027adc  mov     [r9], r10w
0x180027ae0  add     rcx, 2
0x180027ae4  add     r9, 2
0x180027ae8  dec     rax
0x180027aeb  sub     rdx, 1
0x180027aef  jnz     short loc_180027ACD
0x180027af1  mov     rax, rdx
0x180027af4  lea     rcx, [r9-2]
0x180027af8  neg     rax
0x180027afb  mov     r11d, 8007007Ah
0x180027b01  sbb     ebx, ebx
0x180027b03  not     ebx
0x180027b05  and     ebx, r11d
0x180027b08  test    rdx, rdx
0x180027b0b  cmovnz  rcx, r9
0x180027b0f  mov     [rcx], di
0x180027b12  jz      short loc_180027B70
0x180027b14  mov     ecx, 1Fh
0x180027b19  lea     rax, [rbp+3A0h+String1]
0x180027b20  mov     r9, r8
0x180027b23  mov     edx, 100h
0x180027b28  test    rcx, rcx
0x180027b2b  jz      short loc_180027B4C
0x180027b2d  movzx   r10d, word ptr [r9]
0x180027b31  test    r10w, r10w
0x180027b35  jz      short loc_180027B4C
0x180027b37  mov     [rax], r10w
0x180027b3b  add     r9, 2
0x180027b3f  add     rax, 2
0x180027b43  dec     rcx
0x180027b46  sub     rdx, 1
0x180027b4a  jnz     short loc_180027B28
0x180027b4c  test    rdx, rdx
0x180027b4f  lea     rcx, [rax-2]
0x180027b53  cmovnz  rcx, rax
0x180027b57  mov     rax, rdx
0x180027b5a  neg     rax
0x180027b5d  sbb     ebx, ebx
0x180027b5f  not     ebx
0x180027b61  mov     [rcx], di
0x180027b64  and     ebx, r11d
0x180027b67  test    rdx, rdx
0x180027b6a  jnz     loc_180027DE5
0x180027b70  xor     esi, esi
0x180027b72  mov     rcx, r8; bstrString
0x180027b75  call    cs:__imp_SysFreeString
0x180027b7b  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x180027b80  call    cs:__imp_SysFreeString
0x180027b86  test    ebx, ebx
0x180027b88  jnz     loc_180027F8C
0x180027b8e  test    r14d, r14d
0x180027b91  jnz     loc_180027D65
0x180027b97  mov     rdi, [rsp+4A0h+var_460]
0x180027b9c  lea     rdx, [rsp+4A0h+var_468]
0x180027ba1  mov     rcx, rdi
0x180027ba4  mov     [rsp+4A0h+var_468], rsi
0x180027ba9  mov     [rsp+4A0h+bstrString], rsi
0x180027bae  mov     r14d, esi
0x180027bb1  mov     rax, [rdi]
0x180027bb4  mov     rax, [rax+148h]
0x180027bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bc0  mov     ebx, eax
0x180027bc2  test    eax, eax
0x180027bc4  js      loc_180027D14
0x180027bca  cmp     [rsp+4A0h+var_468], rsi
0x180027bcf  jz      loc_180027D14
0x180027bd5  mov     rax, [rdi]
0x180027bd8  lea     rdx, [rsp+4A0h+bstrString]
0x180027bdd  mov     rcx, rdi
0x180027be0  mov     rax, [rax+138h]
0x180027be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bec  mov     ebx, eax
0x180027bee  test    eax, eax
0x180027bf0  js      loc_180027D09
0x180027bf6  mov     r8, [rsp+4A0h+bstrString]
0x180027bfb  test    r8, r8
0x180027bfe  jz      loc_180027D09
0x180027c04  mov     ecx, 7FFFFFFFh
0x180027c09  mov     rax, r8
0x180027c0c  mov     edx, ecx
0x180027c0e  cmp     [rax], si
0x180027c11  jz      short loc_180027C1D
0x180027c13  add     rax, 2
0x180027c17  sub     rdx, 1
0x180027c1b  jnz     short loc_180027C0E
0x180027c1d  mov     rax, rdx
0x180027c20  neg     rax
0x180027c23  mov     rax, rdx
0x180027c26  sbb     ebx, ebx
0x180027c28  sub     rcx, rdx
0x180027c2b  not     ebx
0x180027c2d  and     ebx, 80070057h
0x180027c33  neg     rax
0x180027c36  sbb     rsi, rsi
0x180027c39  xor     edi, edi
0x180027c3b  and     rsi, rcx
0x180027c3e  test    rdx, rdx
0x180027c41  jz      loc_180027CFE
0x180027c47  lea     eax, [rdi+1Fh]
0x180027c4a  mov     edx, 100h
0x180027c4f  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180027c56  lea     r9, [rsp+4A0h+String2]
0x180027c5b  test    rax, rax
0x180027c5e  jz      short loc_180027C7F
0x180027c60  movzx   r10d, word ptr [rcx]
0x180027c64  test    r10w, r10w
0x180027c68  jz      short loc_180027C7F
0x180027c6a  mov     [r9], r10w
  ... truncated ...
```
