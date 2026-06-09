# windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)

- ea: `0x18000a56c`
- end: `0x18000a5a9`
- name: `??$make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@rt@windows@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@34@@Z`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa00`

## callees

- `0x180009ec0`
- `0x18000a56c`
- `0x18000b908`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Microsoft::WRL::Details::Make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(
    a1,
    a2,
    a3);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v4, v5, v6);
  return a1;
}

```

## disassembly

```asm
0x18000a56c  mov     [rsp+arg_0], rcx
0x18000a571  push    rbx
0x18000a572  sub     rsp, 30h
0x18000a576  mov     rbx, rcx
0x18000a579  mov     [rsp+38h+var_18], 0
0x18000a581  call    ??$Make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@12@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@12@@Z; Microsoft::WRL::Details::Make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)
0x18000a586  mov     [rsp+38h+var_18], 1
0x18000a58e  mov     rcx, [rsp+38h]; this
0x18000a593  cmp     qword ptr [rbx], 0
0x18000a597  jnz     short loc_18000A59F
0x18000a599  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000a59f  mov     rax, rbx
0x18000a5a2  add     rsp, 30h
0x18000a5a6  pop     rbx
0x18000a5a7  retn
```
