# CServerTableEntry::WaitForLocalServer(void *,CClassData *,int)

- ea: `0x180074428`
- end: `0x18007482d`
- name: `?WaitForLocalServer@CServerTableEntry@@QEAAJPEAXPEAVCClassData@@H@Z`
- size: `1029`
- prototype: `int(CServerTableEntry *__hidden this, void *, struct CClassData *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c680`

## callees

- `0x180025950`
- `0x180034260`
- `0x180034c74`
- `0x180046930`
- `0x180046994`
- `0x180074428`
- `0x1800855d8`
- `0x1800fbb04`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800744e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800744e1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18007467a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18007467a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800744bc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800744bc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180074498`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180074498`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007451d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007451d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800745c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800745f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007468a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800746a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007474e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800747f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800745c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800745f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007468a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800746a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007474e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800747f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007458a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007463b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800746ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007458a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007463b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800746ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074798`

## string_xrefs

- `0x1800745d6`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800747d8`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800747ba`: `Wait for Local server ClassIdentifier:%ws PID:%x encountered error: %x `
- `0x180074709`: `Wait for Local server timed out ClassIdentifier:%ws PID:%x`
- `0x18007465a`: `Terminating server ClassIdentifier:%ws PID:%x`
- `0x1800745ac`: `Wait for Local server: Server Process Terminated: ClassIdentifier:%ws PID:%x error: %x `

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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x180074428  mov     [rsp-28h+arg_8], rbx
0x18007442d  mov     [rsp-28h+arg_10], rsi
0x180074432  push    rbp
0x180074433  push    rdi
0x180074434  push    r12
0x180074436  push    r14
0x180074438  push    r15
0x18007443a  mov     rbp, rsp
0x18007443d  sub     rsp, 50h
0x180074441  xor     r15d, r15d
0x180074444  xorps   xmm0, xmm0
0x180074447  mov     rdi, rdx
0x18007444a  mov     rsi, rcx
0x18007444d  mov     bl, r15b
0x180074450  movups  xmmword ptr [rbp+Handles], xmm0
0x180074454  lea     r12d, [r15+1]
0x180074458  test    r9d, r9d
0x18007445b  jz      short loc_180074463
0x18007445d  or      r9d, 0FFFFFFFFh
0x180074461  jmp     short loc_18007447C
0x180074463  mov     r9d, cs:?gServerStartTimeout@@3KC; dwMilliseconds
0x18007446a  mov     rax, [r8+60h]
0x18007446e  test    rax, rax
0x180074471  jz      short loc_180074479
0x180074473  cmp     [rax+18h], r15
0x180074477  jnz     short loc_18007447C
0x180074479  mov     bl, r12b
0x18007447c  mov     rax, [rcx+18h]
0x180074480  lea     rdx, [rbp+Handles]; lpHandles
0x180074484  xor     r8d, r8d; bWaitAll
0x180074487  mov     [rbp+Handles], rdi
0x18007448b  mov     [rbp+Handles+8], rax
0x18007448f  mov     [rsp+50h+bAlertable], r15d; bAlertable
0x180074494  lea     ecx, [r8+2]; nCount
0x180074498  call    cs:__imp_WaitForMultipleObjectsEx
0x18007449f  nop     dword ptr [rax+rax+00h]
0x1800744a4  mov     [rbp+ExitCode], r15d
0x1800744a8  mov     r14d, eax
0x1800744ab  cmp     eax, r12d
0x1800744ae  jnz     loc_1800745CD
0x1800744b4  mov     rcx, [rsi+18h]; hProcess
0x1800744b8  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800744bc  call    cs:__imp_GetExitCodeProcess
0x1800744c3  nop     dword ptr [rax+rax+00h]
0x1800744c8  test    bl, bl
0x1800744ca  jz      short loc_180074534
0x1800744cc  mov     edx, [rsi+10h]; unsigned int
0x1800744cf  call    ?ZeroPID@CActivationStateList@@QEAAXK@Z; CActivationStateList::ZeroPID(ulong)
0x1800744d4  lea     rcx, [rsi+58h]; lpCriticalSection
0x1800744d8  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x1800744dd  mov     rcx, [rsi+18h]; hObject
0x1800744e1  call    cs:__imp_CloseHandle
0x1800744e8  nop     dword ptr [rax+rax+00h]
0x1800744ed  lea     rcx, [rsi+58h]; this
0x1800744f1  mov     [rsi+18h], r15
0x1800744f5  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x1800744fa  cmp     [rbp+ExitCode], 0C000026Bh
0x180074501  jz      loc_180074741
0x180074507  cmp     [rbp+ExitCode], 0C0000135h
0x18007450e  jz      loc_180074741
0x180074514  mov     edx, cs:?gServerStartSecondChanceTimeout@@3KC; dwMilliseconds
0x18007451a  mov     rcx, rdi; hHandle
0x18007451d  call    cs:__imp_WaitForSingleObject
0x180074524  nop     dword ptr [rax+rax+00h]
0x180074529  mov     r14d, eax
0x18007452c  test    eax, eax
0x18007452e  jz      loc_180074811
0x180074534  mov     rax, [rsi]
0x180074537  xor     ecx, ecx; string
0x180074539  mov     [rbp+string], r15
0x18007453d  mov     rbx, [rax+20h]
0x180074541  call    cs:__imp_WindowsDeleteString
0x180074548  nop     dword ptr [rax+rax+00h]
0x18007454d  lea     rdx, [rbp+string]
0x180074551  mov     [rbp+string], r15
0x180074555  mov     rcx, rsi
0x180074558  mov     rax, rbx
0x18007455b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074560  mov     eax, cs:dword_1801574B8
0x180074566  test    eax, eax
0x180074568  jnz     short loc_18007457E
0x18007456a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180074571  jz      short loc_1800745BD
0x180074573  xor     ecx, ecx
0x180074575  call    IsWppLevelEnabled
0x18007457a  test    al, al
0x18007457c  jz      short loc_1800745BD
0x18007457e  mov     rcx, [rbp+string]; string
0x180074582  xor     edx, edx; length
0x180074584  mov     ebx, [rbp+ExitCode]
0x180074587  mov     edi, [rsi+10h]
0x18007458a  call    cs:__imp_WindowsGetStringRawBuffer
0x180074591  nop     dword ptr [rax+rax+00h]
0x180074596  mov     [rsp+50h+var_18], ebx
0x18007459a  xor     r9d, r9d
0x18007459d  mov     [rsp+50h+var_20], edi
0x1800745a1  mov     r8d, 0C37h
0x1800745a7  mov     [rsp+50h+var_28], rax
0x1800745ac  lea     rax, aWaitForLocalSe_0; "Wait for Local server: Server Process T"...
0x1800745b3  mov     qword ptr [rsp+50h+bAlertable], rax
0x1800745b8  call    ??$ComTraceMessageT@PEBGKK@@YAXPEBD0HW4TraceLevel@@PEBG2KK@Z; ComTraceMessageT<ushort const *,ulong,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,ulong)
0x1800745bd  mov     rcx, [rbp+string]; string
0x1800745c1  call    cs:__imp_WindowsDeleteString
0x1800745c8  nop     dword ptr [rax+rax+00h]
0x1800745cd  test    r14d, r14d
0x1800745d0  jz      loc_180074811
0x1800745d6  lea     rdi, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800745dd  cmp     [rsi+18h], r15
0x1800745e1  jz      loc_180074696
0x1800745e7  mov     rax, [rsi]
0x1800745ea  xor     ecx, ecx; string
0x1800745ec  mov     [rbp+string], r15
0x1800745f0  mov     rbx, [rax+20h]
0x1800745f4  call    cs:__imp_WindowsDeleteString
0x1800745fb  nop     dword ptr [rax+rax+00h]
0x180074600  lea     rdx, [rbp+string]
0x180074604  mov     [rbp+string], r15
0x180074608  mov     rcx, rsi
0x18007460b  mov     rax, rbx
0x18007460e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074613  mov     eax, cs:dword_1801574B8
0x180074619  test    eax, eax
0x18007461b  jnz     short loc_180074632
0x18007461d  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180074624  jz      short loc_180074674
0x180074626  mov     ecx, r12d
0x180074629  call    IsWppLevelEnabled
0x18007462e  test    al, al
0x180074630  jz      short loc_180074674
0x180074632  mov     rcx, [rbp+string]; string
0x180074636  xor     edx, edx; length
0x180074638  mov     ebx, [rsi+10h]
0x18007463b  call    cs:__imp_WindowsGetStringRawBuffer
0x180074642  nop     dword ptr [rax+rax+00h]
0x180074647  mov     [rsp+50h+var_20], ebx
0x18007464b  lea     rdx, aCservertableen_2; "CServerTableEntry::WaitForLocalServer"
0x180074652  mov     [rsp+50h+var_28], rax
0x180074657  mov     r9d, r12d
0x18007465a  lea     rax, aTerminatingSer_0; "Terminating server ClassIdentifier:%ws "...
0x180074661  mov     r8d, 0C42h
0x180074667  mov     rcx, rdi
0x18007466a  mov     qword ptr [rsp+50h+bAlertable], rax
0x18007466f  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180074674  mov     rcx, [rsi+18h]; hProcess
0x180074678  xor     edx, edx; uExitCode
0x18007467a  call    cs:__imp_TerminateProcess
0x180074681  nop     dword ptr [rax+rax+00h]
0x180074686  mov     rcx, [rbp+string]; string
0x18007468a  call    cs:__imp_WindowsDeleteString
0x180074691  nop     dword ptr [rax+rax+00h]
0x180074696  mov     rax, [rsi]
0x180074699  xor     ecx, ecx; string
0x18007469b  mov     [rbp+string], r15
0x18007469f  mov     rbx, [rax+20h]
0x1800746a3  call    cs:__imp_WindowsDeleteString
0x1800746aa  nop     dword ptr [rax+rax+00h]
0x1800746af  lea     rdx, [rbp+string]
0x1800746b3  mov     [rbp+string], r15
0x1800746b7  mov     rcx, rsi
0x1800746ba  mov     rax, rbx
0x1800746bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800746c2  mov     eax, cs:dword_1801574B8
0x1800746c8  test    eax, eax
0x1800746ca  jnz     short loc_1800746E1
0x1800746cc  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800746d3  jz      short loc_180074723
0x1800746d5  mov     ecx, r12d
0x1800746d8  call    IsWppLevelEnabled
0x1800746dd  test    al, al
0x1800746df  jz      short loc_180074723
0x1800746e1  mov     rcx, [rbp+string]; string
0x1800746e5  xor     edx, edx; length
0x1800746e7  mov     ebx, [rsi+10h]
0x1800746ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800746f1  nop     dword ptr [rax+rax+00h]
0x1800746f6  mov     [rsp+50h+var_20], ebx
0x1800746fa  lea     rdx, aCservertableen_2; "CServerTableEntry::WaitForLocalServer"
0x180074701  mov     [rsp+50h+var_28], rax
0x180074706  mov     r9d, r12d
0x180074709  lea     rax, aWaitForLocalSe; "Wait for Local server timed out ClassId"...
0x180074710  mov     r8d, 0C4Eh
0x180074716  mov     rcx, rdi
0x180074719  mov     qword ptr [rsp+50h+bAlertable], rax
0x18007471e  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180074723  mov     r9d, [rbp+ExitCode]
0x180074727  mov     r8, rdi
0x18007472a  mov     rcx, [rbp+28h]
0x18007472e  test    r9d, r9d
0x180074731  jz      loc_180074804
0x180074737  mov     edx, 0C52h
0x18007473c  jmp     loc_1800747E4
0x180074741  mov     rax, [rsi]
0x180074744  xor     ecx, ecx; string
0x180074746  mov     [rbp+string], r15
0x18007474a  mov     rbx, [rax+20h]
0x18007474e  call    cs:__imp_WindowsDeleteString
0x180074755  nop     dword ptr [rax+rax+00h]
0x18007475a  lea     rdx, [rbp+string]
0x18007475e  mov     [rbp+string], r15
0x180074762  mov     rcx, rsi
0x180074765  mov     rax, rbx
0x180074768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007476d  mov     eax, cs:dword_1801574B8
0x180074773  test    eax, eax
0x180074775  jnz     short loc_18007478C
0x180074777  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18007477e  jz      short loc_1800747CB
0x180074780  mov     ecx, r12d
0x180074783  call    IsWppLevelEnabled
0x180074788  test    al, al
0x18007478a  jz      short loc_1800747CB
0x18007478c  mov     rcx, [rbp+string]; string
0x180074790  xor     edx, edx; length
0x180074792  mov     ebx, [rbp+ExitCode]
0x180074795  mov     edi, [rsi+10h]
0x180074798  call    cs:__imp_WindowsGetStringRawBuffer
0x18007479f  nop     dword ptr [rax+rax+00h]
0x1800747a4  mov     [rsp+50h+var_18], ebx
0x1800747a8  mov     r9d, r12d
0x1800747ab  mov     [rsp+50h+var_20], edi
0x1800747af  mov     r8d, 0C26h
0x1800747b5  mov     [rsp+50h+var_28], rax
0x1800747ba  lea     rax, aWaitForLocalSe_1; "Wait for Local server ClassIdentifier:%"...
0x1800747c1  mov     qword ptr [rsp+50h+bAlertable], rax; unsigned int
0x1800747c6  call    ??$ComTraceMessageT@PEBGKK@@YAXPEBD0HW4TraceLevel@@PEBG2KK@Z; ComTraceMessageT<ushort const *,ulong,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,ulong)
0x1800747cb  mov     r9d, [rbp+ExitCode]; char *
0x1800747cf  test    r9d, r9d
0x1800747d2  jz      short loc_1800747ED
0x1800747d4  mov     rcx, [rbp+28h]; this
0x1800747d8  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800747df  mov     edx, 0C28h; void *
0x1800747e4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800747e9  mov     ebx, eax
0x1800747eb  jmp     short loc_1800747F0
0x1800747ed  mov     ebx, r15d
0x1800747f0  mov     rcx, [rbp+string]; string
0x1800747f4  call    cs:__imp_WindowsDeleteString
0x1800747fb  nop     dword ptr [rax+rax+00h]
0x180074800  mov     eax, ebx
0x180074802  jmp     short loc_180074813
0x180074804  mov     r9d, 5B4h
0x18007480a  mov     edx, 0C54h
0x18007480f  jmp     short loc_1800747E4
0x180074811  xor     eax, eax
0x180074813  lea     r11, [rsp+50h+var_s0]
0x180074818  mov     rbx, [r11+38h]
0x18007481c  mov     rsi, [r11+40h]
0x180074820  mov     rsp, r11
0x180074823  pop     r15
0x180074825  pop     r14
0x180074827  pop     r12
0x180074829  pop     rdi
0x18007482a  pop     rbp
0x18007482b  retn
```
