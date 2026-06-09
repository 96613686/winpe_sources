# ResourceHolder::ExtractAndLoadResource(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1400310e4`
- end: `0x140031186`
- name: `?ExtractAndLoadResource@ResourceHolder@@AEAAKPEB_W00@Z`
- size: `162`
- prototype: `unsigned int __fastcall(ResourceHolder *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14003118c`

## callees

- `0x140031008`
- `0x1400310e4`
- `0x140031554`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x14003116b`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x14003116b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14003111b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14003111b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140031144`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140031144`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14003115a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14003115a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400310ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400310ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031129`

## string_xrefs

- `0x140031111`: `WEVT_TEMPLATE`

## pseudocode

```c
DWORD __fastcall ResourceHolder::ExtractAndLoadResource(
        ResourceHolder *this,
        const wchar_t *a2,
        wchar_t *a3,
        const wchar_t *a4)
{
  HINSTANCE Library; // rax
  HRSRC Resource; // rax
  HRSRC v8; // rbx
  DWORD LastError; // ebx
  HGLOBAL v10; // rax
  DWORD v11; // eax
  LPVOID v12; // rax

  Library = LibraryCache::LoadLibraryExW(this, a2, a3);
  *((_QWORD *)this + 5) = Library;
  if ( !Library )
    return GetLastError();
  Resource = FindResourceExW(Library, L"WEVT_TEMPLATE", L"#1", 0);
  v8 = Resource;
  if ( Resource )
  {
    v10 = LoadResource(*((HMODULE *)this + 5), Resource);
    *((_QWORD *)this + 4) = v10;
    if ( v10 )
    {
      v11 = SizeofResource(*((HMODULE *)this + 5), v8);
      *((_DWORD *)this + 6) = v11;
      if ( v11 )
      {
        v12 = LockResource(*((HGLOBAL *)this + 4));
        *(_QWORD *)this = v12;
        if ( v12 )
          return 0;
      }
    }
  }
  LastError = GetLastError();
  ResourceHolder::Close(this);
  return LastError;
}

```

## disassembly

```asm
0x1400310e4  mov     [rsp+arg_0], rbx
0x1400310e9  push    rdi
0x1400310ea  sub     rsp, 20h
0x1400310ee  mov     rdi, rcx
0x1400310f1  call    ?LoadLibraryExW@LibraryCache@@QEAAPEAUHINSTANCE__@@PEB_WPEAXK@Z; LibraryCache::LoadLibraryExW(wchar_t const *,void *,ulong)
0x1400310f6  mov     [rdi+28h], rax
0x1400310fa  test    rax, rax
0x1400310fd  jnz     short loc_140031107
0x1400310ff  call    cs:__imp_GetLastError
0x140031105  jmp     short loc_14003117B
0x140031107  xor     r9d, r9d; wLanguage
0x14003110a  lea     r8, Name; "#1"
0x140031111  lea     rdx, Type; "WEVT_TEMPLATE"
0x140031118  mov     rcx, rax; hModule
0x14003111b  call    cs:__imp_FindResourceExW
0x140031121  mov     rbx, rax
0x140031124  test    rax, rax
0x140031127  jnz     short loc_14003113D
0x140031129  call    cs:__imp_GetLastError
0x14003112f  mov     rcx, rdi; this
0x140031132  mov     ebx, eax
0x140031134  call    ?Close@ResourceHolder@@QEAAXXZ; ResourceHolder::Close(void)
0x140031139  mov     eax, ebx
0x14003113b  jmp     short loc_14003117B
0x14003113d  mov     rcx, [rdi+28h]; hModule
0x140031141  mov     rdx, rbx; hResInfo
0x140031144  call    cs:__imp_LoadResource
0x14003114a  mov     [rdi+20h], rax
0x14003114e  test    rax, rax
0x140031151  jz      short loc_140031129
0x140031153  mov     rcx, [rdi+28h]; hModule
0x140031157  mov     rdx, rbx; hResInfo
0x14003115a  call    cs:__imp_SizeofResource
0x140031160  mov     [rdi+18h], eax
0x140031163  test    eax, eax
0x140031165  jz      short loc_140031129
0x140031167  mov     rcx, [rdi+20h]; hResData
0x14003116b  call    cs:__imp_LockResource
0x140031171  mov     [rdi], rax
0x140031174  test    rax, rax
0x140031177  jz      short loc_140031129
0x140031179  xor     eax, eax
0x14003117b  mov     rbx, [rsp+28h+arg_0]
0x140031180  add     rsp, 20h
0x140031184  pop     rdi
0x140031185  retn
```
