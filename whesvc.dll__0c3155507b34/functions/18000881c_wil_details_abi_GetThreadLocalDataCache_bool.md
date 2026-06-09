# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000881c`
- end: `0x1800088d7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008190`

## callees

- `0x180007864`
- `0x18000881c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008872`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008872`

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
0x18000881c  mov     [rsp+arg_0], rbx
0x180008821  push    rdi
0x180008822  sub     rsp, 20h
0x180008826  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000882d  xor     ebx, ebx
0x18000882f  test    rdi, rdi
0x180008832  jz      short loc_1800088B2
0x180008834  cmp     [rdi+8], rbx
0x180008838  jnz     short loc_18000885F
0x18000883a  mov     rcx, [rdi]
0x18000883d  lea     rdx, [rsp+28h+arg_8]
0x180008842  mov     [rsp+28h+arg_8], rbx
0x180008847  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000884c  test    eax, eax
0x18000884e  js      short loc_18000885F
0x180008850  cmp     [rdi+8], rbx
0x180008854  jnz     short loc_18000885F
0x180008856  mov     rax, [rsp+28h+arg_8]
0x18000885b  mov     [rdi+8], rax
0x18000885f  mov     rax, [rdi+8]
0x180008863  lea     rcx, [rax+20h]
0x180008867  neg     rax
0x18000886a  sbb     rdi, rdi
0x18000886d  and     rdi, rcx
0x180008870  jz      short loc_1800088B2
0x180008872  call    cs:__imp_GetCurrentThreadId
0x180008878  mov     r8d, eax
0x18000887b  mov     r9d, eax
0x18000887e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008888  shr     r8, 2
0x18000888c  mul     r8
0x18000888f  shr     rdx, 3
0x180008893  lea     rcx, [rdx+rdx*4]
0x180008897  add     rcx, rcx
0x18000889a  sub     r8, rcx
0x18000889d  mov     rbx, [rdi+r8*8+8]
0x1800088a2  jmp     short loc_1800088AD
0x1800088a4  cmp     [rbx], r9d
0x1800088a7  jz      short loc_1800088C0
0x1800088a9  mov     rbx, [rbx+8]
0x1800088ad  test    rbx, rbx
0x1800088b0  jnz     short loc_1800088A4
0x1800088b2  mov     rax, rbx
0x1800088b5  mov     rbx, [rsp+28h+arg_0]
0x1800088ba  add     rsp, 20h
0x1800088be  pop     rdi
0x1800088bf  retn
0x1800088c0  add     rbx, 10h
0x1800088c4  jz      short loc_1800088B2
0x1800088c6  cmp     qword ptr [rbx+8], 0
0x1800088cb  jnz     short loc_1800088B2
0x1800088cd  lea     rax, [rdi+4]
0x1800088d1  mov     [rbx+8], rax
0x1800088d5  jmp     short loc_1800088B2
```
