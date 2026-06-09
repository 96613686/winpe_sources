# HrValidateActionList(IXMLDOMNode *,IXMLDOMNode *,ushort * *)

- ea: `0x180009eb0`
- end: `0x18000a36a`
- name: `?HrValidateActionList@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z`
- size: `1210`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010800`

## callees

- `0x180009ae0`
- `0x180009eb0`
- `0x18000a370`
- `0x18000db4c`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000a154`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18000a154`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000a16b`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18000a16b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a12b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a12b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a08e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a099`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a08e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a099`

## string_xrefs

- `0x180009fde`: `urn:schemas-upnp-org:service-1-`

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
0x180009eb0  mov     r11, rsp
0x180009eb3  push    rbp
0x180009eb4  push    rbx
0x180009eb5  lea     rbp, [r11-3A8h]
0x180009ebc  sub     rsp, 498h
0x180009ec3  mov     rax, cs:__security_cookie
0x180009eca  xor     rax, rsp
0x180009ecd  mov     [rbp+3A0h+var_40], rax
0x180009ed4  mov     rax, [rcx]
0x180009ed7  mov     [r11+20h], rsi
0x180009edb  xor     esi, esi
0x180009edd  mov     [r11-18h], rdi
0x180009ee1  mov     [r11-20h], r12
0x180009ee5  mov     r12, rdx
0x180009ee8  mov     rax, [rax+68h]
0x180009eec  lea     rdx, [rsp+4A0h+var_468]
0x180009ef1  mov     [r11-28h], r13
0x180009ef5  mov     r13, rcx
0x180009ef8  mov     [r11-38h], r15
0x180009efc  mov     r15d, esi
0x180009eff  mov     [rsp+4A0h+var_448], r8
0x180009f04  mov     [rsp+4A0h+var_458], rsi
0x180009f09  mov     [rsp+4A0h+var_468], rsi
0x180009f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f13  mov     rdi, [rsp+4A0h+var_468]
0x180009f18  mov     ebx, eax
0x180009f1a  mov     [rsp+4A0h+var_28], r14
0x180009f22  test    ebx, ebx
0x180009f24  js      loc_18000A199
0x180009f2a  test    rdi, rdi
0x180009f2d  jz      loc_18000A2CA
0x180009f33  mov     [rsp+4A0h+var_450], rsi
0x180009f38  lea     rdx, [rsp+4A0h+var_460]
0x180009f3d  mov     rax, [rdi]
0x180009f40  mov     rcx, rdi
0x180009f43  mov     [rsp+4A0h+var_460], rsi
0x180009f48  mov     r14d, esi
0x180009f4b  mov     [rsp+4A0h+bstrString], rsi
0x180009f50  mov     rax, [rax+148h]
0x180009f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f5c  mov     ebx, eax
0x180009f5e  test    eax, eax
0x180009f60  js      loc_18000A09F
0x180009f66  cmp     [rsp+4A0h+var_460], 0
0x180009f6c  jz      loc_18000A09F
0x180009f72  mov     rax, [rdi]
0x180009f75  lea     rdx, [rsp+4A0h+bstrString]
0x180009f7a  mov     rcx, rdi
0x180009f7d  mov     rax, [rax+138h]
0x180009f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f89  mov     ebx, eax
0x180009f8b  test    eax, eax
0x180009f8d  js      loc_18000A094
0x180009f93  mov     r10, [rsp+4A0h+bstrString]
0x180009f98  test    r10, r10
0x180009f9b  jz      loc_18000A094
0x180009fa1  mov     ecx, 7FFFFFFFh
0x180009fa6  mov     rax, r10
0x180009fa9  nop     dword ptr [rax+00000000h]
0x180009fb0  cmp     word ptr [rax], 0
0x180009fb4  jz      short loc_180009FC7
0x180009fb6  add     rax, 2
0x180009fba  sub     rcx, 1
0x180009fbe  jnz     short loc_180009FB0
0x180009fc0  mov     ebx, 80070057h
0x180009fc5  jmp     short loc_180009FD1
0x180009fc7  mov     esi, 7FFFFFFFh
0x180009fcc  sub     rsi, rcx
0x180009fcf  xor     ebx, ebx
0x180009fd1  test    ebx, ebx
0x180009fd3  js      loc_18000A27D
0x180009fd9  mov     ecx, 1Fh
0x180009fde  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180009fe5  mov     r8d, 100h
0x180009feb  lea     r9, [rbp+3A0h+String1]
0x180009ff2  test    rcx, rcx
0x180009ff5  jz      short loc_18000A014
0x180009ff7  movzx   eax, word ptr [rdx]
0x180009ffa  test    ax, ax
0x180009ffd  jz      short loc_18000A014
0x180009fff  mov     [r9], ax
0x18000a003  add     rdx, 2
0x18000a007  add     r9, 2
0x18000a00b  dec     rcx
0x18000a00e  sub     r8, 1
0x18000a012  jnz     short loc_180009FF2
0x18000a014  test    r8, r8
0x18000a017  lea     rcx, [r9-2]
0x18000a01b  mov     ebx, 8007007Ah
0x18000a020  cmovnz  rcx, r9
0x18000a024  xor     eax, eax
0x18000a026  test    r8, r8
0x18000a029  cmovnz  ebx, eax
0x18000a02c  mov     [rcx], ax
0x18000a02f  test    ebx, ebx
0x18000a031  js      short loc_18000A089
0x18000a033  mov     ecx, 1Fh
0x18000a038  lea     r9, [rsp+4A0h+String2]
0x18000a03d  mov     rdx, r10
0x18000a040  mov     r8d, 100h
0x18000a046  test    rcx, rcx
0x18000a049  jz      short loc_18000A068
0x18000a04b  movzx   eax, word ptr [rdx]
0x18000a04e  test    ax, ax
0x18000a051  jz      short loc_18000A068
0x18000a053  mov     [r9], ax
0x18000a057  add     rdx, 2
0x18000a05b  add     r9, 2
0x18000a05f  dec     rcx
0x18000a062  sub     r8, 1
0x18000a066  jnz     short loc_18000A046
0x18000a068  test    r8, r8
0x18000a06b  lea     rcx, [r9-2]
0x18000a06f  mov     ebx, 8007007Ah
0x18000a074  cmovnz  rcx, r9
0x18000a078  xor     eax, eax
0x18000a07a  test    r8, r8
0x18000a07d  cmovnz  ebx, eax
0x18000a080  mov     [rcx], ax
0x18000a083  jnz     loc_18000A109
0x18000a089  xor     esi, esi
0x18000a08b  mov     rcx, r10; bstrString
0x18000a08e  call    cs:__imp_SysFreeString
0x18000a094  mov     rcx, [rsp+4A0h+var_460]; bstrString
0x18000a099  call    cs:__imp_SysFreeString
0x18000a09f  test    ebx, ebx
0x18000a0a1  jnz     loc_18000A284
0x18000a0a7  test    r14d, r14d
0x18000a0aa  jz      short loc_18000A0CE
0x18000a0ac  mov     rcx, [rsp+4A0h+var_468]; struct IXMLDOMNode *
0x18000a0b1  lea     r8, [rsp+4A0h+var_458]; unsigned __int16 **
0x18000a0b6  mov     rdx, r12; struct IXMLDOMNode *
0x18000a0b9  call    ?HrValidateAction@@YAJPEAUIXMLDOMNode@@0PEAPEAG@Z; HrValidateAction(IXMLDOMNode *,IXMLDOMNode *,ushort * *)
0x18000a0be  mov     ebx, eax
0x18000a0c0  mov     r15d, 1
0x18000a0c6  test    eax, eax
0x18000a0c8  js      loc_18000A188
0x18000a0ce  mov     rcx, [rsp+4A0h+var_468]
0x18000a0d3  lea     rdx, [rsp+4A0h+var_450]
0x18000a0d8  mov     rax, [rcx]
0x18000a0db  mov     rax, [rax+80h]
0x18000a0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e7  mov     rcx, [rsp+4A0h+var_468]
0x18000a0ec  mov     ebx, eax
0x18000a0ee  mov     rax, [rcx]
0x18000a0f1  mov     rax, [rax+10h]
0x18000a0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fa  mov     rdi, [rsp+4A0h+var_450]
0x18000a0ff  mov     [rsp+4A0h+var_468], rdi
0x18000a104  jmp     loc_180009F22
0x18000a109  mov     rcx, [rsp+4A0h+var_460]; lpString1
0x18000a10e  lea     rdx, aAction; "action"
0x18000a115  call    cs:__imp_lstrcmpW
0x18000a11b  test    eax, eax
0x18000a11d  jnz     short loc_18000A17E
0x18000a11f  lea     rdx, [rsp+4A0h+String2]; lpString2
0x18000a124  lea     rcx, [rbp+3A0h+String1]; lpString1
0x18000a12b  call    cs:__imp_lstrcmpW
0x18000a131  test    eax, eax
0x18000a133  jnz     short loc_18000A17E
0x18000a135  mov     r14d, 1
0x18000a13b  cmp     rsi, 1Fh
0x18000a13f  jbe     short loc_18000A17E
0x18000a141  mov     edi, 1Fh
0x18000a146  cmp     rdi, rsi
0x18000a149  jnb     short loc_18000A17E
0x18000a14b  mov     rcx, [rsp+4A0h+bstrString]
0x18000a150  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18000a154  call    cs:__imp_IsCharAlphaNumericW
0x18000a15a  test    eax, eax
0x18000a15c  jz      loc_18000A208
0x18000a162  mov     rcx, [rsp+4A0h+bstrString]
0x18000a167  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x18000a16b  call    cs:__imp_IsCharAlphaW
0x18000a171  test    eax, eax
0x18000a173  jnz     loc_18000A208
0x18000a179  inc     rdi
0x18000a17c  jmp     short loc_18000A146
0x18000a17e  mov     r10, [rsp+4A0h+bstrString]
0x18000a183  jmp     loc_18000A089
0x18000a188  mov     rcx, [rsp+4A0h+var_468]
0x18000a18d  mov     rax, [rcx]
0x18000a190  mov     rax, [rax+10h]
0x18000a194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a199  lea     r14, WPP_GLOBAL_Control
0x18000a1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1a7  mov     rax, [rsp+4A0h+var_458]
0x18000a1ac  mov     r15, [rsp+4A0h+var_30]
0x18000a1b4  mov     r13, [rsp+4A0h+var_20]
0x18000a1bc  mov     r12, [rsp+4A0h+var_18]
0x18000a1c4  mov     rdi, [rsp+490h]
0x18000a1cc  mov     rsi, [rsp+4A0h+arg_18]
0x18000a1d4  test    rax, rax
0x18000a1d7  jnz     loc_18000A31E
0x18000a1dd  test    ebx, ebx
0x18000a1df  jnz     loc_18000A332
0x18000a1e5  mov     r14, [rsp+4A0h+var_28]
0x18000a1ed  mov     eax, ebx
0x18000a1ef  mov     rcx, [rbp+3A0h+var_40]
0x18000a1f6  xor     rcx, rsp; StackCookie
0x18000a1f9  call    __security_check_cookie
0x18000a1fe  add     rsp, 498h
0x18000a205  pop     rbx
0x18000a206  pop     rbp
0x18000a207  retn
0x18000a208  mov     r10, [rsp+4A0h+bstrString]
0x18000a20d  xor     esi, esi
0x18000a20f  mov     r14d, esi
0x18000a212  jmp     loc_18000A08B
0x18000a217  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x18000a21c  xor     r8d, r8d; unsigned __int16 *
0x18000a21f  lea     rdx, aActionlistDidN; "<actionList> did not contain any <actio"...
0x18000a226  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000a22b  mov     ebx, eax
0x18000a22d  test    eax, eax
0x18000a22f  js      loc_18000A199
0x18000a235  lea     r9, [rsp+4A0h+bstrString]; int *
0x18000a23a  mov     dword ptr [rsp+4A0h+bstrString], esi
0x18000a23e  lea     rdx, aScpdActionScpd; "scpd:action/scpd:name"
0x18000a245  mov     rcx, r13; struct IXMLDOMNode *
0x18000a248  call    ?HrAreThereDuplicatesInChildNodeTextValues@@YAJPEAUIXMLDOMNode@@PEBGHPEAH@Z; HrAreThereDuplicatesInChildNodeTextValues(IXMLDOMNode *,ushort const *,int,int *)
0x18000a24d  mov     ebx, eax
0x18000a24f  test    eax, eax
0x18000a251  js      loc_18000A2D8
0x18000a257  cmp     dword ptr [rsp+4A0h+bstrString], 0
0x18000a25c  jz      loc_18000A199
0x18000a262  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x18000a267  xor     r8d, r8d; unsigned __int16 *
0x18000a26a  lea     rdx, aActionlistCont; "<actionList> contained <action> element"...
0x18000a271  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x18000a276  mov     ebx, eax
0x18000a278  jmp     loc_18000A199
0x18000a27d  xor     esi, esi
0x18000a27f  jmp     loc_18000A02F
0x18000a284  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a28b  lea     rax, WPP_GLOBAL_Control
0x18000a292  cmp     rcx, rax
0x18000a295  jz      loc_18000A0A7
0x18000a29b  test    byte ptr [rcx+1Ch], 1
0x18000a29f  jz      loc_18000A0A7
0x18000a2a5  mov     rcx, [rcx+10h]
0x18000a2a9  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x18000a2b0  mov     edx, 14h
0x18000a2b5  mov     [rsp+20h], ebx
0x18000a2b9  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a2c0  call    WPP_SF_sd
0x18000a2c5  jmp     loc_18000A0A7
0x18000a2ca  test    r15d, r15d
0x18000a2cd  jnz     loc_18000A235
0x18000a2d3  jmp     loc_18000A217
0x18000a2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2df  lea     r14, WPP_GLOBAL_Control
0x18000a2e6  cmp     rcx, r14
0x18000a2e9  jz      loc_18000A1A7
0x18000a2ef  test    byte ptr [rcx+1Ch], 1
0x18000a2f3  jz      loc_18000A1A7
0x18000a2f9  mov     rcx, [rcx+10h]
0x18000a2fd  lea     r9, aHrvalidateacti_1; "HrValidateActionList(): Failed to check"...
0x18000a304  mov     edx, 1Ah
0x18000a309  mov     [rsp+20h], eax
0x18000a30d  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x18000a314  call    WPP_SF_sd
0x18000a319  jmp     loc_18000A1A0
0x18000a31e  mov     rcx, [rsp+4A0h+var_448]
0x18000a323  mov     [rcx], rax
0x18000a326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a32d  jmp     loc_18000A1DD
0x18000a332  cmp     rcx, r14
0x18000a335  jz      loc_18000A1E5
0x18000a33b  test    byte ptr [rcx+1Ch], 1
0x18000a33f  jz      loc_18000A1E5
0x18000a345  mov     rcx, [rcx+10h]
0x18000a349  lea     r9, aHrvalidateacti; "HrValidateActionList(): Exiting"
0x18000a350  mov     edx, 1Bh
0x18000a355  mov     [rsp+20h], ebx
0x18000a359  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x18000a360  call    WPP_SF_sd
0x18000a365  jmp     loc_18000A1E5
```
