# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004b04`
- end: `0x180004bb0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b40`
- `0x180006d34`
- `0x1800081b8`
- `0x1800087d0`

## callees

- `0x1800041f0`
- `0x180004b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004b78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004b78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004b91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004b91`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 Ptr; // rcx
  void *v6; // [rsp+50h] [rbp+8h] BYREF

  if ( !this[3].Ptr )
  {
    LastError = GetLastError();
    if ( this[3].Ptr )
    {
      v3 = 0;
    }
    else
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(Ptr, &v6) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v6;
        }
      }
      v3 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    }
    AcquireSRWLockExclusive(this + 4);
    if ( !this[3].Ptr )
      this[3].Ptr = (PVOID)v3;
    if ( this != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(this + 4);
    SetLastError(LastError);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x180004b04  push    rbx
0x180004b06  push    rbp
0x180004b07  push    rsi
0x180004b08  push    rdi
0x180004b09  sub     rsp, 28h
0x180004b0d  cmp     qword ptr [rcx+18h], 0
0x180004b12  mov     rbx, rcx
0x180004b15  jnz     loc_180004B9F
0x180004b1b  call    cs:__imp_GetLastError
0x180004b21  cmp     qword ptr [rbx+18h], 0
0x180004b26  mov     ebp, eax
0x180004b28  jz      short loc_180004B2E
0x180004b2a  xor     esi, esi
0x180004b2c  jmp     short loc_180004B71
0x180004b2e  cmp     qword ptr [rbx+10h], 0
0x180004b33  jnz     short loc_180004B60
0x180004b35  mov     rcx, [rbx+8]
0x180004b39  lea     rdx, [rsp+48h+arg_0]
0x180004b3e  mov     [rsp+48h+arg_0], 0
0x180004b47  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004b4c  test    eax, eax
0x180004b4e  js      short loc_180004B60
0x180004b50  cmp     qword ptr [rbx+10h], 0
0x180004b55  jnz     short loc_180004B60
0x180004b57  mov     rax, [rsp+48h+arg_0]
0x180004b5c  mov     [rbx+10h], rax
0x180004b60  mov     rax, [rbx+10h]
0x180004b64  lea     rcx, [rax+20h]
0x180004b68  neg     rax
0x180004b6b  sbb     rsi, rsi
0x180004b6e  and     rsi, rcx
0x180004b71  lea     rdi, [rbx+20h]
0x180004b75  mov     rcx, rdi; SRWLock
0x180004b78  call    cs:__imp_AcquireSRWLockExclusive
0x180004b7e  cmp     qword ptr [rbx+18h], 0
0x180004b83  jnz     short loc_180004B89
0x180004b85  mov     [rbx+18h], rsi
0x180004b89  test    rdi, rdi
0x180004b8c  jz      short loc_180004B97
0x180004b8e  mov     rcx, rdi; SRWLock
0x180004b91  call    cs:__imp_ReleaseSRWLockExclusive
0x180004b97  mov     ecx, ebp; dwErrCode
0x180004b99  call    cs:__imp_SetLastError
0x180004b9f  cmp     qword ptr [rbx+18h], 0
0x180004ba4  setnz   al
0x180004ba7  add     rsp, 28h
0x180004bab  pop     rdi
0x180004bac  pop     rsi
0x180004bad  pop     rbp
0x180004bae  pop     rbx
0x180004baf  retn
```
