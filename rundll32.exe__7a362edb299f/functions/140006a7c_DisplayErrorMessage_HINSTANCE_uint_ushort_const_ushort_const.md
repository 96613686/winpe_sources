# _DisplayErrorMessage(HINSTANCE__ *,uint,ushort const *,ushort const *)

- ea: `0x140006a7c`
- end: `0x140006c1e`
- name: `?_DisplayErrorMessage@@YAXPEAUHINSTANCE__@@IPEBG1@Z`
- size: `418`
- prototype: `void __fastcall(HINSTANCE hInstance, UINT, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140006e44`
- `0x140007798`

## callees

- `0x1400015a0`
- `0x140006328`
- `0x140006a7c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140006ab7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140006b01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140006ab7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140006b01`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140006b40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140006b40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006bdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006bdd`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140006b86`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140006ba6`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140006bd4`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140006b86`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140006ba6`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140006bd4`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x140006bfb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x140006bfb`

## pseudocode

```c
void __fastcall _DisplayErrorMessage(
        HINSTANCE hInstance,
        UINT a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HANDLE FileW; // rax
  __int64 v8; // rbx
  void *v9; // rdi
  __int64 v10; // r8
  DWORD NumberOfCharsWritten[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[200]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Text[464]; // [rsp+1E0h] [rbp+E0h] BYREF

  if ( LoadStringW(hInstance, a2, Buffer, 200)
    && (int)StringCchPrintfW(Text, 0x1CCu, Buffer, a3, a4) >= 0
    && LoadStringW(hInstance, 0x402u, Buffer, 200) )
  {
    if ( g_PrintMessageOption == 1 )
    {
      FileW = CreateFileW(L"CONOUT$", 0xC0000000, 3u, 0, 3u, 0, 0);
      v8 = -1;
      v9 = 0;
      if ( FileW != (HANDLE)-1LL )
        v9 = FileW;
      if ( v9 )
      {
        NumberOfCharsWritten[0] = 0;
        v10 = -1;
        do
          ++v10;
        while ( Buffer[v10] );
        WriteConsoleW(v9, Buffer, v10, NumberOfCharsWritten, 0);
        WriteConsoleW(v9, L": ", 2u, NumberOfCharsWritten, 0);
        do
          ++v8;
        while ( Text[v8] );
        WriteConsoleW(v9, Text, v8, NumberOfCharsWritten, 0);
        CloseHandle(v9);
      }
    }
    else if ( !g_PrintMessageOption )
    {
      MessageBoxW(0, Text, Buffer, 0x10u);
    }
  }
}

```

## disassembly

