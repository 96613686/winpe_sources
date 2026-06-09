# InitializeGlobals

- ea: `0x140039d80`
- end: `0x14003a0c4`
- name: `InitializeGlobals`
- size: `836`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14003a0cc`

## callees

- `0x140002bf0`
- `0x140038850`
- `0x140039d80`
- `0x14003b4cc`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `msvcrt!free` at `0x14003a045`
- `msvcrt!free` at `0x14003a052`
- `msvcrt!free` at `0x14003a045`
- `msvcrt!free` at `0x14003a052`
- `msvcrt!malloc` at `0x140039fcc`
- `msvcrt!malloc` at `0x140039fe1`
- `msvcrt!malloc` at `0x140039fcc`
- `msvcrt!malloc` at `0x140039fe1`
- `msvcrt!fprintf` at `0x140039f35`
- `msvcrt!fprintf` at `0x14003a038`
- `msvcrt!fprintf` at `0x14003a070`
- `msvcrt!fprintf` at `0x14003a097`
- `msvcrt!fprintf` at `0x140039f35`
- `msvcrt!fprintf` at `0x14003a038`
- `msvcrt!fprintf` at `0x14003a070`
- `msvcrt!fprintf` at `0x14003a097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a078`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140039df3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140039df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140039ef4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140039ef4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140039ed4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140039ed4`
- `imagehlp!SymSetOptions` at `0x140039f4c`
- `imagehlp!SymSetOptions` at `0x140039f4c`
- `imagehlp!SymRegisterCallback64` at `0x140039f77`
- `imagehlp!SymRegisterCallback64` at `0x140039f77`
- `dbghelp!SymInitializeW` at `0x140039f0c`
- `dbghelp!SymInitializeW` at `0x140039f0c`

## string_xrefs

- `0x140039ecd`: `_NT_SYMBOL_PATH`
- `0x14003a069`: `WPPFMT : error : out of memory from splitpath\n`
- `0x140039ee8`: `Symbol Path = [%ws]\n`

## pseudocode

```c
char InitializeGlobals()
{
  unsigned __int64 v0; // rcx
  WCHAR *v1; // r8
  WCHAR *v2; // rax
  WCHAR *v3; // rdx
  WCHAR *v4; // rax
  WCHAR *v5; // rcx
  unsigned __int64 v6; // rax
  DWORD v7; // ebx
  FILE *v8; // rax
  DWORD v9; // ebx
  FILE *v10; // rax
  void *v11; // rdi
  void *v12; // rax
  void *v13; // rbx
  FILE *v14; // rax
  FILE *v16; // rax
  DWORD LastError; // ebx
  FILE *v18; // rax
  WCHAR Filename[2]; // [rsp+20h] [rbp-228h] BYREF
  char v20; // [rsp+24h] [rbp-224h] BYREF

  gDefaultBaseForVirtualMods = 0x1000000;
  gBase = 0;
  gDefaultBase = 0x1000000;
  memset_0(lastguid, 0, 0x104u);
  memset_0(Filename, 0, 0x20Au);
  if ( !GetModuleFileNameW(0, Filename, 0x105u) || GetLastError() )
  {
    LastError = GetLastError();
    v18 = _acrt_iob_func(2u);
    fprintf(v18, "WPPFMT : error : 0x%x from GetModuleFileNameW()\n", LastError);
    return 0;
  }
  v0 = -1;
  do
    ++v0;
  while ( Filename[v0] );
  v1 = Filename;
  if ( v0 >= 2 )
  {
    v2 = (WCHAR *)&v20;
    if ( Filename[1] != 58 )
      v2 = Filename;
    v1 = v2;
  }
  v3 = &Filename[v0];
  v4 = v3;
  while ( v3 != v1 )
  {
    v5 = v3--;
    if ( *v3 == 46 )
    {
      v4 = v3;
      while ( v3 != v1 )
      {
        v5 = v3--;
        if ( *v3 == 47 || *v3 == 92 )
          goto LABEL_20;
      }
      break;
    }
    if ( *v3 == 47 || *v3 == 92 )
    {
LABEL_20:
      v3 = v5;
      break;
    }
  }
  v6 = v4 - v3;
  if ( !v6
    || !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)&g_CurrentModuleFileName,
          v3,
          v6) )
  {
    v16 = _acrt_iob_func(2u);
    fprintf(v16, "WPPFMT : error : out of memory from splitpath\n");
    return 0;
  }
  dprintf("dbg: initializing...\n");
  if ( !GetEnvironmentVariableW(L"_NT_SYMBOL_PATH", &gSymbolSearchPath, 0x400u) )
    gSymbolSearchPath = 0;
  dprintf("Symbol Path = [%ws]\n");
  gSymHandle = (HANDLE)(GetCurrentThreadId() + 1LL);
  if ( !SymInitializeW(gSymHandle, &gSymbolSearchPath, 0) )
  {
    v7 = GetLastError();
    v8 = _acrt_iob_func(2u);
    fprintf(v8, "WPPFMT : error : 0x%x from SymInitialize()\n", v7);
    gSymHandle = 0;
    return 0;
  }
  gOptions = SymSetOptions(0x10813u);
  dprintf("SymOpts = 0x%x\n");
  if ( !SymRegisterCallback64(gSymHandle, cbSymbol, 0) )
  {
    v9 = GetLastError();
    v10 = _acrt_iob_func(2u);
    fprintf(v10, "WPPFMT : error : 0x%x from SymRegisterCallback64()\n", v9);
    return 0;
  }
  NextFreeEnum = 0;
  EnumCount = 64;
  GuidCount = 64;
  NextFreeGuid = 0;
  PostProcessEnums = 0;
  *(_QWORD *)&GuidHead.Data1 = malloc(0xE00u);
  v11 = *(void **)&GuidHead.Data1;
  v12 = malloc(0x600u);
  EnumHead = v12;
  v13 = v12;
  if ( v11 && v12 )
  {
    memset_0(v11, 0, 0xE00u);
    memset_0(v13, 0, 0x600u);
    PostProcessEnums = 1;
  }
  else
  {
    v14 = _acrt_iob_func(2u);
    fprintf(v14, "WPPFMT : warning : enums will not be proccessed (failed allocation of structures)\n");
    free(*(void **)&GuidHead.Data1);
    free(EnumHead);
  }
  return 1;
}

```

