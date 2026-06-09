# CInvertedStorePluginLocator::LookUpPlugin(wchar_t const *,wchar_t const *,ICiCDocStore * *)

- ea: `0x1800f66f0`
- end: `0x1800f687c`
- name: `?LookUpPlugin@CInvertedStorePluginLocator@@UEAAJPEB_W0PEAPEAUICiCDocStore@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(CInvertedStorePluginLocator *__hidden this, const wchar_t *, const wchar_t *, struct ICiCDocStore **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800f66f0`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f67b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f67b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f672d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f672d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f683a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f683a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6733`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f679b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f686c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f679b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f686c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CInvertedStorePluginLocator::LookUpPlugin(
        RTL_SRWLOCK *this,
        const wchar_t *a2,
        const wchar_t *a3,
        struct ICiCDocStore **a4)
{
  unsigned int v7; // r15d
  RTL_SRWLOCK *v8; // rdi
  __int64 **i; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  bool v12; // si
  void *v14; // [rsp+40h] [rbp-10h] BYREF
  char v15; // [rsp+48h] [rbp-8h]
  void *pv; // [rsp+90h] [rbp+40h]
  __int64 v18; // [rsp+A8h] [rbp+58h] BYREF

  *a4 = 0;
  v7 = -2147213053;
  v8 = this + 3;
  AcquireSRWLockShared(this + 3);
  HIDWORD(v8[1].Ptr) = GetCurrentThreadId();
  for ( i = (__int64 **)this[5].Ptr; i != this[6].Ptr; ++i )
  {
    pv = 0;
    v10 = *i;
    v11 = **i;
    v14 = 0;
    v15 = 1;
    v12 = (*(int (__fastcall **)(__int64 *, void **))(v11 + 112))(v10, &v14) >= 0;
    if ( v15 )
      pv = v14;
    if ( v12 && !(unsigned int)_o__wcsicmp(pv, a3) )
    {
      v18 = 0;
      if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD, _QWORD, __int64 *))(**i + 88))(*i, a2, 0, 0, &v18) >= 0 )
        v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICiCDocStore **))v18)(
               v18,
               &GUID_46625468_3c32_11d0_8c90_0020af1d740e,
               a4);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      if ( pv )
        CoTaskMemFree(pv);
      break;
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  ReleaseSRWLockShared(v8);
  return v7;
}

```

## disassembly

