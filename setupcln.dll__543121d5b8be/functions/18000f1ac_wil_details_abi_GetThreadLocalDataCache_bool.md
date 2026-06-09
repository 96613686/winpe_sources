# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000f1ac`
- end: `0x18000f1fc`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `80`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e7e0`

## callees

- `0x18000ec4c`
- `0x18000efdc`
- `0x18000f1ac`

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
0x18000f1ac  mov     [rsp+arg_0], rbx
0x18000f1b1  push    rdi
0x18000f1b2  sub     rsp, 20h
0x18000f1b6  xor     ebx, ebx
0x18000f1b8  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000f1bf  jz      short loc_18000F1EE
0x18000f1c1  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x18000f1c6  mov     rdi, rax
0x18000f1c9  test    rax, rax
0x18000f1cc  jz      short loc_18000F1EE
0x18000f1ce  lea     rcx, [rax+8]
0x18000f1d2  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x18000f1d7  mov     rbx, rax
0x18000f1da  test    rax, rax
0x18000f1dd  jz      short loc_18000F1EE
0x18000f1df  cmp     qword ptr [rax+8], 0
0x18000f1e4  jnz     short loc_18000F1EE
0x18000f1e6  lea     rcx, [rdi+4]
0x18000f1ea  mov     [rax+8], rcx
0x18000f1ee  mov     rax, rbx
0x18000f1f1  mov     rbx, [rsp+28h+arg_0]
0x18000f1f6  add     rsp, 20h
0x18000f1fa  pop     rdi
0x18000f1fb  retn
```
