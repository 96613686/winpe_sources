# SystemNaturalLanguageGet

- ea: `0x180030d34`
- end: `0x180030df5`
- name: `SystemNaturalLanguageGet`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180030918`

## callees

- `0x180002590`
- `0x180030d34`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030d8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030d8b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030dd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d99`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180030da3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180030da3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180030d69`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180030d69`

## string_xrefs

- `0x180030d57`: `mlang.dll`

## pseudocode

```c
__int64 __fastcall SystemNaturalLanguageGet(_WORD *a1)
{
  DWORD LastError; // ebx
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rsi
  LCID SystemDefaultLCID; // eax
  char v8; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+21h] [rbp-47h]

  *a1 = 25966;
  LastError = 0;
  v9 = 0;
  v8 = 0;
  LibraryW = LoadLibraryW(L"mlang.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "LcidToRfc1766A");
    if ( ProcAddress )
    {
      SystemDefaultLCID = GetSystemDefaultLCID();
      ((void (__fastcall *)(_QWORD, char *, __int64))ProcAddress)(SystemDefaultLCID, &v8, 9);
      *a1 = (char)v9 | (unsigned __int16)(v8 << 8);
    }
    else
    {
      LastError = GetLastError();
    }
    FreeLibrary(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180030d34  push    rbx
0x180030d36  push    rsi
0x180030d37  push    rdi
0x180030d38  push    r14
0x180030d3a  sub     rsp, 48h
0x180030d3e  mov     rax, cs:__security_cookie
0x180030d45  xor     rax, rsp
0x180030d48  mov     [rsp+68h+var_38], rax
0x180030d4d  mov     r14, rcx
0x180030d50  mov     word ptr [rcx], 656Eh
0x180030d55  xor     eax, eax
0x180030d57  lea     rcx, aMlangDll; "mlang.dll"
0x180030d5e  xor     ebx, ebx
0x180030d60  mov     [rsp+68h+var_47], rax
0x180030d65  mov     [rsp+68h+var_48], bl
0x180030d69  call    cs:__imp_LoadLibraryW
0x180030d6f  mov     rdi, rax
0x180030d72  test    rax, rax
0x180030d75  jnz     short loc_180030D81
0x180030d77  call    cs:__imp_GetLastError
0x180030d7d  mov     ebx, eax
0x180030d7f  jmp     short loc_180030DDC
0x180030d81  lea     rdx, aLcidtorfc1766a; "LcidToRfc1766A"
0x180030d88  mov     rcx, rdi; hModule
0x180030d8b  call    cs:__imp_GetProcAddress
0x180030d91  mov     rsi, rax
0x180030d94  test    rax, rax
0x180030d97  jnz     short loc_180030DA3
0x180030d99  call    cs:__imp_GetLastError
0x180030d9f  mov     ebx, eax
0x180030da1  jmp     short loc_180030DD3
0x180030da3  call    cs:__imp_GetSystemDefaultLCID
0x180030da9  mov     r8d, 9
0x180030daf  lea     rdx, [rsp+68h+var_48]
0x180030db4  mov     ecx, eax
0x180030db6  mov     rax, rsi
0x180030db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dbe  movsx   ecx, [rsp+68h+var_48]
0x180030dc3  movsx   eax, byte ptr [rsp+68h+var_47]
0x180030dc8  shl     cx, 8
0x180030dcc  or      cx, ax
0x180030dcf  mov     [r14], cx
0x180030dd3  mov     rcx, rdi; hLibModule
0x180030dd6  call    cs:__imp_FreeLibrary
0x180030ddc  mov     eax, ebx
0x180030dde  mov     rcx, [rsp+68h+var_38]
0x180030de3  xor     rcx, rsp; StackCookie
0x180030de6  call    __security_check_cookie
0x180030deb  add     rsp, 48h
0x180030def  pop     r14
0x180030df1  pop     rdi
0x180030df2  pop     rsi
0x180030df3  pop     rbx
0x180030df4  retn
```
