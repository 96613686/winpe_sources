# xxxCheckProcessAndSessionState(_W32PROCESS *)

- ea: `0x140090df8`
- end: `0x1400911dc`
- name: `?xxxCheckProcessAndSessionState@@YAJPEAU_W32PROCESS@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct _W32PROCESS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14014c4ec`

## callees

- `0x14001bdf0`
- `0x140033364`
- `0x140074bf0`
- `0x140078090`
- `0x140090df8`
- `0x140092f1c`
- `0x140092f54`
- `0x140157378`
- `0x14018b0b8`
- `0x1401a9f9c`
- `0x140238240`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140090fcc`
- `ntoskrnl!ZwClose` at `0x140090fcc`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400910ba`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400910ba`
- `ntoskrnl!PsGetProcessId` at `0x1400911ae`
- `ntoskrnl!PsGetProcessId` at `0x1400911ae`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140090ee9`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140090ee9`
- `ntoskrnl!ZwOpenProcess` at `0x140090f35`
- `ntoskrnl!ZwOpenProcess` at `0x140090f35`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140090f62`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140090f62`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140090e6f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140090f74`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140090f9c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009100e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140090e6f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140090f74`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140090f9c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009100e`
- `WIN32K!W32GetUserGdiSessionState` at `0x140090e29`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009115a`
- `WIN32K!W32GetUserGdiSessionState` at `0x140091183`
- `WIN32K!W32GetUserGdiSessionState` at `0x140090e29`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009115a`
- `WIN32K!W32GetUserGdiSessionState` at `0x140091183`
- `WIN32K!W32GetUserSessionState` at `0x140090e3f`
- `WIN32K!W32GetUserSessionState` at `0x140090e54`
- `WIN32K!W32GetUserSessionState` at `0x140091047`
- `WIN32K!W32GetUserSessionState` at `0x140091062`
- `WIN32K!W32GetUserSessionState` at `0x14009116d`
- `WIN32K!W32GetUserSessionState` at `0x140091198`
- `WIN32K!W32GetUserSessionState` at `0x140090e3f`
- `WIN32K!W32GetUserSessionState` at `0x140090e54`
- `WIN32K!W32GetUserSessionState` at `0x140091047`
- `WIN32K!W32GetUserSessionState` at `0x140091062`
- `WIN32K!W32GetUserSessionState` at `0x14009116d`
- `WIN32K!W32GetUserSessionState` at `0x140091198`

## pseudocode

