# RouterGetErrorStringW(x,x)

- ea: `0x100091f0`
- end: `0x100092b9`
- name: `_RouterGetErrorStringW@8`
- size: `201`
- prototype: `DWORD __stdcall(DWORD dwErrorCode, LPWSTR *lplpwszErrorString)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10009330`

## callees

- `0x100091f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10009255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10009255`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10009246`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10009246`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10009262`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10009262`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x100092a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x100092a7`

## string_xrefs

- `0x10009241`: `mprmsg.dll`

## pseudocode

```c
DWORD __stdcall RouterGetErrorStringW(DWORD dwErrorCode, LPWSTR *lplpwszErrorString)
{
  DWORD v3; // eax

  if ( (dwErrorCode < 0x258 || dwErrorCode > 0x36E)
    && (dwErrorCode < 0x384 || dwErrorCode > 0x3BD)
    && dwErrorCode - 20000 > 0x3E7 )
  {
    v3 = FormatMessageW(0x1300u, 0, dwErrorCode, 0x400u, (LPWSTR)lplpwszErrorString, 0, 0);
  }
  else
  {
    if ( !_InterlockedCompareExchange(&g_hDll, -1, 0) )
    {
      g_hDll = (int)LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
      if ( !g_hDll )
        return GetLastError();
    }
    while ( g_hDll == -1 )
      Sleep(0x1F4u);
    if ( !g_hDll )
      return 1003;
    v3 = FormatMessageW(0x900u, (LPCVOID)g_hDll, dwErrorCode, 0x400u, (LPWSTR)lplpwszErrorString, 0, 0);
  }
  if ( !v3 )
    return GetLastError();
  return 0;
}

```

## disassembly

```asm
0x100091f0  mov     edi, edi
0x100091f2  push    ebp
0x100091f3  mov     ebp, esp
0x100091f5  push    esi
0x100091f6  mov     esi, [ebp+dwErrorCode]
0x100091f9  push    edi
0x100091fa  cmp     esi, 258h
0x10009200  jb      short loc_1000920A
0x10009202  cmp     esi, 36Eh
0x10009208  jbe     short loc_10009227
0x1000920a  cmp     esi, 384h
0x10009210  jb      short loc_1000921A
0x10009212  cmp     esi, 3BDh
0x10009218  jbe     short loc_10009227
0x1000921a  lea     eax, [esi-4E20h]
0x10009220  cmp     eax, 3E7h
0x10009225  ja      short loc_10009294
0x10009227  or      ecx, 0FFFFFFFFh
0x1000922a  mov     edx, offset _g_hDll
0x1000922f  xor     eax, eax
0x10009231  lock cmpxchg [edx], ecx
0x10009235  xor     edi, edi
0x10009237  test    eax, eax
0x10009239  jnz     short loc_10009268
0x1000923b  push    800h; dwFlags
0x10009240  push    edi; hFile
0x10009241  push    offset aMprmsgDll; "mprmsg.dll"
0x10009246  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x1000924c  mov     _g_hDll, eax
0x10009251  test    eax, eax
0x10009253  jnz     short loc_10009268
0x10009255  call    ds:__imp__GetLastError@0; GetLastError()
0x1000925b  jmp     short loc_100092B3
0x1000925d  push    1F4h; dwMilliseconds
0x10009262  call    ds:__imp__Sleep@4; Sleep(x)
0x10009268  cmp     _g_hDll, 0FFFFFFFFh
0x1000926f  jz      short loc_1000925D
0x10009271  mov     eax, _g_hDll
0x10009276  test    eax, eax
0x10009278  jnz     short loc_10009281
0x1000927a  mov     eax, 3EBh
0x1000927f  jmp     short loc_100092B3
0x10009281  push    edi
0x10009282  push    edi
0x10009283  push    [ebp+lplpwszErrorString]
0x10009286  push    400h
0x1000928b  push    esi
0x1000928c  push    eax
0x1000928d  push    900h
0x10009292  jmp     short loc_100092A7
0x10009294  xor     edi, edi
0x10009296  push    edi; Arguments
0x10009297  push    edi; nSize
0x10009298  push    [ebp+lplpwszErrorString]; lpBuffer
0x1000929b  push    400h; dwLanguageId
0x100092a0  push    esi; dwMessageId
0x100092a1  push    edi; lpSource
0x100092a2  push    1300h; dwFlags
0x100092a7  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x100092ad  test    eax, eax
0x100092af  jz      short loc_10009255
0x100092b1  xor     eax, eax
0x100092b3  pop     edi
0x100092b4  pop     esi
0x100092b5  pop     ebp
0x100092b6  retn    8
```
