# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140003540`
- end: `0x14000361f`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001110`
- `0x14000111c`
- `0x140003540`
- `0x14000380c`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400035fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400035fd`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140003540  push    rbx
0x140003542  push    rbp
0x140003543  push    rsi
0x140003544  push    rdi
0x140003545  push    r14
0x140003547  push    r15
0x140003549  sub     rsp, 28h
0x14000354d  mov     r14, r8
0x140003550  mov     r15, rdx
0x140003553  mov     rdi, rcx
0x140003556  test    r8, r8
0x140003559  jnz     short loc_140003565
0x14000355b  mov     eax, 80004003h
0x140003560  jmp     loc_140003612
0x140003565  mov     ecx, 48h ; 'H'; Size
0x14000356a  mov     qword ptr [r8], 0
0x140003571  mov     esi, 8007000Eh
0x140003576  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000357b  mov     rbx, rax
0x14000357e  test    rax, rax
0x140003581  jz      loc_140003610
0x140003587  mov     dword ptr [rax+8], 0
0x14000358e  lea     rcx, [rbx+10h]; this
0x140003592  xor     eax, eax
0x140003594  xorps   xmm0, xmm0
0x140003597  movups  xmmword ptr [rbx+10h], xmm0
0x14000359b  movups  xmmword ptr [rbx+20h], xmm0
0x14000359f  mov     [rbx+30h], rax
0x1400035a3  mov     [rbx+38h], al
0x1400035a6  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x1400035ad  mov     [rbx], rax
0x1400035b0  mov     [rbx+40h], rdi
0x1400035b4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400035b9  lea     rdi, [rbx+38h]
0x1400035bd  mov     esi, eax
0x1400035bf  test    eax, eax
0x1400035c1  js      short loc_1400035E0
0x1400035c3  mov     byte ptr [rdi], 1
0x1400035c6  mov     r8, r14
0x1400035c9  mov     rax, [rbx]
0x1400035cc  mov     rdx, r15
0x1400035cf  mov     rcx, rbx
0x1400035d2  mov     rax, [rax]
0x1400035d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035da  mov     esi, eax
0x1400035dc  test    eax, eax
0x1400035de  jz      short loc_140003610
0x1400035e0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1400035e7  mov     dword ptr [rbx+8], 0C0000001h
0x1400035ee  mov     [rbx], rax
0x1400035f1  cmp     byte ptr [rdi], 0
0x1400035f4  jz      short loc_140003603
0x1400035f6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1400035fa  mov     byte ptr [rdi], 0
0x1400035fd  call    cs:__imp_DeleteCriticalSection
0x140003603  mov     edx, 48h ; 'H'
0x140003608  mov     rcx, rbx; Block
0x14000360b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003610  mov     eax, esi
0x140003612  add     rsp, 28h
0x140003616  pop     r15
0x140003618  pop     r14
0x14000361a  pop     rdi
0x14000361b  pop     rsi
0x14000361c  pop     rbp
0x14000361d  pop     rbx
0x14000361e  retn
```