## disassembly

```asm
0x140039d80  mov     [rsp+arg_0], rbx
0x140039d85  mov     [rsp+arg_8], rsi
0x140039d8a  push    rdi
0x140039d8b  sub     rsp, 240h
0x140039d92  mov     rax, cs:__security_cookie
0x140039d99  xor     rax, rsp
0x140039d9c  mov     [rsp+248h+var_18], rax
0x140039da4  mov     eax, 1000000h
0x140039da9  lea     rcx, ?lastguid@@3PADA; void *
0x140039db0  xor     esi, esi
0x140039db2  mov     cs:?gDefaultBaseForVirtualMods@@3_KA, rax; unsigned __int64 gDefaultBaseForVirtualMods
0x140039db9  xor     edx, edx; Val
0x140039dbb  mov     cs:?gBase@@3_KA, rsi; unsigned __int64 gBase
0x140039dc2  mov     r8d, 104h; Size
0x140039dc8  mov     cs:?gDefaultBase@@3_KA, rax; unsigned __int64 gDefaultBase
0x140039dcf  call    memset_0
0x140039dd4  xor     edx, edx; Val
0x140039dd6  lea     rcx, [rsp+248h+Filename]; void *
0x140039ddb  mov     r8d, 20Ah; Size
0x140039de1  call    memset_0
0x140039de6  mov     r8d, 105h; nSize
0x140039dec  lea     rdx, [rsp+248h+Filename]; lpFilename
0x140039df1  xor     ecx, ecx; hModule
0x140039df3  call    cs:__imp_GetModuleFileNameW
0x140039df9  test    eax, eax
0x140039dfb  jz      loc_14003A078
0x140039e01  call    cs:__imp_GetLastError
0x140039e07  test    eax, eax
0x140039e09  jnz     loc_14003A078
0x140039e0f  lea     rax, [rsp+248h+Filename]
0x140039e14  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140039e18  inc     rcx
0x140039e1b  cmp     [rax+rcx*2], si
0x140039e1f  jnz     short loc_140039E18
0x140039e21  lea     r8, [rsp+248h+Filename]
0x140039e26  cmp     rcx, 2
0x140039e2a  jb      short loc_140039E3E
0x140039e2c  cmp     [rsp+248h+var_226], 3Ah ; ':'
0x140039e32  lea     rax, [rsp+248h+var_224]
0x140039e37  cmovnz  rax, r8
0x140039e3b  mov     r8, rax
0x140039e3e  lea     rdx, [rsp+248h+Filename]
0x140039e43  lea     rdx, [rdx+rcx*2]
0x140039e47  mov     rax, rdx
0x140039e4a  jmp     short loc_140039E65
0x140039e4c  mov     rcx, rdx
0x140039e4f  sub     rdx, 2
0x140039e53  cmp     word ptr [rdx], 2Eh ; '.'
0x140039e57  jz      short loc_140039E6C
0x140039e59  cmp     word ptr [rdx], 2Fh ; '/'
0x140039e5d  jz      short loc_140039E8B
0x140039e5f  cmp     word ptr [rdx], 5Ch ; '\'
0x140039e63  jz      short loc_140039E8B
0x140039e65  cmp     rdx, r8
0x140039e68  jnz     short loc_140039E4C
0x140039e6a  jmp     short loc_140039E8E
0x140039e6c  mov     rax, rdx
0x140039e6f  jmp     short loc_140039E84
0x140039e71  mov     rcx, rdx
0x140039e74  sub     rdx, 2
0x140039e78  cmp     word ptr [rdx], 2Fh ; '/'
0x140039e7c  jz      short loc_140039E8B
0x140039e7e  cmp     word ptr [rdx], 5Ch ; '\'
0x140039e82  jz      short loc_140039E8B
0x140039e84  cmp     rdx, r8
0x140039e87  jnz     short loc_140039E71
0x140039e89  jmp     short loc_140039E8E
0x140039e8b  mov     rdx, rcx
0x140039e8e  sub     rax, rdx
0x140039e91  sar     rax, 1
0x140039e94  jz      loc_14003A05C
0x140039e9a  mov     r8, rax
0x140039e9d  lea     rcx, ?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x140039ea4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140039ea9  test    al, al
0x140039eab  jz      loc_14003A05C
0x140039eb1  lea     rcx, aDbgInitializin; "dbg: initializing...\n"
0x140039eb8  call    dprintf
0x140039ebd  lea     rbx, ?gSymbolSearchPath@@3PAGA; ushort near * gSymbolSearchPath
0x140039ec4  mov     r8d, 400h; nSize
0x140039eca  mov     rdx, rbx; lpBuffer
0x140039ecd  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x140039ed4  call    cs:__imp_GetEnvironmentVariableW
0x140039eda  test    eax, eax
0x140039edc  jnz     short loc_140039EE5
0x140039ede  mov     cs:?gSymbolSearchPath@@3PAGA, si; ushort near * gSymbolSearchPath
0x140039ee5  mov     rdx, rbx
0x140039ee8  lea     rcx, aSymbolPathWs; "Symbol Path = [%ws]\n"
0x140039eef  call    dprintf
0x140039ef4  call    cs:__imp_GetCurrentThreadId
0x140039efa  mov     ecx, eax
0x140039efc  xor     r8d, r8d; fInvadeProcess
0x140039eff  inc     rcx; hProcess
0x140039f02  mov     rdx, rbx; UserSearchPath
0x140039f05  mov     cs:?gSymHandle@@3PEAXEA, rcx; void * gSymHandle
0x140039f0c  call    cs:__imp_SymInitializeW
0x140039f12  test    eax, eax
0x140039f14  jnz     short loc_140039F47
0x140039f16  call    cs:__imp_GetLastError
0x140039f1c  mov     ecx, 2; Ix
0x140039f21  mov     ebx, eax
0x140039f23  call    __acrt_iob_func
0x140039f28  mov     r8d, ebx
0x140039f2b  lea     rdx, aWppfmtError0xX_1; "WPPFMT : error : 0x%x from SymInitializ"...
0x140039f32  mov     rcx, rax; Stream
0x140039f35  call    cs:__imp_fprintf
0x140039f3b  mov     cs:?gSymHandle@@3PEAXEA, rsi; void * gSymHandle
0x140039f42  jmp     loc_14003A09D
0x140039f47  mov     ecx, 10813h; SymOptions
0x140039f4c  call    cs:__imp_SymSetOptions
0x140039f52  mov     edx, eax
0x140039f54  mov     cs:?gOptions@@3KA, eax; ulong gOptions
0x140039f5a  lea     rcx, aSymopts0xX; "SymOpts = 0x%x\n"
0x140039f61  call    dprintf
0x140039f66  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x140039f6d  lea     rdx, cbSymbol; CallbackFunction
0x140039f74  xor     r8d, r8d; UserContext
0x140039f77  call    cs:__imp_SymRegisterCallback64
0x140039f7d  test    eax, eax
0x140039f7f  jnz     short loc_140039F9F
0x140039f81  call    cs:__imp_GetLastError
0x140039f87  mov     ecx, 2; Ix
0x140039f8c  mov     ebx, eax
0x140039f8e  call    __acrt_iob_func
0x140039f93  lea     rdx, aWppfmtError0xX_0; "WPPFMT : error : 0x%x from SymRegisterC"...
0x140039f9a  jmp     loc_14003A091
0x140039f9f  mov     eax, 40h ; '@'
0x140039fa4  mov     cs:?NextFreeEnum@@3GA, si; ushort NextFreeEnum
0x140039fab  mov     ecx, 0E00h; Size
0x140039fb0  mov     cs:?EnumCount@@3GA, ax; ushort EnumCount
0x140039fb7  mov     cs:?GuidCount@@3GA, ax; ushort GuidCount
0x140039fbe  mov     cs:?NextFreeGuid@@3GA, si; ushort NextFreeGuid
0x140039fc5  mov     cs:?PostProcessEnums@@3_NA, sil; bool PostProcessEnums
0x140039fcc  call    cs:__imp_malloc
0x140039fd2  mov     ecx, 600h; Size
0x140039fd7  mov     qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1, rax; GUID_POST_PROCESS_DATA * GuidHead ...
0x140039fde  mov     rdi, rax
0x140039fe1  call    cs:__imp_malloc
0x140039fe7  mov     cs:?EnumHead@@3PEAUENUMDATA@@EA, rax; ENUMDATA * EnumHead
0x140039fee  mov     rbx, rax
0x140039ff1  test    rdi, rdi
0x140039ff4  jz      short loc_14003A024
0x140039ff6  test    rax, rax
0x140039ff9  jz      short loc_14003A024
0x140039ffb  xor     edx, edx; Val
0x140039ffd  mov     r8d, 0E00h; Size
0x14003a003  mov     rcx, rdi; void *
0x14003a006  call    memset_0
0x14003a00b  xor     edx, edx; Val
0x14003a00d  mov     r8d, 600h; Size
0x14003a013  mov     rcx, rbx; void *
0x14003a016  call    memset_0
0x14003a01b  mov     cs:?PostProcessEnums@@3_NA, 1; bool PostProcessEnums
0x14003a022  jmp     short loc_14003A058
0x14003a024  mov     ecx, 2; Ix
0x14003a029  call    __acrt_iob_func
0x14003a02e  mov     rcx, rax; Stream
0x14003a031  lea     rdx, aWppfmtWarningE; "WPPFMT : warning : enums will not be pr"...
0x14003a038  call    cs:__imp_fprintf
0x14003a03e  mov     rcx, qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1; Block
0x14003a045  call    cs:__imp_free
0x14003a04b  mov     rcx, cs:?EnumHead@@3PEAUENUMDATA@@EA; Block
0x14003a052  call    cs:__imp_free
0x14003a058  mov     al, 1
0x14003a05a  jmp     short loc_14003A09F
0x14003a05c  mov     ecx, 2; Ix
0x14003a061  call    __acrt_iob_func
0x14003a066  mov     rcx, rax; Stream
0x14003a069  lea     rdx, aWppfmtErrorOut_1; "WPPFMT : error : out of memory from spl"...
0x14003a070  call    cs:__imp_fprintf
0x14003a076  jmp     short loc_14003A09D
0x14003a078  call    cs:__imp_GetLastError
0x14003a07e  mov     ecx, 2; Ix
0x14003a083  mov     ebx, eax
0x14003a085  call    __acrt_iob_func
0x14003a08a  lea     rdx, aWppfmtError0xX; "WPPFMT : error : 0x%x from GetModuleFil"...
0x14003a091  mov     r8d, ebx
0x14003a094  mov     rcx, rax; Stream
0x14003a097  call    cs:__imp_fprintf
0x14003a09d  xor     al, al
0x14003a09f  mov     rcx, [rsp+248h+var_18]
0x14003a0a7  xor     rcx, rsp; StackCookie
0x14003a0aa  call    __security_check_cookie
0x14003a0af  lea     r11, [rsp+248h+var_8]
0x14003a0b7  mov     rbx, [r11+10h]
0x14003a0bb  mov     rsi, [r11+18h]
0x14003a0bf  mov     rsp, r11
0x14003a0c2  pop     rdi
0x14003a0c3  retn
```
