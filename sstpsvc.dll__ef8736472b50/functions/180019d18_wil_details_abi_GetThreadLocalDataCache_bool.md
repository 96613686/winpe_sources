# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180019d18`
- end: `0x180019d69`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `81`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019550`

## callees

- `0x1800199ec`
- `0x180019b40`
- `0x180019d18`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 Shared; // rax
  __int64 v3; // rdi
  __int64 Local; // rax

  v1 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(this);
    v3 = Shared;
    if ( Shared )
    {
      Local = wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(Shared + 8);
      v1 = Local;
      if ( Local )
      {
        if ( !*(_QWORD *)(Local + 8) )
          *(_QWORD *)(Local + 8) = v3 + 4;
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v1;
}

```

## disassembly

```asm
0x180019d18  mov     [rsp+arg_0], rbx
0x180019d1d  push    rdi
0x180019d1e  sub     rsp, 20h
0x180019d22  xor     ebx, ebx
0x180019d24  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180019d2b  jz      short loc_180019D5A
0x180019d2d  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x180019d32  mov     rdi, rax
0x180019d35  test    rax, rax
0x180019d38  jz      short loc_180019D5A
0x180019d3a  lea     rcx, [rax+8]
0x180019d3e  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x180019d43  mov     rbx, rax
0x180019d46  test    rax, rax
0x180019d49  jz      short loc_180019D5A
0x180019d4b  cmp     qword ptr [rax+8], 0
0x180019d50  jnz     short loc_180019D5A
0x180019d52  lea     rcx, [rdi+4]
0x180019d56  mov     [rax+8], rcx
0x180019d5a  mov     rax, rbx
0x180019d5d  mov     rbx, [rsp+28h+arg_0]
0x180019d62  add     rsp, 20h
0x180019d66  pop     rdi
0x180019d67  retn
```
