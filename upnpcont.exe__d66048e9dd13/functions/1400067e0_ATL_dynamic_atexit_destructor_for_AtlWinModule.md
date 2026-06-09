# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1400067e0`
- end: `0x140006857`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001df4`
- `0x1400067e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000681b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000681b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( qword_14000B238 )
    {
      free(qword_14000B238);
      qword_14000B238 = 0;
    }
    qword_14000B240 = 0;
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_14000B238 )
  {
    free(qword_14000B238);
    qword_14000B238 = 0;
  }
  qword_14000B240 = 0;
}

```

## disassembly

```asm
0x1400067e0  sub     rsp, 28h
0x1400067e4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1400067eb  jnz     short loc_14000682B
0x1400067ed  mov     rcx, cs:qword_14000B238; Block
0x1400067f4  test    rcx, rcx
0x1400067f7  jz      short loc_140006809
0x1400067f9  call    free
0x1400067fe  mov     cs:qword_14000B238, 0
0x140006809  lea     rcx, CriticalSection; lpCriticalSection
0x140006810  mov     cs:qword_14000B240, 0
0x14000681b  call    cs:__imp_DeleteCriticalSection
0x140006821  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x14000682b  mov     rcx, cs:qword_14000B238; Block
0x140006832  test    rcx, rcx
0x140006835  jz      short loc_140006847
0x140006837  call    free
0x14000683c  mov     cs:qword_14000B238, 0
0x140006847  mov     cs:qword_14000B240, 0
0x140006852  add     rsp, 28h
0x140006856  retn
```
