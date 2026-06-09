# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006cb4`
- end: `0x180006d71`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006720`

## callees

- `0x1800059e8`
- `0x180006cb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d0e`

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
0x180006cb4  mov     [rsp+arg_0], rbx
0x180006cb9  push    rdi
0x180006cba  sub     rsp, 20h
0x180006cbe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006cc5  xor     ebx, ebx
0x180006cc7  test    rdi, rdi
0x180006cca  jz      loc_180006D63
0x180006cd0  cmp     [rdi+8], rbx
0x180006cd4  jnz     short loc_180006CFB
0x180006cd6  mov     rcx, [rdi]
0x180006cd9  lea     rdx, [rsp+28h+arg_8]
0x180006cde  mov     [rsp+28h+arg_8], rbx
0x180006ce3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006ce8  test    eax, eax
0x180006cea  js      short loc_180006CFB
0x180006cec  cmp     [rdi+8], rbx
0x180006cf0  jnz     short loc_180006CFB
0x180006cf2  mov     rax, [rsp+28h+arg_8]
0x180006cf7  mov     [rdi+8], rax
0x180006cfb  mov     rax, [rdi+8]
0x180006cff  lea     rcx, [rax+20h]
0x180006d03  neg     rax
0x180006d06  sbb     rdi, rdi
0x180006d09  and     rdi, rcx
0x180006d0c  jz      short loc_180006D63
0x180006d0e  call    cs:__imp_GetCurrentThreadId
0x180006d14  mov     r8d, eax
0x180006d17  mov     r9d, eax
0x180006d1a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006d24  shr     r8, 2
0x180006d28  mul     r8
0x180006d2b  shr     rdx, 3
0x180006d2f  lea     rcx, [rdx+rdx*4]
0x180006d33  add     rcx, rcx
0x180006d36  sub     r8, rcx
0x180006d39  mov     rbx, [rdi+r8*8+8]
0x180006d3e  test    rbx, rbx
0x180006d41  jz      short loc_180006D63
0x180006d43  cmp     [rbx], r9d
0x180006d46  jz      short loc_180006D4E
0x180006d48  mov     rbx, [rbx+8]
0x180006d4c  jmp     short loc_180006D3E
0x180006d4e  add     rbx, 10h
0x180006d52  jz      short loc_180006D63
0x180006d54  cmp     qword ptr [rbx+8], 0
0x180006d59  jnz     short loc_180006D63
0x180006d5b  lea     rax, [rdi+4]
0x180006d5f  mov     [rbx+8], rax
0x180006d63  mov     rax, rbx
0x180006d66  mov     rbx, [rsp+28h+arg_0]
0x180006d6b  add     rsp, 20h
0x180006d6f  pop     rdi
0x180006d70  retn
```
