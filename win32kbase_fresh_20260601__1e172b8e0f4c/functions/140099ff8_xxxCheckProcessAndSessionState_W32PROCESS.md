# xxxCheckProcessAndSessionState(_W32PROCESS *)

- ea: `0x140099ff8`
- end: `0x14009a3dc`
- name: `?xxxCheckProcessAndSessionState@@YAJPEAU_W32PROCESS@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct _W32PROCESS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400b471c`

## callees

- `0x140012c80`
- `0x14002a0e4`
- `0x140073a50`
- `0x140076ef0`
- `0x140099ff8`
- `0x14009c11c`
- `0x14009c154`
- `0x140156bb8`
- `0x140189f58`
- `0x1401aa4fc`
- `0x140238bf0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14009a1cc`
- `ntoskrnl!ZwClose` at `0x14009a1cc`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14009a2ba`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14009a2ba`
- `ntoskrnl!PsGetProcessId` at `0x14009a3ae`
- `ntoskrnl!PsGetProcessId` at `0x14009a3ae`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14009a0e9`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14009a0e9`
- `ntoskrnl!ZwOpenProcess` at `0x14009a135`
- `ntoskrnl!ZwOpenProcess` at `0x14009a135`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14009a162`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14009a162`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a06f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a174`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a19c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a20e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a06f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a174`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a19c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009a20e`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009a029`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009a35a`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009a383`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009a029`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009a35a`
- `WIN32K!W32GetUserGdiSessionState` at `0x14009a383`
- `WIN32K!W32GetUserSessionState` at `0x14009a03f`
- `WIN32K!W32GetUserSessionState` at `0x14009a054`
- `WIN32K!W32GetUserSessionState` at `0x14009a247`
- `WIN32K!W32GetUserSessionState` at `0x14009a262`
- `WIN32K!W32GetUserSessionState` at `0x14009a36d`
- `WIN32K!W32GetUserSessionState` at `0x14009a398`
- `WIN32K!W32GetUserSessionState` at `0x14009a03f`
- `WIN32K!W32GetUserSessionState` at `0x14009a054`
- `WIN32K!W32GetUserSessionState` at `0x14009a247`
- `WIN32K!W32GetUserSessionState` at `0x14009a262`
- `WIN32K!W32GetUserSessionState` at `0x14009a36d`
- `WIN32K!W32GetUserSessionState` at `0x14009a398`

## pseudocode

