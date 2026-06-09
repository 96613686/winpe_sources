# HrValidateArgList(IXMLDOMNode *,IXMLDOMNode *,ushort * *)

- ea: `0x18000ab30`
- end: `0x18000b087`
- name: `?HrValidateArgList@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z`
- size: `1367`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a370`

## callees

- `0x180009ae0`
- `0x18000ab30`
- `0x18000b090`
- `0x18000db4c`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000ae3b`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000ae3b`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000ae4e`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000ae4e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000adfc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000ae12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000adfc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000ae12`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad26`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad38`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad26`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad38`

## string_xrefs

- `0x18000ac73`: `urn:schemas-upnp-org:service-1-`

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
0x18000ab30  mov     r11, rsp
0x18000ab33  push    rbp
0x18000ab34  push    rbx
0x18000ab35  push    rsi
0x18000ab36  lea     rbp, [r11-3B8h]
0x18000ab3d  sub     rsp, 4A0h
0x18000ab44  mov     rax, cs:__security_cookie
0x18000ab4b  xor     rax, rsp
0x18000ab4e  mov     [rbp+3B0h+var_40], rax
0x18000ab55  mov     rax, [rcx]
0x18000ab58  mov     [r11+20h], rdi
0x18000ab5c  mov     [r11-20h], r12
0x18000ab60  mov     r12, rdx
0x18000ab63  mov     [r11-28h], r13
0x18000ab67  lea     rdx, [rsp+4B0h+var_470]
0x18000ab6c  mov     rax, [rax+68h]
0x18000ab70  xor     r13d, r13d
0x18000ab73  mov     [r11-38h], r15
0x18000ab77  xor     r15d, r15d
0x18000ab7a  mov     [rsp+4B0h+var_450], r8
0x18000ab7f  mov     [rsp+4B0h+var_458], rcx
0x18000ab84  mov     [rsp+4B0h+var_468], 0
0x18000ab8d  mov     [rsp+4B0h+var_470], 0
0x18000ab96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab9b  mov     rdi, [rsp+4B0h+var_470]
0x18000aba0  lea     rsi, WPP_GLOBAL_Control
0x18000aba7  mov     ebx, eax
0x18000aba9  mov     [rsp+4B0h+var_28], r14
0x18000abb1  test    ebx, ebx
0x18000abb3  js      loc_18000AEBB
0x18000abb9  test    rdi, rdi
0x18000abbc  jz      loc_18000AE7F
0x18000abc2  mov     [rsp+4B0h+var_460], 0
0x18000abcb  lea     rdx, [rsp+4B0h+var_478]
0x18000abd0  mov     rax, [rdi]
0x18000abd3  mov     rcx, rdi
0x18000abd6  mov     [rsp+4B0h+var_478], 0
0x18000abdf  xor     r14d, r14d
0x18000abe2  mov     [rsp+4B0h+bstrString], 0
0x18000abeb  mov     rax, [rax+148h]
0x18000abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abf7  mov     ebx, eax
0x18000abf9  test    eax, eax
0x18000abfb  js      loc_18000AD3E
0x18000ac01  cmp     [rsp+4B0h+var_478], r14
0x18000ac06  jz      loc_18000AD3E
0x18000ac0c  mov     rax, [rdi]
0x18000ac0f  lea     rdx, [rsp+4B0h+bstrString]
0x18000ac14  mov     rcx, rdi
0x18000ac17  mov     rax, [rax+138h]
0x18000ac1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac23  mov     ebx, eax
0x18000ac25  test    eax, eax
0x18000ac27  js      loc_18000AD33
0x18000ac2d  mov     r10, [rsp+4B0h+bstrString]
0x18000ac32  test    r10, r10
0x18000ac35  jz      loc_18000AD33
0x18000ac3b  mov     ecx, 7FFFFFFFh
0x18000ac40  mov     rax, r10
0x18000ac43  cmp     [rax], r14w
0x18000ac47  jz      short loc_18000AC5C
0x18000ac49  add     rax, 2
0x18000ac4d  sub     rcx, 1
0x18000ac51  jnz     short loc_18000AC43
0x18000ac53  xor     esi, esi
0x18000ac55  mov     ebx, 80070057h
0x18000ac5a  jmp     short loc_18000AC66
0x18000ac5c  mov     esi, 7FFFFFFFh
0x18000ac61  sub     rsi, rcx
0x18000ac64  xor     ebx, ebx
0x18000ac66  test    ebx, ebx
0x18000ac68  js      loc_18000AF5B
0x18000ac6e  mov     ecx, 1Fh
0x18000ac73  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18000ac7a  mov     r8d, 100h
0x18000ac80  lea     r9, [rbp+3B0h+String1]
0x18000ac87  test    rcx, rcx
0x18000ac8a  jz      short loc_18000ACA9
0x18000ac8c  movzx   eax, word ptr [rdx]
0x18000ac8f  test    ax, ax
0x18000ac92  jz      short loc_18000ACA9
0x18000ac94  mov     [r9], ax
0x18000ac98  add     rdx, 2
0x18000ac9c  add     r9, 2
0x18000aca0  dec     rcx
0x18000aca3  sub     r8, 1
0x18000aca7  jnz     short loc_18000AC87
0x18000aca9  test    r8, r8
0x18000acac  lea     rcx, [r9-2]
0x18000acb0  mov     ebx, 8007007Ah
0x18000acb5  cmovnz  rcx, r9
0x18000acb9  xor     eax, eax
0x18000acbb  test    r8, r8
0x18000acbe  cmovnz  ebx, eax
0x18000acc1  mov     [rcx], ax
0x18000acc4  test    ebx, ebx
0x18000acc6  js      short loc_18000AD23
0x18000acc8  mov     ecx, 1Fh
0x18000accd  lea     r9, [rsp+4B0h+String2]
0x18000acd2  mov     rdx, r10
0x18000acd5  mov     r8d, 100h
0x18000acdb  nop     dword ptr [rax+rax+00h]
0x18000ace0  test    rcx, rcx
0x18000ace3  jz      short loc_18000AD02
0x18000ace5  movzx   eax, word ptr [rdx]
0x18000ace8  test    ax, ax
0x18000aceb  jz      short loc_18000AD02
0x18000aced  mov     [r9], ax
0x18000acf1  add     rdx, 2
0x18000acf5  add     r9, 2
0x18000acf9  dec     rcx
0x18000acfc  sub     r8, 1
0x18000ad00  jnz     short loc_18000ACE0
0x18000ad02  test    r8, r8
0x18000ad05  lea     rcx, [r9-2]
0x18000ad09  mov     ebx, 8007007Ah
0x18000ad0e  cmovnz  rcx, r9
0x18000ad12  xor     eax, eax
0x18000ad14  test    r8, r8
0x18000ad17  cmovnz  ebx, eax
0x18000ad1a  mov     [rcx], ax
0x18000ad1d  jnz     loc_18000ADF0
0x18000ad23  mov     rcx, r10; bstrString
0x18000ad26  call    cs:__imp_SysFreeString
0x18000ad2c  lea     rsi, WPP_GLOBAL_Control
0x18000ad33  mov     rcx, [rsp+4B0h+var_478]; bstrString
0x18000ad38  call    cs:__imp_SysFreeString
0x18000ad3e  test    ebx, ebx
0x18000ad40  jnz     loc_18000AF62
0x18000ad46  test    r14d, r14d
0x18000ad49  jz      short loc_18000ADB5
0x18000ad4b  mov     rcx, [rsp+4B0h+var_470]; struct IXMLDOMNode *
0x18000ad50  lea     rax, [rsp+4B0h+var_468]
0x18000ad55  lea     r9, [rsp+4B0h+bstrString]; int *
0x18000ad5a  mov     [rsp+4B0h+var_490], rax; unsigned __int16 **
0x18000ad5f  lea     r8, [rsp+4B0h+var_478]; int *
0x18000ad64  mov     dword ptr [rsp+4B0h+var_478], 0
0x18000ad6c  mov     rdx, r12; struct IXMLDOMNode *
0x18000ad6f  mov     dword ptr [rsp+4B0h+bstrString], 0
0x18000ad77  mov     r15d, 1
0x18000ad7d  call    ?HrValidateArg@@YAJPEAUIXMLDOMNode@@0PEAH1PEAPEAG@Z; HrValidateArg(IXMLDOMNode *,IXMLDOMNode *,int *,int *,ushort * *)
0x18000ad82  mov     ebx, eax
0x18000ad84  test    eax, eax
0x18000ad86  js      loc_18000AE6A
0x18000ad8c  cmp     dword ptr [rsp+4B0h+bstrString], 0
0x18000ad91  mov     edi, dword ptr [rsp+4B0h+var_478]
0x18000ad95  jnz     loc_18000AFA1
0x18000ad9b  test    edi, edi
0x18000ad9d  jnz     short loc_18000ADA4
0x18000ad9f  mov     r13d, r15d
0x18000ada2  jmp     short loc_18000ADB5
0x18000ada4  test    r13d, r13d
0x18000ada7  jnz     loc_18000AFC6
0x18000adad  test    ebx, ebx
0x18000adaf  js      loc_18000AE6A
0x18000adb5  mov     rcx, [rsp+4B0h+var_470]
0x18000adba  lea     rdx, [rsp+4B0h+var_460]
0x18000adbf  mov     rax, [rcx]
0x18000adc2  mov     rax, [rax+80h]
0x18000adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adce  mov     rcx, [rsp+4B0h+var_470]
0x18000add3  mov     ebx, eax
0x18000add5  mov     rax, [rcx]
0x18000add8  mov     rax, [rax+10h]
0x18000addc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ade1  mov     rdi, [rsp+4B0h+var_460]
0x18000ade6  mov     [rsp+4B0h+var_470], rdi
0x18000adeb  jmp     loc_18000ABB1
0x18000adf0  mov     rcx, [rsp+4B0h+var_478]; lpString1
0x18000adf5  lea     rdx, aArgument; "argument"
0x18000adfc  call    cs:__imp_lstrcmpW
0x18000ae02  test    eax, eax
0x18000ae04  jnz     short loc_18000AE60
0x18000ae06  lea     rdx, [rsp+4B0h+String2]; lpString2
0x18000ae0b  lea     rcx, [rbp+3B0h+String1]; lpString1
0x18000ae12  call    cs:__imp_lstrcmpW
0x18000ae18  test    eax, eax
0x18000ae1a  jnz     short loc_18000AE60
0x18000ae1c  mov     r14d, 1
0x18000ae22  cmp     rsi, 1Fh
0x18000ae26  jbe     short loc_18000AE60
0x18000ae28  mov     edi, 1Fh
0x18000ae2d  cmp     rdi, rsi
0x18000ae30  jnb     short loc_18000AE60
0x18000ae32  mov     rcx, [rsp+4B0h+bstrString]
0x18000ae37  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18000ae3b  call    cs:__imp_IsCharAlphaNumericW
0x18000ae41  test    eax, eax
0x18000ae43  jz      short loc_18000AE5D
0x18000ae45  mov     rcx, [rsp+4B0h+bstrString]
0x18000ae4a  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18000ae4e  call    cs:__imp_IsCharAlphaW
0x18000ae54  test    eax, eax
0x18000ae56  jnz     short loc_18000AE5D
0x18000ae58  inc     rdi
0x18000ae5b  jmp     short loc_18000AE2D
0x18000ae5d  xor     r14d, r14d
0x18000ae60  mov     r10, [rsp+4B0h+bstrString]
0x18000ae65  jmp     loc_18000AD23
0x18000ae6a  mov     rcx, [rsp+4B0h+var_470]
0x18000ae6f  mov     rax, [rcx]
0x18000ae72  mov     rax, [rax+10h]
0x18000ae76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7b  test    ebx, ebx
0x18000ae7d  js      short loc_18000AEBB
0x18000ae7f  test    r15d, r15d
0x18000ae82  jz      loc_18000AF38
0x18000ae88  mov     rcx, [rsp+4B0h+var_458]; struct IXMLDOMNode *
0x18000ae8d  lea     r9, [rsp+4B0h+bstrString]; int *
0x18000ae92  lea     rdx, aScpdArgumentSc; "scpd:argument/scpd:name"
0x18000ae99  mov     dword ptr [rsp+4B0h+bstrString], 0
0x18000aea1  call    ?HrAreThereDuplicatesInChildNodeTextValues@@YAJPEAUIXMLDOMNode@@PEBGHPEAH@Z; HrAreThereDuplicatesInChildNodeTextValues(IXMLDOMNode *,ushort const *,int,int *)
0x18000aea6  mov     ebx, eax
0x18000aea8  test    eax, eax
0x18000aeaa  js      loc_18000AFFC
0x18000aeb0  cmp     dword ptr [rsp+4B0h+bstrString], 0
0x18000aeb5  jnz     loc_18000AFE1
0x18000aebb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aec2  mov     rax, [rsp+4B0h+var_468]
0x18000aec7  mov     r15, [rsp+4B0h+var_30]
0x18000aecf  mov     r14, [rsp+4B0h+var_28]
0x18000aed7  mov     r13, [rsp+4B0h+var_20]
0x18000aedf  mov     r12, [rsp+4B0h+var_18]
0x18000aee7  mov     rdi, [rsp+4B0h+arg_18]
0x18000aeef  test    rax, rax
0x18000aef2  jnz     loc_18000B03B
0x18000aef8  test    ebx, ebx
0x18000aefa  jnz     loc_18000B04F
0x18000af00  mov     eax, ebx
0x18000af02  mov     rcx, [rbp+3B0h+var_40]
0x18000af09  xor     rcx, rsp; StackCookie
0x18000af0c  call    __security_check_cookie
0x18000af11  add     rsp, 4A0h
0x18000af18  pop     rsi
0x18000af19  pop     rbx
0x18000af1a  pop     rbp
0x18000af1b  retn
0x18000af1c  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18000af21  xor     r8d, r8d; unsigned __int16 *
0x18000af24  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000af29  mov     ebx, eax
0x18000af2b  test    eax, eax
0x18000af2d  jns     loc_18000AD9B
0x18000af33  jmp     loc_18000AE6A
0x18000af38  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18000af3d  xor     r8d, r8d; unsigned __int16 *
0x18000af40  lea     rdx, aArgumentlistDi; "<argumentList> did not contain any <arg"...
0x18000af47  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000af4c  mov     ebx, eax
0x18000af4e  test    eax, eax
0x18000af50  js      loc_18000AEBB
0x18000af56  jmp     loc_18000AE88
0x18000af5b  xor     esi, esi
0x18000af5d  jmp     loc_18000ACC4
0x18000af62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af69  cmp     rcx, rsi
0x18000af6c  jz      loc_18000AD46
0x18000af72  test    byte ptr [rcx+1Ch], 1
0x18000af76  jz      loc_18000AD46
0x18000af7c  mov     rcx, [rcx+10h]
0x18000af80  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x18000af87  mov     edx, 14h
0x18000af8c  mov     dword ptr [rsp+4B0h+var_490], ebx
0x18000af90  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000af97  call    WPP_SF_sd
0x18000af9c  jmp     loc_18000AD46
0x18000afa1  test    edi, edi
0x18000afa3  jz      short loc_18000AFB1
0x18000afa5  lea     rdx, aRetvalElementF; "<retval> element found in \"in\" <argum"...
0x18000afac  jmp     loc_18000AF1C
0x18000afb1  test    r13d, r13d
0x18000afb4  jz      loc_18000AD9B
0x18000afba  lea     rdx, aRetvalElementF_0; "<retval> element found in \"out\" <argu"...
0x18000afc1  jmp     loc_18000AF1C
0x18000afc6  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18000afcb  xor     r8d, r8d; unsigned __int16 *
0x18000afce  lea     rdx, aInArgumentFoun; "\"in\" <argument> found after one or mo"...
0x18000afd5  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000afda  mov     ebx, eax
0x18000afdc  jmp     loc_18000ADAD
0x18000afe1  lea     r9, [rsp+4B0h+var_468]; unsigned __int16 **
0x18000afe6  xor     r8d, r8d; unsigned __int16 *
0x18000afe9  lea     rdx, aArgumentlistCo; "<argumentList> contained <argument> ele"...
0x18000aff0  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000aff5  mov     ebx, eax
0x18000aff7  jmp     loc_18000AEBB
0x18000affc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b003  cmp     rcx, rsi
0x18000b006  jz      loc_18000AEC2
0x18000b00c  test    byte ptr [rcx+1Ch], 1
0x18000b010  jz      loc_18000AEC2
0x18000b016  mov     rcx, [rcx+10h]
0x18000b01a  lea     r9, aHrvalidateargl; "HrValidateArgList(): Failed to check fo"...
0x18000b021  mov     edx, 17h
0x18000b026  mov     dword ptr [rsp+4B0h+var_490], eax
0x18000b02a  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x18000b031  call    WPP_SF_sd
0x18000b036  jmp     loc_18000AEBB
0x18000b03b  mov     rcx, [rsp+4B0h+var_450]
0x18000b040  mov     [rcx], rax
  ... truncated ...
```
