# XEDefaultPathRemoveFileSpec(wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x1005e6d00`
- end: `0x1005e6e0c`
- name: `?XEDefaultPathRemoveFileSpec@@YAHPEB_WPEA_W_K@Z`
- size: `268`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10042d580`
- `0x1005e6d00`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1005e6d42`
- `SHLWAPI!PathFindFileNameW` at `0x1005e6d42`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1005e6ded`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1005e6ded`
- `SHLWAPI!PathIsURLW` at `0x1005e6d31`
- `SHLWAPI!PathIsURLW` at `0x1005e6d31`

## pseudocode

```c
BOOL __fastcall XEDefaultPathRemoveFileSpec(const wchar_t *a1, wchar_t *a2, unsigned __int64 a3)
{
  WCHAR *v4; // rbx
  const wchar_t *FileNameW; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v9; // rdx
  char *v10; // rsi
  WCHAR v11; // ax
  WCHAR *v12; // rax
  int v13; // eax

  v4 = a2;
  if ( !a1 || !a2 )
    return 0;
  if ( !PathIsURLW(a1) )
  {
    if ( (int)StringCchCopyW(v4, a3, a1) >= 0 )
    {
      _mm_lfence();
      return PathRemoveFileSpecW(v4);
    }
    return 0;
  }
  FileNameW = PathFindFileNameW(a1);
  if ( FileNameW == a1 )
    return 0;
  v7 = FileNameW - a1;
  if ( a3 - 1 > 0x7FFFFFFE )
  {
    if ( a3 )
      *v4 = 0;
    return 0;
  }
  else if ( v7 <= 0x7FFFFFFE )
  {
    v9 = v7 - a3;
    v10 = (char *)((char *)a1 - (char *)v4);
    do
    {
      if ( !(v9 + a3) )
        break;
      v11 = *(WCHAR *)((char *)v4 + (_QWORD)v10);
      if ( !v11 )
        break;
      *v4++ = v11;
      --a3;
    }
    while ( a3 );
    v12 = v4 - 1;
    if ( a3 )
      v12 = v4;
    *v12 = 0;
    v13 = -2147024774;
    if ( a3 )
      v13 = 0;
    return v13 >= 0;
  }
  else
  {
    *v4 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1005e6d00  mov     [rsp+arg_0], rbx
0x1005e6d05  mov     [rsp+arg_8], rbp
0x1005e6d0a  mov     [rsp+arg_10], rsi
0x1005e6d0f  push    rdi
0x1005e6d10  sub     rsp, 20h
0x1005e6d14  xor     ebp, ebp
0x1005e6d16  mov     rdi, r8
0x1005e6d19  mov     rbx, rdx
0x1005e6d1c  mov     rsi, rcx
0x1005e6d1f  test    rcx, rcx
0x1005e6d22  jz      loc_1005E6DF5
0x1005e6d28  test    rdx, rdx
0x1005e6d2b  jz      loc_1005E6DF5
0x1005e6d31  call    cs:__imp_PathIsURLW
0x1005e6d37  test    eax, eax
0x1005e6d39  jz      loc_1005E6DD5
0x1005e6d3f  mov     rcx, rsi; pszPath
0x1005e6d42  call    cs:__imp_PathFindFileNameW
0x1005e6d48  mov     rdx, rax
0x1005e6d4b  cmp     rax, rsi
0x1005e6d4e  jz      loc_1005E6DF5
0x1005e6d54  sub     rdx, rsi
0x1005e6d57  lea     rcx, [rdi-1]
0x1005e6d5b  sar     rdx, 1
0x1005e6d5e  cmp     rcx, 7FFFFFFEh
0x1005e6d65  ja      short loc_1005E6DC1
0x1005e6d67  cmp     rdx, 7FFFFFFEh
0x1005e6d6e  jbe     short loc_1005E6D7F
0x1005e6d70  mov     eax, 80070057h
0x1005e6d75  mov     [rbx], bp
0x1005e6d78  not     eax
0x1005e6d7a  shr     eax, 1Fh
0x1005e6d7d  jmp     short loc_1005E6DF7
0x1005e6d7f  sub     rdx, rdi
0x1005e6d82  sub     rsi, rbx
0x1005e6d85  lea     rax, [rdx+rdi]
0x1005e6d89  test    rax, rax
0x1005e6d8c  jz      short loc_1005E6DA4
0x1005e6d8e  movzx   eax, word ptr [rsi+rbx]
0x1005e6d92  test    ax, ax
0x1005e6d95  jz      short loc_1005E6DA4
0x1005e6d97  mov     [rbx], ax
0x1005e6d9a  add     rbx, 2
0x1005e6d9e  sub     rdi, 1
0x1005e6da2  jnz     short loc_1005E6D85
0x1005e6da4  test    rdi, rdi
0x1005e6da7  lea     rax, [rbx-2]
0x1005e6dab  cmovnz  rax, rbx
0x1005e6daf  mov     [rax], bp
0x1005e6db2  mov     eax, 8007007Ah
0x1005e6db7  cmovnz  eax, ebp
0x1005e6dba  not     eax
0x1005e6dbc  shr     eax, 1Fh
0x1005e6dbf  jmp     short loc_1005E6DF7
0x1005e6dc1  mov     eax, 80070057h
0x1005e6dc6  test    rdi, rdi
0x1005e6dc9  jz      short loc_1005E6DCE
0x1005e6dcb  mov     [rbx], bp
0x1005e6dce  not     eax
0x1005e6dd0  shr     eax, 1Fh
0x1005e6dd3  jmp     short loc_1005E6DF7
0x1005e6dd5  mov     r8, rsi; wchar_t *
0x1005e6dd8  mov     rdx, rdi; unsigned __int64
0x1005e6ddb  mov     rcx, rbx; wchar_t *
0x1005e6dde  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1005e6de3  test    eax, eax
0x1005e6de5  js      short loc_1005E6DF5
0x1005e6de7  lfence
0x1005e6dea  mov     rcx, rbx; pszPath
0x1005e6ded  call    cs:__imp_PathRemoveFileSpecW
0x1005e6df3  jmp     short loc_1005E6DF7
0x1005e6df5  mov     eax, ebp
0x1005e6df7  mov     rbx, [rsp+28h+arg_0]
0x1005e6dfc  mov     rbp, [rsp+28h+arg_8]
0x1005e6e01  mov     rsi, [rsp+28h+arg_10]
0x1005e6e06  add     rsp, 20h
0x1005e6e0a  pop     rdi
0x1005e6e0b  retn
```
