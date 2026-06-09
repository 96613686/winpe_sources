# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001900`
- end: `0x180001937`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001900`
- `0x180002340`
- `0x18001bf1c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_180048100) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001900  sub     rsp, 28h
0x180001904  lea     rcx, qword_180048100; this
0x18000190b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001910  test    eax, eax
0x180001912  jns     short loc_18000191D
0x180001914  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000191b  jmp     short loc_180001927
0x18000191d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001927  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000192e  add     rsp, 28h
0x180001932  jmp     atexit
```
