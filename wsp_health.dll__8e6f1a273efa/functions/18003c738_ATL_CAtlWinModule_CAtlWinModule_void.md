# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18003c738`
- end: `0x18003c778`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008d6d0`

## callees

- `0x18003c738`
- `0x18003c7e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c758`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c758`

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
0x18003c738  push    rbx
0x18003c73a  sub     rsp, 20h
0x18003c73e  mov     rbx, rcx
0x18003c741  test    rcx, rcx
0x18003c744  jz      short loc_18003C76A
0x18003c746  cmp     dword ptr [rcx], 48h ; 'H'
0x18003c749  jnz     short loc_18003C76A
0x18003c74b  add     rcx, 38h ; '8'
0x18003c74f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003c754  lea     rcx, [rbx+8]; lpCriticalSection
0x18003c758  call    cs:__imp_DeleteCriticalSection
0x18003c75f  nop     dword ptr [rax+rax+00h]
0x18003c764  mov     dword ptr [rbx], 0
0x18003c76a  lea     rcx, [rbx+38h]
0x18003c76e  add     rsp, 20h
0x18003c772  pop     rbx
0x18003c773  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
