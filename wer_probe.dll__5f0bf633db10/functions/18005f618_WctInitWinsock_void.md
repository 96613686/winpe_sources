# WctInitWinsock(void)

- ea: `0x18005f618`
- end: `0x18005f792`
- name: `?WctInitWinsock@@YAHXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005f798`

## callees

- `0x180050db0`
- `0x1800517cc`
- `0x18005f618`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f708`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f728`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f708`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f728`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005f76a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005f76a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005f660`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005f660`

## string_xrefs

- `0x18005f659`: `ws2_32.dll`
- `0x18005f701`: `WSACleanup`

## pseudocode

```c
__int64 WctInitWinsock(void)
{
  HMODULE LibraryW; // rax
  unsigned int v2; // ebx
  _BYTE v3[416]; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(v3, 0, 0x198u);
  if ( g_ws2_32 )
    return 1;
  LibraryW = LoadLibraryW(L"ws2_32.dll");
  g_ws2_32 = LibraryW;
  if ( !LibraryW )
    goto LABEL_13;
  g_WSAStartup = (int (*)(unsigned __int16, struct WSAData *))GetProcAddress(LibraryW, "WSAStartup");
  if ( !g_WSAStartup
    || (g_getsockopt = (int (*)(unsigned __int64, int, int, char *, int *))GetProcAddress(g_ws2_32, "getsockopt")) == 0
    || (g_getsockname = (int (*)(unsigned __int64, struct sockaddr *, int *))GetProcAddress(g_ws2_32, "getsockname")) == 0
    || (g_getpeername = (int (*)(unsigned __int64, struct sockaddr *, int *))GetProcAddress(g_ws2_32, "getpeername")) == 0
    || (g_WSACleanup = (int (*)(void))GetProcAddress(g_ws2_32, "WSACleanup")) == 0
    || (g_closesocket = (int (*)(unsigned __int64))GetProcAddress(g_ws2_32, "closesocket")) == 0
    || (unsigned int)((__int64 (__fastcall *)(__int64, _BYTE *))g_WSAStartup)(514, v3) )
  {
    LibraryW = g_ws2_32;
LABEL_13:
    v2 = 0;
    if ( LibraryW )
    {
      FreeLibrary(LibraryW);
      g_ws2_32 = 0;
    }
    return v2;
  }
  return 1;
}

```

## disassembly

```asm
0x18005f618  push    rbx
0x18005f61a  sub     rsp, 1D0h
0x18005f621  mov     rax, cs:__security_cookie
0x18005f628  xor     rax, rsp
0x18005f62b  mov     [rsp+1D8h+var_18], rax
0x18005f633  xor     edx, edx; Val
0x18005f635  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x18005f63a  mov     r8d, 198h; Size
0x18005f640  call    memset_0
0x18005f645  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x18005f64d  jz      short loc_18005F659
0x18005f64f  mov     eax, 1
0x18005f654  jmp     loc_18005F779
0x18005f659  lea     rcx, aWs232Dll; "ws2_32.dll"
0x18005f660  call    cs:__imp_LoadLibraryW
0x18005f666  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x18005f66d  test    rax, rax
0x18005f670  jz      loc_18005F760
0x18005f676  lea     rdx, aWsastartup; "WSAStartup"
0x18005f67d  mov     rcx, rax; hModule
0x18005f680  call    cs:__imp_GetProcAddress
0x18005f686  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x18005f68d  test    rax, rax
0x18005f690  jz      loc_18005F759
0x18005f696  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f69d  lea     rdx, aGetsockopt; "getsockopt"
0x18005f6a4  call    cs:__imp_GetProcAddress
0x18005f6aa  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x18005f6b1  test    rax, rax
0x18005f6b4  jz      loc_18005F759
0x18005f6ba  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f6c1  lea     rdx, aGetsockname; "getsockname"
0x18005f6c8  call    cs:__imp_GetProcAddress
0x18005f6ce  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x18005f6d5  test    rax, rax
0x18005f6d8  jz      short loc_18005F759
0x18005f6da  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f6e1  lea     rdx, aGetpeername; "getpeername"
0x18005f6e8  call    cs:__imp_GetProcAddress
0x18005f6ee  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x18005f6f5  test    rax, rax
0x18005f6f8  jz      short loc_18005F759
0x18005f6fa  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f701  lea     rdx, aWsacleanup; "WSACleanup"
0x18005f708  call    cs:__imp_GetProcAddress
0x18005f70e  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x18005f715  test    rax, rax
0x18005f718  jz      short loc_18005F759
0x18005f71a  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f721  lea     rdx, aClosesocket; "closesocket"
0x18005f728  call    cs:__imp_GetProcAddress
0x18005f72e  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x18005f735  test    rax, rax
0x18005f738  jz      short loc_18005F759
0x18005f73a  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x18005f741  lea     rdx, [rsp+1D8h+var_1B8]
0x18005f746  mov     ecx, 202h
0x18005f74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f750  test    eax, eax
0x18005f752  jnz     short loc_18005F759
0x18005f754  lea     ebx, [rax+1]
0x18005f757  jmp     short loc_18005F777
0x18005f759  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x18005f760  xor     ebx, ebx
0x18005f762  test    rax, rax
0x18005f765  jz      short loc_18005F777
0x18005f767  mov     rcx, rax; hLibModule
0x18005f76a  call    cs:__imp_FreeLibrary
0x18005f770  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x18005f777  mov     eax, ebx
0x18005f779  mov     rcx, [rsp+1D8h+var_18]
0x18005f781  xor     rcx, rsp; StackCookie
0x18005f784  call    __security_check_cookie
0x18005f789  add     rsp, 1D0h
0x18005f790  pop     rbx
0x18005f791  retn
```
