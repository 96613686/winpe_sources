# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004ef0`
- end: `0x180004fab`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004710`

## callees

- `0x180003f78`
- `0x180004ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f46`

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
0x180004ef0  mov     [rsp+arg_0], rbx
0x180004ef5  push    rdi
0x180004ef6  sub     rsp, 20h
0x180004efa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004f01  xor     ebx, ebx
0x180004f03  test    rdi, rdi
0x180004f06  jz      short loc_180004F86
0x180004f08  cmp     [rdi+8], rbx
0x180004f0c  jnz     short loc_180004F33
0x180004f0e  mov     rcx, [rdi]
0x180004f11  lea     rdx, [rsp+28h+arg_8]
0x180004f16  mov     [rsp+28h+arg_8], rbx
0x180004f1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004f20  test    eax, eax
0x180004f22  js      short loc_180004F33
0x180004f24  cmp     [rdi+8], rbx
0x180004f28  jnz     short loc_180004F33
0x180004f2a  mov     rax, [rsp+28h+arg_8]
0x180004f2f  mov     [rdi+8], rax
0x180004f33  mov     rax, [rdi+8]
0x180004f37  lea     rcx, [rax+20h]
0x180004f3b  neg     rax
0x180004f3e  sbb     rdi, rdi
0x180004f41  and     rdi, rcx
0x180004f44  jz      short loc_180004F86
0x180004f46  call    cs:__imp_GetCurrentThreadId
0x180004f4c  mov     r8d, eax
0x180004f4f  mov     r9d, eax
0x180004f52  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004f5c  shr     r8, 2
0x180004f60  mul     r8
0x180004f63  shr     rdx, 3
0x180004f67  lea     rcx, [rdx+rdx*4]
0x180004f6b  add     rcx, rcx
0x180004f6e  sub     r8, rcx
0x180004f71  mov     rbx, [rdi+r8*8+8]
0x180004f76  jmp     short loc_180004F81
0x180004f78  cmp     [rbx], r9d
0x180004f7b  jz      short loc_180004F94
0x180004f7d  mov     rbx, [rbx+8]
0x180004f81  test    rbx, rbx
0x180004f84  jnz     short loc_180004F78
0x180004f86  mov     rax, rbx
0x180004f89  mov     rbx, [rsp+28h+arg_0]
0x180004f8e  add     rsp, 20h
0x180004f92  pop     rdi
0x180004f93  retn
0x180004f94  add     rbx, 10h
0x180004f98  jz      short loc_180004F86
0x180004f9a  cmp     qword ptr [rbx+8], 0
0x180004f9f  jnz     short loc_180004F86
0x180004fa1  lea     rax, [rdi+4]
0x180004fa5  mov     [rbx+8], rax
0x180004fa9  jmp     short loc_180004F86
```
