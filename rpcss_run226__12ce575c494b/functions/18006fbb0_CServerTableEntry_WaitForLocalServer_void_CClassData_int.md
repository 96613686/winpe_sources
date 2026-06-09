# CServerTableEntry::WaitForLocalServer(void *,CClassData *,int)

- ea: `0x18006fbb0`
- end: `0x18006ff54`
- name: `?WaitForLocalServer@CServerTableEntry@@QEAAJPEAXPEAVCClassData@@H@Z`
- size: `932`
- prototype: `int(CServerTableEntry *__hidden this, void *, struct CClassData *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067898`

## callees

- `0x18002f8cc`
- `0x180034540`
- `0x18003e920`
- `0x18003e97c`
- `0x180055c44`
- `0x18006fbb0`
- `0x180081210`
- `0x1800f3d2c`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fc5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fc5d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18006fdcc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18006fdcc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18006fc3e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18006fc3e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006fc20`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006fc20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006fc93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006fc93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fcb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fd25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fd52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fe88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ff22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fcb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fd25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fd52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fe88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ff22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fcf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fd93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fe2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fcf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fd93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fe2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fecc`

## string_xrefs

- `0x18006fd34`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006ff06`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006fd10`: `Wait for Local server: Server Process Terminated: ClassIdentifier:%ws PID:%x error: %x `
- `0x18006fee8`: `Wait for Local server ClassIdentifier:%ws PID:%x encountered error: %x `
- `0x18006fe43`: `Wait for Local server timed out ClassIdentifier:%ws PID:%x`
- `0x18006fdac`: `Terminating server ClassIdentifier:%ws PID:%x`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::WaitForLocalServer(
        CServerTableEntry *this,
        void *a2,
        struct CClassData *a3,
        int a4)
{
  char v6; // bl
  DWORD v7; // r9d
  __int64 v8; // rax
  void *v9; // rax
  DWORD v10; // eax
  DWORD v11; // r14d
  CActivationStateList *v12; // rcx
  __int64 v13; // rax
  void (__fastcall *v14)(CServerTableEntry *, HSTRING *); // rbx
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rax
  void (__fastcall *v18)(CServerTableEntry *, HSTRING *); // rbx
  __int64 v19; // rax
  void (__fastcall *v20)(CServerTableEntry *, HSTRING *); // rbx
  __int64 v21; // r9
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  void (__fastcall *v25)(CServerTableEntry *, HSTRING *); // rbx
  int v26; // edx
  int v27; // ecx
  unsigned int v28; // ebx
  unsigned int bAlertable; // [rsp+20h] [rbp-30h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HSTRING string; // [rsp+80h] [rbp+30h] BYREF
  DWORD ExitCode; // [rsp+98h] [rbp+48h] BYREF

  v6 = 0;
  *(_OWORD *)Handles = 0;
  if ( a4 )
  {
    v7 = -1;
  }
  else
  {
    v7 = gServerStartTimeout;
    v8 = *((_QWORD *)a3 + 12);
    if ( !v8 || !*(_QWORD *)(v8 + 24) )
      v6 = 1;
  }
  v9 = (void *)*((_QWORD *)this + 3);
  Handles[0] = a2;
  Handles[1] = v9;
  v10 = WaitForMultipleObjectsEx(2u, Handles, 0, v7, 0);
  ExitCode = 0;
  v11 = v10;
  if ( v10 != 1 )
  {
LABEL_16:
    if ( v11 )
    {
      if ( *((_QWORD *)this + 3) )
      {
        v17 = *(_QWORD *)this;
        string = 0;
        v18 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v17 + 32);
        WindowsDeleteString(0);
        string = 0;
        v18(this, &string);
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
        {
          WindowsGetStringRawBuffer(string, 0);
          ComTraceMessageT<unsigned __int64,unsigned long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (unsigned int)"CServerTableEntry::WaitForLocalServer",
            3138,
            1,
            (__int64)L"Terminating server ClassIdentifier:%ws PID:%x");
        }
        TerminateProcess(*((HANDLE *)this + 3), 0);
        WindowsDeleteString(string);
      }
      v19 = *(_QWORD *)this;
      string = 0;
      v20 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v19 + 32);
      WindowsDeleteString(0);
      string = 0;
      v20(this, &string);
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
      {
        WindowsGetStringRawBuffer(string, 0);
        ComTraceMessageT<unsigned __int64,unsigned long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (unsigned int)"CServerTableEntry::WaitForLocalServer",
          3150,
          1,
          (__int64)L"Wait for Local server timed out ClassIdentifier:%ws PID:%x");
      }
      v21 = ExitCode;
      v22 = retaddr;
      if ( ExitCode )
      {
        v23 = 3154;
      }
      else
      {
        v21 = 1460;
        v23 = 3156;
      }
      goto LABEL_35;
    }
    return 0;
  }
  GetExitCodeProcess(*((HANDLE *)this + 3), &ExitCode);
  if ( !v6 )
    goto LABEL_11;
  CActivationStateList::ZeroPID(v12, *((_DWORD *)this + 4));
  CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
  CloseHandle(*((HANDLE *)this + 3));
  *((_QWORD *)this + 3) = 0;
  CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
  if ( ExitCode == -1073741205 || ExitCode == -1073741515 )
  {
    v24 = *(_QWORD *)this;
    string = 0;
    v25 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v24 + 32);
    WindowsDeleteString(0);
    string = 0;
    v25(this, &string);
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
    {
      WindowsGetStringRawBuffer(string, 0);
      ComTraceMessageT<unsigned short const *,unsigned long,unsigned long>(
        v27,
        v26,
        3110,
        1,
        (__int64)L"Wait for Local server ClassIdentifier:%ws PID:%x encountered error: %x ");
    }
    v21 = ExitCode;
    if ( !ExitCode )
    {
      v28 = 0;
      goto LABEL_37;
    }
    v22 = retaddr;
    v23 = 3112;
