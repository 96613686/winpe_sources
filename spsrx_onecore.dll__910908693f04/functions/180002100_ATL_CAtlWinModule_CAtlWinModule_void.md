# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180002100`
- end: `0x18000213a`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003680`

## callees

- `0x180002100`
- `0x1800088fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002120`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002120`

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
0x180002100  push    rbx
0x180002102  sub     rsp, 20h
0x180002106  mov     rbx, rcx
0x180002109  test    rcx, rcx
0x18000210c  jz      short loc_18000212C
0x18000210e  cmp     dword ptr [rcx], 48h ; 'H'
0x180002111  jnz     short loc_18000212C
0x180002113  add     rcx, 38h ; '8'
0x180002117  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000211c  lea     rcx, [rbx+8]; lpCriticalSection
0x180002120  call    cs:__imp_DeleteCriticalSection
0x180002126  mov     dword ptr [rbx], 0
0x18000212c  lea     rcx, [rbx+38h]
0x180002130  add     rsp, 20h
0x180002134  pop     rbx
0x180002135  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
