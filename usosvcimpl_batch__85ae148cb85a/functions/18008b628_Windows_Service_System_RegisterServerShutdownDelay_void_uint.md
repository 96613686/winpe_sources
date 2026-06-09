# Windows::Service::System::RegisterServerShutdownDelay(void *,uint)

- ea: `0x18008b628`
- end: `0x18008b6e7`
- name: `?RegisterServerShutdownDelay@System@Service@Windows@@UEAAXPEAXI@Z`
- size: `191`
- prototype: `void __fastcall(Windows::Service::System *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006f510`

## callees

- `0x180010f24`
- `0x1800112d0`
- `0x18008b628`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008b670`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008b670`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008b69b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008b69b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008b649`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008b649`

## string_xrefs

- `0x18008b642`: `combase.dll`
- `0x18008b6b1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\ServiceSystem.cpp`
- `0x18008b6c3`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\ServiceSystem.cpp`
- `0x18008b6d5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\ServiceSystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Service::System::RegisterServerShutdownDelay(
        Windows::Service::System *this,
        void *a2,
        unsigned int a3)
{
  HMODULE Library; // rax
  const char *v6; // r9
  HMODULE v7; // rbx
  bool v8; // di
  FARPROC ProcAddress; // rax
  const char *v10; // r9
  int v11; // eax
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Library = LoadLibraryExW(L"combase.dll", 0, 0x800u);
  v7 = Library;
  v12 = (int)Library;
  v8 = Library != 0;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x197,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\ServiceSystem.cpp",
      v6);
  ProcAddress = GetProcAddress(Library, (LPCSTR)0x45);
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\ServiceSystem.cpp",
      v10);
  v11 = ((__int64 (__fastcall *)(void *, _QWORD))ProcAddress)(a2, a3);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\ServiceSystem.cpp",
      (const char *)(unsigned int)v11,
      v12);
  if ( v8 )
    FreeLibrary(v7);
}

```

## disassembly

```asm
0x18008b628  mov     [rsp+arg_0], rbx
0x18008b62d  push    rbp
0x18008b62e  push    rsi
0x18008b62f  push    rdi
0x18008b630  sub     rsp, 30h
0x18008b634  mov     ebp, r8d
0x18008b637  mov     rsi, rdx
0x18008b63a  xor     edx, edx; hFile
0x18008b63c  mov     r8d, 800h; dwFlags
0x18008b642  lea     rcx, aCombaseDll; "combase.dll"
0x18008b649  call    cs:__imp_LoadLibraryExW
0x18008b64f  mov     rbx, rax
0x18008b652  mov     qword ptr [rsp+48h+var_28], rax; int
0x18008b657  mov     rcx, [rsp+48h]; this
0x18008b65c  test    rax, rax
0x18008b65f  setnz   dil
0x18008b663  test    rax, rax
0x18008b666  jz      short loc_18008B6C3
0x18008b668  mov     edx, 45h ; 'E'; lpProcName
0x18008b66d  mov     rcx, rax; hModule
0x18008b670  call    cs:__imp_GetProcAddress
0x18008b676  mov     rcx, [rsp+48h]; this
0x18008b67b  test    rax, rax
0x18008b67e  jz      short loc_18008B6D5
0x18008b680  mov     edx, ebp
0x18008b682  mov     rcx, rsi
0x18008b685  call    _guard_dispatch_icall
0x18008b68a  mov     rcx, [rsp+48h]; this
0x18008b68f  test    eax, eax
0x18008b691  js      short loc_18008B6AE
0x18008b693  test    dil, dil
0x18008b696  jz      short loc_18008B6A1
0x18008b698  mov     rcx, rbx; hLibModule
0x18008b69b  call    cs:__imp_FreeLibrary
0x18008b6a1  mov     rbx, [rsp+48h+arg_0]
0x18008b6a6  add     rsp, 30h
0x18008b6aa  pop     rdi
0x18008b6ab  pop     rsi
0x18008b6ac  pop     rbp
0x18008b6ad  retn
0x18008b6ae  mov     r9d, eax; char *
0x18008b6b1  lea     r8, aCW1SSrcOrchest_33; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008b6b8  mov     edx, 19Dh; void *
0x18008b6bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008b6c3  lea     r8, aCW1SSrcOrchest_33; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008b6ca  mov     edx, 197h; void *
0x18008b6cf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008b6d5  lea     r8, aCW1SSrcOrchest_33; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008b6dc  mov     edx, 19Bh; void *
0x18008b6e1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
