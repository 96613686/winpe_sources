# CCFRegProp::CreateImpObj(void)

- ea: `0x180012720`
- end: `0x180012780`
- name: `?CreateImpObj@CCFRegProp@@UEAAPEAUIUnknown@@XZ`
- size: `96`
- prototype: `struct IUnknown *__fastcall(CCFRegProp *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b630`
- `0x18000e44c`
- `0x180012720`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001272b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180012756`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001272b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180012756`

## pseudocode

```c
struct IUnknown *__fastcall CCFRegProp::CreateImpObj(CCFRegProp *this)
{
  CImpDynProp *v1; // rax
  CImpDynProp *v2; // rbx
  _QWORD *v3; // rcx
  CImpReg *v4; // rax

  v1 = (CImpDynProp *)CWin32DefaultArena::WbemMemAlloc(0x68u);
  v2 = v1;
  if ( !v1 )
    return 0;
  CImpDynProp::CImpDynProp(v1);
  *v3 = &CImpRegProp::`vftable';
  v4 = (CImpReg *)CWin32DefaultArena::WbemMemAlloc(0xC8u);
  if ( v4 )
    v4 = CImpReg::CImpReg(v4);
  *((_QWORD *)v2 + 12) = v4;
  return (struct IUnknown *)v2;
}

```

## disassembly

```asm
0x180012720  push    rbx
0x180012722  sub     rsp, 20h
0x180012726  mov     ecx, 68h ; 'h'
0x18001272b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180012731  mov     rbx, rax
0x180012734  mov     [rsp+28h+arg_8], rax
0x180012739  test    rax, rax
0x18001273c  jz      short loc_180012775
0x18001273e  mov     rcx, rax; this
0x180012741  call    ??0CImpDynProp@@QEAA@XZ; CImpDynProp::CImpDynProp(void)
0x180012746  nop
0x180012747  lea     rax, ??_7CImpRegProp@@6B@; const CImpRegProp::`vftable'
0x18001274e  mov     [rcx], rax
0x180012751  mov     ecx, 0C8h
0x180012756  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001275c  mov     [rsp+28h+arg_10], rax
0x180012761  test    rax, rax
0x180012764  jz      short loc_18001276F
0x180012766  mov     rcx, rax; this
0x180012769  call    ??0CImpReg@@QEAA@XZ; CImpReg::CImpReg(void)
0x18001276e  nop
0x18001276f  mov     [rbx+60h], rax
0x180012773  jmp     short loc_180012777
0x180012775  xor     ebx, ebx
0x180012777  mov     rax, rbx
0x18001277a  add     rsp, 20h
0x18001277e  pop     rbx
0x18001277f  retn
```
