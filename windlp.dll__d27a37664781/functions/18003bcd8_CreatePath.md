# CreatePath

- ea: `0x18003bcd8`
- end: `0x18003bead`
- name: `CreatePath`
- size: `469`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180032518`
- `0x18003379c`
- `0x18003a380`
- `0x18003a4c8`

## callees

- `0x18000200c`
- `0x180039394`
- `0x18003bcd8`
- `0x18003c464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003bd74`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003bdea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003bd74`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003bdea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003be12`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003be12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003be5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003be5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003be68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003be68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bdad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003be7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003be8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bdad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003be7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003be8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be70`

## string_xrefs

- `0x18003bd99`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x18003bdde`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x18003be06`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x18003be42`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x18003be2d`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall CreatePath(const wchar_t *a1)
{
  WCHAR *v2; // rdi
  DWORD v3; // ebx
  int v4; // ebp
  const wchar_t *v5; // rax
  wchar_t *v6; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  void *v9; // r9
  const wchar_t *v10; // r8
  DWORD FileAttributesW; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // [rsp+20h] [rbp-38h]
  wchar_t *v15; // [rsp+60h] [rbp+8h]

  if ( a1 && *a1 )
  {
    v2 = (WCHAR *)PrepareUnicodePathEx(a1);
    if ( v2 )
    {
      v3 = 0;
      v4 = 1;
      v5 = v2;
      while ( 1 )
      {
        v6 = wcschr_0(v5, 0x5Cu);
        v15 = v6;
        if ( !v6 )
          break;
        *v6 = 0;
        if ( !CreateDirectoryW(v2, 0) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError == 5 || LastError == 183 )
          {
            v3 = 0;
          }
          else
          {
            LODWORD(v14) = LastError;
            LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x", v2, v14);
            SetLastError(v3);
            v4 = 0;
          }
        }
        *v15 = 92;
        v5 = v15 + 1;
        if ( v4 != 1 )
        {
          v8 = GetLastError();
          v9 = (void *)a1;
          v10 = L"CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x";
          goto LABEL_21;
        }
      }
      if ( CreateDirectoryW(v2, 0) )
        goto LABEL_23;
      v8 = GetLastError();
      v3 = v8;
      if ( v8 != 183 )
      {
        v9 = v2;
        v10 = L"CreatePath: Unable to create [%s]; GLE = 0x%x";
        goto LABEL_22;
      }
      FileAttributesW = GetFileAttributesW(v2);
      if ( FileAttributesW == -1 )
      {
        v8 = GetLastError();
        v9 = v2;
        v10 = L"CreatePath: Unable to get attributes for [%s]; GLE = 0x%x";
LABEL_21:
        v3 = v8;
LABEL_22:
        LODWORD(v14) = v8;
        LibLog(&g_WdsLibLog, 50331648, v10, v9, v14);
        goto LABEL_23;
      }
      if ( (FileAttributesW & 0x10) != 0 )
      {
        v3 = 0;
      }
      else
      {
        LODWORD(v14) = 183;
        LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Existing path [%s] is not a directory; GLE = 0x%x", v2, v14);
      }
LABEL_23:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    else
    {
      v3 = GetLastError();
    }
    SetLastError(v3);
    return v3 == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18003bcd8  mov     r11, rsp
0x18003bcdb  mov     [r11+10h], rbx
0x18003bcdf  mov     [r11+18h], rbp
0x18003bce3  push    rsi
0x18003bce4  push    rdi
0x18003bce5  push    r13
0x18003bce7  push    r14
0x18003bce9  push    r15
0x18003bceb  sub     rsp, 30h
0x18003bcef  mov     qword ptr [r11+8], 0
0x18003bcf7  mov     rsi, rcx
0x18003bcfa  test    rcx, rcx
0x18003bcfd  jz      loc_18003BE89
0x18003bd03  xor     eax, eax
0x18003bd05  cmp     ax, [rcx]
0x18003bd08  jz      loc_18003BE89
0x18003bd0e  lea     rdx, [r11+8]
0x18003bd12  call    PrepareUnicodePathEx
0x18003bd17  mov     rdi, rax
0x18003bd1a  test    rax, rax
0x18003bd1d  jz      loc_18003BE70
0x18003bd23  mov     rax, [rsp+58h+arg_0]
0x18003bd28  xor     ebx, ebx
0x18003bd2a  mov     ebp, 1
0x18003bd2f  test    rax, rax
0x18003bd32  jz      short loc_18003BD3A
0x18003bd34  add     rax, 2
0x18003bd38  jmp     short loc_18003BD3D
0x18003bd3a  mov     rax, rdi
0x18003bd3d  mov     [rsp+58h+arg_0], rax
0x18003bd42  lea     r15, g_WdsLibLog
0x18003bd49  mov     r13d, 5Ch ; '\'
0x18003bd4f  mov     r14d, 3000000h
0x18003bd55  mov     edx, r13d; Ch
0x18003bd58  mov     rcx, rax; Str
0x18003bd5b  call    wcschr_0
0x18003bd60  xor     edx, edx; lpSecurityAttributes
0x18003bd62  mov     [rsp+58h+arg_0], rax
0x18003bd67  test    rax, rax
0x18003bd6a  jz      short loc_18003BDE7
0x18003bd6c  xor     ecx, ecx
0x18003bd6e  mov     [rax], cx
0x18003bd71  mov     rcx, rdi; lpPathName
0x18003bd74  call    cs:__imp_CreateDirectoryW
0x18003bd7a  test    eax, eax
0x18003bd7c  jnz     short loc_18003BDB9
0x18003bd7e  call    cs:__imp_GetLastError
0x18003bd84  mov     ebx, eax
0x18003bd86  cmp     eax, 5
0x18003bd89  jz      short loc_18003BDB7
0x18003bd8b  cmp     eax, 0B7h
0x18003bd90  jz      short loc_18003BDB7
0x18003bd92  mov     r9, rdi
0x18003bd95  mov     dword ptr [rsp+58h+var_38], eax
0x18003bd99  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x18003bda0  mov     edx, r14d
0x18003bda3  mov     rcx, r15
0x18003bda6  call    LibLog
0x18003bdab  mov     ecx, ebx; dwErrCode
0x18003bdad  call    cs:__imp_SetLastError
0x18003bdb3  xor     ebp, ebp
0x18003bdb5  jmp     short loc_18003BDB9
0x18003bdb7  xor     ebx, ebx
0x18003bdb9  mov     rax, [rsp+58h+arg_0]
0x18003bdbe  mov     [rax], r13w
0x18003bdc2  mov     rax, [rsp+58h+arg_0]
0x18003bdc7  add     rax, 2
0x18003bdcb  mov     [rsp+58h+arg_0], rax
0x18003bdd0  cmp     ebp, 1
0x18003bdd3  jz      short loc_18003BD55
0x18003bdd5  call    cs:__imp_GetLastError
0x18003bddb  mov     r9, rsi
0x18003bdde  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x18003bde5  jmp     short loc_18003BE49
0x18003bde7  mov     rcx, rdi; lpPathName
0x18003bdea  call    cs:__imp_CreateDirectoryW
0x18003bdf0  test    eax, eax
0x18003bdf2  jnz     short loc_18003BE5A
0x18003bdf4  call    cs:__imp_GetLastError
0x18003bdfa  mov     ebx, eax
0x18003bdfc  cmp     eax, 0B7h
0x18003be01  jz      short loc_18003BE0F
0x18003be03  mov     r9, rdi
0x18003be06  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x18003be0d  jmp     short loc_18003BE4B
0x18003be0f  mov     rcx, rdi; lpFileName
0x18003be12  call    cs:__imp_GetFileAttributesW
0x18003be18  cmp     eax, 0FFFFFFFFh
0x18003be1b  jz      short loc_18003BE39
0x18003be1d  test    al, 10h
0x18003be1f  jz      short loc_18003BE25
0x18003be21  xor     ebx, ebx
0x18003be23  jmp     short loc_18003BE5A
0x18003be25  mov     dword ptr [rsp+58h+var_38], 0B7h
0x18003be2d  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x18003be34  mov     r9, rdi
0x18003be37  jmp     short loc_18003BE4F
0x18003be39  call    cs:__imp_GetLastError
0x18003be3f  mov     r9, rdi
0x18003be42  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x18003be49  mov     ebx, eax
0x18003be4b  mov     dword ptr [rsp+58h+var_38], eax
0x18003be4f  mov     edx, r14d
0x18003be52  mov     rcx, r15
0x18003be55  call    LibLog
0x18003be5a  call    cs:__imp_GetProcessHeap
0x18003be60  mov     r8, rdi; lpMem
0x18003be63  xor     edx, edx; dwFlags
0x18003be65  mov     rcx, rax; hHeap
0x18003be68  call    cs:__imp_HeapFree
0x18003be6e  jmp     short loc_18003BE78
0x18003be70  call    cs:__imp_GetLastError
0x18003be76  mov     ebx, eax
0x18003be78  mov     ecx, ebx; dwErrCode
0x18003be7a  call    cs:__imp_SetLastError
0x18003be80  xor     eax, eax
0x18003be82  test    ebx, ebx
0x18003be84  setz    al
0x18003be87  jmp     short loc_18003BE96
0x18003be89  mov     ecx, 57h ; 'W'; dwErrCode
0x18003be8e  call    cs:__imp_SetLastError
0x18003be94  xor     eax, eax
0x18003be96  mov     rbx, [rsp+58h+arg_8]
0x18003be9b  mov     rbp, [rsp+58h+arg_10]
0x18003bea0  add     rsp, 30h
0x18003bea4  pop     r15
0x18003bea6  pop     r14
0x18003bea8  pop     r13
0x18003beaa  pop     rdi
0x18003beab  pop     rsi
0x18003beac  retn
```
