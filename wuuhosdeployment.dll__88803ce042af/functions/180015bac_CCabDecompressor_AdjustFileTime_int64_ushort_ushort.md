# CCabDecompressor::AdjustFileTime(__int64,ushort,ushort)

- ea: `0x180015bac`
- end: `0x180015c92`
- name: `?AdjustFileTime@CCabDecompressor@@CAH_JGG@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015ca0`

## callees

- `0x18000956c`
- `0x180015bac`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c37`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180015bfc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180015bfc`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180015c10`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180015c10`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180015c2d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180015c2d`

## string_xrefs

- `0x180015c57`: `AdjustFileTime - SetFileTime`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::AdjustFileTime(__int64 a1, WORD a2, WORD a3)
{
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
    GetLastError();
    WUTrace(0, 0, 32, 3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180015bac  push    rbx
0x180015bae  sub     rsp, 50h
0x180015bb2  mov     rax, cs:__security_cookie
0x180015bb9  xor     rax, rsp
0x180015bbc  mov     [rsp+58h+var_18], rax
0x180015bc1  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x180015bca  movzx   r9d, r8w
0x180015bce  mov     qword ptr [rsp+58h+CreationTime.dwLowDateTime], 0
0x180015bd7  movzx   eax, dx
0x180015bda  mov     rbx, rcx
0x180015bdd  test    rcx, rcx
0x180015be0  jz      loc_180015C76
0x180015be6  cmp     dword ptr [rcx+10h], 1
0x180015bea  jnz     loc_180015C76
0x180015bf0  lea     r8, [rsp+58h+FileTime]; lpFileTime
0x180015bf5  movzx   edx, r9w; wFatTime
0x180015bf9  movzx   ecx, ax; wFatDate
0x180015bfc  call    cs:__imp_DosDateTimeToFileTime
0x180015c02  test    eax, eax
0x180015c04  jz      short loc_180015C76
0x180015c06  lea     rdx, [rsp+58h+CreationTime]; lpFileTime
0x180015c0b  lea     rcx, [rsp+58h+FileTime]; lpLocalFileTime
0x180015c10  call    cs:__imp_LocalFileTimeToFileTime
0x180015c16  test    eax, eax
0x180015c18  jz      short loc_180015C76
0x180015c1a  mov     rcx, [rbx+8]; hFile
0x180015c1e  lea     r9, [rsp+58h+CreationTime]; lpLastWriteTime
0x180015c23  lea     r8, [rsp+58h+CreationTime]; lpLastAccessTime
0x180015c28  lea     rdx, [rsp+58h+CreationTime]; lpCreationTime
0x180015c2d  call    cs:__imp_SetFileTime
0x180015c33  test    eax, eax
0x180015c35  jnz     short loc_180015C8B
0x180015c37  call    cs:__imp_GetLastError
0x180015c3d  movzx   ecx, ax
0x180015c40  or      ecx, 80070000h
0x180015c46  test    eax, eax
0x180015c48  cmovle  ecx, eax
0x180015c4b  mov     eax, 8000FFFFh
0x180015c50  test    ecx, ecx
0x180015c52  cmovns  ecx, eax
0x180015c55  xor     edx, edx
0x180015c57  lea     rax, aAdjustfiletime; "AdjustFileTime - SetFileTime"
0x180015c5e  mov     [rsp+58h+var_30], rax
0x180015c63  mov     [rsp+58h+var_38], ecx
0x180015c67  xor     ecx, ecx
0x180015c69  lea     r9d, [rdx+3]
0x180015c6d  lea     r8d, [rdx+20h]
0x180015c71  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180015c76  xor     eax, eax
0x180015c78  mov     rcx, [rsp+58h+var_18]
0x180015c7d  xor     rcx, rsp; StackCookie
0x180015c80  call    __security_check_cookie
0x180015c85  add     rsp, 50h
0x180015c89  pop     rbx
0x180015c8a  retn
0x180015c8b  mov     eax, 1
0x180015c90  jmp     short loc_180015C78
```
