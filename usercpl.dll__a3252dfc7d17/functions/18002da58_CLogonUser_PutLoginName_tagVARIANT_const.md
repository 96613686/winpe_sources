# CLogonUser::_PutLoginName(tagVARIANT const &)

- ea: `0x18002da58`
- end: `0x18002dcd7`
- name: `?_PutLoginName@CLogonUser@@AEAAJAEBUtagVARIANT@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(CLogonUser *__hidden this, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18002f560`

## callees

- `0x180006df4`
- `0x18002d5a8`
- `0x18002da58`
- `0x1800772c0`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x18002db98`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18002db98`
- `SHLWAPI!PathAppendW` at `0x18002dbb0`
- `SHLWAPI!PathAppendW` at `0x18002dbb0`
- `SHLWAPI!PathFindExtensionW` at `0x18002dbc1`
- `SHLWAPI!PathFindExtensionW` at `0x18002dbc1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002dc49`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002dc49`
- `samcli!NetUserSetInfo` at `0x18002db00`
- `samcli!NetUserSetInfo` at `0x18002db00`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002dbe9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002dbe9`

## pseudocode

```c
signed int __fastcall CLogonUser::_PutLoginName(CLogonUser *this, const struct tagVARIANT *a2)
{
  BSTR bstrVal; // rax
  _WORD *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  signed int result; // eax
  unsigned __int16 *v8; // r14
  __int64 v9; // rdi
  const WCHAR *v10; // rsi
  WCHAR *v11; // rax
  const WCHAR *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  WCHAR *v15; // rcx
  const unsigned __int16 *ExtensionW; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // r8
  __int64 v19; // r9
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r8
  LPCWSTR v22; // rax
  _WORD *v23; // rcx
  BYTE buf[8]; // [rsp+30h] [rbp-268h] BYREF
  WCHAR pszPath[272]; // [rsp+40h] [rbp-258h] BYREF

  if ( a2->vt != 8 )
    return -2147024809;
  bstrVal = a2->bstrVal;
  if ( !bstrVal || !*bstrVal )
    return -2147024809;
  v4 = (_WORD *)((char *)this + 12);
  if ( !*((_WORD *)this + 6) )
  {
    v5 = 2147483646;
    v6 = 257;
    do
    {
      if ( !v5 )
        break;
      if ( !*bstrVal )
        break;
      *v4++ = *bstrVal++;
      --v5;
      --v6;
    }
    while ( v6 );
LABEL_37:
    v23 = v4 - 1;
    if ( v6 )
      v23 = v4;
    result = v6 == 0 ? 0x8007007A : 0;
    *v23 = 0;
    return result;
  }
  *(_QWORD *)buf = a2->llVal;
  result = NetUserSetInfo(0, (LPCWSTR)this + 6, 0, buf, 0);
  if ( !result )
  {
    v8 = (unsigned __int16 *)((char *)this + 2080);
    v9 = 2147483646;
    if ( (*((_WORD *)this + 1040) != 0xFFFF || (int)CLogonUser::_InitPicture(this) >= 0) && *v8 )
    {
      v10 = (const WCHAR *)((char *)this + 2094);
      v11 = pszPath;
      v12 = v10;
      v13 = 267;
      v14 = 2147483646;
      do
      {
        if ( !v14 )
          break;
        if ( !*v12 )
          break;
        *v11++ = *v12++;
        --v14;
        --v13;
      }
      while ( v13 );
      v15 = v11 - 1;
      if ( v13 )
        v15 = v11;
      *v15 = 0;
      if ( v13 )
      {
        if ( PathRemoveFileSpecW(pszPath) )
        {
          if ( PathAppendW(pszPath, *(LPCWSTR *)buf) )
          {
            ExtensionW = PathFindExtensionW(v10);
            if ( (int)StringCchCatW(pszPath, 0x10Bu, ExtensionW) >= 0 )
            {
              if ( MoveFileExW(v10, pszPath, 1u) )
              {
                v17 = 2147483646;
                v18 = L"file://";
                v19 = 267;
                v20 = v8;
                do
                {
                  if ( !v17 )
                    break;
                  if ( !*v18 )
                    break;
                  *v20++ = *v18++;
                  --v17;
                  --v19;
                }
                while ( v19 );
                v21 = v20 - 1;
                if ( v19 )
                  v21 = v20;
                *v21 = 0;
                StringCchCatW(v8, 0x10Bu, pszPath);
              }
              else
              {
                DeleteFileW(v10);
                *v8 = -1;
              }
            }
          }
        }
      }
    }
    v22 = *(LPCWSTR *)buf;
    v6 = 257;
    do
    {
      if ( !v9 )
        break;
      if ( !*v22 )
        break;
      *v4++ = *v22++;
      --v9;
      --v6;
    }
    while ( v6 );
    goto LABEL_37;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002da58  mov     [rsp+arg_10], rbx
0x18002da5d  mov     [rsp+arg_18], rbp
0x18002da62  push    rsi
0x18002da63  push    rdi
0x18002da64  push    r12
0x18002da66  push    r14
0x18002da68  push    r15
0x18002da6a  sub     rsp, 270h
0x18002da71  mov     rax, cs:__security_cookie
0x18002da78  xor     rax, rsp
0x18002da7b  mov     [rsp+298h+var_38], rax
0x18002da83  cmp     word ptr [rdx], 8
0x18002da87  mov     rsi, rcx
0x18002da8a  jnz     loc_18002DCA6
0x18002da90  mov     rax, [rdx+8]
0x18002da94  xor     ebp, ebp
0x18002da96  test    rax, rax
0x18002da99  jz      loc_18002DCA6
0x18002da9f  cmp     [rax], bp
0x18002daa2  jz      loc_18002DCA6
0x18002daa8  lea     rbx, [rcx+0Ch]
0x18002daac  cmp     [rbx], bp
0x18002daaf  jnz     short loc_18002DAE9
0x18002dab1  mov     edi, 7FFFFFFEh
0x18002dab6  mov     edx, 101h
0x18002dabb  test    rdi, rdi
0x18002dabe  jz      loc_18002DC7E
0x18002dac4  movzx   ecx, word ptr [rax]
0x18002dac7  test    cx, cx
0x18002daca  jz      loc_18002DC7E
0x18002dad0  mov     [rbx], cx
0x18002dad3  add     rax, 2
0x18002dad7  add     rbx, 2
0x18002dadb  dec     rdi
0x18002dade  sub     rdx, 1
0x18002dae2  jnz     short loc_18002DABB
0x18002dae4  jmp     loc_18002DC7E
0x18002dae9  lea     r9, [rsp+298h+buf]; buf
0x18002daee  mov     qword ptr [rsp+298h+buf], rax
0x18002daf3  xor     r8d, r8d; level
0x18002daf6  mov     [rsp+298h+parm_err], rbp; parm_err
0x18002dafb  mov     rdx, rbx; username
0x18002dafe  xor     ecx, ecx; servername
0x18002db00  call    cs:__imp_NetUserSetInfo
0x18002db06  test    eax, eax
0x18002db08  jnz     loc_18002DC9A
0x18002db0e  lea     r14, [rsi+820h]
0x18002db15  mov     r12d, 0FFFFh
0x18002db1b  mov     edi, 7FFFFFFEh
0x18002db20  cmp     r12w, [r14]
0x18002db24  jnz     short loc_18002DB36
0x18002db26  mov     rcx, rsi; this
0x18002db29  call    ?_InitPicture@CLogonUser@@AEAAJXZ; CLogonUser::_InitPicture(void)
0x18002db2e  test    eax, eax
0x18002db30  js      loc_18002DC53
0x18002db36  cmp     [r14], bp
0x18002db3a  jz      loc_18002DC53
0x18002db40  add     rsi, 82Eh
0x18002db47  lea     rax, [rsp+298h+pszPath]
0x18002db4c  mov     r15d, 10Bh
0x18002db52  mov     r8, rsi
0x18002db55  mov     edx, r15d
0x18002db58  mov     rcx, rdi
0x18002db5b  test    rcx, rcx
0x18002db5e  jz      short loc_18002DB7F
0x18002db60  movzx   r9d, word ptr [r8]
0x18002db64  test    r9w, r9w
0x18002db68  jz      short loc_18002DB7F
0x18002db6a  mov     [rax], r9w
0x18002db6e  add     r8, 2
0x18002db72  add     rax, 2
0x18002db76  dec     rcx
0x18002db79  sub     rdx, 1
0x18002db7d  jnz     short loc_18002DB5B
0x18002db7f  test    rdx, rdx
0x18002db82  lea     rcx, [rax-2]
0x18002db86  cmovnz  rcx, rax
0x18002db8a  mov     [rcx], bp
0x18002db8d  jz      loc_18002DC53
0x18002db93  lea     rcx, [rsp+298h+pszPath]; pszPath
0x18002db98  call    cs:__imp_PathRemoveFileSpecW
0x18002db9e  test    eax, eax
0x18002dba0  jz      loc_18002DC53
0x18002dba6  mov     rdx, qword ptr [rsp+298h+buf]; pszMore
0x18002dbab  lea     rcx, [rsp+298h+pszPath]; pszPath
0x18002dbb0  call    cs:__imp_PathAppendW
0x18002dbb6  test    eax, eax
0x18002dbb8  jz      loc_18002DC53
0x18002dbbe  mov     rcx, rsi; pszPath
0x18002dbc1  call    cs:__imp_PathFindExtensionW
0x18002dbc7  mov     rdx, r15; unsigned __int64
0x18002dbca  lea     rcx, [rsp+298h+pszPath]; unsigned __int16 *
0x18002dbcf  mov     r8, rax; unsigned __int16 *
0x18002dbd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dbd7  test    eax, eax
0x18002dbd9  js      short loc_18002DC53
0x18002dbdb  mov     r8d, 1; dwFlags
0x18002dbe1  lea     rdx, [rsp+298h+pszPath]; lpNewFileName
0x18002dbe6  mov     rcx, rsi; lpExistingFileName
0x18002dbe9  call    cs:__imp_MoveFileExW
0x18002dbef  test    eax, eax
0x18002dbf1  jz      short loc_18002DC46
0x18002dbf3  mov     rcx, rdi
0x18002dbf6  lea     r8, aFile; "file://"
0x18002dbfd  mov     r9, r15
0x18002dc00  mov     rax, r14
0x18002dc03  test    rcx, rcx
0x18002dc06  jz      short loc_18002DC25
0x18002dc08  movzx   edx, word ptr [r8]
0x18002dc0c  test    dx, dx
0x18002dc0f  jz      short loc_18002DC25
0x18002dc11  mov     [rax], dx
0x18002dc14  add     r8, 2
0x18002dc18  add     rax, 2
0x18002dc1c  dec     rcx
0x18002dc1f  sub     r9, 1
0x18002dc23  jnz     short loc_18002DC03
0x18002dc25  test    r9, r9
0x18002dc28  lea     r8, [rax-2]
0x18002dc2c  mov     rdx, r15; unsigned __int64
0x18002dc2f  mov     rcx, r14; unsigned __int16 *
0x18002dc32  cmovnz  r8, rax
0x18002dc36  mov     [r8], bp
0x18002dc3a  lea     r8, [rsp+298h+pszPath]; unsigned __int16 *
0x18002dc3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dc44  jmp     short loc_18002DC53
0x18002dc46  mov     rcx, rsi; lpFileName
0x18002dc49  call    cs:__imp_DeleteFileW
0x18002dc4f  mov     [r14], r12w
0x18002dc53  mov     rax, qword ptr [rsp+298h+buf]
0x18002dc58  mov     edx, 101h
0x18002dc5d  test    rdi, rdi
0x18002dc60  jz      short loc_18002DC7E
0x18002dc62  movzx   ecx, word ptr [rax]
0x18002dc65  test    cx, cx
0x18002dc68  jz      short loc_18002DC7E
0x18002dc6a  mov     [rbx], cx
0x18002dc6d  add     rax, 2
0x18002dc71  add     rbx, 2
0x18002dc75  dec     rdi
0x18002dc78  sub     rdx, 1
0x18002dc7c  jnz     short loc_18002DC5D
0x18002dc7e  test    rdx, rdx
0x18002dc81  lea     rcx, [rbx-2]
0x18002dc85  cmovnz  rcx, rbx
0x18002dc89  neg     rdx
0x18002dc8c  sbb     eax, eax
0x18002dc8e  not     eax
0x18002dc90  and     eax, 8007007Ah
0x18002dc95  mov     [rcx], bp
0x18002dc98  jmp     short loc_18002DCAB
0x18002dc9a  jle     short loc_18002DCAB
0x18002dc9c  movzx   eax, ax
0x18002dc9f  or      eax, 80070000h
0x18002dca4  jmp     short loc_18002DCAB
0x18002dca6  mov     eax, 80070057h
0x18002dcab  mov     rcx, [rsp+298h+var_38]
0x18002dcb3  xor     rcx, rsp; StackCookie
0x18002dcb6  call    __security_check_cookie
0x18002dcbb  lea     r11, [rsp+298h+var_28]
0x18002dcc3  mov     rbx, [r11+40h]
0x18002dcc7  mov     rbp, [r11+48h]
0x18002dccb  mov     rsp, r11
0x18002dcce  pop     r15
0x18002dcd0  pop     r14
0x18002dcd2  pop     r12
0x18002dcd4  pop     rdi
0x18002dcd5  pop     rsi
0x18002dcd6  retn
```
