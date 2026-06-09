# ItSrvInitialize

- ea: `0x180073c94`
- end: `0x180074128`
- name: `ItSrvInitialize`
- size: `1172`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f190`

## callees

- `0x18007254c`
- `0x180072b88`
- `0x180072ec0`
- `0x180073254`
- `0x180073c40`
- `0x180073c94`
- `0x180074918`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073e00`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180073d05`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180073d05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800740ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800740ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073fae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073fae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073dee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e52`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073eb1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073ed2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073dee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e52`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073e90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073eb1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073ed2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073dae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073dbb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073dc8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073dae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073dbb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073dc8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180073fbb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180073fbb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073fea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073fea`
- `ntdll!RtlInitializeSRWLock` at `0x180073eef`
- `ntdll!RtlInitializeSRWLock` at `0x180073eef`
- `RPCRT4!RpcServerUseProtseqW` at `0x180074050`
- `RPCRT4!RpcServerUseProtseqW` at `0x180074050`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180074097`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180074097`
- `RPCRT4!RpcServerInqBindings` at `0x180074067`
- `RPCRT4!RpcServerInqBindings` at `0x180074067`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800740ae`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800740ae`
- `RPCRT4!RpcEpRegisterW` at `0x1800740d5`
- `RPCRT4!RpcEpRegisterW` at `0x1800740d5`
- `POWRPROF!PowerDeterminePlatformRole` at `0x180073f2b`
- `POWRPROF!PowerDeterminePlatformRole` at `0x180073f2b`

## pseudocode

```c
__int64 ItSrvInitialize()
{
  char v0; // di
  BOOL Version; // ebx
  struct _ITSRV_GLOBAL_CONTEXT *v2; // rcx
  unsigned int LastError; // ebx
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int32 v6; // eax
  __int32 v7; // eax
  __int32 v8; // eax
  struct _ITSRV_GLOBAL_CONTEXT *v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v12; // [rsp+40h] [rbp-C0h]
  int v13; // [rsp+50h] [rbp-B0h]
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF
  char v15; // [rsp+17Ah] [rbp+7Ah]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  v0 = 0;
  memset_0(&ItSrvGlobalContext, 0, 0x368u);
  VersionInformation.dwOSVersionInfoSize = 284;
  stru_1800BD210.Blink = &stru_1800BD210;
  stru_1800BD210.Flink = &stru_1800BD210;
  Version = GetVersionExW(&VersionInformation);
  if ( !Version || (byte_1800BD492 = 1, v15 != 1) )
    byte_1800BD492 = 0;
  dword_1800BD394 &= 0xFFFFFFC0;
  dword_1800BD3EC &= 0xFFFFFFC0;
  ItSrvGlobalContext = 1147547697;
  xmmword_1800BD1C4 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  dword_1800BD3A0 = 0;
  qword_1800BD3A8 = 0;
  xmmword_1800BD1D4 = xmmword_1800BD1C4;
  dword_1800BD390 = -1;
  dword_1800BD3F8 = 0;
  qword_1800BD400 = 0;
  dword_1800BD3E8 = -1;
  memset_0(qword_1800BD440, 0, sizeof(qword_1800BD440));
  InitializeCriticalSection(&stru_1800BD1E8);
  InitializeCriticalSection(&stru_1800BD230);
  InitializeCriticalSection(&stru_1800BD260);
  stru_1800BD288.Blink = &stru_1800BD288;
  stru_1800BD288.Flink = &stru_1800BD288;
  hObject = CreateEventW(0, 1, 0, 0);
  if ( !hObject
    || (qword_1800BD310 = CreateEventW(0, 1, 1, 0)) == 0
    || (hHandle = CreateEventW(0, 1, 1, 0)) == 0
    || (qword_1800BD498 = CreateEventW(0, 1, 0, 0)) == 0
    || (qword_1800BD320 = CreateEventW(0, 1, 1, 0)) == 0
    || (qword_1800BD4A0 = CreateEventW(0, 1, 0, 0)) == 0
    || (hEvent = CreateEventW(0, 1, 0, 0)) == 0
    || (qword_1800BD220 = CreateEventW(0, 1, 1, 0)) == 0 )
  {
    LastError = GetLastError();
    goto LABEL_34;
  }
  RtlInitializeSRWLock(&qword_1800BD358);
  if ( Version )
  {
    if ( v15 != 1 )
    {
      v4 = xmmword_1800A8988;
      v5 = xmmword_1800A8998;
      goto LABEL_24;
    }
    v6 = PowerDeterminePlatformRole() - 1;
    if ( !v6 )
      goto LABEL_23;
    v7 = v6 - 1;
    if ( !v7 )
    {
      v4 = xmmword_1800A89AC;
      v5 = xmmword_1800A89BC;
      goto LABEL_24;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
LABEL_23:
      v4 = xmmword_1800A8964;
      v5 = xmmword_1800A8974;
      goto LABEL_24;
    }
    if ( v8 == 5 )
    {
      v4 = xmmword_1800A89D0;
      v5 = xmmword_1800A89E0;
      goto LABEL_24;
    }
  }
  v4 = xmmword_1800A8940;
  v5 = xmmword_1800A8950;
LABEL_24:
  v13 = 512;
  v12 = v5;
  v11 = v4;
  LastError = ItSpRetrieveDetectionOverrides((struct _IT_IDLE_DETECTION_PARAMETERS *)&v11);
  if ( LastError )
    goto LABEL_37;
  EnterCriticalSection(&stru_1800BD1E8);
  RtlAcquireSRWLockExclusive(&qword_1800BD358);
  dword_1800BD350 = v13;
  *(_OWORD *)byte_1800BD330 = v11;
  *(__int128 *)((char *)&xmmword_1800BD33C + 4) = v12;
  RtlReleaseSRWLockExclusive(&qword_1800BD358);
  byte_1800BD360 = 0;
  String1 = 0;
  dword_1800BD364 = 0;
  LastError = ItSpRetrieveRuntimeOverrides((struct _IT_IDLE_RUNTIME_PARAMETERS *)&byte_1800BD360);
  if ( !LastError )
  {
    v0 = 1;
    LastError = ItSpStartIdleDetection(v9);
    if ( !LastError )
    {
      ItSpUpdateStatus(&ItSrvGlobalContext, 1147547698);
      LastError = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0x100u, 0);
      if ( !LastError )
      {
        LastError = RpcServerInqBindings(&BindingVector);
        if ( !LastError )
        {
          LastError = RpcServerRegisterIfEx(qword_180087190, 0, 0, 9u, 0x4D2u, ItSpRpcSecurityCallback);
          if ( !LastError )
          {
            LastError = RpcServerRegisterAuthInfoW(0, 0xAu, 0, 0);
            if ( !LastError )
            {
              byte_1800BD491 = 1;
              LastError = RpcEpRegisterW(qword_180087190, BindingVector, 0, 0);
              if ( !LastError )
                byte_1800BD490 = 1;
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection(&stru_1800BD1E8);
LABEL_34:
  if ( LastError )
  {
    if ( v0 )
    {
      ItSrvUninitialize();
      return LastError;
    }
LABEL_37:
    ItSpCleanupGlobalContext(v2);
  }
  return LastError;
}

```

