# FixupPageFilePath(ushort const *,ushort * *,bool *)

- ea: `0x18000f8d4`
- end: `0x18000faae`
- name: `?FixupPageFilePath@@YAJPEBGPEAPEAGPEA_N@Z`
- size: `474`
- prototype: `__int64 __fastcall(wchar_t *Source, unsigned __int16 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x180010a5c`

## callees

- `0x180002692`
- `0x18000f8d4`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f959`
- `msvcrt!wcscat_s` at `0x18000f969`
- `msvcrt!wcscat_s` at `0x18000fa23`
- `msvcrt!wcscat_s` at `0x18000f959`
- `msvcrt!wcscat_s` at `0x18000f969`
- `msvcrt!wcscat_s` at `0x18000fa23`
- `msvcrt!wcsrchr` at `0x18000f913`
- `msvcrt!wcsrchr` at `0x18000f913`
- `msvcrt!malloc` at `0x18000f9f4`
- `msvcrt!malloc` at `0x18000f9f4`
- `msvcrt!free` at `0x18000fa6b`
- `msvcrt!free` at `0x18000fa6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fa7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fa7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f9a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f9a7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000fa10`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000fa10`

## pseudocode

```c
__int64 __fastcall FixupPageFilePath(wchar_t *Source, unsigned __int16 **a2, bool *a3)
{
  wchar_t *v6; // rax
  signed int v7; // ebx
  wchar_t *v8; // r15
  wchar_t v9; // bx
  __int64 v10; // rsi
  __int64 v11; // rbx
  HANDLE FileW; // rbp
  signed int LastError; // eax
  rsize_t v14; // r14
  WCHAR *v15; // rax
  wchar_t *v16; // rdi
  _WORD *v17; // rdx
  wchar_t Destination[264]; // [rsp+40h] [rbp-258h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = wcsrchr(Source, 0x5Cu);
  if ( v6 )
  {
    v8 = v6 + 1;
    v9 = v6[1];
    v6[1] = 0;
    memset_0(Destination, 0, 0x208u);
    wcscat_s(Destination, 0x104u, L"\\\\?\\GLOBALROOT");
    wcscat_s(Destination, 0x104u, Source);
    v10 = -1;
    *v8 = v9;
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    FileW = CreateFileW(Destination, 0, 7u, 0, 3u, 0x2000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v14 = v11 + (v11 + 1 < (unsigned __int64)(v11 + 260) ? 260LL : 1LL);
      v15 = (WCHAR *)malloc(2 * v14);
      v7 = 0;
      v16 = v15;
      if ( v15 )
      {
        if ( GetFinalPathNameByHandleW(FileW, v15, v14, 0) )
        {
          wcscat_s(v16, v14, v8);
          v17 = v16 + 4;
          do
            ++v10;
          while ( v17[v10] );
          memmove_0(v16, v17, 2 * v10 + 2);
          *a2 = v16;
          *a3 = 1;
        }
        else
        {
          v7 = GetLastError();
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          free(v16);
        }
      }
      else
      {
        v7 = -2147024882;
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f8d4  mov     [rsp+arg_18], rbx
0x18000f8d9  push    rbp
0x18000f8da  push    rsi
0x18000f8db  push    rdi
0x18000f8dc  push    r12
0x18000f8de  push    r13
0x18000f8e0  push    r14
0x18000f8e2  push    r15
0x18000f8e4  sub     rsp, 260h
0x18000f8eb  mov     rax, cs:__security_cookie
0x18000f8f2  xor     rax, rsp
0x18000f8f5  mov     [rsp+298h+var_48], rax
0x18000f8fd  xor     r14d, r14d
0x18000f900  mov     r12, rdx
0x18000f903  mov     [r8], r14b
0x18000f906  mov     r13, r8
0x18000f909  mov     [rdx], r14
0x18000f90c  mov     rdi, rcx
0x18000f90f  lea     edx, [r14+5Ch]; Ch
0x18000f913  call    cs:__imp_wcsrchr
0x18000f919  test    rax, rax
0x18000f91c  jnz     short loc_18000F928
0x18000f91e  mov     ebx, 8000FFFFh
0x18000f923  jmp     loc_18000FA81
0x18000f928  lea     r15, [rax+2]
0x18000f92c  xor     edx, edx; Val
0x18000f92e  movzx   ebx, word ptr [r15]
0x18000f932  lea     rcx, [rsp+298h+Destination]; void *
0x18000f937  mov     r8d, 208h; Size
0x18000f93d  mov     [r15], r14w
0x18000f941  call    memset_0
0x18000f946  mov     esi, 104h
0x18000f94b  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x18000f952  mov     edx, esi; SizeInWords
0x18000f954  lea     rcx, [rsp+298h+Destination]; Destination
0x18000f959  call    cs:__imp_wcscat_s
0x18000f95f  mov     r8, rdi; Source
0x18000f962  lea     rcx, [rsp+298h+Destination]; Destination
0x18000f967  mov     edx, esi; SizeInWords
0x18000f969  call    cs:__imp_wcscat_s
0x18000f96f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f973  mov     [r15], bx
0x18000f977  mov     rbx, rsi
0x18000f97a  inc     rbx
0x18000f97d  cmp     [r15+rbx*2], r14w
0x18000f982  jnz     short loc_18000F97A
0x18000f984  xor     r9d, r9d; lpSecurityAttributes
0x18000f987  mov     [rsp+298h+hTemplateFile], r14; hTemplateFile
0x18000f98c  mov     [rsp+298h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18000f994  lea     rcx, [rsp+298h+Destination]; lpFileName
0x18000f999  xor     edx, edx; dwDesiredAccess
0x18000f99b  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f9a3  lea     r8d, [r9+7]; dwShareMode
0x18000f9a7  call    cs:__imp_CreateFileW
0x18000f9ad  mov     rbp, rax
0x18000f9b0  cmp     rax, rsi
0x18000f9b3  jnz     short loc_18000F9D3
0x18000f9b5  call    cs:__imp_GetLastError
0x18000f9bb  mov     ebx, eax
0x18000f9bd  test    eax, eax
0x18000f9bf  jle     loc_18000FA81
0x18000f9c5  movzx   ebx, ax
0x18000f9c8  or      ebx, 80070000h
0x18000f9ce  jmp     loc_18000FA81
0x18000f9d3  lea     rcx, [rbx+104h]
0x18000f9da  lea     rax, [rbx+1]
0x18000f9de  cmp     rax, rcx
0x18000f9e1  sbb     rax, rax
0x18000f9e4  and     eax, 103h
0x18000f9e9  lea     r14, [rax+1]
0x18000f9ed  add     r14, rbx
0x18000f9f0  lea     rcx, [r14+r14]; Size
0x18000f9f4  call    cs:__imp_malloc
0x18000f9fa  xor     ebx, ebx
0x18000f9fc  mov     rdi, rax
0x18000f9ff  test    rax, rax
0x18000fa02  jz      short loc_18000FA73
0x18000fa04  mov     r8d, r14d; cchFilePath
0x18000fa07  xor     r9d, r9d; dwFlags
0x18000fa0a  mov     rdx, rax; lpszFilePath
0x18000fa0d  mov     rcx, rbp; hFile
0x18000fa10  call    cs:__imp_GetFinalPathNameByHandleW
0x18000fa16  test    eax, eax
0x18000fa18  jz      short loc_18000FA53
0x18000fa1a  mov     r8, r15; Source
0x18000fa1d  mov     rdx, r14; SizeInWords
0x18000fa20  mov     rcx, rdi; Destination
0x18000fa23  call    cs:__imp_wcscat_s
0x18000fa29  lea     rdx, [rdi+8]; Src
0x18000fa2d  xor     eax, eax
0x18000fa2f  inc     rsi
0x18000fa32  cmp     [rdx+rsi*2], ax
0x18000fa36  jnz     short loc_18000FA2F
0x18000fa38  lea     r8, ds:2[rsi*2]; Size
0x18000fa40  mov     rcx, rdi; void *
0x18000fa43  call    memmove_0
0x18000fa48  mov     [r12], rdi
0x18000fa4c  mov     byte ptr [r13+0], 1
0x18000fa51  jmp     short loc_18000FA78
0x18000fa53  call    cs:__imp_GetLastError
0x18000fa59  mov     ebx, eax
0x18000fa5b  test    eax, eax
0x18000fa5d  jle     short loc_18000FA68
0x18000fa5f  movzx   ebx, bx
0x18000fa62  or      ebx, 80070000h
0x18000fa68  mov     rcx, rdi; Block
0x18000fa6b  call    cs:__imp_free
0x18000fa71  jmp     short loc_18000FA78
0x18000fa73  mov     ebx, 8007000Eh
0x18000fa78  mov     rcx, rbp; hObject
0x18000fa7b  call    cs:__imp_CloseHandle
0x18000fa81  mov     eax, ebx
0x18000fa83  mov     rcx, [rsp+298h+var_48]
0x18000fa8b  xor     rcx, rsp; StackCookie
0x18000fa8e  call    __security_check_cookie
0x18000fa93  mov     rbx, [rsp+298h+arg_18]
0x18000fa9b  add     rsp, 260h
0x18000faa2  pop     r15
0x18000faa4  pop     r14
0x18000faa6  pop     r13
0x18000faa8  pop     r12
0x18000faaa  pop     rdi
0x18000faab  pop     rsi
0x18000faac  pop     rbp
0x18000faad  retn
```
