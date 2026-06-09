# _bidLoadEntryPoint

- ea: `0x383893dd0`
- end: `0x383893e04`
- name: `_bidLoadEntryPoint`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x383893a20`

## callees

- `0x383893dd0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x3838be3e1`
- `KERNEL32!FreeLibrary` at `0x3838be3e1`
- `KERNEL32!LoadLibraryW` at `0x3838be399`
- `KERNEL32!LoadLibraryW` at `0x3838be399`
- `KERNEL32!GetProcAddress` at `0x3838be3b5`
- `KERNEL32!GetProcAddress` at `0x3838be3b5`

## string_xrefs

- `0x3838be3ab`: `DllBidEntryPoint`

## pseudocode

```c
int bidLoadEntryPoint()
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax

  if ( dword_383B23BF0 )
  {
    LibraryW = LoadLibraryW(lpOutputString);
    hLibModule = LibraryW;
  }
  else
  {
    LibraryW = hLibModule;
  }
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DllBidEntryPoint");
    bidpEntryPoint = ProcAddress;
    if ( !ProcAddress )
    {
      ProcAddress = (FARPROC)ImplBidEntryPoint;
      bidpEntryPoint = ImplBidEntryPoint;
      if ( hLibModule )
      {
        LODWORD(ProcAddress) = FreeLibrary(hLibModule);
        hLibModule = 0;
      }
    }
  }
  else
  {
    ProcAddress = (FARPROC)ImplBidEntryPoint;
    bidpEntryPoint = ImplBidEntryPoint;
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x383893dd0  sub     rsp, 28h
0x383893dd4  cmp     cs:dword_383B23BF0, 0
0x383893ddb  jnz     loc_3838BE392
0x383893de1  mov     rax, cs:hLibModule
0x383893de8  test    rax, rax
0x383893deb  jnz     loc_3838BE3AB
0x383893df1  lea     rax, ImplBidEntryPoint
0x383893df8  mov     cs:_bidpEntryPoint, rax
0x383893dff  add     rsp, 28h
0x383893e03  retn
0x3838be392  mov     rcx, cs:lpOutputString; lpLibFileName
0x3838be399  call    cs:__imp_LoadLibraryW
0x3838be39f  mov     cs:hLibModule, rax
0x3838be3a6  jmp     loc_383893DE8
0x3838be3ab  lea     rdx, aDllbidentrypoi; "DllBidEntryPoint"
0x3838be3b2  mov     rcx, rax; hModule
0x3838be3b5  call    cs:__imp_GetProcAddress
0x3838be3bb  mov     cs:_bidpEntryPoint, rax
0x3838be3c2  test    rax, rax
0x3838be3c5  jnz     short loc_3838BE3F2
0x3838be3c7  mov     rcx, cs:hLibModule; hLibModule
0x3838be3ce  lea     rax, ImplBidEntryPoint
0x3838be3d5  mov     cs:_bidpEntryPoint, rax
0x3838be3dc  test    rcx, rcx
0x3838be3df  jz      short loc_3838BE3F2
0x3838be3e1  call    cs:__imp_FreeLibrary
0x3838be3e7  mov     cs:hLibModule, 0
0x3838be3f2  add     rsp, 28h
0x3838be3f6  retn
```
