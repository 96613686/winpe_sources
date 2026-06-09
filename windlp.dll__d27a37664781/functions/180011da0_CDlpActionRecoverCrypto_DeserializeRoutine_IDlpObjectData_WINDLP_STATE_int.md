# CDlpActionRecoverCrypto::DeserializeRoutine(IDlpObjectData *,WINDLP_STATE,int *)

- ea: `0x180011da0`
- end: `0x180012370`
- name: `?DeserializeRoutine@CDlpActionRecoverCrypto@@EEAAJPEAVIDlpObjectData@@W4WINDLP_STATE@@PEAH@Z`
- size: `1488`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x18000aba4`
- `0x180011da0`
- `0x180012f5c`
- `0x18001fd60`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800122f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180012308`
- `OLEAUT32!__imp_SysFreeString` at `0x18001231b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001232e`
- `OLEAUT32!__imp_SysFreeString` at `0x180012341`
- `OLEAUT32!__imp_SysFreeString` at `0x1800122f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180012308`
- `OLEAUT32!__imp_SysFreeString` at `0x18001231b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001232e`
- `OLEAUT32!__imp_SysFreeString` at `0x180012341`

## string_xrefs

- `0x180012010`: `DeleteSource`
- `0x180011e39`: `CDlpActionRecoverCrypto::DeserializeRoutine`
- `0x180011e98`: `WimSourcePath`
- `0x180011f15`: `RepairRetryCount`
- `0x180011f55`: `RepairAttemptsCount`
- `0x18001208b`: `WimTargetPath`
- `0x1800120db`: `RemoteSourcePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpActionRecoverCrypto::DeserializeRoutine(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rsi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v25; // [rsp+20h] [rbp-99h]
  int v26; // [rsp+28h] [rbp-91h]
  int v27; // [rsp+30h] [rbp-89h] BYREF
  int v28; // [rsp+34h] [rbp-85h] BYREF
  int v29; // [rsp+38h] [rbp-81h] BYREF
  int v30; // [rsp+3Ch] [rbp-7Dh] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-79h] BYREF
  BSTR v32; // [rsp+48h] [rbp-71h] BYREF
  BSTR v33; // [rsp+50h] [rbp-69h] BYREF
  BSTR v34; // [rsp+58h] [rbp-61h] BYREF
  BSTR v35; // [rsp+60h] [rbp-59h] BYREF
  __int64 v36; // [rsp+68h] [rbp-51h] BYREF
  __int128 v37; // [rsp+70h] [rbp-49h] BYREF
  __int64 v38; // [rsp+80h] [rbp-39h]
  BSTR v39; // [rsp+88h] [rbp-31h]
  BSTR v40; // [rsp+90h] [rbp-29h]
  BSTR v41; // [rsp+98h] [rbp-21h]
  BSTR v42; // [rsp+A0h] [rbp-19h]
  int v43; // [rsp+A8h] [rbp-11h]
  int v44; // [rsp+ACh] [rbp-Dh]
  BSTR v45; // [rsp+B0h] [rbp-9h]
  int v46; // [rsp+B8h] [rbp-1h]
  int v47; // [rsp+BCh] [rbp+3h]
  BOOL v48; // [rsp+C0h] [rbp+7h]
  int v49; // [rsp+C4h] [rbp+Bh]

  v35 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  bstrString = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v36 = 0;
  memset_0(&v37, 0, 0x58u);
  if ( a2 )
  {
    if ( a4 )
    {
      v12 = a2 + 8;
      v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(
              v12,
              L"WimSourcePath",
              &v35);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v14 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v12)(v12, L"HashType", &v28);
        v8 = v14;
        if ( v14 >= 0 )
        {
          v15 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v12)(v12, L"RepairRetryCount", &v29);
          v8 = v15;
          if ( v15 >= 0 )
          {
            v16 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, __int64))v12)(
                    v12,
                    L"RepairAttemptsCount",
                    a1 + 668);
            v8 = v16;
            if ( v16 >= 0 )
            {
              v17 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, __int64))v12)(
                      v12,
                      L"CorruptBlocksCount",
                      a1 + 664);
              v8 = v17;
              if ( v17 >= 0 )
              {
                v18 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v12)(v12, L"Flags", &v27);
                v8 = v18;
                if ( v18 >= 0 )
                {
                  v19 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v12)(v12, L"DeleteSource", &v30);
                  v8 = v19;
                  if ( v19 >= 0 )
                  {
                    v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v12 + 8LL))(
                            v12,
                            L"WimFileSize",
                            &v36);
                    v8 = v20;
                    if ( v20 >= 0 )
                    {
                      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(
                             v12,
                             L"WimTargetPath",
                             &v34);
                      if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147023728 )
                      {
                        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(
                               v12,
                               L"RemoteSourcePath",
                               &v33);
                        if ( ((v8 + 0x80000000) & 0x80000000) != 0 || v8 == -2147023728 )
                        {
                          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(
                                 v12,
                                 L"CryptoKey",
                                 &v32);
                          if ( ((v8 + 0x80000000) & 0x80000000) != 0 || v8 == -2147023728 )
                          {
                            v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(
                                   v12,
                                   L"FileHash",
                                   &bstrString);
                            if ( ((v8 + 0x80000000) & 0x80000000) != 0 || v8 == -2147023728 )
                            {
                              v44 = 0;
                              v49 = 0;
                              v37 = WINDLP_ACTION_RECOVERCRYPTO;
                              v39 = v35;
                              v40 = v34;
                              v42 = v33;
                              v38 = v36;
                              v46 = v27;
                              v41 = v32;
                              v45 = bstrString;
                              v43 = v28;
                              v47 = v29;
                              v48 = v30 != 0;
                              v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 32LL))(
                                      a1,
                                      &v37,
                                      88);
                              v8 = v21;
                              if ( v21 >= 0 )
                              {
                                if ( a3 == 4 )
                                {
                                  *(_DWORD *)(a1 + 640) = 1;
                                  v22 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, __int64))v12)(
                                          v12,
                                          L"CurrentRangeWritten",
                                          a1 + 736);
                                  v8 = v22;
                                  if ( v22 < 0 )
                                  {
                                    v9 = *(_QWORD *)(a1 + 88);
                                    if ( !v9 )
                                      goto LABEL_61;
                                    v26 = v22;
                                    v25 = 703;
                                    goto LABEL_4;
                                  }
                                  v23 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, __int64))v12)(
                                          v12,
                                          L"CurrentRangeSaved",
                                          a1 + 732);
                                  v8 = v23;
                                  if ( v23 < 0 )
                                  {
                                    v9 = *(_QWORD *)(a1 + 88);
                                    if ( !v9 )
                                      goto LABEL_61;
                                    v26 = v23;
                                    v25 = 706;
                                    goto LABEL_4;
                                  }
                                }
                                *a4 = 0;
                                goto LABEL_61;
                              }
                              v9 = *(_QWORD *)(a1 + 88);
                              if ( !v9 )
                                goto LABEL_61;
                              v26 = v21;
                              v25 = 694;
                            }
                            else
                            {
                              v9 = *(_QWORD *)(a1 + 88);
                              if ( !v9 )
                                goto LABEL_61;
                              v26 = v8;
                              v25 = 677;
                            }
                          }
                          else
                          {
                            v9 = *(_QWORD *)(a1 + 88);
                            if ( !v9 )
                              goto LABEL_61;
                            v26 = v8;
                            v25 = 673;
                          }
                        }
                        else
                        {
                          v9 = *(_QWORD *)(a1 + 88);
                          if ( !v9 )
                            goto LABEL_61;
                          v26 = v8;
                          v25 = 669;
                        }
                      }
                      else
                      {
                        v9 = *(_QWORD *)(a1 + 88);
                        if ( !v9 )
                          goto LABEL_61;
                        v26 = v8;
                        v25 = 665;
                      }
                    }
                    else
                    {
                      v9 = *(_QWORD *)(a1 + 88);
                      if ( !v9 )
                        goto LABEL_61;
                      v26 = v20;
                      v25 = 661;
                    }
                  }
                  else
                  {
                    v9 = *(_QWORD *)(a1 + 88);
                    if ( !v9 )
                      goto LABEL_61;
                    v26 = v19;
                    v25 = 660;
                  }
                }
                else
                {
                  v9 = *(_QWORD *)(a1 + 88);
                  if ( !v9 )
                    goto LABEL_61;
                  v26 = v18;
                  v25 = 659;
                }
              }
              else
              {
                v9 = *(_QWORD *)(a1 + 88);
                if ( !v9 )
                  goto LABEL_61;
                v26 = v17;
                v25 = 658;
              }
            }
            else
            {
              v9 = *(_QWORD *)(a1 + 88);
              if ( !v9 )
                goto LABEL_61;
              v26 = v16;
              v25 = 657;
            }
          }
          else
          {
            v9 = *(_QWORD *)(a1 + 88);
            if ( !v9 )
              goto LABEL_61;
            v26 = v15;
            v25 = 656;
          }
        }
        else
        {
          v9 = *(_QWORD *)(a1 + 88);
          if ( !v9 )
            goto LABEL_61;
          v26 = v14;
          v25 = 655;
        }
      }
      else
      {
        v9 = *(_QWORD *)(a1 + 88);
        if ( !v9 )
          goto LABEL_61;
        v26 = v13;
        v25 = 654;
      }
    }
    else
    {
      v8 = -2147024809;
      v9 = *(_QWORD *)(a1 + 88);
      if ( !v9 )
        goto LABEL_61;
      v26 = -2147024809;
      v25 = 652;
    }
  }
  else
  {
    v8 = -2147024809;
    v9 = *(_QWORD *)(a1 + 88);
    if ( !v9 )
      goto LABEL_61;
    v26 = -2147024809;
    v25 = 651;
  }
LABEL_4:
  v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v9,
          4,
          L"%s(%d): Result = 0x%X",
          L"CDlpActionRecoverCrypto::DeserializeRoutine",
          v25,
          v26);
  v11 = (unsigned int)v10;
  if ( v10 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
LABEL_61:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v32 )
  {
    SysFreeString(v32);
    v32 = 0;
  }
  if ( v33 )
  {
    SysFreeString(v33);
    v33 = 0;
  }
  if ( v34 )
  {
    SysFreeString(v34);
    v34 = 0;
  }
  if ( v35 )
    SysFreeString(v35);
  return v8;
}

```

