# UalOpenSession

- ea: `0x14005cd4c`
- end: `0x14005cedb`
- name: `UalOpenSession`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14004c580`

## callees

- `0x14002d0a0`
- `0x14002dd20`
- `0x14005cd4c`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005cdc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005cded`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005ce13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005cdc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005cded`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005ce13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ce2b`
- `KERNEL32!FreeLibrary` at `0x14005ce4d`
- `KERNEL32!FreeLibrary` at `0x14005ce4d`
- `KERNEL32!LoadLibraryExW` at `0x14005cd84`
- `KERNEL32!LoadLibraryExW` at `0x14005cd84`

## string_xrefs

- `0x14005cd77`: `ualapi.dll`

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
0x14005cd4c  push    rbx
0x14005cd4e  sub     rsp, 2E0h
0x14005cd55  mov     rax, cs:__security_cookie
0x14005cd5c  xor     rax, rsp
0x14005cd5f  mov     [rsp+2E8h+var_18], rax
0x14005cd67  cmp     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x14005cd6f  jnz     loc_14005CE89
0x14005cd75  xor     edx, edx; hFile
0x14005cd77  lea     rcx, aUalapiDll; "ualapi.dll"
0x14005cd7e  mov     r8d, 800h; dwFlags
0x14005cd84  call    cs:__imp_LoadLibraryExW
0x14005cd8b  nop     dword ptr [rax+rax+00h]
0x14005cd90  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ualapiModule
0x14005cd97  test    rax, rax
0x14005cd9a  jnz     short loc_14005CDBD
0x14005cd9c  call    cs:__imp_GetLastError
0x14005cda3  nop     dword ptr [rax+rax+00h]
0x14005cda8  test    eax, eax
0x14005cdaa  jle     loc_14005CEC1
0x14005cdb0  movzx   eax, ax
0x14005cdb3  or      eax, 80070000h
0x14005cdb8  jmp     loc_14005CEC1
0x14005cdbd  lea     rdx, aUalinstrument; "UalInstrument"
0x14005cdc4  mov     rcx, rax; hModule
0x14005cdc7  call    cs:__imp_GetProcAddress
0x14005cdce  nop     dword ptr [rax+rax+00h]
0x14005cdd3  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x14005cdda  test    rax, rax
0x14005cddd  jz      short loc_14005CE2B
0x14005cddf  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x14005cde6  lea     rdx, aUalstart; "UalStart"
0x14005cded  call    cs:__imp_GetProcAddress
0x14005cdf4  nop     dword ptr [rax+rax+00h]
0x14005cdf9  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x14005ce00  test    rax, rax
0x14005ce03  jz      short loc_14005CE2B
0x14005ce05  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x14005ce0c  lea     rdx, aUalstop; "UalStop"
0x14005ce13  call    cs:__imp_GetProcAddress
0x14005ce1a  nop     dword ptr [rax+rax+00h]
0x14005ce1f  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x14005ce26  test    rax, rax
0x14005ce29  jnz     short loc_14005CE89
0x14005ce2b  call    cs:__imp_GetLastError
0x14005ce32  nop     dword ptr [rax+rax+00h]
0x14005ce37  mov     ebx, eax
0x14005ce39  test    eax, eax
0x14005ce3b  jle     short loc_14005CE46
0x14005ce3d  movzx   ebx, ax
0x14005ce40  or      ebx, 80070000h
0x14005ce46  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x14005ce4d  call    cs:__imp_FreeLibrary
0x14005ce54  nop     dword ptr [rax+rax+00h]
0x14005ce59  mov     eax, ebx
0x14005ce5b  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x14005ce66  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x14005ce71  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x14005ce7c  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x14005ce87  jmp     short loc_14005CEC1
0x14005ce89  xor     edx, edx; Val
0x14005ce8b  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x14005ce90  mov     r8d, 29Ch; Size
0x14005ce96  call    memset_0
0x14005ce9b  movups  xmm0, cs:SumGuid_PRINT
0x14005cea2  mov     rax, cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x14005cea9  lea     rcx, [rsp+2E8h+var_2C8]
0x14005ceae  mov     [rsp+2E8h+var_2C8], 2B0h
0x14005ceb6  movdqu  [rsp+2E8h+var_2C4], xmm0
0x14005cebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cec1  mov     rcx, [rsp+2E8h+var_18]
0x14005cec9  xor     rcx, rsp; StackCookie
0x14005cecc  call    __security_check_cookie
0x14005ced1  add     rsp, 2E0h
0x14005ced8  pop     rbx
0x14005ced9  retn
```