## disassembly

```asm
0x180073c94  push    rbp
0x180073c96  push    rbx
0x180073c97  push    rdi
0x180073c98  push    r14
0x180073c9a  lea     rbp, [rsp-98h]
0x180073ca2  sub     rsp, 198h
0x180073ca9  mov     rax, cs:__security_cookie
0x180073cb0  xor     rax, rsp
0x180073cb3  mov     [rbp+0B0h+var_30], rax
0x180073cba  xor     edx, edx; Val
0x180073cbc  lea     rcx, [rsp+1B0h+VersionInformation.dwMajorVersion]; void *
0x180073cc1  mov     r8d, 118h; Size
0x180073cc7  call    memset_0
0x180073ccc  xor     edx, edx; Val
0x180073cce  lea     rcx, ?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; void *
0x180073cd5  mov     r8d, 368h; Size
0x180073cdb  xor     dil, dil
0x180073cde  call    memset_0
0x180073ce3  lea     rax, stru_1800BD210
0x180073cea  mov     [rsp+1B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180073cf2  lea     rcx, [rsp+1B0h+VersionInformation]; lpVersionInformation
0x180073cf7  mov     cs:stru_1800BD210.Blink, rax
0x180073cfe  mov     cs:stru_1800BD210.Flink, rax
0x180073d05  call    cs:__imp_GetVersionExW
0x180073d0b  mov     ebx, eax
0x180073d0d  mov     r14d, 1
0x180073d13  test    eax, eax
0x180073d15  jz      short loc_180073D24
0x180073d17  mov     cs:byte_1800BD492, r14b
0x180073d1e  cmp     [rbp+0B0h+var_36], r14b
0x180073d22  jz      short loc_180073D2B
0x180073d24  mov     cs:byte_1800BD492, dil
0x180073d2b  movdqa  xmm0, cs:__xmm@44663031446630314466303144663031
0x180073d33  mov     ecx, 0FFFFFFC0h
0x180073d38  and     cs:dword_1800BD394, ecx
0x180073d3e  or      eax, 0FFFFFFFFh
0x180073d41  and     cs:dword_1800BD3EC, ecx
0x180073d47  xor     edx, edx; Val
0x180073d49  lea     rcx, qword_1800BD440; void *
0x180073d50  mov     cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A, 44663031h; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x180073d5a  movups  cs:xmmword_1800BD1C4, xmm0
0x180073d61  mov     cs:dword_1800BD3A0, 0
0x180073d6b  lea     r8d, [rdx+40h]; Size
0x180073d6f  mov     cs:qword_1800BD3A8, 0
0x180073d7a  movups  cs:xmmword_1800BD1D4, xmm0
0x180073d81  mov     cs:dword_1800BD390, eax
0x180073d87  mov     cs:dword_1800BD3F8, 0
0x180073d91  mov     cs:qword_1800BD400, 0
0x180073d9c  mov     cs:dword_1800BD3E8, eax
0x180073da2  call    memset_0
0x180073da7  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x180073dae  call    cs:__imp_InitializeCriticalSection
0x180073db4  lea     rcx, stru_1800BD230; lpCriticalSection
0x180073dbb  call    cs:__imp_InitializeCriticalSection
0x180073dc1  lea     rcx, stru_1800BD260; lpCriticalSection
0x180073dc8  call    cs:__imp_InitializeCriticalSection
0x180073dce  lea     rax, stru_1800BD288
0x180073dd5  xor     r9d, r9d; lpName
0x180073dd8  xor     r8d, r8d; bInitialState
0x180073ddb  mov     cs:stru_1800BD288.Blink, rax
0x180073de2  mov     edx, r14d; bManualReset
0x180073de5  mov     cs:stru_1800BD288.Flink, rax
0x180073dec  xor     ecx, ecx; lpEventAttributes
0x180073dee  call    cs:__imp_CreateEventW
0x180073df4  mov     cs:hObject, rax
0x180073dfb  test    rax, rax
0x180073dfe  jnz     short loc_180073E0D
0x180073e00  call    cs:__imp_GetLastError
0x180073e06  mov     ebx, eax
0x180073e08  jmp     loc_1800740F5
0x180073e0d  xor     r9d, r9d; lpName
0x180073e10  mov     r8d, r14d; bInitialState
0x180073e13  mov     edx, r14d; bManualReset
0x180073e16  xor     ecx, ecx; lpEventAttributes
0x180073e18  call    cs:__imp_CreateEventW
0x180073e1e  mov     cs:qword_1800BD310, rax
0x180073e25  test    rax, rax
0x180073e28  jz      short loc_180073E00
0x180073e2a  xor     r9d, r9d; lpName
0x180073e2d  mov     r8d, r14d; bInitialState
0x180073e30  mov     edx, r14d; bManualReset
0x180073e33  xor     ecx, ecx; lpEventAttributes
0x180073e35  call    cs:__imp_CreateEventW
0x180073e3b  mov     cs:hHandle, rax
0x180073e42  test    rax, rax
0x180073e45  jz      short loc_180073E00
0x180073e47  xor     r9d, r9d; lpName
0x180073e4a  xor     r8d, r8d; bInitialState
0x180073e4d  mov     edx, r14d; bManualReset
0x180073e50  xor     ecx, ecx; lpEventAttributes
0x180073e52  call    cs:__imp_CreateEventW
0x180073e58  mov     cs:qword_1800BD498, rax
0x180073e5f  test    rax, rax
0x180073e62  jz      short loc_180073E00
0x180073e64  xor     r9d, r9d; lpName
0x180073e67  mov     r8d, r14d; bInitialState
0x180073e6a  mov     edx, r14d; bManualReset
0x180073e6d  xor     ecx, ecx; lpEventAttributes
0x180073e6f  call    cs:__imp_CreateEventW
0x180073e75  mov     cs:qword_1800BD320, rax
0x180073e7c  test    rax, rax
0x180073e7f  jz      loc_180073E00
0x180073e85  xor     r9d, r9d; lpName
0x180073e88  xor     r8d, r8d; bInitialState
0x180073e8b  mov     edx, r14d; bManualReset
0x180073e8e  xor     ecx, ecx; lpEventAttributes
0x180073e90  call    cs:__imp_CreateEventW
0x180073e96  mov     cs:qword_1800BD4A0, rax
0x180073e9d  test    rax, rax
0x180073ea0  jz      loc_180073E00
0x180073ea6  xor     r9d, r9d; lpName
0x180073ea9  xor     r8d, r8d; bInitialState
0x180073eac  mov     edx, r14d; bManualReset
0x180073eaf  xor     ecx, ecx; lpEventAttributes
0x180073eb1  call    cs:__imp_CreateEventW
0x180073eb7  mov     cs:hEvent, rax
0x180073ebe  test    rax, rax
0x180073ec1  jz      loc_180073E00
0x180073ec7  xor     r9d, r9d; lpName
0x180073eca  mov     r8d, r14d; bInitialState
0x180073ecd  mov     edx, r14d; bManualReset
0x180073ed0  xor     ecx, ecx; lpEventAttributes
0x180073ed2  call    cs:__imp_CreateEventW
0x180073ed8  mov     cs:qword_1800BD220, rax
0x180073edf  test    rax, rax
0x180073ee2  jz      loc_180073E00
0x180073ee8  lea     rcx, qword_1800BD358
0x180073eef  call    cs:__imp_RtlInitializeSRWLock
0x180073ef5  test    ebx, ebx
0x180073ef7  jnz     short loc_180073F0F
0x180073ef9  movaps  xmm0, cs:xmmword_1800A8940
0x180073f00  movaps  xmm1, cs:xmmword_1800A8950
0x180073f07  mov     eax, cs:dword_1800A8960
0x180073f0d  jmp     short loc_180073F85
0x180073f0f  cmp     [rbp+0B0h+var_36], r14b
0x180073f13  jz      short loc_180073F2B
0x180073f15  movups  xmm0, cs:xmmword_1800A8988
0x180073f1c  mov     eax, cs:dword_1800A89A8
0x180073f22  movups  xmm1, cs:xmmword_1800A8998
0x180073f29  jmp     short loc_180073F85
0x180073f2b  call    cs:__imp_PowerDeterminePlatformRole
0x180073f31  sub     eax, r14d
0x180073f34  jz      short loc_180073F71
0x180073f36  sub     eax, r14d
0x180073f39  jz      short loc_180073F5B
0x180073f3b  sub     eax, r14d
0x180073f3e  jz      short loc_180073F71
0x180073f40  cmp     eax, 5
0x180073f43  jnz     short loc_180073EF9
0x180073f45  movaps  xmm0, cs:xmmword_1800A89D0
0x180073f4c  movaps  xmm1, cs:xmmword_1800A89E0
0x180073f53  mov     eax, cs:dword_1800A89F0
0x180073f59  jmp     short loc_180073F85
0x180073f5b  movups  xmm0, cs:xmmword_1800A89AC
0x180073f62  mov     eax, cs:dword_1800A89CC
0x180073f68  movups  xmm1, cs:xmmword_1800A89BC
0x180073f6f  jmp     short loc_180073F85
0x180073f71  movups  xmm0, cs:xmmword_1800A8964
0x180073f78  mov     eax, cs:dword_1800A8984
0x180073f7e  movups  xmm1, cs:xmmword_1800A8974
0x180073f85  lea     rcx, [rsp+1B0h+var_180]; struct _IT_IDLE_DETECTION_PARAMETERS *
0x180073f8a  mov     [rsp+1B0h+var_160], eax
0x180073f8e  movups  [rsp+1B0h+var_170], xmm1
0x180073f93  movups  [rsp+1B0h+var_180], xmm0
0x180073f98  call    ?ItSpRetrieveDetectionOverrides@@YAKPEAU_IT_IDLE_DETECTION_PARAMETERS@@@Z; ItSpRetrieveDetectionOverrides(_IT_IDLE_DETECTION_PARAMETERS *)
0x180073f9d  mov     ebx, eax
0x180073f9f  test    eax, eax
0x180073fa1  jnz     loc_180074105
0x180073fa7  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x180073fae  call    cs:__imp_EnterCriticalSection
0x180073fb4  lea     rcx, qword_1800BD358
0x180073fbb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180073fc1  movups  xmm0, [rsp+1B0h+var_180]
0x180073fc6  mov     eax, [rsp+1B0h+var_160]
0x180073fca  lea     rcx, qword_1800BD358
0x180073fd1  movups  xmm1, [rsp+1B0h+var_170]
0x180073fd6  mov     cs:dword_1800BD350, eax
0x180073fdc  movaps  xmmword ptr cs:byte_1800BD330, xmm0
0x180073fe3  movaps  cs:xmmword_1800BD33C+4, xmm1
0x180073fea  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180073ff0  lea     rcx, byte_1800BD360; struct _IT_IDLE_RUNTIME_PARAMETERS *
0x180073ff7  mov     cs:byte_1800BD360, dil
0x180073ffe  mov     cs:String1, 0
0x180074009  mov     cs:dword_1800BD364, ebx
0x18007400f  call    ?ItSpRetrieveRuntimeOverrides@@YAKPEAU_IT_IDLE_RUNTIME_PARAMETERS@@@Z; ItSpRetrieveRuntimeOverrides(_IT_IDLE_RUNTIME_PARAMETERS *)
0x180074014  mov     ebx, eax
0x180074016  test    eax, eax
0x180074018  jnz     loc_1800740E8
0x18007401e  mov     dil, r14b
0x180074021  call    ?ItSpStartIdleDetection@@YAKPEAU_ITSRV_GLOBAL_CONTEXT@@@Z; ItSpStartIdleDetection(_ITSRV_GLOBAL_CONTEXT *)
0x180074026  mov     ebx, eax
0x180074028  test    eax, eax
0x18007402a  jnz     loc_1800740E8
0x180074030  mov     edx, 44663032h
0x180074035  lea     rcx, ?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x18007403c  call    ?ItSpUpdateStatus@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@W4_ITSRV_GLOBAL_CONTEXT_STATUS@@@Z; ItSpUpdateStatus(_ITSRV_GLOBAL_CONTEXT *,_ITSRV_GLOBAL_CONTEXT_STATUS)
0x180074041  xor     r8d, r8d; SecurityDescriptor
0x180074044  lea     rcx, aNcalrpc; "ncalrpc"
0x18007404b  mov     edx, 100h; MaxCalls
0x180074050  call    cs:__imp_RpcServerUseProtseqW
0x180074056  mov     ebx, eax
0x180074058  test    eax, eax
0x18007405a  jnz     loc_1800740E8
0x180074060  lea     rcx, BindingVector; BindingVector
0x180074067  call    cs:__imp_RpcServerInqBindings
0x18007406d  mov     ebx, eax
0x18007406f  test    eax, eax
0x180074071  jnz     short loc_1800740E8
0x180074073  lea     rax, ?ItSpRpcSecurityCallback@@YAJPEAX0@Z; ItSpRpcSecurityCallback(void *,void *)
0x18007407a  xor     r8d, r8d; MgrEpv
0x18007407d  mov     [rsp+1B0h+IfCallback], rax; IfCallback
0x180074082  lea     r9d, [rbx+9]; Flags
0x180074086  xor     edx, edx; MgrTypeUuid
0x180074088  mov     [rsp+1B0h+MaxCalls], 4D2h; MaxCalls
0x180074090  lea     rcx, qword_180087190; IfSpec
0x180074097  call    cs:__imp_RpcServerRegisterIfEx
0x18007409d  mov     ebx, eax
0x18007409f  test    eax, eax
0x1800740a1  jnz     short loc_1800740E8
0x1800740a3  xor     r9d, r9d; Arg
0x1800740a6  lea     edx, [rax+0Ah]; AuthnSvc
0x1800740a9  xor     r8d, r8d; GetKeyFn
0x1800740ac  xor     ecx, ecx; ServerPrincName
0x1800740ae  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800740b4  mov     ebx, eax
0x1800740b6  test    eax, eax
0x1800740b8  jnz     short loc_1800740E8
0x1800740ba  mov     rdx, cs:BindingVector; BindingVector
0x1800740c1  lea     rcx, qword_180087190; IfSpec
0x1800740c8  xor     r9d, r9d; Annotation
0x1800740cb  mov     cs:byte_1800BD491, r14b
0x1800740d2  xor     r8d, r8d; UuidVector
0x1800740d5  call    cs:__imp_RpcEpRegisterW
0x1800740db  mov     ebx, eax
0x1800740dd  test    eax, eax
0x1800740df  jnz     short loc_1800740E8
0x1800740e1  mov     cs:byte_1800BD490, r14b
0x1800740e8  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x1800740ef  call    cs:__imp_LeaveCriticalSection
0x1800740f5  test    ebx, ebx
0x1800740f7  jz      short loc_18007410A
0x1800740f9  test    dil, dil
0x1800740fc  jz      short loc_180074105
0x1800740fe  call    ItSrvUninitialize
0x180074103  jmp     short loc_18007410A
0x180074105  call    ?ItSpCleanupGlobalContext@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@@Z; ItSpCleanupGlobalContext(_ITSRV_GLOBAL_CONTEXT *)
0x18007410a  mov     eax, ebx
0x18007410c  mov     rcx, [rbp+0B0h+var_30]
0x180074113  xor     rcx, rsp; StackCookie
0x180074116  call    __security_check_cookie
0x18007411b  add     rsp, 198h
0x180074122  pop     r14
0x180074124  pop     rdi
0x180074125  pop     rbx
0x180074126  pop     rbp
0x180074127  retn
```
