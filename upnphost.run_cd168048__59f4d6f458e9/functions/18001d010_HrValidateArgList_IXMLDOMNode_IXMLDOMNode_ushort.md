# HrValidateArgList(IXMLDOMNode *,IXMLDOMNode *,ushort * *)

- ea: `0x18001d010`
- end: `0x18001d58c`
- name: `?HrValidateArgList@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z`
- size: `1404`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c800`

## callees

- `0x18001bf10`
- `0x18001d010`
- `0x18001d5a0`
- `0x1800200f4`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001d333`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001d333`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001d34c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001d34c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001d2e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001d304`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001d2e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001d304`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d206`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d21e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d206`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d21e`

## string_xrefs

- `0x18001d153`: `urn:schemas-upnp-org:service-1-`

## pseudocode

```c
__int64 __fastcall HrValidateArgList(struct IXMLDOMNode *a1, struct IXMLDOMNode *a2, unsigned __int16 **a3)
{
  HRESULT (__stdcall *get_firstChild)(IXMLDOMNode *, IXMLDOMNode **); // rax
  int v5; // r13d
  int v6; // r15d
  int v7; // eax
  int v8; // ecx
  int v9; // r8d
  struct IXMLDOMNode *v10; // rdi
  int v11; // ebx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v13; // r14d
  int v14; // ebx
  OLECHAR *v15; // r10
  __int64 v16; // rcx
  BSTR v17; // rax
  unsigned __int64 v18; // rsi
  __int64 v19; // rcx
  const wchar_t *v20; // rdx
  __int64 v21; // r8
  WCHAR *v22; // r9
  WCHAR *v23; // rcx
  __int64 v24; // rcx
  WCHAR *v25; // r9
  OLECHAR *v26; // rdx
  __int64 v27; // r8
  WCHAR *v28; // rcx
  int v29; // ecx
  int v30; // edi
  unsigned __int64 i; // rdi
  int v32; // eax
  int v33; // ecx
  STRSAFE_PCNZWCH v34; // rcx
  const unsigned __int16 *v36; // rdx
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  BSTR v38; // [rsp+40h] [rbp-C8h] BYREF
  struct IXMLDOMNode *v39; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-B8h] BYREF
  struct IXMLDOMNode *v41; // [rsp+58h] [rbp-B0h] BYREF
  struct IXMLDOMNode *v42; // [rsp+60h] [rbp-A8h]
  unsigned __int16 **v43; // [rsp+68h] [rbp-A0h]
  WCHAR String2[256]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR String1[256]; // [rsp+278h] [rbp+170h] BYREF

  get_firstChild = a1->lpVtbl->get_firstChild;
  v5 = 0;
  v6 = 0;
  v43 = a3;
  v42 = a1;
  v40 = 0;
  v39 = 0;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))get_firstChild)(a1, &v39);
  v10 = v39;
  v11 = v7;
  while ( 1 )
  {
    if ( v11 < 0 )
      goto LABEL_56;
    if ( !v10 )
      break;
    v41 = 0;
    lpVtbl = v10->lpVtbl;
    v38 = 0;
    v13 = 0;
    bstrString = 0;
    v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_baseName)(v10, &v38);
    if ( v14 >= 0 && v38 )
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
              v18 = 0;
              v14 = -2147024809;
              goto LABEL_13;
            }
          }
          v18 = 0x7FFFFFFF - v16;
          v14 = 0;
LABEL_13:
          if ( v14 < 0 )
          {
            v18 = 0;
          }
          else
          {
            v19 = 31;
            v20 = L"urn:schemas-upnp-org:service-1-";
            v21 = 256;
            v22 = String1;
            do
            {
              if ( !v19 )
                break;
              if ( !*v20 )
                break;
              *v22++ = *v20++;
              --v19;
              --v21;
            }
            while ( v21 );
            v23 = v22 - 1;
            v14 = -2147024774;
            if ( v21 )
            {
              v23 = v22;
              v14 = 0;
            }
            *v23 = 0;
          }
          if ( v14 >= 0 )
          {
            v24 = 31;
            v25 = String2;
            v26 = v15;
            v27 = 256;
            do
            {
              if ( !v24 )
                break;
              if ( !*v26 )
                break;
              *v25++ = *v26++;
              --v24;
              --v27;
            }
            while ( v27 );
            v28 = v25 - 1;
            v14 = -2147024774;
            if ( v27 )
            {
              v28 = v25;
              v14 = 0;
            }
            *v28 = 0;
            if ( v27 )
            {
              if ( !lstrcmpW(v38, L"argument") && !lstrcmpW(String1, String2) )
              {
                v13 = 1;
                if ( v18 > 0x1F )
                {
                  for ( i = 31; i < v18; ++i )
                  {
                    if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                    {
                      v13 = 0;
                      break;
                    }
                  }
                }
              }
              v15 = bstrString;
            }
          }
          SysFreeString(v15);
        }
      }
      SysFreeString(v38);
    }
    if ( v14 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
        v14);
    if ( !v13 )
      goto LABEL_40;
    LODWORD(v38) = 0;
    LODWORD(bstrString) = 0;
    v6 = 1;
    v11 = HrValidateArg(v39, a2, (int *)&v38, (int *)&bstrString, &v40);
    if ( v11 < 0 )
      goto LABEL_51;
    v30 = (int)v38;
    if ( (_DWORD)bstrString )
    {
      if ( (_DWORD)v38 )
      {
        v36 = L"<retval> element found in \"in\" <argument>";
      }
      else
      {
        if ( !v5 )
          goto LABEL_35;
        v36 = L"<retval> element found in \"out\" <argument> that was not the first one";
      }
      v11 = HrAllocErrorStringAndReturnHr(v29, v36, 0, &v40);
      if ( v11 < 0 )
        goto LABEL_51;
    }
LABEL_35:
    if ( v30 )
    {
      if ( v5 )
        v11 = HrAllocErrorStringAndReturnHr(
                v29,
                L"\"in\" <argument> found after one or more \"out\" <argument>s",
                0,
                &v40);
      if ( v11 < 0 )
      {
LABEL_51:
        ((void (__fastcall *)(struct IXMLDOMNode *))v39->lpVtbl->Release)(v39);
LABEL_56:
        v34 = WPP_GLOBAL_Control;
        goto LABEL_57;
      }
    }
    else
    {
      v5 = 1;
    }
LABEL_40:
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v39->lpVtbl->get_nextSibling)(v39, &v41);
    ((void (__fastcall *)(struct IXMLDOMNode *))v39->lpVtbl->Release)(v39);
    v10 = v41;
    v39 = v41;
  }
  if ( !v6 )
  {
    v11 = HrAllocErrorStringAndReturnHr(v8, L"<argumentList> did not contain any <argument> elements", 0, &v40);
    if ( v11 < 0 )
      goto LABEL_56;
  }
  LODWORD(bstrString) = 0;
  v32 = HrAreThereDuplicatesInChildNodeTextValues(v42, L"scpd:argument/scpd:name", v9, (int *)&bstrString);
  v11 = v32;
  if ( v32 >= 0 )
  {
    if ( (_DWORD)bstrString )
      v11 = HrAllocErrorStringAndReturnHr(
              v33,
              L"<argumentList> contained <argument> elements with duplicate names",
              0,
              &v40);
    goto LABEL_56;
  }
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateArgList(): Failed to check for duplicate names",
      v32);
    goto LABEL_56;
  }
LABEL_57:
  if ( v40 )
  {
    *v43 = v40;
    v34 = WPP_GLOBAL_Control;
  }
  if ( v11 && v34 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v34[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)v34 + 2),
      24,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateArgList(): Exiting",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001d010  mov     r11, rsp
0x18001d013  push    rbp
0x18001d014  push    rbx
0x18001d015  push    rsi
0x18001d016  lea     rbp, [r11-3B8h]
0x18001d01d  sub     rsp, 4A0h
0x18001d024  mov     rax, cs:__security_cookie
0x18001d02b  xor     rax, rsp
0x18001d02e  mov     [rbp+3B0h+var_40], rax
0x18001d035  mov     rax, [rcx]
0x18001d038  mov     [r11+20h], rdi
0x18001d03c  mov     [r11-20h], r12
0x18001d040  mov     r12, rdx
0x18001d043  mov     [r11-28h], r13
0x18001d047  lea     rdx, [rsp+4B0h+var_470]
0x18001d04c  mov     rax, [rax+68h]
0x18001d050  xor     r13d, r13d
0x18001d053  mov     [r11-38h], r15
0x18001d057  xor     r15d, r15d
0x18001d05a  mov     [rsp+4B0h+var_450], r8
0x18001d05f  mov     [rsp+4B0h+var_458], rcx
0x18001d064  mov     [rsp+4B0h+var_468], 0
0x18001d06d  mov     [rsp+4B0h+var_470], 0
0x18001d076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d07b  mov     rdi, [rsp+4B0h+var_470]
0x18001d080  lea     rsi, WPP_GLOBAL_Control
0x18001d087  mov     ebx, eax
0x18001d089  mov     [rsp+4B0h+var_28], r14
0x18001d091  test    ebx, ebx
0x18001d093  js      loc_18001D3BF
0x18001d099  test    rdi, rdi
0x18001d09c  jz      loc_18001D383
0x18001d0a2  mov     [rsp+4B0h+var_460], 0
0x18001d0ab  lea     rdx, [rsp+4B0h+var_478]
0x18001d0b0  mov     rax, [rdi]
0x18001d0b3  mov     rcx, rdi
0x18001d0b6  mov     [rsp+4B0h+var_478], 0
0x18001d0bf  xor     r14d, r14d
0x18001d0c2  mov     [rsp+4B0h+bstrString], 0
0x18001d0cb  mov     rax, [rax+148h]
0x18001d0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0d7  mov     ebx, eax
0x18001d0d9  test    eax, eax
0x18001d0db  js      loc_18001D22A
0x18001d0e1  cmp     [rsp+4B0h+var_478], r14
0x18001d0e6  jz      loc_18001D22A
0x18001d0ec  mov     rax, [rdi]
0x18001d0ef  lea     rdx, [rsp+4B0h+bstrString]
0x18001d0f4  mov     rcx, rdi
0x18001d0f7  mov     rax, [rax+138h]
0x18001d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d103  mov     ebx, eax
0x18001d105  test    eax, eax
0x18001d107  js      loc_18001D219
0x18001d10d  mov     r10, [rsp+4B0h+bstrString]
0x18001d112  test    r10, r10
0x18001d115  jz      loc_18001D219
0x18001d11b  mov     ecx, 7FFFFFFFh
0x18001d120  mov     rax, r10
0x18001d123  cmp     [rax], r14w
0x18001d127  jz      short loc_18001D13C
0x18001d129  add     rax, 2
0x18001d12d  sub     rcx, 1
0x18001d131  jnz     short loc_18001D123
0x18001d133  xor     esi, esi
0x18001d135  mov     ebx, 80070057h
0x18001d13a  jmp     short loc_18001D146
0x18001d13c  mov     esi, 7FFFFFFFh
0x18001d141  sub     rsi, rcx
0x18001d144  xor     ebx, ebx
0x18001d146  test    ebx, ebx
0x18001d148  js      loc_18001D460
0x18001d14e  mov     ecx, 1Fh
0x18001d153  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18001d15a  mov     r8d, 100h
0x18001d160  lea     r9, [rbp+3B0h+String1]
0x18001d167  test    rcx, rcx
0x18001d16a  jz      short loc_18001D189
0x18001d16c  movzx   eax, word ptr [rdx]
0x18001d16f  test    ax, ax
0x18001d172  jz      short loc_18001D189
0x18001d174  mov     [r9], ax
0x18001d178  add     rdx, 2
0x18001d17c  add     r9, 2
0x18001d180  dec     rcx
0x18001d183  sub     r8, 1
0x18001d187  jnz     short loc_18001D167
0x18001d189  test    r8, r8
0x18001d18c  lea     rcx, [r9-2]
0x18001d190  mov     ebx, 8007007Ah
0x18001d195  cmovnz  rcx, r9
0x18001d199  xor     eax, eax
0x18001d19b  test    r8, r8
0x18001d19e  cmovnz  ebx, eax
0x18001d1a1  mov     [rcx], ax
0x18001d1a4  test    ebx, ebx
0x18001d1a6  js      short loc_18001D203
0x18001d1a8  mov     ecx, 1Fh
0x18001d1ad  lea     r9, [rsp+4B0h+String2]
0x18001d1b2  mov     rdx, r10
0x18001d1b5  mov     r8d, 100h
0x18001d1bb  nop     dword ptr [rax+rax+00h]
0x18001d1c0  test    rcx, rcx
0x18001d1c3  jz      short loc_18001D1E2
0x18001d1c5  movzx   eax, word ptr [rdx]
0x18001d1c8  test    ax, ax
0x18001d1cb  jz      short loc_18001D1E2
0x18001d1cd  mov     [r9], ax
0x18001d1d1  add     rdx, 2
0x18001d1d5  add     r9, 2
0x18001d1d9  dec     rcx
0x18001d1dc  sub     r8, 1
0x18001d1e0  jnz     short loc_18001D1C0
0x18001d1e2  test    r8, r8
0x18001d1e5  lea     rcx, [r9-2]
0x18001d1e9  mov     ebx, 8007007Ah
0x18001d1ee  cmovnz  rcx, r9
0x18001d1f2  xor     eax, eax
0x18001d1f4  test    r8, r8
0x18001d1f7  cmovnz  ebx, eax
0x18001d1fa  mov     [rcx], ax
0x18001d1fd  jnz     loc_18001D2DC
0x18001d203  mov     rcx, r10; bstrString
0x18001d206  call    cs:__imp_SysFreeString
0x18001d20d  nop     dword ptr [rax+rax+00h]
0x18001d212  lea     rsi, WPP_GLOBAL_Control
0x18001d219  mov     rcx, [rsp+4B0h+var_478]; bstrString
0x18001d21e  call    cs:__imp_SysFreeString
0x18001d225  nop     dword ptr [rax+rax+00h]
0x18001d22a  test    ebx, ebx
0x18001d22c  jnz     loc_18001D467
0x18001d232  test    r14d, r14d
0x18001d235  jz      short loc_18001D2A1
0x18001d237  mov     rcx, [rsp+4B0h+var_470]; struct IXMLDOMNode *
0x18001d23c  lea     rax, [rsp+4B0h+var_468]
0x18001d241  lea     r9, [rsp+4B0h+bstrString]; int *
0x18001d246  mov     [rsp+4B0h+var_490], rax; unsigned __int16 **
0x18001d24b  lea     r8, [rsp+4B0h+var_478]; int *
0x18001d250  mov     dword ptr [rsp+4B0h+var_478], 0
0x18001d258  mov     rdx, r12; struct IXMLDOMNode *
0x18001d25b  mov     dword ptr [rsp+4B0h+bstrString], 0
0x18001d263  mov     r15d, 1
0x18001d269  call    ?HrValidateArg@@YAJPEAUIXMLDOMNode@@0PEAH1PEAPEAG@Z; HrValidateArg(IXMLDOMNode *,IXMLDOMNode *,int *,int *,ushort * *)
0x18001d26e  mov     ebx, eax
0x18001d270  test    eax, eax
0x18001d272  js      loc_18001D36E
0x18001d278  cmp     dword ptr [rsp+4B0h+bstrString], 0
0x18001d27d  mov     edi, dword ptr [rsp+4B0h+var_478]
0x18001d281  jnz     loc_18001D4A6
0x18001d287  test    edi, edi
0x18001d289  jnz     short loc_18001D290
0x18001d28b  mov     r13d, r15d
0x18001d28e  jmp     short loc_18001D2A1
0x18001d290  test    r13d, r13d
0x18001d293  jnz     loc_18001D4CB
0x18001d299  test    ebx, ebx
0x18001d29b  js      loc_18001D36E
0x18001d2a1  mov     rcx, [rsp+4B0h+var_470]
0x18001d2a6  lea     rdx, [rsp+4B0h+var_460]
0x18001d2ab  mov     rax, [rcx]
0x18001d2ae  mov     rax, [rax+80h]
0x18001d2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ba  mov     rcx, [rsp+4B0h+var_470]
0x18001d2bf  mov     ebx, eax
0x18001d2c1  mov     rax, [rcx]
0x18001d2c4  mov     rax, [rax+10h]
0x18001d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2cd  mov     rdi, [rsp+4B0h+var_460]
0x18001d2d2  mov     [rsp+4B0h+var_470], rdi
0x18001d2d7  jmp     loc_18001D091
0x18001d2dc  mov     rcx, [rsp+4B0h+var_478]; lpString1
0x18001d2e1  lea     rdx, aArgument; "argument"
0x18001d2e8  call    cs:__imp_lstrcmpW
0x18001d2ef  nop     dword ptr [rax+rax+00h]
0x18001d2f4  test    eax, eax
0x18001d2f6  jnz     short loc_18001D364
0x18001d2f8  lea     rdx, [rsp+4B0h+String2]; lpString2
0x18001d2fd  lea     rcx, [rbp+3B0h+String1]; lpString1
0x18001d304  call    cs:__imp_lstrcmpW
0x18001d30b  nop     dword ptr [rax+rax+00h]
0x18001d310  test    eax, eax
0x18001d312  jnz     short loc_18001D364
0x18001d314  mov     r14d, 1
0x18001d31a  cmp     rsi, 1Fh
0x18001d31e  jbe     short loc_18001D364
0x18001d320  mov     edi, 1Fh
0x18001d325  cmp     rdi, rsi
0x18001d328  jnb     short loc_18001D364
0x18001d32a  mov     rcx, [rsp+4B0h+bstrString]
0x18001d32f  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18001d333  call    cs:__imp_IsCharAlphaNumericW
0x18001d33a  nop     dword ptr [rax+rax+00h]
0x18001d33f  test    eax, eax
0x18001d341  jz      short loc_18001D361
0x18001d343  mov     rcx, [rsp+4B0h+bstrString]
0x18001d348  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18001d34c  call    cs:__imp_IsCharAlphaW
0x18001d353  nop     dword ptr [rax+rax+00h]
0x18001d358  test    eax, eax
0x18001d35a  jnz     short loc_18001D361
0x18001d35c  inc     rdi
0x18001d35f  jmp     short loc_18001D325
0x18001d361  xor     r14d, r14d
0x18001d364  mov     r10, [rsp+4B0h+bstrString]
0x18001d369  jmp     loc_18001D203
0x18001d36e  mov     rcx, [rsp+4B0h+var_470]
0x18001d373  mov     rax, [rcx]
0x18001d376  mov     rax, [rax+10h]
0x18001d37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d37f  test    ebx, ebx
0x18001d381  js      short loc_18001D3BF
0x18001d383  test    r15d, r15d
0x18001d386  jz      loc_18001D43D
0x18001d38c  mov     rcx, [rsp+4B0h+var_458]; struct IXMLDOMNode *
0x18001d391  lea     r9, [rsp+4B0h+bstrString]; int *
0x18001d396  lea     rdx, aScpdArgumentSc; "scpd:argument/scpd:name"
0x18001d39d  mov     dword ptr [rsp+4B0h+bstrString], 0
0x18001d3a5  call    ?HrAreThereDuplicatesInChildNodeTextValues@@YAJPEAUIXMLDOMNode@@PEBGHPEAH@Z; HrAreThereDuplicatesInChildNodeTextValues(IXMLDOMNode *,ushort const *,int,int *)
0x18001d3aa  mov     ebx, eax
0x18001d3ac  test    eax, eax
0x18001d3ae  js      loc_18001D501
0x18001d3b4  cmp     dword ptr [rsp+4B0h+bstrString], 0
0x18001d3b9  jnz     loc_18001D4E6
0x18001d3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3c6  mov     rax, [rsp+4B0h+var_468]
0x18001d3cb  mov     r15, [rsp+4B0h+var_30]
0x18001d3d3  mov     r14, [rsp+4B0h+var_28]
0x18001d3db  mov     r13, [rsp+4B0h+var_20]
0x18001d3e3  mov     r12, [rsp+4B0h+var_18]
0x18001d3eb  mov     rdi, [rsp+4B0h+arg_18]
0x18001d3f3  test    rax, rax
0x18001d3f6  jnz     loc_18001D540
0x18001d3fc  test    ebx, ebx
0x18001d3fe  jnz     loc_18001D554
0x18001d404  mov     eax, ebx
0x18001d406  mov     rcx, [rbp+3B0h+var_40]
0x18001d40d  xor     rcx, rsp; StackCookie
0x18001d410  call    __security_check_cookie
0x18001d415  add     rsp, 4A0h
0x18001d41c  pop     rsi
0x18001d41d  pop     rbx
0x18001d41e  pop     rbp
0x18001d41f  retn
0x18001d421  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18001d426  xor     r8d, r8d; unsigned __int16 *
0x18001d429  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18001d42e  mov     ebx, eax
0x18001d430  test    eax, eax
0x18001d432  jns     loc_18001D287
0x18001d438  jmp     loc_18001D36E
0x18001d43d  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18001d442  xor     r8d, r8d; unsigned __int16 *
0x18001d445  lea     rdx, aArgumentlistDi; "<argumentList> did not contain any <arg"...
0x18001d44c  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18001d451  mov     ebx, eax
0x18001d453  test    eax, eax
0x18001d455  js      loc_18001D3BF
0x18001d45b  jmp     loc_18001D38C
0x18001d460  xor     esi, esi
0x18001d462  jmp     loc_18001D1A4
0x18001d467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d46e  cmp     rcx, rsi
0x18001d471  jz      loc_18001D232
0x18001d477  test    byte ptr [rcx+1Ch], 1
0x18001d47b  jz      loc_18001D232
0x18001d481  mov     rcx, [rcx+10h]
0x18001d485  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x18001d48c  mov     edx, 14h
0x18001d491  mov     dword ptr [rsp+4B0h+var_490], ebx
0x18001d495  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001d49c  call    WPP_SF_sd
0x18001d4a1  jmp     loc_18001D232
0x18001d4a6  test    edi, edi
0x18001d4a8  jz      short loc_18001D4B6
0x18001d4aa  lea     rdx, aRetvalElementF; "<retval> element found in \"in\" <argum"...
0x18001d4b1  jmp     loc_18001D421
0x18001d4b6  test    r13d, r13d
0x18001d4b9  jz      loc_18001D287
0x18001d4bf  lea     rdx, aRetvalElementF_0; "<retval> element found in \"out\" <argu"...
0x18001d4c6  jmp     loc_18001D421
0x18001d4cb  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18001d4d0  xor     r8d, r8d; unsigned __int16 *
0x18001d4d3  lea     rdx, aInArgumentFoun; "\"in\" <argument> found after one or mo"...
0x18001d4da  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18001d4df  mov     ebx, eax
0x18001d4e1  jmp     loc_18001D299
0x18001d4e6  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18001d4eb  xor     r8d, r8d; unsigned __int16 *
0x18001d4ee  lea     rdx, aArgumentlistCo; "<argumentList> contained <argument> ele"...
0x18001d4f5  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18001d4fa  mov     ebx, eax
0x18001d4fc  jmp     loc_18001D3BF
0x18001d501  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d508  cmp     rcx, rsi
0x18001d50b  jz      loc_18001D3C6
0x18001d511  test    byte ptr [rcx+1Ch], 1
0x18001d515  jz      loc_18001D3C6
0x18001d51b  mov     rcx, [rcx+10h]
0x18001d51f  lea     r9, aHrvalidateargl; "HrValidateArgList(): Failed to check fo"...
0x18001d526  mov     edx, 17h
  ... truncated ...
```
