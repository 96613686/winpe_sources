# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800094c0`
- end: `0x180009577`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009680`

## callees

- `0x1800094c0`
- `0x180009a28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009516`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009516`

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
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
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
0x1800094c0  mov     [rsp+arg_0], rbx
0x1800094c5  push    rdi
0x1800094c6  sub     rsp, 20h
0x1800094ca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800094d1  xor     ebx, ebx
0x1800094d3  test    rdi, rdi
0x1800094d6  jz      short loc_180009552
0x1800094d8  cmp     [rdi+8], rbx
0x1800094dc  jnz     short loc_180009503
0x1800094de  mov     rcx, [rdi]
0x1800094e1  lea     rdx, [rsp+28h+arg_8]
0x1800094e6  mov     [rsp+28h+arg_8], rbx
0x1800094eb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800094f0  test    eax, eax
0x1800094f2  js      short loc_180009503
0x1800094f4  cmp     [rdi+8], rbx
0x1800094f8  jnz     short loc_180009503
0x1800094fa  mov     rax, [rsp+28h+arg_8]
0x1800094ff  mov     [rdi+8], rax
0x180009503  mov     rax, [rdi+8]
0x180009507  lea     rcx, [rax+20h]
0x18000950b  neg     rax
0x18000950e  sbb     rdi, rdi
0x180009511  and     rdi, rcx
0x180009514  jz      short loc_180009552
0x180009516  call    cs:__imp_GetCurrentThreadId
0x18000951c  mov     r8d, eax
0x18000951f  mov     r9d, eax
0x180009522  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000952c  mul     r9
0x18000952f  shr     rdx, 3
0x180009533  lea     rcx, [rdx+rdx*4]
0x180009537  add     rcx, rcx
0x18000953a  sub     r8, rcx
0x18000953d  mov     rbx, [rdi+r8*8+8]
0x180009542  jmp     short loc_18000954D
0x180009544  cmp     [rbx], r9d
0x180009547  jz      short loc_180009560
0x180009549  mov     rbx, [rbx+8]
0x18000954d  test    rbx, rbx
0x180009550  jnz     short loc_180009544
0x180009552  mov     rax, rbx
0x180009555  mov     rbx, [rsp+28h+arg_0]
0x18000955a  add     rsp, 20h
0x18000955e  pop     rdi
0x18000955f  retn
0x180009560  add     rbx, 10h
0x180009564  jz      short loc_180009552
0x180009566  cmp     qword ptr [rbx+8], 0
0x18000956b  jnz     short loc_180009552
0x18000956d  lea     rax, [rdi+4]
0x180009571  mov     [rbx+8], rax
0x180009575  jmp     short loc_180009552
```
