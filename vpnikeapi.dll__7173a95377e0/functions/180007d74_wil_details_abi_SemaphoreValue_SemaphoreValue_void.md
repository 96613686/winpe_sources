# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180007d74`
- end: `0x180007d93`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(wil::details **this, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007930`
- `0x180007960`
- `0x180009a80`
- `0x180009ba8`

## callees

- `0x180007be8`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details **this, void *a2)
{
  void *v3; // rdx

  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this + 1,
    a2);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this,
    v3);
}

```

## disassembly

```asm
0x180007d74  push    rbx
0x180007d76  sub     rsp, 20h
0x180007d7a  mov     rbx, rcx
0x180007d7d  add     rcx, 8
0x180007d81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007d86  mov     rcx, rbx
0x180007d89  add     rsp, 20h
0x180007d8d  pop     rbx
0x180007d8e  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
