# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::put_StateData(tagSAFEARRAY *)

- ea: `0x1800368b0`
- end: `0x180036986`
- name: `?put_StateData@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800368b0`
- `0x180037cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003693f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003693f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800368fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800368fe`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180036950`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180036950`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180036924`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180036924`

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
0x1800368b0  mov     [rsp+arg_0], rbx
0x1800368b5  mov     [rsp+arg_18], rsi
0x1800368ba  push    rdi
0x1800368bb  push    r14
0x1800368bd  push    r15
0x1800368bf  sub     rsp, 30h
0x1800368c3  mov     r15, rdx
0x1800368c6  mov     rdi, rcx
0x1800368c9  test    rdx, rdx
0x1800368cc  jnz     short loc_1800368E8
0x1800368ce  mov     eax, 80004003h
0x1800368d3  mov     rbx, [rsp+48h+arg_0]
0x1800368d8  mov     rsi, [rsp+48h+arg_18]
0x1800368dd  add     rsp, 30h
0x1800368e1  pop     r15
0x1800368e3  pop     r14
0x1800368e5  pop     rdi
0x1800368e6  retn
0x1800368e8  mov     rax, rdi
0x1800368eb  add     rcx, 18h
0x1800368ef  neg     rax
0x1800368f2  sbb     rbx, rbx
0x1800368f5  and     rbx, rcx
0x1800368f8  jz      short loc_18003690A
0x1800368fa  lea     rcx, [rbx+8]; lpCriticalSection
0x1800368fe  call    cs:__imp_EnterCriticalSection
0x180036905  nop     dword ptr [rax+rax+00h]
0x18003690a  mov     [rsp+48h+arg_10], rbx
0x18003690f  lea     rsi, [rdi+0A0h]
0x180036916  mov     rcx, [rsi]; psa
0x180036919  test    rcx, rcx
0x18003691c  jnz     short loc_180036950
0x18003691e  mov     rdx, rsi; ppsaOut
0x180036921  mov     rcx, r15; psa
0x180036924  call    cs:__imp_SafeArrayCopy
0x18003692b  nop     dword ptr [rax+rax+00h]
0x180036930  mov     edi, eax
0x180036932  mov     [rsp+48h+arg_8], eax
0x180036936  test    rbx, rbx
0x180036939  jz      short loc_18003694C
0x18003693b  lea     rcx, [rbx+8]; lpCriticalSection
0x18003693f  call    cs:__imp_LeaveCriticalSection
0x180036946  nop     dword ptr [rax+rax+00h]
0x18003694b  nop
0x18003694c  mov     eax, edi
0x18003694e  jmp     short loc_1800368D3
0x180036950  call    cs:__imp_SafeArrayDestroy
0x180036957  nop     dword ptr [rax+rax+00h]
0x18003695c  mov     edi, eax
0x18003695e  mov     [rsp+48h+arg_8], eax
0x180036962  test    eax, eax
0x180036964  jns     short loc_180036977
0x180036966  lea     rcx, [rsp+48h+arg_10]
0x18003696b  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180036970  mov     eax, edi
0x180036972  jmp     loc_1800368D3
0x180036977  mov     qword ptr [rsi], 0
0x18003697e  jmp     short loc_18003691E
0x180036980  mov     edi, [rsp+48h+arg_8]
0x180036984  jmp     short loc_18003694C
```
