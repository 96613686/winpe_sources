# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000b0d8`
- end: `0x18000b1b1`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `217`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800090b0`
- `0x18000d514`
- `0x18000fe70`
- `0x180010600`

## callees

- `0x18000a5fc`
- `0x18000b0d8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b187`
- `KERNEL32!SetLastError` at `0x18000b187`
- `KERNEL32!GetLastError` at `0x18000b0fa`
- `KERNEL32!GetLastError` at `0x18000b0fa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b15a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b15a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b179`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b179`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rdi
  __int64 Ptr; // rcx
  void *v6; // [rsp+30h] [rbp+8h] BYREF

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
0x18000b0d8  mov     [rsp+arg_8], rbx
0x18000b0dd  mov     [rsp+arg_10], rbp
0x18000b0e2  mov     [rsp+arg_18], rsi
0x18000b0e7  push    rdi
0x18000b0e8  sub     rsp, 20h
0x18000b0ec  cmp     qword ptr [rcx+18h], 0
0x18000b0f1  mov     rbx, rcx
0x18000b0f4  jnz     loc_18000B193
0x18000b0fa  call    cs:__imp_GetLastError
0x18000b101  nop     dword ptr [rax+rax+00h]
0x18000b106  cmp     qword ptr [rbx+18h], 0
0x18000b10b  mov     ebp, eax
0x18000b10d  jz      short loc_18000B113
0x18000b10f  xor     edi, edi
0x18000b111  jmp     short loc_18000B153
0x18000b113  cmp     qword ptr [rbx+10h], 0
0x18000b118  jnz     short loc_18000B142
0x18000b11a  mov     rcx, [rbx+8]
0x18000b11e  lea     rdx, [rsp+28h+arg_0]
0x18000b123  and     [rsp+28h+arg_0], 0
0x18000b129  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000b12e  test    eax, eax
0x18000b130  js      short loc_18000B142
0x18000b132  cmp     qword ptr [rbx+10h], 0
0x18000b137  jnz     short loc_18000B142
0x18000b139  mov     rax, [rsp+28h+arg_0]
0x18000b13e  mov     [rbx+10h], rax
0x18000b142  mov     rax, [rbx+10h]
0x18000b146  lea     rcx, [rax+20h]
0x18000b14a  neg     rax
0x18000b14d  sbb     rdi, rdi
0x18000b150  and     rdi, rcx
0x18000b153  lea     rsi, [rbx+20h]
0x18000b157  mov     rcx, rsi; SRWLock
0x18000b15a  call    cs:__imp_AcquireSRWLockExclusive
0x18000b161  nop     dword ptr [rax+rax+00h]
0x18000b166  cmp     qword ptr [rbx+18h], 0
0x18000b16b  jnz     short loc_18000B171
0x18000b16d  mov     [rbx+18h], rdi
0x18000b171  test    rsi, rsi
0x18000b174  jz      short loc_18000B185
0x18000b176  mov     rcx, rsi; SRWLock
0x18000b179  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b180  nop     dword ptr [rax+rax+00h]
0x18000b185  mov     ecx, ebp; dwErrCode
0x18000b187  call    cs:__imp_SetLastError
0x18000b18e  nop     dword ptr [rax+rax+00h]
0x18000b193  cmp     qword ptr [rbx+18h], 0
0x18000b198  mov     rbx, [rsp+28h+arg_8]
0x18000b19d  mov     rbp, [rsp+28h+arg_10]
0x18000b1a2  setnz   al
0x18000b1a5  mov     rsi, [rsp+28h+arg_18]
0x18000b1aa  add     rsp, 20h
0x18000b1ae  pop     rdi
0x18000b1af  retn
```
