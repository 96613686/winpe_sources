# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800037c0`
- end: `0x1800038cc`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004560`

## callees

- `0x180003700`
- `0x1800037c0`
- `0x180004274`
- `0x180004674`
- `0x180012010`

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
  for ( i = off_1800200F0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800200F8; ++i )
  {
    v10 = *i;
    if ( *i && *((_QWORD *)v10 + 2) && (unsigned int)InlineIsEqualGUID(v5, *(_QWORD *)v10) )
    {
      v11 = (_QWORD *)((char *)v10 + 32);
      if ( !*((_QWORD *)v10 + 4) )
      {
        v13 = 0;
        v12 = qword_180020100;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v12);
        if ( v8 < 0 )
        {
          CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v10 + 2))(
                 *((_QWORD *)v10 + 3),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (__int64)v10 + 32);
        CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v12);
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
0x1800037c0  push    rbx
0x1800037c2  push    rbp
0x1800037c3  push    rsi
0x1800037c4  push    rdi
0x1800037c5  push    r14
0x1800037c7  sub     rsp, 30h
0x1800037cb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800037d2  mov     r14, r9
0x1800037d5  mov     r9, rdx
0x1800037d8  mov     rbp, r8
0x1800037db  jnz     short loc_1800037E7
0x1800037dd  mov     eax, 8000FFFFh
0x1800037e2  jmp     loc_1800038C1
0x1800037e7  test    r14, r14
0x1800037ea  jnz     short loc_1800037F6
0x1800037ec  mov     eax, 80004003h
0x1800037f1  jmp     loc_1800038C1
0x1800037f6  mov     qword ptr [r14], 0
0x1800037fd  xor     ebx, ebx
0x1800037ff  mov     r8, cs:off_1800200F0
0x180003806  cmp     r8, cs:off_1800200F8
0x18000380d  jnb     loc_1800038AF
0x180003813  mov     rdi, [r8]
0x180003816  test    rdi, rdi
0x180003819  jz      short loc_180003830
0x18000381b  cmp     [rdi+10h], rbx
0x18000381f  jz      short loc_180003830
0x180003821  mov     rdx, [rdi]
0x180003824  mov     rcx, r9
0x180003827  call    InlineIsEqualGUID
0x18000382c  test    eax, eax
0x18000382e  jnz     short loc_180003836
0x180003830  add     r8, 8
0x180003834  jmp     short loc_180003806
0x180003836  lea     rsi, [rdi+20h]
0x18000383a  cmp     [rsi], rbx
0x18000383d  jnz     short loc_180003894
0x18000383f  lea     rax, qword_180020100
0x180003846  mov     [rsp+58h+var_30], bl
0x18000384a  lea     rcx, [rsp+58h+var_38]
0x18000384f  mov     [rsp+58h+var_38], rax
0x180003854  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180003859  mov     ebx, eax
0x18000385b  test    eax, eax
0x18000385d  jns     short loc_18000386B
0x18000385f  lea     rcx, [rsp+58h+var_38]
0x180003864  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180003869  jmp     short loc_1800038AF
0x18000386b  cmp     qword ptr [rsi], 0
0x18000386f  jnz     short loc_18000388A
0x180003871  mov     rcx, [rdi+18h]
0x180003875  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000387c  mov     rax, [rdi+10h]
0x180003880  mov     r8, rsi
0x180003883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003888  mov     ebx, eax
0x18000388a  lea     rcx, [rsp+58h+var_38]
0x18000388f  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180003894  mov     rcx, [rsi]
0x180003897  test    rcx, rcx
0x18000389a  jz      short loc_1800038AF
0x18000389c  mov     rax, [rcx]
0x18000389f  mov     r8, r14
0x1800038a2  mov     rdx, rbp
0x1800038a5  mov     rax, [rax]
0x1800038a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ad  mov     ebx, eax
0x1800038af  cmp     qword ptr [r14], 0
0x1800038b3  jnz     short loc_1800038BF
0x1800038b5  test    ebx, ebx
0x1800038b7  mov     eax, 80040111h
0x1800038bc  cmovz   ebx, eax
0x1800038bf  mov     eax, ebx
0x1800038c1  add     rsp, 30h
0x1800038c5  pop     r14
0x1800038c7  pop     rdi
0x1800038c8  pop     rsi
0x1800038c9  pop     rbp
0x1800038ca  pop     rbx
0x1800038cb  retn
```
