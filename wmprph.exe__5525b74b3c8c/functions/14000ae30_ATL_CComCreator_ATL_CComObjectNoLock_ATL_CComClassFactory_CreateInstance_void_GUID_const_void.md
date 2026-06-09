# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x14000ae30`
- end: `0x14000aed7`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x140001014`
- `0x14000ae30`
- `0x14000f010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000ae7b`
- `KERNEL32!InitializeCriticalSection` at `0x14000ae7b`
- `KERNEL32!DeleteCriticalSection` at `0x14000aeb5`
- `KERNEL32!DeleteCriticalSection` at `0x14000aeb5`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x40u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
    *(_QWORD *)v9 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
    *((_QWORD *)v9 + 7) = a1;
    v7 = ((__int64 (__fastcall *)(char *, __int64, _QWORD *))ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable')(
           v9,
           a2,
           a3);
    if ( v7 )
    {
      *(_QWORD *)v9 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      operator delete(v9, 0x40u);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000ae30  push    rbx
0x14000ae32  push    rbp
0x14000ae33  push    rsi
0x14000ae34  push    rdi
0x14000ae35  push    r12
0x14000ae37  push    r14
0x14000ae39  sub     rsp, 28h
0x14000ae3d  mov     rdi, r8
0x14000ae40  mov     rbp, rdx
0x14000ae43  mov     r14, rcx
0x14000ae46  test    r8, r8
0x14000ae49  jnz     short loc_14000AE52
0x14000ae4b  mov     eax, 80004003h
0x14000ae50  jmp     short loc_14000AECA
0x14000ae52  mov     ecx, 40h ; '@'; Size
0x14000ae57  mov     qword ptr [r8], 0
0x14000ae5e  mov     esi, 8007000Eh
0x14000ae63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ae68  mov     rbx, rax
0x14000ae6b  test    rax, rax
0x14000ae6e  jz      short loc_14000AEC8
0x14000ae70  lea     rcx, [rax+10h]; lpCriticalSection
0x14000ae74  mov     dword ptr [rax+8], 0
0x14000ae7b  call    cs:__imp_InitializeCriticalSection
0x14000ae81  lea     r12, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x14000ae88  mov     r8, rdi
0x14000ae8b  mov     rax, [r12]
0x14000ae8f  mov     rdx, rbp
0x14000ae92  mov     [rbx], r12
0x14000ae95  mov     rcx, rbx
0x14000ae98  mov     [rbx+38h], r14
0x14000ae9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aea1  mov     esi, eax
0x14000aea3  test    eax, eax
0x14000aea5  jz      short loc_14000AEC8
0x14000aea7  lea     rcx, [rbx+10h]; lpCriticalSection
0x14000aeab  mov     [rbx], r12
0x14000aeae  mov     dword ptr [rbx+8], 1
0x14000aeb5  call    cs:__imp_DeleteCriticalSection
0x14000aebb  mov     edx, 40h ; '@'; unsigned __int64
0x14000aec0  mov     rcx, rbx; void *
0x14000aec3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000aec8  mov     eax, esi
0x14000aeca  add     rsp, 28h
0x14000aece  pop     r14
0x14000aed0  pop     r12
0x14000aed2  pop     rdi
0x14000aed3  pop     rsi
0x14000aed4  pop     rbp
0x14000aed5  pop     rbx
0x14000aed6  retn
```
