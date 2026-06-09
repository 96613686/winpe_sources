# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CContainer>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140003440`
- end: `0x14000352d`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCContainer@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000111c`
- `0x140003440`
- `0x14000380c`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CContainer>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _BYTE *v6; // rax
  _BYTE *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  int v9; // eax
  int v10; // ecx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x40u);
  v7 = v6;
  if ( v6 )
  {
    v8 = ATL::_pAtlModule;
    *((_DWORD *)v6 + 2) = 0;
    *((_OWORD *)v6 + 1) = 0;
    *((_OWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 6) = 0;
    v6[56] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CContainer>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v9 >= 0 )
      v7[56] = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v5 = 0;
    if ( v10 < 0 )
      v5 = v10;
    if ( v5 || (v5 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v7 + 48LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x140003440  push    rbx
0x140003442  push    rbp
0x140003443  push    rsi
0x140003444  push    rdi
0x140003445  sub     rsp, 28h
0x140003449  mov     rsi, r8
0x14000344c  mov     rbp, rdx
0x14000344f  test    rcx, rcx
0x140003452  jnz     loc_14000350A
0x140003458  test    r8, r8
0x14000345b  jz      loc_14000350F
0x140003461  mov     [r8], rcx
0x140003464  mov     ebx, 8007000Eh
0x140003469  mov     ecx, 40h ; '@'; Size
0x14000346e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003473  mov     rdi, rax
0x140003476  test    rax, rax
0x140003479  jz      loc_140003522
0x14000347f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003486  xorps   xmm0, xmm0
0x140003489  mov     dword ptr [rax+8], 0
0x140003490  xor     eax, eax
0x140003492  movups  xmmword ptr [rdi+10h], xmm0
0x140003496  movups  xmmword ptr [rdi+20h], xmm0
0x14000349a  mov     [rdi+30h], rax
0x14000349e  mov     [rdi+38h], al
0x1400034a1  lea     rax, ??_7?$CComObject@VCContainer@@@ATL@@6B@; const ATL::CComObject<CContainer>::`vftable'
0x1400034a8  mov     [rdi], rax
0x1400034ab  mov     rax, [rcx]
0x1400034ae  mov     rax, [rax+8]
0x1400034b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034b7  lea     rcx, [rdi+10h]; this
0x1400034bb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400034c0  test    eax, eax
0x1400034c2  js      short loc_1400034C8
0x1400034c4  mov     byte ptr [rdi+38h], 1
0x1400034c8  xor     ecx, ecx
0x1400034ca  test    eax, eax
0x1400034cc  cmovs   ecx, eax
0x1400034cf  xor     ebx, ebx
0x1400034d1  test    ecx, ecx
0x1400034d3  cmovs   ebx, ecx
0x1400034d6  test    ebx, ebx
0x1400034d8  jnz     short loc_1400034F4
0x1400034da  mov     rax, [rdi]
0x1400034dd  mov     r8, rsi
0x1400034e0  mov     rdx, rbp
0x1400034e3  mov     rcx, rdi
0x1400034e6  mov     rax, [rax]
0x1400034e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034ee  mov     ebx, eax
0x1400034f0  test    eax, eax
0x1400034f2  jz      short loc_140003522
0x1400034f4  mov     rax, [rdi]
0x1400034f7  mov     edx, 1
0x1400034fc  mov     rcx, rdi
0x1400034ff  mov     rax, [rax+30h]
0x140003503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003508  jmp     short loc_140003522
0x14000350a  test    rsi, rsi
0x14000350d  jnz     short loc_140003516
0x14000350f  mov     ebx, 80004003h
0x140003514  jmp     short loc_140003522
0x140003516  mov     qword ptr [r8], 0
0x14000351d  mov     ebx, 80040110h
0x140003522  mov     eax, ebx
0x140003524  add     rsp, 28h
0x140003528  pop     rdi
0x140003529  pop     rsi
0x14000352a  pop     rbp
0x14000352b  pop     rbx
0x14000352c  retn
```
