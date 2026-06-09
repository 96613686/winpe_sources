# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800111d4`
- end: `0x180011280`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f710`
- `0x180012ce4`
- `0x180013f30`
- `0x1800144b0`

## callees

- `0x180010b30`
- `0x1800111d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800111eb`
- `KERNEL32!GetLastError` at `0x1800111eb`
- `KERNEL32!SetLastError` at `0x180011269`
- `KERNEL32!SetLastError` at `0x180011269`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011261`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011261`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011248`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011248`

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
0x1800111d4  push    rbx
0x1800111d6  push    rbp
0x1800111d7  push    rsi
0x1800111d8  push    rdi
0x1800111d9  sub     rsp, 28h
0x1800111dd  cmp     qword ptr [rcx+18h], 0
0x1800111e2  mov     rbx, rcx
0x1800111e5  jnz     loc_18001126F
0x1800111eb  call    cs:__imp_GetLastError
0x1800111f1  cmp     qword ptr [rbx+18h], 0
0x1800111f6  mov     ebp, eax
0x1800111f8  jz      short loc_1800111FE
0x1800111fa  xor     esi, esi
0x1800111fc  jmp     short loc_180011241
0x1800111fe  cmp     qword ptr [rbx+10h], 0
0x180011203  jnz     short loc_180011230
0x180011205  mov     rcx, [rbx+8]
0x180011209  lea     rdx, [rsp+48h+arg_0]
0x18001120e  mov     [rsp+48h+arg_0], 0
0x180011217  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18001121c  test    eax, eax
0x18001121e  js      short loc_180011230
0x180011220  cmp     qword ptr [rbx+10h], 0
0x180011225  jnz     short loc_180011230
0x180011227  mov     rax, [rsp+48h+arg_0]
0x18001122c  mov     [rbx+10h], rax
0x180011230  mov     rax, [rbx+10h]
0x180011234  lea     rcx, [rax+20h]
0x180011238  neg     rax
0x18001123b  sbb     rsi, rsi
0x18001123e  and     rsi, rcx
0x180011241  lea     rdi, [rbx+20h]
0x180011245  mov     rcx, rdi; SRWLock
0x180011248  call    cs:__imp_AcquireSRWLockExclusive
0x18001124e  cmp     qword ptr [rbx+18h], 0
0x180011253  jnz     short loc_180011259
0x180011255  mov     [rbx+18h], rsi
0x180011259  test    rdi, rdi
0x18001125c  jz      short loc_180011267
0x18001125e  mov     rcx, rdi; SRWLock
0x180011261  call    cs:__imp_ReleaseSRWLockExclusive
0x180011267  mov     ecx, ebp; dwErrCode
0x180011269  call    cs:__imp_SetLastError
0x18001126f  cmp     qword ptr [rbx+18h], 0
0x180011274  setnz   al
0x180011277  add     rsp, 28h
0x18001127b  pop     rdi
0x18001127c  pop     rsi
0x18001127d  pop     rbp
0x18001127e  pop     rbx
0x18001127f  retn
```
