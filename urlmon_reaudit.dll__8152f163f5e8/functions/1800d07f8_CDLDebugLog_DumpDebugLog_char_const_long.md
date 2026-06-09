# CDLDebugLog::DumpDebugLog(char const *,long)

- ea: `0x1800d07f8`
- end: `0x1800d0b64`
- name: `?DumpDebugLog@CDLDebugLog@@QEAAXPEBDJ@Z`
- size: `876`
- prototype: `void __fastcall(CDLDebugLog *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bc0d0`
- `0x1800c673c`

## callees

- `0x18005789c`
- `0x1800d07f8`
- `0x1800d0e40`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800d08c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800d08c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d0ae5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d0ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0ad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0ad5`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800d0884`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800d0884`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d08b6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d09a6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d09f9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d0a5d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d0a9b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d0ac6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d08b6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d09a6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d09f9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d0a5d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d0a9b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d0ac6`
- `WININET!CommitUrlCacheEntryA` at `0x1800d0b25`
- `WININET!CommitUrlCacheEntryA` at `0x1800d0b25`

## string_xrefs

- `0x1800d0a33`: `Operation failed. Detailed Information:\n     CodeBase: %s\n     CLSID: %s\n     Extension: %s\n     Type: %s\n\n`

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
          byte_180171E40,
          0x800u,
          "*** Code Download Log entry (%s%d %s %d @ %s%d:%s%d:%s%d) ***\n",
          v8,
          *(_QWORD *)dwCreationDisposition,
          off_180131B00[SystemTime.wMonth - 1],
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
        while ( byte_180171E40[v12] );
        WriteFile(v7, byte_180171E40, v12, &NumberOfBytesWritten, 0);
        v13 = "(null)";
        if ( a2 )
          v13 = a2;
        StringCchPrintfA(byte_180171E40, 0x800u, "Code Download Error: (hr = %lx) %s\n", (unsigned int)v25, v13);
        v14 = -1;
        do
          ++v14;
        while ( byte_180171E40[v14] );
        WriteFile(v7, byte_180171E40, v14, &NumberOfBytesWritten, 0);
        StringCchPrintfA(
          byte_180171E40,
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
        while ( byte_180171E40[v15] );
        WriteFile(v7, byte_180171E40, v15, &NumberOfBytesWritten, 0);
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
0x1800d07f8  mov     [rsp-8+arg_18], rbx
0x1800d07fd  push    rbp
0x1800d07fe  push    rsi
0x1800d07ff  push    rdi
0x1800d0800  push    r12
0x1800d0802  push    r13
0x1800d0804  push    r14
0x1800d0806  push    r15
0x1800d0808  lea     rbp, [rsp-27h]
0x1800d080d  sub     rsp, 0B0h
0x1800d0814  mov     rax, cs:__security_cookie
0x1800d081b  xor     rax, rsp
0x1800d081e  mov     [rbp+57h+var_40], rax
0x1800d0822  xor     ebx, ebx
0x1800d0824  mov     dword ptr [rbp+57h+var_68], r8d
0x1800d0828  lea     r12, [rcx+34h]
0x1800d082c  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800d0830  xorps   xmm0, xmm0
0x1800d0833  mov     r13, rdx
0x1800d0836  mov     r14, rcx
0x1800d0839  mov     [rbp+57h+NumberOfBytesWritten], ebx
0x1800d083c  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800d0840  cmp     [r12], bl
0x1800d0844  jnz     short loc_1800D084B
0x1800d0846  call    ?MakeFile@CDLDebugLog@@QEAAXXZ; CDLDebugLog::MakeFile(void)
0x1800d084b  mov     rax, [r14]
0x1800d084e  test    rax, rax
0x1800d0851  jz      loc_1800D0B3C
0x1800d0857  cmp     [rax+10h], rbx
0x1800d085b  jz      loc_1800D0B3C
0x1800d0861  mov     [rsp+0E0h+hTemplateFile], rbx; hTemplateFile
0x1800d0866  xor     r9d, r9d; lpSecurityAttributes
0x1800d0869  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d0871  xor     r8d, r8d; dwShareMode
0x1800d0874  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d0879  mov     [rsp+0E0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d0881  mov     rcx, r12; lpFileName
0x1800d0884  call    cs:__imp_CreateFileA
0x1800d088b  nop     dword ptr [rax+rax+00h]
0x1800d0890  mov     r15, rax
0x1800d0893  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d0897  jz      loc_1800D0B3C
0x1800d089d  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d08a1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rbx; lpOverlapped
0x1800d08a6  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x1800d08ac  lea     rdx, aHtmlPre; "<html><pre>\n"
0x1800d08b3  mov     rcx, rax; hFile
0x1800d08b6  call    cs:__imp_WriteFile
0x1800d08bd  nop     dword ptr [rax+rax+00h]
0x1800d08c2  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800d08c6  call    cs:__imp_GetLocalTime
0x1800d08cd  nop     dword ptr [rax+rax+00h]
0x1800d08d2  cmp     [rbp+57h+SystemTime.wSecond], 9
0x1800d08d7  lea     rax, a0; "0"
0x1800d08de  movzx   r8d, [rbp+57h+SystemTime.wHour]
0x1800d08e3  lea     rsi, Default
0x1800d08ea  movzx   edx, [rbp+57h+SystemTime.wYear]
0x1800d08ee  lea     rcx, off_180131B00; "Jan"
0x1800d08f5  movzx   edi, [rbp+57h+SystemTime.wSecond]
0x1800d08f9  mov     rbx, rsi
0x1800d08fc  movzx   r10d, [rbp+57h+SystemTime.wMinute]
0x1800d0901  cmovbe  rbx, rax
0x1800d0905  cmp     [rbp+57h+SystemTime.wMinute], 9
0x1800d090a  mov     r11, rsi
0x1800d090d  mov     [rsp+0E0h+var_80], edi
0x1800d0911  mov     r9, rsi
0x1800d0914  mov     [rsp+0E0h+var_88], rbx
0x1800d0919  cmovbe  r11, rax
0x1800d091d  cmp     [rbp+57h+SystemTime.wHour], 9
0x1800d0922  lea     rbx, byte_180171E40
0x1800d0929  mov     [rsp+0E0h+var_90], r10d
0x1800d092e  cmovbe  r9, rax
0x1800d0932  mov     [rsp+0E0h+var_98], r11
0x1800d0937  cmp     [rbp+57h+SystemTime.wDay], 9
0x1800d093c  mov     dword ptr [rsp+0E0h+lpszOriginalUrl], r8d
0x1800d0941  lea     r8, aCodeDownloadLo; "*** Code Download Log entry (%s%d %s %d"...
0x1800d0948  mov     [rsp+0E0h+lpszFileExtension], r9
0x1800d094d  mov     [rbp+57h+var_58], rax
0x1800d0951  movzx   eax, [rbp+57h+SystemTime.wMonth]
0x1800d0955  cmovbe  rsi, [rbp+57h+var_58]
0x1800d095a  mov     dword ptr [rsp+0E0h+hTemplateFile], edx
0x1800d095e  mov     r9, rsi
0x1800d0961  mov     esi, 800h
0x1800d0966  mov     rcx, [rcx+rax*8-8]
0x1800d096b  mov     edx, esi; unsigned __int64
0x1800d096d  movzx   eax, [rbp+57h+SystemTime.wDay]
0x1800d0971  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x1800d0976  mov     rcx, rbx; char *
0x1800d0979  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1800d097d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800d0982  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d0986  mov     r8, rdi
0x1800d0989  inc     r8; nNumberOfBytesToWrite
0x1800d098c  cmp     byte ptr [rbx+r8], 0
0x1800d0991  jnz     short loc_1800D0989
0x1800d0993  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d0997  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1800d09a0  mov     rdx, rbx; lpBuffer
0x1800d09a3  mov     rcx, r15; hFile
0x1800d09a6  call    cs:__imp_WriteFile
0x1800d09ad  nop     dword ptr [rax+rax+00h]
0x1800d09b2  mov     r9d, dword ptr [rbp+57h+var_68]
0x1800d09b6  lea     rax, aNull_0; "(null)"
0x1800d09bd  test    r13, r13
0x1800d09c0  lea     r8, aCodeDownloadEr; "Code Download Error: (hr = %lx) %s\n"
0x1800d09c7  mov     rdx, rsi; unsigned __int64
0x1800d09ca  mov     rcx, rbx; char *
0x1800d09cd  cmovnz  rax, r13
0x1800d09d1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x1800d09d6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800d09db  mov     r8, rdi
0x1800d09de  xor     r13d, r13d
0x1800d09e1  inc     r8; nNumberOfBytesToWrite
0x1800d09e4  cmp     [rbx+r8], r13b
0x1800d09e8  jnz     short loc_1800D09E1
0x1800d09ea  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d09ee  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800d09f3  mov     rdx, rbx; lpBuffer
0x1800d09f6  mov     rcx, r15; hFile
0x1800d09f9  call    cs:__imp_WriteFile
0x1800d0a00  nop     dword ptr [rax+rax+00h]
0x1800d0a05  lea     rax, [r14+187Ch]
0x1800d0a0c  mov     rdx, rsi; unsigned __int64
0x1800d0a0f  mov     [rsp+0E0h+hTemplateFile], rax
0x1800d0a14  lea     rcx, [r14+207Ch]
0x1800d0a1b  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x1800d0a20  lea     r8, [r14+107Ch]
0x1800d0a27  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r8
0x1800d0a2c  lea     r9, [r14+287Ch]
0x1800d0a33  lea     r8, aOperationFaile; "Operation failed. Detailed Information:"...
0x1800d0a3a  mov     rcx, rbx; char *
0x1800d0a3d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800d0a42  mov     r8, rdi
0x1800d0a45  inc     r8; nNumberOfBytesToWrite
0x1800d0a48  cmp     [rbx+r8], r13b
0x1800d0a4c  jnz     short loc_1800D0A45
0x1800d0a4e  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d0a52  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800d0a57  mov     rdx, rbx; lpBuffer
0x1800d0a5a  mov     rcx, r15; hFile
0x1800d0a5d  call    cs:__imp_WriteFile
0x1800d0a64  nop     dword ptr [rax+rax+00h]
0x1800d0a69  mov     esi, [r14+10h]
0x1800d0a6d  mov     edi, r13d
0x1800d0a70  mov     rbx, [r14]
0x1800d0a73  test    esi, esi
0x1800d0a75  jle     short loc_1800D0AAD
0x1800d0a77  mov     rax, [rbx+10h]
0x1800d0a7b  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d0a7f  mov     rbx, [rbx]
0x1800d0a82  mov     rdx, [rax+8]; lpBuffer
0x1800d0a86  inc     r8; nNumberOfBytesToWrite
0x1800d0a89  cmp     [rdx+r8], r13b
0x1800d0a8d  jnz     short loc_1800D0A86
0x1800d0a8f  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d0a93  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800d0a98  mov     rcx, r15; hFile
0x1800d0a9b  call    cs:__imp_WriteFile
0x1800d0aa2  nop     dword ptr [rax+rax+00h]
0x1800d0aa7  inc     edi
0x1800d0aa9  cmp     edi, esi
0x1800d0aab  jl      short loc_1800D0A77
0x1800d0aad  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d0ab1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x1800d0ab6  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x1800d0abc  lea     rdx, aPreHtml; "\n</pre></html>"
0x1800d0ac3  mov     rcx, r15; hFile
0x1800d0ac6  call    cs:__imp_WriteFile
0x1800d0acd  nop     dword ptr [rax+rax+00h]
0x1800d0ad2  mov     rcx, r15; hObject
0x1800d0ad5  call    cs:__imp_CloseHandle
0x1800d0adc  nop     dword ptr [rax+rax+00h]
0x1800d0ae1  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800d0ae5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d0aec  nop     dword ptr [rax+rax+00h]
0x1800d0af1  mov     r9, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]; LastModifiedTime
0x1800d0af5  lea     rbx, [r14+858h]
0x1800d0afc  mov     [rsp+0E0h+lpszOriginalUrl], r13; lpszOriginalUrl
0x1800d0b01  mov     r8, r13; ExpireTime
0x1800d0b04  mov     [rsp+0E0h+lpszFileExtension], r13; lpszFileExtension
0x1800d0b09  mov     rdx, r12; lpszLocalFileName
0x1800d0b0c  mov     dword ptr [rsp+0E0h+hTemplateFile], r13d; cchHeaderInfo
0x1800d0b11  mov     rcx, rbx; lpszUrlName
0x1800d0b14  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r13; lpHeaderInfo
0x1800d0b19  mov     [rsp+0E0h+dwCreationDisposition], 1; CacheEntryType
0x1800d0b21  mov     [rbp+57h+var_68], r13
0x1800d0b25  call    cs:__imp_CommitUrlCacheEntryA
0x1800d0b2c  nop     dword ptr [rax+rax+00h]
0x1800d0b31  mov     [r14+30h], r13d
0x1800d0b35  mov     [rbx], r13b
0x1800d0b38  mov     [r12], r13b
0x1800d0b3c  mov     rcx, [rbp+57h+var_40]
0x1800d0b40  xor     rcx, rsp; StackCookie
0x1800d0b43  call    __security_check_cookie
0x1800d0b48  mov     rbx, [rsp+0E0h+arg_18]
0x1800d0b50  add     rsp, 0B0h
0x1800d0b57  pop     r15
0x1800d0b59  pop     r14
0x1800d0b5b  pop     r13
0x1800d0b5d  pop     r12
0x1800d0b5f  pop     rdi
0x1800d0b60  pop     rsi
0x1800d0b61  pop     rbp
0x1800d0b62  retn
```
