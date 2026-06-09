# CreatePath

- ea: `0x1800099c0`
- end: `0x180009b95`
- name: `CreatePath`
- size: `469`
- prototype: `_BOOL8 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005080`

## callees

- `0x1800029a5`
- `0x180008f64`
- `0x1800099c0`
- `0x18000a0f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b50`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009a5c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009ad2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009a5c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009ad2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009afa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009afa`

## string_xrefs

- `0x180009a81`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x180009b15`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x180009b2a`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x180009aee`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x180009ac6`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`

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
0x1800099c0  mov     r11, rsp
0x1800099c3  mov     [r11+10h], rbx
0x1800099c7  mov     [r11+18h], rbp
0x1800099cb  push    rsi
0x1800099cc  push    rdi
0x1800099cd  push    r13
0x1800099cf  push    r14
0x1800099d1  push    r15
0x1800099d3  sub     rsp, 30h
0x1800099d7  mov     qword ptr [r11+8], 0
0x1800099df  mov     rsi, rcx
0x1800099e2  test    rcx, rcx
0x1800099e5  jz      loc_180009B71
0x1800099eb  xor     eax, eax
0x1800099ed  cmp     ax, [rcx]
0x1800099f0  jz      loc_180009B71
0x1800099f6  lea     rdx, [r11+8]
0x1800099fa  call    PrepareUnicodePathEx
0x1800099ff  mov     rdi, rax
0x180009a02  test    rax, rax
0x180009a05  jz      loc_180009B58
0x180009a0b  mov     rax, [rsp+58h+arg_0]
0x180009a10  xor     ebx, ebx
0x180009a12  mov     ebp, 1
0x180009a17  test    rax, rax
0x180009a1a  jz      short loc_180009A22
0x180009a1c  add     rax, 2
0x180009a20  jmp     short loc_180009A25
0x180009a22  mov     rax, rdi
0x180009a25  mov     [rsp+58h+arg_0], rax
0x180009a2a  lea     r15, g_WdsLibLog
0x180009a31  mov     r13d, 5Ch ; '\'
0x180009a37  mov     r14d, 3000000h
0x180009a3d  mov     edx, r13d; Ch
0x180009a40  mov     rcx, rax; Str
0x180009a43  call    wcschr_0
0x180009a48  xor     edx, edx; lpSecurityAttributes
0x180009a4a  mov     [rsp+58h+arg_0], rax
0x180009a4f  test    rax, rax
0x180009a52  jz      short loc_180009ACF
0x180009a54  xor     ecx, ecx
0x180009a56  mov     [rax], cx
0x180009a59  mov     rcx, rdi; lpPathName
0x180009a5c  call    cs:__imp_CreateDirectoryW
0x180009a62  test    eax, eax
0x180009a64  jnz     short loc_180009AA1
0x180009a66  call    cs:__imp_GetLastError
0x180009a6c  mov     ebx, eax
0x180009a6e  cmp     eax, 5
0x180009a71  jz      short loc_180009A9F
0x180009a73  cmp     eax, 0B7h
0x180009a78  jz      short loc_180009A9F
0x180009a7a  mov     r9, rdi
0x180009a7d  mov     dword ptr [rsp+58h+var_38], eax
0x180009a81  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x180009a88  mov     edx, r14d
0x180009a8b  mov     rcx, r15
0x180009a8e  call    LibLog
0x180009a93  mov     ecx, ebx; dwErrCode
0x180009a95  call    cs:__imp_SetLastError
0x180009a9b  xor     ebp, ebp
0x180009a9d  jmp     short loc_180009AA1
0x180009a9f  xor     ebx, ebx
0x180009aa1  mov     rax, [rsp+58h+arg_0]
0x180009aa6  mov     [rax], r13w
0x180009aaa  mov     rax, [rsp+58h+arg_0]
0x180009aaf  add     rax, 2
0x180009ab3  mov     [rsp+58h+arg_0], rax
0x180009ab8  cmp     ebp, 1
0x180009abb  jz      short loc_180009A3D
0x180009abd  call    cs:__imp_GetLastError
0x180009ac3  mov     r9, rsi
0x180009ac6  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180009acd  jmp     short loc_180009B31
0x180009acf  mov     rcx, rdi; lpPathName
0x180009ad2  call    cs:__imp_CreateDirectoryW
0x180009ad8  test    eax, eax
0x180009ada  jnz     short loc_180009B42
0x180009adc  call    cs:__imp_GetLastError
0x180009ae2  mov     ebx, eax
0x180009ae4  cmp     eax, 0B7h
0x180009ae9  jz      short loc_180009AF7
0x180009aeb  mov     r9, rdi
0x180009aee  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x180009af5  jmp     short loc_180009B33
0x180009af7  mov     rcx, rdi; lpFileName
0x180009afa  call    cs:__imp_GetFileAttributesW
0x180009b00  cmp     eax, 0FFFFFFFFh
0x180009b03  jz      short loc_180009B21
0x180009b05  test    al, 10h
0x180009b07  jz      short loc_180009B0D
0x180009b09  xor     ebx, ebx
0x180009b0b  jmp     short loc_180009B42
0x180009b0d  mov     dword ptr [rsp+58h+var_38], 0B7h
0x180009b15  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x180009b1c  mov     r9, rdi
0x180009b1f  jmp     short loc_180009B37
0x180009b21  call    cs:__imp_GetLastError
0x180009b27  mov     r9, rdi
0x180009b2a  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x180009b31  mov     ebx, eax
0x180009b33  mov     dword ptr [rsp+58h+var_38], eax
0x180009b37  mov     edx, r14d
0x180009b3a  mov     rcx, r15
0x180009b3d  call    LibLog
0x180009b42  call    cs:__imp_GetProcessHeap
0x180009b48  mov     r8, rdi; lpMem
0x180009b4b  xor     edx, edx; dwFlags
0x180009b4d  mov     rcx, rax; hHeap
0x180009b50  call    cs:__imp_HeapFree
0x180009b56  jmp     short loc_180009B60
0x180009b58  call    cs:__imp_GetLastError
0x180009b5e  mov     ebx, eax
0x180009b60  mov     ecx, ebx; dwErrCode
0x180009b62  call    cs:__imp_SetLastError
0x180009b68  xor     eax, eax
0x180009b6a  test    ebx, ebx
0x180009b6c  setz    al
0x180009b6f  jmp     short loc_180009B7E
0x180009b71  mov     ecx, 57h ; 'W'; dwErrCode
0x180009b76  call    cs:__imp_SetLastError
0x180009b7c  xor     eax, eax
0x180009b7e  mov     rbx, [rsp+58h+arg_8]
0x180009b83  mov     rbp, [rsp+58h+arg_10]
0x180009b88  add     rsp, 30h
0x180009b8c  pop     r15
0x180009b8e  pop     r14
0x180009b90  pop     r13
0x180009b92  pop     rdi
0x180009b93  pop     rsi
0x180009b94  retn
```
