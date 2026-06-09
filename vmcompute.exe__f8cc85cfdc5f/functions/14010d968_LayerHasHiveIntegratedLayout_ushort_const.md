# LayerHasHiveIntegratedLayout(ushort const *)

- ea: `0x14010d968`
- end: `0x14010db5e`
- name: `?LayerHasHiveIntegratedLayout@@YA_NPEBG@Z`
- size: `502`
- prototype: `bool __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14010d8ec`

## callees

- `0x140017040`
- `0x140024030`
- `0x140057aec`
- `0x140080180`
- `0x1400aaf6c`
- `0x1400c4154`
- `0x1400fcfe4`
- `0x14010d968`
- `0x1401332f0`
- `0x1401365c5`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14010d9fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14010d9fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14010d9d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14010d9d8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14010da62`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14010da62`

## string_xrefs

- `0x14010da0e`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x14010da79`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x14010db14`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall LayerHasHiveIntegratedLayout(PCWSTR pszPathIn)
{
  const WCHAR *v1; // rcx
  HANDLE FileW; // rax
  const char *v3; // r9
  const char *v5; // r9
  void **v6; // rdx
  size_t v7; // r8
  void **v8; // rcx
  bool v9; // bl
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HANDLE v11; // [rsp+40h] [rbp-C0h] BYREF
  void *Buf1[2]; // [rsp+48h] [rbp-B8h] BYREF
  size_t Size[2]; // [rsp+58h] [rbp-A8h]
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buffer[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  CommonUtilities::CombineFilePath((PWSTR)lpFileName, pszPathIn, L"layout");
  v1 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v1 = lpFileName[0];
  FileW = CreateFileW(v1, 0x80000000, 1u, 0, 3u, 0, 0);
  v11 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, Buffer, 0x100u, &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v5);
    *(_OWORD *)Buf1 = 0;
    *(_OWORD *)Size = 0;
    std::string::_Construct<1,char const *>(Buf1, Buffer, NumberOfBytesRead);
    v6 = &Buf2;
    if ( *((_QWORD *)&xmmword_1403DCED8 + 1) > 0xFu )
      v6 = (void **)Buf2;
    v7 = Size[0];
    v8 = Buf1;
    if ( Size[1] > 0xF )
      v8 = (void **)Buf1[0];
    v9 = Size[0] != (_QWORD)xmmword_1403DCED8 || Size[0] && memcmp_0(v8, v6, Size[0]);
    std::string::~string(Buf1, v6, v7);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)0xC0370112LL,
        dwCreationDisposition);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
    return 1;
  }
  else
  {
    if ( GetLastError() != 2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v3);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
    return 0;
  }
}

