# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180014464`
- end: `0x1800144fe`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026fb0`
- `0x18002aca4`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180014464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001448f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001448f`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        RTL_SRWLOCK *a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  __int64 result; // rax
  unsigned int *v9; // rbx
  unsigned __int64 v10; // r8
  unsigned int Ptr_high; // eax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-20h]
  unsigned int *v14; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v14 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (Source[1] = 0,
          Source[0] = a3,
          v13 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[10], Source, v10)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x180014464  mov     [rsp+arg_8], rbx
0x180014469  mov     [rsp+arg_10], rbp
0x18001446e  push    rsi
0x18001446f  push    rdi
0x180014470  push    r14
0x180014472  sub     rsp, 30h
0x180014476  mov     eax, [rcx]
0x180014478  mov     ebp, r9d
0x18001447b  mov     edi, r8d
0x18001447e  mov     rsi, rdx
0x180014481  mov     r14, rcx
0x180014484  test    eax, eax
0x180014486  jz      short loc_1800144EA
0x180014488  lea     rbx, [rcx+8]
0x18001448c  mov     rcx, rbx; SRWLock
0x18001448f  call    cs:__imp_AcquireSRWLockExclusive
0x180014496  nop     dword ptr [rax+rax+00h]
0x18001449b  mov     eax, [r14+1Ch]
0x18001449f  mov     [rsp+48h+arg_0], rbx
0x1800144a4  test    ebp, ebp
0x1800144a6  jz      short loc_1800144CF
0x1800144a8  cmp     ebp, eax
0x1800144aa  jnz     short loc_1800144CF
0x1800144ac  lea     rcx, [r14+50h]; this
0x1800144b0  mov     [rsp+48h+var_24], 0
0x1800144b8  lea     rdx, [rsp+48h+Source]; Source
0x1800144bd  mov     [rsp+48h+Source], edi
0x1800144c1  mov     [rsp+48h+var_20], rsi
0x1800144c6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800144cb  test    al, al
0x1800144cd  jnz     short loc_1800144E0
0x1800144cf  neg     edi
0x1800144d1  sbb     eax, eax
0x1800144d3  and     eax, 83Ah
0x1800144d8  add     eax, 0FFFFF7C1h
0x1800144dd  lock and [rsi], eax
0x1800144e0  lea     rcx, [rsp+48h+arg_0]
0x1800144e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800144ea  mov     rbx, [rsp+48h+arg_8]
0x1800144ef  mov     rbp, [rsp+48h+arg_10]
0x1800144f4  add     rsp, 30h
0x1800144f8  pop     r14
0x1800144fa  pop     rdi
0x1800144fb  pop     rsi
0x1800144fc  retn
```
