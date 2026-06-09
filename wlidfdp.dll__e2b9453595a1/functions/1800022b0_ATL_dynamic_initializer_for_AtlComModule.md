# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800022b0`
- end: `0x1800022e7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800022b0`
- `0x180002bd8`
- `0x18000424c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_180020100) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800022b0  sub     rsp, 28h
0x1800022b4  lea     rcx, qword_180020100; this
0x1800022bb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800022c0  test    eax, eax
0x1800022c2  jns     short loc_1800022CD
0x1800022c4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800022cb  jmp     short loc_1800022D7
0x1800022cd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800022d7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800022de  add     rsp, 28h
0x1800022e2  jmp     atexit
```
