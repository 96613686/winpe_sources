# InitializeSharedModules(void)

- ea: `0x383893ff0`
- end: `0x38389417c`
- name: `?InitializeSharedModules@@YAHXZ`
- size: `396`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3838963c0`
- `0x3838a0ef0`

## callees

- `0x383892de0`
- `0x383893ff0`
- `0x383894210`
- `0x38391ac30`
- `0x38391ac40`
- `0x38391ac90`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x3838be93f`
- `KERNEL32!FreeLibrary` at `0x3838bea0a`
- `KERNEL32!FreeLibrary` at `0x3838be93f`
- `KERNEL32!FreeLibrary` at `0x3838bea0a`
- `KERNEL32!GetModuleHandleW` at `0x383894126`
- `KERNEL32!GetModuleHandleW` at `0x383894126`
- `KERNEL32!LoadLibraryW` at `0x383894084`
- `KERNEL32!LoadLibraryW` at `0x3838940f6`
- `KERNEL32!LoadLibraryW` at `0x3838be953`
- `KERNEL32!LoadLibraryW` at `0x383894084`
- `KERNEL32!LoadLibraryW` at `0x3838940f6`
- `KERNEL32!LoadLibraryW` at `0x3838be953`
- `KERNEL32!GetProcAddress` at `0x3838940a4`
- `KERNEL32!GetProcAddress` at `0x3838940bf`
- `KERNEL32!GetProcAddress` at `0x383894112`
- `KERNEL32!GetProcAddress` at `0x38389413f`
- `KERNEL32!GetProcAddress` at `0x3838be973`
- `KERNEL32!GetProcAddress` at `0x3838be98e`
- `KERNEL32!GetProcAddress` at `0x3838be9a9`
- `KERNEL32!GetProcAddress` at `0x3838940a4`
- `KERNEL32!GetProcAddress` at `0x3838940bf`
- `KERNEL32!GetProcAddress` at `0x383894112`
- `KERNEL32!GetProcAddress` at `0x38389413f`
- `KERNEL32!GetProcAddress` at `0x3838be973`
- `KERNEL32!GetProcAddress` at `0x3838be98e`
- `KERNEL32!GetProcAddress` at `0x3838be9a9`
- `ADVAPI32!ReportEventW` at `0x3838be8df`
- `ADVAPI32!ReportEventW` at `0x3838be8df`
- `ADVAPI32!RegisterEventSourceW` at `0x3838be8a9`
- `ADVAPI32!RegisterEventSourceW` at `0x3838be8a9`
- `ADVAPI32!DeregisterEventSource` at `0x3838be8e8`
- `ADVAPI32!DeregisterEventSource` at `0x3838be8e8`

## string_xrefs

