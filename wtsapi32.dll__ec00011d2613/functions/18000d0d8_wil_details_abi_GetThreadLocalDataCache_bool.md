# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d0d8`
- end: `0x18000d195`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ca60`

## callees

- `0x18000c584`
- `0x18000d0d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d132`

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
0x18000d0d8  mov     [rsp+arg_0], rbx
0x18000d0dd  push    rdi
0x18000d0de  sub     rsp, 20h
0x18000d0e2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d0e9  xor     ebx, ebx
0x18000d0eb  test    rdi, rdi
0x18000d0ee  jz      loc_18000D187
0x18000d0f4  cmp     [rdi+8], rbx
0x18000d0f8  jnz     short loc_18000D11F
0x18000d0fa  mov     rcx, [rdi]
0x18000d0fd  lea     rdx, [rsp+28h+arg_8]
0x18000d102  mov     [rsp+28h+arg_8], rbx
0x18000d107  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d10c  test    eax, eax
0x18000d10e  js      short loc_18000D11F
0x18000d110  cmp     [rdi+8], rbx
0x18000d114  jnz     short loc_18000D11F
0x18000d116  mov     rax, [rsp+28h+arg_8]
0x18000d11b  mov     [rdi+8], rax
0x18000d11f  mov     rax, [rdi+8]
0x18000d123  lea     rcx, [rax+20h]
0x18000d127  neg     rax
0x18000d12a  sbb     rdi, rdi
0x18000d12d  and     rdi, rcx
0x18000d130  jz      short loc_18000D187
0x18000d132  call    cs:__imp_GetCurrentThreadId
0x18000d138  mov     r8d, eax
0x18000d13b  mov     r9d, eax
0x18000d13e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d148  shr     r8, 2
0x18000d14c  mul     r8
0x18000d14f  shr     rdx, 3
0x18000d153  lea     rcx, [rdx+rdx*4]
0x18000d157  add     rcx, rcx
0x18000d15a  sub     r8, rcx
0x18000d15d  mov     rbx, [rdi+r8*8+8]
0x18000d162  test    rbx, rbx
0x18000d165  jz      short loc_18000D187
0x18000d167  cmp     [rbx], r9d
0x18000d16a  jz      short loc_18000D172
0x18000d16c  mov     rbx, [rbx+8]
0x18000d170  jmp     short loc_18000D162
0x18000d172  add     rbx, 10h
0x18000d176  jz      short loc_18000D187
0x18000d178  cmp     qword ptr [rbx+8], 0
0x18000d17d  jnz     short loc_18000D187
0x18000d17f  lea     rax, [rdi+4]
0x18000d183  mov     [rbx+8], rax
0x18000d187  mov     rax, rbx
0x18000d18a  mov     rbx, [rsp+28h+arg_0]
0x18000d18f  add     rsp, 20h
0x18000d193  pop     rdi
0x18000d194  retn
```
