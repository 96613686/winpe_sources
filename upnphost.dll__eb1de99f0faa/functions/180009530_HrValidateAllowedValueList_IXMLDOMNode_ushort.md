# HrValidateAllowedValueList(IXMLDOMNode *,ushort * *)

- ea: `0x180009530`
- end: `0x180009ad4`
- name: `?HrValidateAllowedValueList@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `1444`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007f30`

## callees

- `0x180009530`
- `0x18000db4c`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000985c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000985c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000986f`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000986f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800097e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800097e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000981d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009833`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000981d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009833`
- `OLEAUT32!__imp_SysFreeString` at `0x18000975e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000976d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000975e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000976d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097f7`

## string_xrefs

- `0x1800096b0`: `urn:schemas-upnp-org:service-1-`

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
0x180009530  push    rbp
0x180009532  push    rbx
0x180009533  push    rdi
0x180009534  push    r12
0x180009536  push    r13
0x180009538  push    r14
0x18000953a  lea     rbp, [rsp-388h]
0x180009542  sub     rsp, 488h
0x180009549  mov     rax, cs:__security_cookie
0x180009550  xor     rax, rsp
0x180009553  mov     [rbp+3B0h+var_40], rax
0x18000955a  mov     rax, [rcx]
0x18000955d  xor     r12d, r12d
0x180009560  mov     rbx, rdx
0x180009563  mov     [rsp+4B0h+var_450], rdx
0x180009568  lea     rdx, [rsp+4B0h+var_460]
0x18000956d  mov     [rsp+4B0h+var_458], r12
0x180009572  mov     r13d, r12d
0x180009575  mov     [rsp+4B0h+var_460], r12
0x18000957a  mov     rax, [rax+60h]
0x18000957e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009583  mov     r14d, eax
0x180009586  test    eax, eax
0x180009588  js      loc_180009A57
0x18000958e  mov     rcx, [rsp+4B0h+var_460]
0x180009593  lea     rdx, [rsp+4B0h+var_470]
0x180009598  mov     [rsp+4B0h+var_470], r12d
0x18000959d  mov     rax, [rcx]
0x1800095a0  mov     rax, [rax+40h]
0x1800095a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a9  mov     r14d, eax
0x1800095ac  test    eax, eax
0x1800095ae  js      loc_180009A09
0x1800095b4  mov     [rsp+4B0h+arg_10], rsi
0x1800095bc  mov     esi, r12d
0x1800095bf  mov     [rsp+4B0h+var_30], r15
0x1800095c7  mov     r15d, r12d
0x1800095ca  mov     [rsp+4B0h+var_46C], r12d
0x1800095cf  nop
0x1800095d0  test    r14d, r14d
0x1800095d3  js      loc_18000988B
0x1800095d9  cmp     r15d, [rsp+4B0h+var_470]
0x1800095de  jge     loc_18000988B
0x1800095e4  mov     rcx, [rsp+4B0h+var_460]
0x1800095e9  lea     r8, [rsp+4B0h+var_468]
0x1800095ee  mov     [rsp+4B0h+var_468], r12
0x1800095f3  mov     edx, r15d
0x1800095f6  mov     rax, [rcx]
0x1800095f9  mov     rax, [rax+38h]
0x1800095fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009602  mov     r14d, eax
0x180009605  test    eax, eax
0x180009607  js      loc_1800098F5
0x18000960d  mov     rdi, [rsp+4B0h+var_468]
0x180009612  lea     rdx, [rsp+4B0h+var_478]
0x180009617  mov     rcx, rdi
0x18000961a  mov     [rsp+4B0h+var_478], r12
0x18000961f  mov     [rsp+4B0h+bstrString], r12
0x180009624  mov     rax, [rdi]
0x180009627  mov     rax, [rax+148h]
0x18000962e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009633  mov     ebx, eax
0x180009635  test    eax, eax
0x180009637  js      loc_180009773
0x18000963d  cmp     [rsp+4B0h+var_478], 0
0x180009643  jz      loc_180009773
0x180009649  mov     rax, [rdi]
0x18000964c  lea     rdx, [rsp+4B0h+bstrString]
0x180009651  mov     rcx, rdi
0x180009654  mov     rax, [rax+138h]
0x18000965b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009660  mov     ebx, eax
0x180009662  test    eax, eax
0x180009664  js      loc_180009768
0x18000966a  mov     r10, [rsp+4B0h+bstrString]
0x18000966f  test    r10, r10
0x180009672  jz      loc_180009768
0x180009678  mov     ecx, 7FFFFFFFh
0x18000967d  mov     rax, r10
0x180009680  cmp     word ptr [rax], 0
0x180009684  jz      short loc_180009699
0x180009686  add     rax, 2
0x18000968a  sub     rcx, 1
0x18000968e  jnz     short loc_180009680
0x180009690  xor     esi, esi
0x180009692  mov     ebx, 80070057h
0x180009697  jmp     short loc_1800096A3
0x180009699  mov     esi, 7FFFFFFFh
0x18000969e  sub     rsi, rcx
0x1800096a1  xor     ebx, ebx
0x1800096a3  test    ebx, ebx
0x1800096a5  js      loc_180009933
0x1800096ab  mov     ecx, 1Fh
0x1800096b0  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x1800096b7  mov     r8d, 100h
0x1800096bd  lea     r9, [rbp+3B0h+String1]
0x1800096c4  test    rcx, rcx
0x1800096c7  jz      short loc_1800096E6
0x1800096c9  movzx   eax, word ptr [rdx]
0x1800096cc  test    ax, ax
0x1800096cf  jz      short loc_1800096E6
0x1800096d1  mov     [r9], ax
0x1800096d5  add     rdx, 2
0x1800096d9  add     r9, 2
0x1800096dd  dec     rcx
0x1800096e0  sub     r8, 1
0x1800096e4  jnz     short loc_1800096C4
0x1800096e6  test    r8, r8
0x1800096e9  lea     rcx, [r9-2]
0x1800096ed  mov     ebx, 8007007Ah
0x1800096f2  cmovnz  rcx, r9
0x1800096f6  xor     eax, eax
0x1800096f8  test    r8, r8
0x1800096fb  cmovnz  ebx, eax
0x1800096fe  mov     [rcx], ax
0x180009701  test    ebx, ebx
0x180009703  js      short loc_18000975B
0x180009705  mov     ecx, 1Fh
0x18000970a  lea     r9, [rsp+4B0h+String2]
0x18000970f  mov     rdx, r10
0x180009712  mov     r8d, 100h
0x180009718  test    rcx, rcx
0x18000971b  jz      short loc_18000973A
0x18000971d  movzx   eax, word ptr [rdx]
0x180009720  test    ax, ax
0x180009723  jz      short loc_18000973A
0x180009725  mov     [r9], ax
0x180009729  add     rdx, 2
0x18000972d  add     r9, 2
0x180009731  dec     rcx
0x180009734  sub     r8, 1
0x180009738  jnz     short loc_180009718
0x18000973a  test    r8, r8
0x18000973d  lea     rcx, [r9-2]
0x180009741  mov     ebx, 8007007Ah
0x180009746  cmovnz  rcx, r9
0x18000974a  xor     eax, eax
0x18000974c  test    r8, r8
0x18000974f  cmovnz  ebx, eax
0x180009752  mov     [rcx], ax
0x180009755  jnz     loc_180009811
0x18000975b  mov     rcx, r10; bstrString
0x18000975e  call    cs:__imp_SysFreeString
0x180009764  mov     esi, [rsp+4B0h+var_46C]
0x180009768  mov     rcx, [rsp+4B0h+var_478]; bstrString
0x18000976d  call    cs:__imp_SysFreeString
0x180009773  test    ebx, ebx
0x180009775  jnz     loc_18000993A
0x18000977b  test    r12d, r12d
0x18000977e  jz      loc_18000980C
0x180009784  mov     rcx, [rsp+4B0h+var_468]
0x180009789  lea     rdx, [rsp+4B0h+var_478]
0x18000978e  xor     r12d, r12d
0x180009791  mov     esi, 1
0x180009796  mov     ebx, r12d
0x180009799  mov     [rsp+4B0h+var_46C], esi
0x18000979d  mov     [rsp+4B0h+bstrString], rbx
0x1800097a2  mov     rax, [rcx]
0x1800097a5  mov     [rsp+4B0h+var_478], r12
0x1800097aa  mov     rax, [rax+0D0h]
0x1800097b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b6  mov     r14d, eax
0x1800097b9  test    eax, eax
0x1800097bb  jns     short loc_1800097DF
0x1800097bd  test    r14d, r14d
0x1800097c0  jnz     loc_1800099A1
0x1800097c6  mov     rcx, [rsp+4B0h+var_468]
0x1800097cb  mov     rax, [rcx]
0x1800097ce  mov     rax, [rax+10h]
0x1800097d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d7  inc     r15d
0x1800097da  jmp     loc_1800095D0
0x1800097df  mov     rcx, [rsp+4B0h+var_478]; lpString
0x1800097e4  call    cs:__imp_lstrlenW
0x1800097ea  test    eax, eax
0x1800097ec  jz      loc_180009980
0x1800097f2  mov     rcx, [rsp+4B0h+var_478]; bstrString
0x1800097f7  call    cs:__imp_SysFreeString
0x1800097fd  test    rbx, rbx
0x180009800  jz      short loc_1800097BD
0x180009802  mov     r13, rbx
0x180009805  mov     [rsp+4B0h+var_458], rbx
0x18000980a  jmp     short loc_1800097BD
0x18000980c  xor     r12d, r12d
0x18000980f  jmp     short loc_1800097C6
0x180009811  mov     rcx, [rsp+4B0h+var_478]; lpString1
0x180009816  lea     rdx, aAllowedvalue; "allowedValue"
0x18000981d  call    cs:__imp_lstrcmpW
0x180009823  test    eax, eax
0x180009825  jnz     short loc_180009881
0x180009827  lea     rdx, [rsp+4B0h+String2]; lpString2
0x18000982c  lea     rcx, [rbp+3B0h+String1]; lpString1
0x180009833  call    cs:__imp_lstrcmpW
0x180009839  test    eax, eax
0x18000983b  jnz     short loc_180009881
0x18000983d  mov     r12d, 1
0x180009843  cmp     rsi, 1Fh
0x180009847  jbe     short loc_180009881
0x180009849  mov     edi, 1Fh
0x18000984e  cmp     rdi, rsi
0x180009851  jnb     short loc_180009881
0x180009853  mov     rcx, [rsp+4B0h+bstrString]
0x180009858  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18000985c  call    cs:__imp_IsCharAlphaNumericW
0x180009862  test    eax, eax
0x180009864  jz      short loc_18000987E
0x180009866  mov     rcx, [rsp+4B0h+bstrString]
0x18000986b  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18000986f  call    cs:__imp_IsCharAlphaW
0x180009875  test    eax, eax
0x180009877  jnz     short loc_18000987E
0x180009879  inc     rdi
0x18000987c  jmp     short loc_18000984E
0x18000987e  xor     r12d, r12d
0x180009881  mov     r10, [rsp+4B0h+bstrString]
0x180009886  jmp     loc_18000975B
0x18000988b  lea     rdi, WPP_GLOBAL_Control
0x180009892  mov     r15, [rsp+4B0h+var_30]
0x18000989a  test    esi, esi
0x18000989c  mov     rsi, [rsp+4B0h+arg_10]
0x1800098a4  jz      loc_1800099E8
0x1800098aa  mov     rbx, [rsp+4B0h+var_450]
0x1800098af  mov     rcx, [rsp+4B0h+var_460]
0x1800098b4  mov     rax, [rcx]
0x1800098b7  mov     rax, [rax+10h]
0x1800098bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c0  test    r13, r13
0x1800098c3  jnz     loc_180009A4F
0x1800098c9  test    r14d, r14d
0x1800098cc  jnz     loc_180009A94
0x1800098d2  mov     eax, r14d
0x1800098d5  mov     rcx, [rbp+3B0h+var_40]
0x1800098dc  xor     rcx, rsp; StackCookie
0x1800098df  call    __security_check_cookie
0x1800098e4  add     rsp, 488h
0x1800098eb  pop     r14
0x1800098ed  pop     r13
0x1800098ef  pop     r12
0x1800098f1  pop     rdi
0x1800098f2  pop     rbx
0x1800098f3  pop     rbp
0x1800098f4  retn
0x1800098f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098fc  lea     rdi, WPP_GLOBAL_Control
0x180009903  cmp     rcx, rdi
0x180009906  jz      short loc_180009892
0x180009908  test    byte ptr [rcx+1Ch], 1
0x18000990c  jz      short loc_180009892
0x18000990e  mov     rcx, [rcx+10h]
0x180009912  lea     r9, aHrvalidateallo_2; "HrValidateAllowedValueList(): Failed to"...
0x180009919  mov     edx, 1Eh
0x18000991e  mov     [rsp+4B0h+var_490], eax
0x180009922  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x180009929  call    WPP_SF_sd
0x18000992e  jmp     loc_180009892
0x180009933  xor     esi, esi
0x180009935  jmp     loc_180009701
0x18000993a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009941  lea     rax, WPP_GLOBAL_Control
0x180009948  cmp     rcx, rax
0x18000994b  jz      loc_18000977B
0x180009951  test    byte ptr [rcx+1Ch], 1
0x180009955  jz      loc_18000977B
0x18000995b  mov     rcx, [rcx+10h]
0x18000995f  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x180009966  mov     edx, 14h
0x18000996b  mov     [rsp+4B0h+var_490], ebx
0x18000996f  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180009976  call    WPP_SF_sd
0x18000997b  jmp     loc_18000977B
0x180009980  lea     r9, [rsp+4B0h+bstrString]; unsigned __int16 **
0x180009985  xor     r8d, r8d; unsigned __int16 *
0x180009988  lea     rdx, aAllowedvalueEl; "<allowedValue> element must not be empt"...
0x18000998f  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x180009994  mov     rbx, [rsp+4B0h+bstrString]
0x180009999  mov     r14d, eax
0x18000999c  jmp     loc_1800097F2
0x1800099a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099a8  lea     rax, WPP_GLOBAL_Control
0x1800099af  cmp     rcx, rax
0x1800099b2  jz      loc_1800097C6
0x1800099b8  test    [rcx+1Ch], sil
0x1800099bc  jz      loc_1800097C6
0x1800099c2  mov     rcx, [rcx+10h]
0x1800099c6  lea     r9, aHrvalidateallo; "HrValidateAllowedValue(): Exiting"
0x1800099cd  mov     edx, 1Dh
0x1800099d2  mov     [rsp+4B0h+var_490], r14d
0x1800099d7  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x1800099de  call    WPP_SF_sd
0x1800099e3  jmp     loc_1800097C6
0x1800099e8  lea     r9, [rsp+4B0h+var_458]; unsigned __int16 **
0x1800099ed  xor     r8d, r8d; unsigned __int16 *
0x1800099f0  lea     rdx, aAllowedvalueli_1; "<allowedValueList> element was empty"
0x1800099f7  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x1800099fc  mov     r13, [rsp+4B0h+var_458]
0x180009a01  mov     r14d, eax
0x180009a04  jmp     loc_1800098AA
0x180009a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a10  lea     rdi, WPP_GLOBAL_Control
0x180009a17  cmp     rcx, rdi
  ... truncated ...
```