```c
__int64 __fastcall xxxCheckProcessAndSessionState(PEPROCESS *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // r15d
  __int64 v5; // rcx
  char v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 UserSessionState; // rbx
  int (*v10)(void); // rax
  NTSTATUS InformationProcess; // edi
  void *ProcessInheritedFromUniqueProcessId; // rax
  __int64 v13; // rcx
  int (*v14)(void); // rax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  unsigned int (__fastcall *v17)(_QWORD); // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 (*v20)(void); // rax
  int v21; // eax
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v27; // rax
  _QWORD *v28; // rsi
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  struct _KPROCESS *v34; // rcx
  HANDLE v35; // rbx
  _CLIENT_ID ClientId; // [rsp+30h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-49h] BYREF
  _DWORD ProcessInformation[28]; // [rsp+70h] [rbp-19h] BYREF
  void *ProcessHandle; // [rsp+F8h] [rbp+6Fh] BYREF

  if ( (int)IsGreIsCurrentProcessSystemCriticalSupported() >= 0 && (unsigned int)GreIsCurrentProcessSystemCritical() )
    return 0;
  v4 = 0;
  v6 = 1;
  if ( !*(_QWORD *)(W32GetUserGdiSessionState(v3, v2) + 40) )
    goto LABEL_10;
  if ( !*(_QWORD *)(W32GetUserSessionState(v5) + 63312) )
    goto LABEL_10;
  UserSessionState = W32GetUserSessionState(v7);
  if ( (*(_DWORD *)(UserSessionState + 68920) & 0x40000) == 0 )
    goto LABEL_10;
  v10 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v8) + 24) + 2576LL);
  if ( !v10 || v10() < 0 || (*(_DWORD *)(UserSessionState + 68920) & 0x10000000) != 0 )
    return 0;
  v4 = 1;
LABEL_10:
  InformationProcess = 0;
  if ( (unsigned int)IsCurrentSessionServiceSession() )
    goto LABEL_43;
  ProcessHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ClientId = 0;
  memset(ProcessInformation, 0, 0x40u);
  ProcessInheritedFromUniqueProcessId = (void *)PsGetProcessInheritedFromUniqueProcessId(*a1);
  if ( !ProcessInheritedFromUniqueProcessId )
    goto LABEL_43;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  ClientId.UniqueProcess = ProcessInheritedFromUniqueProcessId;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ClientId.UniqueThread = 0;
  InformationProcess = ZwOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  if ( InformationProcess >= 0 )
  {
    InformationProcess = ZwQueryInformationProcess(ProcessHandle, ProcessImageInformation, ProcessInformation, 0x40u, 0);
    if ( InformationProcess >= 0 )
    {
      v14 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v13) + 48) + 1672LL);
      if ( v14 )
      {
        if ( v14() >= 0 )
        {
          v16 = ProcessInformation[8];
          v17 = *(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v15) + 48) + 1680LL);
          if ( !v17 || !v17(v16) )
            InformationProcess = -1073741790;
        }
      }
    }
    ZwClose(ProcessHandle);
    if ( InformationProcess >= 0 )
      goto LABEL_43;
  }
  if ( InformationProcess == -1073741813 || InformationProcess == -1073741558 )
  {
    InformationProcess = 0;
LABEL_43:
    if ( (unsigned int)Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( !*(_QWORD *)(W32GetUserGdiSessionState(v30, v29) + 40)
        || !*(_QWORD *)(W32GetUserSessionState(v31) + 63312)
        || (v34 = *(struct _KPROCESS **)(W32GetUserGdiSessionState(v33, v32) + 40), v34 == *a1)
        || (v35 = *(HANDLE *)(W32GetUserSessionState(v34) + 63312), v35 == PsGetProcessId(*a1)) )
      {
        v6 = 0;
      }
      *((_BYTE *)a1 + 296) = v6;
    }
    return (unsigned int)InformationProcess;
  }
  if ( !v4 )
    goto LABEL_43;
  UserSessionSwitchLeaveCritWithNonPaged();
  v19 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v18) + 24);
  v20 = *(__int64 (**)(void))(v19 + 2584);
  if ( v20 )
  {
    v21 = v20();
    InformationProcess = v21;
    if ( v21 == 259 )
    {
      InformationProcess = 0;
    }
    else if ( v21 >= 0 )
    {
      v23 = W32GetUserSessionState(v19);
      *(_DWORD *)(v23 + 68920) |= 0x10000000u;
    }
  }
  else
  {
    InformationProcess = -1073741637;
  }
  v24 = W32GetUserSessionState(v19);
  v25 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v24,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v24 + 16) = v25;
  if ( v25 )
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v25 + 520), 0, 0) & 0x1000000) != 0
      && *(char *)(v25 + 1360) >= 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
        {
          while ( 1 )
          {
            v28 = *(_QWORD **)(v24 + 19544);
            if ( !v28 )
              break;
            *(_QWORD *)(v24 + 19544) = v28[2];
            v27 = *v28;
            v28[2] = 0;
            if ( !*(_DWORD *)(v27 + 8) )
            {
              LODWORD(ProcessHandle) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            }
            HMUnlockObject(*v28);
          }
          DestroyDeferredUnlockObjectAssignmentList(v24 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v24 + 19560);
        }
      }
    }
  }
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x140090df8  push    rbp
0x140090dfa  push    rbx
0x140090dfb  push    rsi
0x140090dfc  push    rdi
0x140090dfd  push    r14
0x140090dff  push    r15
0x140090e01  lea     rbp, [rsp-2Fh]
0x140090e06  sub     rsp, 0B8h
0x140090e0d  mov     rsi, rcx
0x140090e10  call    IsGreIsCurrentProcessSystemCriticalSupported
0x140090e15  test    eax, eax
0x140090e17  js      short loc_140090E26
0x140090e19  call    GreIsCurrentProcessSystemCritical
0x140090e1e  test    eax, eax
0x140090e20  jnz     loc_14009103C
0x140090e26  xor     r15d, r15d
0x140090e29  call    cs:__imp_W32GetUserGdiSessionState
0x140090e30  nop     dword ptr [rax+rax+00h]
0x140090e35  lea     r14d, [r15+1]
0x140090e39  cmp     [rax+28h], r15
0x140090e3d  jz      short loc_140090EAF
0x140090e3f  call    cs:__imp_W32GetUserSessionState
0x140090e46  nop     dword ptr [rax+rax+00h]
0x140090e4b  cmp     [rax+0F750h], r15
0x140090e52  jz      short loc_140090EAF
0x140090e54  call    cs:__imp_W32GetUserSessionState
0x140090e5b  nop     dword ptr [rax+rax+00h]
0x140090e60  mov     rbx, rax
0x140090e63  test    dword ptr [rax+10D38h], 40000h
0x140090e6d  jz      short loc_140090EAF
0x140090e6f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140090e76  nop     dword ptr [rax+rax+00h]
0x140090e7b  mov     rcx, [rax+18h]
0x140090e7f  mov     rax, [rcx+0A10h]
0x140090e86  test    rax, rax
0x140090e89  jz      loc_14009103C
0x140090e8f  call    _guard_dispatch_icall
0x140090e94  test    eax, eax
0x140090e96  js      loc_14009103C
0x140090e9c  test    dword ptr [rbx+10D38h], 10000000h
0x140090ea6  jnz     loc_14009103C
0x140090eac  mov     r15d, r14d
0x140090eaf  xor     edi, edi
0x140090eb1  call    IsCurrentSessionServiceSession
0x140090eb6  test    eax, eax
0x140090eb8  jnz     loc_140091151
0x140090ebe  xorps   xmm0, xmm0
0x140090ec1  mov     [rbp+57h+ProcessHandle], rdi
0x140090ec5  lea     ebx, [rdi+40h]
0x140090ec8  xor     edx, edx; Val
0x140090eca  mov     r8d, ebx; Size
0x140090ecd  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x140090ed1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140090ed5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140090ed9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140090edd  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x140090ee1  call    memset
0x140090ee6  mov     rcx, [rsi]
0x140090ee9  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x140090ef0  nop     dword ptr [rax+rax+00h]
0x140090ef5  test    rax, rax
0x140090ef8  jz      loc_140091151
0x140090efe  xorps   xmm0, xmm0
0x140090f01  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140090f08  lea     r9, [rbp+57h+ClientId]; ClientId
0x140090f0c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140090f10  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140090f14  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140090f1b  mov     edx, 1000h; DesiredAccess
0x140090f20  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x140090f24  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140090f28  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x140090f2c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140090f31  mov     [rbp+57h+ClientId.UniqueThread], rdi
0x140090f35  call    cs:__imp_ZwOpenProcess
0x140090f3c  nop     dword ptr [rax+rax+00h]
0x140090f41  mov     edi, eax
0x140090f43  test    eax, eax
0x140090f45  js      loc_140090FE0
0x140090f4b  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140090f4f  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x140090f53  mov     r9d, ebx; ProcessInformationLength
0x140090f56  mov     [rsp+0E0h+ReturnLength], 0; ReturnLength
0x140090f5f  lea     edx, [rbx-1Bh]; ProcessInformationClass
0x140090f62  call    cs:__imp_ZwQueryInformationProcess
0x140090f69  nop     dword ptr [rax+rax+00h]
0x140090f6e  mov     edi, eax
0x140090f70  test    eax, eax
0x140090f72  js      short loc_140090FC8
0x140090f74  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140090f7b  nop     dword ptr [rax+rax+00h]
0x140090f80  mov     rcx, [rax+30h]
0x140090f84  mov     rax, [rcx+688h]
0x140090f8b  test    rax, rax
0x140090f8e  jz      short loc_140090FC8
0x140090f90  call    _guard_dispatch_icall
0x140090f95  test    eax, eax
0x140090f97  js      short loc_140090FC8
0x140090f99  mov     ebx, [rbp+57h+var_50]
0x140090f9c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140090fa3  nop     dword ptr [rax+rax+00h]
0x140090fa8  mov     rdx, [rax+30h]
0x140090fac  mov     rax, [rdx+690h]
0x140090fb3  test    rax, rax
0x140090fb6  jz      short loc_140090FC3
0x140090fb8  mov     ecx, ebx
0x140090fba  call    _guard_dispatch_icall
0x140090fbf  test    eax, eax
0x140090fc1  jnz     short loc_140090FC8
0x140090fc3  mov     edi, 0C0000022h
0x140090fc8  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140090fcc  call    cs:__imp_ZwClose
0x140090fd3  nop     dword ptr [rax+rax+00h]
0x140090fd8  test    edi, edi
0x140090fda  jns     loc_140091151
0x140090fe0  cmp     edi, 0C000000Bh
0x140090fe6  jz      loc_14009114F
0x140090fec  cmp     edi, 0C000010Ah
0x140090ff2  jz      loc_14009114F
0x140090ff8  test    edi, edi
0x140090ffa  jns     loc_140091151
0x140091000  test    r15d, r15d
0x140091003  jz      loc_140091151
0x140091009  call    UserSessionSwitchLeaveCritWithNonPaged
0x14009100e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140091015  nop     dword ptr [rax+rax+00h]
0x14009101a  mov     rcx, [rax+18h]
0x14009101e  mov     rax, [rcx+0A18h]
0x140091025  test    rax, rax
0x140091028  jz      short loc_14009105D
0x14009102a  call    _guard_dispatch_icall
0x14009102f  mov     edi, eax
0x140091031  cmp     eax, 103h
0x140091036  jnz     short loc_140091043
0x140091038  xor     edi, edi
0x14009103a  jmp     short loc_140091062
0x14009103c  xor     eax, eax
0x14009103e  jmp     loc_1400911CB
0x140091043  test    eax, eax
0x140091045  js      short loc_140091062
0x140091047  call    cs:__imp_W32GetUserSessionState
0x14009104e  nop     dword ptr [rax+rax+00h]
0x140091053  bts     dword ptr [rax+10D38h], 1Ch
0x14009105b  jmp     short loc_140091062
0x14009105d  mov     edi, 0C00000BBh
0x140091062  call    cs:__imp_W32GetUserSessionState
0x140091069  nop     dword ptr [rax+rax+00h]
0x14009106e  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140091075  xor     r8d, r8d
0x140091078  mov     rcx, rax
0x14009107b  mov     edx, r14d
0x14009107e  mov     rbx, rax
0x140091081  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x140091086  mov     [rbx+10h], rax
0x14009108a  mov     rdx, rax
0x14009108d  test    rax, rax
0x140091090  jz      loc_1400911C9
0x140091096  xor     ecx, ecx
0x140091098  xor     eax, eax
0x14009109a  lock cmpxchg [rdx+208h], ecx
0x1400910a2  bt      eax, 18h
0x1400910a6  jnb     loc_1400911C9
0x1400910ac  mov     al, [rdx+550h]
0x1400910b2  test    al, al
0x1400910b4  js      loc_1400911C9
0x1400910ba  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400910c1  nop     dword ptr [rax+rax+00h]
0x1400910c6  test    rax, rax
0x1400910c9  jz      loc_1400911C9
0x1400910cf  cmp     qword ptr [rax], 0
0x1400910d3  jz      loc_1400911C9
0x1400910d9  mov     al, [rax+4B0h]
0x1400910df  cmp     al, r14b
0x1400910e2  jz      short loc_140091129
0x1400910e4  jmp     loc_1400911C9
0x1400910e9  mov     rax, [rsi+10h]
0x1400910ed  mov     [rbx+4C58h], rax
0x1400910f4  mov     rax, [rsi]
0x1400910f7  mov     qword ptr [rsi+10h], 0
0x1400910ff  cmp     [rax+8], r14d
0x140091103  jnb     short loc_140091121
0x140091105  mov     dword ptr [rbp+57h+ProcessHandle], 20000h
0x14009110c  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140091113  mov     edx, dword ptr [rbp+57h+ProcessHandle]
0x140091116  mov     r8d, 1236h
0x14009111c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140091121  mov     rcx, [rsi]
0x140091124  call    HMUnlockObject
0x140091129  mov     rsi, [rbx+4C58h]
0x140091130  test    rsi, rsi
0x140091133  jnz     short loc_1400910E9
0x140091135  lea     rcx, [rbx+4C78h]
0x14009113c  call    DestroyDeferredUnlockObjectAssignmentList
0x140091141  lea     rcx, [rbx+4C68h]
0x140091148  call    DestroyDeferredUnlockObjectAssignmentList
0x14009114d  jmp     short loc_1400911C9
0x14009114f  xor     edi, edi
0x140091151  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x140091156  test    eax, eax
0x140091158  jz      short loc_1400911C9
0x14009115a  call    cs:__imp_W32GetUserGdiSessionState
0x140091161  nop     dword ptr [rax+rax+00h]
0x140091166  cmp     qword ptr [rax+28h], 0
0x14009116b  jz      short loc_1400911BF
0x14009116d  call    cs:__imp_W32GetUserSessionState
0x140091174  nop     dword ptr [rax+rax+00h]
0x140091179  cmp     qword ptr [rax+0F750h], 0
0x140091181  jz      short loc_1400911BF
0x140091183  call    cs:__imp_W32GetUserGdiSessionState
0x14009118a  nop     dword ptr [rax+rax+00h]
0x14009118f  mov     rcx, [rax+28h]
0x140091193  cmp     rcx, [rsi]
0x140091196  jz      short loc_1400911BF
0x140091198  call    cs:__imp_W32GetUserSessionState
0x14009119f  nop     dword ptr [rax+rax+00h]
0x1400911a4  mov     rcx, [rsi]; Process
0x1400911a7  mov     rbx, [rax+0F750h]
0x1400911ae  call    cs:__imp_PsGetProcessId
0x1400911b5  nop     dword ptr [rax+rax+00h]
0x1400911ba  cmp     rbx, rax
0x1400911bd  jnz     short loc_1400911C2
0x1400911bf  xor     r14b, r14b
0x1400911c2  mov     [rsi+128h], r14b
0x1400911c9  mov     eax, edi
0x1400911cb  add     rsp, 0B8h
0x1400911d2  pop     r15
0x1400911d4  pop     r14
0x1400911d6  pop     rdi
0x1400911d7  pop     rsi
0x1400911d8  pop     rbx
0x1400911d9  pop     rbp
0x1400911da  retn
```
