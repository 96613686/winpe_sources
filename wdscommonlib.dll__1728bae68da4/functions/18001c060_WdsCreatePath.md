# WdsCreatePath

- ea: `0x18001c060`
- end: `0x18001c237`
- name: `WdsCreatePath`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a1c8`

## callees

- `0x18001bef0`
- `0x18001c060`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001c0c1`
- `msvcrt!_wcsnicmp` at `0x18001c0c1`
- `msvcrt!wcschr` at `0x18001c0ee`
- `msvcrt!wcschr` at `0x18001c121`
- `msvcrt!wcschr` at `0x18001c1a7`
- `msvcrt!wcschr` at `0x18001c0ee`
- `msvcrt!wcschr` at `0x18001c121`
- `msvcrt!wcschr` at `0x18001c1a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c20b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c20b`
- `KERNEL32!GetFileAttributesW` at `0x18001c158`
- `KERNEL32!GetFileAttributesW` at `0x18001c158`
- `KERNEL32!CreateDirectoryW` at `0x18001c16e`
- `KERNEL32!CreateDirectoryW` at `0x18001c1c1`
- `KERNEL32!CreateDirectoryW` at `0x18001c16e`
- `KERNEL32!CreateDirectoryW` at `0x18001c1c1`
- `KERNEL32!GetLastError` at `0x18001c17e`
- `KERNEL32!GetLastError` at `0x18001c1d1`
- `KERNEL32!GetLastError` at `0x18001c17e`
- `KERNEL32!GetLastError` at `0x18001c1d1`

## pseudocode

```c
__int64 __fastcall WdsCreatePath(unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2, int a3)
{
  int ExtendedPath; // ebx
  __int64 v6; // rax
  unsigned int v7; // edi
  wchar_t *v8; // rax
  __int64 v9; // rax
  wchar_t *v10; // rax
  const wchar_t *i; // rcx
  wchar_t *v12; // r14
  wchar_t *v13; // rdi
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  wchar_t *v16; // rax

  if ( a1 )
  {
    ExtendedPath = WdsCreateExtendedPath(a1);
    if ( ExtendedPath >= 0 )
    {
      if ( _wcsnicmp(0, L"\\\\?\\UNC", 7u) )
      {
        v9 = 8;
LABEL_12:
        v10 = wcschr((const wchar_t *)v9, 0x5Cu);
        if ( v10 )
        {
          for ( i = v10 + 1; ; i = v13 )
          {
            v16 = wcschr(i, 0x5Cu);
            v13 = v16;
            if ( !v16 )
              break;
            v12 = v16;
            do
              ++v13;
            while ( *v13 == 92 );
            if ( !*v13 )
              break;
            *v16 = 0;
            FileAttributesW = GetFileAttributesW(0);
            if ( FileAttributesW == -1 )
            {
              if ( !CreateDirectoryW(0, 0) )
              {
                LastError = GetLastError();
                if ( LastError != 183 )
                {
                  if ( LastError > 0 )
                    return (unsigned __int16)LastError | 0x80070000;
                  return (unsigned int)LastError;
                }
              }
            }
            else if ( (FileAttributesW & 0x10) == 0 )
            {
              return (unsigned int)-2147024629;
            }
            *v12 = 92;
          }
        }
        if ( !CreateDirectoryW(0, a2) )
        {
          LastError = GetLastError();
          ExtendedPath = LastError;
          if ( a3 && LastError == 183 )
          {
            return 0;
          }
          else if ( LastError > 0 )
          {
            return (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      else
      {
        v6 = 14;
        v7 = 0;
        while ( 1 )
        {
          if ( v7 >= 3 )
          {
LABEL_9:
            v9 = v6 - 2;
            goto LABEL_12;
          }
          v8 = wcschr((const wchar_t *)v6, 0x5Cu);
          if ( !v8 )
            return (unsigned int)-2147024843;
          ++v7;
          v6 = (__int64)(v8 + 1);
          if ( !v6 )
            goto LABEL_9;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ExtendedPath;
}

```

## disassembly

