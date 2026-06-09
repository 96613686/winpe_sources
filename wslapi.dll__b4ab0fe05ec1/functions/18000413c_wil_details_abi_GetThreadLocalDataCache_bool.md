# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000413c`
- end: `0x1800041f9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b20`

## callees

- `0x180003638`
- `0x18000413c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004196`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004196`

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
0x18000413c  mov     [rsp+arg_0], rbx
0x180004141  push    rdi
0x180004142  sub     rsp, 20h
0x180004146  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000414d  xor     ebx, ebx
0x18000414f  test    rdi, rdi
0x180004152  jz      loc_1800041EB
0x180004158  cmp     [rdi+8], rbx
0x18000415c  jnz     short loc_180004183
0x18000415e  mov     rcx, [rdi]
0x180004161  lea     rdx, [rsp+28h+arg_8]
0x180004166  mov     [rsp+28h+arg_8], rbx
0x18000416b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004170  test    eax, eax
0x180004172  js      short loc_180004183
0x180004174  cmp     [rdi+8], rbx
0x180004178  jnz     short loc_180004183
0x18000417a  mov     rax, [rsp+28h+arg_8]
0x18000417f  mov     [rdi+8], rax
0x180004183  mov     rax, [rdi+8]
0x180004187  lea     rcx, [rax+20h]
0x18000418b  neg     rax
0x18000418e  sbb     rdi, rdi
0x180004191  and     rdi, rcx
0x180004194  jz      short loc_1800041EB
0x180004196  call    cs:__imp_GetCurrentThreadId
0x18000419c  mov     r8d, eax
0x18000419f  mov     r9d, eax
0x1800041a2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800041ac  shr     r8, 2
0x1800041b0  mul     r8
0x1800041b3  shr     rdx, 3
0x1800041b7  lea     rcx, [rdx+rdx*4]
0x1800041bb  add     rcx, rcx
0x1800041be  sub     r8, rcx
0x1800041c1  mov     rbx, [rdi+r8*8+8]
0x1800041c6  test    rbx, rbx
0x1800041c9  jz      short loc_1800041EB
0x1800041cb  cmp     [rbx], r9d
0x1800041ce  jz      short loc_1800041D6
0x1800041d0  mov     rbx, [rbx+8]
0x1800041d4  jmp     short loc_1800041C6
0x1800041d6  add     rbx, 10h
0x1800041da  jz      short loc_1800041EB
0x1800041dc  cmp     qword ptr [rbx+8], 0
0x1800041e1  jnz     short loc_1800041EB
0x1800041e3  lea     rax, [rdi+4]
0x1800041e7  mov     [rbx+8], rax
0x1800041eb  mov     rax, rbx
0x1800041ee  mov     rbx, [rsp+28h+arg_0]
0x1800041f3  add     rsp, 20h
0x1800041f7  pop     rdi
0x1800041f8  retn
```
