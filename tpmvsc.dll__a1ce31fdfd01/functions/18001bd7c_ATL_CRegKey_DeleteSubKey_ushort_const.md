# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18001bd7c`
- end: `0x18001be31`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b7b0`

## callees

- `0x18001bd7c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001bdce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001bdce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bdb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bde3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bdb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bde3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bda1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be1f`

## string_xrefs

- `0x18001bd9a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001bdac`: `RegDeleteKeyExW`
- `0x18001bdc7`: `advapi32.dll`
- `0x18001bdd9`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001bd7c  mov     [rsp+arg_0], rbx
0x18001bd81  push    rdi
0x18001bd82  sub     rsp, 30h
0x18001bd86  mov     rdi, rdx
0x18001bd89  mov     rbx, rcx
0x18001bd8c  cmp     qword ptr [rcx+8], 0
0x18001bd91  jnz     short loc_18001BDED
0x18001bd93  cmp     qword ptr [rcx+10h], 0
0x18001bd98  jnz     short loc_18001BDED
0x18001bd9a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18001bda1  call    cs:__imp_GetModuleHandleW
0x18001bda7  test    rax, rax
0x18001bdaa  jz      short loc_18001BDC2
0x18001bdac  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18001bdb3  mov     rcx, rax; hModule
0x18001bdb6  call    cs:__imp_GetProcAddress
0x18001bdbc  mov     [rbx+8], rax
0x18001bdc0  jmp     short loc_18001BDED
0x18001bdc2  xor     r8d, r8d; dwFlags
0x18001bdc5  xor     edx, edx; hFile
0x18001bdc7  lea     rcx, LibFileName; "advapi32.dll"
0x18001bdce  call    cs:__imp_LoadLibraryExW
0x18001bdd4  test    rax, rax
0x18001bdd7  jz      short loc_18001BDED
0x18001bdd9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001bde0  mov     rcx, rax; hModule
0x18001bde3  call    cs:__imp_GetProcAddress
0x18001bde9  mov     [rbx+10h], rax
0x18001bded  mov     rax, [rbx+8]
0x18001bdf1  test    rax, rax
0x18001bdf4  jz      short loc_18001BE09
0x18001bdf6  xor     r9d, r9d
0x18001bdf9  xor     r8d, r8d
0x18001bdfc  mov     rdx, rdi
0x18001bdff  mov     rcx, [rbx]
0x18001be02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be07  jmp     short loc_18001BE26
0x18001be09  mov     rax, [rbx+10h]
0x18001be0d  test    rax, rax
0x18001be10  jz      short loc_18001BE1F
0x18001be12  mov     rdx, rdi
0x18001be15  mov     rcx, [rbx]
0x18001be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be1d  jmp     short loc_18001BE26
0x18001be1f  call    cs:__imp_GetLastError
0x18001be25  nop
0x18001be26  mov     rbx, [rsp+38h+arg_0]
0x18001be2b  add     rsp, 30h
0x18001be2f  pop     rdi
0x18001be30  retn
```
