# CCFPerfProp::CreateImpObj(void)

- ea: `0x1800126b0`
- end: `0x180012710`
- name: `?CreateImpObj@CCFPerfProp@@UEAAPEAUIUnknown@@XZ`
- size: `96`
- prototype: `struct IUnknown *__fastcall(CCFPerfProp *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e44c`
- `0x18000f914`
- `0x1800126b0`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800126bb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800126e6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800126bb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800126e6`

## pseudocode

```c
struct IUnknown *__fastcall CCFPerfProp::CreateImpObj(CCFPerfProp *this)
{
  CImpDynProp *v1; // rax
  CImpDynProp *v2; // rbx
  _QWORD *v3; // rcx
  CImpPerf *v4; // rax

  v1 = (CImpDynProp *)CWin32DefaultArena::WbemMemAlloc(0x68u);
  v2 = v1;
  if ( !v1 )
    return 0;
  CImpDynProp::CImpDynProp(v1);
  *v3 = &CImpPerfProp::`vftable';
  v4 = (CImpPerf *)CWin32DefaultArena::WbemMemAlloc(0x2B0u);
  if ( v4 )
    v4 = CImpPerf::CImpPerf(v4);
  *((_QWORD *)v2 + 12) = v4;
  return (struct IUnknown *)v2;
}

```

## disassembly

```asm
0x1800126b0  push    rbx
0x1800126b2  sub     rsp, 20h
0x1800126b6  mov     ecx, 68h ; 'h'
0x1800126bb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800126c1  mov     rbx, rax
0x1800126c4  mov     [rsp+28h+arg_8], rax
0x1800126c9  test    rax, rax
0x1800126cc  jz      short loc_180012705
0x1800126ce  mov     rcx, rax; this
0x1800126d1  call    ??0CImpDynProp@@QEAA@XZ; CImpDynProp::CImpDynProp(void)
0x1800126d6  nop
0x1800126d7  lea     rax, ??_7CImpPerfProp@@6B@; const CImpPerfProp::`vftable'
0x1800126de  mov     [rcx], rax
0x1800126e1  mov     ecx, 2B0h
0x1800126e6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800126ec  mov     [rsp+28h+arg_10], rax
0x1800126f1  test    rax, rax
0x1800126f4  jz      short loc_1800126FF
0x1800126f6  mov     rcx, rax; this
0x1800126f9  call    ??0CImpPerf@@QEAA@XZ; CImpPerf::CImpPerf(void)
0x1800126fe  nop
0x1800126ff  mov     [rbx+60h], rax
0x180012703  jmp     short loc_180012707
0x180012705  xor     ebx, ebx
0x180012707  mov     rax, rbx
0x18001270a  add     rsp, 20h
0x18001270e  pop     rbx
0x18001270f  retn
```
