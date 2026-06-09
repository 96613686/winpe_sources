# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a158`
- end: `0x18000a21f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `199`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800099c0`

## callees

- `0x180009600`
- `0x18000a158`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a1b2`
- `KERNEL32!GetCurrentThreadId` at `0x18000a1b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 v3; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v9 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v9) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v9;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(v2 + 8) >> 64);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (CurrentThreadId % 0xAuLL) + 8); ; i = *(_QWORD *)(i + 8) )
      {
        if ( !i )
          return 0;
        if ( *(_DWORD *)i == CurrentThreadId )
          break;
      }
      v7 = i == -16;
      v8 = i + 16;
      v1 = v8;
      if ( !v7 && !*(_QWORD *)(v8 + 8) )
        *(_QWORD *)(v8 + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v1;
}

```

## disassembly

```asm
0x18000a158  mov     [rsp+arg_0], rbx
0x18000a15d  push    rdi
0x18000a15e  sub     rsp, 20h
0x18000a162  xor     edi, edi
0x18000a164  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a16b  test    rbx, rbx
0x18000a16e  jz      loc_18000A1F6
0x18000a174  cmp     [rbx+8], rdi
0x18000a178  jnz     short loc_18000A19F
0x18000a17a  and     [rsp+28h+arg_8], rdi
0x18000a17f  lea     rdx, [rsp+28h+arg_8]
0x18000a184  mov     rcx, [rbx]
0x18000a187  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a18c  test    eax, eax
0x18000a18e  js      short loc_18000A19F
0x18000a190  cmp     [rbx+8], rdi
0x18000a194  jnz     short loc_18000A19F
0x18000a196  mov     rax, [rsp+28h+arg_8]
0x18000a19b  mov     [rbx+8], rax
0x18000a19f  mov     rcx, [rbx+8]
0x18000a1a3  lea     rax, [rcx+20h]
0x18000a1a7  neg     rcx
0x18000a1aa  sbb     rbx, rbx
0x18000a1ad  and     rbx, rax
0x18000a1b0  jz      short loc_18000A1F6
0x18000a1b2  call    cs:__imp_GetCurrentThreadId
0x18000a1b9  nop     dword ptr [rax+rax+00h]
0x18000a1be  mov     r9d, eax
0x18000a1c1  mov     r8d, eax
0x18000a1c4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a1ce  mul     r9
0x18000a1d1  shr     rdx, 3
0x18000a1d5  lea     rcx, [rdx+rdx*4]
0x18000a1d9  add     rcx, rcx
0x18000a1dc  sub     r8, rcx
0x18000a1df  mov     rcx, [rbx+r8*8+8]
0x18000a1e4  jmp     short loc_18000A1EF
0x18000a1e6  cmp     [rcx], r9d
0x18000a1e9  jz      short loc_18000A205
0x18000a1eb  mov     rcx, [rcx+8]
0x18000a1ef  test    rcx, rcx
0x18000a1f2  jnz     short loc_18000A1E6
0x18000a1f4  xor     edi, edi
0x18000a1f6  mov     rax, rdi
0x18000a1f9  mov     rbx, [rsp+28h+arg_0]
0x18000a1fe  add     rsp, 20h
0x18000a202  pop     rdi
0x18000a203  retn
0x18000a205  add     rcx, 10h
0x18000a209  mov     rdi, rcx
0x18000a20c  jz      short loc_18000A1F6
0x18000a20e  cmp     qword ptr [rcx+8], 0
0x18000a213  jnz     short loc_18000A1F6
0x18000a215  lea     rax, [rbx+4]
0x18000a219  mov     [rcx+8], rax
0x18000a21d  jmp     short loc_18000A1F6
```
