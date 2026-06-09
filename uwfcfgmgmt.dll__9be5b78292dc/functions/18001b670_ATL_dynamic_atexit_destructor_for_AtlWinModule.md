# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18001b670`
- end: `0x18001b6e9`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b670`

## import_xrefs

- `msvcrt!free` at `0x18001b689`
- `msvcrt!free` at `0x18001b6c8`
- `msvcrt!free` at `0x18001b689`
- `msvcrt!free` at `0x18001b6c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b6ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b6ac`

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
    qword_18002A580 = 0;
    DeleteCriticalSection(&stru_18002A548);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18002A580 = 0;
}

```

## disassembly

```asm
0x18001b670  sub     rsp, 28h
0x18001b674  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001b67b  jnz     short loc_18001B6BC
0x18001b67d  mov     rcx, cs:Block; Block
0x18001b684  test    rcx, rcx
0x18001b687  jz      short loc_18001B69A
0x18001b689  call    cs:__imp_free
0x18001b68f  mov     cs:Block, 0
0x18001b69a  lea     rcx, stru_18002A548; lpCriticalSection
0x18001b6a1  mov     cs:qword_18002A580, 0
0x18001b6ac  call    cs:__imp_DeleteCriticalSection
0x18001b6b2  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001b6bc  mov     rcx, cs:Block; Block
0x18001b6c3  test    rcx, rcx
0x18001b6c6  jz      short loc_18001B6D9
0x18001b6c8  call    cs:__imp_free
0x18001b6ce  mov     cs:Block, 0
0x18001b6d9  mov     cs:qword_18002A580, 0
0x18001b6e4  add     rsp, 28h
0x18001b6e8  retn
```
