# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1400958f0`
- end: `0x1400959a5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14009744c`
- `0x140097914`

## callees

- `0x1400958f0`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095993`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140095915`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140095915`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009592a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140095957`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009592a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140095957`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140095942`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140095942`

## string_xrefs

- `0x14009590e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140095920`: `RegDeleteKeyExW`
- `0x14009593b`: `advapi32.dll`
- `0x14009594d`: `RegDeleteKeyW`

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
0x1400958f0  mov     [rsp+arg_0], rbx
0x1400958f5  push    rdi
0x1400958f6  sub     rsp, 30h
0x1400958fa  mov     rdi, rdx
0x1400958fd  mov     rbx, rcx
0x140095900  cmp     qword ptr [rcx+8], 0
0x140095905  jnz     short loc_140095961
0x140095907  cmp     qword ptr [rcx+10h], 0
0x14009590c  jnz     short loc_140095961
0x14009590e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140095915  call    cs:__imp_GetModuleHandleW
0x14009591b  test    rax, rax
0x14009591e  jz      short loc_140095936
0x140095920  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x140095927  mov     rcx, rax; hModule
0x14009592a  call    cs:__imp_GetProcAddress
0x140095930  mov     [rbx+8], rax
0x140095934  jmp     short loc_140095961
0x140095936  xor     r8d, r8d; dwFlags
0x140095939  xor     edx, edx; hFile
0x14009593b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x140095942  call    cs:__imp_LoadLibraryExW
0x140095948  test    rax, rax
0x14009594b  jz      short loc_140095961
0x14009594d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140095954  mov     rcx, rax; hModule
0x140095957  call    cs:__imp_GetProcAddress
0x14009595d  mov     [rbx+10h], rax
0x140095961  mov     rax, [rbx+8]
0x140095965  test    rax, rax
0x140095968  jz      short loc_14009597D
0x14009596a  xor     r9d, r9d
0x14009596d  xor     r8d, r8d
0x140095970  mov     rdx, rdi
0x140095973  mov     rcx, [rbx]
0x140095976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009597b  jmp     short loc_14009599A
0x14009597d  mov     rax, [rbx+10h]
0x140095981  test    rax, rax
0x140095984  jz      short loc_140095993
0x140095986  mov     rdx, rdi
0x140095989  mov     rcx, [rbx]
0x14009598c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095991  jmp     short loc_14009599A
0x140095993  call    cs:__imp_GetLastError
0x140095999  nop
0x14009599a  mov     rbx, [rsp+38h+arg_0]
0x14009599f  add     rsp, 30h
0x1400959a3  pop     rdi
0x1400959a4  retn
```
