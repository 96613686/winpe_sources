# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800045b0`
- end: `0x180004691`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012c0`
- `0x1800012e4`
- `0x1800045b0`
- `0x180008180`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000466d`
- `KERNEL32!DeleteCriticalSection` at `0x18000466d`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
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
0x1800045b0  push    rbx
0x1800045b2  push    rbp
0x1800045b3  push    rsi
0x1800045b4  push    rdi
0x1800045b5  push    r14
0x1800045b7  push    r15
0x1800045b9  sub     rsp, 28h
0x1800045bd  mov     r14, r8
0x1800045c0  mov     r15, rdx
0x1800045c3  mov     rdi, rcx
0x1800045c6  test    r8, r8
0x1800045c9  jnz     short loc_1800045D5
0x1800045cb  mov     eax, 80004003h
0x1800045d0  jmp     loc_180004683
0x1800045d5  mov     ecx, 48h ; 'H'; Size
0x1800045da  mov     qword ptr [r8], 0
0x1800045e1  mov     esi, 8007000Eh
0x1800045e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045eb  mov     rbx, rax
0x1800045ee  test    rax, rax
0x1800045f1  jz      loc_180004681
0x1800045f7  mov     dword ptr [rax+8], 0
0x1800045fe  lea     rcx, [rbx+10h]; this
0x180004602  xor     eax, eax
0x180004604  xorps   xmm0, xmm0
0x180004607  movups  xmmword ptr [rbx+10h], xmm0
0x18000460b  movups  xmmword ptr [rbx+20h], xmm0
0x18000460f  mov     [rbx+30h], rax
0x180004613  mov     [rbx+38h], al
0x180004616  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000461d  mov     [rbx], rax
0x180004620  mov     [rbx+40h], rdi
0x180004624  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004629  lea     rdi, [rbx+38h]
0x18000462d  mov     esi, eax
0x18000462f  test    eax, eax
0x180004631  js      short loc_180004650
0x180004633  mov     byte ptr [rdi], 1
0x180004636  mov     r8, r14
0x180004639  mov     rax, [rbx]
0x18000463c  mov     rdx, r15
0x18000463f  mov     rcx, rbx
0x180004642  mov     rax, [rax]
0x180004645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464a  mov     esi, eax
0x18000464c  test    eax, eax
0x18000464e  jz      short loc_180004681
0x180004650  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004657  mov     dword ptr [rbx+8], 0C0000001h
0x18000465e  mov     [rbx], rax
0x180004661  cmp     byte ptr [rdi], 0
0x180004664  jz      short loc_180004679
0x180004666  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000466a  mov     byte ptr [rdi], 0
0x18000466d  call    cs:__imp_DeleteCriticalSection
0x180004674  nop     dword ptr [rax+rax+00h]
0x180004679  mov     rcx, rbx; Block
0x18000467c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004681  mov     eax, esi
0x180004683  add     rsp, 28h
0x180004687  pop     r15
0x180004689  pop     r14
0x18000468b  pop     rdi
0x18000468c  pop     rsi
0x18000468d  pop     rbp
0x18000468e  pop     rbx
0x18000468f  retn
```
