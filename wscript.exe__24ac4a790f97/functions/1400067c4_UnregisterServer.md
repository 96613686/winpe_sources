# UnregisterServer

- ea: `0x1400067c4`
- end: `0x140006c7f`
- name: `UnregisterServer`
- size: `1211`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006c88`

## callees

- `0x140001008`
- `0x140001048`
- `0x140006744`
- `0x1400067c4`
- `0x140017566`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x140006a82`
- `msvcrt!sprintf_s` at `0x140006a82`
- `OLEAUT32!__imp_SysFreeString` at `0x1400069c0`
- `OLEAUT32!__imp_SysFreeString` at `0x140006c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400069c0`
- `OLEAUT32!__imp_SysFreeString` at `0x140006c4f`
- `OLEAUT32!__imp_SysStringLen` at `0x140006a53`
- `OLEAUT32!__imp_SysStringLen` at `0x140006a53`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x14000685b`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x14000685b`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x140006ba4`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x140006ba4`
- `ole32!CoGetMalloc` at `0x140006830`
- `ole32!CoGetMalloc` at `0x140006830`
- `ole32!StringFromCLSID` at `0x1400068c5`
- `ole32!StringFromCLSID` at `0x140006a03`
- `ole32!StringFromCLSID` at `0x1400068c5`
- `ole32!StringFromCLSID` at `0x140006a03`
- `ADVAPI32!RegCloseKey` at `0x140006b2c`
- `ADVAPI32!RegCloseKey` at `0x140006b6a`
- `ADVAPI32!RegCloseKey` at `0x140006b7e`
- `ADVAPI32!RegCloseKey` at `0x140006c44`
- `ADVAPI32!RegCloseKey` at `0x140006b2c`
- `ADVAPI32!RegCloseKey` at `0x140006b6a`
- `ADVAPI32!RegCloseKey` at `0x140006b7e`
- `ADVAPI32!RegCloseKey` at `0x140006c44`
- `ADVAPI32!RegOpenKeyA` at `0x1400068a0`
- `ADVAPI32!RegOpenKeyA` at `0x140006a96`
- `ADVAPI32!RegOpenKeyA` at `0x140006b4b`
- `ADVAPI32!RegOpenKeyA` at `0x1400068a0`
- `ADVAPI32!RegOpenKeyA` at `0x140006a96`
- `ADVAPI32!RegOpenKeyA` at `0x140006b4b`
- `ADVAPI32!RegDeleteKeyA` at `0x140006aeb`
- `ADVAPI32!RegDeleteKeyA` at `0x140006afd`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b0f`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b21`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b3b`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b60`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b76`
- `ADVAPI32!RegDeleteKeyA` at `0x140006aeb`
- `ADVAPI32!RegDeleteKeyA` at `0x140006afd`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b0f`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b21`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b3b`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b60`
- `ADVAPI32!RegDeleteKeyA` at `0x140006b76`
- `ADVAPI32!RegQueryValueA` at `0x140006ac1`
- `ADVAPI32!RegQueryValueA` at `0x140006ac1`

## string_xrefs

- `0x140006899`: `CLSID`
- `0x140006b59`: `CLSID`

## pseudocode

```c
__int64 UnregisterServer()
{
  char *v0; // rdi
  int Malloc; // ebx
  LSTATUS v2; // eax
  unsigned int v3; // r14d
  unsigned int v4; // esi
  __int64 v5; // rcx
  size_t v6; // rbx
  char *v7; // rax
  __int64 v8; // rcx
  ITypeLib *v9; // rcx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  IID *v14; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  LONG cbData; // [rsp+68h] [rbp-98h] BYREF
  LPMALLOC ppMalloc; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp-80h] BYREF
  LPOLESTR v20; // [rsp+88h] [rbp-78h] BYREF
  HKEY v21; // [rsp+90h] [rbp-70h] BYREF
  IID *rclsid; // [rsp+98h] [rbp-68h] BYREF
  CHAR Data[32]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR SubKey[48]; // [rsp+C0h] [rbp-40h] BYREF
  char v25[48]; // [rsp+F0h] [rbp-10h] BYREF

  cbData = 0;
  v0 = 0;
  lpsz = 0;
  v20 = 0;
  v21 = 0;
  hKey = 0;
  bstrString = 0;
  ppMalloc = 0;
  pptlib = 0;
  rclsid = 0;
  phkResult = 0;
  v12 = 0;
  v14 = 0;
  Malloc = CoGetMalloc(1u, &ppMalloc);
  if ( Malloc >= 0 )
  {
    Malloc = LoadRegTypeLib(&LIBID_WSHRemoteLibrary, 1u, 0, 0, &pptlib);
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
            StringCchPrintfA(v25, 0x30u, "%S", lpsz);
            ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, lpsz);
            v3 = ((__int64 (__fastcall *)(ITypeLib *))pptlib->lpVtbl->GetTypeInfoCount)(pptlib);
            v4 = 0;
            if ( v3 )
            {
              while ( 1 )
              {
                v5 = v12;
                if ( v12 )
                {
                  if ( v14 )
                  {
                    (*(void (**)(void))(*(_QWORD *)v12 + 152LL))();
                    v5 = v12;
                    v14 = 0;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
                  v12 = 0;
                }
                Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, __int64 *))pptlib->lpVtbl->GetTypeInfo)(
                           pptlib,
                           v4,
                           &v12);
                if ( Malloc < 0 )
                  break;
                Malloc = (*(__int64 (__fastcall **)(__int64, IID **))(*(_QWORD *)v12 + 24LL))(v12, &v14);
                if ( Malloc < 0 )
                  break;
                if ( *(_DWORD *)&v14[2].Data4[4] == 5 && (v14[3].Data4[2] & 2) != 0 )
                {
                  SysFreeString(bstrString);
                  bstrString = 0;
                  Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))pptlib->lpVtbl->GetDocumentation)(
                             pptlib,
                             v4,
                             &bstrString,
                             0,
                             0,
                             0);
                  if ( Malloc < 0 )
                    break;
                  Malloc = StringFromCLSID(v14, &v20);
                  if ( Malloc < 0 )
                    break;
                  StringCchPrintfA(SubKey, 0x30u, "%S", v20);
                  ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, v20);
                  if ( v0 )
                    operator delete(v0);
                  v6 = SysStringLen(bstrString) + 2;
                  v7 = (char *)operator new(v6);
                  v0 = v7;
                  if ( !v7 )
                  {
                    Malloc = -2147024882;
                    break;
                  }
                  sprintf_s(v7, (unsigned int)v6, "%S", bstrString);
                  if ( !RegOpenKeyA(phkResult, SubKey, &hKey) )
                  {
                    cbData = 32;
                    RegQueryValueA(hKey, "Version", Data, &cbData);
                    if ( !strcmp_0(Data, "1.0") )
                    {
                      RegDeleteKeyA(hKey, "LocalServer32");
                      RegDeleteKeyA(hKey, "TypeLib");
                      RegDeleteKeyA(hKey, "Version");
                      RegDeleteKeyA(hKey, "ProgID");
                      RegCloseKey(hKey);
                      RegDeleteKeyA(phkResult, SubKey);
                      if ( !RegOpenKeyA(HKEY_CLASSES_ROOT, v0, &v21) )
                      {
                        RegDeleteKeyA(v21, "CLSID");
                        RegCloseKey(v21);
                        RegDeleteKeyA(HKEY_CLASSES_ROOT, v0);
                      }
                    }
                    else
                    {
                      RegCloseKey(hKey);
                    }
                  }
                }
                if ( ++v4 >= v3 )
                  goto LABEL_28;
              }
            }
            else
            {
LABEL_28:
              Malloc = UnRegisterTypeLib(&LIBID_WSHRemoteLibrary, 1u, 0, 0, SYS_WIN32);
              if ( Malloc >= 0 )
                Malloc = 0;
            }
          }
        }
      }
    }
  }
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( v0 )
    operator delete(v0);
  v8 = v12;
  if ( v12 )
  {
    if ( v14 )
    {
      (*(void (**)(void))(*(_QWORD *)v12 + 152LL))();
      v8 = v12;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = pptlib;
  if ( pptlib )
  {
    if ( rclsid )
    {
      ((void (*)(void))pptlib->lpVtbl->ReleaseTLibAttr)();
      v9 = pptlib;
    }
    ((void (__fastcall *)(ITypeLib *))v9->lpVtbl->Release)(v9);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  SysFreeString(bstrString);
  return (unsigned int)Malloc;
}

```

## disassembly

```asm
0x1400067c4  push    rbp
0x1400067c6  push    rbx
0x1400067c7  push    rsi
0x1400067c8  push    rdi
0x1400067c9  push    r13
0x1400067cb  push    r14
0x1400067cd  push    r15
0x1400067cf  lea     rbp, [rsp-30h]
0x1400067d4  sub     rsp, 130h
0x1400067db  mov     rax, cs:__security_cookie
0x1400067e2  xor     rax, rsp
0x1400067e5  mov     [rbp+60h+var_40], rax
0x1400067e9  xor     r15d, r15d
0x1400067ec  lea     rdx, [rsp+160h+ppMalloc]; ppMalloc
0x1400067f1  mov     [rsp+160h+cbData], r15d
0x1400067f6  mov     edi, r15d
0x1400067f9  mov     [rbp+60h+lpsz], r15
0x1400067fd  mov     [rbp+60h+var_D8], r15
0x140006801  lea     ecx, [r15+1]; dwMemContext
0x140006805  mov     [rbp+60h+var_D0], r15
0x140006809  mov     [rsp+160h+hKey], r15
0x14000680e  mov     [rsp+160h+bstrString], r15
0x140006813  mov     [rsp+160h+ppMalloc], r15
0x140006818  mov     [rsp+160h+var_110], r15
0x14000681d  mov     [rbp+60h+rclsid], r15
0x140006821  mov     [rsp+160h+phkResult], r15
0x140006826  mov     [rsp+160h+var_118], r15
0x14000682b  mov     [rsp+160h+var_108], r15
0x140006830  call    cs:__imp_CoGetMalloc
0x140006836  mov     ebx, eax
0x140006838  test    eax, eax
0x14000683a  js      loc_140006BB3
0x140006840  lea     rax, [rsp+160h+var_110]
0x140006845  xor     r8d, r8d; wVerMinor
0x140006848  lea     edx, [r15+1]; wVerMajor
0x14000684c  mov     [rsp+160h+pptlib], rax; pptlib
0x140006851  xor     r9d, r9d; lcid
0x140006854  lea     rcx, LIBID_WSHRemoteLibrary; rguid
0x14000685b  call    cs:__imp_LoadRegTypeLib
0x140006861  mov     ebx, eax
0x140006863  test    eax, eax
0x140006865  js      loc_140006BB3
0x14000686b  mov     rcx, [rsp+160h+var_110]
0x140006870  lea     rdx, [rbp+60h+rclsid]
0x140006874  mov     rax, [rcx]
0x140006877  mov     rax, [rax+38h]
0x14000687b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006880  mov     ebx, eax
0x140006882  test    eax, eax
0x140006884  js      loc_140006BB3
0x14000688a  mov     r13, 0FFFFFFFF80000000h
0x140006891  lea     r8, [rsp+160h+phkResult]; phkResult
0x140006896  mov     rcx, r13; hKey
0x140006899  lea     rdx, SubKey; "CLSID"
0x1400068a0  call    cs:__imp_RegOpenKeyA
0x1400068a6  mov     ebx, eax
0x1400068a8  test    eax, eax
0x1400068aa  jle     short loc_1400068B5
0x1400068ac  movzx   ebx, ax
0x1400068af  or      ebx, 80070000h
0x1400068b5  test    ebx, ebx
0x1400068b7  js      loc_140006BB3
0x1400068bd  mov     rcx, [rbp+60h+rclsid]; rclsid
0x1400068c1  lea     rdx, [rbp+60h+lpsz]; lplpsz
0x1400068c5  call    cs:__imp_StringFromCLSID
0x1400068cb  mov     ebx, eax
0x1400068cd  test    eax, eax
0x1400068cf  js      loc_140006BB3
0x1400068d5  mov     r9, [rbp+60h+lpsz]
0x1400068d9  lea     r8, aS_0; "%S"
0x1400068e0  mov     edx, 30h ; '0'; unsigned __int64
0x1400068e5  lea     rcx, [rbp+60h+var_70]; char *
0x1400068e9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400068ee  mov     rcx, [rsp+160h+ppMalloc]
0x1400068f3  mov     rdx, [rbp+60h+lpsz]
0x1400068f7  mov     rax, [rcx]
0x1400068fa  mov     rax, [rax+28h]
0x1400068fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006903  mov     rcx, [rsp+160h+var_110]
0x140006908  mov     rax, [rcx]
0x14000690b  mov     rax, [rax+18h]
0x14000690f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006914  mov     r14d, eax
0x140006917  mov     esi, r15d
0x14000691a  test    eax, eax
0x14000691c  jz      loc_140006B8F
0x140006922  mov     rcx, [rsp+160h+var_118]
0x140006927  test    rcx, rcx
0x14000692a  jz      short loc_140006960
0x14000692c  mov     rdx, [rsp+160h+var_108]
0x140006931  test    rdx, rdx
0x140006934  jz      short loc_14000694F
0x140006936  mov     rax, [rcx]
0x140006939  mov     rax, [rax+98h]
0x140006940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006945  mov     rcx, [rsp+160h+var_118]
0x14000694a  mov     [rsp+160h+var_108], r15
0x14000694f  mov     rax, [rcx]
0x140006952  mov     rax, [rax+10h]
0x140006956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000695b  mov     [rsp+160h+var_118], r15
0x140006960  mov     rcx, [rsp+160h+var_110]
0x140006965  lea     r8, [rsp+160h+var_118]
0x14000696a  mov     edx, esi
0x14000696c  mov     rax, [rcx]
0x14000696f  mov     rax, [rax+20h]
0x140006973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006978  mov     ebx, eax
0x14000697a  test    eax, eax
0x14000697c  js      loc_140006BB3
0x140006982  mov     rcx, [rsp+160h+var_118]
0x140006987  lea     rdx, [rsp+160h+var_108]
0x14000698c  mov     rax, [rcx]
0x14000698f  mov     rax, [rax+18h]
0x140006993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006998  mov     ebx, eax
0x14000699a  test    eax, eax
0x14000699c  js      loc_140006BB3
0x1400069a2  mov     rdx, [rsp+160h+var_108]
0x1400069a7  cmp     dword ptr [rdx+2Ch], 5
0x1400069ab  jnz     loc_140006B84
0x1400069b1  test    byte ptr [rdx+3Ah], 2
0x1400069b5  jz      loc_140006B84
0x1400069bb  mov     rcx, [rsp+160h+bstrString]; bstrString
0x1400069c0  call    cs:__imp_SysFreeString
0x1400069c6  mov     rcx, [rsp+160h+var_110]
0x1400069cb  lea     r8, [rsp+160h+bstrString]
0x1400069d0  mov     [rsp+160h+bstrString], r15
0x1400069d5  xor     r9d, r9d
0x1400069d8  mov     [rsp+160h+var_138], r15
0x1400069dd  mov     edx, esi
0x1400069df  mov     [rsp+160h+pptlib], r15
0x1400069e4  mov     rax, [rcx]
0x1400069e7  mov     rax, [rax+48h]
0x1400069eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069f0  mov     ebx, eax
0x1400069f2  test    eax, eax
0x1400069f4  js      loc_140006BB3
0x1400069fa  mov     rcx, [rsp+160h+var_108]; rclsid
0x1400069ff  lea     rdx, [rbp+60h+var_D8]; lplpsz
0x140006a03  call    cs:__imp_StringFromCLSID
0x140006a09  mov     ebx, eax
0x140006a0b  test    eax, eax
0x140006a0d  js      loc_140006BB3
0x140006a13  mov     r9, [rbp+60h+var_D8]
0x140006a17  lea     r8, aS_0; "%S"
0x140006a1e  mov     edx, 30h ; '0'; unsigned __int64
0x140006a23  lea     rcx, [rbp+60h+SubKey]; char *
0x140006a27  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140006a2c  mov     rcx, [rsp+160h+ppMalloc]
0x140006a31  mov     rdx, [rbp+60h+var_D8]
0x140006a35  mov     rax, [rcx]
0x140006a38  mov     rax, [rax+28h]
0x140006a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a41  test    rdi, rdi
0x140006a44  jz      short loc_140006A4E
0x140006a46  mov     rcx, rdi; Block
0x140006a49  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006a4e  mov     rcx, [rsp+160h+bstrString]; pbstr
0x140006a53  call    cs:__imp_SysStringLen
0x140006a59  add     eax, 2
0x140006a5c  mov     ecx, eax; Size
0x140006a5e  mov     ebx, eax
0x140006a60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006a65  mov     rdi, rax
0x140006a68  test    rax, rax
0x140006a6b  jz      loc_140006C75
0x140006a71  mov     r9, [rsp+160h+bstrString]
0x140006a76  lea     r8, aS_0; "%S"
0x140006a7d  mov     edx, ebx; BufferCount
0x140006a7f  mov     rcx, rax; Buffer
0x140006a82  call    cs:__imp_sprintf_s
0x140006a88  mov     rcx, [rsp+160h+phkResult]; hKey
0x140006a8d  lea     r8, [rsp+160h+hKey]; phkResult
0x140006a92  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x140006a96  call    cs:__imp_RegOpenKeyA
0x140006a9c  test    eax, eax
0x140006a9e  jnz     loc_140006B84
0x140006aa4  mov     rcx, [rsp+160h+hKey]; hKey
0x140006aa9  lea     r9, [rsp+160h+cbData]; lpcbData
0x140006aae  lea     r8, [rbp+60h+Data]; lpData
0x140006ab2  mov     [rsp+160h+cbData], 20h ; ' '
0x140006aba  lea     rdx, aVersion; "Version"
0x140006ac1  call    cs:__imp_RegQueryValueA
0x140006ac7  lea     rdx, Str2; "1.0"
0x140006ace  lea     rcx, [rbp+60h+Data]; Str1
0x140006ad2  call    strcmp_0
0x140006ad7  mov     rcx, [rsp+160h+hKey]; hKey
0x140006adc  test    eax, eax
0x140006ade  jnz     loc_140006B7E
0x140006ae4  lea     rdx, aLocalserver32; "LocalServer32"
0x140006aeb  call    cs:__imp_RegDeleteKeyA
0x140006af1  mov     rcx, [rsp+160h+hKey]; hKey
0x140006af6  lea     rdx, aTypelib; "TypeLib"
0x140006afd  call    cs:__imp_RegDeleteKeyA
0x140006b03  mov     rcx, [rsp+160h+hKey]; hKey
0x140006b08  lea     rdx, aVersion; "Version"
0x140006b0f  call    cs:__imp_RegDeleteKeyA
0x140006b15  mov     rcx, [rsp+160h+hKey]; hKey
0x140006b1a  lea     rdx, aProgid; "ProgID"
0x140006b21  call    cs:__imp_RegDeleteKeyA
0x140006b27  mov     rcx, [rsp+160h+hKey]; hKey
0x140006b2c  call    cs:__imp_RegCloseKey
0x140006b32  mov     rcx, [rsp+160h+phkResult]; hKey
0x140006b37  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x140006b3b  call    cs:__imp_RegDeleteKeyA
0x140006b41  lea     r8, [rbp+60h+var_D0]; phkResult
0x140006b45  mov     rdx, rdi; lpSubKey
0x140006b48  mov     rcx, r13; hKey
0x140006b4b  call    cs:__imp_RegOpenKeyA
0x140006b51  test    eax, eax
0x140006b53  jnz     short loc_140006B84
0x140006b55  mov     rcx, [rbp+60h+var_D0]; hKey
0x140006b59  lea     rdx, SubKey; "CLSID"
0x140006b60  call    cs:__imp_RegDeleteKeyA
0x140006b66  mov     rcx, [rbp+60h+var_D0]; hKey
0x140006b6a  call    cs:__imp_RegCloseKey
0x140006b70  mov     rdx, rdi; lpSubKey
0x140006b73  mov     rcx, r13; hKey
0x140006b76  call    cs:__imp_RegDeleteKeyA
0x140006b7c  jmp     short loc_140006B84
0x140006b7e  call    cs:__imp_RegCloseKey
0x140006b84  inc     esi
0x140006b86  cmp     esi, r14d
0x140006b89  jb      loc_140006922
0x140006b8f  xor     r8d, r8d; wVerMinor
0x140006b92  lea     rcx, LIBID_WSHRemoteLibrary; libID
0x140006b99  xor     r9d, r9d; lcid
0x140006b9c  lea     edx, [r8+1]; wVerMajor
0x140006ba0  mov     dword ptr [rsp+160h+pptlib], edx; syskind
0x140006ba4  call    cs:__imp_UnRegisterTypeLib
0x140006baa  mov     ebx, eax
0x140006bac  test    eax, eax
0x140006bae  js      short loc_140006BB3
0x140006bb0  mov     ebx, r15d
0x140006bb3  mov     rcx, [rsp+160h+ppMalloc]
0x140006bb8  test    rcx, rcx
0x140006bbb  jz      short loc_140006BC9
0x140006bbd  mov     rax, [rcx]
0x140006bc0  mov     rax, [rax+10h]
0x140006bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bc9  test    rdi, rdi
0x140006bcc  jz      short loc_140006BD6
0x140006bce  mov     rcx, rdi; Block
0x140006bd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006bd6  mov     rcx, [rsp+160h+var_118]
0x140006bdb  test    rcx, rcx
0x140006bde  jz      short loc_140006C0A
0x140006be0  mov     rdx, [rsp+160h+var_108]
0x140006be5  test    rdx, rdx
0x140006be8  jz      short loc_140006BFE
0x140006bea  mov     rax, [rcx]
0x140006bed  mov     rax, [rax+98h]
0x140006bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bf9  mov     rcx, [rsp+160h+var_118]
0x140006bfe  mov     rax, [rcx]
0x140006c01  mov     rax, [rax+10h]
0x140006c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c0a  mov     rcx, [rsp+160h+var_110]
0x140006c0f  test    rcx, rcx
0x140006c12  jz      short loc_140006C3A
0x140006c14  mov     rdx, [rbp+60h+rclsid]
0x140006c18  test    rdx, rdx
0x140006c1b  jz      short loc_140006C2E
0x140006c1d  mov     rax, [rcx]
0x140006c20  mov     rax, [rax+60h]
0x140006c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c29  mov     rcx, [rsp+160h+var_110]
0x140006c2e  mov     rax, [rcx]
0x140006c31  mov     rax, [rax+10h]
0x140006c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c3a  mov     rcx, [rsp+160h+phkResult]; hKey
0x140006c3f  test    rcx, rcx
0x140006c42  jz      short loc_140006C4A
0x140006c44  call    cs:__imp_RegCloseKey
0x140006c4a  mov     rcx, [rsp+160h+bstrString]; bstrString
0x140006c4f  call    cs:__imp_SysFreeString
0x140006c55  mov     eax, ebx
0x140006c57  mov     rcx, [rbp+60h+var_40]
0x140006c5b  xor     rcx, rsp; StackCookie
0x140006c5e  call    __security_check_cookie
0x140006c63  add     rsp, 130h
0x140006c6a  pop     r15
0x140006c6c  pop     r14
0x140006c6e  pop     r13
0x140006c70  pop     rdi
0x140006c71  pop     rsi
0x140006c72  pop     rbx
0x140006c73  pop     rbp
0x140006c74  retn
0x140006c75  mov     ebx, 8007000Eh
0x140006c7a  jmp     loc_140006BB3
```
