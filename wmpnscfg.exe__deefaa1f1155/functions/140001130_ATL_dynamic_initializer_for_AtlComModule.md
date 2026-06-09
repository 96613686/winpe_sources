# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x140001130`
- end: `0x14000115e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001130`
- `0x140001764`
- `0x1400034ec`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_14000C0C0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x140001130  sub     rsp, 28h
0x140001134  lea     rcx, qword_14000C0C0; this
0x14000113b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001140  test    eax, eax
0x140001142  js      short loc_14000114E
0x140001144  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x14000114e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x140001155  add     rsp, 28h
0x140001159  jmp     atexit
```
