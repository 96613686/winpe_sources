# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800090cc`
- end: `0x18000911c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `80`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008950`

## callees

- `0x180008dbc`
- `0x180008efc`
- `0x1800090cc`

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
0x1800090cc  mov     [rsp+arg_0], rbx
0x1800090d1  push    rdi
0x1800090d2  sub     rsp, 20h
0x1800090d6  xor     ebx, ebx
0x1800090d8  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800090df  jz      short loc_18000910E
0x1800090e1  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x1800090e6  mov     rdi, rax
0x1800090e9  test    rax, rax
0x1800090ec  jz      short loc_18000910E
0x1800090ee  lea     rcx, [rax+8]
0x1800090f2  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x1800090f7  mov     rbx, rax
0x1800090fa  test    rax, rax
0x1800090fd  jz      short loc_18000910E
0x1800090ff  cmp     qword ptr [rax+8], 0
0x180009104  jnz     short loc_18000910E
0x180009106  lea     rcx, [rdi+4]
0x18000910a  mov     [rax+8], rcx
0x18000910e  mov     rax, rbx
0x180009111  mov     rbx, [rsp+28h+arg_0]
0x180009116  add     rsp, 20h
0x18000911a  pop     rdi
0x18000911b  retn
```
