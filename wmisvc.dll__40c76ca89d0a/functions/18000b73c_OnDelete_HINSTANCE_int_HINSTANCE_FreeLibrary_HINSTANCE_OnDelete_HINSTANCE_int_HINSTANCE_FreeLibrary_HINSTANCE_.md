# OnDelete<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *)>::~OnDelete<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *)>(void)

- ea: `0x18000b73c`
- end: `0x18000b74f`
- name: `??1?$OnDelete@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z@@QEAA@XZ`
- size: `19`
- prototype: `BOOL __fastcall(HMODULE *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001df50`
- `0x18001df62`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b743`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b743`

## pseudocode

```c
BOOL __fastcall OnDelete<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *)>::~OnDelete<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *)>(
        HMODULE *a1)
{
  return FreeLibrary(*a1);
}

```

## disassembly

```asm
0x18000b73c  sub     rsp, 28h
0x18000b740  mov     rcx, [rcx]; hLibModule
0x18000b743  call    cs:__imp_FreeLibrary
0x18000b749  nop
0x18000b74a  add     rsp, 28h
0x18000b74e  retn
```
