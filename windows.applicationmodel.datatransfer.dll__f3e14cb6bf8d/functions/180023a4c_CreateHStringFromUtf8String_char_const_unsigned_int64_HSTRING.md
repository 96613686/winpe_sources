# CreateHStringFromUtf8String(char const *,unsigned __int64,HSTRING__ * *)

- ea: `0x180023a4c`
- end: `0x180023b8c`
- name: `?CreateHStringFromUtf8String@@YAJPEBD_KPEAPEAUHSTRING__@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int64, HSTRING *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800239c4`
- `0x1800611a0`
- `0x18006168c`

## callees

- `0x180023a4c`
- `0x18004ebbc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180023b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180023b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180023b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180023b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180023b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180023b1c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023afa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023afa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023ae4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023aaa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023a9e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023b42`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023a9e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023b42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateHStringFromUtf8String(LPCCH lpMultiByteStr, unsigned __int64 a2, HSTRING *a3)
{
  unsigned __int64 v5; // rax
  int v6; // r14d
  signed int v7; // eax
  int cchWideChar; // ebx
  signed int LastError; // eax
  signed int v10; // ebx
  HRESULT v11; // edi
  unsigned int StringW; // eax
  HSTRING_BUFFER v13; // rcx
  HSTRING_BUFFER Buffer; // [rsp+70h] [rbp+40h] BYREF
  WCHAR *charBuffer; // [rsp+78h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = StringNzCbSize(lpMultiByteStr, a2);
  v6 = v5;
  if ( v5 > 0x7FFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v7 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v5, 0, 0);
    cchWideChar = v7;
    if ( v7 > 0 )
    {
      Buffer = 0;
      charBuffer = 0;
      v11 = WindowsPreallocateStringBuffer(v7, &charBuffer, &Buffer);
      if ( v11 < 0
        || (MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v6, charBuffer, cchWideChar),
            v11 = WindowsPromoteStringBuffer(Buffer, a3),
            v11 < 0) )
      {
        v13 = Buffer;
      }
      else
      {
        v13 = 0;
        Buffer = 0;
      }
      if ( v13 )
        WindowsDeleteStringBuffer(v13);
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      Buffer = 0;
      v11 = v10;
      StringW = LoadStringW(&_ImageBase, 0x11u, (LPWSTR)&Buffer, 0);
      if ( StringW )
        RoOriginateErrorW((unsigned int)v10, StringW, Buffer);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180023a4c  mov     [rsp-28h+arg_0], rbx
0x180023a51  push    rbp
0x180023a52  push    rsi
0x180023a53  push    rdi
0x180023a54  push    r14
0x180023a56  push    r15
0x180023a58  mov     rbp, rsp
0x180023a5b  sub     rsp, 30h
0x180023a5f  mov     r15, r8
0x180023a62  mov     qword ptr [r8], 0
0x180023a69  mov     rsi, rcx
0x180023a6c  call    ?StringNzCbSize@@YA_KPEBD_K@Z; StringNzCbSize(char const *,unsigned __int64)
0x180023a71  mov     r14, rax
0x180023a74  cmp     rax, 7FFFFFFFh
0x180023a7a  ja      loc_180023B74
0x180023a80  mov     [rsp+30h+cchWideChar], 0; cchWideChar
0x180023a88  mov     r9d, r14d; cbMultiByte
0x180023a8b  mov     r8, rsi; lpMultiByteStr
0x180023a8e  mov     [rsp+30h+lpWideCharStr], 0; lpWideCharStr
0x180023a97  xor     edx, edx; dwFlags
0x180023a99  mov     ecx, 0FDE9h; CodePage
0x180023a9e  call    cs:__imp_MultiByteToWideChar
0x180023aa4  mov     ebx, eax
0x180023aa6  test    eax, eax
0x180023aa8  jg      short loc_180023B02
0x180023aaa  call    cs:__imp_GetLastError
0x180023ab0  mov     ebx, eax
0x180023ab2  test    eax, eax
0x180023ab4  jle     short loc_180023ABF
0x180023ab6  movzx   ebx, ax
0x180023ab9  or      ebx, 80070000h
0x180023abf  test    ebx, ebx
0x180023ac1  js      short loc_180023AC8
0x180023ac3  mov     ebx, 80004005h
0x180023ac8  xor     r9d, r9d; cchBufferMax
0x180023acb  mov     [rbp+Buffer], 0
0x180023ad3  lea     r8, [rbp+Buffer]; lpBuffer
0x180023ad7  mov     edi, ebx
0x180023ad9  lea     rcx, __ImageBase; hInstance
0x180023ae0  lea     edx, [r9+11h]; uID
0x180023ae4  call    cs:__imp_LoadStringW
0x180023aea  test    eax, eax
0x180023aec  jz      loc_180023B79
0x180023af2  mov     r8, [rbp+Buffer]
0x180023af6  mov     edx, eax
0x180023af8  mov     ecx, ebx
0x180023afa  call    cs:__imp_RoOriginateErrorW
0x180023b00  jmp     short loc_180023B79
0x180023b02  lea     r8, [rbp+Buffer]; bufferHandle
0x180023b06  mov     [rbp+Buffer], 0
0x180023b0e  lea     rdx, [rbp+charBuffer]; charBuffer
0x180023b12  mov     [rbp+charBuffer], 0
0x180023b1a  mov     ecx, ebx; length
0x180023b1c  call    cs:__imp_WindowsPreallocateStringBuffer
0x180023b22  mov     edi, eax
0x180023b24  test    eax, eax
0x180023b26  js      short loc_180023B63
0x180023b28  mov     rax, [rbp+charBuffer]
0x180023b2c  mov     r9d, r14d; cbMultiByte
0x180023b2f  mov     [rsp+30h+cchWideChar], ebx; cchWideChar
0x180023b33  mov     r8, rsi; lpMultiByteStr
0x180023b36  xor     edx, edx; dwFlags
0x180023b38  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180023b3d  mov     ecx, 0FDE9h; CodePage
0x180023b42  call    cs:__imp_MultiByteToWideChar
0x180023b48  mov     rcx, [rbp+Buffer]; bufferHandle
0x180023b4c  mov     rdx, r15; string
0x180023b4f  call    cs:__imp_WindowsPromoteStringBuffer
0x180023b55  mov     edi, eax
0x180023b57  test    eax, eax
0x180023b59  js      short loc_180023B63
0x180023b5b  xor     ecx, ecx
0x180023b5d  mov     [rbp+Buffer], rcx
0x180023b61  jmp     short loc_180023B67
0x180023b63  mov     rcx, [rbp+Buffer]; bufferHandle
0x180023b67  test    rcx, rcx
0x180023b6a  jz      short loc_180023B79
0x180023b6c  call    cs:__imp_WindowsDeleteStringBuffer
0x180023b72  jmp     short loc_180023B79
0x180023b74  mov     edi, 80070216h
0x180023b79  mov     rbx, [rsp+30h+arg_0]
0x180023b7e  mov     eax, edi
0x180023b80  add     rsp, 30h
0x180023b84  pop     r15
0x180023b86  pop     r14
0x180023b88  pop     rdi
0x180023b89  pop     rsi
0x180023b8a  pop     rbp
0x180023b8b  retn
```
