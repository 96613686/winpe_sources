# CDlpActionRecoverCrypto::DoFastEncryption(void)

- ea: `0x180013444`
- end: `0x180013910`
- name: `?DoFastEncryption@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `1228`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000fb18`

## callees

- `0x18000aba4`
- `0x18000b3cc`
- `0x180012f5c`
- `0x180013444`
- `0x180013c10`
- `0x18001455c`
- `0x18001875c`
- `0x18001c9d0`
- `0x18001fd60`
- `0x180028a30`
- `0x18002b900`
- `0x18002bc30`
- `0x18002e31c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800138df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800138df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800138ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800138ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001385c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001385c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180013852`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180013852`

## string_xrefs

- `0x1800138c1`: `RecoverCrypto: Decrypted ESD path [%s]`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::DoFastEncryption(CDlpActionRecoverCrypto *this)
{
  unsigned __int16 *v2; // r14
  int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  int TempDir; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 *v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  int CryptoArray; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const WCHAR *v29; // rdx
  signed int LastError; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  HANDLE ProcessHeap; // rax
  __int64 v35; // [rsp+20h] [rbp-28h]
  int v36; // [rsp+20h] [rbp-28h]
  __int64 v37; // [rsp+28h] [rbp-20h]
  int v38; // [rsp+28h] [rbp-20h]
  int v39; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 *v40; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v40 = 0;
  v39 = 0;
  if ( (*((_BYTE *)this + 632) & 1) == 0 || *((_DWORD *)this + 160) )
    goto LABEL_18;
  v3 = CDlpActionRecoverCrypto::DoRecovery(this);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_81;
    v38 = v3;
    v36 = 1358;
    goto LABEL_6;
  }
  v8 = CDlpActionRecoverCrypto::SetProgressRange(this, 0, 0x50u);
  v4 = v8;
  if ( v8 >= 0 )
  {
    v9 = CDlpActionRecoverCrypto::VerifyFileHash(this, &v39);
    v4 = v9;
    if ( v9 < 0 )
    {
      v5 = *((_QWORD *)this + 11);
      if ( !v5 )
        goto LABEL_81;
      v38 = v9;
      v36 = 1364;
      goto LABEL_6;
    }
    if ( !v39 )
    {
      v4 = -2147023504;
      v5 = *((_QWORD *)this + 11);
      if ( !v5 )
        goto LABEL_81;
      v38 = -2147023504;
      v36 = 1371;
      goto LABEL_6;
    }
LABEL_18:
    if ( *((_DWORD *)this + 176) && !*((_DWORD *)this + 160) )
    {
      TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v40);
      v4 = TempDir;
      if ( TempDir < 0 )
      {
        v11 = *((_QWORD *)this + 11);
        if ( v11 )
        {
          v12 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v11,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionRecoverCrypto::DoFastEncryption",
                  1380,
                  TempDir);
          v13 = (unsigned int)v12;
          if ( v12 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
        }
        v2 = v40;
        goto LABEL_81;
      }
      v2 = v40;
      v14 = CDlpActionRecoverCrypto::SetupWimIoCallbacks(this, 1, v40);
      v4 = v14;
      if ( v14 < 0 )
      {
        v5 = *((_QWORD *)this + 11);
        if ( !v5 )
          goto LABEL_81;
        v38 = v14;
        v36 = 1382;
        goto LABEL_6;
      }
      if ( (*((_BYTE *)this + 632) & 1) != 0 )
      {
        v15 = CDlpActionRecoverCrypto::SetProgressRange(this, 0x50u, 0x5Au);
        if ( v15 < 0 )
        {
          v16 = (__int64 *)((char *)this + 88);
          v17 = *((_QWORD *)this + 11);
          if ( !v17 )
            goto LABEL_51;
          LODWORD(v37) = v15;
          LODWORD(v35) = 1389;
          goto LABEL_48;
        }
      }
      else
      {
        v18 = CDlpActionRecoverCrypto::SetProgressRange(this, 0, 0x32u);
        if ( v18 < 0 )
        {
          v16 = (__int64 *)((char *)this + 88);
          v17 = *((_QWORD *)this + 11);
          if ( !v17 )
            goto LABEL_51;
          LODWORD(v37) = v18;
          LODWORD(v35) = 1393;
          goto LABEL_48;
        }
      }
      CryptoArray = CDlpActionRecoverCrypto::GenerateCryptoArray(this);
      if ( CryptoArray < 0 )
      {
        v16 = (__int64 *)((char *)this + 88);
        v17 = *((_QWORD *)this + 11);
        if ( !v17 )
          goto LABEL_51;
        LODWORD(v37) = CryptoArray;
        LODWORD(v35) = 1398;
        goto LABEL_48;
      }
      if ( *((int *)this + 155) <= 0 )
      {
        v16 = (__int64 *)((char *)this + 88);
        v17 = *((_QWORD *)this + 11);
        if ( !v17 )
          goto LABEL_51;
        LODWORD(v37) = -2147024664;
        LODWORD(v35) = 1402;
        goto LABEL_48;
      }
      v20 = CDlpActionRecoverCrypto::SaveEncryptedRangesToWim(this);
      if ( v20 < 0 )
      {
        v16 = (__int64 *)((char *)this + 88);
        v17 = *((_QWORD *)this + 11);
        if ( !v17 )
          goto LABEL_51;
        LODWORD(v37) = v20;
        LODWORD(v35) = 1406;
        goto LABEL_48;
      }
      v21 = CDlpActionRecoverCrypto::SetupWimIoCallbacks(this, 0, 0);
      if ( v21 < 0 )
      {
        v16 = (__int64 *)((char *)this + 88);
        v17 = *((_QWORD *)this + 11);
        if ( !v17 )
          goto LABEL_51;
        LODWORD(v37) = v21;
        LODWORD(v35) = 1408;
LABEL_48:
        v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v17,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::DoFastEncryption",
                v35,
                v37);
        v23 = (unsigned int)v22;
        if ( v22 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v22);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
LABEL_51:
        while ( 1 )
        {
          v24 = CDlpActionRecoverCrypto::SetupWimIoCallbacks(this, 0, 0);
          v4 = v24;
          if ( v24 >= 0 )
            goto LABEL_81;
          v17 = *v16;
          if ( *v16 )
          {
            LODWORD(v37) = v24;
            LODWORD(v35) = 1447;
            goto LABEL_48;
          }
        }
      }
    }
    if ( (*((_BYTE *)this + 632) & 1) != 0 )
    {
      v25 = CDlpActionRecoverCrypto::SetProgressRange(this, 0x5Au, 0x64u);
      v4 = v25;
      if ( v25 < 0 )
      {
        v5 = *((_QWORD *)this + 11);
        if ( !v5 )
          goto LABEL_81;
        v38 = v25;
        v36 = 1416;
        goto LABEL_6;
      }
    }
    else
    {
      v26 = CDlpActionRecoverCrypto::SetProgressRange(this, 0x32u, 0x64u);
      v4 = v26;
      if ( v26 < 0 )
      {
        v5 = *((_QWORD *)this + 11);
        if ( !v5 )
          goto LABEL_81;
        v38 = v26;
        v36 = 1420;
        goto LABEL_6;
      }
    }
    v27 = CDlpActionRecoverCrypto::EncryptRanges(this);
    v4 = v27;
    if ( v27 >= 0 )
    {
      if ( *((_DWORD *)this + 176) || (v28 = CDlpActionRecoverCrypto::ClearRangesFromXml(this), v4 = v28, v28 >= 0) )
      {
        v29 = (const WCHAR *)*((_QWORD *)this + 70);
        if ( !v29 || MoveFileExW(*((LPCWSTR *)this + 69), v29, 1u) )
        {
          v31 = *((_QWORD *)this + 11);
          if ( v31 )
          {
            v32 = *((_QWORD *)this + 70);
            if ( !v32 )
              v32 = *((_QWORD *)this + 69);
            CDlpLogT<CEmptyType>::DlpLogFormat(v31, 2u, (__int64)L"RecoverCrypto: Decrypted ESD path [%s]", v32);
          }
          goto LABEL_81;
        }
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
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_81;
        v7 = 0;
        if ( (v4 & 0x80000000) == 0 )
        {
LABEL_8:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
          goto LABEL_81;
        }
        v38 = v4;
        v36 = 1438;
        v5 = *((_QWORD *)this + 11);
      }
      else
      {
        v5 = *((_QWORD *)this + 11);
        if ( !v5 )
          goto LABEL_81;
        v38 = v28;
        v36 = 1431;
      }
    }
    else
    {
      v5 = *((_QWORD *)this + 11);
      if ( !v5 )
        goto LABEL_81;
      v38 = v27;
      v36 = 1425;
    }
LABEL_6:
    v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v5,
           4u,
           (__int64)L"%s(%d): Result = 0x%X",
           L"CDlpActionRecoverCrypto::DoFastEncryption",
           v36,
           v38);
    v7 = (unsigned int)v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_8;
  }
  v5 = *((_QWORD *)this + 11);
  if ( v5 )
  {
    v38 = v8;
    v36 = 1363;
    goto LABEL_6;
  }
LABEL_81:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v4;
}

```

