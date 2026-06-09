# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006434`
- end: `0x1800064f1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b30`

## callees

- `0x180004c10`
- `0x180006434`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000648e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000648e`

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
0x180006434  mov     [rsp+arg_0], rbx
0x180006439  push    rdi
0x18000643a  sub     rsp, 20h
0x18000643e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006445  xor     ebx, ebx
0x180006447  test    rdi, rdi
0x18000644a  jz      loc_1800064E3
0x180006450  cmp     [rdi+8], rbx
0x180006454  jnz     short loc_18000647B
0x180006456  mov     rcx, [rdi]
0x180006459  lea     rdx, [rsp+28h+arg_8]
0x18000645e  mov     [rsp+28h+arg_8], rbx
0x180006463  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006468  test    eax, eax
0x18000646a  js      short loc_18000647B
0x18000646c  cmp     [rdi+8], rbx
0x180006470  jnz     short loc_18000647B
0x180006472  mov     rax, [rsp+28h+arg_8]
0x180006477  mov     [rdi+8], rax
0x18000647b  mov     rax, [rdi+8]
0x18000647f  lea     rcx, [rax+20h]
0x180006483  neg     rax
0x180006486  sbb     rdi, rdi
0x180006489  and     rdi, rcx
0x18000648c  jz      short loc_1800064E3
0x18000648e  call    cs:__imp_GetCurrentThreadId
0x180006494  mov     r8d, eax
0x180006497  mov     r9d, eax
0x18000649a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800064a4  shr     r8, 2
0x1800064a8  mul     r8
0x1800064ab  shr     rdx, 3
0x1800064af  lea     rcx, [rdx+rdx*4]
0x1800064b3  add     rcx, rcx
0x1800064b6  sub     r8, rcx
0x1800064b9  mov     rbx, [rdi+r8*8+8]
0x1800064be  test    rbx, rbx
0x1800064c1  jz      short loc_1800064E3
0x1800064c3  cmp     [rbx], r9d
0x1800064c6  jz      short loc_1800064CE
0x1800064c8  mov     rbx, [rbx+8]
0x1800064cc  jmp     short loc_1800064BE
0x1800064ce  add     rbx, 10h
0x1800064d2  jz      short loc_1800064E3
0x1800064d4  cmp     qword ptr [rbx+8], 0
0x1800064d9  jnz     short loc_1800064E3
0x1800064db  lea     rax, [rdi+4]
0x1800064df  mov     [rbx+8], rax
0x1800064e3  mov     rax, rbx
0x1800064e6  mov     rbx, [rsp+28h+arg_0]
0x1800064eb  add     rsp, 20h
0x1800064ef  pop     rdi
0x1800064f0  retn
```
