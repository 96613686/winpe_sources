# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400067f0`
- end: `0x14000689c`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b00`
- `0x14000954c`
- `0x14000ad3c`
- `0x14000bce0`

## callees

- `0x14000539c`
- `0x1400067f0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140006864`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006864`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000687d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000687d`
- `KERNEL32!GetLastError` at `0x140006807`
- `KERNEL32!GetLastError` at `0x140006807`
- `KERNEL32!SetLastError` at `0x140006885`
- `KERNEL32!SetLastError` at `0x140006885`

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
0x1400067f0  push    rbx
0x1400067f2  push    rbp
0x1400067f3  push    rsi
0x1400067f4  push    rdi
0x1400067f5  sub     rsp, 28h
0x1400067f9  cmp     qword ptr [rcx+18h], 0
0x1400067fe  mov     rbx, rcx
0x140006801  jnz     loc_14000688B
0x140006807  call    cs:__imp_GetLastError
0x14000680d  cmp     qword ptr [rbx+18h], 0
0x140006812  mov     ebp, eax
0x140006814  jz      short loc_14000681A
0x140006816  xor     esi, esi
0x140006818  jmp     short loc_14000685D
0x14000681a  cmp     qword ptr [rbx+10h], 0
0x14000681f  jnz     short loc_14000684C
0x140006821  mov     rcx, [rbx+8]
0x140006825  lea     rdx, [rsp+48h+arg_0]
0x14000682a  mov     [rsp+48h+arg_0], 0
0x140006833  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140006838  test    eax, eax
0x14000683a  js      short loc_14000684C
0x14000683c  cmp     qword ptr [rbx+10h], 0
0x140006841  jnz     short loc_14000684C
0x140006843  mov     rax, [rsp+48h+arg_0]
0x140006848  mov     [rbx+10h], rax
0x14000684c  mov     rax, [rbx+10h]
0x140006850  lea     rcx, [rax+20h]
0x140006854  neg     rax
0x140006857  sbb     rsi, rsi
0x14000685a  and     rsi, rcx
0x14000685d  lea     rdi, [rbx+20h]
0x140006861  mov     rcx, rdi; SRWLock
0x140006864  call    cs:__imp_AcquireSRWLockExclusive
0x14000686a  cmp     qword ptr [rbx+18h], 0
0x14000686f  jnz     short loc_140006875
0x140006871  mov     [rbx+18h], rsi
0x140006875  test    rdi, rdi
0x140006878  jz      short loc_140006883
0x14000687a  mov     rcx, rdi; SRWLock
0x14000687d  call    cs:__imp_ReleaseSRWLockExclusive
0x140006883  mov     ecx, ebp; dwErrCode
0x140006885  call    cs:__imp_SetLastError
0x14000688b  cmp     qword ptr [rbx+18h], 0
0x140006890  setnz   al
0x140006893  add     rsp, 28h
0x140006897  pop     rdi
0x140006898  pop     rsi
0x140006899  pop     rbp
0x14000689a  pop     rbx
0x14000689b  retn
```
