# CPhoneActivationBook::GetDefaultTapiCountryCode(ushort const *,ushort * *)

- ea: `0x18001f2a0`
- end: `0x18001f534`
- name: `?GetDefaultTapiCountryCode@CPhoneActivationBook@@AEAAJPEBGPEAPEAG@Z`
- size: `660`
- prototype: `int(CPhoneActivationBook *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001f8cc`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x18001ecb0`
- `0x18001f2a0`
- `0x18003c560`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f4b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f4b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f4cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f4cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f4e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f4e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f36c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f36c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f3ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3bc`
- `SETUPAPI!SetupCloseInfFile` at `0x18001f501`
- `SETUPAPI!SetupCloseInfFile` at `0x18001f501`
- `SETUPAPI!SetupOpenInfFileW` at `0x18001f2f0`
- `SETUPAPI!SetupOpenInfFileW` at `0x18001f2f0`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001f418`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001f418`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001f445`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001f445`

## string_xrefs

- `0x18001f309`: `Tapi32.dll`

## pseudocode

```c
__int64 __fastcall CPhoneActivationBook::GetDefaultTapiCountryCode(
        CPhoneActivationBook *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HMODULE v3; // rbx
  char *v4; // rdi
  int v5; // eax
  unsigned int v6; // r14d
  signed int LastError; // eax
  __int64 v8; // rcx
  HMODULE Library; // rax
  signed int v10; // eax
  FARPROC ProcAddress; // rax
  signed int v12; // eax
  int StringCch; // eax
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-D0h] BYREF
  _INFCONTEXT Context; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ReturnBuffer[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Key[32]; // [rsp+90h] [rbp-70h] BYREF
  char v19[64]; // [rsp+D0h] [rbp-30h] BYREF

  lpLibFileName = 0;
  v3 = 0;
  memset(&Context, 0, sizeof(Context));
  v4 = (char *)SetupOpenInfFileW(a2, 0, 2u, 0);
  if ( v4 == (char *)-1LL )
  {
    LastError = GetLastError();
    v8 = (unsigned int)LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_8;
    }
LABEL_5:
    v8 = 2147500037LL;
LABEL_8:
    v6 = v8;
LABEL_26:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_27;
  }
  v5 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(L"Tapi32.dll");
  v6 = v5;
  if ( v5 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
    goto LABEL_27;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  v3 = Library;
  if ( !Library )
  {
    v10 = GetLastError();
    v6 = v10;
    if ( v10 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
    v3 = 0;
    goto LABEL_27;
  }
  ProcAddress = GetProcAddress(Library, "tapiGetLocationInfo");
  if ( !ProcAddress )
    goto LABEL_14;
  if ( ((unsigned int (__fastcall *)(WCHAR *, char *))ProcAddress)(Key, v19) )
    goto LABEL_5;
  if ( !SetupFindFirstLineW(v4, L"TapiCodes", Key, &Context)
    || !SetupGetStringFieldW(&Context, 1u, ReturnBuffer, 0x20u, 0) )
  {
LABEL_14:
    v12 = GetLastError();
    v6 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
LABEL_25:
    v8 = v6;
    goto LABEL_26;
  }
  LODWORD(lpLibFileName) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(ReturnBuffer, &lpLibFileName);
  v6 = StringCch;
  if ( StringCch < 0
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(ReturnBuffer),
        v6 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_25;
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v3 )
    FreeLibrary(v3);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    SetupCloseInfFile(v4);
  return v6;
}

```

## disassembly

