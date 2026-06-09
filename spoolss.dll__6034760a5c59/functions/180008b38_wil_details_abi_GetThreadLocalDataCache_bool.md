# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008b38`
- end: `0x180008bf5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008320`

## callees

- `0x180007568`
- `0x180008b38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b92`

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
0x180008b38  mov     [rsp+arg_0], rbx
0x180008b3d  push    rdi
0x180008b3e  sub     rsp, 20h
0x180008b42  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008b49  xor     ebx, ebx
0x180008b4b  test    rdi, rdi
0x180008b4e  jz      loc_180008BE7
0x180008b54  cmp     [rdi+8], rbx
0x180008b58  jnz     short loc_180008B7F
0x180008b5a  mov     rcx, [rdi]
0x180008b5d  lea     rdx, [rsp+28h+arg_8]
0x180008b62  mov     [rsp+28h+arg_8], rbx
0x180008b67  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008b6c  test    eax, eax
0x180008b6e  js      short loc_180008B7F
0x180008b70  cmp     [rdi+8], rbx
0x180008b74  jnz     short loc_180008B7F
0x180008b76  mov     rax, [rsp+28h+arg_8]
0x180008b7b  mov     [rdi+8], rax
0x180008b7f  mov     rax, [rdi+8]
0x180008b83  lea     rcx, [rax+20h]
0x180008b87  neg     rax
0x180008b8a  sbb     rdi, rdi
0x180008b8d  and     rdi, rcx
0x180008b90  jz      short loc_180008BE7
0x180008b92  call    cs:__imp_GetCurrentThreadId
0x180008b98  mov     r8d, eax
0x180008b9b  mov     r9d, eax
0x180008b9e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008ba8  shr     r8, 2
0x180008bac  mul     r8
0x180008baf  shr     rdx, 3
0x180008bb3  lea     rcx, [rdx+rdx*4]
0x180008bb7  add     rcx, rcx
0x180008bba  sub     r8, rcx
0x180008bbd  mov     rbx, [rdi+r8*8+8]
0x180008bc2  test    rbx, rbx
0x180008bc5  jz      short loc_180008BE7
0x180008bc7  cmp     [rbx], r9d
0x180008bca  jz      short loc_180008BD2
0x180008bcc  mov     rbx, [rbx+8]
0x180008bd0  jmp     short loc_180008BC2
0x180008bd2  add     rbx, 10h
0x180008bd6  jz      short loc_180008BE7
0x180008bd8  cmp     qword ptr [rbx+8], 0
0x180008bdd  jnz     short loc_180008BE7
0x180008bdf  lea     rax, [rdi+4]
0x180008be3  mov     [rbx+8], rax
0x180008be7  mov     rax, rbx
0x180008bea  mov     rbx, [rsp+28h+arg_0]
0x180008bef  add     rsp, 20h
0x180008bf3  pop     rdi
0x180008bf4  retn
```
