# GetResourceString(ulong,STRU *)

- ea: `0x140001a20`
- end: `0x140001b4c`
- name: `?GetResourceString@@YAJKPEAVSTRU@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(UINT uID, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ff8`
- `0x14000377c`

## callees

- `0x140001a20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001aff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001a4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001a4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140001ac8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140001ac8`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x140001ae1`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x140001ae1`
- `iisutil!PuDbgPrint` at `0x140001aab`
- `iisutil!PuDbgPrint` at `0x140001b34`
- `iisutil!PuDbgPrint` at `0x140001aab`
- `iisutil!PuDbgPrint` at `0x140001b34`

## string_xrefs

- `0x140001aa4`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140001b17`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140001a43`: `iisres.dll`
- `0x140001a87`: `Error Loading required resource DLL.  hr = %x\n`

## pseudocode

```c
__int64 __fastcall GetResourceString(UINT uID, LPWSTR *a2)
{
  HMODULE Library; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  unsigned int StringW; // eax
  unsigned int v8; // ecx
  DWORD LastError; // eax

  Library = g_hResourceDll;
  if ( g_hResourceDll || (Library = LoadLibraryExW(L"iisres.dll", 0, 0), (g_hResourceDll = Library) != 0) )
  {
    v6 = 0;
    while ( 1 )
    {
      StringW = LoadStringW(Library, uID, a2[4], *((_DWORD *)a2 + 10) >> 1);
      if ( !StringW )
        break;
      v8 = *((_DWORD *)a2 + 10) >> 1;
      if ( StringW < v8 )
        return v6;
      v6 = STRU::Resize((STRU *)a2, 2 * v8);
      if ( (v6 & 0x80000000) != 0 )
        return v6;
      Library = g_hResourceDll;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
        789,
        "GetResourceString",
        "Error retrieving resource id '%d'.  GetLastError = %d\n",
        uID,
        LastError);
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
        772,
        "GetResourceString",
        "Error Loading required resource DLL.  hr = %x\n",
        v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140001a20  mov     [rsp+arg_0], rbx
0x140001a25  mov     [rsp+arg_8], rsi
0x140001a2a  push    rdi
0x140001a2b  sub     rsp, 40h
0x140001a2f  mov     rax, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResourceDll
0x140001a36  mov     rdi, rdx
0x140001a39  mov     esi, ecx
0x140001a3b  test    rax, rax
0x140001a3e  jnz     short loc_140001AB6
0x140001a40  xor     r8d, r8d; dwFlags
0x140001a43  lea     rcx, aIisresDll; "iisres.dll"
0x140001a4a  xor     edx, edx; hFile
0x140001a4c  call    cs:__imp_LoadLibraryExW
0x140001a52  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResourceDll
0x140001a59  test    rax, rax
0x140001a5c  jnz     short loc_140001AB6
0x140001a5e  call    cs:__imp_GetLastError
0x140001a64  mov     ebx, eax
0x140001a66  test    eax, eax
0x140001a68  jle     short loc_140001A73
0x140001a6a  movzx   ebx, ax
0x140001a6d  or      ebx, 80070000h
0x140001a73  test    byte ptr cs:g_dwDebugFlags, 3
0x140001a7a  jz      loc_140001B3A
0x140001a80  mov     rcx, cs:g_pDebug
0x140001a87  lea     rax, aErrorLoadingRe; "Error Loading required resource DLL.  h"...
0x140001a8e  mov     [rsp+48h+var_20], ebx
0x140001a92  lea     r9, aGetresourcestr; "GetResourceString"
0x140001a99  mov     r8d, 304h
0x140001a9f  mov     [rsp+48h+var_28], rax
0x140001aa4  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140001aab  call    cs:__imp_PuDbgPrint
0x140001ab1  jmp     loc_140001B3A
0x140001ab6  xor     ebx, ebx
0x140001ab8  mov     r9d, [rdi+28h]
0x140001abc  mov     edx, esi; uID
0x140001abe  mov     r8, [rdi+20h]; lpBuffer
0x140001ac2  mov     rcx, rax; hInstance
0x140001ac5  shr     r9d, 1; cchBufferMax
0x140001ac8  call    cs:__imp_LoadStringW
0x140001ace  test    eax, eax
0x140001ad0  jz      short loc_140001AF6
0x140001ad2  mov     ecx, [rdi+28h]
0x140001ad5  shr     ecx, 1
0x140001ad7  cmp     eax, ecx
0x140001ad9  jb      short loc_140001B3A
0x140001adb  lea     edx, [rcx+rcx]
0x140001ade  mov     rcx, rdi
0x140001ae1  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x140001ae7  mov     ebx, eax
0x140001ae9  test    eax, eax
0x140001aeb  js      short loc_140001B3A
0x140001aed  mov     rax, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResourceDll
0x140001af4  jmp     short loc_140001AB8
0x140001af6  test    byte ptr cs:g_dwDebugFlags, 3
0x140001afd  jz      short loc_140001B3A
0x140001aff  call    cs:__imp_GetLastError
0x140001b05  mov     rcx, cs:g_pDebug
0x140001b0c  lea     r9, aGetresourcestr; "GetResourceString"
0x140001b13  mov     [rsp+48h+var_18], eax
0x140001b17  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140001b1e  lea     rax, aErrorRetrievin; "Error retrieving resource id '%d'.  Get"...
0x140001b25  mov     [rsp+48h+var_20], esi
0x140001b29  mov     r8d, 315h
0x140001b2f  mov     [rsp+48h+var_28], rax
0x140001b34  call    cs:__imp_PuDbgPrint
0x140001b3a  mov     rsi, [rsp+48h+arg_8]
0x140001b3f  mov     eax, ebx
0x140001b41  mov     rbx, [rsp+48h+arg_0]
0x140001b46  add     rsp, 40h
0x140001b4a  pop     rdi
0x140001b4b  retn
```
