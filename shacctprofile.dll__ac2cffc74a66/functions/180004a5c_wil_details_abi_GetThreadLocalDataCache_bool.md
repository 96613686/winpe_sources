# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004a5c`
- end: `0x180004b17`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004280`

## callees

- `0x180003bd0`
- `0x180004a5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ab2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ab2`

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
0x180004a5c  mov     [rsp+arg_0], rbx
0x180004a61  push    rdi
0x180004a62  sub     rsp, 20h
0x180004a66  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004a6d  xor     ebx, ebx
0x180004a6f  test    rdi, rdi
0x180004a72  jz      short loc_180004AF2
0x180004a74  cmp     [rdi+8], rbx
0x180004a78  jnz     short loc_180004A9F
0x180004a7a  mov     rcx, [rdi]
0x180004a7d  lea     rdx, [rsp+28h+arg_8]
0x180004a82  mov     [rsp+28h+arg_8], rbx
0x180004a87  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004a8c  test    eax, eax
0x180004a8e  js      short loc_180004A9F
0x180004a90  cmp     [rdi+8], rbx
0x180004a94  jnz     short loc_180004A9F
0x180004a96  mov     rax, [rsp+28h+arg_8]
0x180004a9b  mov     [rdi+8], rax
0x180004a9f  mov     rax, [rdi+8]
0x180004aa3  lea     rcx, [rax+20h]
0x180004aa7  neg     rax
0x180004aaa  sbb     rdi, rdi
0x180004aad  and     rdi, rcx
0x180004ab0  jz      short loc_180004AF2
0x180004ab2  call    cs:__imp_GetCurrentThreadId
0x180004ab8  mov     r8d, eax
0x180004abb  mov     r9d, eax
0x180004abe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004ac8  shr     r8, 2
0x180004acc  mul     r8
0x180004acf  shr     rdx, 3
0x180004ad3  lea     rcx, [rdx+rdx*4]
0x180004ad7  add     rcx, rcx
0x180004ada  sub     r8, rcx
0x180004add  mov     rbx, [rdi+r8*8+8]
0x180004ae2  jmp     short loc_180004AED
0x180004ae4  cmp     [rbx], r9d
0x180004ae7  jz      short loc_180004B00
0x180004ae9  mov     rbx, [rbx+8]
0x180004aed  test    rbx, rbx
0x180004af0  jnz     short loc_180004AE4
0x180004af2  mov     rax, rbx
0x180004af5  mov     rbx, [rsp+28h+arg_0]
0x180004afa  add     rsp, 20h
0x180004afe  pop     rdi
0x180004aff  retn
0x180004b00  add     rbx, 10h
0x180004b04  jz      short loc_180004AF2
0x180004b06  cmp     qword ptr [rbx+8], 0
0x180004b0b  jnz     short loc_180004AF2
0x180004b0d  lea     rax, [rdi+4]
0x180004b11  mov     [rbx+8], rax
0x180004b15  jmp     short loc_180004AF2
```
