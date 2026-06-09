# SvcRelease(void)

- ea: `0x1800352d4`
- end: `0x180035348`
- name: `?SvcRelease@@YAXXZ`
- size: `116`
- prototype: `void(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d650`
- `0x1800349a8`
- `0x180039dd0`
- `0x18003a630`
- `0x1800407e0`
- `0x180070bcc`
- `0x180075140`

## callees

- `0x1800352d4`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035318`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035318`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035337`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035337`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800352f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800352f6`

## string_xrefs

- `0x1800352ef`: `combase.dll`

## pseudocode

```c
void SvcRelease(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  bool v2; // di
  FARPROC ProcAddress; // rax

  if ( dword_180150110 )
  {
    Library = LoadLibraryExW(L"combase.dll", 0, 0x800u);
    v1 = Library;
    v2 = Library != 0;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, (LPCSTR)0x44);
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD))ProcAddress)((unsigned int)dword_180150110);
    }
    if ( v2 )
      FreeLibrary(v1);
  }
}

```

## disassembly

```asm
0x1800352d4  mov     [rsp+arg_8], rbx
0x1800352d9  push    rdi
0x1800352da  sub     rsp, 20h
0x1800352de  cmp     cs:dword_180150110, 0
0x1800352e5  jz      short loc_18003533D
0x1800352e7  xor     edx, edx; hFile
0x1800352e9  mov     r8d, 800h; dwFlags
0x1800352ef  lea     rcx, aCombaseDll; "combase.dll"
0x1800352f6  call    cs:__imp_LoadLibraryExW
0x1800352fc  mov     rbx, rax
0x1800352ff  mov     [rsp+28h+arg_0], rax
0x180035304  test    rax, rax
0x180035307  setnz   dil
0x18003530b  test    rax, rax
0x18003530e  jz      short loc_18003532F
0x180035310  mov     edx, 44h ; 'D'; lpProcName
0x180035315  mov     rcx, rax; hModule
0x180035318  call    cs:__imp_GetProcAddress
0x18003531e  test    rax, rax
0x180035321  jz      short loc_18003532F
0x180035323  mov     ecx, cs:dword_180150110
0x180035329  call    _guard_dispatch_icall
0x18003532e  nop
0x18003532f  test    dil, dil
0x180035332  jz      short loc_18003533D
0x180035334  mov     rcx, rbx; hLibModule
0x180035337  call    cs:__imp_FreeLibrary
0x18003533d  mov     rbx, [rsp+28h+arg_8]
0x180035342  add     rsp, 20h
0x180035346  pop     rdi
0x180035347  retn
```
