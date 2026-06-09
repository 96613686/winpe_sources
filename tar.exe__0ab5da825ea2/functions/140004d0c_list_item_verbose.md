# list_item_verbose

- ea: `0x140004d0c`
- end: `0x14000508b`
- name: `list_item_verbose`
- size: `895`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x14000422c`
- `0x14000583c`
- `0x140006db0`
- `0x140006ea4`

## callees

- `0x140001340`
- `0x140001d10`
- `0x140001e14`
- `0x140001e7c`
- `0x140004d0c`
- `0x1400050fc`
- `0x14000561c`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x140004d83`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x140004d83`
- `api-ms-win-crt-private-l1-1-0!_o__localtime64_s` at `0x140004fbc`
- `api-ms-win-crt-private-l1-1-0!_o__localtime64_s` at `0x140004fbc`
- `api-ms-win-crt-private-l1-1-0!_o_strftime` at `0x140004fde`
- `api-ms-win-crt-private-l1-1-0!_o_strftime` at `0x140004fde`
- `archiveint!archive_entry_size` at `0x140004ecb`
- `archiveint!archive_entry_size` at `0x140004ecb`
- `archiveint!archive_entry_pathname` at `0x14000500f`
- `archiveint!archive_entry_pathname` at `0x14000500f`
- `archiveint!archive_entry_rdevmajor` at `0x140004efb`
- `archiveint!archive_entry_rdevmajor` at `0x140004efb`
- `archiveint!archive_entry_hardlink` at `0x14000502a`
- `archiveint!archive_entry_hardlink` at `0x140005038`
- `archiveint!archive_entry_hardlink` at `0x14000502a`
- `archiveint!archive_entry_hardlink` at `0x140005038`
- `archiveint!archive_entry_mtime` at `0x140004f62`
- `archiveint!archive_entry_mtime` at `0x140004f62`
- `archiveint!archive_entry_symlink` at `0x140005047`
- `archiveint!archive_entry_symlink` at `0x140005055`
- `archiveint!archive_entry_symlink` at `0x140005047`
- `archiveint!archive_entry_symlink` at `0x140005055`
- `archiveint!archive_entry_filetype` at `0x140004ea5`
- `archiveint!archive_entry_filetype` at `0x140004eb8`
- `archiveint!archive_entry_filetype` at `0x140004ea5`
- `archiveint!archive_entry_filetype` at `0x140004eb8`
- `archiveint!archive_entry_nlink` at `0x140004d8c`
- `archiveint!archive_entry_nlink` at `0x140004d8c`
- `archiveint!archive_entry_gid` at `0x140004e62`
- `archiveint!archive_entry_gid` at `0x140004e62`
- `archiveint!archive_entry_uname` at `0x140004db5`
- `archiveint!archive_entry_uname` at `0x140004db5`
- `archiveint!archive_entry_rdevminor` at `0x140004ef0`
- `archiveint!archive_entry_rdevminor` at `0x140004ef0`
- `archiveint!archive_entry_uid` at `0x140004dd1`
- `archiveint!archive_entry_uid` at `0x140004dd1`
- `archiveint!archive_entry_gname` at `0x140004e2b`
- `archiveint!archive_entry_gname` at `0x140004e2b`
- `archiveint!archive_entry_strmode` at `0x140004d97`
- `archiveint!archive_entry_strmode` at `0x140004d97`

## string_xrefs

- `0x14000503e`: ` link to %s`

## pseudocode

```c
__int64 __fastcall list_item_verbose(__int64 a1, FILE *a2, __int64 a3)
{
  int v6; // ebx
  const char *v7; // rax
  char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  char *v11; // r9
  int v12; // eax
  __int64 v13; // r15
  unsigned __int64 v14; // rax
  const char *v15; // rax
  const char *v16; // rbx
  __int64 v17; // r14
  int v18; // eax
  __int64 v19; // rax
  int v20; // ebx
  int v21; // eax
  __time64_t v22; // rax
  const char *v23; // rax
  const char *v24; // rbx
  int v25; // eax
  _OWORD *v26; // r9
  char *v27; // rdx
  __int64 result; // rax
  __time64_t v29; // [rsp+30h] [rbp-89h] BYREF
  _OWORD v30[2]; // [rsp+38h] [rbp-81h] BYREF
  int v31; // [rsp+58h] [rbp-61h]
  char Buffer[112]; // [rsp+60h] [rbp-59h] BYREF

  v29 = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  if ( !*(_QWORD *)(a1 + 176) )
  {
    *(_QWORD *)(a1 + 176) = 6;
    *(_QWORD *)(a1 + 168) = 13;
  }
  if ( !Time )
    _time64(&Time);
  v6 = archive_entry_nlink(a3);
  v7 = (const char *)archive_entry_strmode(a3);
  fprintf(a2, "%s %u ", v7, v6);
  v8 = (char *)archive_entry_uname(a3);
  v11 = v8;
  if ( !v8 || !*v8 )
  {
    v12 = archive_entry_uid(a3, v9, v10, v8);
    snprintf(Buffer, 0x64u, "%lu ", v12);
    v11 = Buffer;
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( v11[v14] );
  if ( v14 > *(_QWORD *)(a1 + 176) )
    *(_QWORD *)(a1 + 176) = v14;
  fprintf(a2, "%-*s ", *(_DWORD *)(a1 + 176), v11);
  v15 = (const char *)archive_entry_gname(a3);
  v16 = v15;
  if ( v15 && *v15 )
  {
    fprintf(a2, "%s", v15);
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
  }
  else
  {
    v18 = archive_entry_gid(a3);
    snprintf(Buffer, 0x64u, "%lu", v18);
    v17 = -1;
    do
      ++v17;
    while ( Buffer[v17] );
    fprintf(a2, "%s", Buffer);
  }
  if ( (unsigned __int16)archive_entry_filetype(a3) == 0x2000 || (unsigned __int16)archive_entry_filetype(a3) == 24576 )
  {
    v20 = archive_entry_rdevminor(a3);
    v21 = archive_entry_rdevmajor(a3);
    snprintf(Buffer, 0x64u, "%lu,%lu", v21, v20);
  }
  else
  {
    v19 = archive_entry_size(a3);
    strcpy(Buffer, (const char *)tar_i64toa(v19));
  }
  do
    ++v13;
  while ( Buffer[v13] );
  if ( (unsigned __int64)(v13 + v17) >= *(_QWORD *)(a1 + 168) )
    *(_QWORD *)(a1 + 168) = v13 + v17 + 1;
  fprintf(a2, "%*s", *(_DWORD *)(a1 + 168) - v17, Buffer);
  v22 = archive_entry_mtime(a3);
  v29 = v22;
  if ( v22 < Time - 15768000 || v22 > Time + 15768000 )
  {
    v24 = "%d %b  %Y";
    v23 = "%b %d  %Y";
  }
  else
  {
    v23 = "%b %d %H:%M";
    v24 = "%d %b %H:%M";
  }
  if ( !*(_BYTE *)(a1 + 104) )
    v24 = v23;
  v25 = _o__localtime64_s(v30, &v29);
  v26 = v30;
  if ( v25 )
    v26 = 0;
  if ( !v26 || !_o_strftime(Buffer, 100, v24) )
    sprintf(Buffer, "-- -- ----");
  fprintf(a2, " %s ", Buffer);
  archive_entry_pathname(a3);
  safe_fprintf(a2, "%s");
  if ( archive_entry_hardlink(a3) )
  {
    archive_entry_hardlink(a3);
    v27 = " link to %s";
  }
  else
  {
    result = archive_entry_symlink(a3);
    if ( !result )
      return result;
    archive_entry_symlink(a3);
    v27 = " -> %s";
  }
  return safe_fprintf(a2, v27);
}

```

## disassembly

```asm
0x140004d0c  push    rbp
0x140004d0e  push    rbx
0x140004d0f  push    rsi
0x140004d10  push    rdi
0x140004d11  push    r12
0x140004d13  push    r14
0x140004d15  push    r15
0x140004d17  lea     rbp, [rsp-27h]
0x140004d1c  sub     rsp, 0E0h
0x140004d23  mov     rax, cs:__security_cookie
0x140004d2a  xor     rax, rsp
0x140004d2d  mov     [rbp+57h+var_40], rax
0x140004d31  xor     eax, eax
0x140004d33  mov     [rsp+110h+var_E0], 0
0x140004d3c  xorps   xmm0, xmm0
0x140004d3f  mov     rdi, r8
0x140004d42  mov     r12, rdx
0x140004d45  mov     rsi, rcx
0x140004d48  movups  [rsp+110h+var_D8], xmm0
0x140004d4d  mov     [rbp+57h+var_B8], eax
0x140004d50  movups  [rbp+57h+var_C8], xmm0
0x140004d54  cmp     [rcx+0B0h], rax
0x140004d5b  jnz     short loc_140004D73
0x140004d5d  mov     qword ptr [rcx+0B0h], 6
0x140004d68  mov     qword ptr [rcx+0A8h], 0Dh
0x140004d73  cmp     cs:Time, rax
0x140004d7a  jnz     short loc_140004D89
0x140004d7c  lea     rcx, Time; Time
0x140004d83  call    cs:__imp__time64
0x140004d89  mov     rcx, rdi
0x140004d8c  call    cs:__imp_archive_entry_nlink
0x140004d92  mov     rcx, rdi
0x140004d95  mov     ebx, eax
0x140004d97  call    cs:__imp_archive_entry_strmode
0x140004d9d  mov     r9d, ebx
0x140004da0  lea     rdx, aSU; "%s %u "
0x140004da7  mov     r8, rax
0x140004daa  mov     rcx, r12; Stream
0x140004dad  call    fprintf
0x140004db2  mov     rcx, rdi
0x140004db5  call    cs:__imp_archive_entry_uname
0x140004dbb  mov     r9, rax
0x140004dbe  mov     r14d, 64h ; 'd'
0x140004dc4  test    rax, rax
0x140004dc7  jz      short loc_140004DCE
0x140004dc9  cmp     byte ptr [rax], 0
0x140004dcc  jnz     short loc_140004DF1
0x140004dce  mov     rcx, rdi
0x140004dd1  call    cs:__imp_archive_entry_uid
0x140004dd7  lea     r8, aLu; "%lu "
0x140004dde  mov     rdx, r14; BufferCount
0x140004de1  mov     r9, rax
0x140004de4  lea     rcx, [rbp+57h+Buffer]; Buffer
0x140004de8  call    snprintf
0x140004ded  lea     r9, [rbp+57h+Buffer]
0x140004df1  or      r15, 0FFFFFFFFFFFFFFFFh
0x140004df5  mov     rax, r15
0x140004df8  inc     rax
0x140004dfb  cmp     byte ptr [r9+rax], 0
0x140004e00  jnz     short loc_140004DF8
0x140004e02  cmp     rax, [rsi+0B0h]
0x140004e09  jbe     short loc_140004E12
0x140004e0b  mov     [rsi+0B0h], rax
0x140004e12  mov     r8d, [rsi+0B0h]
0x140004e19  lea     rdx, aS_0; "%-*s "
0x140004e20  mov     rcx, r12; Stream
0x140004e23  call    fprintf
0x140004e28  mov     rcx, rdi
0x140004e2b  call    cs:__imp_archive_entry_gname
0x140004e31  mov     rbx, rax
0x140004e34  test    rax, rax
0x140004e37  jz      short loc_140004E5F
0x140004e39  cmp     byte ptr [rax], 0
0x140004e3c  jz      short loc_140004E5F
0x140004e3e  mov     r8, rax
0x140004e41  lea     rdx, aS_5; "%s"
0x140004e48  mov     rcx, r12; Stream
0x140004e4b  call    fprintf
0x140004e50  mov     r14, r15
0x140004e53  inc     r14
0x140004e56  cmp     byte ptr [rbx+r14], 0
0x140004e5b  jnz     short loc_140004E53
0x140004e5d  jmp     short loc_140004EA2
0x140004e5f  mov     rcx, rdi
0x140004e62  call    cs:__imp_archive_entry_gid
0x140004e68  lea     r8, aLu_0; "%lu"
0x140004e6f  mov     rdx, r14; BufferCount
0x140004e72  mov     r9, rax
0x140004e75  lea     rcx, [rbp+57h+Buffer]; Buffer
0x140004e79  call    snprintf
0x140004e7e  lea     rax, [rbp+57h+Buffer]
0x140004e82  mov     r14, r15
0x140004e85  inc     r14
0x140004e88  cmp     byte ptr [rax+r14], 0
0x140004e8d  jnz     short loc_140004E85
0x140004e8f  lea     r8, [rbp+57h+Buffer]
0x140004e93  mov     rcx, r12; Stream
0x140004e96  lea     rdx, aS_5; "%s"
0x140004e9d  call    fprintf
0x140004ea2  mov     rcx, rdi
0x140004ea5  call    cs:__imp_archive_entry_filetype
0x140004eab  mov     ecx, 2000h
0x140004eb0  cmp     ax, cx
0x140004eb3  jz      short loc_140004EED
0x140004eb5  mov     rcx, rdi
0x140004eb8  call    cs:__imp_archive_entry_filetype
0x140004ebe  mov     ecx, 6000h
0x140004ec3  cmp     ax, cx
0x140004ec6  jz      short loc_140004EED
0x140004ec8  mov     rcx, rdi
0x140004ecb  call    cs:__imp_archive_entry_size
0x140004ed1  mov     rcx, rax
0x140004ed4  call    tar_i64toa
0x140004ed9  lea     rdx, [rbp+57h+Buffer]
0x140004edd  mov     cl, [rax]
0x140004edf  inc     rax
0x140004ee2  mov     [rdx], cl
0x140004ee4  inc     rdx
0x140004ee7  test    cl, cl
0x140004ee9  jnz     short loc_140004EDD
0x140004eeb  jmp     short loc_140004F1D
0x140004eed  mov     rcx, rdi
0x140004ef0  call    cs:__imp_archive_entry_rdevminor
0x140004ef6  mov     rcx, rdi
0x140004ef9  mov     ebx, eax
0x140004efb  call    cs:__imp_archive_entry_rdevmajor
0x140004f01  lea     r8, aLuLu; "%lu,%lu"
0x140004f08  mov     [rsp+110h+var_F0], ebx
0x140004f0c  mov     r9d, eax
0x140004f0f  lea     rcx, [rbp+57h+Buffer]; Buffer
0x140004f13  mov     edx, 64h ; 'd'; BufferCount
0x140004f18  call    snprintf
0x140004f1d  lea     rax, [rbp+57h+Buffer]
0x140004f21  inc     r15
0x140004f24  cmp     byte ptr [rax+r15], 0
0x140004f29  jnz     short loc_140004F21
0x140004f2b  lea     rax, [r15+r14]
0x140004f2f  cmp     rax, [rsi+0A8h]
0x140004f36  jb      short loc_140004F42
0x140004f38  inc     rax
0x140004f3b  mov     [rsi+0A8h], rax
0x140004f42  mov     r8d, [rsi+0A8h]
0x140004f49  lea     r9, [rbp+57h+Buffer]
0x140004f4d  sub     r8d, r14d
0x140004f50  lea     rdx, aS_3; "%*s"
0x140004f57  mov     rcx, r12; Stream
0x140004f5a  call    fprintf
0x140004f5f  mov     rcx, rdi
0x140004f62  call    cs:__imp_archive_entry_mtime
0x140004f68  mov     rdx, cs:Time
0x140004f6f  mov     [rsp+110h+var_E0], rax
0x140004f74  lea     rcx, [rdx-0F099C0h]
0x140004f7b  cmp     rax, rcx
0x140004f7e  jl      short loc_140004F9C
0x140004f80  lea     rcx, [rdx+0F099C0h]
0x140004f87  cmp     rax, rcx
0x140004f8a  jg      short loc_140004F9C
0x140004f8c  lea     rax, aBDHM; "%b %d %H:%M"
0x140004f93  lea     rbx, aDBHM; "%d %b %H:%M"
0x140004f9a  jmp     short loc_140004FAA
0x140004f9c  lea     rbx, aDBY; "%d %b  %Y"
0x140004fa3  lea     rax, aBDY; "%b %d  %Y"
0x140004faa  cmp     byte ptr [rsi+68h], 0
0x140004fae  lea     rdx, [rsp+110h+var_E0]
0x140004fb3  lea     rcx, [rsp+110h+var_D8]
0x140004fb8  cmovz   rbx, rax
0x140004fbc  call    cs:__imp__o__localtime64_s
0x140004fc2  xor     ecx, ecx
0x140004fc4  lea     r9, [rsp+110h+var_D8]
0x140004fc9  test    eax, eax
0x140004fcb  cmovnz  r9, rcx
0x140004fcf  test    r9, r9
0x140004fd2  jz      short loc_140004FE9
0x140004fd4  lea     edx, [rcx+64h]
0x140004fd7  mov     r8, rbx
0x140004fda  lea     rcx, [rbp+57h+Buffer]
0x140004fde  call    cs:__imp__o_strftime
0x140004fe4  test    rax, rax
0x140004fe7  jnz     short loc_140004FF9
0x140004fe9  lea     rdx, asc_14000BBA0; "-- -- ----"
0x140004ff0  lea     rcx, [rbp+57h+Buffer]; Buffer
0x140004ff4  call    sprintf
0x140004ff9  lea     r8, [rbp+57h+Buffer]
0x140004ffd  mov     rcx, r12; Stream
0x140005000  lea     rdx, aS; " %s "
0x140005007  call    fprintf
0x14000500c  mov     rcx, rdi
0x14000500f  call    cs:__imp_archive_entry_pathname
0x140005015  lea     rdx, aS_5; "%s"
0x14000501c  mov     rcx, r12; Stream
0x14000501f  mov     r8, rax
0x140005022  call    safe_fprintf
0x140005027  mov     rcx, rdi
0x14000502a  call    cs:__imp_archive_entry_hardlink
0x140005030  mov     rcx, rdi
0x140005033  test    rax, rax
0x140005036  jz      short loc_140005047
0x140005038  call    cs:__imp_archive_entry_hardlink
0x14000503e  lea     rdx, aLinkToS; " link to %s"
0x140005045  jmp     short loc_140005062
0x140005047  call    cs:__imp_archive_entry_symlink
0x14000504d  test    rax, rax
0x140005050  jz      short loc_14000506D
0x140005052  mov     rcx, rdi
0x140005055  call    cs:__imp_archive_entry_symlink
0x14000505b  lea     rdx, aS_4; " -> %s"
0x140005062  mov     r8, rax
0x140005065  mov     rcx, r12; Stream
0x140005068  call    safe_fprintf
0x14000506d  mov     rcx, [rbp+57h+var_40]
0x140005071  xor     rcx, rsp; StackCookie
0x140005074  call    __security_check_cookie
0x140005079  add     rsp, 0E0h
0x140005080  pop     r15
0x140005082  pop     r14
0x140005084  pop     r12
0x140005086  pop     rdi
0x140005087  pop     rsi
0x140005088  pop     rbx
0x140005089  pop     rbp
0x14000508a  retn
```
