# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180017d10`
- end: `0x180017dd0`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `192`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800173c0`

## callees

- `0x18000a834`
- `0x180017d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          break;
        }
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180017d10  mov     [rsp+arg_0], rbx
0x180017d15  push    rdi
0x180017d16  sub     rsp, 20h
0x180017d1a  xor     ebx, ebx
0x180017d1c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180017d23  test    rdi, rdi
0x180017d26  jz      loc_180017DC2
0x180017d2c  cmp     [rdi+8], rbx
0x180017d30  jnz     short loc_180017D57
0x180017d32  mov     [rsp+28h+arg_8], rbx
0x180017d37  lea     rdx, [rsp+28h+arg_8]
0x180017d3c  mov     rcx, [rdi]
0x180017d3f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180017d44  test    eax, eax
0x180017d46  js      short loc_180017D57
0x180017d48  cmp     [rdi+8], rbx
0x180017d4c  jnz     short loc_180017D57
0x180017d4e  mov     rax, [rsp+28h+arg_8]
0x180017d53  mov     [rdi+8], rax
0x180017d57  mov     rcx, [rdi+8]
0x180017d5b  lea     rax, [rcx+20h]
0x180017d5f  neg     rcx
0x180017d62  sbb     rdi, rdi
0x180017d65  and     rdi, rax
0x180017d68  jz      short loc_180017DC2
0x180017d6a  call    cs:__imp_GetCurrentThreadId
0x180017d70  mov     r9d, eax
0x180017d73  mov     r8d, eax
0x180017d76  shr     r8, 2
0x180017d7a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180017d84  mul     r8
0x180017d87  shr     rdx, 3
0x180017d8b  lea     rcx, [rdx+rdx*4]
0x180017d8f  add     rcx, rcx
0x180017d92  sub     r8, rcx
0x180017d95  mov     rbx, [rdi+r8*8+8]
0x180017d9a  test    rbx, rbx
0x180017d9d  jz      short loc_180017DAE
0x180017d9f  cmp     [rbx], r9d
0x180017da2  jz      short loc_180017DAA
0x180017da4  mov     rbx, [rbx+8]
0x180017da8  jmp     short loc_180017D9A
0x180017daa  add     rbx, 10h
0x180017dae  test    rbx, rbx
0x180017db1  jz      short loc_180017DC2
0x180017db3  cmp     qword ptr [rbx+8], 0
0x180017db8  jnz     short loc_180017DC2
0x180017dba  lea     rcx, [rdi+4]
0x180017dbe  mov     [rbx+8], rcx
0x180017dc2  mov     rax, rbx
0x180017dc5  mov     rbx, [rsp+28h+arg_0]
0x180017dca  add     rsp, 20h
0x180017dce  pop     rdi
0x180017dcf  retn
```
