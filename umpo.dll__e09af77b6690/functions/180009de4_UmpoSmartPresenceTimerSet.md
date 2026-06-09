# UmpoSmartPresenceTimerSet

- ea: `0x180009de4`
- end: `0x180009f0c`
- name: `UmpoSmartPresenceTimerSet`
- size: `296`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009390`
- `0x180009d8c`

## callees

- `0x18000950c`
- `0x180009de4`
- `0x18000f3dc`

## import_xrefs

- `ntdll!DbgPrint` at `0x180009ec7`
- `ntdll!DbgPrint` at `0x180009ec7`
- `ntdll!RtlNtStatusToDosError` at `0x180009e34`
- `ntdll!RtlNtStatusToDosError` at `0x180009e34`
- `ntdll!NtSetIRTimer` at `0x180009ed8`
- `ntdll!NtSetIRTimer` at `0x180009ed8`
- `ntdll!NtQuerySystemTime` at `0x180009e28`
- `ntdll!NtQuerySystemTime` at `0x180009e28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009ef7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009ef7`

## pseudocode

```c
__int64 __fastcall UmpoSmartPresenceTimerSet(union _LARGE_INTEGER *a1)
{
  int v2; // eax
  unsigned int AwayInterval; // esi
  union _LARGE_INTEGER v4; // rbx
  union _LARGE_INTEGER *v5; // rcx
  __int64 v6; // rdi
  union _LARGE_INTEGER v7; // rax
  unsigned __int64 v9; // [rsp+20h] [rbp-10h] BYREF
  union _LARGE_INTEGER v10; // [rsp+28h] [rbp-8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int64 v12; // [rsp+60h] [rbp+30h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+68h] [rbp+38h] BYREF

  v11 = 0;
  v12 = 0;
  v9 = 0;
  SystemTime.QuadPart = 0;
  if ( UmpoSmartPresenceSuspendCount )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = NtQuerySystemTime(&SystemTime);
  if ( v2 < 0 )
    return RtlNtStatusToDosError(v2);
  v4 = SystemTime;
  v5 = &v10;
  v10 = SystemTime;
  if ( a1 )
    v5 = a1;
  AwayInterval = UmpoGetAwayInterval(v5->QuadPart, &v9, &v12);
  if ( !AwayInterval )
  {
    v6 = v9;
    v7.QuadPart = v12;
    if ( v9 >= v12 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v7.QuadPart = v12;
    }
    if ( v7.QuadPart < (unsigned __int64)v4.QuadPart )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( v4.QuadPart < (unsigned __int64)v6 )
    {
      v11 = v6;
      if ( v6 < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      v11 = 0;
    }
    if ( (UmpoDebug & 2) != 0 )
      DbgPrint("%s: Absolute interval timer set (duetime=%lld)\n", "UmpoSmartPresenceTimerSet", v11);
    v2 = NtSetIRTimer(h, &v11);
    if ( v2 >= 0 )
    {
      SetThreadpoolWait(UmpoTimerWork, h, 0);
      return AwayInterval;
    }
    return RtlNtStatusToDosError(v2);
  }
  return AwayInterval;
}

```

## disassembly

```asm
0x180009de4  mov     [rsp-18h+arg_0], rbx
0x180009de9  push    rbp
0x180009dea  push    rsi
0x180009deb  push    rdi
0x180009dec  mov     rbp, rsp
0x180009def  sub     rsp, 30h
0x180009df3  cmp     cs:UmpoSmartPresenceSuspendCount, 0
0x180009dfa  mov     rdi, rcx
0x180009dfd  mov     [rbp+arg_8], 0
0x180009e05  mov     [rbp+arg_10], 0
0x180009e0d  mov     [rbp+var_10], 0
0x180009e15  mov     qword ptr [rbp+SystemTime], 0
0x180009e1d  jz      short loc_180009E24
0x180009e1f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009e24  lea     rcx, [rbp+SystemTime]; SystemTime
0x180009e28  call    cs:__imp_NtQuerySystemTime
0x180009e2e  test    eax, eax
0x180009e30  jns     short loc_180009E41
0x180009e32  mov     ecx, eax; Status
0x180009e34  call    cs:__imp_RtlNtStatusToDosError
0x180009e3a  mov     esi, eax
0x180009e3c  jmp     loc_180009EFD
0x180009e41  mov     rbx, qword ptr [rbp+SystemTime]
0x180009e45  lea     rcx, [rbp+var_8]
0x180009e49  test    rdi, rdi
0x180009e4c  mov     [rbp+var_8], rbx
0x180009e50  lea     r8, [rbp+arg_10]
0x180009e54  cmovnz  rcx, rdi
0x180009e58  lea     rdx, [rbp+var_10]
0x180009e5c  mov     rcx, [rcx]
0x180009e5f  call    UmpoGetAwayInterval
0x180009e64  mov     esi, eax
0x180009e66  test    eax, eax
0x180009e68  jnz     loc_180009EFD
0x180009e6e  mov     rdi, [rbp+var_10]
0x180009e72  mov     rax, [rbp+arg_10]
0x180009e76  cmp     rdi, rax
0x180009e79  jb      short loc_180009E84
0x180009e7b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009e80  mov     rax, [rbp+arg_10]
0x180009e84  cmp     rax, rbx
0x180009e87  jnb     short loc_180009E8E
0x180009e89  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009e8e  cmp     rbx, rdi
0x180009e91  jb      short loc_180009E9D
0x180009e93  mov     [rbp+arg_8], 0
0x180009e9b  jmp     short loc_180009EAB
0x180009e9d  mov     [rbp+arg_8], rdi
0x180009ea1  test    rdi, rdi
0x180009ea4  jns     short loc_180009EAB
0x180009ea6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009eab  mov     eax, cs:UmpoDebug
0x180009eb1  test    al, 2
0x180009eb3  jz      short loc_180009ECD
0x180009eb5  mov     r8, [rbp+arg_8]
0x180009eb9  lea     rdx, aUmposmartprese_0; "UmpoSmartPresenceTimerSet"
0x180009ec0  lea     rcx, aSAbsoluteInter; "%s: Absolute interval timer set (duetim"...
0x180009ec7  call    cs:__imp_DbgPrint
0x180009ecd  mov     rcx, cs:h
0x180009ed4  lea     rdx, [rbp+arg_8]
0x180009ed8  call    cs:__imp_NtSetIRTimer
0x180009ede  test    eax, eax
0x180009ee0  js      loc_180009E32
0x180009ee6  mov     rdx, cs:h; h
0x180009eed  xor     r8d, r8d; pftTimeout
0x180009ef0  mov     rcx, cs:UmpoTimerWork; pwa
0x180009ef7  call    cs:__imp_SetThreadpoolWait
0x180009efd  mov     rbx, [rsp+30h+arg_0]
0x180009f02  mov     eax, esi
0x180009f04  add     rsp, 30h
0x180009f08  pop     rdi
0x180009f09  pop     rsi
0x180009f0a  pop     rbp
0x180009f0b  retn
```
