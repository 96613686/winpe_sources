# xxxCheckProcessAndSessionState(_W32PROCESS *)

- ea: `0x140063ef0`
- end: `0x1400642d4`
- name: `?xxxCheckProcessAndSessionState@@YAJPEAU_W32PROCESS@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct _W32PROCESS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14014e31c`

## callees

- `0x140029710`
- `0x14004c020`
- `0x14004f4c0`
- `0x140063878`
- `0x1400638c0`
- `0x140063ef0`
- `0x14006601c`
- `0x140066054`
- `0x1400701d4`
- `0x1401aab9c`
- `0x1402389c0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400640c4`
- `ntoskrnl!ZwClose` at `0x1400640c4`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400641b2`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400641b2`
- `ntoskrnl!PsGetProcessId` at `0x1400642a6`
- `ntoskrnl!PsGetProcessId` at `0x1400642a6`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140063fe1`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140063fe1`
- `ntoskrnl!ZwOpenProcess` at `0x14006402d`
- `ntoskrnl!ZwOpenProcess` at `0x14006402d`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14006405a`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14006405a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140063f67`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14006406c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140064094`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140064106`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140063f67`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14006406c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140064094`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140064106`
- `WIN32K!W32GetUserGdiSessionState` at `0x140063f21`
- `WIN32K!W32GetUserGdiSessionState` at `0x140064252`
- `WIN32K!W32GetUserGdiSessionState` at `0x14006427b`
- `WIN32K!W32GetUserGdiSessionState` at `0x140063f21`
- `WIN32K!W32GetUserGdiSessionState` at `0x140064252`
- `WIN32K!W32GetUserGdiSessionState` at `0x14006427b`
- `WIN32K!W32GetUserSessionState` at `0x140063f37`
- `WIN32K!W32GetUserSessionState` at `0x140063f4c`
- `WIN32K!W32GetUserSessionState` at `0x14006413f`
- `WIN32K!W32GetUserSessionState` at `0x14006415a`
- `WIN32K!W32GetUserSessionState` at `0x140064265`
- `WIN32K!W32GetUserSessionState` at `0x140064290`
- `WIN32K!W32GetUserSessionState` at `0x140063f37`
- `WIN32K!W32GetUserSessionState` at `0x140063f4c`
- `WIN32K!W32GetUserSessionState` at `0x14006413f`
- `WIN32K!W32GetUserSessionState` at `0x14006415a`
- `WIN32K!W32GetUserSessionState` at `0x140064265`
- `WIN32K!W32GetUserSessionState` at `0x140064290`

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
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 UserSessionState; // rbx
  int (*v15)(void); // rax
  NTSTATUS InformationProcess; // edi
  void *ProcessInheritedFromUniqueProcessId; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int (*v21)(void); // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // ebx
  unsigned int (__fastcall *v25)(_QWORD); // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 (*v31)(void); // rax
  int v32; // eax
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v38; // rax
  _QWORD *v39; // rsi
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  struct _KPROCESS *v48; // rcx
  __int64 v49; // r8
  HANDLE v50; // rbx
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
  v15 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v13, v12) + 24) + 2576LL);
  if ( !v15 || v15() < 0 || (*(_DWORD *)(UserSessionState + 68920) & 0x10000000) != 0 )
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
      v21 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v20, v19) + 48) + 1672LL);
      if ( v21 )
      {
        if ( v21() >= 0 )
        {
          v24 = ProcessInformation[8];
          v25 = *(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v23, v22) + 48) + 1680LL);
          if ( !v25 || !v25(v24) )
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
      if ( !*(_QWORD *)(W32GetUserGdiSessionState(v41, v40) + 40)
        || !*(_QWORD *)(W32GetUserSessionState(v43, v42, v44) + 63312)
        || (v48 = *(struct _KPROCESS **)(W32GetUserGdiSessionState(v46, v45) + 40), v48 == *a1)
        || (v50 = *(HANDLE *)(W32GetUserSessionState(v48, v47, v49) + 63312), v50 == PsGetProcessId(*a1)) )
      {
        v8 = 0;
      }
      *((_BYTE *)a1 + 296) = v8;
    }
    return (unsigned int)InformationProcess;
  }
  if ( !v4 )
    goto LABEL_43;
  UserSessionSwitchLeaveCritWithNonPaged(v18);
  v29 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v27, v26) + 24);
  v31 = *(__int64 (**)(void))(v29 + 2584);
  if ( v31 )
  {
    v32 = v31();
    InformationProcess = v32;
    if ( v32 == 259 )
    {
      InformationProcess = 0;
    }
    else if ( v32 >= 0 )
    {
      v34 = W32GetUserSessionState(v29, v28, v30);
      *(_DWORD *)(v34 + 68920) |= 0x10000000u;
    }
  }
  else
  {
    InformationProcess = -1073741637;
  }
  v35 = W32GetUserSessionState(v29, v28, v30);
  v36 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v35,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v35 + 16) = v36;
  if ( v36 )
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v36 + 520), 0, 0) & 0x1000000) != 0
      && *(char *)(v36 + 1360) >= 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
        {
          while ( 1 )
          {
            v39 = *(_QWORD **)(v35 + 19544);
            if ( !v39 )
              break;
            *(_QWORD *)(v35 + 19544) = v39[2];
            v38 = *v39;
            v39[2] = 0;
            if ( !*(_DWORD *)(v38 + 8) )
            {
              LODWORD(ProcessHandle) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            }
            HMUnlockObject(*v39);
          }
          DestroyDeferredUnlockObjectAssignmentList(v35 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v35 + 19560);
        }
      }
    }
  }
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x140063ef0  push    rbp
0x140063ef2  push    rbx
0x140063ef3  push    rsi
0x140063ef4  push    rdi
0x140063ef5  push    r14
0x140063ef7  push    r15
0x140063ef9  lea     rbp, [rsp-2Fh]
0x140063efe  sub     rsp, 0B8h
0x140063f05  mov     rsi, rcx
0x140063f08  call    IsGreIsCurrentProcessSystemCriticalSupported
0x140063f0d  test    eax, eax
0x140063f0f  js      short loc_140063F1E
0x140063f11  call    GreIsCurrentProcessSystemCritical
0x140063f16  test    eax, eax
0x140063f18  jnz     loc_140064134
0x140063f1e  xor     r15d, r15d
0x140063f21  call    cs:__imp_W32GetUserGdiSessionState
0x140063f28  nop     dword ptr [rax+rax+00h]
0x140063f2d  lea     r14d, [r15+1]
0x140063f31  cmp     [rax+28h], r15
0x140063f35  jz      short loc_140063FA7
0x140063f37  call    cs:__imp_W32GetUserSessionState
0x140063f3e  nop     dword ptr [rax+rax+00h]
0x140063f43  cmp     [rax+0F750h], r15
0x140063f4a  jz      short loc_140063FA7
0x140063f4c  call    cs:__imp_W32GetUserSessionState
0x140063f53  nop     dword ptr [rax+rax+00h]
0x140063f58  mov     rbx, rax
0x140063f5b  test    dword ptr [rax+10D38h], 40000h
0x140063f65  jz      short loc_140063FA7
0x140063f67  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140063f6e  nop     dword ptr [rax+rax+00h]
0x140063f73  mov     rcx, [rax+18h]
0x140063f77  mov     rax, [rcx+0A10h]
0x140063f7e  test    rax, rax
0x140063f81  jz      loc_140064134
0x140063f87  call    _guard_dispatch_icall
0x140063f8c  test    eax, eax
0x140063f8e  js      loc_140064134
0x140063f94  test    dword ptr [rbx+10D38h], 10000000h
0x140063f9e  jnz     loc_140064134
0x140063fa4  mov     r15d, r14d
0x140063fa7  xor     edi, edi
0x140063fa9  call    IsCurrentSessionServiceSession
0x140063fae  test    eax, eax
0x140063fb0  jnz     loc_140064249
0x140063fb6  xorps   xmm0, xmm0
0x140063fb9  mov     [rbp+57h+ProcessHandle], rdi
0x140063fbd  lea     ebx, [rdi+40h]
0x140063fc0  xor     edx, edx; Val
0x140063fc2  mov     r8d, ebx; Size
0x140063fc5  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x140063fc9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140063fcd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140063fd1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140063fd5  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x140063fd9  call    memset
0x140063fde  mov     rcx, [rsi]
0x140063fe1  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x140063fe8  nop     dword ptr [rax+rax+00h]
0x140063fed  test    rax, rax
0x140063ff0  jz      loc_140064249
0x140063ff6  xorps   xmm0, xmm0
0x140063ff9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140064000  lea     r9, [rbp+57h+ClientId]; ClientId
0x140064004  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140064008  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14006400c  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140064013  mov     edx, 1000h; DesiredAccess
0x140064018  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x14006401c  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140064020  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x140064024  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140064029  mov     [rbp+57h+ClientId.UniqueThread], rdi
0x14006402d  call    cs:__imp_ZwOpenProcess
0x140064034  nop     dword ptr [rax+rax+00h]
0x140064039  mov     edi, eax
0x14006403b  test    eax, eax
0x14006403d  js      loc_1400640D8
0x140064043  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140064047  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14006404b  mov     r9d, ebx; ProcessInformationLength
0x14006404e  mov     [rsp+0E0h+ReturnLength], 0; ReturnLength
0x140064057  lea     edx, [rbx-1Bh]; ProcessInformationClass
0x14006405a  call    cs:__imp_ZwQueryInformationProcess
0x140064061  nop     dword ptr [rax+rax+00h]
0x140064066  mov     edi, eax
0x140064068  test    eax, eax
0x14006406a  js      short loc_1400640C0
0x14006406c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140064073  nop     dword ptr [rax+rax+00h]
0x140064078  mov     rcx, [rax+30h]
0x14006407c  mov     rax, [rcx+688h]
0x140064083  test    rax, rax
0x140064086  jz      short loc_1400640C0
0x140064088  call    _guard_dispatch_icall
0x14006408d  test    eax, eax
0x14006408f  js      short loc_1400640C0
0x140064091  mov     ebx, [rbp+57h+var_50]
0x140064094  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14006409b  nop     dword ptr [rax+rax+00h]
0x1400640a0  mov     rdx, [rax+30h]
0x1400640a4  mov     rax, [rdx+690h]
0x1400640ab  test    rax, rax
0x1400640ae  jz      short loc_1400640BB
0x1400640b0  mov     ecx, ebx
0x1400640b2  call    _guard_dispatch_icall
0x1400640b7  test    eax, eax
0x1400640b9  jnz     short loc_1400640C0
0x1400640bb  mov     edi, 0C0000022h
0x1400640c0  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1400640c4  call    cs:__imp_ZwClose
0x1400640cb  nop     dword ptr [rax+rax+00h]
0x1400640d0  test    edi, edi
0x1400640d2  jns     loc_140064249
0x1400640d8  cmp     edi, 0C000000Bh
0x1400640de  jz      loc_140064247
0x1400640e4  cmp     edi, 0C000010Ah
0x1400640ea  jz      loc_140064247
0x1400640f0  test    edi, edi
0x1400640f2  jns     loc_140064249
0x1400640f8  test    r15d, r15d
0x1400640fb  jz      loc_140064249
0x140064101  call    UserSessionSwitchLeaveCritWithNonPaged
0x140064106  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14006410d  nop     dword ptr [rax+rax+00h]
0x140064112  mov     rcx, [rax+18h]
0x140064116  mov     rax, [rcx+0A18h]
0x14006411d  test    rax, rax
0x140064120  jz      short loc_140064155
0x140064122  call    _guard_dispatch_icall
0x140064127  mov     edi, eax
0x140064129  cmp     eax, 103h
0x14006412e  jnz     short loc_14006413B
0x140064130  xor     edi, edi
0x140064132  jmp     short loc_14006415A
0x140064134  xor     eax, eax
0x140064136  jmp     loc_1400642C3
0x14006413b  test    eax, eax
0x14006413d  js      short loc_14006415A
0x14006413f  call    cs:__imp_W32GetUserSessionState
0x140064146  nop     dword ptr [rax+rax+00h]
0x14006414b  bts     dword ptr [rax+10D38h], 1Ch
0x140064153  jmp     short loc_14006415A
0x140064155  mov     edi, 0C00000BBh
0x14006415a  call    cs:__imp_W32GetUserSessionState
0x140064161  nop     dword ptr [rax+rax+00h]
0x140064166  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14006416d  xor     r8d, r8d
0x140064170  mov     rcx, rax
0x140064173  mov     edx, r14d
0x140064176  mov     rbx, rax
0x140064179  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14006417e  mov     [rbx+10h], rax
0x140064182  mov     rdx, rax
0x140064185  test    rax, rax
0x140064188  jz      loc_1400642C1
0x14006418e  xor     ecx, ecx
0x140064190  xor     eax, eax
0x140064192  lock cmpxchg [rdx+208h], ecx
0x14006419a  bt      eax, 18h
0x14006419e  jnb     loc_1400642C1
0x1400641a4  mov     al, [rdx+550h]
0x1400641aa  test    al, al
0x1400641ac  js      loc_1400642C1
0x1400641b2  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400641b9  nop     dword ptr [rax+rax+00h]
0x1400641be  test    rax, rax
0x1400641c1  jz      loc_1400642C1
0x1400641c7  cmp     qword ptr [rax], 0
0x1400641cb  jz      loc_1400642C1
0x1400641d1  mov     al, [rax+4B0h]
0x1400641d7  cmp     al, r14b
0x1400641da  jz      short loc_140064221
0x1400641dc  jmp     loc_1400642C1
0x1400641e1  mov     rax, [rsi+10h]
0x1400641e5  mov     [rbx+4C58h], rax
0x1400641ec  mov     rax, [rsi]
0x1400641ef  mov     qword ptr [rsi+10h], 0
0x1400641f7  cmp     [rax+8], r14d
0x1400641fb  jnb     short loc_140064219
0x1400641fd  mov     dword ptr [rbp+57h+ProcessHandle], 20000h
0x140064204  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14006420b  mov     edx, dword ptr [rbp+57h+ProcessHandle]
0x14006420e  mov     r8d, 1236h
0x140064214  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140064219  mov     rcx, [rsi]
0x14006421c  call    HMUnlockObject
0x140064221  mov     rsi, [rbx+4C58h]
0x140064228  test    rsi, rsi
0x14006422b  jnz     short loc_1400641E1
0x14006422d  lea     rcx, [rbx+4C78h]
0x140064234  call    DestroyDeferredUnlockObjectAssignmentList
0x140064239  lea     rcx, [rbx+4C68h]
0x140064240  call    DestroyDeferredUnlockObjectAssignmentList
0x140064245  jmp     short loc_1400642C1
0x140064247  xor     edi, edi
0x140064249  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x14006424e  test    eax, eax
0x140064250  jz      short loc_1400642C1
0x140064252  call    cs:__imp_W32GetUserGdiSessionState
0x140064259  nop     dword ptr [rax+rax+00h]
0x14006425e  cmp     qword ptr [rax+28h], 0
0x140064263  jz      short loc_1400642B7
0x140064265  call    cs:__imp_W32GetUserSessionState
0x14006426c  nop     dword ptr [rax+rax+00h]
0x140064271  cmp     qword ptr [rax+0F750h], 0
0x140064279  jz      short loc_1400642B7
0x14006427b  call    cs:__imp_W32GetUserGdiSessionState
0x140064282  nop     dword ptr [rax+rax+00h]
0x140064287  mov     rcx, [rax+28h]
0x14006428b  cmp     rcx, [rsi]
0x14006428e  jz      short loc_1400642B7
0x140064290  call    cs:__imp_W32GetUserSessionState
0x140064297  nop     dword ptr [rax+rax+00h]
0x14006429c  mov     rcx, [rsi]; Process
0x14006429f  mov     rbx, [rax+0F750h]
0x1400642a6  call    cs:__imp_PsGetProcessId
0x1400642ad  nop     dword ptr [rax+rax+00h]
0x1400642b2  cmp     rbx, rax
0x1400642b5  jnz     short loc_1400642BA
0x1400642b7  xor     r14b, r14b
0x1400642ba  mov     [rsi+128h], r14b
0x1400642c1  mov     eax, edi
0x1400642c3  add     rsp, 0B8h
0x1400642ca  pop     r15
0x1400642cc  pop     r14
0x1400642ce  pop     rdi
0x1400642cf  pop     rsi
0x1400642d0  pop     rbx
0x1400642d1  pop     rbp
0x1400642d2  retn
```
