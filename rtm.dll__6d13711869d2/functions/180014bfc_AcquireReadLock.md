# AcquireReadLock

- ea: `0x180014bfc`
- end: `0x180014d23`
- name: `AcquireReadLock`
- size: `295`
- prototype: ``
- caller_count: `26`
- callee_count: `6`
- tags: ``

## callers

- `0x1800039a0`
- `0x180006250`
- `0x180006990`
- `0x180007050`
- `0x1800071a0`
- `0x18000a450`
- `0x18000a770`
- `0x18000ae90`
- `0x18000b2d8`
- `0x18000cee0`
- `0x180011850`
- `0x180012800`
- `0x1800134c0`
- `0x180013930`
- `0x180014580`
- `0x180014970`
- `0x180016a40`
- `0x180017a44`
- `0x180018070`
- `0x18001958c`
- `0x180019de0`
- `0x18001a360`
- `0x18001af20`
- `0x18001e77c`
- `0x18001e8d4`
- `0x18001ed64`

## callees

- `0x180014bfc`
- `0x180014dd8`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014c3d`
- `KERNEL32!EnterCriticalSection` at `0x180014c7d`
- `KERNEL32!EnterCriticalSection` at `0x180014c3d`
- `KERNEL32!EnterCriticalSection` at `0x180014c7d`
- `KERNEL32!LeaveCriticalSection` at `0x180014c70`
- `KERNEL32!LeaveCriticalSection` at `0x180014c91`
- `KERNEL32!LeaveCriticalSection` at `0x180014ccf`
- `KERNEL32!LeaveCriticalSection` at `0x180014c70`
- `KERNEL32!LeaveCriticalSection` at `0x180014c91`
- `KERNEL32!LeaveCriticalSection` at `0x180014ccf`

## string_xrefs

- `0x180014ce1`: `LEAVING AcquireReadLock, lock %x, error %x`

## pseudocode

```c
__int64 __fastcall AcquireReadLock(_QWORD *a1)
{
  LPVOID v2; // rcx
  unsigned int v4; // edi
  int v5; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-814h] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  EnterCriticalSection(&CriticalSection);
  if ( *a1 )
    goto LABEL_4;
  v2 = lpMem;
  if ( lpMem )
  {
    lpMem = *(LPVOID *)lpMem;
    *a1 = v2;
LABEL_4:
    _InterlockedIncrement((volatile signed __int32 *)(*a1 + 64LL));
    LeaveCriticalSection(&CriticalSection);
    EnterCriticalSection((LPCRITICAL_SECTION)(*a1 + 8LL));
    _InterlockedIncrement((volatile signed __int32 *)(*a1 + 48LL));
    LeaveCriticalSection((LPCRITICAL_SECTION)(*a1 + 8LL));
    return 0;
  }
  v4 = CreateReadWriteLock(a1);
  if ( !v4 )
    goto LABEL_4;
  LeaveCriticalSection(&CriticalSection);
  if ( qword_18002B8A8 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"LEAVING AcquireReadLock, lock %x, error %x", a1, v4);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180014bfc  mov     [rsp+arg_8], rbx
0x180014c01  push    rdi
0x180014c02  sub     rsp, 830h
0x180014c09  mov     rax, cs:__security_cookie
0x180014c10  xor     rax, rsp
0x180014c13  mov     [rsp+838h+var_18], rax
0x180014c1b  mov     rbx, rcx
0x180014c1e  xor     eax, eax
0x180014c20  lea     rcx, [rsp+838h+var_814]; void *
0x180014c25  mov     [rsp+838h+var_818], eax
0x180014c29  xor     edx, edx; Val
0x180014c2b  mov     r8d, 7FCh; Size
0x180014c31  call    memset_0
0x180014c36  lea     rcx, CriticalSection; lpCriticalSection
0x180014c3d  call    cs:__imp_EnterCriticalSection
0x180014c43  cmp     qword ptr [rbx], 0
0x180014c47  jnz     short loc_180014C62
0x180014c49  mov     rcx, cs:lpMem
0x180014c50  test    rcx, rcx
0x180014c53  jz      short loc_180014CBA
0x180014c55  mov     rax, [rcx]
0x180014c58  mov     cs:lpMem, rax
0x180014c5f  mov     [rbx], rcx
0x180014c62  mov     rax, [rbx]
0x180014c65  lock inc dword ptr [rax+40h]
0x180014c69  lea     rcx, CriticalSection; lpCriticalSection
0x180014c70  call    cs:__imp_LeaveCriticalSection
0x180014c76  mov     rcx, [rbx]
0x180014c79  add     rcx, 8; lpCriticalSection
0x180014c7d  call    cs:__imp_EnterCriticalSection
0x180014c83  mov     rax, [rbx]
0x180014c86  lock inc dword ptr [rax+30h]
0x180014c8a  mov     rcx, [rbx]
0x180014c8d  add     rcx, 8; lpCriticalSection
0x180014c91  call    cs:__imp_LeaveCriticalSection
0x180014c97  xor     eax, eax
0x180014c99  mov     rcx, [rsp+838h+var_18]
0x180014ca1  xor     rcx, rsp; StackCookie
0x180014ca4  call    __security_check_cookie
0x180014ca9  mov     rbx, [rsp+838h+arg_8]
0x180014cb1  add     rsp, 830h
0x180014cb8  pop     rdi
0x180014cb9  retn
0x180014cba  mov     rcx, rbx
0x180014cbd  call    CreateReadWriteLock
0x180014cc2  mov     edi, eax
0x180014cc4  test    eax, eax
0x180014cc6  jz      short loc_180014C62
0x180014cc8  lea     rcx, CriticalSection; lpCriticalSection
0x180014ccf  call    cs:__imp_LeaveCriticalSection
0x180014cd5  cmp     cs:qword_18002B8A8, 0
0x180014cdd  jz      short loc_180014D1C
0x180014cdf  xor     ecx, ecx
0x180014ce1  lea     rdx, aLeavingAcquire; "LEAVING AcquireReadLock, lock %x, error"...
0x180014ce8  mov     word ptr [rsp+838h+var_818], cx
0x180014ced  mov     r9d, edi
0x180014cf0  lea     rcx, [rsp+838h+var_818]
0x180014cf5  mov     r8, rbx
0x180014cf8  call    FormatRRASErrorString
0x180014cfd  mov     rdx, cs:qword_18002B8A8
0x180014d04  lea     r8, [rsp+838h+var_818]
0x180014d09  mov     rcx, cs:gMgmEtwContext
0x180014d10  mov     rax, cs:gMgmTemplateFunc
0x180014d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d1c  mov     eax, edi
0x180014d1e  jmp     loc_180014C99
```
