# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004060`
- end: `0x180004117`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004220`

## callees

- `0x180004060`
- `0x180005754`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040b6`

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
0x180004060  mov     [rsp+arg_0], rbx
0x180004065  push    rdi
0x180004066  sub     rsp, 20h
0x18000406a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004071  xor     ebx, ebx
0x180004073  test    rdi, rdi
0x180004076  jz      short loc_1800040F2
0x180004078  cmp     [rdi+8], rbx
0x18000407c  jnz     short loc_1800040A3
0x18000407e  mov     rcx, [rdi]
0x180004081  lea     rdx, [rsp+28h+arg_8]
0x180004086  mov     [rsp+28h+arg_8], rbx
0x18000408b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004090  test    eax, eax
0x180004092  js      short loc_1800040A3
0x180004094  cmp     [rdi+8], rbx
0x180004098  jnz     short loc_1800040A3
0x18000409a  mov     rax, [rsp+28h+arg_8]
0x18000409f  mov     [rdi+8], rax
0x1800040a3  mov     rax, [rdi+8]
0x1800040a7  lea     rcx, [rax+20h]
0x1800040ab  neg     rax
0x1800040ae  sbb     rdi, rdi
0x1800040b1  and     rdi, rcx
0x1800040b4  jz      short loc_1800040F2
0x1800040b6  call    cs:__imp_GetCurrentThreadId
0x1800040bc  mov     r8d, eax
0x1800040bf  mov     r9d, eax
0x1800040c2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800040cc  mul     r9
0x1800040cf  shr     rdx, 3
0x1800040d3  lea     rcx, [rdx+rdx*4]
0x1800040d7  add     rcx, rcx
0x1800040da  sub     r8, rcx
0x1800040dd  mov     rbx, [rdi+r8*8+8]
0x1800040e2  jmp     short loc_1800040ED
0x1800040e4  cmp     [rbx], r9d
0x1800040e7  jz      short loc_180004100
0x1800040e9  mov     rbx, [rbx+8]
0x1800040ed  test    rbx, rbx
0x1800040f0  jnz     short loc_1800040E4
0x1800040f2  mov     rax, rbx
0x1800040f5  mov     rbx, [rsp+28h+arg_0]
0x1800040fa  add     rsp, 20h
0x1800040fe  pop     rdi
0x1800040ff  retn
0x180004100  add     rbx, 10h
0x180004104  jz      short loc_1800040F2
0x180004106  cmp     qword ptr [rbx+8], 0
0x18000410b  jnz     short loc_1800040F2
0x18000410d  lea     rax, [rdi+4]
0x180004111  mov     [rbx+8], rax
0x180004115  jmp     short loc_1800040F2
```
