# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800011d0`
- end: `0x180001207`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800011d0`
- `0x180001e00`
- `0x18000968c`

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
0x1800011d0  sub     rsp, 28h
0x1800011d4  lea     rcx, CriticalSection; this
0x1800011db  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800011e0  test    eax, eax
0x1800011e2  jns     short loc_1800011ED
0x1800011e4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800011eb  jmp     short loc_1800011F7
0x1800011ed  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800011f7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800011fe  add     rsp, 28h
0x180001202  jmp     atexit
```
