# ScStartTracingSession(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x140031618`
- end: `0x140031ab9`
- name: `?ScStartTracingSession@@YAKPEBG000@Z`
- size: `1185`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400848e0`

## callees

- `0x140004c58`
- `0x140008b90`
- `0x14001df34`
- `0x140031618`
- `0x140031ac0`
- `0x1400575b0`
- `0x140058030`
- `0x140086dd8`
- `0x140086e24`
- `0x1400873e8`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140031a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140031a94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031a86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031888`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031703`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400317c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031806`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031703`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400317c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031806`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400316c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400316c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031a7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031a7b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14003183f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14003183f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003190a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140031929`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14003190a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140031929`
- `ntdll!RtlInitUnicodeString` at `0x140031856`
- `ntdll!RtlInitUnicodeString` at `0x140031856`
- `ntdll!RtlUnicodeStringToInteger` at `0x14003186b`
- `ntdll!RtlUnicodeStringToInteger` at `0x14003186b`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140031999`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140031999`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x14003193e`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x14003193e`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031978`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031a34`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031978`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x140031a34`

## pseudocode

```c
__int64 __fastcall ScStartTracingSession(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct _EVENT_TRACE_PROPERTIES *v4; // rdi
  const unsigned __int16 *v5; // rdx
  const unsigned __int16 *v6; // rcx
  unsigned int FullLogPath; // ebx
  int v8; // eax
  struct _EVENT_TRACE_PROPERTIES *v9; // rax
  const unsigned __int16 *v10; // rdx
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  HANDLE ProcessHeap; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v18[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Value; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  ULONG64 TraceHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[8]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  wchar_t Str[264]; // [rsp+A0h] [rbp-60h] BYREF

  cbData = 0;
  Type = 0;
  Value = 0;
  *(_DWORD *)v19 = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v18 = 0;
  v4 = 0;
  DestinationString = 0;
  v26 = 0;
  *(_OWORD *)Buffer = 0;
  TraceHandle = 0;
  v25 = 0;
  hKey = 0;
  memset(Str, 0, 0x208u);
  FullLogPath = ScGetFullLogPath(v6, v5, Str);
  if ( FullLogPath )
    goto LABEL_33;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\SCM\\Regular",
         0,
         0x20019u,
         &hKey) )
  {
    *(_DWORD *)Data = 0;
    *(_DWORD *)v19 = 267646975;
  }
  else
  {
    cbData = 4;
    FullLogPath = RegQueryValueExW(hKey, L"TracingDisabled", 0, &Type, Data, &cbData);
    if ( FullLogPath || Type != 4 )
    {
      v8 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v8 = *(_DWORD *)Data;
    }
    if ( v8 )
    {
      qword_1400BC500 = 0;
      WPP_MAIN_CB = (__int64)&qword_1400BC518;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_Regular;
      qword_1400BC4E8 = (__int64)WPP_ThisDir_CTLGUID_UmdfTraceGuid;
      WPP_GLOBAL_Control = (PRPC_ASYNC_STATE)&WPP_MAIN_CB;
      qword_1400BC508 = 1;
      qword_1400BC528 = 0;
      qword_1400BC518 = 0;
      qword_1400BC530 = 1;
      WppInitUm();
      goto LABEL_33;
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Flags", 0, &Type, v19, &cbData) || Type != 4 )
      *(_DWORD *)v19 = 267646975;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TracingBuffers", 0, &Type, v18, &cbData) && Type == 4 )
      goto LABEL_17;
  }
  *(_DWORD *)v18 = 10;
LABEL_17:
  if ( GetEnvironmentVariableW(L"SCMLogSize", Buffer, 0x14u) - 1 > 0x12 )
  {
    Value = 5;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, Buffer);
    RtlUnicodeStringToInteger(&DestinationString, 0xAu, &Value);
  }
  v9 = ScAllocSessionProperties();
  v4 = v9;
  if ( v9 )
  {
    StringCchCopyW((unsigned __int16 *)((char *)v9 + v9->LogFileNameOffset), 0x104u, Str);
    v4->LogFileMode |= 0x10000002u;
    v4->MaximumFileSize = Value;
    v4->BufferSize = 128;
    v4->MinimumBuffers = *(_DWORD *)v18;
    v4->MaximumBuffers = 25;
    ScBackupTraceFile(Str, v10);
    v11 = wcsrchr(Str, 0x5Cu);
    if ( v11 )
      *v11 = 0;
    v12 = wcsrchr(Str, 0x5Cu);
    if ( v12 )
      *v12 = 0;
    CreateDirectoryW(Str, 0);
    StringCchCatW(Str, 0x104u, L"\\Scm\\");
    CreateDirectoryW(Str, 0);
    FullLogPath = StartTraceW(&TraceHandle, L"SCM", v4);
    if ( !FullLogPath )
    {
      FullLogPath = EnableTraceEx2(TraceHandle, &ScmWppLoggingGuid, 1u, 0, *(unsigned int *)v19, 0, 0, 0);
      if ( FullLogPath )
      {
        ControlTraceW(TraceHandle, L"SCM", v4, 1u);
      }
      else
      {
        qword_1400BC500 = 0;
        WPP_MAIN_CB = (__int64)&qword_1400BC518;
        WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_Regular;
        qword_1400BC4E8 = (__int64)WPP_ThisDir_CTLGUID_UmdfTraceGuid;
        WPP_GLOBAL_Control = (PRPC_ASYNC_STATE)&WPP_MAIN_CB;
        qword_1400BC508 = 1;
        qword_1400BC528 = 0;
        qword_1400BC518 = 0;
        qword_1400BC530 = 1;
        WppInitUm();
        FullLogPath = EnableTraceEx2(TraceHandle, &ScmTraceLoggingGuid, 1u, 5u, 0, 0, 0, 0);
        if ( FullLogPath
          && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 10, WPP_e76593a1149539588ac687e1e1cef570_Traceguids, FullLogPath);
        }
      }
    }
  }
  else
  {
    FullLogPath = GetLastError();
  }
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return FullLogPath;
}

```

