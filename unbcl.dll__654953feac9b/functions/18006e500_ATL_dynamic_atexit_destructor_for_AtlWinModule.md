# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18006e500`
- end: `0x18006e579`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18006e500`

## import_xrefs

- `msvcrt!free` at `0x18006e519`
- `msvcrt!free` at `0x18006e558`
- `msvcrt!free` at `0x18006e519`
- `msvcrt!free` at `0x18006e558`
- `KERNEL32!DeleteCriticalSection` at `0x18006e53c`
- `KERNEL32!DeleteCriticalSection` at `0x18006e53c`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    qword_1800FF400 = 0;
    DeleteCriticalSection(&stru_1800FF3C8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800FF400 = 0;
}

```

## disassembly

```asm
0x18006e500  sub     rsp, 28h
0x18006e504  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18006e50b  jnz     short loc_18006E54C
0x18006e50d  mov     rcx, cs:Block; Block
0x18006e514  test    rcx, rcx
0x18006e517  jz      short loc_18006E52A
0x18006e519  call    cs:__imp_free
0x18006e51f  mov     cs:Block, 0
0x18006e52a  lea     rcx, stru_1800FF3C8; lpCriticalSection
0x18006e531  mov     cs:qword_1800FF400, 0
0x18006e53c  call    cs:__imp_DeleteCriticalSection
0x18006e542  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18006e54c  mov     rcx, cs:Block; Block
0x18006e553  test    rcx, rcx
0x18006e556  jz      short loc_18006E569
0x18006e558  call    cs:__imp_free
0x18006e55e  mov     cs:Block, 0
0x18006e569  mov     cs:qword_1800FF400, 0
0x18006e574  add     rsp, 28h
0x18006e578  retn
```
