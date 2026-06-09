# DriverEntry

- ea: `0x14003003c`
- end: `0x140030258`
- name: `DriverEntry`
- size: `540`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14000bf74`

## callees

- `0x140003824`
- `0x1400038cc`
- `0x14000c700`
- `0x140017190`
- `0x140027300`
- `0x140027474`
- `0x140027508`
- `0x140029684`
- `0x14003003c`
- `0x140030260`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140030084`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140030084`
- `ntoskrnl!KeInitializeEvent` at `0x140030233`
- `ntoskrnl!KeInitializeEvent` at `0x140030233`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int (__fastcall *SystemRoutineAddress)(__int64, char *, __int64, _QWORD); // rax
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v8[2]; // [rsp+50h] [rbp-20h] BYREF
  char v9; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v10; // [rsp+A8h] [rbp+38h] BYREF

  memset(v8, 0, 28);
  v10 = 0;
  wil_InitializeFeatureStaging();
  v9 = 0;
  SystemRoutineName.Buffer = L"ZwQuerySystemInformation";
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemRoutineAddress = (int (__fastcall *)(__int64, char *, __int64, _QWORD))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress && SystemRoutineAddress(227, &v9, 1, 0) >= 0 && v9 )
    ExPoolZeroingNativelySupported = 1;
  ExDefaultNonPagedPoolType = 512;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_VMBusDriverTraceGuid;
  ExDefaultMdlProtection = 0x40000000;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  McGenEventRegister_EtwRegister();
  InitializeTelemetryAssertsKMByDriverObject((__int64)DriverObject);
  memset(v8, 0, sizeof(v8));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x18 )
      LODWORD(v8[0]) = -1;
    else
      LODWORD(v8[0]) = *(_DWORD *)(WdfStructures + 192);
  }
  else
  {
    LODWORD(v8[0]) = 32;
  }
  HIDWORD(v8[1]) = 1467310678;
  *((_QWORD *)&v8[0] + 1) = RootDeviceAdd;
  *(_QWORD *)&v8[1] = VmBusDriverUnload;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, _OWORD *, __int64 *))(WdfFunctions_01033 + 928))(
         WdfDriverGlobals,
         DriverObject,
         RegistryPath,
         0,
         v8,
         &v10);
  if ( v5 >= 0 )
  {
    v5 = InstanceInitializeNuma();
    if ( v5 >= 0 )
    {
      CrashLock.Count = 1;
      CrashLock.Owner = 0;
      CrashLock.Contention = 0;
      KeInitializeEvent(&CrashLock.Event, SynchronizationEvent, 0);
      v5 = 0;
      qword_140020A48 = (__int64)&CrashChannels;
      CrashChannels = &CrashChannels;
      return v5;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9e459d95b5f83e526cd0ff3b047e831b_Traceguids, (unsigned int)v5);
  }
  VmBusDriverCleanup();
  return v5;
}

```

## disassembly

