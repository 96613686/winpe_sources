# DllRegisterServer

- ea: `0x180056e40`
- end: `0x18005736c`
- name: `DllRegisterServer`
- size: `1324`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001bf24`
- `0x18002ad14`
- `0x18003846c`
- `0x180038498`
- `0x180042098`
- `0x1800425d8`
- `0x18004494c`
- `0x180045ca8`
- `0x180056e40`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18005715c`
- `msvcrt!sprintf_s` at `0x18005718e`
- `msvcrt!sprintf_s` at `0x1800571a5`
- `msvcrt!sprintf_s` at `0x18005715c`
- `msvcrt!sprintf_s` at `0x18005718e`
- `msvcrt!sprintf_s` at `0x1800571a5`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180057042`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180057097`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180057042`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180057097`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18005705e`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800570b3`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18005705e`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800570b3`
- `KERNEL32!WideCharToMultiByte` at `0x18005712f`
- `KERNEL32!WideCharToMultiByte` at `0x18005712f`
- `KERNEL32!GetVersionExA` at `0x180056e88`
- `KERNEL32!GetVersionExA` at `0x180056e88`
- `KERNEL32!MultiByteToWideChar` at `0x180057000`
- `KERNEL32!MultiByteToWideChar` at `0x180057000`
- `KERNEL32!GetModuleHandleA` at `0x180056f8b`
- `KERNEL32!GetModuleHandleA` at `0x180056f8b`
- `KERNEL32!GetLastError` at `0x180056fab`
- `KERNEL32!GetLastError` at `0x180056fab`
- `KERNEL32!GetModuleFileNameA` at `0x180056fa1`
- `KERNEL32!GetModuleFileNameA` at `0x180056fa1`
- `ADVAPI32!RegSetValueExA` at `0x180057221`
- `ADVAPI32!RegSetValueExA` at `0x18005725f`
- `ADVAPI32!RegSetValueExA` at `0x1800572a5`
- `ADVAPI32!RegSetValueExA` at `0x1800572e4`
- `ADVAPI32!RegSetValueExA` at `0x180057324`
- `ADVAPI32!RegSetValueExA` at `0x180057221`
- `ADVAPI32!RegSetValueExA` at `0x18005725f`
- `ADVAPI32!RegSetValueExA` at `0x1800572a5`
- `ADVAPI32!RegSetValueExA` at `0x1800572e4`
- `ADVAPI32!RegSetValueExA` at `0x180057324`
- `ADVAPI32!RegCreateKeyExA` at `0x1800571e7`
- `ADVAPI32!RegCreateKeyExA` at `0x1800571e7`
- `ADVAPI32!RegCloseKey` at `0x180057230`
- `ADVAPI32!RegCloseKey` at `0x180057337`
- `ADVAPI32!RegCloseKey` at `0x180057230`
- `ADVAPI32!RegCloseKey` at `0x180057337`

## string_xrefs

