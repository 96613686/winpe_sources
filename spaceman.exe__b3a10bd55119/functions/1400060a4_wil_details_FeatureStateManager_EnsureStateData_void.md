# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400060a4`
- end: `0x140006150`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400043b0`
- `0x140007bb4`
- `0x1400095bc`
- `0x140009b30`

## callees

- `0x140005850`
- `0x1400060a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006139`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006131`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006118`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006118`

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
0x1400060a4  push    rbx
0x1400060a6  push    rbp
0x1400060a7  push    rsi
0x1400060a8  push    rdi
0x1400060a9  sub     rsp, 28h
0x1400060ad  cmp     qword ptr [rcx+18h], 0
0x1400060b2  mov     rbx, rcx
0x1400060b5  jnz     loc_14000613F
0x1400060bb  call    cs:__imp_GetLastError
0x1400060c1  cmp     qword ptr [rbx+18h], 0
0x1400060c6  mov     ebp, eax
0x1400060c8  jz      short loc_1400060CE
0x1400060ca  xor     esi, esi
0x1400060cc  jmp     short loc_140006111
0x1400060ce  cmp     qword ptr [rbx+10h], 0
0x1400060d3  jnz     short loc_140006100
0x1400060d5  mov     rcx, [rbx+8]
0x1400060d9  lea     rdx, [rsp+48h+arg_0]
0x1400060de  mov     [rsp+48h+arg_0], 0
0x1400060e7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400060ec  test    eax, eax
0x1400060ee  js      short loc_140006100
0x1400060f0  cmp     qword ptr [rbx+10h], 0
0x1400060f5  jnz     short loc_140006100
0x1400060f7  mov     rax, [rsp+48h+arg_0]
0x1400060fc  mov     [rbx+10h], rax
0x140006100  mov     rax, [rbx+10h]
0x140006104  lea     rcx, [rax+20h]
0x140006108  neg     rax
0x14000610b  sbb     rsi, rsi
0x14000610e  and     rsi, rcx
0x140006111  lea     rdi, [rbx+20h]
0x140006115  mov     rcx, rdi; SRWLock
0x140006118  call    cs:__imp_AcquireSRWLockExclusive
0x14000611e  cmp     qword ptr [rbx+18h], 0
0x140006123  jnz     short loc_140006129
0x140006125  mov     [rbx+18h], rsi
0x140006129  test    rdi, rdi
0x14000612c  jz      short loc_140006137
0x14000612e  mov     rcx, rdi; SRWLock
0x140006131  call    cs:__imp_ReleaseSRWLockExclusive
0x140006137  mov     ecx, ebp; dwErrCode
0x140006139  call    cs:__imp_SetLastError
0x14000613f  cmp     qword ptr [rbx+18h], 0
0x140006144  setnz   al
0x140006147  add     rsp, 28h
0x14000614b  pop     rdi
0x14000614c  pop     rsi
0x14000614d  pop     rbp
0x14000614e  pop     rbx
0x14000614f  retn
```
