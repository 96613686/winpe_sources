# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800043e8`
- end: `0x1800044a5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d70`

## callees

- `0x1800038c8`
- `0x1800043e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004442`

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
0x1800043e8  mov     [rsp+arg_0], rbx
0x1800043ed  push    rdi
0x1800043ee  sub     rsp, 20h
0x1800043f2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800043f9  xor     ebx, ebx
0x1800043fb  test    rdi, rdi
0x1800043fe  jz      loc_180004497
0x180004404  cmp     [rdi+8], rbx
0x180004408  jnz     short loc_18000442F
0x18000440a  mov     rcx, [rdi]
0x18000440d  lea     rdx, [rsp+28h+arg_8]
0x180004412  mov     [rsp+28h+arg_8], rbx
0x180004417  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000441c  test    eax, eax
0x18000441e  js      short loc_18000442F
0x180004420  cmp     [rdi+8], rbx
0x180004424  jnz     short loc_18000442F
0x180004426  mov     rax, [rsp+28h+arg_8]
0x18000442b  mov     [rdi+8], rax
0x18000442f  mov     rax, [rdi+8]
0x180004433  lea     rcx, [rax+20h]
0x180004437  neg     rax
0x18000443a  sbb     rdi, rdi
0x18000443d  and     rdi, rcx
0x180004440  jz      short loc_180004497
0x180004442  call    cs:__imp_GetCurrentThreadId
0x180004448  mov     r8d, eax
0x18000444b  mov     r9d, eax
0x18000444e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004458  shr     r8, 2
0x18000445c  mul     r8
0x18000445f  shr     rdx, 3
0x180004463  lea     rcx, [rdx+rdx*4]
0x180004467  add     rcx, rcx
0x18000446a  sub     r8, rcx
0x18000446d  mov     rbx, [rdi+r8*8+8]
0x180004472  test    rbx, rbx
0x180004475  jz      short loc_180004497
0x180004477  cmp     [rbx], r9d
0x18000447a  jz      short loc_180004482
0x18000447c  mov     rbx, [rbx+8]
0x180004480  jmp     short loc_180004472
0x180004482  add     rbx, 10h
0x180004486  jz      short loc_180004497
0x180004488  cmp     qword ptr [rbx+8], 0
0x18000448d  jnz     short loc_180004497
0x18000448f  lea     rax, [rdi+4]
0x180004493  mov     [rbx+8], rax
0x180004497  mov     rax, rbx
0x18000449a  mov     rbx, [rsp+28h+arg_0]
0x18000449f  add     rsp, 20h
0x1800044a3  pop     rdi
0x1800044a4  retn
```
