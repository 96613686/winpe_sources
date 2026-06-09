# InitializeGlobals

- ea: `0x180048360`
- end: `0x18004864a`
- name: `InitializeGlobals`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180048650`

## callees

- `0x1800207c0`
- `0x1800212ea`
- `0x180021490`
- `0x180021724`
- `0x180042240`
- `0x180048360`
- `0x180048f18`
- `0x180049998`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800485cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800485da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800485cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800485da`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180048555`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004856a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180048555`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004856a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004850a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004850a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800483d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800483d3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18004845e`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18004845e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004847e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004847e`
- `dbghelp!SymInitializeW` at `0x180048496`
- `dbghelp!SymInitializeW` at `0x180048496`
- `dbghelp!SymSetOptions` at `0x1800484d5`
- `dbghelp!SymSetOptions` at `0x1800484d5`
- `dbghelp!SymRegisterCallback64` at `0x180048500`
- `dbghelp!SymRegisterCallback64` at `0x180048500`

## string_xrefs

- `0x1800485f1`: `WPPFMT : error : out of memory from splitpath\n`
- `0x180048457`: `_NT_SYMBOL_PATH`
- `0x180048472`: `Symbol Path = [%ws]\n`

## pseudocode

```c
char InitializeGlobals()
{
  __int64 v0; // r8
  DWORD v1; // ebx
  FILE *v2; // rax
  DWORD v3; // ebx
  FILE *v4; // rax
  void *v5; // rdi
  void *v6; // rax
  void *v7; // rbx
  FILE *v8; // rax
  FILE *v10; // rax
  DWORD LastError; // ebx
  FILE *v12; // rax
  _BYTE v13[16]; // [rsp+20h] [rbp-258h] BYREF
  __int64 v14; // [rsp+30h] [rbp-248h]
  __int64 v15; // [rsp+38h] [rbp-240h]
  WCHAR Filename[264]; // [rsp+50h] [rbp-228h] BYREF

  gDefaultBaseForVirtualMods = 0x1000000;
  gBase = 0;
  gDefaultBase = 0x1000000;
  memset_0(lastguid, 0, 0x104u);
  memset_0(Filename, 0, 0x20Au);
  if ( !GetModuleFileNameW(0, Filename, 0x105u) || GetLastError() )
  {
    LastError = GetLastError();
    v12 = o___acrt_iob_func_0(2u);
    fprintf(v12, "WPPFMT : error : 0x%x from GetModuleFileNameW()\n", LastError);
    return 0;
  }
  v0 = -1;
  do
    ++v0;
  while ( Filename[v0] );
  tlx::split_path<unsigned short>::_Init(v13, Filename);
  if ( !((v15 - v14) >> 1)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &g_CurrentModuleFileName,
                           v14,
                           (v15 - v14) >> 1) )
  {
    v10 = o___acrt_iob_func_0(2u);
    fprintf(v10, "WPPFMT : error : out of memory from splitpath\n");
    return 0;
  }
  dprintf("dbg: initializing...\n");
  if ( !GetEnvironmentVariableW(L"_NT_SYMBOL_PATH", &gSymbolSearchPath, 0x400u) )
    gSymbolSearchPath = 0;
  dprintf("Symbol Path = [%ws]\n");
  gSymHandle = (HANDLE)(GetCurrentThreadId() + 1LL);
  if ( !SymInitializeW(gSymHandle, &gSymbolSearchPath, 0) )
  {
    v1 = GetLastError();
    v2 = o___acrt_iob_func_0(2u);
    fprintf(v2, "WPPFMT : error : 0x%x from SymInitialize()\n", v1);
    gSymHandle = 0;
    return 0;
  }
  gOptions = SymSetOptions(0x10813u);
  dprintf("SymOpts = 0x%x\n");
  if ( !SymRegisterCallback64(gSymHandle, cbSymbol, 0) )
  {
    v3 = GetLastError();
    v4 = o___acrt_iob_func_0(2u);
    fprintf(v4, "WPPFMT : error : 0x%x from SymRegisterCallback64()\n", v3);
    return 0;
  }
  NextFreeEnum = 0;
  EnumCount = 64;
  GuidCount = 64;
  NextFreeGuid = 0;
  PostProcessEnums = 0;
  *(_QWORD *)&GuidHead.Data1 = malloc(0xE00u);
  v5 = *(void **)&GuidHead.Data1;
  v6 = malloc(0x600u);
  EnumHead = v6;
  v7 = v6;
  if ( v5 && v6 )
  {
    memset_0(v5, 0, 0xE00u);
    memset_0(v7, 0, 0x600u);
    PostProcessEnums = 1;
  }
  else
  {
    v8 = o___acrt_iob_func_0(2u);
    fprintf(v8, "WPPFMT : warning : enums will not be proccessed (failed allocation of structures)\n");
    free(*(void **)&GuidHead.Data1);
    free(EnumHead);
  }
  return 1;
}

```

