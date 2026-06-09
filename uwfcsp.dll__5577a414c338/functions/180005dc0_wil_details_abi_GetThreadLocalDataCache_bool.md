# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005dc0`
- end: `0x180005e7b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005600`

## callees

- `0x180004f1c`
- `0x180005dc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e16`

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
0x180005dc0  mov     [rsp+arg_0], rbx
0x180005dc5  push    rdi
0x180005dc6  sub     rsp, 20h
0x180005dca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005dd1  xor     ebx, ebx
0x180005dd3  test    rdi, rdi
0x180005dd6  jz      short loc_180005E56
0x180005dd8  cmp     [rdi+8], rbx
0x180005ddc  jnz     short loc_180005E03
0x180005dde  mov     rcx, [rdi]
0x180005de1  lea     rdx, [rsp+28h+arg_8]
0x180005de6  mov     [rsp+28h+arg_8], rbx
0x180005deb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005df0  test    eax, eax
0x180005df2  js      short loc_180005E03
0x180005df4  cmp     [rdi+8], rbx
0x180005df8  jnz     short loc_180005E03
0x180005dfa  mov     rax, [rsp+28h+arg_8]
0x180005dff  mov     [rdi+8], rax
0x180005e03  mov     rax, [rdi+8]
0x180005e07  lea     rcx, [rax+20h]
0x180005e0b  neg     rax
0x180005e0e  sbb     rdi, rdi
0x180005e11  and     rdi, rcx
0x180005e14  jz      short loc_180005E56
0x180005e16  call    cs:__imp_GetCurrentThreadId
0x180005e1c  mov     r8d, eax
0x180005e1f  mov     r9d, eax
0x180005e22  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005e2c  shr     r8, 2
0x180005e30  mul     r8
0x180005e33  shr     rdx, 3
0x180005e37  lea     rcx, [rdx+rdx*4]
0x180005e3b  add     rcx, rcx
0x180005e3e  sub     r8, rcx
0x180005e41  mov     rbx, [rdi+r8*8+8]
0x180005e46  jmp     short loc_180005E51
0x180005e48  cmp     [rbx], r9d
0x180005e4b  jz      short loc_180005E64
0x180005e4d  mov     rbx, [rbx+8]
0x180005e51  test    rbx, rbx
0x180005e54  jnz     short loc_180005E48
0x180005e56  mov     rax, rbx
0x180005e59  mov     rbx, [rsp+28h+arg_0]
0x180005e5e  add     rsp, 20h
0x180005e62  pop     rdi
0x180005e63  retn
0x180005e64  add     rbx, 10h
0x180005e68  jz      short loc_180005E56
0x180005e6a  cmp     qword ptr [rbx+8], 0
0x180005e6f  jnz     short loc_180005E56
0x180005e71  lea     rax, [rdi+4]
0x180005e75  mov     [rbx+8], rax
0x180005e79  jmp     short loc_180005E56
```
