# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdrRestoreService>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a6a0`
- end: `0x18000a7a0`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@V?$CComClassFactorySingleton@VCSdrRestoreService@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001554`
- `0x180001578`
- `0x18000a6a0`
- `0x18000ac0c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a783`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a783`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdrRestoreService>>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdrRestoreService>>::`vftable';
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactorySingleton<CSdrRestoreService>::`vftable';
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
0x18000a6a0  push    rbx
0x18000a6a2  push    rbp
0x18000a6a3  push    rsi
0x18000a6a4  push    rdi
0x18000a6a5  push    r14
0x18000a6a7  push    r15
0x18000a6a9  sub     rsp, 28h
0x18000a6ad  mov     r14, r8
0x18000a6b0  mov     r15, rdx
0x18000a6b3  mov     rdi, rcx
0x18000a6b6  test    r8, r8
0x18000a6b9  jnz     short loc_18000A6C5
0x18000a6bb  mov     eax, 80004003h
0x18000a6c0  jmp     loc_18000A793
0x18000a6c5  mov     ecx, 58h ; 'X'; Size
0x18000a6ca  mov     qword ptr [r8], 0
0x18000a6d1  mov     esi, 8007000Eh
0x18000a6d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6db  mov     rbx, rax
0x18000a6de  test    rax, rax
0x18000a6e1  jz      loc_18000A791
0x18000a6e7  mov     dword ptr [rax+8], 0
0x18000a6ee  lea     rcx, [rbx+10h]; this
0x18000a6f2  xor     eax, eax
0x18000a6f4  xorps   xmm0, xmm0
0x18000a6f7  movups  xmmword ptr [rbx+10h], xmm0
0x18000a6fb  movups  xmmword ptr [rbx+20h], xmm0
0x18000a6ff  mov     [rbx+30h], rax
0x18000a703  mov     [rbx+38h], al
0x18000a706  mov     [rbx+48h], eax
0x18000a709  mov     [rbx+50h], rax
0x18000a70d  lea     rax, ??_7?$CComObjectNoLock@V?$CComClassFactorySingleton@VCSdrRestoreService@@@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdrRestoreService>>::`vftable'
0x18000a714  mov     [rbx], rax
0x18000a717  mov     [rbx+40h], rdi
0x18000a71b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000a720  lea     rdi, [rbx+38h]
0x18000a724  mov     esi, eax
0x18000a726  test    eax, eax
0x18000a728  js      short loc_18000A747
0x18000a72a  mov     byte ptr [rdi], 1
0x18000a72d  mov     r8, r14
0x18000a730  mov     rax, [rbx]
0x18000a733  mov     rdx, r15
0x18000a736  mov     rcx, rbx
0x18000a739  mov     rax, [rax]
0x18000a73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a741  mov     esi, eax
0x18000a743  test    eax, eax
0x18000a745  jz      short loc_18000A791
0x18000a747  lea     rax, ??_7?$CComClassFactorySingleton@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComClassFactorySingleton<CSdrRestoreService>::`vftable'
0x18000a74e  mov     dword ptr [rbx+8], 0C0000001h
0x18000a755  mov     [rbx], rax
0x18000a758  mov     rcx, [rbx+50h]
0x18000a75c  test    rcx, rcx
0x18000a75f  jz      short loc_18000A76D
0x18000a761  mov     rax, [rcx]
0x18000a764  mov     rax, [rax+10h]
0x18000a768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a76d  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000a774  mov     [rbx], rax
0x18000a777  cmp     byte ptr [rdi], 0
0x18000a77a  jz      short loc_18000A789
0x18000a77c  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a780  mov     byte ptr [rdi], 0
0x18000a783  call    cs:__imp_DeleteCriticalSection
0x18000a789  mov     rcx, rbx; Block
0x18000a78c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a791  mov     eax, esi
0x18000a793  add     rsp, 28h
0x18000a797  pop     r15
0x18000a799  pop     r14
0x18000a79b  pop     rdi
0x18000a79c  pop     rsi
0x18000a79d  pop     rbp
0x18000a79e  pop     rbx
0x18000a79f  retn
```