## disassembly

```asm
0x180013444  mov     rax, rsp
0x180013447  mov     [rax+18h], rbx
0x18001344b  mov     [rax+20h], rbp
0x18001344f  push    rsi
0x180013450  push    rdi
0x180013451  push    r14
0x180013453  sub     rsp, 30h
0x180013457  mov     rbx, rcx
0x18001345a  xor     r14d, r14d
0x18001345d  mov     [rax+10h], r14
0x180013461  mov     [rax+8], r14d
0x180013465  lea     esi, [r14+1]
0x180013469  test    [rcx+278h], sil
0x180013470  jz      loc_18001355E
0x180013476  cmp     [rcx+280h], r14d
0x18001347d  jnz     loc_18001355E
0x180013483  call    ?DoRecovery@CDlpActionRecoverCrypto@@AEAAJXZ; CDlpActionRecoverCrypto::DoRecovery(void)
0x180013488  mov     edi, eax
0x18001348a  test    eax, eax
0x18001348c  jns     short loc_1800134D4
0x18001348e  mov     rcx, [rbx+58h]
0x180013492  test    rcx, rcx
0x180013495  jz      loc_1800138D2
0x18001349b  mov     dword ptr [rsp+48h+var_20], eax
0x18001349f  mov     dword ptr [rsp+48h+var_28], 54Eh
0x1800134a7  mov     edx, 4
0x1800134ac  lea     r9, aCdlpactionreco_27; "CDlpActionRecoverCrypto::DoFastEncrypti"...
0x1800134b3  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800134ba  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800134bf  test    eax, eax
0x1800134c1  mov     ecx, eax
0x1800134c3  jns     short loc_1800134CA
0x1800134c5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800134ca  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800134cf  jmp     loc_1800138D2
0x1800134d4  xor     edx, edx; unsigned int
0x1800134d6  lea     r8d, [rdx+50h]; unsigned int
0x1800134da  mov     rcx, rbx; this
0x1800134dd  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x1800134e2  mov     edi, eax
0x1800134e4  test    eax, eax
0x1800134e6  jns     short loc_180013503
0x1800134e8  mov     rcx, [rbx+58h]
0x1800134ec  test    rcx, rcx
0x1800134ef  jz      loc_1800138D2
0x1800134f5  mov     dword ptr [rsp+48h+var_20], eax
0x1800134f9  mov     dword ptr [rsp+48h+var_28], 553h
0x180013501  jmp     short loc_1800134A7
0x180013503  lea     rdx, [rsp+48h+arg_0]; int *
0x180013508  mov     rcx, rbx; this
0x18001350b  call    ?VerifyFileHash@CDlpActionRecoverCrypto@@AEAAJPEAH@Z; CDlpActionRecoverCrypto::VerifyFileHash(int *)
0x180013510  mov     edi, eax
0x180013512  test    eax, eax
0x180013514  jns     short loc_180013534
0x180013516  mov     rcx, [rbx+58h]
0x18001351a  test    rcx, rcx
0x18001351d  jz      loc_1800138D2
0x180013523  mov     dword ptr [rsp+48h+var_20], eax
0x180013527  mov     dword ptr [rsp+48h+var_28], 554h
0x18001352f  jmp     loc_1800134A7
0x180013534  cmp     [rsp+48h+arg_0], 0
0x180013539  jnz     short loc_18001355E
0x18001353b  mov     edi, 80070570h
0x180013540  mov     rcx, [rbx+58h]
0x180013544  test    rcx, rcx
0x180013547  jz      loc_1800138D2
0x18001354d  mov     dword ptr [rsp+48h+var_20], edi
0x180013551  mov     dword ptr [rsp+48h+var_28], 55Bh
0x180013559  jmp     loc_1800134A7
0x18001355e  cmp     dword ptr [rbx+2C0h], 0
0x180013565  jz      loc_18001376D
0x18001356b  cmp     dword ptr [rbx+280h], 0
0x180013572  jnz     loc_18001376D
0x180013578  lea     rcx, [rsp+48h+arg_8]
0x18001357d  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x180013582  mov     edi, eax
0x180013584  test    eax, eax
0x180013586  jns     short loc_1800135CF
0x180013588  mov     rcx, [rbx+58h]
0x18001358c  test    rcx, rcx
0x18001358f  jz      short loc_1800135C5
0x180013591  mov     dword ptr [rsp+48h+var_20], eax
0x180013595  mov     dword ptr [rsp+48h+var_28], 564h
0x18001359d  lea     r9, aCdlpactionreco_27; "CDlpActionRecoverCrypto::DoFastEncrypti"...
0x1800135a4  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800135ab  mov     edx, 4
0x1800135b0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800135b5  mov     ecx, eax
0x1800135b7  test    eax, eax
0x1800135b9  jns     short loc_1800135C0
0x1800135bb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800135c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800135c5  mov     r14, [rsp+48h+arg_8]
0x1800135ca  jmp     loc_1800138D2
0x1800135cf  mov     r14, [rsp+48h+arg_8]
0x1800135d4  mov     r8, r14; unsigned __int16 *
0x1800135d7  mov     edx, esi; int
0x1800135d9  mov     rcx, rbx; this
0x1800135dc  call    ?SetupWimIoCallbacks@CDlpActionRecoverCrypto@@AEAAJHPEBG@Z; CDlpActionRecoverCrypto::SetupWimIoCallbacks(int,ushort const *)
0x1800135e1  mov     edi, eax
0x1800135e3  test    eax, eax
0x1800135e5  jns     short loc_180013605
0x1800135e7  mov     rcx, [rbx+58h]
0x1800135eb  test    rcx, rcx
0x1800135ee  jz      loc_1800138D2
0x1800135f4  mov     dword ptr [rsp+48h+var_20], eax
0x1800135f8  mov     dword ptr [rsp+48h+var_28], 566h
0x180013600  jmp     loc_1800134A7
0x180013605  mov     ebp, 4
0x18001360a  mov     rcx, rbx; this
0x18001360d  test    [rbx+278h], sil
0x180013614  jz      short loc_180013647
0x180013616  lea     edx, [rbp+4Ch]; unsigned int
0x180013619  lea     r8d, [rbp+56h]; unsigned int
0x18001361d  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013622  test    eax, eax
0x180013624  jns     short loc_180013677
0x180013626  lea     rsi, [rbx+58h]
0x18001362a  mov     rcx, [rsi]
0x18001362d  test    rcx, rcx
0x180013630  jz      loc_180013740
0x180013636  mov     dword ptr [rsp+48h+var_20], eax
0x18001363a  mov     dword ptr [rsp+48h+var_28], 56Dh
0x180013642  jmp     loc_18001371B
0x180013647  xor     edx, edx; unsigned int
0x180013649  lea     r8d, [rdx+32h]; unsigned int
0x18001364d  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x180013652  test    eax, eax
0x180013654  jns     short loc_180013677
0x180013656  lea     rsi, [rbx+58h]
0x18001365a  mov     rcx, [rsi]
0x18001365d  test    rcx, rcx
0x180013660  jz      loc_180013740
0x180013666  mov     dword ptr [rsp+48h+var_20], eax
0x18001366a  mov     dword ptr [rsp+48h+var_28], 571h
0x180013672  jmp     loc_18001371B
0x180013677  mov     rcx, rbx; this
0x18001367a  call    ?GenerateCryptoArray@CDlpActionRecoverCrypto@@AEAAJXZ; CDlpActionRecoverCrypto::GenerateCryptoArray(void)
0x18001367f  test    eax, eax
0x180013681  jns     short loc_1800136A1
0x180013683  lea     rsi, [rbx+58h]
0x180013687  mov     rcx, [rsi]
0x18001368a  test    rcx, rcx
0x18001368d  jz      loc_180013740
0x180013693  mov     dword ptr [rsp+48h+var_20], eax
0x180013697  mov     dword ptr [rsp+48h+var_28], 576h
0x18001369f  jmp     short loc_18001371B
0x1800136a1  cmp     dword ptr [rbx+26Ch], 0
0x1800136a8  jg      short loc_1800136CC
0x1800136aa  lea     rsi, [rbx+58h]
0x1800136ae  mov     rcx, [rsi]
0x1800136b1  test    rcx, rcx
0x1800136b4  jz      loc_180013740
0x1800136ba  mov     dword ptr [rsp+48h+var_20], 800700E8h
0x1800136c2  mov     dword ptr [rsp+48h+var_28], 57Ah
0x1800136ca  jmp     short loc_18001371B
0x1800136cc  mov     rcx, rbx; this
0x1800136cf  call    ?SaveEncryptedRangesToWim@CDlpActionRecoverCrypto@@AEAAJXZ; CDlpActionRecoverCrypto::SaveEncryptedRangesToWim(void)
0x1800136d4  test    eax, eax
0x1800136d6  jns     short loc_1800136F2
0x1800136d8  lea     rsi, [rbx+58h]
0x1800136dc  mov     rcx, [rsi]
0x1800136df  test    rcx, rcx
0x1800136e2  jz      short loc_180013740
0x1800136e4  mov     dword ptr [rsp+48h+var_20], eax
0x1800136e8  mov     dword ptr [rsp+48h+var_28], 57Eh
0x1800136f0  jmp     short loc_18001371B
0x1800136f2  xor     r8d, r8d; unsigned __int16 *
0x1800136f5  xor     edx, edx; int
0x1800136f7  mov     rcx, rbx; this
0x1800136fa  call    ?SetupWimIoCallbacks@CDlpActionRecoverCrypto@@AEAAJHPEBG@Z; CDlpActionRecoverCrypto::SetupWimIoCallbacks(int,ushort const *)
0x1800136ff  test    eax, eax
0x180013701  jns     short loc_180013772
0x180013703  lea     rsi, [rbx+58h]
0x180013707  mov     rcx, [rsi]
0x18001370a  test    rcx, rcx
0x18001370d  jz      short loc_180013740
0x18001370f  mov     dword ptr [rsp+48h+var_20], eax
0x180013713  mov     dword ptr [rsp+48h+var_28], 580h
0x18001371b  lea     r9, aCdlpactionreco_27; "CDlpActionRecoverCrypto::DoFastEncrypti"...
0x180013722  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180013729  mov     edx, ebp
0x18001372b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180013730  mov     ecx, eax
0x180013732  test    eax, eax
0x180013734  jns     short loc_18001373B
0x180013736  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001373b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013740  xor     r8d, r8d; unsigned __int16 *
0x180013743  xor     edx, edx; int
0x180013745  mov     rcx, rbx; this
0x180013748  call    ?SetupWimIoCallbacks@CDlpActionRecoverCrypto@@AEAAJHPEBG@Z; CDlpActionRecoverCrypto::SetupWimIoCallbacks(int,ushort const *)
0x18001374d  mov     edi, eax
0x18001374f  test    eax, eax
0x180013751  jns     loc_1800138D2
0x180013757  mov     rcx, [rsi]
0x18001375a  test    rcx, rcx
0x18001375d  jz      short loc_180013740
0x18001375f  mov     dword ptr [rsp+48h+var_20], eax
0x180013763  mov     dword ptr [rsp+48h+var_28], 5A7h
0x18001376b  jmp     short loc_18001371B
0x18001376d  mov     ebp, 4
0x180013772  mov     r8d, 64h ; 'd'; unsigned int
0x180013778  mov     rcx, rbx; this
0x18001377b  test    [rbx+278h], sil
0x180013782  jz      short loc_1800137B3
0x180013784  lea     edx, [r8-0Ah]; unsigned int
0x180013788  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x18001378d  mov     edi, eax
0x18001378f  test    eax, eax
0x180013791  jns     short loc_1800137DE
0x180013793  mov     rcx, [rbx+58h]
0x180013797  test    rcx, rcx
0x18001379a  jz      loc_1800138D2
0x1800137a0  mov     dword ptr [rsp+48h+var_20], eax
0x1800137a4  mov     dword ptr [rsp+48h+var_28], 588h
0x1800137ac  mov     edx, ebp
0x1800137ae  jmp     loc_1800134AC
0x1800137b3  mov     edx, 32h ; '2'; unsigned int
0x1800137b8  call    ?SetProgressRange@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressRange(ulong,ulong)
0x1800137bd  mov     edi, eax
0x1800137bf  test    eax, eax
0x1800137c1  jns     short loc_1800137DE
0x1800137c3  mov     rcx, [rbx+58h]
0x1800137c7  test    rcx, rcx
0x1800137ca  jz      loc_1800138D2
0x1800137d0  mov     dword ptr [rsp+48h+var_20], eax
0x1800137d4  mov     dword ptr [rsp+48h+var_28], 58Ch
0x1800137dc  jmp     short loc_1800137AC
0x1800137de  mov     rcx, rbx; this
0x1800137e1  call    ?EncryptRanges@CDlpActionRecoverCrypto@@AEAAJXZ; CDlpActionRecoverCrypto::EncryptRanges(void)
0x1800137e6  mov     edi, eax
0x1800137e8  test    eax, eax
0x1800137ea  jns     short loc_180013807
0x1800137ec  mov     rcx, [rbx+58h]
0x1800137f0  test    rcx, rcx
0x1800137f3  jz      loc_1800138D2
0x1800137f9  mov     dword ptr [rsp+48h+var_20], eax
0x1800137fd  mov     dword ptr [rsp+48h+var_28], 591h
0x180013805  jmp     short loc_1800137AC
0x180013807  cmp     dword ptr [rbx+2C0h], 0
0x18001380e  jnz     short loc_18001383C
0x180013810  mov     rcx, rbx; this
0x180013813  call    ?ClearRangesFromXml@CDlpActionRecoverCrypto@@AEAAJXZ; CDlpActionRecoverCrypto::ClearRangesFromXml(void)
0x180013818  mov     edi, eax
0x18001381a  test    eax, eax
0x18001381c  jns     short loc_18001383C
0x18001381e  mov     rcx, [rbx+58h]
0x180013822  test    rcx, rcx
0x180013825  jz      loc_1800138D2
0x18001382b  mov     dword ptr [rsp+48h+var_20], eax
0x18001382f  mov     dword ptr [rsp+48h+var_28], 597h
0x180013837  jmp     loc_1800137AC
0x18001383c  mov     rdx, [rbx+230h]; lpNewFileName
0x180013843  test    rdx, rdx
0x180013846  jz      short loc_1800138A2
0x180013848  mov     r8d, esi; dwFlags
0x18001384b  mov     rcx, [rbx+228h]; lpExistingFileName
0x180013852  call    cs:__imp_MoveFileExW
0x180013858  test    eax, eax
0x18001385a  jnz     short loc_1800138A2
0x18001385c  call    cs:__imp_GetLastError
0x180013862  mov     edi, eax
0x180013864  test    eax, eax
0x180013866  jnz     short loc_18001386F
0x180013868  mov     edi, 80004005h
0x18001386d  jmp     short loc_18001387A
0x18001386f  jle     short loc_18001387A
0x180013871  movzx   edi, ax
0x180013874  or      edi, 80070000h
0x18001387a  cmp     qword ptr [rbx+58h], 0
0x18001387f  jz      short loc_1800138D2
0x180013881  xor     ecx, ecx
0x180013883  test    edi, edi
0x180013885  jns     loc_1800134CA
0x18001388b  mov     dword ptr [rsp+48h+var_20], edi
0x18001388f  mov     dword ptr [rsp+48h+var_28], 59Eh
0x180013897  mov     edx, ebp
0x180013899  mov     rcx, [rbx+58h]
0x18001389d  jmp     loc_1800134AC
0x1800138a2  mov     rcx, [rbx+58h]
0x1800138a6  test    rcx, rcx
0x1800138a9  jz      short loc_1800138D2
0x1800138ab  mov     rax, [rbx+230h]
0x1800138b2  test    rax, rax
0x1800138b5  jnz     short loc_1800138BE
0x1800138b7  mov     rax, [rbx+228h]
0x1800138be  mov     r9, rax
0x1800138c1  lea     r8, aRecovercryptoD_0; "RecoverCrypto: Decrypted ESD path [%s]"
0x1800138c8  mov     edx, 2
0x1800138cd  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800138d2  mov     ecx, edi
0x1800138d4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800138d9  nop
0x1800138da  test    r14, r14
0x1800138dd  jz      short loc_1800138FB
0x1800138df  call    cs:__imp_GetProcessHeap
0x1800138e5  mov     rcx, rax; hHeap
0x1800138e8  lea     r8, [r14-4]; lpMem
0x1800138ec  xor     edx, edx; dwFlags
  ... truncated ...
```
