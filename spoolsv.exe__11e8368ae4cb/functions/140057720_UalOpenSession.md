# UalOpenSession

- ea: `0x140057720`
- end: `0x140057884`
- name: `UalOpenSession`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140048140`

## callees

- `0x14002abc0`
- `0x14002b810`
- `0x140057720`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005778f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400577af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400577cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005778f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400577af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400577cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005776a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400577e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005776a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400577e1`
- `KERNEL32!FreeLibrary` at `0x1400577fd`
- `KERNEL32!FreeLibrary` at `0x1400577fd`
- `KERNEL32!LoadLibraryExW` at `0x140057758`
- `KERNEL32!LoadLibraryExW` at `0x140057758`

## string_xrefs

- `0x14005774b`: `ualapi.dll`

## pseudocode

```c
signed int UalOpenSession()
{
  HMODULE Library; // rax
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+20h] [rbp-2C8h] BYREF
  __int128 v5; // [rsp+24h] [rbp-2C4h]
  _BYTE v6[668]; // [rsp+34h] [rbp-2B4h] BYREF

  if ( ualapiModule )
    goto LABEL_11;
  Library = LoadLibraryExW(L"ualapi.dll", 0, 0x800u);
  ualapiModule = Library;
  if ( !Library )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  fnUalInstrument = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(Library, "UalInstrument");
  if ( fnUalInstrument )
  {
    fnUalStart = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStart");
    if ( fnUalStart )
    {
      fnUalStop = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStop");
      if ( fnUalStop )
      {
LABEL_11:
        memset_0(v6, 0, sizeof(v6));
        v4 = 688;
        v5 = SumGuid_PRINT;
        return ((__int64 (__fastcall *)(int *))fnUalStart)(&v4);
      }
    }
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  FreeLibrary(ualapiModule);
  result = v3;
  ualapiModule = 0;
  fnUalInstrument = 0;
  fnUalStart = 0;
  fnUalStop = 0;
  return result;
}

```

## disassembly

```asm
0x140057720  push    rbx
0x140057722  sub     rsp, 2E0h
0x140057729  mov     rax, cs:__security_cookie
0x140057730  xor     rax, rsp
0x140057733  mov     [rsp+2E8h+var_18], rax
0x14005773b  cmp     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x140057743  jnz     loc_140057833
0x140057749  xor     edx, edx; hFile
0x14005774b  lea     rcx, aUalapiDll; "ualapi.dll"
0x140057752  mov     r8d, 800h; dwFlags
0x140057758  call    cs:__imp_LoadLibraryExW
0x14005775e  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ualapiModule
0x140057765  test    rax, rax
0x140057768  jnz     short loc_140057785
0x14005776a  call    cs:__imp_GetLastError
0x140057770  test    eax, eax
0x140057772  jle     loc_14005786B
0x140057778  movzx   eax, ax
0x14005777b  or      eax, 80070000h
0x140057780  jmp     loc_14005786B
0x140057785  lea     rdx, aUalinstrument; "UalInstrument"
0x14005778c  mov     rcx, rax; hModule
0x14005778f  call    cs:__imp_GetProcAddress
0x140057795  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x14005779c  test    rax, rax
0x14005779f  jz      short loc_1400577E1
0x1400577a1  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x1400577a8  lea     rdx, aUalstart; "UalStart"
0x1400577af  call    cs:__imp_GetProcAddress
0x1400577b5  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x1400577bc  test    rax, rax
0x1400577bf  jz      short loc_1400577E1
0x1400577c1  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x1400577c8  lea     rdx, aUalstop; "UalStop"
0x1400577cf  call    cs:__imp_GetProcAddress
0x1400577d5  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x1400577dc  test    rax, rax
0x1400577df  jnz     short loc_140057833
0x1400577e1  call    cs:__imp_GetLastError
0x1400577e7  mov     ebx, eax
0x1400577e9  test    eax, eax
0x1400577eb  jle     short loc_1400577F6
0x1400577ed  movzx   ebx, ax
0x1400577f0  or      ebx, 80070000h
0x1400577f6  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x1400577fd  call    cs:__imp_FreeLibrary
0x140057803  mov     eax, ebx
0x140057805  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x140057810  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x14005781b  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x140057826  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x140057831  jmp     short loc_14005786B
0x140057833  xor     edx, edx; Val
0x140057835  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x14005783a  mov     r8d, 29Ch; Size
0x140057840  call    memset_0
0x140057845  movups  xmm0, cs:SumGuid_PRINT
0x14005784c  mov     rax, cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x140057853  lea     rcx, [rsp+2E8h+var_2C8]
0x140057858  mov     [rsp+2E8h+var_2C8], 2B0h
0x140057860  movdqu  [rsp+2E8h+var_2C4], xmm0
0x140057866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005786b  mov     rcx, [rsp+2E8h+var_18]
0x140057873  xor     rcx, rsp; StackCookie
0x140057876  call    __security_check_cookie
0x14005787b  add     rsp, 2E0h
0x140057882  pop     rbx
0x140057883  retn
```
