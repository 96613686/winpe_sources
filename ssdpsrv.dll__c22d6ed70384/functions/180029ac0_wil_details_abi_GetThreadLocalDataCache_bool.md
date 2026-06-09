# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180029ac0`
- end: `0x180029b7d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029550`

## callees

- `0x180028c3c`
- `0x180029ac0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029b1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029b1a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x180029ac0  mov     [rsp+arg_0], rbx
0x180029ac5  push    rdi
0x180029ac6  sub     rsp, 20h
0x180029aca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180029ad1  xor     ebx, ebx
0x180029ad3  test    rdi, rdi
0x180029ad6  jz      loc_180029B6F
0x180029adc  cmp     [rdi+8], rbx
0x180029ae0  jnz     short loc_180029B07
0x180029ae2  mov     rcx, [rdi]
0x180029ae5  lea     rdx, [rsp+28h+arg_8]
0x180029aea  mov     [rsp+28h+arg_8], rbx
0x180029aef  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180029af4  test    eax, eax
0x180029af6  js      short loc_180029B07
0x180029af8  cmp     [rdi+8], rbx
0x180029afc  jnz     short loc_180029B07
0x180029afe  mov     rax, [rsp+28h+arg_8]
0x180029b03  mov     [rdi+8], rax
0x180029b07  mov     rax, [rdi+8]
0x180029b0b  lea     rcx, [rax+20h]
0x180029b0f  neg     rax
0x180029b12  sbb     rdi, rdi
0x180029b15  and     rdi, rcx
0x180029b18  jz      short loc_180029B6F
0x180029b1a  call    cs:__imp_GetCurrentThreadId
0x180029b20  mov     r8d, eax
0x180029b23  mov     r9d, eax
0x180029b26  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180029b30  shr     r8, 2
0x180029b34  mul     r8
0x180029b37  shr     rdx, 3
0x180029b3b  lea     rcx, [rdx+rdx*4]
0x180029b3f  add     rcx, rcx
0x180029b42  sub     r8, rcx
0x180029b45  mov     rbx, [rdi+r8*8+8]
0x180029b4a  test    rbx, rbx
0x180029b4d  jz      short loc_180029B6F
0x180029b4f  cmp     [rbx], r9d
0x180029b52  jz      short loc_180029B5A
0x180029b54  mov     rbx, [rbx+8]
0x180029b58  jmp     short loc_180029B4A
0x180029b5a  add     rbx, 10h
0x180029b5e  jz      short loc_180029B6F
0x180029b60  cmp     qword ptr [rbx+8], 0
0x180029b65  jnz     short loc_180029B6F
0x180029b67  lea     rax, [rdi+4]
0x180029b6b  mov     [rbx+8], rax
0x180029b6f  mov     rax, rbx
0x180029b72  mov     rbx, [rsp+28h+arg_0]
0x180029b77  add     rsp, 20h
0x180029b7b  pop     rdi
0x180029b7c  retn
```
