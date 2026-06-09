# _dynamic_atexit_destructor_for__IdleHandler::m_idleLock__

- ea: `0x140015810`
- end: `0x140015839`
- name: `_dynamic_atexit_destructor_for__IdleHandler::m_idleLock__`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140015810`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140015824`
- `KERNEL32!DeleteCriticalSection` at `0x140015824`

## pseudocode

```c
void dynamic_atexit_destructor_for__IdleHandler::m_idleLock__()
{
  if ( dword_140021500 >= 0 )
  {
    DeleteCriticalSection(&IdleHandler::m_idleLock);
    dword_140021500 = -2147467259;
  }
}

```

## disassembly

```asm
0x140015810  sub     rsp, 28h
0x140015814  cmp     cs:dword_140021500, 0
0x14001581b  jl      short loc_140015834
0x14001581d  lea     rcx, ?m_idleLock@IdleHandler@@0VTCriticalSection@NCoreLibrary@@A; lpCriticalSection
0x140015824  call    cs:__imp_DeleteCriticalSection
0x14001582a  mov     cs:dword_140021500, 80004005h
0x140015834  add     rsp, 28h
0x140015838  retn
```
