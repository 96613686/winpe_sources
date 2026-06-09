# UnregisterSecurityCenterBroker

- ea: `0x180028a30`
- end: `0x180028a93`
- name: `UnregisterSecurityCenterBroker`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c8e0`

## callees

- `0x180028a30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028a7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028a7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028a49`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a57`

## string_xrefs

- `0x180028a42`: `UnregisterSecurityCenterBroker`

## pseudocode

```c
void UnregisterSecurityCenterBroker()
{
  void (*ProcAddress)(void); // rbx
  signed int LastError; // eax
  bool v2; // sf

  if ( g_hBroker )
  {
    ProcAddress = (void (*)(void))GetProcAddress(g_hBroker, "UnregisterSecurityCenterBroker");
    if ( ProcAddress )
      goto LABEL_6;
    LastError = GetLastError();
    v2 = LastError < 0;
    if ( LastError > 0 )
      v2 = 1;
    if ( !v2 )
LABEL_6:
      ProcAddress();
    FreeLibrary(g_hBroker);
    g_hBroker = 0;
  }
}

```

## disassembly

```asm
0x180028a30  push    rbx
0x180028a32  sub     rsp, 20h
0x180028a36  mov     rcx, cs:?g_hBroker@@3PEAUHINSTANCE__@@EA; hModule
0x180028a3d  test    rcx, rcx
0x180028a40  jz      short loc_180028A8D
0x180028a42  lea     rdx, aUnregistersecu; "UnregisterSecurityCenterBroker"
0x180028a49  call    cs:__imp_GetProcAddress
0x180028a4f  mov     rbx, rax
0x180028a52  test    rax, rax
0x180028a55  jnz     short loc_180028A6D
0x180028a57  call    cs:__imp_GetLastError
0x180028a5d  test    eax, eax
0x180028a5f  jle     short loc_180028A6B
0x180028a61  movzx   eax, ax
0x180028a64  or      eax, 80070000h
0x180028a69  test    eax, eax
0x180028a6b  js      short loc_180028A75
0x180028a6d  mov     rax, rbx
0x180028a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a75  mov     rcx, cs:?g_hBroker@@3PEAUHINSTANCE__@@EA; hLibModule
0x180028a7c  call    cs:__imp_FreeLibrary
0x180028a82  mov     cs:?g_hBroker@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hBroker
0x180028a8d  add     rsp, 20h
0x180028a91  pop     rbx
0x180028a92  retn
```
