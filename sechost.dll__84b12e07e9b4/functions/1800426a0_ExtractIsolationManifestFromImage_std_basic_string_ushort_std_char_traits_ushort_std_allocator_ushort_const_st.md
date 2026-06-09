# ExtractIsolationManifestFromImage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,int *)

- ea: `0x1800426a0`
- end: `0x18004272f`
- name: `?ExtractIsolationManifestFromImage@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@PEAH@Z`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180042a1c`

## callees

- `0x1800426a0`
- `0x180042738`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800426cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800426cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042717`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800426ee`

## pseudocode

```c
__int64 __fastcall ExtractIsolationManifestFromImage(const WCHAR *a1, __int64 a2, _DWORD *a3)
{
  HMODULE Library; // rax
  HMODULE v6; // rdi
  unsigned int IsolationManifestResource; // ebx

  *a3 = 0;
  if ( *((_QWORD *)a1 + 3) >= 8u )
    a1 = *(const WCHAR **)a1;
  Library = LoadLibraryExW(a1, 0, 0x22u);
  v6 = Library;
  if ( Library )
  {
    IsolationManifestResource = ExtractIsolationManifestResource(Library, 4, a2, a3);
    FreeLibrary(v6);
  }
  else if ( (int)GetLastError() > 0 )
  {
    return (unsigned __int16)GetLastError() | 0xC0070000;
  }
  else
  {
    return GetLastError();
  }
  return IsolationManifestResource;
}

```

## disassembly

```asm
0x1800426a0  mov     [rsp+arg_0], rbx
0x1800426a5  mov     [rsp+arg_8], rsi
0x1800426aa  push    rdi
0x1800426ab  sub     rsp, 20h
0x1800426af  mov     dword ptr [r8], 0
0x1800426b6  mov     rbx, r8
0x1800426b9  cmp     qword ptr [rcx+18h], 8
0x1800426be  mov     rsi, rdx
0x1800426c1  jb      short loc_1800426C6
0x1800426c3  mov     rcx, [rcx]; lpLibFileName
0x1800426c6  xor     edx, edx; hFile
0x1800426c8  lea     r8d, [rdx+22h]; dwFlags
0x1800426cc  call    cs:__imp_LoadLibraryExW
0x1800426d2  mov     rdi, rax
0x1800426d5  test    rax, rax
0x1800426d8  jnz     short loc_1800426FF
0x1800426da  call    cs:__imp_GetLastError
0x1800426e0  test    eax, eax
0x1800426e2  jg      short loc_1800426EE
0x1800426e4  call    cs:__imp_GetLastError
0x1800426ea  mov     ebx, eax
0x1800426ec  jmp     short loc_18004271D
0x1800426ee  call    cs:__imp_GetLastError
0x1800426f4  movzx   ebx, ax
0x1800426f7  or      ebx, 0C0070000h
0x1800426fd  jmp     short loc_18004271D
0x1800426ff  mov     r9, rbx
0x180042702  mov     r8, rsi
0x180042705  mov     edx, 4
0x18004270a  mov     rcx, rdi
0x18004270d  call    ?ExtractIsolationManifestResource@@YAJPEAUHINSTANCE__@@_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAH@Z; ExtractIsolationManifestResource(HINSTANCE__ *,unsigned __int64,std::wstring &,int *)
0x180042712  mov     ebx, eax
0x180042714  mov     rcx, rdi; hLibModule
0x180042717  call    cs:__imp_FreeLibrary
0x18004271d  mov     rsi, [rsp+28h+arg_8]
0x180042722  mov     eax, ebx
0x180042724  mov     rbx, [rsp+28h+arg_0]
0x180042729  add     rsp, 20h
0x18004272d  pop     rdi
0x18004272e  retn
```
