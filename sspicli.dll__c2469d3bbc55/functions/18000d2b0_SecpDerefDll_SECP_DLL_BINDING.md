# SecpDerefDll(_SECP_DLL_BINDING *)

- ea: `0x18000d2b0`
- end: `0x18000d304`
- name: `?SecpDerefDll@@YAXPEAU_SECP_DLL_BINDING@@@Z`
- size: `84`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800069d8`
- `0x1800070d0`
- `0x18000cfec`
- `0x18000d0f0`
- `0x18000d30c`
- `0x18001caa0`

## callees

- `0x18000d2b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d2fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d2fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2f0`

## pseudocode

```c
void __fastcall SecpDerefDll(HLOCAL *hMem)
{
  int v3; // edi
  HMODULE v4; // rcx

  if ( (*((_DWORD *)hMem + 8))-- == 1 )
  {
    v3 = DllState & 0x100000;
    LocalFree(hMem[3]);
    v4 = (HMODULE)hMem[1];
    if ( v4 )
    {
      if ( !v3 )
        FreeLibrary(v4);
    }
    LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x18000d2b0  mov     [rsp+arg_8], rbx
0x18000d2b5  push    rdi
0x18000d2b6  sub     rsp, 20h
0x18000d2ba  add     dword ptr [rcx+20h], 0FFFFFFFFh
0x18000d2be  mov     rbx, rcx
0x18000d2c1  jz      short loc_18000D2CE
0x18000d2c3  mov     rbx, [rsp+28h+arg_8]
0x18000d2c8  add     rsp, 20h
0x18000d2cc  pop     rdi
0x18000d2cd  retn
0x18000d2ce  mov     edi, cs:DllState
0x18000d2d4  mov     rcx, [rcx+18h]; hMem
0x18000d2d8  and     edi, 100000h
0x18000d2de  call    cs:__imp_LocalFree
0x18000d2e4  mov     rcx, [rbx+8]; hLibModule
0x18000d2e8  test    rcx, rcx
0x18000d2eb  jnz     short loc_18000D2F8
0x18000d2ed  mov     rcx, rbx; hMem
0x18000d2f0  call    cs:__imp_LocalFree
0x18000d2f6  jmp     short loc_18000D2C3
0x18000d2f8  test    edi, edi
0x18000d2fa  jnz     short loc_18000D2ED
0x18000d2fc  call    cs:__imp_FreeLibrary
0x18000d302  jmp     short loc_18000D2ED
```
