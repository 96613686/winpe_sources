# CSpSapiServer::WaitServerNamedPipe(ulong,void * *)

- ea: `0x18005ded0`
- end: `0x18005e0c1`
- name: `?WaitServerNamedPipe@CSpSapiServer@@CAJKPEAPEAX@Z`
- size: `497`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800e8b60`

## callees

- `0x18000a590`
- `0x180013ec0`
- `0x180045938`
- `0x18005ded0`
- `0x1800e8774`
- `0x1800ec144`
- `0x1800ec9f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005df02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005df02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e031`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005df0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e04e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005df0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e04e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005df7a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005df7a`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18005df9f`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18005df9f`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18005e019`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18005e019`

## string_xrefs

- `0x18005dfdb`: `CreateFile`
- `0x18005dfc8`: `Client failed to wait for the named pipe, Attempt = %u, Error = %X.`
- `0x18005e095`: `SrNamedPipeClientPipeInformation: Failed to log access denied on pipe. Error = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpSapiServer::WaitServerNamedPipe(int a1, void **a2)
{
  DWORD TickCount; // r12d
  signed int PipeNameForClient; // ebx
  HANDLE FileW; // rdi
  int v6; // esi
  int i; // r14d
  signed int LastError; // eax
  int Win32Error; // eax
  int v10; // eax
  DWORD CurrentProcessId; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-10h] BYREF
  int v15; // [rsp+A0h] [rbp+40h] BYREF
  int v16; // [rsp+B0h] [rbp+50h] BYREF
  DWORD Mode; // [rsp+B8h] [rbp+58h] BYREF

  v15 = a1;
  lpFileName[0] = 0;
  v16 = -1;
  v13 = &cchOriginalDestLength;
  CurrentProcessId = GetCurrentProcessId();
  TickCount = GetTickCount();
  PipeNameForClient = SpGetPipeNameForClient((struct CSpDynamicString *)lpFileName);
  v15 = PipeNameForClient;
  if ( PipeNameForClient >= 0 )
  {
    PipeNameForClient = -2147200911;
    v15 = -2147200911;
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      v16 = v6;
      if ( i >= 20 )
        goto LABEL_20;
      FileW = CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( LastError != 231 )
      {
        v13 = L"CreateFile";
        if ( LastError > 0 )
          PipeNameForClient = (unsigned __int16)LastError | 0x80070000;
        else
          PipeNameForClient = LastError;
        v15 = PipeNameForClient;
        goto LABEL_14;
      }
      if ( !WaitNamedPipeW(lpFileName[0], 0x1388u) )
      {
        v13 = L"WaitNamedPipe";
        Win32Error = SpHrFromLastWin32Error();
        DoTraceMessage(4, "Client failed to wait for the named pipe, Attempt = %u, Error = %X.", v6, Win32Error);
LABEL_14:
        if ( PipeNameForClient < 0 )
          goto LABEL_20;
LABEL_17:
        Mode = 2;
        if ( !SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
        {
          v13 = L"SetNamedPipeHandleState";
          CloseHandle(FileW);
          PipeNameForClient = SpHrFromLastWin32Error();
          v15 = PipeNameForClient;
        }
        goto LABEL_19;
      }
      v6 = i + 1;
    }
    PipeNameForClient = 0;
    v15 = 0;
    goto LABEL_17;
  }
  FileW = 0;
  v13 = L"SpGetPipeNameForClient";
LABEL_19:
  if ( PipeNameForClient < 0 )
LABEL_20:
    FileW = 0;
  *a2 = FileW;
  if ( PipeNameForClient < 0 )
  {
    Mode = GetTickCount() - TickCount;
    SPTelemetry::SrNamedPipeClientPipeInformation<unsigned long &,CSpDynamicString &,unsigned short const * &,long &,unsigned long,int &>(
      (unsigned int)&CurrentProcessId,
      (unsigned int)lpFileName,
      (unsigned int)&v13,
      (unsigned int)&v15,
      (__int64)&Mode,
      (__int64)&v16);
    if ( PipeNameForClient == -2147024891 )
    {
      v10 = TraceNamedPipeClientAccessDenied();
      if ( v10 < 0 )
        DoTraceMessage(2, "SrNamedPipeClientPipeInformation: Failed to log access denied on pipe. Error = 0x%08x.", v10);
    }
  }
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)lpFileName);
  return (unsigned int)PipeNameForClient;
}

```

