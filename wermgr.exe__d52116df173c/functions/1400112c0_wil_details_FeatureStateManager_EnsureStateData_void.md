# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400112c0`
- end: `0x14001136c`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f850`
- `0x140012540`
- `0x140013e88`
- `0x1400144d0`

## callees

- `0x140010b80`
- `0x1400112c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011355`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011355`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001134d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001134d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011334`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011334`

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
0x1400112c0  push    rbx
0x1400112c2  push    rbp
0x1400112c3  push    rsi
0x1400112c4  push    rdi
0x1400112c5  sub     rsp, 28h
0x1400112c9  cmp     qword ptr [rcx+18h], 0
0x1400112ce  mov     rbx, rcx
0x1400112d1  jnz     loc_14001135B
0x1400112d7  call    cs:__imp_GetLastError
0x1400112dd  cmp     qword ptr [rbx+18h], 0
0x1400112e2  mov     ebp, eax
0x1400112e4  jz      short loc_1400112EA
0x1400112e6  xor     esi, esi
0x1400112e8  jmp     short loc_14001132D
0x1400112ea  cmp     qword ptr [rbx+10h], 0
0x1400112ef  jnz     short loc_14001131C
0x1400112f1  mov     rcx, [rbx+8]; int
0x1400112f5  lea     rdx, [rsp+48h+arg_0]
0x1400112fa  mov     [rsp+48h+arg_0], 0
0x140011303  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140011308  test    eax, eax
0x14001130a  js      short loc_14001131C
0x14001130c  cmp     qword ptr [rbx+10h], 0
0x140011311  jnz     short loc_14001131C
0x140011313  mov     rax, [rsp+48h+arg_0]
0x140011318  mov     [rbx+10h], rax
0x14001131c  mov     rax, [rbx+10h]
0x140011320  lea     rcx, [rax+20h]
0x140011324  neg     rax
0x140011327  sbb     rsi, rsi
0x14001132a  and     rsi, rcx
0x14001132d  lea     rdi, [rbx+20h]
0x140011331  mov     rcx, rdi; SRWLock
0x140011334  call    cs:__imp_AcquireSRWLockExclusive
0x14001133a  cmp     qword ptr [rbx+18h], 0
0x14001133f  jnz     short loc_140011345
0x140011341  mov     [rbx+18h], rsi
0x140011345  test    rdi, rdi
0x140011348  jz      short loc_140011353
0x14001134a  mov     rcx, rdi; SRWLock
0x14001134d  call    cs:__imp_ReleaseSRWLockExclusive
0x140011353  mov     ecx, ebp; dwErrCode
0x140011355  call    cs:__imp_SetLastError
0x14001135b  cmp     qword ptr [rbx+18h], 0
0x140011360  setnz   al
0x140011363  add     rsp, 28h
0x140011367  pop     rdi
0x140011368  pop     rsi
0x140011369  pop     rbp
0x14001136a  pop     rbx
0x14001136b  retn
```
