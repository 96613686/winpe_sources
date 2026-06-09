# TzautoupdateWorker::InitializeFinders(bool)

- ea: `0x1800175d0`
- end: `0x180017710`
- name: `?InitializeFinders@TzautoupdateWorker@@AEAA?AV?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@_N@Z`
- size: `320`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180004018`

## callees

- `0x180002050`
- `0x1800175d0`
- `0x1800177c4`

## pseudocode

```c
_QWORD *__fastcall TzautoupdateWorker::InitializeFinders(__int64 a1, _QWORD *a2, char a3)
{
  _QWORD *v5; // rdi
  _QWORD *v6; // rdi
  _QWORD *v7; // rdi
  _QWORD *v8; // rdi

  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v5 = operator new(8u);
  if ( v5 )
    *v5 = &HilbertFinder::`vftable';
  else
    v5 = 0;
  if ( a2[1] == a2[2] )
    std::vector<std::unique_ptr<Finder>>::_Reserve(a2);
  *(_QWORD *)a2[1] = v5;
  a2[1] += 8LL;
  v6 = operator new(8u);
  if ( v6 )
    *v6 = &CountryCodeFinder::`vftable';
  else
    v6 = 0;
  if ( a2[1] == a2[2] )
    std::vector<std::unique_ptr<Finder>>::_Reserve(a2);
  *(_QWORD *)a2[1] = v6;
  a2[1] += 8LL;
  v7 = operator new(8u);
  if ( v7 )
    *v7 = &NitzFinder::`vftable';
  else
    v7 = 0;
  if ( a2[1] == a2[2] )
    std::vector<std::unique_ptr<Finder>>::_Reserve(a2);
  *(_QWORD *)a2[1] = v7;
  a2[1] += 8LL;
  if ( !a3 )
  {
    v8 = operator new(8u);
    if ( v8 )
      *v8 = &RegionFinder::`vftable';
    else
      v8 = 0;
    if ( a2[1] == a2[2] )
      std::vector<std::unique_ptr<Finder>>::_Reserve(a2);
    *(_QWORD *)a2[1] = v8;
    a2[1] += 8LL;
  }
  return a2;
}

```

## disassembly

```asm
0x1800175d0  mov     [rsp+arg_8], rdx
0x1800175d5  push    rbx
0x1800175d6  push    rsi
0x1800175d7  push    rdi
0x1800175d8  push    r14
0x1800175da  sub     rsp, 38h
0x1800175de  mov     sil, r8b
0x1800175e1  mov     rbx, rdx
0x1800175e4  mov     [rsp+58h+var_38], 0
0x1800175ec  mov     qword ptr [rdx], 0
0x1800175f3  mov     qword ptr [rdx+8], 0
0x1800175fb  mov     qword ptr [rdx+10h], 0
0x180017603  mov     [rsp+58h+var_38], 1
0x18001760b  mov     r14d, 8
0x180017611  mov     ecx, r14d; Size
0x180017614  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017619  mov     rdi, rax
0x18001761c  test    rax, rax
0x18001761f  jz      short loc_18001762D
0x180017621  lea     rax, ??_7HilbertFinder@@6B@; const HilbertFinder::`vftable'
0x180017628  mov     [rdi], rax
0x18001762b  jmp     short loc_18001762F
0x18001762d  xor     edi, edi
0x18001762f  mov     rax, [rbx+10h]
0x180017633  cmp     [rbx+8], rax
0x180017637  jnz     short loc_180017641
0x180017639  mov     rcx, rbx
0x18001763c  call    ?_Reserve@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<Finder>>::_Reserve(unsigned __int64)
0x180017641  mov     rax, [rbx+8]
0x180017645  mov     [rax], rdi
0x180017648  add     [rbx+8], r14
0x18001764c  mov     rcx, r14; Size
0x18001764f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017654  mov     rdi, rax
0x180017657  test    rax, rax
0x18001765a  jz      short loc_180017668
0x18001765c  lea     rax, ??_7CountryCodeFinder@@6B@; const CountryCodeFinder::`vftable'
0x180017663  mov     [rdi], rax
0x180017666  jmp     short loc_18001766A
0x180017668  xor     edi, edi
0x18001766a  mov     rax, [rbx+10h]
0x18001766e  cmp     [rbx+8], rax
0x180017672  jnz     short loc_18001767C
0x180017674  mov     rcx, rbx
0x180017677  call    ?_Reserve@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<Finder>>::_Reserve(unsigned __int64)
0x18001767c  mov     rax, [rbx+8]
0x180017680  mov     [rax], rdi
0x180017683  add     [rbx+8], r14
0x180017687  mov     rcx, r14; Size
0x18001768a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001768f  mov     rdi, rax
0x180017692  test    rax, rax
0x180017695  jz      short loc_1800176A3
0x180017697  lea     rax, ??_7NitzFinder@@6B@; const NitzFinder::`vftable'
0x18001769e  mov     [rdi], rax
0x1800176a1  jmp     short loc_1800176A5
0x1800176a3  xor     edi, edi
0x1800176a5  mov     rax, [rbx+10h]
0x1800176a9  cmp     [rbx+8], rax
0x1800176ad  jnz     short loc_1800176B7
0x1800176af  mov     rcx, rbx
0x1800176b2  call    ?_Reserve@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<Finder>>::_Reserve(unsigned __int64)
0x1800176b7  mov     rax, [rbx+8]
0x1800176bb  mov     [rax], rdi
0x1800176be  add     [rbx+8], r14
0x1800176c2  test    sil, sil
0x1800176c5  jnz     short loc_180017702
0x1800176c7  mov     rcx, r14; Size
0x1800176ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800176cf  mov     rdi, rax
0x1800176d2  test    rax, rax
0x1800176d5  jz      short loc_1800176E3
0x1800176d7  lea     rax, ??_7RegionFinder@@6B@; const RegionFinder::`vftable'
0x1800176de  mov     [rdi], rax
0x1800176e1  jmp     short loc_1800176E5
0x1800176e3  xor     edi, edi
0x1800176e5  mov     rax, [rbx+10h]
0x1800176e9  cmp     [rbx+8], rax
0x1800176ed  jnz     short loc_1800176F7
0x1800176ef  mov     rcx, rbx
0x1800176f2  call    ?_Reserve@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<Finder>>::_Reserve(unsigned __int64)
0x1800176f7  mov     rax, [rbx+8]
0x1800176fb  mov     [rax], rdi
0x1800176fe  add     [rbx+8], r14
0x180017702  mov     rax, rbx
0x180017705  add     rsp, 38h
0x180017709  pop     r14
0x18001770b  pop     rdi
0x18001770c  pop     rsi
0x18001770d  pop     rbx
0x18001770e  retn
```
