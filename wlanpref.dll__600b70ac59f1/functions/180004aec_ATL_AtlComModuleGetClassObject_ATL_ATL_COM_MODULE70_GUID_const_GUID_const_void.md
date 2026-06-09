# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180004aec`
- end: `0x180004bf8`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `int(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007874`

## callees

- `0x180003014`
- `0x180004aec`
- `0x1800080c4`
- `0x180008560`
- `0x180030010`

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
  for ( i = off_18003F6E0[0]; i < off_18003F6E8; ++i )
  {
    v10 = *i;
    if ( *i && *(_QWORD *)(v10 + 16) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(v10 + 32) )
      {
        v13 = 0;
        v12 = qword_18003F6F0;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock((__int64)&v12);
        if ( v8 < 0 )
        {
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                 *(_QWORD *)(v10 + 24),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 v10 + 32);
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v12);
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
0x180004aec  push    rbx
0x180004aee  push    rbp
0x180004aef  push    rsi
0x180004af0  push    rdi
0x180004af1  push    r14
0x180004af3  sub     rsp, 30h
0x180004af7  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180004afe  mov     r14, r9
0x180004b01  mov     r9, rdx
0x180004b04  mov     rbp, r8
0x180004b07  jnz     short loc_180004B13
0x180004b09  mov     eax, 8000FFFFh
0x180004b0e  jmp     loc_180004BED
0x180004b13  test    r14, r14
0x180004b16  jnz     short loc_180004B22
0x180004b18  mov     eax, 80004003h
0x180004b1d  jmp     loc_180004BED
0x180004b22  mov     qword ptr [r14], 0
0x180004b29  xor     ebx, ebx
0x180004b2b  mov     r8, cs:off_18003F6E0
0x180004b32  cmp     r8, cs:off_18003F6E8
0x180004b39  jnb     loc_180004BDB
0x180004b3f  mov     rdi, [r8]
0x180004b42  test    rdi, rdi
0x180004b45  jz      short loc_180004B5C
0x180004b47  cmp     [rdi+10h], rbx
0x180004b4b  jz      short loc_180004B5C
0x180004b4d  mov     rdx, [rdi]; struct _GUID *
0x180004b50  mov     rcx, r9; struct _GUID *
0x180004b53  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004b58  test    eax, eax
0x180004b5a  jnz     short loc_180004B62
0x180004b5c  add     r8, 8
0x180004b60  jmp     short loc_180004B32
0x180004b62  lea     rsi, [rdi+20h]
0x180004b66  cmp     [rsi], rbx
0x180004b69  jnz     short loc_180004BC0
0x180004b6b  lea     rax, qword_18003F6F0
0x180004b72  mov     [rsp+58h+var_30], bl
0x180004b76  lea     rcx, [rsp+58h+var_38]
0x180004b7b  mov     [rsp+58h+var_38], rax
0x180004b80  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180004b85  mov     ebx, eax
0x180004b87  test    eax, eax
0x180004b89  jns     short loc_180004B97
0x180004b8b  lea     rcx, [rsp+58h+var_38]
0x180004b90  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180004b95  jmp     short loc_180004BDB
0x180004b97  cmp     qword ptr [rsi], 0
0x180004b9b  jnz     short loc_180004BB6
0x180004b9d  mov     rcx, [rdi+18h]
0x180004ba1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004ba8  mov     rax, [rdi+10h]
0x180004bac  mov     r8, rsi
0x180004baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb4  mov     ebx, eax
0x180004bb6  lea     rcx, [rsp+58h+var_38]
0x180004bbb  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180004bc0  mov     rcx, [rsi]
0x180004bc3  test    rcx, rcx
0x180004bc6  jz      short loc_180004BDB
0x180004bc8  mov     rax, [rcx]
0x180004bcb  mov     r8, r14
0x180004bce  mov     rdx, rbp
0x180004bd1  mov     rax, [rax]
0x180004bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd9  mov     ebx, eax
0x180004bdb  cmp     qword ptr [r14], 0
0x180004bdf  jnz     short loc_180004BEB
0x180004be1  test    ebx, ebx
0x180004be3  mov     eax, 80040111h
0x180004be8  cmovz   ebx, eax
0x180004beb  mov     eax, ebx
0x180004bed  add     rsp, 30h
0x180004bf1  pop     r14
0x180004bf3  pop     rdi
0x180004bf4  pop     rsi
0x180004bf5  pop     rbp
0x180004bf6  pop     rbx
0x180004bf7  retn
```
