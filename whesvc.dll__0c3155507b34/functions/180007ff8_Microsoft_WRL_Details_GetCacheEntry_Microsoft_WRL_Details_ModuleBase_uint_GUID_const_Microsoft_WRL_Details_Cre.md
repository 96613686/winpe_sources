# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180007ff8`
- end: `0x18000817c`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006ae0`

## callees

- `0x180007ff8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000808c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800080a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000808c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800080a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008130`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000804a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000804a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008101`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008101`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000805c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008110`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000805c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008110`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = a5;
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
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              v8);
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
    *(_QWORD *)v8 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007ff8  mov     rax, rsp
0x180007ffb  mov     [rax+8], rbx
0x180007fff  mov     [rax+10h], rbp
0x180008003  mov     [rax+18h], r8
0x180008007  push    rsi
0x180008008  push    rdi
0x180008009  push    r14
0x18000800b  sub     rsp, 30h
0x18000800f  mov     rdi, r9
0x180008012  mov     rbp, rdx
0x180008015  mov     rsi, rcx
0x180008018  mov     r14, [rsp+48h+arg_20]
0x18000801d  mov     qword ptr [r14], 0
0x180008024  mov     qword ptr [rax+18h], 0
0x18000802c  mov     rax, [r9+18h]
0x180008030  mov     r8, [rax]
0x180008033  test    r8, r8
0x180008036  jz      short loc_1800080A7
0x180008038  mov     rax, [rcx]
0x18000803b  mov     rax, [rax+38h]
0x18000803f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008044  mov     rbx, rax
0x180008047  mov     rcx, rax; SRWLock
0x18000804a  call    cs:__imp_AcquireSRWLockShared
0x180008050  mov     rcx, [rdi+18h]
0x180008054  mov     rcx, [rcx]; Ptr
0x180008057  test    rcx, rcx
0x18000805a  jz      short loc_180008099
0x18000805c  call    cs:__imp_DecodePointer
0x180008062  mov     r9, rax
0x180008065  mov     [rsp+48h+Ptr], rax
0x18000806a  mov     rcx, [rax]
0x18000806d  mov     rax, [rcx]
0x180008070  mov     r8, r14
0x180008073  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000807a  mov     rcx, r9
0x18000807d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008082  mov     edi, eax
0x180008084  test    rbx, rbx
0x180008087  jz      short loc_180008092
0x180008089  mov     rcx, rbx; SRWLock
0x18000808c  call    cs:__imp_ReleaseSRWLockShared
0x180008092  mov     eax, edi
0x180008094  jmp     loc_180008169
0x180008099  test    rbx, rbx
0x18000809c  jz      short loc_1800080A7
0x18000809e  mov     rcx, rbx; SRWLock
0x1800080a1  call    cs:__imp_ReleaseSRWLockShared
0x1800080a7  lea     r9, [rsp+48h+Ptr]
0x1800080ac  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x1800080b3  mov     rdx, rdi
0x1800080b6  mov     rcx, rbp
0x1800080b9  mov     rax, [rdi]
0x1800080bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c1  test    eax, eax
0x1800080c3  js      loc_180008169
0x1800080c9  test    byte ptr [rbp+0], 4
0x1800080cd  jnz     loc_18000815F
0x1800080d3  mov     rax, [rsi]
0x1800080d6  mov     rcx, rsi
0x1800080d9  mov     rax, [rax+38h]
0x1800080dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e2  mov     rsi, rax
0x1800080e5  mov     rcx, rax; SRWLock
0x1800080e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800080ee  mov     rcx, [rdi+18h]
0x1800080f2  mov     rcx, [rcx]; Ptr
0x1800080f5  test    rcx, rcx
0x1800080f8  jnz     short loc_180008110
0x1800080fa  xor     ebx, ebx
0x1800080fc  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180008101  call    cs:__imp_EncodePointer
0x180008107  mov     rcx, [rdi+18h]
0x18000810b  mov     [rcx], rax
0x18000810e  jmp     short loc_180008128
0x180008110  call    cs:__imp_DecodePointer
0x180008116  mov     rbx, rax
0x180008119  mov     rcx, [rax]
0x18000811c  mov     rax, [rcx+8]
0x180008120  mov     rcx, rbx
0x180008123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008128  test    rsi, rsi
0x18000812b  jz      short loc_180008136
0x18000812d  mov     rcx, rsi; SRWLock
0x180008130  call    cs:__imp_ReleaseSRWLockExclusive
0x180008136  test    rbx, rbx
0x180008139  jz      short loc_18000815F
0x18000813b  mov     rcx, [rsp+48h+Ptr]
0x180008140  mov     rax, [rcx]
0x180008143  mov     rax, [rax+10h]
0x180008147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814c  mov     rcx, [rsp+48h+Ptr]
0x180008151  mov     rax, [rcx]
0x180008154  mov     rax, [rax+10h]
0x180008158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000815d  jmp     short loc_180008164
0x18000815f  mov     rbx, [rsp+48h+Ptr]
0x180008164  mov     [r14], rbx
0x180008167  xor     eax, eax
0x180008169  mov     rbx, [rsp+48h+arg_0]
0x18000816e  mov     rbp, [rsp+48h+arg_8]
0x180008173  add     rsp, 30h
0x180008177  pop     r14
0x180008179  pop     rdi
0x18000817a  pop     rsi
0x18000817b  retn
```
