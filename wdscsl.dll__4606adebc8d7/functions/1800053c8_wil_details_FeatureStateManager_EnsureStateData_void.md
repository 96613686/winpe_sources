# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800053c8`
- end: `0x1800054a1`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `217`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027f0`
- `0x180008a34`
- `0x18000ad58`
- `0x18000b3e0`

## callees

- `0x180003f2c`
- `0x1800053c8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005477`
- `KERNEL32!SetLastError` at `0x180005477`
- `KERNEL32!GetLastError` at `0x1800053ea`
- `KERNEL32!GetLastError` at `0x1800053ea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005469`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005469`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000544a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000544a`

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
0x1800053c8  mov     [rsp+arg_8], rbx
0x1800053cd  mov     [rsp+arg_10], rbp
0x1800053d2  mov     [rsp+arg_18], rsi
0x1800053d7  push    rdi
0x1800053d8  sub     rsp, 20h
0x1800053dc  cmp     qword ptr [rcx+18h], 0
0x1800053e1  mov     rbx, rcx
0x1800053e4  jnz     loc_180005483
0x1800053ea  call    cs:__imp_GetLastError
0x1800053f1  nop     dword ptr [rax+rax+00h]
0x1800053f6  cmp     qword ptr [rbx+18h], 0
0x1800053fb  mov     ebp, eax
0x1800053fd  jz      short loc_180005403
0x1800053ff  xor     edi, edi
0x180005401  jmp     short loc_180005443
0x180005403  cmp     qword ptr [rbx+10h], 0
0x180005408  jnz     short loc_180005432
0x18000540a  mov     rcx, [rbx+8]
0x18000540e  lea     rdx, [rsp+28h+arg_0]
0x180005413  and     [rsp+28h+arg_0], 0
0x180005419  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000541e  test    eax, eax
0x180005420  js      short loc_180005432
0x180005422  cmp     qword ptr [rbx+10h], 0
0x180005427  jnz     short loc_180005432
0x180005429  mov     rax, [rsp+28h+arg_0]
0x18000542e  mov     [rbx+10h], rax
0x180005432  mov     rax, [rbx+10h]
0x180005436  lea     rcx, [rax+20h]
0x18000543a  neg     rax
0x18000543d  sbb     rdi, rdi
0x180005440  and     rdi, rcx
0x180005443  lea     rsi, [rbx+20h]
0x180005447  mov     rcx, rsi; SRWLock
0x18000544a  call    cs:__imp_AcquireSRWLockExclusive
0x180005451  nop     dword ptr [rax+rax+00h]
0x180005456  cmp     qword ptr [rbx+18h], 0
0x18000545b  jnz     short loc_180005461
0x18000545d  mov     [rbx+18h], rdi
0x180005461  test    rsi, rsi
0x180005464  jz      short loc_180005475
0x180005466  mov     rcx, rsi; SRWLock
0x180005469  call    cs:__imp_ReleaseSRWLockExclusive
0x180005470  nop     dword ptr [rax+rax+00h]
0x180005475  mov     ecx, ebp; dwErrCode
0x180005477  call    cs:__imp_SetLastError
0x18000547e  nop     dword ptr [rax+rax+00h]
0x180005483  cmp     qword ptr [rbx+18h], 0
0x180005488  mov     rbx, [rsp+28h+arg_8]
0x18000548d  mov     rbp, [rsp+28h+arg_10]
0x180005492  setnz   al
0x180005495  mov     rsi, [rsp+28h+arg_18]
0x18000549a  add     rsp, 20h
0x18000549e  pop     rdi
0x18000549f  retn
```
