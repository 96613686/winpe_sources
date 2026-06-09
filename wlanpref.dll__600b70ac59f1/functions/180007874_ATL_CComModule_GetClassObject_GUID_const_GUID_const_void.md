# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180007874`
- end: `0x180007979`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `261`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c590`

## callees

- `0x180003014`
- `0x180004aec`
- `0x180007874`
- `0x1800080c4`
- `0x180008560`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::GetClassObject(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v8; // edi
  __int64 v9; // rbx
  ATL::CComModule **v10; // r14
  __int64 *v11; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = qword_1800402F8;
  if ( qword_1800402F8 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && (unsigned int)InlineIsEqualGUID(a2, *(const struct _GUID **)v9) )
      {
        v10 = (ATL::CComModule **)(v9 + 32);
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v11 = qword_18003F6F0;
          v12 = 0;
          v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock((__int64)&v11);
          if ( v8 < 0 )
          {
            ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v11);
            break;
          }
          if ( !*v10 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                   *(_QWORD *)(v9 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v9 + 32);
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v11);
        }
        this = *v10;
        if ( *v10 )
          v8 = (**(__int64 (__fastcall ***)(ATL::CComModule *, const struct _GUID *, void **))this)(this, a3, a4);
        break;
      }
      v9 += 72;
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)ATL::AtlComModuleGetClassObject(this, a2, a3, a4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007874  push    rbx
0x180007876  push    rbp
0x180007877  push    rsi
0x180007878  push    rdi
0x180007879  push    r14
0x18000787b  push    r15
0x18000787d  sub     rsp, 38h
0x180007881  mov     rsi, r9
0x180007884  mov     r15, r8
0x180007887  mov     rbp, rdx
0x18000788a  test    r9, r9
0x18000788d  jnz     short loc_180007899
0x18000788f  mov     eax, 80004003h
0x180007894  jmp     loc_18000796C
0x180007899  mov     qword ptr [r9], 0
0x1800078a0  xor     edi, edi
0x1800078a2  mov     rbx, cs:qword_1800402F8
0x1800078a9  test    rbx, rbx
0x1800078ac  jz      loc_180007950
0x1800078b2  mov     rdx, [rbx]; struct _GUID *
0x1800078b5  test    rdx, rdx
0x1800078b8  jz      loc_180007950
0x1800078be  cmp     [rbx+10h], rdi
0x1800078c2  jz      short loc_1800078D0
0x1800078c4  mov     rcx, rbp; struct _GUID *
0x1800078c7  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800078cc  test    eax, eax
0x1800078ce  jnz     short loc_1800078D6
0x1800078d0  add     rbx, 48h ; 'H'
0x1800078d4  jmp     short loc_1800078B2
0x1800078d6  lea     r14, [rbx+20h]
0x1800078da  cmp     [r14], rdi
0x1800078dd  jnz     short loc_180007935
0x1800078df  lea     rax, qword_18003F6F0
0x1800078e6  mov     [rsp+68h+var_48], rax
0x1800078eb  mov     [rsp+68h+var_40], dil
0x1800078f0  lea     rcx, [rsp+68h+var_48]
0x1800078f5  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800078fa  mov     edi, eax
0x1800078fc  test    eax, eax
0x1800078fe  jns     short loc_18000790C
0x180007900  lea     rcx, [rsp+68h+var_48]
0x180007905  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000790a  jmp     short loc_180007950
0x18000790c  cmp     qword ptr [r14], 0
0x180007910  jnz     short loc_18000792B
0x180007912  mov     r8, r14
0x180007915  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000791c  mov     rcx, [rbx+18h]
0x180007920  mov     rax, [rbx+10h]
0x180007924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007929  mov     edi, eax
0x18000792b  lea     rcx, [rsp+68h+var_48]
0x180007930  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180007935  mov     rcx, [r14]
0x180007938  test    rcx, rcx
0x18000793b  jz      short loc_180007950
0x18000793d  mov     rax, [rcx]
0x180007940  mov     r8, rsi
0x180007943  mov     rdx, r15
0x180007946  mov     rax, [rax]
0x180007949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000794e  mov     edi, eax
0x180007950  cmp     qword ptr [rsi], 0
0x180007954  jnz     short loc_18000796A
0x180007956  test    edi, edi
0x180007958  jnz     short loc_18000796A
0x18000795a  mov     r9, rsi; void **
0x18000795d  mov     r8, r15; struct _GUID *
0x180007960  mov     rdx, rbp; struct _GUID *
0x180007963  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180007968  mov     edi, eax
0x18000796a  mov     eax, edi
0x18000796c  add     rsp, 38h
0x180007970  pop     r15
0x180007972  pop     r14
0x180007974  pop     rdi
0x180007975  pop     rsi
0x180007976  pop     rbp
0x180007977  pop     rbx
0x180007978  retn
```
