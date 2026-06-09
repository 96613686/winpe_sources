# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800069a8`
- end: `0x1800069e2`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012f60`

## callees

- `0x1800069a8`
- `0x180006a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800069c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800069c8`

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
0x1800069a8  push    rbx
0x1800069aa  sub     rsp, 20h
0x1800069ae  mov     rbx, rcx
0x1800069b1  test    rcx, rcx
0x1800069b4  jz      short loc_1800069D4
0x1800069b6  cmp     dword ptr [rcx], 48h ; 'H'
0x1800069b9  jnz     short loc_1800069D4
0x1800069bb  add     rcx, 38h ; '8'
0x1800069bf  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800069c4  lea     rcx, [rbx+8]; lpCriticalSection
0x1800069c8  call    cs:__imp_DeleteCriticalSection
0x1800069ce  mov     dword ptr [rbx], 0
0x1800069d4  lea     rcx, [rbx+38h]
0x1800069d8  add     rsp, 20h
0x1800069dc  pop     rbx
0x1800069dd  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
