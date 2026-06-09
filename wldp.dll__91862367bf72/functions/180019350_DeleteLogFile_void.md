# DeleteLogFile(void)

- ea: `0x180019350`
- end: `0x180019423`
- name: `?DeleteLogFile@@YAJXZ`
- size: `211`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001d220`
- `0x18002af60`

## callees

- `0x180019350`
- `0x18001942c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019391`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019405`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800193ce`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800193ce`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001937d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800193a8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001937d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800193a8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001935b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001935b`

## string_xrefs

- `0x180019363`: `%SystemRoot%\System32\CodeIntegrity\Data\Non-Production Errors.txt`

## pseudocode

```c
__int64 DeleteLogFile(void)
{
  WCHAR *v0; // rsi
  const WCHAR *v1; // rbp
  DWORD v2; // eax
  DWORD v3; // ebx
  WCHAR *v4; // rax
  WCHAR *v5; // rdi
  signed int v6; // ebx
  signed int LastError; // eax
  signed int v9; // eax

  v0 = 0;
  v1 = L"%SystemDrive%\\data\\systemdata\\etw\\Non-Production Errors.txt";
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
    v1 = L"%SystemRoot%\\System32\\CodeIntegrity\\Data\\Non-Production Errors.txt";
  v2 = ExpandEnvironmentStringsW(v1, 0, 0);
  v3 = v2;
  if ( v2 )
  {
    v4 = (WCHAR *)LocalAlloc(0x40u, 2LL * v2);
    v5 = v4;
    if ( !v4 )
    {
      v6 = -2147024882;
      goto LABEL_7;
    }
    if ( ExpandEnvironmentStringsW(v1, v4, v3) )
    {
      v6 = 0;
      v0 = v5;
      v5 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    v5 = 0;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
  LocalFree(v5);
  if ( v6 >= 0 )
  {
    CloseLogFile();
    if ( !DeleteFileW(v0) )
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
    }
  }
  LocalFree(v0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019350  push    rbx
0x180019352  push    rbp
0x180019353  push    rsi
0x180019354  push    rdi
0x180019355  sub     rsp, 28h
0x180019359  xor     esi, esi
0x18001935b  call    cs:__imp_RtlIsStateSeparationEnabled
0x180019361  test    al, al
0x180019363  lea     rcx, Src; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18001936a  lea     rbp, aSystemdriveDat; "%SystemDrive%\\data\\systemdata\\etw\\N"...
0x180019371  cmovz   rbp, rcx
0x180019375  xor     r8d, r8d; nSize
0x180019378  mov     rcx, rbp; lpSrc
0x18001937b  xor     edx, edx; lpDst
0x18001937d  call    cs:__imp_ExpandEnvironmentStringsW
0x180019383  mov     ebx, eax
0x180019385  test    eax, eax
0x180019387  jz      short loc_1800193EC
0x180019389  mov     edx, ebx
0x18001938b  lea     ecx, [rsi+40h]; uFlags
0x18001938e  add     rdx, rdx; uBytes
0x180019391  call    cs:__imp_LocalAlloc
0x180019397  mov     rdi, rax
0x18001939a  test    rax, rax
0x18001939d  jz      short loc_18001941C
0x18001939f  mov     r8d, ebx; nSize
0x1800193a2  mov     rdx, rax; lpDst
0x1800193a5  mov     rcx, rbp; lpSrc
0x1800193a8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800193ae  test    eax, eax
0x1800193b0  jz      short loc_1800193EE
0x1800193b2  xor     ebx, ebx
0x1800193b4  mov     rsi, rdi
0x1800193b7  xor     edi, edi
0x1800193b9  mov     rcx, rdi; hMem
0x1800193bc  call    cs:__imp_LocalFree
0x1800193c2  test    ebx, ebx
0x1800193c4  js      short loc_1800193D8
0x1800193c6  call    ?CloseLogFile@@YAXXZ; CloseLogFile(void)
0x1800193cb  mov     rcx, rsi; lpFileName
0x1800193ce  call    cs:__imp_DeleteFileW
0x1800193d4  test    eax, eax
0x1800193d6  jz      short loc_180019405
0x1800193d8  mov     rcx, rsi; hMem
0x1800193db  call    cs:__imp_LocalFree
0x1800193e1  mov     eax, ebx
0x1800193e3  add     rsp, 28h
0x1800193e7  pop     rdi
0x1800193e8  pop     rsi
0x1800193e9  pop     rbp
0x1800193ea  pop     rbx
0x1800193eb  retn
0x1800193ec  xor     edi, edi
0x1800193ee  call    cs:__imp_GetLastError
0x1800193f4  mov     ebx, eax
0x1800193f6  test    eax, eax
0x1800193f8  jle     short loc_1800193B9
0x1800193fa  movzx   ebx, ax
0x1800193fd  or      ebx, 80070000h
0x180019403  jmp     short loc_1800193B9
0x180019405  call    cs:__imp_GetLastError
0x18001940b  mov     ebx, eax
0x18001940d  test    eax, eax
0x18001940f  jle     short loc_1800193D8
0x180019411  movzx   ebx, ax
0x180019414  or      ebx, 80070000h
0x18001941a  jmp     short loc_1800193D8
0x18001941c  mov     ebx, 8007000Eh
0x180019421  jmp     short loc_1800193B9
```
