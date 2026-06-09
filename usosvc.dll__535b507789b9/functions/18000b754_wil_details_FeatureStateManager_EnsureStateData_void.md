# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000b754`
- end: `0x18000b800`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ab10`
- `0x18000c7d0`
- `0x18000d8dc`
- `0x18000dc00`

## callees

- `0x18000b35c`
- `0x18000b754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b7e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b7e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b76b`

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
0x18000b754  push    rbx
0x18000b756  push    rbp
0x18000b757  push    rsi
0x18000b758  push    rdi
0x18000b759  sub     rsp, 28h
0x18000b75d  cmp     qword ptr [rcx+18h], 0
0x18000b762  mov     rbx, rcx
0x18000b765  jnz     loc_18000B7EF
0x18000b76b  call    cs:__imp_GetLastError
0x18000b771  cmp     qword ptr [rbx+18h], 0
0x18000b776  mov     ebp, eax
0x18000b778  jz      short loc_18000B77E
0x18000b77a  xor     esi, esi
0x18000b77c  jmp     short loc_18000B7C1
0x18000b77e  cmp     qword ptr [rbx+10h], 0
0x18000b783  jnz     short loc_18000B7B0
0x18000b785  mov     rcx, [rbx+8]
0x18000b789  lea     rdx, [rsp+48h+arg_0]
0x18000b78e  mov     [rsp+48h+arg_0], 0
0x18000b797  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000b79c  test    eax, eax
0x18000b79e  js      short loc_18000B7B0
0x18000b7a0  cmp     qword ptr [rbx+10h], 0
0x18000b7a5  jnz     short loc_18000B7B0
0x18000b7a7  mov     rax, [rsp+48h+arg_0]
0x18000b7ac  mov     [rbx+10h], rax
0x18000b7b0  mov     rax, [rbx+10h]
0x18000b7b4  lea     rcx, [rax+20h]
0x18000b7b8  neg     rax
0x18000b7bb  sbb     rsi, rsi
0x18000b7be  and     rsi, rcx
0x18000b7c1  lea     rdi, [rbx+20h]
0x18000b7c5  mov     rcx, rdi; SRWLock
0x18000b7c8  call    cs:__imp_AcquireSRWLockExclusive
0x18000b7ce  cmp     qword ptr [rbx+18h], 0
0x18000b7d3  jnz     short loc_18000B7D9
0x18000b7d5  mov     [rbx+18h], rsi
0x18000b7d9  test    rdi, rdi
0x18000b7dc  jz      short loc_18000B7E7
0x18000b7de  mov     rcx, rdi; SRWLock
0x18000b7e1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b7e7  mov     ecx, ebp; dwErrCode
0x18000b7e9  call    cs:__imp_SetLastError
0x18000b7ef  cmp     qword ptr [rbx+18h], 0
0x18000b7f4  setnz   al
0x18000b7f7  add     rsp, 28h
0x18000b7fb  pop     rdi
0x18000b7fc  pop     rsi
0x18000b7fd  pop     rbp
0x18000b7fe  pop     rbx
0x18000b7ff  retn
```
