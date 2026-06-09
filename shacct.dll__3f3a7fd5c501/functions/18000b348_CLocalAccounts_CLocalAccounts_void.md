# CLocalAccounts::~CLocalAccounts(void)

- ea: `0x18000b348`
- end: `0x18000b3a5`
- name: `??1CLocalAccounts@@MEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CLocalAccounts *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b310`

## callees

- `0x18000b348`
- `0x18000b3b0`
- `0x1800113b0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b392`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b392`

## pseudocode

```c
void __fastcall CLocalAccounts::~CLocalAccounts(CLocalAccounts *this)
{
  bool v1; // zf
  __int64 v3; // rcx

  v1 = *((_DWORD *)this + 11) == 0;
  *(_QWORD *)this = &CLocalAccounts::`vftable';
  if ( !v1 )
    CLocalAccounts::Unadvise(this, *((_DWORD *)this + 24));
  v3 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CLocalAccounts::Reset(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x18000b348  push    rbx
0x18000b34a  sub     rsp, 20h
0x18000b34e  cmp     dword ptr [rcx+2Ch], 0
0x18000b352  lea     rax, ??_7CLocalAccounts@@6B@; const CLocalAccounts::`vftable'
0x18000b359  mov     [rcx], rax
0x18000b35c  mov     rbx, rcx
0x18000b35f  jz      short loc_18000B369
0x18000b361  mov     edx, [rcx+60h]; unsigned int
0x18000b364  call    ?Unadvise@CLocalAccounts@@UEAAJK@Z; CLocalAccounts::Unadvise(ulong)
0x18000b369  mov     rcx, [rbx+58h]
0x18000b36d  mov     qword ptr [rbx+58h], 0
0x18000b375  test    rcx, rcx
0x18000b378  jz      short loc_18000B386
0x18000b37a  mov     rax, [rcx]
0x18000b37d  mov     rax, [rax+10h]
0x18000b381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b386  mov     rcx, rbx; this
0x18000b389  call    ?Reset@CLocalAccounts@@UEAAJXZ; CLocalAccounts::Reset(void)
0x18000b38e  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000b392  call    cs:__imp_DeleteCriticalSection
0x18000b398  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x18000b39f  add     rsp, 20h
0x18000b3a3  pop     rbx
0x18000b3a4  retn
```
