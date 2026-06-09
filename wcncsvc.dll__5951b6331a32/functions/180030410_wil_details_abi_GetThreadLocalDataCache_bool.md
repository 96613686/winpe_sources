# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180030410`
- end: `0x1800304cb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f9d0`

## callees

- `0x18002def8`
- `0x180030410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030466`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030466`

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
0x180030410  mov     [rsp+arg_0], rbx
0x180030415  push    rdi
0x180030416  sub     rsp, 20h
0x18003041a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180030421  xor     ebx, ebx
0x180030423  test    rdi, rdi
0x180030426  jz      short loc_1800304A6
0x180030428  cmp     [rdi+8], rbx
0x18003042c  jnz     short loc_180030453
0x18003042e  mov     rcx, [rdi]
0x180030431  lea     rdx, [rsp+28h+arg_8]
0x180030436  mov     [rsp+28h+arg_8], rbx
0x18003043b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180030440  test    eax, eax
0x180030442  js      short loc_180030453
0x180030444  cmp     [rdi+8], rbx
0x180030448  jnz     short loc_180030453
0x18003044a  mov     rax, [rsp+28h+arg_8]
0x18003044f  mov     [rdi+8], rax
0x180030453  mov     rax, [rdi+8]
0x180030457  lea     rcx, [rax+20h]
0x18003045b  neg     rax
0x18003045e  sbb     rdi, rdi
0x180030461  and     rdi, rcx
0x180030464  jz      short loc_1800304A6
0x180030466  call    cs:__imp_GetCurrentThreadId
0x18003046c  mov     r8d, eax
0x18003046f  mov     r9d, eax
0x180030472  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003047c  shr     r8, 2
0x180030480  mul     r8
0x180030483  shr     rdx, 3
0x180030487  lea     rcx, [rdx+rdx*4]
0x18003048b  add     rcx, rcx
0x18003048e  sub     r8, rcx
0x180030491  mov     rbx, [rdi+r8*8+8]
0x180030496  jmp     short loc_1800304A1
0x180030498  cmp     [rbx], r9d
0x18003049b  jz      short loc_1800304B4
0x18003049d  mov     rbx, [rbx+8]
0x1800304a1  test    rbx, rbx
0x1800304a4  jnz     short loc_180030498
0x1800304a6  mov     rax, rbx
0x1800304a9  mov     rbx, [rsp+28h+arg_0]
0x1800304ae  add     rsp, 20h
0x1800304b2  pop     rdi
0x1800304b3  retn
0x1800304b4  add     rbx, 10h
0x1800304b8  jz      short loc_1800304A6
0x1800304ba  cmp     qword ptr [rbx+8], 0
0x1800304bf  jnz     short loc_1800304A6
0x1800304c1  lea     rax, [rdi+4]
0x1800304c5  mov     [rbx+8], rax
0x1800304c9  jmp     short loc_1800304A6
```
