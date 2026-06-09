# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000c690`
- end: `0x18000c74b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b7f0`

## callees

- `0x18000988c`
- `0x18000c690`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c6e6`
- `KERNEL32!GetCurrentThreadId` at `0x18000c6e6`

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
0x18000c690  mov     [rsp+arg_0], rbx
0x18000c695  push    rdi
0x18000c696  sub     rsp, 20h
0x18000c69a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000c6a1  xor     ebx, ebx
0x18000c6a3  test    rdi, rdi
0x18000c6a6  jz      short loc_18000C726
0x18000c6a8  cmp     [rdi+8], rbx
0x18000c6ac  jnz     short loc_18000C6D3
0x18000c6ae  mov     rcx, [rdi]
0x18000c6b1  lea     rdx, [rsp+28h+arg_8]
0x18000c6b6  mov     [rsp+28h+arg_8], rbx
0x18000c6bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000c6c0  test    eax, eax
0x18000c6c2  js      short loc_18000C6D3
0x18000c6c4  cmp     [rdi+8], rbx
0x18000c6c8  jnz     short loc_18000C6D3
0x18000c6ca  mov     rax, [rsp+28h+arg_8]
0x18000c6cf  mov     [rdi+8], rax
0x18000c6d3  mov     rax, [rdi+8]
0x18000c6d7  lea     rcx, [rax+20h]
0x18000c6db  neg     rax
0x18000c6de  sbb     rdi, rdi
0x18000c6e1  and     rdi, rcx
0x18000c6e4  jz      short loc_18000C726
0x18000c6e6  call    cs:__imp_GetCurrentThreadId
0x18000c6ec  mov     r8d, eax
0x18000c6ef  mov     r9d, eax
0x18000c6f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c6fc  shr     r8, 2
0x18000c700  mul     r8
0x18000c703  shr     rdx, 3
0x18000c707  lea     rcx, [rdx+rdx*4]
0x18000c70b  add     rcx, rcx
0x18000c70e  sub     r8, rcx
0x18000c711  mov     rbx, [rdi+r8*8+8]
0x18000c716  jmp     short loc_18000C721
0x18000c718  cmp     [rbx], r9d
0x18000c71b  jz      short loc_18000C734
0x18000c71d  mov     rbx, [rbx+8]
0x18000c721  test    rbx, rbx
0x18000c724  jnz     short loc_18000C718
0x18000c726  mov     rax, rbx
0x18000c729  mov     rbx, [rsp+28h+arg_0]
0x18000c72e  add     rsp, 20h
0x18000c732  pop     rdi
0x18000c733  retn
0x18000c734  add     rbx, 10h
0x18000c738  jz      short loc_18000C726
0x18000c73a  cmp     qword ptr [rbx+8], 0
0x18000c73f  jnz     short loc_18000C726
0x18000c741  lea     rax, [rdi+4]
0x18000c745  mov     [rbx+8], rax
0x18000c749  jmp     short loc_18000C726
```
