# SOS_OS::PreBoot(void)

- ea: `0x1004b1e10`
- end: `0x1004b1f26`
- name: `?PreBoot@SOS_OS@@SA?AW4SOS_RESULT@@XZ`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1004b1e10`
- `0x1004b5fa0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004b1eb4`
- `KERNEL32!CreateEventW` at `0x1004b1eb4`
- `KERNEL32!GetModuleHandleW` at `0x1004b1e6f`
- `KERNEL32!GetModuleHandleW` at `0x1004b1e6f`
- `KERNEL32!GetProcAddress` at `0x1004b1e9a`
- `KERNEL32!GetProcAddress` at `0x1004b1e9a`
- `SQLOS!IsHardwareSupported` at `0x1004b1e56`
- `SQLOS!IsHardwareSupported` at `0x1004b1e56`
- `VCRUNTIME140!_set_se_translator` at `0x1004b1e29`
- `VCRUNTIME140!_set_se_translator` at `0x1004b1e29`
- `VCRUNTIME140!set_unexpected` at `0x1004b1e43`
- `VCRUNTIME140!set_unexpected` at `0x1004b1e43`
- `api-ms-win-crt-runtime-l1-1-0!_set_new_handler` at `0x1004b1e50`
- `api-ms-win-crt-runtime-l1-1-0!_set_new_handler` at `0x1004b1e50`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x1004b1e36`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x1004b1e36`

## string_xrefs

- `0x1004b1e8b`: `SetDllMainCallback`

## pseudocode

```c
__int64 SOS_OS::PreBoot()
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rbx
  unsigned int v3; // ecx
  _DWORD v4[4]; // [rsp+20h] [rbp-18h] BYREF

  SOS_OS::sm_SOSProcessGlobals = g_SosProcessConfiguration;
  _set_se_translator(SOS_SEHTranslator);
  set_terminate(ex_terminator);
  set_unexpected(ex_terminator);
  _set_new_handler(SOS_OS::OutOfMemoryHandler);
  IsHardwareSupported();
  ModuleHandleW = SOS_OS::sm_hmodSQLOS;
  if ( !SOS_OS::sm_hmodSQLOS )
  {
    ModuleHandleW = GetModuleHandleW(SOS_OS_SOSDllName);
    SOS_OS::sm_hmodSQLOS = ModuleHandleW;
    if ( !ModuleHandleW )
      return 0x80000000LL;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SetDllMainCallback");
  if ( !ProcAddress )
    return 0x80000000LL;
  SOS_OS_BootEvent = CreateEventW(0, 1, 0, 0);
  if ( !SOS_OS_BootEvent )
    return 0x80000000LL;
  ((void (__fastcall *)(__int64 (__fastcall *)(HINSTANCE, unsigned int, void *)))ProcAddress)(SystemThread::DllMainCallback);
  SOS_OS::QueryIsHypervisorEnabledInternal((struct SOS_OS::HypervisorInfo *)v4);
  if ( v4[0] )
  {
    v3 = SOS_PublicGlobals::sm_osStatus | 0x400;
    SOS_PublicGlobals::sm_osStatus |= 0x400u;
    if ( v4[1] )
      SOS_PublicGlobals::sm_osStatus = v3 | 0x4000;
  }
  SOS_OS_sm_osProcessStatus |= 0x200u;
  return 0;
}

