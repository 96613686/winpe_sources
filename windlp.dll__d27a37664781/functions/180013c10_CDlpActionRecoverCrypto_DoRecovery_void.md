# CDlpActionRecoverCrypto::DoRecovery(void)

- ea: `0x180013c10`
- end: `0x180013f31`
- name: `?DoRecovery@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `801`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013444`
- `0x1800165d0`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x180013c10`
- `0x18001fd60`
- `0x18002b900`
- `0x18002e31c`
- `0x18002e5ec`

## import_xrefs

- `WIMGAPI!WIMRegisterMessageCallback` at `0x180013cd6`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x180013cd6`
- `WIMGAPI!WIMCloseHandle` at `0x180013f19`
- `WIMGAPI!WIMCloseHandle` at `0x180013f19`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013de3`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013e59`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013de3`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180013e59`
- `WIMGAPI!WIMCreateFile` at `0x180013d82`
- `WIMGAPI!WIMCreateFile` at `0x180013d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionRecoverCrypto::DoRecovery(const unsigned __int16 **this)
{
  __int64 v2; // rbx
  int v3; // eax
  signed int v4; // edi
  const unsigned __int16 *v5; // rcx
  int v6; // eax
  int HasIntegrityData; // eax
  signed int LastError; // eax
  __int64 v9; // rcx
  int v10; // eax
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  signed int v13; // eax
  __int64 v14; // rcx
  signed int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-18h]
  __int64 v22; // [rsp+28h] [rbp-10h]
  int v23; // [rsp+48h] [rbp+10h] BYREF
  __int64 v24; // [rsp+50h] [rbp+18h]

  v2 = 0;
  v24 = 0;
  v23 = 0;
  v3 = CDlpActionRecoverCrypto::SetProgressRange((CDlpActionRecoverCrypto *)this, 0, 0xAu);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = this[11];
    if ( !v5 )
      goto LABEL_55;
    LODWORD(v22) = v3;
    LODWORD(v21) = 1769;
    goto LABEL_52;
  }
  v6 = CDlpActionRecoverCrypto::VerifyFileHash((CDlpActionRecoverCrypto *)this, &v23);
  v4 = v6;
  if ( v6 < 0 )
  {
    v5 = this[11];
    if ( !v5 )
      goto LABEL_55;
    LODWORD(v22) = v6;
    LODWORD(v21) = 1770;
    goto LABEL_52;
  }
  if ( v23 )
    goto LABEL_55;
  HasIntegrityData = CDlpActionRecoverCrypto::VerifyWimHasIntegrityData((CDlpActionRecoverCrypto *)this, this[69]);
  v4 = HasIntegrityData;
  if ( HasIntegrityData < 0 )
  {
    v5 = this[11];
    if ( !v5 )
      goto LABEL_55;
    LODWORD(v22) = HasIntegrityData;
    LODWORD(v21) = 1778;
    goto LABEL_52;
  }
  if ( (unsigned int)WIMRegisterMessageCallback(0, CDlpActionRecoverCrypto::WimCallback, this) == -1 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( this[11] )
    {
      v9 = 0;
      if ( v4 >= 0 )
      {
LABEL_54:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
        goto LABEL_55;
      }
      LODWORD(v22) = v4;
      LODWORD(v21) = 1780;
      v5 = this[11];
LABEL_52:
      v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v5,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionRecoverCrypto::DoRecovery",
              v21,
              v22);
      v9 = (unsigned int)v19;
      if ( v19 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v19);
      goto LABEL_54;
    }
    goto LABEL_55;
  }
  v10 = CDlpActionRecoverCrypto::SetProgressRange((CDlpActionRecoverCrypto *)this, 0xAu, 0x5Au);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = this[11];
    if ( !v11 )
    {
LABEL_42:
      WIMUnregisterMessageCallback(0, CDlpActionRecoverCrypto::WimCallback);
      goto LABEL_55;
    }
    LODWORD(v22) = v10;
    LODWORD(v21) = 1782;
    goto LABEL_39;
  }
  v12 = WIMCreateFile(this[69], 0, 3, 536870978, 0, 0);
  v2 = v12;
  if ( !v12 )
  {
    v24 = 0;
    v13 = GetLastError();
    v4 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v4 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( !this[11] )
      goto LABEL_42;
    v14 = 0;
    if ( v4 >= 0 )
      goto LABEL_41;
    LODWORD(v22) = v4;
    LODWORD(v21) = 1789;
LABEL_38:
    v11 = this[11];
LABEL_39:
    v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v11,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionRecoverCrypto::DoRecovery",
            v21,
            v22);
    v14 = (unsigned int)v16;
    if ( v16 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
LABEL_41:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
    goto LABEL_42;
  }
  v24 = v12;
  if ( !(unsigned int)WIMUnregisterMessageCallback(0, CDlpActionRecoverCrypto::WimCallback) )
  {
    v15 = GetLastError();
    v4 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v4 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( !this[11] )
      goto LABEL_42;
    v14 = 0;
    if ( v4 >= 0 )
      goto LABEL_41;
    LODWORD(v22) = v4;
    LODWORD(v21) = 1791;
    goto LABEL_38;
  }
  v17 = CDlpActionRecoverCrypto::SetProgressRange((CDlpActionRecoverCrypto *)this, 0x5Au, 0x64u);
  v4 = v17;
  if ( v17 < 0 )
  {
    v5 = this[11];
    if ( !v5 )
      goto LABEL_55;
    LODWORD(v22) = v17;
    LODWORD(v21) = 1796;
    goto LABEL_52;
  }
  v18 = CDlpActionRecoverCrypto::VerifyFileHash((CDlpActionRecoverCrypto *)this, &v23);
  v4 = v18;
  if ( v18 < 0 )
  {
    v5 = this[11];
    if ( !v5 )
      goto LABEL_55;
    LODWORD(v22) = v18;
    LODWORD(v21) = 1797;
    goto LABEL_52;
  }
  if ( !v23 )
  {
    v4 = -2147023504;
    v5 = this[11];
    if ( v5 )
    {
      LODWORD(v22) = -2147023504;
      LODWORD(v21) = 1801;
      goto LABEL_52;
    }
  }
LABEL_55:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v2 )
    WIMCloseHandle(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013c10  mov     rax, rsp
0x180013c13  mov     [rax+8], rbx
0x180013c17  mov     [rax+20h], rsi
0x180013c1b  push    rdi
0x180013c1c  sub     rsp, 30h
0x180013c20  mov     rsi, rcx
0x180013c23  xor     ebx, ebx
0x180013c25  mov     [rax+18h], rbx
0x180013c29  mov     [rax+10h], ebx
0x180013c2c  xor     edx, edx; unsigned int
0x180013c2e  lea     r8d, [rbx+0Ah]; unsigned int
0x180013c32  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013c37  mov     edi, eax
0x180013c39  test    eax, eax
0x180013c3b  jns     short loc_180013C5B
0x180013c3d  mov     rcx, [rsi+58h]
0x180013c41  test    rcx, rcx
0x180013c44  jz      loc_180013F09
0x180013c4a  mov     dword ptr [rsp+38h+var_10], eax
0x180013c4e  mov     dword ptr [rsp+38h+var_18], 6E9h
0x180013c56  jmp     loc_180013EE1
0x180013c5b  lea     rdx, [rsp+38h+arg_8]; int *
0x180013c60  mov     rcx, rsi; this
0x180013c63  call    ?VerifyFileHash@CDlpActionRecoverCrypto@@AEAAJPEAH@Z; CDlpActionRecoverCrypto::VerifyFileHash(int *)
0x180013c68  mov     edi, eax
0x180013c6a  test    eax, eax
0x180013c6c  jns     short loc_180013C8C
0x180013c6e  mov     rcx, [rsi+58h]
0x180013c72  test    rcx, rcx
0x180013c75  jz      loc_180013F09
0x180013c7b  mov     dword ptr [rsp+38h+var_10], eax
0x180013c7f  mov     dword ptr [rsp+38h+var_18], 6EAh
0x180013c87  jmp     loc_180013EE1
0x180013c8c  cmp     [rsp+38h+arg_8], 0
0x180013c91  jnz     loc_180013F09
0x180013c97  mov     rdx, [rsi+228h]; unsigned __int16 *
0x180013c9e  mov     rcx, rsi; this
0x180013ca1  call    ?VerifyWimHasIntegrityData@CDlpActionRecoverCrypto@@AEAAJPEBG@Z; CDlpActionRecoverCrypto::VerifyWimHasIntegrityData(ushort const *)
0x180013ca6  mov     edi, eax
0x180013ca8  test    eax, eax
0x180013caa  jns     short loc_180013CCA
0x180013cac  mov     rcx, [rsi+58h]
0x180013cb0  test    rcx, rcx
0x180013cb3  jz      loc_180013F09
0x180013cb9  mov     dword ptr [rsp+38h+var_10], eax
0x180013cbd  mov     dword ptr [rsp+38h+var_18], 6F2h
0x180013cc5  jmp     loc_180013EE1
0x180013cca  mov     r8, rsi
0x180013ccd  lea     rdx, ?WimCallback@CDlpActionRecoverCrypto@@SAKK_K_JPEAX@Z; CDlpActionRecoverCrypto::WimCallback(ulong,unsigned __int64,__int64,void *)
0x180013cd4  xor     ecx, ecx
0x180013cd6  call    cs:__imp_WIMRegisterMessageCallback
0x180013cdc  cmp     eax, 0FFFFFFFFh
0x180013cdf  jnz     short loc_180013D29
0x180013ce1  call    cs:__imp_GetLastError
0x180013ce7  mov     edi, eax
0x180013ce9  test    eax, eax
0x180013ceb  jnz     short loc_180013CF4
0x180013ced  mov     edi, 80004005h
0x180013cf2  jmp     short loc_180013CFF
0x180013cf4  jle     short loc_180013CFF
0x180013cf6  movzx   edi, ax
0x180013cf9  or      edi, 80070000h
0x180013cff  cmp     qword ptr [rsi+58h], 0
0x180013d04  jz      loc_180013F09
0x180013d0a  xor     ecx, ecx
0x180013d0c  test    edi, edi
0x180013d0e  jns     loc_180013F04
0x180013d14  mov     dword ptr [rsp+38h+var_10], edi
0x180013d18  mov     dword ptr [rsp+38h+var_18], 6F4h
0x180013d20  mov     rcx, [rsi+58h]
0x180013d24  jmp     loc_180013EE1
0x180013d29  mov     edx, 0Ah; unsigned int
0x180013d2e  lea     r8d, [rdx+50h]; unsigned int
0x180013d32  mov     rcx, rsi; this
0x180013d35  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013d3a  mov     edi, eax
0x180013d3c  test    eax, eax
0x180013d3e  jns     short loc_180013D5E
0x180013d40  mov     rcx, [rsi+58h]
0x180013d44  test    rcx, rcx
0x180013d47  jz      loc_180013E50
0x180013d4d  mov     dword ptr [rsp+38h+var_10], eax
0x180013d51  mov     dword ptr [rsp+38h+var_18], 6F6h
0x180013d59  jmp     loc_180013E28
0x180013d5e  mov     [rsp+38h+var_10], 0
0x180013d67  mov     dword ptr [rsp+38h+var_18], 0
0x180013d6f  xor     edx, edx
0x180013d71  mov     r9d, 20000042h
0x180013d77  lea     r8d, [rdx+3]
0x180013d7b  mov     rcx, [rsi+228h]
0x180013d82  call    cs:__imp_WIMCreateFile
0x180013d88  mov     rbx, rax
0x180013d8b  test    rax, rax
0x180013d8e  jnz     short loc_180013DD5
0x180013d90  mov     [rsp+38h+arg_10], rax
0x180013d95  call    cs:__imp_GetLastError
0x180013d9b  mov     edi, eax
0x180013d9d  test    eax, eax
0x180013d9f  jnz     short loc_180013DA8
0x180013da1  mov     edi, 80004005h
0x180013da6  jmp     short loc_180013DB3
0x180013da8  jle     short loc_180013DB3
0x180013daa  movzx   edi, ax
0x180013dad  or      edi, 80070000h
0x180013db3  cmp     [rsi+58h], rbx
0x180013db7  jz      loc_180013E50
0x180013dbd  xor     ecx, ecx
0x180013dbf  test    edi, edi
0x180013dc1  jns     loc_180013E4B
0x180013dc7  mov     dword ptr [rsp+38h+var_10], edi
0x180013dcb  mov     dword ptr [rsp+38h+var_18], 6FDh
0x180013dd3  jmp     short loc_180013E24
0x180013dd5  mov     [rsp+38h+arg_10], rax
0x180013dda  lea     rdx, ?WimCallback@CDlpActionRecoverCrypto@@SAKK_K_JPEAX@Z; CDlpActionRecoverCrypto::WimCallback(ulong,unsigned __int64,__int64,void *)
0x180013de1  xor     ecx, ecx
0x180013de3  call    cs:__imp_WIMUnregisterMessageCallback
0x180013de9  test    eax, eax
0x180013deb  jnz     short loc_180013E64
0x180013ded  call    cs:__imp_GetLastError
0x180013df3  mov     edi, eax
0x180013df5  test    eax, eax
0x180013df7  jnz     short loc_180013E00
0x180013df9  mov     edi, 80004005h
0x180013dfe  jmp     short loc_180013E0B
0x180013e00  jle     short loc_180013E0B
0x180013e02  movzx   edi, ax
0x180013e05  or      edi, 80070000h
0x180013e0b  cmp     qword ptr [rsi+58h], 0
0x180013e10  jz      short loc_180013E50
0x180013e12  xor     ecx, ecx
0x180013e14  test    edi, edi
0x180013e16  jns     short loc_180013E4B
0x180013e18  mov     dword ptr [rsp+38h+var_10], edi
0x180013e1c  mov     dword ptr [rsp+38h+var_18], 6FFh
0x180013e24  mov     rcx, [rsi+58h]
0x180013e28  lea     r9, aCdlpactionreco_16; "CDlpActionRecoverCrypto::DoRecovery"
0x180013e2f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180013e36  mov     edx, 4
0x180013e3b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180013e40  mov     ecx, eax
0x180013e42  test    eax, eax
0x180013e44  jns     short loc_180013E4B
0x180013e46  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013e4b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013e50  lea     rdx, ?WimCallback@CDlpActionRecoverCrypto@@SAKK_K_JPEAX@Z; CDlpActionRecoverCrypto::WimCallback(ulong,unsigned __int64,__int64,void *)
0x180013e57  xor     ecx, ecx
0x180013e59  call    cs:__imp_WIMUnregisterMessageCallback
0x180013e5f  jmp     loc_180013F09
0x180013e64  mov     edx, 5Ah ; 'Z'; unsigned int
0x180013e69  lea     r8d, [rdx+0Ah]; unsigned int
0x180013e6d  mov     rcx, rsi; this
0x180013e70  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013e75  mov     edi, eax
0x180013e77  test    eax, eax
0x180013e79  jns     short loc_180013E96
0x180013e7b  mov     rcx, [rsi+58h]
0x180013e7f  test    rcx, rcx
0x180013e82  jz      loc_180013F09
0x180013e88  mov     dword ptr [rsp+38h+var_10], eax
0x180013e8c  mov     dword ptr [rsp+38h+var_18], 704h
0x180013e94  jmp     short loc_180013EE1
0x180013e96  lea     rdx, [rsp+38h+arg_8]; int *
0x180013e9b  mov     rcx, rsi; this
0x180013e9e  call    ?VerifyFileHash@CDlpActionRecoverCrypto@@AEAAJPEAH@Z; CDlpActionRecoverCrypto::VerifyFileHash(int *)
0x180013ea3  mov     edi, eax
0x180013ea5  test    eax, eax
0x180013ea7  jns     short loc_180013EC0
0x180013ea9  mov     rcx, [rsi+58h]
0x180013ead  test    rcx, rcx
0x180013eb0  jz      short loc_180013F09
0x180013eb2  mov     dword ptr [rsp+38h+var_10], eax
0x180013eb6  mov     dword ptr [rsp+38h+var_18], 705h
0x180013ebe  jmp     short loc_180013EE1
0x180013ec0  cmp     [rsp+38h+arg_8], 0
0x180013ec5  jnz     short loc_180013F09
0x180013ec7  mov     edi, 80070570h
0x180013ecc  mov     rcx, [rsi+58h]
0x180013ed0  test    rcx, rcx
0x180013ed3  jz      short loc_180013F09
0x180013ed5  mov     dword ptr [rsp+38h+var_10], edi
0x180013ed9  mov     dword ptr [rsp+38h+var_18], 709h
0x180013ee1  lea     r9, aCdlpactionreco_16; "CDlpActionRecoverCrypto::DoRecovery"
0x180013ee8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180013eef  mov     edx, 4
0x180013ef4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180013ef9  mov     ecx, eax
0x180013efb  test    eax, eax
0x180013efd  jns     short loc_180013F04
0x180013eff  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013f04  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013f09  mov     ecx, edi
0x180013f0b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013f10  nop
0x180013f11  test    rbx, rbx
0x180013f14  jz      short loc_180013F1F
0x180013f16  mov     rcx, rbx
0x180013f19  call    cs:__imp_WIMCloseHandle
0x180013f1f  mov     eax, edi
0x180013f21  mov     rbx, [rsp+38h+arg_0]
0x180013f26  mov     rsi, [rsp+38h+arg_18]
0x180013f2b  add     rsp, 30h
0x180013f2f  pop     rdi
0x180013f30  retn
```
