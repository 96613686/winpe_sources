# CErcLuaDownloadAndInstall::DownloadAndInstallThread(void)

- ea: `0x1800031bc`
- end: `0x18000385f`
- name: `?DownloadAndInstallThread@CErcLuaDownloadAndInstall@@AEAAKXZ`
- size: `1699`
- prototype: `unsigned int __fastcall(CErcLuaDownloadAndInstall *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006c30`

## callees

- `0x180002850`
- `0x1800031bc`
- `0x180006c9c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003237`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003237`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003299`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003299`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800037cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800037cd`

## pseudocode

```c
__int64 __fastcall CErcLuaDownloadAndInstall::DownloadAndInstallThread(CErcLuaDownloadAndInstall *this)
{
  HRESULT v2; // eax
  int v3; // r14d
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int *v9; // rdi
  int v10; // ebx
  int v11; // ecx
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-8h] BYREF
  int v19; // [rsp+A8h] [rbp+48h] BYREF
  int v20; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+58h] BYREF

  v19 = -2147467259;
  ppv = 0;
  v21 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
  v2 = CoInitializeEx(0, 2u);
  v19 = v2;
  if ( v2 >= 0 )
  {
    v3 = 1;
    v2 = CoCreateInstance(
           &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
           0,
           1u,
           &GUID_816858a4_260d_4260_933a_2585f1abc76b,
           &ppv);
    v19 = v2;
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 96LL))(ppv, &v21);
      v19 = v2;
      if ( v2 >= 0 )
      {
        if ( !v21 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = (unsigned int)v19;
            v5 = 31;
            goto LABEL_9;
          }
          goto LABEL_90;
        }
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 112LL))(v21, 0);
        v19 = v2;
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 96LL))(v21, 0);
          v19 = v2;
          if ( v2 >= 0 )
          {
            v2 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 168LL))(v21, 0);
            v19 = v2;
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 152LL))(
                     v21,
                     *((_QWORD *)this + 1),
                     &v17);
              v19 = v2;
              if ( v2 >= 0 )
              {
                if ( v17 )
                {
                  v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 72LL))(v17, &v16);
                  v19 = v2;
                  if ( v2 < 0 )
                  {
                    v4 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v5 = 37;
                      goto LABEL_8;
                    }
                    goto LABEL_90;
                  }
                  if ( v16 )
                  {
                    v9 = (int *)((char *)this + 16);
                    v2 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v16 + 80LL))(v16, (char *)this + 16);
                    v19 = v2;
                    if ( v2 >= 0 )
                    {
                      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 112LL))(ppv, &v15);
                      v19 = v2;
                      if ( v2 >= 0 )
                      {
                        v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 128LL))(v15, v16);
                        v19 = v2;
                        if ( v2 >= 0 )
                        {
                          v2 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 96LL))(
                                 v15,
                                 *(_QWORD *)this);
                          v19 = v2;
                          if ( v2 >= 0 )
                          {
                            v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 176LL))(
                                   v15,
                                   0,
                                   &v14);
                            v19 = v2;
                            if ( v2 >= 0 )
                            {
                              if ( v14 )
                              {
                                (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 56LL))(v14, &v19);
                                v2 = v19;
                                if ( v19 >= 0 )
                                {
                                  v10 = 0;
                                  if ( *v9 <= 0 )
                                  {
LABEL_89:
                                    v19 = 0;
                                  }
                                  else
                                  {
                                    while ( 1 )
                                    {
                                      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 80LL))(
                                              v14,
                                              (unsigned int)v10,
                                              &v13);
                                      if ( v19 < 0 )
                                      {
                                        v4 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                        {
                                          v5 = 46;
                                          goto LABEL_116;
                                        }
                                        goto LABEL_90;
                                      }
                                      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 56LL))(v13, &v19);
                                      if ( v19 < 0 )
                                        break;
                                      v20 = 0;
                                      v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 72LL))(
                                              v13,
                                              &v20);
                                      if ( v19 < 0 )
                                      {
                                        v4 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                        {
                                          v5 = 48;
LABEL_116:
                                          v6 = (unsigned int)v19;
                                          goto LABEL_9;
                                        }
                                        goto LABEL_90;
                                      }
                                      v11 = v20;
                                      if ( (unsigned int)(v20 - 2) <= 3 || !v20 )
                                        ++*((_DWORD *)this + 5);
                                      if ( v11 != 5 || *v9 != 1 )
                                      {
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                                        ++v10;
                                        v13 = 0;
                                        if ( v10 < *v9 )
                                          continue;
                                      }
                                      goto LABEL_89;
                                    }
                                    v4 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                    {
                                      v5 = 47;
                                      goto LABEL_116;
                                    }
                                  }
                                  goto LABEL_90;
                                }
                                v4 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                {
                                  v5 = 45;
                                  goto LABEL_8;
                                }
                              }
                              else
                              {
                                v6 = 2147942487LL;
                                v19 = -2147024809;
                                v4 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                {
                                  v5 = 44;
                                  goto LABEL_9;
                                }
                              }
                            }
                            else
                            {
                              v4 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                              {
                                v5 = 43;
                                goto LABEL_8;
                              }
                            }
                          }
                          else
                          {
                            v4 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                            {
                              v5 = 42;
                              goto LABEL_8;
                            }
                          }
                        }
                        else
                        {
                          v4 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            v5 = 41;
                            goto LABEL_8;
                          }
                        }
                      }
                      else
                      {
                        v4 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          v5 = 40;
                          goto LABEL_8;
                        }
                      }
                    }
                    else
                    {
                      v4 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        v5 = 39;
                        goto LABEL_8;
                      }
                    }
                    goto LABEL_90;
                  }
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  {
                    goto LABEL_92;
                  }
                  v8 = 38;
                }
                else
                {
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  {
                    goto LABEL_90;
                  }
                  v8 = 36;
                }
                WPP_SF_(v7[2], v8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
                goto LABEL_90;
              }
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v5 = 35;
                goto LABEL_8;
              }
            }
            else
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v5 = 34;
                goto LABEL_8;
              }
            }
          }
          else
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v5 = 33;
              goto LABEL_8;
            }
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = 32;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 30;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 29;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v3 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 28;
LABEL_8:
      v6 = (unsigned int)v2;
LABEL_9:
      WPP_SF_d(v4[2], v5, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, v6);
    }
  }
LABEL_90:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_92:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v3 )
    CoUninitialize();
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800031bc  mov     [rsp-38h+arg_0], rbx
0x1800031c1  push    rbp
0x1800031c2  push    rsi
0x1800031c3  push    rdi
0x1800031c4  push    r12
0x1800031c6  push    r13
0x1800031c8  push    r14
0x1800031ca  push    r15
0x1800031cc  mov     rbp, rsp
0x1800031cf  sub     rsp, 60h
0x1800031d3  xor     r15d, r15d
0x1800031d6  mov     [rbp+arg_8], 80004005h
0x1800031dd  mov     [rbp+var_8], r15
0x1800031e1  mov     rsi, rcx
0x1800031e4  mov     [rbp+arg_18], r15
0x1800031e8  mov     [rbp+var_28], r15
0x1800031ec  mov     [rbp+var_30], r15
0x1800031f0  mov     [rbp+var_20], r15
0x1800031f4  mov     [rbp+var_10], r15
0x1800031f8  mov     [rbp+var_18], r15
0x1800031fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003203  lea     r13, WPP_GLOBAL_Control
0x18000320a  lea     r12d, [r15+1]
0x18000320e  lea     rbx, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003215  cmp     rcx, r13
0x180003218  jz      short loc_180003230
0x18000321a  test    [rcx+1Ch], r12b
0x18000321e  jz      short loc_180003230
0x180003220  mov     rcx, [rcx+10h]
0x180003224  lea     edx, [r15+1Bh]
0x180003228  mov     r8, rbx
0x18000322b  call    WPP_SF_
0x180003230  mov     edx, 2; dwCoInit
0x180003235  xor     ecx, ecx; pvReserved
0x180003237  call    cs:__imp_CoInitializeEx
0x18000323d  mov     [rbp+arg_8], eax
0x180003240  test    eax, eax
0x180003242  jns     short loc_18000327A
0x180003244  mov     r14d, r15d
0x180003247  mov     rcx, cs:WPP_GLOBAL_Control
0x18000324e  cmp     rcx, r13
0x180003251  jz      loc_180003735
0x180003257  test    [rcx+1Ch], r12b
0x18000325b  jz      loc_180003735
0x180003261  mov     edx, 1Ch
0x180003266  mov     r9d, eax
0x180003269  mov     r8, rbx
0x18000326c  mov     rcx, [rcx+10h]
0x180003270  call    WPP_SF_d
0x180003275  jmp     loc_180003735
0x18000327a  lea     rax, [rbp+var_8]
0x18000327e  mov     r8d, r12d; dwClsContext
0x180003281  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x180003288  mov     [rsp+60h+ppv], rax; ppv
0x18000328d  xor     edx, edx; pUnkOuter
0x18000328f  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x180003296  mov     r14d, r12d
0x180003299  call    cs:__imp_CoCreateInstance
0x18000329f  mov     [rbp+arg_8], eax
0x1800032a2  test    eax, eax
0x1800032a4  jns     short loc_1800032C7
0x1800032a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032ad  cmp     rcx, r13
0x1800032b0  jz      loc_180003735
0x1800032b6  test    [rcx+1Ch], r12b
0x1800032ba  jz      loc_180003735
0x1800032c0  mov     edx, 1Dh
0x1800032c5  jmp     short loc_180003266
0x1800032c7  mov     rcx, [rbp+var_8]
0x1800032cb  lea     rdx, [rbp+arg_18]
0x1800032cf  mov     rax, [rcx]
0x1800032d2  mov     rax, [rax+60h]
0x1800032d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032db  mov     [rbp+arg_8], eax
0x1800032de  test    eax, eax
0x1800032e0  jns     short loc_180003306
0x1800032e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032e9  cmp     rcx, r13
0x1800032ec  jz      loc_180003735
0x1800032f2  test    [rcx+1Ch], r12b
0x1800032f6  jz      loc_180003735
0x1800032fc  mov     edx, 1Eh
0x180003301  jmp     loc_180003266
0x180003306  cmp     [rbp+arg_18], r15
0x18000330a  jnz     short loc_180003334
0x18000330c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003313  cmp     rcx, r13
0x180003316  jz      loc_180003735
0x18000331c  test    [rcx+1Ch], r12b
0x180003320  jz      loc_180003735
0x180003326  mov     r9d, [rbp+arg_8]
0x18000332a  mov     edx, 1Fh
0x18000332f  jmp     loc_180003269
0x180003334  mov     rcx, [rbp+arg_18]
0x180003338  xor     edx, edx
0x18000333a  mov     rax, [rcx]
0x18000333d  mov     rax, [rax+70h]
0x180003341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003346  mov     [rbp+arg_8], eax
0x180003349  test    eax, eax
0x18000334b  jns     short loc_180003371
0x18000334d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003354  cmp     rcx, r13
0x180003357  jz      loc_180003735
0x18000335d  test    [rcx+1Ch], r12b
0x180003361  jz      loc_180003735
0x180003367  mov     edx, 20h ; ' '
0x18000336c  jmp     loc_180003266
0x180003371  mov     rcx, [rbp+arg_18]
0x180003375  xor     edx, edx
0x180003377  mov     rax, [rcx]
0x18000337a  mov     rax, [rax+60h]
0x18000337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003383  mov     [rbp+arg_8], eax
0x180003386  test    eax, eax
0x180003388  jns     short loc_1800033AE
0x18000338a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003391  cmp     rcx, r13
0x180003394  jz      loc_180003735
0x18000339a  test    [rcx+1Ch], r12b
0x18000339e  jz      loc_180003735
0x1800033a4  mov     edx, 21h ; '!'
0x1800033a9  jmp     loc_180003266
0x1800033ae  mov     rcx, [rbp+arg_18]
0x1800033b2  xor     edx, edx
0x1800033b4  mov     rax, [rcx]
0x1800033b7  mov     rax, [rax+0A8h]
0x1800033be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c3  mov     [rbp+arg_8], eax
0x1800033c6  test    eax, eax
0x1800033c8  jns     short loc_1800033EE
0x1800033ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033d1  cmp     rcx, r13
0x1800033d4  jz      loc_180003735
0x1800033da  test    [rcx+1Ch], r12b
0x1800033de  jz      loc_180003735
0x1800033e4  mov     edx, 22h ; '"'
0x1800033e9  jmp     loc_180003266
0x1800033ee  mov     rcx, [rbp+arg_18]
0x1800033f2  lea     r8, [rbp+var_10]
0x1800033f6  mov     rdx, [rsi+8]
0x1800033fa  mov     rax, [rcx]
0x1800033fd  mov     rax, [rax+98h]
0x180003404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003409  mov     [rbp+arg_8], eax
0x18000340c  test    eax, eax
0x18000340e  jns     short loc_180003434
0x180003410  mov     rcx, cs:WPP_GLOBAL_Control
0x180003417  cmp     rcx, r13
0x18000341a  jz      loc_180003735
0x180003420  test    [rcx+1Ch], r12b
0x180003424  jz      loc_180003735
0x18000342a  mov     edx, 23h ; '#'
0x18000342f  jmp     loc_180003266
0x180003434  cmp     [rbp+var_10], r15
0x180003438  jnz     short loc_18000346A
0x18000343a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003441  cmp     rcx, r13
0x180003444  jz      loc_180003735
0x18000344a  test    [rcx+1Ch], r12b
0x18000344e  jz      loc_180003735
0x180003454  mov     edx, 24h ; '$'
0x180003459  mov     rcx, [rcx+10h]
0x18000345d  mov     r8, rbx
0x180003460  call    WPP_SF_
0x180003465  jmp     loc_180003735
0x18000346a  mov     rcx, [rbp+var_10]
0x18000346e  lea     rdx, [rbp+var_18]
0x180003472  mov     rax, [rcx]
0x180003475  mov     rax, [rax+48h]
0x180003479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347e  mov     [rbp+arg_8], eax
0x180003481  test    eax, eax
0x180003483  jns     short loc_1800034A9
0x180003485  mov     rcx, cs:WPP_GLOBAL_Control
0x18000348c  cmp     rcx, r13
0x18000348f  jz      loc_180003735
0x180003495  test    [rcx+1Ch], r12b
0x180003499  jz      loc_180003735
0x18000349f  mov     edx, 25h ; '%'
0x1800034a4  jmp     loc_180003266
0x1800034a9  mov     rcx, [rbp+var_18]
0x1800034ad  test    rcx, rcx
0x1800034b0  jnz     short loc_1800034D3
0x1800034b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034b9  cmp     rcx, r13
0x1800034bc  jz      loc_18000374A
0x1800034c2  test    [rcx+1Ch], r12b
0x1800034c6  jz      loc_18000374A
0x1800034cc  mov     edx, 26h ; '&'
0x1800034d1  jmp     short loc_180003459
0x1800034d3  mov     rax, [rcx]
0x1800034d6  lea     rdi, [rsi+10h]
0x1800034da  mov     rdx, rdi
0x1800034dd  mov     rax, [rax+50h]
0x1800034e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e6  mov     [rbp+arg_8], eax
0x1800034e9  test    eax, eax
0x1800034eb  jns     short loc_180003511
0x1800034ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034f4  cmp     rcx, r13
0x1800034f7  jz      loc_180003735
0x1800034fd  test    [rcx+1Ch], r12b
0x180003501  jz      loc_180003735
0x180003507  mov     edx, 27h ; '''
0x18000350c  jmp     loc_180003266
0x180003511  mov     rcx, [rbp+var_8]
0x180003515  lea     rdx, [rbp+var_20]
0x180003519  mov     rax, [rcx]
0x18000351c  mov     rax, [rax+70h]
0x180003520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003525  mov     [rbp+arg_8], eax
0x180003528  test    eax, eax
0x18000352a  jns     short loc_180003550
0x18000352c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003533  cmp     rcx, r13
0x180003536  jz      loc_180003735
0x18000353c  test    [rcx+1Ch], r12b
0x180003540  jz      loc_180003735
0x180003546  mov     edx, 28h ; '('
0x18000354b  jmp     loc_180003266
0x180003550  mov     rcx, [rbp+var_20]
0x180003554  mov     rdx, [rbp+var_18]
0x180003558  mov     rax, [rcx]
0x18000355b  mov     rax, [rax+80h]
0x180003562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003567  mov     [rbp+arg_8], eax
0x18000356a  test    eax, eax
0x18000356c  jns     short loc_180003592
0x18000356e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003575  cmp     rcx, r13
0x180003578  jz      loc_180003735
0x18000357e  test    [rcx+1Ch], r12b
0x180003582  jz      loc_180003735
0x180003588  mov     edx, 29h ; ')'
0x18000358d  jmp     loc_180003266
0x180003592  mov     rcx, [rbp+var_20]
0x180003596  mov     rdx, [rsi]
0x180003599  mov     rax, [rcx]
0x18000359c  mov     rax, [rax+60h]
0x1800035a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a5  mov     [rbp+arg_8], eax
0x1800035a8  test    eax, eax
0x1800035aa  jns     short loc_1800035D0
0x1800035ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035b3  cmp     rcx, r13
0x1800035b6  jz      loc_180003735
0x1800035bc  test    [rcx+1Ch], r12b
0x1800035c0  jz      loc_180003735
0x1800035c6  mov     edx, 2Ah ; '*'
0x1800035cb  jmp     loc_180003266
0x1800035d0  mov     rcx, [rbp+var_20]
0x1800035d4  lea     r8, [rbp+var_28]
0x1800035d8  xor     edx, edx
0x1800035da  mov     rax, [rcx]
0x1800035dd  mov     rax, [rax+0B0h]
0x1800035e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e9  mov     [rbp+arg_8], eax
0x1800035ec  test    eax, eax
0x1800035ee  jns     short loc_180003614
0x1800035f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035f7  cmp     rcx, r13
0x1800035fa  jz      loc_180003735
0x180003600  test    [rcx+1Ch], r12b
0x180003604  jz      loc_180003735
0x18000360a  mov     edx, 2Bh ; '+'
0x18000360f  jmp     loc_180003266
0x180003614  cmp     [rbp+var_28], r15
0x180003618  jnz     short loc_180003648
0x18000361a  mov     r9d, 80070057h
0x180003620  mov     [rbp+arg_8], r9d
0x180003624  mov     rcx, cs:WPP_GLOBAL_Control
0x18000362b  cmp     rcx, r13
0x18000362e  jz      loc_180003735
0x180003634  test    [rcx+1Ch], r12b
0x180003638  jz      loc_180003735
0x18000363e  mov     edx, 2Ch ; ','
0x180003643  jmp     loc_180003269
0x180003648  mov     rcx, [rbp+var_28]
0x18000364c  lea     rdx, [rbp+arg_8]
0x180003650  mov     rax, [rcx]
0x180003653  mov     rax, [rax+38h]
0x180003657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000365c  mov     eax, [rbp+arg_8]
0x18000365f  test    eax, eax
0x180003661  jns     short loc_180003687
0x180003663  mov     rcx, cs:WPP_GLOBAL_Control
0x18000366a  cmp     rcx, r13
0x18000366d  jz      loc_180003735
0x180003673  test    [rcx+1Ch], r12b
0x180003677  jz      loc_180003735
0x18000367d  mov     edx, 2Dh ; '-'
0x180003682  jmp     loc_180003266
0x180003687  mov     ebx, r15d
0x18000368a  cmp     [rdi], r15d
0x18000368d  jle     loc_180003731
0x180003693  mov     rcx, [rbp+var_28]
0x180003697  lea     r8, [rbp+var_30]
0x18000369b  mov     edx, ebx
0x18000369d  mov     rax, [rcx]
  ... truncated ...
```
