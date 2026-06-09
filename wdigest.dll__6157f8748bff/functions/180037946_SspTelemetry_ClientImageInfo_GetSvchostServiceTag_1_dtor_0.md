# _SspTelemetry::ClientImageInfo::GetSvchostServiceTag_::_1_::dtor$0

- ea: `0x180037946`
- end: `0x180037975`
- name: `_SspTelemetry::ClientImageInfo::GetSvchostServiceTag_::_1_::dtor$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x1800348ac`
- `0x180037946`

## pseudocode

```c
__int64 __fastcall SspTelemetry::ClientImageInfo::GetSvchostServiceTag_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 144) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 144) &= ~1u;
    return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>>(*(_QWORD *)(a2 + 152));
  }
  return result;
}

```

## disassembly

```asm
0x180037946  push    rbp
0x180037948  sub     rsp, 20h
0x18003794c  mov     rbp, rdx
0x18003794f  mov     eax, [rbp+90h]
0x180037955  and     eax, 1
0x180037958  test    eax, eax
0x18003795a  jz      short loc_18003796F
0x18003795c  and     dword ptr [rbp+90h], 0FFFFFFFEh
0x180037963  mov     rcx, [rbp+98h]
0x18003796a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>>(void)
0x18003796f  add     rsp, 20h
0x180037973  pop     rbp
0x180037974  retn
```