LABEL_35:
    v28 = wil::details::in1diag3::Return_Win32(
            v22,
            (void *)v23,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)v21,
            bAlertable);
LABEL_37:
    WindowsDeleteString(string);
    return v28;
  }
  v11 = WaitForSingleObject(a2, gServerStartSecondChanceTimeout);
  if ( v11 )
  {
LABEL_11:
    v13 = *(_QWORD *)this;
    string = 0;
    v14 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v13 + 32);
    WindowsDeleteString(0);
    string = 0;
    v14(this, &string);
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      WindowsGetStringRawBuffer(string, 0);
      ComTraceMessageT<unsigned short const *,unsigned long,unsigned long>(
        v16,
        v15,
        3127,
        0,
        (__int64)L"Wait for Local server: Server Process Terminated: ClassIdentifier:%ws PID:%x error: %x ");
    }
    WindowsDeleteString(string);
    goto LABEL_16;
  }
  return 0;
}

```

## disassembly

```asm
0x18006fbb0  mov     [rsp-28h+arg_8], rbx
0x18006fbb5  mov     [rsp-28h+arg_10], rsi
0x18006fbba  push    rbp
0x18006fbbb  push    rdi
0x18006fbbc  push    r12
0x18006fbbe  push    r14
0x18006fbc0  push    r15
0x18006fbc2  mov     rbp, rsp
0x18006fbc5  sub     rsp, 50h
0x18006fbc9  xor     r15d, r15d
0x18006fbcc  xorps   xmm0, xmm0
0x18006fbcf  mov     rdi, rdx
0x18006fbd2  mov     rsi, rcx
0x18006fbd5  mov     bl, r15b
0x18006fbd8  movups  xmmword ptr [rbp+Handles], xmm0
0x18006fbdc  lea     r12d, [r15+1]
0x18006fbe0  test    r9d, r9d
0x18006fbe3  jz      short loc_18006FBEB
0x18006fbe5  or      r9d, 0FFFFFFFFh
0x18006fbe9  jmp     short loc_18006FC04
0x18006fbeb  mov     r9d, cs:?gServerStartTimeout@@3KC; dwMilliseconds
0x18006fbf2  mov     rax, [r8+60h]
0x18006fbf6  test    rax, rax
0x18006fbf9  jz      short loc_18006FC01
0x18006fbfb  cmp     [rax+18h], r15
0x18006fbff  jnz     short loc_18006FC04
0x18006fc01  mov     bl, r12b
0x18006fc04  mov     rax, [rcx+18h]
0x18006fc08  lea     rdx, [rbp+Handles]; lpHandles
0x18006fc0c  xor     r8d, r8d; bWaitAll
0x18006fc0f  mov     [rbp+Handles], rdi
0x18006fc13  mov     [rbp+Handles+8], rax
0x18006fc17  mov     [rsp+50h+bAlertable], r15d; bAlertable
0x18006fc1c  lea     ecx, [r8+2]; nCount
0x18006fc20  call    cs:__imp_WaitForMultipleObjectsEx
0x18006fc26  mov     [rbp+ExitCode], r15d
0x18006fc2a  mov     r14d, eax
0x18006fc2d  cmp     eax, r12d
0x18006fc30  jnz     loc_18006FD2B
0x18006fc36  mov     rcx, [rsi+18h]; hProcess
0x18006fc3a  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18006fc3e  call    cs:__imp_GetExitCodeProcess
0x18006fc44  test    bl, bl
0x18006fc46  jz      short loc_18006FCA4
0x18006fc48  mov     edx, [rsi+10h]; unsigned int
0x18006fc4b  call    ?ZeroPID@CActivationStateList@@QEAAXK@Z; CActivationStateList::ZeroPID(ulong)
0x18006fc50  lea     rcx, [rsi+58h]; lpCriticalSection
0x18006fc54  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x18006fc59  mov     rcx, [rsi+18h]; hObject
0x18006fc5d  call    cs:__imp_CloseHandle
0x18006fc63  lea     rcx, [rsi+58h]; this
0x18006fc67  mov     [rsi+18h], r15
0x18006fc6b  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x18006fc70  cmp     [rbp+ExitCode], 0C000026Bh
0x18006fc77  jz      loc_18006FE7B
0x18006fc7d  cmp     [rbp+ExitCode], 0C0000135h
0x18006fc84  jz      loc_18006FE7B
0x18006fc8a  mov     edx, cs:?gServerStartSecondChanceTimeout@@3KC; dwMilliseconds
0x18006fc90  mov     rcx, rdi; hHandle
0x18006fc93  call    cs:__imp_WaitForSingleObject
0x18006fc99  mov     r14d, eax
0x18006fc9c  test    eax, eax
0x18006fc9e  jz      loc_18006FF39
0x18006fca4  mov     rax, [rsi]
0x18006fca7  xor     ecx, ecx; string
0x18006fca9  mov     [rbp+string], r15
0x18006fcad  mov     rbx, [rax+20h]
0x18006fcb1  call    cs:__imp_WindowsDeleteString
0x18006fcb7  lea     rdx, [rbp+string]
0x18006fcbb  mov     [rbp+string], r15
0x18006fcbf  mov     rcx, rsi
0x18006fcc2  mov     rax, rbx
0x18006fcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcca  mov     eax, cs:dword_18014E4B8
0x18006fcd0  test    eax, eax
0x18006fcd2  jnz     short loc_18006FCE8
0x18006fcd4  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18006fcdb  jz      short loc_18006FD21
0x18006fcdd  xor     ecx, ecx
0x18006fcdf  call    IsWppLevelEnabled
0x18006fce4  test    al, al
0x18006fce6  jz      short loc_18006FD21
0x18006fce8  mov     rcx, [rbp+string]; string
0x18006fcec  xor     edx, edx; length
0x18006fcee  mov     ebx, [rbp+ExitCode]
0x18006fcf1  mov     edi, [rsi+10h]
0x18006fcf4  call    cs:__imp_WindowsGetStringRawBuffer
0x18006fcfa  mov     [rsp+50h+var_18], ebx
0x18006fcfe  xor     r9d, r9d
0x18006fd01  mov     [rsp+50h+var_20], edi
0x18006fd05  mov     r8d, 0C37h
0x18006fd0b  mov     [rsp+50h+var_28], rax
0x18006fd10  lea     rax, aWaitForLocalSe_0; "Wait for Local server: Server Process T"...
0x18006fd17  mov     qword ptr [rsp+50h+bAlertable], rax
0x18006fd1c  call    ??$ComTraceMessageT@PEBGKK@@YAXPEBD0HW4TraceLevel@@PEBG2KK@Z; ComTraceMessageT<ushort const *,ulong,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,ulong)
0x18006fd21  mov     rcx, [rbp+string]; string
0x18006fd25  call    cs:__imp_WindowsDeleteString
0x18006fd2b  test    r14d, r14d
0x18006fd2e  jz      loc_18006FF39
0x18006fd34  lea     rdi, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18006fd3b  cmp     [rsi+18h], r15
0x18006fd3f  jz      loc_18006FDDC
0x18006fd45  mov     rax, [rsi]
0x18006fd48  xor     ecx, ecx; string
0x18006fd4a  mov     [rbp+string], r15
0x18006fd4e  mov     rbx, [rax+20h]
0x18006fd52  call    cs:__imp_WindowsDeleteString
0x18006fd58  lea     rdx, [rbp+string]
0x18006fd5c  mov     [rbp+string], r15
0x18006fd60  mov     rcx, rsi
0x18006fd63  mov     rax, rbx
0x18006fd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd6b  mov     eax, cs:dword_18014E4B8
0x18006fd71  test    eax, eax
0x18006fd73  jnz     short loc_18006FD8A
0x18006fd75  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18006fd7c  jz      short loc_18006FDC6
0x18006fd7e  mov     ecx, r12d
0x18006fd81  call    IsWppLevelEnabled
0x18006fd86  test    al, al
0x18006fd88  jz      short loc_18006FDC6
0x18006fd8a  mov     rcx, [rbp+string]; string
0x18006fd8e  xor     edx, edx; length
0x18006fd90  mov     ebx, [rsi+10h]
0x18006fd93  call    cs:__imp_WindowsGetStringRawBuffer
0x18006fd99  mov     [rsp+50h+var_20], ebx
0x18006fd9d  lea     rdx, aCservertableen_2; "CServerTableEntry::WaitForLocalServer"
0x18006fda4  mov     [rsp+50h+var_28], rax
0x18006fda9  mov     r9d, r12d
0x18006fdac  lea     rax, aTerminatingSer_0; "Terminating server ClassIdentifier:%ws "...
0x18006fdb3  mov     r8d, 0C42h
0x18006fdb9  mov     rcx, rdi
0x18006fdbc  mov     qword ptr [rsp+50h+bAlertable], rax
0x18006fdc1  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18006fdc6  mov     rcx, [rsi+18h]; hProcess
0x18006fdca  xor     edx, edx; uExitCode
0x18006fdcc  call    cs:__imp_TerminateProcess
0x18006fdd2  mov     rcx, [rbp+string]; string
0x18006fdd6  call    cs:__imp_WindowsDeleteString
0x18006fddc  mov     rax, [rsi]
0x18006fddf  xor     ecx, ecx; string
0x18006fde1  mov     [rbp+string], r15
0x18006fde5  mov     rbx, [rax+20h]
0x18006fde9  call    cs:__imp_WindowsDeleteString
0x18006fdef  lea     rdx, [rbp+string]
0x18006fdf3  mov     [rbp+string], r15
0x18006fdf7  mov     rcx, rsi
0x18006fdfa  mov     rax, rbx
0x18006fdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe02  mov     eax, cs:dword_18014E4B8
0x18006fe08  test    eax, eax
0x18006fe0a  jnz     short loc_18006FE21
0x18006fe0c  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18006fe13  jz      short loc_18006FE5D
0x18006fe15  mov     ecx, r12d
0x18006fe18  call    IsWppLevelEnabled
0x18006fe1d  test    al, al
0x18006fe1f  jz      short loc_18006FE5D
0x18006fe21  mov     rcx, [rbp+string]; string
0x18006fe25  xor     edx, edx; length
0x18006fe27  mov     ebx, [rsi+10h]
0x18006fe2a  call    cs:__imp_WindowsGetStringRawBuffer
0x18006fe30  mov     [rsp+50h+var_20], ebx
0x18006fe34  lea     rdx, aCservertableen_2; "CServerTableEntry::WaitForLocalServer"
0x18006fe3b  mov     [rsp+50h+var_28], rax
0x18006fe40  mov     r9d, r12d
0x18006fe43  lea     rax, aWaitForLocalSe; "Wait for Local server timed out ClassId"...
0x18006fe4a  mov     r8d, 0C4Eh
0x18006fe50  mov     rcx, rdi
0x18006fe53  mov     qword ptr [rsp+50h+bAlertable], rax
0x18006fe58  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18006fe5d  mov     r9d, [rbp+ExitCode]
0x18006fe61  mov     r8, rdi
0x18006fe64  mov     rcx, [rbp+28h]
0x18006fe68  test    r9d, r9d
0x18006fe6b  jz      loc_18006FF2C
0x18006fe71  mov     edx, 0C52h
0x18006fe76  jmp     loc_18006FF12
0x18006fe7b  mov     rax, [rsi]
0x18006fe7e  xor     ecx, ecx; string
0x18006fe80  mov     [rbp+string], r15
0x18006fe84  mov     rbx, [rax+20h]
0x18006fe88  call    cs:__imp_WindowsDeleteString
0x18006fe8e  lea     rdx, [rbp+string]
0x18006fe92  mov     [rbp+string], r15
0x18006fe96  mov     rcx, rsi
0x18006fe99  mov     rax, rbx
0x18006fe9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fea1  mov     eax, cs:dword_18014E4B8
0x18006fea7  test    eax, eax
0x18006fea9  jnz     short loc_18006FEC0
0x18006feab  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18006feb2  jz      short loc_18006FEF9
0x18006feb4  mov     ecx, r12d
0x18006feb7  call    IsWppLevelEnabled
0x18006febc  test    al, al
0x18006febe  jz      short loc_18006FEF9
0x18006fec0  mov     rcx, [rbp+string]; string
0x18006fec4  xor     edx, edx; length
0x18006fec6  mov     ebx, [rbp+ExitCode]
0x18006fec9  mov     edi, [rsi+10h]
0x18006fecc  call    cs:__imp_WindowsGetStringRawBuffer
0x18006fed2  mov     [rsp+50h+var_18], ebx
0x18006fed6  mov     r9d, r12d
0x18006fed9  mov     [rsp+50h+var_20], edi
0x18006fedd  mov     r8d, 0C26h
0x18006fee3  mov     [rsp+50h+var_28], rax
0x18006fee8  lea     rax, aWaitForLocalSe_1; "Wait for Local server ClassIdentifier:%"...
0x18006feef  mov     qword ptr [rsp+50h+bAlertable], rax; unsigned int
0x18006fef4  call    ??$ComTraceMessageT@PEBGKK@@YAXPEBD0HW4TraceLevel@@PEBG2KK@Z; ComTraceMessageT<ushort const *,ulong,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,ulong)
0x18006fef9  mov     r9d, [rbp+ExitCode]; char *
0x18006fefd  test    r9d, r9d
0x18006ff00  jz      short loc_18006FF1B
0x18006ff02  mov     rcx, [rbp+28h]; this
0x18006ff06  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18006ff0d  mov     edx, 0C28h; void *
0x18006ff12  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006ff17  mov     ebx, eax
0x18006ff19  jmp     short loc_18006FF1E
0x18006ff1b  mov     ebx, r15d
0x18006ff1e  mov     rcx, [rbp+string]; string
0x18006ff22  call    cs:__imp_WindowsDeleteString
0x18006ff28  mov     eax, ebx
0x18006ff2a  jmp     short loc_18006FF3B
0x18006ff2c  mov     r9d, 5B4h
0x18006ff32  mov     edx, 0C54h
0x18006ff37  jmp     short loc_18006FF12
0x18006ff39  xor     eax, eax
0x18006ff3b  lea     r11, [rsp+50h+var_s0]
0x18006ff40  mov     rbx, [r11+38h]
0x18006ff44  mov     rsi, [r11+40h]
0x18006ff48  mov     rsp, r11
0x18006ff4b  pop     r15
0x18006ff4d  pop     r14
0x18006ff4f  pop     r12
0x18006ff51  pop     rdi
0x18006ff52  pop     rbp
0x18006ff53  retn
```
