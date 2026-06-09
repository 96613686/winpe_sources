# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180006174`
- end: `0x180006312`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005de4`

## callees

- `0x180001dc0`
- `0x180006174`
- `0x180006388`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800062bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800062bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800061d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800061d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006228`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006228`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000628e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000628e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800061e7`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000629d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800061e7`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000629d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  void *v14; // rcx
  PVOID v15; // rbx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-58h] BYREF
  PVOID Ptr; // [rsp+38h] [rbp-50h] BYREF

  *(_QWORD *)a5 = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, unsigned int *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              a3,
              a5);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, PVOID *))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    SRWLock = 0;
    v13 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v13);
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
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    *(_QWORD *)a5 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006174  push    rbx
0x180006176  push    rbp
0x180006177  push    rsi
0x180006178  push    rdi
0x180006179  push    r14
0x18000617b  push    r15
0x18000617d  sub     rsp, 58h
0x180006181  mov     rax, cs:__security_cookie
0x180006188  xor     rax, rsp
0x18000618b  mov     [rsp+88h+var_48], rax
0x180006190  mov     rdi, r9
0x180006193  mov     r15, r8
0x180006196  mov     rbp, rdx
0x180006199  mov     rsi, rcx
0x18000619c  mov     r14, [rsp+88h+arg_20]
0x1800061a4  mov     qword ptr [r14], 0
0x1800061ab  mov     [rsp+88h+Ptr], 0
0x1800061b4  mov     rax, [r9+18h]
0x1800061b8  mov     rcx, [rax]
0x1800061bb  test    rcx, rcx
0x1800061be  jz      short loc_18000622E
0x1800061c0  mov     rax, [rsi]
0x1800061c3  mov     rcx, rsi
0x1800061c6  mov     rax, [rax+38h]
0x1800061ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061cf  mov     rbx, rax
0x1800061d2  mov     rcx, rax; SRWLock
0x1800061d5  call    cs:__imp_AcquireSRWLockShared
0x1800061db  mov     rcx, [rdi+18h]
0x1800061df  mov     rcx, [rcx]; Ptr
0x1800061e2  test    rcx, rcx
0x1800061e5  jz      short loc_180006220
0x1800061e7  call    cs:__imp_DecodePointer
0x1800061ed  mov     r9, rax
0x1800061f0  mov     [rsp+88h+Ptr], rax
0x1800061f5  mov     rcx, [rax]
0x1800061f8  mov     rax, [rcx]
0x1800061fb  mov     r8, r14
0x1800061fe  mov     rdx, r15
0x180006201  mov     rcx, r9
0x180006204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006209  mov     edi, eax
0x18000620b  test    rbx, rbx
0x18000620e  jz      short loc_180006219
0x180006210  mov     rcx, rbx; SRWLock
0x180006213  call    cs:__imp_ReleaseSRWLockShared
0x180006219  mov     eax, edi
0x18000621b  jmp     loc_1800062F8
0x180006220  test    rbx, rbx
0x180006223  jz      short loc_18000622E
0x180006225  mov     rcx, rbx; SRWLock
0x180006228  call    cs:__imp_ReleaseSRWLockShared
0x18000622e  lea     r9, [rsp+88h+Ptr]
0x180006233  mov     r8, r15
0x180006236  mov     rdx, rdi
0x180006239  mov     rcx, rbp
0x18000623c  mov     rax, [rdi]
0x18000623f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006244  test    eax, eax
0x180006246  js      loc_1800062F8
0x18000624c  test    byte ptr [rbp+0], 4
0x180006250  jnz     loc_1800062EE
0x180006256  mov     [rsp+88h+SRWLock], 0
0x18000625f  mov     rax, [rsi]
0x180006262  mov     rcx, rsi
0x180006265  mov     rax, [rax+38h]
0x180006269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000626e  mov     rdx, rax
0x180006271  lea     rcx, [rsp+88h+SRWLock]
0x180006276  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000627b  mov     rax, [rdi+18h]
0x18000627f  mov     rcx, [rax]; Ptr
0x180006282  test    rcx, rcx
0x180006285  jnz     short loc_18000629D
0x180006287  xor     ebx, ebx
0x180006289  mov     rcx, [rsp+88h+Ptr]; Ptr
0x18000628e  call    cs:__imp_EncodePointer
0x180006294  mov     rcx, [rdi+18h]
0x180006298  mov     [rcx], rax
0x18000629b  jmp     short loc_1800062B5
0x18000629d  call    cs:__imp_DecodePointer
0x1800062a3  mov     rbx, rax
0x1800062a6  mov     rcx, [rax]
0x1800062a9  mov     rax, [rcx+8]
0x1800062ad  mov     rcx, rbx
0x1800062b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b5  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x1800062ba  test    rcx, rcx
0x1800062bd  jz      short loc_1800062C5
0x1800062bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800062c5  test    rbx, rbx
0x1800062c8  jz      short loc_1800062EE
0x1800062ca  mov     rcx, [rsp+88h+Ptr]
0x1800062cf  mov     rax, [rcx]
0x1800062d2  mov     rax, [rax+10h]
0x1800062d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062db  mov     rcx, [rsp+88h+Ptr]
0x1800062e0  mov     rax, [rcx]
0x1800062e3  mov     rax, [rax+10h]
0x1800062e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ec  jmp     short loc_1800062F3
0x1800062ee  mov     rbx, [rsp+88h+Ptr]
0x1800062f3  mov     [r14], rbx
0x1800062f6  xor     eax, eax
0x1800062f8  mov     rcx, [rsp+88h+var_48]
0x1800062fd  xor     rcx, rsp; StackCookie
0x180006300  call    __security_check_cookie
0x180006305  add     rsp, 58h
0x180006309  pop     r15
0x18000630b  pop     r14
0x18000630d  pop     rdi
0x18000630e  pop     rsi
0x18000630f  pop     rbp
0x180006310  pop     rbx
0x180006311  retn
```
