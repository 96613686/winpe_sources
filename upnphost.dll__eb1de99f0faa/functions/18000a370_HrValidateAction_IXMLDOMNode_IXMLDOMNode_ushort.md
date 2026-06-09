# HrValidateAction(IXMLDOMNode *,IXMLDOMNode *,ushort * *)

- ea: `0x18000a370`
- end: `0x18000ab20`
- name: `?HrValidateAction@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z`
- size: `1968`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009eb0`

## callees

- `0x18000a370`
- `0x18000ab30`
- `0x18000db4c`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000a8a1`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000a920`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000a8a1`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000a920`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000a8b8`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000a933`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000a8b8`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000a933`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a624`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a862`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a878`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a8e1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a8f7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a624`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a862`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a878`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a8e1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a8f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a54c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a557`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a728`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a733`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a82e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a54c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a557`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a728`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a733`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a82e`

## string_xrefs

- `0x18000a495`: `urn:schemas-upnp-org:service-1-`
- `0x18000a676`: `urn:schemas-upnp-org:service-1-`

## pseudocode

```c
__int64 __fastcall HrValidateAction(struct IXMLDOMNode *a1, struct IXMLDOMNode *a2, unsigned __int16 **a3)
{
  unsigned __int64 v3; // rsi
  HRESULT (__stdcall *get_firstChild)(IXMLDOMNode *, IXMLDOMNode **); // rax
  int v7; // r15d
  int v8; // eax
  int v9; // ecx
  struct IXMLDOMNode *v10; // rdi
  int v11; // ebx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v13; // r14d
  int v14; // ebx
  OLECHAR *v15; // r10
  __int64 v16; // rcx
  BSTR v17; // rax
  __int64 v18; // rcx
  const wchar_t *v19; // rdx
  __int64 v20; // r8
  WCHAR *v21; // r9
  WCHAR *v22; // rcx
  __int64 v23; // rcx
  WCHAR *v24; // r9
  OLECHAR *v25; // rdx
  __int64 v26; // r8
  WCHAR *v27; // rcx
  struct IXMLDOMNode *v28; // rdi
  int v29; // r14d
  int v30; // ebx
  OLECHAR *v31; // r10
  __int64 v32; // rcx
  BSTR v33; // rax
  int v34; // eax
  int v35; // ecx
  int k; // ecx
  OLECHAR v37; // dx
  __int64 v38; // rcx
  const wchar_t *v39; // rdx
  __int64 v40; // r8
  WCHAR *v41; // r9
  WCHAR *v42; // rcx
  __int64 v43; // rcx
  WCHAR *v44; // r9
  OLECHAR *v45; // rdx
  __int64 v46; // r8
  WCHAR *v47; // rcx
  bool v48; // sf
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rdi
  STRSAFE_PCNZWCH v52; // rcx
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  BSTR v54; // [rsp+40h] [rbp-C8h] BYREF
  struct IXMLDOMNode *v55; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v56; // [rsp+50h] [rbp-B8h] BYREF
  struct IXMLDOMNode *v57; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR String2[256]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR String1[256]; // [rsp+268h] [rbp+160h] BYREF

  v3 = 0;
  get_firstChild = a1->lpVtbl->get_firstChild;
  v7 = 0;
  v56 = 0;
  v55 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))get_firstChild)(a1, &v55);
  v10 = v55;
  v11 = v8;
  while ( v11 >= 0 )
  {
    if ( !v10 )
    {
      if ( v7 == 1 )
        v11 = 0;
      else
        v11 = HrAllocErrorStringAndReturnHr(v9, L"<action> did not contain exactly one <name> element", 0, &v56);
      break;
    }
    v57 = 0;
    lpVtbl = v10->lpVtbl;
    v54 = 0;
    v13 = 0;
    bstrString = 0;
    v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_baseName)(v10, &v54);
    if ( v14 >= 0 && v54 )
    {
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v10->lpVtbl->get_namespaceURI)(v10, &bstrString);
      if ( v14 >= 0 )
      {
        v15 = bstrString;
        if ( bstrString )
        {
          v16 = 0x7FFFFFFF;
          v17 = bstrString;
          while ( *v17 )
          {
            ++v17;
            if ( !--v16 )
            {
              v14 = -2147024809;
              goto LABEL_13;
            }
          }
          v3 = 0x7FFFFFFF - v16;
          v14 = 0;
LABEL_13:
          if ( v14 < 0 )
          {
            v3 = 0;
          }
          else
          {
            v18 = 31;
            v19 = L"urn:schemas-upnp-org:service-1-";
            v20 = 256;
            v21 = String1;
            do
            {
              if ( !v18 )
                break;
              if ( !*v19 )
                break;
              *v21++ = *v19++;
              --v18;
              --v20;
            }
            while ( v20 );
            v22 = v21 - 1;
            v14 = -2147024774;
            if ( v20 )
            {
              v22 = v21;
              v14 = 0;
            }
            *v22 = 0;
          }
          if ( v14 >= 0 )
          {
            v23 = 31;
            v24 = String2;
            v25 = v15;
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
            v14 = -2147024774;
            if ( v26 )
            {
              v27 = v24;
              v14 = 0;
            }
            *v27 = 0;
            if ( v26 )
            {
              if ( !lstrcmpW(v54, L"name") && !lstrcmpW(String1, String2) )
              {
                v13 = 1;
                if ( v3 > 0x1F )
                {
                  for ( i = 31; i < v3; ++i )
                  {
                    if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                    {
                      v15 = bstrString;
                      v3 = 0;
                      v13 = 0;
                      goto LABEL_30;
                    }
                  }
                }
              }
              v15 = bstrString;
            }
          }
          v3 = 0;
LABEL_30:
          SysFreeString(v15);
        }
      }
      SysFreeString(v54);
    }
    if ( v14 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
        v14);
    bstrString = 0;
    v54 = 0;
    if ( !v13 )
    {
      v28 = v55;
      v29 = 0;
      v30 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v55->lpVtbl->get_baseName)(v55, &v54);
      if ( v30 >= 0 && v54 )
      {
        v30 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v28->lpVtbl->get_namespaceURI)(v28, &bstrString);
        if ( v30 >= 0 )
        {
          v31 = bstrString;
          if ( bstrString )
          {
            v32 = 0x7FFFFFFF;
            v33 = bstrString;
            while ( *v33 )
            {
              ++v33;
              if ( !--v32 )
              {
                v30 = -2147024809;
                goto LABEL_49;
              }
            }
            v3 = 0x7FFFFFFF - v32;
            v30 = 0;
LABEL_49:
            if ( v30 < 0 )
            {
              v3 = 0;
            }
            else
            {
              v38 = 31;
              v39 = L"urn:schemas-upnp-org:service-1-";
              v40 = 256;
              v41 = String2;
              do
              {
                if ( !v38 )
                  break;
                if ( !*v39 )
                  break;
                *v41++ = *v39++;
                --v38;
                --v40;
              }
              while ( v40 );
              v42 = v41 - 1;
              v30 = -2147024774;
              if ( v40 )
              {
                v42 = v41;
                v30 = 0;
              }
              *v42 = 0;
            }
            if ( v30 >= 0 )
            {
              v43 = 31;
              v44 = String1;
              v45 = v31;
              v46 = 256;
              do
              {
                if ( !v43 )
                  break;
                if ( !*v45 )
                  break;
                *v44++ = *v45++;
                --v43;
                --v46;
              }
              while ( v46 );
              v47 = v44 - 1;
              v30 = -2147024774;
              if ( v46 )
              {
                v47 = v44;
                v30 = 0;
              }
              *v47 = 0;
              if ( v46 )
              {
                if ( !lstrcmpW(v54, L"argumentList") && !lstrcmpW(String2, String1) )
                {
                  v29 = 1;
                  if ( v3 > 0x1F )
                  {
                    for ( j = 31; j < v3; ++j )
                    {
                      if ( !IsCharAlphaNumericW(bstrString[j]) || IsCharAlphaW(bstrString[j]) )
                      {
                        v31 = bstrString;
                        v3 = 0;
                        v29 = 0;
                        goto LABEL_66;
                      }
                    }
                  }
                }
                v31 = bstrString;
              }
            }
            v3 = 0;
LABEL_66:
            SysFreeString(v31);
          }
        }
        SysFreeString(v54);
      }
      if ( v30 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
          v30);
      if ( !v29 )
        goto LABEL_73;
      v11 = HrValidateArgList(v55, a2, &v56);
      goto LABEL_71;
    }
    ++v7;
    v34 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v55->lpVtbl->get_text)(v55, &v54);
    v11 = v34;
    if ( v34 < 0 )
    {
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
            (unsigned int)"HrValidateName(): Failed to get node text",
            v34);
LABEL_114:
          v52 = WPP_GLOBAL_Control;
        }
        if ( v52 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v52[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)v52 + 2),
            15,
            (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
            (unsigned int)"HrValidateName(): Exiting",
            v11);
      }
LABEL_71:
      v48 = v11 < 0;
      goto LABEL_72;
    }
    if ( lstrcmpW(v54, &Format)
      || (v11 = HrAllocErrorStringAndReturnHr(v35, L"<name> element was empty", 0, &bstrString), v11 >= 0) )
    {
      for ( k = 0; ; ++k )
      {
        v37 = v54[k];
        if ( !v37 )
          break;
        if ( v37 == 45 )
        {
          v11 = HrAllocErrorStringAndReturnHr(k, L"<name> element may not contain '-'", 0, &bstrString);
          break;
        }
      }
    }
    SysFreeString(v54);
    if ( bstrString )
      v56 = bstrString;
    v48 = v11 < 0;
    if ( v11 )
      goto LABEL_114;
LABEL_72:
    if ( v48 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v55->lpVtbl->Release)(v55);
      break;
    }
LABEL_73:
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v55->lpVtbl->get_nextSibling)(v55, &v57);
    ((void (__fastcall *)(struct IXMLDOMNode *))v55->lpVtbl->Release)(v55);
    v10 = v57;
    v55 = v57;
  }
  if ( v56 )
    *a3 = v56;
  if ( v11 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateAction(): Exiting",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a370  mov     r11, rsp
0x18000a373  push    rbp
0x18000a374  push    rbx
0x18000a375  lea     rbp, [r11-3A8h]
0x18000a37c  sub     rsp, 498h
0x18000a383  mov     rax, cs:__security_cookie
0x18000a38a  xor     rax, rsp
0x18000a38d  mov     [rbp+3A0h+var_40], rax
0x18000a394  mov     rax, [rcx]
0x18000a397  mov     [r11+20h], rsi
0x18000a39b  xor     esi, esi
0x18000a39d  mov     [r11-18h], rdi
0x18000a3a1  mov     [r11-20h], r12
0x18000a3a5  mov     r12, rdx
0x18000a3a8  mov     rax, [rax+68h]
0x18000a3ac  lea     rdx, [rsp+4A0h+var_460]
0x18000a3b1  mov     [r11-28h], r13
0x18000a3b5  mov     r13, r8
0x18000a3b8  mov     [r11-38h], r15
0x18000a3bc  mov     r15d, esi
0x18000a3bf  mov     [rsp+4A0h+var_458], rsi
0x18000a3c4  mov     [rsp+4A0h+var_460], rsi
0x18000a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ce  mov     rdi, [rsp+4A0h+var_460]
0x18000a3d3  mov     ebx, eax
0x18000a3d5  mov     [rsp+4A0h+var_28], r14
0x18000a3dd  nop     dword ptr [rax]
0x18000a3e0  test    ebx, ebx
0x18000a3e2  js      loc_18000A7AA
0x18000a3e8  test    rdi, rdi
0x18000a3eb  jz      loc_18000A96A
0x18000a3f1  mov     [rsp+4A0h+var_450], rsi
0x18000a3f6  lea     rdx, [rsp+4A0h+var_468]
0x18000a3fb  mov     rax, [rdi]
0x18000a3fe  mov     rcx, rdi
0x18000a401  mov     [rsp+4A0h+var_468], rsi
0x18000a406  mov     r14d, esi
0x18000a409  mov     [rsp+4A0h+bstrString], rsi
0x18000a40e  mov     rax, [rax+148h]
0x18000a415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41a  mov     ebx, eax
0x18000a41c  test    eax, eax
0x18000a41e  js      loc_18000A55D
0x18000a424  cmp     [rsp+4A0h+var_468], 0
0x18000a42a  jz      loc_18000A55D
0x18000a430  mov     rax, [rdi]
0x18000a433  lea     rdx, [rsp+4A0h+bstrString]
0x18000a438  mov     rcx, rdi
0x18000a43b  mov     rax, [rax+138h]
0x18000a442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a447  mov     ebx, eax
0x18000a449  test    eax, eax
0x18000a44b  js      loc_18000A552
0x18000a451  mov     r10, [rsp+4A0h+bstrString]
0x18000a456  test    r10, r10
0x18000a459  jz      loc_18000A552
0x18000a45f  mov     ecx, 7FFFFFFFh
0x18000a464  mov     rax, r10
0x18000a467  cmp     word ptr [rax], 0
0x18000a46b  jz      short loc_18000A47E
0x18000a46d  add     rax, 2
0x18000a471  sub     rcx, 1
0x18000a475  jnz     short loc_18000A467
0x18000a477  mov     ebx, 80070057h
0x18000a47c  jmp     short loc_18000A488
0x18000a47e  mov     esi, 7FFFFFFFh
0x18000a483  sub     rsi, rcx
0x18000a486  xor     ebx, ebx
0x18000a488  test    ebx, ebx
0x18000a48a  js      loc_18000A97B
0x18000a490  mov     ecx, 1Fh
0x18000a495  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18000a49c  mov     r8d, 100h
0x18000a4a2  lea     r9, [rbp+3A0h+String1]
0x18000a4a9  nop     dword ptr [rax+00000000h]
0x18000a4b0  test    rcx, rcx
0x18000a4b3  jz      short loc_18000A4D2
0x18000a4b5  movzx   eax, word ptr [rdx]
0x18000a4b8  test    ax, ax
0x18000a4bb  jz      short loc_18000A4D2
0x18000a4bd  mov     [r9], ax
0x18000a4c1  add     rdx, 2
0x18000a4c5  add     r9, 2
0x18000a4c9  dec     rcx
0x18000a4cc  sub     r8, 1
0x18000a4d0  jnz     short loc_18000A4B0
0x18000a4d2  test    r8, r8
0x18000a4d5  lea     rcx, [r9-2]
0x18000a4d9  mov     ebx, 8007007Ah
0x18000a4de  cmovnz  rcx, r9
0x18000a4e2  xor     eax, eax
0x18000a4e4  test    r8, r8
0x18000a4e7  cmovnz  ebx, eax
0x18000a4ea  mov     [rcx], ax
0x18000a4ed  test    ebx, ebx
0x18000a4ef  js      short loc_18000A547
0x18000a4f1  mov     ecx, 1Fh
0x18000a4f6  lea     r9, [rsp+4A0h+String2]
0x18000a4fb  mov     rdx, r10
0x18000a4fe  mov     r8d, 100h
0x18000a504  test    rcx, rcx
0x18000a507  jz      short loc_18000A526
0x18000a509  movzx   eax, word ptr [rdx]
0x18000a50c  test    ax, ax
0x18000a50f  jz      short loc_18000A526
0x18000a511  mov     [r9], ax
0x18000a515  add     rdx, 2
0x18000a519  add     r9, 2
0x18000a51d  dec     rcx
0x18000a520  sub     r8, 1
0x18000a524  jnz     short loc_18000A504
0x18000a526  test    r8, r8
0x18000a529  lea     rcx, [r9-2]
0x18000a52d  mov     ebx, 8007007Ah
0x18000a532  cmovnz  rcx, r9
0x18000a536  xor     eax, eax
0x18000a538  test    r8, r8
0x18000a53b  cmovnz  ebx, eax
0x18000a53e  mov     [rcx], ax
0x18000a541  jnz     loc_18000A856
0x18000a547  xor     esi, esi
0x18000a549  mov     rcx, r10; bstrString
0x18000a54c  call    cs:__imp_SysFreeString
0x18000a552  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x18000a557  call    cs:__imp_SysFreeString
0x18000a55d  test    ebx, ebx
0x18000a55f  jnz     loc_18000A982
0x18000a565  mov     [rsp+4A0h+bstrString], rsi
0x18000a56a  lea     rdx, [rsp+4A0h+var_468]
0x18000a56f  mov     [rsp+4A0h+var_468], rsi
0x18000a574  test    r14d, r14d
0x18000a577  jnz     short loc_18000A5F7
0x18000a579  mov     rdi, [rsp+4A0h+var_460]
0x18000a57e  mov     r14d, esi
0x18000a581  mov     rcx, rdi
0x18000a584  mov     rax, [rdi]
0x18000a587  mov     rax, [rax+148h]
0x18000a58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a593  mov     ebx, eax
0x18000a595  test    eax, eax
0x18000a597  js      loc_18000A739
0x18000a59d  cmp     [rsp+4A0h+var_468], 0
0x18000a5a3  jz      loc_18000A739
0x18000a5a9  mov     rax, [rdi]
0x18000a5ac  lea     rdx, [rsp+4A0h+bstrString]
0x18000a5b1  mov     rcx, rdi
0x18000a5b4  mov     rax, [rax+138h]
0x18000a5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c0  mov     ebx, eax
0x18000a5c2  test    eax, eax
0x18000a5c4  js      loc_18000A72E
0x18000a5ca  mov     r10, [rsp+4A0h+bstrString]
0x18000a5cf  test    r10, r10
0x18000a5d2  jz      loc_18000A72E
0x18000a5d8  mov     ecx, 7FFFFFFFh
0x18000a5dd  mov     rax, r10
0x18000a5e0  cmp     word ptr [rax], 0
0x18000a5e4  jz      short loc_18000A65F
0x18000a5e6  add     rax, 2
0x18000a5ea  sub     rcx, 1
0x18000a5ee  jnz     short loc_18000A5E0
0x18000a5f0  mov     ebx, 80070057h
0x18000a5f5  jmp     short loc_18000A669
0x18000a5f7  mov     rcx, [rsp+4A0h+var_460]
0x18000a5fc  inc     r15d
0x18000a5ff  mov     rax, [rcx]
0x18000a602  mov     rax, [rax+0D0h]
0x18000a609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60e  mov     ebx, eax
0x18000a610  test    eax, eax
0x18000a612  js      loc_18000A9ED
0x18000a618  mov     rcx, [rsp+4A0h+var_468]; lpString1
0x18000a61d  lea     rdx, Format; lpString2
0x18000a624  call    cs:__imp_lstrcmpW
0x18000a62a  test    eax, eax
0x18000a62c  jz      loc_18000A80B
0x18000a632  mov     r8, [rsp+4A0h+var_468]
0x18000a637  mov     ecx, esi; int
0x18000a639  nop     dword ptr [rax+00000000h]
0x18000a640  movsxd  rax, ecx
0x18000a643  movzx   edx, word ptr [r8+rax*2]
0x18000a648  test    dx, dx
0x18000a64b  jz      loc_18000A829
0x18000a651  cmp     dx, 2Dh ; '-'
0x18000a655  jz      loc_18000A9C8
0x18000a65b  inc     ecx
0x18000a65d  jmp     short loc_18000A640
0x18000a65f  mov     esi, 7FFFFFFFh
0x18000a664  sub     rsi, rcx
0x18000a667  xor     ebx, ebx
0x18000a669  test    ebx, ebx
0x18000a66b  js      loc_18000AA69
0x18000a671  mov     ecx, 1Fh
0x18000a676  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18000a67d  mov     r8d, 100h
0x18000a683  lea     r9, [rsp+4A0h+String2]
0x18000a688  test    rcx, rcx
0x18000a68b  jz      short loc_18000A6AA
0x18000a68d  movzx   eax, word ptr [rdx]
0x18000a690  test    ax, ax
0x18000a693  jz      short loc_18000A6AA
0x18000a695  mov     [r9], ax
0x18000a699  add     rdx, 2
0x18000a69d  add     r9, 2
0x18000a6a1  dec     rcx
0x18000a6a4  sub     r8, 1
0x18000a6a8  jnz     short loc_18000A688
0x18000a6aa  test    r8, r8
0x18000a6ad  lea     rcx, [r9-2]
0x18000a6b1  mov     ebx, 8007007Ah
0x18000a6b6  cmovnz  rcx, r9
0x18000a6ba  xor     eax, eax
0x18000a6bc  test    r8, r8
0x18000a6bf  cmovnz  ebx, eax
0x18000a6c2  mov     [rcx], ax
0x18000a6c5  test    ebx, ebx
0x18000a6c7  js      short loc_18000A723
0x18000a6c9  mov     ecx, 1Fh
0x18000a6ce  lea     r9, [rbp+3A0h+String1]
0x18000a6d5  mov     rdx, r10
0x18000a6d8  mov     r8d, 100h
0x18000a6de  xchg    ax, ax
0x18000a6e0  test    rcx, rcx
0x18000a6e3  jz      short loc_18000A702
0x18000a6e5  movzx   eax, word ptr [rdx]
0x18000a6e8  test    ax, ax
0x18000a6eb  jz      short loc_18000A702
0x18000a6ed  mov     [r9], ax
0x18000a6f1  add     rdx, 2
0x18000a6f5  add     r9, 2
0x18000a6f9  dec     rcx
0x18000a6fc  sub     r8, 1
0x18000a700  jnz     short loc_18000A6E0
0x18000a702  test    r8, r8
0x18000a705  lea     rcx, [r9-2]
0x18000a709  mov     ebx, 8007007Ah
0x18000a70e  cmovnz  rcx, r9
0x18000a712  xor     eax, eax
0x18000a714  test    r8, r8
0x18000a717  cmovnz  ebx, eax
0x18000a71a  mov     [rcx], ax
0x18000a71d  jnz     loc_18000A8D5
0x18000a723  xor     esi, esi
0x18000a725  mov     rcx, r10; bstrString
0x18000a728  call    cs:__imp_SysFreeString
0x18000a72e  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x18000a733  call    cs:__imp_SysFreeString
0x18000a739  test    ebx, ebx
0x18000a73b  jnz     loc_18000AA70
0x18000a741  test    r14d, r14d
0x18000a744  jz      short loc_18000A75E
0x18000a746  mov     rcx, [rsp+4A0h+var_460]; struct IXMLDOMNode *
0x18000a74b  lea     r8, [rsp+4A0h+var_458]; unsigned __int16 **
0x18000a750  mov     rdx, r12; struct IXMLDOMNode *
0x18000a753  call    ?HrValidateArgList@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z; HrValidateArgList(IXMLDOMNode *,IXMLDOMNode *,ushort * *)
0x18000a758  mov     ebx, eax
0x18000a75a  test    ebx, ebx
0x18000a75c  js      short loc_18000A799
0x18000a75e  mov     rcx, [rsp+4A0h+var_460]
0x18000a763  lea     rdx, [rsp+4A0h+var_450]
0x18000a768  mov     rax, [rcx]
0x18000a76b  mov     rax, [rax+80h]
0x18000a772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a777  mov     rcx, [rsp+4A0h+var_460]
0x18000a77c  mov     ebx, eax
0x18000a77e  mov     rax, [rcx]
0x18000a781  mov     rax, [rax+10h]
0x18000a785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a78a  mov     rdi, [rsp+4A0h+var_450]
0x18000a78f  mov     [rsp+4A0h+var_460], rdi
0x18000a794  jmp     loc_18000A3E0
0x18000a799  mov     rcx, [rsp+4A0h+var_460]
0x18000a79e  mov     rax, [rcx]
0x18000a7a1  mov     rax, [rax+10h]
0x18000a7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7aa  mov     rax, [rsp+4A0h+var_458]
0x18000a7af  mov     r15, [rsp+4A0h+var_30]
0x18000a7b7  mov     r14, [rsp+4A0h+var_28]
0x18000a7bf  mov     r12, [rsp+4A0h+var_18]
0x18000a7c7  mov     rdi, [rsp+490h]
0x18000a7cf  mov     rsi, [rsp+4A0h+arg_18]
0x18000a7d7  test    rax, rax
0x18000a7da  jnz     loc_18000AAD1
0x18000a7e0  mov     r13, [rsp+4A0h+var_20]
0x18000a7e8  test    ebx, ebx
0x18000a7ea  jnz     loc_18000AADA
0x18000a7f0  mov     eax, ebx
0x18000a7f2  mov     rcx, [rbp+3A0h+var_40]
0x18000a7f9  xor     rcx, rsp; StackCookie
0x18000a7fc  call    __security_check_cookie
0x18000a801  add     rsp, 498h
0x18000a808  pop     rbx
0x18000a809  pop     rbp
0x18000a80a  retn
0x18000a80b  lea     r9, [rsp+4A0h+bstrString]; unsigned __int16 **
0x18000a810  xor     r8d, r8d; unsigned __int16 *
0x18000a813  lea     rdx, aNameElementWas; "<name> element was empty"
0x18000a81a  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000a81f  mov     ebx, eax
0x18000a821  test    eax, eax
  ... truncated ...
```
