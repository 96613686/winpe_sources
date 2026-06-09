# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000abfc`
- end: `0x18000acba`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `190`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006f24`
- `0x18000b364`
- `0x18000c3ac`

## callees

- `0x180006fec`
- `0x180007050`
- `0x180007070`
- `0x18000a99c`
- `0x18000abfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ac78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ac78`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  __int64 v2; // rsi
  __int64 Ptr; // rcx
  bool v4; // zf
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !this[3].Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
    if ( this[3].Ptr )
    {
      v2 = 0;
    }
    else
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
                    Ptr,
                    (void **)&v6) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v6;
        }
      }
      v2 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    }
    AcquireSRWLockExclusive(this + 4);
    v4 = this[3].Ptr == 0;
    v6 = this + 4;
    if ( v4 )
      this[3].Ptr = (PVOID)v2;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x18000abfc  mov     [rsp+arg_10], rbx
0x18000ac01  mov     [rsp+arg_18], rsi
0x18000ac06  push    rdi
0x18000ac07  sub     rsp, 20h
0x18000ac0b  cmp     qword ptr [rcx+18h], 0
0x18000ac10  mov     rdi, rcx
0x18000ac13  jnz     loc_18000ACA2
0x18000ac19  lea     rcx, [rsp+28h+arg_8]; this
0x18000ac1e  call    ??0last_error_context@wil@@QEAA@XZ
0x18000ac23  cmp     qword ptr [rdi+18h], 0
0x18000ac28  jz      short loc_18000AC2E
0x18000ac2a  xor     esi, esi
0x18000ac2c  jmp     short loc_18000AC71
0x18000ac2e  cmp     qword ptr [rdi+10h], 0
0x18000ac33  jnz     short loc_18000AC60
0x18000ac35  mov     rcx, [rdi+8]
0x18000ac39  lea     rdx, [rsp+28h+arg_0]
0x18000ac3e  mov     [rsp+28h+arg_0], 0
0x18000ac47  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z
0x18000ac4c  test    eax, eax
0x18000ac4e  js      short loc_18000AC60
0x18000ac50  cmp     qword ptr [rdi+10h], 0
0x18000ac55  jnz     short loc_18000AC60
0x18000ac57  mov     rax, [rsp+28h+arg_0]
0x18000ac5c  mov     [rdi+10h], rax
0x18000ac60  mov     rax, [rdi+10h]
0x18000ac64  lea     rcx, [rax+20h]
0x18000ac68  neg     rax
0x18000ac6b  sbb     rsi, rsi
0x18000ac6e  and     rsi, rcx
0x18000ac71  lea     rbx, [rdi+20h]
0x18000ac75  mov     rcx, rbx; SRWLock
0x18000ac78  call    cs:__imp_AcquireSRWLockExclusive
0x18000ac7e  cmp     qword ptr [rdi+18h], 0
0x18000ac83  mov     [rsp+28h+arg_0], rbx
0x18000ac88  jnz     short loc_18000AC8E
0x18000ac8a  mov     [rdi+18h], rsi
0x18000ac8e  lea     rcx, [rsp+28h+arg_0]
0x18000ac93  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ac98  lea     rcx, [rsp+28h+arg_8]; this
0x18000ac9d  call    ??1last_error_context@wil@@QEAA@XZ
0x18000aca2  cmp     qword ptr [rdi+18h], 0
0x18000aca7  mov     rbx, [rsp+28h+arg_10]
0x18000acac  mov     rsi, [rsp+28h+arg_18]
0x18000acb1  setnz   al
0x18000acb4  add     rsp, 20h
0x18000acb8  pop     rdi
0x18000acb9  retn
```
