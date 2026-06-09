# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000c344`
- end: `0x18000c3f0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a280`
- `0x18000def4`
- `0x18000f39c`
- `0x18000f970`

## callees

- `0x18000bb64`
- `0x18000c344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c35b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c35b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c3d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c3d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c3b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c3b8`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 Ptr; // rcx
  void *v6; // [rsp+20h] [rbp-38h] BYREF

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
0x18000c344  push    rbx
0x18000c346  push    rbp
0x18000c347  push    rsi
0x18000c348  push    rdi
0x18000c349  sub     rsp, 38h
0x18000c34d  cmp     qword ptr [rcx+18h], 0
0x18000c352  mov     rbx, rcx
0x18000c355  jnz     loc_18000C3DF
0x18000c35b  call    cs:__imp_GetLastError
0x18000c361  cmp     qword ptr [rbx+18h], 0
0x18000c366  mov     ebp, eax
0x18000c368  jz      short loc_18000C36E
0x18000c36a  xor     esi, esi
0x18000c36c  jmp     short loc_18000C3B1
0x18000c36e  cmp     qword ptr [rbx+10h], 0
0x18000c373  jnz     short loc_18000C3A0
0x18000c375  mov     rcx, [rbx+8]
0x18000c379  lea     rdx, [rsp+58h+var_38]
0x18000c37e  mov     [rsp+58h+var_38], 0
0x18000c387  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000c38c  test    eax, eax
0x18000c38e  js      short loc_18000C3A0
0x18000c390  cmp     qword ptr [rbx+10h], 0
0x18000c395  jnz     short loc_18000C3A0
0x18000c397  mov     rax, [rsp+58h+var_38]
0x18000c39c  mov     [rbx+10h], rax
0x18000c3a0  mov     rax, [rbx+10h]
0x18000c3a4  lea     rcx, [rax+20h]
0x18000c3a8  neg     rax
0x18000c3ab  sbb     rsi, rsi
0x18000c3ae  and     rsi, rcx
0x18000c3b1  lea     rdi, [rbx+20h]
0x18000c3b5  mov     rcx, rdi; SRWLock
0x18000c3b8  call    cs:__imp_AcquireSRWLockExclusive
0x18000c3be  cmp     qword ptr [rbx+18h], 0
0x18000c3c3  jnz     short loc_18000C3C9
0x18000c3c5  mov     [rbx+18h], rsi
0x18000c3c9  test    rdi, rdi
0x18000c3cc  jz      short loc_18000C3D7
0x18000c3ce  mov     rcx, rdi; SRWLock
0x18000c3d1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c3d7  mov     ecx, ebp; dwErrCode
0x18000c3d9  call    cs:__imp_SetLastError
0x18000c3df  cmp     qword ptr [rbx+18h], 0
0x18000c3e4  setnz   al
0x18000c3e7  add     rsp, 38h
0x18000c3eb  pop     rdi
0x18000c3ec  pop     rsi
0x18000c3ed  pop     rbp
0x18000c3ee  pop     rbx
0x18000c3ef  retn
```