```c
__int64 __fastcall xxxCheckProcessAndSessionState(PEPROCESS *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // r15d
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  char v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 UserSessionState; // rbx
  int (*v14)(void); // rax
  NTSTATUS InformationProcess; // edi
  void *ProcessInheritedFromUniqueProcessId; // rax
  __int64 v17; // rcx
  int (*v18)(void); // rax
  __int64 v19; // rcx
  unsigned int v20; // ebx
  unsigned int (__fastcall *v21)(_QWORD); // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 (*v26)(void); // rax
  int v27; // eax
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v33; // rax
  _QWORD *v34; // rsi
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  struct _KPROCESS *v43; // rcx
  __int64 v44; // r8
  HANDLE v45; // rbx
  _CLIENT_ID ClientId; // [rsp+30h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-49h] BYREF
  _DWORD ProcessInformation[28]; // [rsp+70h] [rbp-19h] BYREF
  void *ProcessHandle; // [rsp+F8h] [rbp+6Fh] BYREF

  if ( (int)IsGreIsCurrentProcessSystemCriticalSupported() >= 0 && (unsigned int)GreIsCurrentProcessSystemCritical() )
    return 0;
  v4 = 0;
  v8 = 1;
  if ( !*(_QWORD *)(W32GetUserGdiSessionState(v3, v2) + 40) )
    goto LABEL_10;
  if ( !*(_QWORD *)(W32GetUserSessionState(v6, v5, v7) + 63312) )
    goto LABEL_10;
  UserSessionState = W32GetUserSessionState(v10, v9, v11);
  if ( (*(_DWORD *)(UserSessionState + 68920) & 0x40000) == 0 )
    goto LABEL_10;
  v14 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v12) + 24) + 2576LL);
  if ( !v14 || v14() < 0 || (*(_DWORD *)(UserSessionState + 68920) & 0x10000000) != 0 )
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
      v18 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v17) + 48) + 1672LL);
      if ( v18 )
      {
        if ( v18() >= 0 )
        {
          v20 = ProcessInformation[8];
          v21 = *(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v19) + 48) + 1680LL);
          if ( !v21 || !v21(v20) )
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
      if ( !*(_QWORD *)(W32GetUserGdiSessionState(v36, v35) + 40)
        || !*(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 63312)
        || (v43 = *(struct _KPROCESS **)(W32GetUserGdiSessionState(v41, v40) + 40), v43 == *a1)
        || (v45 = *(HANDLE *)(W32GetUserSessionState(v43, v42, v44) + 63312), v45 == PsGetProcessId(*a1)) )
      {
        v8 = 0;
      }
      *((_BYTE *)a1 + 296) = v8;
    }
    return (unsigned int)InformationProcess;
  }
  if ( !v4 )
    goto LABEL_43;
  UserSessionSwitchLeaveCritWithNonPaged();
  v24 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v22) + 24);
  v26 = *(__int64 (**)(void))(v24 + 2584);
  if ( v26 )
  {
    v27 = v26();
    InformationProcess = v27;
    if ( v27 == 259 )
    {
      InformationProcess = 0;
    }
    else if ( v27 >= 0 )
    {
      v29 = W32GetUserSessionState(v24, v23, v25);
      *(_DWORD *)(v29 + 68920) |= 0x10000000u;
    }
  }
  else
  {
    InformationProcess = -1073741637;
  }
  v30 = W32GetUserSessionState(v24, v23, v25);
  v31 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v30,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v30 + 16) = v31;
  if ( v31 )
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v31 + 520), 0, 0) & 0x1000000) != 0
      && *(char *)(v31 + 1360) >= 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
        {
          while ( 1 )
          {
            v34 = *(_QWORD **)(v30 + 19544);
            if ( !v34 )
              break;
            *(_QWORD *)(v30 + 19544) = v34[2];
            v33 = *v34;
            v34[2] = 0;
            if ( !*(_DWORD *)(v33 + 8) )
            {
              LODWORD(ProcessHandle) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            }
            HMUnlockObject(*v34);
          }
          DestroyDeferredUnlockObjectAssignmentList(v30 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v30 + 19560);
        }
      }
    }
  }
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x140099ff8  push    rbp
0x140099ffa  push    rbx
0x140099ffb  push    rsi
0x140099ffc  push    rdi
0x140099ffd  push    r14
0x140099fff  push    r15
0x14009a001  lea     rbp, [rsp-2Fh]
0x14009a006  sub     rsp, 0B8h
0x14009a00d  mov     rsi, rcx
0x14009a010  call    IsGreIsCurrentProcessSystemCriticalSupported
0x14009a015  test    eax, eax
0x14009a017  js      short loc_14009A026
0x14009a019  call    GreIsCurrentProcessSystemCritical
0x14009a01e  test    eax, eax
0x14009a020  jnz     loc_14009A23C
0x14009a026  xor     r15d, r15d
0x14009a029  call    cs:__imp_W32GetUserGdiSessionState
0x14009a030  nop     dword ptr [rax+rax+00h]
0x14009a035  lea     r14d, [r15+1]
0x14009a039  cmp     [rax+28h], r15
0x14009a03d  jz      short loc_14009A0AF
0x14009a03f  call    cs:__imp_W32GetUserSessionState
0x14009a046  nop     dword ptr [rax+rax+00h]
0x14009a04b  cmp     [rax+0F750h], r15
0x14009a052  jz      short loc_14009A0AF
0x14009a054  call    cs:__imp_W32GetUserSessionState
0x14009a05b  nop     dword ptr [rax+rax+00h]
0x14009a060  mov     rbx, rax
0x14009a063  test    dword ptr [rax+10D38h], 40000h
0x14009a06d  jz      short loc_14009A0AF
0x14009a06f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009a076  nop     dword ptr [rax+rax+00h]
0x14009a07b  mov     rcx, [rax+18h]
0x14009a07f  mov     rax, [rcx+0A10h]
0x14009a086  test    rax, rax
0x14009a089  jz      loc_14009A23C
0x14009a08f  call    _guard_dispatch_icall
0x14009a094  test    eax, eax
0x14009a096  js      loc_14009A23C
0x14009a09c  test    dword ptr [rbx+10D38h], 10000000h
0x14009a0a6  jnz     loc_14009A23C
0x14009a0ac  mov     r15d, r14d
0x14009a0af  xor     edi, edi
0x14009a0b1  call    IsCurrentSessionServiceSession
0x14009a0b6  test    eax, eax
0x14009a0b8  jnz     loc_14009A351
0x14009a0be  xorps   xmm0, xmm0
0x14009a0c1  mov     [rbp+57h+ProcessHandle], rdi
0x14009a0c5  lea     ebx, [rdi+40h]
0x14009a0c8  xor     edx, edx; Val
0x14009a0ca  mov     r8d, ebx; Size
0x14009a0cd  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x14009a0d1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14009a0d5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14009a0d9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009a0dd  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x14009a0e1  call    memset
0x14009a0e6  mov     rcx, [rsi]
0x14009a0e9  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x14009a0f0  nop     dword ptr [rax+rax+00h]
0x14009a0f5  test    rax, rax
0x14009a0f8  jz      loc_14009A351
0x14009a0fe  xorps   xmm0, xmm0
0x14009a101  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14009a108  lea     r9, [rbp+57h+ClientId]; ClientId
0x14009a10c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x14009a110  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009a114  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14009a11b  mov     edx, 1000h; DesiredAccess
0x14009a120  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x14009a124  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14009a128  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x14009a12c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009a131  mov     [rbp+57h+ClientId.UniqueThread], rdi
0x14009a135  call    cs:__imp_ZwOpenProcess
0x14009a13c  nop     dword ptr [rax+rax+00h]
0x14009a141  mov     edi, eax
0x14009a143  test    eax, eax
0x14009a145  js      loc_14009A1E0
0x14009a14b  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14009a14f  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14009a153  mov     r9d, ebx; ProcessInformationLength
0x14009a156  mov     [rsp+0E0h+ReturnLength], 0; ReturnLength
0x14009a15f  lea     edx, [rbx-1Bh]; ProcessInformationClass
0x14009a162  call    cs:__imp_ZwQueryInformationProcess
0x14009a169  nop     dword ptr [rax+rax+00h]
0x14009a16e  mov     edi, eax
0x14009a170  test    eax, eax
0x14009a172  js      short loc_14009A1C8
0x14009a174  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009a17b  nop     dword ptr [rax+rax+00h]
0x14009a180  mov     rcx, [rax+30h]
0x14009a184  mov     rax, [rcx+688h]
0x14009a18b  test    rax, rax
0x14009a18e  jz      short loc_14009A1C8
0x14009a190  call    _guard_dispatch_icall
0x14009a195  test    eax, eax
0x14009a197  js      short loc_14009A1C8
0x14009a199  mov     ebx, [rbp+57h+var_50]
0x14009a19c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009a1a3  nop     dword ptr [rax+rax+00h]
0x14009a1a8  mov     rdx, [rax+30h]
0x14009a1ac  mov     rax, [rdx+690h]
0x14009a1b3  test    rax, rax
0x14009a1b6  jz      short loc_14009A1C3
0x14009a1b8  mov     ecx, ebx
0x14009a1ba  call    _guard_dispatch_icall
0x14009a1bf  test    eax, eax
0x14009a1c1  jnz     short loc_14009A1C8
0x14009a1c3  mov     edi, 0C0000022h
0x14009a1c8  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14009a1cc  call    cs:__imp_ZwClose
0x14009a1d3  nop     dword ptr [rax+rax+00h]
0x14009a1d8  test    edi, edi
0x14009a1da  jns     loc_14009A351
0x14009a1e0  cmp     edi, 0C000000Bh
0x14009a1e6  jz      loc_14009A34F
0x14009a1ec  cmp     edi, 0C000010Ah
0x14009a1f2  jz      loc_14009A34F
0x14009a1f8  test    edi, edi
0x14009a1fa  jns     loc_14009A351
0x14009a200  test    r15d, r15d
0x14009a203  jz      loc_14009A351
0x14009a209  call    UserSessionSwitchLeaveCritWithNonPaged
0x14009a20e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009a215  nop     dword ptr [rax+rax+00h]
0x14009a21a  mov     rcx, [rax+18h]
0x14009a21e  mov     rax, [rcx+0A18h]
0x14009a225  test    rax, rax
0x14009a228  jz      short loc_14009A25D
0x14009a22a  call    _guard_dispatch_icall
0x14009a22f  mov     edi, eax
0x14009a231  cmp     eax, 103h
0x14009a236  jnz     short loc_14009A243
0x14009a238  xor     edi, edi
0x14009a23a  jmp     short loc_14009A262
0x14009a23c  xor     eax, eax
0x14009a23e  jmp     loc_14009A3CB
0x14009a243  test    eax, eax
0x14009a245  js      short loc_14009A262
0x14009a247  call    cs:__imp_W32GetUserSessionState
0x14009a24e  nop     dword ptr [rax+rax+00h]
0x14009a253  bts     dword ptr [rax+10D38h], 1Ch
0x14009a25b  jmp     short loc_14009A262
0x14009a25d  mov     edi, 0C00000BBh
0x14009a262  call    cs:__imp_W32GetUserSessionState
0x14009a269  nop     dword ptr [rax+rax+00h]
0x14009a26e  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14009a275  xor     r8d, r8d
0x14009a278  mov     rcx, rax
0x14009a27b  mov     edx, r14d
0x14009a27e  mov     rbx, rax
0x14009a281  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14009a286  mov     [rbx+10h], rax
0x14009a28a  mov     rdx, rax
0x14009a28d  test    rax, rax
0x14009a290  jz      loc_14009A3C9
0x14009a296  xor     ecx, ecx
0x14009a298  xor     eax, eax
0x14009a29a  lock cmpxchg [rdx+208h], ecx
0x14009a2a2  bt      eax, 18h
0x14009a2a6  jnb     loc_14009A3C9
0x14009a2ac  mov     al, [rdx+550h]
0x14009a2b2  test    al, al
0x14009a2b4  js      loc_14009A3C9
0x14009a2ba  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14009a2c1  nop     dword ptr [rax+rax+00h]
0x14009a2c6  test    rax, rax
0x14009a2c9  jz      loc_14009A3C9
0x14009a2cf  cmp     qword ptr [rax], 0
0x14009a2d3  jz      loc_14009A3C9
0x14009a2d9  mov     al, [rax+4B0h]
0x14009a2df  cmp     al, r14b
0x14009a2e2  jz      short loc_14009A329
0x14009a2e4  jmp     loc_14009A3C9
0x14009a2e9  mov     rax, [rsi+10h]
0x14009a2ed  mov     [rbx+4C58h], rax
0x14009a2f4  mov     rax, [rsi]
0x14009a2f7  mov     qword ptr [rsi+10h], 0
0x14009a2ff  cmp     [rax+8], r14d
0x14009a303  jnb     short loc_14009A321
0x14009a305  mov     dword ptr [rbp+57h+ProcessHandle], 20000h
0x14009a30c  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14009a313  mov     edx, dword ptr [rbp+57h+ProcessHandle]
0x14009a316  mov     r8d, 1236h
0x14009a31c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14009a321  mov     rcx, [rsi]
0x14009a324  call    HMUnlockObject
0x14009a329  mov     rsi, [rbx+4C58h]
0x14009a330  test    rsi, rsi
0x14009a333  jnz     short loc_14009A2E9
0x14009a335  lea     rcx, [rbx+4C78h]
0x14009a33c  call    DestroyDeferredUnlockObjectAssignmentList
0x14009a341  lea     rcx, [rbx+4C68h]
0x14009a348  call    DestroyDeferredUnlockObjectAssignmentList
0x14009a34d  jmp     short loc_14009A3C9
0x14009a34f  xor     edi, edi
0x14009a351  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x14009a356  test    eax, eax
0x14009a358  jz      short loc_14009A3C9
0x14009a35a  call    cs:__imp_W32GetUserGdiSessionState
0x14009a361  nop     dword ptr [rax+rax+00h]
0x14009a366  cmp     qword ptr [rax+28h], 0
0x14009a36b  jz      short loc_14009A3BF
0x14009a36d  call    cs:__imp_W32GetUserSessionState
0x14009a374  nop     dword ptr [rax+rax+00h]
0x14009a379  cmp     qword ptr [rax+0F750h], 0
0x14009a381  jz      short loc_14009A3BF
0x14009a383  call    cs:__imp_W32GetUserGdiSessionState
0x14009a38a  nop     dword ptr [rax+rax+00h]
0x14009a38f  mov     rcx, [rax+28h]
0x14009a393  cmp     rcx, [rsi]
0x14009a396  jz      short loc_14009A3BF
0x14009a398  call    cs:__imp_W32GetUserSessionState
0x14009a39f  nop     dword ptr [rax+rax+00h]
0x14009a3a4  mov     rcx, [rsi]; Process
0x14009a3a7  mov     rbx, [rax+0F750h]
0x14009a3ae  call    cs:__imp_PsGetProcessId
0x14009a3b5  nop     dword ptr [rax+rax+00h]
0x14009a3ba  cmp     rbx, rax
0x14009a3bd  jnz     short loc_14009A3C2
0x14009a3bf  xor     r14b, r14b
0x14009a3c2  mov     [rsi+128h], r14b
0x14009a3c9  mov     eax, edi
0x14009a3cb  add     rsp, 0B8h
0x14009a3d2  pop     r15
0x14009a3d4  pop     r14
0x14009a3d6  pop     rdi
0x14009a3d7  pop     rsi
0x14009a3d8  pop     rbx
0x14009a3d9  pop     rbp
0x14009a3da  retn
```
