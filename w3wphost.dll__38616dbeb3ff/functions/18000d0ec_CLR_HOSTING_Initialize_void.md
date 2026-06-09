# CLR_HOSTING::Initialize(void)

- ea: `0x18000d0ec`
- end: `0x18000d20c`
- name: `?Initialize@CLR_HOSTING@@SAJXZ`
- size: `288`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800062bc`

## callees

- `0x18000d0ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d106`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d106`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d15a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d182`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d15a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d19a`
- `iisutil!PuDbgPrint` at `0x18000d1f2`
- `iisutil!PuDbgPrint` at `0x18000d1f2`

## string_xrefs

- `0x18000d0f8`: `mscoree.dll`
- `0x18000d1c9`: `Error loading dll '%ws'. Error = 0x%x\n`
- `0x18000d1e0`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\clr_hosting.cxx`

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
    CLR_HOSTING::s_pFnCoreBindToRuntimeEx = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(Library, "CorBindToRuntimeEx");
    if ( CLR_HOSTING::s_pFnCoreBindToRuntimeEx )
    {
      v2 = 0;
      CLR_HOSTING::s_pFnCoreBindToRuntimeHost = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(CLR_HOSTING::s_hClrModule, "CorBindToRuntimeHost");
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
      "Error loading dll '%ws'. Error = 0x%x\n",
      L"mscoree.dll",
      v2);
  return v2;
}

```

## disassembly

```asm
0x18000d0ec  mov     [rsp+arg_0], rbx
0x18000d0f1  push    rdi
0x18000d0f2  sub     rsp, 40h
0x18000d0f6  xor     edx, edx; hFile
0x18000d0f8  lea     rdi, LibFileName; "mscoree.dll"
0x18000d0ff  mov     rcx, rdi; lpLibFileName
0x18000d102  lea     r8d, [rdx+8]; dwFlags
0x18000d106  call    cs:__imp_LoadLibraryExW
0x18000d10d  nop     dword ptr [rax+rax+00h]
0x18000d112  mov     cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CLR_HOSTING::s_hClrModule
0x18000d119  test    rax, rax
0x18000d11c  jnz     short loc_18000D150
0x18000d11e  call    cs:__imp_GetLastError
0x18000d125  nop     dword ptr [rax+rax+00h]
0x18000d12a  mov     ebx, eax
0x18000d12c  test    eax, eax
0x18000d12e  jle     short loc_18000D139
0x18000d130  movzx   ebx, ax
0x18000d133  or      ebx, 80070000h
0x18000d139  lea     eax, [rbx+7FF8FFFEh]
0x18000d13f  cmp     eax, 1
0x18000d142  jbe     short loc_18000D14C
0x18000d144  cmp     ebx, 8007007Eh
0x18000d14a  jnz     short loc_18000D1B5
0x18000d14c  xor     ebx, ebx
0x18000d14e  jmp     short loc_18000D1B5
0x18000d150  lea     rdx, aCorbindtorunti_0; "CorBindToRuntimeEx"
0x18000d157  mov     rcx, rax; hModule
0x18000d15a  call    cs:__imp_GetProcAddress
0x18000d161  nop     dword ptr [rax+rax+00h]
0x18000d166  mov     cs:?s_pFnCoreBindToRuntimeEx@CLR_HOSTING@@0P6AJPEBG0KAEBU_GUID@@1PEAPEAX@ZEA, rax; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeEx)(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x18000d16d  test    rax, rax
0x18000d170  jz      short loc_18000D19A
0x18000d172  mov     rcx, cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA; hModule
0x18000d179  lea     rdx, aCorbindtorunti; "CorBindToRuntimeHost"
0x18000d180  xor     ebx, ebx
0x18000d182  call    cs:__imp_GetProcAddress
0x18000d189  nop     dword ptr [rax+rax+00h]
0x18000d18e  mov     cs:?s_pFnCoreBindToRuntimeHost@CLR_HOSTING@@0P6AJPEBG00PEAXKAEBU_GUID@@2PEAPEAX@ZEA, rax; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeHost)(ushort const *,ushort const *,ushort const *,void *,ulong,_GUID const &,_GUID const &,void * *)
0x18000d195  test    rax, rax
0x18000d198  jnz     short loc_18000D1FE
0x18000d19a  call    cs:__imp_GetLastError
0x18000d1a1  nop     dword ptr [rax+rax+00h]
0x18000d1a6  mov     ebx, eax
0x18000d1a8  test    eax, eax
0x18000d1aa  jle     short loc_18000D1B5
0x18000d1ac  movzx   ebx, ax
0x18000d1af  or      ebx, 80070000h
0x18000d1b5  test    ebx, ebx
0x18000d1b7  jns     short loc_18000D1FE
0x18000d1b9  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d1c0  jz      short loc_18000D1FE
0x18000d1c2  mov     rcx, cs:g_pDebug
0x18000d1c9  lea     rax, aErrorLoadingDl; "Error loading dll '%ws'. Error = 0x%x\n"
0x18000d1d0  mov     [rsp+48h+var_18], ebx
0x18000d1d4  lea     r9, aClrHostingInit; "CLR_HOSTING::Initialize"
0x18000d1db  mov     [rsp+48h+var_20], rdi
0x18000d1e0  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000d1e7  mov     r8d, 70h ; 'p'
0x18000d1ed  mov     [rsp+48h+var_28], rax
0x18000d1f2  call    cs:__imp_PuDbgPrint
0x18000d1f9  nop     dword ptr [rax+rax+00h]
0x18000d1fe  mov     eax, ebx
0x18000d200  mov     rbx, [rsp+48h+arg_0]
0x18000d205  add     rsp, 40h
0x18000d209  pop     rdi
0x18000d20a  retn
```
