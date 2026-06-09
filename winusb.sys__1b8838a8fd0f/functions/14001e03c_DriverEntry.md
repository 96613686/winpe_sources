# DriverEntry

- ea: `0x14001e03c`
- end: `0x14001e37d`
- name: `DriverEntry`
- size: `833`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140010134`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400013d0`
- `0x1400106c0`
- `0x140010700`
- `0x14001a628`
- `0x14001a6dc`
- `0x14001a7a4`
- `0x14001e03c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e18d`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e1f3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e221`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e24f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e27d`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e2ab`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e18d`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e1f3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e221`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e24f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e27d`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001e2ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e1e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e211`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e23f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e26d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e29b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e1e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e211`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e23f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e26d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e29b`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14001e0fc`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14001e0fc`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // edx
  int (__fastcall *SystemRoutineAddress)(__int64, _BYTE *, __int64); // rax
  PVOID v6; // rax
  NTSTATUS v7; // eax
  int v8; // edx
  NTSTATUS v9; // ebx
  _BYTE v11[8]; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+58h] [rbp-21h] BYREF
  __m256i v14; // [rsp+68h] [rbp-11h] BYREF
  __int64 v15; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+90h] [rbp+17h] BYREF

  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  v15 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WinUSB;
  memset(&v14, 0, 28);
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  DestinationString = 0;
  v16 = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  LODWORD(v16) = 16;
  BYTE4(v16) = 1;
  *((_QWORD *)&v16 + 1) = 0x200000001LL;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, &v16);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v4) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        1,
        10,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 4;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        11,
        11,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
        (char)DriverObject);
    }
  }
  v11[0] = 0;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemRoutineAddress = (int (__fastcall *)(__int64, _BYTE *, __int64))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress && SystemRoutineAddress(227, v11, 1) >= 0 && v11[0] )
    ExPoolZeroingNativelySupported = 1;
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  RtlInitUnicodeString(&DestinationString, L"IoGetActivityIdIrp");
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (_IO_ALLOCATION_ACTION (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *, void *))MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"IoSetActivityIdIrp");
  WPP_MAIN_CB.Queue.ListEntry.Blink = (_LIST_ENTRY *)MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"IoGetInitiatorProcess");
  g_pIoGetInitiatorProcess = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"IoIncrementKeepAliveCount");
  WPP_MAIN_CB.Queue.ListEntry.Flink = (_LIST_ENTRY *)MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"IoDecrementKeepAliveCount");
  v6 = MmGetSystemRoutineAddress(&DestinationString);
  v14.m256i_i64[0] = 32;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = v6;
  v14.m256i_i64[1] = (__int64)WinUSB_AddDevice;
  v14.m256i_i64[3] = 0;
  v14.m256i_i64[2] = (__int64)WinUSB_Unload;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, __m256i *, __int64 *))(WdfFunctions_01015 + 928))(
         WdfDriverGlobals,
         DriverObject,
         RegistryPath,
         0,
         &v14,
         &v15);
  v9 = v7;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      13,
      (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
      v7);
  }
  if ( v9 < 0 )
    WppCleanupKm(DriverObject);
  return v9;
}

```

## disassembly

