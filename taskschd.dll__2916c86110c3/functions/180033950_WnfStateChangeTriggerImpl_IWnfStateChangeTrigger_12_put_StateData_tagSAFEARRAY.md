# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::put_StateData(tagSAFEARRAY *)

- ea: `0x180033950`
- end: `0x180033a0d`
- name: `?put_StateData@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180033950`
- `0x1800351ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003399d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003399d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800339dd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800339dd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800339bd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800339bd`

## pseudocode

```c
__int64 __fastcall WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::put_StateData(__int64 a1, SAFEARRAY *a2)
{
  __int64 v5; // rbx
  SAFEARRAY **v6; // rsi
  SAFEARRAY *v7; // rcx
  unsigned int v8; // edi
  HRESULT v9; // edi
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (a1 + 24) & -(__int64)(a1 != 0);
  if ( v5 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  v10 = v5;
  v6 = (SAFEARRAY **)(a1 + 160);
  v7 = *(SAFEARRAY **)(a1 + 160);
  if ( v7 )
  {
    v9 = SafeArrayDestroy(v7);
    if ( v9 < 0 )
    {
      ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v10);
      return (unsigned int)v9;
    }
    *v6 = 0;
  }
  v8 = SafeArrayCopy(a2, v6);
  if ( v5 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return v8;
}

```

## disassembly

```asm
0x180033950  mov     [rsp+arg_0], rbx
0x180033955  mov     [rsp+arg_18], rsi
0x18003395a  push    rdi
0x18003395b  push    r14
0x18003395d  push    r15
0x18003395f  sub     rsp, 30h
0x180033963  mov     r15, rdx
0x180033966  mov     rdi, rcx
0x180033969  test    rdx, rdx
0x18003396c  jnz     short loc_180033987
0x18003396e  mov     eax, 80004003h
0x180033973  mov     rbx, [rsp+48h+arg_0]
0x180033978  mov     rsi, [rsp+48h+arg_18]
0x18003397d  add     rsp, 30h
0x180033981  pop     r15
0x180033983  pop     r14
0x180033985  pop     rdi
0x180033986  retn
0x180033987  mov     rax, rdi
0x18003398a  add     rcx, 18h
0x18003398e  neg     rax
0x180033991  sbb     rbx, rbx
0x180033994  and     rbx, rcx
0x180033997  jz      short loc_1800339A3
0x180033999  lea     rcx, [rbx+8]; lpCriticalSection
0x18003399d  call    cs:__imp_EnterCriticalSection
0x1800339a3  mov     [rsp+48h+arg_10], rbx
0x1800339a8  lea     rsi, [rdi+0A0h]
0x1800339af  mov     rcx, [rsi]; psa
0x1800339b2  test    rcx, rcx
0x1800339b5  jnz     short loc_1800339DD
0x1800339b7  mov     rdx, rsi; ppsaOut
0x1800339ba  mov     rcx, r15; psa
0x1800339bd  call    cs:__imp_SafeArrayCopy
0x1800339c3  mov     edi, eax
0x1800339c5  mov     [rsp+48h+arg_8], eax
0x1800339c9  test    rbx, rbx
0x1800339cc  jz      short loc_1800339D9
0x1800339ce  lea     rcx, [rbx+8]; lpCriticalSection
0x1800339d2  call    cs:__imp_LeaveCriticalSection
0x1800339d8  nop
0x1800339d9  mov     eax, edi
0x1800339db  jmp     short loc_180033973
0x1800339dd  call    cs:__imp_SafeArrayDestroy
0x1800339e3  mov     edi, eax
0x1800339e5  mov     [rsp+48h+arg_8], eax
0x1800339e9  test    eax, eax
0x1800339eb  jns     short loc_1800339FE
0x1800339ed  lea     rcx, [rsp+48h+arg_10]
0x1800339f2  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x1800339f7  mov     eax, edi
0x1800339f9  jmp     loc_180033973
0x1800339fe  mov     qword ptr [rsi], 0
0x180033a05  jmp     short loc_1800339B7
0x180033a07  mov     edi, [rsp+48h+arg_8]
0x180033a0b  jmp     short loc_1800339D9
```
