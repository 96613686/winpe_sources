# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::put_StateName(tagSAFEARRAY *)

- ea: `0x180032270`
- end: `0x180032346`
- name: `?put_StateName@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180032270`
- `0x180037cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800322ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800322ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800322be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800322be`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032310`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032310`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800322e4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800322e4`

## pseudocode

```c
__int64 __fastcall WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::put_StateName(__int64 a1, SAFEARRAY *a2)
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
  v6 = (SAFEARRAY **)(a1 + 152);
  v7 = *(SAFEARRAY **)(a1 + 152);
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
0x180032270  mov     [rsp+arg_0], rbx
0x180032275  mov     [rsp+arg_18], rsi
0x18003227a  push    rdi
0x18003227b  push    r14
0x18003227d  push    r15
0x18003227f  sub     rsp, 30h
0x180032283  mov     r15, rdx
0x180032286  mov     rdi, rcx
0x180032289  test    rdx, rdx
0x18003228c  jnz     short loc_1800322A8
0x18003228e  mov     eax, 80004003h
0x180032293  mov     rbx, [rsp+48h+arg_0]
0x180032298  mov     rsi, [rsp+48h+arg_18]
0x18003229d  add     rsp, 30h
0x1800322a1  pop     r15
0x1800322a3  pop     r14
0x1800322a5  pop     rdi
0x1800322a6  retn
0x1800322a8  mov     rax, rdi
0x1800322ab  add     rcx, 18h
0x1800322af  neg     rax
0x1800322b2  sbb     rbx, rbx
0x1800322b5  and     rbx, rcx
0x1800322b8  jz      short loc_1800322CA
0x1800322ba  lea     rcx, [rbx+8]; lpCriticalSection
0x1800322be  call    cs:__imp_EnterCriticalSection
0x1800322c5  nop     dword ptr [rax+rax+00h]
0x1800322ca  mov     [rsp+48h+arg_10], rbx
0x1800322cf  lea     rsi, [rdi+98h]
0x1800322d6  mov     rcx, [rsi]; psa
0x1800322d9  test    rcx, rcx
0x1800322dc  jnz     short loc_180032310
0x1800322de  mov     rdx, rsi; ppsaOut
0x1800322e1  mov     rcx, r15; psa
0x1800322e4  call    cs:__imp_SafeArrayCopy
0x1800322eb  nop     dword ptr [rax+rax+00h]
0x1800322f0  mov     edi, eax
0x1800322f2  mov     [rsp+48h+arg_8], eax
0x1800322f6  test    rbx, rbx
0x1800322f9  jz      short loc_18003230C
0x1800322fb  lea     rcx, [rbx+8]; lpCriticalSection
0x1800322ff  call    cs:__imp_LeaveCriticalSection
0x180032306  nop     dword ptr [rax+rax+00h]
0x18003230b  nop
0x18003230c  mov     eax, edi
0x18003230e  jmp     short loc_180032293
0x180032310  call    cs:__imp_SafeArrayDestroy
0x180032317  nop     dword ptr [rax+rax+00h]
0x18003231c  mov     edi, eax
0x18003231e  mov     [rsp+48h+arg_8], eax
0x180032322  test    eax, eax
0x180032324  jns     short loc_180032337
0x180032326  lea     rcx, [rsp+48h+arg_10]
0x18003232b  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180032330  mov     eax, edi
0x180032332  jmp     loc_180032293
0x180032337  mov     qword ptr [rsi], 0
0x18003233e  jmp     short loc_1800322DE
0x180032340  mov     edi, [rsp+48h+arg_8]
0x180032344  jmp     short loc_18003230C
```
