# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a924`
- end: `0x18000a9e9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a1a0`

## callees

- `0x180009110`
- `0x18000a924`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a97e`
- `KERNEL32!GetCurrentThreadId` at `0x18000a97e`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
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
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x18000a924  mov     [rsp+arg_0], rbx
0x18000a929  push    rdi
0x18000a92a  sub     rsp, 20h
0x18000a92e  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a935  xor     edi, edi
0x18000a937  test    rbx, rbx
0x18000a93a  jz      loc_18000A9DA
0x18000a940  cmp     [rbx+8], rdi
0x18000a944  jnz     short loc_18000A96B
0x18000a946  mov     rcx, [rbx]
0x18000a949  lea     rdx, [rsp+28h+arg_8]
0x18000a94e  and     [rsp+28h+arg_8], rdi
0x18000a953  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a958  test    eax, eax
0x18000a95a  js      short loc_18000A96B
0x18000a95c  cmp     [rbx+8], rdi
0x18000a960  jnz     short loc_18000A96B
0x18000a962  mov     rax, [rsp+28h+arg_8]
0x18000a967  mov     [rbx+8], rax
0x18000a96b  mov     rax, [rbx+8]
0x18000a96f  lea     rcx, [rax+20h]
0x18000a973  neg     rax
0x18000a976  sbb     rbx, rbx
0x18000a979  and     rbx, rcx
0x18000a97c  jz      short loc_18000A9DA
0x18000a97e  call    cs:__imp_GetCurrentThreadId
0x18000a985  nop     dword ptr [rax+rax+00h]
0x18000a98a  mov     r8d, eax
0x18000a98d  mov     r9d, eax
0x18000a990  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a99a  mul     r9
0x18000a99d  shr     rdx, 3
0x18000a9a1  lea     rcx, [rdx+rdx*4]
0x18000a9a5  add     rcx, rcx
0x18000a9a8  sub     r8, rcx
0x18000a9ab  mov     rcx, [rbx+r8*8+8]
0x18000a9b0  jmp     short loc_18000A9BB
0x18000a9b2  cmp     [rcx], r9d
0x18000a9b5  jz      short loc_18000A9C2
0x18000a9b7  mov     rcx, [rcx+8]
0x18000a9bb  test    rcx, rcx
0x18000a9be  jnz     short loc_18000A9B2
0x18000a9c0  jmp     short loc_18000A9DA
0x18000a9c2  add     rcx, 10h
0x18000a9c6  mov     rdi, rcx
0x18000a9c9  jz      short loc_18000A9DA
0x18000a9cb  cmp     qword ptr [rcx+8], 0
0x18000a9d0  jnz     short loc_18000A9DA
0x18000a9d2  lea     rax, [rbx+4]
0x18000a9d6  mov     [rcx+8], rax
0x18000a9da  mov     rbx, [rsp+28h+arg_0]
0x18000a9df  mov     rax, rdi
0x18000a9e2  add     rsp, 20h
0x18000a9e6  pop     rdi
0x18000a9e7  retn
```