```asm
0x18001c060  mov     rax, rsp
0x18001c063  mov     [rax+10h], rbx
0x18001c067  mov     [rax+18h], rbp
0x18001c06b  mov     [rax+20h], rsi
0x18001c06f  push    rdi
0x18001c070  push    r12
0x18001c072  push    r13
0x18001c074  push    r14
0x18001c076  push    r15
0x18001c078  sub     rsp, 20h
0x18001c07c  xor     r12d, r12d
0x18001c07f  mov     ebp, r8d
0x18001c082  mov     [rax+8], r12
0x18001c086  mov     r15, rdx
0x18001c089  test    rcx, rcx
0x18001c08c  jnz     short loc_18001C098
0x18001c08e  mov     ebx, 80070057h
0x18001c093  jmp     loc_18001C217
0x18001c098  lea     rdx, [rsp+48h+String1]
0x18001c09d  call    WdsCreateExtendedPath
0x18001c0a2  mov     rsi, [rsp+48h+String1]
0x18001c0a7  mov     ebx, eax
0x18001c0a9  test    eax, eax
0x18001c0ab  js      loc_18001C203
0x18001c0b1  mov     r8d, 7; MaxCount
0x18001c0b7  lea     rdx, aUnc; "\\\\?\\UNC"
0x18001c0be  mov     rcx, rsi; String1
0x18001c0c1  call    cs:__imp__wcsnicmp
0x18001c0c8  nop     dword ptr [rax+rax+00h]
0x18001c0cd  mov     r13d, 5Ch ; '\'
0x18001c0d3  test    eax, eax
0x18001c0d5  jnz     short loc_18001C117
0x18001c0d7  lea     rax, [rsi+0Eh]
0x18001c0db  mov     edi, r12d
0x18001c0de  test    rax, rax
0x18001c0e1  jz      short loc_18001C107
0x18001c0e3  cmp     edi, 3
0x18001c0e6  jnb     short loc_18001C107
0x18001c0e8  mov     edx, r13d; Ch
0x18001c0eb  mov     rcx, rax; Str
0x18001c0ee  call    cs:__imp_wcschr
0x18001c0f5  nop     dword ptr [rax+rax+00h]
0x18001c0fa  test    rax, rax
0x18001c0fd  jz      short loc_18001C10D
0x18001c0ff  inc     edi
0x18001c101  add     rax, 2
0x18001c105  jnz     short loc_18001C0E3
0x18001c107  sub     rax, 2
0x18001c10b  jmp     short loc_18001C11B
0x18001c10d  mov     ebx, 80070035h
0x18001c112  jmp     loc_18001C203
0x18001c117  lea     rax, [rsi+8]
0x18001c11b  mov     edx, r13d; Ch
0x18001c11e  mov     rcx, rax; Str
0x18001c121  call    cs:__imp_wcschr
0x18001c128  nop     dword ptr [rax+rax+00h]
0x18001c12d  test    rax, rax
0x18001c130  jz      loc_18001C1BB
0x18001c136  lea     rcx, [rax+2]
0x18001c13a  jmp     short loc_18001C1A4
0x18001c13c  mov     r14, rdi
0x18001c13f  add     rdi, 2
0x18001c143  movzx   eax, word ptr [rdi]
0x18001c146  cmp     ax, r13w
0x18001c14a  jz      short loc_18001C13F
0x18001c14c  test    ax, ax
0x18001c14f  jz      short loc_18001C1BB
0x18001c151  mov     rcx, rsi; lpFileName
0x18001c154  mov     [r14], r12w
0x18001c158  call    cs:__imp_GetFileAttributesW
0x18001c15f  nop     dword ptr [rax+rax+00h]
0x18001c164  cmp     eax, 0FFFFFFFFh
0x18001c167  jnz     short loc_18001C199
0x18001c169  xor     edx, edx; lpSecurityAttributes
0x18001c16b  mov     rcx, rsi; lpPathName
0x18001c16e  call    cs:__imp_CreateDirectoryW
0x18001c175  nop     dword ptr [rax+rax+00h]
0x18001c17a  test    eax, eax
0x18001c17c  jnz     short loc_18001C19D
0x18001c17e  call    cs:__imp_GetLastError
0x18001c185  nop     dword ptr [rax+rax+00h]
0x18001c18a  cmp     eax, 0B7h
0x18001c18f  jz      short loc_18001C19D
0x18001c191  test    eax, eax
0x18001c193  jg      short loc_18001C1FA
0x18001c195  mov     ebx, eax
0x18001c197  jmp     short loc_18001C203
0x18001c199  test    al, 10h
0x18001c19b  jz      short loc_18001C1EF
0x18001c19d  mov     [r14], r13w
0x18001c1a1  mov     rcx, rdi; Str
0x18001c1a4  mov     edx, r13d; Ch
0x18001c1a7  call    cs:__imp_wcschr
0x18001c1ae  nop     dword ptr [rax+rax+00h]
0x18001c1b3  mov     rdi, rax
0x18001c1b6  test    rax, rax
0x18001c1b9  jnz     short loc_18001C13C
0x18001c1bb  mov     rdx, r15; lpSecurityAttributes
0x18001c1be  mov     rcx, rsi; lpPathName
0x18001c1c1  call    cs:__imp_CreateDirectoryW
0x18001c1c8  nop     dword ptr [rax+rax+00h]
0x18001c1cd  test    eax, eax
0x18001c1cf  jnz     short loc_18001C203
0x18001c1d1  call    cs:__imp_GetLastError
0x18001c1d8  nop     dword ptr [rax+rax+00h]
0x18001c1dd  mov     ebx, eax
0x18001c1df  test    ebp, ebp
0x18001c1e1  jz      short loc_18001C1F6
0x18001c1e3  cmp     eax, 0B7h
0x18001c1e8  jnz     short loc_18001C1F6
0x18001c1ea  mov     ebx, r12d
0x18001c1ed  jmp     short loc_18001C203
0x18001c1ef  mov     ebx, 8007010Bh
0x18001c1f4  jmp     short loc_18001C203
0x18001c1f6  test    eax, eax
0x18001c1f8  jle     short loc_18001C203
0x18001c1fa  movzx   ebx, ax
0x18001c1fd  or      ebx, 80070000h
0x18001c203  test    rsi, rsi
0x18001c206  jz      short loc_18001C217
0x18001c208  mov     rcx, rsi
0x18001c20b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c212  nop     dword ptr [rax+rax+00h]
0x18001c217  mov     rbp, [rsp+48h+arg_10]
0x18001c21c  mov     eax, ebx
0x18001c21e  mov     rbx, [rsp+48h+arg_8]
0x18001c223  mov     rsi, [rsp+48h+arg_18]
0x18001c228  add     rsp, 20h
0x18001c22c  pop     r15
0x18001c22e  pop     r14
0x18001c230  pop     r13
0x18001c232  pop     r12
0x18001c234  pop     rdi
0x18001c235  retn
```
