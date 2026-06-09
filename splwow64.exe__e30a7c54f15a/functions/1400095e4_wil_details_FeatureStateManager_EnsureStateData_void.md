# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400095e4`
- end: `0x140009690`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400089a0`
- `0x14000a880`
- `0x14000babc`
- `0x14000be50`

## callees

- `0x140009214`
- `0x1400095e4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140009679`
- `KERNEL32!SetLastError` at `0x140009679`
- `KERNEL32!GetLastError` at `0x1400095fb`
- `KERNEL32!GetLastError` at `0x1400095fb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009658`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009658`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009671`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009671`

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
0x1400095e4  push    rbx
0x1400095e6  push    rbp
0x1400095e7  push    rsi
0x1400095e8  push    rdi
0x1400095e9  sub     rsp, 28h
0x1400095ed  cmp     qword ptr [rcx+18h], 0
0x1400095f2  mov     rbx, rcx
0x1400095f5  jnz     loc_14000967F
0x1400095fb  call    cs:__imp_GetLastError
0x140009601  cmp     qword ptr [rbx+18h], 0
0x140009606  mov     ebp, eax
0x140009608  jz      short loc_14000960E
0x14000960a  xor     esi, esi
0x14000960c  jmp     short loc_140009651
0x14000960e  cmp     qword ptr [rbx+10h], 0
0x140009613  jnz     short loc_140009640
0x140009615  mov     rcx, [rbx+8]
0x140009619  lea     rdx, [rsp+48h+arg_0]
0x14000961e  mov     [rsp+48h+arg_0], 0
0x140009627  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x14000962c  test    eax, eax
0x14000962e  js      short loc_140009640
0x140009630  cmp     qword ptr [rbx+10h], 0
0x140009635  jnz     short loc_140009640
0x140009637  mov     rax, [rsp+48h+arg_0]
0x14000963c  mov     [rbx+10h], rax
0x140009640  mov     rax, [rbx+10h]
0x140009644  lea     rcx, [rax+20h]
0x140009648  neg     rax
0x14000964b  sbb     rsi, rsi
0x14000964e  and     rsi, rcx
0x140009651  lea     rdi, [rbx+20h]
0x140009655  mov     rcx, rdi; SRWLock
0x140009658  call    cs:__imp_AcquireSRWLockExclusive
0x14000965e  cmp     qword ptr [rbx+18h], 0
0x140009663  jnz     short loc_140009669
0x140009665  mov     [rbx+18h], rsi
0x140009669  test    rdi, rdi
0x14000966c  jz      short loc_140009677
0x14000966e  mov     rcx, rdi; SRWLock
0x140009671  call    cs:__imp_ReleaseSRWLockExclusive
0x140009677  mov     ecx, ebp; dwErrCode
0x140009679  call    cs:__imp_SetLastError
0x14000967f  cmp     qword ptr [rbx+18h], 0
0x140009684  setnz   al
0x140009687  add     rsp, 28h
0x14000968b  pop     rdi
0x14000968c  pop     rsi
0x14000968d  pop     rbp
0x14000968e  pop     rbx
0x14000968f  retn
```
