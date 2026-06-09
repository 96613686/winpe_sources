# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d608`
- end: `0x18000d6cc`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d1f0`

## callees

- `0x18000c42c`
- `0x18000d608`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d662`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x18000d608  mov     [rsp+arg_0], rbx
0x18000d60d  push    rdi
0x18000d60e  sub     rsp, 20h
0x18000d612  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d619  xor     ebx, ebx
0x18000d61b  test    rdi, rdi
0x18000d61e  jz      loc_18000D6BD
0x18000d624  cmp     [rdi+8], rbx
0x18000d628  jnz     short loc_18000D64F
0x18000d62a  mov     rcx, [rdi]
0x18000d62d  lea     rdx, [rsp+28h+arg_8]
0x18000d632  mov     [rsp+28h+arg_8], rbx
0x18000d637  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d63c  test    eax, eax
0x18000d63e  js      short loc_18000D64F
0x18000d640  cmp     [rdi+8], rbx
0x18000d644  jnz     short loc_18000D64F
0x18000d646  mov     rax, [rsp+28h+arg_8]
0x18000d64b  mov     [rdi+8], rax
0x18000d64f  mov     rax, [rdi+8]
0x18000d653  lea     rcx, [rax+20h]
0x18000d657  neg     rax
0x18000d65a  sbb     rdi, rdi
0x18000d65d  and     rdi, rcx
0x18000d660  jz      short loc_18000D6BD
0x18000d662  call    cs:__imp_GetCurrentThreadId
0x18000d669  nop     dword ptr [rax+rax+00h]
0x18000d66e  mov     r8d, eax
0x18000d671  mov     r9d, eax
0x18000d674  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d67e  shr     r8, 2
0x18000d682  mul     r8
0x18000d685  shr     rdx, 3
0x18000d689  lea     rcx, [rdx+rdx*4]
0x18000d68d  add     rcx, rcx
0x18000d690  sub     r8, rcx
0x18000d693  mov     rbx, [rdi+r8*8+8]
0x18000d698  test    rbx, rbx
0x18000d69b  jz      short loc_18000D6BD
0x18000d69d  cmp     [rbx], r9d
0x18000d6a0  jz      short loc_18000D6A8
0x18000d6a2  mov     rbx, [rbx+8]
0x18000d6a6  jmp     short loc_18000D698
0x18000d6a8  add     rbx, 10h
0x18000d6ac  jz      short loc_18000D6BD
0x18000d6ae  cmp     qword ptr [rbx+8], 0
0x18000d6b3  jnz     short loc_18000D6BD
0x18000d6b5  lea     rax, [rdi+4]
0x18000d6b9  mov     [rbx+8], rax
0x18000d6bd  mov     rax, rbx
0x18000d6c0  mov     rbx, [rsp+28h+arg_0]
0x18000d6c5  add     rsp, 20h
0x18000d6c9  pop     rdi
0x18000d6ca  retn
```
