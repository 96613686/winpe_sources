# _dynamic_initializer_for__ComModule__

- ea: `0x180001010`
- end: `0x18000104c`
- name: `_dynamic_initializer_for__ComModule__`
- size: `60`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x1800018ec`
- `0x1800031ac`

## pseudocode

```c
int dynamic_initializer_for__ComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_18000C318) >= 0 )
    dword_18000C308 = 56;
  ComModule = &ATL::CComModule::`vftable';
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__ComModule__);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  lea     rcx, qword_18000C318; this
0x18000101b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001020  test    eax, eax
0x180001022  js      short loc_18000102E
0x180001024  mov     cs:dword_18000C308, 38h ; '8'
0x18000102e  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180001035  lea     rcx, _dynamic_atexit_destructor_for__ComModule__
0x18000103c  mov     cs:?ComModule@@3VCComModule@ATL@@A, rax; ATL::CComModule ComModule
0x180001043  add     rsp, 28h
0x180001047  jmp     atexit
```
