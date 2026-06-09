# ComposeSsdpResponse(_SSDP_REQUEST const *,char * *)

- ea: `0x180016c14`
- end: `0x1800173ec`
- name: `?ComposeSsdpResponse@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z`
- size: `2008`
- prototype: `__int64 __fastcall(const struct _SSDP_REQUEST *, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016410`

## callees

- `0x180016c14`
- `0x180018e90`
- `0x18001bc88`
- `0x18001dad0`
- `0x180026a30`
- `0x180028000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017321`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800173bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017321`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800173bd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016eba`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016eba`

## pseudocode

```c
__int64 __fastcall ComposeSsdpResponse(const struct _SSDP_REQUEST *a1, char **a2)
{
  __int64 v3; // rcx
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // r9
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // r14d
  unsigned int v39; // r8d
  __int64 v40; // rax
  size_t v41; // rbx
  char *v42; // rax
  char *v43; // rsi
  const char *v44; // rcx
  const char *v45; // rcx
  const char *v46; // rcx
  const char *v47; // rcx
  const char *v48; // rcx
  const char *v49; // rcx
  const char *v50; // rcx
  const char *v51; // rcx
  const char *v52; // rcx
  const char *v53; // rcx
  void *v54; // rdi
  int v55; // ebx
  int v56; // eax
  unsigned int v58; // [rsp+28h] [rbp-51h]
  size_t cbDest; // [rsp+50h] [rbp-29h] BYREF
  char *Buffer; // [rsp+58h] [rbp-21h] BYREF
  void *Block; // [rsp+60h] [rbp-19h] BYREF
  char v62[16]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v63; // [rsp+78h] [rbp-1h]
  __int64 v64; // [rsp+88h] [rbp+Fh]

  v64 = 0;
  Block = 0;
  strcpy(v62, "HTTP/1.1 200 OK");
  v3 = -1;
  v63 = 0;
  do
    ++v3;
  while ( v62[v3] );
  v5 = (_QWORD *)*((_QWORD *)a1 + 10);
  v6 = v3 + 2;
  v7 = v5[1];
  if ( v7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( aSt[v8] );
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v7 + v9) );
    v6 += v9 + v8 + 4;
  }
  v10 = v5[6];
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( aLocation[v11] );
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(v10 + v12) );
    v6 += v11 + v12 + 4;
  }
  v13 = v5[7];
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( aAl[v14] );
    v15 = -1;
    do
      ++v15;
    while ( *(_BYTE *)(v13 + v15) );
    v6 += v14 + v15 + 4;
  }
  v16 = v5[19];
  if ( v16 )
  {
    v17 = -1;
    do
      ++v17;
    while ( aNls[v17] );
    v18 = -1;
    do
      ++v18;
    while ( *(_BYTE *)(v16 + v18) );
    v6 += v17 + v18 + 4;
  }
  v19 = v5[8];
  if ( v19 )
  {
    v20 = -1;
    do
      ++v20;
    while ( aUsn[v20] );
    v21 = -1;
    do
      ++v21;
    while ( *(_BYTE *)(v19 + v21) );
    v6 += v20 + v21 + 4;
  }
  v22 = v5[9];
  if ( v22 )
  {
    v23 = -1;
    do
      ++v23;
    while ( aCacheControl[v23] );
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(v22 + v24) );
    v6 += v23 + v24 + 4;
  }
  v25 = v5[13];
  if ( v25 )
  {
    v26 = -1;
    do
      ++v26;
    while ( aSid[v26] );
    v27 = -1;
    do
      ++v27;
    while ( *(_BYTE *)(v25 + v27) );
    v6 += v26 + v27 + 4;
  }
  v28 = v5[11];
  if ( v28 )
  {
    v29 = -1;
    do
      ++v29;
    while ( aTimeout[v29] );
    v30 = -1;
    do
      ++v30;
    while ( *(_BYTE *)(v28 + v30) );
    v6 += v29 + v30 + 4;
  }
  v31 = v5[17];
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( aServer[v32] );
    v33 = -1;
    do
      ++v33;
    while ( *(_BYTE *)(v31 + v33) );
    v6 += v32 + v33 + 4;
  }
  v34 = v5[18];
  if ( v34 )
  {
    v35 = -1;
    do
      ++v35;
    while ( aExt[v35] );
    v36 = -1;
    do
      ++v36;
    while ( *(_BYTE *)(v34 + v36) );
    v6 += v35 + v36 + 4;
  }
  v37 = v6 + 38;
  v38 = 20;
  if ( *((_DWORD *)a1 + 18) > 0x14u )
  {
    v39 = 20;
    do
    {
      v40 = -1;
      do
        ++v40;
      while ( *(_BYTE *)(v5[v39] + v40) );
      ++v39;
      v37 += v40 + 2;
    }
    while ( v39 < *((_DWORD *)a1 + 18) );
  }
  v41 = v37 + 3;
  v42 = (char *)malloc(v37 + 3);
  v43 = v42;
  if ( v42 )
  {
    cbDest = v41;
    Buffer = v42;
    if ( (int)StringCbPrintfExA(v42, v41, &Buffer, &cbDest, 0, "%s%s", v62, "\r\n") >= 0 )
    {
      v44 = *(const char **)(*((_QWORD *)a1 + 10) + 8LL);
      if ( !v44 || (int)StringCbPrintfExA(Buffer, cbDest, &Buffer, &cbDest, 0, "%s%s%s%s", "ST", ": ", v44, "\r\n") >= 0 )
      {
        v45 = *(const char **)(*((_QWORD *)a1 + 10) + 64LL);
        if ( !v45
          || (int)StringCbPrintfExA(Buffer, cbDest, &Buffer, &cbDest, 0, "%s%s%s%s", "USN", ": ", v45, "\r\n") >= 0 )
        {
          v46 = *(const char **)(*((_QWORD *)a1 + 10) + 48LL);
          if ( !v46
            || (int)StringCbPrintfExA(Buffer, cbDest, &Buffer, &cbDest, 0, "%s%s%s%s", "Location", ": ", v46, "\r\n") >= 0 )
          {
            v47 = *(const char **)(*((_QWORD *)a1 + 10) + 56LL);
            if ( !v47
              || (int)StringCbPrintfExA(Buffer, cbDest, &Buffer, &cbDest, 0, "%s%s%s%s", "AL", ": ", v47, "\r\n") >= 0 )
            {
              v48 = *(const char **)(*((_QWORD *)a1 + 10) + 152LL);
              if ( !v48
                || (int)StringCbPrintfExA(Buffer, cbDest, &Buffer, &cbDest, 0, "%s%s%s%s", "NLS", ": ", v48, "\r\n") >= 0 )
              {
                v49 = *(const char **)(*((_QWORD *)a1 + 10) + 72LL);
                if ( !v49
                  || (int)StringCbPrintfExA(
                            Buffer,
                            cbDest,
                            &Buffer,
                            &cbDest,
                            0,
                            "%s%s%s%s",
                            "Cache-Control",
                            ": ",
                            v49,
                            "\r\n") >= 0 )
                {
                  v50 = *(const char **)(*((_QWORD *)a1 + 10) + 104LL);
                  if ( !v50
                    || (int)StringCbPrintfExA(Buffer, cbDest, &Buffer, &cbDest, 0, "%s%s%s%s", "SID", ": ", v50, "\r\n") >= 0 )
                  {
                    v51 = *(const char **)(*((_QWORD *)a1 + 10) + 88LL);
                    if ( !v51
                      || (int)StringCbPrintfExA(
                                Buffer,
                                cbDest,
                                &Buffer,
                                &cbDest,
                                0,
                                "%s%s%s%s",
                                "Timeout",
                                ": ",
                                v51,
                                "\r\n") >= 0 )
                    {
                      v52 = *(const char **)(*((_QWORD *)a1 + 10) + 136LL);
                      if ( !v52
                        || (int)StringCbPrintfExA(
                                  Buffer,
                                  cbDest,
                                  &Buffer,
                                  &cbDest,
                                  0,
                                  "%s%s%s%s",
                                  "Server",
                                  ": ",
                                  v52,
                                  "\r\n") >= 0 )
                      {
                        v53 = *(const char **)(*((_QWORD *)a1 + 10) + 144LL);
                        if ( (!v53
                           || (int)StringCbPrintfExA(
                                     Buffer,
                                     cbDest,
                                     &Buffer,
                                     &cbDest,
                                     0,
                                     "%s%s%s%s",
                                     "Ext",
                                     ": ",
                                     v53,
                                     "\r\n") >= 0)
                          && !(unsigned int)GetSSDPDate((char **)&Block) )
                        {
                          v54 = Block;
                          if ( Block )
                          {
                            v55 = StringCbPrintfExA(
                                    Buffer,
                                    cbDest,
                                    &Buffer,
                                    &cbDest,
                                    0,
                                    "%s%s%s%s",
                                    "Date",
                                    ": ",
                                    (const char *)Block,
                                    "\r\n");
                            free(v54);
                            if ( v55 >= 0 )
                            {
                              if ( *((_DWORD *)a1 + 18) <= 0x14u )
                              {
LABEL_100:
                                if ( (int)StringCbCopyExA(Buffer, cbDest, "\r\n", &Buffer, &cbDest, v58) >= 0 )
                                {
                                  *a2 = v43;
                                  return 1;
                                }
                              }
                              else
                              {
                                while ( v55 >= 0 )
                                {
                                  v56 = StringCbPrintfExA(
                                          Buffer,
                                          cbDest,
                                          &Buffer,
                                          &cbDest,
                                          0,
                                          "%s%s",
                                          *(const char **)(*((_QWORD *)a1 + 10) + 8LL * v38++),
                                          "\r\n");
                                  v55 = v56;
                                  if ( v38 >= *((_DWORD *)a1 + 18) )
                                  {
                                    if ( v56 < 0 )
                                      break;
                                    goto LABEL_100;
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    free(v43);
  }
  else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180016c14  mov     [rsp-8+arg_10], rbx
0x180016c19  push    rbp
0x180016c1a  push    rsi
0x180016c1b  push    rdi
0x180016c1c  push    r12
0x180016c1e  push    r13
0x180016c20  push    r14
0x180016c22  push    r15
0x180016c24  lea     rbp, [rsp-27h]
0x180016c29  sub     rsp, 0A0h
0x180016c30  mov     rax, cs:__security_cookie
0x180016c37  xor     rax, rsp
0x180016c3a  mov     [rbp+57h+var_40], rax
0x180016c3e  movups  xmm0, xmmword ptr cs:aHttp11200Ok; "HTTP/1.1 200 OK"
0x180016c45  xor     eax, eax
0x180016c47  xor     r13d, r13d
0x180016c4a  or      r10, 0FFFFFFFFFFFFFFFFh
0x180016c4e  mov     [rbp+57h+var_48], rax
0x180016c52  xorps   xmm1, xmm1
0x180016c55  mov     [rbp+57h+Block], r13
0x180016c59  mov     r15, rcx
0x180016c5c  lea     rax, [rbp+57h+var_68]
0x180016c60  movdqu  [rbp+57h+var_68], xmm0
0x180016c65  mov     rcx, r10
0x180016c68  mov     r12, rdx
0x180016c6b  movups  [rbp+57h+var_58], xmm1
0x180016c6f  inc     rcx
0x180016c72  cmp     [rax+rcx], r13b
0x180016c76  jnz     short loc_180016C6F
0x180016c78  mov     rdx, [r15+50h]
0x180016c7c  add     rcx, 2
0x180016c80  mov     r9, [rdx+8]
0x180016c84  test    r9, r9
0x180016c87  jz      short loc_180016CB2
0x180016c89  mov     r8, cs:off_1800382A8; "ST"
0x180016c90  mov     rax, r10
0x180016c93  inc     rax
0x180016c96  cmp     [r8+rax], r13b
0x180016c9a  jnz     short loc_180016C93
0x180016c9c  mov     r8, r10
0x180016c9f  inc     r8
0x180016ca2  cmp     [r9+r8], r13b
0x180016ca6  jnz     short loc_180016C9F
0x180016ca8  add     rcx, 4
0x180016cac  add     rcx, rax
0x180016caf  add     rcx, r8
0x180016cb2  mov     r9, [rdx+30h]
0x180016cb6  test    r9, r9
0x180016cb9  jz      short loc_180016CE4
0x180016cbb  mov     rax, cs:off_1800382C0; "Location"
0x180016cc2  mov     r8, r10
0x180016cc5  inc     r8
0x180016cc8  cmp     [rax+r8], r13b
0x180016ccc  jnz     short loc_180016CC5
0x180016cce  mov     rax, r10
0x180016cd1  inc     rax
0x180016cd4  cmp     [r9+rax], r13b
0x180016cd8  jnz     short loc_180016CD1
0x180016cda  add     rax, r8
0x180016cdd  add     rcx, 4
0x180016ce1  add     rcx, rax
0x180016ce4  mov     r9, [rdx+38h]
0x180016ce8  test    r9, r9
0x180016ceb  jz      short loc_180016D16
0x180016ced  mov     rax, cs:off_1800382C8; "AL"
0x180016cf4  mov     r8, r10
0x180016cf7  inc     r8
0x180016cfa  cmp     [rax+r8], r13b
0x180016cfe  jnz     short loc_180016CF7
0x180016d00  mov     rax, r10
0x180016d03  inc     rax
0x180016d06  cmp     [r9+rax], r13b
0x180016d0a  jnz     short loc_180016D03
0x180016d0c  add     rax, r8
0x180016d0f  add     rcx, 4
0x180016d13  add     rcx, rax
0x180016d16  mov     r9, [rdx+98h]
0x180016d1d  test    r9, r9
0x180016d20  jz      short loc_180016D4B
0x180016d22  mov     rax, cs:off_180038328; "NLS"
0x180016d29  mov     r8, r10
0x180016d2c  inc     r8
0x180016d2f  cmp     [rax+r8], r13b
0x180016d33  jnz     short loc_180016D2C
0x180016d35  mov     rax, r10
0x180016d38  inc     rax
0x180016d3b  cmp     [r9+rax], r13b
0x180016d3f  jnz     short loc_180016D38
0x180016d41  add     rax, r8
0x180016d44  add     rcx, 4
0x180016d48  add     rcx, rax
0x180016d4b  mov     r9, [rdx+40h]
0x180016d4f  test    r9, r9
0x180016d52  jz      short loc_180016D7D
0x180016d54  mov     rax, cs:off_1800382D0; "USN"
0x180016d5b  mov     r8, r10
0x180016d5e  inc     r8
0x180016d61  cmp     [rax+r8], r13b
0x180016d65  jnz     short loc_180016D5E
0x180016d67  mov     rax, r10
0x180016d6a  inc     rax
0x180016d6d  cmp     [r9+rax], r13b
0x180016d71  jnz     short loc_180016D6A
0x180016d73  add     rax, r8
0x180016d76  add     rcx, 4
0x180016d7a  add     rcx, rax
0x180016d7d  mov     r9, [rdx+48h]
0x180016d81  test    r9, r9
0x180016d84  jz      short loc_180016DAF
0x180016d86  mov     rax, cs:off_1800382D8; "Cache-Control"
0x180016d8d  mov     r8, r10
0x180016d90  inc     r8
0x180016d93  cmp     [rax+r8], r13b
0x180016d97  jnz     short loc_180016D90
0x180016d99  mov     rax, r10
0x180016d9c  inc     rax
0x180016d9f  cmp     [r9+rax], r13b
0x180016da3  jnz     short loc_180016D9C
0x180016da5  add     rax, r8
0x180016da8  add     rcx, 4
0x180016dac  add     rcx, rax
0x180016daf  mov     r9, [rdx+68h]
0x180016db3  test    r9, r9
0x180016db6  jz      short loc_180016DE1
0x180016db8  mov     rax, cs:off_1800382F8; "SID"
0x180016dbf  mov     r8, r10
0x180016dc2  inc     r8
0x180016dc5  cmp     [rax+r8], r13b
0x180016dc9  jnz     short loc_180016DC2
0x180016dcb  mov     rax, r10
0x180016dce  inc     rax
0x180016dd1  cmp     [r9+rax], r13b
0x180016dd5  jnz     short loc_180016DCE
0x180016dd7  add     rax, r8
0x180016dda  add     rcx, 4
0x180016dde  add     rcx, rax
0x180016de1  mov     r9, [rdx+58h]
0x180016de5  test    r9, r9
0x180016de8  jz      short loc_180016E13
0x180016dea  mov     rax, cs:off_1800382E8; "Timeout"
0x180016df1  mov     r8, r10
0x180016df4  inc     r8
0x180016df7  cmp     [rax+r8], r13b
0x180016dfb  jnz     short loc_180016DF4
0x180016dfd  mov     rax, r10
0x180016e00  inc     rax
0x180016e03  cmp     [r9+rax], r13b
0x180016e07  jnz     short loc_180016E00
0x180016e09  add     rax, r8
0x180016e0c  add     rcx, 4
0x180016e10  add     rcx, rax
0x180016e13  mov     r9, [rdx+88h]
0x180016e1a  test    r9, r9
0x180016e1d  jz      short loc_180016E48
0x180016e1f  mov     rax, cs:off_180038318; "Server"
0x180016e26  mov     r8, r10
0x180016e29  inc     r8
0x180016e2c  cmp     [rax+r8], r13b
0x180016e30  jnz     short loc_180016E29
0x180016e32  mov     rax, r10
0x180016e35  inc     rax
0x180016e38  cmp     [r9+rax], r13b
0x180016e3c  jnz     short loc_180016E35
0x180016e3e  add     rax, r8
0x180016e41  add     rcx, 4
0x180016e45  add     rcx, rax
0x180016e48  mov     r9, [rdx+90h]
0x180016e4f  test    r9, r9
0x180016e52  jz      short loc_180016E7D
0x180016e54  mov     rax, cs:off_180038320; "Ext"
0x180016e5b  mov     r8, r10
0x180016e5e  inc     r8
0x180016e61  cmp     [rax+r8], r13b
0x180016e65  jnz     short loc_180016E5E
0x180016e67  mov     rax, r10
0x180016e6a  inc     rax
0x180016e6d  cmp     [r9+rax], r13b
0x180016e71  jnz     short loc_180016E6A
0x180016e73  add     rax, r8
0x180016e76  add     rcx, 4
0x180016e7a  add     rcx, rax
0x180016e7d  add     rcx, 26h ; '&'
0x180016e81  mov     r14d, 14h
0x180016e87  cmp     [r15+48h], r14d
0x180016e8b  jbe     short loc_180016EB3
0x180016e8d  mov     r8d, r14d
0x180016e90  mov     eax, r8d
0x180016e93  mov     r9, [rdx+rax*8]
0x180016e97  mov     rax, r10
0x180016e9a  inc     rax
0x180016e9d  cmp     [r9+rax], r13b
0x180016ea1  jnz     short loc_180016E9A
0x180016ea3  add     rcx, 2
0x180016ea7  inc     r8d
0x180016eaa  add     rcx, rax
0x180016ead  cmp     r8d, [r15+48h]
0x180016eb1  jb      short loc_180016E90
0x180016eb3  lea     rbx, [rcx+3]
0x180016eb7  mov     rcx, rbx; Size
0x180016eba  call    cs:__imp_malloc
0x180016ec0  mov     rsi, rax
0x180016ec3  test    rax, rax
0x180016ec6  jnz     short loc_180016F01
0x180016ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ecf  lea     rax, WPP_GLOBAL_Control
0x180016ed6  cmp     rcx, rax
0x180016ed9  jz      loc_1800173C3
0x180016edf  test    byte ptr [rcx+1Ch], 1
0x180016ee3  jz      loc_1800173C3
0x180016ee9  mov     rcx, [rcx+10h]
0x180016eed  lea     edx, [rsi+0Ah]
0x180016ef0  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180016ef7  call    WPP_SF_
0x180016efc  jmp     loc_1800173C3
0x180016f01  lea     rax, [rbp+57h+var_68]
0x180016f05  mov     [rbp+57h+cbDest], rbx
0x180016f09  lea     rdi, asc_18003914C; "\r\n"
0x180016f10  mov     [rbp+57h+Buffer], rsi
0x180016f14  mov     [rsp+0D0h+var_98], rdi
0x180016f19  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x180016f1d  mov     [rsp+0D0h+var_A0], rax
0x180016f22  lea     r8, [rbp+57h+Buffer]; char **
0x180016f26  lea     rax, aSS; "%s%s"
0x180016f2d  mov     rdx, rbx; cbDest
0x180016f30  mov     [rsp+0D0h+var_A8], rax; char *
0x180016f35  mov     rcx, rsi; Buffer
0x180016f38  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x180016f3d  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180016f42  test    eax, eax
0x180016f44  js      loc_1800173BA
0x180016f4a  mov     rax, [r15+50h]
0x180016f4e  lea     rbx, asc_18003B28C; ": "
0x180016f55  lea     rdx, aSSSS; "%s%s%s%s"
0x180016f5c  mov     rcx, [rax+8]
0x180016f60  test    rcx, rcx
0x180016f63  jz      short loc_180016FAE
0x180016f65  mov     rax, cs:off_1800382A8; "ST"
0x180016f6c  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x180016f70  mov     [rsp+0D0h+var_88], rdi
0x180016f75  lea     r8, [rbp+57h+Buffer]; char **
0x180016f79  mov     [rsp+0D0h+var_90], rcx
0x180016f7e  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180016f82  mov     [rsp+0D0h+var_98], rbx
0x180016f87  mov     [rsp+0D0h+var_A0], rax
0x180016f8c  mov     [rsp+0D0h+var_A8], rdx; char *
0x180016f91  mov     rdx, [rbp+57h+cbDest]; cbDest
0x180016f95  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x180016f9a  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180016f9f  test    eax, eax
0x180016fa1  js      loc_1800173BA
0x180016fa7  lea     rdx, aSSSS; "%s%s%s%s"
0x180016fae  mov     rax, [r15+50h]
0x180016fb2  mov     rcx, [rax+40h]
0x180016fb6  test    rcx, rcx
0x180016fb9  jz      short loc_180016FFD
0x180016fbb  mov     rax, cs:off_1800382D0; "USN"
0x180016fc2  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x180016fc6  mov     [rsp+0D0h+var_88], rdi
0x180016fcb  lea     r8, [rbp+57h+Buffer]; char **
0x180016fcf  mov     [rsp+0D0h+var_90], rcx
0x180016fd4  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180016fd8  mov     [rsp+0D0h+var_98], rbx
0x180016fdd  mov     [rsp+0D0h+var_A0], rax
0x180016fe2  mov     [rsp+0D0h+var_A8], rdx; char *
0x180016fe7  mov     rdx, [rbp+57h+cbDest]; cbDest
0x180016feb  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x180016ff0  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180016ff5  test    eax, eax
0x180016ff7  js      loc_1800173BA
0x180016ffd  mov     rax, [r15+50h]
0x180017001  mov     rcx, [rax+30h]
0x180017005  test    rcx, rcx
0x180017008  jz      short loc_180017053
0x18001700a  mov     rax, cs:off_1800382C0; "Location"
0x180017011  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x180017015  mov     rdx, [rbp+57h+cbDest]; cbDest
0x180017019  lea     r8, [rbp+57h+Buffer]; char **
0x18001701d  mov     [rsp+0D0h+var_88], rdi
0x180017022  mov     [rsp+0D0h+var_90], rcx
0x180017027  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18001702b  mov     [rsp+0D0h+var_98], rbx
0x180017030  mov     [rsp+0D0h+var_A0], rax
0x180017035  lea     rax, aSSSS; "%s%s%s%s"
0x18001703c  mov     [rsp+0D0h+var_A8], rax; char *
0x180017041  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x180017046  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18001704b  test    eax, eax
0x18001704d  js      loc_1800173BA
0x180017053  mov     rax, [r15+50h]
0x180017057  mov     rcx, [rax+38h]
0x18001705b  test    rcx, rcx
0x18001705e  jz      short loc_1800170A9
0x180017060  mov     rax, cs:off_1800382C8; "AL"
0x180017067  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x18001706b  mov     rdx, [rbp+57h+cbDest]; cbDest
0x18001706f  lea     r8, [rbp+57h+Buffer]; char **
0x180017073  mov     [rsp+0D0h+var_88], rdi
0x180017078  mov     [rsp+0D0h+var_90], rcx
0x18001707d  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180017081  mov     [rsp+0D0h+var_98], rbx
  ... truncated ...
```
