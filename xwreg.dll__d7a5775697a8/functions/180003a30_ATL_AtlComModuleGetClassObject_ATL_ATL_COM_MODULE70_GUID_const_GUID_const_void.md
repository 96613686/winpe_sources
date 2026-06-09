# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003a30`
- end: `0x180003b3c`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000478c`

## callees

- `0x180002c40`
- `0x180003a30`
- `0x180004ae0`
- `0x1800066e0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v5; // r9
  int v8; // ebx
  __int64 *i; // r8
  __int64 v10; // rdi
  _QWORD *v11; // rsi
  __int64 *v12; // [rsp+20h] [rbp-38h] BYREF
  char v13; // [rsp+28h] [rbp-30h]

  v5 = a2;
  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_18001D330[0]; i < off_18001D338; ++i )
  {
    v10 = *i;
    if ( *i && *(_QWORD *)(v10 + 16) && (unsigned int)InlineIsEqualGUID(v5) )
    {
      v11 = (_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(v10 + 32) )
      {
        v13 = 0;
        v12 = qword_18001D340;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v12);
        if ( v8 < 0 )
        {
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                 *(_QWORD *)(v10 + 24),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 v10 + 32);
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v12);
      }
      if ( *v11 )
        v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v11)(*v11, a3, a4);
      break;
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003a30  push    rbx
0x180003a32  push    rbp
0x180003a33  push    rsi
0x180003a34  push    rdi
0x180003a35  push    r14
0x180003a37  sub     rsp, 30h
0x180003a3b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180003a42  mov     r14, r9
0x180003a45  mov     r9, rdx
0x180003a48  mov     rbp, r8
0x180003a4b  jnz     short loc_180003A57
0x180003a4d  mov     eax, 8000FFFFh
0x180003a52  jmp     loc_180003B31
0x180003a57  test    r14, r14
0x180003a5a  jnz     short loc_180003A66
0x180003a5c  mov     eax, 80004003h
0x180003a61  jmp     loc_180003B31
0x180003a66  mov     qword ptr [r14], 0
0x180003a6d  xor     ebx, ebx
0x180003a6f  mov     r8, cs:off_18001D330
0x180003a76  cmp     r8, cs:off_18001D338
0x180003a7d  jnb     loc_180003B1F
0x180003a83  mov     rdi, [r8]
0x180003a86  test    rdi, rdi
0x180003a89  jz      short loc_180003AA0
0x180003a8b  cmp     [rdi+10h], rbx
0x180003a8f  jz      short loc_180003AA0
0x180003a91  mov     rdx, [rdi]
0x180003a94  mov     rcx, r9
0x180003a97  call    InlineIsEqualGUID
0x180003a9c  test    eax, eax
0x180003a9e  jnz     short loc_180003AA6
0x180003aa0  add     r8, 8
0x180003aa4  jmp     short loc_180003A76
0x180003aa6  lea     rsi, [rdi+20h]
0x180003aaa  cmp     [rsi], rbx
0x180003aad  jnz     short loc_180003B04
0x180003aaf  lea     rax, qword_18001D340
0x180003ab6  mov     [rsp+58h+var_30], bl
0x180003aba  lea     rcx, [rsp+58h+var_38]
0x180003abf  mov     [rsp+58h+var_38], rax
0x180003ac4  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180003ac9  mov     ebx, eax
0x180003acb  test    eax, eax
0x180003acd  jns     short loc_180003ADB
0x180003acf  lea     rcx, [rsp+58h+var_38]
0x180003ad4  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180003ad9  jmp     short loc_180003B1F
0x180003adb  cmp     qword ptr [rsi], 0
0x180003adf  jnz     short loc_180003AFA
0x180003ae1  mov     rcx, [rdi+18h]
0x180003ae5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003aec  mov     rax, [rdi+10h]
0x180003af0  mov     r8, rsi
0x180003af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af8  mov     ebx, eax
0x180003afa  lea     rcx, [rsp+58h+var_38]
0x180003aff  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180003b04  mov     rcx, [rsi]
0x180003b07  test    rcx, rcx
0x180003b0a  jz      short loc_180003B1F
0x180003b0c  mov     rax, [rcx]
0x180003b0f  mov     r8, r14
0x180003b12  mov     rdx, rbp
0x180003b15  mov     rax, [rax]
0x180003b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1d  mov     ebx, eax
0x180003b1f  cmp     qword ptr [r14], 0
0x180003b23  jnz     short loc_180003B2F
0x180003b25  test    ebx, ebx
0x180003b27  mov     eax, 80040111h
0x180003b2c  cmovz   ebx, eax
0x180003b2f  mov     eax, ebx
0x180003b31  add     rsp, 30h
0x180003b35  pop     r14
0x180003b37  pop     rdi
0x180003b38  pop     rsi
0x180003b39  pop     rbp
0x180003b3a  pop     rbx
0x180003b3b  retn
```
