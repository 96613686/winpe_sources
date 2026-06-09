# RouterGetErrorStringA

- ea: `0x180008750`
- end: `0x180008836`
- name: `RouterGetErrorStringA`
- size: `230`
- prototype: `DWORD __stdcall(DWORD dwErrorCode, LPSTR *lplpszErrorString)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008980`

## callees

- `0x180008750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800087b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800087b2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800087d1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800087d1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18000881a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18000881a`

## string_xrefs

- `0x1800087a5`: `mprmsg.dll`

## pseudocode

```c
DWORD __stdcall RouterGetErrorStringA(DWORD dwErrorCode, LPSTR *lplpszErrorString)
{
  LPCVOID v4; // rdx
  DWORD v5; // ecx

  if ( dwErrorCode - 600 <= 0x116 || dwErrorCode - 900 <= 0x39 || dwErrorCode - 20000 <= 0x3E7 )
  {
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&g_hDll, -1, 0) )
    {
      g_hDll = LoadLibraryExA("mprmsg.dll", 0, 0x800u);
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
  if ( !FormatMessageA(v5, v4, dwErrorCode, 0x400u, (LPSTR)lplpszErrorString, 0, 0) )
    return GetLastError();
  return 0;
}

```

## disassembly

```asm
0x180008750  mov     [rsp+arg_0], rbx
0x180008755  mov     [rsp+arg_8], rsi
0x18000875a  push    rdi
0x18000875b  sub     rsp, 40h
0x18000875f  lea     eax, [rcx-258h]
0x180008765  mov     rdi, rdx
0x180008768  mov     ebx, ecx
0x18000876a  cmp     eax, 116h
0x18000876f  jbe     short loc_180008792
0x180008771  lea     eax, [rcx-384h]
0x180008777  cmp     eax, 39h ; '9'
0x18000877a  jbe     short loc_180008792
0x18000877c  lea     eax, [rcx-4E20h]
0x180008782  cmp     eax, 3E7h
0x180008787  jbe     short loc_180008792
0x180008789  xor     edx, edx
0x18000878b  mov     ecx, 1300h
0x180008790  jmp     short loc_1800087FB
0x180008792  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008796  xor     eax, eax
0x180008798  lock cmpxchg cs:g_hDll, rsi
0x1800087a1  jnz     short loc_1800087D7
0x1800087a3  xor     edx, edx; hFile
0x1800087a5  lea     rcx, LibFileName; "mprmsg.dll"
0x1800087ac  mov     r8d, 800h; dwFlags
0x1800087b2  call    cs:__imp_LoadLibraryExA
0x1800087b8  mov     cs:g_hDll, rax
0x1800087bf  test    rax, rax
0x1800087c2  jnz     short loc_1800087D7
0x1800087c4  call    cs:__imp_GetLastError
0x1800087ca  jmp     short loc_180008826
0x1800087cc  mov     ecx, 1F4h; dwMilliseconds
0x1800087d1  call    cs:__imp_Sleep
0x1800087d7  mov     rax, cs:g_hDll
0x1800087de  cmp     rax, rsi
0x1800087e1  jz      short loc_1800087CC
0x1800087e3  mov     rdx, cs:g_hDll; lpSource
0x1800087ea  test    rdx, rdx
0x1800087ed  jnz     short loc_1800087F6
0x1800087ef  mov     eax, 3EBh
0x1800087f4  jmp     short loc_180008826
0x1800087f6  mov     ecx, 900h; dwFlags
0x1800087fb  mov     [rsp+48h+Arguments], 0; Arguments
0x180008804  mov     r9d, 400h; dwLanguageId
0x18000880a  mov     [rsp+48h+nSize], 0; nSize
0x180008812  mov     r8d, ebx; dwMessageId
0x180008815  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000881a  call    cs:__imp_FormatMessageA
0x180008820  test    eax, eax
0x180008822  jz      short loc_1800087C4
0x180008824  xor     eax, eax
0x180008826  mov     rbx, [rsp+48h+arg_0]
0x18000882b  mov     rsi, [rsp+48h+arg_8]
0x180008830  add     rsp, 40h
0x180008834  pop     rdi
0x180008835  retn
```
