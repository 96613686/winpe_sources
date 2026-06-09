# LoadOLEOnce(void)

- ea: `0x18005d7a0`
- end: `0x18005d8ad`
- name: `?LoadOLEOnce@@YAJXZ`
- size: `269`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180087fb0`

## callees

- `0x18005d7a0`
- `0x1800a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009ffe2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009ffe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d844`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d844`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005d823`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005d823`

## string_xrefs

- `0x18005d7c2`: `OLE32.DLL`

## pseudocode

```c
__int64 LoadOLEOnce(void)
{
  HMODULE Library; // rax
  FARPROC **v1; // rbx
  FARPROC *v2; // rdi
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  _QWORD **v5; // rax
  _QWORD *v6; // rcx
  _QWORD v7[8]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v8; // [rsp+60h] [rbp-10h]
  __int64 (__fastcall *v9)(_QWORD); // [rsp+80h] [rbp+10h] BYREF

  v9 = 0;
  v7[0] = &v9;
  v7[1] = "OleInitialize";
  v8 = 0;
  v7[2] = &gpfnOLEOleUninitialize;
  v7[3] = "OleUninitialize";
  v7[4] = &gpfnOLERegisterDD;
  v7[5] = "RegisterDragDrop";
  v7[6] = &gpfnOLERevokeDD;
  v7[7] = "RevokeDragDrop";
  Library = LoadLibraryExW(L"OLE32.DLL", 0, 0);
  ghinstOLE = Library;
  if ( !Library )
    goto LABEL_10;
  v1 = (FARPROC **)v7;
  v2 = (FARPROC *)&v9;
  while ( 1 )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)v1[1]);
    *v2 = ProcAddress;
    if ( !ProcAddress )
      break;
    v1 += 2;
    v2 = *v1;
    if ( !*v1 )
      break;
    Library = ghinstOLE;
  }
  if ( *v1 || (result = v9(0), (int)result < 0) )
  {
    v5 = (_QWORD **)v7;
    v6 = &v9;
    do
    {
      v5 += 2;
      *v6 = 0;
      v6 = *v5;
    }
    while ( *v5 );
    FreeLibrary(ghinstOLE);
LABEL_10:
    ghinstOLE = (HMODULE)-1LL;
    return 3221225473LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005d7a0  mov     [rsp-8+arg_8], rbx
0x18005d7a5  mov     [rsp-8+arg_10], rdi
0x18005d7aa  push    rbp
0x18005d7ab  mov     rbp, rsp
0x18005d7ae  sub     rsp, 70h
0x18005d7b2  lea     rax, [rbp+arg_0]
0x18005d7b6  mov     [rbp+arg_0], 0
0x18005d7be  mov     [rbp+var_50], rax
0x18005d7c2  lea     rcx, aOle32Dll; "OLE32.DLL"
0x18005d7c9  lea     rax, aOleinitialize; "OleInitialize"
0x18005d7d0  xorps   xmm0, xmm0
0x18005d7d3  mov     [rbp+var_48], rax
0x18005d7d7  xor     r8d, r8d; dwFlags
0x18005d7da  lea     rax, ?gpfnOLEOleUninitialize@@3P6A_JXZEA; __int64 (*gpfnOLEOleUninitialize)(void)
0x18005d7e1  movdqa  [rbp+var_10], xmm0
0x18005d7e6  mov     [rbp+var_40], rax
0x18005d7ea  xor     edx, edx; hFile
0x18005d7ec  lea     rax, aOleuninitializ; "OleUninitialize"
0x18005d7f3  mov     [rbp+var_38], rax
0x18005d7f7  lea     rax, ?gpfnOLERegisterDD@@3P6A_JXZEA; __int64 (*gpfnOLERegisterDD)(void)
0x18005d7fe  mov     [rbp+var_30], rax
0x18005d802  lea     rax, aRegisterdragdr; "RegisterDragDrop"
0x18005d809  mov     [rbp+var_28], rax
0x18005d80d  lea     rax, ?gpfnOLERevokeDD@@3P6A_JXZEA; __int64 (*gpfnOLERevokeDD)(void)
0x18005d814  mov     [rbp+var_20], rax
0x18005d818  lea     rax, aRevokedragdrop; "RevokeDragDrop"
0x18005d81f  mov     [rbp+var_18], rax
0x18005d823  call    cs:__imp_LoadLibraryExW
0x18005d829  mov     cs:?ghinstOLE@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghinstOLE
0x18005d830  test    rax, rax
0x18005d833  jz      short loc_18005D89B
0x18005d835  lea     rbx, [rbp+var_50]
0x18005d839  lea     rdi, [rbp+arg_0]
0x18005d83d  mov     rdx, [rbx+8]; lpProcName
0x18005d841  mov     rcx, rax; hModule
0x18005d844  call    cs:__imp_GetProcAddress
0x18005d84a  mov     [rdi], rax
0x18005d84d  test    rax, rax
0x18005d850  jz      short loc_18005D85E
0x18005d852  add     rbx, 10h
0x18005d856  mov     rdi, [rbx]
0x18005d859  test    rdi, rdi
0x18005d85c  jnz     short loc_18005D885
0x18005d85e  cmp     qword ptr [rbx], 0
0x18005d862  jnz     short loc_18005D88E
0x18005d864  mov     rax, [rbp+arg_0]
0x18005d868  xor     ecx, ecx
0x18005d86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d86f  test    eax, eax
0x18005d871  js      short loc_18005D88E
0x18005d873  lea     r11, [rsp+70h+var_s0]
0x18005d878  mov     rbx, [r11+18h]
0x18005d87c  mov     rdi, [r11+20h]
0x18005d880  mov     rsp, r11
0x18005d883  pop     rbp
0x18005d884  retn
0x18005d885  mov     rax, cs:?ghinstOLE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghinstOLE
0x18005d88c  jmp     short loc_18005D83D
0x18005d88e  lea     rax, [rbp+var_50]
0x18005d892  lea     rcx, [rbp+arg_0]
0x18005d896  jmp     loc_18009FFC8
0x18005d89b  mov     cs:?ghinstOLE@@3PEAUHINSTANCE__@@EA, 0FFFFFFFFFFFFFFFFh; HINSTANCE__ * ghinstOLE
0x18005d8a6  mov     eax, 0C0000001h
0x18005d8ab  jmp     short loc_18005D873
0x18009ffc8  lea     rax, [rax+10h]
0x18009ffcc  mov     qword ptr [rcx], 0
0x18009ffd3  mov     rcx, [rax]
0x18009ffd6  test    rcx, rcx
0x18009ffd9  jnz     short loc_18009FFC8
0x18009ffdb  mov     rcx, cs:?ghinstOLE@@3PEAUHINSTANCE__@@EA; hLibModule
0x18009ffe2  call    cs:__imp_FreeLibrary
0x18009ffe8  nop
0x18009ffe9  jmp     loc_18005D89B
```
