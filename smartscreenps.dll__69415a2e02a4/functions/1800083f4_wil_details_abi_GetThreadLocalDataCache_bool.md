# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800083f4`
- end: `0x1800084b8`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d40`

## callees

- `0x18000781c`
- `0x1800083f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000844e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000844e`

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
0x1800083f4  mov     [rsp+arg_0], rbx
0x1800083f9  push    rdi
0x1800083fa  sub     rsp, 20h
0x1800083fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008405  xor     ebx, ebx
0x180008407  test    rdi, rdi
0x18000840a  jz      loc_1800084A9
0x180008410  cmp     [rdi+8], rbx
0x180008414  jnz     short loc_18000843B
0x180008416  mov     rcx, [rdi]
0x180008419  lea     rdx, [rsp+28h+arg_8]
0x18000841e  mov     [rsp+28h+arg_8], rbx
0x180008423  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008428  test    eax, eax
0x18000842a  js      short loc_18000843B
0x18000842c  cmp     [rdi+8], rbx
0x180008430  jnz     short loc_18000843B
0x180008432  mov     rax, [rsp+28h+arg_8]
0x180008437  mov     [rdi+8], rax
0x18000843b  mov     rax, [rdi+8]
0x18000843f  lea     rcx, [rax+20h]
0x180008443  neg     rax
0x180008446  sbb     rdi, rdi
0x180008449  and     rdi, rcx
0x18000844c  jz      short loc_1800084A9
0x18000844e  call    cs:__imp_GetCurrentThreadId
0x180008455  nop     dword ptr [rax+rax+00h]
0x18000845a  mov     r8d, eax
0x18000845d  mov     r9d, eax
0x180008460  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000846a  shr     r8, 2
0x18000846e  mul     r8
0x180008471  shr     rdx, 3
0x180008475  lea     rcx, [rdx+rdx*4]
0x180008479  add     rcx, rcx
0x18000847c  sub     r8, rcx
0x18000847f  mov     rbx, [rdi+r8*8+8]
0x180008484  test    rbx, rbx
0x180008487  jz      short loc_1800084A9
0x180008489  cmp     [rbx], r9d
0x18000848c  jz      short loc_180008494
0x18000848e  mov     rbx, [rbx+8]
0x180008492  jmp     short loc_180008484
0x180008494  add     rbx, 10h
0x180008498  jz      short loc_1800084A9
0x18000849a  cmp     qword ptr [rbx+8], 0
0x18000849f  jnz     short loc_1800084A9
0x1800084a1  lea     rax, [rdi+4]
0x1800084a5  mov     [rbx+8], rax
0x1800084a9  mov     rax, rbx
0x1800084ac  mov     rbx, [rsp+28h+arg_0]
0x1800084b1  add     rsp, 20h
0x1800084b5  pop     rdi
0x1800084b6  retn
```
