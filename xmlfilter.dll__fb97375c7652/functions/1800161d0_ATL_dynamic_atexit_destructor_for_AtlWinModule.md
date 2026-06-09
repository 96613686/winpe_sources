# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800161d0`
- end: `0x180016247`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002b14`
- `0x1800161d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001620b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001620b`

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
    qword_1800217D0 = 0;
    DeleteCriticalSection(&stru_180021798);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800217D0 = 0;
}

```

## disassembly

```asm
0x1800161d0  sub     rsp, 28h
0x1800161d4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800161db  jnz     short loc_18001621B
0x1800161dd  mov     rcx, cs:Block; Block
0x1800161e4  test    rcx, rcx
0x1800161e7  jz      short loc_1800161F9
0x1800161e9  call    free
0x1800161ee  mov     cs:Block, 0
0x1800161f9  lea     rcx, stru_180021798; lpCriticalSection
0x180016200  mov     cs:qword_1800217D0, 0
0x18001620b  call    cs:__imp_DeleteCriticalSection
0x180016211  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001621b  mov     rcx, cs:Block; Block
0x180016222  test    rcx, rcx
0x180016225  jz      short loc_180016237
0x180016227  call    free
0x18001622c  mov     cs:Block, 0
0x180016237  mov     cs:qword_1800217D0, 0
0x180016242  add     rsp, 28h
0x180016246  retn
```
