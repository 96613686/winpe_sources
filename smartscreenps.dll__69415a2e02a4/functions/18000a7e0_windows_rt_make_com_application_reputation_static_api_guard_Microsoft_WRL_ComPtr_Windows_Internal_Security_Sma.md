# windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)

- ea: `0x18000a7e0`
- end: `0x18000a81d`
- name: `??$make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@rt@windows@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@34@@Z`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac90`

## callees

- `0x18000a100`
- `0x18000a7e0`
- `0x18000bbd8`

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
0x18000a7e0  mov     [rsp+arg_0], rcx
0x18000a7e5  push    rbx
0x18000a7e6  sub     rsp, 30h
0x18000a7ea  mov     rbx, rcx
0x18000a7ed  mov     [rsp+38h+var_18], 0
0x18000a7f5  call    ??$Make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@12@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@12@@Z; Microsoft::WRL::Details::Make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)
0x18000a7fa  mov     [rsp+38h+var_18], 1
0x18000a802  mov     rcx, [rsp+38h]; this
0x18000a807  cmp     qword ptr [rbx], 0
0x18000a80b  jnz     short loc_18000A813
0x18000a80d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000a813  mov     rax, rbx
0x18000a816  add     rsp, 30h
0x18000a81a  pop     rbx
0x18000a81b  retn
```
