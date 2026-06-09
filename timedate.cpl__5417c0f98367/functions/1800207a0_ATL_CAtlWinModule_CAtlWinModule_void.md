# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800207a0`
- end: `0x180020825`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800298c0`

## callees

- `0x18001affc`
- `0x1800207a0`
- `0x180020860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800207fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800207fd`
- `USER32!UnregisterClassA` at `0x1800207de`
- `USER32!UnregisterClassA` at `0x1800207de`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rbp
  int v4; // edi
  _QWORD *v5; // rsi

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    v4 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v5 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v4 < 0 || (v5 = (_QWORD *)((char *)this + 56), v4 >= *((_DWORD *)this + 16)) )
        {
          ATL::_AtlRaiseException(0xC000008C, a2);
          JUMPOUT(0x180020824LL);
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v5 + 2LL * v4++), v3);
      }
      while ( v4 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x1800207a0  push    rbx
0x1800207a2  push    rbp
0x1800207a3  push    rsi
0x1800207a4  push    rdi
0x1800207a5  sub     rsp, 28h
0x1800207a9  mov     rbx, rcx
0x1800207ac  test    rcx, rcx
0x1800207af  jz      short loc_180020809
0x1800207b1  cmp     dword ptr [rcx], 48h ; 'H'
0x1800207b4  jnz     short loc_180020809
0x1800207b6  mov     rbp, cs:hInstance
0x1800207bd  xor     edi, edi
0x1800207bf  cmp     [rcx+40h], edi
0x1800207c2  jle     short loc_1800207ED
0x1800207c4  test    edi, edi
0x1800207c6  js      short loc_18002081A
0x1800207c8  lea     rsi, [rbx+38h]
0x1800207cc  cmp     edi, [rsi+8]
0x1800207cf  jge     short loc_18002081A
0x1800207d1  mov     rax, [rsi]
0x1800207d4  mov     rdx, rbp; hInstance
0x1800207d7  movsxd  rcx, edi
0x1800207da  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800207de  call    cs:__imp_UnregisterClassA
0x1800207e4  inc     edi
0x1800207e6  cmp     edi, [rbx+40h]
0x1800207e9  jl      short loc_1800207C4
0x1800207eb  jmp     short loc_1800207F1
0x1800207ed  lea     rsi, [rcx+38h]
0x1800207f1  mov     rcx, rsi
0x1800207f4  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800207f9  lea     rcx, [rbx+8]; lpCriticalSection
0x1800207fd  call    cs:__imp_DeleteCriticalSection
0x180020803  mov     dword ptr [rbx], 0
0x180020809  lea     rcx, [rbx+38h]
0x18002080d  add     rsp, 28h
0x180020811  pop     rdi
0x180020812  pop     rsi
0x180020813  pop     rbp
0x180020814  pop     rbx
0x180020815  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002081a  mov     ecx, 0C000008Ch; unsigned int
0x18002081f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
