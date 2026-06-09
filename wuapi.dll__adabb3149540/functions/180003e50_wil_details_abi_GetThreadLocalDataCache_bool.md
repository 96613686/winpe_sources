# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003e50`
- end: `0x180003f07`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004010`

## callees

- `0x180003e50`
- `0x180004dfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ea6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ea6`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180003e50  mov     [rsp+arg_0], rbx
0x180003e55  push    rdi
0x180003e56  sub     rsp, 20h
0x180003e5a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003e61  xor     ebx, ebx
0x180003e63  test    rdi, rdi
0x180003e66  jz      short loc_180003EE2
0x180003e68  cmp     [rdi+8], rbx
0x180003e6c  jnz     short loc_180003E93
0x180003e6e  mov     rcx, [rdi]
0x180003e71  lea     rdx, [rsp+28h+arg_8]
0x180003e76  mov     [rsp+28h+arg_8], rbx
0x180003e7b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003e80  test    eax, eax
0x180003e82  js      short loc_180003E93
0x180003e84  cmp     [rdi+8], rbx
0x180003e88  jnz     short loc_180003E93
0x180003e8a  mov     rax, [rsp+28h+arg_8]
0x180003e8f  mov     [rdi+8], rax
0x180003e93  mov     rax, [rdi+8]
0x180003e97  lea     rcx, [rax+20h]
0x180003e9b  neg     rax
0x180003e9e  sbb     rdi, rdi
0x180003ea1  and     rdi, rcx
0x180003ea4  jz      short loc_180003EE2
0x180003ea6  call    cs:__imp_GetCurrentThreadId
0x180003eac  mov     r8d, eax
0x180003eaf  mov     r9d, eax
0x180003eb2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003ebc  mul     r9
0x180003ebf  shr     rdx, 3
0x180003ec3  lea     rcx, [rdx+rdx*4]
0x180003ec7  add     rcx, rcx
0x180003eca  sub     r8, rcx
0x180003ecd  mov     rbx, [rdi+r8*8+8]
0x180003ed2  jmp     short loc_180003EDD
0x180003ed4  cmp     [rbx], r9d
0x180003ed7  jz      short loc_180003EF0
0x180003ed9  mov     rbx, [rbx+8]
0x180003edd  test    rbx, rbx
0x180003ee0  jnz     short loc_180003ED4
0x180003ee2  mov     rax, rbx
0x180003ee5  mov     rbx, [rsp+28h+arg_0]
0x180003eea  add     rsp, 20h
0x180003eee  pop     rdi
0x180003eef  retn
0x180003ef0  add     rbx, 10h
0x180003ef4  jz      short loc_180003EE2
0x180003ef6  cmp     qword ptr [rbx+8], 0
0x180003efb  jnz     short loc_180003EE2
0x180003efd  lea     rax, [rdi+4]
0x180003f01  mov     [rbx+8], rax
0x180003f05  jmp     short loc_180003EE2
```
