# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000478c`
- end: `0x18000488e`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `258`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800066a0`

## callees

- `0x180002c40`
- `0x180003a30`
- `0x18000478c`
- `0x180004ae0`
- `0x1800066e0`
- `0x180013010`

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
  v9 = *((_QWORD *)this + 9);
  if ( v9 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && (unsigned int)InlineIsEqualGUID(a2) )
      {
        v10 = (ATL::CComModule **)(v9 + 32);
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v11 = qword_18001D340;
          v12 = 0;
          v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v11);
          if ( v8 < 0 )
          {
            ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v11);
            break;
          }
          if ( !*v10 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                   *(_QWORD *)(v9 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v9 + 32);
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v11);
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
0x18000478c  push    rbx
0x18000478e  push    rbp
0x18000478f  push    rsi
0x180004790  push    rdi
0x180004791  push    r14
0x180004793  push    r15
0x180004795  sub     rsp, 38h
0x180004799  mov     rsi, r9
0x18000479c  mov     r15, r8
0x18000479f  mov     rbp, rdx
0x1800047a2  test    r9, r9
0x1800047a5  jnz     short loc_1800047B1
0x1800047a7  mov     eax, 80004003h
0x1800047ac  jmp     loc_180004881
0x1800047b1  mov     qword ptr [r9], 0
0x1800047b8  xor     edi, edi
0x1800047ba  mov     rbx, [rcx+48h]
0x1800047be  test    rbx, rbx
0x1800047c1  jz      loc_180004865
0x1800047c7  mov     rdx, [rbx]
0x1800047ca  test    rdx, rdx
0x1800047cd  jz      loc_180004865
0x1800047d3  cmp     [rbx+10h], rdi
0x1800047d7  jz      short loc_1800047E5
0x1800047d9  mov     rcx, rbp
0x1800047dc  call    InlineIsEqualGUID
0x1800047e1  test    eax, eax
0x1800047e3  jnz     short loc_1800047EB
0x1800047e5  add     rbx, 48h ; 'H'
0x1800047e9  jmp     short loc_1800047C7
0x1800047eb  lea     r14, [rbx+20h]
0x1800047ef  cmp     [r14], rdi
0x1800047f2  jnz     short loc_18000484A
0x1800047f4  lea     rax, qword_18001D340
0x1800047fb  mov     [rsp+68h+var_48], rax
0x180004800  mov     [rsp+68h+var_40], dil
0x180004805  lea     rcx, [rsp+68h+var_48]
0x18000480a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000480f  mov     edi, eax
0x180004811  test    eax, eax
0x180004813  jns     short loc_180004821
0x180004815  lea     rcx, [rsp+68h+var_48]
0x18000481a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000481f  jmp     short loc_180004865
0x180004821  cmp     qword ptr [r14], 0
0x180004825  jnz     short loc_180004840
0x180004827  mov     r8, r14
0x18000482a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004831  mov     rcx, [rbx+18h]
0x180004835  mov     rax, [rbx+10h]
0x180004839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000483e  mov     edi, eax
0x180004840  lea     rcx, [rsp+68h+var_48]
0x180004845  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000484a  mov     rcx, [r14]
0x18000484d  test    rcx, rcx
0x180004850  jz      short loc_180004865
0x180004852  mov     rax, [rcx]
0x180004855  mov     r8, rsi
0x180004858  mov     rdx, r15
0x18000485b  mov     rax, [rax]
0x18000485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004863  mov     edi, eax
0x180004865  cmp     qword ptr [rsi], 0
0x180004869  jnz     short loc_18000487F
0x18000486b  test    edi, edi
0x18000486d  jnz     short loc_18000487F
0x18000486f  mov     r9, rsi; void **
0x180004872  mov     r8, r15; struct _GUID *
0x180004875  mov     rdx, rbp; struct _GUID *
0x180004878  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000487d  mov     edi, eax
0x18000487f  mov     eax, edi
0x180004881  add     rsp, 38h
0x180004885  pop     r15
0x180004887  pop     r14
0x180004889  pop     rdi
0x18000488a  pop     rsi
0x18000488b  pop     rbp
0x18000488c  pop     rbx
0x18000488d  retn
```
