# _provLoadDLL(ushort *,HINSTANCE__ * *)

- ea: `0x18000ed7c`
- end: `0x18000ede3`
- name: `?_provLoadDLL@@YAHPEAGPEAPEAUHINSTANCE__@@@Z`
- size: `103`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpLibFileName, HINSTANCE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e4e0`

## callees

- `0x18000ed7c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000eda2`
- `msvcrt!_wcsicmp` at `0x18000eda2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000edd5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000edd5`

## string_xrefs

- `0x18000ed9b`: `WINTRUST.DLL`

## pseudocode

```c
_BOOL8 __fastcall _provLoadDLL(LPCWSTR lpLibFileName, HINSTANCE *a2)
{
  HMODULE LibraryW; // rcx

  *a2 = 0;
  if ( !*lpLibFileName )
    return 0;
  if ( _wcsicmp(lpLibFileName, L"WINTRUST.DLL") )
  {
    LibraryW = LoadLibraryW(lpLibFileName);
    *a2 = LibraryW;
  }
  else
  {
    LibraryW = (HMODULE)hMeDLL;
    *a2 = (HINSTANCE)hMeDLL;
  }
  return LibraryW != 0;
}

```

## disassembly

```asm
0x18000ed7c  mov     [rsp+arg_0], rbx
0x18000ed81  mov     [rsp+arg_8], rsi
0x18000ed86  push    rdi
0x18000ed87  sub     rsp, 20h
0x18000ed8b  xor     esi, esi
0x18000ed8d  mov     rbx, rdx
0x18000ed90  mov     [rdx], rsi
0x18000ed93  mov     rdi, rcx
0x18000ed96  cmp     [rcx], si
0x18000ed99  jz      short loc_18000EDCE
0x18000ed9b  lea     rdx, aWintrustDll_0; "WINTRUST.DLL"
0x18000eda2  call    cs:__imp__wcsicmp
0x18000eda8  test    eax, eax
0x18000edaa  jnz     short loc_18000EDD2
0x18000edac  mov     rcx, cs:hMeDLL
0x18000edb3  mov     [rbx], rcx
0x18000edb6  test    rcx, rcx
0x18000edb9  mov     eax, esi
0x18000edbb  setnz   al
0x18000edbe  mov     rbx, [rsp+28h+arg_0]
0x18000edc3  mov     rsi, [rsp+28h+arg_8]
0x18000edc8  add     rsp, 20h
0x18000edcc  pop     rdi
0x18000edcd  retn
0x18000edce  xor     eax, eax
0x18000edd0  jmp     short loc_18000EDBE
0x18000edd2  mov     rcx, rdi; lpLibFileName
0x18000edd5  call    cs:__imp_LoadLibraryW
0x18000eddb  mov     rcx, rax
0x18000edde  mov     [rbx], rax
0x18000ede1  jmp     short loc_18000EDB6
```
