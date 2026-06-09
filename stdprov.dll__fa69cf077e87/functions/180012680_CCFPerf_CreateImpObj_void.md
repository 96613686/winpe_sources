# CCFPerf::CreateImpObj(void)

- ea: `0x180012680`
- end: `0x1800126a7`
- name: `?CreateImpObj@CCFPerf@@UEAAPEAUIUnknown@@XZ`
- size: `39`
- prototype: `struct IUnknown *__fastcall(CCFPerf *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f914`
- `0x180012680`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180012689`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180012689`

## pseudocode

```c
struct IUnknown *__fastcall CCFPerf::CreateImpObj(CCFPerf *this)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)CWin32DefaultArena::WbemMemAlloc(0x2B0u);
  if ( result )
    return (struct IUnknown *)CImpPerf::CImpPerf((CImpPerf *)result);
  return result;
}

```

## disassembly

```asm
0x180012680  sub     rsp, 28h
0x180012684  mov     ecx, 2B0h
0x180012689  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001268f  mov     [rsp+28h+arg_8], rax
0x180012694  test    rax, rax
0x180012697  jz      short loc_1800126A2
0x180012699  mov     rcx, rax; this
0x18001269c  call    ??0CImpPerf@@QEAA@XZ; CImpPerf::CImpPerf(void)
0x1800126a1  nop
0x1800126a2  add     rsp, 28h
0x1800126a6  retn
```
