# _SxsDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18005244c`
- end: `0x1800525d2`
- name: `?_SxsDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `390`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180052400`

## callees

- `0x1800011bc`
- `0x18000c000`
- `0x180052400`
- `0x18005244c`
- `0x1800525d8`
- `0x180058720`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005258d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005258d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005251e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005251e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180052479`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180052479`

## string_xrefs

- `0x1800524f4`: `SXS: %s - %ls(DLL_PROCESS_ATTACH) failed. Last WinError 0x%08x (%d).\n`
- `0x1800524e5`: `_SxsDllMain`
- `0x1800525a1`: `_SxsDllMain`
- `0x1800525ac`: `SXS: %s - %ls(DLL_PROCESS_DETACH) failed. Last WinError 0x%08x (%d).\n`

## pseudocode

```c
__int64 __fastcall _SxsDllMain(HINSTANCE hinstDLL, int a2, void *a3)
{
  __int64 i; // rdi
  unsigned int v6; // r14d
  DWORD LastError; // eax
  const wchar_t *v8; // r9
  DWORD v9; // ebx
  __int64 v11; // rbx
  char v12; // al
  DWORD v13; // eax

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      g_hInstance = hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation();
      for ( i = 0; i != 5; ++i )
      {
        if ( !(unsigned int)(*(&funcs_1800524B8 + 2 * i))(hinstDLL, 1u, a3) )
        {
          v6 = 0;
          LastError = GetLastError();
          v8 = (&off_180074228)[2 * i];
          *((_BYTE *)&g_SxspDllMainStartupStatus + i) |= 1u;
          v9 = LastError;
          FusionpDbgPrintEx(
            0xC0000000,
            "SXS: %s - %ls(DLL_PROCESS_ATTACH) failed. Last WinError 0x%08x (%d).\n",
            "_SxsDllMain",
            v8,
            LastError,
            LastError);
          SxsDllMain(hinstDLL, 0, a3);
          SetLastError(v9);
          return v6;
        }
        *((_BYTE *)&g_SxspDllMainStartupStatus + i) |= 1u;
      }
    }
  }
  else
  {
    if ( a3 )
      return 1;
    TraceLoggingUnregister_EventUnregister();
    v11 = 5;
    do
    {
      v12 = *((_BYTE *)&g_AlternateAssemblyStoreRoot + v11 + 7);
      if ( (v12 & 1) != 0 )
      {
        *((_BYTE *)&g_AlternateAssemblyStoreRoot + v11 + 7) = v12 & 0xFE;
        if ( !((unsigned int (__fastcall *)(HINSTANCE, _QWORD, _QWORD))qword_180074210[2 * v11])(hinstDLL, 0, 0) )
        {
          v13 = GetLastError();
          FusionpDbgPrintEx(
            0xC0000000,
            "SXS: %s - %ls(DLL_PROCESS_DETACH) failed. Last WinError 0x%08x (%d).\n",
            "_SxsDllMain",
            (const wchar_t *)qword_180074218[2 * v11],
            v13,
            v13);
        }
      }
      --v11;
    }
    while ( v11 );
  }
  return 1;
}

```

## disassembly

