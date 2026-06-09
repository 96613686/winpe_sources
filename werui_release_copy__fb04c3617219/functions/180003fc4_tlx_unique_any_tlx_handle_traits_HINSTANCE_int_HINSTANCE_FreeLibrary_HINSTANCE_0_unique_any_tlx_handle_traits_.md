# tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)

- ea: `0x180003fc4`
- end: `0x180003fdb`
- name: `??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000438c`
- `0x180004488`
- `0x180006bdc`
- `0x18000afd8`
- `0x18000c268`
- `0x18000d114`
- `0x180013f10`
- `0x1800144b4`
- `0x180017118`
- `0x18001712a`
- `0x1800171b2`
- `0x18001733e`
- `0x180017460`

## callees

- `0x180003fc4`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180003fd0`
- `KERNEL32!FreeLibrary` at `0x180003fd0`

## pseudocode

```c
BOOL __fastcall tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(
        HMODULE *a1)
{
  HMODULE v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return FreeLibrary(v1);
  return result;
}

```

## disassembly

```asm
0x180003fc4  sub     rsp, 28h
0x180003fc8  mov     rcx, [rcx]; hLibModule
0x180003fcb  test    rcx, rcx
0x180003fce  jz      short loc_180003FD6
0x180003fd0  call    cs:__imp_FreeLibrary
0x180003fd6  add     rsp, 28h
0x180003fda  retn
```
