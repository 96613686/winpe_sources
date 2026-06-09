# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x18001b490`
- end: `0x18001b59c`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001c300`

## callees

- `0x18001b198`
- `0x18001b490`
- `0x18001bf44`
- `0x18001bf74`
- `0x180037010`

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
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // r8
  struct ATL::_ATL_OBJMAP_ENTRY30 *v10; // rdi
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
  for ( i = off_1800480F0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800480F8; ++i )
  {
    v10 = *i;
    if ( *i && *((_QWORD *)v10 + 2) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)((char *)v10 + 32);
      if ( !*((_QWORD *)v10 + 4) )
      {
        v13 = 0;
        v12 = qword_180048100;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v12);
        if ( v8 < 0 )
        {
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v10 + 2))(
                 *((_QWORD *)v10 + 3),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (__int64)v10 + 32);
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
0x18001b490  push    rbx
0x18001b492  push    rbp
0x18001b493  push    rsi
0x18001b494  push    rdi
0x18001b495  push    r14
0x18001b497  sub     rsp, 30h
0x18001b49b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18001b4a2  mov     r14, r9
0x18001b4a5  mov     r9, rdx
0x18001b4a8  mov     rbp, r8
0x18001b4ab  jnz     short loc_18001B4B7
0x18001b4ad  mov     eax, 8000FFFFh
0x18001b4b2  jmp     loc_18001B591
0x18001b4b7  test    r14, r14
0x18001b4ba  jnz     short loc_18001B4C6
0x18001b4bc  mov     eax, 80004003h
0x18001b4c1  jmp     loc_18001B591
0x18001b4c6  mov     qword ptr [r14], 0
0x18001b4cd  xor     ebx, ebx
0x18001b4cf  mov     r8, cs:off_1800480F0
0x18001b4d6  cmp     r8, cs:off_1800480F8
0x18001b4dd  jnb     loc_18001B57F
0x18001b4e3  mov     rdi, [r8]
0x18001b4e6  test    rdi, rdi
0x18001b4e9  jz      short loc_18001B500
0x18001b4eb  cmp     [rdi+10h], rbx
0x18001b4ef  jz      short loc_18001B500
0x18001b4f1  mov     rdx, [rdi]; struct _GUID *
0x18001b4f4  mov     rcx, r9; struct _GUID *
0x18001b4f7  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001b4fc  test    eax, eax
0x18001b4fe  jnz     short loc_18001B506
0x18001b500  add     r8, 8
0x18001b504  jmp     short loc_18001B4D6
0x18001b506  lea     rsi, [rdi+20h]
0x18001b50a  cmp     [rsi], rbx
0x18001b50d  jnz     short loc_18001B564
0x18001b50f  lea     rax, qword_180048100
0x18001b516  mov     [rsp+58h+var_30], bl
0x18001b51a  lea     rcx, [rsp+58h+var_38]
0x18001b51f  mov     [rsp+58h+var_38], rax
0x18001b524  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001b529  mov     ebx, eax
0x18001b52b  test    eax, eax
0x18001b52d  jns     short loc_18001B53B
0x18001b52f  lea     rcx, [rsp+58h+var_38]
0x18001b534  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001b539  jmp     short loc_18001B57F
0x18001b53b  cmp     qword ptr [rsi], 0
0x18001b53f  jnz     short loc_18001B55A
0x18001b541  mov     rcx, [rdi+18h]
0x18001b545  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001b54c  mov     rax, [rdi+10h]
0x18001b550  mov     r8, rsi
0x18001b553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b558  mov     ebx, eax
0x18001b55a  lea     rcx, [rsp+58h+var_38]
0x18001b55f  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001b564  mov     rcx, [rsi]
0x18001b567  test    rcx, rcx
0x18001b56a  jz      short loc_18001B57F
0x18001b56c  mov     rax, [rcx]
0x18001b56f  mov     r8, r14
0x18001b572  mov     rdx, rbp
0x18001b575  mov     rax, [rax]
0x18001b578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b57d  mov     ebx, eax
0x18001b57f  cmp     qword ptr [r14], 0
0x18001b583  jnz     short loc_18001B58F
0x18001b585  test    ebx, ebx
0x18001b587  mov     eax, 80040111h
0x18001b58c  cmovz   ebx, eax
0x18001b58f  mov     eax, ebx
0x18001b591  add     rsp, 30h
0x18001b595  pop     r14
0x18001b597  pop     rdi
0x18001b598  pop     rsi
0x18001b599  pop     rbp
0x18001b59a  pop     rbx
0x18001b59b  retn
```
