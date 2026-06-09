# UnregisterSignControl(void)

- ea: `0x180005980`
- end: `0x180005e59`
- name: `?UnregisterSignControl@@YAJXZ`
- size: `1241`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800071e0`

## callees

- `0x180005900`
- `0x180005980`
- `0x18000d18a`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `msvcrt!malloc` at `0x180005c1f`
- `msvcrt!malloc` at `0x180005c1f`
- `msvcrt!free` at `0x180005c0b`
- `msvcrt!free` at `0x180005da5`
- `msvcrt!free` at `0x180005c0b`
- `msvcrt!free` at `0x180005da5`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b82`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e33`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b82`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e33`
- `OLEAUT32!__imp_SysStringLen` at `0x180005c16`
- `OLEAUT32!__imp_SysStringLen` at `0x180005c39`
- `OLEAUT32!__imp_SysStringLen` at `0x180005c16`
- `OLEAUT32!__imp_SysStringLen` at `0x180005c39`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180005a17`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180005a17`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180005d73`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180005d73`
- `ADVAPI32!RegOpenKeyA` at `0x180005a5c`
- `ADVAPI32!RegOpenKeyA` at `0x180005c62`
- `ADVAPI32!RegOpenKeyA` at `0x180005d17`
- `ADVAPI32!RegOpenKeyA` at `0x180005a5c`
- `ADVAPI32!RegOpenKeyA` at `0x180005c62`
- `ADVAPI32!RegOpenKeyA` at `0x180005d17`
- `ADVAPI32!RegDeleteKeyA` at `0x180005cb7`
- `ADVAPI32!RegDeleteKeyA` at `0x180005cc9`
- `ADVAPI32!RegDeleteKeyA` at `0x180005cdb`
- `ADVAPI32!RegDeleteKeyA` at `0x180005ced`
- `ADVAPI32!RegDeleteKeyA` at `0x180005d07`
- `ADVAPI32!RegDeleteKeyA` at `0x180005d2c`
- `ADVAPI32!RegDeleteKeyA` at `0x180005d42`
- `ADVAPI32!RegDeleteKeyA` at `0x180005cb7`
- `ADVAPI32!RegDeleteKeyA` at `0x180005cc9`
- `ADVAPI32!RegDeleteKeyA` at `0x180005cdb`
- `ADVAPI32!RegDeleteKeyA` at `0x180005ced`
- `ADVAPI32!RegDeleteKeyA` at `0x180005d07`
- `ADVAPI32!RegDeleteKeyA` at `0x180005d2c`
- `ADVAPI32!RegDeleteKeyA` at `0x180005d42`
- `ADVAPI32!RegCloseKey` at `0x180005cf8`
- `ADVAPI32!RegCloseKey` at `0x180005d36`
- `ADVAPI32!RegCloseKey` at `0x180005d4a`
- `ADVAPI32!RegCloseKey` at `0x180005e23`
- `ADVAPI32!RegCloseKey` at `0x180005cf8`
- `ADVAPI32!RegCloseKey` at `0x180005d36`
- `ADVAPI32!RegCloseKey` at `0x180005d4a`
- `ADVAPI32!RegCloseKey` at `0x180005e23`
- `ADVAPI32!RegQueryValueA` at `0x180005c8d`
- `ADVAPI32!RegQueryValueA` at `0x180005c8d`
- `ole32!CoGetMalloc` at `0x1800059ec`
- `ole32!CoGetMalloc` at `0x1800059ec`
- `ole32!StringFromCLSID` at `0x180005a81`
- `ole32!StringFromCLSID` at `0x180005bc5`
- `ole32!StringFromCLSID` at `0x180005a81`
- `ole32!StringFromCLSID` at `0x180005bc5`

## string_xrefs

- `0x180005a55`: `CLSID`
- `0x180005d25`: `CLSID`

## pseudocode

```c
__int64 UnregisterSignControl(void)
{
  void *v0; // rdi
  int Malloc; // ebx
  LSTATUS v2; // eax
  unsigned int v3; // r14d
  unsigned int i; // esi
  __int64 v5; // rcx
  UINT v6; // eax
  const wchar_t *v7; // rbx
  UINT v8; // eax
  __int64 v9; // rcx
  ITypeLib *v10; // rcx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  IID *v14; // [rsp+50h] [rbp-B0h] BYREF
  ITypeLib *pptlib; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  LONG cbData; // [rsp+68h] [rbp-98h] BYREF
  LPMALLOC ppMalloc; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp-80h] BYREF
  LPOLESTR v21; // [rsp+88h] [rbp-78h] BYREF
  HKEY v22; // [rsp+90h] [rbp-70h] BYREF
  IID *rclsid; // [rsp+98h] [rbp-68h] BYREF
  CHAR Data[32]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR SubKey[48]; // [rsp+C0h] [rbp-40h] BYREF
  char v26[48]; // [rsp+F0h] [rbp-10h] BYREF

  cbData = 0;
  v0 = 0;
  bstrString = 0;
  lpsz = 0;
  v21 = 0;
  v13 = 0;
  v14 = 0;
  pptlib = 0;
  rclsid = 0;
  ppMalloc = 0;
  phkResult = 0;
  v22 = 0;
  hKey = 0;
  Malloc = CoGetMalloc(1u, &ppMalloc);
  if ( Malloc >= 0 )
  {
    Malloc = LoadRegTypeLib(&LIBID_ScriptSigner, 1u, 0, 0, &pptlib);
    if ( Malloc >= 0 )
    {
      Malloc = ((__int64 (__fastcall *)(ITypeLib *, IID **))pptlib->lpVtbl->GetLibAttr)(pptlib, &rclsid);
      if ( Malloc >= 0 )
      {
        v2 = RegOpenKeyA(HKEY_CLASSES_ROOT, "CLSID", &phkResult);
        Malloc = v2;
        if ( v2 > 0 )
          Malloc = (unsigned __int16)v2 | 0x80070000;
        if ( Malloc >= 0 )
        {
          Malloc = StringFromCLSID(rclsid, &lpsz);
          if ( Malloc >= 0 )
          {
            StringCchPrintfA(v26, 0x30u, "%S", lpsz);
            ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, lpsz);
            v3 = ((__int64 (__fastcall *)(ITypeLib *))pptlib->lpVtbl->GetTypeInfoCount)(pptlib);
            for ( i = 0; i < v3; ++i )
            {
              v5 = v13;
              if ( v13 )
              {
                if ( v14 )
                {
                  (*(void (**)(void))(*(_QWORD *)v13 + 152LL))();
                  v5 = v13;
                  v14 = 0;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
                v13 = 0;
              }
              Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, __int64 *))pptlib->lpVtbl->GetTypeInfo)(
                         pptlib,
                         i,
                         &v13);
              if ( Malloc < 0 )
                goto LABEL_34;
              Malloc = (*(__int64 (__fastcall **)(__int64, IID **))(*(_QWORD *)v13 + 24LL))(v13, &v14);
              if ( Malloc < 0 )
                goto LABEL_34;
              if ( *(_DWORD *)&v14[2].Data4[4] == 5 && (v14[3].Data4[2] & 2) != 0 )
              {
                if ( bstrString )
                {
                  SysFreeString(bstrString);
                  bstrString = 0;
                }
                Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))pptlib->lpVtbl->GetDocumentation)(
                           pptlib,
                           i,
                           &bstrString,
                           0,
                           0,
                           0);
                if ( Malloc < 0 )
                  goto LABEL_34;
                Malloc = StringFromCLSID(v14, &v21);
                if ( Malloc < 0 )
                  goto LABEL_34;
                StringCchPrintfA(SubKey, 0x30u, "%S", v21);
                ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, v21);
                if ( v0 )
                  free(v0);
                v6 = SysStringLen(bstrString);
                v0 = malloc(v6 + 2);
                if ( !v0 )
                {
                  Malloc = -2147024882;
                  goto LABEL_34;
                }
                v7 = bstrString;
                v8 = SysStringLen(bstrString);
                StringCchPrintfA((char *)v0, v8 + 2, "%S", v7);
                if ( !RegOpenKeyA(phkResult, SubKey, &hKey) )
                {
                  cbData = 32;
                  RegQueryValueA(hKey, "Version", Data, &cbData);
                  if ( !strcmp_0(Data, "1.0") )
                  {
                    RegDeleteKeyA(hKey, "InprocServer32");
                    RegDeleteKeyA(hKey, "TypeLib");
                    RegDeleteKeyA(hKey, "Version");
                    RegDeleteKeyA(hKey, "ProgID");
                    RegCloseKey(hKey);
                    RegDeleteKeyA(phkResult, SubKey);
                    if ( !RegOpenKeyA(HKEY_CLASSES_ROOT, (LPCSTR)v0, &v22) )
                    {
                      RegDeleteKeyA(v22, "CLSID");
                      RegCloseKey(v22);
                      RegDeleteKeyA(HKEY_CLASSES_ROOT, (LPCSTR)v0);
                    }
                  }
                  else
                  {
                    RegCloseKey(hKey);
                  }
                }
              }
            }
            Malloc = UnRegisterTypeLib(&LIBID_ScriptSigner, 1u, 0, 0, SYS_WIN32);
            if ( Malloc >= 0 )
              Malloc = 0;
          }
        }
      }
    }
  }
