# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001bd0`
- end: `0x180001bfe`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001bd0`
- `0x180002518`
- `0x180011aec`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_180021280) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001bd0  sub     rsp, 28h
0x180001bd4  lea     rcx, stru_180021280; this
0x180001bdb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001be0  test    eax, eax
0x180001be2  js      short loc_180001BEE
0x180001be4  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001bee  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001bf5  add     rsp, 28h
0x180001bf9  jmp     atexit
```
