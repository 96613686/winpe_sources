# CheckValidDriveType

- ea: `0x18000e970`
- end: `0x18000eab3`
- name: `CheckValidDriveType`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000eba0`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000e970`
- `0x1800425cc`
- `0x1800425e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000e9fa`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000e9fa`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000ea23`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000ea23`

## pseudocode

```c
__int64 __fastcall CheckValidDriveType(LPCWSTR lpszFileName, int a2, int a3)
{
  unsigned int LastError; // edi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  DWORD v10; // r15d
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  const char *v13; // r9
  UINT DriveTypeW; // eax
  UINT v15; // eax
  UINT v16; // eax
  UINT v17; // eax
  __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LastError = 0;
  if ( lpszFileName )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpszFileName[v9] );
    v10 = v9 + 1;
    v11 = (WCHAR *)o_malloc_0(saturated_mul((int)v9 + 1, 2u));
    v12 = v11;
    if ( !v11 )
    {
      v7 = -2147024882;
      v8 = 302;
      goto LABEL_3;
    }
    if ( !GetVolumePathNameW(lpszFileName, v11, v10) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x133,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
                    v13);
LABEL_10:
      v7 = LastError;
LABEL_22:
      free(v12);
      return v7;
    }
    DriveTypeW = GetDriveTypeW(v12);
    if ( DriveTypeW )
    {
      v15 = DriveTypeW - 2;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( !v16 )
          goto LABEL_10;
        v17 = v16 - 1;
        if ( !v17 )
        {
          v7 = a2 == 0 ? 0x80070005 : 0;
          if ( a2 )
            goto LABEL_22;
          v18 = 328;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
            (const char *)v7,
            v20);
          goto LABEL_22;
        }
        if ( v17 - 1 >= 2 )
        {
          v7 = -2147024809;
          v18 = 331;
          goto LABEL_21;
        }
      }
    }
    v7 = a3 == 0 ? 0x80070005 : 0;
    if ( a3 )
      goto LABEL_22;
    v18 = 325;
    goto LABEL_21;
  }
  v7 = -2147024809;
  v8 = 298;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
    (const char *)v7,
    v20);
  return v7;
}

```

## disassembly

```asm
0x18000e970  mov     [rsp+arg_18], rbx
0x18000e975  push    rbp
0x18000e976  push    rsi
0x18000e977  push    rdi
0x18000e978  push    r14
0x18000e97a  push    r15; int
0x18000e97c  sub     rsp, 20h
0x18000e980  xor     edi, edi
0x18000e982  mov     r14d, r8d
0x18000e985  mov     ebp, edx
0x18000e987  mov     rbx, rcx
0x18000e98a  test    rcx, rcx
0x18000e98d  jnz     short loc_18000E9B2
0x18000e98f  mov     ebx, 80070057h
0x18000e994  mov     edx, 12Ah; void *
0x18000e999  mov     rcx, [rsp+48h]; this
0x18000e99e  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000e9a5  mov     r9d, ebx; char *
0x18000e9a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9ad  jmp     loc_18000EAA0
0x18000e9b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e9b6  mov     rax, r8
0x18000e9b9  inc     rax
0x18000e9bc  cmp     [rcx+rax*2], di
0x18000e9c0  jnz     short loc_18000E9B9
0x18000e9c2  lea     r15d, [rax+1]
0x18000e9c6  mov     eax, 2
0x18000e9cb  movsxd  rcx, r15d
0x18000e9ce  mul     rcx
0x18000e9d1  cmovb   rax, r8
0x18000e9d5  mov     rcx, rax; Size
0x18000e9d8  call    _o_malloc_0
0x18000e9dd  mov     rsi, rax
0x18000e9e0  test    rax, rax
0x18000e9e3  jnz     short loc_18000E9F1
0x18000e9e5  mov     ebx, 8007000Eh
0x18000e9ea  mov     edx, 12Eh
0x18000e9ef  jmp     short loc_18000E999
0x18000e9f1  mov     r8d, r15d; cchBufferLength
0x18000e9f4  mov     rdx, rsi; lpszVolumePathName
0x18000e9f7  mov     rcx, rbx; lpszFileName
0x18000e9fa  call    cs:__imp_GetVolumePathNameW
0x18000ea00  test    eax, eax
0x18000ea02  jnz     short loc_18000EA20
0x18000ea04  mov     rcx, [rsp+48h]; this
0x18000ea09  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000ea10  mov     edx, 133h; void *
0x18000ea15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ea1a  mov     edi, eax
0x18000ea1c  mov     ebx, edi
0x18000ea1e  jmp     short loc_18000EA98
0x18000ea20  mov     rcx, rsi; lpRootPathName
0x18000ea23  call    cs:__imp_GetDriveTypeW
0x18000ea29  test    eax, eax
0x18000ea2b  jz      short loc_18000EA6B
0x18000ea2d  sub     eax, 2
0x18000ea30  jz      short loc_18000EA6B
0x18000ea32  sub     eax, 1
0x18000ea35  jz      short loc_18000EA1C
0x18000ea37  sub     eax, 1
0x18000ea3a  jz      short loc_18000EA52
0x18000ea3c  sub     eax, 1
0x18000ea3f  jz      short loc_18000EA6B
0x18000ea41  cmp     eax, 1
0x18000ea44  jz      short loc_18000EA6B
0x18000ea46  mov     ebx, 80070057h
0x18000ea4b  mov     edx, 14Bh
0x18000ea50  jmp     short loc_18000EA84
0x18000ea52  mov     eax, ebp
0x18000ea54  neg     eax
0x18000ea56  sbb     ebx, ebx
0x18000ea58  not     ebx
0x18000ea5a  and     ebx, 80070005h
0x18000ea60  test    ebp, ebp
0x18000ea62  jnz     short loc_18000EA98
0x18000ea64  mov     edx, 148h
0x18000ea69  jmp     short loc_18000EA84
0x18000ea6b  mov     eax, r14d
0x18000ea6e  neg     eax
0x18000ea70  sbb     ebx, ebx
0x18000ea72  not     ebx
0x18000ea74  and     ebx, 80070005h
0x18000ea7a  test    r14d, r14d
0x18000ea7d  jnz     short loc_18000EA98
0x18000ea7f  mov     edx, 145h; void *
0x18000ea84  mov     rcx, [rsp+48h]; this
0x18000ea89  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000ea90  mov     r9d, ebx; char *
0x18000ea93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea98  mov     rcx, rsi; Block
0x18000ea9b  call    free
0x18000eaa0  mov     eax, ebx
0x18000eaa2  mov     rbx, [rsp+48h+arg_18]
0x18000eaa7  add     rsp, 20h
0x18000eaab  pop     r15
0x18000eaad  pop     r14
0x18000eaaf  pop     rdi
0x18000eab0  pop     rsi
0x18000eab1  pop     rbp
0x18000eab2  retn
```