LABEL_34:
  if ( ppMalloc )
  {
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    ppMalloc = 0;
  }
  if ( v0 )
    free(v0);
  v9 = v13;
  if ( v13 )
  {
    if ( v14 )
    {
      (*(void (**)(void))(*(_QWORD *)v13 + 152LL))();
      v9 = v13;
      v14 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v13 = 0;
  }
  v10 = pptlib;
  if ( pptlib )
  {
    if ( rclsid )
    {
      ((void (*)(void))pptlib->lpVtbl->ReleaseTLibAttr)();
      v10 = pptlib;
    }
    ((void (__fastcall *)(ITypeLib *))v10->lpVtbl->Release)(v10);
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  SysFreeString(bstrString);
  return (unsigned int)Malloc;
}

```

## disassembly

```asm
0x180005980  push    rbp
0x180005982  push    rbx
0x180005983  push    rsi
0x180005984  push    rdi
0x180005985  push    r13
0x180005987  push    r14
0x180005989  push    r15
0x18000598b  lea     rbp, [rsp-30h]
0x180005990  sub     rsp, 130h
0x180005997  mov     rax, cs:__security_cookie
0x18000599e  xor     rax, rsp
0x1800059a1  mov     [rbp+60h+var_40], rax
0x1800059a5  xor     r15d, r15d
0x1800059a8  lea     rdx, [rsp+160h+ppMalloc]; ppMalloc
0x1800059ad  mov     [rsp+160h+cbData], r15d
0x1800059b2  mov     edi, r15d
0x1800059b5  mov     [rsp+160h+bstrString], r15
0x1800059ba  mov     [rbp+60h+lpsz], r15
0x1800059be  lea     ecx, [r15+1]; dwMemContext
0x1800059c2  mov     [rbp+60h+var_D8], r15
0x1800059c6  mov     [rsp+160h+var_118], r15
0x1800059cb  mov     [rsp+160h+var_110], r15
0x1800059d0  mov     [rsp+160h+var_108], r15
0x1800059d5  mov     [rbp+60h+rclsid], r15
0x1800059d9  mov     [rsp+160h+ppMalloc], r15
0x1800059de  mov     [rsp+160h+phkResult], r15
0x1800059e3  mov     [rbp+60h+var_D0], r15
0x1800059e7  mov     [rsp+160h+hKey], r15
0x1800059ec  call    cs:__imp_CoGetMalloc
0x1800059f2  mov     ebx, eax
0x1800059f4  test    eax, eax
0x1800059f6  js      loc_180005D82
0x1800059fc  lea     rax, [rsp+160h+var_108]
0x180005a01  xor     r8d, r8d; wVerMinor
0x180005a04  lea     edx, [r15+1]; wVerMajor
0x180005a08  mov     [rsp+160h+pptlib], rax; pptlib
0x180005a0d  xor     r9d, r9d; lcid
0x180005a10  lea     rcx, LIBID_ScriptSigner; rguid
0x180005a17  call    cs:__imp_LoadRegTypeLib
0x180005a1d  mov     ebx, eax
0x180005a1f  test    eax, eax
0x180005a21  js      loc_180005D82
0x180005a27  mov     rcx, [rsp+160h+var_108]
0x180005a2c  lea     rdx, [rbp+60h+rclsid]
0x180005a30  mov     rax, [rcx]
0x180005a33  mov     rax, [rax+38h]
0x180005a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3c  mov     ebx, eax
0x180005a3e  test    eax, eax
0x180005a40  js      loc_180005D82
0x180005a46  mov     r13, 0FFFFFFFF80000000h
0x180005a4d  lea     r8, [rsp+160h+phkResult]; phkResult
0x180005a52  mov     rcx, r13; hKey
0x180005a55  lea     rdx, aClsid; "CLSID"
0x180005a5c  call    cs:__imp_RegOpenKeyA
0x180005a62  mov     ebx, eax
0x180005a64  test    eax, eax
0x180005a66  jle     short loc_180005A71
0x180005a68  movzx   ebx, ax
0x180005a6b  or      ebx, 80070000h
0x180005a71  test    ebx, ebx
0x180005a73  js      loc_180005D82
0x180005a79  mov     rcx, [rbp+60h+rclsid]; rclsid
0x180005a7d  lea     rdx, [rbp+60h+lpsz]; lplpsz
0x180005a81  call    cs:__imp_StringFromCLSID
0x180005a87  mov     ebx, eax
0x180005a89  test    eax, eax
0x180005a8b  js      loc_180005D82
0x180005a91  mov     r9, [rbp+60h+lpsz]
0x180005a95  lea     r8, aS; "%S"
0x180005a9c  mov     edx, 30h ; '0'; unsigned __int64
0x180005aa1  lea     rcx, [rbp+60h+var_70]; char *
0x180005aa5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180005aaa  mov     rcx, [rsp+160h+ppMalloc]
0x180005aaf  mov     rdx, [rbp+60h+lpsz]
0x180005ab3  mov     rax, [rcx]
0x180005ab6  mov     rax, [rax+28h]
0x180005aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abf  mov     rcx, [rsp+160h+var_108]
0x180005ac4  mov     rax, [rcx]
0x180005ac7  mov     rax, [rax+18h]
0x180005acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad0  mov     r14d, eax
0x180005ad3  mov     esi, r15d
0x180005ad6  cmp     esi, r14d
0x180005ad9  jnb     loc_180005D5E
0x180005adf  mov     rcx, [rsp+160h+var_118]
0x180005ae4  test    rcx, rcx
0x180005ae7  jz      short loc_180005B1D
0x180005ae9  mov     rdx, [rsp+160h+var_110]
0x180005aee  test    rdx, rdx
0x180005af1  jz      short loc_180005B0C
0x180005af3  mov     rax, [rcx]
0x180005af6  mov     rax, [rax+98h]
0x180005afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b02  mov     rcx, [rsp+160h+var_118]
0x180005b07  mov     [rsp+160h+var_110], r15
0x180005b0c  mov     rax, [rcx]
0x180005b0f  mov     rax, [rax+10h]
0x180005b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b18  mov     [rsp+160h+var_118], r15
0x180005b1d  mov     rcx, [rsp+160h+var_108]
0x180005b22  lea     r8, [rsp+160h+var_118]
0x180005b27  mov     edx, esi
0x180005b29  mov     rax, [rcx]
0x180005b2c  mov     rax, [rax+20h]
0x180005b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b35  mov     ebx, eax
0x180005b37  test    eax, eax
0x180005b39  js      loc_180005D82
0x180005b3f  mov     rcx, [rsp+160h+var_118]
0x180005b44  lea     rdx, [rsp+160h+var_110]
0x180005b49  mov     rax, [rcx]
0x180005b4c  mov     rax, [rax+18h]
0x180005b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b55  mov     ebx, eax
0x180005b57  test    eax, eax
0x180005b59  js      loc_180005D82
0x180005b5f  mov     rdx, [rsp+160h+var_110]
0x180005b64  cmp     dword ptr [rdx+2Ch], 5
0x180005b68  jnz     loc_180005D50
0x180005b6e  test    byte ptr [rdx+3Ah], 2
0x180005b72  jz      loc_180005D50
0x180005b78  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180005b7d  test    rcx, rcx
0x180005b80  jz      short loc_180005B8D
0x180005b82  call    cs:__imp_SysFreeString
0x180005b88  mov     [rsp+160h+bstrString], r15
0x180005b8d  mov     rcx, [rsp+160h+var_108]
0x180005b92  lea     r8, [rsp+160h+bstrString]
0x180005b97  mov     [rsp+160h+var_138], r15
0x180005b9c  xor     r9d, r9d
0x180005b9f  mov     edx, esi
0x180005ba1  mov     [rsp+160h+pptlib], r15
0x180005ba6  mov     rax, [rcx]
0x180005ba9  mov     rax, [rax+48h]
0x180005bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb2  mov     ebx, eax
0x180005bb4  test    eax, eax
0x180005bb6  js      loc_180005D82
0x180005bbc  mov     rcx, [rsp+160h+var_110]; rclsid
0x180005bc1  lea     rdx, [rbp+60h+var_D8]; lplpsz
0x180005bc5  call    cs:__imp_StringFromCLSID
0x180005bcb  mov     ebx, eax
0x180005bcd  test    eax, eax
0x180005bcf  js      loc_180005D82
0x180005bd5  mov     r9, [rbp+60h+var_D8]
0x180005bd9  lea     r8, aS; "%S"
0x180005be0  mov     edx, 30h ; '0'; unsigned __int64
0x180005be5  lea     rcx, [rbp+60h+SubKey]; char *
0x180005be9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180005bee  mov     rcx, [rsp+160h+ppMalloc]
0x180005bf3  mov     rdx, [rbp+60h+var_D8]
0x180005bf7  mov     rax, [rcx]
0x180005bfa  mov     rax, [rax+28h]
0x180005bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c03  test    rdi, rdi
0x180005c06  jz      short loc_180005C11
0x180005c08  mov     rcx, rdi; Block
0x180005c0b  call    cs:__imp_free
0x180005c11  mov     rcx, [rsp+160h+bstrString]; pbstr
0x180005c16  call    cs:__imp_SysStringLen
0x180005c1c  lea     ecx, [rax+2]; Size
0x180005c1f  call    cs:__imp_malloc
0x180005c25  mov     rdi, rax
0x180005c28  test    rax, rax
0x180005c2b  jz      loc_180005D57
0x180005c31  mov     rbx, [rsp+160h+bstrString]
0x180005c36  mov     rcx, rbx; pbstr
0x180005c39  call    cs:__imp_SysStringLen
0x180005c3f  mov     r9, rbx
0x180005c42  lea     r8, aS; "%S"
0x180005c49  mov     rcx, rdi; char *
0x180005c4c  lea     edx, [rax+2]; unsigned __int64
0x180005c4f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180005c54  mov     rcx, [rsp+160h+phkResult]; hKey
0x180005c59  lea     r8, [rsp+160h+hKey]; phkResult
0x180005c5e  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x180005c62  call    cs:__imp_RegOpenKeyA
0x180005c68  test    eax, eax
0x180005c6a  jnz     loc_180005D50
0x180005c70  mov     rcx, [rsp+160h+hKey]; hKey
0x180005c75  lea     r9, [rsp+160h+cbData]; lpcbData
0x180005c7a  lea     r8, [rbp+60h+Data]; lpData
0x180005c7e  mov     [rsp+160h+cbData], 20h ; ' '
0x180005c86  lea     rdx, aVersion; "Version"
0x180005c8d  call    cs:__imp_RegQueryValueA
0x180005c93  lea     rdx, a10; "1.0"
0x180005c9a  lea     rcx, [rbp+60h+Data]; Str1
0x180005c9e  call    strcmp_0
0x180005ca3  mov     rcx, [rsp+160h+hKey]; hKey
0x180005ca8  test    eax, eax
0x180005caa  jnz     loc_180005D4A
0x180005cb0  lea     rdx, aInprocserver32_0; "InprocServer32"
0x180005cb7  call    cs:__imp_RegDeleteKeyA
0x180005cbd  mov     rcx, [rsp+160h+hKey]; hKey
0x180005cc2  lea     rdx, aTypelib; "TypeLib"
0x180005cc9  call    cs:__imp_RegDeleteKeyA
0x180005ccf  mov     rcx, [rsp+160h+hKey]; hKey
0x180005cd4  lea     rdx, aVersion; "Version"
0x180005cdb  call    cs:__imp_RegDeleteKeyA
0x180005ce1  mov     rcx, [rsp+160h+hKey]; hKey
0x180005ce6  lea     rdx, aProgid; "ProgID"
0x180005ced  call    cs:__imp_RegDeleteKeyA
0x180005cf3  mov     rcx, [rsp+160h+hKey]; hKey
0x180005cf8  call    cs:__imp_RegCloseKey
0x180005cfe  mov     rcx, [rsp+160h+phkResult]; hKey
0x180005d03  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x180005d07  call    cs:__imp_RegDeleteKeyA
0x180005d0d  lea     r8, [rbp+60h+var_D0]; phkResult
0x180005d11  mov     rdx, rdi; lpSubKey
0x180005d14  mov     rcx, r13; hKey
0x180005d17  call    cs:__imp_RegOpenKeyA
0x180005d1d  test    eax, eax
0x180005d1f  jnz     short loc_180005D50
0x180005d21  mov     rcx, [rbp+60h+var_D0]; hKey
0x180005d25  lea     rdx, aClsid; "CLSID"
0x180005d2c  call    cs:__imp_RegDeleteKeyA
0x180005d32  mov     rcx, [rbp+60h+var_D0]; hKey
0x180005d36  call    cs:__imp_RegCloseKey
0x180005d3c  mov     rdx, rdi; lpSubKey
0x180005d3f  mov     rcx, r13; hKey
0x180005d42  call    cs:__imp_RegDeleteKeyA
0x180005d48  jmp     short loc_180005D50
0x180005d4a  call    cs:__imp_RegCloseKey
0x180005d50  inc     esi
0x180005d52  jmp     loc_180005AD6
0x180005d57  mov     ebx, 8007000Eh
0x180005d5c  jmp     short loc_180005D82
0x180005d5e  xor     r8d, r8d; wVerMinor
0x180005d61  lea     rcx, LIBID_ScriptSigner; libID
0x180005d68  xor     r9d, r9d; lcid
0x180005d6b  lea     edx, [r8+1]; wVerMajor
0x180005d6f  mov     dword ptr [rsp+160h+pptlib], edx; syskind
0x180005d73  call    cs:__imp_UnRegisterTypeLib
0x180005d79  mov     ebx, eax
0x180005d7b  test    eax, eax
0x180005d7d  js      short loc_180005D82
0x180005d7f  mov     ebx, r15d
0x180005d82  mov     rcx, [rsp+160h+ppMalloc]
0x180005d87  test    rcx, rcx
0x180005d8a  jz      short loc_180005D9D
0x180005d8c  mov     rax, [rcx]
0x180005d8f  mov     rax, [rax+10h]
0x180005d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d98  mov     [rsp+160h+ppMalloc], r15
0x180005d9d  test    rdi, rdi
0x180005da0  jz      short loc_180005DAB
0x180005da2  mov     rcx, rdi; Block
0x180005da5  call    cs:__imp_free
0x180005dab  mov     rcx, [rsp+160h+var_118]
0x180005db0  test    rcx, rcx
0x180005db3  jz      short loc_180005DE9
0x180005db5  mov     rdx, [rsp+160h+var_110]
0x180005dba  test    rdx, rdx
0x180005dbd  jz      short loc_180005DD8
0x180005dbf  mov     rax, [rcx]
0x180005dc2  mov     rax, [rax+98h]
0x180005dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dce  mov     rcx, [rsp+160h+var_118]
0x180005dd3  mov     [rsp+160h+var_110], r15
0x180005dd8  mov     rax, [rcx]
0x180005ddb  mov     rax, [rax+10h]
0x180005ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de4  mov     [rsp+160h+var_118], r15
0x180005de9  mov     rcx, [rsp+160h+var_108]
0x180005dee  test    rcx, rcx
0x180005df1  jz      short loc_180005E19
0x180005df3  mov     rdx, [rbp+60h+rclsid]
0x180005df7  test    rdx, rdx
0x180005dfa  jz      short loc_180005E0D
0x180005dfc  mov     rax, [rcx]
0x180005dff  mov     rax, [rax+60h]
0x180005e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e08  mov     rcx, [rsp+160h+var_108]
0x180005e0d  mov     rax, [rcx]
0x180005e10  mov     rax, [rax+10h]
0x180005e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e19  mov     rcx, [rsp+160h+phkResult]; hKey
0x180005e1e  test    rcx, rcx
0x180005e21  jz      short loc_180005E2E
0x180005e23  call    cs:__imp_RegCloseKey
0x180005e29  mov     [rsp+160h+phkResult], r15
0x180005e2e  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180005e33  call    cs:__imp_SysFreeString
0x180005e39  mov     eax, ebx
0x180005e3b  mov     rcx, [rbp+60h+var_40]
0x180005e3f  xor     rcx, rsp; StackCookie
0x180005e42  call    __security_check_cookie
0x180005e47  add     rsp, 130h
0x180005e4e  pop     r15
0x180005e50  pop     r14
0x180005e52  pop     r13
0x180005e54  pop     rdi
0x180005e55  pop     rsi
0x180005e56  pop     rbx
0x180005e57  pop     rbp
0x180005e58  retn
```
