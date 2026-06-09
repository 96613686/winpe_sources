# RegisterSecurityCenterBroker

- ea: `0x18001cf9c`
- end: `0x18001d01c`
- name: `RegisterSecurityCenterBroker`
- size: `128`
- prototype: `signed int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d2f0`

## callees

- `0x18001cf9c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cfb1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001cfb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cfea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cff8`

## string_xrefs

- `0x18001cfa4`: `SecurityCenterBroker.dll`
- `0x18001cfe0`: `RegisterSecurityCenterBroker`

## pseudocode

```c
signed int RegisterSecurityCenterBroker()
{
  HMODULE Library; // rax
  signed int result; // eax
  bool v2; // sf
  __int64 (*ProcAddress)(void); // rbx
  bool v4; // sf

  Library = LoadLibraryExW(L"SecurityCenterBroker.dll", 0, 0x800u);
  g_hBroker = Library;
  if ( Library )
    goto LABEL_6;
  result = GetLastError();
  v2 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v2 = result < 0;
  }
  if ( !v2 )
  {
    Library = g_hBroker;
LABEL_6:
    ProcAddress = GetProcAddress(Library, "RegisterSecurityCenterBroker");
    if ( ProcAddress )
      return ProcAddress();
    result = GetLastError();
    v4 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v4 = result < 0;
    }
    if ( !v4 )
      return ProcAddress();
  }
  return result;
}

```

## disassembly

```asm
0x18001cf9c  push    rbx
0x18001cf9e  sub     rsp, 20h
0x18001cfa2  xor     edx, edx; hFile
0x18001cfa4  lea     rcx, aSecuritycenter_1; "SecurityCenterBroker.dll"
0x18001cfab  mov     r8d, 800h; dwFlags
0x18001cfb1  call    cs:__imp_LoadLibraryExW
0x18001cfb7  mov     cs:?g_hBroker@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hBroker
0x18001cfbe  test    rax, rax
0x18001cfc1  jnz     short loc_18001CFE0
0x18001cfc3  call    cs:__imp_GetLastError
0x18001cfc9  test    eax, eax
0x18001cfcb  jle     short loc_18001CFD7
0x18001cfcd  movzx   eax, ax
0x18001cfd0  or      eax, 80070000h
0x18001cfd5  test    eax, eax
0x18001cfd7  js      short loc_18001D016
0x18001cfd9  mov     rax, cs:?g_hBroker@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hBroker
0x18001cfe0  lea     rdx, aRegistersecuri; "RegisterSecurityCenterBroker"
0x18001cfe7  mov     rcx, rax; hModule
0x18001cfea  call    cs:__imp_GetProcAddress
0x18001cff0  mov     rbx, rax
0x18001cff3  test    rax, rax
0x18001cff6  jnz     short loc_18001D00E
0x18001cff8  call    cs:__imp_GetLastError
0x18001cffe  test    eax, eax
0x18001d000  jle     short loc_18001D00C
0x18001d002  movzx   eax, ax
0x18001d005  or      eax, 80070000h
0x18001d00a  test    eax, eax
0x18001d00c  js      short loc_18001D016
0x18001d00e  mov     rax, rbx
0x18001d011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d016  add     rsp, 20h
0x18001d01a  pop     rbx
0x18001d01b  retn
```