- `0x1800571c2`: `Software\Microsoft\Active Setup\Installed Components\{4f645220-306d-11d2-995d-00c04f98bbc9}`
- `0x180057250`: `IsInstalled`
- `0x180057312`: `ComponentID`
- `0x180056f7d`: `vbscript.dll`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  CClassFactory *ClassFactory; // rax
  CClassFactory *v2; // rbx
  int v3; // edi
  CClassFactory *AuthorClassFactory; // rax
  CClassFactory *v5; // rbx
  CClassFactory *EncodeClassFactory; // rax
  CClassFactory *v7; // rbx
  CClassFactory *RegExpClassFactory; // rax
  CClassFactory *v9; // rbx
  HMODULE ModuleHandleA; // rax
  DWORD ModuleFileNameA; // eax
  int v12; // eax
  __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  unsigned int DefaultLocale; // eax
  __int64 v16; // rbx
  __int64 v17; // rax
  LSTATUS v18; // eax
  HKEY v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  LSTATUS v22; // eax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  ITypeLib *pptlib; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OSVERSIONINFOA VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  WCHAR WideCharStr[264]; // [rsp+110h] [rbp+10h] BYREF
  CHAR Filename[260]; // [rsp+320h] [rbp+220h] BYREF
  char v29; // [rsp+424h] [rbp+324h]
  BYTE Buffer[272]; // [rsp+430h] [rbp+330h] BYREF
  BYTE v31[272]; // [rsp+540h] [rbp+440h] BYREF
  CHAR MultiByteStr[272]; // [rsp+650h] [rbp+550h] BYREF
  BYTE v33[272]; // [rsp+760h] [rbp+660h] BYREF
  WCHAR v34[264]; // [rsp+870h] [rbp+770h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
  VersionInformation.dwOSVersionInfoSize = 148;
  if ( GetVersionExA(&VersionInformation) && VersionInformation.dwMajorVersion >= 6 )
    return 0;
  ClassFactory = CreateClassFactory();
  v2 = ClassFactory;
  if ( !ClassFactory )
    return -2147418113;
  v3 = CClassFactory::RegisterServer(ClassFactory, (BYTE *)"Both");
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( v3 < 0 )
    return v3;
  AuthorClassFactory = CreateAuthorClassFactory();
  v5 = AuthorClassFactory;
  if ( !AuthorClassFactory )
    return -2147418113;
  v3 = CClassFactory::RegisterServer(AuthorClassFactory, (BYTE *)"Both");
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v3 < 0 )
    return v3;
  EncodeClassFactory = CreateEncodeClassFactory();
  v7 = EncodeClassFactory;
  if ( !EncodeClassFactory )
    return -2147418113;
  v3 = CClassFactory::RegisterServer(EncodeClassFactory, (BYTE *)"Both");
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v3 < 0 )
    return v3;
  RegExpClassFactory = CreateRegExpClassFactory();
  v9 = RegExpClassFactory;
  if ( !RegExpClassFactory )
    return -2147418113;
  v3 = CClassFactory::RegisterServer(RegExpClassFactory, (BYTE *)"Apartment");
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v3 < 0 )
    return v3;
  v29 = 0;
  ModuleHandleA = GetModuleHandleA("vbscript.dll");
  ModuleFileNameA = GetModuleFileNameA(ModuleHandleA, Filename, 0x105u);
  if ( ModuleFileNameA )
  {
    if ( v29 )
    {
      return -2147024774;
    }
    else
    {
      pptlib = 0;
      v12 = MultiByteToWideChar(0, 0, Filename, ModuleFileNameA, WideCharStr, 260);
      if ( v12 )
      {
        v13 = v12;
        v14 = 2LL * v12 + 4;
        *(_DWORD *)&WideCharStr[v12] = 3276892;
        if ( v14 >= 0x20E )
          _report_rangecheckfailure();
        *(WCHAR *)((char *)WideCharStr + v14) = 0;
        pptlib = 0;
        v3 = LoadTypeLib(WideCharStr, &pptlib);
        if ( v3 < 0 )
          return v3;
        v3 = RegisterTypeLib(pptlib, WideCharStr, 0);
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        if ( v3 < 0 )
          return v3;
        pptlib = 0;
        WideCharStr[v13 + 1] = 51;
        v3 = LoadTypeLib(WideCharStr, &pptlib);
        if ( v3 < 0 )
          return v3;
        v3 = RegisterTypeLib(pptlib, WideCharStr, 0);
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        if ( v3 < 0 )
          return v3;
        phkResult = 0;
        DefaultLocale = GetDefaultLocale();
        if ( FGetResourceString(30000, v34, 260, DefaultLocale, 0) )
        {
          v16 = -1;
          if ( WideCharToMultiByte(0, 0, v34, -1, MultiByteStr, 260, 0, 0) )
          {
            sprintf_s((char *const)Buffer, 0x104u, "Microsoft Windows Script %d.%d", 10, 8);
            sprintf_s((char *const)v31, 0x104u, "%d,%d,%d,%d", 10, 8, 10011, 0x4000);
            sprintf_s((char *const)v33, 0x104u, "MSVBScript");
            *(_DWORD *)Data = 1;
            if ( !RegCreateKeyExA(
                    HKEY_LOCAL_MACHINE,
                    "Software\\Microsoft\\Active Setup\\Installed Components\\{4f645220-306d-11d2-995d-00c04f98bbc9}",
                    0,
                    0,
                    0,
                    0x2000000u,
                    0,
                    &phkResult,
                    0) )
            {
              v17 = -1;
              do
                ++v17;
              while ( Buffer[v17] );
              v18 = RegSetValueExA(phkResult, 0, 0, 1u, Buffer, v17);
              v19 = phkResult;
              if ( !v18 )
              {
                if ( RegSetValueExA(phkResult, "IsInstalled", 0, 4u, Data, 4u) )
                  goto LABEL_33;
                v20 = -1;
                do
                  ++v20;
                while ( v31[v20] );
                if ( RegSetValueExA(phkResult, "Version", 0, 1u, v31, v20) )
                  goto LABEL_33;
                v21 = -1;
                do
                  ++v21;
                while ( MultiByteStr[v21] );
                if ( RegSetValueExA(phkResult, "Locale", 0, 1u, (const BYTE *)MultiByteStr, v21) )
                {
LABEL_33:
                  v19 = phkResult;
                }
                else
                {
                  do
                    ++v16;
                  while ( v33[v16] );
                  v22 = RegSetValueExA(phkResult, "ComponentID", 0, 1u, v33, v16);
                  v19 = phkResult;
                  if ( !v22 )
                  {
                    RegCloseKey(phkResult);
                    return v3;
                  }
                }
              }
              RegCloseKey(v19);
            }
          }
        }
      }
      return -2147467259;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180056e40  push    rbp
0x180056e42  push    rbx
0x180056e43  push    rsi
0x180056e44  push    rdi
0x180056e45  push    r12
0x180056e47  push    r15
0x180056e49  lea     rbp, [rsp-998h]
0x180056e51  sub     rsp, 0A98h
0x180056e58  mov     rax, cs:__security_cookie
0x180056e5f  xor     rax, rsp
0x180056e62  mov     [rbp+9C0h+var_40], rax
0x180056e69  xor     edx, edx; Val
0x180056e6b  lea     rcx, [rsp+0AC0h+VersionInformation.dwMajorVersion]; void *
0x180056e70  mov     r8d, 90h; Size
0x180056e76  call    memset_0
0x180056e7b  lea     rcx, [rsp+0AC0h+VersionInformation]; lpVersionInformation
0x180056e80  mov     [rsp+0AC0h+VersionInformation.dwOSVersionInfoSize], 94h
0x180056e88  call    cs:__imp_GetVersionExA
0x180056e8e  xor     r15d, r15d
0x180056e91  test    eax, eax
0x180056e93  jz      short loc_180056EA3
0x180056e95  cmp     [rsp+0AC0h+VersionInformation.dwMajorVersion], 6
0x180056e9a  jb      short loc_180056EA3
0x180056e9c  xor     eax, eax
0x180056e9e  jmp     loc_18005734D
0x180056ea3  call    ?CreateClassFactory@@YAPEAVCClassFactory@@XZ; CreateClassFactory(void)
0x180056ea8  mov     rbx, rax
0x180056eab  test    rax, rax
0x180056eae  jz      loc_180057348
0x180056eb4  lea     rsi, aBoth; "Both"
0x180056ebb  mov     rcx, rax; this
0x180056ebe  mov     rdx, rsi; lpData
0x180056ec1  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x180056ec6  mov     rcx, [rbx]
0x180056ec9  mov     edi, eax
0x180056ecb  mov     rax, [rcx+10h]
0x180056ecf  mov     rcx, rbx
0x180056ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ed7  test    edi, edi
0x180056ed9  jns     short loc_180056EE2
0x180056edb  mov     eax, edi
0x180056edd  jmp     loc_18005734D
0x180056ee2  call    ?CreateAuthorClassFactory@@YAPEAVCClassFactory@@XZ; CreateAuthorClassFactory(void)
0x180056ee7  mov     rbx, rax
0x180056eea  test    rax, rax
0x180056eed  jz      loc_180057348
0x180056ef3  mov     rdx, rsi; lpData
0x180056ef6  mov     rcx, rax; this
0x180056ef9  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x180056efe  mov     rcx, [rbx]
0x180056f01  mov     edi, eax
0x180056f03  mov     rax, [rcx+10h]
0x180056f07  mov     rcx, rbx
0x180056f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f0f  test    edi, edi
0x180056f11  js      short loc_180056EDB
0x180056f13  call    ?CreateEncodeClassFactory@@YAPEAVCClassFactory@@XZ; CreateEncodeClassFactory(void)
0x180056f18  mov     rbx, rax
0x180056f1b  test    rax, rax
0x180056f1e  jz      loc_180057348
0x180056f24  mov     rdx, rsi; lpData
0x180056f27  mov     rcx, rax; this
0x180056f2a  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x180056f2f  mov     rcx, [rbx]
0x180056f32  mov     edi, eax
0x180056f34  mov     rax, [rcx+10h]
0x180056f38  mov     rcx, rbx
0x180056f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f40  test    edi, edi
0x180056f42  js      short loc_180056EDB
0x180056f44  call    ?CreateRegExpClassFactory@@YAPEAVCClassFactory@@XZ; CreateRegExpClassFactory(void)
0x180056f49  mov     rbx, rax
0x180056f4c  test    rax, rax
0x180056f4f  jz      loc_180057348
0x180056f55  lea     rdx, aApartment; "Apartment"
0x180056f5c  mov     rcx, rax; this
0x180056f5f  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x180056f64  mov     rcx, [rbx]
0x180056f67  mov     edi, eax
0x180056f69  mov     rax, [rcx+10h]
0x180056f6d  mov     rcx, rbx
0x180056f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f75  test    edi, edi
0x180056f77  js      loc_180056EDB
0x180056f7d  lea     rcx, aVbscriptDll_1; "vbscript.dll"
0x180056f84  mov     [rbp+9C0h+var_69C], r15b
0x180056f8b  call    cs:__imp_GetModuleHandleA
0x180056f91  mov     r8d, 105h; nSize
0x180056f97  lea     rdx, [rbp+9C0h+Filename]; lpFilename
0x180056f9e  mov     rcx, rax; hModule
0x180056fa1  call    cs:__imp_GetModuleFileNameA
0x180056fa7  test    eax, eax
0x180056fa9  jnz     short loc_180056FC6
0x180056fab  call    cs:__imp_GetLastError
0x180056fb1  test    eax, eax
0x180056fb3  jle     loc_18005734D
0x180056fb9  movzx   eax, ax
0x180056fbc  or      eax, 80070000h
0x180056fc1  jmp     loc_18005734D
0x180056fc6  cmp     [rbp+9C0h+var_69C], r15b
0x180056fcd  jz      short loc_180056FD9
0x180056fcf  mov     eax, 8007007Ah
0x180056fd4  jmp     loc_18005734D
0x180056fd9  lea     rcx, [rbp+9C0h+WideCharStr]
0x180056fdd  mov     [rsp+0AC0h+pptlib], r15
0x180056fe2  mov     r12d, 104h
0x180056fe8  lea     r8, [rbp+9C0h+Filename]; lpMultiByteStr
0x180056fef  mov     [rsp+0AC0h+cchWideChar], r12d; cchWideChar
0x180056ff4  mov     r9d, eax; cbMultiByte
0x180056ff7  mov     [rsp+0AC0h+lpWideCharStr], rcx; lpWideCharStr
0x180056ffc  xor     edx, edx; dwFlags
0x180056ffe  xor     ecx, ecx; CodePage
0x180057000  call    cs:__imp_MultiByteToWideChar
0x180057006  test    eax, eax
0x180057008  jz      loc_180057236
0x18005700e  movsxd  rbx, eax
0x180057011  lea     rcx, ds:4[rbx*2]
0x180057019  mov     dword ptr [rbp+rbx*2+9C0h+WideCharStr], 32005Ch
0x180057021  cmp     rcx, 20Eh
0x180057028  jnb     loc_180057342
0x18005702e  mov     [rbp+rcx+9C0h+WideCharStr], r15w
0x180057034  lea     rdx, [rsp+0AC0h+pptlib]; pptlib
0x180057039  lea     rcx, [rbp+9C0h+WideCharStr]; szFile
0x18005703d  mov     [rsp+0AC0h+pptlib], r15
0x180057042  call    cs:__imp_LoadTypeLib
0x180057048  mov     edi, eax
0x18005704a  test    eax, eax
0x18005704c  js      loc_180056EDB
0x180057052  mov     rcx, [rsp+0AC0h+pptlib]; ptlib
0x180057057  lea     rdx, [rbp+9C0h+WideCharStr]; szFullPath
0x18005705b  xor     r8d, r8d; szHelpDir
0x18005705e  call    cs:__imp_RegisterTypeLib
0x180057064  mov     rcx, [rsp+0AC0h+pptlib]
0x180057069  mov     edi, eax
0x18005706b  mov     rax, [rcx]
0x18005706e  mov     rax, [rax+10h]
0x180057072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057077  test    edi, edi
0x180057079  js      loc_180056EDB
0x18005707f  mov     eax, 33h ; '3'
0x180057084  mov     [rsp+0AC0h+pptlib], r15
0x180057089  lea     rdx, [rsp+0AC0h+pptlib]; pptlib
0x18005708e  mov     [rbp+rbx*2+9C0h+WideCharStr+2], ax
0x180057093  lea     rcx, [rbp+9C0h+WideCharStr]; szFile
0x180057097  call    cs:__imp_LoadTypeLib
0x18005709d  mov     edi, eax
0x18005709f  test    eax, eax
0x1800570a1  js      loc_180056EDB
0x1800570a7  mov     rcx, [rsp+0AC0h+pptlib]; ptlib
0x1800570ac  lea     rdx, [rbp+9C0h+WideCharStr]; szFullPath
0x1800570b0  xor     r8d, r8d; szHelpDir
0x1800570b3  call    cs:__imp_RegisterTypeLib
0x1800570b9  mov     rcx, [rsp+0AC0h+pptlib]
0x1800570be  mov     edi, eax
0x1800570c0  mov     rax, [rcx]
0x1800570c3  mov     rax, [rax+10h]
0x1800570c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570cc  test    edi, edi
0x1800570ce  js      loc_180056EDB
0x1800570d4  mov     [rsp+0AC0h+phkResult], r15
0x1800570d9  call    ?GetDefaultLocale@@YAKXZ; GetDefaultLocale(void)
0x1800570de  mov     r9d, eax; unsigned int
0x1800570e1  mov     dword ptr [rsp+0AC0h+lpWideCharStr], r15d; int
0x1800570e6  mov     r8d, r12d; int
0x1800570e9  lea     rdx, [rbp+9C0h+var_250]; unsigned __int16 *
0x1800570f0  mov     ecx, 7530h; int
0x1800570f5  call    ?FGetResourceString@@YAHJPEAGHKH@Z; FGetResourceString(long,ushort *,int,ulong,int)
0x1800570fa  test    eax, eax
0x1800570fc  jz      loc_180057236
0x180057102  mov     [rsp+0AC0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180057107  lea     rax, [rbp+9C0h+MultiByteStr]
0x18005710e  mov     [rsp+0AC0h+lpDefaultChar], r15; lpDefaultChar
0x180057113  lea     r8, [rbp+9C0h+var_250]; lpWideCharStr
0x18005711a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005711e  mov     [rsp+0AC0h+cchWideChar], r12d; cbMultiByte
0x180057123  mov     r9d, ebx; cchWideChar
0x180057126  mov     [rsp+0AC0h+lpWideCharStr], rax; lpMultiByteStr
0x18005712b  xor     edx, edx; dwFlags
0x18005712d  xor     ecx, ecx; CodePage
0x18005712f  call    cs:__imp_WideCharToMultiByte
0x180057135  test    eax, eax
0x180057137  jz      loc_180057236
0x18005713d  lea     esi, [rbx+0Bh]
0x180057140  mov     dword ptr [rsp+0AC0h+lpWideCharStr], 8
0x180057148  mov     r9d, esi
0x18005714b  lea     r8, aMicrosoftWindo; "Microsoft Windows Script %d.%d"
0x180057152  mov     edx, r12d; BufferCount
0x180057155  lea     rcx, [rbp+9C0h+Buffer]; Buffer
0x18005715c  call    cs:__imp_sprintf_s
0x180057162  mov     dword ptr [rsp+0AC0h+lpDefaultChar], 4000h
0x18005716a  lea     r8, aDDDD; "%d,%d,%d,%d"
0x180057171  mov     [rsp+0AC0h+cchWideChar], 271Bh
0x180057179  lea     rcx, [rbp+9C0h+var_580]; Buffer
0x180057180  mov     r9d, esi
0x180057183  mov     dword ptr [rsp+0AC0h+lpWideCharStr], 8
0x18005718b  mov     edx, r12d; BufferCount
0x18005718e  call    cs:__imp_sprintf_s
0x180057194  lea     r8, aMsvbscript; "MSVBScript"
0x18005719b  mov     edx, r12d; BufferCount
0x18005719e  lea     rcx, [rbp+9C0h+var_360]; Buffer
0x1800571a5  call    cs:__imp_sprintf_s
0x1800571ab  mov     [rsp+0AC0h+lpdwDisposition], r15; lpdwDisposition
0x1800571b0  lea     rax, [rsp+0AC0h+phkResult]
0x1800571b5  mov     [rsp+0AC0h+lpUsedDefaultChar], rax; phkResult
0x1800571ba  lea     esi, [rbx+2]
0x1800571bd  mov     [rsp+0AC0h+lpDefaultChar], r15; lpSecurityAttributes
0x1800571c2  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Active Setup\\Inst"...
0x1800571c9  mov     [rsp+0AC0h+cchWideChar], 2000000h; samDesired
0x1800571d1  xor     r9d, r9d; lpClass
0x1800571d4  xor     r8d, r8d; Reserved
0x1800571d7  mov     dword ptr [rsp+0AC0h+lpWideCharStr], r15d; dwOptions
0x1800571dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800571e3  mov     dword ptr [rsp+0AC0h+Data], esi
0x1800571e7  call    cs:__imp_RegCreateKeyExA
0x1800571ed  test    eax, eax
0x1800571ef  jnz     short loc_180057236
0x1800571f1  lea     rcx, [rbp+9C0h+Buffer]
0x1800571f8  mov     rax, rbx
0x1800571fb  inc     rax
0x1800571fe  cmp     [rcx+rax], r15b
0x180057202  jnz     short loc_1800571FB
0x180057204  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180057209  mov     r9d, esi; dwType
0x18005720c  mov     [rsp+0AC0h+cchWideChar], eax; cbData
0x180057210  xor     r8d, r8d; Reserved
0x180057213  lea     rax, [rbp+9C0h+Buffer]
0x18005721a  xor     edx, edx; lpValueName
0x18005721c  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x180057221  call    cs:__imp_RegSetValueExA
0x180057227  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x18005722c  test    eax, eax
0x18005722e  jz      short loc_180057240
0x180057230  call    cs:__imp_RegCloseKey
0x180057236  mov     eax, 80004005h
0x18005723b  jmp     loc_18005734D
0x180057240  mov     r9d, 4; dwType
0x180057246  lea     rax, [rsp+0AC0h+Data]
0x18005724b  mov     [rsp+0AC0h+cchWideChar], r9d; cbData
0x180057250  lea     rdx, aIsinstalled; "IsInstalled"
0x180057257  xor     r8d, r8d; Reserved
0x18005725a  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x18005725f  call    cs:__imp_RegSetValueExA
0x180057265  test    eax, eax
0x180057267  jz      short loc_180057270
0x180057269  mov     rcx, [rsp+0AC0h+phkResult]
0x18005726e  jmp     short loc_180057230
0x180057270  lea     rcx, [rbp+9C0h+var_580]
0x180057277  mov     rax, rbx
0x18005727a  inc     rax
0x18005727d  cmp     [rcx+rax], r15b
0x180057281  jnz     short loc_18005727A
0x180057283  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180057288  lea     rdx, aVersion; "Version"
0x18005728f  mov     [rsp+0AC0h+cchWideChar], eax; cbData
0x180057293  mov     r9d, esi; dwType
0x180057296  lea     rax, [rbp+9C0h+var_580]
0x18005729d  xor     r8d, r8d; Reserved
0x1800572a0  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x1800572a5  call    cs:__imp_RegSetValueExA
0x1800572ab  test    eax, eax
0x1800572ad  jnz     short loc_180057269
0x1800572af  lea     rcx, [rbp+9C0h+MultiByteStr]
0x1800572b6  mov     rax, rbx
0x1800572b9  inc     rax
0x1800572bc  cmp     [rcx+rax], r15b
0x1800572c0  jnz     short loc_1800572B9
0x1800572c2  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x1800572c7  lea     rdx, aLocale; "Locale"
0x1800572ce  mov     [rsp+0AC0h+cchWideChar], eax; cbData
0x1800572d2  mov     r9d, esi; dwType
0x1800572d5  lea     rax, [rbp+9C0h+MultiByteStr]
0x1800572dc  xor     r8d, r8d; Reserved
0x1800572df  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x1800572e4  call    cs:__imp_RegSetValueExA
0x1800572ea  test    eax, eax
0x1800572ec  jnz     loc_180057269
0x1800572f2  lea     rax, [rbp+9C0h+var_360]
0x1800572f9  inc     rbx
0x1800572fc  cmp     [rax+rbx], r15b
0x180057300  jnz     short loc_1800572F9
0x180057302  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180057307  lea     rax, [rbp+9C0h+var_360]
0x18005730e  mov     [rsp+0AC0h+cchWideChar], ebx; cbData
0x180057312  lea     rdx, aComponentid; "ComponentID"
0x180057319  mov     r9d, esi; dwType
0x18005731c  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x180057321  xor     r8d, r8d; Reserved
0x180057324  call    cs:__imp_RegSetValueExA
0x18005732a  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x18005732f  test    eax, eax
0x180057331  jnz     loc_180057230
0x180057337  call    cs:__imp_RegCloseKey
0x18005733d  jmp     loc_180056EDB
0x180057342  call    __report_rangecheckfailure
0x180057348  mov     eax, 8000FFFFh
0x18005734d  mov     rcx, [rbp+9C0h+var_40]
0x180057354  xor     rcx, rsp; StackCookie
0x180057357  call    __security_check_cookie
0x18005735c  add     rsp, 0A98h
0x180057363  pop     r15
  ... truncated ...
```
