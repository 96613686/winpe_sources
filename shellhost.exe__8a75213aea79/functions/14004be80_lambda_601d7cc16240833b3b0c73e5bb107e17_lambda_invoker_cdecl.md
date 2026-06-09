# _lambda_601d7cc16240833b3b0c73e5bb107e17_::_lambda_invoker_cdecl_

- ea: `0x14004be80`
- end: `0x14004beb7`
- name: `_lambda_601d7cc16240833b3b0c73e5bb107e17_::_lambda_invoker_cdecl_`
- size: `55`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14004be80`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004bea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004bea0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14004be8b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14004be8b`

## string_xrefs

- `0x14004be84`: `ControlCenter.dll`

## pseudocode

```c
__int64 __fastcall lambda_601d7cc16240833b3b0c73e5bb107e17_::_lambda_invoker_cdecl_(LPVOID lpThreadParameter)
{
  HMODULE LibraryW; // rax
  void (*ProcAddress)(void); // rax

  LibraryW = LoadLibraryW(L"ControlCenter.dll");
  if ( LibraryW )
  {
    ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "ControlCenterMain");
    if ( ProcAddress )
      ProcAddress();
  }
  return 0;
}

```

## disassembly

```asm
0x14004be80  sub     rsp, 28h
0x14004be84  lea     rcx, LibFileName; "ControlCenter.dll"
0x14004be8b  call    cs:__imp_LoadLibraryW
0x14004be91  test    rax, rax
0x14004be94  jz      short loc_14004BEB0
0x14004be96  lea     rdx, aControlcenterm; "ControlCenterMain"
0x14004be9d  mov     rcx, rax; hModule
0x14004bea0  call    cs:__imp_GetProcAddress
0x14004bea6  test    rax, rax
0x14004bea9  jz      short loc_14004BEB0
0x14004beab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004beb0  xor     eax, eax
0x14004beb2  add     rsp, 28h
0x14004beb6  retn
```
