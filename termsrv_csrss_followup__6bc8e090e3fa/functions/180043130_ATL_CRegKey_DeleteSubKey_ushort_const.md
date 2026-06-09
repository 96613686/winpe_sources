# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180043130`
- end: `0x180043204`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004b108`
- `0x18004b974`

## callees

- `0x180043130`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043170`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800431a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043170`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800431a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043155`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043155`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004318e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004318e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431eb`

## string_xrefs

- `0x18004314e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180043166`: `RegDeleteKeyExW`
- `0x180043187`: `advapi32.dll`
- `0x18004319f`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180043130  mov     [rsp+arg_0], rbx
0x180043135  push    rdi
0x180043136  sub     rsp, 30h
0x18004313a  mov     rdi, rdx
0x18004313d  mov     rbx, rcx
0x180043140  cmp     qword ptr [rcx+8], 0
0x180043145  jnz     short loc_1800431B9
0x180043147  cmp     qword ptr [rcx+10h], 0
0x18004314c  jnz     short loc_1800431B9
0x18004314e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180043155  call    cs:__imp_GetModuleHandleW
0x18004315c  nop     dword ptr [rax+rax+00h]
0x180043161  test    rax, rax
0x180043164  jz      short loc_180043182
0x180043166  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18004316d  mov     rcx, rax; hModule
0x180043170  call    cs:__imp_GetProcAddress
0x180043177  nop     dword ptr [rax+rax+00h]
0x18004317c  mov     [rbx+8], rax
0x180043180  jmp     short loc_1800431B9
0x180043182  xor     r8d, r8d; dwFlags
0x180043185  xor     edx, edx; hFile
0x180043187  lea     rcx, LibFileName; "advapi32.dll"
0x18004318e  call    cs:__imp_LoadLibraryExW
0x180043195  nop     dword ptr [rax+rax+00h]
0x18004319a  test    rax, rax
0x18004319d  jz      short loc_1800431B9
0x18004319f  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800431a6  mov     rcx, rax; hModule
0x1800431a9  call    cs:__imp_GetProcAddress
0x1800431b0  nop     dword ptr [rax+rax+00h]
0x1800431b5  mov     [rbx+10h], rax
0x1800431b9  mov     rax, [rbx+8]
0x1800431bd  test    rax, rax
0x1800431c0  jz      short loc_1800431D5
0x1800431c2  xor     r9d, r9d
0x1800431c5  xor     r8d, r8d
0x1800431c8  mov     rdx, rdi
0x1800431cb  mov     rcx, [rbx]
0x1800431ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431d3  jmp     short loc_1800431F8
0x1800431d5  mov     rax, [rbx+10h]
0x1800431d9  test    rax, rax
0x1800431dc  jz      short loc_1800431EB
0x1800431de  mov     rdx, rdi
0x1800431e1  mov     rcx, [rbx]
0x1800431e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431e9  jmp     short loc_1800431F8
0x1800431eb  call    cs:__imp_GetLastError
0x1800431f2  nop     dword ptr [rax+rax+00h]
0x1800431f7  nop
0x1800431f8  mov     rbx, [rsp+38h+arg_0]
0x1800431fd  add     rsp, 30h
0x180043201  pop     rdi
0x180043202  retn
```
