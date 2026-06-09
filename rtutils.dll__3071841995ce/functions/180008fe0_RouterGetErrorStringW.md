# RouterGetErrorStringW

- ea: `0x180008fe0`
- end: `0x1800090c6`
- name: `RouterGetErrorStringW`
- size: `230`
- prototype: `DWORD __stdcall(DWORD dwErrorCode, LPWSTR *lplpwszErrorString)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009170`

## callees

- `0x180008fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009054`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009042`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009042`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009061`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009061`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800090aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800090aa`

## string_xrefs

- `0x180009035`: `mprmsg.dll`

## pseudocode

```c
DWORD __stdcall RouterGetErrorStringW(DWORD dwErrorCode, LPWSTR *lplpwszErrorString)
{
  LPCVOID v4; // rdx
  DWORD v5; // ecx

  if ( dwErrorCode - 600 <= 0x116 || dwErrorCode - 900 <= 0x39 || dwErrorCode - 20000 <= 0x3E7 )
  {
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&g_hDll, -1, 0) )
    {
      g_hDll = LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
      if ( !g_hDll )
        return GetLastError();
    }
    while ( g_hDll == (LPCVOID)-1LL )
      Sleep(0x1F4u);
    v4 = g_hDll;
    if ( !g_hDll )
      return 1003;
    v5 = 2304;
  }
  else
  {
    v4 = 0;
    v5 = 4864;
  }
  if ( !FormatMessageW(v5, v4, dwErrorCode, 0x400u, (LPWSTR)lplpwszErrorString, 0, 0) )
    return GetLastError();
  return 0;
}

```

## disassembly

```asm
0x180008fe0  mov     [rsp+arg_0], rbx
0x180008fe5  mov     [rsp+arg_8], rsi
0x180008fea  push    rdi
0x180008feb  sub     rsp, 40h
0x180008fef  lea     eax, [rcx-258h]
0x180008ff5  mov     rdi, rdx
0x180008ff8  mov     ebx, ecx
0x180008ffa  cmp     eax, 116h
0x180008fff  jbe     short loc_180009022
0x180009001  lea     eax, [rcx-384h]
0x180009007  cmp     eax, 39h ; '9'
0x18000900a  jbe     short loc_180009022
0x18000900c  lea     eax, [rcx-4E20h]
0x180009012  cmp     eax, 3E7h
0x180009017  jbe     short loc_180009022
0x180009019  xor     edx, edx
0x18000901b  mov     ecx, 1300h
0x180009020  jmp     short loc_18000908B
0x180009022  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009026  xor     eax, eax
0x180009028  lock cmpxchg cs:g_hDll, rsi
0x180009031  jnz     short loc_180009067
0x180009033  xor     edx, edx; hFile
0x180009035  lea     rcx, aMprmsgDll; "mprmsg.dll"
0x18000903c  mov     r8d, 800h; dwFlags
0x180009042  call    cs:__imp_LoadLibraryExW
0x180009048  mov     cs:g_hDll, rax
0x18000904f  test    rax, rax
0x180009052  jnz     short loc_180009067
0x180009054  call    cs:__imp_GetLastError
0x18000905a  jmp     short loc_1800090B6
0x18000905c  mov     ecx, 1F4h; dwMilliseconds
0x180009061  call    cs:__imp_Sleep
0x180009067  mov     rax, cs:g_hDll
0x18000906e  cmp     rax, rsi
0x180009071  jz      short loc_18000905C
0x180009073  mov     rdx, cs:g_hDll; lpSource
0x18000907a  test    rdx, rdx
0x18000907d  jnz     short loc_180009086
0x18000907f  mov     eax, 3EBh
0x180009084  jmp     short loc_1800090B6
0x180009086  mov     ecx, 900h; dwFlags
0x18000908b  mov     [rsp+48h+Arguments], 0; Arguments
0x180009094  mov     r9d, 400h; dwLanguageId
0x18000909a  mov     [rsp+48h+nSize], 0; nSize
0x1800090a2  mov     r8d, ebx; dwMessageId
0x1800090a5  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800090aa  call    cs:__imp_FormatMessageW
0x1800090b0  test    eax, eax
0x1800090b2  jz      short loc_180009054
0x1800090b4  xor     eax, eax
0x1800090b6  mov     rbx, [rsp+48h+arg_0]
0x1800090bb  mov     rsi, [rsp+48h+arg_8]
0x1800090c0  add     rsp, 40h
0x1800090c4  pop     rdi
0x1800090c5  retn
```
