# HrValidateSST(IXMLDOMNode *,ushort * *)

- ea: `0x180001c20`
- end: `0x1800020db`
- name: `?HrValidateSST@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `1211`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800047a0`

## callees

- `0x180001c20`
- `0x1800020f0`
- `0x18001bf10`
- `0x1800200f4`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180001ef0`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180001ef0`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180001f09`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180001f09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180001ea5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180001ec1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180001ea5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180001ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e26`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e26`

## string_xrefs

- `0x180001d60`: `urn:schemas-upnp-org:service-1-`
- `0x180001fa6`: `<serviceStateTable> did not contain any <stateVariable> elements`
- `0x180001fed`: `<serviceStateTable> contained <stateVariable> elements with duplicate names`

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
0x180001c20  mov     r11, rsp
0x180001c23  push    rbp
0x180001c24  push    rbx
0x180001c25  push    rsi
0x180001c26  lea     rbp, [r11-3A8h]
0x180001c2d  sub     rsp, 490h
0x180001c34  mov     rax, cs:__security_cookie
0x180001c3b  xor     rax, rsp
0x180001c3e  mov     [rbp+3A0h+var_40], rax
0x180001c45  mov     rax, [rcx]
0x180001c48  mov     [r11+18h], rdi
0x180001c4c  mov     [r11-20h], r12
0x180001c50  mov     r12, rcx
0x180001c53  mov     [r11-28h], r13
0x180001c57  mov     r13, rdx
0x180001c5a  mov     rax, [rax+68h]
0x180001c5e  lea     rdx, [rsp+4A0h+var_468]
0x180001c63  mov     [r11-38h], r15
0x180001c67  xor     r15d, r15d
0x180001c6a  mov     [rsp+4A0h+var_458], 0
0x180001c73  mov     [rsp+4A0h+var_468], 0
0x180001c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c81  mov     rdi, [rsp+4A0h+var_468]
0x180001c86  lea     rsi, WPP_GLOBAL_Control
0x180001c8d  mov     ebx, eax
0x180001c8f  mov     [rsp+4A0h+var_28], r14
0x180001c97  test    ebx, ebx
0x180001c99  js      loc_180001F3C
0x180001c9f  test    rdi, rdi
0x180001ca2  jz      loc_180002046
0x180001ca8  mov     [rsp+4A0h+var_450], 0
0x180001cb1  lea     rdx, [rsp+4A0h+var_460]
0x180001cb6  mov     rax, [rdi]
0x180001cb9  mov     rcx, rdi
0x180001cbc  mov     [rsp+4A0h+var_460], 0
0x180001cc5  xor     r14d, r14d
0x180001cc8  mov     [rsp+4A0h+bstrString], 0
0x180001cd1  mov     rax, [rax+148h]
0x180001cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cdd  mov     ebx, eax
0x180001cdf  test    eax, eax
0x180001ce1  js      loc_180001E32
0x180001ce7  cmp     [rsp+4A0h+var_460], r14
0x180001cec  jz      loc_180001E32
0x180001cf2  mov     rax, [rdi]
0x180001cf5  lea     rdx, [rsp+4A0h+bstrString]
0x180001cfa  mov     rcx, rdi
0x180001cfd  mov     rax, [rax+138h]
0x180001d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d09  mov     ebx, eax
0x180001d0b  test    eax, eax
0x180001d0d  js      loc_180001E21
0x180001d13  mov     r10, [rsp+4A0h+bstrString]
0x180001d18  test    r10, r10
0x180001d1b  jz      loc_180001E21
0x180001d21  mov     ecx, 7FFFFFFFh
0x180001d26  mov     rax, r10
0x180001d29  nop     dword ptr [rax+00000000h]
0x180001d30  cmp     [rax], r14w
0x180001d34  jz      short loc_180001D49
0x180001d36  add     rax, 2
0x180001d3a  sub     rcx, 1
0x180001d3e  jnz     short loc_180001D30
0x180001d40  xor     esi, esi
0x180001d42  mov     ebx, 80070057h
0x180001d47  jmp     short loc_180001D53
0x180001d49  mov     esi, 7FFFFFFFh
0x180001d4e  sub     rsi, rcx
0x180001d51  xor     ebx, ebx
0x180001d53  test    ebx, ebx
0x180001d55  js      loc_180002000
0x180001d5b  mov     ecx, 1Fh
0x180001d60  lea     rdx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180001d67  mov     r8d, 100h
0x180001d6d  lea     r9, [rbp+3A0h+String1]
0x180001d74  test    rcx, rcx
0x180001d77  jz      short loc_180001D96
0x180001d79  movzx   eax, word ptr [rdx]
0x180001d7c  test    ax, ax
0x180001d7f  jz      short loc_180001D96
0x180001d81  mov     [r9], ax
0x180001d85  add     rdx, 2
0x180001d89  add     r9, 2
0x180001d8d  dec     rcx
0x180001d90  sub     r8, 1
0x180001d94  jnz     short loc_180001D74
0x180001d96  test    r8, r8
0x180001d99  lea     rcx, [r9-2]
0x180001d9d  mov     ebx, 8007007Ah
0x180001da2  cmovnz  rcx, r9
0x180001da6  xor     eax, eax
0x180001da8  test    r8, r8
0x180001dab  cmovnz  ebx, eax
0x180001dae  mov     [rcx], ax
0x180001db1  test    ebx, ebx
0x180001db3  js      short loc_180001E0B
0x180001db5  mov     ecx, 1Fh
0x180001dba  lea     r9, [rsp+4A0h+String2]
0x180001dbf  mov     rdx, r10
0x180001dc2  mov     r8d, 100h
0x180001dc8  test    rcx, rcx
0x180001dcb  jz      short loc_180001DEA
0x180001dcd  movzx   eax, word ptr [rdx]
0x180001dd0  test    ax, ax
0x180001dd3  jz      short loc_180001DEA
0x180001dd5  mov     [r9], ax
0x180001dd9  add     rdx, 2
0x180001ddd  add     r9, 2
0x180001de1  dec     rcx
0x180001de4  sub     r8, 1
0x180001de8  jnz     short loc_180001DC8
0x180001dea  test    r8, r8
0x180001ded  lea     rcx, [r9-2]
0x180001df1  mov     ebx, 8007007Ah
0x180001df6  cmovnz  rcx, r9
0x180001dfa  xor     eax, eax
0x180001dfc  test    r8, r8
0x180001dff  cmovnz  ebx, eax
0x180001e02  mov     [rcx], ax
0x180001e05  jnz     loc_180001E99
0x180001e0b  mov     rcx, r10; bstrString
0x180001e0e  call    cs:__imp_SysFreeString
0x180001e15  nop     dword ptr [rax+rax+00h]
0x180001e1a  lea     rsi, WPP_GLOBAL_Control
0x180001e21  mov     rcx, [rsp+4A0h+var_460]; bstrString
0x180001e26  call    cs:__imp_SysFreeString
0x180001e2d  nop     dword ptr [rax+rax+00h]
0x180001e32  test    ebx, ebx
0x180001e34  jnz     loc_180002007
0x180001e3a  test    r14d, r14d
0x180001e3d  jz      short loc_180001E5E
0x180001e3f  mov     rcx, [rsp+4A0h+var_468]; struct IXMLDOMNode *
0x180001e44  lea     rdx, [rsp+4A0h+var_458]; unsigned __int16 **
0x180001e49  call    ?HrValidateStateVariable@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z; HrValidateStateVariable(IXMLDOMNode *,ushort * *)
0x180001e4e  mov     ebx, eax
0x180001e50  mov     r15d, 1
0x180001e56  test    eax, eax
0x180001e58  js      loc_180001F2B
0x180001e5e  mov     rcx, [rsp+4A0h+var_468]
0x180001e63  lea     rdx, [rsp+4A0h+var_450]
0x180001e68  mov     rax, [rcx]
0x180001e6b  mov     rax, [rax+80h]
0x180001e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e77  mov     rcx, [rsp+4A0h+var_468]
0x180001e7c  mov     ebx, eax
0x180001e7e  mov     rax, [rcx]
0x180001e81  mov     rax, [rax+10h]
0x180001e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e8a  mov     rdi, [rsp+4A0h+var_450]
0x180001e8f  mov     [rsp+4A0h+var_468], rdi
0x180001e94  jmp     loc_180001C97
0x180001e99  mov     rcx, [rsp+4A0h+var_460]; lpString1
0x180001e9e  lea     rdx, String2; "stateVariable"
0x180001ea5  call    cs:__imp_lstrcmpW
0x180001eac  nop     dword ptr [rax+rax+00h]
0x180001eb1  test    eax, eax
0x180001eb3  jnz     short loc_180001F21
0x180001eb5  lea     rdx, [rsp+4A0h+String2]; lpString2
0x180001eba  lea     rcx, [rbp+3A0h+String1]; lpString1
0x180001ec1  call    cs:__imp_lstrcmpW
0x180001ec8  nop     dword ptr [rax+rax+00h]
0x180001ecd  test    eax, eax
0x180001ecf  jnz     short loc_180001F21
0x180001ed1  mov     r14d, 1
0x180001ed7  cmp     rsi, 1Fh
0x180001edb  jbe     short loc_180001F21
0x180001edd  mov     edi, 1Fh
0x180001ee2  cmp     rdi, rsi
0x180001ee5  jnb     short loc_180001F21
0x180001ee7  mov     rcx, [rsp+4A0h+bstrString]
0x180001eec  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x180001ef0  call    cs:__imp_IsCharAlphaNumericW
0x180001ef7  nop     dword ptr [rax+rax+00h]
0x180001efc  test    eax, eax
0x180001efe  jz      short loc_180001F1E
0x180001f00  mov     rcx, [rsp+4A0h+bstrString]
0x180001f05  movzx   ecx, word ptr [rcx+rdi*2]; ch
0x180001f09  call    cs:__imp_IsCharAlphaW
0x180001f10  nop     dword ptr [rax+rax+00h]
0x180001f15  test    eax, eax
0x180001f17  jnz     short loc_180001F1E
0x180001f19  inc     rdi
0x180001f1c  jmp     short loc_180001EE2
0x180001f1e  xor     r14d, r14d
0x180001f21  mov     r10, [rsp+4A0h+bstrString]
0x180001f26  jmp     loc_180001E0B
0x180001f2b  mov     rcx, [rsp+4A0h+var_468]
0x180001f30  mov     rax, [rcx]
0x180001f33  mov     rax, [rax+10h]
0x180001f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f43  mov     rax, [rsp+4A0h+var_458]
0x180001f48  mov     r15, [rsp+4A0h+var_30]
0x180001f50  mov     r14, [rsp+4A0h+var_28]
0x180001f58  mov     r12, [rsp+4A0h+var_18]
0x180001f60  mov     rdi, [rsp+4A0h+arg_10]
0x180001f68  test    rax, rax
0x180001f6b  jnz     loc_180002093
0x180001f71  mov     r13, [rsp+4A0h+var_20]
0x180001f79  test    ebx, ebx
0x180001f7b  jnz     loc_1800020A3
0x180001f81  mov     eax, ebx
0x180001f83  mov     rcx, [rbp+3A0h+var_40]
0x180001f8a  xor     rcx, rsp; StackCookie
0x180001f8d  call    __security_check_cookie
0x180001f92  add     rsp, 490h
0x180001f99  pop     rsi
0x180001f9a  pop     rbx
0x180001f9b  pop     rbp
0x180001f9c  retn
0x180001f9e  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x180001fa3  xor     r8d, r8d; unsigned __int16 *
0x180001fa6  lea     rdx, aServicestateta_1; "<serviceStateTable> did not contain any"...
0x180001fad  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x180001fb2  mov     ebx, eax
0x180001fb4  test    eax, eax
0x180001fb6  js      short loc_180001F3C
0x180001fb8  lea     r9, [rsp+4A0h+bstrString]; int *
0x180001fbd  mov     dword ptr [rsp+4A0h+bstrString], 0
0x180001fc5  lea     rdx, aScpdStatevaria; "scpd:stateVariable/scpd:name"
0x180001fcc  mov     rcx, r12; struct IXMLDOMNode *
0x180001fcf  call    ?HrAreThereDuplicatesInChildNodeTextValues@@YAJPEAUIXMLDOMNode@@PEBGHPEAH@Z; HrAreThereDuplicatesInChildNodeTextValues(IXMLDOMNode *,ushort const *,int,int *)
0x180001fd4  mov     ebx, eax
0x180001fd6  test    eax, eax
0x180001fd8  js      short loc_180002054
0x180001fda  cmp     dword ptr [rsp+4A0h+bstrString], 0
0x180001fdf  jz      loc_180001F3C
0x180001fe5  lea     r9, [rsp+4A0h+var_458]; unsigned __int16 **
0x180001fea  xor     r8d, r8d; unsigned __int16 *
0x180001fed  lea     rdx, aServicestateta_0; "<serviceStateTable> contained <stateVar"...
0x180001ff4  call    ?HrAllocErrorStringAndReturnHr@@YAJJPEBG0PEAPEAG@Z; HrAllocErrorStringAndReturnHr(long,ushort const *,ushort const *,ushort * *)
0x180001ff9  mov     ebx, eax
0x180001ffb  jmp     loc_180001F3C
0x180002000  xor     esi, esi
0x180002002  jmp     loc_180001DB1
0x180002007  mov     rcx, cs:WPP_GLOBAL_Control
0x18000200e  cmp     rcx, rsi
0x180002011  jz      loc_180001E3A
0x180002017  test    byte ptr [rcx+1Ch], 1
0x18000201b  jz      loc_180001E3A
0x180002021  mov     rcx, [rcx+10h]
0x180002025  lea     r9, aFisthisthenode; "FIsThisTheNodeNameWithNamespace(): Exit"...
0x18000202c  mov     edx, 14h
0x180002031  mov     [rsp+4A0h+var_480], ebx
0x180002035  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000203c  call    WPP_SF_sd
0x180002041  jmp     loc_180001E3A
0x180002046  test    r15d, r15d
0x180002049  jnz     loc_180001FB8
0x18000204f  jmp     loc_180001F9E
0x180002054  mov     rcx, cs:WPP_GLOBAL_Control
0x18000205b  cmp     rcx, rsi
0x18000205e  jz      loc_180001F43
0x180002064  test    byte ptr [rcx+1Ch], 1
0x180002068  jz      loc_180001F43
0x18000206e  mov     rcx, [rcx+10h]
0x180002072  lea     r9, aHrvalidatesstF; "HrValidateSST(): Failed to check for du"...
0x180002079  mov     edx, 24h ; '$'
0x18000207e  mov     [rsp+4A0h+var_480], eax
0x180002082  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x180002089  call    WPP_SF_sd
0x18000208e  jmp     loc_180001F3C
0x180002093  mov     [r13+0], rax
0x180002097  mov     rcx, cs:WPP_GLOBAL_Control
0x18000209e  jmp     loc_180001F71
0x1800020a3  cmp     rcx, rsi
0x1800020a6  jz      loc_180001F81
0x1800020ac  test    byte ptr [rcx+1Ch], 1
0x1800020b0  jz      loc_180001F81
0x1800020b6  mov     rcx, [rcx+10h]
0x1800020ba  lea     r9, aHrvalidatesstE; "HrValidateSST(): Exiting"
0x1800020c1  mov     edx, 25h ; '%'
0x1800020c6  mov     [rsp+4A0h+var_480], ebx
0x1800020ca  lea     r8, WPP_b522c78dcf6c3de65204eee127e73824_Traceguids
0x1800020d1  call    WPP_SF_sd
0x1800020d6  jmp     loc_180001F81
```
