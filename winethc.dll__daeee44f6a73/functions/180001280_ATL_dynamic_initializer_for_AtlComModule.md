# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001280`
- end: `0x1800012b7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001280`
- `0x180001c30`
- `0x180008180`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001280  sub     rsp, 28h
0x180001284  lea     rcx, CriticalSection; this
0x18000128b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001290  test    eax, eax
0x180001292  jns     short loc_18000129D
0x180001294  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000129b  jmp     short loc_1800012A7
0x18000129d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800012a7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800012ae  add     rsp, 28h
0x1800012b2  jmp     atexit
```
