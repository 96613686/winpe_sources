# CDlpActionRecoverCrypto::DoFullEncryption(ushort const *,ushort const *)

- ea: `0x180013918`
- end: `0x180013c0a`
- name: `?DoFullEncryption@CDlpActionRecoverCrypto@@AEAAJPEBG0@Z`
- size: `754`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000fb18`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x180013918`
- `0x18001fd60`
- `0x18002b900`
- `0x18002e31c`

## import_xrefs

- `WIMGAPI!WIMRegisterMessageCallback` at `0x180013a05`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x180013a05`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013ac5`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013b3b`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013ac5`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013b3b`
- `WIMGAPI!WIMCopyFile` at `0x180013a75`
- `WIMGAPI!WIMCopyFile` at `0x180013a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013acf`

## string_xrefs

- `0x180013be7`: `RecoverCrypto: Decrypted ESD path [%s]`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::DoFullEncryption(
        CDlpActionRecoverCrypto *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  signed int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  __int64 v14; // rcx
  signed int LastError; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v21; // [rsp+20h] [rbp-38h]
  __int64 v22; // [rsp+28h] [rbp-30h]
  int v23; // [rsp+70h] [rbp+18h] BYREF

  v23 = 0;
  if ( !a3 )
  {
    v6 = *((_QWORD *)this + 11);
    v7 = -2147024809;
    if ( v6 )
    {
      LODWORD(v22) = -2147024809;
      LODWORD(v21) = 1467;
      goto LABEL_4;
    }
    goto LABEL_55;
  }
  if ( (*((_BYTE *)this + 632) & 1) != 0 )
  {
    v10 = CDlpActionRecoverCrypto::SetProgressRange(this, 0, 0x5Au);
    v7 = v10;
    if ( v10 < 0 )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_55;
      LODWORD(v22) = v10;
      LODWORD(v21) = 1475;
      goto LABEL_4;
    }
  }
  else
  {
    v11 = CDlpActionRecoverCrypto::SetProgressRange(this, 0, 0x64u);
    v7 = v11;
    if ( v11 < 0 )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_55;
      LODWORD(v22) = v11;
      LODWORD(v21) = 1479;
      goto LABEL_4;
    }
    *((_DWORD *)this + 135) = 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v7 = 0;
  }
  if ( (unsigned int)WIMRegisterMessageCallback(0, CDlpActionRecoverCrypto::WimCallback, this) != -1 )
  {
    if ( (unsigned int)WIMCopyFile(a2, a3, 0, 0, 0, 0) )
    {
      if ( (unsigned int)WIMUnregisterMessageCallback(0, CDlpActionRecoverCrypto::WimCallback) )
      {
        if ( (*((_BYTE *)this + 632) & 1) != 0 )
        {
          v17 = CDlpActionRecoverCrypto::SetProgressRange(this, 0x5Au, 0x64u);
          v7 = v17;
          if ( v17 < 0 )
          {
            v6 = *((_QWORD *)this + 11);
            if ( !v6 )
              goto LABEL_55;
            LODWORD(v22) = v17;
            LODWORD(v21) = 1497;
            goto LABEL_4;
          }
          v18 = CDlpActionRecoverCrypto::VerifyFileHash(this, &v23);
          v7 = v18;
          if ( v18 < 0 )
          {
            v6 = *((_QWORD *)this + 11);
            if ( !v6 )
              goto LABEL_55;
            LODWORD(v22) = v18;
            LODWORD(v21) = 1498;
            goto LABEL_4;
          }
          if ( !v23 )
          {
            v6 = *((_QWORD *)this + 11);
            v7 = -2147023504;
            if ( !v6 )
              goto LABEL_55;
            LODWORD(v22) = -2147023504;
            LODWORD(v21) = 1505;
            goto LABEL_4;
          }
        }
        v19 = *((_QWORD *)this + 11);
        if ( v19 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v19, 2u, (__int64)L"RecoverCrypto: Decrypted ESD path [%s]", a3);
        goto LABEL_55;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
      {
LABEL_42:
        WIMUnregisterMessageCallback(0, CDlpActionRecoverCrypto::WimCallback);
        goto LABEL_55;
      }
      v14 = 0;
      if ( v7 >= 0 )
      {
LABEL_41:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
        goto LABEL_42;
      }
      LODWORD(v22) = v7;
      LODWORD(v21) = 1489;
    }
    else
    {
      v13 = GetLastError();
      v7 = v13;
      if ( v13 )
      {
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_42;
      v14 = 0;
      if ( v7 >= 0 )
        goto LABEL_41;
      LODWORD(v22) = v7;
      LODWORD(v21) = 1488;
    }
    v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
            *((_QWORD *)this + 11),
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpActionRecoverCrypto::DoFullEncryption",
            v21,
            v22);
    v14 = (unsigned int)v16;
    if ( v16 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    goto LABEL_41;
  }
  v12 = GetLastError();
  v7 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
  }
  else
  {
    v7 = -2147467259;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v9 = 0;
    if ( v7 >= 0 )
    {
LABEL_6:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
      goto LABEL_55;
    }
    v6 = *((_QWORD *)this + 11);
    LODWORD(v22) = v7;
    LODWORD(v21) = 1486;
LABEL_4:
    v8 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v6,
           4u,
           (__int64)L"%s(%d): Result = 0x%X",
           L"CDlpActionRecoverCrypto::DoFullEncryption",
           v21,
           v22);
    v9 = (unsigned int)v8;
    if ( v8 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_6;
  }
LABEL_55:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013918  push    rbx
0x18001391a  push    rbp
0x18001391b  push    rsi
0x18001391c  push    rdi
0x18001391d  sub     rsp, 38h
0x180013921  mov     [rsp+58h+arg_10], 0
0x180013929  mov     rsi, r8
0x18001392c  mov     rbp, rdx
0x18001392f  mov     rdi, rcx
0x180013932  test    r8, r8
0x180013935  jnz     short loc_180013982
0x180013937  mov     rcx, [rcx+58h]
0x18001393b  mov     ebx, 80070057h
0x180013940  test    rcx, rcx
0x180013943  jz      loc_180013BF8
0x180013949  mov     dword ptr [rsp+58h+var_30], ebx
0x18001394d  mov     dword ptr [rsp+58h+var_38], 5BBh
0x180013955  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001395c  mov     edx, 4
0x180013961  lea     r9, aCdlpactionreco_1; "CDlpActionRecoverCrypto::DoFullEncrypti"...
0x180013968  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001396d  mov     ecx, eax
0x18001396f  test    eax, eax
0x180013971  jns     short loc_180013978
0x180013973  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013978  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001397d  jmp     loc_180013BF8
0x180013982  xor     edx, edx; unsigned int
0x180013984  test    byte ptr [rcx+278h], 1
0x18001398b  jz      short loc_1800139B7
0x18001398d  lea     r8d, [rdx+5Ah]; unsigned int
0x180013991  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013996  mov     ebx, eax
0x180013998  test    eax, eax
0x18001399a  jns     short loc_1800139F9
0x18001399c  mov     rcx, [rdi+58h]; this
0x1800139a0  test    rcx, rcx
0x1800139a3  jz      loc_180013BF8
0x1800139a9  mov     dword ptr [rsp+58h+var_30], eax
0x1800139ad  mov     dword ptr [rsp+58h+var_38], 5C3h
0x1800139b5  jmp     short loc_180013955
0x1800139b7  mov     r8d, 64h ; 'd'; unsigned int
0x1800139bd  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x1800139c2  mov     ebx, eax
0x1800139c4  test    eax, eax
0x1800139c6  jns     short loc_1800139E6
0x1800139c8  mov     rcx, [rdi+58h]
0x1800139cc  test    rcx, rcx
0x1800139cf  jz      loc_180013BF8
0x1800139d5  mov     dword ptr [rsp+58h+var_30], eax
0x1800139d9  mov     dword ptr [rsp+58h+var_38], 5C7h
0x1800139e1  jmp     loc_180013955
0x1800139e6  mov     dword ptr [rdi+21Ch], 1
0x1800139f0  xor     ecx, ecx
0x1800139f2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800139f7  xor     ebx, ebx
0x1800139f9  mov     r8, rdi
0x1800139fc  lea     rdx, ?WimCallback@CDlpActionRecoverCrypto@@SAKK_K_JPEAX@Z; CDlpActionRecoverCrypto::WimCallback(ulong,unsigned __int64,__int64,void *)
0x180013a03  xor     ecx, ecx
0x180013a05  call    cs:__imp_WIMRegisterMessageCallback
0x180013a0b  cmp     eax, 0FFFFFFFFh
0x180013a0e  jnz     short loc_180013A58
0x180013a10  call    cs:__imp_GetLastError
0x180013a16  mov     ebx, eax
0x180013a18  test    eax, eax
0x180013a1a  jnz     short loc_180013A23
0x180013a1c  mov     ebx, 80004005h
0x180013a21  jmp     short loc_180013A2E
0x180013a23  jle     short loc_180013A2E
0x180013a25  movzx   ebx, ax
0x180013a28  or      ebx, 80070000h
0x180013a2e  cmp     qword ptr [rdi+58h], 0
0x180013a33  jz      loc_180013BF8
0x180013a39  xor     ecx, ecx
0x180013a3b  test    ebx, ebx
0x180013a3d  jns     loc_180013978
0x180013a43  mov     rcx, [rdi+58h]
0x180013a47  mov     dword ptr [rsp+58h+var_30], ebx
0x180013a4b  mov     dword ptr [rsp+58h+var_38], 5CEh
0x180013a53  jmp     loc_180013955
0x180013a58  mov     dword ptr [rsp+58h+var_30], 0
0x180013a60  xor     r9d, r9d
0x180013a63  xor     r8d, r8d
0x180013a66  mov     [rsp+58h+var_38], 0
0x180013a6f  mov     rdx, rsi
0x180013a72  mov     rcx, rbp
0x180013a75  call    cs:__imp_WIMCopyFile
0x180013a7b  test    eax, eax
0x180013a7d  jnz     short loc_180013ABC
0x180013a7f  call    cs:__imp_GetLastError
0x180013a85  mov     ebx, eax
0x180013a87  test    eax, eax
0x180013a89  jnz     short loc_180013A92
0x180013a8b  mov     ebx, 80004005h
0x180013a90  jmp     short loc_180013A9D
0x180013a92  jle     short loc_180013A9D
0x180013a94  movzx   ebx, ax
0x180013a97  or      ebx, 80070000h
0x180013a9d  cmp     qword ptr [rdi+58h], 0
0x180013aa2  jz      loc_180013B32
0x180013aa8  xor     ecx, ecx
0x180013aaa  test    ebx, ebx
0x180013aac  jns     short loc_180013B2D
0x180013aae  mov     dword ptr [rsp+58h+var_30], ebx
0x180013ab2  mov     dword ptr [rsp+58h+var_38], 5D0h
0x180013aba  jmp     short loc_180013B06
0x180013abc  lea     rdx, ?WimCallback@CDlpActionRecoverCrypto@@SAKK_K_JPEAX@Z; CDlpActionRecoverCrypto::WimCallback(ulong,unsigned __int64,__int64,void *)
0x180013ac3  xor     ecx, ecx
0x180013ac5  call    cs:__imp_WIMUnregisterMessageCallback
0x180013acb  test    eax, eax
0x180013acd  jnz     short loc_180013B46
0x180013acf  call    cs:__imp_GetLastError
0x180013ad5  mov     ebx, eax
0x180013ad7  test    eax, eax
0x180013ad9  jnz     short loc_180013AE2
0x180013adb  mov     ebx, 80004005h
0x180013ae0  jmp     short loc_180013AED
0x180013ae2  jle     short loc_180013AED
0x180013ae4  movzx   ebx, ax
0x180013ae7  or      ebx, 80070000h
0x180013aed  cmp     qword ptr [rdi+58h], 0
0x180013af2  jz      short loc_180013B32
0x180013af4  xor     ecx, ecx
0x180013af6  test    ebx, ebx
0x180013af8  jns     short loc_180013B2D
0x180013afa  mov     dword ptr [rsp+58h+var_30], ebx
0x180013afe  mov     dword ptr [rsp+58h+var_38], 5D1h
0x180013b06  mov     rcx, [rdi+58h]
0x180013b0a  lea     r9, aCdlpactionreco_1; "CDlpActionRecoverCrypto::DoFullEncrypti"...
0x180013b11  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180013b18  mov     edx, 4
0x180013b1d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180013b22  mov     ecx, eax
0x180013b24  test    eax, eax
0x180013b26  jns     short loc_180013B2D
0x180013b28  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013b2d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013b32  lea     rdx, ?WimCallback@CDlpActionRecoverCrypto@@SAKK_K_JPEAX@Z; CDlpActionRecoverCrypto::WimCallback(ulong,unsigned __int64,__int64,void *)
0x180013b39  xor     ecx, ecx
0x180013b3b  call    cs:__imp_WIMUnregisterMessageCallback
0x180013b41  jmp     loc_180013BF8
0x180013b46  test    byte ptr [rdi+278h], 1
0x180013b4d  jz      loc_180013BDB
0x180013b53  mov     edx, 5Ah ; 'Z'; unsigned int
0x180013b58  mov     rcx, rdi; this
0x180013b5b  lea     r8d, [rdx+0Ah]; unsigned int
0x180013b5f  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013b64  mov     ebx, eax
0x180013b66  test    eax, eax
0x180013b68  jns     short loc_180013B88
0x180013b6a  mov     rcx, [rdi+58h]
0x180013b6e  test    rcx, rcx
0x180013b71  jz      loc_180013BF8
0x180013b77  mov     dword ptr [rsp+58h+var_30], eax
0x180013b7b  mov     dword ptr [rsp+58h+var_38], 5D9h
0x180013b83  jmp     loc_180013955
0x180013b88  lea     rdx, [rsp+58h+arg_10]; int *
0x180013b8d  mov     rcx, rdi; this
0x180013b90  call    ?VerifyFileHash@CDlpActionRecoverCrypto@@AEAAJPEAH@Z; CDlpActionRecoverCrypto::VerifyFileHash(int *)
0x180013b95  mov     ebx, eax
0x180013b97  test    eax, eax
0x180013b99  jns     short loc_180013BB5
0x180013b9b  mov     rcx, [rdi+58h]
0x180013b9f  test    rcx, rcx
0x180013ba2  jz      short loc_180013BF8
0x180013ba4  mov     dword ptr [rsp+58h+var_30], eax
0x180013ba8  mov     dword ptr [rsp+58h+var_38], 5DAh
0x180013bb0  jmp     loc_180013955
0x180013bb5  cmp     [rsp+58h+arg_10], 0
0x180013bba  jnz     short loc_180013BDB
0x180013bbc  mov     rcx, [rdi+58h]
0x180013bc0  mov     ebx, 80070570h
0x180013bc5  test    rcx, rcx
0x180013bc8  jz      short loc_180013BF8
0x180013bca  mov     dword ptr [rsp+58h+var_30], ebx
0x180013bce  mov     dword ptr [rsp+58h+var_38], 5E1h
0x180013bd6  jmp     loc_180013955
0x180013bdb  mov     rcx, [rdi+58h]
0x180013bdf  test    rcx, rcx
0x180013be2  jz      short loc_180013BF8
0x180013be4  mov     r9, rsi
0x180013be7  lea     r8, aRecovercryptoD_0; "RecoverCrypto: Decrypted ESD path [%s]"
0x180013bee  mov     edx, 2
0x180013bf3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180013bf8  mov     ecx, ebx
0x180013bfa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013bff  mov     eax, ebx
0x180013c01  add     rsp, 38h
0x180013c05  pop     rdi
0x180013c06  pop     rsi
0x180013c07  pop     rbp
0x180013c08  pop     rbx
0x180013c09  retn
```
