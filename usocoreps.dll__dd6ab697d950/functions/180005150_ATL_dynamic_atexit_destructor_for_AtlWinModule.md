# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180005150`
- end: `0x1800051c7`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800020ee`
- `0x180005150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000518b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000518b`

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
    qword_18000C240 = 0;
    DeleteCriticalSection(&stru_18000C208);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18000C240 = 0;
}

```

## disassembly

```asm
0x180005150  sub     rsp, 28h
0x180005154  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000515b  jnz     short loc_18000519B
0x18000515d  mov     rcx, cs:Block; Block
0x180005164  test    rcx, rcx
0x180005167  jz      short loc_180005179
0x180005169  call    free
0x18000516e  mov     cs:Block, 0
0x180005179  lea     rcx, stru_18000C208; lpCriticalSection
0x180005180  mov     cs:qword_18000C240, 0
0x18000518b  call    cs:__imp_DeleteCriticalSection
0x180005191  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000519b  mov     rcx, cs:Block; Block
0x1800051a2  test    rcx, rcx
0x1800051a5  jz      short loc_1800051B7
0x1800051a7  call    free
0x1800051ac  mov     cs:Block, 0
0x1800051b7  mov     cs:qword_18000C240, 0
0x1800051c2  add     rsp, 28h
0x1800051c6  retn
```
