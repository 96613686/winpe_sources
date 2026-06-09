# JobsService::InitializeWPTS(void)

- ea: `0x18005a3dc`
- end: `0x18005a4aa`
- name: `?InitializeWPTS@JobsService@@AEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(JobsService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18004f190`

## callees

- `0x180054084`
- `0x18005a3dc`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a418`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a40d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a40d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a491`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a491`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a3f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a3f1`

## string_xrefs

- `0x18005a3e4`: `WPTaskScheduler.dll`

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
0x18005a3dc  push    rbx
0x18005a3de  sub     rsp, 20h
0x18005a3e2  xor     edx, edx; hFile
0x18005a3e4  lea     rcx, LibFileName; "WPTaskScheduler.dll"
0x18005a3eb  mov     r8d, 800h; dwFlags
0x18005a3f1  call    cs:__imp_LoadLibraryExW
0x18005a3f7  mov     cs:?g_hModuleWpts@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModuleWpts
0x18005a3fe  test    rax, rax
0x18005a401  jz      short loc_18005A418
0x18005a403  lea     rdx, aWptsinitialize; "WptsInitialize"
0x18005a40a  mov     rcx, rax; hModule
0x18005a40d  call    cs:__imp_GetProcAddress
0x18005a413  test    rax, rax
0x18005a416  jnz     short loc_18005A433
0x18005a418  call    cs:__imp_GetLastError
0x18005a41e  mov     ebx, eax
0x18005a420  test    eax, eax
0x18005a422  jle     short loc_18005A42D
0x18005a424  movzx   ebx, ax
0x18005a427  or      ebx, 80070000h
0x18005a42d  test    ebx, ebx
0x18005a42f  jns     short loc_18005A4A2
0x18005a431  jmp     short loc_18005A485
0x18005a433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a438  mov     ebx, eax
0x18005a43a  test    eax, eax
0x18005a43c  jle     short loc_18005A447
0x18005a43e  movzx   ebx, ax
0x18005a441  or      ebx, 80070000h
0x18005a447  test    ebx, ebx
0x18005a449  jns     short loc_18005A4A2
0x18005a44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a452  lea     rax, WPP_GLOBAL_Control
0x18005a459  cmp     rcx, rax
0x18005a45c  jz      short loc_18005A485
0x18005a45e  test    dword ptr [rcx+1Ch], 400h
0x18005a465  jz      short loc_18005A485
0x18005a467  cmp     byte ptr [rcx+19h], 2
0x18005a46b  jb      short loc_18005A485
0x18005a46d  mov     rcx, [rcx+10h]
0x18005a471  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005a478  mov     edx, 1Eh
0x18005a47d  mov     r9d, ebx
0x18005a480  call    WPP_SF_d
0x18005a485  mov     rcx, cs:?g_hModuleWpts@@3PEAUHINSTANCE__@@EA; hLibModule
0x18005a48c  test    rcx, rcx
0x18005a48f  jz      short loc_18005A4A2
0x18005a491  call    cs:__imp_FreeLibrary
0x18005a497  mov     cs:?g_hModuleWpts@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hModuleWpts
0x18005a4a2  mov     eax, ebx
0x18005a4a4  add     rsp, 20h
0x18005a4a8  pop     rbx
0x18005a4a9  retn
```
