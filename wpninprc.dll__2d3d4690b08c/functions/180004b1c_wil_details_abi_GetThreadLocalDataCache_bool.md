# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004b1c`
- end: `0x180004bd7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004720`

## callees

- `0x180004144`
- `0x180004b1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b72`

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
0x180004b1c  mov     [rsp+arg_0], rbx
0x180004b21  push    rdi
0x180004b22  sub     rsp, 20h
0x180004b26  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004b2d  xor     ebx, ebx
0x180004b2f  test    rdi, rdi
0x180004b32  jz      short loc_180004BB2
0x180004b34  cmp     [rdi+8], rbx
0x180004b38  jnz     short loc_180004B5F
0x180004b3a  mov     rcx, [rdi]
0x180004b3d  lea     rdx, [rsp+28h+arg_8]
0x180004b42  mov     [rsp+28h+arg_8], rbx
0x180004b47  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004b4c  test    eax, eax
0x180004b4e  js      short loc_180004B5F
0x180004b50  cmp     [rdi+8], rbx
0x180004b54  jnz     short loc_180004B5F
0x180004b56  mov     rax, [rsp+28h+arg_8]
0x180004b5b  mov     [rdi+8], rax
0x180004b5f  mov     rax, [rdi+8]
0x180004b63  lea     rcx, [rax+20h]
0x180004b67  neg     rax
0x180004b6a  sbb     rdi, rdi
0x180004b6d  and     rdi, rcx
0x180004b70  jz      short loc_180004BB2
0x180004b72  call    cs:__imp_GetCurrentThreadId
0x180004b78  mov     r8d, eax
0x180004b7b  mov     r9d, eax
0x180004b7e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004b88  shr     r8, 2
0x180004b8c  mul     r8
0x180004b8f  shr     rdx, 3
0x180004b93  lea     rcx, [rdx+rdx*4]
0x180004b97  add     rcx, rcx
0x180004b9a  sub     r8, rcx
0x180004b9d  mov     rbx, [rdi+r8*8+8]
0x180004ba2  jmp     short loc_180004BAD
0x180004ba4  cmp     [rbx], r9d
0x180004ba7  jz      short loc_180004BC0
0x180004ba9  mov     rbx, [rbx+8]
0x180004bad  test    rbx, rbx
0x180004bb0  jnz     short loc_180004BA4
0x180004bb2  mov     rax, rbx
0x180004bb5  mov     rbx, [rsp+28h+arg_0]
0x180004bba  add     rsp, 20h
0x180004bbe  pop     rdi
0x180004bbf  retn
0x180004bc0  add     rbx, 10h
0x180004bc4  jz      short loc_180004BB2
0x180004bc6  cmp     qword ptr [rbx+8], 0
0x180004bcb  jnz     short loc_180004BB2
0x180004bcd  lea     rax, [rdi+4]
0x180004bd1  mov     [rbx+8], rax
0x180004bd5  jmp     short loc_180004BB2
```
