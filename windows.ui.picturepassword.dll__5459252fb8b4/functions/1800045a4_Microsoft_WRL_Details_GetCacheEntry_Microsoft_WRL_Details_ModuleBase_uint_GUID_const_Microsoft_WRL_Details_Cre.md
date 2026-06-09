# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800045a4`
- end: `0x180004733`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004400`

## callees

- `0x1800045a4`
- `0x1800047a8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004606`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800046bf`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004606`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800046bf`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800046b0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800046b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800045f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800045f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004635`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000464a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004635`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000464a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046e4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v5; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  __int64 v14; // rax
  void *v15; // rcx
  PVOID v16; // rbx
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

  v5 = Ptr;
  Ptr = 0;
  *v5 = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v5);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      return v12;
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, _QWORD **))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v14 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v14);
    v15 = **(void ***)a4[1].Data4;
    if ( v15 )
    {
      v16 = DecodePointer(v15);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
    }
    else
    {
      v16 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( !v16 )
    {
LABEL_17:
      v16 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    *v5 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800045a4  mov     rax, rsp
0x1800045a7  push    rbx
0x1800045a8  push    rbp
0x1800045a9  push    rsi
0x1800045aa  push    rdi
0x1800045ab  push    r14
0x1800045ad  push    r15
0x1800045af  sub     rsp, 38h
0x1800045b3  mov     r14, [rsp+68h+Ptr]
0x1800045bb  mov     rdi, r9
0x1800045be  mov     qword ptr [rax+28h], 0
0x1800045c6  mov     r15, r8
0x1800045c9  mov     rbp, rdx
0x1800045cc  mov     rsi, rcx
0x1800045cf  mov     qword ptr [r14], 0
0x1800045d6  mov     rax, [r9+18h]
0x1800045da  mov     r10, [rax]
0x1800045dd  test    r10, r10
0x1800045e0  jz      short loc_180004650
0x1800045e2  mov     rax, [rcx]
0x1800045e5  mov     rax, [rax+38h]
0x1800045e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ee  mov     rcx, rax; SRWLock
0x1800045f1  mov     rbx, rax
0x1800045f4  call    cs:__imp_AcquireSRWLockShared
0x1800045fa  mov     rcx, [rdi+18h]
0x1800045fe  mov     rcx, [rcx]; Ptr
0x180004601  test    rcx, rcx
0x180004604  jz      short loc_180004642
0x180004606  call    cs:__imp_DecodePointer
0x18000460c  mov     [rsp+68h+Ptr], rax
0x180004614  mov     r8, r14
0x180004617  mov     r9, rax
0x18000461a  mov     rdx, r15
0x18000461d  mov     rcx, [rax]
0x180004620  mov     rax, [rcx]
0x180004623  mov     rcx, r9
0x180004626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000462b  mov     edi, eax
0x18000462d  test    rbx, rbx
0x180004630  jz      short loc_18000463B
0x180004632  mov     rcx, rbx; SRWLock
0x180004635  call    cs:__imp_ReleaseSRWLockShared
0x18000463b  mov     eax, edi
0x18000463d  jmp     loc_180004726
0x180004642  test    rbx, rbx
0x180004645  jz      short loc_180004650
0x180004647  mov     rcx, rbx; SRWLock
0x18000464a  call    cs:__imp_ReleaseSRWLockShared
0x180004650  mov     rax, [rdi]
0x180004653  lea     r9, [rsp+68h+Ptr]
0x18000465b  mov     r8, r15
0x18000465e  mov     rdx, rdi
0x180004661  mov     rcx, rbp
0x180004664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004669  test    eax, eax
0x18000466b  js      loc_180004726
0x180004671  test    byte ptr [rbp+0], 4
0x180004675  jnz     loc_180004719
0x18000467b  mov     rax, [rsi]
0x18000467e  mov     rcx, rsi
0x180004681  mov     rax, [rax+38h]
0x180004685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468a  mov     rdx, rax
0x18000468d  lea     rcx, [rsp+68h+SRWLock]
0x180004695  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000469a  mov     rax, [rdi+18h]
0x18000469e  mov     rcx, [rax]; Ptr
0x1800046a1  test    rcx, rcx
0x1800046a4  jnz     short loc_1800046BF
0x1800046a6  mov     rcx, [rsp+68h+Ptr]; Ptr
0x1800046ae  xor     ebx, ebx
0x1800046b0  call    cs:__imp_EncodePointer
0x1800046b6  mov     rcx, [rdi+18h]
0x1800046ba  mov     [rcx], rax
0x1800046bd  jmp     short loc_1800046D7
0x1800046bf  call    cs:__imp_DecodePointer
0x1800046c5  mov     rbx, rax
0x1800046c8  mov     rcx, [rax]
0x1800046cb  mov     rax, [rcx+8]
0x1800046cf  mov     rcx, rbx
0x1800046d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d7  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x1800046df  test    rcx, rcx
0x1800046e2  jz      short loc_1800046EA
0x1800046e4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800046ea  test    rbx, rbx
0x1800046ed  jz      short loc_180004719
0x1800046ef  mov     rcx, [rsp+68h+Ptr]
0x1800046f7  mov     rax, [rcx]
0x1800046fa  mov     rax, [rax+10h]
0x1800046fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004703  mov     rcx, [rsp+68h+Ptr]
0x18000470b  mov     rax, [rcx]
0x18000470e  mov     rax, [rax+10h]
0x180004712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004717  jmp     short loc_180004721
0x180004719  mov     rbx, [rsp+68h+Ptr]
0x180004721  mov     [r14], rbx
0x180004724  xor     eax, eax
0x180004726  add     rsp, 38h
0x18000472a  pop     r15
0x18000472c  pop     r14
0x18000472e  pop     rdi
0x18000472f  pop     rsi
0x180004730  pop     rbp
0x180004731  pop     rbx
0x180004732  retn
```
