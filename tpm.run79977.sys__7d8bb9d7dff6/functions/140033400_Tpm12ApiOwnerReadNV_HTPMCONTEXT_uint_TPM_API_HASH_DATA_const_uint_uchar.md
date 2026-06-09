# Tpm12ApiOwnerReadNV(HTPMCONTEXT__ *,uint,_TPM_API_HASH_DATA const *,uint *,uchar *)

- ea: `0x140033400`
- end: `0x140033bd2`
- name: `?Tpm12ApiOwnerReadNV@@YAJPEAUHTPMCONTEXT__@@IPEBU_TPM_API_HASH_DATA@@PEAIPEAE@Z`
- size: `2002`
- prototype: `__int64 __fastcall(struct HTPMCONTEXT__ *, unsigned int, const struct _TPM_API_HASH_DATA *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14002a410`

## callees

- `0x140032cc8`
- `0x140033400`
- `0x140033bd8`
- `0x140034248`
- `0x1400342a4`
- `0x1400344a4`
- `0x140034694`
- `0x140034848`
- `0x14003487c`
- `0x1400390c4`
- `0x1400391a0`
- `0x140039228`
- `0x14003926c`
- `0x1400392c8`
- `0x1400392f0`
- `0x140039374`
- `0x1400393e0`
- `0x1400394cc`
- `0x14003950c`
- `0x140039570`
- `0x1400395ac`
- `0x140039740`
- `0x140039b40`

## pseudocode

