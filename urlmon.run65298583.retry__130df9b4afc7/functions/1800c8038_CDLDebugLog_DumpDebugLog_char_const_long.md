# CDLDebugLog::DumpDebugLog(char const *,long)

- ea: `0x1800c8038`
- end: `0x1800c8361`
- name: `?DumpDebugLog@CDLDebugLog@@QEAAXPEBDJ@Z`
- size: `809`
- prototype: `void __fastcall(CDLDebugLog *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b4640`
- `0x1800be538`

## callees

- `0x180044b84`
- `0x1800c8038`
- `0x1800c8608`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800c80fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800c80fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c82ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c82ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c82e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c82e5`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c80c4`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c80c4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c80f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c81d4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c8221`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c827f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c82b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c82dc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c80f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c81d4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c8221`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c827f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c82b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c82dc`
- `WININET!CommitUrlCacheEntryA` at `0x1800c8329`
- `WININET!CommitUrlCacheEntryA` at `0x1800c8329`

## string_xrefs

- `0x1800c8255`: `Operation failed. Detailed Information:\n     CodeBase: %s\n     CLSID: %s\n     Extension: %s\n     Type: %s\n\n`

## pseudocode

```c
void __fastcall CDLDebugLog::DumpDebugLog(CHAR *this, const char *a2, int a3)
{
  const CHAR *v3; // r12
  HANDLE FileA; // rax
  void *v7; // r15
  const BYTE *v8; // rsi
  const char *v9; // rbx
  const char *v10; // r11
  const char *v11; // r9
  __int64 v12; // r8
  const char *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // esi
  int v17; // edi
  _QWORD *i; // rbx
  __int64 v19; // rax
  __int64 v20; // r8
  _BYTE *v21; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-69h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-59h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-19h] BYREF
  __int64 v25; // [rsp+78h] [rbp-11h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-9h] BYREF
  const char *v27; // [rsp+88h] [rbp-1h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp+7h] BYREF

  LODWORD(v25) = a3;
  v3 = this + 52;
  SystemTimeAsFileTime = 0;
  NumberOfBytesWritten = 0;
  SystemTime = 0;
  if ( !this[52] )
    CDLDebugLog::MakeFile((CDLDebugLog *)this);
  if ( *(_QWORD *)this )
  {
    if ( *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      FileA = CreateFileA(v3, 0xC0000000, 0, 0, 2u, 0x80u, 0);
      v7 = FileA;
      if ( FileA != (HANDLE)-1LL )
      {
        WriteFile(FileA, "<html><pre>\n", 0xCu, &NumberOfBytesWritten, 0);
        GetLocalTime(&SystemTime);
        v8 = &Default;
        v9 = (const char *)&Default;
        if ( SystemTime.wSecond <= 9u )
          v9 = "0";
        v10 = (const char *)&Default;
        v11 = (const char *)&Default;
        if ( SystemTime.wMinute <= 9u )
          v10 = "0";
        if ( SystemTime.wHour <= 9u )
          v11 = "0";
        v27 = "0";
        if ( SystemTime.wDay <= 9u )
          v8 = (const BYTE *)v27;
        LODWORD(hTemplateFile) = SystemTime.wYear;
        dwCreationDisposition[0] = SystemTime.wDay;
        StringCchPrintfA(
          qword_180164E70,
          0x800u,
          "*** Code Download Log entry (%s%d %s %d @ %s%d:%s%d:%s%d) ***\n",
          v8,
          *(_QWORD *)dwCreationDisposition,
          off_180124B00[SystemTime.wMonth - 1],
          hTemplateFile,
          v11,
          SystemTime.wHour,
          v10,
          SystemTime.wMinute,
          v9,
          SystemTime.wSecond);
        v12 = -1;
        do
          ++v12;
        while ( qword_180164E70[v12] );
        WriteFile(v7, qword_180164E70, v12, &NumberOfBytesWritten, 0);
        v13 = "(null)";
        if ( a2 )
          v13 = a2;
        StringCchPrintfA(qword_180164E70, 0x800u, "Code Download Error: (hr = %lx) %s\n", (unsigned int)v25, v13);
        v14 = -1;
        do
          ++v14;
        while ( qword_180164E70[v14] );
        WriteFile(v7, qword_180164E70, v14, &NumberOfBytesWritten, 0);
        StringCchPrintfA(
          qword_180164E70,
          0x800u,
          "Operation failed. Detailed Information:\n"
          "     CodeBase: %s\n"
          "     CLSID: %s\n"
          "     Extension: %s\n"
          "     Type: %s\n"
          "\n",
          this + 10364,
          this + 4220,
          this + 8316,
          this + 6268);
        v15 = -1;
        do
          ++v15;
        while ( qword_180164E70[v15] );
        WriteFile(v7, qword_180164E70, v15, &NumberOfBytesWritten, 0);
        v16 = *((_DWORD *)this + 4);
        v17 = 0;
        for ( i = *(_QWORD **)this; v17 < v16; ++v17 )
        {
          v19 = i[2];
          v20 = -1;
          i = (_QWORD *)*i;
          v21 = *(_BYTE **)(v19 + 8);
          do
            ++v20;
          while ( v21[v20] );
          WriteFile(v7, v21, v20, &NumberOfBytesWritten, 0);
        }
        WriteFile(v7, "\n</pre></html>", 0xEu, &NumberOfBytesWritten, 0);
        CloseHandle(v7);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v25 = 0;
        CommitUrlCacheEntryA(this + 2136, v3, 0, SystemTimeAsFileTime, 1u, 0, 0, 0, 0);
        *((_DWORD *)this + 12) = 0;
        this[2136] = 0;
        *v3 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800c8038  mov     [rsp-8+arg_18], rbx
0x1800c803d  push    rbp
0x1800c803e  push    rsi
0x1800c803f  push    rdi
0x1800c8040  push    r12
0x1800c8042  push    r13
0x1800c8044  push    r14
0x1800c8046  push    r15
0x1800c8048  lea     rbp, [rsp-27h]
0x1800c804d  sub     rsp, 0B0h
0x1800c8054  mov     rax, cs:__security_cookie
0x1800c805b  xor     rax, rsp
0x1800c805e  mov     [rbp+57h+var_40], rax
0x1800c8062  xor     ebx, ebx
0x1800c8064  mov     dword ptr [rbp+57h+var_68], r8d
0x1800c8068  lea     r12, [rcx+34h]
0x1800c806c  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800c8070  xorps   xmm0, xmm0
0x1800c8073  mov     r13, rdx
0x1800c8076  mov     r14, rcx
0x1800c8079  mov     [rbp+57h+NumberOfBytesWritten], ebx
0x1800c807c  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800c8080  cmp     [r12], bl
0x1800c8084  jnz     short loc_1800C808B
0x1800c8086  call    ?MakeFile@CDLDebugLog@@QEAAXXZ; CDLDebugLog::MakeFile(void)
0x1800c808b  mov     rax, [r14]
0x1800c808e  test    rax, rax
0x1800c8091  jz      loc_1800C833A
0x1800c8097  cmp     [rax+10h], rbx
0x1800c809b  jz      loc_1800C833A
0x1800c80a1  mov     [rsp+0E0h+hTemplateFile], rbx; hTemplateFile
0x1800c80a6  xor     r9d, r9d; lpSecurityAttributes
0x1800c80a9  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c80b1  xor     r8d, r8d; dwShareMode
0x1800c80b4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800c80b9  mov     [rsp+0E0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c80c1  mov     rcx, r12; lpFileName
0x1800c80c4  call    cs:__imp_CreateFileA
0x1800c80ca  mov     r15, rax
0x1800c80cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c80d1  jz      loc_1800C833A
0x1800c80d7  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c80db  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rbx; lpOverlapped
0x1800c80e0  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x1800c80e6  lea     rdx, aHtmlPre; "<html><pre>\n"
0x1800c80ed  mov     rcx, rax; hFile
0x1800c80f0  call    cs:__imp_WriteFile
0x1800c80f6  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800c80fa  call    cs:__imp_GetLocalTime
0x1800c8100  cmp     [rbp+57h+SystemTime.wSecond], 9
0x1800c8105  lea     rax, a0; "0"
0x1800c810c  movzx   r8d, [rbp+57h+SystemTime.wHour]
0x1800c8111  lea     rsi, Default
0x1800c8118  movzx   edx, [rbp+57h+SystemTime.wYear]
0x1800c811c  lea     rcx, off_180124B00; "Jan"
0x1800c8123  movzx   edi, [rbp+57h+SystemTime.wSecond]
0x1800c8127  mov     rbx, rsi
0x1800c812a  movzx   r10d, [rbp+57h+SystemTime.wMinute]
0x1800c812f  cmovbe  rbx, rax
0x1800c8133  cmp     [rbp+57h+SystemTime.wMinute], 9
0x1800c8138  mov     r11, rsi
0x1800c813b  mov     [rsp+0E0h+var_80], edi
0x1800c813f  mov     r9, rsi
0x1800c8142  mov     [rsp+0E0h+var_88], rbx
0x1800c8147  cmovbe  r11, rax
0x1800c814b  cmp     [rbp+57h+SystemTime.wHour], 9
0x1800c8150  lea     rbx, qword_180164E70
0x1800c8157  mov     [rsp+0E0h+var_90], r10d
0x1800c815c  cmovbe  r9, rax
0x1800c8160  mov     [rsp+0E0h+var_98], r11
0x1800c8165  cmp     [rbp+57h+SystemTime.wDay], 9
0x1800c816a  mov     dword ptr [rsp+0E0h+lpszOriginalUrl], r8d
0x1800c816f  lea     r8, aCodeDownloadLo; "*** Code Download Log entry (%s%d %s %d"...
0x1800c8176  mov     [rsp+0E0h+lpszFileExtension], r9
0x1800c817b  mov     [rbp+57h+var_58], rax
0x1800c817f  movzx   eax, [rbp+57h+SystemTime.wMonth]
0x1800c8183  cmovbe  rsi, [rbp+57h+var_58]
0x1800c8188  mov     dword ptr [rsp+0E0h+hTemplateFile], edx
0x1800c818c  mov     r9, rsi
0x1800c818f  mov     esi, 800h
0x1800c8194  mov     rcx, [rcx+rax*8-8]
0x1800c8199  mov     edx, esi; unsigned __int64
0x1800c819b  movzx   eax, [rbp+57h+SystemTime.wDay]
0x1800c819f  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x1800c81a4  mov     rcx, rbx; char *
0x1800c81a7  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1800c81ab  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800c81b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c81b4  mov     r8, rdi
0x1800c81b7  inc     r8; nNumberOfBytesToWrite
0x1800c81ba  cmp     byte ptr [rbx+r8], 0
0x1800c81bf  jnz     short loc_1800C81B7
0x1800c81c1  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c81c5  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1800c81ce  mov     rdx, rbx; lpBuffer
0x1800c81d1  mov     rcx, r15; hFile
0x1800c81d4  call    cs:__imp_WriteFile
0x1800c81da  mov     r9d, dword ptr [rbp+57h+var_68]
0x1800c81de  lea     rax, aNull_0; "(null)"
0x1800c81e5  test    r13, r13
0x1800c81e8  lea     r8, aCodeDownloadEr; "Code Download Error: (hr = %lx) %s\n"
0x1800c81ef  mov     rdx, rsi; unsigned __int64
0x1800c81f2  mov     rcx, rbx; char *
0x1800c81f5  cmovnz  rax, r13
0x1800c81f9  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x1800c81fe  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800c8203  mov     r8, rdi
0x1800c8206  xor     r13d, r13d
0x1800c8209  inc     r8; nNumberOfBytesToWrite
0x1800c820c  cmp     [rbx+r8], r13b
0x1800c8210  jnz     short loc_1800C8209
0x1800c8212  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c8216  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800c821b  mov     rdx, rbx; lpBuffer
0x1800c821e  mov     rcx, r15; hFile
0x1800c8221  call    cs:__imp_WriteFile
0x1800c8227  lea     rax, [r14+187Ch]
0x1800c822e  mov     rdx, rsi; unsigned __int64
0x1800c8231  mov     [rsp+0E0h+hTemplateFile], rax
0x1800c8236  lea     rcx, [r14+207Ch]
0x1800c823d  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x1800c8242  lea     r8, [r14+107Ch]
0x1800c8249  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r8
0x1800c824e  lea     r9, [r14+287Ch]
0x1800c8255  lea     r8, aOperationFaile; "Operation failed. Detailed Information:"...
0x1800c825c  mov     rcx, rbx; char *
0x1800c825f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800c8264  mov     r8, rdi
0x1800c8267  inc     r8; nNumberOfBytesToWrite
0x1800c826a  cmp     [rbx+r8], r13b
0x1800c826e  jnz     short loc_1800C8267
0x1800c8270  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c8274  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800c8279  mov     rdx, rbx; lpBuffer
0x1800c827c  mov     rcx, r15; hFile
0x1800c827f  call    cs:__imp_WriteFile
0x1800c8285  mov     esi, [r14+10h]
0x1800c8289  mov     edi, r13d
0x1800c828c  mov     rbx, [r14]
0x1800c828f  test    esi, esi
0x1800c8291  jle     short loc_1800C82C3
0x1800c8293  mov     rax, [rbx+10h]
0x1800c8297  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c829b  mov     rbx, [rbx]
0x1800c829e  mov     rdx, [rax+8]; lpBuffer
0x1800c82a2  inc     r8; nNumberOfBytesToWrite
0x1800c82a5  cmp     [rdx+r8], r13b
0x1800c82a9  jnz     short loc_1800C82A2
0x1800c82ab  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c82af  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800c82b4  mov     rcx, r15; hFile
0x1800c82b7  call    cs:__imp_WriteFile
0x1800c82bd  inc     edi
0x1800c82bf  cmp     edi, esi
0x1800c82c1  jl      short loc_1800C8293
0x1800c82c3  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c82c7  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800c82cc  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x1800c82d2  lea     rdx, aPreHtml; "\n</pre></html>"
0x1800c82d9  mov     rcx, r15; hFile
0x1800c82dc  call    cs:__imp_WriteFile
0x1800c82e2  mov     rcx, r15; hObject
0x1800c82e5  call    cs:__imp_CloseHandle
0x1800c82eb  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800c82ef  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c82f5  mov     r9, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]; LastModifiedTime
0x1800c82f9  lea     rbx, [r14+858h]
0x1800c8300  mov     [rsp+0E0h+lpszOriginalUrl], r13; lpszOriginalUrl
0x1800c8305  mov     r8, r13; ExpireTime
0x1800c8308  mov     [rsp+0E0h+lpszFileExtension], r13; lpszFileExtension
0x1800c830d  mov     rdx, r12; lpszLocalFileName
0x1800c8310  mov     dword ptr [rsp+0E0h+hTemplateFile], r13d; cchHeaderInfo
0x1800c8315  mov     rcx, rbx; lpszUrlName
0x1800c8318  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r13; lpHeaderInfo
0x1800c831d  mov     [rsp+0E0h+dwCreationDisposition], 1; CacheEntryType
0x1800c8325  mov     [rbp+57h+var_68], r13
0x1800c8329  call    cs:__imp_CommitUrlCacheEntryA
0x1800c832f  mov     [r14+30h], r13d
0x1800c8333  mov     [rbx], r13b
0x1800c8336  mov     [r12], r13b
0x1800c833a  mov     rcx, [rbp+57h+var_40]
0x1800c833e  xor     rcx, rsp; StackCookie
0x1800c8341  call    __security_check_cookie
0x1800c8346  mov     rbx, [rsp+0E0h+arg_18]
0x1800c834e  add     rsp, 0B0h
0x1800c8355  pop     r15
0x1800c8357  pop     r14
0x1800c8359  pop     r13
0x1800c835b  pop     r12
0x1800c835d  pop     rdi
0x1800c835e  pop     rsi
0x1800c835f  pop     rbp
0x1800c8360  retn
```