## disassembly

```asm
0x18005ded0  mov     [rsp-38h+arg_0], ecx
0x18005ded4  push    rbp
0x18005ded5  push    rbx
0x18005ded6  push    rsi
0x18005ded7  push    rdi
0x18005ded8  push    r12
0x18005deda  push    r14
0x18005dedc  push    r15
0x18005dede  mov     rbp, rsp
0x18005dee1  sub     rsp, 60h
0x18005dee5  mov     r15, rdx
0x18005dee8  mov     [rbp+lpFileName], 0
0x18005def0  mov     [rbp+arg_10], 0FFFFFFFFh
0x18005def7  lea     rax, cchOriginalDestLength
0x18005defe  mov     [rbp+var_18], rax
0x18005df02  call    cs:__imp_GetCurrentProcessId
0x18005df08  mov     [rbp+var_20], eax
0x18005df0b  call    cs:__imp_GetTickCount
0x18005df11  mov     r12d, eax
0x18005df14  lea     rcx, [rbp+lpFileName]; struct CSpDynamicString *
0x18005df18  call    ?SpGetPipeNameForClient@@YAJAEAVCSpDynamicString@@@Z; SpGetPipeNameForClient(CSpDynamicString &)
0x18005df1d  mov     ebx, eax
0x18005df1f  mov     [rbp+arg_0], eax
0x18005df22  test    eax, eax
0x18005df24  jns     short loc_18005DF38
0x18005df26  xor     edi, edi
0x18005df28  lea     rax, aSpgetpipenamef; "SpGetPipeNameForClient"
0x18005df2f  mov     [rbp+var_18], rax
0x18005df33  jmp     loc_18005E041
0x18005df38  mov     ebx, 80045071h
0x18005df3d  mov     [rbp+arg_0], ebx
0x18005df40  xor     esi, esi
0x18005df42  xor     r14d, r14d
0x18005df45  mov     [rbp+arg_10], esi
0x18005df48  cmp     r14d, 14h
0x18005df4c  jge     loc_18005E045
0x18005df52  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18005df5b  mov     [rsp+60h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18005df63  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18005df6b  xor     r9d, r9d; lpSecurityAttributes
0x18005df6e  xor     r8d, r8d; dwShareMode
0x18005df71  mov     edx, 0C0000000h; dwDesiredAccess
0x18005df76  mov     rcx, [rbp+lpFileName]; lpFileName
0x18005df7a  call    cs:__imp_CreateFileW
0x18005df80  mov     rdi, rax
0x18005df83  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005df87  jnz     short loc_18005E000
0x18005df89  call    cs:__imp_GetLastError
0x18005df8f  cmp     eax, 0E7h
0x18005df94  jnz     short loc_18005DFDB
0x18005df96  mov     edx, 1388h; nTimeOut
0x18005df9b  mov     rcx, [rbp+lpFileName]; lpNamedPipeName
0x18005df9f  call    cs:__imp_WaitNamedPipeW
0x18005dfa5  test    eax, eax
0x18005dfa7  jz      short loc_18005DFB2
0x18005dfa9  lea     esi, [r14+1]
0x18005dfad  mov     r14d, esi
0x18005dfb0  jmp     short loc_18005DF45
0x18005dfb2  lea     rax, aWaitnamedpipe; "WaitNamedPipe"
0x18005dfb9  mov     [rbp+var_18], rax
0x18005dfbd  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18005dfc2  mov     r9d, eax
0x18005dfc5  mov     r8d, esi
0x18005dfc8  lea     rdx, aClientFailedTo; "Client failed to wait for the named pip"...
0x18005dfcf  mov     ecx, 4; int
0x18005dfd4  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18005dfd9  jmp     short loc_18005DFFA
0x18005dfdb  lea     rcx, aCreatefile; "CreateFile"
0x18005dfe2  mov     [rbp+var_18], rcx
0x18005dfe6  test    eax, eax
0x18005dfe8  jg      short loc_18005DFEE
0x18005dfea  mov     ebx, eax
0x18005dfec  jmp     short loc_18005DFF7
0x18005dfee  movzx   ebx, ax
0x18005dff1  or      ebx, 80070000h
0x18005dff7  mov     [rbp+arg_0], ebx
0x18005dffa  test    ebx, ebx
0x18005dffc  js      short loc_18005E045
0x18005dffe  jmp     short loc_18005E005
0x18005e000  xor     ebx, ebx
0x18005e002  mov     [rbp+arg_0], ebx
0x18005e005  mov     [rbp+Mode], 2
0x18005e00c  xor     r9d, r9d; lpCollectDataTimeout
0x18005e00f  xor     r8d, r8d; lpMaxCollectionCount
0x18005e012  lea     rdx, [rbp+Mode]; lpMode
0x18005e016  mov     rcx, rdi; hNamedPipe
0x18005e019  call    cs:__imp_SetNamedPipeHandleState
0x18005e01f  test    eax, eax
0x18005e021  jnz     short loc_18005E041
0x18005e023  lea     rax, aSetnamedpipeha; "SetNamedPipeHandleState"
0x18005e02a  mov     [rbp+var_18], rax
0x18005e02e  mov     rcx, rdi; hObject
0x18005e031  call    cs:__imp_CloseHandle
0x18005e037  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18005e03c  mov     ebx, eax
0x18005e03e  mov     [rbp+arg_0], eax
0x18005e041  test    ebx, ebx
0x18005e043  jns     short loc_18005E047
0x18005e045  xor     edi, edi
0x18005e047  mov     [r15], rdi
0x18005e04a  test    ebx, ebx
0x18005e04c  jns     short loc_18005E0A7
0x18005e04e  call    cs:__imp_GetTickCount
0x18005e054  sub     eax, r12d
0x18005e057  mov     [rbp+Mode], eax
0x18005e05a  lea     rax, [rbp+arg_10]
0x18005e05e  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax
0x18005e063  lea     rax, [rbp+Mode]
0x18005e067  mov     qword ptr [rsp+60h+dwCreationDisposition], rax
0x18005e06c  lea     r9, [rbp+arg_0]
0x18005e070  lea     r8, [rbp+var_18]
0x18005e074  lea     rdx, [rbp+lpFileName]
0x18005e078  lea     rcx, [rbp+var_20]
0x18005e07c  call    ??$SrNamedPipeClientPipeInformation@AEAKAEAVCSpDynamicString@@AEAPEBGAEAJKAEAH@SPTelemetry@@SAXAEAKAEAVCSpDynamicString@@AEAPEBGAEAJ$$QEAKAEAH@Z; SPTelemetry::SrNamedPipeClientPipeInformation<ulong &,CSpDynamicString &,ushort const * &,long &,ulong,int &>(ulong &,CSpDynamicString &,ushort const * &,long &,ulong &&,int &)
0x18005e081  cmp     ebx, 80070005h
0x18005e087  jnz     short loc_18005E0A7
0x18005e089  call    ?TraceNamedPipeClientAccessDenied@@YAJXZ; TraceNamedPipeClientAccessDenied(void)
0x18005e08e  test    eax, eax
0x18005e090  jns     short loc_18005E0A7
0x18005e092  mov     r8d, eax
0x18005e095  lea     rdx, aSrnamedpipecli; "SrNamedPipeClientPipeInformation: Faile"...
0x18005e09c  mov     ecx, 2; int
0x18005e0a1  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18005e0a6  nop
0x18005e0a7  lea     rcx, [rbp+lpFileName]; this
0x18005e0ab  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x18005e0b0  mov     eax, ebx
0x18005e0b2  add     rsp, 60h
0x18005e0b6  pop     r15
0x18005e0b8  pop     r14
0x18005e0ba  pop     r12
0x18005e0bc  pop     rdi
0x18005e0bd  pop     rsi
0x18005e0be  pop     rbx
0x18005e0bf  pop     rbp
0x18005e0c0  retn
```
