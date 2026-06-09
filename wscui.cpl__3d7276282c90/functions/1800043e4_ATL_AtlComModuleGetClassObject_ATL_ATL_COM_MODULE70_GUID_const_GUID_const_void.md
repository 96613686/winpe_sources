# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800043e4`
- end: `0x1800044f0`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `int(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004660`

## callees

- `0x180003c1c`
- `0x1800042d0`
- `0x1800043e4`
- `0x1800045ac`
- `0x18000c010`

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
  __int128 *v12; // [rsp+20h] [rbp-38h] BYREF
  char v13; // [rsp+28h] [rbp-30h]

  v5 = a2;
  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = (__int64 *)qword_180014AC0; (unsigned __int64)i < qword_180014AC8; ++i )
  {
    v10 = *i;
    if ( *i && *(_QWORD *)(v10 + 16) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(v10 + 32) )
      {
        v13 = 0;
        v12 = &xmmword_180014AD0;
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
0x1800043e4  push    rbx
0x1800043e6  push    rbp
0x1800043e7  push    rsi
0x1800043e8  push    rdi
0x1800043e9  push    r14
0x1800043eb  sub     rsp, 30h
0x1800043ef  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800043f6  mov     r14, r9
0x1800043f9  mov     r9, rdx
0x1800043fc  mov     rbp, r8
0x1800043ff  jnz     short loc_18000440B
0x180004401  mov     eax, 8000FFFFh
0x180004406  jmp     loc_1800044E5
0x18000440b  test    r14, r14
0x18000440e  jnz     short loc_18000441A
0x180004410  mov     eax, 80004003h
0x180004415  jmp     loc_1800044E5
0x18000441a  mov     qword ptr [r14], 0
0x180004421  xor     ebx, ebx
0x180004423  mov     r8, cs:qword_180014AC0
0x18000442a  cmp     r8, cs:qword_180014AC8
0x180004431  jnb     loc_1800044D3
0x180004437  mov     rdi, [r8]
0x18000443a  test    rdi, rdi
0x18000443d  jz      short loc_180004454
0x18000443f  cmp     [rdi+10h], rbx
0x180004443  jz      short loc_180004454
0x180004445  mov     rdx, [rdi]; struct _GUID *
0x180004448  mov     rcx, r9; struct _GUID *
0x18000444b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004450  test    eax, eax
0x180004452  jnz     short loc_18000445A
0x180004454  add     r8, 8
0x180004458  jmp     short loc_18000442A
0x18000445a  lea     rsi, [rdi+20h]
0x18000445e  cmp     [rsi], rbx
0x180004461  jnz     short loc_1800044B8
0x180004463  lea     rax, xmmword_180014AD0
0x18000446a  mov     [rsp+58h+var_30], bl
0x18000446e  lea     rcx, [rsp+58h+var_38]
0x180004473  mov     [rsp+58h+var_38], rax
0x180004478  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000447d  mov     ebx, eax
0x18000447f  test    eax, eax
0x180004481  jns     short loc_18000448F
0x180004483  lea     rcx, [rsp+58h+var_38]
0x180004488  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000448d  jmp     short loc_1800044D3
0x18000448f  cmp     qword ptr [rsi], 0
0x180004493  jnz     short loc_1800044AE
0x180004495  mov     rcx, [rdi+18h]
0x180004499  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800044a0  mov     rax, [rdi+10h]
0x1800044a4  mov     r8, rsi
0x1800044a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ac  mov     ebx, eax
0x1800044ae  lea     rcx, [rsp+58h+var_38]
0x1800044b3  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800044b8  mov     rcx, [rsi]
0x1800044bb  test    rcx, rcx
0x1800044be  jz      short loc_1800044D3
0x1800044c0  mov     rax, [rcx]
0x1800044c3  mov     r8, r14
0x1800044c6  mov     rdx, rbp
0x1800044c9  mov     rax, [rax]
0x1800044cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d1  mov     ebx, eax
0x1800044d3  cmp     qword ptr [r14], 0
0x1800044d7  jnz     short loc_1800044E3
0x1800044d9  test    ebx, ebx
0x1800044db  mov     eax, 80040111h
0x1800044e0  cmovz   ebx, eax
0x1800044e3  mov     eax, ebx
0x1800044e5  add     rsp, 30h
0x1800044e9  pop     r14
0x1800044eb  pop     rdi
0x1800044ec  pop     rsi
0x1800044ed  pop     rbp
0x1800044ee  pop     rbx
0x1800044ef  retn
```