## disassembly

```asm
0x140031618  push    rbp
0x14003161a  push    rbx
0x14003161b  push    rsi
0x14003161c  push    rdi
0x14003161d  push    r14
0x14003161f  lea     rbp, [rsp-1C0h]
0x140031627  sub     rsp, 2C0h
0x14003162e  mov     rax, cs:__security_cookie
0x140031635  xor     rax, rsp
0x140031638  mov     [rbp+1E0h+var_30], rax
0x14003163f  xor     esi, esi
0x140031641  lea     rcx, [rbp+1E0h+Str]; void *
0x140031645  xorps   xmm1, xmm1
0x140031648  mov     [rsp+2E0h+cbData], esi
0x14003164c  xorps   xmm0, xmm0
0x14003164f  mov     [rsp+2E0h+Type], esi
0x140031653  xor     eax, eax
0x140031655  mov     [rsp+2E0h+Value], esi
0x140031659  xor     edx, edx; Val
0x14003165b  mov     dword ptr [rsp+2E0h+var_290], esi
0x14003165f  mov     r8d, 208h; Size
0x140031665  mov     dword ptr [rsp+2E0h+Data], esi
0x140031669  mov     dword ptr [rsp+2E0h+var_294], esi
0x14003166d  mov     edi, esi
0x14003166f  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x140031674  mov     [rbp+1E0h+var_248], rax
0x140031678  movups  xmmword ptr [rsp+2E0h+Buffer], xmm1
0x14003167d  mov     [rsp+2E0h+TraceHandle], rsi
0x140031682  movups  [rbp+1E0h+var_258], xmm1
0x140031686  mov     [rsp+2E0h+hKey], rsi
0x14003168b  call    memset
0x140031690  lea     r8, [rbp+1E0h+Str]; unsigned __int16 *
0x140031694  call    ?ScGetFullLogPath@@YAKPEBG0PEAG@Z; ScGetFullLogPath(ushort const *,ushort const *,ushort *)
0x140031699  mov     ebx, eax
0x14003169b  test    eax, eax
0x14003169d  jnz     loc_140031A71
0x1400316a3  lea     rax, [rsp+2E0h+hKey]
0x1400316a8  mov     r9d, 20019h; samDesired
0x1400316ae  xor     r8d, r8d; ulOptions
0x1400316b1  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1400316b6  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400316bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400316c4  call    cs:__imp_RegOpenKeyExW
0x1400316ca  test    eax, eax
0x1400316cc  jnz     loc_140031819
0x1400316d2  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400316d7  lea     rax, [rsp+2E0h+cbData]
0x1400316dc  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1400316e1  lea     r14d, [rsi+4]
0x1400316e5  lea     rax, [rsp+2E0h+Data]
0x1400316ea  mov     [rsp+2E0h+cbData], r14d
0x1400316ef  lea     r9, [rsp+2E0h+Type]; lpType
0x1400316f4  mov     [rsp+2E0h+phkResult], rax; lpData
0x1400316f9  xor     r8d, r8d; lpReserved
0x1400316fc  lea     rdx, aTracingdisable; "TracingDisabled"
0x140031703  call    cs:__imp_RegQueryValueExW
0x140031709  mov     ebx, eax
0x14003170b  test    eax, eax
0x14003170d  jnz     short loc_14003171C
0x14003170f  cmp     [rsp+2E0h+Type], r14d
0x140031714  jnz     short loc_14003171C
0x140031716  mov     eax, dword ptr [rsp+2E0h+Data]
0x14003171a  jmp     short loc_140031722
0x14003171c  mov     eax, esi
0x14003171e  mov     dword ptr [rsp+2E0h+Data], eax
0x140031722  test    eax, eax
0x140031724  jz      short loc_140031793
0x140031726  lea     rax, qword_1400BC518
0x14003172d  mov     cs:qword_1400BC500, rsi
0x140031734  mov     cs:WPP_MAIN_CB, rax
0x14003173b  lea     rax, WPP_ThisDir_CTLGUID_Regular
0x140031742  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140031749  lea     rax, WPP_ThisDir_CTLGUID_UmdfTraceGuid
0x140031750  mov     cs:qword_1400BC4E8, rax
0x140031757  lea     rax, WPP_MAIN_CB
0x14003175e  mov     cs:WPP_GLOBAL_Control, rax
0x140031765  mov     cs:qword_1400BC508, 1
0x140031770  mov     cs:qword_1400BC528, rsi
0x140031777  mov     cs:qword_1400BC518, rsi
0x14003177e  mov     cs:qword_1400BC530, 1
0x140031789  call    WppInitUm
0x14003178e  jmp     loc_140031A71
0x140031793  mov     rcx, [rsp+2E0h+hKey]; hKey
0x140031798  lea     rax, [rsp+2E0h+cbData]
0x14003179d  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1400317a2  lea     r9, [rsp+2E0h+Type]; lpType
0x1400317a7  lea     rax, [rsp+2E0h+var_290]
0x1400317ac  mov     [rsp+2E0h+cbData], r14d
0x1400317b1  xor     r8d, r8d; lpReserved
0x1400317b4  mov     [rsp+2E0h+phkResult], rax; lpData
0x1400317b9  lea     rdx, aFlags; "Flags"
0x1400317c0  call    cs:__imp_RegQueryValueExW
0x1400317c6  test    eax, eax
0x1400317c8  jnz     short loc_1400317D1
0x1400317ca  cmp     [rsp+2E0h+Type], r14d
0x1400317cf  jz      short loc_1400317D9
0x1400317d1  mov     dword ptr [rsp+2E0h+var_290], 0FF3F7FFh
0x1400317d9  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400317de  lea     rax, [rsp+2E0h+cbData]
0x1400317e3  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1400317e8  lea     r9, [rsp+2E0h+Type]; lpType
0x1400317ed  lea     rax, [rsp+2E0h+var_294]
0x1400317f2  mov     [rsp+2E0h+cbData], r14d
0x1400317f7  xor     r8d, r8d; lpReserved
0x1400317fa  mov     [rsp+2E0h+phkResult], rax; lpData
0x1400317ff  lea     rdx, aTracingbuffers; "TracingBuffers"
0x140031806  call    cs:__imp_RegQueryValueExW
0x14003180c  test    eax, eax
0x14003180e  jnz     short loc_140031825
0x140031810  cmp     [rsp+2E0h+Type], r14d
0x140031815  jnz     short loc_140031825
0x140031817  jmp     short loc_14003182D
0x140031819  mov     dword ptr [rsp+2E0h+Data], esi
0x14003181d  mov     dword ptr [rsp+2E0h+var_290], 0FF3F7FFh
0x140031825  mov     dword ptr [rsp+2E0h+var_294], 0Ah
0x14003182d  mov     r8d, 14h; nSize
0x140031833  lea     rdx, [rsp+2E0h+Buffer]; lpBuffer
0x140031838  lea     rcx, aScmlogsize; "SCMLogSize"
0x14003183f  call    cs:__imp_GetEnvironmentVariableW
0x140031845  dec     eax
0x140031847  cmp     eax, 12h
0x14003184a  ja      short loc_140031873
0x14003184c  lea     rdx, [rsp+2E0h+Buffer]; SourceString
0x140031851  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x140031856  call    cs:__imp_RtlInitUnicodeString
0x14003185c  lea     r8, [rsp+2E0h+Value]; Value
0x140031861  mov     edx, 0Ah; Base
0x140031866  lea     rcx, [rsp+2E0h+DestinationString]; String
0x14003186b  call    cs:__imp_RtlUnicodeStringToInteger
0x140031871  jmp     short loc_14003187B
0x140031873  mov     [rsp+2E0h+Value], 5
0x14003187b  call    ?ScAllocSessionProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ; ScAllocSessionProperties(void)
0x140031880  mov     rdi, rax
0x140031883  test    rax, rax
0x140031886  jnz     short loc_140031895
0x140031888  call    cs:__imp_GetLastError
0x14003188e  mov     ebx, eax
0x140031890  jmp     loc_140031A71
0x140031895  mov     ecx, [rax+70h]
0x140031898  lea     r8, [rbp+1E0h+Str]; unsigned __int16 *
0x14003189c  mov     r14d, 104h
0x1400318a2  add     rcx, rdi; unsigned __int16 *
0x1400318a5  mov     edx, r14d; unsigned __int64
0x1400318a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400318ad  or      dword ptr [rdi+40h], 10000002h
0x1400318b4  lea     rcx, [rbp+1E0h+Str]; unsigned __int16 *
0x1400318b8  mov     eax, [rsp+2E0h+Value]
0x1400318bc  mov     [rdi+3Ch], eax
0x1400318bf  mov     dword ptr [rdi+30h], 80h
0x1400318c6  mov     eax, dword ptr [rsp+2E0h+var_294]
0x1400318ca  mov     [rdi+34h], eax
0x1400318cd  mov     dword ptr [rdi+38h], 19h
0x1400318d4  call    ?ScBackupTraceFile@@YAXPEBG0@Z; ScBackupTraceFile(ushort const *,ushort const *)
0x1400318d9  mov     ebx, 5Ch ; '\'
0x1400318de  lea     rcx, [rbp+1E0h+Str]; Str
0x1400318e2  mov     edx, ebx; Ch
0x1400318e4  call    wcsrchr
0x1400318e9  test    rax, rax
0x1400318ec  jz      short loc_1400318F1
0x1400318ee  mov     [rax], si
0x1400318f1  mov     edx, ebx; Ch
0x1400318f3  lea     rcx, [rbp+1E0h+Str]; Str
0x1400318f7  call    wcsrchr
0x1400318fc  test    rax, rax
0x1400318ff  jz      short loc_140031904
0x140031901  mov     [rax], si
0x140031904  xor     edx, edx; lpSecurityAttributes
0x140031906  lea     rcx, [rbp+1E0h+Str]; lpPathName
0x14003190a  call    cs:__imp_CreateDirectoryW
0x140031910  lea     r8, aScm; "\\Scm\\"
0x140031917  mov     rdx, r14; unsigned __int64
0x14003191a  lea     rcx, [rbp+1E0h+Str]; unsigned __int16 *
0x14003191e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140031923  xor     edx, edx; lpSecurityAttributes
0x140031925  lea     rcx, [rbp+1E0h+Str]; lpPathName
0x140031929  call    cs:__imp_CreateDirectoryW
0x14003192f  mov     r8, rdi; Properties
0x140031932  lea     rdx, InstanceName; "SCM"
0x140031939  lea     rcx, [rsp+2E0h+TraceHandle]; TraceHandle
0x14003193e  call    cs:__imp_StartTraceW
0x140031944  mov     ebx, eax
0x140031946  test    eax, eax
0x140031948  jnz     loc_140031A71
0x14003194e  mov     eax, dword ptr [rsp+2E0h+var_290]
0x140031952  lea     r8d, [rbx+1]; ControlCode
0x140031956  mov     rcx, [rsp+2E0h+TraceHandle]; TraceHandle
0x14003195b  lea     rdx, ScmWppLoggingGuid; ProviderId
0x140031962  mov     [rsp+2E0h+EnableParameters], rsi; EnableParameters
0x140031967  xor     r9d, r9d; Level
0x14003196a  mov     [rsp+2E0h+Timeout], esi; Timeout
0x14003196e  mov     [rsp+2E0h+lpcbData], rsi; MatchAllKeyword
0x140031973  mov     [rsp+2E0h+phkResult], rax; MatchAnyKeyword
0x140031978  call    cs:__imp_EnableTraceEx2
0x14003197e  mov     ebx, eax
0x140031980  test    eax, eax
0x140031982  jz      short loc_1400319A4
0x140031984  mov     rcx, [rsp+2E0h+TraceHandle]; TraceHandle
0x140031989  lea     rdx, InstanceName; "SCM"
0x140031990  mov     r9d, 1; ControlCode
0x140031996  mov     r8, rdi; Properties
0x140031999  call    cs:__imp_ControlTraceW
0x14003199f  jmp     loc_140031A71
0x1400319a4  lea     rax, qword_1400BC518
0x1400319ab  mov     cs:qword_1400BC500, rsi
0x1400319b2  mov     cs:WPP_MAIN_CB, rax
0x1400319b9  lea     rax, WPP_ThisDir_CTLGUID_Regular
0x1400319c0  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1400319c7  lea     rax, WPP_ThisDir_CTLGUID_UmdfTraceGuid
0x1400319ce  mov     cs:qword_1400BC4E8, rax
0x1400319d5  lea     rax, WPP_MAIN_CB
0x1400319dc  mov     cs:WPP_GLOBAL_Control, rax
0x1400319e3  mov     cs:qword_1400BC508, 1
0x1400319ee  mov     cs:qword_1400BC528, rsi
0x1400319f5  mov     cs:qword_1400BC518, rsi
0x1400319fc  mov     cs:qword_1400BC530, 1
0x140031a07  call    WppInitUm
0x140031a0c  mov     rcx, [rsp+2E0h+TraceHandle]; TraceHandle
0x140031a11  lea     rdx, ScmTraceLoggingGuid; ProviderId
0x140031a18  mov     [rsp+2E0h+EnableParameters], rsi; EnableParameters
0x140031a1d  mov     r9b, 5; Level
0x140031a20  mov     [rsp+2E0h+Timeout], esi; Timeout
0x140031a24  mov     r8d, 1; ControlCode
0x140031a2a  mov     [rsp+2E0h+lpcbData], rsi; MatchAllKeyword
0x140031a2f  mov     [rsp+2E0h+phkResult], rsi; MatchAnyKeyword
0x140031a34  call    cs:__imp_EnableTraceEx2
0x140031a3a  mov     ebx, eax
0x140031a3c  test    eax, eax
0x140031a3e  jz      short loc_140031A71
0x140031a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a47  lea     rax, WPP_GLOBAL_Control
0x140031a4e  cmp     rcx, rax
0x140031a51  jz      short loc_140031A71
0x140031a53  test    byte ptr [rcx+1Ch], 1
0x140031a57  jz      short loc_140031A71
0x140031a59  mov     rcx, [rcx+10h]
0x140031a5d  lea     r8, WPP_e76593a1149539588ac687e1e1cef570_Traceguids
0x140031a64  mov     edx, 0Ah
0x140031a69  mov     r9d, ebx
0x140031a6c  call    WPP_SF_d
0x140031a71  mov     rcx, [rsp+2E0h+hKey]; hKey
0x140031a76  test    rcx, rcx
0x140031a79  jz      short loc_140031A81
0x140031a7b  call    cs:__imp_RegCloseKey
0x140031a81  test    rdi, rdi
0x140031a84  jz      short loc_140031A9A
0x140031a86  call    cs:__imp_GetProcessHeap
0x140031a8c  mov     r8, rdi; lpMem
0x140031a8f  xor     edx, edx; dwFlags
0x140031a91  mov     rcx, rax; hHeap
0x140031a94  call    cs:__imp_HeapFree
0x140031a9a  mov     eax, ebx
0x140031a9c  mov     rcx, [rbp+1E0h+var_30]
0x140031aa3  xor     rcx, rsp; StackCookie
0x140031aa6  call    __security_check_cookie
0x140031aab  add     rsp, 2C0h
0x140031ab2  pop     r14
0x140031ab4  pop     rdi
0x140031ab5  pop     rsi
0x140031ab6  pop     rbx
0x140031ab7  pop     rbp
0x140031ab8  retn
```
