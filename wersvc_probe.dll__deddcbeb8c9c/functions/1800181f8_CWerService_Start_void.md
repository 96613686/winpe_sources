# CWerService::Start(void)

- ea: `0x1800181f8`
- end: `0x1800186ee`
- name: `?Start@CWerService@@QEAAJXZ`
- size: `1270`
- prototype: `__int64 __fastcall(CWerService *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017e70`

## callees

- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x180013df4`
- `0x180016968`
- `0x1800181f8`
- `0x18001d7c0`
- `0x18001d92c`
- `0x18001df68`
- `0x18001e054`
- `0x18001e47c`
- `0x18002e09c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018304`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018304`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001827b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001860e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001827b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001860e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018622`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800186d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018622`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800186d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018322`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180018398`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180018398`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001837f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001837f`
- `ntdll!RtlInitUnicodeString` at `0x18001852e`
- `ntdll!RtlInitUnicodeString` at `0x18001852e`
- `ntdll!NtOpenEvent` at `0x18001856a`
- `ntdll!NtOpenEvent` at `0x18001856a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180018296`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180018296`

## string_xrefs

- `0x1800184b6`: `ServiceTimeout`
- `0x180018523`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::Start(CWerService *this)
{
  HANDLE v2; // rcx
  SERVICE_STATUS_HANDLE v3; // rax
  unsigned int v4; // r8d
  signed int LastError; // eax
  signed int v6; // ebx
  bool v7; // cc
  HANDLE EventW; // rax
  void *v9; // rcx
  __int64 v10; // r8
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  struct _TP_CLEANUP_GROUP *v12; // rcx
  __int64 v13; // rax
  signed int v14; // eax
  _DWORD *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // r9
  void **v18; // rax
  NTSTATUS v19; // eax
  int v20; // eax
  HANDLE *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  int started; // eax
  unsigned int v25; // r8d
  int v26; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  DWORD pcbData; // [rsp+D0h] [rbp+67h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  if ( !*((_QWORD *)this + 40) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  if ( *((_QWORD *)this + 41) != -1 && *((_QWORD *)this + 41) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  if ( *((_QWORD *)this + 38) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v3 = RegisterServiceCtrlHandlerExW(L"wersvc", CWerService::StaticServiceHandler, this);
  *((_QWORD *)this + 38) = v3;
  if ( !v3 )
    goto LABEL_11;
  v6 = CWerService::_SetServiceStatus(this, 2u, v4);
  if ( v6 < 0 )
    goto LABEL_16;
  EventW = CreateEventW(0, 1, 0, 0);
  v9 = (void *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = EventW;
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  v10 = *((_QWORD *)this + 41);
  if ( (unsigned __int64)(v10 + 1) <= 1 )
  {
LABEL_11:
    LastError = GetLastError();
    v6 = LastError;
    v7 = LastError <= 0;
LABEL_12:
    if ( !v7 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_16;
  }
  *((_QWORD *)this + 42) = 0;
  LastError = (*(__int64 (__fastcall **)(char *, const WCHAR *, __int64, void (__fastcall *)(LPCRITICAL_SECTION, unsigned __int8), CWerService *, int))(*((_QWORD *)this + 40) + 192LL))(
                (char *)this + 336,
                L"wersvc",
                v10,
                CWerService::StaticStopCallback,
                this,
                8);
  v6 = LastError;
  v7 = LastError <= 0;
  if ( LastError )
    goto LABEL_12;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  v12 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 28);
  *((_QWORD *)this + 28) = ThreadpoolCleanupGroup;
  if ( v12 )
    CloseThreadpoolCleanupGroup(v12);
  v13 = *((_QWORD *)this + 28);
  if ( !v13 )
  {
    v14 = GetLastError();
    v6 = v14;
    if ( v14 > 0 )
      v6 = (unsigned __int16)v14 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v6);
    goto LABEL_16;
  }
  *((_DWORD *)this + 58) = 3;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_DWORD *)this + 73) = 1;
  *((_DWORD *)this + 74) = 72;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = v13;
  *((_QWORD *)this + 32) = 0;
  pcbData = 0;
  if ( (int)CWerService::QueryServiceStartType(v12, &pcbData) >= 0 && pcbData == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    *((_DWORD *)this + 54) = -1;
  }
  else
  {
    pcbData = 4;
    v15 = (_DWORD *)((char *)this + 216);
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\Windows Error Reporting",
           L"ServiceTimeout",
           0x18u,
           0,
           (char *)this + 216,
           &pcbData)
      || pcbData != 4
      || (v17 = (unsigned int)*v15, (unsigned int)v17 < 0xEA60) )
    {
      *v15 = 60000;
      v17 = 60000;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v16, v17);
  }
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\SystemErrorPortReady");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v18 = (void **)tlx::replace<tlx::file_handle_traits>((char *)this + 344);
  v19 = NtOpenEvent(v18, 2u, &ObjectAttributes);
  if ( v19 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      v19 | 0x10000000u);
  v20 = CHandleMonitor::Initialize((CWerService *)((char *)this + 80));
  v6 = v20;
  if ( v20 < 0 )
  {
    v21 = (HANDLE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        161,
        &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v20);
      v21 = (HANDLE *)WPP_GLOBAL_Control;
    }
    if ( v21 == &WPP_GLOBAL_Control || (*((_BYTE *)v21 + 28) & 1) == 0 )
      goto LABEL_16;
    v22 = 47;
    v23 = (unsigned int)v6;
    goto LABEL_58;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_DWORD *)this + 33) = 4;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  started = CWerService::_StartWork(this);
  v6 = started;
  if ( started < 0 )
  {
    v21 = (HANDLE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 48;
      v23 = (unsigned int)started;
LABEL_58:
      WPP_SF_d(v21[2], v22, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v23);
    }
LABEL_16:
    if ( *((_QWORD *)this + 42) )
    {
      CWerService::_SignalStop(this);
    }
    else
    {
      v26 = CWerService::_Stop(this);
      if ( v26 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          (unsigned int)v26);
    }
    goto LABEL_72;
  }
  v6 = CWerService::_SetServiceStatus(this, 4u, v25);
  if ( v6 < 0 )
    goto LABEL_16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  v6 = 0;
LABEL_72:
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800181f8  push    rbp
0x1800181fa  push    rbx
0x1800181fb  push    rsi
0x1800181fc  push    rdi
0x1800181fd  push    r12
0x1800181ff  push    r15
0x180018201  lea     rbp, [rsp-2Fh]
0x180018206  sub     rsp, 98h
0x18001820d  mov     rdi, rcx
0x180018210  lea     r15, WPP_GLOBAL_Control
0x180018217  lea     r12, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001821e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018225  cmp     rcx, r15
0x180018228  jz      short loc_180018241
0x18001822a  test    byte ptr [rcx+1Ch], 4
0x18001822e  jz      short loc_180018241
0x180018230  mov     edx, 29h ; ')'
0x180018235  mov     r8, r12
0x180018238  mov     rcx, [rcx+10h]
0x18001823c  call    WPP_SF_
0x180018241  xor     esi, esi
0x180018243  cmp     [rdi+140h], rsi
0x18001824a  jnz     short loc_180018251
0x18001824c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018251  mov     rax, [rdi+148h]
0x180018258  inc     rax
0x18001825b  cmp     rax, 1
0x18001825f  jbe     short loc_180018266
0x180018261  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018266  cmp     [rdi+130h], rsi
0x18001826d  jz      short loc_180018274
0x18001826f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018274  mov     [rbp+57h+lpCriticalSection], rdi
0x180018278  mov     rcx, rdi; lpCriticalSection
0x18001827b  call    cs:__imp_EnterCriticalSection
0x180018281  mov     [rbp+57h+var_78], 1
0x180018285  mov     r8, rdi; lpContext
0x180018288  lea     rdx, ?StaticServiceHandler@CWerService@@CAKKKPEAX0@Z; lpHandlerProc
0x18001828f  lea     rcx, aWersvc_0; "wersvc"
0x180018296  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001829c  mov     [rdi+130h], rax
0x1800182a3  test    rax, rax
0x1800182a6  jnz     short loc_1800182E5
0x1800182a8  call    cs:__imp_GetLastError
0x1800182ae  mov     ebx, eax
0x1800182b0  test    eax, eax
0x1800182b2  jle     short loc_1800182BD
0x1800182b4  movzx   ebx, ax
0x1800182b7  or      ebx, 80070000h
0x1800182bd  mov     eax, 80004005h
0x1800182c2  test    ebx, ebx
0x1800182c4  cmovns  ebx, eax
0x1800182c7  lea     rdx, [rbp+57h+lpCriticalSection]
0x1800182cb  mov     rcx, rdi; this
0x1800182ce  cmp     [rdi+150h], rsi
0x1800182d5  jz      loc_18001869C
0x1800182db  call    ?_SignalStop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_SignalStop(utl::unique_lock<utl::recursive_mutex> &)
0x1800182e0  jmp     loc_1800186CC
0x1800182e5  mov     edx, 2; unsigned int
0x1800182ea  mov     rcx, rdi; this
0x1800182ed  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x1800182f2  mov     ebx, eax
0x1800182f4  test    eax, eax
0x1800182f6  js      short loc_1800182C7
0x1800182f8  xor     r9d, r9d; lpName
0x1800182fb  xor     r8d, r8d; bInitialState
0x1800182fe  lea     edx, [r9+1]; bManualReset
0x180018302  xor     ecx, ecx; lpEventAttributes
0x180018304  call    cs:__imp_CreateEventW
0x18001830a  mov     rcx, [rdi+148h]; hObject
0x180018311  mov     [rdi+148h], rax
0x180018318  lea     rax, [rcx+1]
0x18001831c  cmp     rax, 1
0x180018320  jbe     short loc_180018328
0x180018322  call    cs:__imp_CloseHandle
0x180018328  mov     r8, [rdi+148h]
0x18001832f  lea     rax, [r8+1]
0x180018333  cmp     rax, 1
0x180018337  jbe     loc_1800182A8
0x18001833d  lea     rcx, [rdi+150h]
0x180018344  mov     [rcx], rsi
0x180018347  mov     rax, [rdi+140h]
0x18001834e  mov     dword ptr [rsp+0C0h+pvData], 8
0x180018356  mov     [rsp+0C0h+pdwType], rdi
0x18001835b  lea     r9, ?StaticStopCallback@CWerService@@CAXPEAXE@Z; CWerService::StaticStopCallback(void *,uchar)
0x180018362  lea     rdx, aWersvc_0; "wersvc"
0x180018369  mov     rax, [rax+0C0h]
0x180018370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018375  mov     ebx, eax
0x180018377  test    eax, eax
0x180018379  jnz     loc_1800182B2
0x18001837f  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180018385  mov     rcx, [rdi+0E0h]; ptpcg
0x18001838c  mov     [rdi+0E0h], rax
0x180018393  test    rcx, rcx
0x180018396  jz      short loc_18001839E
0x180018398  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001839e  mov     rax, [rdi+0E0h]
0x1800183a5  test    rax, rax
0x1800183a8  jnz     short loc_1800183FC
0x1800183aa  call    cs:__imp_GetLastError
0x1800183b0  mov     ebx, eax
0x1800183b2  test    eax, eax
0x1800183b4  jle     short loc_1800183BF
0x1800183b6  movzx   ebx, ax
0x1800183b9  or      ebx, 80070000h
0x1800183bf  mov     eax, 80004005h
0x1800183c4  test    ebx, ebx
0x1800183c6  cmovns  ebx, eax
0x1800183c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183d0  cmp     rcx, r15
0x1800183d3  jz      short loc_1800183EF
0x1800183d5  test    byte ptr [rcx+1Ch], 1
0x1800183d9  jz      short loc_1800183EF
0x1800183db  mov     edx, 2Ah ; '*'
0x1800183e0  mov     r9d, ebx
0x1800183e3  mov     r8, r12
0x1800183e6  mov     rcx, [rcx+10h]
0x1800183ea  call    WPP_SF_d
0x1800183ef  test    ebx, ebx
0x1800183f1  jns     loc_1800186CC
0x1800183f7  jmp     loc_1800182C7
0x1800183fc  mov     dword ptr [rdi+0E8h], 3
0x180018406  mov     [rdi+108h], rsi
0x18001840d  mov     [rdi+110h], rsi
0x180018414  mov     [rdi+118h], rsi
0x18001841b  mov     [rdi+120h], esi
0x180018421  mov     dword ptr [rdi+124h], 1
0x18001842b  mov     dword ptr [rdi+128h], 48h ; 'H'
0x180018435  mov     [rdi+0F0h], rsi
0x18001843c  mov     [rdi+0F8h], rax
0x180018443  mov     [rdi+100h], rsi
0x18001844a  mov     [rbp+57h+arg_0], esi
0x18001844d  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x180018451  call    ?QueryServiceStartType@CWerService@@AEAAJPEAK@Z; CWerService::QueryServiceStartType(ulong *)
0x180018456  test    eax, eax
0x180018458  js      short loc_18001848F
0x18001845a  cmp     [rbp+57h+arg_0], 2
0x18001845e  jnz     short loc_18001848F
0x180018460  mov     rcx, cs:WPP_GLOBAL_Control
0x180018467  cmp     rcx, r15
0x18001846a  jz      short loc_180018483
0x18001846c  test    byte ptr [rcx+1Ch], 8
0x180018470  jz      short loc_180018483
0x180018472  mov     edx, 2Ch ; ','
0x180018477  mov     r8, r12
0x18001847a  mov     rcx, [rcx+10h]
0x18001847e  call    WPP_SF_
0x180018483  mov     dword ptr [rdi+0D8h], 0FFFFFFFFh
0x18001848d  jmp     short loc_18001850D
0x18001848f  mov     [rbp+57h+arg_0], 4
0x180018496  lea     rbx, [rdi+0D8h]
0x18001849d  lea     rax, [rbp+57h+arg_0]
0x1800184a1  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800184a6  mov     [rsp+0C0h+pvData], rbx; pvData
0x1800184ab  mov     [rsp+0C0h+pdwType], rsi; pdwType
0x1800184b0  mov     r9d, 18h; dwFlags
0x1800184b6  lea     r8, aServicetimeout; "ServiceTimeout"
0x1800184bd  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\Windows E"...
0x1800184c4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800184cb  call    cs:__imp_RegGetValueW
0x1800184d1  mov     ecx, 0EA60h
0x1800184d6  test    eax, eax
0x1800184d8  jnz     short loc_1800184E8
0x1800184da  cmp     [rbp+57h+arg_0], 4
0x1800184de  jnz     short loc_1800184E8
0x1800184e0  mov     r9d, [rbx]
0x1800184e3  cmp     r9d, ecx
0x1800184e6  jnb     short loc_1800184ED
0x1800184e8  mov     [rbx], ecx
0x1800184ea  mov     r9d, ecx
0x1800184ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184f4  cmp     rcx, r15
0x1800184f7  jz      short loc_18001850D
0x1800184f9  test    byte ptr [rcx+1Ch], 8
0x1800184fd  jz      short loc_18001850D
0x1800184ff  mov     edx, 2Dh ; '-'
0x180018504  mov     rcx, [rcx+10h]
0x180018508  call    WPP_SF_L
0x18001850d  xorps   xmm0, xmm0
0x180018510  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180018514  xorps   xmm1, xmm1
0x180018517  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001851b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18001851f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180018523  lea     rdx, SourceString; "\\KernelObjects\\SystemErrorPortReady"
0x18001852a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001852e  call    cs:__imp_RtlInitUnicodeString
0x180018534  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001853b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18001853f  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180018542  lea     rax, [rbp+57h+DestinationString]
0x180018546  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001854a  xorps   xmm0, xmm0
0x18001854d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018552  lea     rcx, [rdi+158h]
0x180018559  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001855e  mov     rcx, rax; EventHandle
0x180018561  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180018565  mov     edx, 2; DesiredAccess
0x18001856a  call    cs:__imp_NtOpenEvent
0x180018570  test    eax, eax
0x180018572  jns     short loc_18001859E
0x180018574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001857b  cmp     rcx, r15
0x18001857e  jz      short loc_18001859E
0x180018580  test    byte ptr [rcx+1Ch], 2
0x180018584  jz      short loc_18001859E
0x180018586  bts     eax, 1Ch
0x18001858a  mov     edx, 2Eh ; '.'
0x18001858f  mov     r9d, eax
0x180018592  mov     r8, r12
0x180018595  mov     rcx, [rcx+10h]
0x180018599  call    WPP_SF_d
0x18001859e  lea     rcx, [rdi+50h]; this
0x1800185a2  call    ?Initialize@CHandleMonitor@@QEAAJXZ; CHandleMonitor::Initialize(void)
0x1800185a7  mov     ebx, eax
0x1800185a9  test    eax, eax
0x1800185ab  jns     short loc_18001860A
0x1800185ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185b4  cmp     rcx, r15
0x1800185b7  jz      loc_1800182C7
0x1800185bd  test    byte ptr [rcx+1Ch], 1
0x1800185c1  jz      short loc_1800185DE
0x1800185c3  mov     edx, 0A1h
0x1800185c8  mov     r9d, eax
0x1800185cb  mov     r8, r12
0x1800185ce  mov     rcx, [rcx+10h]
0x1800185d2  call    WPP_SF_d
0x1800185d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185de  cmp     rcx, r15
0x1800185e1  jz      loc_1800182C7
0x1800185e7  test    byte ptr [rcx+1Ch], 1
0x1800185eb  jz      loc_1800182C7
0x1800185f1  mov     edx, 2Fh ; '/'
0x1800185f6  mov     r9d, ebx
0x1800185f9  mov     r8, r12
0x1800185fc  mov     rcx, [rcx+10h]
0x180018600  call    WPP_SF_d
0x180018605  jmp     loc_1800182C7
0x18001860a  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001860e  call    cs:__imp_EnterCriticalSection
0x180018614  mov     dword ptr [rdi+84h], 4
0x18001861e  lea     rcx, [rdi+58h]; lpCriticalSection
0x180018622  call    cs:__imp_LeaveCriticalSection
0x180018628  lea     rdx, [rbp+57h+lpCriticalSection]
0x18001862c  mov     rcx, rdi; this
0x18001862f  call    ?_StartWork@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_StartWork(utl::unique_lock<utl::recursive_mutex> &)
0x180018634  mov     ebx, eax
0x180018636  test    eax, eax
0x180018638  jns     short loc_18001865E
0x18001863a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018641  cmp     rcx, r15
0x180018644  jz      loc_1800182C7
0x18001864a  test    byte ptr [rcx+1Ch], 1
0x18001864e  jz      loc_1800182C7
0x180018654  mov     edx, 30h ; '0'
0x180018659  mov     r9d, eax
0x18001865c  jmp     short loc_1800185F9
0x18001865e  mov     edx, 4; unsigned int
0x180018663  mov     rcx, rdi; this
0x180018666  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x18001866b  mov     ebx, eax
0x18001866d  test    eax, eax
0x18001866f  js      loc_1800182C7
0x180018675  mov     rcx, cs:WPP_GLOBAL_Control
0x18001867c  cmp     rcx, r15
0x18001867f  jz      short loc_180018698
0x180018681  test    byte ptr [rcx+1Ch], 4
0x180018685  jz      short loc_180018698
0x180018687  mov     edx, 31h ; '1'
0x18001868c  mov     r8, r12
0x18001868f  mov     rcx, [rcx+10h]
0x180018693  call    WPP_SF_
0x180018698  mov     ebx, esi
0x18001869a  jmp     short loc_1800186CC
0x18001869c  call    ?_Stop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_Stop(utl::unique_lock<utl::recursive_mutex> &)
0x1800186a1  test    eax, eax
0x1800186a3  jns     short loc_1800186CC
0x1800186a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186ac  cmp     rcx, r15
0x1800186af  jz      short loc_1800186CC
0x1800186b1  test    byte ptr [rcx+1Ch], 1
0x1800186b5  jz      short loc_1800186CC
0x1800186b7  mov     edx, 32h ; '2'
0x1800186bc  mov     r9d, eax
0x1800186bf  mov     r8, r12
0x1800186c2  mov     rcx, [rcx+10h]
0x1800186c6  call    WPP_SF_d
0x1800186cb  nop
0x1800186cc  cmp     [rbp+57h+var_78], sil
0x1800186d0  jz      short loc_1800186DC
0x1800186d2  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800186d6  call    cs:__imp_LeaveCriticalSection
0x1800186dc  mov     eax, ebx
0x1800186de  add     rsp, 98h
0x1800186e5  pop     r15
0x1800186e7  pop     r12
0x1800186e9  pop     rdi
0x1800186ea  pop     rsi
  ... truncated ...
```