```asm
0x18005244c  push    rbx
0x18005244e  push    rbp
0x18005244f  push    rsi
0x180052450  push    rdi
0x180052451  push    r12
0x180052453  push    r14
0x180052455  push    r15
0x180052457  sub     rsp, 30h
0x18005245b  mov     r15, r8
0x18005245e  mov     rbp, rcx
0x180052461  test    edx, edx
0x180052463  jz      loc_18005253D
0x180052469  cmp     edx, 1
0x18005246c  jnz     loc_1800525C7
0x180052472  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x180052479  call    cs:__imp_DisableThreadLibraryCalls
0x180052480  nop     dword ptr [rax+rax+00h]
0x180052485  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18005248a  xor     edi, edi
0x18005248c  lea     rsi, __ImageBase
0x180052493  lea     ebx, [rdi+5]
0x180052496  cmp     rdi, rbx
0x180052499  jz      loc_1800525C7
0x18005249f  mov     r12, rdi
0x1800524a2  mov     r8, r15; void *
0x1800524a5  add     r12, r12
0x1800524a8  mov     edx, 1; unsigned int
0x1800524ad  mov     rcx, rbp; HINSTANCE
0x1800524b0  mov     rax, ds:(funcs_1800524B8 - 180000000h)[rsi+r12*8]
0x1800524b8  call    _guard_dispatch_icall$thunk$10345483385596137414; DllStartup_HeapSetup(HINSTANCE__ *,ulong,void *) ...
0x1800524bd  test    eax, eax
0x1800524bf  jz      short loc_1800524CE
0x1800524c1  or      byte ptr [rdi+rsi+98968h], 1
0x1800524c9  inc     rdi
0x1800524cc  jmp     short loc_180052496
0x1800524ce  xor     r14d, r14d
0x1800524d1  call    cs:__imp_GetLastError
0x1800524d8  nop     dword ptr [rax+rax+00h]
0x1800524dd  mov     r9, ds:rva off_180074228[rsi+r12*8]; "DllStartup_HeapSetup" ...
0x1800524e5  lea     r8, aSxsdllmain; "_SxsDllMain"
0x1800524ec  or      byte ptr [rdi+rsi+98968h], 1
0x1800524f4  lea     rdx, aSxsSLsDllProce; "SXS: %s - %ls(DLL_PROCESS_ATTACH) faile"...
0x1800524fb  mov     [rsp+68h+var_40], eax
0x1800524ff  mov     ecx, 0C0000000h; unsigned int
0x180052504  mov     [rsp+68h+var_48], eax
0x180052508  mov     ebx, eax
0x18005250a  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18005250f  mov     r8, r15; lpReserved
0x180052512  xor     edx, edx; fdwReason
0x180052514  mov     rcx, rbp; hinstDLL
0x180052517  call    SxsDllMain
0x18005251c  mov     ecx, ebx; dwErrCode
0x18005251e  call    cs:__imp_SetLastError
0x180052525  nop     dword ptr [rax+rax+00h]
0x18005252a  mov     eax, r14d
0x18005252d  add     rsp, 30h
0x180052531  pop     r15
0x180052533  pop     r14
0x180052535  pop     r12
0x180052537  pop     rdi
0x180052538  pop     rsi
0x180052539  pop     rbp
0x18005253a  pop     rbx
0x18005253b  retn
0x18005253d  test    r15, r15
0x180052540  jz      short loc_180052549
0x180052542  mov     eax, 1
0x180052547  jmp     short loc_18005252D
0x180052549  call    TraceLoggingUnregister_EventUnregister
0x18005254e  mov     ebx, 5
0x180052553  lea     rsi, __ImageBase
0x18005255a  mov     al, [rbx+rsi+98967h]
0x180052561  test    al, 1
0x180052563  jz      short loc_1800525C1
0x180052565  and     al, 0FEh
0x180052567  mov     rdi, rbx
0x18005256a  mov     [rbx+rsi+98967h], al
0x180052571  add     rdi, rdi
0x180052574  mov     r8, r15
0x180052577  xor     edx, edx
0x180052579  mov     rcx, rbp
0x18005257c  mov     rax, ds:rva qword_180074210[rsi+rdi*8]
0x180052584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052589  test    eax, eax
0x18005258b  jnz     short loc_1800525C1
0x18005258d  call    cs:__imp_GetLastError
0x180052594  nop     dword ptr [rax+rax+00h]
0x180052599  mov     r9, ds:rva qword_180074218[rsi+rdi*8]
0x1800525a1  lea     r8, aSxsdllmain; "_SxsDllMain"
0x1800525a8  mov     [rsp+68h+var_40], eax
0x1800525ac  lea     rdx, aSxsSLsDllProce_0; "SXS: %s - %ls(DLL_PROCESS_DETACH) faile"...
0x1800525b3  mov     ecx, 0C0000000h; unsigned int
0x1800525b8  mov     [rsp+68h+var_48], eax
0x1800525bc  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800525c1  sub     rbx, 1
0x1800525c5  jnz     short loc_18005255A
0x1800525c7  mov     r14d, 1
0x1800525cd  jmp     loc_18005252A
```
