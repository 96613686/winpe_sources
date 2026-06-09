# UmpoAlpcInit

- ea: `0x180011790`
- end: `0x18001190f`
- name: `UmpoAlpcInit`
- size: `383`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed10`

## callees

- `0x180010070`
- `0x180010946`
- `0x180011790`
- `0x180011918`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180011816`
- `ntdll!RtlInitUnicodeString` at `0x180011816`
- `ntdll!NtAlpcConnectPort` at `0x180011896`
- `ntdll!NtAlpcConnectPort` at `0x180011896`
- `ntdll!TpAllocAlpcCompletion` at `0x1800118c1`
- `ntdll!TpAllocAlpcCompletion` at `0x1800118c1`
- `ntdll!RtlNtStatusToDosError` at `0x1800118cd`
- `ntdll!RtlNtStatusToDosError` at `0x1800118cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800117ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800117ed`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800117ce`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800117ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117ff`
- `KERNELBASE!WTSIsServerContainer` at `0x1800117d4`
- `KERNELBASE!WTSIsServerContainer` at `0x1800117d4`

## pseudocode

```c
__int64 UmpoAlpcInit()
{
  DWORD LastError; // eax
  NTSTATUS v1; // eax
  DWORD v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-78h] BYREF
  _DWORD v5[4]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v6; // [rsp+80h] [rbp-58h]
  __int64 v7; // [rsp+90h] [rbp-48h]

  DestinationString = 0;
  memset_0(v5, 0, 0x48u);
  InitializeSRWLock(&UmpoAlpcPoPortLock);
  if ( (unsigned __int8)WTSIsServerContainer() )
    return 0;
  UmpoAlpcEvent = CreateEventW(0, 1, 0, 0);
  if ( !UmpoAlpcEvent )
  {
    LastError = GetLastError();
    goto LABEL_7;
  }
  RtlInitUnicodeString(&DestinationString, L"\\PowerPort");
  memset_0(v5, 0, 0x48u);
  v6 = 4096;
  v7 = 0x20000;
  v5[0] = 0x20000;
  v1 = NtAlpcConnectPort(&UmpoAlpcPoPort, &DestinationString, 0, v5, 0x20000, 0, 0, 0, 0, 0, 0);
  if ( v1 >= 0 )
  {
    v1 = TpAllocAlpcCompletion(&UmpoAlpcCompletion, UmpoAlpcPoPort, UmpoAlpcCalback, 0, 0);
    if ( v1 >= 0 )
      return 0;
  }
  LastError = RtlNtStatusToDosError(v1);
LABEL_7:
  v2 = LastError;
  if ( LastError )
  {
    UmpoAlpcReleaseResources(UmpoAlpcPoPort);
    UmpoAlpcPoPort = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180011790  push    rbx
0x180011792  sub     rsp, 0D0h
0x180011799  mov     rax, cs:__security_cookie
0x1800117a0  xor     rax, rsp
0x1800117a3  mov     [rsp+0D8h+var_18], rax
0x1800117ab  xorps   xmm0, xmm0
0x1800117ae  lea     rcx, [rsp+0D8h+var_68]; void *
0x1800117b3  mov     ebx, 48h ; 'H'
0x1800117b8  xor     edx, edx; Val
0x1800117ba  mov     r8d, ebx; Size
0x1800117bd  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x1800117c2  call    memset_0
0x1800117c7  lea     rcx, UmpoAlpcPoPortLock; SRWLock
0x1800117ce  call    cs:__imp_InitializeSRWLock
0x1800117d4  call    cs:__imp_WTSIsServerContainer
0x1800117da  test    al, al
0x1800117dc  jnz     loc_1800118F2
0x1800117e2  xor     r9d, r9d; lpName
0x1800117e5  lea     edx, [rbx-47h]; bManualReset
0x1800117e8  xor     r8d, r8d; bInitialState
0x1800117eb  xor     ecx, ecx; lpEventAttributes
0x1800117ed  call    cs:__imp_CreateEventW
0x1800117f3  mov     cs:UmpoAlpcEvent, rax
0x1800117fa  test    rax, rax
0x1800117fd  jnz     short loc_18001180A
0x1800117ff  call    cs:__imp_GetLastError
0x180011805  jmp     loc_1800118D3
0x18001180a  lea     rdx, SourceString; "\\PowerPort"
0x180011811  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180011816  call    cs:__imp_RtlInitUnicodeString
0x18001181c  mov     r8, rbx; Size
0x18001181f  lea     rcx, [rsp+0D8h+var_68]; void *
0x180011824  xor     edx, edx; Val
0x180011826  call    memset_0
0x18001182b  mov     [rsp+0D8h+var_88], 0
0x180011834  lea     r9, [rsp+0D8h+var_68]
0x180011839  mov     [rsp+0D8h+var_90], 0
0x180011842  lea     rdx, [rsp+0D8h+DestinationString]
0x180011847  mov     [rsp+0D8h+var_98], 0
0x180011850  lea     rcx, UmpoAlpcPoPort
0x180011857  mov     eax, 20000h
0x18001185c  mov     [rsp+0D8h+var_A0], 0
0x180011865  mov     [rsp+0D8h+var_A8], 0
0x18001186e  xor     r8d, r8d
0x180011871  mov     [rsp+0D8h+var_B0], 0
0x18001187a  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18001187e  mov     [rsp+0D8h+var_58], 1000h
0x18001188a  mov     [rsp+0D8h+var_48], rax
0x180011892  mov     [rsp+0D8h+var_68], eax
0x180011896  call    cs:__imp_NtAlpcConnectPort
0x18001189c  test    eax, eax
0x18001189e  js      short loc_1800118CB
0x1800118a0  mov     rdx, cs:UmpoAlpcPoPort
0x1800118a7  lea     r8, UmpoAlpcCalback
0x1800118ae  xor     r9d, r9d
0x1800118b1  mov     [rsp+0D8h+var_B8], 0
0x1800118ba  lea     rcx, UmpoAlpcCompletion
0x1800118c1  call    cs:__imp_TpAllocAlpcCompletion
0x1800118c7  test    eax, eax
0x1800118c9  jns     short loc_1800118F2
0x1800118cb  mov     ecx, eax; Status
0x1800118cd  call    cs:__imp_RtlNtStatusToDosError
0x1800118d3  mov     ebx, eax
0x1800118d5  test    eax, eax
0x1800118d7  jz      short loc_1800118F4
0x1800118d9  mov     rcx, cs:UmpoAlpcPoPort; hObject
0x1800118e0  call    UmpoAlpcReleaseResources
0x1800118e5  mov     cs:UmpoAlpcPoPort, 0
0x1800118f0  jmp     short loc_1800118F4
0x1800118f2  xor     ebx, ebx
0x1800118f4  mov     eax, ebx
0x1800118f6  mov     rcx, [rsp+0D8h+var_18]
0x1800118fe  xor     rcx, rsp; StackCookie
0x180011901  call    __security_check_cookie
0x180011906  add     rsp, 0D0h
0x18001190d  pop     rbx
0x18001190e  retn
```
