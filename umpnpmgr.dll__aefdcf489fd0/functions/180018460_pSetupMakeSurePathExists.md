# pSetupMakeSurePathExists

- ea: `0x180018460`
- end: `0x180018660`
- name: `pSetupMakeSurePathExists`
- size: `512`
- prototype: `DWORD __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800164e0`
- `0x180017708`

## callees

- `0x180018460`
- `0x180018970`

## import_xrefs

- `msvcrt!wcschr` at `0x180018537`
- `msvcrt!wcschr` at `0x18001854d`
- `msvcrt!wcschr` at `0x180018537`
- `msvcrt!wcschr` at `0x18001854d`
- `msvcrt!wcsrchr` at `0x1800185bc`
- `msvcrt!wcsrchr` at `0x1800185bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184bd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800184ab`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800184ab`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800185ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800185ff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018564`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800185d8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018564`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800185d8`

## pseudocode

```c
DWORD __fastcall pSetupMakeSurePathExists(const WCHAR *a1)
{
  DWORD FullPathNameW; // eax
  wchar_t *v3; // rsi
  wchar_t *v4; // rax
  DWORD FileAttributesW; // eax
  WCHAR *p_Buffer; // rdi
  wchar_t *v7; // rax
  wchar_t *v8; // r14
  wchar_t v9; // bx
  DWORD v10; // eax
  __int64 v11; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+32h] [rbp-CEh]
  wchar_t Str[262]; // [rsp+34h] [rbp-CCh] BYREF

  FilePart = 0;
  FullPathNameW = GetFullPathNameW(a1, 0x104u, &Buffer, &FilePart);
  if ( FullPathNameW >= 0x104 )
    return 123;
  if ( !FullPathNameW )
    return GetLastError();
  if ( !FilePart || FilePart == &Buffer )
    return 123;
  *FilePart = 0;
  v3 = 0;
  if ( ((unsigned __int16)(Buffer - 65) <= 0x19u || (unsigned __int16)(Buffer - 97) <= 0x19u) && v14 == 58 )
  {
    if ( Str[0] != 92 )
      return 123;
    v3 = Str;
  }
  if ( Buffer == 92 && v14 == 92 )
  {
    v4 = wcschr(Str, 0x5Cu);
    if ( !v4 )
      return 123;
    v3 = wcschr(v4 + 1, 0x5Cu);
    if ( !v3 )
      return 123;
  }
  FileAttributesW = GetFileAttributesW(&Buffer);
  if ( FileAttributesW == -1 )
  {
    if ( FilePart == &Buffer )
      p_Buffer = &Buffer;
    else
      p_Buffer = FilePart - 1;
    if ( p_Buffer != v3 && *p_Buffer == 92 )
    {
      while ( p_Buffer > v3 )
      {
        *p_Buffer = 0;
        v7 = wcsrchr(&Buffer, 0x5Cu);
        v8 = v7;
        if ( !v7 )
          break;
        v9 = v7[1];
        v7[1] = 0;
        v10 = GetFileAttributesW(&Buffer);
        v8[1] = v9;
        if ( v10 != -1 )
        {
          if ( (v10 & 0x10) == 0 )
            return 267;
          while ( CreateDirectoryW(&Buffer, 0) )
          {
            if ( !p_Buffer[1] )
              return 0;
            *p_Buffer = 92;
            v11 = -1;
            do
              ++v11;
            while ( p_Buffer[v11] );
            p_Buffer += v11;
          }
          return GetLastError();
        }
        p_Buffer = v8;
      }
    }
    return 123;
  }
  if ( (FileAttributesW & 0x10) != 0 )
    return 0;
  else
    return 267;
}

```

## disassembly

