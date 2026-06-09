# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009188`
- end: `0x180009245`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008bf0`

## callees

- `0x180008790`
- `0x180009188`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091e2`

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
0x180009188  mov     [rsp+arg_0], rbx
0x18000918d  push    rdi
0x18000918e  sub     rsp, 20h
0x180009192  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009199  xor     ebx, ebx
0x18000919b  test    rdi, rdi
0x18000919e  jz      loc_180009237
0x1800091a4  cmp     [rdi+8], rbx
0x1800091a8  jnz     short loc_1800091CF
0x1800091aa  mov     rcx, [rdi]
0x1800091ad  lea     rdx, [rsp+28h+arg_8]
0x1800091b2  mov     [rsp+28h+arg_8], rbx
0x1800091b7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800091bc  test    eax, eax
0x1800091be  js      short loc_1800091CF
0x1800091c0  cmp     [rdi+8], rbx
0x1800091c4  jnz     short loc_1800091CF
0x1800091c6  mov     rax, [rsp+28h+arg_8]
0x1800091cb  mov     [rdi+8], rax
0x1800091cf  mov     rax, [rdi+8]
0x1800091d3  lea     rcx, [rax+20h]
0x1800091d7  neg     rax
0x1800091da  sbb     rdi, rdi
0x1800091dd  and     rdi, rcx
0x1800091e0  jz      short loc_180009237
0x1800091e2  call    cs:__imp_GetCurrentThreadId
0x1800091e8  mov     r8d, eax
0x1800091eb  mov     r9d, eax
0x1800091ee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800091f8  shr     r8, 2
0x1800091fc  mul     r8
0x1800091ff  shr     rdx, 3
0x180009203  lea     rcx, [rdx+rdx*4]
0x180009207  add     rcx, rcx
0x18000920a  sub     r8, rcx
0x18000920d  mov     rbx, [rdi+r8*8+8]
0x180009212  test    rbx, rbx
0x180009215  jz      short loc_180009237
0x180009217  cmp     [rbx], r9d
0x18000921a  jz      short loc_180009222
0x18000921c  mov     rbx, [rbx+8]
0x180009220  jmp     short loc_180009212
0x180009222  add     rbx, 10h
0x180009226  jz      short loc_180009237
0x180009228  cmp     qword ptr [rbx+8], 0
0x18000922d  jnz     short loc_180009237
0x18000922f  lea     rax, [rdi+4]
0x180009233  mov     [rbx+8], rax
0x180009237  mov     rax, rbx
0x18000923a  mov     rbx, [rsp+28h+arg_0]
0x18000923f  add     rsp, 20h
0x180009243  pop     rdi
0x180009244  retn
```
