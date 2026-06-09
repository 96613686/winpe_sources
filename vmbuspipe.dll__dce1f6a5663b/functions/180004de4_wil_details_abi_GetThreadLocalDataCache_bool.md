# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004de4`
- end: `0x180004ea1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004540`

## callees

- `0x180001980`
- `0x180004de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e3e`

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
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
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
0x180004de4  mov     [rsp+arg_0], rbx
0x180004de9  push    rdi
0x180004dea  sub     rsp, 20h
0x180004dee  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004df5  xor     ebx, ebx
0x180004df7  test    rdi, rdi
0x180004dfa  jz      loc_180004E93
0x180004e00  cmp     [rdi+8], rbx
0x180004e04  jnz     short loc_180004E2B
0x180004e06  mov     rcx, [rdi]
0x180004e09  lea     rdx, [rsp+28h+arg_8]
0x180004e0e  mov     [rsp+28h+arg_8], rbx
0x180004e13  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004e18  test    eax, eax
0x180004e1a  js      short loc_180004E2B
0x180004e1c  cmp     [rdi+8], rbx
0x180004e20  jnz     short loc_180004E2B
0x180004e22  mov     rax, [rsp+28h+arg_8]
0x180004e27  mov     [rdi+8], rax
0x180004e2b  mov     rax, [rdi+8]
0x180004e2f  lea     rcx, [rax+20h]
0x180004e33  neg     rax
0x180004e36  sbb     rdi, rdi
0x180004e39  and     rdi, rcx
0x180004e3c  jz      short loc_180004E93
0x180004e3e  call    cs:__imp_GetCurrentThreadId
0x180004e44  mov     r8d, eax
0x180004e47  mov     r9d, eax
0x180004e4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004e54  shr     r8, 2
0x180004e58  mul     r8
0x180004e5b  shr     rdx, 3
0x180004e5f  lea     rcx, [rdx+rdx*4]
0x180004e63  add     rcx, rcx
0x180004e66  sub     r8, rcx
0x180004e69  mov     rbx, [rdi+r8*8+8]
0x180004e6e  test    rbx, rbx
0x180004e71  jz      short loc_180004E93
0x180004e73  cmp     [rbx], r9d
0x180004e76  jz      short loc_180004E7E
0x180004e78  mov     rbx, [rbx+8]
0x180004e7c  jmp     short loc_180004E6E
0x180004e7e  add     rbx, 10h
0x180004e82  jz      short loc_180004E93
0x180004e84  cmp     qword ptr [rbx+8], 0
0x180004e89  jnz     short loc_180004E93
0x180004e8b  lea     rax, [rdi+4]
0x180004e8f  mov     [rbx+8], rax
0x180004e93  mov     rax, rbx
0x180004e96  mov     rbx, [rsp+28h+arg_0]
0x180004e9b  add     rsp, 20h
0x180004e9f  pop     rdi
0x180004ea0  retn
```
