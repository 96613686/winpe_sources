# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140001e50`
- end: `0x140001edd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `141`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001cc0`

## callees

- `0x140001e50`
- `0x140001ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001e72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001e72`

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
0x140001e50  mov     [rsp+arg_0], rbx
0x140001e55  push    rdi
0x140001e56  sub     rsp, 20h
0x140001e5a  xor     ebx, ebx
0x140001e5c  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140001e63  jz      short loc_140001EBD
0x140001e65  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x140001e6a  mov     rdi, rax
0x140001e6d  test    rax, rax
0x140001e70  jz      short loc_140001EBD
0x140001e72  call    cs:__imp_GetCurrentThreadId
0x140001e79  nop     dword ptr [rax+rax+00h]
0x140001e7e  mov     ecx, eax
0x140001e80  mov     r8d, eax
0x140001e83  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140001e8d  shr     rcx, 2
0x140001e91  mul     rcx
0x140001e94  shr     rdx, 3
0x140001e98  lea     rax, [rdx+rdx*4]
0x140001e9c  add     rax, rax
0x140001e9f  sub     rcx, rax
0x140001ea2  mov     rbx, [rdi+rcx*8+8]
0x140001ea7  test    rbx, rbx
0x140001eaa  jz      short loc_140001EBD
0x140001eac  cmp     [rbx], r8d
0x140001eaf  jz      short loc_140001EB7
0x140001eb1  mov     rbx, [rbx+8]
0x140001eb5  jmp     short loc_140001EA7
0x140001eb7  add     rbx, 10h
0x140001ebb  jnz     short loc_140001ECC
0x140001ebd  mov     rax, rbx
0x140001ec0  mov     rbx, [rsp+28h+arg_0]
0x140001ec5  add     rsp, 20h
0x140001ec9  pop     rdi
0x140001eca  retn
0x140001ecc  cmp     qword ptr [rbx+8], 0
0x140001ed1  jnz     short loc_140001EBD
0x140001ed3  lea     rax, [rdi+4]
0x140001ed7  mov     [rbx+8], rax
0x140001edb  jmp     short loc_140001EBD
```
