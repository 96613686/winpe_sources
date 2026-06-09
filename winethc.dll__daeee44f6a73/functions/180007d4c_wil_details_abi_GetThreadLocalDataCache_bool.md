# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007d4c`
- end: `0x180007e12`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054e0`

## callees

- `0x180003548`
- `0x180007d4c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007da6`
- `KERNEL32!GetCurrentThreadId` at `0x180007da6`

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
0x180007d4c  mov     [rsp+arg_0], rbx
0x180007d51  push    rdi
0x180007d52  sub     rsp, 20h
0x180007d56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007d5d  xor     ebx, ebx
0x180007d5f  test    rdi, rdi
0x180007d62  jz      loc_180007DEC
0x180007d68  cmp     [rdi+8], rbx
0x180007d6c  jnz     short loc_180007D93
0x180007d6e  mov     rcx, [rdi]
0x180007d71  lea     rdx, [rsp+28h+arg_8]
0x180007d76  mov     [rsp+28h+arg_8], rbx
0x180007d7b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007d80  test    eax, eax
0x180007d82  js      short loc_180007D93
0x180007d84  cmp     [rdi+8], rbx
0x180007d88  jnz     short loc_180007D93
0x180007d8a  mov     rax, [rsp+28h+arg_8]
0x180007d8f  mov     [rdi+8], rax
0x180007d93  mov     rax, [rdi+8]
0x180007d97  lea     rcx, [rax+20h]
0x180007d9b  neg     rax
0x180007d9e  sbb     rdi, rdi
0x180007da1  and     rdi, rcx
0x180007da4  jz      short loc_180007DEC
0x180007da6  call    cs:__imp_GetCurrentThreadId
0x180007dad  nop     dword ptr [rax+rax+00h]
0x180007db2  mov     r8d, eax
0x180007db5  mov     r9d, eax
0x180007db8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007dc2  shr     r8, 2
0x180007dc6  mul     r8
0x180007dc9  shr     rdx, 3
0x180007dcd  lea     rcx, [rdx+rdx*4]
0x180007dd1  add     rcx, rcx
0x180007dd4  sub     r8, rcx
0x180007dd7  mov     rbx, [rdi+r8*8+8]
0x180007ddc  jmp     short loc_180007DE7
0x180007dde  cmp     [rbx], r9d
0x180007de1  jz      short loc_180007DFB
0x180007de3  mov     rbx, [rbx+8]
0x180007de7  test    rbx, rbx
0x180007dea  jnz     short loc_180007DDE
0x180007dec  mov     rax, rbx
0x180007def  mov     rbx, [rsp+28h+arg_0]
0x180007df4  add     rsp, 20h
0x180007df8  pop     rdi
0x180007df9  retn
0x180007dfb  add     rbx, 10h
0x180007dff  jz      short loc_180007DEC
0x180007e01  cmp     qword ptr [rbx+8], 0
0x180007e06  jnz     short loc_180007DEC
0x180007e08  lea     rax, [rdi+4]
0x180007e0c  mov     [rbx+8], rax
0x180007e10  jmp     short loc_180007DEC
```
