# ReadHttpCacheEntryFile(_HTTP_CACHE_ENTRY *)

- ea: `0x18008bc18`
- end: `0x18008be5b`
- name: `?ReadHttpCacheEntryFile@@YAJPEAU_HTTP_CACHE_ENTRY@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(struct _HTTP_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18008bad4`

## callees

- `0x18000bfd0`
- `0x18007a8fc`
- `0x18008bc18`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bcd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bcd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bdd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008be2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008be2d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bcb5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bcb5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008bccf`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008bccf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008bd6b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008bd6b`

## pseudocode

```c
__int64 __fastcall ReadHttpCacheEntryFile(struct _HTTP_CACHE_ENTRY *a1)
{
  signed int v2; // r14d
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  __int64 v5; // rsi
  signed int LastError; // eax
  DWORD LowPart; // edi
  LPVOID v8; // rbx
  signed int v9; // eax
  signed int v10; // eax
  LPVOID lpBuffer; // [rsp+48h] [rbp-28h]
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-20h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-18h] BYREF

  lpBuffer = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  v3 = (const WCHAR *)*((_QWORD *)a1 + 7);
  if ( !v3 || !*v3 )
  {
    v5 = -1;
    v2 = -2147024809;
    goto LABEL_34;
  }
  if ( *((_QWORD *)a1 + 8) )
    return 0;
  FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v5 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 >= 0 )
        v2 = -2147418113;
      goto LABEL_35;
    }
    LowPart = FileSize.LowPart;
    if ( FileSize.QuadPart >= 0x4000000 )
    {
      v2 = -2147024883;
      goto LABEL_35;
    }
    if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
    {
      v2 = -2147024362;
      goto LABEL_35;
    }
    v8 = lpBuffer;
    v2 = WxAlloc<unsigned short,WxCoTaskAllocator>(FileSize.LowPart + 2);
    if ( v2 >= 0 )
    {
      if ( ReadFile((HANDLE)v5, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead == LowPart )
        {
          v2 = 0;
          *((_WORD *)lpBuffer + ((unsigned __int64)LowPart >> 1)) = 0;
          *((_QWORD *)a1 + 8) = v8;
          goto LABEL_35;
        }
        v2 = -2147418113;
      }
      else
      {
        v9 = GetLastError();
        v2 = v9;
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        if ( v2 >= 0 )
          v2 = -2147418113;
      }
    }
LABEL_34:
    if ( v5 == -1 )
      return (unsigned int)v2;
LABEL_35:
    CloseHandle((HANDLE)v5);
    return (unsigned int)v2;
  }
  v10 = GetLastError();
  v2 = v10;
  if ( v10 > 0 )
    v2 = (unsigned __int16)v10 | 0x80070000;
  if ( v2 >= 0 )
    return (unsigned int)-2147418113;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008bc18  mov     [rsp-28h+arg_8], rbx
0x18008bc1d  mov     [rsp-28h+arg_10], rsi
0x18008bc22  push    rbp
0x18008bc23  push    rdi
0x18008bc24  push    r12
0x18008bc26  push    r14
0x18008bc28  push    r15
0x18008bc2a  mov     rbp, rsp
0x18008bc2d  sub     rsp, 70h
0x18008bc31  mov     rax, cs:__security_cookie
0x18008bc38  xor     rax, rsp
0x18008bc3b  mov     [rbp+var_10], rax
0x18008bc3f  xor     r12d, r12d
0x18008bc42  mov     r15, rcx
0x18008bc45  mov     [rbp+var_2C], r12d
0x18008bc49  mov     ebx, r12d
0x18008bc4c  mov     [rbp+lpBuffer], rbx
0x18008bc50  mov     qword ptr [rbp+FileSize], r12
0x18008bc54  mov     [rbp+NumberOfBytesRead], r12d
0x18008bc58  test    rcx, rcx
0x18008bc5b  jnz     short loc_18008BC6F
0x18008bc5d  mov     [rbp+var_2C], 4CFh
0x18008bc64  mov     r14d, 80070057h
0x18008bc6a  jmp     loc_18008BE33
0x18008bc6f  mov     rcx, [rcx+38h]; lpFileName
0x18008bc73  test    rcx, rcx
0x18008bc76  jz      loc_18008BE05
0x18008bc7c  cmp     [rcx], r12w
0x18008bc80  jz      loc_18008BE05
0x18008bc86  cmp     [r15+40h], r12
0x18008bc8a  jz      short loc_18008BC94
0x18008bc8c  mov     r14d, r12d
0x18008bc8f  jmp     loc_18008BE33
0x18008bc94  xor     r9d, r9d; lpSecurityAttributes
0x18008bc97  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x18008bc9c  mov     [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18008bca4  mov     edx, 80000000h; dwDesiredAccess
0x18008bca9  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18008bcb1  lea     r8d, [r9+1]; dwShareMode
0x18008bcb5  call    cs:__imp_CreateFileW
0x18008bcbb  mov     rsi, rax
0x18008bcbe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008bcc2  jz      loc_18008BDD8
0x18008bcc8  lea     rdx, [rbp+FileSize]; lpFileSize
0x18008bccc  mov     rcx, rax; hFile
0x18008bccf  call    cs:__imp_GetFileSizeEx
0x18008bcd5  test    eax, eax
0x18008bcd7  jnz     short loc_18008BD09
0x18008bcd9  call    cs:__imp_GetLastError
0x18008bcdf  mov     r14d, eax
0x18008bce2  test    eax, eax
0x18008bce4  jle     short loc_18008BCF1
0x18008bce6  movzx   r14d, ax
0x18008bcea  or      r14d, 80070000h
0x18008bcf1  test    r14d, r14d
0x18008bcf4  mov     [rbp+var_2C], 4E6h
0x18008bcfb  mov     eax, 8000FFFFh
0x18008bd00  cmovns  r14d, eax
0x18008bd04  jmp     loc_18008BE2A
0x18008bd09  mov     rdi, qword ptr [rbp+FileSize]
0x18008bd0d  cmp     rdi, 4000000h
0x18008bd14  jl      short loc_18008BD28
0x18008bd16  mov     [rbp+var_2C], 4E7h
0x18008bd1d  mov     r14d, 8007000Dh
0x18008bd23  jmp     loc_18008BE2A
0x18008bd28  mov     eax, 0FFFFFFFFh
0x18008bd2d  cmp     rdi, rax
0x18008bd30  ja      loc_18008BDC9
0x18008bd36  lea     ecx, [rdi+2]; cb
0x18008bd39  lea     rdx, [rbp+lpBuffer]
0x18008bd3d  call    ??$WxAlloc@GVWxCoTaskAllocator@@@@YAJKPEAPEAG@Z; WxAlloc<ushort,WxCoTaskAllocator>(ulong,ushort * *)
0x18008bd42  mov     rbx, [rbp+lpBuffer]
0x18008bd46  mov     r14d, eax
0x18008bd49  test    eax, eax
0x18008bd4b  jns     short loc_18008BD59
0x18008bd4d  mov     [rbp+var_2C], 4EAh
0x18008bd54  jmp     loc_18008BE16
0x18008bd59  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008bd5d  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; lpOverlapped
0x18008bd62  mov     r8d, edi; nNumberOfBytesToRead
0x18008bd65  mov     rdx, rbx; lpBuffer
0x18008bd68  mov     rcx, rsi; hFile
0x18008bd6b  call    cs:__imp_ReadFile
0x18008bd71  test    eax, eax
0x18008bd73  jnz     short loc_18008BDA2
0x18008bd75  call    cs:__imp_GetLastError
0x18008bd7b  mov     r14d, eax
0x18008bd7e  test    eax, eax
0x18008bd80  jle     short loc_18008BD8D
0x18008bd82  movzx   r14d, ax
0x18008bd86  or      r14d, 80070000h
0x18008bd8d  test    r14d, r14d
0x18008bd90  mov     [rbp+var_2C], 4F0h
0x18008bd97  mov     eax, 8000FFFFh
0x18008bd9c  cmovns  r14d, eax
0x18008bda0  jmp     short loc_18008BE16
0x18008bda2  cmp     [rbp+NumberOfBytesRead], edi
0x18008bda5  jz      short loc_18008BDB6
0x18008bda7  mov     [rbp+var_2C], 4F2h
0x18008bdae  mov     r14d, 8000FFFFh
0x18008bdb4  jmp     short loc_18008BE16
0x18008bdb6  mov     ecx, edi
0x18008bdb8  mov     r14d, r12d
0x18008bdbb  shr     rcx, 1
0x18008bdbe  mov     [rbx+rcx*2], r12w
0x18008bdc3  mov     [r15+40h], rbx
0x18008bdc7  jmp     short loc_18008BE2A
0x18008bdc9  mov     [rbp+var_2C], 4E8h
0x18008bdd0  mov     r14d, 80070216h
0x18008bdd6  jmp     short loc_18008BE2A
0x18008bdd8  call    cs:__imp_GetLastError
0x18008bdde  mov     r14d, eax
0x18008bde1  test    eax, eax
0x18008bde3  jle     short loc_18008BDF0
0x18008bde5  movzx   r14d, ax
0x18008bde9  or      r14d, 80070000h
0x18008bdf0  test    r14d, r14d
0x18008bdf3  mov     [rbp+var_2C], 4E0h
0x18008bdfa  mov     eax, 8000FFFFh
0x18008bdff  cmovns  r14d, eax
0x18008be03  jmp     short loc_18008BE33
0x18008be05  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008be09  mov     [rbp+var_2C], 4D1h
0x18008be10  mov     r14d, 80070057h
0x18008be16  test    rbx, rbx
0x18008be19  jz      short loc_18008BE24
0x18008be1b  lea     rcx, [rbp+lpBuffer]; void **
0x18008be1f  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18008be24  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18008be28  jz      short loc_18008BE33
0x18008be2a  mov     rcx, rsi; hObject
0x18008be2d  call    cs:__imp_CloseHandle
0x18008be33  mov     eax, r14d
0x18008be36  mov     rcx, [rbp+var_10]
0x18008be3a  xor     rcx, rsp; StackCookie
0x18008be3d  call    __security_check_cookie
0x18008be42  lea     r11, [rsp+70h+var_s0]
0x18008be47  mov     rbx, [r11+38h]
0x18008be4b  mov     rsi, [r11+40h]
0x18008be4f  mov     rsp, r11
0x18008be52  pop     r15
0x18008be54  pop     r14
0x18008be56  pop     r12
0x18008be58  pop     rdi
0x18008be59  pop     rbp
0x18008be5a  retn
```
