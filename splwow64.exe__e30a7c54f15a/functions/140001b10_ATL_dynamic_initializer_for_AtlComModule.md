# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x140001b10`
- end: `0x140001b3e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001b10`
- `0x140002154`
- `0x140004cd0`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_140021280) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x140001b10  sub     rsp, 28h
0x140001b14  lea     rcx, qword_140021280; this
0x140001b1b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001b20  test    eax, eax
0x140001b22  js      short loc_140001B2E
0x140001b24  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x140001b2e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x140001b35  add     rsp, 28h
0x140001b39  jmp     atexit
```
