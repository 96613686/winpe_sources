# HrValidateActionList(IXMLDOMNode *,IXMLDOMNode *,ushort * *)

- ea: `0x18001c310`
- end: `0x18001c7ef`
- name: `?HrValidateActionList@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z`
- size: `1247`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800047a0`

## callees

- `0x18001bf10`
- `0x18001c310`
- `0x18001c800`
- `0x1800200f4`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001c5cc`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18001c5cc`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001c5e9`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18001c5e9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001c581`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001c59d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001c581`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001c59d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4ff`

## string_xrefs

- `0x18001c43e`: `urn:schemas-upnp-org:service-1-`

## pseudocode

```c
__int64 __fastcall HrValidateActionList(struct IXMLDOMNode *a1, struct IXMLDOMNode *a2, unsigned __int16 **a3)
{
  unsigned __int64 v3; // rsi
  HRESULT (__stdcall *get_firstChild)(IXMLDOMNode *, IXMLDOMNode **); // rax
  int v7; // r15d
  int v8; // eax
  int v9; // ecx
  int v10; // r8d
  struct IXMLDOMNode *v11; // rdi
  int v12; // ebx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v14; // r14d
  int v15; // ebx
  OLECHAR *v16; // r10
  __int64 v17; // rcx
  BSTR v18; // rax
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
  unsigned __int64 i; // rdi
  STRSAFE_PCNZWCH v30; // rcx
  int v32; // eax
  int v33; // ecx
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  struct IXMLDOMNode *v35; // [rsp+40h] [rbp-C8h] BYREF
  BSTR v36; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v37; // [rsp+50h] [rbp-B8h] BYREF
  struct IXMLDOMNode *v38; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 **v39; // [rsp+60h] [rbp-A8h]
  WCHAR String2[256]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR String1[256]; // [rsp+268h] [rbp+160h] BYREF

  v3 = 0;
  get_firstChild = a1->lpVtbl->get_firstChild;
  v7 = 0;
  v39 = a3;
  v37 = 0;
  v35 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))get_firstChild)(a1, &v35);
  v11 = v35;
  v12 = v8;
  while ( 1 )
  {
    if ( v12 < 0 )
      goto LABEL_46;
    if ( !v11 )
      break;
    v38 = 0;
    lpVtbl = v11->lpVtbl;
    v36 = 0;
    v14 = 0;
    bstrString = 0;
    v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_baseName)(v11, &v36);
    if ( v15 >= 0 && v36 )
    {
      v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v11->lpVtbl->get_namespaceURI)(v11, &bstrString);
      if ( v15 >= 0 )
      {
        v16 = bstrString;
        if ( bstrString )
        {
          v17 = 0x7FFFFFFF;
          v18 = bstrString;
          while ( *v18 )
          {
            ++v18;
            if ( !--v17 )
            {
              v15 = -2147024809;
              goto LABEL_13;
            }
          }
          v3 = 0x7FFFFFFF - v17;
          v15 = 0;
LABEL_13:
          if ( v15 < 0 )
          {
            v3 = 0;
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
            v15 = -2147024774;
            if ( v21 )
            {
              v23 = v22;
              v15 = 0;
            }
            *v23 = 0;
          }
          if ( v15 >= 0 )
          {
            v24 = 31;
            v25 = String2;
            v26 = v16;
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
            v15 = -2147024774;
            if ( v27 )
            {
              v28 = v25;
              v15 = 0;
            }
            *v28 = 0;
            if ( v27 )
            {
              if ( !lstrcmpW(v36, L"action") && !lstrcmpW(String1, String2) )
              {
                v14 = 1;
                if ( v3 > 0x1F )
                {
                  for ( i = 31; i < v3; ++i )
                  {
                    if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                    {
                      v16 = bstrString;
                      v3 = 0;
                      v14 = 0;
                      goto LABEL_30;
                    }
                  }
                }
              }
              v16 = bstrString;
            }
          }
          v3 = 0;
LABEL_30:
          SysFreeString(v16);
        }
      }
      SysFreeString(v36);
    }
    if ( v15 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
        v15);
    if ( v14 )
    {
      v12 = HrValidateAction(v35, a2, &v37);
      v7 = 1;
      if ( v12 < 0 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v35->lpVtbl->Release)(v35);
LABEL_46:
        v30 = WPP_GLOBAL_Control;
        goto LABEL_47;
      }
    }
    v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v35->lpVtbl->get_nextSibling)(v35, &v38);
    ((void (__fastcall *)(struct IXMLDOMNode *))v35->lpVtbl->Release)(v35);
    v11 = v38;
    v35 = v38;
  }
  if ( !v7 )
  {
    v12 = HrAllocErrorStringAndReturnHr(v9, L"<actionList> did not contain any <action> elements", 0, &v37);
    if ( v12 < 0 )
      goto LABEL_46;
  }
  LODWORD(bstrString) = 0;
  v32 = HrAreThereDuplicatesInChildNodeTextValues(a1, L"scpd:action/scpd:name", v10, (int *)&bstrString);
  v12 = v32;
  if ( v32 >= 0 )
  {
    if ( (_DWORD)bstrString )
      v12 = HrAllocErrorStringAndReturnHr(
              v33,
              L"<actionList> contained <action> elements with duplicate names",
              0,
              &v37);
    goto LABEL_46;
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateActionList(): Failed to check for duplicate names",
      v32);
    goto LABEL_46;
  }