```c
__int64 __fastcall Tpm12ApiOwnerReadNV(
        struct HTPMCONTEXT__ *a1,
        unsigned int a2,
        const struct _TPM_API_HASH_DATA *a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  unsigned int *v8; // rsi
  __int64 v9; // r13
  int started; // ebx
  struct HTPMCONTEXT__ *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // r11d
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // r15d
  unsigned int v25; // r14d
  struct HTPMCONTEXT__ *v26; // r12
  unsigned int v27; // r13d
  unsigned int v28; // r12d
  __int64 v29; // rdx
  int v30; // eax
  _BYTE *v31; // rax
  unsigned int v33; // [rsp+34h] [rbp-D4h] BYREF
  unsigned int v34; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int *v36; // [rsp+40h] [rbp-C8h] BYREF
  struct HTPMCONTEXT__ *v37; // [rsp+48h] [rbp-C0h]
  unsigned int v38; // [rsp+50h] [rbp-B8h]
  unsigned int v39; // [rsp+54h] [rbp-B4h]
  const struct _TPM_API_HASH_DATA *v40; // [rsp+58h] [rbp-B0h]
  unsigned __int8 *v41; // [rsp+60h] [rbp-A8h]
  unsigned int *v42; // [rsp+68h] [rbp-A0h]
  struct HTPMCONTEXT__ *v43; // [rsp+70h] [rbp-98h]
  _BYTE v44[80]; // [rsp+80h] [rbp-88h] BYREF

  v42 = a4;
  v40 = a3;
  v38 = a2;
  v37 = a1;
  v43 = a1;
  v41 = a5;
  v8 = 0;
  v36 = 0;
  v34 = 0;
  v35 = 0;
  v33 = 0;
  v9 = 72;
  memset(v44, 0, 0x48u);
  if ( *a4 )
  {
    if ( !a5 )
    {
      started = -2144796413;
      goto LABEL_93;
    }
    memset(a5, 0, *a4);
  }
  started = TpmApiCreateCmdBuf(a1, &v36);
  if ( started >= 0 )
  {
    v8 = v36;
    started = CmdBufStartCommand(v36, 193, 101);
    if ( started >= 0 )
    {
      started = CmdBufStartHashableData(v8);
      if ( started >= 0 )
      {
        started = CmdBufAddUint32(v8, 17);
        if ( started >= 0 )
        {
          started = CmdBufAddUint32(v8, 4);
          if ( started >= 0 )
          {
            started = CmdBufAddUint32(v8, a2);
            if ( started >= 0 )
            {
              started = CmdBufEndHashableData(v8);
              if ( started >= 0 )
              {
                started = CmdBufFinishCommand(v8);
                if ( started >= 0 )
                {
                  v34 = *v8;
                  v11 = v37;
                  started = TpmApiCallbackTpmCall(v37, v8[5], *((_QWORD *)v8 + 1), &v34, *((_QWORD *)v8 + 1));
                  if ( started >= 0 )
                  {
                    started = CmdBufStartResult(v8, v34);
                    if ( started >= 0 )
                    {
                      started = CmdBufCheckResponse(v8);
                      if ( started >= 0 )
                      {
                        started = CmdBufStartHashableData(v8);
                        if ( started >= 0 )
                        {
                          started = CmdBufGetUint32(v8, &v35);
                          if ( started >= 0 )
                          {
                            if ( v35 )
                            {
                              started = CmdBufSkipData(v8, 2);
                              if ( started >= 0 )
                              {
                                started = CmdBufSkipData(v12, 4);
                                if ( started >= 0 )
                                {
                                  started = CmdBufGetUint16(v13, &v33);
                                  if ( started >= 0 )
                                  {
                                    if ( !v33 || (started = CmdBufSkipData(v8, v33), started >= 0) )
                                    {
                                      started = CmdBufSkipData(v8, 1);
                                      if ( started >= 0 )
                                      {
                                        started = CmdBufSkipData(v14, 20);
                                        if ( started >= 0 )
                                        {
                                          started = CmdBufGetUint16(v15, &v33);
                                          if ( started >= 0 )
                                          {
                                            if ( !v33 || (started = CmdBufSkipData(v8, v33), started >= 0) )
                                            {
                                              started = CmdBufSkipData(v8, 1);
                                              if ( started >= 0 )
                                              {
                                                started = CmdBufSkipData(v16, v17);
                                                if ( started >= 0 )
                                                {
                                                  started = CmdBufSkipData(v18, 2);
                                                  if ( started >= 0 )
                                                  {
                                                    started = CmdBufSkipData(v19, 4);
                                                    if ( started >= 0 )
                                                    {
                                                      started = CmdBufSkipData(v20, 1);
                                                      if ( started >= 0 )
                                                      {
                                                        started = CmdBufSkipData(v21, 1);
                                                        if ( started >= 0 )
                                                        {
                                                          started = CmdBufSkipData(v22, 1);
                                                          if ( started >= 0 )
                                                          {
                                                            started = CmdBufGetUint32(v23, &v33);
                                                            if ( started >= 0 )
                                                            {
                                                              started = CmdBufEndHashableData(v8);
                                                              if ( started >= 0 )
                                                              {
                                                                started = CmdBufFinishResult(v8);
                                                                if ( started >= 0 )
                                                                {
                                                                  TpmApiCleanupCmdBuf(v11, v8);
                                                                  v8 = 0;
                                                                  v36 = 0;
                                                                  v24 = v33;
                                                                  if ( v33 )
                                                                  {
                                                                    if ( a5 && v33 <= *a4 )
                                                                    {
                                                                      v25 = 0;
                                                                      v39 = 0;
                                                                      v26 = v37;
                                                                      while ( v25 < v24 )
                                                                      {
                                                                        v27 = v24 - v25;
                                                                        if ( v24 - v25 > 0x300 )
                                                                          v27 = 768;
                                                                        v35 = 0;
                                                                        started = TpmApiCreateCmdBuf(v26, &v36);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v8 = v36;
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        v8 = v36;
                                                                        started = TpmApiAuthSessCreateOIAP(
                                                                                    v26,
                                                                                    v36,
                                                                                    v40,
                                                                                    v44);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufStartCommand(v8, 194, 207);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufStartHashableData(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufAddUint32(v8, v38);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufAddUint32(v8, v25);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufAddUint32(v8, v27);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufEndHashableData(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = TpmApiAuthSessPackAuthSession(v8, v44);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufFinishCommand(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        v34 = *v8;
                                                                        started = TpmApiCallbackTpmCall(
                                                                                    v26,
                                                                                    v8[5],
                                                                                    *((_QWORD *)v8 + 1),
                                                                                    &v34,
                                                                                    *((_QWORD *)v8 + 1));
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufStartResult(v8, v34);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufCheckResponse(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufStartHashableData(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufGetUint32(v8, &v35);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        v28 = v35;
                                                                        if ( v35 > v27 )
                                                                        {
                                                                          started = -2144796414;
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufGetData(v8, v35, &v41[v25]);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        v25 += v28;
                                                                        v39 = v25;
                                                                        started = CmdBufEndHashableData(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        v30 = TpmApiAuthSessVerifyAuthSession(
                                                                                v8,
                                                                                v29,
                                                                                v44);
                                                                        started = v30;
                                                                        if ( v30 && v30 != -2144796407 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        started = CmdBufFinishResult(v8);
                                                                        if ( started < 0 )
                                                                        {
                                                                          v9 = 72;
                                                                          goto LABEL_93;
                                                                        }
                                                                        v26 = v37;
                                                                        TpmApiCleanupCmdBuf(v37, v8);
                                                                        v8 = 0;
                                                                        v36 = 0;
                                                                      }
                                                                      *v42 = v24;
                                                                      v9 = 72;
                                                                    }
                                                                    else
                                                                    {
                                                                      *a4 = v33;
                                                                      started = -2144796410;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    *a4 = 0;
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
                                  }
                                }
                              }
                            }
                            else
                            {
                              started = -2144796412;
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
  else
  {
    v8 = v36;
  }
LABEL_93:
  TpmApiAuthSessReleaseIfNeeded(v37, v8, (unsigned int)started, v44);
  TpmApiCleanupCmdBuf(v37, v8);
  v31 = v44;
  do
  {
    *v31++ = 0;
    --v9;
  }
  while ( v9 );
  return (unsigned int)started;
}

```

