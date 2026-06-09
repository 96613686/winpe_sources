# CSpRegistryXMLLoader::ProcessXMLCategoryChildren(HKEY__ *,IXMLDOMNode *,int *,int)

- ea: `0x180016c90`
- end: `0x180017065`
- name: `?ProcessXMLCategoryChildren@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@PEAHH@Z`
- size: `981`
- prototype: `__int64 __usercall@<rax>(CSpRegistryXMLLoader *__hidden this@<rcx>, HKEY@<rdx>, struct IXMLDOMNode *@<r8>, int *@<r9>, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800667b0`

## callees

- `0x18000f080`
- `0x180016c90`
- `0x180017070`
- `0x1800171c0`
- `0x180017610`
- `0x1800177e0`
- `0x18003ce60`
- `0x180079e30`
- `0x1800fefe8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016dd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016e19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016fbe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016dd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016e19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180016fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180016ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180017001`
- `OLEAUT32!__imp_SysFreeString` at `0x180016ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180017001`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016f55`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016f55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016eb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016eb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f9b`

## string_xrefs

- `0x180016e12`: `token`
- `0x180016e63`: `Tokens\%s`
- `0x180016f0b`: `Tokens\%s`
- `0x180016fb7`: `tokenEnum`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSpRegistryXMLLoader::ProcessXMLCategoryChildren(
        CSpRegistryXMLLoader *this,
        HKEY a2,
        struct IXMLDOMNode *a3,
        int *a4,
        int a5)
{
  signed int NamedAttributeTextFromNode; // ebx
  __int64 v9; // rcx
  unsigned int i; // esi
  CSpRegistryXMLLoader *v11; // rcx
  CSpRegistryXMLLoader *v12; // rcx
  LSTATUS v13; // eax
  struct IXMLDOMNode *v14; // rdi
  LSTATUS v15; // eax
  CSpRegistryXMLLoader *v16; // rcx
  struct IXMLDOMNode *v18; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+6Ch] [rbp-94h] BYREF
  BSTR v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  NamedAttributeTextFromNode = 0;
  if ( !a3 )
    NamedAttributeTextFromNode = -2147024809;
  if ( !a4 )
    NamedAttributeTextFromNode = -2147024809;
  v9 = 0;
  v24 = 0;
  if ( NamedAttributeTextFromNode >= 0 )
  {
    NamedAttributeTextFromNode = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a3->lpVtbl->get_childNodes)(
                                   a3,
                                   &v24);
    v9 = v24;
  }
  v21 = 0;
  if ( NamedAttributeTextFromNode >= 0 )
  {
    NamedAttributeTextFromNode = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 64LL))(v9, &v21);
    v9 = v24;
  }
  *a4 = 0;
  for ( i = 0; NamedAttributeTextFromNode >= 0; v9 = v24 )
  {
    if ( (int)i >= v21 )
      break;
    v18 = 0;
    v23 = 0;
    v22 = 0;
    NamedAttributeTextFromNode = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v9 + 56LL))(
                                   v9,
                                   i,
                                   &v18);
    if ( NamedAttributeTextFromNode >= 0 )
    {
      NamedAttributeTextFromNode = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v18->lpVtbl->get_nodeType)(
                                     v18,
                                     &v22);
      if ( NamedAttributeTextFromNode >= 0 )
      {
        NamedAttributeTextFromNode = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v18->lpVtbl->get_nodeName)(
                                       v18,
                                       &v23);
        if ( NamedAttributeTextFromNode >= 0 && v22 == 1 )
        {
          if ( (unsigned int)_o__wcsnicmp(L"string") )
          {
            if ( (unsigned int)_o__wcsnicmp(L"token") )
            {
              if ( (unsigned int)_o__wcsnicmp(L"tokenEnum") )
              {
                NamedAttributeTextFromNode = -2147024809;
              }
              else if ( a5 )
              {
                NamedAttributeTextFromNode = CSpRegistryXMLLoader::ValidateTokenNode(v16, a2, v18, 1);
              }
              else
              {
                NamedAttributeTextFromNode = CSpRegistryXMLLoader::ImportXMLTokenNode(this, a2, v18, 1);
                *a4 = 1;
              }
            }
            else if ( a5 )
            {
              NamedAttributeTextFromNode = -2147024809;
              if ( v18 )
                NamedAttributeTextFromNode = 0;
              bstrString = 0;
              if ( v18 )
              {
                NamedAttributeTextFromNode = CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(
                                               v12,
                                               v18,
                                               L"name",
                                               &bstrString);
                if ( NamedAttributeTextFromNode >= 0 )
                {
                  NamedAttributeTextFromNode = StringCchPrintfW(SubKey, 0x104u, L"Tokens\\%s", bstrString);
                  if ( NamedAttributeTextFromNode >= 0 )
                  {
                    hKey = 0;
                    v13 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey);
                    if ( v13 != 2 )
                    {
                      if ( !v13 )
                        RegCloseKey(hKey);
                      NamedAttributeTextFromNode = -2147200875;
                    }
                  }
                }
              }
              SysFreeString(bstrString);
            }
            else
            {
              v14 = v18;
              hKey = 0;
              if ( v18 )
              {
                bstrString = 0;
                NamedAttributeTextFromNode = CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(
                                               v12,
                                               v18,
                                               L"name",
                                               &bstrString);
                if ( NamedAttributeTextFromNode >= 0 )
                {
                  NamedAttributeTextFromNode = StringCchPrintfW(SubKey, 0x104u, L"Tokens\\%s", bstrString);
                  if ( NamedAttributeTextFromNode >= 0 )
                  {
                    v15 = RegCreateKeyExW(a2, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
                    NamedAttributeTextFromNode = v15;
                    if ( v15 > 0 )
                      NamedAttributeTextFromNode = (unsigned __int16)v15 | 0x80070000;
                  }
                }
                SysFreeString(bstrString);
                if ( NamedAttributeTextFromNode >= 0 )
                  NamedAttributeTextFromNode = CSpRegistryXMLLoader::ImportXMLTokenChildren(this, hKey, v14, 0, 0);
              }
              else
              {
                NamedAttributeTextFromNode = -2147024809;
              }
              RegCloseKey(hKey);
              *a4 = 1;
            }
          }
          else if ( a5 )
          {
            NamedAttributeTextFromNode = CSpRegistryXMLLoader::ValidateStringNode(v11, a2, v18);
          }
          else
          {
            NamedAttributeTextFromNode = CSpRegistryXMLLoader::ImportXMLStringNode(this, a2, v18, 0);
          }
        }
      }
    }
    SysFreeString(v23);
    if ( v18 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
    ++i;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)NamedAttributeTextFromNode;
}

