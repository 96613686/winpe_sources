# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001070`
- end: `0x180001089`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800014e0`
- `0x18000297c`

## pseudocode

```c
int __fastcall ATL::_dynamic_initializer_for___AtlComModule__(ATL::CAtlComModule *a1)
{
  ATL::CAtlComModule::CAtlComModule(a1);
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001070  sub     rsp, 28h
0x180001074  call    ??0CAtlComModule@ATL@@QEAA@XZ; ATL::CAtlComModule::CAtlComModule(void)
0x180001079  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001080  add     rsp, 28h
0x180001084  jmp     atexit
```