```asm
0x14001e03c  mov     [rsp-8+arg_10], rbx
0x14001e041  push    rbp
0x14001e042  push    rsi
0x14001e043  push    rdi
0x14001e044  push    r12
0x14001e046  push    r15
0x14001e048  lea     rbp, [rsp-37h]
0x14001e04d  sub     rsp, 0B0h
0x14001e054  mov     rax, cs:__security_cookie
0x14001e05b  xor     rax, rsp
0x14001e05e  mov     [rbp+57h+var_30], rax
0x14001e062  xor     esi, esi
0x14001e064  mov     cs:WPP_MAIN_CB.Timer, 1
0x14001e06f  xorps   xmm0, xmm0
0x14001e072  mov     [rbp+57h+var_48], rsi
0x14001e076  xor     eax, eax
0x14001e078  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14001e07f  lea     rax, WPP_ThisDir_CTLGUID_WinUSB
0x14001e086  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x14001e08d  xorps   xmm1, xmm1
0x14001e090  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001e097  movups  [rbp+57h+var_68], xmm0
0x14001e09b  mov     rbx, rdx
0x14001e09e  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14001e0a5  mov     rdi, rcx
0x14001e0a8  mov     cs:WPP_MAIN_CB.DeviceExtension, rsi
0x14001e0af  movups  [rbp+57h+var_68+0Ch], xmm0
0x14001e0b3  mov     cs:WPP_MAIN_CB.DeviceType, esi
0x14001e0b9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001e0bd  movups  [rbp+57h+var_40], xmm1
0x14001e0c1  call    WppLoadTracingSupport
0x14001e0c6  mov     rdx, rbx; __annotation("TMC:", "ef201d1b-4e45-4199-9e9e-74591f447955", "WinUSB", "TraceEntryExit", "TraceIoctl", "TraceParameter", "TraceReadPipe", "TraceWritePipe", "TraceControl", "TracePipePolicy", "TracePowerPolicy", "TraceInit", "TraceInfo", "TraceDriver", "TraceCreateClose", "TracePower", "TracePnP", "TraceUsb", "PUBLIC_TMF:")
0x14001e0c9  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14001e0d0  mov     rcx, rdi
0x14001e0d3  call    WppInitKm
0x14001e0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e0df  lea     rdx, [rbp+57h+var_40]
0x14001e0e3  mov     dword ptr [rbp+57h+var_40], 10h
0x14001e0ea  mov     dword ptr [rbp+57h+var_40+0Ch], 2
0x14001e0f1  mov     byte ptr [rbp+57h+var_40+4], 1
0x14001e0f5  mov     dword ptr [rbp+57h+var_40+8], 1
0x14001e0fc  call    cs:__imp_imp_WppRecorderConfigure
0x14001e103  nop     dword ptr [rax+rax+00h]
0x14001e108  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e10f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001e116  lea     r15, WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids
0x14001e11d  jz      short loc_14001E172
0x14001e11f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e126  cmp     [rcx+48h], si
0x14001e12a  jz      short loc_14001E144
0x14001e12c  mov     rcx, [rcx+40h]
0x14001e130  lea     r9d, [rsi+0Ah]
0x14001e134  lea     r8d, [rsi+1]
0x14001e138  mov     [rsp+0D0h+var_B0], r15
0x14001e13d  mov     dl, 5
0x14001e13f  call    WPP_RECORDER_SF_
0x14001e144  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001e14b  jz      short loc_14001E172
0x14001e14d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e154  mov     r8d, 0Bh
0x14001e15a  mov     r9d, r8d
0x14001e15d  mov     [rsp+0D0h+var_A8], rdi
0x14001e162  mov     dl, 4
0x14001e164  mov     [rsp+0D0h+var_B0], r15
0x14001e169  mov     rcx, [rcx+40h]
0x14001e16d  call    WPP_RECORDER_SF_q
0x14001e172  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x14001e179  mov     [rbp+57h+var_90], sil
0x14001e17d  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x14001e181  mov     [rbp+57h+SystemRoutineName.Buffer], rax
0x14001e185  mov     qword ptr [rbp+57h+SystemRoutineName.Length], 320030h
0x14001e18d  call    cs:__imp_MmGetSystemRoutineAddress
0x14001e194  nop     dword ptr [rax+rax+00h]
0x14001e199  test    rax, rax
0x14001e19c  jz      short loc_14001E1C4
0x14001e19e  xor     r9d, r9d
0x14001e1a1  lea     rdx, [rbp+57h+var_90]
0x14001e1a5  mov     ecx, 0E3h
0x14001e1aa  lea     r8d, [r9+1]
0x14001e1ae  call    _guard_dispatch_icall
0x14001e1b3  test    eax, eax
0x14001e1b5  js      short loc_14001E1C4
0x14001e1b7  cmp     [rbp+57h+var_90], sil
0x14001e1bb  jz      short loc_14001E1C4
0x14001e1bd  mov     cs:ExPoolZeroingNativelySupported, 1
0x14001e1c4  lea     rdx, aIogetactivityi; "IoGetActivityIdIrp"
0x14001e1cb  mov     cs:ExDefaultNonPagedPoolType, 200h
0x14001e1d5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e1d9  mov     cs:ExDefaultMdlProtection, 40000000h
0x14001e1e3  call    cs:__imp_RtlInitUnicodeString
0x14001e1ea  nop     dword ptr [rax+rax+00h]
0x14001e1ef  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001e1f3  call    cs:__imp_MmGetSystemRoutineAddress
0x14001e1fa  nop     dword ptr [rax+rax+00h]
0x14001e1ff  lea     rdx, aIosetactivityi; "IoSetActivityIdIrp"
0x14001e206  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rax
0x14001e20d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e211  call    cs:__imp_RtlInitUnicodeString
0x14001e218  nop     dword ptr [rax+rax+00h]
0x14001e21d  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001e221  call    cs:__imp_MmGetSystemRoutineAddress
0x14001e228  nop     dword ptr [rax+rax+00h]
0x14001e22d  lea     rdx, aIogetinitiator; "IoGetInitiatorProcess"
0x14001e234  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14001e23b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e23f  call    cs:__imp_RtlInitUnicodeString
0x14001e246  nop     dword ptr [rax+rax+00h]
0x14001e24b  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001e24f  call    cs:__imp_MmGetSystemRoutineAddress
0x14001e256  nop     dword ptr [rax+rax+00h]
0x14001e25b  lea     rdx, aIoincrementkee; "IoIncrementKeepAliveCount"
0x14001e262  mov     cs:g_pIoGetInitiatorProcess, rax
0x14001e269  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e26d  call    cs:__imp_RtlInitUnicodeString
0x14001e274  nop     dword ptr [rax+rax+00h]
0x14001e279  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001e27d  call    cs:__imp_MmGetSystemRoutineAddress
0x14001e284  nop     dword ptr [rax+rax+00h]
0x14001e289  lea     rdx, aIodecrementkee; "IoDecrementKeepAliveCount"
0x14001e290  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x14001e297  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e29b  call    cs:__imp_RtlInitUnicodeString
0x14001e2a2  nop     dword ptr [rax+rax+00h]
0x14001e2a7  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001e2ab  call    cs:__imp_MmGetSystemRoutineAddress
0x14001e2b2  nop     dword ptr [rax+rax+00h]
0x14001e2b7  lea     rcx, [rbp+57h+var_48]
0x14001e2bb  mov     qword ptr [rbp+57h+var_68], 20h ; ' '
0x14001e2c3  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x14001e2ca  xor     r9d, r9d
0x14001e2cd  mov     [rsp+0D0h+var_A8], rcx
0x14001e2d2  lea     rax, WinUSB_AddDevice
0x14001e2d9  mov     qword ptr [rbp+57h+var_68+8], rax
0x14001e2dd  lea     rcx, [rbp+57h+var_68]
0x14001e2e1  lea     rax, WinUSB_Unload
0x14001e2e8  mov     [rbp+57h+var_50], rsi
0x14001e2ec  mov     [rbp+57h+var_58], rax
0x14001e2f0  mov     r8, rbx
0x14001e2f3  mov     rax, cs:WdfFunctions_01015
0x14001e2fa  mov     rdx, rdi
0x14001e2fd  mov     [rsp+0D0h+var_B0], rcx
0x14001e302  mov     rcx, cs:WdfDriverGlobals
0x14001e309  mov     rax, [rax+3A0h]
0x14001e310  call    _guard_dispatch_icall
0x14001e315  mov     ebx, eax
0x14001e317  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001e31e  jz      short loc_14001E34B
0x14001e320  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e327  cmp     [rcx+48h], si
0x14001e32b  jz      short loc_14001E34B
0x14001e32d  mov     rcx, [rcx+40h]
0x14001e331  mov     r9d, 0Dh
0x14001e337  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14001e33b  mov     dl, 5
0x14001e33d  mov     [rsp+0D0h+var_B0], r15
0x14001e342  lea     r8d, [r9-0Ch]
0x14001e346  call    WPP_RECORDER_SF_d
0x14001e34b  test    ebx, ebx
0x14001e34d  jns     short loc_14001E357
0x14001e34f  mov     rcx, rdi
0x14001e352  call    WppCleanupKm
0x14001e357  mov     eax, ebx
0x14001e359  mov     rcx, [rbp+57h+var_30]
0x14001e35d  xor     rcx, rsp; StackCookie
0x14001e360  call    __security_check_cookie
0x14001e365  mov     rbx, [rsp+0D0h+arg_10]
0x14001e36d  add     rsp, 0B0h
0x14001e374  pop     r15
0x14001e376  pop     r12
0x14001e378  pop     rdi
0x14001e379  pop     rsi
0x14001e37a  pop     rbp
0x14001e37b  retn
```
