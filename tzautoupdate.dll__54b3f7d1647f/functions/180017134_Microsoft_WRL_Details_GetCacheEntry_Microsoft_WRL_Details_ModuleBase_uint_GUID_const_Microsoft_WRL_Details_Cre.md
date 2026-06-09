# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180017134`
- end: `0x1800172c3`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016e20`
- `0x180016f98`

## callees

- `0x180011b30`
- `0x180017134`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017274`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017274`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017184`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017184`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800171c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800171da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800171c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800171da`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180017240`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180017240`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180017196`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001724f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180017196`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001724f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v9; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  void *v14; // rcx
  PVOID v15; // rbx
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

  v9 = Ptr;
  *Ptr = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v9);
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
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock);
    v14 = **(void ***)a4[1].Data4;
    if ( v14 )
    {
      v15 = DecodePointer(v14);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 8LL))(v15);
    }
    else
    {
      v15 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( !v15 )
    {
LABEL_17:
      v15 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    *v9 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017134  mov     rax, rsp
0x180017137  push    rbx
0x180017138  push    rbp
0x180017139  push    rsi
0x18001713a  push    rdi
0x18001713b  push    r14
0x18001713d  push    r15
0x18001713f  sub     rsp, 38h
0x180017143  mov     rdi, r9
0x180017146  mov     r15, r8
0x180017149  mov     rbp, rdx
0x18001714c  mov     rsi, rcx
0x18001714f  mov     r14, [rsp+68h+Ptr]
0x180017157  mov     qword ptr [r14], 0
0x18001715e  mov     qword ptr [rax+28h], 0
0x180017166  mov     rax, [r9+18h]
0x18001716a  mov     r10, [rax]
0x18001716d  test    r10, r10
0x180017170  jz      short loc_1800171E0
0x180017172  mov     rax, [rcx]
0x180017175  mov     rax, [rax+38h]
0x180017179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001717e  mov     rbx, rax
0x180017181  mov     rcx, rax; SRWLock
0x180017184  call    cs:__imp_AcquireSRWLockShared
0x18001718a  mov     rcx, [rdi+18h]
0x18001718e  mov     rcx, [rcx]; Ptr
0x180017191  test    rcx, rcx
0x180017194  jz      short loc_1800171D2
0x180017196  call    cs:__imp_DecodePointer
0x18001719c  mov     r9, rax
0x18001719f  mov     [rsp+68h+Ptr], rax
0x1800171a7  mov     rcx, [rax]
0x1800171aa  mov     rax, [rcx]
0x1800171ad  mov     r8, r14
0x1800171b0  mov     rdx, r15
0x1800171b3  mov     rcx, r9
0x1800171b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171bb  mov     edi, eax
0x1800171bd  test    rbx, rbx
0x1800171c0  jz      short loc_1800171CB
0x1800171c2  mov     rcx, rbx; SRWLock
0x1800171c5  call    cs:__imp_ReleaseSRWLockShared
0x1800171cb  mov     eax, edi
0x1800171cd  jmp     loc_1800172B6
0x1800171d2  test    rbx, rbx
0x1800171d5  jz      short loc_1800171E0
0x1800171d7  mov     rcx, rbx; SRWLock
0x1800171da  call    cs:__imp_ReleaseSRWLockShared
0x1800171e0  lea     r9, [rsp+68h+Ptr]
0x1800171e8  mov     r8, r15
0x1800171eb  mov     rdx, rdi
0x1800171ee  mov     rcx, rbp
0x1800171f1  mov     rax, [rdi]
0x1800171f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f9  test    eax, eax
0x1800171fb  js      loc_1800172B6
0x180017201  test    byte ptr [rbp+0], 4
0x180017205  jnz     loc_1800172A9
0x18001720b  mov     rax, [rsi]
0x18001720e  mov     rcx, rsi
0x180017211  mov     rax, [rax+38h]
0x180017215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001721a  mov     rdx, rax
0x18001721d  lea     rcx, [rsp+68h+SRWLock]
0x180017225  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001722a  mov     rax, [rdi+18h]
0x18001722e  mov     rcx, [rax]; Ptr
0x180017231  test    rcx, rcx
0x180017234  jnz     short loc_18001724F
0x180017236  xor     ebx, ebx
0x180017238  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180017240  call    cs:__imp_EncodePointer
0x180017246  mov     rcx, [rdi+18h]
0x18001724a  mov     [rcx], rax
0x18001724d  jmp     short loc_180017267
0x18001724f  call    cs:__imp_DecodePointer
0x180017255  mov     rbx, rax
0x180017258  mov     rcx, [rax]
0x18001725b  mov     rax, [rcx+8]
0x18001725f  mov     rcx, rbx
0x180017262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017267  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18001726f  test    rcx, rcx
0x180017272  jz      short loc_18001727A
0x180017274  call    cs:__imp_ReleaseSRWLockExclusive
0x18001727a  test    rbx, rbx
0x18001727d  jz      short loc_1800172A9
0x18001727f  mov     rcx, [rsp+68h+Ptr]
0x180017287  mov     rax, [rcx]
0x18001728a  mov     rax, [rax+10h]
0x18001728e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017293  mov     rcx, [rsp+68h+Ptr]
0x18001729b  mov     rax, [rcx]
0x18001729e  mov     rax, [rax+10h]
0x1800172a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a7  jmp     short loc_1800172B1
0x1800172a9  mov     rbx, [rsp+68h+Ptr]
0x1800172b1  mov     [r14], rbx
0x1800172b4  xor     eax, eax
0x1800172b6  add     rsp, 38h
0x1800172ba  pop     r15
0x1800172bc  pop     r14
0x1800172be  pop     rdi
0x1800172bf  pop     rsi
0x1800172c0  pop     rbp
0x1800172c1  pop     rbx
0x1800172c2  retn
```
