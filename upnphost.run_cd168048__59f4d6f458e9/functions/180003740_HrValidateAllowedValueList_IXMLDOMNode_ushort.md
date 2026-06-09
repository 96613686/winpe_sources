# HrValidateAllowedValueList(IXMLDOMNode *,ushort * *)

- ea: `0x180003740`
- end: `0x180003d15`
- name: `?HrValidateAllowedValueList@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `1493`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800020f0`

## callees

- `0x180003740`
- `0x1800200f4`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180003a90`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180003a90`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180003aa9`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180003aa9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003a00`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003a00`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003a45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003a61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003a45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003a61`
- `OLEAUT32!__imp_SysFreeString` at `0x18000396e`
- `OLEAUT32!__imp_SysFreeString` at `0x180003983`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a19`
- `OLEAUT32!__imp_SysFreeString` at `0x18000396e`
- `OLEAUT32!__imp_SysFreeString` at `0x180003983`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a19`

## string_xrefs

- `0x1800038c0`: `urn:schemas-upnp-org:service-1-`

## pseudocode

```c
__int64 __fastcall HrValidateAllowedValueList(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v3; // r12d
  unsigned __int16 **v4; // rbx
  unsigned __int16 *v5; // r13
  int v6; // eax
  int v7; // r14d
  int v8; // eax
  int v9; // ecx
  int v10; // esi
  unsigned int v11; // r15d
  int v12; // eax
  __int64 *v13; // rdi
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
  unsigned __int16 *v29; // rbx
  __int64 v30; // rax
  int v31; // ecx
  unsigned __int64 i; // rdi
  int v34; // eax
  int v35; // eax
  STRSAFE_PCNZWCH v36; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+44h] [rbp-BCh]
  __int64 *v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v43; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v44; // [rsp+60h] [rbp-A0h]
  WCHAR String2[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String1[256]; // [rsp+270h] [rbp+170h] BYREF

  lpVtbl = a1->lpVtbl;
  v3 = 0;
  v4 = a2;
  v44 = a2;
  v43 = 0;
  v5 = 0;
  v42 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))lpVtbl->get_childNodes)(a1, &v42);
  v7 = v6;
  if ( v6 < 0 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return (unsigned int)v7;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_78;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateAllowedValueList(): Failed to get node children",
      v6);
LABEL_77:
    v36 = WPP_GLOBAL_Control;
LABEL_78:
    if ( v36 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v36[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)v36 + 2),
        33,
        (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
        (unsigned int)"HrValidateAllowedValueList(): Exiting",
        v7);
    return (unsigned int)v7;
  }
  v39 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 64LL))(v42, &v39);
  v7 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
        (unsigned int)"HrValidateAllowedValueList(): Failed to get list length",
        v8);
  }
  else
  {
    v10 = 0;
    v11 = 0;
    v40 = 0;
    while ( v7 >= 0 && (int)v11 < v39 )
    {
      v41 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v42 + 56LL))(v42, v11, &v41);
      v7 = v12;
      if ( v12 < 0 )
      {
        v9 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
            (unsigned int)"HrValidateAllowedValueList(): Failed to get list item",
            v12);
        break;
      }
      v13 = v41;
      v38 = 0;
      bstrString = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v41 + 328))(v41, &v38);
      if ( v14 >= 0 && v38 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v13 + 312))(v13, &bstrString);
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
                goto LABEL_16;
              }
            }
            v18 = 0x7FFFFFFF - v16;
            v14 = 0;
LABEL_16:
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
                if ( !lstrcmpW(v38, L"allowedValue") && !lstrcmpW(String1, String2) )
                {
                  v3 = 1;
                  if ( v18 > 0x1F )
                  {
                    for ( i = 31; i < v18; ++i )
                    {
                      if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                      {
                        v3 = 0;
                        break;
                      }
                    }
                  }
                }
                v15 = bstrString;
              }
            }
            SysFreeString(v15);
            v10 = v40;
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
      if ( v3 )
      {
        v3 = 0;
        v10 = 1;
        v29 = 0;
        v40 = 1;
        bstrString = 0;
        v30 = *v41;
        v38 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v30 + 208))(v41, &v38);
        if ( v7 >= 0 )
        {
          if ( !lstrlenW(v38) )
          {
            v34 = HrAllocErrorStringAndReturnHr(v31, L"<allowedValue> element must not be empty", 0, &bstrString);
            v29 = bstrString;
            v7 = v34;
          }
          SysFreeString(v38);
          if ( v29 )
          {
            v5 = v29;
            v43 = v29;
          }
        }
        if ( v7 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
            (unsigned int)"HrValidateAllowedValue(): Exiting",
            v7);
      }
      else
      {
        v3 = 0;
      }
      (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
      ++v11;
    }
    if ( !v10 )
    {
      v35 = HrAllocErrorStringAndReturnHr(v9, L"<allowedValueList> element was empty", 0, &v43);
      v5 = v43;
      v7 = v35;
    }
    v4 = v44;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v5 )
    *v4 = v5;
  if ( v7 )
    goto LABEL_77;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003740  push    rbp
0x180003742  push    rbx
0x180003743  push    rdi
0x180003744  push    r12
0x180003746  push    r13
0x180003748  push    r14
0x18000374a  lea     rbp, [rsp-388h]
0x180003752  sub     rsp, 488h
0x180003759  mov     rax, cs:__security_cookie
0x180003760  xor     rax, rsp
0x180003763  mov     [rbp+3B0h+var_40], rax
0x18000376a  mov     rax, [rcx]
0x18000376d  xor     r12d, r12d
0x180003770  mov     rbx, rdx
0x180003773  mov     [rsp+4B0h+var_450], rdx
0x180003778  lea     rdx, [rsp+4B0h+var_460]
0x18000377d  mov     [rsp+4B0h+var_458], r12
0x180003782  mov     r13d, r12d
0x180003785  mov     [rsp+4B0h+var_460], r12
0x18000378a  mov     rax, [rax+60h]
0x18000378e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003793  mov     r14d, eax
0x180003796  test    eax, eax
0x180003798  js      loc_180003C98
0x18000379e  mov     rcx, [rsp+4B0h+var_460]
0x1800037a3  lea     rdx, [rsp+4B0h+var_470]
0x1800037a8  mov     [rsp+4B0h+var_470], r12d
0x1800037ad  mov     rax, [rcx]
0x1800037b0  mov     rax, [rax+40h]
0x1800037b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b9  mov     r14d, eax
0x1800037bc  test    eax, eax
0x1800037be  js      loc_180003C4A
0x1800037c4  mov     [rsp+4B0h+arg_10], rsi
0x1800037cc  mov     esi, r12d
0x1800037cf  mov     [rsp+4B0h+var_30], r15
0x1800037d7  mov     r15d, r12d
0x1800037da  mov     [rsp+4B0h+var_46C], r12d
0x1800037df  nop
0x1800037e0  test    r14d, r14d
0x1800037e3  js      loc_180003ACB
0x1800037e9  cmp     r15d, [rsp+4B0h+var_470]
0x1800037ee  jge     loc_180003ACB
0x1800037f4  mov     rcx, [rsp+4B0h+var_460]
0x1800037f9  lea     r8, [rsp+4B0h+var_468]
0x1800037fe  mov     [rsp+4B0h+var_468], r12
0x180003803  mov     edx, r15d
0x180003806  mov     rax, [rcx]
0x180003809  mov     rax, [rax+38h]
0x18000380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003812  mov     r14d, eax
0x180003815  test    eax, eax
0x180003817  js      loc_180003B36
0x18000381d  mov     rdi, [rsp+4B0h+var_468]
0x180003822  lea     rdx, [rsp+4B0h+var_478]
0x180003827  mov     rcx, rdi
0x18000382a  mov     [rsp+4B0h+var_478], r12
0x18000382f  mov     [rsp+4B0h+bstrString], r12
0x180003834  mov     rax, [rdi]
0x180003837  mov     rax, [rax+148h]
0x18000383e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003843  mov     ebx, eax
0x180003845  test    eax, eax
0x180003847  js      loc_18000398F
0x18000384d  cmp     [rsp+4B0h+var_478], 0
0x180003853  jz      loc_18000398F
0x180003859  mov     rax, [rdi]
0x18000385c  lea     rdx, [rsp+4B0h+bstrString]
0x180003861  mov     rcx, rdi
0x180003864  mov     rax, [rax+138h]
0x18000386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003870  mov     ebx, eax
0x180003872  test    eax, eax
0x180003874  js      loc_18000397E
0x18000387a  mov     r10, [rsp+4B0h+bstrString]
0x18000387f  test    r10, r10
0x180003882  jz      loc_18000397E
0x180003888  mov     ecx, 7FFFFFFFh
0x18000388d  mov     rax, r10
0x180003890  cmp     word ptr [rax], 0
0x180003894  jz      short loc_1800038A9
0x180003896  add     rax, 2
0x18000389a  sub     rcx, 1
0x18000389e  jnz     short loc_180003890
0x1800038a0  xor     esi, esi
0x1800038a2  mov     ebx, 80070057h
0x1800038a7  jmp     short loc_1800038B3
0x1800038a9  mov     esi, 7FFFFFFFh
0x1800038ae  sub     rsi, rcx
0x1800038b1  xor     ebx, ebx
0x1800038b3  test    ebx, ebx
0x1800038b5  js      loc_180003B74
0x1800038bb  mov     ecx, 1Fh
0x1800038c0  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x1800038c7  mov     r8d, 100h
0x1800038cd  lea     r9, [rbp+3B0h+String1]
0x1800038d4  test    rcx, rcx
0x1800038d7  jz      short loc_1800038F6
0x1800038d9  movzx   eax, word ptr [rdx]
0x1800038dc  test    ax, ax
0x1800038df  jz      short loc_1800038F6
0x1800038e1  mov     [r9], ax
0x1800038e5  add     rdx, 2
0x1800038e9  add     r9, 2
0x1800038ed  dec     rcx
0x1800038f0  sub     r8, 1
0x1800038f4  jnz     short loc_1800038D4
0x1800038f6  test    r8, r8
0x1800038f9  lea     rcx, [r9-2]
0x1800038fd  mov     ebx, 8007007Ah
0x180003902  cmovnz  rcx, r9
0x180003906  xor     eax, eax
0x180003908  test    r8, r8
0x18000390b  cmovnz  ebx, eax
0x18000390e  mov     [rcx], ax
0x180003911  test    ebx, ebx
0x180003913  js      short loc_18000396B
0x180003915  mov     ecx, 1Fh
0x18000391a  lea     r9, [rsp+4B0h+String2]
0x18000391f  mov     rdx, r10
0x180003922  mov     r8d, 100h
0x180003928  test    rcx, rcx
0x18000392b  jz      short loc_18000394A
0x18000392d  movzx   eax, word ptr [rdx]
0x180003930  test    ax, ax
0x180003933  jz      short loc_18000394A
0x180003935  mov     [r9], ax
0x180003939  add     rdx, 2
0x18000393d  add     r9, 2
0x180003941  dec     rcx
0x180003944  sub     r8, 1
0x180003948  jnz     short loc_180003928
0x18000394a  test    r8, r8
0x18000394d  lea     rcx, [r9-2]
0x180003951  mov     ebx, 8007007Ah
0x180003956  cmovnz  rcx, r9
0x18000395a  xor     eax, eax
0x18000395c  test    r8, r8
0x18000395f  cmovnz  ebx, eax
0x180003962  mov     [rcx], ax
0x180003965  jnz     loc_180003A39
0x18000396b  mov     rcx, r10; bstrString
0x18000396e  call    cs:__imp_SysFreeString
0x180003975  nop     dword ptr [rax+rax+00h]
0x18000397a  mov     esi, [rsp+4B0h+var_46C]
0x18000397e  mov     rcx, [rsp+4B0h+var_478]; bstrString
0x180003983  call    cs:__imp_SysFreeString
0x18000398a  nop     dword ptr [rax+rax+00h]
0x18000398f  test    ebx, ebx
0x180003991  jnz     loc_180003B7B
0x180003997  test    r12d, r12d
0x18000399a  jz      loc_180003A34
0x1800039a0  mov     rcx, [rsp+4B0h+var_468]
0x1800039a5  lea     rdx, [rsp+4B0h+var_478]
0x1800039aa  xor     r12d, r12d
0x1800039ad  mov     esi, 1
0x1800039b2  mov     ebx, r12d
0x1800039b5  mov     [rsp+4B0h+var_46C], esi
0x1800039b9  mov     [rsp+4B0h+bstrString], rbx
0x1800039be  mov     rax, [rcx]
0x1800039c1  mov     [rsp+4B0h+var_478], r12
0x1800039c6  mov     rax, [rax+0D0h]
0x1800039cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d2  mov     r14d, eax
0x1800039d5  test    eax, eax
0x1800039d7  jns     short loc_1800039FB
0x1800039d9  test    r14d, r14d
0x1800039dc  jnz     loc_180003BE2
0x1800039e2  mov     rcx, [rsp+4B0h+var_468]
0x1800039e7  mov     rax, [rcx]
0x1800039ea  mov     rax, [rax+10h]
0x1800039ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f3  inc     r15d
0x1800039f6  jmp     loc_1800037E0
0x1800039fb  mov     rcx, [rsp+4B0h+var_478]; lpString
0x180003a00  call    cs:__imp_lstrlenW
0x180003a07  nop     dword ptr [rax+rax+00h]
0x180003a0c  test    eax, eax
0x180003a0e  jz      loc_180003BC1
0x180003a14  mov     rcx, [rsp+4B0h+var_478]; bstrString
0x180003a19  call    cs:__imp_SysFreeString
0x180003a20  nop     dword ptr [rax+rax+00h]
0x180003a25  test    rbx, rbx
0x180003a28  jz      short loc_1800039D9
0x180003a2a  mov     r13, rbx
0x180003a2d  mov     [rsp+4B0h+var_458], rbx
0x180003a32  jmp     short loc_1800039D9
0x180003a34  xor     r12d, r12d
0x180003a37  jmp     short loc_1800039E2
0x180003a39  mov     rcx, [rsp+4B0h+var_478]; lpString1
0x180003a3e  lea     rdx, aAllowedvalue; "allowedValue"
0x180003a45  call    cs:__imp_lstrcmpW
0x180003a4c  nop     dword ptr [rax+rax+00h]
0x180003a51  test    eax, eax
0x180003a53  jnz     short loc_180003AC1
0x180003a55  lea     rdx, [rsp+4B0h+String2]; lpString2
0x180003a5a  lea     rcx, [rbp+3B0h+String1]; lpString1
0x180003a61  call    cs:__imp_lstrcmpW
0x180003a68  nop     dword ptr [rax+rax+00h]
0x180003a6d  test    eax, eax
0x180003a6f  jnz     short loc_180003AC1
0x180003a71  mov     r12d, 1
0x180003a77  cmp     rsi, 1Fh
0x180003a7b  jbe     short loc_180003AC1
0x180003a7d  mov     edi, 1Fh
0x180003a82  cmp     rdi, rsi
0x180003a85  jnb     short loc_180003AC1
0x180003a87  mov     rcx, [rsp+4B0h+bstrString]
0x180003a8c  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x180003a90  call    cs:__imp_IsCharAlphaNumericW
0x180003a97  nop     dword ptr [rax+rax+00h]
0x180003a9c  test    eax, eax
0x180003a9e  jz      short loc_180003ABE
0x180003aa0  mov     rcx, [rsp+4B0h+bstrString]
0x180003aa5  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x180003aa9  call    cs:__imp_IsCharAlphaW
0x180003ab0  nop     dword ptr [rax+rax+00h]
0x180003ab5  test    eax, eax
0x180003ab7  jnz     short loc_180003ABE
0x180003ab9  inc     rdi
0x180003abc  jmp     short loc_180003A82
0x180003abe  xor     r12d, r12d
0x180003ac1  mov     r10, [rsp+4B0h+bstrString]
0x180003ac6  jmp     loc_18000396B
0x180003acb  lea     rdi, WPP_GLOBAL_Control
0x180003ad2  mov     r15, [rsp+4B0h+var_30]
0x180003ada  test    esi, esi
0x180003adc  mov     rsi, [rsp+4B0h+arg_10]
0x180003ae4  jz      loc_180003C29
0x180003aea  mov     rbx, [rsp+4B0h+var_450]
0x180003aef  mov     rcx, [rsp+4B0h+var_460]
0x180003af4  mov     rax, [rcx]
0x180003af7  mov     rax, [rax+10h]
0x180003afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b00  test    r13, r13
0x180003b03  jnz     loc_180003C90
0x180003b09  test    r14d, r14d
0x180003b0c  jnz     loc_180003CD5
0x180003b12  mov     eax, r14d
0x180003b15  mov     rcx, [rbp+3B0h+var_40]
0x180003b1c  xor     rcx, rsp; StackCookie
0x180003b1f  call    __security_check_cookie
0x180003b24  add     rsp, 488h
0x180003b2b  pop     r14
0x180003b2d  pop     r13
0x180003b2f  pop     r12
0x180003b31  pop     rdi
0x180003b32  pop     rbx
0x180003b33  pop     rbp
0x180003b34  retn
0x180003b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b3d  lea     rdi, WPP_GLOBAL_Control
0x180003b44  cmp     rcx, rdi
0x180003b47  jz      short loc_180003AD2
0x180003b49  test    byte ptr [rcx+1Ch], 1
0x180003b4d  jz      short loc_180003AD2
0x180003b4f  mov     rcx, [rcx+10h]
0x180003b53  lea     r9, aHrvalidateallo_2; "HrValidateAllowedValueList(): Failed to"...
0x180003b5a  mov     edx, 1Eh
0x180003b5f  mov     [rsp+4B0h+var_490], eax
0x180003b63  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x180003b6a  call    WPP_SF_sd
0x180003b6f  jmp     loc_180003AD2
0x180003b74  xor     esi, esi
0x180003b76  jmp     loc_180003911
0x180003b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b82  lea     rax, WPP_GLOBAL_Control
0x180003b89  cmp     rcx, rax
0x180003b8c  jz      loc_180003997
0x180003b92  test    byte ptr [rcx+1Ch], 1
0x180003b96  jz      loc_180003997
0x180003b9c  mov     rcx, [rcx+10h]
0x180003ba0  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x180003ba7  mov     edx, 14h
0x180003bac  mov     [rsp+4B0h+var_490], ebx
0x180003bb0  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180003bb7  call    WPP_SF_sd
0x180003bbc  jmp     loc_180003997
0x180003bc1  lea     r9, [rsp+4B0h+bstrString]; unsigned __int16 **
0x180003bc6  xor     r8d, r8d; unsigned __int16 *
0x180003bc9  lea     rdx, aAllowedvalueEl; "<allowedValue> element must not be empt"...
0x180003bd0  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x180003bd5  mov     rbx, [rsp+4B0h+bstrString]
0x180003bda  mov     r14d, eax
0x180003bdd  jmp     loc_180003A14
0x180003be2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003be9  lea     rax, WPP_GLOBAL_Control
0x180003bf0  cmp     rcx, rax
0x180003bf3  jz      loc_1800039E2
0x180003bf9  test    [rcx+1Ch], sil
0x180003bfd  jz      loc_1800039E2
0x180003c03  mov     rcx, [rcx+10h]
0x180003c07  lea     r9, aHrvalidateallo; "HrValidateAllowedValue(): Exiting"
0x180003c0e  mov     edx, 1Dh
0x180003c13  mov     [rsp+4B0h+var_490], r14d
0x180003c18  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x180003c1f  call    WPP_SF_sd
0x180003c24  jmp     loc_1800039E2
0x180003c29  lea     r9, [rsp+4B0h+var_458]; unsigned __int16 **
0x180003c2e  xor     r8d, r8d; unsigned __int16 *
  ... truncated ...
```
