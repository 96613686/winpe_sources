# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000bce8`
- end: `0x18000bd22`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180033710`

## callees

- `0x18000bce8`
- `0x18000bd5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bd08`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bd08`

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
0x18000bce8  push    rbx
0x18000bcea  sub     rsp, 20h
0x18000bcee  mov     rbx, rcx
0x18000bcf1  test    rcx, rcx
0x18000bcf4  jz      short loc_18000BD14
0x18000bcf6  cmp     dword ptr [rcx], 48h ; 'H'
0x18000bcf9  jnz     short loc_18000BD14
0x18000bcfb  add     rcx, 38h ; '8'
0x18000bcff  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000bd04  lea     rcx, [rbx+8]; lpCriticalSection
0x18000bd08  call    cs:__imp_DeleteCriticalSection
0x18000bd0e  mov     dword ptr [rbx], 0
0x18000bd14  lea     rcx, [rbx+38h]
0x18000bd18  add     rsp, 20h
0x18000bd1c  pop     rbx
0x18000bd1d  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
