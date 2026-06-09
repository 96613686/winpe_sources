# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800081c0`
- end: `0x18000829a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d4`
- `0x1800012f8`
- `0x1800081c0`
- `0x18000857c`
- `0x180016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000827d`
- `KERNEL32!DeleteCriticalSection` at `0x18000827d`

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
0x1800081c0  push    rbx
0x1800081c2  push    rbp
0x1800081c3  push    rsi
0x1800081c4  push    rdi
0x1800081c5  push    r14
0x1800081c7  push    r15
0x1800081c9  sub     rsp, 28h
0x1800081cd  mov     r14, r8
0x1800081d0  mov     r15, rdx
0x1800081d3  mov     rdi, rcx
0x1800081d6  test    r8, r8
0x1800081d9  jnz     short loc_1800081E5
0x1800081db  mov     eax, 80004003h
0x1800081e0  jmp     loc_18000828D
0x1800081e5  mov     ecx, 48h ; 'H'; Size
0x1800081ea  mov     qword ptr [r8], 0
0x1800081f1  mov     esi, 8007000Eh
0x1800081f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800081fb  mov     rbx, rax
0x1800081fe  test    rax, rax
0x180008201  jz      loc_18000828B
0x180008207  mov     dword ptr [rax+8], 0
0x18000820e  lea     rcx, [rbx+10h]; this
0x180008212  xor     eax, eax
0x180008214  xorps   xmm0, xmm0
0x180008217  movups  xmmword ptr [rbx+10h], xmm0
0x18000821b  movups  xmmword ptr [rbx+20h], xmm0
0x18000821f  mov     [rbx+30h], rax
0x180008223  mov     [rbx+38h], al
0x180008226  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000822d  mov     [rbx], rax
0x180008230  mov     [rbx+40h], rdi
0x180008234  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008239  lea     rdi, [rbx+38h]
0x18000823d  mov     esi, eax
0x18000823f  test    eax, eax
0x180008241  js      short loc_180008260
0x180008243  mov     byte ptr [rdi], 1
0x180008246  mov     r8, r14
0x180008249  mov     rax, [rbx]
0x18000824c  mov     rdx, r15
0x18000824f  mov     rcx, rbx
0x180008252  mov     rax, [rax]
0x180008255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825a  mov     esi, eax
0x18000825c  test    eax, eax
0x18000825e  jz      short loc_18000828B
0x180008260  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180008267  mov     dword ptr [rbx+8], 0C0000001h
0x18000826e  mov     [rbx], rax
0x180008271  cmp     byte ptr [rdi], 0
0x180008274  jz      short loc_180008283
0x180008276  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000827a  mov     byte ptr [rdi], 0
0x18000827d  call    cs:__imp_DeleteCriticalSection
0x180008283  mov     rcx, rbx; Block
0x180008286  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000828b  mov     eax, esi
0x18000828d  add     rsp, 28h
0x180008291  pop     r15
0x180008293  pop     r14
0x180008295  pop     rdi
0x180008296  pop     rsi
0x180008297  pop     rbp
0x180008298  pop     rbx
0x180008299  retn
```
