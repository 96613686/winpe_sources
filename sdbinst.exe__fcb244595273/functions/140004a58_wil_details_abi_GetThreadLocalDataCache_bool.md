# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004a58`
- end: `0x140004b13`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004190`

## callees

- `0x140003410`
- `0x140004a58`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004aae`
- `KERNEL32!GetCurrentThreadId` at `0x140004aae`

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
0x140004a58  mov     [rsp+arg_0], rbx
0x140004a5d  push    rdi
0x140004a5e  sub     rsp, 20h
0x140004a62  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004a69  xor     ebx, ebx
0x140004a6b  test    rdi, rdi
0x140004a6e  jz      short loc_140004AEE
0x140004a70  cmp     [rdi+8], rbx
0x140004a74  jnz     short loc_140004A9B
0x140004a76  mov     rcx, [rdi]
0x140004a79  lea     rdx, [rsp+28h+arg_8]
0x140004a7e  mov     [rsp+28h+arg_8], rbx
0x140004a83  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004a88  test    eax, eax
0x140004a8a  js      short loc_140004A9B
0x140004a8c  cmp     [rdi+8], rbx
0x140004a90  jnz     short loc_140004A9B
0x140004a92  mov     rax, [rsp+28h+arg_8]
0x140004a97  mov     [rdi+8], rax
0x140004a9b  mov     rax, [rdi+8]
0x140004a9f  lea     rcx, [rax+20h]
0x140004aa3  neg     rax
0x140004aa6  sbb     rdi, rdi
0x140004aa9  and     rdi, rcx
0x140004aac  jz      short loc_140004AEE
0x140004aae  call    cs:__imp_GetCurrentThreadId
0x140004ab4  mov     r8d, eax
0x140004ab7  mov     r9d, eax
0x140004aba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004ac4  shr     r8, 2
0x140004ac8  mul     r8
0x140004acb  shr     rdx, 3
0x140004acf  lea     rcx, [rdx+rdx*4]
0x140004ad3  add     rcx, rcx
0x140004ad6  sub     r8, rcx
0x140004ad9  mov     rbx, [rdi+r8*8+8]
0x140004ade  jmp     short loc_140004AE9
0x140004ae0  cmp     [rbx], r9d
0x140004ae3  jz      short loc_140004AFC
0x140004ae5  mov     rbx, [rbx+8]
0x140004ae9  test    rbx, rbx
0x140004aec  jnz     short loc_140004AE0
0x140004aee  mov     rax, rbx
0x140004af1  mov     rbx, [rsp+28h+arg_0]
0x140004af6  add     rsp, 20h
0x140004afa  pop     rdi
0x140004afb  retn
0x140004afc  add     rbx, 10h
0x140004b00  jz      short loc_140004AEE
0x140004b02  cmp     qword ptr [rbx+8], 0
0x140004b07  jnz     short loc_140004AEE
0x140004b09  lea     rax, [rdi+4]
0x140004b0d  mov     [rbx+8], rax
0x140004b11  jmp     short loc_140004AEE
```
