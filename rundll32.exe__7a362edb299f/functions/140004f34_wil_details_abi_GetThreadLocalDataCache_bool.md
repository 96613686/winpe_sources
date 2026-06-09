# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004f34`
- end: `0x140004fef`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046f0`

## callees

- `0x140003b94`
- `0x140004f34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004f8a`

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
0x140004f34  mov     [rsp+arg_0], rbx
0x140004f39  push    rdi
0x140004f3a  sub     rsp, 20h
0x140004f3e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004f45  xor     ebx, ebx
0x140004f47  test    rdi, rdi
0x140004f4a  jz      short loc_140004FCA
0x140004f4c  cmp     [rdi+8], rbx
0x140004f50  jnz     short loc_140004F77
0x140004f52  mov     rcx, [rdi]
0x140004f55  lea     rdx, [rsp+28h+arg_8]
0x140004f5a  mov     [rsp+28h+arg_8], rbx
0x140004f5f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004f64  test    eax, eax
0x140004f66  js      short loc_140004F77
0x140004f68  cmp     [rdi+8], rbx
0x140004f6c  jnz     short loc_140004F77
0x140004f6e  mov     rax, [rsp+28h+arg_8]
0x140004f73  mov     [rdi+8], rax
0x140004f77  mov     rax, [rdi+8]
0x140004f7b  lea     rcx, [rax+20h]
0x140004f7f  neg     rax
0x140004f82  sbb     rdi, rdi
0x140004f85  and     rdi, rcx
0x140004f88  jz      short loc_140004FCA
0x140004f8a  call    cs:__imp_GetCurrentThreadId
0x140004f90  mov     r8d, eax
0x140004f93  mov     r9d, eax
0x140004f96  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004fa0  shr     r8, 2
0x140004fa4  mul     r8
0x140004fa7  shr     rdx, 3
0x140004fab  lea     rcx, [rdx+rdx*4]
0x140004faf  add     rcx, rcx
0x140004fb2  sub     r8, rcx
0x140004fb5  mov     rbx, [rdi+r8*8+8]
0x140004fba  jmp     short loc_140004FC5
0x140004fbc  cmp     [rbx], r9d
0x140004fbf  jz      short loc_140004FD8
0x140004fc1  mov     rbx, [rbx+8]
0x140004fc5  test    rbx, rbx
0x140004fc8  jnz     short loc_140004FBC
0x140004fca  mov     rax, rbx
0x140004fcd  mov     rbx, [rsp+28h+arg_0]
0x140004fd2  add     rsp, 20h
0x140004fd6  pop     rdi
0x140004fd7  retn
0x140004fd8  add     rbx, 10h
0x140004fdc  jz      short loc_140004FCA
0x140004fde  cmp     qword ptr [rbx+8], 0
0x140004fe3  jnz     short loc_140004FCA
0x140004fe5  lea     rax, [rdi+4]
0x140004fe9  mov     [rbx+8], rax
0x140004fed  jmp     short loc_140004FCA
```