## disassembly

```asm
0x180011da0  mov     [rsp-8+arg_10], rbx
0x180011da5  push    rbp
0x180011da6  push    rsi
0x180011da7  push    rdi
0x180011da8  push    r12
0x180011daa  push    r13
0x180011dac  push    r14
0x180011dae  push    r15
0x180011db0  lea     rbp, [rsp-27h]
0x180011db5  sub     rsp, 0E0h
0x180011dbc  mov     rax, cs:__security_cookie
0x180011dc3  xor     rax, rsp
0x180011dc6  mov     [rbp+57h+var_40], rax
0x180011dca  mov     r14, r9
0x180011dcd  mov     r15d, r8d
0x180011dd0  mov     rsi, rdx
0x180011dd3  mov     rdi, rcx
0x180011dd6  xor     r12d, r12d
0x180011dd9  mov     [rbp+57h+var_B0], r12
0x180011ddd  mov     [rbp+57h+var_B8], r12
0x180011de1  mov     [rbp+57h+var_C0], r12
0x180011de5  mov     [rbp+57h+var_C8], r12
0x180011de9  mov     [rbp+57h+bstrString], r12
0x180011ded  mov     [rsp+110h+var_DC], r12d
0x180011df2  mov     [rsp+110h+var_E0], r12d
0x180011df7  mov     [rsp+110h+var_D8], r12d
0x180011dfc  mov     [rbp+57h+var_D4], r12d
0x180011e00  mov     [rbp+57h+var_A8], r12
0x180011e04  xor     edx, edx; Val
0x180011e06  lea     r8d, [r12+58h]; Size
0x180011e0b  lea     rcx, [rbp+57h+var_A0]; void *
0x180011e0f  call    memset_0
0x180011e14  test    rsi, rsi
0x180011e17  jnz     short loc_180011E66
0x180011e19  mov     eax, 80070057h
0x180011e1e  mov     ebx, eax
0x180011e20  mov     rcx, [rdi+58h]
0x180011e24  test    rcx, rcx
0x180011e27  jz      loc_1800122E4
0x180011e2d  mov     [rsp+110h+var_E8], eax
0x180011e31  mov     [rsp+110h+var_F0], 28Bh
0x180011e39  lea     r9, aCdlpactionreco_15; "CDlpActionRecoverCrypto::DeserializeRou"...
0x180011e40  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180011e47  mov     edx, 4
0x180011e4c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180011e51  test    eax, eax
0x180011e53  mov     ecx, eax
0x180011e55  jns     short loc_180011E5C
0x180011e57  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011e5c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180011e61  jmp     loc_1800122E4
0x180011e66  test    r14, r14
0x180011e69  jnz     short loc_180011E8D
0x180011e6b  mov     eax, 80070057h
0x180011e70  mov     ebx, eax
0x180011e72  mov     rcx, [rdi+58h]
0x180011e76  test    rcx, rcx
0x180011e79  jz      loc_1800122E4
0x180011e7f  mov     [rsp+110h+var_E8], eax
0x180011e83  mov     [rsp+110h+var_F0], 28Ch
0x180011e8b  jmp     short loc_180011E39
0x180011e8d  add     rsi, 8
0x180011e91  mov     rax, [rsi]
0x180011e94  lea     r8, [rbp+57h+var_B0]
0x180011e98  lea     rdx, aWimsourcepath; "WimSourcePath"
0x180011e9f  mov     rcx, rsi
0x180011ea2  mov     rax, [rax+10h]
0x180011ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eab  mov     ebx, eax
0x180011ead  test    eax, eax
0x180011eaf  jns     short loc_180011ECF
0x180011eb1  mov     rcx, [rdi+58h]
0x180011eb5  test    rcx, rcx
0x180011eb8  jz      loc_1800122E4
0x180011ebe  mov     [rsp+110h+var_E8], eax
0x180011ec2  mov     [rsp+110h+var_F0], 28Eh
0x180011eca  jmp     loc_180011E39
0x180011ecf  mov     rax, [rsi]
0x180011ed2  lea     r8, [rsp+110h+var_DC]
0x180011ed7  lea     rdx, aHashtype; "HashType"
0x180011ede  mov     rcx, rsi
0x180011ee1  mov     rax, [rax]
0x180011ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ee9  mov     ebx, eax
0x180011eeb  test    eax, eax
0x180011eed  jns     short loc_180011F0D
0x180011eef  mov     rcx, [rdi+58h]
0x180011ef3  test    rcx, rcx
0x180011ef6  jz      loc_1800122E4
0x180011efc  mov     [rsp+110h+var_E8], eax
0x180011f00  mov     [rsp+110h+var_F0], 28Fh
0x180011f08  jmp     loc_180011E39
0x180011f0d  mov     rax, [rsi]
0x180011f10  lea     r8, [rsp+110h+var_D8]
0x180011f15  lea     rdx, aRepairretrycou; "RepairRetryCount"
0x180011f1c  mov     rcx, rsi
0x180011f1f  mov     rax, [rax]
0x180011f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f27  mov     ebx, eax
0x180011f29  test    eax, eax
0x180011f2b  jns     short loc_180011F4B
0x180011f2d  mov     rcx, [rdi+58h]
0x180011f31  test    rcx, rcx
0x180011f34  jz      loc_1800122E4
0x180011f3a  mov     [rsp+110h+var_E8], eax
0x180011f3e  mov     [rsp+110h+var_F0], 290h
0x180011f46  jmp     loc_180011E39
0x180011f4b  mov     rax, [rsi]
0x180011f4e  lea     r8, [rdi+29Ch]
0x180011f55  lea     rdx, aRepairattempts; "RepairAttemptsCount"
0x180011f5c  mov     rcx, rsi
0x180011f5f  mov     rax, [rax]
0x180011f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f67  mov     ebx, eax
0x180011f69  test    eax, eax
0x180011f6b  jns     short loc_180011F8B
0x180011f6d  mov     rcx, [rdi+58h]
0x180011f71  test    rcx, rcx
0x180011f74  jz      loc_1800122E4
0x180011f7a  mov     [rsp+110h+var_E8], eax
0x180011f7e  mov     [rsp+110h+var_F0], 291h
0x180011f86  jmp     loc_180011E39
0x180011f8b  mov     rax, [rsi]
0x180011f8e  lea     r8, [rdi+298h]
0x180011f95  lea     rdx, aCorruptblocksc; "CorruptBlocksCount"
0x180011f9c  mov     rcx, rsi
0x180011f9f  mov     rax, [rax]
0x180011fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa7  mov     ebx, eax
0x180011fa9  test    eax, eax
0x180011fab  jns     short loc_180011FCB
0x180011fad  mov     rcx, [rdi+58h]
0x180011fb1  test    rcx, rcx
0x180011fb4  jz      loc_1800122E4
0x180011fba  mov     [rsp+110h+var_E8], eax
0x180011fbe  mov     [rsp+110h+var_F0], 292h
0x180011fc6  jmp     loc_180011E39
0x180011fcb  mov     rax, [rsi]
0x180011fce  lea     r8, [rsp+110h+var_E0]
0x180011fd3  lea     rdx, aFlags; "Flags"
0x180011fda  mov     rcx, rsi
0x180011fdd  mov     rax, [rax]
0x180011fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fe5  mov     ebx, eax
0x180011fe7  test    eax, eax
0x180011fe9  jns     short loc_180012009
0x180011feb  mov     rcx, [rdi+58h]
0x180011fef  test    rcx, rcx
0x180011ff2  jz      loc_1800122E4
0x180011ff8  mov     [rsp+110h+var_E8], eax
0x180011ffc  mov     [rsp+110h+var_F0], 293h
0x180012004  jmp     loc_180011E39
0x180012009  mov     rax, [rsi]
0x18001200c  lea     r8, [rbp+57h+var_D4]
0x180012010  lea     rdx, aDeletesource; "DeleteSource"
0x180012017  mov     rcx, rsi
0x18001201a  mov     rax, [rax]
0x18001201d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012022  mov     ebx, eax
0x180012024  test    eax, eax
0x180012026  jns     short loc_180012046
0x180012028  mov     rcx, [rdi+58h]
0x18001202c  test    rcx, rcx
0x18001202f  jz      loc_1800122E4
0x180012035  mov     [rsp+110h+var_E8], eax
0x180012039  mov     [rsp+110h+var_F0], 294h
0x180012041  jmp     loc_180011E39
0x180012046  mov     rax, [rsi]
0x180012049  lea     r8, [rbp+57h+var_A8]
0x18001204d  lea     rdx, aWimfilesize; "WimFileSize"
0x180012054  mov     rcx, rsi
0x180012057  mov     rax, [rax+8]
0x18001205b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012060  mov     ebx, eax
0x180012062  test    eax, eax
0x180012064  jns     short loc_180012084
0x180012066  mov     rcx, [rdi+58h]
0x18001206a  test    rcx, rcx
0x18001206d  jz      loc_1800122E4
0x180012073  mov     [rsp+110h+var_E8], eax
0x180012077  mov     [rsp+110h+var_F0], 295h
0x18001207f  jmp     loc_180011E39
0x180012084  mov     rax, [rsi]
0x180012087  lea     r8, [rbp+57h+var_B8]
0x18001208b  lea     rdx, aWimtargetpath; "WimTargetPath"
0x180012092  mov     rcx, rsi
0x180012095  mov     rax, [rax+10h]
0x180012099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001209e  mov     ebx, eax
0x1800120a0  mov     r13d, 80000000h
0x1800120a6  add     eax, r13d
0x1800120a9  test    r13d, eax
0x1800120ac  jnz     short loc_1800120D4
0x1800120ae  cmp     ebx, 80070490h
0x1800120b4  jz      short loc_1800120D4
0x1800120b6  mov     rcx, [rdi+58h]
0x1800120ba  test    rcx, rcx
0x1800120bd  jz      loc_1800122E4
0x1800120c3  mov     [rsp+110h+var_E8], ebx
0x1800120c7  mov     [rsp+110h+var_F0], 299h
0x1800120cf  jmp     loc_180011E39
0x1800120d4  mov     rax, [rsi]
0x1800120d7  lea     r8, [rbp+57h+var_C0]
0x1800120db  lea     rdx, aRemotesourcepa; "RemoteSourcePath"
0x1800120e2  mov     rcx, rsi
0x1800120e5  mov     rax, [rax+10h]
0x1800120e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ee  mov     ebx, eax
0x1800120f0  add     eax, r13d
0x1800120f3  test    r13d, eax
0x1800120f6  jnz     short loc_18001211E
0x1800120f8  cmp     ebx, 80070490h
0x1800120fe  jz      short loc_18001211E
0x180012100  mov     rcx, [rdi+58h]
0x180012104  test    rcx, rcx
0x180012107  jz      loc_1800122E4
0x18001210d  mov     [rsp+110h+var_E8], ebx
0x180012111  mov     [rsp+110h+var_F0], 29Dh
0x180012119  jmp     loc_180011E39
0x18001211e  mov     rax, [rsi]
0x180012121  lea     r8, [rbp+57h+var_C8]
0x180012125  lea     rdx, aCryptokey; "CryptoKey"
0x18001212c  mov     rcx, rsi
0x18001212f  mov     rax, [rax+10h]
0x180012133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012138  mov     ebx, eax
0x18001213a  add     eax, r13d
0x18001213d  test    r13d, eax
0x180012140  jnz     short loc_180012168
0x180012142  cmp     ebx, 80070490h
0x180012148  jz      short loc_180012168
0x18001214a  mov     rcx, [rdi+58h]
0x18001214e  test    rcx, rcx
0x180012151  jz      loc_1800122E4
0x180012157  mov     [rsp+110h+var_E8], ebx
0x18001215b  mov     [rsp+110h+var_F0], 2A1h
0x180012163  jmp     loc_180011E39
0x180012168  mov     rax, [rsi]
0x18001216b  lea     r8, [rbp+57h+bstrString]
0x18001216f  lea     rdx, aFilehash; "FileHash"
0x180012176  mov     rcx, rsi
0x180012179  mov     rax, [rax+10h]
0x18001217d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012182  mov     ebx, eax
0x180012184  add     eax, r13d
0x180012187  test    r13d, eax
0x18001218a  jnz     short loc_1800121B2
0x18001218c  cmp     ebx, 80070490h
0x180012192  jz      short loc_1800121B2
0x180012194  mov     rcx, [rdi+58h]
0x180012198  test    rcx, rcx
0x18001219b  jz      loc_1800122E4
0x1800121a1  mov     [rsp+110h+var_E8], ebx
0x1800121a5  mov     [rsp+110h+var_F0], 2A5h
0x1800121ad  jmp     loc_180011E39
0x1800121b2  xor     eax, eax
0x1800121b4  mov     [rbp+57h+var_64], eax
0x1800121b7  mov     [rbp+57h+var_4C], eax
0x1800121ba  movups  xmm0, cs:WINDLP_ACTION_RECOVERCRYPTO
0x1800121c1  movdqu  [rbp+57h+var_A0], xmm0
0x1800121c6  mov     rax, [rbp+57h+var_B0]
0x1800121ca  mov     [rbp+57h+var_88], rax
0x1800121ce  mov     rax, [rbp+57h+var_B8]
0x1800121d2  mov     [rbp+57h+var_80], rax
0x1800121d6  mov     rax, [rbp+57h+var_C0]
0x1800121da  mov     [rbp+57h+var_70], rax
0x1800121de  mov     rax, [rbp+57h+var_A8]
0x1800121e2  mov     [rbp+57h+var_90], rax
0x1800121e6  mov     eax, [rsp+110h+var_E0]
0x1800121ea  mov     [rbp+57h+var_58], eax
0x1800121ed  mov     rax, [rbp+57h+var_C8]
0x1800121f1  mov     [rbp+57h+var_78], rax
0x1800121f5  mov     rax, [rbp+57h+bstrString]
0x1800121f9  mov     [rbp+57h+var_60], rax
0x1800121fd  mov     eax, [rsp+110h+var_DC]
0x180012201  mov     [rbp+57h+var_68], eax
0x180012204  mov     eax, [rsp+110h+var_D8]
0x180012208  mov     [rbp+57h+var_54], eax
0x18001220b  mov     eax, r12d
0x18001220e  cmp     [rbp+57h+var_D4], r12d
0x180012212  setnz   al
0x180012215  mov     [rbp+57h+var_50], eax
0x180012218  mov     rax, [rdi]
0x18001221b  mov     r8d, 58h ; 'X'
0x180012221  lea     rdx, [rbp+57h+var_A0]
0x180012225  mov     rcx, rdi
0x180012228  mov     rax, [rax+20h]
0x18001222c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012231  mov     ebx, eax
0x180012233  test    eax, eax
0x180012235  jns     short loc_180012255
0x180012237  mov     rcx, [rdi+58h]
0x18001223b  test    rcx, rcx
0x18001223e  jz      loc_1800122E4
0x180012244  mov     [rsp+110h+var_E8], eax
0x180012248  mov     [rsp+110h+var_F0], 2B6h
0x180012250  jmp     loc_180011E39
0x180012255  cmp     r15d, 4
0x180012259  jnz     loc_1800122E1
0x18001225f  mov     dword ptr [rdi+280h], 1
  ... truncated ...
```
