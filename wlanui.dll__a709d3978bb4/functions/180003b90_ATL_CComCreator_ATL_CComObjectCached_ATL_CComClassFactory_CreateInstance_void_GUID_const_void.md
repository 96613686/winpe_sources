# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003b90`
- end: `0x180003c6b`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011d0`
- `0x180003b90`
- `0x180003e5c`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003c56`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c56`
- `KERNEL32!DeleteCriticalSection` at `0x180003c4d`
- `KERNEL32!DeleteCriticalSection` at `0x180003c4d`

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
0x180003b90  push    rbx
0x180003b92  push    rbp
0x180003b93  push    rsi
0x180003b94  push    rdi
0x180003b95  push    r14
0x180003b97  push    r15
0x180003b99  sub     rsp, 28h
0x180003b9d  mov     r14, r8
0x180003ba0  mov     r15, rdx
0x180003ba3  mov     rdi, rcx
0x180003ba6  test    r8, r8
0x180003ba9  jnz     short loc_180003BB5
0x180003bab  mov     eax, 80004003h
0x180003bb0  jmp     loc_180003C5E
0x180003bb5  mov     ecx, 48h ; 'H'; Size
0x180003bba  mov     qword ptr [r8], 0
0x180003bc1  mov     esi, 8007000Eh
0x180003bc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003bcb  mov     rbx, rax
0x180003bce  test    rax, rax
0x180003bd1  jz      loc_180003C5C
0x180003bd7  mov     dword ptr [rax+8], 0
0x180003bde  lea     rcx, [rbx+10h]; this
0x180003be2  xor     eax, eax
0x180003be4  xorps   xmm0, xmm0
0x180003be7  movups  xmmword ptr [rbx+10h], xmm0
0x180003beb  movups  xmmword ptr [rbx+20h], xmm0
0x180003bef  mov     [rbx+30h], rax
0x180003bf3  mov     [rbx+38h], al
0x180003bf6  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180003bfd  mov     [rbx], rax
0x180003c00  mov     [rbx+40h], rdi
0x180003c04  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003c09  lea     rdi, [rbx+38h]
0x180003c0d  mov     esi, eax
0x180003c0f  test    eax, eax
0x180003c11  js      short loc_180003C30
0x180003c13  mov     byte ptr [rdi], 1
0x180003c16  mov     r8, r14
0x180003c19  mov     rax, [rbx]
0x180003c1c  mov     rdx, r15
0x180003c1f  mov     rcx, rbx
0x180003c22  mov     rax, [rax]
0x180003c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2a  mov     esi, eax
0x180003c2c  test    eax, eax
0x180003c2e  jz      short loc_180003C5C
0x180003c30  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003c37  mov     dword ptr [rbx+8], 0C0000001h
0x180003c3e  mov     [rbx], rax
0x180003c41  cmp     byte ptr [rdi], 0
0x180003c44  jz      short loc_180003C53
0x180003c46  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003c4a  mov     byte ptr [rdi], 0
0x180003c4d  call    cs:__imp_DeleteCriticalSection
0x180003c53  mov     rcx, rbx
0x180003c56  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003c5c  mov     eax, esi
0x180003c5e  add     rsp, 28h
0x180003c62  pop     r15
0x180003c64  pop     r14
0x180003c66  pop     rdi
0x180003c67  pop     rsi
0x180003c68  pop     rbp
0x180003c69  pop     rbx
0x180003c6a  retn
```
