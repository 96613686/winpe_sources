# AppendNewLine(IXMLDOMDocument2 *,IXMLDOMNode *,ulong)

- ea: `0x180039cc0`
- end: `0x180039ecd`
- name: `?AppendNewLine@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@K@Z`
- size: `525`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003a880`
- `0x18003b31c`

## callees

- `0x1800241bb`
- `0x18002cd00`
- `0x180039cc0`
- `0x18003d9b0`
- `0x180042a80`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180039d49`
- `msvcrt!wcscat_s` at `0x180039d49`
- `msvcrt!wcscpy_s` at `0x180039d2c`
- `msvcrt!wcscpy_s` at `0x180039d2c`
- `OLEAUT32!__imp_SysAllocString` at `0x180039d5a`
- `OLEAUT32!__imp_SysAllocString` at `0x180039d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180039e9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180039e9e`

## string_xrefs

- `0x180039da7`: `pXmlDom->createNode failed with 0x%x`
- `0x180039e2a`: `pRegistryKeysNode->appendChild failed with 0x%x`

## pseudocode

```c
__int64 __fastcall AppendNewLine(struct IXMLDOMDocument2 *a1, struct IXMLDOMNode *a2, unsigned int a3)
{
  unsigned int i; // ebx
  OLECHAR *v7; // rsi
  int v8; // ebx
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  v11 = 0;
  v10 = 0;
  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, L"\n");
  for ( i = 0; i < a3; ++i )
    wcscat_s(Destination, 0x104u, L"\t");
  v7 = SysAllocString(Destination);
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))a1->lpVtbl->createTextNode)(
         a1,
         v7,
         &v10);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))a2->lpVtbl->appendChild)(a2, v10, &v11);
    if ( v8 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pRegistryKeysNode->appendChild failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        v8);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pXmlDom->createNode failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        v8);
    }
    TraceXMLFailure(a1);
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  SysFreeString(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039cc0  mov     [rsp-8+arg_10], rbx
0x180039cc5  mov     [rsp-8+arg_18], rsi
0x180039cca  push    rbp
0x180039ccb  push    rdi
0x180039ccc  push    r14
0x180039cce  lea     rbp, [rsp-160h]
0x180039cd6  sub     rsp, 260h
0x180039cdd  mov     rax, cs:__security_cookie
0x180039ce4  xor     rax, rsp
0x180039ce7  mov     [rbp+170h+var_20], rax
0x180039cee  mov     esi, r8d
0x180039cf1  mov     [rsp+270h+var_238], 0
0x180039cfa  mov     r14, rdx
0x180039cfd  mov     [rsp+270h+var_240], 0
0x180039d06  mov     rdi, rcx
0x180039d09  xor     edx, edx; Val
0x180039d0b  mov     r8d, 208h; Size
0x180039d11  lea     rcx, [rsp+270h+Destination]; void *
0x180039d16  call    memset_0
0x180039d1b  lea     r8, asc_180064360; "\n"
0x180039d22  mov     edx, 104h; SizeInWords
0x180039d27  lea     rcx, [rsp+270h+Destination]; Destination
0x180039d2c  call    cs:__imp_wcscpy_s
0x180039d32  xor     ebx, ebx
0x180039d34  test    esi, esi
0x180039d36  jz      short loc_180039D55
0x180039d38  lea     r8, asc_180064364; "\t"
0x180039d3f  mov     edx, 104h; SizeInWords
0x180039d44  lea     rcx, [rsp+270h+Destination]; Destination
0x180039d49  call    cs:__imp_wcscat_s
0x180039d4f  inc     ebx
0x180039d51  cmp     ebx, esi
0x180039d53  jb      short loc_180039D38
0x180039d55  lea     rcx, [rsp+270h+Destination]; psz
0x180039d5a  call    cs:__imp_SysAllocString
0x180039d60  mov     rcx, [rdi]
0x180039d63  lea     r8, [rsp+270h+var_240]
0x180039d68  mov     rsi, rax
0x180039d6b  mov     rdx, rsi
0x180039d6e  mov     rax, [rcx+188h]
0x180039d75  mov     rcx, rdi
0x180039d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d7d  mov     ebx, eax
0x180039d7f  test    eax, eax
0x180039d81  jns     short loc_180039DE4
0x180039d83  mov     rax, cs:WPP_GLOBAL_Control
0x180039d8a  lea     rcx, WPP_GLOBAL_Control
0x180039d91  cmp     rax, rcx
0x180039d94  jz      short loc_180039DDA
0x180039d96  cmp     byte ptr [rax+19h], 2
0x180039d9a  jb      short loc_180039DDA
0x180039d9c  test    dword ptr [rax+1Ch], 400h
0x180039da3  jz      short loc_180039DDA
0x180039da5  mov     edx, ebx
0x180039da7  lea     rcx, aPxmldomCreaten; "pXmlDom->createNode failed with 0x%x"
0x180039dae  call    WppDbgPrint
0x180039db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dba  lea     r9, aNpssdo; "NPSSDO"
0x180039dc1  mov     edx, 12h
0x180039dc6  mov     [rsp+270h+var_250], ebx
0x180039dca  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x180039dd1  mov     rcx, [rcx+10h]
0x180039dd5  call    WPP_SF_sd
0x180039dda  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180039ddd  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x180039de2  jmp     short loc_180039E5D
0x180039de4  mov     rax, [r14]
0x180039de7  lea     r8, [rsp+270h+var_238]
0x180039dec  mov     rdx, [rsp+270h+var_240]
0x180039df1  mov     rcx, r14
0x180039df4  mov     rax, [rax+0A8h]
0x180039dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e00  mov     ebx, eax
0x180039e02  test    eax, eax
0x180039e04  jns     short loc_180039E5D
0x180039e06  mov     rax, cs:WPP_GLOBAL_Control
0x180039e0d  lea     rcx, WPP_GLOBAL_Control
0x180039e14  cmp     rax, rcx
0x180039e17  jz      short loc_180039E5D
0x180039e19  cmp     byte ptr [rax+19h], 2
0x180039e1d  jb      short loc_180039E5D
0x180039e1f  test    dword ptr [rax+1Ch], 400h
0x180039e26  jz      short loc_180039E5D
0x180039e28  mov     edx, ebx
0x180039e2a  lea     rcx, aPregistrykeysn_0; "pRegistryKeysNode->appendChild failed w"...
0x180039e31  call    WppDbgPrint
0x180039e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e3d  lea     r9, aNpssdo; "NPSSDO"
0x180039e44  mov     edx, 13h
0x180039e49  mov     [rsp+270h+var_250], ebx
0x180039e4d  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x180039e54  mov     rcx, [rcx+10h]
0x180039e58  call    WPP_SF_sd
0x180039e5d  mov     rcx, [rsp+270h+var_240]
0x180039e62  test    rcx, rcx
0x180039e65  jz      short loc_180039E7C
0x180039e67  mov     rax, [rcx]
0x180039e6a  mov     rax, [rax+10h]
0x180039e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e73  mov     [rsp+270h+var_240], 0
0x180039e7c  mov     rcx, [rsp+270h+var_238]
0x180039e81  test    rcx, rcx
0x180039e84  jz      short loc_180039E9B
0x180039e86  mov     rax, [rcx]
0x180039e89  mov     rax, [rax+10h]
0x180039e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e92  mov     [rsp+270h+var_238], 0
0x180039e9b  mov     rcx, rsi; bstrString
0x180039e9e  call    cs:__imp_SysFreeString
0x180039ea4  mov     eax, ebx
0x180039ea6  mov     rcx, [rbp+170h+var_20]
0x180039ead  xor     rcx, rsp; StackCookie
0x180039eb0  call    __security_check_cookie
0x180039eb5  lea     r11, [rsp+270h+var_10]
0x180039ebd  mov     rbx, [r11+30h]
0x180039ec1  mov     rsi, [r11+38h]
0x180039ec5  mov     rsp, r11
0x180039ec8  pop     r14
0x180039eca  pop     rdi
0x180039ecb  pop     rbp
0x180039ecc  retn
```
