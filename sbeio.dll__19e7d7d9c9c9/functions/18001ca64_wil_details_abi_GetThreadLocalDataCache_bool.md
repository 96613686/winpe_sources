# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001ca64`
- end: `0x18001cab4`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `80`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bae0`

## callees

- `0x18001c6f4`
- `0x18001c8c4`
- `0x18001ca64`

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
0x18001ca64  mov     [rsp+arg_0], rbx
0x18001ca69  push    rdi
0x18001ca6a  sub     rsp, 20h
0x18001ca6e  xor     ebx, ebx
0x18001ca70  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001ca77  jz      short loc_18001CAA6
0x18001ca79  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x18001ca7e  mov     rdi, rax
0x18001ca81  test    rax, rax
0x18001ca84  jz      short loc_18001CAA6
0x18001ca86  lea     rcx, [rax+8]
0x18001ca8a  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x18001ca8f  mov     rbx, rax
0x18001ca92  test    rax, rax
0x18001ca95  jz      short loc_18001CAA6
0x18001ca97  cmp     qword ptr [rax+8], 0
0x18001ca9c  jnz     short loc_18001CAA6
0x18001ca9e  lea     rcx, [rdi+4]
0x18001caa2  mov     [rax+8], rcx
0x18001caa6  mov     rax, rbx
0x18001caa9  mov     rbx, [rsp+28h+arg_0]
0x18001caae  add     rsp, 20h
0x18001cab2  pop     rdi
0x18001cab3  retn
```
