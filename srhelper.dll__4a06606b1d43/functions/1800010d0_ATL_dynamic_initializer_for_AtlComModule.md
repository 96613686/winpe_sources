# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800010d0`
- end: `0x1800010fe`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800010d0`
- `0x180001c40`
- `0x18000857c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_18001D130) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800010d0  sub     rsp, 28h
0x1800010d4  lea     rcx, stru_18001D130; this
0x1800010db  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800010e0  test    eax, eax
0x1800010e2  js      short loc_1800010EE
0x1800010e4  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800010ee  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800010f5  add     rsp, 28h
0x1800010f9  jmp     atexit
```
