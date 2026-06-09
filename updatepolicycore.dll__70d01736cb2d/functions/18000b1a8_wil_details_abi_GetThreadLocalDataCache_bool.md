# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b1a8`
- end: `0x18000b25f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b370`

## callees

- `0x18000b1a8`
- `0x18000c208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1fe`

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
0x18000b1a8  mov     [rsp+arg_0], rbx
0x18000b1ad  push    rdi
0x18000b1ae  sub     rsp, 20h
0x18000b1b2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b1b9  xor     ebx, ebx
0x18000b1bb  test    rdi, rdi
0x18000b1be  jz      short loc_18000B23A
0x18000b1c0  cmp     [rdi+8], rbx
0x18000b1c4  jnz     short loc_18000B1EB
0x18000b1c6  mov     rcx, [rdi]
0x18000b1c9  lea     rdx, [rsp+28h+arg_8]
0x18000b1ce  mov     [rsp+28h+arg_8], rbx
0x18000b1d3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b1d8  test    eax, eax
0x18000b1da  js      short loc_18000B1EB
0x18000b1dc  cmp     [rdi+8], rbx
0x18000b1e0  jnz     short loc_18000B1EB
0x18000b1e2  mov     rax, [rsp+28h+arg_8]
0x18000b1e7  mov     [rdi+8], rax
0x18000b1eb  mov     rax, [rdi+8]
0x18000b1ef  lea     rcx, [rax+20h]
0x18000b1f3  neg     rax
0x18000b1f6  sbb     rdi, rdi
0x18000b1f9  and     rdi, rcx
0x18000b1fc  jz      short loc_18000B23A
0x18000b1fe  call    cs:__imp_GetCurrentThreadId
0x18000b204  mov     r8d, eax
0x18000b207  mov     r9d, eax
0x18000b20a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b214  mul     r9
0x18000b217  shr     rdx, 3
0x18000b21b  lea     rcx, [rdx+rdx*4]
0x18000b21f  add     rcx, rcx
0x18000b222  sub     r8, rcx
0x18000b225  mov     rbx, [rdi+r8*8+8]
0x18000b22a  jmp     short loc_18000B235
0x18000b22c  cmp     [rbx], r9d
0x18000b22f  jz      short loc_18000B248
0x18000b231  mov     rbx, [rbx+8]
0x18000b235  test    rbx, rbx
0x18000b238  jnz     short loc_18000B22C
0x18000b23a  mov     rax, rbx
0x18000b23d  mov     rbx, [rsp+28h+arg_0]
0x18000b242  add     rsp, 20h
0x18000b246  pop     rdi
0x18000b247  retn
0x18000b248  add     rbx, 10h
0x18000b24c  jz      short loc_18000B23A
0x18000b24e  cmp     qword ptr [rbx+8], 0
0x18000b253  jnz     short loc_18000B23A
0x18000b255  lea     rax, [rdi+4]
0x18000b259  mov     [rbx+8], rax
0x18000b25d  jmp     short loc_18000B23A
```
