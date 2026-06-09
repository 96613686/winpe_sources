# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800188ec`
- end: `0x18001893c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `80`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018170`

## callees

- `0x1800185dc`
- `0x18001871c`
- `0x1800188ec`

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
0x1800188ec  mov     [rsp+arg_0], rbx
0x1800188f1  push    rdi
0x1800188f2  sub     rsp, 20h
0x1800188f6  xor     ebx, ebx
0x1800188f8  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800188ff  jz      short loc_18001892E
0x180018901  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x180018906  mov     rdi, rax
0x180018909  test    rax, rax
0x18001890c  jz      short loc_18001892E
0x18001890e  lea     rcx, [rax+8]
0x180018912  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x180018917  mov     rbx, rax
0x18001891a  test    rax, rax
0x18001891d  jz      short loc_18001892E
0x18001891f  cmp     qword ptr [rax+8], 0
0x180018924  jnz     short loc_18001892E
0x180018926  lea     rcx, [rdi+4]
0x18001892a  mov     [rax+8], rcx
0x18001892e  mov     rax, rbx
0x180018931  mov     rbx, [rsp+28h+arg_0]
0x180018936  add     rsp, 20h
0x18001893a  pop     rdi
0x18001893b  retn
```
