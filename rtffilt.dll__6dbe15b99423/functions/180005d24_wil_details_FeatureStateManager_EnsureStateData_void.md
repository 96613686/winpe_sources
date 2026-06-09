# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180005d24`
- end: `0x180005dd0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ce0`
- `0x180008614`
- `0x18000b4e4`
- `0x18000bf70`

## callees

- `0x180004f48`
- `0x180005d24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005db1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005db9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d3b`

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
0x180005d24  push    rbx
0x180005d26  push    rbp
0x180005d27  push    rsi
0x180005d28  push    rdi
0x180005d29  sub     rsp, 28h
0x180005d2d  cmp     qword ptr [rcx+18h], 0
0x180005d32  mov     rbx, rcx
0x180005d35  jnz     loc_180005DBF
0x180005d3b  call    cs:__imp_GetLastError
0x180005d41  cmp     qword ptr [rbx+18h], 0
0x180005d46  mov     ebp, eax
0x180005d48  jz      short loc_180005D4E
0x180005d4a  xor     esi, esi
0x180005d4c  jmp     short loc_180005D91
0x180005d4e  cmp     qword ptr [rbx+10h], 0
0x180005d53  jnz     short loc_180005D80
0x180005d55  mov     rcx, [rbx+8]
0x180005d59  lea     rdx, [rsp+48h+arg_0]
0x180005d5e  mov     [rsp+48h+arg_0], 0
0x180005d67  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180005d6c  test    eax, eax
0x180005d6e  js      short loc_180005D80
0x180005d70  cmp     qword ptr [rbx+10h], 0
0x180005d75  jnz     short loc_180005D80
0x180005d77  mov     rax, [rsp+48h+arg_0]
0x180005d7c  mov     [rbx+10h], rax
0x180005d80  mov     rax, [rbx+10h]
0x180005d84  lea     rcx, [rax+20h]
0x180005d88  neg     rax
0x180005d8b  sbb     rsi, rsi
0x180005d8e  and     rsi, rcx
0x180005d91  lea     rdi, [rbx+20h]
0x180005d95  mov     rcx, rdi; SRWLock
0x180005d98  call    cs:__imp_AcquireSRWLockExclusive
0x180005d9e  cmp     qword ptr [rbx+18h], 0
0x180005da3  jnz     short loc_180005DA9
0x180005da5  mov     [rbx+18h], rsi
0x180005da9  test    rdi, rdi
0x180005dac  jz      short loc_180005DB7
0x180005dae  mov     rcx, rdi; SRWLock
0x180005db1  call    cs:__imp_ReleaseSRWLockExclusive
0x180005db7  mov     ecx, ebp; dwErrCode
0x180005db9  call    cs:__imp_SetLastError
0x180005dbf  cmp     qword ptr [rbx+18h], 0
0x180005dc4  setnz   al
0x180005dc7  add     rsp, 28h
0x180005dcb  pop     rdi
0x180005dcc  pop     rsi
0x180005dcd  pop     rbp
0x180005dce  pop     rbx
0x180005dcf  retn
```
