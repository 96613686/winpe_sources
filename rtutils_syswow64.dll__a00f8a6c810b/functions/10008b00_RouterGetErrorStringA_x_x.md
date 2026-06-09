# RouterGetErrorStringA(x,x)

- ea: `0x10008b00`
- end: `0x10008bc9`
- name: `_RouterGetErrorStringA@8`
- size: `201`
- prototype: `DWORD __stdcall(DWORD dwErrorCode, LPSTR *lplpszErrorString)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10008cb0`

## callees

- `0x10008b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10008b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10008b65`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10008b56`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10008b56`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10008b72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10008b72`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x10008bb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x10008bb7`

## string_xrefs

- `0x10008b51`: `mprmsg.dll`

## pseudocode

```c
DWORD __stdcall RouterGetErrorStringA(DWORD dwErrorCode, LPSTR *lplpszErrorString)
{
  DWORD v3; // eax

  if ( (dwErrorCode < 0x258 || dwErrorCode > 0x36E)
    && (dwErrorCode < 0x384 || dwErrorCode > 0x3BD)
    && dwErrorCode - 20000 > 0x3E7 )
  {
    v3 = FormatMessageA(0x1300u, 0, dwErrorCode, 0x400u, (LPSTR)lplpszErrorString, 0, 0);
  }
  else
  {
    if ( !_InterlockedCompareExchange(&g_hDll, -1, 0) )
    {
      g_hDll = (int)LoadLibraryExA("mprmsg.dll", 0, 0x800u);
      if ( !g_hDll )
        return GetLastError();
    }
    while ( g_hDll == -1 )
      Sleep(0x1F4u);
    if ( !g_hDll )
      return 1003;
    v3 = FormatMessageA(0x900u, (LPCVOID)g_hDll, dwErrorCode, 0x400u, (LPSTR)lplpszErrorString, 0, 0);
  }
  if ( !v3 )
    return GetLastError();
  return 0;
}

```

## disassembly

```asm
0x10008b00  mov     edi, edi
0x10008b02  push    ebp
0x10008b03  mov     ebp, esp
0x10008b05  push    esi
0x10008b06  mov     esi, [ebp+dwErrorCode]
0x10008b09  push    edi
0x10008b0a  cmp     esi, 258h
0x10008b10  jb      short loc_10008B1A
0x10008b12  cmp     esi, 36Eh
0x10008b18  jbe     short loc_10008B37
0x10008b1a  cmp     esi, 384h
0x10008b20  jb      short loc_10008B2A
0x10008b22  cmp     esi, 3BDh
0x10008b28  jbe     short loc_10008B37
0x10008b2a  lea     eax, [esi-4E20h]
0x10008b30  cmp     eax, 3E7h
0x10008b35  ja      short loc_10008BA4
0x10008b37  or      ecx, 0FFFFFFFFh
0x10008b3a  mov     edx, offset _g_hDll
0x10008b3f  xor     eax, eax
0x10008b41  lock cmpxchg [edx], ecx
0x10008b45  xor     edi, edi
0x10008b47  test    eax, eax
0x10008b49  jnz     short loc_10008B78
0x10008b4b  push    800h; dwFlags
0x10008b50  push    edi; hFile
0x10008b51  push    offset LibFileName; "mprmsg.dll"
0x10008b56  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10008b5c  mov     _g_hDll, eax
0x10008b61  test    eax, eax
0x10008b63  jnz     short loc_10008B78
0x10008b65  call    ds:__imp__GetLastError@0; GetLastError()
0x10008b6b  jmp     short loc_10008BC3
0x10008b6d  push    1F4h; dwMilliseconds
0x10008b72  call    ds:__imp__Sleep@4; Sleep(x)
0x10008b78  cmp     _g_hDll, 0FFFFFFFFh
0x10008b7f  jz      short loc_10008B6D
0x10008b81  mov     eax, _g_hDll
0x10008b86  test    eax, eax
0x10008b88  jnz     short loc_10008B91
0x10008b8a  mov     eax, 3EBh
0x10008b8f  jmp     short loc_10008BC3
0x10008b91  push    edi
0x10008b92  push    edi
0x10008b93  push    [ebp+lplpszErrorString]
0x10008b96  push    400h
0x10008b9b  push    esi
0x10008b9c  push    eax
0x10008b9d  push    900h
0x10008ba2  jmp     short loc_10008BB7
0x10008ba4  xor     edi, edi
0x10008ba6  push    edi; Arguments
0x10008ba7  push    edi; nSize
0x10008ba8  push    [ebp+lplpszErrorString]; lpBuffer
0x10008bab  push    400h; dwLanguageId
0x10008bb0  push    esi; dwMessageId
0x10008bb1  push    edi; lpSource
0x10008bb2  push    1300h; dwFlags
0x10008bb7  call    ds:__imp__FormatMessageA@28; FormatMessageA(x,x,x,x,x,x,x)
0x10008bbd  test    eax, eax
0x10008bbf  jz      short loc_10008B65
0x10008bc1  xor     eax, eax
0x10008bc3  pop     edi
0x10008bc4  pop     esi
0x10008bc5  pop     ebp
0x10008bc6  retn    8
```
