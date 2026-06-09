# DriverEntry

- ea: `0x14005003c`
- end: `0x140050169`
- name: `DriverEntry`
- size: `301`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140030574`

## callees

- `0x140018fc8`
- `0x14001d3d4`
- `0x14001d414`
- `0x140039780`
- `0x14004e008`
- `0x14004e0b4`
- `0x14004e0ec`
- `0x14004e170`
- `0x14004e204`
- `0x14004e6b0`
- `0x14005003c`
- `0x140050170`

## import_xrefs

- `ntoskrnl!ExIsSoftBoot` at `0x140050130`
- `ntoskrnl!ExIsSoftBoot` at `0x140050130`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v5; // ebx
  struct _DRIVER_OBJECT *v6; // rcx
  __int128 v7; // [rsp+40h] [rbp-28h] BYREF
  __int128 v8; // [rsp+50h] [rbp-18h]

  v7 = 0;
  v8 = 0;
  if ( SkipDriverEntry )
    return -1073741823;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_TpmCtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  McGenEventRegister_EtwRegister();
  wil_InitializeFeatureStaging();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  *(_QWORD *)&v7 = 32;
  *((_QWORD *)&v7 + 1) = TpmEvtDeviceAdd;
  *((_QWORD *)&v8 + 1) = 0;
  *(_QWORD *)&v8 = TpmEvtDriverUnload;
  v5 = (*((__int64 (__fastcall **)(PKDPC, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, __int128 *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
        + 116))(
         WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
         DriverObject,
         RegistryPath,
         0,
         &v7,
         0);
  if ( v5 < 0 )
  {
    wil_UninitializeFeatureStaging();
    McGenEventUnregister_EtwUnregister();
    WppCleanupKm();
    TraceLoggingUnregister_EtwUnregister();
  }
  else if ( !(unsigned __int8)ExIsSoftBoot() )
  {
    TpmTransportType::Determine(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x14005003c  mov     [rsp+arg_0], rbx
0x140050041  push    rdi
0x140050042  sub     rsp, 60h
0x140050046  cmp     cs:SkipDriverEntry, 0
0x14005004d  xorps   xmm0, xmm0
0x140050050  movups  [rsp+68h+var_28], xmm0
0x140050055  mov     rbx, rdx
0x140050058  mov     rdi, rcx
0x14005005b  movups  [rsp+68h+var_18], xmm0
0x140050060  jz      short loc_14005006C
0x140050062  mov     eax, 0C0000001h
0x140050067  jmp     loc_14005015D
0x14005006c  lea     rax, WPP_ThisDir_CTLGUID_TpmCtlGuid
0x140050073  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14005007e  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140050085  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x140050090  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14005009b  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400500a6  call    WppLoadTracingSupport
0x1400500ab  mov     cs:WPP_MAIN_CB.CurrentIrp, 0; __annotation("TMC:", "3A8D6942-B034-48e2-B314-F69C2B4655A3", "TpmCtlGuid", "ERROR", "WARNING", "INFORMATION", "VERBOSE", "TPMCMDHEXDUMP", "PPIHEXDUMP", "MXTRACEERRORS", "PUBLIC_TMF:")
0x1400500b6  call    WppInitKm
0x1400500bb  call    McGenEventRegister_EtwRegister
0x1400500c0  call    wil_InitializeFeatureStaging
0x1400500c5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400500ca  lea     rax, TpmEvtDeviceAdd
0x1400500d1  mov     qword ptr [rsp+68h+var_28], 20h ; ' '
0x1400500da  mov     qword ptr [rsp+68h+var_28+8], rax
0x1400500df  lea     rcx, [rsp+68h+var_28]
0x1400500e4  lea     rax, TpmEvtDriverUnload
0x1400500eb  mov     qword ptr [rsp+68h+var_18+8], 0
0x1400500f4  mov     qword ptr [rsp+68h+var_18], rax
0x1400500f9  xor     r9d, r9d
0x1400500fc  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140050103  mov     r8, rbx
0x140050106  mov     [rsp+68h+var_40], 0
0x14005010f  mov     rdx, rdi
0x140050112  mov     [rsp+68h+var_48], rcx
0x140050117  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14005011e  mov     rax, [rax+3A0h]
0x140050125  call    _guard_dispatch_icall
0x14005012a  mov     ebx, eax
0x14005012c  test    eax, eax
0x14005012e  js      short loc_140050147
0x140050130  call    cs:__imp_ExIsSoftBoot
0x140050137  nop     dword ptr [rax+rax+00h]
0x14005013c  test    al, al
0x14005013e  jnz     short loc_14005015B
0x140050140  call    ?Determine@TpmTransportType@@SAJQEAU_DRIVER_OBJECT@@@Z; TpmTransportType::Determine(_DRIVER_OBJECT * const)
0x140050145  jmp     short loc_14005015B
0x140050147  call    wil_UninitializeFeatureStaging
0x14005014c  call    McGenEventUnregister_EtwUnregister
0x140050151  call    WppCleanupKm
0x140050156  call    TraceLoggingUnregister_EtwUnregister
0x14005015b  mov     eax, ebx
0x14005015d  mov     rbx, [rsp+68h+arg_0]
0x140050162  add     rsp, 60h
0x140050166  pop     rdi
0x140050167  retn
```
