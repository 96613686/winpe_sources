# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b444`
- end: `0x18000b4fb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b650`

## callees

- `0x18000b444`
- `0x18000bd6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b49a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b49a`

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
0x18000b444  mov     [rsp+arg_0], rbx
0x18000b449  push    rdi
0x18000b44a  sub     rsp, 20h
0x18000b44e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b455  xor     ebx, ebx
0x18000b457  test    rdi, rdi
0x18000b45a  jz      short loc_18000B4D6
0x18000b45c  cmp     [rdi+8], rbx
0x18000b460  jnz     short loc_18000B487
0x18000b462  mov     rcx, [rdi]
0x18000b465  lea     rdx, [rsp+28h+arg_8]
0x18000b46a  mov     [rsp+28h+arg_8], rbx
0x18000b46f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b474  test    eax, eax
0x18000b476  js      short loc_18000B487
0x18000b478  cmp     [rdi+8], rbx
0x18000b47c  jnz     short loc_18000B487
0x18000b47e  mov     rax, [rsp+28h+arg_8]
0x18000b483  mov     [rdi+8], rax
0x18000b487  mov     rax, [rdi+8]
0x18000b48b  lea     rcx, [rax+20h]
0x18000b48f  neg     rax
0x18000b492  sbb     rdi, rdi
0x18000b495  and     rdi, rcx
0x18000b498  jz      short loc_18000B4D6
0x18000b49a  call    cs:__imp_GetCurrentThreadId
0x18000b4a0  mov     r8d, eax
0x18000b4a3  mov     r9d, eax
0x18000b4a6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b4b0  mul     r9
0x18000b4b3  shr     rdx, 3
0x18000b4b7  lea     rcx, [rdx+rdx*4]
0x18000b4bb  add     rcx, rcx
0x18000b4be  sub     r8, rcx
0x18000b4c1  mov     rbx, [rdi+r8*8+8]
0x18000b4c6  jmp     short loc_18000B4D1
0x18000b4c8  cmp     [rbx], r9d
0x18000b4cb  jz      short loc_18000B4E4
0x18000b4cd  mov     rbx, [rbx+8]
0x18000b4d1  test    rbx, rbx
0x18000b4d4  jnz     short loc_18000B4C8
0x18000b4d6  mov     rax, rbx
0x18000b4d9  mov     rbx, [rsp+28h+arg_0]
0x18000b4de  add     rsp, 20h
0x18000b4e2  pop     rdi
0x18000b4e3  retn
0x18000b4e4  add     rbx, 10h
0x18000b4e8  jz      short loc_18000B4D6
0x18000b4ea  cmp     qword ptr [rbx+8], 0
0x18000b4ef  jnz     short loc_18000B4D6
0x18000b4f1  lea     rax, [rdi+4]
0x18000b4f5  mov     [rbx+8], rax
0x18000b4f9  jmp     short loc_18000B4D6
```
