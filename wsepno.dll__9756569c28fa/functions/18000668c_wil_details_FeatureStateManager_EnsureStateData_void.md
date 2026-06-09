# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000668c`
- end: `0x180006738`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e80`
- `0x1800091f4`
- `0x18000a88c`
- `0x18000aeb0`

## callees

- `0x18000595c`
- `0x18000668c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006721`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006700`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006700`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006719`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006719`

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
0x18000668c  push    rbx
0x18000668e  push    rbp
0x18000668f  push    rsi
0x180006690  push    rdi
0x180006691  sub     rsp, 28h
0x180006695  cmp     qword ptr [rcx+18h], 0
0x18000669a  mov     rbx, rcx
0x18000669d  jnz     loc_180006727
0x1800066a3  call    cs:__imp_GetLastError
0x1800066a9  cmp     qword ptr [rbx+18h], 0
0x1800066ae  mov     ebp, eax
0x1800066b0  jz      short loc_1800066B6
0x1800066b2  xor     esi, esi
0x1800066b4  jmp     short loc_1800066F9
0x1800066b6  cmp     qword ptr [rbx+10h], 0
0x1800066bb  jnz     short loc_1800066E8
0x1800066bd  mov     rcx, [rbx+8]
0x1800066c1  lea     rdx, [rsp+48h+arg_0]
0x1800066c6  mov     [rsp+48h+arg_0], 0
0x1800066cf  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800066d4  test    eax, eax
0x1800066d6  js      short loc_1800066E8
0x1800066d8  cmp     qword ptr [rbx+10h], 0
0x1800066dd  jnz     short loc_1800066E8
0x1800066df  mov     rax, [rsp+48h+arg_0]
0x1800066e4  mov     [rbx+10h], rax
0x1800066e8  mov     rax, [rbx+10h]
0x1800066ec  lea     rcx, [rax+20h]
0x1800066f0  neg     rax
0x1800066f3  sbb     rsi, rsi
0x1800066f6  and     rsi, rcx
0x1800066f9  lea     rdi, [rbx+20h]
0x1800066fd  mov     rcx, rdi; SRWLock
0x180006700  call    cs:__imp_AcquireSRWLockExclusive
0x180006706  cmp     qword ptr [rbx+18h], 0
0x18000670b  jnz     short loc_180006711
0x18000670d  mov     [rbx+18h], rsi
0x180006711  test    rdi, rdi
0x180006714  jz      short loc_18000671F
0x180006716  mov     rcx, rdi; SRWLock
0x180006719  call    cs:__imp_ReleaseSRWLockExclusive
0x18000671f  mov     ecx, ebp; dwErrCode
0x180006721  call    cs:__imp_SetLastError
0x180006727  cmp     qword ptr [rbx+18h], 0
0x18000672c  setnz   al
0x18000672f  add     rsp, 28h
0x180006733  pop     rdi
0x180006734  pop     rsi
0x180006735  pop     rbp
0x180006736  pop     rbx
0x180006737  retn
```
