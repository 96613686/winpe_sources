# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180024b38`
- end: `0x180024bf5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024310`

## callees

- `0x1800235d0`
- `0x180024b38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024b92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024b92`

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
0x180024b38  mov     [rsp+arg_0], rbx
0x180024b3d  push    rdi
0x180024b3e  sub     rsp, 20h
0x180024b42  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180024b49  xor     ebx, ebx
0x180024b4b  test    rdi, rdi
0x180024b4e  jz      loc_180024BE7
0x180024b54  cmp     [rdi+8], rbx
0x180024b58  jnz     short loc_180024B7F
0x180024b5a  mov     rcx, [rdi]
0x180024b5d  lea     rdx, [rsp+28h+arg_8]
0x180024b62  mov     [rsp+28h+arg_8], rbx
0x180024b67  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180024b6c  test    eax, eax
0x180024b6e  js      short loc_180024B7F
0x180024b70  cmp     [rdi+8], rbx
0x180024b74  jnz     short loc_180024B7F
0x180024b76  mov     rax, [rsp+28h+arg_8]
0x180024b7b  mov     [rdi+8], rax
0x180024b7f  mov     rax, [rdi+8]
0x180024b83  lea     rcx, [rax+20h]
0x180024b87  neg     rax
0x180024b8a  sbb     rdi, rdi
0x180024b8d  and     rdi, rcx
0x180024b90  jz      short loc_180024BE7
0x180024b92  call    cs:__imp_GetCurrentThreadId
0x180024b98  mov     r8d, eax
0x180024b9b  mov     r9d, eax
0x180024b9e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180024ba8  shr     r8, 2
0x180024bac  mul     r8
0x180024baf  shr     rdx, 3
0x180024bb3  lea     rcx, [rdx+rdx*4]
0x180024bb7  add     rcx, rcx
0x180024bba  sub     r8, rcx
0x180024bbd  mov     rbx, [rdi+r8*8+8]
0x180024bc2  test    rbx, rbx
0x180024bc5  jz      short loc_180024BE7
0x180024bc7  cmp     [rbx], r9d
0x180024bca  jz      short loc_180024BD2
0x180024bcc  mov     rbx, [rbx+8]
0x180024bd0  jmp     short loc_180024BC2
0x180024bd2  add     rbx, 10h
0x180024bd6  jz      short loc_180024BE7
0x180024bd8  cmp     qword ptr [rbx+8], 0
0x180024bdd  jnz     short loc_180024BE7
0x180024bdf  lea     rax, [rdi+4]
0x180024be3  mov     [rbx+8], rax
0x180024be7  mov     rax, rbx
0x180024bea  mov     rbx, [rsp+28h+arg_0]
0x180024bef  add     rsp, 20h
0x180024bf3  pop     rdi
0x180024bf4  retn
```