## disassembly

```asm
0x180048360  mov     [rsp+arg_0], rbx
0x180048365  mov     [rsp+arg_8], rsi
0x18004836a  push    rdi
0x18004836b  sub     rsp, 270h
0x180048372  mov     rax, cs:__security_cookie
0x180048379  xor     rax, rsp
0x18004837c  mov     [rsp+278h+var_18], rax
0x180048384  mov     eax, 1000000h
0x180048389  lea     rcx, ?lastguid@@3PADA; void *
0x180048390  xor     esi, esi
0x180048392  mov     cs:?gDefaultBaseForVirtualMods@@3_KA, rax; unsigned __int64 gDefaultBaseForVirtualMods
0x180048399  xor     edx, edx; Val
0x18004839b  mov     cs:?gBase@@3_KA, rsi; unsigned __int64 gBase
0x1800483a2  mov     r8d, 104h; Size
0x1800483a8  mov     cs:?gDefaultBase@@3_KA, rax; unsigned __int64 gDefaultBase
0x1800483af  call    memset_0
0x1800483b4  xor     edx, edx; Val
0x1800483b6  lea     rcx, [rsp+278h+Filename]; void *
0x1800483bb  mov     r8d, 20Ah; Size
0x1800483c1  call    memset_0
0x1800483c6  mov     r8d, 105h; nSize
0x1800483cc  lea     rdx, [rsp+278h+Filename]; lpFilename
0x1800483d1  xor     ecx, ecx; hModule
0x1800483d3  call    cs:__imp_GetModuleFileNameW
0x1800483d9  test    eax, eax
0x1800483db  jz      loc_1800485FF
0x1800483e1  call    cs:__imp_GetLastError
0x1800483e7  test    eax, eax
0x1800483e9  jnz     loc_1800485FF
0x1800483ef  lea     rax, [rsp+278h+Filename]
0x1800483f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800483f8  inc     r8
0x1800483fb  cmp     [rax+r8*2], si
0x180048400  jnz     short loc_1800483F8
0x180048402  lea     rdx, [rsp+278h+Filename]
0x180048407  lea     rcx, [rsp+278h+var_258]
0x18004840c  call    ?_Init@?$split_path@G@tlx@@AEAAXPEBG_K@Z; tlx::split_path<ushort>::_Init(ushort const *,unsigned __int64)
0x180048411  mov     rdx, [rsp+278h+var_248]
0x180048416  mov     r8, [rsp+278h+var_240]
0x18004841b  sub     r8, rdx
0x18004841e  sar     r8, 1
0x180048421  jz      loc_1800485E4
0x180048427  lea     rcx, ?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x18004842e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180048433  test    al, al
0x180048435  jz      loc_1800485E4
0x18004843b  lea     rcx, aDbgInitializin; "dbg: initializing...\n"
0x180048442  call    dprintf
0x180048447  lea     rbx, ?gSymbolSearchPath@@3PAGA; ushort near * gSymbolSearchPath
0x18004844e  mov     r8d, 400h; nSize
0x180048454  mov     rdx, rbx; lpBuffer
0x180048457  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18004845e  call    cs:__imp_GetEnvironmentVariableW
0x180048464  test    eax, eax
0x180048466  jnz     short loc_18004846F
0x180048468  mov     cs:?gSymbolSearchPath@@3PAGA, si; ushort near * gSymbolSearchPath
0x18004846f  mov     rdx, rbx
0x180048472  lea     rcx, aSymbolPathWs; "Symbol Path = [%ws]\n"
0x180048479  call    dprintf
0x18004847e  call    cs:__imp_GetCurrentThreadId
0x180048484  mov     ecx, eax
0x180048486  xor     r8d, r8d; fInvadeProcess
0x180048489  inc     rcx; hProcess
0x18004848c  mov     rdx, rbx; UserSearchPath
0x18004848f  mov     cs:?gSymHandle@@3PEAXEA, rcx; void * gSymHandle
0x180048496  call    cs:__imp_SymInitializeW
0x18004849c  test    eax, eax
0x18004849e  jnz     short loc_1800484D0
0x1800484a0  call    cs:__imp_GetLastError
0x1800484a6  mov     ecx, 2; Ix
0x1800484ab  mov     ebx, eax
0x1800484ad  call    _o___acrt_iob_func_0
0x1800484b2  mov     r8d, ebx
0x1800484b5  lea     rdx, aWppfmtError0xX_1; "WPPFMT : error : 0x%x from SymInitializ"...
0x1800484bc  mov     rcx, rax; Stream
0x1800484bf  call    fprintf
0x1800484c4  mov     cs:?gSymHandle@@3PEAXEA, rsi; void * gSymHandle
0x1800484cb  jmp     loc_180048623
0x1800484d0  mov     ecx, 10813h; SymOptions
0x1800484d5  call    cs:__imp_SymSetOptions
0x1800484db  mov     edx, eax
0x1800484dd  mov     cs:?gOptions@@3KA, eax; ulong gOptions
0x1800484e3  lea     rcx, aSymopts0xX; "SymOpts = 0x%x\n"
0x1800484ea  call    dprintf
0x1800484ef  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x1800484f6  lea     rdx, cbSymbol; CallbackFunction
0x1800484fd  xor     r8d, r8d; UserContext
0x180048500  call    cs:__imp_SymRegisterCallback64
0x180048506  test    eax, eax
0x180048508  jnz     short loc_180048528
0x18004850a  call    cs:__imp_GetLastError
0x180048510  mov     ecx, 2; Ix
0x180048515  mov     ebx, eax
0x180048517  call    _o___acrt_iob_func_0
0x18004851c  lea     rdx, aWppfmtError0xX_0; "WPPFMT : error : 0x%x from SymRegisterC"...
0x180048523  jmp     loc_180048618
0x180048528  mov     eax, 40h ; '@'
0x18004852d  mov     cs:?NextFreeEnum@@3GA, si; ushort NextFreeEnum
0x180048534  mov     ecx, 0E00h; Size
0x180048539  mov     cs:?EnumCount@@3GA, ax; ushort EnumCount
0x180048540  mov     cs:?GuidCount@@3GA, ax; ushort GuidCount
0x180048547  mov     cs:?NextFreeGuid@@3GA, si; ushort NextFreeGuid
0x18004854e  mov     cs:?PostProcessEnums@@3_NA, sil; bool PostProcessEnums
0x180048555  call    cs:__imp_malloc
0x18004855b  mov     ecx, 600h; Size
0x180048560  mov     qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1, rax; GUID_POST_PROCESS_DATA * GuidHead ...
0x180048567  mov     rdi, rax
0x18004856a  call    cs:__imp_malloc
0x180048570  mov     cs:?EnumHead@@3PEAUENUMDATA@@EA, rax; ENUMDATA * EnumHead
0x180048577  mov     rbx, rax
0x18004857a  test    rdi, rdi
0x18004857d  jz      short loc_1800485AD
0x18004857f  test    rax, rax
0x180048582  jz      short loc_1800485AD
0x180048584  xor     edx, edx; Val
0x180048586  mov     r8d, 0E00h; Size
0x18004858c  mov     rcx, rdi; void *
0x18004858f  call    memset_0
0x180048594  xor     edx, edx; Val
0x180048596  mov     r8d, 600h; Size
0x18004859c  mov     rcx, rbx; void *
0x18004859f  call    memset_0
0x1800485a4  mov     cs:?PostProcessEnums@@3_NA, 1; bool PostProcessEnums
0x1800485ab  jmp     short loc_1800485E0
0x1800485ad  mov     ecx, 2; Ix
0x1800485b2  call    _o___acrt_iob_func_0
0x1800485b7  mov     rcx, rax; Stream
0x1800485ba  lea     rdx, aWppfmtWarningE; "WPPFMT : warning : enums will not be pr"...
0x1800485c1  call    fprintf
0x1800485c6  mov     rcx, qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1; Block
0x1800485cd  call    cs:__imp_free
0x1800485d3  mov     rcx, cs:?EnumHead@@3PEAUENUMDATA@@EA; Block
0x1800485da  call    cs:__imp_free
0x1800485e0  mov     al, 1
0x1800485e2  jmp     short loc_180048625
0x1800485e4  mov     ecx, 2; Ix
0x1800485e9  call    _o___acrt_iob_func_0
0x1800485ee  mov     rcx, rax; Stream
0x1800485f1  lea     rdx, aWppfmtErrorOut_1; "WPPFMT : error : out of memory from spl"...
0x1800485f8  call    fprintf
0x1800485fd  jmp     short loc_180048623
0x1800485ff  call    cs:__imp_GetLastError
0x180048605  mov     ecx, 2; Ix
0x18004860a  mov     ebx, eax
0x18004860c  call    _o___acrt_iob_func_0
0x180048611  lea     rdx, aWppfmtError0xX; "WPPFMT : error : 0x%x from GetModuleFil"...
0x180048618  mov     r8d, ebx
0x18004861b  mov     rcx, rax; Stream
0x18004861e  call    fprintf
0x180048623  xor     al, al
0x180048625  mov     rcx, [rsp+278h+var_18]
0x18004862d  xor     rcx, rsp; StackCookie
0x180048630  call    __security_check_cookie
0x180048635  lea     r11, [rsp+278h+var_8]
0x18004863d  mov     rbx, [r11+10h]
0x180048641  mov     rsi, [r11+18h]
0x180048645  mov     rsp, r11
0x180048648  pop     rdi
0x180048649  retn
```
