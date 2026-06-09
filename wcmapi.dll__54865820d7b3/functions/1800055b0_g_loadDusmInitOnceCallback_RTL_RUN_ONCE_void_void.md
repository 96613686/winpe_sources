# g_loadDusmInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800055b0`
- end: `0x180005623`
- name: `?g_loadDusmInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `115`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180004d10`
- `0x1800055b0`
- `0x18000562c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800055c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800055c3`

## string_xrefs

- `0x1800055b6`: `dusmapi.dll`

## pseudocode

```c
__int64 __fastcall g_loadDusmInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  hModule = LoadLibraryExW(L"dusmapi.dll", 0, 0x800u);
  if ( hModule )
  {
    LoadDusmFuncPointers();
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800055b0  sub     rsp, 28h
0x1800055b4  xor     edx, edx; hFile
0x1800055b6  lea     rcx, LibFileName; "dusmapi.dll"
0x1800055bd  mov     r8d, 800h; dwFlags
0x1800055c3  call    cs:__imp_LoadLibraryExW
0x1800055ca  nop     dword ptr [rax+rax+00h]
0x1800055cf  mov     cs:hModule, rax
0x1800055d6  test    rax, rax
0x1800055d9  jz      short loc_1800055EB
0x1800055db  call    LoadDusmFuncPointers
0x1800055e0  mov     eax, 1
0x1800055e5  add     rsp, 28h
0x1800055e9  retn
0x1800055eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055f2  lea     rax, WPP_GLOBAL_Control
0x1800055f9  cmp     rcx, rax
0x1800055fc  jz      short loc_18000561F
0x1800055fe  cmp     byte ptr [rcx+19h], 4
0x180005602  jb      short loc_18000561F
0x180005604  test    byte ptr [rcx+1Ch], 1
0x180005608  jz      short loc_18000561F
0x18000560a  mov     rcx, [rcx+10h]
0x18000560e  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180005615  mov     edx, 0Bh
0x18000561a  call    WPP_SF_
0x18000561f  xor     eax, eax
0x180005621  jmp     short loc_1800055E5
```
