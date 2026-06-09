# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001ea74`
- end: `0x18001eb31`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e440`

## callees

- `0x180016b70`
- `0x18001ea74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eace`

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
0x18001ea74  mov     [rsp+arg_0], rbx
0x18001ea79  push    rdi
0x18001ea7a  sub     rsp, 20h
0x18001ea7e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001ea85  xor     ebx, ebx
0x18001ea87  test    rdi, rdi
0x18001ea8a  jz      loc_18001EB23
0x18001ea90  cmp     [rdi+8], rbx
0x18001ea94  jnz     short loc_18001EABB
0x18001ea96  mov     rcx, [rdi]
0x18001ea99  lea     rdx, [rsp+28h+arg_8]
0x18001ea9e  mov     [rsp+28h+arg_8], rbx
0x18001eaa3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001eaa8  test    eax, eax
0x18001eaaa  js      short loc_18001EABB
0x18001eaac  cmp     [rdi+8], rbx
0x18001eab0  jnz     short loc_18001EABB
0x18001eab2  mov     rax, [rsp+28h+arg_8]
0x18001eab7  mov     [rdi+8], rax
0x18001eabb  mov     rax, [rdi+8]
0x18001eabf  lea     rcx, [rax+20h]
0x18001eac3  neg     rax
0x18001eac6  sbb     rdi, rdi
0x18001eac9  and     rdi, rcx
0x18001eacc  jz      short loc_18001EB23
0x18001eace  call    cs:__imp_GetCurrentThreadId
0x18001ead4  mov     r8d, eax
0x18001ead7  mov     r9d, eax
0x18001eada  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001eae4  shr     r8, 2
0x18001eae8  mul     r8
0x18001eaeb  shr     rdx, 3
0x18001eaef  lea     rcx, [rdx+rdx*4]
0x18001eaf3  add     rcx, rcx
0x18001eaf6  sub     r8, rcx
0x18001eaf9  mov     rbx, [rdi+r8*8+8]
0x18001eafe  test    rbx, rbx
0x18001eb01  jz      short loc_18001EB23
0x18001eb03  cmp     [rbx], r9d
0x18001eb06  jz      short loc_18001EB0E
0x18001eb08  mov     rbx, [rbx+8]
0x18001eb0c  jmp     short loc_18001EAFE
0x18001eb0e  add     rbx, 10h
0x18001eb12  jz      short loc_18001EB23
0x18001eb14  cmp     qword ptr [rbx+8], 0
0x18001eb19  jnz     short loc_18001EB23
0x18001eb1b  lea     rax, [rdi+4]
0x18001eb1f  mov     [rbx+8], rax
0x18001eb23  mov     rax, rbx
0x18001eb26  mov     rbx, [rsp+28h+arg_0]
0x18001eb2b  add     rsp, 20h
0x18001eb2f  pop     rdi
0x18001eb30  retn
```
