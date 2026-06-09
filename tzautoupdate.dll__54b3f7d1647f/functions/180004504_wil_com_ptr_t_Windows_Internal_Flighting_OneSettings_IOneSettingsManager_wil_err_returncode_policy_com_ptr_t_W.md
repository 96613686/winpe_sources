# wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(void)

- ea: `0x180004504`
- end: `0x180004522`
- name: `??1?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c4e0`

## callees

- `0x180004504`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(
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
0x180004504  sub     rsp, 28h
0x180004508  mov     rcx, [rcx]
0x18000450b  test    rcx, rcx
0x18000450e  jz      short loc_18000451D
0x180004510  mov     rax, [rcx]
0x180004513  mov     rax, [rax+10h]
0x180004517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000451c  nop
0x18000451d  add     rsp, 28h
0x180004521  retn
```
