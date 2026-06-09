# CCabDecompressor::AdjustFileTime(__int64,ushort,ushort)

- ea: `0x1800989ac`
- end: `0x180098a92`
- name: `?AdjustFileTime@CCabDecompressor@@CAH_JGG@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180098aa0`

## callees

- `0x180090bc8`
- `0x1800989ac`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a37`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180098a2d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180098a2d`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180098a10`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180098a10`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800989fc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800989fc`

## string_xrefs

- `0x180098a57`: `AdjustFileTime - SetFileTime`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::AdjustFileTime(__int64 a1, WORD a2, WORD a3)
{
  signed int LastError; // eax
  signed int v5; // ecx
  __int64 v7; // [rsp+20h] [rbp-38h]
  FILETIME CreationTime; // [rsp+30h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-20h] BYREF

  FileTime = 0;
  CreationTime = 0;
  if ( !a1
    || *(_DWORD *)(a1 + 16) != 1
    || !DosDateTimeToFileTime(a2, a3, &FileTime)
    || !LocalFileTimeToFileTime(&FileTime, &CreationTime) )
  {
    return 0;
  }
  if ( !SetFileTime(*(HANDLE *)(a1 + 8), &CreationTime, &CreationTime, &CreationTime) )
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
    if ( v5 >= 0 )
      v5 = -2147418113;
    LODWORD(v7) = v5;
    WUTrace(0, 0, 32, 3, v7, L"AdjustFileTime - SetFileTime", CreationTime, FileTime);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800989ac  push    rbx
0x1800989ae  sub     rsp, 50h
0x1800989b2  mov     rax, cs:__security_cookie
0x1800989b9  xor     rax, rsp
0x1800989bc  mov     [rsp+58h+var_18], rax
0x1800989c1  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x1800989ca  movzx   r9d, r8w
0x1800989ce  mov     qword ptr [rsp+58h+CreationTime.dwLowDateTime], 0
0x1800989d7  movzx   eax, dx
0x1800989da  mov     rbx, rcx
0x1800989dd  test    rcx, rcx
0x1800989e0  jz      loc_180098A76
0x1800989e6  cmp     dword ptr [rcx+10h], 1
0x1800989ea  jnz     loc_180098A76
0x1800989f0  lea     r8, [rsp+58h+FileTime]; lpFileTime
0x1800989f5  movzx   edx, r9w; wFatTime
0x1800989f9  movzx   ecx, ax; wFatDate
0x1800989fc  call    cs:__imp_DosDateTimeToFileTime
0x180098a02  test    eax, eax
0x180098a04  jz      short loc_180098A76
0x180098a06  lea     rdx, [rsp+58h+CreationTime]; lpFileTime
0x180098a0b  lea     rcx, [rsp+58h+FileTime]; lpLocalFileTime
0x180098a10  call    cs:__imp_LocalFileTimeToFileTime
0x180098a16  test    eax, eax
0x180098a18  jz      short loc_180098A76
0x180098a1a  mov     rcx, [rbx+8]; hFile
0x180098a1e  lea     r9, [rsp+58h+CreationTime]; lpLastWriteTime
0x180098a23  lea     r8, [rsp+58h+CreationTime]; lpLastAccessTime
0x180098a28  lea     rdx, [rsp+58h+CreationTime]; lpCreationTime
0x180098a2d  call    cs:__imp_SetFileTime
0x180098a33  test    eax, eax
0x180098a35  jnz     short loc_180098A8B
0x180098a37  call    cs:__imp_GetLastError
0x180098a3d  movzx   ecx, ax
0x180098a40  or      ecx, 80070000h
0x180098a46  test    eax, eax
0x180098a48  cmovle  ecx, eax
0x180098a4b  mov     eax, 8000FFFFh
0x180098a50  test    ecx, ecx
0x180098a52  cmovns  ecx, eax
0x180098a55  xor     edx, edx
0x180098a57  lea     rax, aAdjustfiletime; "AdjustFileTime - SetFileTime"
0x180098a5e  mov     [rsp+58h+var_30], rax
0x180098a63  mov     dword ptr [rsp+58h+var_38], ecx
0x180098a67  xor     ecx, ecx
0x180098a69  lea     r9d, [rdx+3]
0x180098a6d  lea     r8d, [rdx+20h]
0x180098a71  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180098a76  xor     eax, eax
0x180098a78  mov     rcx, [rsp+58h+var_18]
0x180098a7d  xor     rcx, rsp; StackCookie
0x180098a80  call    __security_check_cookie
0x180098a85  add     rsp, 50h
0x180098a89  pop     rbx
0x180098a8a  retn
0x180098a8b  mov     eax, 1
0x180098a90  jmp     short loc_180098A78
```
