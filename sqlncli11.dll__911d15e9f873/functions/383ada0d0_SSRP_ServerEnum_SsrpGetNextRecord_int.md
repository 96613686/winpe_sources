# SSRP::ServerEnum::SsrpGetNextRecord(int)

- ea: `0x383ada0d0`
- end: `0x383adaa11`
- name: `?SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z`
- size: `2369`
- prototype: `bool(SSRP::ServerEnum *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x383adaa80`

## callees

- `0x38391ac00`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab00c0`
- `0x383ad8da0`
- `0x383ada0d0`

## import_xrefs

- `MSVCR100!strchr` at `0x383ada339`
- `MSVCR100!strchr` at `0x383ada4a2`
- `MSVCR100!strchr` at `0x383ada633`
- `MSVCR100!strchr` at `0x383ada339`
- `MSVCR100!strchr` at `0x383ada4a2`
- `MSVCR100!strchr` at `0x383ada633`
- `MSVCR100!strncmp` at `0x383ada423`
- `MSVCR100!strncmp` at `0x383ada5e9`
- `MSVCR100!strncmp` at `0x383ada60a`
- `MSVCR100!strncmp` at `0x383ada423`
- `MSVCR100!strncmp` at `0x383ada5e9`
- `MSVCR100!strncmp` at `0x383ada60a`
- `MSVCR100!memmove` at `0x383ada5c1`
- `MSVCR100!memmove` at `0x383ada8c3`
- `MSVCR100!memmove` at `0x383ada5c1`
- `MSVCR100!memmove` at `0x383ada8c3`
- `MSVCR100!_stricmp` at `0x383ada5a2`
- `MSVCR100!_stricmp` at `0x383ada5a2`
- `KERNEL32!GetTickCount` at `0x383ada13e`
- `KERNEL32!GetTickCount` at `0x383ada15a`
- `KERNEL32!GetTickCount` at `0x383ada13e`
- `KERNEL32!GetTickCount` at `0x383ada15a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall SSRP::ServerEnum::SsrpGetNextRecord(SSRP::ServerEnum *this, unsigned int a2)
{
  int v2; // ebx
  int v4; // r12d
  char v5; // di
  DWORD TickCount; // esi
  int v7; // eax
  const CHAR *v8; // rcx
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rbp
  char *v13; // rax
  int v14; // edi
  char *v15; // rbx
  const char *v16; // rbx
  char *v17; // rax
  char *v18; // r14
  int v19; // esi
  int v20; // r15d
  _BYTE *v21; // rcx
  _BYTE *v22; // rbx
  const char *v23; // rbx
  _BYTE *v24; // r14
  char *v25; // rax
  char *v26; // rdi
  char v27; // al
  char *v28; // rcx
  char *v29; // rax
  int v31; // [rsp+20h] [rbp-58h]
  _QWORD v32[9]; // [rsp+30h] [rbp-48h] BYREF
  char v34; // [rsp+90h] [rbp+18h]
  DWORD v35; // [rsp+98h] [rbp+20h]

  v32[1] = -2;
  v2 = a2;
  v32[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `SSRP::ServerEnum::SsrpGetNextRecord'::`7'::_bidPtrSA_040_1139[0] )
    bidScopeEnterA(v32, `SSRP::ServerEnum::SsrpGetNextRecord'::`7'::_bidPtrSA_040_1139[0], a2);
  v4 = v2;
  v5 = 1;
  v34 = 1;
  TickCount = GetTickCount();
  v35 = TickCount;
  while ( 1 )
  {
    if ( v5 )
    {
      v5 = 0;
      v34 = 0;
      goto LABEL_11;
    }
    if ( v2 != -1 )
    {
      v4 = TickCount + v2 - GetTickCount();
      if ( v4 <= 0 || v4 > v2 )
        break;
    }
LABEL_11:
    if ( *((_QWORD *)this + 580) )
      goto LABEL_22;
    v7 = SSRP::SsrpSocket::ReadEx((SSRP::ServerEnum *)((char *)this + 8), (char *)this + 544, 4095, v4);
    if ( v7 == -1 || !v7 )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && `SSRP::ServerEnum::SsrpGetNextRecord'::`41'::_bidPtrSA_030_1175[0] )
        bidTraceA(
          `SSRP::ServerEnum::SsrpGetNextRecord'::`41'::_bidSrcFileA[0],
          1203200,
          `SSRP::ServerEnum::SsrpGetNextRecord'::`41'::_bidPtrSA_030_1175[0],
          (unsigned int)v4,
          v31);
      goto LABEL_112;
    }
    if ( v7 > 3 && *((_BYTE *)this + 544) == 5 && v7 - 3 == *(unsigned __int16 *)((char *)this + 545) )
    {
      *((_BYTE *)this + v7 + 544) = 0;
      *((_QWORD *)this + 580) = (char *)this + 547;
      v2 = a2;
LABEL_22:
      v8 = (const CHAR *)*((_QWORD *)this + 580);
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      if ( v9 > 0x7FFFFFFF )
      {
        if ( (bidGblFlags & 0x20002) == 0x20002
          && `SSRP::ServerEnum::SsrpGetNextRecord'::`61'::_bidPtrSA_030_1208[0]
          && bidID != -1 )
        {
          off_383B15038();
        }
        goto LABEL_112;
      }
      v10 = -1;
      do
        ++v10;
      while ( v8[v10] );
      v11 = StrStrA_SYS(v8);
      *((_QWORD *)this + 580) = 0;
      if ( v11 )
      {
        v12 = v11 + 11;
        v13 = strchr((const char *)(v11 + 11), 59);
        if ( v13 )
        {
          *v13 = 0;
          v14 = (_DWORD)v13 - v12;
          if ( (int)v13 - (int)v12 <= 255 )
          {
            v15 = v13 + 1;
            if ( !strncmp(v13 + 1, "InstanceName;", 0xDu) )
            {
              v16 = v15 + 13;
              v17 = strchr(v16, 59);
              v18 = v17;
              if ( v17 )
              {
                *v17 = 0;
                v19 = (_DWORD)v17 - (_DWORD)v16;
                if ( (int)v17 - (int)v16 <= 255 )
                {
                  v20 = v14 + 1;
                  if ( _stricmp("MSSQLSERVER", v16) )
                  {
                    v21 = (_BYTE *)(v12 + v14);
                    *v21 = 92;
                    memmove(v21 + 1, v16, v19 + 1);
                    v20 = v19 + v14 + 2;
                  }
                  if ( !*((_BYTE *)this + 1) )
                  {
                    v29 = v18 + 1;
LABEL_99:
                    *((_QWORD *)this + 580) = v29;
                    *((_QWORD *)this + 581) = v12;
                    *((_DWORD *)this + 1164) = v20;
                    if ( (bidGblFlags & 0x20002) == 0x20002
                      && `SSRP::ServerEnum::SsrpGetNextRecord'::`185'::_bidPtrSA_030_1395[0]
                      && bidID != -1 )
                    {
                      off_383B15038();
                    }
                    if ( v32[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
                      off_383B15058();
                    return 1;
                  }
                  if ( !strncmp(v18 + 1, "IsClustered;No;Version;", 0x17u) )
                  {
                    v22 = v18 + 23;
LABEL_65:
                    *v22 = 58;
                    v23 = v22 + 1;
                    v24 = v18 + 3;
                    v24[9] = 58;
                    v25 = strchr(v23, 59);
                    v26 = v25;
                    if ( v25 )
                    {
                      *v25 = 0;
                      if ( (int)v25 - (int)v23 < 16 )
                      {
                        if ( *v23 )
                        {
                          while ( 1 )
                          {
                            v27 = *v23;
                            if ( (*v23 > 57 || v27 < 48) && v27 != 46 )
                              break;
                            ++v23;
                          }
                          if ( !*v23 )
                          {
                            v28 = (char *)(v12 + v20);
                            *(v28 - 1) = 59;
                            memmove(v28, v24, (int)v26 - (int)v24 + 1);
                            v20 += (_DWORD)v26 - (_DWORD)v24 + 1;
                            v29 = v26 + 1;
                            goto LABEL_99;
                          }
                        }
                        v2 = a2;
                        v5 = v34;
                        TickCount = v35;
                        if ( (bidGblFlags & 2) != 0
                          && `SSRP::ServerEnum::SsrpGetNextRecord'::`176'::_bidPtrSA_030_1364[0]
                          && bidID != -1 )
                        {
LABEL_32:
                          v31 = 0;
                          off_383B15038();
                        }
                      }
                      else
                      {
                        v2 = a2;
                        v5 = v34;
                        TickCount = v35;
                        if ( (bidGblFlags & 2) != 0
                          && `SSRP::ServerEnum::SsrpGetNextRecord'::`166'::_bidPtrSA_030_1357[0]
                          && bidID != -1 )
                        {
                          goto LABEL_32;
                        }
                      }
                    }
                    else
                    {
                      v2 = a2;
                      v5 = v34;
                      TickCount = v35;
                      if ( (bidGblFlags & 2) != 0
                        && `SSRP::ServerEnum::SsrpGetNextRecord'::`156'::_bidPtrSA_030_1346[0]
                        && bidID != -1 )
                      {
                        goto LABEL_32;
                      }
                    }
                  }
                  else
                  {
                    if ( !strncmp(v18 + 1, "IsClustered;Yes;Version;", 0x18u) )
                    {
                      v22 = v18 + 24;
                      goto LABEL_65;
                    }
                    v2 = a2;
                    v5 = v34;
                    TickCount = v35;
                    if ( (bidGblFlags & 2) != 0
                      && `SSRP::ServerEnum::SsrpGetNextRecord'::`146'::_bidPtrSA_030_1325[0]
                      && bidID != -1 )
                    {
                      goto LABEL_32;
                    }
                  }
                }
                else
                {
                  v2 = a2;
                  v5 = v34;
                  TickCount = v35;
                  if ( (bidGblFlags & 2) != 0
                    && `SSRP::ServerEnum::SsrpGetNextRecord'::`124'::_bidPtrSA_030_1269[0]
                    && bidID != -1 )
                  {
                    goto LABEL_32;
                  }
                }
              }
              else
              {
                v2 = a2;
                v5 = v34;
                if ( (bidGblFlags & 2) != 0
                  && `SSRP::ServerEnum::SsrpGetNextRecord'::`114'::_bidPtrSA_030_1260[0]
                  && bidID != -1 )
                {
                  goto LABEL_32;
                }
              }
            }
            else
            {
              v2 = a2;
              v5 = v34;
              if ( (bidGblFlags & 2) != 0
                && `SSRP::ServerEnum::SsrpGetNextRecord'::`104'::_bidPtrSA_030_1251[0]
                && bidID != -1 )
              {
                goto LABEL_32;
              }
            }
          }
          else
          {
            v5 = v34;
            if ( (bidGblFlags & 2) != 0
              && `SSRP::ServerEnum::SsrpGetNextRecord'::`94'::_bidPtrSA_030_1243[0]
              && bidID != -1 )
            {
              goto LABEL_32;
            }
          }
        }
        else if ( (bidGblFlags & 2) != 0
               && `SSRP::ServerEnum::SsrpGetNextRecord'::`84'::_bidPtrSA_030_1234[0]
               && bidID != -1 )
        {
          goto LABEL_32;
        }
      }
      else if ( this == (SSRP::ServerEnum *)-544LL
             && (bidGblFlags & 0x20002) == 0x20002
             && `SSRP::ServerEnum::SsrpGetNextRecord'::`74'::_bidPtrSA_030_1224[0]
             && bidID != -1 )
      {
        goto LABEL_32;
      }
    }
    else
    {
      v2 = a2;
      if ( (bidGblFlags & 2) != 0 && `SSRP::ServerEnum::SsrpGetNextRecord'::`51'::_bidPtrSA_030_1186[0] && bidID != -1 )
        goto LABEL_32;
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && `SSRP::ServerEnum::SsrpGetNextRecord'::`27'::_bidPtrSA_030_1157[0] )
    bidTraceA(
      `SSRP::ServerEnum::SsrpGetNextRecord'::`27'::_bidSrcFileA[0],
      1184768,
      `SSRP::ServerEnum::SsrpGetNextRecord'::`27'::_bidPtrSA_030_1157[0],
      (unsigned int)v4,
      v31);
LABEL_112:
  if ( v32[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 0;
}

```

## disassembly

```asm
0x383ada0d0  mov     rax, rsp
0x383ada0d3  mov     [rax+10h], edx
0x383ada0d6  push    rbp
0x383ada0d7  push    rsi
0x383ada0d8  push    rdi
0x383ada0d9  push    r12
0x383ada0db  push    r13
0x383ada0dd  push    r14
0x383ada0df  push    r15
0x383ada0e1  sub     rsp, 40h
0x383ada0e5  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x383ada0ed  mov     [rax+8], rbx
0x383ada0f1  mov     ebx, edx
0x383ada0f3  mov     r13, rcx
0x383ada0f6  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFFh
0x383ada0fe  mov     eax, cs:_bidGblFlags
0x383ada104  and     eax, 20004h
0x383ada109  cmp     eax, 20004h
0x383ada10e  jnz     short loc_383ADA130
0x383ada110  mov     rax, cs:?_bidPtrSA_040_1139@?6??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`7'::_bidPtrSA_040_1139
0x383ada117  test    rax, rax
0x383ada11a  jz      short loc_383ADA130
0x383ada11c  mov     r8d, edx
0x383ada11f  mov     rdx, cs:?_bidPtrSA_040_1139@?6??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`7'::_bidPtrSA_040_1139
0x383ada126  lea     rcx, [rsp+78h+var_48]
0x383ada12b  call    _bidScopeEnterA
0x383ada130  mov     r12d, ebx
0x383ada133  mov     dil, 1
0x383ada136  mov     [rsp+78h+arg_10], dil
0x383ada13e  call    cs:__imp_GetTickCount
0x383ada144  mov     esi, eax
0x383ada146  mov     [rsp+78h+arg_18], eax
0x383ada14d  nop     dword ptr [rax]
0x383ada150  test    dil, dil
0x383ada153  jnz     short loc_383ADA17B
0x383ada155  cmp     ebx, 0FFFFFFFFh
0x383ada158  jz      short loc_383ADA186
0x383ada15a  call    cs:__imp_GetTickCount
0x383ada160  lea     r12d, [rsi+rbx]
0x383ada164  sub     r12d, eax
0x383ada167  test    r12d, r12d
0x383ada16a  jle     loc_383ADA82D
0x383ada170  cmp     r12d, ebx
0x383ada173  jg      loc_383ADA82D
0x383ada179  jmp     short loc_383ADA186
0x383ada17b  xor     dil, dil
0x383ada17e  mov     [rsp+78h+arg_10], dil
0x383ada186  cmp     qword ptr [r13+1220h], 0
0x383ada18e  jnz     loc_383ADA25F
0x383ada194  lea     rcx, [r13+8]; this
0x383ada198  mov     r9d, r12d; int
0x383ada19b  mov     r8d, 0FFFh; int
0x383ada1a1  lea     rdx, [r13+220h]; char *
0x383ada1a8  call    ?ReadEx@SsrpSocket@SSRP@@QEAAHPEADHH@Z; SSRP::SsrpSocket::ReadEx(char *,int,int)
0x383ada1ad  cmp     eax, 0FFFFFFFFh
0x383ada1b0  jz      loc_383ADA86C
0x383ada1b6  test    eax, eax
0x383ada1b8  jz      loc_383ADA86C
0x383ada1be  cmp     eax, 3
0x383ada1c1  jle     short loc_383ADA1FE
0x383ada1c3  cmp     byte ptr [r13+220h], 5
0x383ada1cb  jnz     short loc_383ADA1FE
0x383ada1cd  movzx   edx, word ptr [r13+221h]
0x383ada1d5  lea     ecx, [rax-3]
0x383ada1d8  cmp     ecx, edx
0x383ada1da  jnz     short loc_383ADA1FE
0x383ada1dc  cdqe
0x383ada1de  mov     byte ptr [rax+r13+220h], 0
0x383ada1e7  lea     rax, [r13+223h]
0x383ada1ee  mov     [r13+1220h], rax
0x383ada1f5  mov     ebx, [rsp+78h+arg_8]
0x383ada1fc  jmp     short loc_383ADA25F
0x383ada1fe  test    byte ptr cs:_bidGblFlags, 2
0x383ada205  mov     ebx, [rsp+78h+arg_8]
0x383ada20c  jz      loc_383ADA150
0x383ada212  mov     rax, cs:?_bidPtrSA_030_1186@?DD@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`51'::_bidPtrSA_030_1186
0x383ada219  test    rax, rax
0x383ada21c  jz      loc_383ADA150
0x383ada222  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada22a  jz      loc_383ADA150
0x383ada230  mov     qword ptr [rsp+78h+var_58], 0
0x383ada239  mov     r9, cs:?_bidPtrSA_030_1186@?DD@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`51'::_bidPtrSA_030_1186
0x383ada240  mov     r8d, 128800h
0x383ada246  mov     rdx, cs:?_bidSrcFileA@?DD@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`51'::_bidSrcFileA
0x383ada24d  mov     rcx, cs:_bidID
0x383ada254  call    cs:off_383B15038
0x383ada25a  jmp     loc_383ADA150
0x383ada25f  mov     rcx, [r13+1220h]; lpCurrentChar
0x383ada266  or      rax, 0FFFFFFFFFFFFFFFFh
0x383ada26a  nop     word ptr [rax+rax+00h]
0x383ada270  inc     rax
0x383ada273  cmp     byte ptr [rcx+rax], 0
0x383ada277  jnz     short loc_383ADA270
0x383ada279  cmp     rax, 7FFFFFFFh
0x383ada27f  ja      loc_383ADA976
0x383ada285  or      rdx, 0FFFFFFFFFFFFFFFFh
0x383ada289  nop     dword ptr [rax+00000000h]
0x383ada290  inc     rdx
0x383ada293  cmp     byte ptr [rcx+rdx], 0
0x383ada297  jnz     short loc_383ADA290
0x383ada299  mov     r9d, 0Bh
0x383ada29f  lea     r8, ?sc_szServerName@?DF@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4QBDB; "ServerName;"
0x383ada2a6  call    StrStrA_SYS
0x383ada2ab  mov     rbp, rax
0x383ada2ae  mov     qword ptr [r13+1220h], 0
0x383ada2b9  test    rax, rax
0x383ada2bc  jnz     short loc_383ADA32D
0x383ada2be  lea     rax, [r13+220h]
0x383ada2c5  test    rax, rax
0x383ada2c8  jnz     loc_383ADA150
0x383ada2ce  mov     eax, cs:_bidGblFlags
0x383ada2d4  and     eax, 20002h
0x383ada2d9  cmp     eax, 20002h
0x383ada2de  jnz     loc_383ADA150
0x383ada2e4  mov     rax, cs:?_bidPtrSA_030_1224@?EK@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`74'::_bidPtrSA_030_1224
0x383ada2eb  test    rax, rax
0x383ada2ee  jz      loc_383ADA150
0x383ada2f4  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada2fc  jz      loc_383ADA150
0x383ada302  mov     qword ptr [rsp+78h+var_58], rbp
0x383ada307  mov     r9, cs:?_bidPtrSA_030_1224@?EK@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`74'::_bidPtrSA_030_1224
0x383ada30e  mov     r8d, 132000h
0x383ada314  mov     rdx, cs:?_bidSrcFileA@?EK@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`74'::_bidSrcFileA
0x383ada31b  mov     rcx, cs:_bidID
0x383ada322  call    cs:off_383B15038
0x383ada328  jmp     loc_383ADA150
0x383ada32d  add     rbp, 0Bh
0x383ada331  mov     edx, 3Bh ; ';'; Val
0x383ada336  mov     rcx, rbp; Str
0x383ada339  call    cs:__imp_strchr
0x383ada33f  test    rax, rax
0x383ada342  jnz     short loc_383ADA39E
0x383ada344  test    byte ptr cs:_bidGblFlags, 2
0x383ada34b  jz      loc_383ADA150
0x383ada351  mov     rax, cs:?_bidPtrSA_030_1234@?FE@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`84'::_bidPtrSA_030_1234
0x383ada358  test    rax, rax
0x383ada35b  jz      loc_383ADA150
0x383ada361  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada369  jz      loc_383ADA150
0x383ada36f  mov     qword ptr [rsp+78h+var_58], 0
0x383ada378  mov     r9, cs:?_bidPtrSA_030_1234@?FE@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`84'::_bidPtrSA_030_1234
0x383ada37f  mov     r8d, 134800h
0x383ada385  mov     rdx, cs:?_bidSrcFileA@?FE@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`84'::_bidSrcFileA
0x383ada38c  mov     rcx, cs:_bidID
0x383ada393  call    cs:off_383B15038
0x383ada399  jmp     loc_383ADA150
0x383ada39e  mov     byte ptr [rax], 0
0x383ada3a1  mov     edi, eax
0x383ada3a3  sub     edi, ebp
0x383ada3a5  cmp     edi, 0FFh
0x383ada3ab  jle     short loc_383ADA40F
0x383ada3ad  test    byte ptr cs:_bidGblFlags, 2
0x383ada3b4  movzx   edi, [rsp+78h+arg_10]
0x383ada3bc  jz      loc_383ADA150
0x383ada3c2  mov     rax, cs:?_bidPtrSA_030_1243@?FO@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`94'::_bidPtrSA_030_1243
0x383ada3c9  test    rax, rax
0x383ada3cc  jz      loc_383ADA150
0x383ada3d2  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada3da  jz      loc_383ADA150
0x383ada3e0  mov     qword ptr [rsp+78h+var_58], 0
0x383ada3e9  mov     r9, cs:?_bidPtrSA_030_1243@?FO@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`94'::_bidPtrSA_030_1243
0x383ada3f0  mov     r8d, 136C00h
0x383ada3f6  mov     rdx, cs:?_bidSrcFileA@?FO@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`94'::_bidSrcFileA
0x383ada3fd  mov     rcx, cs:_bidID
0x383ada404  call    cs:off_383B15038
0x383ada40a  jmp     loc_383ADA150
0x383ada40f  lea     rbx, [rax+1]
0x383ada413  mov     r8d, 0Dh; MaxCount
0x383ada419  lea     rdx, aInstancename; "InstanceName;"
0x383ada420  mov     rcx, rbx; Str1
0x383ada423  call    cs:__imp_strncmp
0x383ada429  test    eax, eax
0x383ada42b  jz      short loc_383ADA496
0x383ada42d  test    byte ptr cs:_bidGblFlags, 2
0x383ada434  mov     ebx, [rsp+78h+arg_8]
0x383ada43b  movzx   edi, [rsp+78h+arg_10]
0x383ada443  jz      loc_383ADA150
0x383ada449  mov     rax, cs:?_bidPtrSA_030_1251@?GI@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`104'::_bidPtrSA_030_1251
0x383ada450  test    rax, rax
0x383ada453  jz      loc_383ADA150
0x383ada459  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada461  jz      loc_383ADA150
0x383ada467  mov     qword ptr [rsp+78h+var_58], 0
0x383ada470  mov     r9, cs:?_bidPtrSA_030_1251@?GI@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`104'::_bidPtrSA_030_1251
0x383ada477  mov     r8d, 138C00h
0x383ada47d  mov     rdx, cs:?_bidSrcFileA@?GI@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`104'::_bidSrcFileA
0x383ada484  mov     rcx, cs:_bidID
0x383ada48b  call    cs:off_383B15038
0x383ada491  jmp     loc_383ADA150
0x383ada496  add     rbx, 0Dh
0x383ada49a  mov     edx, 3Bh ; ';'; Val
0x383ada49f  mov     rcx, rbx; Str
0x383ada4a2  call    cs:__imp_strchr
0x383ada4a8  mov     r14, rax
0x383ada4ab  test    rax, rax
0x383ada4ae  jnz     short loc_383ADA515
0x383ada4b0  test    byte ptr cs:_bidGblFlags, 2
0x383ada4b7  mov     ebx, [rsp+78h+arg_8]
0x383ada4be  movzx   edi, [rsp+78h+arg_10]
0x383ada4c6  jz      loc_383ADA150
0x383ada4cc  mov     rax, cs:?_bidPtrSA_030_1260@?HC@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`114'::_bidPtrSA_030_1260
0x383ada4d3  test    rax, rax
0x383ada4d6  jz      loc_383ADA150
0x383ada4dc  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada4e4  jz      loc_383ADA150
0x383ada4ea  mov     qword ptr [rsp+78h+var_58], r14
0x383ada4ef  mov     r9, cs:?_bidPtrSA_030_1260@?HC@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`114'::_bidPtrSA_030_1260
0x383ada4f6  mov     r8d, 13B000h
0x383ada4fc  mov     rdx, cs:?_bidSrcFileA@?HC@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`114'::_bidSrcFileA
0x383ada503  mov     rcx, cs:_bidID
0x383ada50a  call    cs:off_383B15038
0x383ada510  jmp     loc_383ADA150
0x383ada515  mov     byte ptr [rax], 0
0x383ada518  mov     esi, eax
0x383ada51a  sub     esi, ebx
0x383ada51c  cmp     esi, 0FFh
0x383ada522  jle     short loc_383ADA594
0x383ada524  test    byte ptr cs:_bidGblFlags, 2
0x383ada52b  mov     ebx, [rsp+78h+arg_8]
0x383ada532  movzx   edi, [rsp+78h+arg_10]
0x383ada53a  mov     esi, [rsp+78h+arg_18]
0x383ada541  jz      loc_383ADA150
0x383ada547  mov     rax, cs:?_bidPtrSA_030_1269@?HM@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`124'::_bidPtrSA_030_1269
0x383ada54e  test    rax, rax
0x383ada551  jz      loc_383ADA150
0x383ada557  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada55f  jz      loc_383ADA150
0x383ada565  mov     qword ptr [rsp+78h+var_58], 0
0x383ada56e  mov     r9, cs:?_bidPtrSA_030_1269@?HM@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`124'::_bidPtrSA_030_1269
0x383ada575  mov     r8d, 13D400h
0x383ada57b  mov     rdx, cs:?_bidSrcFileA@?HM@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`124'::_bidSrcFileA
0x383ada582  mov     rcx, cs:_bidID
0x383ada589  call    cs:off_383B15038
0x383ada58f  jmp     loc_383ADA150
0x383ada594  lea     r15d, [rdi+1]
0x383ada598  mov     rdx, rbx; String2
0x383ada59b  lea     rcx, aMssqlserver; "MSSQLSERVER"
0x383ada5a2  call    cs:__imp__stricmp
0x383ada5a8  test    eax, eax
0x383ada5aa  jz      short loc_383ADA5CD
0x383ada5ac  movsxd  rcx, edi
0x383ada5af  add     rcx, rbp
0x383ada5b2  mov     byte ptr [rcx], 5Ch ; '\'
0x383ada5b5  lea     eax, [rsi+1]
0x383ada5b8  movsxd  r8, eax; Size
0x383ada5bb  inc     rcx; void *
0x383ada5be  mov     rdx, rbx; Src
0x383ada5c1  call    cs:__imp_memmove
0x383ada5c7  inc     r15d
0x383ada5ca  add     r15d, esi
0x383ada5cd  cmp     byte ptr [r13+1], 0
0x383ada5d2  jz      loc_383ADA8D5
0x383ada5d8  mov     r8d, 17h; MaxCount
0x383ada5de  lea     rdx, aIsclusteredNoV; "IsClustered;No;Version;"
0x383ada5e5  lea     rcx, [r14+1]; Str1
0x383ada5e9  call    cs:__imp_strncmp
0x383ada5ef  test    eax, eax
0x383ada5f1  jnz     short loc_383ADA5F9
0x383ada5f3  lea     rbx, [r14+17h]
0x383ada5f7  jmp     short loc_383ADA61C
0x383ada5f9  mov     r8d, 18h; MaxCount
0x383ada5ff  lea     rdx, aIsclusteredYes; "IsClustered;Yes;Version;"
0x383ada606  lea     rcx, [r14+1]; Str1
0x383ada60a  call    cs:__imp_strncmp
0x383ada610  test    eax, eax
0x383ada612  jnz     loc_383ADA7BD
0x383ada618  lea     rbx, [r14+18h]
0x383ada61c  mov     byte ptr [rbx], 3Ah ; ':'
0x383ada61f  inc     rbx
0x383ada622  add     r14, 3
0x383ada626  mov     byte ptr [r14+9], 3Ah ; ':'
0x383ada62b  mov     edx, 3Bh ; ';'; Val
0x383ada630  mov     rcx, rbx; Str
0x383ada633  call    cs:__imp_strchr
0x383ada639  mov     rdi, rax
0x383ada63c  test    rax, rax
0x383ada63f  jnz     short loc_383ADA6B1
0x383ada641  test    byte ptr cs:_bidGblFlags, 2
0x383ada648  mov     ebx, [rsp+78h+arg_8]
0x383ada64f  movzx   edi, [rsp+78h+arg_10]
0x383ada657  mov     esi, [rsp+78h+arg_18]
0x383ada65e  jz      loc_383ADA150
0x383ada664  mov     rax, cs:?_bidPtrSA_030_1346@?JM@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`156'::_bidPtrSA_030_1346
0x383ada66b  test    rax, rax
0x383ada66e  jz      loc_383ADA150
0x383ada674  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ada67c  jz      loc_383ADA150
0x383ada682  mov     qword ptr [rsp+78h+var_58], 0
0x383ada68b  mov     r9, cs:?_bidPtrSA_030_1346@?JM@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`156'::_bidPtrSA_030_1346
0x383ada692  mov     r8d, 150800h
0x383ada698  mov     rdx, cs:?_bidSrcFileA@?JM@??SsrpGetNextRecord@ServerEnum@SSRP@@QEAA_NH@Z@4REBDEB; char const * const `SSRP::ServerEnum::SsrpGetNextRecord(int)'::`156'::_bidSrcFileA
0x383ada69f  mov     rcx, cs:_bidID
0x383ada6a6  call    cs:off_383B15038
0x383ada6ac  jmp     loc_383ADA150
0x383ada6b1  mov     byte ptr [rax], 0
0x383ada6b4  sub     eax, ebx
0x383ada6b6  cmp     eax, 10h
0x383ada6b9  jl      short loc_383ADA72B
0x383ada6bb  test    byte ptr cs:_bidGblFlags, 2
0x383ada6c2  mov     ebx, [rsp+78h+arg_8]
  ... truncated ...
```
