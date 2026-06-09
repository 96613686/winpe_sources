# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180025a40`
- end: `0x180025ac0`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `128`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180036060`

## callees

- `0x180025a40`
- `0x180025afc`
- `0x180025b38`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180025a9d`
- `KERNEL32!DeleteCriticalSection` at `0x180025a9d`
- `USER32!UnregisterClassA` at `0x180025a7e`
- `USER32!UnregisterClassA` at `0x180025a7e`

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
          ATL::_AtlRaiseException((unsigned int)this, a2);
          JUMPOUT(0x180025ABFLL);
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
0x180025a40  push    rbx
0x180025a42  push    rbp
0x180025a43  push    rsi
0x180025a44  push    rdi
0x180025a45  sub     rsp, 28h
0x180025a49  mov     rbx, rcx
0x180025a4c  test    rcx, rcx
0x180025a4f  jz      short loc_180025AA9
0x180025a51  cmp     dword ptr [rcx], 48h ; 'H'
0x180025a54  jnz     short loc_180025AA9
0x180025a56  mov     rbp, cs:hInstance
0x180025a5d  xor     edi, edi
0x180025a5f  cmp     [rcx+40h], edi
0x180025a62  jle     short loc_180025A8D
0x180025a64  test    edi, edi
0x180025a66  js      short loc_180025ABA
0x180025a68  lea     rsi, [rbx+38h]
0x180025a6c  cmp     edi, [rsi+8]
0x180025a6f  jge     short loc_180025ABA
0x180025a71  mov     rax, [rsi]
0x180025a74  mov     rdx, rbp; hInstance
0x180025a77  movsxd  rcx, edi
0x180025a7a  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180025a7e  call    cs:__imp_UnregisterClassA
0x180025a84  inc     edi
0x180025a86  cmp     edi, [rbx+40h]
0x180025a89  jl      short loc_180025A64
0x180025a8b  jmp     short loc_180025A91
0x180025a8d  lea     rsi, [rcx+38h]
0x180025a91  mov     rcx, rsi
0x180025a94  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180025a99  lea     rcx, [rbx+8]; lpCriticalSection
0x180025a9d  call    cs:__imp_DeleteCriticalSection
0x180025aa3  mov     dword ptr [rbx], 0
0x180025aa9  lea     rcx, [rbx+38h]; unsigned int
0x180025aad  add     rsp, 28h
0x180025ab1  pop     rdi
0x180025ab2  pop     rsi
0x180025ab3  pop     rbp
0x180025ab4  pop     rbx
0x180025ab5  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180025aba  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