```

## disassembly

```asm
0x1004b1e10  sub     rsp, 38h
0x1004b1e14  lea     rax, ?g_SosProcessConfiguration@@3V?$SOS_ProcessConfigImpl@$0A@@@A; SOS_ProcessConfigImpl<0> g_SosProcessConfiguration
0x1004b1e1b  lea     rcx, ?SOS_SEHTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SOS_SEHTranslator(uint,_EXCEPTION_POINTERS *)
0x1004b1e22  mov     cs:?sm_SOSProcessGlobals@SOS_OS@@0VPerProcessGlobals@@A, rax; PerProcessGlobals SOS_OS::sm_SOSProcessGlobals
0x1004b1e29  call    cs:__imp__set_se_translator
0x1004b1e2f  lea     rcx, ?ex_terminator@@YAXXZ; ex_terminator(void)
0x1004b1e36  call    cs:__imp_set_terminate
0x1004b1e3c  lea     rcx, ?ex_terminator@@YAXXZ; ex_terminator(void)
0x1004b1e43  call    cs:__imp_set_unexpected
0x1004b1e49  lea     rcx, ?OutOfMemoryHandler@SOS_OS@@SAH_K@Z; NewHandler
0x1004b1e50  call    cs:__imp__set_new_handler
0x1004b1e56  call    cs:__imp_?IsHardwareSupported@@YA?AW4HardwareCheckResult@@XZ; IsHardwareSupported(void)
0x1004b1e5c  mov     rax, cs:?sm_hmodSQLOS@SOS_OS@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * SOS_OS::sm_hmodSQLOS
0x1004b1e63  test    rax, rax
0x1004b1e66  jnz     short loc_1004B1E8B
0x1004b1e68  mov     rcx, cs:?SOS_OS_SOSDllName@@3PEA_WEA; lpModuleName
0x1004b1e6f  call    cs:__imp_GetModuleHandleW
0x1004b1e75  mov     cs:?sm_hmodSQLOS@SOS_OS@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * SOS_OS::sm_hmodSQLOS
0x1004b1e7c  test    rax, rax
0x1004b1e7f  jnz     short loc_1004B1E8B
0x1004b1e81  mov     eax, 80000000h
0x1004b1e86  add     rsp, 38h
0x1004b1e8a  retn
0x1004b1e8b  lea     rdx, aSetdllmaincall; "SetDllMainCallback"
0x1004b1e92  mov     [rsp+38h+var_8], rbx
0x1004b1e97  mov     rcx, rax; hModule
0x1004b1e9a  call    cs:__imp_GetProcAddress
0x1004b1ea0  mov     rbx, rax
0x1004b1ea3  test    rax, rax
0x1004b1ea6  jz      short loc_1004B1EC6
0x1004b1ea8  xor     r9d, r9d; lpName
0x1004b1eab  xor     r8d, r8d; bInitialState
0x1004b1eae  xor     ecx, ecx; lpEventAttributes
0x1004b1eb0  lea     edx, [r9+1]; bManualReset
0x1004b1eb4  call    cs:__imp_CreateEventW
0x1004b1eba  mov     cs:?SOS_OS_BootEvent@@3PEAXEA, rax; void * SOS_OS_BootEvent
0x1004b1ec1  test    rax, rax
0x1004b1ec4  jnz     short loc_1004B1ED5
0x1004b1ec6  mov     rbx, [rsp+38h+var_8]
0x1004b1ecb  mov     eax, 80000000h
0x1004b1ed0  add     rsp, 38h
0x1004b1ed4  retn
0x1004b1ed5  lea     rcx, ?DllMainCallback@SystemThread@@SAHPEAUHINSTANCE__@@KPEAX@Z; SystemThread::DllMainCallback(HINSTANCE__ *,ulong,void *)
0x1004b1edc  call    rbx
0x1004b1ede  lea     rcx, [rsp+38h+var_18]; struct SOS_OS::HypervisorInfo *
0x1004b1ee3  call    ?QueryIsHypervisorEnabledInternal@SOS_OS@@SAXPEAUHypervisorInfo@1@@Z; SOS_OS::QueryIsHypervisorEnabledInternal(SOS_OS::HypervisorInfo *)
0x1004b1ee8  cmp     [rsp+38h+var_18], 0
0x1004b1eed  jz      short loc_1004B1F10
0x1004b1eef  mov     ecx, cs:?sm_osStatus@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStatus
0x1004b1ef5  bts     ecx, 0Ah
0x1004b1ef9  cmp     [rsp+38h+var_14], 0
0x1004b1efe  mov     cs:?sm_osStatus@SOS_PublicGlobals@@2KA, ecx; ulong SOS_PublicGlobals::sm_osStatus
0x1004b1f04  jz      short loc_1004B1F10
0x1004b1f06  bts     ecx, 0Eh
0x1004b1f0a  mov     cs:?sm_osStatus@SOS_PublicGlobals@@2KA, ecx; ulong SOS_PublicGlobals::sm_osStatus
0x1004b1f10  or      cs:?SOS_OS_sm_osProcessStatus@@3KA, 200h; ulong SOS_OS_sm_osProcessStatus
0x1004b1f1a  mov     rbx, [rsp+38h+var_8]
0x1004b1f1f  xor     eax, eax
0x1004b1f21  add     rsp, 38h
0x1004b1f25  retn
```
