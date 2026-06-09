# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180008644`
- end: `0x18000871d`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `217`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006560`
- `0x18000b804`
- `0x18000dc10`
- `0x18000e4f0`

## callees

- `0x180007d44`
- `0x180008644`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800086f3`
- `KERNEL32!SetLastError` at `0x1800086f3`
- `KERNEL32!GetLastError` at `0x180008666`
- `KERNEL32!GetLastError` at `0x180008666`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800086c6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800086c6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800086e5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800086e5`

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
0x180008644  mov     [rsp+arg_8], rbx
0x180008649  mov     [rsp+arg_10], rbp
0x18000864e  mov     [rsp+arg_18], rsi
0x180008653  push    rdi
0x180008654  sub     rsp, 20h
0x180008658  cmp     qword ptr [rcx+18h], 0
0x18000865d  mov     rbx, rcx
0x180008660  jnz     loc_1800086FF
0x180008666  call    cs:__imp_GetLastError
0x18000866d  nop     dword ptr [rax+rax+00h]
0x180008672  cmp     qword ptr [rbx+18h], 0
0x180008677  mov     ebp, eax
0x180008679  jz      short loc_18000867F
0x18000867b  xor     edi, edi
0x18000867d  jmp     short loc_1800086BF
0x18000867f  cmp     qword ptr [rbx+10h], 0
0x180008684  jnz     short loc_1800086AE
0x180008686  mov     rcx, [rbx+8]
0x18000868a  lea     rdx, [rsp+28h+arg_0]
0x18000868f  and     [rsp+28h+arg_0], 0
0x180008695  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000869a  test    eax, eax
0x18000869c  js      short loc_1800086AE
0x18000869e  cmp     qword ptr [rbx+10h], 0
0x1800086a3  jnz     short loc_1800086AE
0x1800086a5  mov     rax, [rsp+28h+arg_0]
0x1800086aa  mov     [rbx+10h], rax
0x1800086ae  mov     rax, [rbx+10h]
0x1800086b2  lea     rcx, [rax+20h]
0x1800086b6  neg     rax
0x1800086b9  sbb     rdi, rdi
0x1800086bc  and     rdi, rcx
0x1800086bf  lea     rsi, [rbx+20h]
0x1800086c3  mov     rcx, rsi; SRWLock
0x1800086c6  call    cs:__imp_AcquireSRWLockExclusive
0x1800086cd  nop     dword ptr [rax+rax+00h]
0x1800086d2  cmp     qword ptr [rbx+18h], 0
0x1800086d7  jnz     short loc_1800086DD
0x1800086d9  mov     [rbx+18h], rdi
0x1800086dd  test    rsi, rsi
0x1800086e0  jz      short loc_1800086F1
0x1800086e2  mov     rcx, rsi; SRWLock
0x1800086e5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800086ec  nop     dword ptr [rax+rax+00h]
0x1800086f1  mov     ecx, ebp; dwErrCode
0x1800086f3  call    cs:__imp_SetLastError
0x1800086fa  nop     dword ptr [rax+rax+00h]
0x1800086ff  cmp     qword ptr [rbx+18h], 0
0x180008704  mov     rbx, [rsp+28h+arg_8]
0x180008709  mov     rbp, [rsp+28h+arg_10]
0x18000870e  setnz   al
0x180008711  mov     rsi, [rsp+28h+arg_18]
0x180008716  add     rsp, 20h
0x18000871a  pop     rdi
0x18000871b  retn
```