## disassembly

```asm
0x140033400  mov     [rsp+arg_8], rbx
0x140033405  push    rsi
0x140033406  push    r12
0x140033408  push    r13
0x14003340a  push    r14
0x14003340c  push    r15
0x14003340e  sub     rsp, 0E0h
0x140033415  mov     rax, cs:__security_cookie
0x14003341c  xor     rax, rsp
0x14003341f  mov     [rsp+108h+var_38], rax
0x140033427  mov     r12, r9
0x14003342a  mov     [rsp+108h+var_A0], r9
0x14003342f  mov     [rsp+108h+var_B0], r8
0x140033434  mov     r15d, edx
0x140033437  mov     [rsp+108h+var_B8], edx
0x14003343b  mov     rbx, rcx
0x14003343e  mov     [rsp+108h+var_C0], rcx
0x140033443  mov     [rsp+108h+var_98], rcx
0x140033448  mov     r14, [rsp+108h+arg_20]
0x140033450  mov     [rsp+108h+var_A8], r14
0x140033455  xor     esi, esi
0x140033457  mov     [rsp+108h+var_C8], rsi
0x14003345c  mov     [rsp+108h+var_D0], esi
0x140033460  mov     [rsp+108h+var_CC], esi
0x140033464  mov     [rsp+108h+var_D4], esi
0x140033468  lea     r13d, [rsi+48h]
0x14003346c  mov     r8d, r13d; Size
0x14003346f  xor     edx, edx; Val
0x140033471  lea     rcx, [rsp+108h+var_88]; void *
0x140033479  call    memset
0x14003347e  nop
0x14003347f  mov     eax, [r12]
0x140033483  test    eax, eax
0x140033485  jz      short loc_1400334A7
0x140033487  test    r14, r14
0x14003348a  jnz     short loc_14003349A
0x14003348c  mov     ebx, 80290103h
0x140033491  mov     [rsp+108h+var_D8], ebx
0x140033495  jmp     loc_140033B6D
0x14003349a  mov     r8, rax; Size
0x14003349d  xor     edx, edx; Val
0x14003349f  mov     rcx, r14; void *
0x1400334a2  call    memset
0x1400334a7  lea     rdx, [rsp+108h+var_C8]
0x1400334ac  mov     rcx, rbx
0x1400334af  call    TpmApiCreateCmdBuf
0x1400334b4  mov     ebx, eax
0x1400334b6  mov     [rsp+108h+var_D8], eax
0x1400334ba  test    eax, eax
0x1400334bc  jns     short loc_1400334C8
0x1400334be  mov     rsi, [rsp+108h+var_C8]
0x1400334c3  jmp     loc_140033B6D
0x1400334c8  mov     edx, 0C1h
0x1400334cd  lea     r8d, [rdx-5Ch]
0x1400334d1  mov     rsi, [rsp+108h+var_C8]
0x1400334d6  mov     rcx, rsi
0x1400334d9  call    CmdBufStartCommand
0x1400334de  mov     ebx, eax
0x1400334e0  mov     [rsp+108h+var_D8], eax
0x1400334e4  test    eax, eax
0x1400334e6  js      loc_140033B6D
0x1400334ec  mov     rcx, rsi
0x1400334ef  call    CmdBufStartHashableData
0x1400334f4  mov     ebx, eax
0x1400334f6  mov     [rsp+108h+var_D8], eax
0x1400334fa  test    eax, eax
0x1400334fc  js      loc_140033B6D
0x140033502  mov     edx, 11h
0x140033507  mov     rcx, rsi
0x14003350a  call    CmdBufAddUint32
0x14003350f  mov     ebx, eax
0x140033511  mov     [rsp+108h+var_D8], eax
0x140033515  test    eax, eax
0x140033517  js      loc_140033B6D
0x14003351d  mov     edx, 4
0x140033522  mov     rcx, rsi
0x140033525  call    CmdBufAddUint32
0x14003352a  mov     ebx, eax
0x14003352c  mov     [rsp+108h+var_D8], eax
0x140033530  test    eax, eax
0x140033532  js      loc_140033B6D
0x140033538  mov     edx, r15d
0x14003353b  mov     rcx, rsi
0x14003353e  call    CmdBufAddUint32
0x140033543  mov     ebx, eax
0x140033545  mov     [rsp+108h+var_D8], eax
0x140033549  test    eax, eax
0x14003354b  js      loc_140033B6D
0x140033551  mov     rcx, rsi
0x140033554  call    CmdBufEndHashableData
0x140033559  mov     ebx, eax
0x14003355b  mov     [rsp+108h+var_D8], eax
0x14003355f  test    eax, eax
0x140033561  js      loc_140033B6D
0x140033567  mov     rcx, rsi
0x14003356a  call    CmdBufFinishCommand
0x14003356f  mov     ebx, eax
0x140033571  mov     [rsp+108h+var_D8], eax
0x140033575  test    eax, eax
0x140033577  js      loc_140033B6D
0x14003357d  mov     eax, [rsi]
0x14003357f  mov     [rsp+108h+var_D0], eax
0x140033583  mov     r8, [rsi+8]
0x140033587  mov     [rsp+108h+var_E8], r8
0x14003358c  lea     r9, [rsp+108h+var_D0]
0x140033591  mov     edx, [rsi+14h]
0x140033594  mov     r15, [rsp+108h+var_C0]
0x140033599  mov     rcx, r15
0x14003359c  call    TpmApiCallbackTpmCall
0x1400335a1  mov     ebx, eax
0x1400335a3  mov     [rsp+108h+var_D8], eax
0x1400335a7  test    eax, eax
0x1400335a9  js      loc_140033B6D
0x1400335af  mov     edx, [rsp+108h+var_D0]
0x1400335b3  mov     rcx, rsi
0x1400335b6  call    CmdBufStartResult
0x1400335bb  mov     ebx, eax
0x1400335bd  mov     [rsp+108h+var_D8], eax
0x1400335c1  test    eax, eax
0x1400335c3  js      loc_140033B6D
0x1400335c9  mov     rcx, rsi
0x1400335cc  call    CmdBufCheckResponse
0x1400335d1  mov     ebx, eax
0x1400335d3  mov     [rsp+108h+var_D8], eax
0x1400335d7  test    eax, eax
0x1400335d9  js      loc_140033B6D
0x1400335df  mov     rcx, rsi
0x1400335e2  call    CmdBufStartHashableData
0x1400335e7  mov     ebx, eax
0x1400335e9  mov     [rsp+108h+var_D8], eax
0x1400335ed  test    eax, eax
0x1400335ef  js      loc_140033B6D
0x1400335f5  lea     rdx, [rsp+108h+var_CC]
0x1400335fa  mov     rcx, rsi
0x1400335fd  call    CmdBufGetUint32
0x140033602  mov     ebx, eax
0x140033604  mov     [rsp+108h+var_D8], eax
0x140033608  test    eax, eax
0x14003360a  js      loc_140033B6D
0x140033610  cmp     [rsp+108h+var_CC], 0
0x140033615  jnz     short loc_140033625
0x140033617  mov     ebx, 80290104h
0x14003361c  mov     [rsp+108h+var_D8], ebx
0x140033620  jmp     loc_140033B6D
0x140033625  mov     edx, 2
0x14003362a  mov     rcx, rsi
0x14003362d  call    CmdBufSkipData
0x140033632  mov     ebx, eax
0x140033634  mov     [rsp+108h+var_D8], eax
0x140033638  test    eax, eax
0x14003363a  js      loc_140033B6D
0x140033640  mov     edx, 4
0x140033645  call    CmdBufSkipData
0x14003364a  mov     ebx, eax
0x14003364c  mov     [rsp+108h+var_D8], eax
0x140033650  test    eax, eax
0x140033652  js      loc_140033B6D
0x140033658  lea     rdx, [rsp+108h+var_D4]
0x14003365d  call    CmdBufGetUint16
0x140033662  mov     ebx, eax
0x140033664  mov     [rsp+108h+var_D8], eax
0x140033668  test    eax, eax
0x14003366a  js      loc_140033B6D
0x140033670  mov     edx, [rsp+108h+var_D4]
0x140033674  test    edx, edx
0x140033676  jz      short loc_14003368E
0x140033678  mov     rcx, rsi
0x14003367b  call    CmdBufSkipData
0x140033680  mov     ebx, eax
0x140033682  mov     [rsp+108h+var_D8], eax
0x140033686  test    eax, eax
0x140033688  js      loc_140033B6D
0x14003368e  mov     edx, 1
0x140033693  mov     rcx, rsi
0x140033696  call    CmdBufSkipData
0x14003369b  mov     ebx, eax
0x14003369d  mov     [rsp+108h+var_D8], eax
0x1400336a1  test    eax, eax
0x1400336a3  js      loc_140033B6D
0x1400336a9  mov     r11d, 14h
0x1400336af  mov     edx, r11d
0x1400336b2  call    CmdBufSkipData
0x1400336b7  mov     ebx, eax
0x1400336b9  mov     [rsp+108h+var_D8], eax
0x1400336bd  test    eax, eax
0x1400336bf  js      loc_140033B6D
0x1400336c5  lea     rdx, [rsp+108h+var_D4]
0x1400336ca  call    CmdBufGetUint16
0x1400336cf  mov     ebx, eax
0x1400336d1  mov     [rsp+108h+var_D8], eax
0x1400336d5  test    eax, eax
0x1400336d7  js      loc_140033B6D
0x1400336dd  mov     edx, [rsp+108h+var_D4]
0x1400336e1  test    edx, edx
0x1400336e3  jz      short loc_1400336FB
0x1400336e5  mov     rcx, rsi
0x1400336e8  call    CmdBufSkipData
0x1400336ed  mov     ebx, eax
0x1400336ef  mov     [rsp+108h+var_D8], eax
0x1400336f3  test    eax, eax
0x1400336f5  js      loc_140033B6D
0x1400336fb  mov     edx, 1
0x140033700  mov     rcx, rsi
0x140033703  call    CmdBufSkipData
0x140033708  mov     ebx, eax
0x14003370a  mov     [rsp+108h+var_D8], eax
0x14003370e  test    eax, eax
0x140033710  js      loc_140033B6D
0x140033716  mov     edx, r11d
0x140033719  call    CmdBufSkipData
0x14003371e  mov     ebx, eax
0x140033720  mov     [rsp+108h+var_D8], eax
0x140033724  test    eax, eax
0x140033726  js      loc_140033B6D
0x14003372c  mov     edx, 2
0x140033731  call    CmdBufSkipData
0x140033736  mov     ebx, eax
0x140033738  mov     [rsp+108h+var_D8], eax
0x14003373c  test    eax, eax
0x14003373e  js      loc_140033B6D
0x140033744  mov     edx, 4
0x140033749  call    CmdBufSkipData
0x14003374e  mov     ebx, eax
0x140033750  mov     [rsp+108h+var_D8], eax
0x140033754  test    eax, eax
0x140033756  js      loc_140033B6D
0x14003375c  mov     edx, 1
0x140033761  call    CmdBufSkipData
0x140033766  mov     ebx, eax
0x140033768  mov     [rsp+108h+var_D8], eax
0x14003376c  test    eax, eax
0x14003376e  js      loc_140033B6D
0x140033774  mov     edx, 1
0x140033779  call    CmdBufSkipData
0x14003377e  mov     ebx, eax
0x140033780  mov     [rsp+108h+var_D8], eax
0x140033784  test    eax, eax
0x140033786  js      loc_140033B6D
0x14003378c  mov     edx, 1
0x140033791  call    CmdBufSkipData
0x140033796  mov     ebx, eax
0x140033798  mov     [rsp+108h+var_D8], eax
0x14003379c  test    eax, eax
0x14003379e  js      loc_140033B6D
0x1400337a4  lea     rdx, [rsp+108h+var_D4]
0x1400337a9  call    CmdBufGetUint32
0x1400337ae  mov     ebx, eax
0x1400337b0  mov     [rsp+108h+var_D8], eax
0x1400337b4  test    eax, eax
0x1400337b6  js      loc_140033B6D
0x1400337bc  mov     rcx, rsi
0x1400337bf  call    CmdBufEndHashableData
0x1400337c4  mov     ebx, eax
0x1400337c6  mov     [rsp+108h+var_D8], eax
0x1400337ca  test    eax, eax
0x1400337cc  js      loc_140033B6D
0x1400337d2  mov     rcx, rsi
0x1400337d5  call    CmdBufFinishResult
0x1400337da  mov     ebx, eax
0x1400337dc  mov     [rsp+108h+var_D8], eax
0x1400337e0  test    eax, eax
0x1400337e2  js      loc_140033B6D
0x1400337e8  mov     rdx, rsi
0x1400337eb  mov     rcx, r15
0x1400337ee  call    TpmApiCleanupCmdBuf
0x1400337f3  xor     esi, esi
0x1400337f5  mov     [rsp+108h+var_C8], rsi
0x1400337fa  mov     r15d, [rsp+108h+var_D4]
0x1400337ff  test    r15d, r15d
0x140033802  jnz     short loc_14003380D
0x140033804  mov     [r12], esi
0x140033808  jmp     loc_140033B6D
0x14003380d  test    r14, r14
0x140033810  jz      loc_140033B3F
0x140033816  cmp     r15d, [r12]
0x14003381a  ja      loc_140033B3F
0x140033820  xor     r14d, r14d
0x140033823  mov     [rsp+108h+var_B4], r14d
0x140033828  mov     r12, [rsp+108h+var_C0]
0x14003382d  mov     eax, 300h
0x140033832  cmp     r14d, r15d
0x140033835  jnb     loc_140033B2F
0x14003383b  mov     r13d, r15d
0x14003383e  sub     r13d, r14d
0x140033841  cmp     r13d, eax
0x140033844  cmova   r13d, eax
0x140033848  mov     [rsp+108h+var_CC], 0
0x140033850  lea     rdx, [rsp+108h+var_C8]
0x140033855  mov     rcx, r12
0x140033858  call    TpmApiCreateCmdBuf
0x14003385d  mov     ebx, eax
0x14003385f  mov     [rsp+108h+var_D8], eax
0x140033863  test    eax, eax
0x140033865  jns     short loc_140033877
0x140033867  mov     rsi, [rsp+108h+var_C8]
0x14003386c  mov     r13d, 48h ; 'H'
0x140033872  jmp     loc_140033B6D
0x140033877  lea     r9, [rsp+108h+var_88]
0x14003387f  mov     r8, [rsp+108h+var_B0]
0x140033884  mov     rsi, [rsp+108h+var_C8]
  ... truncated ...
```
