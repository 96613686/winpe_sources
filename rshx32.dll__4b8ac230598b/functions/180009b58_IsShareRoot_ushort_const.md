# IsShareRoot(ushort const *)

- ea: `0x180009b58`
- end: `0x180009c61`
- name: `?IsShareRoot@@YAHPEBG@Z`
- size: `265`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009148`

## callees

- `0x180009b58`
- `0x18001d370`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x180009bef`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180009bef`
- `SHLWAPI!PathIsRootW` at `0x180009c29`
- `SHLWAPI!PathIsRootW` at `0x180009c29`
- `SHLWAPI!PathIsUNCServerShareW` at `0x180009b86`
- `SHLWAPI!PathIsUNCServerShareW` at `0x180009b86`
- `SHLWAPI!PathFindFileNameW` at `0x180009b97`
- `SHLWAPI!PathFindFileNameW` at `0x180009b97`
- `netutils!NetApiBufferFree` at `0x180009c3d`
- `netutils!NetApiBufferFree` at `0x180009c3d`
- `srvcli!NetShareGetInfo` at `0x180009c11`
- `srvcli!NetShareGetInfo` at `0x180009c11`

## pseudocode

```c
__int64 __fastcall IsShareRoot(LPCWSTR pszPath)
{
  const WCHAR *v1; // rbx
  unsigned int v2; // edi
  WCHAR *FileNameW; // rsi
  __int64 v4; // rcx
  WCHAR *v5; // r9
  __int64 v6; // rdx
  WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  LPBYTE bufptr; // [rsp+20h] [rbp-258h] BYREF
  WCHAR pszPatha[264]; // [rsp+30h] [rbp-248h] BYREF

  v1 = pszPath;
  v2 = 0;
  if ( pszPath )
  {
    if ( PathIsUNCServerShareW(pszPath) )
    {
      FileNameW = PathFindFileNameW(v1);
      if ( FileNameW )
      {
        v4 = 2147483646;
        v5 = pszPatha;
        v6 = 260;
        do
        {
          if ( !v4 )
            break;
          if ( !*v1 )
            break;
          *v5++ = *v1++;
          --v4;
          --v6;
        }
        while ( v6 );
        v7 = v5 - 1;
        if ( v6 )
          v7 = v5;
        *v7 = 0;
        if ( v6 )
        {
          if ( PathRemoveFileSpecW(pszPatha) )
          {
            bufptr = 0;
            if ( !NetShareGetInfo(pszPatha, FileNameW, 2u, &bufptr) )
            {
              v8 = (const WCHAR *)*((_QWORD *)bufptr + 5);
              if ( v8 && PathIsRootW(v8) )
                v2 = 1;
              NetApiBufferFree(bufptr);
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180009b58  push    rbx
0x180009b5a  push    rbp
0x180009b5b  push    rsi
0x180009b5c  push    rdi
0x180009b5d  sub     rsp, 258h
0x180009b64  mov     rax, cs:__security_cookie
0x180009b6b  xor     rax, rsp
0x180009b6e  mov     [rsp+278h+var_38], rax
0x180009b76  xor     ebp, ebp
0x180009b78  mov     rbx, rcx
0x180009b7b  mov     edi, ebp
0x180009b7d  test    rcx, rcx
0x180009b80  jz      loc_180009C43
0x180009b86  call    cs:__imp_PathIsUNCServerShareW
0x180009b8c  test    eax, eax
0x180009b8e  jz      loc_180009C43
0x180009b94  mov     rcx, rbx; pszPath
0x180009b97  call    cs:__imp_PathFindFileNameW
0x180009b9d  mov     rsi, rax
0x180009ba0  test    rax, rax
0x180009ba3  jz      loc_180009C43
0x180009ba9  mov     ecx, 7FFFFFFEh
0x180009bae  lea     r9, [rsp+278h+pszPath]
0x180009bb3  mov     edx, 104h
0x180009bb8  test    rcx, rcx
0x180009bbb  jz      short loc_180009BDA
0x180009bbd  movzx   eax, word ptr [rbx]
0x180009bc0  test    ax, ax
0x180009bc3  jz      short loc_180009BDA
0x180009bc5  mov     [r9], ax
0x180009bc9  add     rbx, 2
0x180009bcd  add     r9, 2
0x180009bd1  dec     rcx
0x180009bd4  sub     rdx, 1
0x180009bd8  jnz     short loc_180009BB8
0x180009bda  test    rdx, rdx
0x180009bdd  lea     rcx, [r9-2]
0x180009be1  cmovnz  rcx, r9
0x180009be5  mov     [rcx], bp
0x180009be8  jz      short loc_180009C43
0x180009bea  lea     rcx, [rsp+278h+pszPath]; pszPath
0x180009bef  call    cs:__imp_PathRemoveFileSpecW
0x180009bf5  test    eax, eax
0x180009bf7  jz      short loc_180009C43
0x180009bf9  lea     r9, [rsp+278h+bufptr]; bufptr
0x180009bfe  mov     [rsp+278h+bufptr], rbp
0x180009c03  mov     r8d, 2; level
0x180009c09  lea     rcx, [rsp+278h+pszPath]; servername
0x180009c0e  mov     rdx, rsi; netname
0x180009c11  call    cs:__imp_NetShareGetInfo
0x180009c17  test    eax, eax
0x180009c19  jnz     short loc_180009C43
0x180009c1b  mov     rax, [rsp+278h+bufptr]
0x180009c20  mov     rcx, [rax+28h]; pszPath
0x180009c24  test    rcx, rcx
0x180009c27  jz      short loc_180009C38
0x180009c29  call    cs:__imp_PathIsRootW
0x180009c2f  test    eax, eax
0x180009c31  jz      short loc_180009C38
0x180009c33  mov     edi, 1
0x180009c38  mov     rcx, [rsp+278h+bufptr]; Buffer
0x180009c3d  call    cs:__imp_NetApiBufferFree
0x180009c43  mov     eax, edi
0x180009c45  mov     rcx, [rsp+278h+var_38]
0x180009c4d  xor     rcx, rsp; StackCookie
0x180009c50  call    __security_check_cookie
0x180009c55  add     rsp, 258h
0x180009c5c  pop     rdi
0x180009c5d  pop     rsi
0x180009c5e  pop     rbp
0x180009c5f  pop     rbx
0x180009c60  retn
```