- `0x3838940ef`: `advapi32.dll`
- `0x3838be94c`: `advapi32.dll`
- `0x38389407d`: `crypt32.dll`
- `0x38389411f`: `ntdll.dll`
- `0x383894135`: `NtCompareTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitializeSharedModules(const unsigned __int16 *a1, HINSTANCE a2, HINSTANCE *a3)
{
  HMODULE LibraryW; // rax
  int (*ProcAddress)(void *, unsigned int, unsigned int); // rax
  HMODULE v5; // rax
  HMODULE ModuleHandleW; // rax
  unsigned int v7; // edx
  void *v8; // r8
  HANDLE v10; // rax
  void *v11; // rbx
  HMODULE v12; // rax
  int (*v13)(int); // rax

  if ( (bidGblFlags & 4) != 0 && off_383B4A718[0] && bidID != -1 )
    off_383B15050();
  if ( (g_uInitializationStatus & 0x110) != 0 )
    return 1;
  LoadResourceDLL(a1, a2, a3);
  if ( g_hinstance_language )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B431B0[0], 377865, off_383B49120[0], 369);
    if ( bidID != -1 )
      off_383B15020();
    LibraryW = LoadLibraryW(L"crypt32.dll");
    g_hCrypt = LibraryW;
    if ( LibraryW )
    {
      g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(
                                                                               LibraryW,
                                                                               "CryptProtectMemory");
      ProcAddress = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(g_hCrypt, "CryptUnprotectMemory");
      g_pfnCryptUnprotectMemory = ProcAddress;
      if ( g_pfnCryptProtectMemory && ProcAddress )
      {
        if ( g_hCrypt )
          goto LABEL_11;
      }
      else
      {
        g_pfnCryptProtectMemory = 0;
        g_pfnCryptUnprotectMemory = 0;
        FreeLibrary(g_hCrypt);
        g_hCrypt = 0;
      }
    }
    v12 = LoadLibraryW(L"advapi32.dll");
    g_hCrypt = v12;
    if ( v12 )
    {
      g_pfnRtlEncryptMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(v12, "SystemFunction040");
      g_pfnRtlDecryptMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(g_hCrypt, "SystemFunction041");
      v13 = (int (*)(int))GetProcAddress(g_hCrypt, "LsaNtStatusToWinError");
      g_pfnLsaNtStatusToWinError = v13;
      if ( g_pfnRtlEncryptMemory && g_pfnRtlDecryptMemory && v13 )
      {
        g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))CryptProtectMemoryInternal;
        g_pfnCryptUnprotectMemory = (int (*)(void *, unsigned int, unsigned int))CryptUnprotectMemoryInternal;
      }
      else
      {
        g_pfnRtlEncryptMemory = 0;
        g_pfnRtlDecryptMemory = 0;
        g_pfnLsaNtStatusToWinError = 0;
        FreeLibrary(g_hCrypt);
        g_hCrypt = 0;
      }
    }
LABEL_11:
    v5 = LoadLibraryW(L"advapi32.dll");
    g_hEvt = v5;
    if ( v5 )
      g_pfnEventActivityIdControl = GetProcAddress(v5, "EventActivityIdControl");
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
    {
      g_pfnNtCompareTokens = (int (*)(void *, void *, unsigned __int8 *))GetProcAddress(
                                                                           ModuleHandleW,
                                                                           "NtCompareTokens");
      if ( g_pfnNtCompareTokens )
        return (unsigned int)DllMain_Sni((HINSTANCE)1, v7, v8);
    }
    return 0;
  }
  if ( !g_fIsEmbeddedSNAC )
  {
    v10 = RegisterEventSourceW(0, L"SQLNCLI11.1");
    v11 = v10;
    if ( v10 )
    {
      ReportEventW(v10, 1u, 0, 0xC0000001, 0, 0, 0, 0, 0);
      DeregisterEventSource(v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x383893ff0  push    rdi
0x383893ff2  sub     rsp, 60h
0x383893ff6  mov     [rsp+68h+var_18], 0FFFFFFFFFFFFFFFEh
0x383893fff  mov     [rsp+68h+arg_8], rbx
0x383894004  mov     [rsp+68h+arg_0], 0FFFFFFFFFFFFFFFFh
0x38389400d  xor     edi, edi
0x38389400f  test    byte ptr cs:_bidGblFlags, 4
0x383894016  jnz     loc_3838BE813
0x38389401c  mov     eax, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x383894022  test    eax, 110h
0x383894027  jnz     loc_3838BE85F
0x38389402d  call    ?LoadResourceDLL@@YAJPEBGPEAUHINSTANCE__@@PEAPEAU1@@Z; LoadResourceDLL(ushort const *,HINSTANCE__ *,HINSTANCE__ * *)
0x383894032  cmp     cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hinstance_language
0x383894039  jz      loc_3838BE897
0x38389403f  test    byte ptr cs:_bidGblFlags, 2
0x383894046  jnz     loc_3838BE8F4
0x38389404c  mov     rcx, cs:_bidID
0x383894053  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383894057  jz      short loc_38389407D
0x383894059  mov     qword ptr [rsp+68h+wNumStrings], rdi
0x38389405e  mov     rax, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_language
0x383894065  mov     [rsp+68h+lpUserSid], rax
0x38389406a  xor     r9d, r9d
0x38389406d  mov     r8d, 40000024h
0x383894073  or      rdx, 0FFFFFFFFFFFFFFFFh
0x383894077  call    cs:off_383B15020
0x38389407d  lea     rcx, LibFileName; "crypt32.dll"
0x383894084  call    cs:__imp_LoadLibraryW
0x38389408a  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x383894091  test    rax, rax
0x383894094  jz      loc_3838BE94C
0x38389409a  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x3838940a1  mov     rcx, rax; hModule
0x3838940a4  call    cs:__imp_GetProcAddress
0x3838940aa  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x3838940b1  lea     rdx, aCryptunprotect; "CryptUnprotectMemory"
0x3838940b8  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x3838940bf  call    cs:__imp_GetProcAddress
0x3838940c5  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x3838940cc  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rdi; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x3838940d3  jz      loc_3838BE92A
0x3838940d9  test    rax, rax
0x3838940dc  jz      loc_3838BE92A
0x3838940e2  cmp     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hCrypt
0x3838940e9  jz      loc_3838BE928
0x3838940ef  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x3838940f6  call    cs:__imp_LoadLibraryW
0x3838940fc  mov     cs:?g_hEvt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEvt
0x383894103  test    rax, rax
0x383894106  jz      short loc_38389411F
0x383894108  lea     rdx, aEventactivityi; "EventActivityIdControl"
0x38389410f  mov     rcx, rax; hModule
0x383894112  call    cs:__imp_GetProcAddress
0x383894118  mov     cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA, rax; __int64 (*g_pfnEventActivityIdControl)(void)
0x38389411f  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x383894126  call    cs:__imp_GetModuleHandleW
0x38389412c  test    rax, rax
0x38389412f  jz      loc_3838BEA52
0x383894135  lea     rdx, aNtcomparetoken; "NtCompareTokens"
0x38389413c  mov     rcx, rax; hModule
0x38389413f  call    cs:__imp_GetProcAddress
0x383894145  mov     cs:?g_pfnNtCompareTokens@@3P6AJPEAX0PEAE@ZEA, rax; long (*g_pfnNtCompareTokens)(void *,void *,uchar *)
0x38389414c  test    rax, rax
0x38389414f  jz      loc_3838BEA1C
0x383894155  mov     ecx, 1; HINSTANCE
0x38389415a  call    ?DllMain_Sni@@YAHPEAUHINSTANCE__@@KPEAX@Z; DllMain_Sni(HINSTANCE__ *,ulong,void *)
0x38389415f  mov     ebx, eax
0x383894161  cmp     [rsp+68h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383894167  jnz     loc_3838BEA1E
0x38389416d  mov     eax, ebx
0x38389416f  jmp     short $+2
0x383894171  mov     rbx, [rsp+68h+arg_8]
0x383894176  add     rsp, 60h
0x38389417a  pop     rdi
0x38389417b  retn
0x3838be813  mov     rax, cs:off_383B4A718; "<InitializeSharedModules|SNAC> "
0x3838be81a  test    rax, rax
0x3838be81d  jz      loc_38389401C
0x3838be823  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838be82b  jz      loc_38389401C
0x3838be831  mov     qword ptr [rsp+68h+wNumStrings], rdi
0x3838be836  mov     rax, cs:off_383B4A718; "<InitializeSharedModules|SNAC> "
0x3838be83d  mov     [rsp+68h+lpUserSid], rax
0x3838be842  lea     r9, [rsp+68h+arg_0]
0x3838be847  xor     r8d, r8d
0x3838be84a  xor     edx, edx
0x3838be84c  mov     rcx, cs:_bidID
0x3838be853  call    cs:off_383B15050
0x3838be859  nop
0x3838be85a  jmp     loc_38389401C
0x3838be85f  cmp     [rsp+68h+arg_0], 0FFFFFFFFFFFFFFFFh
0x3838be865  jz      short loc_3838BE88D
0x3838be867  test    byte ptr cs:_bidGblFlags, 4
0x3838be86e  jz      short loc_3838BE88D
0x3838be870  mov     rcx, cs:_bidID
0x3838be877  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838be87b  jz      short loc_3838BE88D
0x3838be87d  lea     r9, [rsp+68h+arg_0]
0x3838be882  xor     r8d, r8d
0x3838be885  xor     edx, edx
0x3838be887  call    cs:off_383B15058
0x3838be88d  mov     eax, 1
0x3838be892  jmp     loc_383894171
0x3838be897  cmp     cs:?g_fIsEmbeddedSNAC@@3_NA, dil; bool g_fIsEmbeddedSNAC
0x3838be89e  jnz     short loc_3838BE8EF
0x3838be8a0  lea     rdx, SourceName; "SQLNCLI11.1"
0x3838be8a7  xor     ecx, ecx; lpUNCServerName
0x3838be8a9  call    cs:__imp_RegisterEventSourceW
0x3838be8af  mov     rbx, rax
0x3838be8b2  test    rax, rax
0x3838be8b5  jz      short loc_3838BE8EF
0x3838be8b7  xor     r8d, r8d; wCategory
0x3838be8ba  lea     edx, [r8+1]; wType
0x3838be8be  mov     [rsp+68h+lpRawData], rdi; lpRawData
0x3838be8c3  mov     [rsp+68h+lpStrings], rdi; lpStrings
0x3838be8c8  mov     [rsp+68h+dwDataSize], edi; dwDataSize
0x3838be8cc  mov     [rsp+68h+wNumStrings], di; wNumStrings
0x3838be8d1  mov     [rsp+68h+lpUserSid], rdi; lpUserSid
0x3838be8d6  mov     r9d, 0C0000001h; dwEventID
0x3838be8dc  mov     rcx, rax; hEventLog
0x3838be8df  call    cs:__imp_ReportEventW
0x3838be8e5  mov     rcx, rbx; hEventLog
0x3838be8e8  call    cs:__imp_DeregisterEventSource
0x3838be8ee  nop
0x3838be8ef  jmp     loc_3838BEA52
0x3838be8f4  mov     rcx, cs:off_383B431B0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838be8fb  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838be902  test    rax, rax
0x3838be905  jz      loc_38389404C
0x3838be90b  mov     r9d, 171h
0x3838be911  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3838be918  mov     edx, 5C409h
0x3838be91d  call    _bidTraceW
0x3838be922  nop
0x3838be923  jmp     loc_38389404C
0x3838be928  jmp     short loc_3838BE94C
0x3838be92a  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rdi; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x3838be931  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rdi; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x3838be938  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hLibModule
0x3838be93f  call    cs:__imp_FreeLibrary
0x3838be945  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hCrypt
0x3838be94c  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x3838be953  call    cs:__imp_LoadLibraryW
0x3838be959  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x3838be960  test    rax, rax
0x3838be963  jz      loc_3838940EF
0x3838be969  lea     rdx, aSystemfunction; "SystemFunction040"
0x3838be970  mov     rcx, rax; hModule
0x3838be973  call    cs:__imp_GetProcAddress
0x3838be979  mov     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rax; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x3838be980  lea     rdx, aSystemfunction_0; "SystemFunction041"
0x3838be987  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x3838be98e  call    cs:__imp_GetProcAddress
0x3838be994  mov     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rax; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x3838be99b  lea     rdx, aLsantstatustow; "LsaNtStatusToWinError"
0x3838be9a2  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x3838be9a9  call    cs:__imp_GetProcAddress
0x3838be9af  mov     cs:?g_pfnLsaNtStatusToWinError@@3P6AJJ@ZEA, rax; long (*g_pfnLsaNtStatusToWinError)(long)
0x3838be9b6  cmp     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rdi; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x3838be9bd  jz      short loc_3838BE9EE
0x3838be9bf  cmp     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rdi; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x3838be9c6  jz      short loc_3838BE9EE
0x3838be9c8  test    rax, rax
0x3838be9cb  jz      short loc_3838BE9EE
0x3838be9cd  lea     rax, ?CryptProtectMemoryInternal@@YAHPEAXKK@Z; CryptProtectMemoryInternal(void *,ulong,ulong)
0x3838be9d4  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x3838be9db  lea     rax, ?CryptUnprotectMemoryInternal@@YAHPEAXKK@Z; CryptUnprotectMemoryInternal(void *,ulong,ulong)
0x3838be9e2  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x3838be9e9  jmp     loc_3838940EF
0x3838be9ee  mov     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rdi; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x3838be9f5  mov     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rdi; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x3838be9fc  mov     cs:?g_pfnLsaNtStatusToWinError@@3P6AJJ@ZEA, rdi; long (*g_pfnLsaNtStatusToWinError)(long)
0x3838bea03  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hLibModule
0x3838bea0a  call    cs:__imp_FreeLibrary
0x3838bea10  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hCrypt
0x3838bea17  jmp     loc_3838940EF
0x3838bea1c  jmp     short loc_3838BEA52
0x3838bea1e  test    byte ptr cs:_bidGblFlags, 4
0x3838bea25  jz      loc_38389416D
0x3838bea2b  mov     rcx, cs:_bidID
0x3838bea32  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838bea36  jz      loc_38389416D
0x3838bea3c  lea     r9, [rsp+68h+arg_0]
0x3838bea41  xor     r8d, r8d
0x3838bea44  xor     edx, edx
0x3838bea46  call    cs:off_383B15058
0x3838bea4c  nop
0x3838bea4d  jmp     loc_38389416D
0x3838bea52  cmp     [rsp+68h+arg_0], 0FFFFFFFFFFFFFFFFh
0x3838bea58  jz      short loc_3838BEA80
0x3838bea5a  test    byte ptr cs:_bidGblFlags, 4
0x3838bea61  jz      short loc_3838BEA80
0x3838bea63  mov     rcx, cs:_bidID
0x3838bea6a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838bea6e  jz      short loc_3838BEA80
0x3838bea70  lea     r9, [rsp+68h+arg_0]
0x3838bea75  xor     r8d, r8d
0x3838bea78  xor     edx, edx
0x3838bea7a  call    cs:off_383B15058
0x3838bea80  xor     eax, eax
0x3838bea82  jmp     loc_383894171
```
