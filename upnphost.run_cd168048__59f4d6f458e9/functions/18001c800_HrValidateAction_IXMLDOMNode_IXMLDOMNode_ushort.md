# HrValidateAction(IXMLDOMNode *,IXMLDOMNode *,ushort * *)

- ea: `0x18001c800`
- end: `0x18001d003`
- name: `?HrValidateAction@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z`
- size: `2051`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c310`

## callees

- `0x18001c800`
- `0x18001d010`
- `0x1800200f4`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001cd60`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001cdf7`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001cd60`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001cdf7`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001cd7d`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001ce10`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001cd7d`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001ce10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cac4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cd15`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cd31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cdac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cdc8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cac4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cd15`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cd31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cdac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001cdc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccdb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccdb`

## string_xrefs

- `0x18001c925`: `urn:schemas-upnp-org:service-1-`
- `0x18001cb16`: `urn:schemas-upnp-org:service-1-`

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
0x18001c800  mov     r11, rsp
0x18001c803  push    rbp
0x18001c804  push    rbx
0x18001c805  lea     rbp, [r11-3A8h]
0x18001c80c  sub     rsp, 498h
0x18001c813  mov     rax, cs:__security_cookie
0x18001c81a  xor     rax, rsp
0x18001c81d  mov     [rbp+3A0h+var_40], rax
0x18001c824  mov     rax, [rcx]
0x18001c827  mov     [r11+20h], rsi
0x18001c82b  xor     esi, esi
0x18001c82d  mov     [r11-18h], rdi
0x18001c831  mov     [r11-20h], r12
0x18001c835  mov     r12, rdx
0x18001c838  mov     rax, [rax+68h]
0x18001c83c  lea     rdx, [rsp+4A0h+var_460]
0x18001c841  mov     [r11-28h], r13
0x18001c845  mov     r13, r8
0x18001c848  mov     [r11-38h], r15
0x18001c84c  mov     r15d, esi
0x18001c84f  mov     [rsp+4A0h+var_458], rsi
0x18001c854  mov     [rsp+4A0h+var_460], rsi
0x18001c859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c85e  mov     rdi, [rsp+4A0h+var_460]
0x18001c863  mov     ebx, eax
0x18001c865  mov     [rsp+4A0h+var_28], r14
0x18001c86d  nop     dword ptr [rax]
0x18001c870  test    ebx, ebx
0x18001c872  js      loc_18001CC56
0x18001c878  test    rdi, rdi
0x18001c87b  jz      loc_18001CE4D
0x18001c881  mov     [rsp+4A0h+var_450], rsi
0x18001c886  lea     rdx, [rsp+4A0h+var_468]
0x18001c88b  mov     rax, [rdi]
0x18001c88e  mov     rcx, rdi
0x18001c891  mov     [rsp+4A0h+var_468], rsi
0x18001c896  mov     r14d, esi
0x18001c899  mov     [rsp+4A0h+bstrString], rsi
0x18001c89e  mov     rax, [rax+148h]
0x18001c8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8aa  mov     ebx, eax
0x18001c8ac  test    eax, eax
0x18001c8ae  js      loc_18001C9F9
0x18001c8b4  cmp     [rsp+4A0h+var_468], 0
0x18001c8ba  jz      loc_18001C9F9
0x18001c8c0  mov     rax, [rdi]
0x18001c8c3  lea     rdx, [rsp+4A0h+bstrString]
0x18001c8c8  mov     rcx, rdi
0x18001c8cb  mov     rax, [rax+138h]
0x18001c8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d7  mov     ebx, eax
0x18001c8d9  test    eax, eax
0x18001c8db  js      loc_18001C9E8
0x18001c8e1  mov     r10, [rsp+4A0h+bstrString]
0x18001c8e6  test    r10, r10
0x18001c8e9  jz      loc_18001C9E8
0x18001c8ef  mov     ecx, 7FFFFFFFh
0x18001c8f4  mov     rax, r10
0x18001c8f7  cmp     word ptr [rax], 0
0x18001c8fb  jz      short loc_18001C90E
0x18001c8fd  add     rax, 2
0x18001c901  sub     rcx, 1
0x18001c905  jnz     short loc_18001C8F7
0x18001c907  mov     ebx, 80070057h
0x18001c90c  jmp     short loc_18001C918
0x18001c90e  mov     esi, 7FFFFFFFh
0x18001c913  sub     rsi, rcx
0x18001c916  xor     ebx, ebx
0x18001c918  test    ebx, ebx
0x18001c91a  js      loc_18001CE5E
0x18001c920  mov     ecx, 1Fh
0x18001c925  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18001c92c  mov     r8d, 100h
0x18001c932  lea     r9, [rbp+3A0h+String1]
0x18001c939  nop     dword ptr [rax+00000000h]
0x18001c940  test    rcx, rcx
0x18001c943  jz      short loc_18001C962
0x18001c945  movzx   eax, word ptr [rdx]
0x18001c948  test    ax, ax
0x18001c94b  jz      short loc_18001C962
0x18001c94d  mov     [r9], ax
0x18001c951  add     rdx, 2
0x18001c955  add     r9, 2
0x18001c959  dec     rcx
0x18001c95c  sub     r8, 1
0x18001c960  jnz     short loc_18001C940
0x18001c962  test    r8, r8
0x18001c965  lea     rcx, [r9-2]
0x18001c969  mov     ebx, 8007007Ah
0x18001c96e  cmovnz  rcx, r9
0x18001c972  xor     eax, eax
0x18001c974  test    r8, r8
0x18001c977  cmovnz  ebx, eax
0x18001c97a  mov     [rcx], ax
0x18001c97d  test    ebx, ebx
0x18001c97f  js      short loc_18001C9D7
0x18001c981  mov     ecx, 1Fh
0x18001c986  lea     r9, [rsp+4A0h+String2]
0x18001c98b  mov     rdx, r10
0x18001c98e  mov     r8d, 100h
0x18001c994  test    rcx, rcx
0x18001c997  jz      short loc_18001C9B6
0x18001c999  movzx   eax, word ptr [rdx]
0x18001c99c  test    ax, ax
0x18001c99f  jz      short loc_18001C9B6
0x18001c9a1  mov     [r9], ax
0x18001c9a5  add     rdx, 2
0x18001c9a9  add     r9, 2
0x18001c9ad  dec     rcx
0x18001c9b0  sub     r8, 1
0x18001c9b4  jnz     short loc_18001C994
0x18001c9b6  test    r8, r8
0x18001c9b9  lea     rcx, [r9-2]
0x18001c9bd  mov     ebx, 8007007Ah
0x18001c9c2  cmovnz  rcx, r9
0x18001c9c6  xor     eax, eax
0x18001c9c8  test    r8, r8
0x18001c9cb  cmovnz  ebx, eax
0x18001c9ce  mov     [rcx], ax
0x18001c9d1  jnz     loc_18001CD09
0x18001c9d7  xor     esi, esi
0x18001c9d9  mov     rcx, r10; bstrString
0x18001c9dc  call    cs:__imp_SysFreeString
0x18001c9e3  nop     dword ptr [rax+rax+00h]
0x18001c9e8  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x18001c9ed  call    cs:__imp_SysFreeString
0x18001c9f4  nop     dword ptr [rax+rax+00h]
0x18001c9f9  test    ebx, ebx
0x18001c9fb  jnz     loc_18001CE65
0x18001ca01  mov     [rsp+4A0h+bstrString], rsi
0x18001ca06  lea     rdx, [rsp+4A0h+var_468]
0x18001ca0b  mov     [rsp+4A0h+var_468], rsi
0x18001ca10  test    r14d, r14d
0x18001ca13  jnz     loc_18001CA97
0x18001ca19  mov     rdi, [rsp+4A0h+var_460]
0x18001ca1e  mov     r14d, esi
0x18001ca21  mov     rcx, rdi
0x18001ca24  mov     rax, [rdi]
0x18001ca27  mov     rax, [rax+148h]
0x18001ca2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca33  mov     ebx, eax
0x18001ca35  test    eax, eax
0x18001ca37  js      loc_18001CBE5
0x18001ca3d  cmp     [rsp+4A0h+var_468], 0
0x18001ca43  jz      loc_18001CBE5
0x18001ca49  mov     rax, [rdi]
0x18001ca4c  lea     rdx, [rsp+4A0h+bstrString]
0x18001ca51  mov     rcx, rdi
0x18001ca54  mov     rax, [rax+138h]
0x18001ca5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca60  mov     ebx, eax
0x18001ca62  test    eax, eax
0x18001ca64  js      loc_18001CBD4
0x18001ca6a  mov     r10, [rsp+4A0h+bstrString]
0x18001ca6f  test    r10, r10
0x18001ca72  jz      loc_18001CBD4
0x18001ca78  mov     ecx, 7FFFFFFFh
0x18001ca7d  mov     rax, r10
0x18001ca80  cmp     word ptr [rax], 0
0x18001ca84  jz      short loc_18001CAFF
0x18001ca86  add     rax, 2
0x18001ca8a  sub     rcx, 1
0x18001ca8e  jnz     short loc_18001CA80
0x18001ca90  mov     ebx, 80070057h
0x18001ca95  jmp     short loc_18001CB09
0x18001ca97  mov     rcx, [rsp+4A0h+var_460]
0x18001ca9c  inc     r15d
0x18001ca9f  mov     rax, [rcx]
0x18001caa2  mov     rax, [rax+0D0h]
0x18001caa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caae  mov     ebx, eax
0x18001cab0  test    eax, eax
0x18001cab2  js      loc_18001CED0
0x18001cab8  mov     rcx, [rsp+4A0h+var_468]; lpString1
0x18001cabd  lea     rdx, Format; lpString2
0x18001cac4  call    cs:__imp_lstrcmpW
0x18001cacb  nop     dword ptr [rax+rax+00h]
0x18001cad0  test    eax, eax
0x18001cad2  jz      loc_18001CCB8
0x18001cad8  mov     r8, [rsp+4A0h+var_468]
0x18001cadd  mov     ecx, esi; int
0x18001cadf  nop
0x18001cae0  movsxd  rax, ecx
0x18001cae3  movzx   edx, word ptr [r8+rax*2]
0x18001cae8  test    dx, dx
0x18001caeb  jz      loc_18001CCD6
0x18001caf1  cmp     dx, 2Dh ; '-'
0x18001caf5  jz      loc_18001CEAB
0x18001cafb  inc     ecx
0x18001cafd  jmp     short loc_18001CAE0
0x18001caff  mov     esi, 7FFFFFFFh
0x18001cb04  sub     rsi, rcx
0x18001cb07  xor     ebx, ebx
0x18001cb09  test    ebx, ebx
0x18001cb0b  js      loc_18001CF4C
0x18001cb11  mov     ecx, 1Fh
0x18001cb16  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18001cb1d  mov     r8d, 100h
0x18001cb23  lea     r9, [rsp+4A0h+String2]
0x18001cb28  test    rcx, rcx
0x18001cb2b  jz      short loc_18001CB4A
0x18001cb2d  movzx   eax, word ptr [rdx]
0x18001cb30  test    ax, ax
0x18001cb33  jz      short loc_18001CB4A
0x18001cb35  mov     [r9], ax
0x18001cb39  add     rdx, 2
0x18001cb3d  add     r9, 2
0x18001cb41  dec     rcx
0x18001cb44  sub     r8, 1
0x18001cb48  jnz     short loc_18001CB28
0x18001cb4a  test    r8, r8
0x18001cb4d  lea     rcx, [r9-2]
0x18001cb51  mov     ebx, 8007007Ah
0x18001cb56  cmovnz  rcx, r9
0x18001cb5a  xor     eax, eax
0x18001cb5c  test    r8, r8
0x18001cb5f  cmovnz  ebx, eax
0x18001cb62  mov     [rcx], ax
0x18001cb65  test    ebx, ebx
0x18001cb67  js      short loc_18001CBC3
0x18001cb69  mov     ecx, 1Fh
0x18001cb6e  lea     r9, [rbp+3A0h+String1]
0x18001cb75  mov     rdx, r10
0x18001cb78  mov     r8d, 100h
0x18001cb7e  xchg    ax, ax
0x18001cb80  test    rcx, rcx
0x18001cb83  jz      short loc_18001CBA2
0x18001cb85  movzx   eax, word ptr [rdx]
0x18001cb88  test    ax, ax
0x18001cb8b  jz      short loc_18001CBA2
0x18001cb8d  mov     [r9], ax
0x18001cb91  add     rdx, 2
0x18001cb95  add     r9, 2
0x18001cb99  dec     rcx
0x18001cb9c  sub     r8, 1
0x18001cba0  jnz     short loc_18001CB80
0x18001cba2  test    r8, r8
0x18001cba5  lea     rcx, [r9-2]
0x18001cba9  mov     ebx, 8007007Ah
0x18001cbae  cmovnz  rcx, r9
0x18001cbb2  xor     eax, eax
0x18001cbb4  test    r8, r8
0x18001cbb7  cmovnz  ebx, eax
0x18001cbba  mov     [rcx], ax
0x18001cbbd  jnz     loc_18001CDA0
0x18001cbc3  xor     esi, esi
0x18001cbc5  mov     rcx, r10; bstrString
0x18001cbc8  call    cs:__imp_SysFreeString
0x18001cbcf  nop     dword ptr [rax+rax+00h]
0x18001cbd4  mov     rcx, [rsp+4A0h+var_468]; bstrString
0x18001cbd9  call    cs:__imp_SysFreeString
0x18001cbe0  nop     dword ptr [rax+rax+00h]
0x18001cbe5  test    ebx, ebx
0x18001cbe7  jnz     loc_18001CF53
0x18001cbed  test    r14d, r14d
0x18001cbf0  jz      short loc_18001CC0A
0x18001cbf2  mov     rcx, [rsp+4A0h+var_460]; struct IXMLDOMNode *
0x18001cbf7  lea     r8, [rsp+4A0h+var_458]; unsigned __int16 **
0x18001cbfc  mov     rdx, r12; struct IXMLDOMNode *
0x18001cbff  call    ?HrValidateArgList@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z; HrValidateArgList(IXMLDOMNode *,IXMLDOMNode *,ushort * *)
0x18001cc04  mov     ebx, eax
0x18001cc06  test    ebx, ebx
0x18001cc08  js      short loc_18001CC45
0x18001cc0a  mov     rcx, [rsp+4A0h+var_460]
0x18001cc0f  lea     rdx, [rsp+4A0h+var_450]
0x18001cc14  mov     rax, [rcx]
0x18001cc17  mov     rax, [rax+80h]
0x18001cc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc23  mov     rcx, [rsp+4A0h+var_460]
0x18001cc28  mov     ebx, eax
0x18001cc2a  mov     rax, [rcx]
0x18001cc2d  mov     rax, [rax+10h]
0x18001cc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc36  mov     rdi, [rsp+4A0h+var_450]
0x18001cc3b  mov     [rsp+4A0h+var_460], rdi
0x18001cc40  jmp     loc_18001C870
0x18001cc45  mov     rcx, [rsp+4A0h+var_460]
0x18001cc4a  mov     rax, [rcx]
0x18001cc4d  mov     rax, [rax+10h]
0x18001cc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc56  mov     rax, [rsp+4A0h+var_458]
0x18001cc5b  mov     r15, [rsp+4A0h+var_30]
0x18001cc63  mov     r14, [rsp+4A0h+var_28]
0x18001cc6b  mov     r12, [rsp+4A0h+var_18]
0x18001cc73  mov     rdi, [rsp+490h]
0x18001cc7b  mov     rsi, [rsp+4A0h+arg_18]
0x18001cc83  test    rax, rax
0x18001cc86  jnz     loc_18001CFB4
0x18001cc8c  mov     r13, [rsp+4A0h+var_20]
0x18001cc94  test    ebx, ebx
0x18001cc96  jnz     loc_18001CFBD
0x18001cc9c  mov     eax, ebx
0x18001cc9e  mov     rcx, [rbp+3A0h+var_40]
0x18001cca5  xor     rcx, rsp; StackCookie
0x18001cca8  call    __security_check_cookie
0x18001ccad  add     rsp, 498h
0x18001ccb4  pop     rbx
0x18001ccb5  pop     rbp
0x18001ccb6  retn
0x18001ccb8  lea     r9, [rsp+4A0h+bstrString]; unsigned __int16 **
  ... truncated ...
```