```asm
0x180018460  mov     [rsp-8+arg_8], rbx
0x180018465  mov     [rsp-8+arg_10], rsi
0x18001846a  push    rbp
0x18001846b  push    rdi
0x18001846c  push    r12
0x18001846e  push    r14
0x180018470  push    r15
0x180018472  lea     rbp, [rsp-150h]
0x18001847a  sub     rsp, 250h
0x180018481  mov     rax, cs:__security_cookie
0x180018488  xor     rax, rsp
0x18001848b  mov     [rbp+170h+var_30], rax
0x180018492  mov     ebx, 104h
0x180018497  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x18001849c  xor     r15d, r15d
0x18001849f  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x1800184a4  mov     edx, ebx; nBufferLength
0x1800184a6  mov     [rsp+270h+FilePart], r15
0x1800184ab  call    cs:__imp_GetFullPathNameW
0x1800184b1  cmp     eax, ebx
0x1800184b3  jnb     loc_180018630
0x1800184b9  test    eax, eax
0x1800184bb  jnz     short loc_1800184C8
0x1800184bd  call    cs:__imp_GetLastError
0x1800184c3  jmp     loc_180018635
0x1800184c8  mov     rcx, [rsp+270h+FilePart]
0x1800184cd  test    rcx, rcx
0x1800184d0  jz      loc_180018630
0x1800184d6  lea     rax, [rsp+270h+Buffer]
0x1800184db  cmp     rcx, rax
0x1800184de  jz      loc_180018630
0x1800184e4  mov     [rcx], r15w
0x1800184e8  mov     rsi, r15
0x1800184eb  movzx   ecx, [rsp+270h+Buffer]
0x1800184f0  mov     r12d, 5Ch ; '\'
0x1800184f6  lea     eax, [rcx-41h]
0x1800184f9  cmp     ax, 19h
0x1800184fd  jbe     short loc_180018508
0x1800184ff  lea     eax, [rcx-61h]
0x180018502  cmp     ax, 19h
0x180018506  ja      short loc_180018521
0x180018508  cmp     [rsp+270h+var_23E], 3Ah ; ':'
0x18001850e  jnz     short loc_180018521
0x180018510  cmp     [rsp+270h+Str], r12w
0x180018516  jnz     loc_180018630
0x18001851c  lea     rsi, [rsp+270h+Str]
0x180018521  cmp     cx, r12w
0x180018525  jnz     short loc_18001855F
0x180018527  cmp     [rsp+270h+var_23E], r12w
0x18001852d  jnz     short loc_18001855F
0x18001852f  mov     edx, r12d; Ch
0x180018532  lea     rcx, [rsp+270h+Str]; Str
0x180018537  call    cs:__imp_wcschr
0x18001853d  test    rax, rax
0x180018540  jz      loc_180018630
0x180018546  mov     edx, r12d; Ch
0x180018549  lea     rcx, [rax+2]; Str
0x18001854d  call    cs:__imp_wcschr
0x180018553  mov     rsi, rax
0x180018556  test    rax, rax
0x180018559  jz      loc_180018630
0x18001855f  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x180018564  call    cs:__imp_GetFileAttributesW
0x18001856a  cmp     eax, 0FFFFFFFFh
0x18001856d  jz      short loc_18001857A
0x18001856f  test    al, 10h
0x180018571  jz      short loc_1800185F1
0x180018573  xor     eax, eax
0x180018575  jmp     loc_180018635
0x18001857a  mov     rdi, [rsp+270h+FilePart]
0x18001857f  lea     rax, [rsp+270h+Buffer]
0x180018584  cmp     rdi, rax
0x180018587  jnz     short loc_180018590
0x180018589  lea     rdi, [rsp+270h+Buffer]
0x18001858e  jmp     short loc_180018594
0x180018590  add     rdi, 0FFFFFFFFFFFFFFFEh
0x180018594  cmp     rdi, rsi
0x180018597  jz      loc_180018630
0x18001859d  cmp     [rdi], r12w
0x1800185a1  jnz     loc_180018630
0x1800185a7  cmp     rdi, rsi
0x1800185aa  jbe     loc_180018630
0x1800185b0  mov     edx, r12d; Ch
0x1800185b3  mov     [rdi], r15w
0x1800185b7  lea     rcx, [rsp+270h+Buffer]; Str
0x1800185bc  call    cs:__imp_wcsrchr
0x1800185c2  mov     r14, rax
0x1800185c5  test    rax, rax
0x1800185c8  jz      short loc_180018630
0x1800185ca  movzx   ebx, word ptr [rax+2]
0x1800185ce  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x1800185d3  mov     [rax+2], r15w
0x1800185d8  call    cs:__imp_GetFileAttributesW
0x1800185de  mov     [r14+2], bx
0x1800185e3  cmp     eax, 0FFFFFFFFh
0x1800185e6  jnz     short loc_1800185ED
0x1800185e8  mov     rdi, r14
0x1800185eb  jmp     short loc_1800185A7
0x1800185ed  test    al, 10h
0x1800185ef  jnz     short loc_1800185F8
0x1800185f1  mov     eax, 10Bh
0x1800185f6  jmp     short loc_180018635
0x1800185f8  xor     edx, edx; lpSecurityAttributes
0x1800185fa  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x1800185ff  call    cs:__imp_CreateDirectoryW
0x180018605  test    eax, eax
0x180018607  jz      loc_1800184BD
0x18001860d  cmp     [rdi+2], r15w
0x180018612  jz      loc_180018573
0x180018618  mov     [rdi], r12w
0x18001861c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018620  inc     rax
0x180018623  cmp     [rdi+rax*2], r15w
0x180018628  jnz     short loc_180018620
0x18001862a  lea     rdi, [rdi+rax*2]
0x18001862e  jmp     short loc_1800185F8
0x180018630  mov     eax, 7Bh ; '{'
0x180018635  mov     rcx, [rbp+170h+var_30]
0x18001863c  xor     rcx, rsp; StackCookie
0x18001863f  call    __security_check_cookie
0x180018644  lea     r11, [rsp+270h+var_20]
0x18001864c  mov     rbx, [r11+38h]
0x180018650  mov     rsi, [r11+40h]
0x180018654  mov     rsp, r11
0x180018657  pop     r15
0x180018659  pop     r14
0x18001865b  pop     r12
0x18001865d  pop     rdi
0x18001865e  pop     rbp
0x18001865f  retn
```
