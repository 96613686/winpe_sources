# JobsService::InitializeWPTS(void)

- ea: `0x18005cdb8`
- end: `0x18005ce9f`
- name: `?InitializeWPTS@JobsService@@AEAAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(JobsService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800519e0`

## callees

- `0x180056954`
- `0x18005cdb8`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cdef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cdef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005ce7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005ce7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005cdcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005cdcd`

## string_xrefs

- `0x18005cdc0`: `WPTaskScheduler.dll`

## pseudocode

```c
__int64 __fastcall JobsService::InitializeWPTS(JobsService *this)
{
  HMODULE Library; // rax
  __int64 (*ProcAddress)(void); // rax
  signed int LastError; // eax
  signed int v4; // ebx
  int v5; // eax

  Library = LoadLibraryExW(L"WPTaskScheduler.dll", 0, 0x800u);
  g_hModuleWpts = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "WptsInitialize")) != 0 )
  {
    v5 = ProcAddress();
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids,
          (unsigned int)v4);
      }
      goto LABEL_14;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
LABEL_14:
      if ( g_hModuleWpts )
      {
        FreeLibrary(g_hModuleWpts);
        g_hModuleWpts = 0;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005cdb8  push    rbx
0x18005cdba  sub     rsp, 20h
0x18005cdbe  xor     edx, edx; hFile
0x18005cdc0  lea     rcx, LibFileName; "WPTaskScheduler.dll"
0x18005cdc7  mov     r8d, 800h; dwFlags
0x18005cdcd  call    cs:__imp_LoadLibraryExW
0x18005cdd4  nop     dword ptr [rax+rax+00h]
0x18005cdd9  mov     cs:?g_hModuleWpts@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModuleWpts
0x18005cde0  test    rax, rax
0x18005cde3  jz      short loc_18005CE00
0x18005cde5  lea     rdx, aWptsinitialize; "WptsInitialize"
0x18005cdec  mov     rcx, rax; hModule
0x18005cdef  call    cs:__imp_GetProcAddress
0x18005cdf6  nop     dword ptr [rax+rax+00h]
0x18005cdfb  test    rax, rax
0x18005cdfe  jnz     short loc_18005CE21
0x18005ce00  call    cs:__imp_GetLastError
0x18005ce07  nop     dword ptr [rax+rax+00h]
0x18005ce0c  mov     ebx, eax
0x18005ce0e  test    eax, eax
0x18005ce10  jle     short loc_18005CE1B
0x18005ce12  movzx   ebx, ax
0x18005ce15  or      ebx, 80070000h
0x18005ce1b  test    ebx, ebx
0x18005ce1d  jns     short loc_18005CE96
0x18005ce1f  jmp     short loc_18005CE73
0x18005ce21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce26  mov     ebx, eax
0x18005ce28  test    eax, eax
0x18005ce2a  jle     short loc_18005CE35
0x18005ce2c  movzx   ebx, ax
0x18005ce2f  or      ebx, 80070000h
0x18005ce35  test    ebx, ebx
0x18005ce37  jns     short loc_18005CE96
0x18005ce39  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ce40  lea     rax, WPP_GLOBAL_Control
0x18005ce47  cmp     rcx, rax
0x18005ce4a  jz      short loc_18005CE73
0x18005ce4c  test    dword ptr [rcx+1Ch], 400h
0x18005ce53  jz      short loc_18005CE73
0x18005ce55  cmp     byte ptr [rcx+19h], 2
0x18005ce59  jb      short loc_18005CE73
0x18005ce5b  mov     rcx, [rcx+10h]
0x18005ce5f  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005ce66  mov     edx, 1Eh
0x18005ce6b  mov     r9d, ebx
0x18005ce6e  call    WPP_SF_d
0x18005ce73  mov     rcx, cs:?g_hModuleWpts@@3PEAUHINSTANCE__@@EA; hLibModule
0x18005ce7a  test    rcx, rcx
0x18005ce7d  jz      short loc_18005CE96
0x18005ce7f  call    cs:__imp_FreeLibrary
0x18005ce86  nop     dword ptr [rax+rax+00h]
0x18005ce8b  mov     cs:?g_hModuleWpts@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hModuleWpts
0x18005ce96  mov     eax, ebx
0x18005ce98  add     rsp, 20h
0x18005ce9c  pop     rbx
0x18005ce9d  retn
```
