# RegisterSignControl(void)

- ea: `0x1800051a8`
- end: `0x1800058c7`
- name: `?RegisterSignControl@@YAJXZ`
- size: `1823`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006df0`

## callees

- `0x1800051a8`
- `0x180005900`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `msvcrt!malloc` at `0x1800054f9`
- `msvcrt!malloc` at `0x1800054f9`
- `msvcrt!strcpy_s` at `0x180005273`
- `msvcrt!strcpy_s` at `0x180005273`
- `msvcrt!sprintf_s` at `0x180005384`
- `msvcrt!sprintf_s` at `0x1800054b4`
- `msvcrt!sprintf_s` at `0x180005528`
- `msvcrt!sprintf_s` at `0x180005384`
- `msvcrt!sprintf_s` at `0x1800054b4`
- `msvcrt!sprintf_s` at `0x180005528`
- `msvcrt!free` at `0x1800054e1`
- `msvcrt!free` at `0x18000589c`
- `msvcrt!free` at `0x1800054e1`
- `msvcrt!free` at `0x18000589c`
- `KERNEL32!GetModuleFileNameA` at `0x180005252`
- `KERNEL32!GetModuleFileNameA` at `0x180005252`
- `KERNEL32!GetModuleHandleA` at `0x18000523d`
- `KERNEL32!GetModuleHandleA` at `0x18000523d`
- `KERNEL32!MultiByteToWideChar` at `0x180005299`
- `KERNEL32!MultiByteToWideChar` at `0x180005299`
- `OLEAUT32!__imp_SysFreeString` at `0x18000544d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000588e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000544d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000588e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800054ec`
- `OLEAUT32!__imp_SysStringLen` at `0x1800054ec`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800052bc`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800052bc`
- `ADVAPI32!RegCreateKeyA` at `0x180005550`
- `ADVAPI32!RegCreateKeyA` at `0x180005590`
- `ADVAPI32!RegCreateKeyA` at `0x18000574d`
- `ADVAPI32!RegCreateKeyA` at `0x180005550`
- `ADVAPI32!RegCreateKeyA` at `0x180005590`
- `ADVAPI32!RegCreateKeyA` at `0x18000574d`
- `ADVAPI32!RegOpenKeyA` at `0x1800052fd`
- `ADVAPI32!RegOpenKeyA` at `0x1800052fd`
- `ADVAPI32!RegSetValueA` at `0x1800055cd`
- `ADVAPI32!RegSetValueA` at `0x18000564f`
- `ADVAPI32!RegSetValueA` at `0x180005691`
- `ADVAPI32!RegSetValueA` at `0x1800056d2`
- `ADVAPI32!RegSetValueA` at `0x18000570f`
- `ADVAPI32!RegSetValueA` at `0x18000578b`
- `ADVAPI32!RegSetValueA` at `0x1800055cd`
- `ADVAPI32!RegSetValueA` at `0x18000564f`
- `ADVAPI32!RegSetValueA` at `0x180005691`
- `ADVAPI32!RegSetValueA` at `0x1800056d2`
- `ADVAPI32!RegSetValueA` at `0x18000570f`
- `ADVAPI32!RegSetValueA` at `0x18000578b`
- `ADVAPI32!RegSetValueExA` at `0x18000560d`
- `ADVAPI32!RegSetValueExA` at `0x18000560d`
- `ADVAPI32!RegCloseKey` at `0x180005538`
- `ADVAPI32!RegCloseKey` at `0x180005574`
- `ADVAPI32!RegCloseKey` at `0x180005733`
- `ADVAPI32!RegCloseKey` at `0x180005841`
- `ADVAPI32!RegCloseKey` at `0x180005856`
- `ADVAPI32!RegCloseKey` at `0x18000586b`
- `ADVAPI32!RegCloseKey` at `0x18000587f`
- `ADVAPI32!RegCloseKey` at `0x180005538`
- `ADVAPI32!RegCloseKey` at `0x180005574`
- `ADVAPI32!RegCloseKey` at `0x180005733`
- `ADVAPI32!RegCloseKey` at `0x180005841`
- `ADVAPI32!RegCloseKey` at `0x180005856`
- `ADVAPI32!RegCloseKey` at `0x18000586b`
- `ADVAPI32!RegCloseKey` at `0x18000587f`
- `ole32!CoGetMalloc` at `0x18000521f`
- `ole32!CoGetMalloc` at `0x18000521f`
- `ole32!StringFromCLSID` at `0x180005325`
- `ole32!StringFromCLSID` at `0x180005490`
- `ole32!StringFromCLSID` at `0x180005325`
- `ole32!StringFromCLSID` at `0x180005490`

## string_xrefs

- `0x1800055fb`: `ThreadingModel`
- `0x1800052f6`: `CLSID`
- `0x180005784`: `CLSID`
- `0x18000522f`: `wshext.dll`
- `0x180005265`: `wshext.dll`

## pseudocode

```c
__int64 RegisterSignControl(void)
{
  void *v0; // rdi
  int Malloc; // ebx
  HMODULE ModuleHandleA; // rax
  LSTATUS v3; // eax
  unsigned int v4; // r14d
  unsigned int i; // esi
  __int64 v6; // rcx
  OLECHAR *v7; // rcx
  size_t v8; // rbx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  __int64 v11; // rax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  __int64 v14; // rax
  LSTATUS v15; // eax
  __int64 v16; // rax
  LSTATUS v17; // eax
  __int64 v18; // rax
  LSTATUS v19; // eax
  __int64 v20; // rax
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  __int64 v23; // rax
  LSTATUS v24; // eax
  ITypeLib *v25; // rcx
  __int64 v26; // rcx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  IID *v31; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v32; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  HKEY v34; // [rsp+70h] [rbp-90h] BYREF
  LPMALLOC ppMalloc; // [rsp+78h] [rbp-88h] BYREF
  IID *rclsid; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  LPOLESTR lpsz; // [rsp+90h] [rbp-70h] BYREF
  LPOLESTR v39; // [rsp+98h] [rbp-68h] BYREF
  CHAR Buffer[32]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR SubKey[48]; // [rsp+C0h] [rbp-40h] BYREF
  CHAR Data[48]; // [rsp+F0h] [rbp-10h] BYREF
  CHAR Filename[260]; // [rsp+120h] [rbp+20h] BYREF
  char v44; // [rsp+224h] [rbp+124h]
  WCHAR WideCharStr[264]; // [rsp+230h] [rbp+130h] BYREF

  pptlib = 0;
  v0 = 0;
  v29 = 0;
  rclsid = 0;
  v31 = 0;
  phkResult = 0;
  hKey = 0;
  v34 = 0;
  v32 = 0;
  bstrString = 0;
  lpsz = 0;
  v39 = 0;
  ppMalloc = 0;
  Malloc = CoGetMalloc(1u, &ppMalloc);
  if ( Malloc >= 0 )
  {
    v44 = 0;
    ModuleHandleA = GetModuleHandleA("wshext.dll");
    if ( !GetModuleFileNameA(ModuleHandleA, Filename, 0x105u) || v44 )
      strcpy_s(Filename, 0x105u, "wshext.dll");
    if ( MultiByteToWideChar(0, 0, Filename, -1, WideCharStr, 260) )
    {
      Malloc = LoadTypeLibEx(WideCharStr, REGKIND_REGISTER, &pptlib);
      if ( Malloc >= 0 )
      {
        Malloc = ((__int64 (__fastcall *)(ITypeLib *, IID **))pptlib->lpVtbl->GetLibAttr)(pptlib, &rclsid);
        if ( Malloc >= 0 )
        {
          v3 = RegOpenKeyA(HKEY_CLASSES_ROOT, "CLSID", &phkResult);
          Malloc = v3;
          if ( v3 > 0 )
            Malloc = (unsigned __int16)v3 | 0x80070000;
          if ( Malloc >= 0 )
          {
            Malloc = StringFromCLSID(rclsid, &lpsz);
            if ( Malloc >= 0 )
            {
              StringCchPrintfA(Data, 0x30u, "%S", lpsz);
              ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, lpsz);
              sprintf_s(
                Buffer,
                0x20u,
                "%d.%d",
                *(unsigned __int16 *)rclsid[1].Data4,
                *(unsigned __int16 *)&rclsid[1].Data4[2]);
              v4 = ((__int64 (__fastcall *)(ITypeLib *))pptlib->lpVtbl->GetTypeInfoCount)(pptlib);
              for ( i = 0; i < v4; ++i )
              {
                v6 = v29;
                if ( v29 )
                {
                  if ( v31 )
                  {
                    (*(void (**)(void))(*(_QWORD *)v29 + 152LL))();
                    v6 = v29;
                    v31 = 0;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
                  v29 = 0;
                }
                Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, __int64 *))pptlib->lpVtbl->GetTypeInfo)(
                           pptlib,
                           i,
                           &v29);
                if ( Malloc >= 0 )
                {
                  Malloc = (*(__int64 (__fastcall **)(__int64, IID **))(*(_QWORD *)v29 + 24LL))(v29, &v31);
                  if ( Malloc >= 0 && *(_DWORD *)&v31[2].Data4[4] == 5 && (v31[3].Data4[2] & 2) != 0 )
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
                    if ( Malloc >= 0 )
                    {
                      Malloc = StringFromCLSID(v31, &v39);
                      if ( Malloc < 0 )
                        break;
                      sprintf_s(SubKey, 0x30u, "%S", v39);
                      ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, v39);
                      v7 = bstrString;
                      if ( bstrString )
                      {
                        if ( v0 )
                        {
                          free(v0);
                          v7 = bstrString;
                        }
                        v8 = SysStringLen(v7) + 11;
                        v0 = malloc(v8);
                        if ( !v0 )
                        {
                          Malloc = -2147024882;
                          break;
                        }
                        sprintf_s((char *const)v0, (unsigned int)v8, "%S.%S", L"Scripting", bstrString);
                      }
                      if ( hKey )
                      {
                        RegCloseKey(hKey);
                        hKey = 0;
                      }
                      v9 = RegCreateKeyA(phkResult, SubKey, &hKey);
                      Malloc = v9;
                      if ( v9 > 0 )
                        Malloc = (unsigned __int16)v9 | 0x80070000;
                      if ( Malloc < 0 )
                        break;
                      if ( v32 )
                      {
                        RegCloseKey(v32);
                        v32 = 0;
                      }
                      v10 = RegCreateKeyA(hKey, "InprocServer32", &v32);
                      Malloc = v10;
                      if ( v10 > 0 )
                        Malloc = (unsigned __int16)v10 | 0x80070000;
                      if ( Malloc < 0 )
                        break;
                      v11 = -1;
                      do
                        ++v11;
                      while ( Filename[v11] );
                      v12 = RegSetValueA(v32, 0, 1u, Filename, v11);
                      Malloc = v12;
                      if ( v12 > 0 )
                        Malloc = (unsigned __int16)v12 | 0x80070000;
                      if ( Malloc < 0 )
                        break;
                      v13 = RegSetValueExA(v32, "ThreadingModel", 0, 1u, "Apartment", 9u);
                      Malloc = v13;
                      if ( v13 > 0 )
                        Malloc = (unsigned __int16)v13 | 0x80070000;
                      if ( Malloc < 0 )
                        break;
                      v14 = -1;
                      do
                        ++v14;
                      while ( Data[v14] );
                      v15 = RegSetValueA(hKey, "TypeLib", 1u, Data, v14);
                      Malloc = v15;
                      if ( v15 > 0 )
                        Malloc = (unsigned __int16)v15 | 0x80070000;
                      if ( Malloc < 0 )
                        break;
                      v16 = -1;
                      do
                        ++v16;
                      while ( Buffer[v16] );
                      v17 = RegSetValueA(hKey, "Version", 1u, Buffer, v16);
                      Malloc = v17;
                      if ( v17 > 0 )
                        Malloc = (unsigned __int16)v17 | 0x80070000;
                      if ( Malloc < 0 )
                        break;
                      if ( v0 )
                      {
                        v18 = -1;
                        do
                          ++v18;
                        while ( *((_BYTE *)v0 + v18) );
                        v19 = RegSetValueA(hKey, 0, 1u, (LPCSTR)v0, v18);
                        Malloc = v19;
                        if ( v19 > 0 )
                          Malloc = (unsigned __int16)v19 | 0x80070000;
                        if ( Malloc < 0 )
                          break;
                        v20 = -1;
                        do
                          ++v20;
                        while ( *((_BYTE *)v0 + v20) );
                        v21 = RegSetValueA(hKey, "ProgID", 1u, (LPCSTR)v0, v20);
                        Malloc = v21;
                        if ( v21 > 0 )
                          Malloc = (unsigned __int16)v21 | 0x80070000;
                        if ( Malloc < 0 )
                          break;
                        if ( v34 )
                        {
                          RegCloseKey(v34);
                          v34 = 0;
                        }
                        v22 = RegCreateKeyA(HKEY_CLASSES_ROOT, (LPCSTR)v0, &v34);
                        Malloc = v22;
                        if ( v22 > 0 )
                          Malloc = (unsigned __int16)v22 | 0x80070000;
                        if ( Malloc < 0 )
                          break;
                        v23 = -1;
                        do
                          ++v23;
                        while ( SubKey[v23] );
                        v24 = RegSetValueA(v34, "CLSID", 1u, SubKey, v23);
                        Malloc = v24;
                        if ( v24 > 0 )
                          Malloc = (unsigned __int16)v24 | 0x80070000;
                        if ( Malloc < 0 )
                          break;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      Malloc = -2147467259;
    }
  }
  if ( ppMalloc )
  {
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    ppMalloc = 0;
  }
  v25 = pptlib;
  if ( pptlib )
  {
    if ( rclsid )
    {
      ((void (*)(void))pptlib->lpVtbl->ReleaseTLibAttr)();
      v25 = pptlib;
    }
    ((void (__fastcall *)(ITypeLib *))v25->lpVtbl->Release)(v25);
  }
  v26 = v29;
  if ( v29 )
  {
    if ( v31 )
    {
      (*(void (**)(void))(*(_QWORD *)v29 + 152LL))();
      v26 = v29;
      v31 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v29 = 0;
  }
  if ( v34 )
  {
    RegCloseKey(v34);
    v34 = 0;
  }
  if ( v32 )
  {
    RegCloseKey(v32);
    v32 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  SysFreeString(bstrString);
  if ( v0 )
    free(v0);
  return (unsigned int)Malloc;
}

```

## disassembly

```asm
0x1800051a8  push    rbp
0x1800051aa  push    rbx
0x1800051ab  push    rsi
0x1800051ac  push    rdi
0x1800051ad  push    r12
0x1800051af  push    r13
0x1800051b1  push    r14
0x1800051b3  push    r15
0x1800051b5  lea     rbp, [rsp-358h]
0x1800051bd  sub     rsp, 458h
0x1800051c4  mov     rax, cs:__security_cookie
0x1800051cb  xor     rax, rsp
0x1800051ce  mov     [rbp+390h+var_50], rax
0x1800051d5  xor     r15d, r15d
0x1800051d8  lea     rdx, [rsp+490h+ppMalloc]; ppMalloc
0x1800051dd  mov     [rsp+490h+pptlib], r15
0x1800051e2  mov     edi, r15d
0x1800051e5  mov     [rsp+490h+var_448], r15
0x1800051ea  mov     [rbp+390h+rclsid], r15
0x1800051ee  lea     r13d, [r15+1]
0x1800051f2  mov     [rsp+490h+var_438], r15
0x1800051f7  mov     ecx, r13d; dwMemContext
0x1800051fa  mov     [rbp+390h+phkResult], r15
0x1800051fe  mov     [rsp+490h+hKey], r15
0x180005203  mov     [rsp+490h+var_420], r15
0x180005208  mov     [rsp+490h+var_430], r15
0x18000520d  mov     [rsp+490h+bstrString], r15
0x180005212  mov     [rbp+390h+lpsz], r15
0x180005216  mov     [rbp+390h+var_3F8], r15
0x18000521a  mov     [rsp+490h+ppMalloc], r15
0x18000521f  call    cs:__imp_CoGetMalloc
0x180005225  mov     ebx, eax
0x180005227  test    eax, eax
0x180005229  js      loc_1800057AE
0x18000522f  lea     rcx, ModuleName; "wshext.dll"
0x180005236  mov     [rbp+390h+var_26C], r15b
0x18000523d  call    cs:__imp_GetModuleHandleA
0x180005243  mov     ebx, 105h
0x180005248  lea     rdx, [rbp+390h+Filename]; lpFilename
0x18000524c  mov     rcx, rax; hModule
0x18000524f  mov     r8d, ebx; nSize
0x180005252  call    cs:__imp_GetModuleFileNameA
0x180005258  test    eax, eax
0x18000525a  jz      short loc_180005265
0x18000525c  cmp     [rbp+390h+var_26C], r15b
0x180005263  jz      short loc_180005279
0x180005265  lea     r8, ModuleName; "wshext.dll"
0x18000526c  mov     rdx, rbx; SizeInBytes
0x18000526f  lea     rcx, [rbp+390h+Filename]; Destination
0x180005273  call    cs:__imp_strcpy_s
0x180005279  lea     rax, [rbp+390h+WideCharStr]
0x180005280  mov     [rsp+490h+cchWideChar], 104h; cchWideChar
0x180005288  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000528c  mov     [rsp+490h+lpWideCharStr], rax; lpWideCharStr
0x180005291  lea     r8, [rbp+390h+Filename]; lpMultiByteStr
0x180005295  xor     edx, edx; dwFlags
0x180005297  xor     ecx, ecx; CodePage
0x180005299  call    cs:__imp_MultiByteToWideChar
0x18000529f  test    eax, eax
0x1800052a1  jnz     short loc_1800052AD
0x1800052a3  mov     ebx, 80004005h
0x1800052a8  jmp     loc_1800057AE
0x1800052ad  lea     r8, [rsp+490h+pptlib]; pptlib
0x1800052b2  mov     edx, r13d; regkind
0x1800052b5  lea     rcx, [rbp+390h+WideCharStr]; szFile
0x1800052bc  call    cs:__imp_LoadTypeLibEx
0x1800052c2  mov     ebx, eax
0x1800052c4  test    eax, eax
0x1800052c6  js      loc_1800057AE
0x1800052cc  mov     rcx, [rsp+490h+pptlib]
0x1800052d1  lea     rdx, [rbp+390h+rclsid]
0x1800052d5  mov     rax, [rcx]
0x1800052d8  mov     rax, [rax+38h]
0x1800052dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e1  mov     ebx, eax
0x1800052e3  test    eax, eax
0x1800052e5  js      loc_1800057AE
0x1800052eb  lea     r8, [rbp+390h+phkResult]; phkResult
0x1800052ef  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800052f6  lea     rdx, aClsid; "CLSID"
0x1800052fd  call    cs:__imp_RegOpenKeyA
0x180005303  mov     ebx, eax
0x180005305  mov     r12d, 80070000h
0x18000530b  test    eax, eax
0x18000530d  jle     short loc_180005315
0x18000530f  movzx   ebx, ax
0x180005312  or      ebx, r12d
0x180005315  test    ebx, ebx
0x180005317  js      loc_1800057AE
0x18000531d  mov     rcx, [rbp+390h+rclsid]; rclsid
0x180005321  lea     rdx, [rbp+390h+lpsz]; lplpsz
0x180005325  call    cs:__imp_StringFromCLSID
0x18000532b  mov     ebx, eax
0x18000532d  test    eax, eax
0x18000532f  js      loc_1800057AE
0x180005335  mov     r9, [rbp+390h+lpsz]
0x180005339  lea     r8, aS; "%S"
0x180005340  mov     edx, 30h ; '0'; unsigned __int64
0x180005345  lea     rcx, [rbp+390h+Data]; char *
0x180005349  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000534e  mov     rcx, [rsp+490h+ppMalloc]
0x180005353  mov     rdx, [rbp+390h+lpsz]
0x180005357  mov     rax, [rcx]
0x18000535a  mov     rax, [rax+28h]
0x18000535e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005363  mov     rax, [rbp+390h+rclsid]
0x180005367  lea     r8, aDD; "%d.%d"
0x18000536e  mov     edx, 20h ; ' '; BufferCount
0x180005373  movzx   ecx, word ptr [rax+1Ah]
0x180005377  movzx   r9d, word ptr [rax+18h]
0x18000537c  mov     dword ptr [rsp+490h+lpWideCharStr], ecx
0x180005380  lea     rcx, [rbp+390h+Buffer]; Buffer
0x180005384  call    cs:__imp_sprintf_s
0x18000538a  mov     rcx, [rsp+490h+pptlib]
0x18000538f  mov     rax, [rcx]
0x180005392  mov     rax, [rax+18h]
0x180005396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539b  mov     r14d, eax
0x18000539e  mov     esi, r15d
0x1800053a1  cmp     esi, r14d
0x1800053a4  jnb     loc_1800057AE
0x1800053aa  mov     rcx, [rsp+490h+var_448]
0x1800053af  test    rcx, rcx
0x1800053b2  jz      short loc_1800053E8
0x1800053b4  mov     rdx, [rsp+490h+var_438]
0x1800053b9  test    rdx, rdx
0x1800053bc  jz      short loc_1800053D7
0x1800053be  mov     rax, [rcx]
0x1800053c1  mov     rax, [rax+98h]
0x1800053c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cd  mov     rcx, [rsp+490h+var_448]
0x1800053d2  mov     [rsp+490h+var_438], r15
0x1800053d7  mov     rax, [rcx]
0x1800053da  mov     rax, [rax+10h]
0x1800053de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e3  mov     [rsp+490h+var_448], r15
0x1800053e8  mov     rcx, [rsp+490h+pptlib]
0x1800053ed  lea     r8, [rsp+490h+var_448]
0x1800053f2  mov     edx, esi
0x1800053f4  mov     rax, [rcx]
0x1800053f7  mov     rax, [rax+20h]
0x1800053fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005400  mov     ebx, eax
0x180005402  test    eax, eax
0x180005404  js      loc_1800057A1
0x18000540a  mov     rcx, [rsp+490h+var_448]
0x18000540f  lea     rdx, [rsp+490h+var_438]
0x180005414  mov     rax, [rcx]
0x180005417  mov     rax, [rax+18h]
0x18000541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005420  mov     ebx, eax
0x180005422  test    eax, eax
0x180005424  js      loc_1800057A1
0x18000542a  mov     rdx, [rsp+490h+var_438]
0x18000542f  cmp     dword ptr [rdx+2Ch], 5
0x180005433  jnz     loc_1800057A1
0x180005439  test    byte ptr [rdx+3Ah], 2
0x18000543d  jz      loc_1800057A1
0x180005443  mov     rcx, [rsp+490h+bstrString]; bstrString
0x180005448  test    rcx, rcx
0x18000544b  jz      short loc_180005458
0x18000544d  call    cs:__imp_SysFreeString
0x180005453  mov     [rsp+490h+bstrString], r15
0x180005458  mov     rcx, [rsp+490h+pptlib]
0x18000545d  lea     r8, [rsp+490h+bstrString]
0x180005462  mov     qword ptr [rsp+490h+cchWideChar], r15
0x180005467  xor     r9d, r9d
0x18000546a  mov     edx, esi
0x18000546c  mov     [rsp+490h+lpWideCharStr], r15
0x180005471  mov     rax, [rcx]
0x180005474  mov     rax, [rax+48h]
0x180005478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547d  mov     ebx, eax
0x18000547f  test    eax, eax
0x180005481  js      loc_1800057A1
0x180005487  mov     rcx, [rsp+490h+var_438]; rclsid
0x18000548c  lea     rdx, [rbp+390h+var_3F8]; lplpsz
0x180005490  call    cs:__imp_StringFromCLSID
0x180005496  mov     ebx, eax
0x180005498  test    eax, eax
0x18000549a  js      loc_1800057AE
0x1800054a0  mov     r9, [rbp+390h+var_3F8]
0x1800054a4  lea     r8, aS; "%S"
0x1800054ab  mov     edx, 30h ; '0'; BufferCount
0x1800054b0  lea     rcx, [rbp+390h+SubKey]; Buffer
0x1800054b4  call    cs:__imp_sprintf_s
0x1800054ba  mov     rcx, [rsp+490h+ppMalloc]
0x1800054bf  mov     rdx, [rbp+390h+var_3F8]
0x1800054c3  mov     rax, [rcx]
0x1800054c6  mov     rax, [rax+28h]
0x1800054ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054cf  mov     rcx, [rsp+490h+bstrString]
0x1800054d4  test    rcx, rcx
0x1800054d7  jz      short loc_18000552E
0x1800054d9  test    rdi, rdi
0x1800054dc  jz      short loc_1800054EC
0x1800054de  mov     rcx, rdi; Block
0x1800054e1  call    cs:__imp_free
0x1800054e7  mov     rcx, [rsp+490h+bstrString]; pbstr
0x1800054ec  call    cs:__imp_SysStringLen
0x1800054f2  add     eax, 0Bh
0x1800054f5  mov     ecx, eax; Size
0x1800054f7  mov     ebx, eax
0x1800054f9  call    cs:__imp_malloc
0x1800054ff  mov     rdi, rax
0x180005502  test    rax, rax
0x180005505  jz      loc_1800057A9
0x18000550b  mov     rax, [rsp+490h+bstrString]
0x180005510  lea     r9, aScripting; "Scripting"
0x180005517  lea     r8, aSS_0; "%S.%S"
0x18000551e  mov     [rsp+490h+lpWideCharStr], rax
0x180005523  mov     edx, ebx; BufferCount
0x180005525  mov     rcx, rdi; Buffer
0x180005528  call    cs:__imp_sprintf_s
0x18000552e  mov     rcx, [rsp+490h+hKey]; hKey
0x180005533  test    rcx, rcx
0x180005536  jz      short loc_180005543
0x180005538  call    cs:__imp_RegCloseKey
0x18000553e  mov     [rsp+490h+hKey], r15
0x180005543  mov     rcx, [rbp+390h+phkResult]; hKey
0x180005547  lea     r8, [rsp+490h+hKey]; phkResult
0x18000554c  lea     rdx, [rbp+390h+SubKey]; lpSubKey
0x180005550  call    cs:__imp_RegCreateKeyA
0x180005556  mov     ebx, eax
0x180005558  test    eax, eax
0x18000555a  jle     short loc_180005562
0x18000555c  movzx   ebx, ax
0x18000555f  or      ebx, r12d
0x180005562  test    ebx, ebx
0x180005564  js      loc_1800057AE
0x18000556a  mov     rcx, [rsp+490h+var_430]; hKey
0x18000556f  test    rcx, rcx
0x180005572  jz      short loc_18000557F
0x180005574  call    cs:__imp_RegCloseKey
0x18000557a  mov     [rsp+490h+var_430], r15
0x18000557f  mov     rcx, [rsp+490h+hKey]; hKey
0x180005584  lea     r8, [rsp+490h+var_430]; phkResult
0x180005589  lea     rdx, aInprocserver32_0; "InprocServer32"
0x180005590  call    cs:__imp_RegCreateKeyA
0x180005596  mov     ebx, eax
0x180005598  test    eax, eax
0x18000559a  jle     short loc_1800055A2
0x18000559c  movzx   ebx, ax
0x18000559f  or      ebx, r12d
0x1800055a2  test    ebx, ebx
0x1800055a4  js      loc_1800057AE
0x1800055aa  lea     rcx, [rbp+390h+Filename]
0x1800055ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800055b2  inc     rax
0x1800055b5  cmp     [rcx+rax], r15b
0x1800055b9  jnz     short loc_1800055B2
0x1800055bb  mov     rcx, [rsp+490h+var_430]; hKey
0x1800055c0  lea     r9, [rbp+390h+Filename]; lpData
0x1800055c4  mov     r8d, r13d; dwType
0x1800055c7  mov     dword ptr [rsp+490h+lpWideCharStr], eax; cbData
0x1800055cb  xor     edx, edx; lpSubKey
0x1800055cd  call    cs:__imp_RegSetValueA
0x1800055d3  mov     ebx, eax
0x1800055d5  test    eax, eax
0x1800055d7  jle     short loc_1800055DF
0x1800055d9  movzx   ebx, ax
0x1800055dc  or      ebx, r12d
0x1800055df  test    ebx, ebx
0x1800055e1  js      loc_1800057AE
0x1800055e7  mov     rcx, [rsp+490h+var_430]; hKey
0x1800055ec  lea     rax, Data; "Apartment"
0x1800055f3  mov     [rsp+490h+cchWideChar], 9; cbData
0x1800055fb  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180005602  mov     r9d, r13d; dwType
0x180005605  mov     [rsp+490h+lpWideCharStr], rax; lpData
0x18000560a  xor     r8d, r8d; Reserved
0x18000560d  call    cs:__imp_RegSetValueExA
0x180005613  mov     ebx, eax
0x180005615  test    eax, eax
0x180005617  jle     short loc_18000561F
0x180005619  movzx   ebx, ax
0x18000561c  or      ebx, r12d
0x18000561f  test    ebx, ebx
0x180005621  js      loc_1800057AE
0x180005627  lea     rcx, [rbp+390h+Data]
0x18000562b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000562f  inc     rax
0x180005632  cmp     [rcx+rax], r15b
0x180005636  jnz     short loc_18000562F
0x180005638  mov     rcx, [rsp+490h+hKey]; hKey
0x18000563d  lea     r9, [rbp+390h+Data]; lpData
0x180005641  mov     r8d, r13d; dwType
0x180005644  mov     dword ptr [rsp+490h+lpWideCharStr], eax; cbData
0x180005648  lea     rdx, aTypelib; "TypeLib"
0x18000564f  call    cs:__imp_RegSetValueA
0x180005655  mov     ebx, eax
0x180005657  test    eax, eax
0x180005659  jle     short loc_180005661
0x18000565b  movzx   ebx, ax
0x18000565e  or      ebx, r12d
0x180005661  test    ebx, ebx
0x180005663  js      loc_1800057AE
0x180005669  lea     rcx, [rbp+390h+Buffer]
0x18000566d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005671  inc     rax
  ... truncated ...
```