```asm
0x14003003c  mov     [rsp-18h+arg_0], rbx
0x140030041  push    rbp
0x140030042  push    rsi
0x140030043  push    rdi
0x140030044  mov     rbp, rsp
0x140030047  sub     rsp, 70h
0x14003004b  xorps   xmm0, xmm0
0x14003004e  xor     esi, esi
0x140030050  movups  [rbp+var_20], xmm0
0x140030054  xor     eax, eax
0x140030056  mov     [rbp+arg_18], rsi
0x14003005a  movups  [rbp+var_20+0Ch], xmm0
0x14003005e  mov     rdi, rdx
0x140030061  mov     rbx, rcx
0x140030064  call    wil_InitializeFeatureStaging
0x140030069  lea     rax, aZwquerysystemi; "ZwQuerySystemInformation"
0x140030070  mov     [rbp+arg_10], sil
0x140030074  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x140030078  mov     [rbp+SystemRoutineName.Buffer], rax
0x14003007c  mov     qword ptr [rbp+SystemRoutineName.Length], 320030h
0x140030084  call    cs:__imp_MmGetSystemRoutineAddress
0x14003008b  nop     dword ptr [rax+rax+00h]
0x140030090  test    rax, rax
0x140030093  jz      short loc_1400300BB
0x140030095  xor     r9d, r9d
0x140030098  lea     r8d, [rsi+1]
0x14003009c  lea     rdx, [rbp+arg_10]
0x1400300a0  mov     ecx, 0E3h
0x1400300a5  call    _guard_dispatch_icall
0x1400300aa  test    eax, eax
0x1400300ac  js      short loc_1400300BB
0x1400300ae  cmp     [rbp+arg_10], sil
0x1400300b2  jz      short loc_1400300BB
0x1400300b4  mov     cs:ExPoolZeroingNativelySupported, 1
0x1400300bb  lea     rax, WPP_ThisDir_CTLGUID_VMBusDriverTraceGuid
0x1400300c2  mov     cs:ExDefaultNonPagedPoolType, 200h
0x1400300cc  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400300d3  mov     cs:ExDefaultMdlProtection, 40000000h
0x1400300dd  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x1400300e4  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x1400300eb  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1400300f2  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400300fd  call    WppLoadTracingSupport
0x140030102  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x140030109  call    WppInitKm
0x14003010e  call    McGenEventRegister_EtwRegister
0x140030113  mov     rcx, rbx
0x140030116  call    InitializeTelemetryAssertsKMByDriverObject
0x14003011b  cmp     cs:WdfClientVersionHigherThanFramework, sil
0x140030122  xorps   xmm0, xmm0
0x140030125  movups  [rbp+var_20], xmm0
0x140030129  movups  [rbp+var_10], xmm0
0x14003012d  jz      short loc_140030153
0x14003012f  cmp     cs:WdfStructureCount, 18h
0x140030136  jbe     short loc_14003014A
0x140030138  mov     rax, cs:WdfStructures
0x14003013f  mov     ecx, [rax+0C0h]
0x140030145  mov     dword ptr [rbp+var_20], ecx
0x140030148  jmp     short loc_14003015A
0x14003014a  mov     dword ptr [rbp+var_20], 0FFFFFFFFh
0x140030151  jmp     short loc_14003015A
0x140030153  mov     dword ptr [rbp+var_20], 20h ; ' '
0x14003015a  lea     rax, RootDeviceAdd
0x140030161  mov     dword ptr [rbp+var_10+0Ch], 57756256h
0x140030168  mov     qword ptr [rbp+var_20+8], rax
0x14003016c  lea     rcx, [rbp+arg_18]
0x140030170  mov     [rsp+70h+var_48], rcx
0x140030175  lea     rax, VmBusDriverUnload
0x14003017c  mov     qword ptr [rbp+var_10], rax
0x140030180  lea     rcx, [rbp+var_20]
0x140030184  mov     rax, cs:WdfFunctions_01033
0x14003018b  xor     r9d, r9d
0x14003018e  mov     [rsp+70h+var_50], rcx
0x140030193  mov     r8, rdi
0x140030196  mov     rcx, cs:WdfDriverGlobals
0x14003019d  mov     rdx, rbx
0x1400301a0  mov     rax, [rax+3A0h]
0x1400301a7  call    _guard_dispatch_icall
0x1400301ac  mov     ebx, eax
0x1400301ae  test    eax, eax
0x1400301b0  jns     short loc_140030203
0x1400301b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400301b9  lea     rax, WPP_GLOBAL_Control
0x1400301c0  cmp     rcx, rax
0x1400301c3  jz      short loc_1400301EB
0x1400301c5  mov     edx, [rcx+2Ch]
0x1400301c8  test    dl, 1
0x1400301cb  jz      short loc_1400301EB
0x1400301cd  cmp     byte ptr [rcx+29h], 2
0x1400301d1  jb      short loc_1400301EB
0x1400301d3  mov     rcx, [rcx+18h]
0x1400301d7  lea     r8, WPP_9e459d95b5f83e526cd0ff3b047e831b_Traceguids
0x1400301de  mov     edx, 0Ah
0x1400301e3  mov     r9d, ebx
0x1400301e6  call    WPP_SF_d
0x1400301eb  call    VmBusDriverCleanup
0x1400301f0  mov     eax, ebx
0x1400301f2  mov     rbx, [rsp+70h+arg_0]
0x1400301fa  add     rsp, 70h
0x1400301fe  pop     rdi
0x1400301ff  pop     rsi
0x140030200  pop     rbp
0x140030201  retn
0x140030203  call    InstanceInitializeNuma
0x140030208  mov     ebx, eax
0x14003020a  test    eax, eax
0x14003020c  js      short loc_1400301EB
0x14003020e  xor     r8d, r8d; State
0x140030211  mov     cs:CrashLock.Count, 1
0x14003021b  lea     rcx, CrashLock.Event; Event
0x140030222  mov     cs:CrashLock.Owner, rsi
0x140030229  mov     cs:CrashLock.Contention, esi
0x14003022f  lea     edx, [r8+1]; Type
0x140030233  call    cs:__imp_KeInitializeEvent
0x14003023a  nop     dword ptr [rax+rax+00h]
0x14003023f  lea     rax, CrashChannels
0x140030246  mov     ebx, esi
0x140030248  mov     cs:qword_140020A48, rax
0x14003024f  mov     cs:CrashChannels, rax
0x140030256  jmp     short loc_1400301F0
```
