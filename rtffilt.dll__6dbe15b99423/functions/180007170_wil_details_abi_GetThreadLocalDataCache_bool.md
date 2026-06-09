# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007170`
- end: `0x18000722b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006760`

## callees

- `0x180004b78`
- `0x180007170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071c6`

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
0x180007170  mov     [rsp+arg_0], rbx
0x180007175  push    rdi
0x180007176  sub     rsp, 20h
0x18000717a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007181  xor     ebx, ebx
0x180007183  test    rdi, rdi
0x180007186  jz      short loc_180007206
0x180007188  cmp     [rdi+8], rbx
0x18000718c  jnz     short loc_1800071B3
0x18000718e  mov     rcx, [rdi]
0x180007191  lea     rdx, [rsp+28h+arg_8]
0x180007196  mov     [rsp+28h+arg_8], rbx
0x18000719b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800071a0  test    eax, eax
0x1800071a2  js      short loc_1800071B3
0x1800071a4  cmp     [rdi+8], rbx
0x1800071a8  jnz     short loc_1800071B3
0x1800071aa  mov     rax, [rsp+28h+arg_8]
0x1800071af  mov     [rdi+8], rax
0x1800071b3  mov     rax, [rdi+8]
0x1800071b7  lea     rcx, [rax+20h]
0x1800071bb  neg     rax
0x1800071be  sbb     rdi, rdi
0x1800071c1  and     rdi, rcx
0x1800071c4  jz      short loc_180007206
0x1800071c6  call    cs:__imp_GetCurrentThreadId
0x1800071cc  mov     r8d, eax
0x1800071cf  mov     r9d, eax
0x1800071d2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800071dc  shr     r8, 2
0x1800071e0  mul     r8
0x1800071e3  shr     rdx, 3
0x1800071e7  lea     rcx, [rdx+rdx*4]
0x1800071eb  add     rcx, rcx
0x1800071ee  sub     r8, rcx
0x1800071f1  mov     rbx, [rdi+r8*8+8]
0x1800071f6  jmp     short loc_180007201
0x1800071f8  cmp     [rbx], r9d
0x1800071fb  jz      short loc_180007214
0x1800071fd  mov     rbx, [rbx+8]
0x180007201  test    rbx, rbx
0x180007204  jnz     short loc_1800071F8
0x180007206  mov     rax, rbx
0x180007209  mov     rbx, [rsp+28h+arg_0]
0x18000720e  add     rsp, 20h
0x180007212  pop     rdi
0x180007213  retn
0x180007214  add     rbx, 10h
0x180007218  jz      short loc_180007206
0x18000721a  cmp     qword ptr [rbx+8], 0
0x18000721f  jnz     short loc_180007206
0x180007221  lea     rax, [rdi+4]
0x180007225  mov     [rbx+8], rax
0x180007229  jmp     short loc_180007206
```
