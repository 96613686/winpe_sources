# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003680`
- end: `0x18000376f`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d4`
- `0x1800018e4`
- `0x180003680`
- `0x1800038ec`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000373a`
- `KERNEL32!DeleteCriticalSection` at `0x18000373a`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  char *v7; // rbx
  _BYTE *v8; // rdi
  int v9; // ebp

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = (char *)operator new(0x48u);
  *((_DWORD *)v7 + 2) = 0;
  *((_OWORD *)v7 + 1) = 0;
  *((_OWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 6) = 0;
  v7[56] = 0;
  *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  *((_QWORD *)v7 + 8) = a1;
  v8 = v7 + 56;
  v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
  if ( v9 < 0 || (*v8 = 1, (v9 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0) )
  {
    *((_DWORD *)v7 + 2) = -1073741823;
    *(_QWORD *)v7 = &ATL::CComClassFactory::`vftable';
    if ( *v8 )
    {
      *v8 = 0;
      DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    }
    operator delete(v7);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003680  mov     [rsp+arg_0], rbx
0x180003685  mov     [rsp+arg_8], rbp
0x18000368a  mov     [rsp+arg_10], rsi
0x18000368f  push    rdi
0x180003690  push    r14
0x180003692  push    r15
0x180003694  sub     rsp, 20h
0x180003698  mov     rsi, r8
0x18000369b  mov     r15, rdx
0x18000369e  mov     rdi, rcx
0x1800036a1  test    r8, r8
0x1800036a4  jnz     short loc_1800036B0
0x1800036a6  mov     eax, 80004003h
0x1800036ab  jmp     loc_180003755
0x1800036b0  mov     ecx, 48h ; 'H'; Size
0x1800036b5  mov     qword ptr [r8], 0
0x1800036bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036c1  mov     rbx, rax
0x1800036c4  xorps   xmm0, xmm0
0x1800036c7  mov     dword ptr [rax+8], 0
0x1800036ce  xor     eax, eax
0x1800036d0  movups  xmmword ptr [rbx+10h], xmm0
0x1800036d4  lea     rcx, [rbx+10h]; this
0x1800036d8  movups  xmmword ptr [rbx+20h], xmm0
0x1800036dc  mov     [rbx+30h], rax
0x1800036e0  mov     [rbx+38h], al
0x1800036e3  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800036ea  mov     [rbx], rax
0x1800036ed  mov     [rbx+40h], rdi
0x1800036f1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800036f6  lea     rdi, [rbx+38h]
0x1800036fa  mov     ebp, eax
0x1800036fc  test    eax, eax
0x1800036fe  js      short loc_18000371D
0x180003700  mov     byte ptr [rdi], 1
0x180003703  mov     r8, rsi
0x180003706  mov     rax, [rbx]
0x180003709  mov     rdx, r15
0x18000370c  mov     rcx, rbx
0x18000370f  mov     rax, [rax]
0x180003712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003717  mov     ebp, eax
0x180003719  test    eax, eax
0x18000371b  jz      short loc_180003753
0x18000371d  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003724  mov     dword ptr [rbx+8], 0C0000001h
0x18000372b  mov     [rbx], rax
0x18000372e  cmp     byte ptr [rdi], 0
0x180003731  jz      short loc_180003746
0x180003733  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003737  mov     byte ptr [rdi], 0
0x18000373a  call    cs:__imp_DeleteCriticalSection
0x180003741  nop     dword ptr [rax+rax+00h]
0x180003746  mov     edx, 48h ; 'H'
0x18000374b  mov     rcx, rbx; Block
0x18000374e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003753  mov     eax, ebp
0x180003755  mov     rbx, [rsp+38h+arg_0]
0x18000375a  mov     rbp, [rsp+38h+arg_8]
0x18000375f  mov     rsi, [rsp+38h+arg_10]
0x180003764  add     rsp, 20h
0x180003768  pop     r15
0x18000376a  pop     r14
0x18000376c  pop     rdi
0x18000376d  retn
```
