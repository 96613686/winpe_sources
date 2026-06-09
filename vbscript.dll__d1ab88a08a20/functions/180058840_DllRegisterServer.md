# DllRegisterServer

- ea: `0x180058840`
- end: `0x180058deb`
- name: `DllRegisterServer`
- size: `1451`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180015fec`
- `0x18003a5bc`
- `0x18003a5e8`
- `0x18003f8b8`
- `0x1800436f4`
- `0x180043c68`
- `0x180045c4c`
- `0x180047098`
- `0x180058840`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180058b98`
- `msvcrt!sprintf_s` at `0x180058bd0`
- `msvcrt!sprintf_s` at `0x180058bed`
- `msvcrt!sprintf_s` at `0x180058b98`
- `msvcrt!sprintf_s` at `0x180058bd0`
- `msvcrt!sprintf_s` at `0x180058bed`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180058a60`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180058ac1`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180058a60`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180058ac1`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180058a82`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180058ae3`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180058a82`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180058ae3`
- `KERNEL32!WideCharToMultiByte` at `0x180058b65`
- `KERNEL32!WideCharToMultiByte` at `0x180058b65`
- `KERNEL32!GetVersionExA` at `0x180058888`
- `KERNEL32!GetVersionExA` at `0x180058888`
- `KERNEL32!MultiByteToWideChar` at `0x180058a18`
- `KERNEL32!MultiByteToWideChar` at `0x180058a18`
- `KERNEL32!GetModuleHandleA` at `0x180058991`
- `KERNEL32!GetModuleHandleA` at `0x180058991`
- `KERNEL32!GetLastError` at `0x1800589bd`
- `KERNEL32!GetLastError` at `0x1800589bd`
- `KERNEL32!GetModuleFileNameA` at `0x1800589ad`
- `KERNEL32!GetModuleFileNameA` at `0x1800589ad`
- `ADVAPI32!RegSetValueExA` at `0x180058c75`
- `ADVAPI32!RegSetValueExA` at `0x180058cbf`
- `ADVAPI32!RegSetValueExA` at `0x180058d0b`
- `ADVAPI32!RegSetValueExA` at `0x180058d50`
- `ADVAPI32!RegSetValueExA` at `0x180058d96`
- `ADVAPI32!RegSetValueExA` at `0x180058c75`
- `ADVAPI32!RegSetValueExA` at `0x180058cbf`
- `ADVAPI32!RegSetValueExA` at `0x180058d0b`
- `ADVAPI32!RegSetValueExA` at `0x180058d50`
- `ADVAPI32!RegSetValueExA` at `0x180058d96`
- `ADVAPI32!RegCreateKeyExA` at `0x180058c35`
- `ADVAPI32!RegCreateKeyExA` at `0x180058c35`
- `ADVAPI32!RegCloseKey` at `0x180058c8a`
- `ADVAPI32!RegCloseKey` at `0x180058daf`
- `ADVAPI32!RegCloseKey` at `0x180058c8a`
- `ADVAPI32!RegCloseKey` at `0x180058daf`

## string_xrefs

