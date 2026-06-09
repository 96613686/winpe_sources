# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140001d9c`
- end: `0x140001e22`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `134`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001c20`

## callees

- `0x140001d9c`
- `0x140001e30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001dbe`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 Shared; // rdi
  DWORD CurrentThreadId; // r8d

  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared();
    if ( Shared )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(Shared + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = Shared + 4;
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
0x140001d9c  mov     [rsp+arg_0], rbx
0x140001da1  push    rdi
0x140001da2  sub     rsp, 20h
0x140001da6  xor     ebx, ebx
0x140001da8  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140001daf  jz      short loc_140001E03
0x140001db1  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x140001db6  mov     rdi, rax
0x140001db9  test    rax, rax
0x140001dbc  jz      short loc_140001E03
0x140001dbe  call    cs:__imp_GetCurrentThreadId
0x140001dc4  mov     ecx, eax
0x140001dc6  mov     r8d, eax
0x140001dc9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140001dd3  shr     rcx, 2
0x140001dd7  mul     rcx
0x140001dda  shr     rdx, 3
0x140001dde  lea     rax, [rdx+rdx*4]
0x140001de2  add     rax, rax
0x140001de5  sub     rcx, rax
0x140001de8  mov     rbx, [rdi+rcx*8+8]
0x140001ded  test    rbx, rbx
0x140001df0  jz      short loc_140001E03
0x140001df2  cmp     [rbx], r8d
0x140001df5  jz      short loc_140001DFD
0x140001df7  mov     rbx, [rbx+8]
0x140001dfb  jmp     short loc_140001DED
0x140001dfd  add     rbx, 10h
0x140001e01  jnz     short loc_140001E11
0x140001e03  mov     rax, rbx
0x140001e06  mov     rbx, [rsp+28h+arg_0]
0x140001e0b  add     rsp, 20h
0x140001e0f  pop     rdi
0x140001e10  retn
0x140001e11  cmp     qword ptr [rbx+8], 0
0x140001e16  jnz     short loc_140001E03
0x140001e18  lea     rax, [rdi+4]
0x140001e1c  mov     [rbx+8], rax
0x140001e20  jmp     short loc_140001E03
```
