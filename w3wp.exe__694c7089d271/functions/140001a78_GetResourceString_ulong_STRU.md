# GetResourceString(ulong,STRU *)

- ea: `0x140001a78`
- end: `0x140001bd3`
- name: `?GetResourceString@@YAJKPEAVSTRU@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(UINT uID, LPWSTR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002118`
- `0x140003b4c`

## callees

- `0x140001a78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001b79`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001aa8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001aa8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140001b36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140001b36`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x140001b55`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x140001b55`
- `iisutil!PuDbgPrint` at `0x140001b13`
- `iisutil!PuDbgPrint` at `0x140001bb4`
- `iisutil!PuDbgPrint` at `0x140001b13`
- `iisutil!PuDbgPrint` at `0x140001bb4`

## string_xrefs

- `0x140001b0c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140001b97`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140001a9f`: `iisres.dll`
- `0x140001aef`: `Error Loading required resource DLL.  hr = %x\n`

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
0x140001a78  mov     [rsp+arg_0], rbx
0x140001a7d  mov     [rsp+arg_8], rsi
0x140001a82  push    rdi
0x140001a83  sub     rsp, 40h
0x140001a87  mov     rax, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResourceDll
0x140001a8e  mov     rdi, rdx
0x140001a91  mov     esi, ecx
0x140001a93  test    rax, rax
0x140001a96  jnz     loc_140001B24
0x140001a9c  xor     r8d, r8d; dwFlags
0x140001a9f  lea     rcx, aIisresDll; "iisres.dll"
0x140001aa6  xor     edx, edx; hFile
0x140001aa8  call    cs:__imp_LoadLibraryExW
0x140001aaf  nop     dword ptr [rax+rax+00h]
0x140001ab4  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResourceDll
0x140001abb  test    rax, rax
0x140001abe  jnz     short loc_140001B24
0x140001ac0  call    cs:__imp_GetLastError
0x140001ac7  nop     dword ptr [rax+rax+00h]
0x140001acc  mov     ebx, eax
0x140001ace  test    eax, eax
0x140001ad0  jle     short loc_140001ADB
0x140001ad2  movzx   ebx, ax
0x140001ad5  or      ebx, 80070000h
0x140001adb  test    byte ptr cs:g_dwDebugFlags, 3
0x140001ae2  jz      loc_140001BC0
0x140001ae8  mov     rcx, cs:g_pDebug
0x140001aef  lea     rax, aErrorLoadingRe; "Error Loading required resource DLL.  h"...
0x140001af6  mov     [rsp+48h+var_20], ebx
0x140001afa  lea     r9, aGetresourcestr; "GetResourceString"
0x140001b01  mov     r8d, 304h
0x140001b07  mov     [rsp+48h+var_28], rax
0x140001b0c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140001b13  call    cs:__imp_PuDbgPrint
0x140001b1a  nop     dword ptr [rax+rax+00h]
0x140001b1f  jmp     loc_140001BC0
0x140001b24  xor     ebx, ebx
0x140001b26  mov     r9d, [rdi+28h]
0x140001b2a  mov     edx, esi; uID
0x140001b2c  mov     r8, [rdi+20h]; lpBuffer
0x140001b30  mov     rcx, rax; hInstance
0x140001b33  shr     r9d, 1; cchBufferMax
0x140001b36  call    cs:__imp_LoadStringW
0x140001b3d  nop     dword ptr [rax+rax+00h]
0x140001b42  test    eax, eax
0x140001b44  jz      short loc_140001B70
0x140001b46  mov     ecx, [rdi+28h]
0x140001b49  shr     ecx, 1
0x140001b4b  cmp     eax, ecx
0x140001b4d  jb      short loc_140001BC0
0x140001b4f  lea     edx, [rcx+rcx]
0x140001b52  mov     rcx, rdi
0x140001b55  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x140001b5c  nop     dword ptr [rax+rax+00h]
0x140001b61  mov     ebx, eax
0x140001b63  test    eax, eax
0x140001b65  js      short loc_140001BC0
0x140001b67  mov     rax, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResourceDll
0x140001b6e  jmp     short loc_140001B26
0x140001b70  test    byte ptr cs:g_dwDebugFlags, 3
0x140001b77  jz      short loc_140001BC0
0x140001b79  call    cs:__imp_GetLastError
0x140001b80  nop     dword ptr [rax+rax+00h]
0x140001b85  mov     rcx, cs:g_pDebug
0x140001b8c  lea     r9, aGetresourcestr; "GetResourceString"
0x140001b93  mov     [rsp+48h+var_18], eax
0x140001b97  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140001b9e  lea     rax, aErrorRetrievin; "Error retrieving resource id '%d'.  Get"...
0x140001ba5  mov     [rsp+48h+var_20], esi
0x140001ba9  mov     r8d, 315h
0x140001baf  mov     [rsp+48h+var_28], rax
0x140001bb4  call    cs:__imp_PuDbgPrint
0x140001bbb  nop     dword ptr [rax+rax+00h]
0x140001bc0  mov     rsi, [rsp+48h+arg_8]
0x140001bc5  mov     eax, ebx
0x140001bc7  mov     rbx, [rsp+48h+arg_0]
0x140001bcc  add     rsp, 40h
0x140001bd0  pop     rdi
0x140001bd1  retn
```
