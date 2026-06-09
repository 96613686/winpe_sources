# GDIThunkingVIALPCThread

- ea: `0x14000fae0`
- end: `0x14000feb5`
- name: `GDIThunkingVIALPCThread`
- size: `981`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001b50`
- `0x140001b90`
- `0x140001ee0`
- `0x1400028b8`
- `0x140005f18`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000f9cc`
- `0x14000fae0`
- `0x14001293c`
- `0x140012a20`
- `0x140012a9c`
- `0x140012bf8`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000fd7d`
- `KERNEL32!GetLastError` at `0x14000fd8c`
- `KERNEL32!GetLastError` at `0x14000fe4e`
- `KERNEL32!GetLastError` at `0x14000fe5d`
- `KERNEL32!GetLastError` at `0x14000fd7d`
- `KERNEL32!GetLastError` at `0x14000fd8c`
- `KERNEL32!GetLastError` at `0x14000fe4e`
- `KERNEL32!GetLastError` at `0x14000fe5d`
- `KERNEL32!CloseHandle` at `0x14000fd68`
- `KERNEL32!CloseHandle` at `0x14000fd68`
- `KERNEL32!GetProcAddress` at `0x14000fb83`
- `KERNEL32!GetProcAddress` at `0x14000fb9d`
- `KERNEL32!GetProcAddress` at `0x14000fb83`
- `KERNEL32!GetProcAddress` at `0x14000fb9d`
- `KERNEL32!LocalFree` at `0x14000fdee`
- `KERNEL32!LocalFree` at `0x14000fdee`
- `KERNEL32!SetEvent` at `0x14000fe7f`
- `KERNEL32!SetEvent` at `0x14000fe7f`
- `KERNEL32!CreateThread` at `0x14000fd5a`
- `KERNEL32!CreateThread` at `0x14000fd5a`
- `KERNEL32!LoadLibraryExW` at `0x14000fb67`
- `KERNEL32!LoadLibraryExW` at `0x14000fb67`
- `ntdll!RtlInitUnicodeString` at `0x14000fc8d`
- `ntdll!RtlInitUnicodeString` at `0x14000fc8d`
- `ntdll!NtAlpcCreatePort` at `0x14000fcf1`
- `ntdll!NtAlpcCreatePort` at `0x14000fcf1`

## string_xrefs

- `0x14000fb51`: `GDI32.DLL`
- `0x14000fd06`: `Created LPC port %ws`
- `0x14000fd0d`: `GDIThunkingVIALPCThread`
- `0x14000fd9f`: `GDIThunkingVIALPCThread`
- `0x14000fddf`: `GDIThunkingVIALPCThread`
- `0x14000fe11`: `GDIThunkingVIALPCThread`
- `0x14000fe70`: `GDIThunkingVIALPCThread`
- `0x14000fd83`: `Failed to create the messaging thread.  Error %d.`
- `0x14000fdd8`: `Failed to create the LPC port %ws. Error %d.`
- `0x14000fe01`: `Failed to get token and auth info.  Error %d.`

## pseudocode

```c
__int64 __fastcall GDIThunkingVIALPCThread(_QWORD *Parameter)
{
  void *v2; // r12
  DWORD v3; // r14d
  __int64 v4; // r15
  HMODULE Library; // rax
  HMODULE v6; // rdi
  void (*ProcAddress)(void); // rax
  int v8; // edx
  FARPROC v9; // rsi
  int v10; // r8d
  int AuthenticationIdAndIntegrity; // ecx
  DWORD v12; // edi
  DWORD v13; // ecx
  HLOCAL v14; // r14
  int v15; // eax
  int v16; // r9d
  _QWORD *v17; // rax
  void *v18; // rdi
  HANDLE v19; // rax
  DWORD v20; // eax
  unsigned __int16 *v21; // rdx
  int v22; // edx
  unsigned int i; // eax
  int v24; // r8d
  DWORD LastError; // eax
  unsigned __int16 *v26; // rdx
  DWORD ThreadId; // [rsp+40h] [rbp-C0h] BYREF
  struct _LUID v29; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v36[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-50h]
  _BYTE v38[64]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SourceString[264]; // [rsp+130h] [rbp+30h] BYREF

  v32 = 0;
  v33 = 0;
  v34 = 0;
  memset_0(v36, 0, 0x48u);
  DestinationString = 0;
  memset_0(SourceString, 0, 0x208u);
  v2 = (void *)Parameter[1];
  v3 = *((_DWORD *)Parameter + 5);
  v4 = *Parameter;
  Library = LoadLibraryExW(L"GDI32.DLL", 0, 0x800u);
  v6 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v26 = L"Failed to load GDI32.  Error %d.";
    goto LABEL_35;
  }
  ProcAddress = (void (*)(void))GetProcAddress(Library, "GdiCurrentProcessSplWow64");
  if ( ProcAddress )
    ProcAddress();
  v9 = GetProcAddress(v6, "GdiPrinterThunk");
  if ( !v9 )
  {
    LastError = GetLastError();
    v26 = L"Failed to get the entry point for GdiPrinterThunk.  Error %d.";
LABEL_35:
    *((_DWORD *)Parameter + 4) = LastError;
    SplWow64Telemetry::WriteDbgTraceError("GDIThunkingVIALPCThread", v26, LastError);
    goto LABEL_36;
  }
  hMem = 0;
  Block = &NCoreLibrary::TString::gszNullState;
  v29 = 0;
  ThreadId = 0;
  NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v38, v8, v10);
  AuthenticationIdAndIntegrity = NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
                                   (NSecurityLibrary::TSidUserContext *)v38,
                                   &v29,
                                   &ThreadId);
  if ( AuthenticationIdAndIntegrity < 0 )
    goto LABEL_27;
  AuthenticationIdAndIntegrity = NSecurityLibrary::TSidUserContext::GetSidAsString(
                                   (NSecurityLibrary::TSidUserContext *)v38,
                                   (struct NCoreLibrary::TString *)&Block);
  if ( AuthenticationIdAndIntegrity < 0 )
    goto LABEL_27;
  v12 = ThreadId;
  v13 = ThreadId;
  if ( v3 < ThreadId )
    v13 = v3;
  AuthenticationIdAndIntegrity = SplWOWCreateSecurityDescriptor(v13, (struct NCoreLibrary::TString *)&Block, 0, &hMem);
  if ( AuthenticationIdAndIntegrity < 0 )
  {
LABEL_27:
    v24 = (unsigned __int16)AuthenticationIdAndIntegrity;
    if ( (AuthenticationIdAndIntegrity & 0x1FFF0000) != 0x70000 )
      v24 = AuthenticationIdAndIntegrity;
    *((_DWORD *)Parameter + 4) = v24;
    SplWow64Telemetry::WriteDbgTraceError("GDIThunkingVIALPCThread", L"Failed to get token and auth info.  Error %d.");
    goto LABEL_30;
  }
  if ( v3 < v12 )
    v12 = v3;
  if ( v12 < 0x2000 )
    v12 = 0x2000;
  StringCchPrintfW(
    SourceString,
    0x104u,
    L"%s_%x_%x_%x_%x",
    L"\\RPC Control\\UmpdProxy",
    *(_DWORD *)(v4 + 56),
    v29.LowPart,
    v29.HighPart,
    v12);
  RtlInitUnicodeString(&DestinationString, SourceString);
  v14 = hMem;
  LODWORD(v32) = 48;
  *((_QWORD *)&v32 + 1) = 0;
  DWORD2(v33) = 64;
  *(_QWORD *)&v33 = &DestinationString;
  v34 = (unsigned __int64)hMem;
  memset_0(v36, 0, 0x48u);
  v36[0] = 0x20000;
  v37 = 512;
  v15 = NtAlpcCreatePort(v4 + 64, &v32, v36);
  v16 = v15;
  if ( v15 < 0 )
  {
    v22 = 87;
    for ( i = 0; i < 0x10; i += 2 )
    {
      if ( *((_DWORD *)&ErrorMap + (int)i) == v16 )
        v22 = *((_DWORD *)&ErrorMap + (int)i + 1);
    }
    *((_DWORD *)Parameter + 4) = v22;
    SplWow64Telemetry::WriteDbgTraceError(
      "GDIThunkingVIALPCThread",
      L"Failed to create the LPC port %ws. Error %d.",
      SourceString);
    goto LABEL_26;
  }
  SplWow64Telemetry::WriteDbgTraceInfo(
    "GDIThunkingVIALPCThread",
    L"Created LPC port %ws",
    SourceString,
    (unsigned int)v15);
  ThreadId = 0;
  v17 = operator new(8u);
  v18 = v17;
  if ( !v17 )
  {
    v20 = GetLastError();
    v21 = L"Failed to allocate memory for message data.  Error %d.";
    goto LABEL_20;
  }
  *v17 = v4;
  *(_QWORD *)(v4 + 72) = v9;
  v19 = CreateThread(0, 0, LPCConnMsgsServingThread, v17, 0, &ThreadId);
  if ( !v19 )
  {
    operator delete(v18);
    v20 = GetLastError();
    v21 = L"Failed to create the messaging thread.  Error %d.";
LABEL_20:
    *((_DWORD *)Parameter + 4) = v20;
    SplWow64Telemetry::WriteDbgTraceError("GDIThunkingVIALPCThread", v21, v20);
    goto LABEL_26;
  }
  CloseHandle(v19);
