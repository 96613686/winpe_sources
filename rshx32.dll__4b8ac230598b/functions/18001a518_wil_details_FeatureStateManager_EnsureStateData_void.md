# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18001a518`
- end: `0x18001a5c4`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800199d0`
- `0x18001b53c`
- `0x18001c604`
- `0x18001c980`

## callees

- `0x18001a148`
- `0x18001a518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a5a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a5a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a58c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a58c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a5ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a5ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a52f`

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
0x18001a518  push    rbx
0x18001a51a  push    rbp
0x18001a51b  push    rsi
0x18001a51c  push    rdi
0x18001a51d  sub     rsp, 28h
0x18001a521  cmp     qword ptr [rcx+18h], 0
0x18001a526  mov     rbx, rcx
0x18001a529  jnz     loc_18001A5B3
0x18001a52f  call    cs:__imp_GetLastError
0x18001a535  cmp     qword ptr [rbx+18h], 0
0x18001a53a  mov     ebp, eax
0x18001a53c  jz      short loc_18001A542
0x18001a53e  xor     esi, esi
0x18001a540  jmp     short loc_18001A585
0x18001a542  cmp     qword ptr [rbx+10h], 0
0x18001a547  jnz     short loc_18001A574
0x18001a549  mov     rcx, [rbx+8]
0x18001a54d  lea     rdx, [rsp+48h+arg_0]
0x18001a552  mov     [rsp+48h+arg_0], 0
0x18001a55b  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18001a560  test    eax, eax
0x18001a562  js      short loc_18001A574
0x18001a564  cmp     qword ptr [rbx+10h], 0
0x18001a569  jnz     short loc_18001A574
0x18001a56b  mov     rax, [rsp+48h+arg_0]
0x18001a570  mov     [rbx+10h], rax
0x18001a574  mov     rax, [rbx+10h]
0x18001a578  lea     rcx, [rax+20h]
0x18001a57c  neg     rax
0x18001a57f  sbb     rsi, rsi
0x18001a582  and     rsi, rcx
0x18001a585  lea     rdi, [rbx+20h]
0x18001a589  mov     rcx, rdi; SRWLock
0x18001a58c  call    cs:__imp_AcquireSRWLockExclusive
0x18001a592  cmp     qword ptr [rbx+18h], 0
0x18001a597  jnz     short loc_18001A59D
0x18001a599  mov     [rbx+18h], rsi
0x18001a59d  test    rdi, rdi
0x18001a5a0  jz      short loc_18001A5AB
0x18001a5a2  mov     rcx, rdi; SRWLock
0x18001a5a5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a5ab  mov     ecx, ebp; dwErrCode
0x18001a5ad  call    cs:__imp_SetLastError
0x18001a5b3  cmp     qword ptr [rbx+18h], 0
0x18001a5b8  setnz   al
0x18001a5bb  add     rsp, 28h
0x18001a5bf  pop     rdi
0x18001a5c0  pop     rsi
0x18001a5c1  pop     rbp
0x18001a5c2  pop     rbx
0x18001a5c3  retn
```
