# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180072e0c`
- end: `0x180072e4c`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800aa740`

## callees

- `0x180072e0c`
- `0x180072eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072e2c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072e2c`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  if ( this && *(_DWORD *)this == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x180072e0c  push    rbx
0x180072e0e  sub     rsp, 20h
0x180072e12  mov     rbx, rcx
0x180072e15  test    rcx, rcx
0x180072e18  jz      short loc_180072E3E
0x180072e1a  cmp     dword ptr [rcx], 48h ; 'H'
0x180072e1d  jnz     short loc_180072E3E
0x180072e1f  add     rcx, 38h ; '8'
0x180072e23  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180072e28  lea     rcx, [rbx+8]; lpCriticalSection
0x180072e2c  call    cs:__imp_DeleteCriticalSection
0x180072e33  nop     dword ptr [rax+rax+00h]
0x180072e38  mov     dword ptr [rbx], 0
0x180072e3e  lea     rcx, [rbx+38h]
0x180072e42  add     rsp, 20h
0x180072e46  pop     rbx
0x180072e47  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
