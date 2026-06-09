# wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)

- ea: `0x1800175b8`
- end: `0x1800175d5`
- name: `??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001777c`
- `0x180017bf8`
- `0x1800185b4`
- `0x1800186c8`

## callees

- `0x1800175b8`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(
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
0x1800175b8  sub     rsp, 28h
0x1800175bc  mov     rcx, [rcx]
0x1800175bf  test    rcx, rcx
0x1800175c2  jz      short loc_1800175D0
0x1800175c4  mov     rax, [rcx]
0x1800175c7  mov     rax, [rax+10h]
0x1800175cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d0  add     rsp, 28h
0x1800175d4  retn
```
