# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000a8ac`
- end: `0x18000a958`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008180`
- `0x18000cb08`
- `0x18000de1c`
- `0x18000eb10`

## callees

- `0x180009f58`
- `0x18000a8ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a939`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a920`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a941`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a941`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  PVOID Ptr; // rcx
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
        Ptr = this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire((int)Ptr, &v6) >= 0
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
0x18000a8ac  push    rbx
0x18000a8ae  push    rbp
0x18000a8af  push    rsi
0x18000a8b0  push    rdi
0x18000a8b1  sub     rsp, 28h
0x18000a8b5  cmp     qword ptr [rcx+18h], 0
0x18000a8ba  mov     rbx, rcx
0x18000a8bd  jnz     loc_18000A947
0x18000a8c3  call    cs:__imp_GetLastError
0x18000a8c9  cmp     qword ptr [rbx+18h], 0
0x18000a8ce  mov     ebp, eax
0x18000a8d0  jz      short loc_18000A8D6
0x18000a8d2  xor     esi, esi
0x18000a8d4  jmp     short loc_18000A919
0x18000a8d6  cmp     qword ptr [rbx+10h], 0
0x18000a8db  jnz     short loc_18000A908
0x18000a8dd  mov     rcx, [rbx+8]; int
0x18000a8e1  lea     rdx, [rsp+48h+arg_0]
0x18000a8e6  mov     [rsp+48h+arg_0], 0
0x18000a8ef  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000a8f4  test    eax, eax
0x18000a8f6  js      short loc_18000A908
0x18000a8f8  cmp     qword ptr [rbx+10h], 0
0x18000a8fd  jnz     short loc_18000A908
0x18000a8ff  mov     rax, [rsp+48h+arg_0]
0x18000a904  mov     [rbx+10h], rax
0x18000a908  mov     rax, [rbx+10h]
0x18000a90c  lea     rcx, [rax+20h]
0x18000a910  neg     rax
0x18000a913  sbb     rsi, rsi
0x18000a916  and     rsi, rcx
0x18000a919  lea     rdi, [rbx+20h]
0x18000a91d  mov     rcx, rdi; SRWLock
0x18000a920  call    cs:__imp_AcquireSRWLockExclusive
0x18000a926  cmp     qword ptr [rbx+18h], 0
0x18000a92b  jnz     short loc_18000A931
0x18000a92d  mov     [rbx+18h], rsi
0x18000a931  test    rdi, rdi
0x18000a934  jz      short loc_18000A93F
0x18000a936  mov     rcx, rdi; SRWLock
0x18000a939  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a93f  mov     ecx, ebp; dwErrCode
0x18000a941  call    cs:__imp_SetLastError
0x18000a947  cmp     qword ptr [rbx+18h], 0
0x18000a94c  setnz   al
0x18000a94f  add     rsp, 28h
0x18000a953  pop     rdi
0x18000a954  pop     rsi
0x18000a955  pop     rbp
0x18000a956  pop     rbx
0x18000a957  retn
```
