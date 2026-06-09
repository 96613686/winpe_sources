# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140003de0`
- end: `0x140003ebf`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001b50`
- `0x140001b90`
- `0x140003de0`
- `0x140004cd0`
- `0x140016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140003e9d`
- `KERNEL32!DeleteCriticalSection` at `0x140003e9d`

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
0x140003de0  push    rbx
0x140003de2  push    rbp
0x140003de3  push    rsi
0x140003de4  push    rdi
0x140003de5  push    r14
0x140003de7  push    r15
0x140003de9  sub     rsp, 28h
0x140003ded  mov     r14, r8
0x140003df0  mov     r15, rdx
0x140003df3  mov     rdi, rcx
0x140003df6  test    r8, r8
0x140003df9  jnz     short loc_140003E05
0x140003dfb  mov     eax, 80004003h
0x140003e00  jmp     loc_140003EB2
0x140003e05  mov     ecx, 48h ; 'H'; Size
0x140003e0a  mov     qword ptr [r8], 0
0x140003e11  mov     esi, 8007000Eh
0x140003e16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003e1b  mov     rbx, rax
0x140003e1e  test    rax, rax
0x140003e21  jz      loc_140003EB0
0x140003e27  mov     dword ptr [rax+8], 0
0x140003e2e  lea     rcx, [rbx+10h]; this
0x140003e32  xor     eax, eax
0x140003e34  xorps   xmm0, xmm0
0x140003e37  movups  xmmword ptr [rbx+10h], xmm0
0x140003e3b  movups  xmmword ptr [rbx+20h], xmm0
0x140003e3f  mov     [rbx+30h], rax
0x140003e43  mov     [rbx+38h], al
0x140003e46  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x140003e4d  mov     [rbx], rax
0x140003e50  mov     [rbx+40h], rdi
0x140003e54  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140003e59  lea     rdi, [rbx+38h]
0x140003e5d  mov     esi, eax
0x140003e5f  test    eax, eax
0x140003e61  js      short loc_140003E80
0x140003e63  mov     byte ptr [rdi], 1
0x140003e66  mov     r8, r14
0x140003e69  mov     rax, [rbx]
0x140003e6c  mov     rdx, r15
0x140003e6f  mov     rcx, rbx
0x140003e72  mov     rax, [rax]
0x140003e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e7a  mov     esi, eax
0x140003e7c  test    eax, eax
0x140003e7e  jz      short loc_140003EB0
0x140003e80  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140003e87  mov     dword ptr [rbx+8], 0C0000001h
0x140003e8e  mov     [rbx], rax
0x140003e91  cmp     byte ptr [rdi], 0
0x140003e94  jz      short loc_140003EA3
0x140003e96  lea     rcx, [rbx+10h]; lpCriticalSection
0x140003e9a  mov     byte ptr [rdi], 0
0x140003e9d  call    cs:__imp_DeleteCriticalSection
0x140003ea3  mov     edx, 48h ; 'H'
0x140003ea8  mov     rcx, rbx; Block
0x140003eab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003eb0  mov     eax, esi
0x140003eb2  add     rsp, 28h
0x140003eb6  pop     r15
0x140003eb8  pop     r14
0x140003eba  pop     rdi
0x140003ebb  pop     rsi
0x140003ebc  pop     rbp
0x140003ebd  pop     rbx
0x140003ebe  retn
```
