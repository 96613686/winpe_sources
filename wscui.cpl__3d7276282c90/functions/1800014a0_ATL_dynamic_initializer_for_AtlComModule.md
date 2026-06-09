# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800014a0`
- end: `0x1800014b9`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800014c0`
- `0x1800023f4`

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
0x1800014a0  sub     rsp, 28h
0x1800014a4  call    ??0CAtlComModule@ATL@@QEAA@XZ; ATL::CAtlComModule::CAtlComModule(void)
0x1800014a9  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800014b0  add     rsp, 28h
0x1800014b4  jmp     atexit
```