```asm
0x18001f2a0  mov     [rsp-8+arg_0], rbx
0x18001f2a5  push    rbp
0x18001f2a6  push    rsi
0x18001f2a7  push    rdi
0x18001f2a8  push    r14
0x18001f2aa  push    r15
0x18001f2ac  lea     rbp, [rsp-20h]
0x18001f2b1  sub     rsp, 120h
0x18001f2b8  mov     rax, cs:__security_cookie
0x18001f2bf  xor     rax, rsp
0x18001f2c2  mov     [rbp+40h+var_30], rax
0x18001f2c6  xor     ecx, ecx
0x18001f2c8  mov     rax, rdx
0x18001f2cb  mov     r15, r8
0x18001f2ce  mov     qword ptr [rsp+140h+Context.Section], rcx
0x18001f2d3  xorps   xmm0, xmm0
0x18001f2d6  xor     esi, esi
0x18001f2d8  xor     r9d, r9d; ErrorLine
0x18001f2db  mov     [rsp+140h+lpLibFileName], rsi
0x18001f2e0  lea     r8d, [rcx+2]; InfStyle
0x18001f2e4  xor     edx, edx; InfClass
0x18001f2e6  mov     rcx, rax; FileName
0x18001f2e9  xor     ebx, ebx
0x18001f2eb  movups  xmmword ptr [rsp+140h+Context.Inf], xmm0
0x18001f2f0  call    cs:__imp_SetupOpenInfFileW
0x18001f2f7  nop     dword ptr [rax+rax+00h]
0x18001f2fc  mov     rdi, rax
0x18001f2ff  test    rax, rax
0x18001f302  jnz     short loc_18001F32D
0x18001f304  lea     rdx, [rsp+140h+lpLibFileName]
0x18001f309  lea     rcx, aTapi32Dll; "Tapi32.dll"
0x18001f310  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x18001f315  mov     r14d, eax
0x18001f318  test    eax, eax
0x18001f31a  jns     short loc_18001F35F
0x18001f31c  mov     ecx, eax
0x18001f31e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f323  mov     rsi, [rsp+140h+lpLibFileName]
0x18001f328  jmp     loc_18001F4AB
0x18001f32d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f331  jnz     short loc_18001F304
0x18001f333  call    cs:__imp_GetLastError
0x18001f33a  nop     dword ptr [rax+rax+00h]
0x18001f33f  mov     ecx, eax
0x18001f341  test    eax, eax
0x18001f343  jnz     short loc_18001F34C
0x18001f345  mov     ecx, 80004005h
0x18001f34a  jmp     short loc_18001F357
0x18001f34c  jle     short loc_18001F357
0x18001f34e  movzx   ecx, ax
0x18001f351  or      ecx, 80070000h
0x18001f357  mov     r14d, ecx
0x18001f35a  jmp     loc_18001F4A6
0x18001f35f  mov     rsi, [rsp+140h+lpLibFileName]
0x18001f364  xor     r8d, r8d; dwFlags
0x18001f367  mov     rcx, rsi; lpLibFileName
0x18001f36a  xor     edx, edx; hFile
0x18001f36c  call    cs:__imp_LoadLibraryExW
0x18001f373  nop     dword ptr [rax+rax+00h]
0x18001f378  mov     rbx, rax
0x18001f37b  test    rax, rax
0x18001f37e  jnz     short loc_18001F3A1
0x18001f380  call    cs:__imp_GetLastError
0x18001f387  nop     dword ptr [rax+rax+00h]
0x18001f38c  mov     r14d, eax
0x18001f38f  test    eax, eax
0x18001f391  jns     short loc_18001F39A
0x18001f393  mov     ecx, eax
0x18001f395  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f39a  xor     ebx, ebx
0x18001f39c  jmp     loc_18001F4AB
0x18001f3a1  mov     rcx, rax; hModule
0x18001f3a4  lea     rdx, aTapigetlocatio; "tapiGetLocationInfo"
0x18001f3ab  call    cs:__imp_GetProcAddress
0x18001f3b2  nop     dword ptr [rax+rax+00h]
0x18001f3b7  test    rax, rax
0x18001f3ba  jnz     short loc_18001F3F0
0x18001f3bc  call    cs:__imp_GetLastError
0x18001f3c3  nop     dword ptr [rax+rax+00h]
0x18001f3c8  mov     r14d, eax
0x18001f3cb  test    eax, eax
0x18001f3cd  jnz     short loc_18001F3DA
0x18001f3cf  mov     r14d, 80004005h
0x18001f3d5  jmp     loc_18001F4A3
0x18001f3da  jle     loc_18001F4A3
0x18001f3e0  movzx   r14d, ax
0x18001f3e4  or      r14d, 80070000h
0x18001f3eb  jmp     loc_18001F4A3
0x18001f3f0  lea     rdx, [rbp+40h+var_70]
0x18001f3f4  lea     rcx, [rbp+40h+Key]
0x18001f3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3fd  test    eax, eax
0x18001f3ff  jnz     loc_18001F345
0x18001f405  lea     r9, [rsp+140h+Context]; Context
0x18001f40a  mov     rcx, rdi; InfHandle
0x18001f40d  lea     r8, [rbp+40h+Key]; Key
0x18001f411  lea     rdx, Section; "TapiCodes"
0x18001f418  call    cs:__imp_SetupFindFirstLineW
0x18001f41f  nop     dword ptr [rax+rax+00h]
0x18001f424  test    eax, eax
0x18001f426  jz      short loc_18001F3BC
0x18001f428  mov     r9d, 20h ; ' '; ReturnBufferSize
0x18001f42e  mov     [rsp+140h+RequiredSize], 0; RequiredSize
0x18001f437  lea     r8, [rsp+140h+ReturnBuffer]; ReturnBuffer
0x18001f43c  lea     rcx, [rsp+140h+Context]; Context
0x18001f441  lea     edx, [r9-1Fh]; FieldIndex
0x18001f445  call    cs:__imp_SetupGetStringFieldW
0x18001f44c  nop     dword ptr [rax+rax+00h]
0x18001f451  test    eax, eax
0x18001f453  jz      loc_18001F3BC
0x18001f459  lea     rdx, [rsp+140h+lpLibFileName]
0x18001f45e  mov     dword ptr [rsp+140h+lpLibFileName], 0
0x18001f466  lea     rcx, [rsp+140h+ReturnBuffer]
0x18001f46b  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001f470  mov     r14d, eax
0x18001f473  test    eax, eax
0x18001f475  js      short loc_18001F48F
0x18001f477  mov     edx, dword ptr [rsp+140h+lpLibFileName]
0x18001f47b  lea     rcx, [rsp+140h+ReturnBuffer]; Src
0x18001f480  mov     r8, r15
0x18001f483  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001f488  mov     r14d, eax
0x18001f48b  test    eax, eax
0x18001f48d  jns     short loc_18001F496
0x18001f48f  mov     ecx, eax
0x18001f491  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f496  mov     ecx, r14d
0x18001f499  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f49e  test    r14d, r14d
0x18001f4a1  jns     short loc_18001F4AB
0x18001f4a3  mov     ecx, r14d
0x18001f4a6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f4ab  mov     ecx, r14d
0x18001f4ae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f4b3  test    rsi, rsi
0x18001f4b6  jz      short loc_18001F4E0
0x18001f4b8  call    cs:__imp_GetProcessHeap
0x18001f4bf  nop     dword ptr [rax+rax+00h]
0x18001f4c4  lea     r8, [rsi-4]; lpMem
0x18001f4c8  xor     edx, edx; dwFlags
0x18001f4ca  mov     rcx, rax; hHeap
0x18001f4cd  call    cs:__imp_HeapFree
0x18001f4d4  nop     dword ptr [rax+rax+00h]
0x18001f4d9  xor     ecx, ecx
0x18001f4db  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f4e0  test    rbx, rbx
0x18001f4e3  jz      short loc_18001F4F4
0x18001f4e5  mov     rcx, rbx; hLibModule
0x18001f4e8  call    cs:__imp_FreeLibrary
0x18001f4ef  nop     dword ptr [rax+rax+00h]
0x18001f4f4  lea     rax, [rdi-1]
0x18001f4f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f4fc  ja      short loc_18001F50D
0x18001f4fe  mov     rcx, rdi; InfHandle
0x18001f501  call    cs:__imp_SetupCloseInfFile
0x18001f508  nop     dword ptr [rax+rax+00h]
0x18001f50d  mov     eax, r14d
0x18001f510  mov     rcx, [rbp+40h+var_30]
0x18001f514  xor     rcx, rsp; StackCookie
0x18001f517  call    __security_check_cookie
0x18001f51c  mov     rbx, [rsp+140h+arg_0]
0x18001f524  add     rsp, 120h
0x18001f52b  pop     r15
0x18001f52d  pop     r14
0x18001f52f  pop     rdi
0x18001f530  pop     rsi
0x18001f531  pop     rbp
0x18001f532  retn
```
