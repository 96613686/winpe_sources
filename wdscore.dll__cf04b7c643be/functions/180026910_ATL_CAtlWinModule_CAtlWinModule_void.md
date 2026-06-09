# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180026910`
- end: `0x180026950`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029a00`

## callees

- `0x180026910`
- `0x180026aac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026930`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026930`

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
0x180026910  push    rbx
0x180026912  sub     rsp, 20h
0x180026916  mov     rbx, rcx
0x180026919  test    rcx, rcx
0x18002691c  jz      short loc_180026942
0x18002691e  cmp     dword ptr [rcx], 48h ; 'H'
0x180026921  jnz     short loc_180026942
0x180026923  add     rcx, 38h ; '8'
0x180026927  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002692c  lea     rcx, [rbx+8]; lpCriticalSection
0x180026930  call    cs:__imp_DeleteCriticalSection
0x180026937  nop     dword ptr [rax+rax+00h]
0x18002693c  mov     dword ptr [rbx], 0
0x180026942  lea     rcx, [rbx+38h]
0x180026946  add     rsp, 20h
0x18002694a  pop     rbx
0x18002694b  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
