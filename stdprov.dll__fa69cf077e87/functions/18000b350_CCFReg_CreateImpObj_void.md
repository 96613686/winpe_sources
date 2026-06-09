# CCFReg::CreateImpObj(void)

- ea: `0x18000b350`
- end: `0x18000b377`
- name: `?CreateImpObj@CCFReg@@UEAAPEAUIUnknown@@XZ`
- size: `39`
- prototype: `struct IUnknown *__fastcall(CCFReg *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b350`
- `0x18000b630`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b359`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b359`

## pseudocode

```c
struct IUnknown *__fastcall CCFReg::CreateImpObj(CCFReg *this)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)CWin32DefaultArena::WbemMemAlloc(0xC8u);
  if ( result )
    return (struct IUnknown *)CImpReg::CImpReg((CImpReg *)result);
  return result;
}

```

## disassembly

```asm
0x18000b350  sub     rsp, 28h
0x18000b354  mov     ecx, 0C8h
0x18000b359  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000b35f  mov     [rsp+28h+arg_8], rax
0x18000b364  test    rax, rax
0x18000b367  jz      short loc_18000B372
0x18000b369  mov     rcx, rax; this
0x18000b36c  call    ??0CImpReg@@QEAA@XZ; CImpReg::CImpReg(void)
0x18000b371  nop
0x18000b372  add     rsp, 28h
0x18000b376  retn
```
