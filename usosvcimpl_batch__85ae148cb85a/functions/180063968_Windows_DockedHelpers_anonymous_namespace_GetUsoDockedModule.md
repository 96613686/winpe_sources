# Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule

- ea: `0x180063968`
- end: `0x180063a4e`
- name: `Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180063a54`

## callees

- `0x180010f24`
- `0x180042e00`
- `0x180042e48`
- `0x180063968`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800639de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800639de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800639b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800639b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063a0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063a0d`

## string_xrefs

- `0x1800639ac`: `UsoDocked.dll`
- `0x180063a1c`: `C:\__w\1\s\src\orchestrator\system\windows\common\DockedHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule()
{
  int v0; // eax
  HMODULE v1; // rbx
  HMODULE Library; // rax
  const char *v3; // r9
  HMODULE v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned int)mtx_do_lock(qword_18014D190) )
    std::_Throw_Cpp_error(5);
  v0 = dword_18014D1DC;
  if ( dword_18014D1DC == 0x7FFFFFFF )
  {
    dword_18014D1DC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v1 = hLibModule;
  if ( !hLibModule )
  {
    Library = LoadLibraryExW(L"UsoDocked.dll", 0, 0x800u);
    v1 = Library;
    if ( !Library )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x19,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\DockedHelpers.cpp",
        v3);
    v4 = hLibModule;
    hLibModule = Library;
    if ( v4 )
    {
      FreeLibrary(v4);
      v1 = hLibModule;
    }
    v0 = dword_18014D1DC;
  }
  dword_18014D1DC = v0 - 1;
  if ( v0 == 1 )
  {
    dword_18014D1D8 = -1;
    ReleaseSRWLockExclusive(&stru_18014D1A0);
  }
  return v1;
}

```

## disassembly

```asm
0x180063968  push    rbx
0x18006396a  sub     rsp, 20h
0x18006396e  lea     rcx, qword_18014D190
0x180063975  mov     [rsp+28h+arg_0], rcx
0x18006397a  call    mtx_do_lock
0x18006397f  test    eax, eax
0x180063981  jnz     loc_180063A2E
0x180063987  mov     eax, cs:dword_18014D1DC
0x18006398d  cmp     eax, 7FFFFFFFh
0x180063992  jz      loc_180063A39
0x180063998  mov     rbx, cs:hLibModule
0x18006399f  test    rbx, rbx
0x1800639a2  jnz     short loc_1800639F1
0x1800639a4  xor     edx, edx; hFile
0x1800639a6  mov     r8d, 800h; dwFlags
0x1800639ac  lea     rcx, aUsodockedDll; "UsoDocked.dll"
0x1800639b3  call    cs:__imp_LoadLibraryExW
0x1800639b9  mov     rbx, rax
0x1800639bc  mov     [rsp+28h+arg_8], rax
0x1800639c1  mov     rcx, [rsp+28h]; this
0x1800639c6  test    rax, rax
0x1800639c9  jz      short loc_180063A1C
0x1800639cb  mov     rcx, cs:hLibModule; hLibModule
0x1800639d2  mov     cs:hLibModule, rax
0x1800639d9  test    rcx, rcx
0x1800639dc  jz      short loc_1800639EB
0x1800639de  call    cs:__imp_FreeLibrary
0x1800639e4  mov     rbx, cs:hLibModule
0x1800639eb  mov     eax, cs:dword_18014D1DC
0x1800639f1  sub     eax, 1
0x1800639f4  mov     cs:dword_18014D1DC, eax
0x1800639fa  jnz     short loc_180063A13
0x1800639fc  mov     cs:dword_18014D1D8, 0FFFFFFFFh
0x180063a06  lea     rcx, stru_18014D1A0; SRWLock
0x180063a0d  call    cs:__imp_ReleaseSRWLockExclusive
0x180063a13  mov     rax, rbx
0x180063a16  add     rsp, 20h
0x180063a1a  pop     rbx
0x180063a1b  retn
0x180063a1c  lea     r8, aCW1SSrcOrchest_23; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180063a23  mov     edx, 19h; void *
0x180063a28  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180063a2e  mov     ecx, 5; int
0x180063a33  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180063a39  mov     cs:dword_18014D1DC, 7FFFFFFEh
0x180063a43  mov     ecx, 6; int
0x180063a48  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