```

## disassembly

```asm
0x180016c90  push    rbp
0x180016c92  push    rbx
0x180016c93  push    rsi
0x180016c94  push    rdi
0x180016c95  push    r12
0x180016c97  push    r13
0x180016c99  push    r14
0x180016c9b  push    r15
0x180016c9d  lea     rbp, [rsp-1A8h]
0x180016ca5  sub     rsp, 2A8h
0x180016cac  mov     rax, cs:__security_cookie
0x180016cb3  xor     rax, rsp
0x180016cb6  mov     [rbp+1E0h+var_50], rax
0x180016cbd  mov     r15, r9
0x180016cc0  mov     r13, rdx
0x180016cc3  mov     r12, rcx
0x180016cc6  xor     edi, edi
0x180016cc8  mov     ebx, edi
0x180016cca  test    r8, r8
0x180016ccd  jnz     short loc_180016CD4
0x180016ccf  mov     ebx, 80070057h
0x180016cd4  test    r15, r15
0x180016cd7  jnz     short loc_180016CDE
0x180016cd9  mov     ebx, 80070057h
0x180016cde  mov     rcx, rdi
0x180016ce1  mov     [rsp+2E0h+var_268], rcx
0x180016ce6  test    ebx, ebx
0x180016ce8  js      short loc_180016D05
0x180016cea  mov     rax, [r8]
0x180016ced  lea     rdx, [rsp+2E0h+var_268]
0x180016cf2  mov     rcx, r8
0x180016cf5  mov     rax, [rax+60h]
0x180016cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cfe  mov     ebx, eax
0x180016d00  mov     rcx, [rsp+2E0h+var_268]
0x180016d05  mov     [rsp+2E0h+var_278], edi
0x180016d09  test    ebx, ebx
0x180016d0b  js      short loc_180016D25
0x180016d0d  mov     rax, [rcx]
0x180016d10  lea     rdx, [rsp+2E0h+var_278]
0x180016d15  mov     rax, [rax+40h]
0x180016d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d1e  mov     ebx, eax
0x180016d20  mov     rcx, [rsp+2E0h+var_268]
0x180016d25  mov     [r15], edi
0x180016d28  mov     esi, edi
0x180016d2a  test    ebx, ebx
0x180016d2c  js      loc_18001702E
0x180016d32  mov     r14d, [rbp+1E0h+arg_20]
0x180016d39  nop     dword ptr [rax+00000000h]
0x180016d40  cmp     esi, [rsp+2E0h+var_278]
0x180016d44  jge     loc_18001702E
0x180016d4a  mov     [rsp+2E0h+var_290], rdi
0x180016d4f  mov     [rsp+2E0h+var_270], rdi
0x180016d54  mov     [rsp+2E0h+var_274], edi
0x180016d58  mov     rax, [rcx]
0x180016d5b  lea     r8, [rsp+2E0h+var_290]
0x180016d60  mov     edx, esi
0x180016d62  mov     rax, [rax+38h]
0x180016d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d6b  mov     ebx, eax
0x180016d6d  test    eax, eax
0x180016d6f  js      loc_180016FFC
0x180016d75  mov     rcx, [rsp+2E0h+var_290]
0x180016d7a  mov     rax, [rcx]
0x180016d7d  lea     rdx, [rsp+2E0h+var_274]
0x180016d82  mov     rax, [rax+50h]
0x180016d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d8b  mov     ebx, eax
0x180016d8d  test    eax, eax
0x180016d8f  js      loc_180016FFC
0x180016d95  mov     rcx, [rsp+2E0h+var_290]
0x180016d9a  mov     rax, [rcx]
0x180016d9d  lea     rdx, [rsp+2E0h+var_270]
0x180016da2  mov     rax, [rax+38h]
0x180016da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dab  mov     ebx, eax
0x180016dad  test    eax, eax
0x180016daf  js      loc_180016FFC
0x180016db5  cmp     [rsp+2E0h+var_274], 1
0x180016dba  jnz     loc_180016FFC
0x180016dc0  mov     r8d, 104h
0x180016dc6  mov     rdx, [rsp+2E0h+var_270]
0x180016dcb  lea     rcx, aString; "string"
0x180016dd2  call    cs:__imp__o__wcsnicmp
0x180016dd8  test    eax, eax
0x180016dda  jnz     short loc_180016E07
0x180016ddc  mov     r8, [rsp+2E0h+var_290]; struct IXMLDOMNode *
0x180016de1  mov     rdx, r13; HKEY
0x180016de4  test    r14d, r14d
0x180016de7  jz      short loc_180016DF5
0x180016de9  call    ?ValidateStringNode@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@@Z; CSpRegistryXMLLoader::ValidateStringNode(HKEY__ *,IXMLDOMNode *)
0x180016dee  mov     ebx, eax
0x180016df0  jmp     loc_180016FFC
0x180016df5  xor     r9d, r9d; int
0x180016df8  mov     rcx, r12; this
0x180016dfb  call    ?ImportXMLStringNode@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@H@Z; CSpRegistryXMLLoader::ImportXMLStringNode(HKEY__ *,IXMLDOMNode *,int)
0x180016e00  mov     ebx, eax
0x180016e02  jmp     loc_180016FFC
0x180016e07  mov     r8d, 104h
0x180016e0d  mov     rdx, [rsp+2E0h+var_270]
0x180016e12  lea     rcx, aToken; "token"
0x180016e19  call    cs:__imp__o__wcsnicmp
0x180016e1f  test    eax, eax
0x180016e21  jnz     loc_180016FAC
0x180016e27  test    r14d, r14d
0x180016e2a  jz      loc_180016ECC
0x180016e30  mov     rdx, [rsp+2E0h+var_290]; struct IXMLDOMNode *
0x180016e35  mov     ebx, 80070057h
0x180016e3a  test    rdx, rdx
0x180016e3d  cmovnz  ebx, edi
0x180016e40  mov     [rsp+2E0h+bstrString], rdi
0x180016e45  jz      short loc_180016EBC
0x180016e47  lea     r9, [rsp+2E0h+bstrString]; unsigned __int16 **
0x180016e4c  lea     r8, psz; "name"
0x180016e53  call    ?GetNamedAttributeTextFromNode@CSpRegistryXMLLoader@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(IXMLDOMNode *,ushort const *,ushort * *)
0x180016e58  mov     ebx, eax
0x180016e5a  test    eax, eax
0x180016e5c  js      short loc_180016EBC
0x180016e5e  mov     r9, [rsp+2E0h+bstrString]
0x180016e63  lea     r8, aTokensS; "Tokens\\%s"
0x180016e6a  mov     edx, 104h; unsigned __int64
0x180016e6f  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x180016e73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016e78  mov     ebx, eax
0x180016e7a  test    eax, eax
0x180016e7c  js      short loc_180016EBC
0x180016e7e  mov     [rsp+2E0h+hKey], rdi
0x180016e83  lea     rax, [rsp+2E0h+hKey]
0x180016e88  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180016e8d  mov     r9d, 20019h; samDesired
0x180016e93  xor     r8d, r8d; ulOptions
0x180016e96  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180016e9a  mov     rcx, r13; hKey
0x180016e9d  call    cs:__imp_RegOpenKeyExW
0x180016ea3  cmp     eax, 2
0x180016ea6  jz      short loc_180016EBC
0x180016ea8  test    eax, eax
0x180016eaa  jnz     short loc_180016EB7
0x180016eac  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180016eb1  call    cs:__imp_RegCloseKey
0x180016eb7  mov     ebx, 80045095h
0x180016ebc  mov     rcx, [rsp+2E0h+bstrString]; bstrString
0x180016ec1  call    cs:__imp_SysFreeString
0x180016ec7  jmp     loc_180016FFC
0x180016ecc  mov     rdi, [rsp+2E0h+var_290]
0x180016ed1  xor     eax, eax
0x180016ed3  mov     [rsp+2E0h+hKey], rax
0x180016ed8  test    rdi, rdi
0x180016edb  jnz     short loc_180016EE7
0x180016edd  mov     ebx, 80070057h
0x180016ee2  jmp     loc_180016F96
0x180016ee7  mov     [rsp+2E0h+bstrString], rax
0x180016eec  lea     r9, [rsp+2E0h+bstrString]; unsigned __int16 **
0x180016ef1  lea     r8, psz; "name"
0x180016ef8  mov     rdx, rdi; struct IXMLDOMNode *
0x180016efb  call    ?GetNamedAttributeTextFromNode@CSpRegistryXMLLoader@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; CSpRegistryXMLLoader::GetNamedAttributeTextFromNode(IXMLDOMNode *,ushort const *,ushort * *)
0x180016f00  mov     ebx, eax
0x180016f02  test    eax, eax
0x180016f04  js      short loc_180016F6A
0x180016f06  mov     r9, [rsp+2E0h+bstrString]
0x180016f0b  lea     r8, aTokensS; "Tokens\\%s"
0x180016f12  mov     edx, 104h; unsigned __int64
0x180016f17  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x180016f1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016f20  mov     ebx, eax
0x180016f22  test    eax, eax
0x180016f24  js      short loc_180016F6A
0x180016f26  xor     ecx, ecx
0x180016f28  mov     [rsp+2E0h+lpdwDisposition], rcx; lpdwDisposition
0x180016f2d  lea     rax, [rsp+2E0h+hKey]
0x180016f32  mov     [rsp+2E0h+var_2A8], rax; phkResult
0x180016f37  mov     [rsp+2E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180016f3c  mov     [rsp+2E0h+samDesired], 0F003Fh; samDesired
0x180016f44  mov     dword ptr [rsp+2E0h+phkResult], ecx; dwOptions
0x180016f48  xor     r9d, r9d; lpClass
0x180016f4b  xor     r8d, r8d; Reserved
0x180016f4e  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180016f52  mov     rcx, r13; hKey
0x180016f55  call    cs:__imp_RegCreateKeyExW
0x180016f5b  mov     ebx, eax
0x180016f5d  test    eax, eax
0x180016f5f  jle     short loc_180016F6A
0x180016f61  movzx   ebx, ax
0x180016f64  or      ebx, 80070000h
0x180016f6a  mov     rcx, [rsp+2E0h+bstrString]; bstrString
0x180016f6f  call    cs:__imp_SysFreeString
0x180016f75  test    ebx, ebx
0x180016f77  js      short loc_180016F96
0x180016f79  mov     dword ptr [rsp+2E0h+phkResult], 0; int
0x180016f81  xor     r9d, r9d; int
0x180016f84  mov     r8, rdi; struct IXMLDOMNode *
0x180016f87  mov     rdx, [rsp+2E0h+hKey]; HKEY
0x180016f8c  mov     rcx, r12; this
0x180016f8f  call    ?ImportXMLTokenChildren@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@HH@Z; CSpRegistryXMLLoader::ImportXMLTokenChildren(HKEY__ *,IXMLDOMNode *,int,int)
0x180016f94  mov     ebx, eax
0x180016f96  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180016f9b  call    cs:__imp_RegCloseKey
0x180016fa1  mov     dword ptr [r15], 1
0x180016fa8  xor     edi, edi
0x180016faa  jmp     short loc_180016FFC
0x180016fac  mov     r8d, 104h
0x180016fb2  mov     rdx, [rsp+2E0h+var_270]
0x180016fb7  lea     rcx, aTokenenum; "tokenEnum"
0x180016fbe  call    cs:__imp__o__wcsnicmp
0x180016fc4  test    eax, eax
0x180016fc6  jnz     short loc_180016FF7
0x180016fc8  mov     r9d, 1; int
0x180016fce  mov     r8, [rsp+2E0h+var_290]; struct IXMLDOMNode *
0x180016fd3  mov     rdx, r13; HKEY
0x180016fd6  test    r14d, r14d
0x180016fd9  jz      short loc_180016FE4
0x180016fdb  call    ?ValidateTokenNode@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@H@Z; CSpRegistryXMLLoader::ValidateTokenNode(HKEY__ *,IXMLDOMNode *,int)
0x180016fe0  mov     ebx, eax
0x180016fe2  jmp     short loc_180016FFC
0x180016fe4  mov     rcx, r12; this
0x180016fe7  call    ?ImportXMLTokenNode@CSpRegistryXMLLoader@@AEAAJPEAUHKEY__@@PEAUIXMLDOMNode@@H@Z; CSpRegistryXMLLoader::ImportXMLTokenNode(HKEY__ *,IXMLDOMNode *,int)
0x180016fec  mov     ebx, eax
0x180016fee  mov     dword ptr [r15], 1
0x180016ff5  jmp     short loc_180016FFC
0x180016ff7  mov     ebx, 80070057h
0x180016ffc  mov     rcx, [rsp+2E0h+var_270]; bstrString
0x180017001  call    cs:__imp_SysFreeString
0x180017007  nop
0x180017008  mov     rcx, [rsp+2E0h+var_290]
0x18001700d  test    rcx, rcx
0x180017010  jz      short loc_18001701F
0x180017012  mov     rax, [rcx]
0x180017015  mov     rax, [rax+10h]
0x180017019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701e  nop
0x18001701f  inc     esi
0x180017021  mov     rcx, [rsp+2E0h+var_268]
0x180017026  test    ebx, ebx
0x180017028  jns     loc_180016D40
0x18001702e  test    rcx, rcx
0x180017031  jz      short loc_180017040
0x180017033  mov     rax, [rcx]
0x180017036  mov     rax, [rax+10h]
0x18001703a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001703f  nop
0x180017040  mov     eax, ebx
0x180017042  mov     rcx, [rbp+1E0h+var_50]
0x180017049  xor     rcx, rsp; StackCookie
0x18001704c  call    __security_check_cookie
0x180017051  add     rsp, 2A8h
0x180017058  pop     r15
0x18001705a  pop     r14
0x18001705c  pop     r13
0x18001705e  pop     r12
0x180017060  pop     rdi
0x180017061  pop     rsi
0x180017062  pop     rbx
0x180017063  pop     rbp
0x180017064  retn
```
