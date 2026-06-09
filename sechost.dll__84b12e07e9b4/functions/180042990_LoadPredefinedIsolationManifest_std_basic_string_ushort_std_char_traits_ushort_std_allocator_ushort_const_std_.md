# LoadPredefinedIsolationManifest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,int *)

- ea: `0x180042990`
- end: `0x180042a14`
- name: `?LoadPredefinedIsolationManifest@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@PEAH@Z`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180042a1c`

## callees

- `0x180019da8`
- `0x180042738`
- `0x180042990`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800429c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800429c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429e6`

## string_xrefs

- `0x1800429c2`: `sechost.dll`

## pseudocode

```c
DWORD __fastcall LoadPredefinedIsolationManifest(__int64 a1, __int64 a2, _DWORD *a3)
{
  HMODULE ModuleHandleW; // rax
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  *a3 = 0;
  if ( !(unsigned __int8)PredefinedIsolationManifests::IsPredefinedManifest(a1, &v7) )
    return 0;
  ModuleHandleW = GetModuleHandleW(L"sechost.dll");
  if ( ModuleHandleW )
    return ExtractIsolationManifestResource(ModuleHandleW, v7, a2, a3);
  if ( (int)GetLastError() > 0 )
    return (unsigned __int16)GetLastError() | 0xC0070000;
  return GetLastError();
}

```

## disassembly

```asm
0x180042990  mov     [rsp+arg_0], rbx
0x180042995  push    rdi
0x180042996  sub     rsp, 20h
0x18004299a  mov     rdi, rdx
0x18004299d  mov     [rsp+28h+arg_10], 0
0x1800429a6  lea     rdx, [rsp+28h+arg_10]
0x1800429ab  mov     dword ptr [r8], 0
0x1800429b2  mov     rbx, r8
0x1800429b5  call    ?IsPredefinedManifest@PredefinedIsolationManifests@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_K@Z; PredefinedIsolationManifests::IsPredefinedManifest(std::wstring const &,unsigned __int64 *)
0x1800429ba  test    al, al
0x1800429bc  jnz     short loc_1800429C2
0x1800429be  xor     eax, eax
0x1800429c0  jmp     short loc_180042A09
0x1800429c2  lea     rcx, aSechostDll_0; "sechost.dll"
0x1800429c9  call    cs:__imp_GetModuleHandleW
0x1800429cf  test    rax, rax
0x1800429d2  jnz     short loc_1800429F6
0x1800429d4  call    cs:__imp_GetLastError
0x1800429da  test    eax, eax
0x1800429dc  jg      short loc_1800429E6
0x1800429de  call    cs:__imp_GetLastError
0x1800429e4  jmp     short loc_180042A09
0x1800429e6  call    cs:__imp_GetLastError
0x1800429ec  movzx   eax, ax
0x1800429ef  or      eax, 0C0070000h
0x1800429f4  jmp     short loc_180042A09
0x1800429f6  mov     rdx, [rsp+28h+arg_10]
0x1800429fb  mov     r9, rbx
0x1800429fe  mov     r8, rdi
0x180042a01  mov     rcx, rax
0x180042a04  call    ?ExtractIsolationManifestResource@@YAJPEAUHINSTANCE__@@_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAH@Z; ExtractIsolationManifestResource(HINSTANCE__ *,unsigned __int64,std::wstring &,int *)
0x180042a09  mov     rbx, [rsp+28h+arg_0]
0x180042a0e  add     rsp, 20h
0x180042a12  pop     rdi
0x180042a13  retn
```
