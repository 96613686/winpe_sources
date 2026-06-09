# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000a3bc`
- end: `0x14000a477`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009be0`

## callees

- `0x140008c5c`
- `0x14000a3bc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000a412`
- `KERNEL32!GetCurrentThreadId` at `0x14000a412`

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
0x14000a3bc  mov     [rsp+arg_0], rbx
0x14000a3c1  push    rdi
0x14000a3c2  sub     rsp, 20h
0x14000a3c6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000a3cd  xor     ebx, ebx
0x14000a3cf  test    rdi, rdi
0x14000a3d2  jz      short loc_14000A452
0x14000a3d4  cmp     [rdi+8], rbx
0x14000a3d8  jnz     short loc_14000A3FF
0x14000a3da  mov     rcx, [rdi]
0x14000a3dd  lea     rdx, [rsp+28h+arg_8]
0x14000a3e2  mov     [rsp+28h+arg_8], rbx
0x14000a3e7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000a3ec  test    eax, eax
0x14000a3ee  js      short loc_14000A3FF
0x14000a3f0  cmp     [rdi+8], rbx
0x14000a3f4  jnz     short loc_14000A3FF
0x14000a3f6  mov     rax, [rsp+28h+arg_8]
0x14000a3fb  mov     [rdi+8], rax
0x14000a3ff  mov     rax, [rdi+8]
0x14000a403  lea     rcx, [rax+20h]
0x14000a407  neg     rax
0x14000a40a  sbb     rdi, rdi
0x14000a40d  and     rdi, rcx
0x14000a410  jz      short loc_14000A452
0x14000a412  call    cs:__imp_GetCurrentThreadId
0x14000a418  mov     r8d, eax
0x14000a41b  mov     r9d, eax
0x14000a41e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a428  shr     r8, 2
0x14000a42c  mul     r8
0x14000a42f  shr     rdx, 3
0x14000a433  lea     rcx, [rdx+rdx*4]
0x14000a437  add     rcx, rcx
0x14000a43a  sub     r8, rcx
0x14000a43d  mov     rbx, [rdi+r8*8+8]
0x14000a442  jmp     short loc_14000A44D
0x14000a444  cmp     [rbx], r9d
0x14000a447  jz      short loc_14000A460
0x14000a449  mov     rbx, [rbx+8]
0x14000a44d  test    rbx, rbx
0x14000a450  jnz     short loc_14000A444
0x14000a452  mov     rax, rbx
0x14000a455  mov     rbx, [rsp+28h+arg_0]
0x14000a45a  add     rsp, 20h
0x14000a45e  pop     rdi
0x14000a45f  retn
0x14000a460  add     rbx, 10h
0x14000a464  jz      short loc_14000A452
0x14000a466  cmp     qword ptr [rbx+8], 0
0x14000a46b  jnz     short loc_14000A452
0x14000a46d  lea     rax, [rdi+4]
0x14000a471  mov     [rbx+8], rax
0x14000a475  jmp     short loc_14000A452
```
