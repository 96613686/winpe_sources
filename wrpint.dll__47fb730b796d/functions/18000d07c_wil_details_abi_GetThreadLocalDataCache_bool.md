# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d07c`
- end: `0x18000d137`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c8a0`

## callees

- `0x18000b794`
- `0x18000d07c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0d2`

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
0x18000d07c  mov     [rsp+arg_0], rbx
0x18000d081  push    rdi
0x18000d082  sub     rsp, 20h
0x18000d086  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d08d  xor     ebx, ebx
0x18000d08f  test    rdi, rdi
0x18000d092  jz      short loc_18000D112
0x18000d094  cmp     [rdi+8], rbx
0x18000d098  jnz     short loc_18000D0BF
0x18000d09a  mov     rcx, [rdi]
0x18000d09d  lea     rdx, [rsp+28h+arg_8]
0x18000d0a2  mov     [rsp+28h+arg_8], rbx
0x18000d0a7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d0ac  test    eax, eax
0x18000d0ae  js      short loc_18000D0BF
0x18000d0b0  cmp     [rdi+8], rbx
0x18000d0b4  jnz     short loc_18000D0BF
0x18000d0b6  mov     rax, [rsp+28h+arg_8]
0x18000d0bb  mov     [rdi+8], rax
0x18000d0bf  mov     rax, [rdi+8]
0x18000d0c3  lea     rcx, [rax+20h]
0x18000d0c7  neg     rax
0x18000d0ca  sbb     rdi, rdi
0x18000d0cd  and     rdi, rcx
0x18000d0d0  jz      short loc_18000D112
0x18000d0d2  call    cs:__imp_GetCurrentThreadId
0x18000d0d8  mov     r8d, eax
0x18000d0db  mov     r9d, eax
0x18000d0de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d0e8  shr     r8, 2
0x18000d0ec  mul     r8
0x18000d0ef  shr     rdx, 3
0x18000d0f3  lea     rcx, [rdx+rdx*4]
0x18000d0f7  add     rcx, rcx
0x18000d0fa  sub     r8, rcx
0x18000d0fd  mov     rbx, [rdi+r8*8+8]
0x18000d102  jmp     short loc_18000D10D
0x18000d104  cmp     [rbx], r9d
0x18000d107  jz      short loc_18000D120
0x18000d109  mov     rbx, [rbx+8]
0x18000d10d  test    rbx, rbx
0x18000d110  jnz     short loc_18000D104
0x18000d112  mov     rax, rbx
0x18000d115  mov     rbx, [rsp+28h+arg_0]
0x18000d11a  add     rsp, 20h
0x18000d11e  pop     rdi
0x18000d11f  retn
0x18000d120  add     rbx, 10h
0x18000d124  jz      short loc_18000D112
0x18000d126  cmp     qword ptr [rbx+8], 0
0x18000d12b  jnz     short loc_18000D112
0x18000d12d  lea     rax, [rdi+4]
0x18000d131  mov     [rbx+8], rax
0x18000d135  jmp     short loc_18000D112
```
