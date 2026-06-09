# wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(void)

- ea: `0x180008d30`
- end: `0x180008d4d`
- name: `??1?$com_ptr_t@UIAudioProcessingObjectLoggingService@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008c98`
- `0x180076c4c`

## callees

- `0x180008d30`
- `0x180086010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180008d30  sub     rsp, 28h
0x180008d34  mov     rcx, [rcx]
0x180008d37  test    rcx, rcx
0x180008d3a  jz      short loc_180008D48
0x180008d3c  mov     rax, [rcx]
0x180008d3f  mov     rax, [rax+10h]
0x180008d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d48  add     rsp, 28h
0x180008d4c  retn
```
