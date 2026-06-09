# WctInitWinsock(void)

- ea: `0x180061d88`
- end: `0x180061f37`
- name: `?WctInitWinsock@@YAHXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180061f40`

## callees

- `0x180053300`
- `0x180053d3c`
- `0x180061d88`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061e9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061ec0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061f08`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061f08`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180061dd0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180061dd0`

## string_xrefs

- `0x180061dc9`: `ws2_32.dll`
- `0x180061e93`: `WSACleanup`

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
0x180061d88  push    rbx
0x180061d8a  sub     rsp, 1D0h
0x180061d91  mov     rax, cs:__security_cookie
0x180061d98  xor     rax, rsp
0x180061d9b  mov     [rsp+1D8h+var_18], rax
0x180061da3  xor     edx, edx; Val
0x180061da5  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x180061daa  mov     r8d, 198h; Size
0x180061db0  call    memset_0
0x180061db5  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x180061dbd  jz      short loc_180061DC9
0x180061dbf  mov     eax, 1
0x180061dc4  jmp     loc_180061F1D
0x180061dc9  lea     rcx, aWs232Dll; "ws2_32.dll"
0x180061dd0  call    cs:__imp_LoadLibraryW
0x180061dd7  nop     dword ptr [rax+rax+00h]
0x180061ddc  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x180061de3  test    rax, rax
0x180061de6  jz      loc_180061EFE
0x180061dec  lea     rdx, aWsastartup; "WSAStartup"
0x180061df3  mov     rcx, rax; hModule
0x180061df6  call    cs:__imp_GetProcAddress
0x180061dfd  nop     dword ptr [rax+rax+00h]
0x180061e02  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x180061e09  test    rax, rax
0x180061e0c  jz      loc_180061EF7
0x180061e12  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180061e19  lea     rdx, aGetsockopt; "getsockopt"
0x180061e20  call    cs:__imp_GetProcAddress
0x180061e27  nop     dword ptr [rax+rax+00h]
0x180061e2c  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x180061e33  test    rax, rax
0x180061e36  jz      loc_180061EF7
0x180061e3c  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180061e43  lea     rdx, aGetsockname; "getsockname"
0x180061e4a  call    cs:__imp_GetProcAddress
0x180061e51  nop     dword ptr [rax+rax+00h]
0x180061e56  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x180061e5d  test    rax, rax
0x180061e60  jz      loc_180061EF7
0x180061e66  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180061e6d  lea     rdx, aGetpeername; "getpeername"
0x180061e74  call    cs:__imp_GetProcAddress
0x180061e7b  nop     dword ptr [rax+rax+00h]
0x180061e80  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x180061e87  test    rax, rax
0x180061e8a  jz      short loc_180061EF7
0x180061e8c  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180061e93  lea     rdx, aWsacleanup; "WSACleanup"
0x180061e9a  call    cs:__imp_GetProcAddress
0x180061ea1  nop     dword ptr [rax+rax+00h]
0x180061ea6  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x180061ead  test    rax, rax
0x180061eb0  jz      short loc_180061EF7
0x180061eb2  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180061eb9  lea     rdx, aClosesocket; "closesocket"
0x180061ec0  call    cs:__imp_GetProcAddress
0x180061ec7  nop     dword ptr [rax+rax+00h]
0x180061ecc  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x180061ed3  test    rax, rax
0x180061ed6  jz      short loc_180061EF7
0x180061ed8  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x180061edf  lea     rdx, [rsp+1D8h+var_1B8]
0x180061ee4  mov     ecx, 202h
0x180061ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061eee  test    eax, eax
0x180061ef0  jnz     short loc_180061EF7
0x180061ef2  lea     ebx, [rax+1]
0x180061ef5  jmp     short loc_180061F1B
0x180061ef7  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x180061efe  xor     ebx, ebx
0x180061f00  test    rax, rax
0x180061f03  jz      short loc_180061F1B
0x180061f05  mov     rcx, rax; hLibModule
0x180061f08  call    cs:__imp_FreeLibrary
0x180061f0f  nop     dword ptr [rax+rax+00h]
0x180061f14  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x180061f1b  mov     eax, ebx
0x180061f1d  mov     rcx, [rsp+1D8h+var_18]
0x180061f25  xor     rcx, rsp; StackCookie
0x180061f28  call    __security_check_cookie
0x180061f2d  add     rsp, 1D0h
0x180061f34  pop     rbx
0x180061f35  retn
```
