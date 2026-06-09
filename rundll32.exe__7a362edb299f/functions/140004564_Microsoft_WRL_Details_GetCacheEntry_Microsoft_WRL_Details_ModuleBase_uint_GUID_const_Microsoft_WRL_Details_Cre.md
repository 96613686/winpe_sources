# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x140004564`
- end: `0x1400046e8`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400028d0`

## callees

- `0x140004564`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000469c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000469c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400045b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400045b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004654`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004654`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400045f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000460d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400045f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000460d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1400045c8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000467c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1400045c8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000467c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000466d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000466d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v5; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v5 = a5;
  Ptr = 0;
  *(_QWORD *)a5 = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              v5);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, GUID *, PVOID *))&a4->Data1)(
             a2,
             a4,
             &GUID_00000035_0000_0000_c000_000000000046,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v13);
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
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    if ( !v15 )
    {
LABEL_17:
      v15 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    *(_QWORD *)v5 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004564  mov     rax, rsp
0x140004567  mov     [rax+8], rbx
0x14000456b  mov     [rax+10h], rbp
0x14000456f  mov     [rax+18h], r8
0x140004573  push    rsi
0x140004574  push    rdi
0x140004575  push    r14
0x140004577  sub     rsp, 30h
0x14000457b  mov     r14, [rsp+48h+arg_20]
0x140004580  mov     rdi, r9
0x140004583  mov     qword ptr [rax+18h], 0
0x14000458b  mov     rbp, rdx
0x14000458e  mov     rsi, rcx
0x140004591  mov     qword ptr [r14], 0
0x140004598  mov     rax, [r9+18h]
0x14000459c  mov     r8, [rax]
0x14000459f  test    r8, r8
0x1400045a2  jz      short loc_140004613
0x1400045a4  mov     rax, [rcx]
0x1400045a7  mov     rax, [rax+38h]
0x1400045ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045b0  mov     rcx, rax; SRWLock
0x1400045b3  mov     rbx, rax
0x1400045b6  call    cs:__imp_AcquireSRWLockShared
0x1400045bc  mov     rcx, [rdi+18h]
0x1400045c0  mov     rcx, [rcx]; Ptr
0x1400045c3  test    rcx, rcx
0x1400045c6  jz      short loc_140004605
0x1400045c8  call    cs:__imp_DecodePointer
0x1400045ce  mov     [rsp+48h+Ptr], rax
0x1400045d3  mov     r8, r14
0x1400045d6  mov     r9, rax
0x1400045d9  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1400045e0  mov     rcx, [rax]
0x1400045e3  mov     rax, [rcx]
0x1400045e6  mov     rcx, r9
0x1400045e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045ee  mov     edi, eax
0x1400045f0  test    rbx, rbx
0x1400045f3  jz      short loc_1400045FE
0x1400045f5  mov     rcx, rbx; SRWLock
0x1400045f8  call    cs:__imp_ReleaseSRWLockShared
0x1400045fe  mov     eax, edi
0x140004600  jmp     loc_1400046D5
0x140004605  test    rbx, rbx
0x140004608  jz      short loc_140004613
0x14000460a  mov     rcx, rbx; SRWLock
0x14000460d  call    cs:__imp_ReleaseSRWLockShared
0x140004613  mov     rax, [rdi]
0x140004616  lea     r9, [rsp+48h+Ptr]
0x14000461b  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x140004622  mov     rdx, rdi
0x140004625  mov     rcx, rbp
0x140004628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000462d  test    eax, eax
0x14000462f  js      loc_1400046D5
0x140004635  test    byte ptr [rbp+0], 4
0x140004639  jnz     loc_1400046CB
0x14000463f  mov     rax, [rsi]
0x140004642  mov     rcx, rsi
0x140004645  mov     rax, [rax+38h]
0x140004649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000464e  mov     rcx, rax; SRWLock
0x140004651  mov     rsi, rax
0x140004654  call    cs:__imp_AcquireSRWLockExclusive
0x14000465a  mov     rcx, [rdi+18h]
0x14000465e  mov     rcx, [rcx]; Ptr
0x140004661  test    rcx, rcx
0x140004664  jnz     short loc_14000467C
0x140004666  mov     rcx, [rsp+48h+Ptr]; Ptr
0x14000466b  xor     ebx, ebx
0x14000466d  call    cs:__imp_EncodePointer
0x140004673  mov     rcx, [rdi+18h]
0x140004677  mov     [rcx], rax
0x14000467a  jmp     short loc_140004694
0x14000467c  call    cs:__imp_DecodePointer
0x140004682  mov     rbx, rax
0x140004685  mov     rcx, [rax]
0x140004688  mov     rax, [rcx+8]
0x14000468c  mov     rcx, rbx
0x14000468f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004694  test    rsi, rsi
0x140004697  jz      short loc_1400046A2
0x140004699  mov     rcx, rsi; SRWLock
0x14000469c  call    cs:__imp_ReleaseSRWLockExclusive
0x1400046a2  test    rbx, rbx
0x1400046a5  jz      short loc_1400046CB
0x1400046a7  mov     rcx, [rsp+48h+Ptr]
0x1400046ac  mov     rax, [rcx]
0x1400046af  mov     rax, [rax+10h]
0x1400046b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046b8  mov     rcx, [rsp+48h+Ptr]
0x1400046bd  mov     rax, [rcx]
0x1400046c0  mov     rax, [rax+10h]
0x1400046c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046c9  jmp     short loc_1400046D0
0x1400046cb  mov     rbx, [rsp+48h+Ptr]
0x1400046d0  mov     [r14], rbx
0x1400046d3  xor     eax, eax
0x1400046d5  mov     rbx, [rsp+48h+arg_0]
0x1400046da  mov     rbp, [rsp+48h+arg_8]
0x1400046df  add     rsp, 30h
0x1400046e3  pop     r14
0x1400046e5  pop     rdi
0x1400046e6  pop     rsi
0x1400046e7  retn
```
