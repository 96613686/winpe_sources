# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800339bc`
- end: `0x1800339f6`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036c80`

## callees

- `0x1800339bc`
- `0x180033a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800339dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800339dc`

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
0x1800339bc  push    rbx
0x1800339be  sub     rsp, 20h
0x1800339c2  mov     rbx, rcx
0x1800339c5  test    rcx, rcx
0x1800339c8  jz      short loc_1800339E8
0x1800339ca  cmp     dword ptr [rcx], 48h ; 'H'
0x1800339cd  jnz     short loc_1800339E8
0x1800339cf  add     rcx, 38h ; '8'
0x1800339d3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800339d8  lea     rcx, [rbx+8]; lpCriticalSection
0x1800339dc  call    cs:__imp_DeleteCriticalSection
0x1800339e2  mov     dword ptr [rbx], 0
0x1800339e8  lea     rcx, [rbx+38h]
0x1800339ec  add     rsp, 20h
0x1800339f0  pop     rbx
0x1800339f1  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
