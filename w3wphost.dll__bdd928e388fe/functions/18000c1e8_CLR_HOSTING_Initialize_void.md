# CLR_HOSTING::Initialize(void)

- ea: `0x18000c1e8`
- end: `0x18000c2e3`
- name: `?Initialize@CLR_HOSTING@@SAJXZ`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005d44`

## callees

- `0x18000c1e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c202`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c202`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c24a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c26c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c24a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c26c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c27e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c27e`
- `iisutil!PuDbgPrint` at `0x18000c2d0`
- `iisutil!PuDbgPrint` at `0x18000c2d0`

## string_xrefs

- `0x18000c1f4`: `mscoree.dll`
- `0x18000c2a7`: `Error loading dll '%ws'. Error = 0x%x\n`
- `0x18000c2be`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\clr_hosting.cxx`

## pseudocode

```c
__int64 CLR_HOSTING::Initialize(void)
{
  HMODULE Library; // rax
  signed int v1; // eax
  unsigned int v2; // ebx
  signed int LastError; // eax

  Library = LoadLibraryExW(L"mscoree.dll", 0, 8u);
  CLR_HOSTING::s_hClrModule = Library;
  if ( Library )
  {
    CLR_HOSTING::s_pFnCoreBindToRuntimeEx = (int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const struct _GUID *, const struct _GUID *, void **))GetProcAddress(Library, "CorBindToRuntimeEx");
    if ( CLR_HOSTING::s_pFnCoreBindToRuntimeEx )
    {
      v2 = 0;
      CLR_HOSTING::s_pFnCoreBindToRuntimeHost = (int (*)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int, const struct _GUID *, const struct _GUID *, void **))GetProcAddress(CLR_HOSTING::s_hClrModule, "CorBindToRuntimeHost");
      if ( CLR_HOSTING::s_pFnCoreBindToRuntimeHost )
        return v2;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    if ( v2 + 2147024894 <= 1 || v2 == -2147024770 )
      v2 = 0;
  }
  if ( (v2 & 0x80000000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\clr_hosting.cxx",
      112,
      "CLR_HOSTING::Initialize",
      "Error loading dll '%ws'. Error = 0x%x\n");
  return v2;
}

```

## disassembly

```asm
0x18000c1e8  mov     [rsp+arg_0], rbx
0x18000c1ed  push    rdi
0x18000c1ee  sub     rsp, 40h
0x18000c1f2  xor     edx, edx; hFile
0x18000c1f4  lea     rdi, LibFileName; "mscoree.dll"
0x18000c1fb  mov     rcx, rdi; lpLibFileName
0x18000c1fe  lea     r8d, [rdx+8]; dwFlags
0x18000c202  call    cs:__imp_LoadLibraryExW
0x18000c208  mov     cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CLR_HOSTING::s_hClrModule
0x18000c20f  test    rax, rax
0x18000c212  jnz     short loc_18000C240
0x18000c214  call    cs:__imp_GetLastError
0x18000c21a  mov     ebx, eax
0x18000c21c  test    eax, eax
0x18000c21e  jle     short loc_18000C229
0x18000c220  movzx   ebx, ax
0x18000c223  or      ebx, 80070000h
0x18000c229  lea     eax, [rbx+7FF8FFFEh]
0x18000c22f  cmp     eax, 1
0x18000c232  jbe     short loc_18000C23C
0x18000c234  cmp     ebx, 8007007Eh
0x18000c23a  jnz     short loc_18000C293
0x18000c23c  xor     ebx, ebx
0x18000c23e  jmp     short loc_18000C293
0x18000c240  lea     rdx, aCorbindtorunti_0; "CorBindToRuntimeEx"
0x18000c247  mov     rcx, rax; hModule
0x18000c24a  call    cs:__imp_GetProcAddress
0x18000c250  mov     cs:?s_pFnCoreBindToRuntimeEx@CLR_HOSTING@@0P6AJPEBG0KAEBU_GUID@@1PEAPEAX@ZEA, rax; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeEx)(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x18000c257  test    rax, rax
0x18000c25a  jz      short loc_18000C27E
0x18000c25c  mov     rcx, cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA; hModule
0x18000c263  lea     rdx, aCorbindtorunti; "CorBindToRuntimeHost"
0x18000c26a  xor     ebx, ebx
0x18000c26c  call    cs:__imp_GetProcAddress
0x18000c272  mov     cs:?s_pFnCoreBindToRuntimeHost@CLR_HOSTING@@0P6AJPEBG00PEAXKAEBU_GUID@@2PEAPEAX@ZEA, rax; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeHost)(ushort const *,ushort const *,ushort const *,void *,ulong,_GUID const &,_GUID const &,void * *)
0x18000c279  test    rax, rax
0x18000c27c  jnz     short loc_18000C2D6
0x18000c27e  call    cs:__imp_GetLastError
0x18000c284  mov     ebx, eax
0x18000c286  test    eax, eax
0x18000c288  jle     short loc_18000C293
0x18000c28a  movzx   ebx, ax
0x18000c28d  or      ebx, 80070000h
0x18000c293  test    ebx, ebx
0x18000c295  jns     short loc_18000C2D6
0x18000c297  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c29e  jz      short loc_18000C2D6
0x18000c2a0  mov     rcx, cs:g_pDebug
0x18000c2a7  lea     rax, aErrorLoadingDl; "Error loading dll '%ws'. Error = 0x%x\n"
0x18000c2ae  mov     [rsp+48h+var_18], ebx
0x18000c2b2  lea     r9, aClrHostingInit; "CLR_HOSTING::Initialize"
0x18000c2b9  mov     [rsp+48h+var_20], rdi
0x18000c2be  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000c2c5  mov     r8d, 70h ; 'p'
0x18000c2cb  mov     [rsp+48h+var_28], rax
0x18000c2d0  call    cs:__imp_PuDbgPrint
0x18000c2d6  mov     eax, ebx
0x18000c2d8  mov     rbx, [rsp+48h+arg_0]
0x18000c2dd  add     rsp, 40h
0x18000c2e1  pop     rdi
0x18000c2e2  retn
```
