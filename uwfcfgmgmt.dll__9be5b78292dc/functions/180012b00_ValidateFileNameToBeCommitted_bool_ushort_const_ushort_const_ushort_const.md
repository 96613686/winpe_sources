# ValidateFileNameToBeCommitted(bool,ushort const *,ushort const *,ushort const *)

- ea: `0x180012b00`
- end: `0x180012c5b`
- name: `?ValidateFileNameToBeCommitted@@YA?AW4FILE_COMMIT_VALIDATE_RESULT@@_NPEBG11@Z`
- size: `347`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800151b0`

## callees

- `0x1800054d0`
- `0x180011e40`
- `0x180012130`
- `0x180012b00`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180012c06`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180012c06`

## pseudocode

```c
__int64 __fastcall ValidateFileNameToBeCommitted(__int64 a1, unsigned __int16 *a2, __int64 a3, wchar_t *a4)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned __int16 v12[2]; // [rsp+30h] [rbp-2C8h] BYREF
  wchar_t v13; // [rsp+34h] [rbp-2C4h]
  unsigned __int16 Src[56]; // [rsp+40h] [rbp-2B8h] BYREF
  WCHAR pszPath[264]; // [rsp+B0h] [rbp-248h] BYREF

  *(_DWORD *)v12 = *(_DWORD *)L"C:";
  v13 = aC[2];
  memset_0(Src, 0, 0x64u);
  memset_0(pszPath, 0, 0x208u);
  v7 = -1;
  if ( !a2 )
    goto LABEL_5;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !v8 )
  {
LABEL_5:
    if ( (int)StringCchPrintfW(Src, 0x32u, L"\\\\?\\%ws\\", a3) < 0 )
      return 2;
    a2 = v12;
    if ( (int)GetDriveLetterFromVolumeName(Src, v12) < 0 )
      a2 = (unsigned __int16 *)&qword_180021C70;
  }
  do
    ++v7;
  while ( a2[v7] );
  if ( v7 )
    v10 = StringCchPrintfW(pszPath, 0x104u, L"%ws%ws", a2, a4);
  else
    v10 = StringCchPrintfW(pszPath, 0x104u, L"\\\\?\\%ws%ws", a3, a4);
  if ( v10 < 0 )
    return 2;
  if ( PathIsDirectoryW(pszPath) )
  {
    return 3;
  }
  else
  {
    v9 = 0;
    if ( !CanFileBeCommitted(a2, a4) )
      return 4;
  }
  return v9;
}

```

## disassembly

```asm
0x180012b00  push    rbx
0x180012b02  push    rbp
0x180012b03  push    rsi
0x180012b04  push    rdi
0x180012b05  push    r14
0x180012b07  sub     rsp, 2D0h
0x180012b0e  mov     rax, cs:__security_cookie
0x180012b15  xor     rax, rsp
0x180012b18  mov     [rsp+2F8h+var_38], rax
0x180012b20  mov     eax, dword ptr cs:aC; "C:"
0x180012b26  lea     rcx, [rsp+2F8h+Src]; void *
0x180012b2b  mov     rdi, rdx
0x180012b2e  mov     dword ptr [rsp+2F8h+var_2C8], eax
0x180012b32  movzx   eax, word ptr cs:aC+4; ""
0x180012b39  xor     edx, edx; Val
0x180012b3b  mov     rbp, r8
0x180012b3e  mov     [rsp+2F8h+var_2C4], ax
0x180012b43  mov     rsi, r9
0x180012b46  lea     r8d, [rdx+64h]; Size
0x180012b4a  call    memset_0
0x180012b4f  xor     edx, edx; Val
0x180012b51  lea     rcx, [rsp+2F8h+pszPath]; void *
0x180012b59  mov     r8d, 208h; Size
0x180012b5f  call    memset_0
0x180012b64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012b68  xor     r14d, r14d
0x180012b6b  test    rdi, rdi
0x180012b6e  jz      short loc_180012B82
0x180012b70  mov     rax, rbx
0x180012b73  inc     rax
0x180012b76  cmp     [rdi+rax*2], r14w
0x180012b7b  jnz     short loc_180012B73
0x180012b7d  test    rax, rax
0x180012b80  jnz     short loc_180012BCA
0x180012b82  mov     r9, rbp
0x180012b85  lea     r8, aWs; "\\\\?\\%ws\\"
0x180012b8c  mov     edx, 32h ; '2'; unsigned __int64
0x180012b91  lea     rcx, [rsp+2F8h+Src]; unsigned __int16 *
0x180012b96  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012b9b  test    eax, eax
0x180012b9d  jns     short loc_180012BA9
0x180012b9f  mov     ebx, 2
0x180012ba4  jmp     loc_180012C3B
0x180012ba9  lea     rdx, [rsp+2F8h+var_2C8]; unsigned __int16 *
0x180012bae  lea     rcx, [rsp+2F8h+Src]; Src
0x180012bb3  call    ?GetDriveLetterFromVolumeName@@YAJPEBGPEAG@Z; GetDriveLetterFromVolumeName(ushort const *,ushort *)
0x180012bb8  test    eax, eax
0x180012bba  lea     rdi, [rsp+2F8h+var_2C8]
0x180012bbf  lea     rcx, qword_180021C70
0x180012bc6  cmovs   rdi, rcx
0x180012bca  inc     rbx
0x180012bcd  cmp     [rdi+rbx*2], r14w
0x180012bd2  jnz     short loc_180012BCA
0x180012bd4  mov     [rsp+2F8h+var_2D8], rsi
0x180012bd9  mov     edx, 104h; unsigned __int64
0x180012bde  lea     rcx, [rsp+2F8h+pszPath]; unsigned __int16 *
0x180012be6  test    rbx, rbx
0x180012be9  jz      short loc_180012C17
0x180012beb  mov     r9, rdi
0x180012bee  lea     r8, aWsWs_0; "%ws%ws"
0x180012bf5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012bfa  test    eax, eax
0x180012bfc  js      short loc_180012B9F
0x180012bfe  lea     rcx, [rsp+2F8h+pszPath]; pszPath
0x180012c06  call    cs:__imp_PathIsDirectoryW
0x180012c0c  test    eax, eax
0x180012c0e  jz      short loc_180012C23
0x180012c10  mov     ebx, 3
0x180012c15  jmp     short loc_180012C3B
0x180012c17  mov     r9, rbp
0x180012c1a  lea     r8, aWsWs; "\\\\?\\%ws%ws"
0x180012c21  jmp     short loc_180012BF5
0x180012c23  mov     rdx, rsi; wchar_t *
0x180012c26  mov     rcx, rdi; String1
0x180012c29  mov     ebx, r14d
0x180012c2c  call    ?CanFileBeCommitted@@YA_NPEBG0@Z; CanFileBeCommitted(ushort const *,ushort const *)
0x180012c31  test    al, al
0x180012c33  mov     ecx, 4
0x180012c38  cmovz   ebx, ecx
0x180012c3b  mov     eax, ebx
0x180012c3d  mov     rcx, [rsp+2F8h+var_38]
0x180012c45  xor     rcx, rsp; StackCookie
0x180012c48  call    __security_check_cookie
0x180012c4d  add     rsp, 2D0h
0x180012c54  pop     r14
0x180012c56  pop     rdi
0x180012c57  pop     rsi
0x180012c58  pop     rbp
0x180012c59  pop     rbx
0x180012c5a  retn
```
