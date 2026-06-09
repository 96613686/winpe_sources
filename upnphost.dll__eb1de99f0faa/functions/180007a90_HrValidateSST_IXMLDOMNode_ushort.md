# HrValidateSST(IXMLDOMNode *,ushort * *)

- ea: `0x180007a90`
- end: `0x180007f26`
- name: `?HrValidateSST@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `1174`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010800`

## callees

- `0x180007a90`
- `0x180007f30`
- `0x180009ae0`
- `0x18000db4c`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180007d48`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180007d48`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180007d5b`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180007d5b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007d09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007d1f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007d09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007d1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c90`

## string_xrefs

- `0x180007bd0`: `urn:schemas-upnp-org:service-1-`
- `0x180007df1`: `<serviceStateTable> did not contain any <stateVariable> elements`
- `0x180007e38`: `<serviceStateTable> contained <stateVariable> elements with duplicate names`

## pseudocode

```c
__int64 __fastcall HrValidateSST(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  HRESULT (__stdcall *get_firstChild)(IXMLDOMNode *, IXMLDOMNode **); // rax
  int v5; // r15d
  int v6; // eax
  int v7; // ecx
  int v8; // r8d
  struct IXMLDOMNode *v9; // rdi
  int v10; // ebx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v12; // r14d
  int v13; // ebx
  OLECHAR *v14; // r10
  __int64 v15; // rcx
  BSTR v16; // rax
  unsigned __int64 v17; // rsi
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
  unsigned __int64 i; // rdi
  STRSAFE_PCNZWCH v29; // rcx
  int v31; // eax
  int v32; // ecx
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  struct IXMLDOMNode *v34; // [rsp+40h] [rbp-C8h] BYREF
  BSTR v35; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v36; // [rsp+50h] [rbp-B8h] BYREF
  struct IXMLDOMNode *v37; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR String2[256]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR String1[256]; // [rsp+268h] [rbp+160h] BYREF

  get_firstChild = a1->lpVtbl->get_firstChild;
  v5 = 0;
  v36 = 0;
  v34 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))get_firstChild)(a1, &v34);
  v9 = v34;
  v10 = v6;
  while ( 1 )
  {
    if ( v10 < 0 )
      goto LABEL_46;
    if ( !v9 )
      break;
    v37 = 0;
    lpVtbl = v9->lpVtbl;
    v35 = 0;
    v12 = 0;
    bstrString = 0;
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_baseName)(v9, &v35);
    if ( v13 >= 0 && v35 )
    {
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v9->lpVtbl->get_namespaceURI)(v9, &bstrString);
      if ( v13 >= 0 )
      {
        v14 = bstrString;
        if ( bstrString )
        {
          v15 = 0x7FFFFFFF;
          v16 = bstrString;
          while ( *v16 )
          {
            ++v16;
            if ( !--v15 )
            {
              v17 = 0;
              v13 = -2147024809;
              goto LABEL_13;
            }
          }
          v17 = 0x7FFFFFFF - v15;
          v13 = 0;
LABEL_13:
          if ( v13 < 0 )
          {
            v17 = 0;
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
            v13 = -2147024774;
            if ( v20 )
            {
              v22 = v21;
              v13 = 0;
            }
            *v22 = 0;
          }
          if ( v13 >= 0 )
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
            v13 = -2147024774;
            if ( v26 )
            {
              v27 = v24;
              v13 = 0;
            }
            *v27 = 0;
            if ( v26 )
            {
              if ( !lstrcmpW(v35, L"stateVariable") && !lstrcmpW(String1, String2) )
              {
                v12 = 1;
                if ( v17 > 0x1F )
                {
                  for ( i = 31; i < v17; ++i )
                  {
                    if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                    {
                      v12 = 0;
                      break;
                    }
                  }
                }
              }
              v14 = bstrString;
            }
          }
          SysFreeString(v14);
        }
      }
      SysFreeString(v35);
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
      v10 = HrValidateStateVariable(v34, &v36);
      v5 = 1;
      if ( v10 < 0 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
LABEL_46:
        v29 = WPP_GLOBAL_Control;
        goto LABEL_47;
      }
    }
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v34->lpVtbl->get_nextSibling)(v34, &v37);
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
    v9 = v37;
    v34 = v37;
  }
  if ( !v5 )
  {
    v10 = HrAllocErrorStringAndReturnHr(
            v7,
            L"<serviceStateTable> did not contain any <stateVariable> elements",
            0,
            &v36);
    if ( v10 < 0 )
      goto LABEL_46;
  }
  LODWORD(bstrString) = 0;
  v31 = HrAreThereDuplicatesInChildNodeTextValues(a1, L"scpd:stateVariable/scpd:name", v8, (int *)&bstrString);
  v10 = v31;
  if ( v31 >= 0 )
  {
    if ( (_DWORD)bstrString )
      v10 = HrAllocErrorStringAndReturnHr(
              v32,
              L"<serviceStateTable> contained <stateVariable> elements with duplicate names",
              0,
              &v36);
    goto LABEL_46;
  }
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateSST(): Failed to check for duplicate names",
      v31);
    goto LABEL_46;
  }
LABEL_47:
  if ( v36 )
  {
    *a2 = v36;
    v29 = WPP_GLOBAL_Control;
  }
  if ( v10 && v29 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v29[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)v29 + 2),
      37,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateSST(): Exiting",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007a90  mov     r11, rsp
0x180007a93  push    rbp
0x180007a94  push    rbx
0x180007a95  push    rsi
0x180007a96  lea     rbp, [r11-3A8h]
0x180007a9d  sub     rsp, 490h
0x180007aa4  mov     rax, cs:__security_cookie
0x180007aab  xor     rax, rsp
0x180007aae  mov     [rbp+3A0h+var_40], rax
0x180007ab5  mov     rax, [rcx]
0x180007ab8  mov     [r11+18h], rdi
0x180007abc  mov     [r11-20h], r12
0x180007ac0  mov     r12, rcx
0x180007ac3  mov     [r11-28h], r13
0x180007ac7  mov     r13, rdx
0x180007aca  mov     rax, [rax+68h]
0x180007ace  lea     rdx, [rsp+4A0h+var_468]
0x180007ad3  mov     [r11-38h], r15
0x180007ad7  xor     r15d, r15d
0x180007ada  mov     [rsp+4A0h+var_458], 0
0x180007ae3  mov     [rsp+4A0h+var_468], 0
0x180007aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af1  mov     rdi, [rsp+4A0h+var_468]
0x180007af6  lea     rsi, WPP_GLOBAL_Control
0x180007afd  mov     ebx, eax
0x180007aff  mov     [rsp+4A0h+var_28], r14
0x180007b07  test    ebx, ebx
0x180007b09  js      loc_180007D88
0x180007b0f  test    rdi, rdi
0x180007b12  jz      loc_180007E91
0x180007b18  mov     [rsp+4A0h+var_450], 0
0x180007b21  lea     rdx, [rsp+4A0h+var_460]
0x180007b26  mov     rax, [rdi]
0x180007b29  mov     rcx, rdi
0x180007b2c  mov     [rsp+4A0h+var_460], 0
0x180007b35  xor     r14d, r14d
0x180007b38  mov     [rsp+4A0h+bstrString], 0
0x180007b41  mov     rax, [rax+148h]
0x180007b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b4d  mov     ebx, eax
0x180007b4f  test    eax, eax
0x180007b51  js      loc_180007C96
0x180007b57  cmp     [rsp+4A0h+var_460], r14
0x180007b5c  jz      loc_180007C96
0x180007b62  mov     rax, [rdi]
0x180007b65  lea     rdx, [rsp+4A0h+bstrString]
0x180007b6a  mov     rcx, rdi
0x180007b6d  mov     rax, [rax+138h]
0x180007b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b79  mov     ebx, eax
0x180007b7b  test    eax, eax
0x180007b7d  js      loc_180007C8B
0x180007b83  mov     r10, [rsp+4A0h+bstrString]
0x180007b88  test    r10, r10
0x180007b8b  jz      loc_180007C8B
0x180007b91  mov     ecx, 7FFFFFFFh
0x180007b96  mov     rax, r10
0x180007b99  nop     dword ptr [rax+00000000h]
0x180007ba0  cmp     [rax], r14w
0x180007ba4  jz      short loc_180007BB9
0x180007ba6  add     rax, 2
0x180007baa  sub     rcx, 1
0x180007bae  jnz     short loc_180007BA0
0x180007bb0  xor     esi, esi
0x180007bb2  mov     ebx, 80070057h
0x180007bb7  jmp     short loc_180007BC3
0x180007bb9  mov     esi, 7FFFFFFFh
0x180007bbe  sub     rsi, rcx
0x180007bc1  xor     ebx, ebx
0x180007bc3  test    ebx, ebx
0x180007bc5  js      loc_180007E4B
0x180007bcb  mov     ecx, 1Fh
0x180007bd0  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180007bd7  mov     r8d, 100h
0x180007bdd  lea     r9, [rbp+3A0h+String1]
0x180007be4  test    rcx, rcx
0x180007be7  jz      short loc_180007C06
0x180007be9  movzx   eax, word ptr [rdx]
0x180007bec  test    ax, ax
0x180007bef  jz      short loc_180007C06
0x180007bf1  mov     [r9], ax
0x180007bf5  add     rdx, 2
0x180007bf9  add     r9, 2
0x180007bfd  dec     rcx
0x180007c00  sub     r8, 1
0x180007c04  jnz     short loc_180007BE4
0x180007c06  test    r8, r8
0x180007c09  lea     rcx, [r9-2]
0x180007c0d  mov     ebx, 8007007Ah
0x180007c12  cmovnz  rcx, r9
0x180007c16  xor     eax, eax
0x180007c18  test    r8, r8
0x180007c1b  cmovnz  ebx, eax
0x180007c1e  mov     [rcx], ax
0x180007c21  test    ebx, ebx
0x180007c23  js      short loc_180007C7B
0x180007c25  mov     ecx, 1Fh
0x180007c2a  lea     r9, [rsp+4A0h+String2]
0x180007c2f  mov     rdx, r10
0x180007c32  mov     r8d, 100h
0x180007c38  test    rcx, rcx
0x180007c3b  jz      short loc_180007C5A
0x180007c3d  movzx   eax, word ptr [rdx]
0x180007c40  test    ax, ax
0x180007c43  jz      short loc_180007C5A
0x180007c45  mov     [r9], ax
0x180007c49  add     rdx, 2
0x180007c4d  add     r9, 2
0x180007c51  dec     rcx
0x180007c54  sub     r8, 1
0x180007c58  jnz     short loc_180007C38
0x180007c5a  test    r8, r8
0x180007c5d  lea     rcx, [r9-2]
0x180007c61  mov     ebx, 8007007Ah
0x180007c66  cmovnz  rcx, r9
0x180007c6a  xor     eax, eax
0x180007c6c  test    r8, r8
0x180007c6f  cmovnz  ebx, eax
0x180007c72  mov     [rcx], ax
0x180007c75  jnz     loc_180007CFD
0x180007c7b  mov     rcx, r10; bstrString
0x180007c7e  call    cs:__imp_SysFreeString
0x180007c84  lea     rsi, WPP_GLOBAL_Control
0x180007c8b  mov     rcx, [rsp+4A0h+var_460]; bstrString
0x180007c90  call    cs:__imp_SysFreeString
0x180007c96  test    ebx, ebx
0x180007c98  jnz     loc_180007E52
0x180007c9e  test    r14d, r14d
0x180007ca1  jz      short loc_180007CC2
0x180007ca3  mov     rcx, [rsp+4A0h+var_468]; struct IXMLDOMNode *
0x180007ca8  lea     rdx, [rsp+4A0h+var_458]; unsigned __int16 **
0x180007cad  call    ?HrValidateStateVariable@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z; HrValidateStateVariable(IXMLDOMNode *,ushort * *)
0x180007cb2  mov     ebx, eax
0x180007cb4  mov     r15d, 1
0x180007cba  test    eax, eax
0x180007cbc  js      loc_180007D77
0x180007cc2  mov     rcx, [rsp+4A0h+var_468]
0x180007cc7  lea     rdx, [rsp+4A0h+var_450]
0x180007ccc  mov     rax, [rcx]
0x180007ccf  mov     rax, [rax+80h]
0x180007cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cdb  mov     rcx, [rsp+4A0h+var_468]
0x180007ce0  mov     ebx, eax
0x180007ce2  mov     rax, [rcx]
0x180007ce5  mov     rax, [rax+10h]
0x180007ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cee  mov     rdi, [rsp+4A0h+var_450]
0x180007cf3  mov     [rsp+4A0h+var_468], rdi
0x180007cf8  jmp     loc_180007B07
0x180007cfd  mov     rcx, [rsp+4A0h+var_460]; lpString1
0x180007d02  lea     rdx, String2; "stateVariable"
0x180007d09  call    cs:__imp_lstrcmpW
0x180007d0f  test    eax, eax
0x180007d11  jnz     short loc_180007D6D
0x180007d13  lea     rdx, [rsp+4A0h+String2]; lpString2
0x180007d18  lea     rcx, [rbp+3A0h+String1]; lpString1
0x180007d1f  call    cs:__imp_lstrcmpW
0x180007d25  test    eax, eax
0x180007d27  jnz     short loc_180007D6D
0x180007d29  mov     r14d, 1
0x180007d2f  cmp     rsi, 1Fh
0x180007d33  jbe     short loc_180007D6D
0x180007d35  mov     edi, 1Fh
0x180007d3a  cmp     rdi, rsi
0x180007d3d  jnb     short loc_180007D6D
0x180007d3f  mov     rcx, [rsp+4A0h+bstrString]
0x180007d44  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x180007d48  call    cs:__imp_IsCharAlphaNumericW
0x180007d4e  test    eax, eax
0x180007d50  jz      short loc_180007D6A
0x180007d52  mov     rcx, [rsp+4A0h+bstrString]
0x180007d57  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x180007d5b  call    cs:__imp_IsCharAlphaW
0x180007d61  test    eax, eax
0x180007d63  jnz     short loc_180007D6A
0x180007d65  inc     rdi
0x180007d68  jmp     short loc_180007D3A
0x180007d6a  xor     r14d, r14d
0x180007d6d  mov     r10, [rsp+4A0h+bstrString]
0x180007d72  jmp     loc_180007C7B
0x180007d77  mov     rcx, [rsp+4A0h+var_468]
0x180007d7c  mov     rax, [rcx]
0x180007d7f  mov     rax, [rax+10h]
0x180007d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d8f  mov     rax, [rsp+4A0h+var_458]
0x180007d94  mov     r15, [rsp+4A0h+var_30]
0x180007d9c  mov     r14, [rsp+4A0h+var_28]
0x180007da4  mov     r12, [rsp+4A0h+var_18]
0x180007dac  mov     rdi, [rsp+4A0h+arg_10]
0x180007db4  test    rax, rax
0x180007db7  jnz     loc_180007EDE
0x180007dbd  mov     r13, [rsp+4A0h+var_20]
0x180007dc5  test    ebx, ebx
0x180007dc7  jnz     loc_180007EEE
0x180007dcd  mov     eax, ebx
0x180007dcf  mov     rcx, [rbp+3A0h+var_40]
0x180007dd6  xor     rcx, rsp; StackCookie
0x180007dd9  call    __security_check_cookie
0x180007dde  add     rsp, 490h
0x180007de5  pop     rsi
0x180007de6  pop     rbx
0x180007de7  pop     rbp
0x180007de8  retn
0x180007de9  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x180007dee  xor     r8d, r8d; unsigned __int16 *
0x180007df1  lea     rdx, aServicestateta_1; "<serviceStateTable> did not contain any"...
0x180007df8  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x180007dfd  mov     ebx, eax
0x180007dff  test    eax, eax
0x180007e01  js      short loc_180007D88
0x180007e03  lea     r9, [rsp+4A0h+bstrString]; int *
0x180007e08  mov     dword ptr [rsp+4A0h+bstrString], 0
0x180007e10  lea     rdx, aScpdStatevaria; "scpd:stateVariable/scpd:name"
0x180007e17  mov     rcx, r12; struct IXMLDOMNode *
0x180007e1a  call    ?HrAreThereDuplicatesInChildNodeTextValues@@YAJPEAUIXMLDOMNode@@PEBGHPEAH@Z; HrAreThereDuplicatesInChildNodeTextValues(IXMLDOMNode *,ushort const *,int,int *)
0x180007e1f  mov     ebx, eax
0x180007e21  test    eax, eax
0x180007e23  js      short loc_180007E9F
0x180007e25  cmp     dword ptr [rsp+4A0h+bstrString], 0
0x180007e2a  jz      loc_180007D88
0x180007e30  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x180007e35  xor     r8d, r8d; unsigned __int16 *
0x180007e38  lea     rdx, aServicestateta_0; "<serviceStateTable> contained <stateVar"...
0x180007e3f  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x180007e44  mov     ebx, eax
0x180007e46  jmp     loc_180007D88
0x180007e4b  xor     esi, esi
0x180007e4d  jmp     loc_180007C21
0x180007e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e59  cmp     rcx, rsi
0x180007e5c  jz      loc_180007C9E
0x180007e62  test    byte ptr [rcx+1Ch], 1
0x180007e66  jz      loc_180007C9E
0x180007e6c  mov     rcx, [rcx+10h]
0x180007e70  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x180007e77  mov     edx, 14h
0x180007e7c  mov     [rsp+4A0h+var_480], ebx
0x180007e80  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180007e87  call    WPP_SF_sd
0x180007e8c  jmp     loc_180007C9E
0x180007e91  test    r15d, r15d
0x180007e94  jnz     loc_180007E03
0x180007e9a  jmp     loc_180007DE9
0x180007e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ea6  cmp     rcx, rsi
0x180007ea9  jz      loc_180007D8F
0x180007eaf  test    byte ptr [rcx+1Ch], 1
0x180007eb3  jz      loc_180007D8F
0x180007eb9  mov     rcx, [rcx+10h]
0x180007ebd  lea     r9, aHrvalidatesstF; "HrValidateSST(): Failed to check for du"...
0x180007ec4  mov     edx, 24h ; '$'
0x180007ec9  mov     [rsp+4A0h+var_480], eax
0x180007ecd  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x180007ed4  call    WPP_SF_sd
0x180007ed9  jmp     loc_180007D88
0x180007ede  mov     [r13+0], rax
0x180007ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ee9  jmp     loc_180007DBD
0x180007eee  cmp     rcx, rsi
0x180007ef1  jz      loc_180007DCD
0x180007ef7  test    byte ptr [rcx+1Ch], 1
0x180007efb  jz      loc_180007DCD
0x180007f01  mov     rcx, [rcx+10h]
0x180007f05  lea     r9, aHrvalidatesstE; "HrValidateSST(): Exiting"
0x180007f0c  mov     edx, 25h ; '%'
0x180007f11  mov     [rsp+4A0h+var_480], ebx
0x180007f15  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x180007f1c  call    WPP_SF_sd
0x180007f21  jmp     loc_180007DCD
```
