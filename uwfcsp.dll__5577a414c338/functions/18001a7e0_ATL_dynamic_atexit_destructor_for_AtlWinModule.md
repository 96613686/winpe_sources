# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18001a7e0`
- end: `0x18001a859`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a7e0`

## import_xrefs

- `msvcrt!free` at `0x18001a7f9`
- `msvcrt!free` at `0x18001a838`
- `msvcrt!free` at `0x18001a7f9`
- `msvcrt!free` at `0x18001a838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a81c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a81c`

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
    qword_180027E20 = 0;
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180027E20 = 0;
}

```

## disassembly

```asm
0x18001a7e0  sub     rsp, 28h
0x18001a7e4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001a7eb  jnz     short loc_18001A82C
0x18001a7ed  mov     rcx, cs:Block; Block
0x18001a7f4  test    rcx, rcx
0x18001a7f7  jz      short loc_18001A80A
0x18001a7f9  call    cs:__imp_free
0x18001a7ff  mov     cs:Block, 0
0x18001a80a  lea     rcx, CriticalSection; lpCriticalSection
0x18001a811  mov     cs:qword_180027E20, 0
0x18001a81c  call    cs:__imp_DeleteCriticalSection
0x18001a822  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18001a82c  mov     rcx, cs:Block; Block
0x18001a833  test    rcx, rcx
0x18001a836  jz      short loc_18001A849
0x18001a838  call    cs:__imp_free
0x18001a83e  mov     cs:Block, 0
0x18001a849  mov     cs:qword_180027E20, 0
0x18001a854  add     rsp, 28h
0x18001a858  retn
```