- `0x180058c10`: `Software\Microsoft\Active Setup\Installed Components\{4f645220-306d-11d2-995d-00c04f98bbc9}`
- `0x180058cb0`: `IsInstalled`
- `0x180058d84`: `ComponentID`
- `0x180058983`: `vbscript.dll`

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
0x180058840  push    rbp
0x180058842  push    rbx
0x180058843  push    rsi
0x180058844  push    rdi
0x180058845  push    r12
0x180058847  push    r15
0x180058849  lea     rbp, [rsp-998h]
0x180058851  sub     rsp, 0A98h
0x180058858  mov     rax, cs:__security_cookie
0x18005885f  xor     rax, rsp
0x180058862  mov     [rbp+9C0h+var_40], rax
0x180058869  xor     edx, edx; Val
0x18005886b  lea     rcx, [rsp+0AC0h+VersionInformation.dwMajorVersion]; void *
0x180058870  mov     r8d, 90h; Size
0x180058876  call    memset_0
0x18005887b  lea     rcx, [rsp+0AC0h+VersionInformation]; lpVersionInformation
0x180058880  mov     [rsp+0AC0h+VersionInformation.dwOSVersionInfoSize], 94h
0x180058888  call    cs:__imp_GetVersionExA
0x18005888f  nop     dword ptr [rax+rax+00h]
0x180058894  xor     r15d, r15d
0x180058897  test    eax, eax
0x180058899  jz      short loc_1800588A9
0x18005889b  cmp     [rsp+0AC0h+VersionInformation.dwMajorVersion], 6
0x1800588a0  jb      short loc_1800588A9
0x1800588a2  xor     eax, eax
0x1800588a4  jmp     loc_180058DCB
0x1800588a9  call    ?CreateClassFactory@@YAPEAVCClassFactory@@XZ; CreateClassFactory(void)
0x1800588ae  mov     rbx, rax
0x1800588b1  test    rax, rax
0x1800588b4  jz      loc_180058DC6
0x1800588ba  lea     rsi, aBoth; "Both"
0x1800588c1  mov     rcx, rax; this
0x1800588c4  mov     rdx, rsi; lpData
0x1800588c7  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x1800588cc  mov     rcx, [rbx]
0x1800588cf  mov     edi, eax
0x1800588d1  mov     rax, [rcx+10h]
0x1800588d5  mov     rcx, rbx
0x1800588d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588dd  test    edi, edi
0x1800588df  jns     short loc_1800588E8
0x1800588e1  mov     eax, edi
0x1800588e3  jmp     loc_180058DCB
0x1800588e8  call    ?CreateAuthorClassFactory@@YAPEAVCClassFactory@@XZ; CreateAuthorClassFactory(void)
0x1800588ed  mov     rbx, rax
0x1800588f0  test    rax, rax
0x1800588f3  jz      loc_180058DC6
0x1800588f9  mov     rdx, rsi; lpData
0x1800588fc  mov     rcx, rax; this
0x1800588ff  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x180058904  mov     rcx, [rbx]
0x180058907  mov     edi, eax
0x180058909  mov     rax, [rcx+10h]
0x18005890d  mov     rcx, rbx
0x180058910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058915  test    edi, edi
0x180058917  js      short loc_1800588E1
0x180058919  call    ?CreateEncodeClassFactory@@YAPEAVCClassFactory@@XZ; CreateEncodeClassFactory(void)
0x18005891e  mov     rbx, rax
0x180058921  test    rax, rax
0x180058924  jz      loc_180058DC6
0x18005892a  mov     rdx, rsi; lpData
0x18005892d  mov     rcx, rax; this
0x180058930  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x180058935  mov     rcx, [rbx]
0x180058938  mov     edi, eax
0x18005893a  mov     rax, [rcx+10h]
0x18005893e  mov     rcx, rbx
0x180058941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058946  test    edi, edi
0x180058948  js      short loc_1800588E1
0x18005894a  call    ?CreateRegExpClassFactory@@YAPEAVCClassFactory@@XZ; CreateRegExpClassFactory(void)
0x18005894f  mov     rbx, rax
0x180058952  test    rax, rax
0x180058955  jz      loc_180058DC6
0x18005895b  lea     rdx, aApartment; "Apartment"
0x180058962  mov     rcx, rax; this
0x180058965  call    ?RegisterServer@CClassFactory@@QEAAJPEBD@Z; CClassFactory::RegisterServer(char const *)
0x18005896a  mov     rcx, [rbx]
0x18005896d  mov     edi, eax
0x18005896f  mov     rax, [rcx+10h]
0x180058973  mov     rcx, rbx
0x180058976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005897b  test    edi, edi
0x18005897d  js      loc_1800588E1
0x180058983  lea     rcx, aVbscriptDll_1; "vbscript.dll"
0x18005898a  mov     [rbp+9C0h+var_69C], r15b
0x180058991  call    cs:__imp_GetModuleHandleA
0x180058998  nop     dword ptr [rax+rax+00h]
0x18005899d  mov     r8d, 105h; nSize
0x1800589a3  lea     rdx, [rbp+9C0h+Filename]; lpFilename
0x1800589aa  mov     rcx, rax; hModule
0x1800589ad  call    cs:__imp_GetModuleFileNameA
0x1800589b4  nop     dword ptr [rax+rax+00h]
0x1800589b9  test    eax, eax
0x1800589bb  jnz     short loc_1800589DE
0x1800589bd  call    cs:__imp_GetLastError
0x1800589c4  nop     dword ptr [rax+rax+00h]
0x1800589c9  test    eax, eax
0x1800589cb  jle     loc_180058DCB
0x1800589d1  movzx   eax, ax
0x1800589d4  or      eax, 80070000h
0x1800589d9  jmp     loc_180058DCB
0x1800589de  cmp     [rbp+9C0h+var_69C], r15b
0x1800589e5  jz      short loc_1800589F1
0x1800589e7  mov     eax, 8007007Ah
0x1800589ec  jmp     loc_180058DCB
0x1800589f1  lea     rcx, [rbp+9C0h+WideCharStr]
0x1800589f5  mov     [rsp+0AC0h+pptlib], r15
0x1800589fa  mov     r12d, 104h
0x180058a00  lea     r8, [rbp+9C0h+Filename]; lpMultiByteStr
0x180058a07  mov     [rsp+0AC0h+cchWideChar], r12d; cchWideChar
0x180058a0c  mov     r9d, eax; cbMultiByte
0x180058a0f  mov     [rsp+0AC0h+lpWideCharStr], rcx; lpWideCharStr
0x180058a14  xor     edx, edx; dwFlags
0x180058a16  xor     ecx, ecx; CodePage
0x180058a18  call    cs:__imp_MultiByteToWideChar
0x180058a1f  nop     dword ptr [rax+rax+00h]
0x180058a24  test    eax, eax
0x180058a26  jz      loc_180058C96
0x180058a2c  movsxd  rbx, eax
0x180058a2f  lea     rcx, ds:4[rbx*2]
0x180058a37  mov     dword ptr [rbp+rbx*2+9C0h+WideCharStr], 32005Ch
0x180058a3f  cmp     rcx, 20Eh
0x180058a46  jnb     loc_180058DC0
0x180058a4c  mov     [rbp+rcx+9C0h+WideCharStr], r15w
0x180058a52  lea     rdx, [rsp+0AC0h+pptlib]; pptlib
0x180058a57  lea     rcx, [rbp+9C0h+WideCharStr]; szFile
0x180058a5b  mov     [rsp+0AC0h+pptlib], r15
0x180058a60  call    cs:__imp_LoadTypeLib
0x180058a67  nop     dword ptr [rax+rax+00h]
0x180058a6c  mov     edi, eax
0x180058a6e  test    eax, eax
0x180058a70  js      loc_1800588E1
0x180058a76  mov     rcx, [rsp+0AC0h+pptlib]; ptlib
0x180058a7b  lea     rdx, [rbp+9C0h+WideCharStr]; szFullPath
0x180058a7f  xor     r8d, r8d; szHelpDir
0x180058a82  call    cs:__imp_RegisterTypeLib
0x180058a89  nop     dword ptr [rax+rax+00h]
0x180058a8e  mov     rcx, [rsp+0AC0h+pptlib]
0x180058a93  mov     edi, eax
0x180058a95  mov     rax, [rcx]
0x180058a98  mov     rax, [rax+10h]
0x180058a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058aa1  test    edi, edi
0x180058aa3  js      loc_1800588E1
0x180058aa9  mov     eax, 33h ; '3'
0x180058aae  mov     [rsp+0AC0h+pptlib], r15
0x180058ab3  lea     rdx, [rsp+0AC0h+pptlib]; pptlib
0x180058ab8  mov     [rbp+rbx*2+9C0h+WideCharStr+2], ax
0x180058abd  lea     rcx, [rbp+9C0h+WideCharStr]; szFile
0x180058ac1  call    cs:__imp_LoadTypeLib
0x180058ac8  nop     dword ptr [rax+rax+00h]
0x180058acd  mov     edi, eax
0x180058acf  test    eax, eax
0x180058ad1  js      loc_1800588E1
0x180058ad7  mov     rcx, [rsp+0AC0h+pptlib]; ptlib
0x180058adc  lea     rdx, [rbp+9C0h+WideCharStr]; szFullPath
0x180058ae0  xor     r8d, r8d; szHelpDir
0x180058ae3  call    cs:__imp_RegisterTypeLib
0x180058aea  nop     dword ptr [rax+rax+00h]
0x180058aef  mov     rcx, [rsp+0AC0h+pptlib]
0x180058af4  mov     edi, eax
0x180058af6  mov     rax, [rcx]
0x180058af9  mov     rax, [rax+10h]
0x180058afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b02  test    edi, edi
0x180058b04  js      loc_1800588E1
0x180058b0a  mov     [rsp+0AC0h+phkResult], r15
0x180058b0f  call    ?GetDefaultLocale@@YAKXZ; GetDefaultLocale(void)
0x180058b14  mov     r9d, eax; unsigned int
0x180058b17  mov     dword ptr [rsp+0AC0h+lpWideCharStr], r15d; int
0x180058b1c  mov     r8d, r12d; int
0x180058b1f  lea     rdx, [rbp+9C0h+var_250]; unsigned __int16 *
0x180058b26  mov     ecx, 7530h; int
0x180058b2b  call    ?FGetResourceString@@YAHJPEAGHKH@Z; FGetResourceString(long,ushort *,int,ulong,int)
0x180058b30  test    eax, eax
0x180058b32  jz      loc_180058C96
0x180058b38  mov     [rsp+0AC0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180058b3d  lea     rax, [rbp+9C0h+MultiByteStr]
0x180058b44  mov     [rsp+0AC0h+lpDefaultChar], r15; lpDefaultChar
0x180058b49  lea     r8, [rbp+9C0h+var_250]; lpWideCharStr
0x180058b50  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180058b54  mov     [rsp+0AC0h+cchWideChar], r12d; cbMultiByte
0x180058b59  mov     r9d, ebx; cchWideChar
0x180058b5c  mov     [rsp+0AC0h+lpWideCharStr], rax; lpMultiByteStr
0x180058b61  xor     edx, edx; dwFlags
0x180058b63  xor     ecx, ecx; CodePage
0x180058b65  call    cs:__imp_WideCharToMultiByte
0x180058b6c  nop     dword ptr [rax+rax+00h]
0x180058b71  test    eax, eax
0x180058b73  jz      loc_180058C96
0x180058b79  lea     esi, [rbx+0Bh]
0x180058b7c  mov     dword ptr [rsp+0AC0h+lpWideCharStr], 8
0x180058b84  mov     r9d, esi
0x180058b87  lea     r8, aMicrosoftWindo; "Microsoft Windows Script %d.%d"
0x180058b8e  mov     edx, r12d; BufferCount
0x180058b91  lea     rcx, [rbp+9C0h+Buffer]; Buffer
0x180058b98  call    cs:__imp_sprintf_s
0x180058b9f  nop     dword ptr [rax+rax+00h]
0x180058ba4  mov     dword ptr [rsp+0AC0h+lpDefaultChar], 4000h
0x180058bac  lea     r8, aDDDD; "%d,%d,%d,%d"
0x180058bb3  mov     [rsp+0AC0h+cchWideChar], 271Bh
0x180058bbb  lea     rcx, [rbp+9C0h+var_580]; Buffer
0x180058bc2  mov     r9d, esi
0x180058bc5  mov     dword ptr [rsp+0AC0h+lpWideCharStr], 8
0x180058bcd  mov     edx, r12d; BufferCount
0x180058bd0  call    cs:__imp_sprintf_s
0x180058bd7  nop     dword ptr [rax+rax+00h]
0x180058bdc  lea     r8, aMsvbscript; "MSVBScript"
0x180058be3  mov     edx, r12d; BufferCount
0x180058be6  lea     rcx, [rbp+9C0h+var_360]; Buffer
0x180058bed  call    cs:__imp_sprintf_s
0x180058bf4  nop     dword ptr [rax+rax+00h]
0x180058bf9  mov     [rsp+0AC0h+lpdwDisposition], r15; lpdwDisposition
0x180058bfe  lea     rax, [rsp+0AC0h+phkResult]
0x180058c03  mov     [rsp+0AC0h+lpUsedDefaultChar], rax; phkResult
0x180058c08  lea     esi, [rbx+2]
0x180058c0b  mov     [rsp+0AC0h+lpDefaultChar], r15; lpSecurityAttributes
0x180058c10  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Active Setup\\Inst"...
0x180058c17  mov     [rsp+0AC0h+cchWideChar], 2000000h; samDesired
0x180058c1f  xor     r9d, r9d; lpClass
0x180058c22  xor     r8d, r8d; Reserved
0x180058c25  mov     dword ptr [rsp+0AC0h+lpWideCharStr], r15d; dwOptions
0x180058c2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058c31  mov     dword ptr [rsp+0AC0h+Data], esi
0x180058c35  call    cs:__imp_RegCreateKeyExA
0x180058c3c  nop     dword ptr [rax+rax+00h]
0x180058c41  test    eax, eax
0x180058c43  jnz     short loc_180058C96
0x180058c45  lea     rcx, [rbp+9C0h+Buffer]
0x180058c4c  mov     rax, rbx
0x180058c4f  inc     rax
0x180058c52  cmp     [rcx+rax], r15b
0x180058c56  jnz     short loc_180058C4F
0x180058c58  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180058c5d  mov     r9d, esi; dwType
0x180058c60  mov     [rsp+0AC0h+cchWideChar], eax; cbData
0x180058c64  xor     r8d, r8d; Reserved
0x180058c67  lea     rax, [rbp+9C0h+Buffer]
0x180058c6e  xor     edx, edx; lpValueName
0x180058c70  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x180058c75  call    cs:__imp_RegSetValueExA
0x180058c7c  nop     dword ptr [rax+rax+00h]
0x180058c81  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180058c86  test    eax, eax
0x180058c88  jz      short loc_180058CA0
0x180058c8a  call    cs:__imp_RegCloseKey
0x180058c91  nop     dword ptr [rax+rax+00h]
0x180058c96  mov     eax, 80004005h
0x180058c9b  jmp     loc_180058DCB
0x180058ca0  mov     r9d, 4; dwType
0x180058ca6  lea     rax, [rsp+0AC0h+Data]
0x180058cab  mov     [rsp+0AC0h+cchWideChar], r9d; cbData
0x180058cb0  lea     rdx, aIsinstalled; "IsInstalled"
0x180058cb7  xor     r8d, r8d; Reserved
0x180058cba  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x180058cbf  call    cs:__imp_RegSetValueExA
0x180058cc6  nop     dword ptr [rax+rax+00h]
0x180058ccb  test    eax, eax
0x180058ccd  jz      short loc_180058CD6
0x180058ccf  mov     rcx, [rsp+0AC0h+phkResult]
0x180058cd4  jmp     short loc_180058C8A
0x180058cd6  lea     rcx, [rbp+9C0h+var_580]
0x180058cdd  mov     rax, rbx
0x180058ce0  inc     rax
0x180058ce3  cmp     [rcx+rax], r15b
0x180058ce7  jnz     short loc_180058CE0
0x180058ce9  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180058cee  lea     rdx, aVersion; "Version"
0x180058cf5  mov     [rsp+0AC0h+cchWideChar], eax; cbData
0x180058cf9  mov     r9d, esi; dwType
0x180058cfc  lea     rax, [rbp+9C0h+var_580]
0x180058d03  xor     r8d, r8d; Reserved
0x180058d06  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x180058d0b  call    cs:__imp_RegSetValueExA
0x180058d12  nop     dword ptr [rax+rax+00h]
0x180058d17  test    eax, eax
0x180058d19  jnz     short loc_180058CCF
0x180058d1b  lea     rcx, [rbp+9C0h+MultiByteStr]
0x180058d22  mov     rax, rbx
0x180058d25  inc     rax
0x180058d28  cmp     [rcx+rax], r15b
0x180058d2c  jnz     short loc_180058D25
0x180058d2e  mov     rcx, [rsp+0AC0h+phkResult]; hKey
0x180058d33  lea     rdx, aLocale; "Locale"
0x180058d3a  mov     [rsp+0AC0h+cchWideChar], eax; cbData
0x180058d3e  mov     r9d, esi; dwType
0x180058d41  lea     rax, [rbp+9C0h+MultiByteStr]
0x180058d48  xor     r8d, r8d; Reserved
0x180058d4b  mov     [rsp+0AC0h+lpWideCharStr], rax; lpData
0x180058d50  call    cs:__imp_RegSetValueExA
0x180058d57  nop     dword ptr [rax+rax+00h]
0x180058d5c  test    eax, eax
0x180058d5e  jnz     loc_180058CCF
0x180058d64  lea     rax, [rbp+9C0h+var_360]
0x180058d6b  inc     rbx
0x180058d6e  cmp     [rax+rbx], r15b
0x180058d72  jnz     short loc_180058D6B
0x180058d74  mov     rcx, [rsp+0AC0h+phkResult]; hKey
  ... truncated ...
```