LABEL_47:
  if ( v37 )
  {
    *v39 = v37;
    v30 = WPP_GLOBAL_Control;
  }
  if ( v12 && v30 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v30[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)v30 + 2),
      27,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateActionList(): Exiting",
      v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001c310  mov     r11, rsp
0x18001c313  push    rbp
0x18001c314  push    rbx
0x18001c315  lea     rbp, [r11-3A8h]
0x18001c31c  sub     rsp, 498h
0x18001c323  mov     rax, cs:__security_cookie
0x18001c32a  xor     rax, rsp
0x18001c32d  mov     [rbp+3A0h+var_40], rax
0x18001c334  mov     rax, [rcx]
0x18001c337  mov     [r11+20h], rsi
0x18001c33b  xor     esi, esi
0x18001c33d  mov     [r11-18h], rdi
0x18001c341  mov     [r11-20h], r12
0x18001c345  mov     r12, rdx
0x18001c348  mov     rax, [rax+68h]
0x18001c34c  lea     rdx, [rsp+4A0h+var_468]
0x18001c351  mov     [r11-28h], r13
0x18001c355  mov     r13, rcx
0x18001c358  mov     [r11-38h], r15
0x18001c35c  mov     r15d, esi
0x18001c35f  mov     [rsp+4A0h+var_448], r8
0x18001c364  mov     [rsp+4A0h+var_458], rsi
0x18001c369  mov     [rsp+4A0h+var_468], rsi
0x18001c36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c373  mov     rdi, [rsp+4A0h+var_468]
0x18001c378  mov     ebx, eax
0x18001c37a  mov     [rsp+4A0h+var_28], r14
0x18001c382  test    ebx, ebx
0x18001c384  js      loc_18001C61D
0x18001c38a  test    rdi, rdi
0x18001c38d  jz      loc_18001C74F
0x18001c393  mov     [rsp+4A0h+var_450], rsi
0x18001c398  lea     rdx, [rsp+4A0h+var_460]
0x18001c39d  mov     rax, [rdi]
0x18001c3a0  mov     rcx, rdi
0x18001c3a3  mov     [rsp+4A0h+var_460], rsi
0x18001c3a8  mov     r14d, esi
0x18001c3ab  mov     [rsp+4A0h+bstrString], rsi
0x18001c3b0  mov     rax, [rax+148h]
0x18001c3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3bc  mov     ebx, eax
0x18001c3be  test    eax, eax
0x18001c3c0  js      loc_18001C50B
0x18001c3c6  cmp     [rsp+4A0h+var_460], 0
0x18001c3cc  jz      loc_18001C50B
0x18001c3d2  mov     rax, [rdi]
0x18001c3d5  lea     rdx, [rsp+4A0h+bstrString]
0x18001c3da  mov     rcx, rdi
0x18001c3dd  mov     rax, [rax+138h]
0x18001c3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3e9  mov     ebx, eax
0x18001c3eb  test    eax, eax
0x18001c3ed  js      loc_18001C4FA
0x18001c3f3  mov     r10, [rsp+4A0h+bstrString]
0x18001c3f8  test    r10, r10
0x18001c3fb  jz      loc_18001C4FA
0x18001c401  mov     ecx, 7FFFFFFFh
0x18001c406  mov     rax, r10
0x18001c409  nop     dword ptr [rax+00000000h]
0x18001c410  cmp     word ptr [rax], 0
0x18001c414  jz      short loc_18001C427
0x18001c416  add     rax, 2
0x18001c41a  sub     rcx, 1
0x18001c41e  jnz     short loc_18001C410
0x18001c420  mov     ebx, 80070057h
0x18001c425  jmp     short loc_18001C431
0x18001c427  mov     esi, 7FFFFFFFh
0x18001c42c  sub     rsi, rcx
0x18001c42f  xor     ebx, ebx
0x18001c431  test    ebx, ebx
0x18001c433  js      loc_18001C702
0x18001c439  mov     ecx, 1Fh
0x18001c43e  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18001c445  mov     r8d, 100h
0x18001c44b  lea     r9, [rbp+3A0h+String1]
0x18001c452  test    rcx, rcx
0x18001c455  jz      short loc_18001C474
0x18001c457  movzx   eax, word ptr [rdx]
0x18001c45a  test    ax, ax
0x18001c45d  jz      short loc_18001C474
0x18001c45f  mov     [r9], ax
0x18001c463  add     rdx, 2
0x18001c467  add     r9, 2
0x18001c46b  dec     rcx
0x18001c46e  sub     r8, 1
0x18001c472  jnz     short loc_18001C452
0x18001c474  test    r8, r8
0x18001c477  lea     rcx, [r9-2]
0x18001c47b  mov     ebx, 8007007Ah
0x18001c480  cmovnz  rcx, r9
0x18001c484  xor     eax, eax
0x18001c486  test    r8, r8
0x18001c489  cmovnz  ebx, eax
0x18001c48c  mov     [rcx], ax
0x18001c48f  test    ebx, ebx
0x18001c491  js      short loc_18001C4E9
0x18001c493  mov     ecx, 1Fh
0x18001c498  lea     r9, [rsp+4A0h+String2]
0x18001c49d  mov     rdx, r10
0x18001c4a0  mov     r8d, 100h
0x18001c4a6  test    rcx, rcx
0x18001c4a9  jz      short loc_18001C4C8
0x18001c4ab  movzx   eax, word ptr [rdx]
0x18001c4ae  test    ax, ax
0x18001c4b1  jz      short loc_18001C4C8
0x18001c4b3  mov     [r9], ax
0x18001c4b7  add     rdx, 2
0x18001c4bb  add     r9, 2
0x18001c4bf  dec     rcx
0x18001c4c2  sub     r8, 1
0x18001c4c6  jnz     short loc_18001C4A6
0x18001c4c8  test    r8, r8
0x18001c4cb  lea     rcx, [r9-2]
0x18001c4cf  mov     ebx, 8007007Ah
0x18001c4d4  cmovnz  rcx, r9
0x18001c4d8  xor     eax, eax
0x18001c4da  test    r8, r8
0x18001c4dd  cmovnz  ebx, eax
0x18001c4e0  mov     [rcx], ax
0x18001c4e3  jnz     loc_18001C575
0x18001c4e9  xor     esi, esi
0x18001c4eb  mov     rcx, r10; bstrString
0x18001c4ee  call    cs:__imp_SysFreeString
0x18001c4f5  nop     dword ptr [rax+rax+00h]
0x18001c4fa  mov     rcx, [rsp+4A0h+var_460]; bstrString
0x18001c4ff  call    cs:__imp_SysFreeString
0x18001c506  nop     dword ptr [rax+rax+00h]
0x18001c50b  test    ebx, ebx
0x18001c50d  jnz     loc_18001C709
0x18001c513  test    r14d, r14d
0x18001c516  jz      short loc_18001C53A
0x18001c518  mov     rcx, [rsp+4A0h+var_468]; struct IXMLDOMNode *
0x18001c51d  lea     r8, [rsp+4A0h+var_458]; unsigned __int16 **
0x18001c522  mov     rdx, r12; struct IXMLDOMNode *
0x18001c525  call    ?HrValidateAction@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z; HrValidateAction(IXMLDOMNode *,IXMLDOMNode *,ushort * *)
0x18001c52a  mov     ebx, eax
0x18001c52c  mov     r15d, 1
0x18001c532  test    eax, eax
0x18001c534  js      loc_18001C60C
0x18001c53a  mov     rcx, [rsp+4A0h+var_468]
0x18001c53f  lea     rdx, [rsp+4A0h+var_450]
0x18001c544  mov     rax, [rcx]
0x18001c547  mov     rax, [rax+80h]
0x18001c54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c553  mov     rcx, [rsp+4A0h+var_468]
0x18001c558  mov     ebx, eax
0x18001c55a  mov     rax, [rcx]
0x18001c55d  mov     rax, [rax+10h]
0x18001c561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c566  mov     rdi, [rsp+4A0h+var_450]
0x18001c56b  mov     [rsp+4A0h+var_468], rdi
0x18001c570  jmp     loc_18001C382
0x18001c575  mov     rcx, [rsp+4A0h+var_460]; lpString1
0x18001c57a  lea     rdx, aAction; "action"
0x18001c581  call    cs:__imp_lstrcmpW
0x18001c588  nop     dword ptr [rax+rax+00h]
0x18001c58d  test    eax, eax
0x18001c58f  jnz     short loc_18001C602
0x18001c591  lea     rdx, [rsp+4A0h+String2]; lpString2
0x18001c596  lea     rcx, [rbp+3A0h+String1]; lpString1
0x18001c59d  call    cs:__imp_lstrcmpW
0x18001c5a4  nop     dword ptr [rax+rax+00h]
0x18001c5a9  test    eax, eax
0x18001c5ab  jnz     short loc_18001C602
0x18001c5ad  mov     r14d, 1
0x18001c5b3  cmp     rsi, 1Fh
0x18001c5b7  jbe     short loc_18001C602
0x18001c5b9  mov     edi, 1Fh
0x18001c5be  cmp     rdi, rsi
0x18001c5c1  jnb     short loc_18001C602
0x18001c5c3  mov     rcx, [rsp+4A0h+bstrString]
0x18001c5c8  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18001c5cc  call    cs:__imp_IsCharAlphaNumericW
0x18001c5d3  nop     dword ptr [rax+rax+00h]
0x18001c5d8  test    eax, eax
0x18001c5da  jz      loc_18001C68D
0x18001c5e0  mov     rcx, [rsp+4A0h+bstrString]
0x18001c5e5  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18001c5e9  call    cs:__imp_IsCharAlphaW
0x18001c5f0  nop     dword ptr [rax+rax+00h]
0x18001c5f5  test    eax, eax
0x18001c5f7  jnz     loc_18001C68D
0x18001c5fd  inc     rdi
0x18001c600  jmp     short loc_18001C5BE
0x18001c602  mov     r10, [rsp+4A0h+bstrString]
0x18001c607  jmp     loc_18001C4E9
0x18001c60c  mov     rcx, [rsp+4A0h+var_468]
0x18001c611  mov     rax, [rcx]
0x18001c614  mov     rax, [rax+10h]
0x18001c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c61d  lea     r14, WPP_GLOBAL_Control
0x18001c624  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c62b  mov     rax, [rsp+4A0h+var_458]
0x18001c630  mov     r15, [rsp+4A0h+var_30]
0x18001c638  mov     r13, [rsp+4A0h+var_20]
0x18001c640  mov     r12, [rsp+4A0h+var_18]
0x18001c648  mov     rdi, [rsp+490h]
0x18001c650  mov     rsi, [rsp+4A0h+arg_18]
0x18001c658  test    rax, rax
0x18001c65b  jnz     loc_18001C7A3
0x18001c661  test    ebx, ebx
0x18001c663  jnz     loc_18001C7B7
0x18001c669  mov     r14, [rsp+4A0h+var_28]
0x18001c671  mov     eax, ebx
0x18001c673  mov     rcx, [rbp+3A0h+var_40]
0x18001c67a  xor     rcx, rsp; StackCookie
0x18001c67d  call    __security_check_cookie
0x18001c682  add     rsp, 498h
0x18001c689  pop     rbx
0x18001c68a  pop     rbp
0x18001c68b  retn
0x18001c68d  mov     r10, [rsp+4A0h+bstrString]
0x18001c692  xor     esi, esi
0x18001c694  mov     r14d, esi
0x18001c697  jmp     loc_18001C4EB
0x18001c69c  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x18001c6a1  xor     r8d, r8d; unsigned __int16 *
0x18001c6a4  lea     rdx, aActionlistDidN; "<actionList> did not contain any <actio"...
0x18001c6ab  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18001c6b0  mov     ebx, eax
0x18001c6b2  test    eax, eax
0x18001c6b4  js      loc_18001C61D
0x18001c6ba  lea     r9, [rsp+4A0h+bstrString]; int *
0x18001c6bf  mov     dword ptr [rsp+4A0h+bstrString], esi
0x18001c6c3  lea     rdx, aScpdActionScpd; "scpd:action/scpd:name"
0x18001c6ca  mov     rcx, r13; struct IXMLDOMNode *
0x18001c6cd  call    ?HrAreThereDuplicatesInChildNodeTextValues@@YAJPEAUIXMLDOMNode@@PEBGHPEAH@Z; HrAreThereDuplicatesInChildNodeTextValues(IXMLDOMNode *,ushort const *,int,int *)
0x18001c6d2  mov     ebx, eax
0x18001c6d4  test    eax, eax
0x18001c6d6  js      loc_18001C75D
0x18001c6dc  cmp     dword ptr [rsp+4A0h+bstrString], 0
0x18001c6e1  jz      loc_18001C61D
0x18001c6e7  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x18001c6ec  xor     r8d, r8d; unsigned __int16 *
0x18001c6ef  lea     rdx, aActionlistCont; "<actionList> contained <action> element"...
0x18001c6f6  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18001c6fb  mov     ebx, eax
0x18001c6fd  jmp     loc_18001C61D
0x18001c702  xor     esi, esi
0x18001c704  jmp     loc_18001C48F
0x18001c709  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c710  lea     rax, WPP_GLOBAL_Control
0x18001c717  cmp     rcx, rax
0x18001c71a  jz      loc_18001C513
0x18001c720  test    byte ptr [rcx+1Ch], 1
0x18001c724  jz      loc_18001C513
0x18001c72a  mov     rcx, [rcx+10h]
0x18001c72e  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x18001c735  mov     edx, 14h
0x18001c73a  mov     [rsp+20h], ebx
0x18001c73e  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001c745  call    WPP_SF_sd
0x18001c74a  jmp     loc_18001C513
0x18001c74f  test    r15d, r15d
0x18001c752  jnz     loc_18001C6BA
0x18001c758  jmp     loc_18001C69C
0x18001c75d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c764  lea     r14, WPP_GLOBAL_Control
0x18001c76b  cmp     rcx, r14
0x18001c76e  jz      loc_18001C62B
0x18001c774  test    byte ptr [rcx+1Ch], 1
0x18001c778  jz      loc_18001C62B
0x18001c77e  mov     rcx, [rcx+10h]
0x18001c782  lea     r9, aHrvalidateacti_1; "HrValidateActionList(): Failed to check"...
0x18001c789  mov     edx, 1Ah
0x18001c78e  mov     [rsp+20h], eax
0x18001c792  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x18001c799  call    WPP_SF_sd
0x18001c79e  jmp     loc_18001C624
0x18001c7a3  mov     rcx, [rsp+4A0h+var_448]
0x18001c7a8  mov     [rcx], rax
0x18001c7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7b2  jmp     loc_18001C661
0x18001c7b7  cmp     rcx, r14
0x18001c7ba  jz      loc_18001C669
0x18001c7c0  test    byte ptr [rcx+1Ch], 1
0x18001c7c4  jz      loc_18001C669
0x18001c7ca  mov     rcx, [rcx+10h]
0x18001c7ce  lea     r9, aHrvalidateacti; "HrValidateActionList(): Exiting"
0x18001c7d5  mov     edx, 1Bh
0x18001c7da  mov     [rsp+20h], ebx
0x18001c7de  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x18001c7e5  call    WPP_SF_sd
0x18001c7ea  jmp     loc_18001C669
```