LABEL_26:
  LocalFree(v14);
LABEL_30:
  NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v38);
  if ( Block != &NCoreLibrary::TString::gszNullState && Block != word_14002174A )
    operator delete(Block);
LABEL_36:
  SetEvent(v2);
  return 1;
}

```

## disassembly

```asm
0x14000fae0  mov     [rsp-8+arg_8], rbx
0x14000fae5  mov     [rsp-8+arg_10], rsi
0x14000faea  push    rbp
0x14000faeb  push    rdi
0x14000faec  push    r12
0x14000faee  push    r14
0x14000faf0  push    r15
0x14000faf2  lea     rbp, [rsp-250h]
0x14000fafa  sub     rsp, 350h
0x14000fb01  mov     rax, cs:__security_cookie
0x14000fb08  xor     rax, rsp
0x14000fb0b  mov     [rbp+270h+var_30], rax
0x14000fb12  xorps   xmm0, xmm0
0x14000fb15  xor     edx, edx; Val
0x14000fb17  mov     rbx, rcx
0x14000fb1a  lea     rcx, [rbp+270h+var_2D0]; void *
0x14000fb1e  movups  [rsp+370h+var_310], xmm0
0x14000fb23  lea     r8d, [rdx+48h]; Size
0x14000fb27  movups  [rsp+370h+var_300], xmm0
0x14000fb2c  movups  [rbp+270h+var_2F0], xmm0
0x14000fb30  call    memset_0
0x14000fb35  xorps   xmm0, xmm0
0x14000fb38  lea     rcx, [rbp+270h+SourceString]; void *
0x14000fb3c  xor     edx, edx; Val
0x14000fb3e  mov     r8d, 208h; Size
0x14000fb44  movups  xmmword ptr [rbp+270h+DestinationString.Length], xmm0
0x14000fb48  call    memset_0
0x14000fb4d  mov     r12, [rbx+8]
0x14000fb51  lea     rcx, aGdi32Dll; "GDI32.DLL"
0x14000fb58  mov     r14d, [rbx+14h]
0x14000fb5c  xor     edx, edx; hFile
0x14000fb5e  mov     r15, [rbx]
0x14000fb61  mov     r8d, 800h; dwFlags
0x14000fb67  call    cs:__imp_LoadLibraryExW
0x14000fb6d  mov     rdi, rax
0x14000fb70  test    rax, rax
0x14000fb73  jz      loc_14000FE5D
0x14000fb79  lea     rdx, aGdicurrentproc; "GdiCurrentProcessSplWow64"
0x14000fb80  mov     rcx, rax; hModule
0x14000fb83  call    cs:__imp_GetProcAddress
0x14000fb89  test    rax, rax
0x14000fb8c  jz      short loc_14000FB93
0x14000fb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb93  lea     rdx, aGdiprinterthun; "GdiPrinterThunk"
0x14000fb9a  mov     rcx, rdi; hModule
0x14000fb9d  call    cs:__imp_GetProcAddress
0x14000fba3  mov     rsi, rax
0x14000fba6  test    rax, rax
0x14000fba9  jz      loc_14000FE4E
0x14000fbaf  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14000fbb6  mov     [rsp+370h+hMem], 0
0x14000fbbf  lea     rcx, [rbp+270h+var_280]; this
0x14000fbc3  mov     [rsp+370h+Block], rax
0x14000fbc8  mov     qword ptr [rsp+370h+var_328.LowPart], 0
0x14000fbd1  mov     [rsp+370h+ThreadId], 0
0x14000fbd9  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x14000fbde  lea     r8, [rsp+370h+ThreadId]; unsigned int *
0x14000fbe3  lea     rdx, [rsp+370h+var_328]; struct _LUID *
0x14000fbe8  lea     rcx, [rbp+270h+var_280]; this
0x14000fbec  call    ?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z; NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)
0x14000fbf1  mov     ecx, eax
0x14000fbf3  test    eax, eax
0x14000fbf5  js      loc_14000FDF6
0x14000fbfb  lea     rdx, [rsp+370h+Block]; struct NCoreLibrary::TString *
0x14000fc00  lea     rcx, [rbp+270h+var_280]; this
0x14000fc04  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x14000fc09  mov     ecx, eax
0x14000fc0b  test    eax, eax
0x14000fc0d  js      loc_14000FDF6
0x14000fc13  mov     edi, [rsp+370h+ThreadId]
0x14000fc17  lea     r9, [rsp+370h+hMem]; void **
0x14000fc1c  mov     ecx, edi
0x14000fc1e  lea     rdx, [rsp+370h+Block]; struct NCoreLibrary::TString *
0x14000fc23  cmp     r14d, edi
0x14000fc26  cmovb   ecx, r14d; unsigned int
0x14000fc2a  xor     r8d, r8d; bool
0x14000fc2d  call    ?SplWOWCreateSecurityDescriptor@@YAJKAEAVTString@NCoreLibrary@@_NPEAPEAX@Z; SplWOWCreateSecurityDescriptor(ulong,NCoreLibrary::TString &,bool,void * *)
0x14000fc32  mov     ecx, eax
0x14000fc34  test    eax, eax
0x14000fc36  js      loc_14000FDF6
0x14000fc3c  mov     eax, 2000h
0x14000fc41  lea     r9, aRpcControlUmpd; "\\RPC Control\\UmpdProxy"
0x14000fc48  cmp     r14d, edi
0x14000fc4b  lea     r8, aSXXXX; "%s_%x_%x_%x_%x"
0x14000fc52  mov     edx, 104h; unsigned __int64
0x14000fc57  lea     rcx, [rbp+270h+SourceString]; unsigned __int16 *
0x14000fc5b  cmovb   edi, r14d
0x14000fc5f  cmp     edi, eax
0x14000fc61  cmovb   edi, eax
0x14000fc64  mov     eax, [rsp+370h+var_328.HighPart]
0x14000fc68  mov     [rsp+370h+var_338], edi
0x14000fc6c  mov     [rsp+370h+var_340], eax
0x14000fc70  mov     eax, [rsp+370h+var_328.LowPart]
0x14000fc74  mov     dword ptr [rsp+370h+lpThreadId], eax
0x14000fc78  mov     eax, [r15+38h]
0x14000fc7c  mov     [rsp+370h+dwCreationFlags], eax
0x14000fc80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fc85  lea     rdx, [rbp+270h+SourceString]; SourceString
0x14000fc89  lea     rcx, [rbp+270h+DestinationString]; DestinationString
0x14000fc8d  call    cs:__imp_RtlInitUnicodeString
0x14000fc93  mov     r14, [rsp+370h+hMem]
0x14000fc98  lea     rax, [rbp+270h+DestinationString]
0x14000fc9c  xor     edx, edx; Val
0x14000fc9e  mov     dword ptr [rsp+370h+var_310], 30h ; '0'
0x14000fca6  lea     rcx, [rbp+270h+var_2D0]; void *
0x14000fcaa  mov     qword ptr [rsp+370h+var_310+8], 0
0x14000fcb3  mov     dword ptr [rsp+370h+var_300+8], 40h ; '@'
0x14000fcbb  mov     qword ptr [rsp+370h+var_300], rax
0x14000fcc0  lea     r8d, [rdx+48h]; Size
0x14000fcc4  mov     qword ptr [rbp+270h+var_2F0], r14
0x14000fcc8  mov     qword ptr [rbp+270h+var_2F0+8], 0
0x14000fcd0  call    memset_0
0x14000fcd5  lea     rcx, [r15+40h]
0x14000fcd9  mov     [rbp+270h+var_2D0], 20000h
0x14000fce0  lea     r8, [rbp+270h+var_2D0]
0x14000fce4  mov     [rbp+270h+var_2C0], 200h
0x14000fcec  lea     rdx, [rsp+370h+var_310]
0x14000fcf1  call    cs:__imp_NtAlpcCreatePort
0x14000fcf7  mov     r9d, eax
0x14000fcfa  test    eax, eax
0x14000fcfc  js      loc_14000FDAD
0x14000fd02  lea     r8, [rbp+270h+SourceString]
0x14000fd06  lea     rdx, aCreatedLpcPort; "Created LPC port %ws"
0x14000fd0d  lea     rcx, aGdithunkingvia; "GDIThunkingVIALPCThread"
0x14000fd14  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000fd19  mov     ecx, 8; Size
0x14000fd1e  mov     [rsp+370h+ThreadId], 0
0x14000fd26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fd2b  mov     rdi, rax
0x14000fd2e  test    rax, rax
0x14000fd31  jz      short loc_14000FD8C
0x14000fd33  mov     [rax], r15
0x14000fd36  lea     r8, LPCConnMsgsServingThread; lpStartAddress
0x14000fd3d  lea     rax, [rsp+370h+ThreadId]
0x14000fd42  mov     [r15+48h], rsi
0x14000fd46  mov     [rsp+370h+lpThreadId], rax; lpThreadId
0x14000fd4b  mov     r9, rdi; lpParameter
0x14000fd4e  xor     edx, edx; dwStackSize
0x14000fd50  mov     [rsp+370h+dwCreationFlags], 0; dwCreationFlags
0x14000fd58  xor     ecx, ecx; lpThreadAttributes
0x14000fd5a  call    cs:__imp_CreateThread
0x14000fd60  test    rax, rax
0x14000fd63  jz      short loc_14000FD70
0x14000fd65  mov     rcx, rax; hObject
0x14000fd68  call    cs:__imp_CloseHandle
0x14000fd6e  jmp     short loc_14000FDEB
0x14000fd70  mov     edx, 8
0x14000fd75  mov     rcx, rdi; Block
0x14000fd78  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fd7d  call    cs:__imp_GetLastError
0x14000fd83  lea     rdx, aFailedToCreate; "Failed to create the messaging thread. "...
0x14000fd8a  jmp     short loc_14000FD99
0x14000fd8c  call    cs:__imp_GetLastError
0x14000fd92  lea     rdx, aFailedToAlloca_0; "Failed to allocate memory for message d"...
0x14000fd99  mov     r8d, eax
0x14000fd9c  mov     [rbx+10h], eax
0x14000fd9f  lea     rcx, aGdithunkingvia; "GDIThunkingVIALPCThread"
0x14000fda6  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000fdab  jmp     short loc_14000FDEB
0x14000fdad  mov     edx, 57h ; 'W'
0x14000fdb2  lea     r8, ?ErrorMap@@3PAJA; long near * ErrorMap
0x14000fdb9  xor     eax, eax
0x14000fdbb  movsxd  rcx, eax
0x14000fdbe  cmp     [r8+rcx*4], r9d
0x14000fdc2  jnz     short loc_14000FDC9
0x14000fdc4  mov     edx, [r8+rcx*4+4]
0x14000fdc9  add     eax, 2
0x14000fdcc  cmp     eax, 10h
0x14000fdcf  jb      short loc_14000FDBB
0x14000fdd1  mov     [rbx+10h], edx
0x14000fdd4  lea     r8, [rbp+270h+SourceString]
0x14000fdd8  lea     rdx, aFailedToCreate_4; "Failed to create the LPC port %ws. Erro"...
0x14000fddf  lea     rcx, aGdithunkingvia; "GDIThunkingVIALPCThread"
0x14000fde6  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000fdeb  mov     rcx, r14; hMem
0x14000fdee  call    cs:__imp_LocalFree
0x14000fdf4  jmp     short loc_14000FE21
0x14000fdf6  mov     eax, ecx
0x14000fdf8  movzx   r8d, cx
0x14000fdfc  and     eax, 1FFF0000h
0x14000fe01  lea     rdx, aFailedToGetTok; "Failed to get token and auth info.  Err"...
0x14000fe08  cmp     eax, 70000h
0x14000fe0d  cmovnz  r8d, ecx
0x14000fe11  lea     rcx, aGdithunkingvia; "GDIThunkingVIALPCThread"
0x14000fe18  mov     [rbx+10h], r8d
0x14000fe1c  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000fe21  lea     rcx, [rbp+270h+var_280]; this
0x14000fe25  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x14000fe2a  mov     rcx, [rsp+370h+Block]; Block
0x14000fe2f  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14000fe36  cmp     rcx, rax
0x14000fe39  jz      short loc_14000FE7C
0x14000fe3b  lea     rax, word_14002174A
0x14000fe42  cmp     rcx, rax
0x14000fe45  jz      short loc_14000FE7C
0x14000fe47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fe4c  jmp     short loc_14000FE7C
0x14000fe4e  call    cs:__imp_GetLastError
0x14000fe54  lea     rdx, aFailedToGetThe; "Failed to get the entry point for GdiPr"...
0x14000fe5b  jmp     short loc_14000FE6A
0x14000fe5d  call    cs:__imp_GetLastError
0x14000fe63  lea     rdx, aFailedToLoadGd; "Failed to load GDI32.  Error %d."
0x14000fe6a  mov     r8d, eax
0x14000fe6d  mov     [rbx+10h], eax
0x14000fe70  lea     rcx, aGdithunkingvia; "GDIThunkingVIALPCThread"
0x14000fe77  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000fe7c  mov     rcx, r12; hEvent
0x14000fe7f  call    cs:__imp_SetEvent
0x14000fe85  mov     eax, 1
0x14000fe8a  mov     rcx, [rbp+270h+var_30]
0x14000fe91  xor     rcx, rsp; StackCookie
0x14000fe94  call    __security_check_cookie
0x14000fe99  lea     r11, [rsp+370h+var_20]
0x14000fea1  mov     rbx, [r11+38h]
0x14000fea5  mov     rsi, [r11+40h]
0x14000fea9  mov     rsp, r11
0x14000feac  pop     r15
0x14000feae  pop     r14
0x14000feb0  pop     r12
0x14000feb2  pop     rdi
0x14000feb3  pop     rbp
0x14000feb4  retn
```
