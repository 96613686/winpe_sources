# WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>::put_StateName(tagSAFEARRAY *)

- ea: `0x18002fbd0`
- end: `0x18002fc8d`
- name: `?put_StateName@?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002fbd0`
- `0x1800351ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc1d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002fc5d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002fc5d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18002fc3d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18002fc3d`

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
0x18002fbd0  mov     [rsp+arg_0], rbx
0x18002fbd5  mov     [rsp+arg_18], rsi
0x18002fbda  push    rdi
0x18002fbdb  push    r14
0x18002fbdd  push    r15
0x18002fbdf  sub     rsp, 30h
0x18002fbe3  mov     r15, rdx
0x18002fbe6  mov     rdi, rcx
0x18002fbe9  test    rdx, rdx
0x18002fbec  jnz     short loc_18002FC07
0x18002fbee  mov     eax, 80004003h
0x18002fbf3  mov     rbx, [rsp+48h+arg_0]
0x18002fbf8  mov     rsi, [rsp+48h+arg_18]
0x18002fbfd  add     rsp, 30h
0x18002fc01  pop     r15
0x18002fc03  pop     r14
0x18002fc05  pop     rdi
0x18002fc06  retn
0x18002fc07  mov     rax, rdi
0x18002fc0a  add     rcx, 18h
0x18002fc0e  neg     rax
0x18002fc11  sbb     rbx, rbx
0x18002fc14  and     rbx, rcx
0x18002fc17  jz      short loc_18002FC23
0x18002fc19  lea     rcx, [rbx+8]; lpCriticalSection
0x18002fc1d  call    cs:__imp_EnterCriticalSection
0x18002fc23  mov     [rsp+48h+arg_10], rbx
0x18002fc28  lea     rsi, [rdi+98h]
0x18002fc2f  mov     rcx, [rsi]; psa
0x18002fc32  test    rcx, rcx
0x18002fc35  jnz     short loc_18002FC5D
0x18002fc37  mov     rdx, rsi; ppsaOut
0x18002fc3a  mov     rcx, r15; psa
0x18002fc3d  call    cs:__imp_SafeArrayCopy
0x18002fc43  mov     edi, eax
0x18002fc45  mov     [rsp+48h+arg_8], eax
0x18002fc49  test    rbx, rbx
0x18002fc4c  jz      short loc_18002FC59
0x18002fc4e  lea     rcx, [rbx+8]; lpCriticalSection
0x18002fc52  call    cs:__imp_LeaveCriticalSection
0x18002fc58  nop
0x18002fc59  mov     eax, edi
0x18002fc5b  jmp     short loc_18002FBF3
0x18002fc5d  call    cs:__imp_SafeArrayDestroy
0x18002fc63  mov     edi, eax
0x18002fc65  mov     [rsp+48h+arg_8], eax
0x18002fc69  test    eax, eax
0x18002fc6b  jns     short loc_18002FC7E
0x18002fc6d  lea     rcx, [rsp+48h+arg_10]
0x18002fc72  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x18002fc77  mov     eax, edi
0x18002fc79  jmp     loc_18002FBF3
0x18002fc7e  mov     qword ptr [rsi], 0
0x18002fc85  jmp     short loc_18002FC37
0x18002fc87  mov     edi, [rsp+48h+arg_8]
0x18002fc8b  jmp     short loc_18002FC59
```
