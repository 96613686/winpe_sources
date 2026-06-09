# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400049d0`
- end: `0x140004a8b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004280`

## callees

- `0x140003bd0`
- `0x1400049d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004a26`
- `KERNEL32!GetCurrentThreadId` at `0x140004a26`

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
0x1400049d0  mov     [rsp+arg_0], rbx
0x1400049d5  push    rdi
0x1400049d6  sub     rsp, 20h
0x1400049da  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400049e1  xor     ebx, ebx
0x1400049e3  test    rdi, rdi
0x1400049e6  jz      short loc_140004A66
0x1400049e8  cmp     [rdi+8], rbx
0x1400049ec  jnz     short loc_140004A13
0x1400049ee  mov     rcx, [rdi]
0x1400049f1  lea     rdx, [rsp+28h+arg_8]
0x1400049f6  mov     [rsp+28h+arg_8], rbx
0x1400049fb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004a00  test    eax, eax
0x140004a02  js      short loc_140004A13
0x140004a04  cmp     [rdi+8], rbx
0x140004a08  jnz     short loc_140004A13
0x140004a0a  mov     rax, [rsp+28h+arg_8]
0x140004a0f  mov     [rdi+8], rax
0x140004a13  mov     rax, [rdi+8]
0x140004a17  lea     rcx, [rax+20h]
0x140004a1b  neg     rax
0x140004a1e  sbb     rdi, rdi
0x140004a21  and     rdi, rcx
0x140004a24  jz      short loc_140004A66
0x140004a26  call    cs:__imp_GetCurrentThreadId
0x140004a2c  mov     r8d, eax
0x140004a2f  mov     r9d, eax
0x140004a32  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004a3c  shr     r8, 2
0x140004a40  mul     r8
0x140004a43  shr     rdx, 3
0x140004a47  lea     rcx, [rdx+rdx*4]
0x140004a4b  add     rcx, rcx
0x140004a4e  sub     r8, rcx
0x140004a51  mov     rbx, [rdi+r8*8+8]
0x140004a56  jmp     short loc_140004A61
0x140004a58  cmp     [rbx], r9d
0x140004a5b  jz      short loc_140004A74
0x140004a5d  mov     rbx, [rbx+8]
0x140004a61  test    rbx, rbx
0x140004a64  jnz     short loc_140004A58
0x140004a66  mov     rax, rbx
0x140004a69  mov     rbx, [rsp+28h+arg_0]
0x140004a6e  add     rsp, 20h
0x140004a72  pop     rdi
0x140004a73  retn
0x140004a74  add     rbx, 10h
0x140004a78  jz      short loc_140004A66
0x140004a7a  cmp     qword ptr [rbx+8], 0
0x140004a7f  jnz     short loc_140004A66
0x140004a81  lea     rax, [rdi+4]
0x140004a85  mov     [rbx+8], rax
0x140004a89  jmp     short loc_140004A66
```
