# IdleBegin(HWND__ *)

- ea: `0x18000e7f8`
- end: `0x18000e8a8`
- name: `?IdleBegin@@YAXPEAUHWND__@@@Z`
- size: `176`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001a994`

## callees

- `0x18000e7f8`
- `0x18001be14`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000e842`
- `KERNEL32!LoadLibraryExW` at `0x18000e842`
- `KERNEL32!GetProcAddress` at `0x18000e85c`
- `KERNEL32!GetProcAddress` at `0x18000e875`
- `KERNEL32!GetProcAddress` at `0x18000e85c`
- `KERNEL32!GetProcAddress` at `0x18000e875`

## string_xrefs

- `0x18000e835`: `msidle.dll`

## pseudocode

```c
void __fastcall IdleBegin(HKEY a1, const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  unsigned int v3; // [rsp+40h] [rbp+8h] BYREF
  int v4; // [rsp+44h] [rbp+Ch]

  v4 = HIDWORD(a1);
  v3 = 0;
  if ( (unsigned int)ReadRegValue(a1, a2, L"IdleMinutes", &v3, 4u) && v3 )
    g_dwIdleMin = v3;
  Library = LoadLibraryExW(L"msidle.dll", 0, 0x800u);
  g_hinstMSIDLE = Library;
  if ( Library )
  {
    g_pfnBegin = (unsigned int (*)(void (*)(unsigned int), unsigned int, unsigned int))GetProcAddress(
                                                                                         Library,
                                                                                         (LPCSTR)3);
    g_pfnEnd = (int (*)(unsigned int))GetProcAddress(g_hinstMSIDLE, (LPCSTR)4);
    if ( g_pfnBegin )
      g_pfnBegin((void (*)(unsigned int))CThrottler::OnIdleStateChange, g_dwIdleMin, 0);
  }
}

```

## disassembly

```asm
0x18000e7f8  mov     rax, rsp
0x18000e7fb  mov     [rax+8], rcx
0x18000e7ff  sub     rsp, 38h
0x18000e803  lea     r9, [rax+8]; void *
0x18000e807  mov     dword ptr [rax+8], 0
0x18000e80e  lea     r8, aIdleminutes; "IdleMinutes"
0x18000e815  mov     dword ptr [rax-18h], 4
0x18000e81c  call    ?ReadRegValue@@YAHPEAUHKEY__@@PEBG1PEAXK@Z; ReadRegValue(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x18000e821  test    eax, eax
0x18000e823  jz      short loc_18000E833
0x18000e825  mov     eax, [rsp+38h+arg_0]
0x18000e829  test    eax, eax
0x18000e82b  jz      short loc_18000E833
0x18000e82d  mov     cs:?g_dwIdleMin@@3KA, eax; ulong g_dwIdleMin
0x18000e833  xor     edx, edx; hFile
0x18000e835  lea     rcx, LibFileName; "msidle.dll"
0x18000e83c  mov     r8d, 800h; dwFlags
0x18000e842  call    cs:__imp_LoadLibraryExW
0x18000e848  mov     cs:?g_hinstMSIDLE@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstMSIDLE
0x18000e84f  test    rax, rax
0x18000e852  jz      short loc_18000E8A3
0x18000e854  mov     edx, 3; lpProcName
0x18000e859  mov     rcx, rax; hModule
0x18000e85c  call    cs:__imp_GetProcAddress
0x18000e862  mov     rcx, cs:?g_hinstMSIDLE@@3PEAUHINSTANCE__@@EA; hModule
0x18000e869  mov     edx, 4; lpProcName
0x18000e86e  mov     cs:?g_pfnBegin@@3P6AKP6AXK@ZKK@ZEA, rax; ulong (*g_pfnBegin)(void (*)(ulong),ulong,ulong)
0x18000e875  call    cs:__imp_GetProcAddress
0x18000e87b  mov     cs:?g_pfnEnd@@3P6AHK@ZEA, rax; int (*g_pfnEnd)(ulong)
0x18000e882  mov     rax, cs:?g_pfnBegin@@3P6AKP6AXK@ZKK@ZEA; ulong (*g_pfnBegin)(void (*)(ulong),ulong,ulong)
0x18000e889  test    rax, rax
0x18000e88c  jz      short loc_18000E8A3
0x18000e88e  mov     edx, cs:?g_dwIdleMin@@3KA; ulong g_dwIdleMin
0x18000e894  lea     rcx, ?OnIdleStateChange@CThrottler@@SAXK@Z; CThrottler::OnIdleStateChange(ulong)
0x18000e89b  xor     r8d, r8d
0x18000e89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a3  add     rsp, 38h
0x18000e8a7  retn
```
