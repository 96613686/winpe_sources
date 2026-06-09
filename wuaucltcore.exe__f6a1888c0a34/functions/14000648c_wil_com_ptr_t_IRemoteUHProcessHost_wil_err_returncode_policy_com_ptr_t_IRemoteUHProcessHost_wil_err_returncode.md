# wil::com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>::~com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>(void)

- ea: `0x14000648c`
- end: `0x1400064aa`
- name: `??1?$com_ptr_t@UIRemoteUHProcessHost@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400214cd`
- `0x140021503`
- `0x1400217fb`
- `0x14002181f`
- `0x140021855`
- `0x1400218c1`
- `0x1400218f7`
- `0x14002192d`
- `0x140021951`
- `0x140021975`
- `0x140021987`
- `0x1400219ab`
- `0x1400219e1`
- `0x140021a29`
- `0x140021b01`

## callees

- `0x14000648c`
- `0x1400206e0`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>::~com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>(
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
0x14000648c  sub     rsp, 28h
0x140006490  mov     rcx, [rcx]
0x140006493  test    rcx, rcx
0x140006496  jz      short loc_1400064A5
0x140006498  mov     rax, [rcx]
0x14000649b  mov     rax, [rax+10h]
0x14000649f  call    _guard_dispatch_icall
0x1400064a4  nop
0x1400064a5  add     rsp, 28h
0x1400064a9  retn
```