```asm
0x1800f66f0  mov     [rsp-38h+arg_10], rbx
0x1800f66f5  mov     [rsp-38h+arg_8], rdx
0x1800f66fa  push    rbp
0x1800f66fb  push    rsi
0x1800f66fc  push    rdi
0x1800f66fd  push    r12
0x1800f66ff  push    r13
0x1800f6701  push    r14
0x1800f6703  push    r15
0x1800f6705  mov     rbp, rsp
0x1800f6708  sub     rsp, 50h
0x1800f670c  mov     r12, r9
0x1800f670f  mov     r13, r8
0x1800f6712  mov     r14, rcx
0x1800f6715  mov     qword ptr [r9], 0
0x1800f671c  mov     r15d, 80042103h
0x1800f6722  lea     rdi, [rcx+18h]
0x1800f6726  mov     [rbp+var_20], rdi
0x1800f672a  mov     rcx, rdi; SRWLock
0x1800f672d  call    cs:__imp_AcquireSRWLockShared
0x1800f6733  call    cs:__imp_GetCurrentThreadId
0x1800f6739  mov     [rdi+0Ch], eax
0x1800f673c  mov     rbx, [r14+28h]
0x1800f6740  cmp     rbx, [r14+30h]
0x1800f6744  jz      loc_1800F6837
0x1800f674a  mov     [rbp+pv], 0
0x1800f6752  mov     rcx, [rbx]
0x1800f6755  mov     rax, [rcx]
0x1800f6758  lea     rdx, [rbp+pv]
0x1800f675c  mov     [rbp+var_18], rdx
0x1800f6760  mov     [rbp+var_10], 0
0x1800f6768  mov     [rbp+var_8], 1
0x1800f676c  lea     rdx, [rbp+var_10]
0x1800f6770  mov     rax, [rax+70h]
0x1800f6774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6779  mov     esi, eax
0x1800f677b  shr     esi, 1Fh
0x1800f677e  xor     sil, 1
0x1800f6782  cmp     [rbp+var_8], 0
0x1800f6786  jz      short loc_1800F67A1
0x1800f6788  mov     r8, [rbp+var_18]
0x1800f678c  mov     rcx, [r8]; pv
0x1800f678f  mov     rdx, [rbp+var_10]
0x1800f6793  mov     [r8], rdx
0x1800f6796  test    rcx, rcx
0x1800f6799  jz      short loc_1800F67A1
0x1800f679b  call    cs:__imp_CoTaskMemFree
0x1800f67a1  test    sil, sil
0x1800f67a4  jz      loc_1800F685B
0x1800f67aa  mov     rdx, r13
0x1800f67ad  mov     rcx, [rbp+pv]
0x1800f67b1  call    cs:__imp__o__wcsicmp
0x1800f67b7  test    eax, eax
0x1800f67b9  jnz     loc_1800F685B
0x1800f67bf  mov     [rbp+arg_18], 0
0x1800f67c7  mov     rcx, [rbx]
0x1800f67ca  mov     rax, [rcx]
0x1800f67cd  lea     rdx, [rbp+arg_18]
0x1800f67d1  mov     [rsp+50h+var_30], rdx
0x1800f67d6  xor     r9d, r9d
0x1800f67d9  xor     r8d, r8d
0x1800f67dc  mov     rdx, [rbp+arg_8]
0x1800f67e0  mov     rax, [rax+58h]
0x1800f67e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f67e9  test    eax, eax
0x1800f67eb  js      short loc_1800F6809
0x1800f67ed  mov     rcx, [rbp+arg_18]
0x1800f67f1  mov     rax, [rcx]
0x1800f67f4  mov     r8, r12
0x1800f67f7  lea     rdx, _GUID_46625468_3c32_11d0_8c90_0020af1d740e
0x1800f67fe  mov     rax, [rax]
0x1800f6801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6806  mov     r15d, eax
0x1800f6809  mov     rcx, [rbp+arg_18]
0x1800f680d  test    rcx, rcx
0x1800f6810  jz      short loc_1800F681F
0x1800f6812  mov     rdx, [rcx]
0x1800f6815  mov     rax, [rdx+10h]
0x1800f6819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f681e  nop
0x1800f681f  mov     rcx, [rbp+pv]; pv
0x1800f6823  mov     [rbp+pv], 0
0x1800f682b  test    rcx, rcx
0x1800f682e  jz      short loc_1800F6837
0x1800f6830  call    cs:__imp_CoTaskMemFree
0x1800f6836  nop
0x1800f6837  mov     rcx, rdi; SRWLock
0x1800f683a  call    cs:__imp_ReleaseSRWLockShared
0x1800f6840  mov     eax, r15d
0x1800f6843  mov     rbx, [rsp+50h+arg_10]
0x1800f684b  add     rsp, 50h
0x1800f684f  pop     r15
0x1800f6851  pop     r14
0x1800f6853  pop     r13
0x1800f6855  pop     r12
0x1800f6857  pop     rdi
0x1800f6858  pop     rsi
0x1800f6859  pop     rbp
0x1800f685a  retn
0x1800f685b  mov     rcx, [rbp+pv]; pv
0x1800f685f  mov     [rbp+pv], 0
0x1800f6867  test    rcx, rcx
0x1800f686a  jz      short loc_1800F6872
0x1800f686c  call    cs:__imp_CoTaskMemFree
0x1800f6872  add     rbx, 8
0x1800f6876  jmp     loc_1800F6740
```