```

## disassembly

```asm
0x14010d968  mov     [rsp-8+arg_8], rbx
0x14010d96d  push    rbp
0x14010d96e  lea     rbp, [rsp-0A0h]
0x14010d976  sub     rsp, 1A0h
0x14010d97d  mov     rax, cs:__security_cookie
0x14010d984  xor     rax, rsp
0x14010d987  mov     [rbp+0A0h+var_10], rax
0x14010d98e  lea     r8, aLayout; "layout"
0x14010d995  mov     rdx, rcx; pszPathIn
0x14010d998  lea     rcx, [rsp+1A0h+lpFileName]; pszPathOut
0x14010d99d  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x14010d9a2  nop
0x14010d9a3  lea     rcx, [rsp+1A0h+lpFileName]
0x14010d9a8  cmp     [rbp+0A0h+var_118], 7
0x14010d9ad  cmova   rcx, [rsp+1A0h+lpFileName]; lpFileName
0x14010d9b3  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x14010d9bc  mov     [rsp+1A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14010d9c4  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x14010d9cc  xor     r9d, r9d; lpSecurityAttributes
0x14010d9cf  mov     edx, 80000000h; dwDesiredAccess
0x14010d9d4  lea     r8d, [r9+1]; dwShareMode
0x14010d9d8  call    cs:__imp_CreateFileW
0x14010d9df  nop     dword ptr [rax+rax+00h]
0x14010d9e4  mov     [rsp+1A0h+var_160], rax
0x14010d9e9  lea     rcx, [rax+1]
0x14010d9ed  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14010d9f4  jnz     short loc_14010DA3F
0x14010d9f6  mov     rbx, [rbp+0A8h]
0x14010d9fd  call    cs:__imp_GetLastError
0x14010da04  nop     dword ptr [rax+rax+00h]
0x14010da09  cmp     eax, 2
0x14010da0c  jz      short loc_14010DA23
0x14010da0e  lea     r8, aOnecoreVmCompu_83; "onecore\\vm\\compute\\shared\\storage\\"...
0x14010da15  mov     edx, 8Ch; void *
0x14010da1a  mov     rcx, rbx; this
0x14010da1d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010da23  lea     rcx, [rsp+1A0h+var_160]; void *
0x14010da28  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14010da2d  nop
0x14010da2e  lea     rcx, [rsp+1A0h+lpFileName]; this
0x14010da33  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14010da38  xor     al, al
0x14010da3a  jmp     loc_14010DB3D
0x14010da3f  mov     [rsp+1A0h+NumberOfBytesRead], 0
0x14010da47  mov     qword ptr [rsp+1A0h+dwCreationDisposition], 0; unsigned int
0x14010da50  lea     r9, [rsp+1A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14010da55  mov     r8d, 100h; nNumberOfBytesToRead
0x14010da5b  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x14010da5f  mov     rcx, rax; hFile
0x14010da62  call    cs:__imp_ReadFile
0x14010da69  nop     dword ptr [rax+rax+00h]
0x14010da6e  mov     rcx, [rbp+0A8h]; this
0x14010da75  test    eax, eax
0x14010da77  jnz     short loc_14010DA8B
0x14010da79  lea     r8, aOnecoreVmCompu_83; "onecore\\vm\\compute\\shared\\storage\\"...
0x14010da80  mov     edx, 92h; void *
0x14010da85  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010da8b  xorps   xmm0, xmm0
0x14010da8e  movups  xmmword ptr [rsp+1A0h+Buf1], xmm0
0x14010da93  xorps   xmm1, xmm1
0x14010da96  movdqu  xmmword ptr [rsp+1A0h+Size], xmm1
0x14010da9c  mov     r8d, [rsp+1A0h+NumberOfBytesRead]
0x14010daa1  lea     rdx, [rbp+0A0h+Buffer]
0x14010daa5  lea     rcx, [rsp+1A0h+Buf1]
0x14010daaa  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14010daaf  lea     rdx, Buf2
0x14010dab6  cmp     qword ptr cs:xmmword_1403DCED8+8, 0Fh
0x14010dabe  cmova   rdx, cs:Buf2; Buf2
0x14010dac6  mov     r8, [rsp+1A0h+Size]; Size
0x14010dacb  lea     rcx, [rsp+1A0h+Buf1]
0x14010dad0  cmp     [rsp+1A0h+Size+8], 0Fh
0x14010dad6  cmova   rcx, [rsp+1A0h+Buf1]; Buf1
0x14010dadc  cmp     r8, qword ptr cs:xmmword_1403DCED8
0x14010dae3  jnz     short loc_14010DAF7
0x14010dae5  test    r8, r8
0x14010dae8  jz      short loc_14010DAF3
0x14010daea  call    memcmp_0
0x14010daef  test    eax, eax
0x14010daf1  jnz     short loc_14010DAF7
0x14010daf3  xor     bl, bl
0x14010daf5  jmp     short loc_14010DAF9
0x14010daf7  mov     bl, 1
0x14010daf9  lea     rcx, [rsp+1A0h+Buf1]
0x14010dafe  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14010db03  test    bl, bl
0x14010db05  jz      short loc_14010DB26
0x14010db07  mov     rcx, [rbp+0A8h]; this
0x14010db0e  mov     r9d, 0C0370112h; char *
0x14010db14  lea     r8, aOnecoreVmCompu_83; "onecore\\vm\\compute\\shared\\storage\\"...
0x14010db1b  mov     edx, 96h; void *
0x14010db20  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14010db26  lea     rcx, [rsp+1A0h+var_160]; void *
0x14010db2b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14010db30  nop
0x14010db31  lea     rcx, [rsp+1A0h+lpFileName]; this
0x14010db36  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14010db3b  mov     al, 1
0x14010db3d  mov     rcx, [rbp+0A0h+var_10]
0x14010db44  xor     rcx, rsp; StackCookie
0x14010db47  call    __security_check_cookie
0x14010db4c  mov     rbx, [rsp+1A0h+arg_8]
0x14010db54  add     rsp, 1A0h
0x14010db5b  pop     rbp
0x14010db5c  retn
```
