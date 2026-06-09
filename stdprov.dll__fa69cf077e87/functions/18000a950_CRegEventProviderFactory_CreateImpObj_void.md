# CRegEventProviderFactory::CreateImpObj(void)

- ea: `0x18000a950`
- end: `0x18000a977`
- name: `?CreateImpObj@CRegEventProviderFactory@@UEAAPEAUIUnknown@@XZ`
- size: `39`
- prototype: `struct IUnknown *__fastcall(CRegEventProviderFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a950`
- `0x18000a980`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a959`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a959`

## pseudocode

```c
struct IUnknown *__fastcall CRegEventProviderFactory::CreateImpObj(CRegEventProviderFactory *this)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)CWin32DefaultArena::WbemMemAlloc(0x130u);
  if ( result )
    return (struct IUnknown *)CRegEventProvider::CRegEventProvider((CRegEventProvider *)result);
  return result;
}

```

## disassembly

```asm
0x18000a950  sub     rsp, 28h
0x18000a954  mov     ecx, 130h
0x18000a959  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a95f  mov     [rsp+28h+arg_8], rax
0x18000a964  test    rax, rax
0x18000a967  jz      short loc_18000A972
0x18000a969  mov     rcx, rax; this
0x18000a96c  call    ??0CRegEventProvider@@QEAA@XZ; CRegEventProvider::CRegEventProvider(void)
0x18000a971  nop
0x18000a972  add     rsp, 28h
0x18000a976  retn
```
