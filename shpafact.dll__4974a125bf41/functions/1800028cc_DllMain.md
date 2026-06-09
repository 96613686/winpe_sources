# DllMain

- ea: `0x1800028cc`
- end: `0x180002ace`
- name: `DllMain`
- size: `514`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012c4`

## callees

- `0x1800028cc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180002a65`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180002a65`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180002aa0`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180002aa0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a7c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800028fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800028fb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800028ee`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800028ee`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v3; // rbx
  const GUID **v4; // rdi
  const GUID *v5; // r8
  _QWORD *v6; // rbx
  TRACEHANDLE v7; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      InitializeCriticalSection(&g_csDll);
      qword_1800076E0 = 0;
      WPP_MAIN_CB = (__int64)&qword_1800076F8;
      v3 = (ULONG64 *)&WPP_MAIN_CB;
      qword_1800076E8 = 1;
      qword_1800076F8 = (__int64)&qword_180007720;
      v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      qword_180007708 = 0;
      qword_180007720 = (__int64)&qword_180007748;
      qword_180007748 = (__int64)&qword_180007770;
      qword_180007770 = (__int64)&qword_180007798;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShellTraceProvider;
      qword_1800077C8 = (__int64)WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
      qword_1800077D0 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
      qword_1800077D8 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider;
      qword_1800077E0 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider;
      qword_1800077E8 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider;
      qword_180007710 = 1;
      qword_180007730 = 0;
      qword_180007738 = 1;
      qword_180007758 = 0;
      qword_180007760 = 1;
      qword_180007780 = 0;
      qword_180007788 = 1;
      qword_1800077A8 = 0;
      qword_180007798 = 0;
      qword_1800077B0 = 1;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      do
      {
        v5 = *v4;
        TraceGuidReg.Guid = v5;
        ++v4;
        TraceGuidReg.RegHandle = 0;
        v3[4] = (ULONG64)v5;
        RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, &TraceGuidReg, 0, 0, v3 + 1);
        v3 = (ULONG64 *)*v3;
      }
      while ( v3 );
    }
  }
  else
  {
    DeleteCriticalSection(&g_csDll);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v6 )
      {
        v7 = v6[1];
        if ( v7 )
        {
          UnregisterTraceGuids(v7);
          v6[1] = 0;
        }
        v6 = (_QWORD *)*v6;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800028cc  mov     [rsp+arg_0], rbx
0x1800028d1  mov     [rsp+arg_8], rsi
0x1800028d6  push    rdi
0x1800028d7  sub     rsp, 50h
0x1800028db  xor     esi, esi
0x1800028dd  test    edx, edx
0x1800028df  jz      loc_180002A75
0x1800028e5  cmp     edx, 1
0x1800028e8  jnz     loc_180002AB9
0x1800028ee  call    cs:__imp_DisableThreadLibraryCalls
0x1800028f4  lea     rcx, g_csDll; lpCriticalSection
0x1800028fb  call    cs:__imp_InitializeCriticalSection
0x180002901  lea     rax, qword_1800076F8
0x180002908  mov     cs:qword_1800076E0, rsi
0x18000290f  mov     cs:WPP_MAIN_CB, rax
0x180002916  lea     rbx, WPP_MAIN_CB
0x18000291d  lea     rax, qword_180007720
0x180002924  mov     cs:qword_1800076E8, 1
0x18000292f  mov     cs:qword_1800076F8, rax
0x180002936  lea     rdi, WPP_REGISTRATION_GUIDS
0x18000293d  lea     rax, qword_180007748
0x180002944  mov     cs:qword_180007708, rsi
0x18000294b  mov     cs:qword_180007720, rax
0x180002952  lea     rax, qword_180007770
0x180002959  mov     cs:qword_180007748, rax
0x180002960  lea     rax, qword_180007798
0x180002967  mov     cs:qword_180007770, rax
0x18000296e  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x180002975  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000297c  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x180002983  mov     cs:qword_1800077C8, rax
0x18000298a  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x180002991  mov     cs:qword_1800077D0, rax
0x180002998  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider
0x18000299f  mov     cs:qword_1800077D8, rax
0x1800029a6  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider
0x1800029ad  mov     cs:qword_1800077E0, rax
0x1800029b4  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider
0x1800029bb  mov     cs:qword_1800077E8, rax
0x1800029c2  mov     cs:qword_180007710, 1
0x1800029cd  mov     cs:qword_180007730, rsi
0x1800029d4  mov     cs:qword_180007738, 1
0x1800029df  mov     cs:qword_180007758, rsi
0x1800029e6  mov     cs:qword_180007760, 1
0x1800029f1  mov     cs:qword_180007780, rsi
0x1800029f8  mov     cs:qword_180007788, 1
0x180002a03  mov     cs:qword_1800077A8, rsi
0x180002a0a  mov     cs:qword_180007798, rsi
0x180002a11  mov     cs:qword_1800077B0, 1
0x180002a1c  mov     cs:WPP_GLOBAL_Control, rbx
0x180002a23  mov     r8, [rdi]; ControlGuid
0x180002a26  lea     rax, [rbx+8]
0x180002a2a  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180002a2f  lea     rcx, WppControlCallback; RequestAddress
0x180002a36  mov     [rsp+58h+MofResourceName], rsi; MofResourceName
0x180002a3b  lea     rax, [rsp+58h+var_18]
0x180002a40  mov     [rsp+58h+var_18.Guid], r8
0x180002a45  lea     rdi, [rdi+8]
0x180002a49  mov     [rsp+58h+var_18.RegHandle], rsi
0x180002a4e  mov     r9d, 1; GuidCount
0x180002a54  mov     [rsp+58h+MofImagePath], rsi; MofImagePath
0x180002a59  mov     rdx, rbx; RequestContext
0x180002a5c  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180002a61  mov     [rbx+20h], r8
0x180002a65  call    cs:__imp_RegisterTraceGuidsW
0x180002a6b  mov     rbx, [rbx]
0x180002a6e  test    rbx, rbx
0x180002a71  jnz     short loc_180002A23
0x180002a73  jmp     short loc_180002AB9
0x180002a75  lea     rcx, g_csDll; lpCriticalSection
0x180002a7c  call    cs:__imp_DeleteCriticalSection
0x180002a82  mov     rbx, cs:WPP_GLOBAL_Control
0x180002a89  lea     rdi, WPP_GLOBAL_Control
0x180002a90  cmp     rbx, rdi
0x180002a93  jz      short loc_180002AB9
0x180002a95  jmp     short loc_180002AAD
0x180002a97  mov     rcx, [rbx+8]; RegistrationHandle
0x180002a9b  test    rcx, rcx
0x180002a9e  jz      short loc_180002AAA
0x180002aa0  call    cs:__imp_UnregisterTraceGuids
0x180002aa6  mov     [rbx+8], rsi
0x180002aaa  mov     rbx, [rbx]
0x180002aad  test    rbx, rbx
0x180002ab0  jnz     short loc_180002A97
0x180002ab2  mov     cs:WPP_GLOBAL_Control, rdi
0x180002ab9  mov     rbx, [rsp+58h+arg_0]
0x180002abe  mov     eax, 1
0x180002ac3  mov     rsi, [rsp+58h+arg_8]
0x180002ac8  add     rsp, 50h
0x180002acc  pop     rdi
0x180002acd  retn
```
