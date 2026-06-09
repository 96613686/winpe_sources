# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdController>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a590`
- end: `0x18000a690`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@V?$CComClassFactorySingleton@VCSdController@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001554`
- `0x180001578`
- `0x18000a590`
- `0x18000ac0c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a673`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a673`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdController>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi
  __int64 v11; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x58u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *((_DWORD *)v8 + 18) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *(_QWORD *)v8 = &ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdController>>::`vftable';
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactorySingleton<CSdController>::`vftable';
      v11 = *((_QWORD *)v9 + 10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
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
0x18000a590  push    rbx
0x18000a592  push    rbp
0x18000a593  push    rsi
0x18000a594  push    rdi
0x18000a595  push    r14
0x18000a597  push    r15
0x18000a599  sub     rsp, 28h
0x18000a59d  mov     r14, r8
0x18000a5a0  mov     r15, rdx
0x18000a5a3  mov     rdi, rcx
0x18000a5a6  test    r8, r8
0x18000a5a9  jnz     short loc_18000A5B5
0x18000a5ab  mov     eax, 80004003h
0x18000a5b0  jmp     loc_18000A683
0x18000a5b5  mov     ecx, 58h ; 'X'; Size
0x18000a5ba  mov     qword ptr [r8], 0
0x18000a5c1  mov     esi, 8007000Eh
0x18000a5c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5cb  mov     rbx, rax
0x18000a5ce  test    rax, rax
0x18000a5d1  jz      loc_18000A681
0x18000a5d7  mov     dword ptr [rax+8], 0
0x18000a5de  lea     rcx, [rbx+10h]; this
0x18000a5e2  xor     eax, eax
0x18000a5e4  xorps   xmm0, xmm0
0x18000a5e7  movups  xmmword ptr [rbx+10h], xmm0
0x18000a5eb  movups  xmmword ptr [rbx+20h], xmm0
0x18000a5ef  mov     [rbx+30h], rax
0x18000a5f3  mov     [rbx+38h], al
0x18000a5f6  mov     [rbx+48h], eax
0x18000a5f9  mov     [rbx+50h], rax
0x18000a5fd  lea     rax, ??_7?$CComObjectNoLock@V?$CComClassFactorySingleton@VCSdController@@@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdController>>::`vftable'
0x18000a604  mov     [rbx], rax
0x18000a607  mov     [rbx+40h], rdi
0x18000a60b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000a610  lea     rdi, [rbx+38h]
0x18000a614  mov     esi, eax
0x18000a616  test    eax, eax
0x18000a618  js      short loc_18000A637
0x18000a61a  mov     byte ptr [rdi], 1
0x18000a61d  mov     r8, r14
0x18000a620  mov     rax, [rbx]
0x18000a623  mov     rdx, r15
0x18000a626  mov     rcx, rbx
0x18000a629  mov     rax, [rax]
0x18000a62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a631  mov     esi, eax
0x18000a633  test    eax, eax
0x18000a635  jz      short loc_18000A681
0x18000a637  lea     rax, ??_7?$CComClassFactorySingleton@VCSdController@@@ATL@@6B@; const ATL::CComClassFactorySingleton<CSdController>::`vftable'
0x18000a63e  mov     dword ptr [rbx+8], 0C0000001h
0x18000a645  mov     [rbx], rax
0x18000a648  mov     rcx, [rbx+50h]
0x18000a64c  test    rcx, rcx
0x18000a64f  jz      short loc_18000A65D
0x18000a651  mov     rax, [rcx]
0x18000a654  mov     rax, [rax+10h]
0x18000a658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a65d  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000a664  mov     [rbx], rax
0x18000a667  cmp     byte ptr [rdi], 0
0x18000a66a  jz      short loc_18000A679
0x18000a66c  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a670  mov     byte ptr [rdi], 0
0x18000a673  call    cs:__imp_DeleteCriticalSection
0x18000a679  mov     rcx, rbx; Block
0x18000a67c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a681  mov     eax, esi
0x18000a683  add     rsp, 28h
0x18000a687  pop     r15
0x18000a689  pop     r14
0x18000a68b  pop     rdi
0x18000a68c  pop     rsi
0x18000a68d  pop     rbp
0x18000a68e  pop     rbx
0x18000a68f  retn
```
