# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x140001060`
- end: `0x14000108e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001060`
- `0x140001730`
- `0x14000380c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_14000B0C0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x140001060  sub     rsp, 28h
0x140001064  lea     rcx, qword_14000B0C0; this
0x14000106b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001070  test    eax, eax
0x140001072  js      short loc_14000107E
0x140001074  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x14000107e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x140001085  add     rsp, 28h
0x140001089  jmp     atexit
```
