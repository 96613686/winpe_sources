# ComposeSsdpResponse(_SSDP_REQUEST const *,char * *)

- ea: `0x18001905c`
- end: `0x180019847`
- name: `?ComposeSsdpResponse@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z`
- size: `2027`
- prototype: `__int64 __fastcall(const struct _SSDP_REQUEST *, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018804`

## callees

- `0x18001905c`
- `0x180019ed0`
- `0x18001d0b4`
- `0x18001ef64`
- `0x1800287d0`
- `0x180029df0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001976f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019811`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001976f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019811`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180019302`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180019302`

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
0x18001905c  mov     [rsp-8+arg_10], rbx
0x180019061  push    rbp
0x180019062  push    rsi
0x180019063  push    rdi
0x180019064  push    r12
0x180019066  push    r13
0x180019068  push    r14
0x18001906a  push    r15
0x18001906c  lea     rbp, [rsp-27h]
0x180019071  sub     rsp, 0A0h
0x180019078  mov     rax, cs:__security_cookie
0x18001907f  xor     rax, rsp
0x180019082  mov     [rbp+57h+var_40], rax
0x180019086  movups  xmm0, xmmword ptr cs:aHttp11200Ok; "HTTP/1.1 200 OK"
0x18001908d  xor     eax, eax
0x18001908f  xor     r13d, r13d
0x180019092  or      r10, 0FFFFFFFFFFFFFFFFh
0x180019096  mov     [rbp+57h+var_48], rax
0x18001909a  xorps   xmm1, xmm1
0x18001909d  mov     [rbp+57h+Block], r13
0x1800190a1  mov     r15, rcx
0x1800190a4  lea     rax, [rbp+57h+var_68]
0x1800190a8  movdqu  [rbp+57h+var_68], xmm0
0x1800190ad  mov     rcx, r10
0x1800190b0  mov     r12, rdx
0x1800190b3  movups  [rbp+57h+var_58], xmm1
0x1800190b7  inc     rcx
0x1800190ba  cmp     [rax+rcx], r13b
0x1800190be  jnz     short loc_1800190B7
0x1800190c0  mov     rdx, [r15+50h]
0x1800190c4  add     rcx, 2
0x1800190c8  mov     r9, [rdx+8]
0x1800190cc  test    r9, r9
0x1800190cf  jz      short loc_1800190FA
0x1800190d1  mov     r8, cs:off_18003B2A8; "ST"
0x1800190d8  mov     rax, r10
0x1800190db  inc     rax
0x1800190de  cmp     [r8+rax], r13b
0x1800190e2  jnz     short loc_1800190DB
0x1800190e4  mov     r8, r10
0x1800190e7  inc     r8
0x1800190ea  cmp     [r9+r8], r13b
0x1800190ee  jnz     short loc_1800190E7
0x1800190f0  add     rcx, 4
0x1800190f4  add     rcx, rax
0x1800190f7  add     rcx, r8
0x1800190fa  mov     r9, [rdx+30h]
0x1800190fe  test    r9, r9
0x180019101  jz      short loc_18001912C
0x180019103  mov     rax, cs:off_18003B2C0; "Location"
0x18001910a  mov     r8, r10
0x18001910d  inc     r8
0x180019110  cmp     [rax+r8], r13b
0x180019114  jnz     short loc_18001910D
0x180019116  mov     rax, r10
0x180019119  inc     rax
0x18001911c  cmp     [r9+rax], r13b
0x180019120  jnz     short loc_180019119
0x180019122  add     rax, r8
0x180019125  add     rcx, 4
0x180019129  add     rcx, rax
0x18001912c  mov     r9, [rdx+38h]
0x180019130  test    r9, r9
0x180019133  jz      short loc_18001915E
0x180019135  mov     rax, cs:off_18003B2C8; "AL"
0x18001913c  mov     r8, r10
0x18001913f  inc     r8
0x180019142  cmp     [rax+r8], r13b
0x180019146  jnz     short loc_18001913F
0x180019148  mov     rax, r10
0x18001914b  inc     rax
0x18001914e  cmp     [r9+rax], r13b
0x180019152  jnz     short loc_18001914B
0x180019154  add     rax, r8
0x180019157  add     rcx, 4
0x18001915b  add     rcx, rax
0x18001915e  mov     r9, [rdx+98h]
0x180019165  test    r9, r9
0x180019168  jz      short loc_180019193
0x18001916a  mov     rax, cs:off_18003B328; "NLS"
0x180019171  mov     r8, r10
0x180019174  inc     r8
0x180019177  cmp     [rax+r8], r13b
0x18001917b  jnz     short loc_180019174
0x18001917d  mov     rax, r10
0x180019180  inc     rax
0x180019183  cmp     [r9+rax], r13b
0x180019187  jnz     short loc_180019180
0x180019189  add     rax, r8
0x18001918c  add     rcx, 4
0x180019190  add     rcx, rax
0x180019193  mov     r9, [rdx+40h]
0x180019197  test    r9, r9
0x18001919a  jz      short loc_1800191C5
0x18001919c  mov     rax, cs:off_18003B2D0; "USN"
0x1800191a3  mov     r8, r10
0x1800191a6  inc     r8
0x1800191a9  cmp     [rax+r8], r13b
0x1800191ad  jnz     short loc_1800191A6
0x1800191af  mov     rax, r10
0x1800191b2  inc     rax
0x1800191b5  cmp     [r9+rax], r13b
0x1800191b9  jnz     short loc_1800191B2
0x1800191bb  add     rax, r8
0x1800191be  add     rcx, 4
0x1800191c2  add     rcx, rax
0x1800191c5  mov     r9, [rdx+48h]
0x1800191c9  test    r9, r9
0x1800191cc  jz      short loc_1800191F7
0x1800191ce  mov     rax, cs:off_18003B2D8; "Cache-Control"
0x1800191d5  mov     r8, r10
0x1800191d8  inc     r8
0x1800191db  cmp     [rax+r8], r13b
0x1800191df  jnz     short loc_1800191D8
0x1800191e1  mov     rax, r10
0x1800191e4  inc     rax
0x1800191e7  cmp     [r9+rax], r13b
0x1800191eb  jnz     short loc_1800191E4
0x1800191ed  add     rax, r8
0x1800191f0  add     rcx, 4
0x1800191f4  add     rcx, rax
0x1800191f7  mov     r9, [rdx+68h]
0x1800191fb  test    r9, r9
0x1800191fe  jz      short loc_180019229
0x180019200  mov     rax, cs:off_18003B2F8; "SID"
0x180019207  mov     r8, r10
0x18001920a  inc     r8
0x18001920d  cmp     [rax+r8], r13b
0x180019211  jnz     short loc_18001920A
0x180019213  mov     rax, r10
0x180019216  inc     rax
0x180019219  cmp     [r9+rax], r13b
0x18001921d  jnz     short loc_180019216
0x18001921f  add     rax, r8
0x180019222  add     rcx, 4
0x180019226  add     rcx, rax
0x180019229  mov     r9, [rdx+58h]
0x18001922d  test    r9, r9
0x180019230  jz      short loc_18001925B
0x180019232  mov     rax, cs:off_18003B2E8; "Timeout"
0x180019239  mov     r8, r10
0x18001923c  inc     r8
0x18001923f  cmp     [rax+r8], r13b
0x180019243  jnz     short loc_18001923C
0x180019245  mov     rax, r10
0x180019248  inc     rax
0x18001924b  cmp     [r9+rax], r13b
0x18001924f  jnz     short loc_180019248
0x180019251  add     rax, r8
0x180019254  add     rcx, 4
0x180019258  add     rcx, rax
0x18001925b  mov     r9, [rdx+88h]
0x180019262  test    r9, r9
0x180019265  jz      short loc_180019290
0x180019267  mov     rax, cs:off_18003B318; "Server"
0x18001926e  mov     r8, r10
0x180019271  inc     r8
0x180019274  cmp     [rax+r8], r13b
0x180019278  jnz     short loc_180019271
0x18001927a  mov     rax, r10
0x18001927d  inc     rax
0x180019280  cmp     [r9+rax], r13b
0x180019284  jnz     short loc_18001927D
0x180019286  add     rax, r8
0x180019289  add     rcx, 4
0x18001928d  add     rcx, rax
0x180019290  mov     r9, [rdx+90h]
0x180019297  test    r9, r9
0x18001929a  jz      short loc_1800192C5
0x18001929c  mov     rax, cs:off_18003B320; "Ext"
0x1800192a3  mov     r8, r10
0x1800192a6  inc     r8
0x1800192a9  cmp     [rax+r8], r13b
0x1800192ad  jnz     short loc_1800192A6
0x1800192af  mov     rax, r10
0x1800192b2  inc     rax
0x1800192b5  cmp     [r9+rax], r13b
0x1800192b9  jnz     short loc_1800192B2
0x1800192bb  add     rax, r8
0x1800192be  add     rcx, 4
0x1800192c2  add     rcx, rax
0x1800192c5  add     rcx, 26h ; '&'
0x1800192c9  mov     r14d, 14h
0x1800192cf  cmp     [r15+48h], r14d
0x1800192d3  jbe     short loc_1800192FB
0x1800192d5  mov     r8d, r14d
0x1800192d8  mov     eax, r8d
0x1800192db  mov     r9, [rdx+rax*8]
0x1800192df  mov     rax, r10
0x1800192e2  inc     rax
0x1800192e5  cmp     [r9+rax], r13b
0x1800192e9  jnz     short loc_1800192E2
0x1800192eb  add     rcx, 2
0x1800192ef  inc     r8d
0x1800192f2  add     rcx, rax
0x1800192f5  cmp     r8d, [r15+48h]
0x1800192f9  jb      short loc_1800192D8
0x1800192fb  lea     rbx, [rcx+3]
0x1800192ff  mov     rcx, rbx; Size
0x180019302  call    cs:__imp_malloc
0x180019309  nop     dword ptr [rax+rax+00h]
0x18001930e  mov     rsi, rax
0x180019311  test    rax, rax
0x180019314  jnz     short loc_18001934F
0x180019316  mov     rcx, cs:WPP_GLOBAL_Control
0x18001931d  lea     rax, WPP_GLOBAL_Control
0x180019324  cmp     rcx, rax
0x180019327  jz      loc_18001981D
0x18001932d  test    byte ptr [rcx+1Ch], 1
0x180019331  jz      loc_18001981D
0x180019337  mov     rcx, [rcx+10h]
0x18001933b  lea     edx, [rsi+0Ah]
0x18001933e  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180019345  call    WPP_SF_
0x18001934a  jmp     loc_18001981D
0x18001934f  lea     rax, [rbp+57h+var_68]
0x180019353  mov     [rbp+57h+cbDest], rbx
0x180019357  lea     rdi, Delimiter; "\r\n"
0x18001935e  mov     [rbp+57h+Buffer], rsi
0x180019362  mov     [rsp+0D0h+var_98], rdi
0x180019367  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x18001936b  mov     [rsp+0D0h+var_A0], rax
0x180019370  lea     r8, [rbp+57h+Buffer]; char **
0x180019374  lea     rax, aSS; "%s%s"
0x18001937b  mov     rdx, rbx; cbDest
0x18001937e  mov     [rsp+0D0h+var_A8], rax; char *
0x180019383  mov     rcx, rsi; Buffer
0x180019386  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x18001938b  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180019390  test    eax, eax
0x180019392  js      loc_18001980E
0x180019398  mov     rax, [r15+50h]
0x18001939c  lea     rbx, asc_18003E29C; ": "
0x1800193a3  lea     rdx, aSSSS; "%s%s%s%s"
0x1800193aa  mov     rcx, [rax+8]
0x1800193ae  test    rcx, rcx
0x1800193b1  jz      short loc_1800193FC
0x1800193b3  mov     rax, cs:off_18003B2A8; "ST"
0x1800193ba  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x1800193be  mov     [rsp+0D0h+var_88], rdi
0x1800193c3  lea     r8, [rbp+57h+Buffer]; char **
0x1800193c7  mov     [rsp+0D0h+var_90], rcx
0x1800193cc  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800193d0  mov     [rsp+0D0h+var_98], rbx
0x1800193d5  mov     [rsp+0D0h+var_A0], rax
0x1800193da  mov     [rsp+0D0h+var_A8], rdx; char *
0x1800193df  mov     rdx, [rbp+57h+cbDest]; cbDest
0x1800193e3  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x1800193e8  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800193ed  test    eax, eax
0x1800193ef  js      loc_18001980E
0x1800193f5  lea     rdx, aSSSS; "%s%s%s%s"
0x1800193fc  mov     rax, [r15+50h]
0x180019400  mov     rcx, [rax+40h]
0x180019404  test    rcx, rcx
0x180019407  jz      short loc_18001944B
0x180019409  mov     rax, cs:off_18003B2D0; "USN"
0x180019410  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x180019414  mov     [rsp+0D0h+var_88], rdi
0x180019419  lea     r8, [rbp+57h+Buffer]; char **
0x18001941d  mov     [rsp+0D0h+var_90], rcx
0x180019422  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180019426  mov     [rsp+0D0h+var_98], rbx
0x18001942b  mov     [rsp+0D0h+var_A0], rax
0x180019430  mov     [rsp+0D0h+var_A8], rdx; char *
0x180019435  mov     rdx, [rbp+57h+cbDest]; cbDest
0x180019439  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x18001943e  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180019443  test    eax, eax
0x180019445  js      loc_18001980E
0x18001944b  mov     rax, [r15+50h]
0x18001944f  mov     rcx, [rax+30h]
0x180019453  test    rcx, rcx
0x180019456  jz      short loc_1800194A1
0x180019458  mov     rax, cs:off_18003B2C0; "Location"
0x18001945f  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x180019463  mov     rdx, [rbp+57h+cbDest]; cbDest
0x180019467  lea     r8, [rbp+57h+Buffer]; char **
0x18001946b  mov     [rsp+0D0h+var_88], rdi
0x180019470  mov     [rsp+0D0h+var_90], rcx
0x180019475  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180019479  mov     [rsp+0D0h+var_98], rbx
0x18001947e  mov     [rsp+0D0h+var_A0], rax
0x180019483  lea     rax, aSSSS; "%s%s%s%s"
0x18001948a  mov     [rsp+0D0h+var_A8], rax; char *
0x18001948f  mov     qword ptr [rsp+0D0h+var_B0], r13; DWORD
0x180019494  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180019499  test    eax, eax
0x18001949b  js      loc_18001980E
0x1800194a1  mov     rax, [r15+50h]
0x1800194a5  mov     rcx, [rax+38h]
0x1800194a9  test    rcx, rcx
0x1800194ac  jz      short loc_1800194F7
0x1800194ae  mov     rax, cs:off_18003B2C8; "AL"
0x1800194b5  lea     r9, [rbp+57h+cbDest]; unsigned __int64 *
0x1800194b9  mov     rdx, [rbp+57h+cbDest]; cbDest
0x1800194bd  lea     r8, [rbp+57h+Buffer]; char **
0x1800194c1  mov     [rsp+0D0h+var_88], rdi
0x1800194c6  mov     [rsp+0D0h+var_90], rcx
0x1800194cb  mov     rcx, [rbp+57h+Buffer]; Buffer
  ... truncated ...
```