```asm
0x140006a7c  push    rbp
0x140006a7e  push    rbx
0x140006a7f  push    rsi
0x140006a80  push    rdi
0x140006a81  push    r14
0x140006a83  lea     rbp, [rsp-490h]
0x140006a8b  sub     rsp, 590h
0x140006a92  mov     rax, cs:__security_cookie
0x140006a99  xor     rax, rsp
0x140006a9c  mov     [rbp+4B0h+var_30], rax
0x140006aa3  mov     rsi, r9
0x140006aa6  mov     rdi, r8
0x140006aa9  mov     r9d, 0C8h; cchBufferMax
0x140006aaf  lea     r8, [rsp+5B0h+Buffer]; lpBuffer
0x140006ab4  mov     rbx, rcx
0x140006ab7  call    cs:__imp_LoadStringW
0x140006abd  xor     r14d, r14d
0x140006ac0  test    eax, eax
0x140006ac2  jz      loc_140006C01
0x140006ac8  mov     r9, rdi
0x140006acb  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rsi
0x140006ad0  lea     r8, [rsp+5B0h+Buffer]; unsigned __int16 *
0x140006ad5  mov     edx, 1CCh; unsigned __int64
0x140006ada  lea     rcx, [rbp+4B0h+Text]; unsigned __int16 *
0x140006ae1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006ae6  test    eax, eax
0x140006ae8  js      loc_140006C01
0x140006aee  mov     r9d, 0C8h; cchBufferMax
0x140006af4  lea     r8, [rsp+5B0h+Buffer]; lpBuffer
0x140006af9  mov     edx, 402h; uID
0x140006afe  mov     rcx, rbx; hInstance
0x140006b01  call    cs:__imp_LoadStringW
0x140006b07  test    eax, eax
0x140006b09  jz      loc_140006C01
0x140006b0f  mov     eax, cs:?g_PrintMessageOption@@3HA; int g_PrintMessageOption
0x140006b15  cmp     eax, 1
0x140006b18  jnz     loc_140006BE5
0x140006b1e  mov     [rsp+5B0h+hTemplateFile], r14; hTemplateFile
0x140006b23  lea     r8d, [r14+3]; dwShareMode
0x140006b27  mov     [rsp+5B0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x140006b2c  lea     rcx, FileName; "CONOUT$"
0x140006b33  xor     r9d, r9d; lpSecurityAttributes
0x140006b36  mov     [rsp+5B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x140006b3b  mov     edx, 0C0000000h; dwDesiredAccess
0x140006b40  call    cs:__imp_CreateFileW
0x140006b46  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140006b4a  mov     edi, r14d
0x140006b4d  cmp     rax, rbx
0x140006b50  cmovnz  rdi, rax
0x140006b54  test    rdi, rdi
0x140006b57  jz      loc_140006C01
0x140006b5d  mov     [rsp+5B0h+NumberOfCharsWritten], r14d
0x140006b62  lea     rax, [rsp+5B0h+Buffer]
0x140006b67  mov     r8, rbx
0x140006b6a  inc     r8; nNumberOfCharsToWrite
0x140006b6d  cmp     [rax+r8*2], r14w
0x140006b72  jnz     short loc_140006B6A
0x140006b74  lea     r9, [rsp+5B0h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x140006b79  mov     qword ptr [rsp+5B0h+dwCreationDisposition], r14; lpReserved
0x140006b7e  lea     rdx, [rsp+5B0h+Buffer]; lpBuffer
0x140006b83  mov     rcx, rdi; hConsoleOutput
0x140006b86  call    cs:__imp_WriteConsoleW
0x140006b8c  lea     r9, [rsp+5B0h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x140006b91  mov     qword ptr [rsp+5B0h+dwCreationDisposition], r14; lpReserved
0x140006b96  mov     r8d, 2; nNumberOfCharsToWrite
0x140006b9c  lea     rdx, asc_14000E240; ": "
0x140006ba3  mov     rcx, rdi; hConsoleOutput
0x140006ba6  call    cs:__imp_WriteConsoleW
0x140006bac  lea     rax, [rbp+4B0h+Text]
0x140006bb3  inc     rbx
0x140006bb6  cmp     [rax+rbx*2], r14w
0x140006bbb  jnz     short loc_140006BB3
0x140006bbd  mov     r8d, ebx; nNumberOfCharsToWrite
0x140006bc0  mov     qword ptr [rsp+5B0h+dwCreationDisposition], r14; lpReserved
0x140006bc5  lea     r9, [rsp+5B0h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x140006bca  mov     rcx, rdi; hConsoleOutput
0x140006bcd  lea     rdx, [rbp+4B0h+Text]; lpBuffer
0x140006bd4  call    cs:__imp_WriteConsoleW
0x140006bda  mov     rcx, rdi; hObject
0x140006bdd  call    cs:__imp_CloseHandle
0x140006be3  jmp     short loc_140006C01
0x140006be5  test    eax, eax
0x140006be7  jnz     short loc_140006C01
0x140006be9  lea     r9d, [rax+10h]; uType
0x140006bed  xor     ecx, ecx; hWnd
0x140006bef  lea     r8, [rsp+5B0h+Buffer]; lpCaption
0x140006bf4  lea     rdx, [rbp+4B0h+Text]; lpText
0x140006bfb  call    cs:__imp_MessageBoxW
0x140006c01  mov     rcx, [rbp+4B0h+var_30]
0x140006c08  xor     rcx, rsp; StackCookie
0x140006c0b  call    __security_check_cookie
0x140006c10  add     rsp, 590h
0x140006c17  pop     r14
0x140006c19  pop     rdi
0x140006c1a  pop     rsi
0x140006c1b  pop     rbx
0x140006c1c  pop     rbp
0x140006c1d  retn
```
