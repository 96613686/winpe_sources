# WdsCreatePath

- ea: `0x18001b1c0`
- end: `0x18001b390`
- name: `WdsCreatePath`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800193b8`

## callees

- `0x18001b050`
- `0x18001b1c0`
- `0x18002e468`

## import_xrefs

- `msvcrt!wcschr` at `0x18001b24e`
- `msvcrt!wcschr` at `0x18001b281`
- `msvcrt!wcschr` at `0x18001b307`
- `msvcrt!wcschr` at `0x18001b24e`
- `msvcrt!wcschr` at `0x18001b281`
- `msvcrt!wcschr` at `0x18001b307`
- `msvcrt!_wcsnicmp` at `0x18001b221`
- `msvcrt!_wcsnicmp` at `0x18001b221`
- `KERNEL32!GetLastError` at `0x18001b2de`
- `KERNEL32!GetLastError` at `0x18001b331`
- `KERNEL32!GetLastError` at `0x18001b2de`
- `KERNEL32!GetLastError` at `0x18001b331`
- `KERNEL32!CreateDirectoryW` at `0x18001b2ce`
- `KERNEL32!CreateDirectoryW` at `0x18001b321`
- `KERNEL32!CreateDirectoryW` at `0x18001b2ce`
- `KERNEL32!CreateDirectoryW` at `0x18001b321`
- `KERNEL32!GetFileAttributesW` at `0x18001b2b8`
- `KERNEL32!GetFileAttributesW` at `0x18001b2b8`

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
0x18001b1c0  mov     rax, rsp
0x18001b1c3  mov     [rax+10h], rbx
0x18001b1c7  mov     [rax+18h], rbp
0x18001b1cb  mov     [rax+20h], rsi
0x18001b1cf  push    rdi
0x18001b1d0  push    r12
0x18001b1d2  push    r13
0x18001b1d4  push    r14
0x18001b1d6  push    r15
0x18001b1d8  sub     rsp, 20h
0x18001b1dc  xor     r12d, r12d
0x18001b1df  mov     ebp, r8d
0x18001b1e2  mov     [rax+8], r12
0x18001b1e6  mov     r15, rdx
0x18001b1e9  test    rcx, rcx
0x18001b1ec  jnz     short loc_18001B1F8
0x18001b1ee  mov     ebx, 80070057h
0x18001b1f3  jmp     loc_18001B370
0x18001b1f8  lea     rdx, [rsp+48h+String1]
0x18001b1fd  call    WdsCreateExtendedPath
0x18001b202  mov     rsi, [rsp+48h+String1]
0x18001b207  mov     ebx, eax
0x18001b209  test    eax, eax
0x18001b20b  js      loc_18001B363
0x18001b211  mov     r8d, 7; MaxCount
0x18001b217  lea     rdx, aUnc; "\\\\?\\UNC"
0x18001b21e  mov     rcx, rsi; String1
0x18001b221  call    cs:__imp__wcsnicmp
0x18001b228  nop     dword ptr [rax+rax+00h]
0x18001b22d  mov     r13d, 5Ch ; '\'
0x18001b233  test    eax, eax
0x18001b235  jnz     short loc_18001B277
0x18001b237  lea     rax, [rsi+0Eh]
0x18001b23b  mov     edi, r12d
0x18001b23e  test    rax, rax
0x18001b241  jz      short loc_18001B267
0x18001b243  cmp     edi, 3
0x18001b246  jnb     short loc_18001B267
0x18001b248  mov     edx, r13d; Ch
0x18001b24b  mov     rcx, rax; Str
0x18001b24e  call    cs:__imp_wcschr
0x18001b255  nop     dword ptr [rax+rax+00h]
0x18001b25a  test    rax, rax
0x18001b25d  jz      short loc_18001B26D
0x18001b25f  inc     edi
0x18001b261  add     rax, 2
0x18001b265  jnz     short loc_18001B243
0x18001b267  sub     rax, 2
0x18001b26b  jmp     short loc_18001B27B
0x18001b26d  mov     ebx, 80070035h
0x18001b272  jmp     loc_18001B363
0x18001b277  lea     rax, [rsi+8]
0x18001b27b  mov     edx, r13d; Ch
0x18001b27e  mov     rcx, rax; Str
0x18001b281  call    cs:__imp_wcschr
0x18001b288  nop     dword ptr [rax+rax+00h]
0x18001b28d  test    rax, rax
0x18001b290  jz      loc_18001B31B
0x18001b296  lea     rcx, [rax+2]
0x18001b29a  jmp     short loc_18001B304
0x18001b29c  mov     r14, rdi
0x18001b29f  add     rdi, 2
0x18001b2a3  movzx   eax, word ptr [rdi]
0x18001b2a6  cmp     ax, r13w
0x18001b2aa  jz      short loc_18001B29F
0x18001b2ac  test    ax, ax
0x18001b2af  jz      short loc_18001B31B
0x18001b2b1  mov     rcx, rsi; lpFileName
0x18001b2b4  mov     [r14], r12w
0x18001b2b8  call    cs:__imp_GetFileAttributesW
0x18001b2bf  nop     dword ptr [rax+rax+00h]
0x18001b2c4  cmp     eax, 0FFFFFFFFh
0x18001b2c7  jnz     short loc_18001B2F9
0x18001b2c9  xor     edx, edx; lpSecurityAttributes
0x18001b2cb  mov     rcx, rsi; lpPathName
0x18001b2ce  call    cs:__imp_CreateDirectoryW
0x18001b2d5  nop     dword ptr [rax+rax+00h]
0x18001b2da  test    eax, eax
0x18001b2dc  jnz     short loc_18001B2FD
0x18001b2de  call    cs:__imp_GetLastError
0x18001b2e5  nop     dword ptr [rax+rax+00h]
0x18001b2ea  cmp     eax, 0B7h
0x18001b2ef  jz      short loc_18001B2FD
0x18001b2f1  test    eax, eax
0x18001b2f3  jg      short loc_18001B35A
0x18001b2f5  mov     ebx, eax
0x18001b2f7  jmp     short loc_18001B363
0x18001b2f9  test    al, 10h
0x18001b2fb  jz      short loc_18001B34F
0x18001b2fd  mov     [r14], r13w
0x18001b301  mov     rcx, rdi; Str
0x18001b304  mov     edx, r13d; Ch
0x18001b307  call    cs:__imp_wcschr
0x18001b30e  nop     dword ptr [rax+rax+00h]
0x18001b313  mov     rdi, rax
0x18001b316  test    rax, rax
0x18001b319  jnz     short loc_18001B29C
0x18001b31b  mov     rdx, r15; lpSecurityAttributes
0x18001b31e  mov     rcx, rsi; lpPathName
0x18001b321  call    cs:__imp_CreateDirectoryW
0x18001b328  nop     dword ptr [rax+rax+00h]
0x18001b32d  test    eax, eax
0x18001b32f  jnz     short loc_18001B363
0x18001b331  call    cs:__imp_GetLastError
0x18001b338  nop     dword ptr [rax+rax+00h]
0x18001b33d  mov     ebx, eax
0x18001b33f  test    ebp, ebp
0x18001b341  jz      short loc_18001B356
0x18001b343  cmp     eax, 0B7h
0x18001b348  jnz     short loc_18001B356
0x18001b34a  mov     ebx, r12d
0x18001b34d  jmp     short loc_18001B363
0x18001b34f  mov     ebx, 8007010Bh
0x18001b354  jmp     short loc_18001B363
0x18001b356  test    eax, eax
0x18001b358  jle     short loc_18001B363
0x18001b35a  movzx   ebx, ax
0x18001b35d  or      ebx, 80070000h
0x18001b363  test    rsi, rsi
0x18001b366  jz      short loc_18001B370
0x18001b368  mov     rcx, rsi; lpMem
0x18001b36b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b370  mov     rbp, [rsp+48h+arg_10]
0x18001b375  mov     eax, ebx
0x18001b377  mov     rbx, [rsp+48h+arg_8]
0x18001b37c  mov     rsi, [rsp+48h+arg_18]
0x18001b381  add     rsp, 20h
0x18001b385  pop     r15
0x18001b387  pop     r14
0x18001b389  pop     r13
0x18001b38b  pop     r12
0x18001b38d  pop     rdi
0x18001b38e  retn
```
