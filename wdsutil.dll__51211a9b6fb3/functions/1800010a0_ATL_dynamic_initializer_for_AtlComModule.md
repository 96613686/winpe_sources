# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800010a0`
- end: `0x1800010ce`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800010a0`
- `0x180001c74`
- `0x18000819c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_18004C8E0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800010a0  sub     rsp, 28h
0x1800010a4  lea     rcx, qword_18004C8E0; this
0x1800010ab  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800010b0  test    eax, eax
0x1800010b2  js      short loc_1800010BE
0x1800010b4  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800010be  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800010c5  add     rsp, 28h
0x1800010c9  jmp     atexit
```
