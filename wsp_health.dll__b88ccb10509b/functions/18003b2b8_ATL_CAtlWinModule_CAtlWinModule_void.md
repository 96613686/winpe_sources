# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18003b2b8`
- end: `0x18003b2f2`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008b110`

## callees

- `0x18003b2b8`
- `0x18003b354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b2d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b2d8`

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
0x18003b2b8  push    rbx
0x18003b2ba  sub     rsp, 20h
0x18003b2be  mov     rbx, rcx
0x18003b2c1  test    rcx, rcx
0x18003b2c4  jz      short loc_18003B2E4
0x18003b2c6  cmp     dword ptr [rcx], 48h ; 'H'
0x18003b2c9  jnz     short loc_18003B2E4
0x18003b2cb  add     rcx, 38h ; '8'
0x18003b2cf  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003b2d4  lea     rcx, [rbx+8]; lpCriticalSection
0x18003b2d8  call    cs:__imp_DeleteCriticalSection
0x18003b2de  mov     dword ptr [rbx], 0
0x18003b2e4  lea     rcx, [rbx+38h]
0x18003b2e8  add     rsp, 20h
0x18003b2ec  pop     rbx
0x18003b2ed  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
