# CDlpActionRecoverCrypto::SaveEncryptedRangesToWim(void)

- ea: `0x180028a30`
- end: `0x180029051`
- name: `?SaveEncryptedRangesToWim@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `1569`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180013444`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001c9d0`
- `0x18001fd60`
- `0x180028640`
- `0x180028a30`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x180028fca`
- `WIMGAPI!WIMCloseHandle` at `0x180028fca`
- `WIMGAPI!WIMGetImageInformation` at `0x180028bae`
- `WIMGAPI!WIMGetImageInformation` at `0x180028bae`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180028b51`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180028b51`
- `WIMGAPI!WIMSetImageInformation` at `0x180028f0f`
- `WIMGAPI!WIMSetImageInformation` at `0x180028f0f`
- `WIMGAPI!WIMCreateFile` at `0x180028a95`
- `WIMGAPI!WIMCreateFile` at `0x180028a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028f97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028fff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028f97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028fff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029021`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028d5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028dda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028fa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028fec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002900e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028d5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028dda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028fa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028fec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002900e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fb8`
- `UNATTEND!UnattendCtxSetString` at `0x180028cae`
- `UNATTEND!UnattendCtxSetString` at `0x180028db6`
- `UNATTEND!UnattendCtxSetString` at `0x180028e33`
- `UNATTEND!UnattendCtxSetString` at `0x180028cae`
- `UNATTEND!UnattendCtxSetString` at `0x180028db6`
- `UNATTEND!UnattendCtxSetString` at `0x180028e33`
- `UNATTEND!UnattendCtxCleanup` at `0x180028f80`
- `UNATTEND!UnattendCtxCleanup` at `0x180028f80`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x180028e5b`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x180028e5b`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x180028c08`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x180028c08`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDlpActionRecoverCrypto::SaveEncryptedRangesToWim(CDlpActionRecoverCrypto *this)
{
  WCHAR *v2; // r13
  unsigned __int16 *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rbx
  signed int LastError; // eax
  signed int v7; // edi
  __int64 v8; // rcx
  int TempDir; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  signed int v13; // eax
  signed int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int StringCch; // eax
  int v23; // r15d
  HANDLE ProcessHeap; // rax
  int v25; // eax
  int v26; // eax
  HANDLE v27; // rax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  signed int v31; // eax
  int v32; // eax
  void *v33; // rsi
  HANDLE v34; // rax
  void *v35; // rbx
  HANDLE v36; // rax
  HANDLE v37; // rax
  HANDLE v38; // rax
  __int64 v40; // [rsp+20h] [rbp-58h]
  __int64 v41; // [rsp+28h] [rbp-50h]
  WCHAR *v42; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-38h] BYREF
  __int64 v45; // [rsp+48h] [rbp-30h]
  __int64 v46; // [rsp+50h] [rbp-28h] BYREF
  __int64 v47; // [rsp+58h] [rbp-20h]
  __int64 v48; // [rsp+60h] [rbp-18h]
  unsigned int v49; // [rsp+C0h] [rbp+48h] BYREF
  int v50; // [rsp+C8h] [rbp+50h] BYREF
  unsigned __int16 *v51; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v52; // [rsp+D8h] [rbp+60h] BYREF

  v48 = 0;
  v2 = 0;
  v42 = 0;
  v3 = 0;
  v51 = 0;
  v45 = 0;
  hMem = 0;
  v49 = 0;
  lpMem = 0;
  v46 = 0;
  v52 = 0;
  v4 = WIMCreateFile(*((_QWORD *)this + 69), 3221225472LL, 3, 0x20000000, 0, 0);
  v5 = v4;
  if ( !v4 )
  {
    v5 = 0;
    v47 = 0;
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
    if ( *((_QWORD *)this + 11) )
    {
      v8 = 0;
      if ( v7 < 0 )
      {
        LODWORD(v41) = v7;
        LODWORD(v40) = 2250;
LABEL_79:
        v16 = *((_QWORD *)this + 11);
LABEL_80:
        v32 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v16,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::SaveEncryptedRangesToWim",
                v40,
                v41);
        v8 = (unsigned int)v32;
        if ( v32 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32);
        goto LABEL_82;
      }
      goto LABEL_82;
    }
    goto LABEL_83;
  }
  v47 = v4;
  TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v42);
  v7 = TempDir;
  if ( TempDir < 0 )
  {
    v10 = *((_QWORD *)this + 11);
    if ( v10 )
    {
      LODWORD(v41) = TempDir;
      LODWORD(v40) = 2252;
      v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v10,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionRecoverCrypto::SaveEncryptedRangesToWim",
              v40,
              v41);
      v12 = (unsigned int)v11;
      if ( v11 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
    }
    v2 = v42;
    goto LABEL_83;
  }
  v2 = v42;
  if ( (unsigned int)WIMSetTemporaryPath(v5, v42) )
  {
    v49 = 0;
    if ( !(unsigned int)WIMGetImageInformation(v5, &hMem, &v49) )
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 )
      {
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v8 = 0;
        if ( v7 < 0 )
        {
          LODWORD(v41) = v7;
          LODWORD(v40) = 2256;
          goto LABEL_79;
        }
        goto LABEL_82;
      }
      goto LABEL_83;
    }
    v15 = UnattendCtxDeserializeBuffer(&v52, hMem, v49);
    v7 = v15;
    if ( v15 < 0 )
    {
      v16 = *((_QWORD *)this + 11);
      if ( !v16 )
        goto LABEL_83;
      LODWORD(v41) = v15;
      LODWORD(v40) = 2261;
      goto LABEL_80;
    }
    v17 = STRAPI_Format(&v51, L"%d", *((unsigned int *)this + 155));
    v7 = v17;
    if ( v17 >= 0 )
    {
      v3 = v51;
      v21 = UnattendCtxSetString(&v52, L"WIM\\ESD\\ENCRYPTED", L"Count", v51);
      v7 = v21;
      if ( v21 < 0 )
      {
        v16 = *((_QWORD *)this + 11);
        if ( !v16 )
          goto LABEL_83;
        LODWORD(v41) = v21;
        LODWORD(v40) = 2266;
        goto LABEL_80;
      }
      v50 = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"WIM\\ESD\\ENCRYPTED\\RANGE[*]", &v50);
      v7 = StringCch;
      if ( StringCch < 0
        || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"WIM\\ESD\\ENCRYPTED\\RANGE[*]"),
            v7 = StringCch,
            StringCch < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v16 = *((_QWORD *)this + 11);
        if ( !v16 )
          goto LABEL_83;
        LODWORD(v41) = v7;
        LODWORD(v40) = 2272;
        goto LABEL_80;
      }
      v23 = 0;
      if ( *((int *)this + 155) <= 0 )
      {
LABEL_60:
        v30 = UnattendCtxSerializeToBuffer(&v52, &lpMem, &v46);
        v7 = v30;
        if ( v30 < 0 )
        {
          v16 = *((_QWORD *)this + 11);
          if ( !v16 )
            goto LABEL_83;
          LODWORD(v41) = v30;
          LODWORD(v40) = 2287;
          goto LABEL_80;
        }
        if ( !(unsigned int)WIMSetImageInformation(v5, lpMem, (unsigned int)v46) )
        {
          v31 = GetLastError();
          v7 = v31;
          if ( v31 )
          {
            if ( v31 > 0 )
              v7 = (unsigned __int16)v31 | 0x80070000;
          }
          else
          {
            v7 = -2147467259;
          }
          if ( *((_QWORD *)this + 11) )
          {
            v8 = 0;
            if ( v7 < 0 )
            {
              LODWORD(v41) = v7;
              LODWORD(v40) = 2288;
              goto LABEL_79;
            }
            goto LABEL_82;
          }
        }
        goto LABEL_83;
      }
      while ( 1 )
      {
        if ( v3 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v3 - 2);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v51 = 0;
        }
        v25 = STRAPI_Format(&v51, L"%I64u", *(_QWORD *)(*((_QWORD *)this + 78) + 16LL * v23));
        v7 = v25;
        if ( v25 < 0 )
          break;
        v3 = v51;
        v26 = UnattendCtxSetString(&v52, v45, L"Offset", v51);
        v7 = v26;
        if ( v26 < 0 )
        {
          v16 = *((_QWORD *)this + 11);
          if ( !v16 )
            goto LABEL_83;
          LODWORD(v41) = v26;
          LODWORD(v40) = 2278;
          goto LABEL_80;
        }
        if ( v3 )
        {
          v27 = GetProcessHeap();
          HeapFree(v27, 0, v3 - 2);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v51 = 0;
        }
        v28 = STRAPI_Format(&v51, L"%d", *(unsigned int *)(*((_QWORD *)this + 78) + 16LL * v23 + 8));
        v7 = v28;
        if ( v28 < 0 )
        {
          v18 = *((_QWORD *)this + 11);
          if ( !v18 )
            goto LABEL_40;
          LODWORD(v41) = v28;
          LODWORD(v40) = 2281;
          goto LABEL_37;
        }
        v3 = v51;
        v29 = UnattendCtxSetString(&v52, v45, L"Bytes", v51);
        v7 = v29;
        if ( v29 < 0 )
        {
          v16 = *((_QWORD *)this + 11);
          if ( !v16 )
            goto LABEL_83;
          LODWORD(v41) = v29;
          LODWORD(v40) = 2282;
          goto LABEL_80;
        }
        if ( ++v23 >= *((_DWORD *)this + 155) )
          goto LABEL_60;
      }
      v18 = *((_QWORD *)this + 11);
      if ( !v18 )
        goto LABEL_40;
      LODWORD(v41) = v25;
      LODWORD(v40) = 2277;
    }
    else
    {
      v18 = *((_QWORD *)this + 11);
      if ( !v18 )
      {
LABEL_40:
        v3 = v51;
        goto LABEL_83;
      }
      LODWORD(v41) = v17;
      LODWORD(v40) = 2265;
    }
LABEL_37:
    v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v18,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionRecoverCrypto::SaveEncryptedRangesToWim",
            v40,
            v41);
    v20 = (unsigned int)v19;
    if ( v19 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v19);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
    goto LABEL_40;
  }
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
  if ( *((_QWORD *)this + 11) )
  {
    v8 = 0;
    if ( v7 < 0 )
    {
      LODWORD(v41) = v7;
      LODWORD(v40) = 2253;
      goto LABEL_79;
    }
LABEL_82:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  }
LABEL_83:
  UnattendCtxCleanup(&v52);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  v33 = lpMem;
  if ( lpMem )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
    lpMem = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v5 )
    WIMCloseHandle(v5);
  if ( v45 )
  {
    v35 = (void *)(v45 - 4);
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028a30  push    rbp
0x180028a32  push    rbx
0x180028a33  push    rsi
0x180028a34  push    rdi
0x180028a35  push    r12
0x180028a37  push    r13
0x180028a39  push    r14
0x180028a3b  push    r15
0x180028a3d  mov     rbp, rsp
0x180028a40  sub     rsp, 78h
0x180028a44  mov     rsi, rcx
0x180028a47  xor     r12d, r12d
0x180028a4a  mov     [rbp+var_18], r12
0x180028a4e  mov     r13d, r12d
0x180028a51  mov     [rbp+var_48], r12
0x180028a55  mov     r14d, r12d
0x180028a58  mov     [rbp+arg_10], r12
0x180028a5c  mov     [rbp+var_30], r12
0x180028a60  mov     [rbp+hMem], r12
0x180028a64  mov     [rbp+arg_0], r12d
0x180028a68  mov     [rbp+lpMem], r12
0x180028a6c  mov     [rbp+var_28], r12
0x180028a70  mov     [rbp+arg_18], r12
0x180028a74  mov     [rsp+78h+var_50], r12
0x180028a79  mov     dword ptr [rsp+78h+var_58], r12d
0x180028a7e  mov     edx, 0C0000000h
0x180028a83  mov     r9d, 20000000h
0x180028a89  lea     r8d, [r12+3]
0x180028a8e  mov     rcx, [rcx+228h]
0x180028a95  call    cs:__imp_WIMCreateFile
0x180028a9b  mov     rbx, rax
0x180028a9e  test    rax, rax
0x180028aa1  jnz     short loc_180028AEE
0x180028aa3  mov     ebx, r12d
0x180028aa6  mov     [rbp+var_20], rbx
0x180028aaa  call    cs:__imp_GetLastError
0x180028ab0  mov     edi, eax
0x180028ab2  test    eax, eax
0x180028ab4  jnz     short loc_180028ABD
0x180028ab6  mov     edi, 80004005h
0x180028abb  jmp     short loc_180028AC8
0x180028abd  jle     short loc_180028AC8
0x180028abf  movzx   edi, ax
0x180028ac2  or      edi, 80070000h
0x180028ac8  cmp     [rsi+58h], r12
0x180028acc  jz      loc_180028F7C
0x180028ad2  mov     ecx, r12d
0x180028ad5  test    edi, edi
0x180028ad7  jns     loc_180028F77
0x180028add  mov     dword ptr [rsp+78h+var_50], edi
0x180028ae1  mov     dword ptr [rsp+78h+var_58], 8CAh
0x180028ae9  jmp     loc_180028F50
0x180028aee  mov     [rbp+var_20], rbx
0x180028af2  lea     rcx, [rbp+var_48]
0x180028af6  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x180028afb  mov     edi, eax
0x180028afd  test    eax, eax
0x180028aff  jns     short loc_180028B47
0x180028b01  mov     rcx, [rsi+58h]
0x180028b05  test    rcx, rcx
0x180028b08  jz      short loc_180028B3E
0x180028b0a  mov     dword ptr [rsp+78h+var_50], eax
0x180028b0e  mov     dword ptr [rsp+78h+var_58], 8CCh
0x180028b16  lea     r9, aCdlpactionreco_8; "CDlpActionRecoverCrypto::SaveEncryptedR"...
0x180028b1d  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180028b24  mov     edx, 4
0x180028b29  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180028b2e  mov     ecx, eax
0x180028b30  test    eax, eax
0x180028b32  jns     short loc_180028B39
0x180028b34  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028b39  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028b3e  mov     r13, [rbp+var_48]
0x180028b42  jmp     loc_180028F7C
0x180028b47  mov     r13, [rbp+var_48]
0x180028b4b  mov     rdx, r13
0x180028b4e  mov     rcx, rbx
0x180028b51  call    cs:__imp_WIMSetTemporaryPath
0x180028b57  test    eax, eax
0x180028b59  jnz     short loc_180028B9F
0x180028b5b  call    cs:__imp_GetLastError
0x180028b61  mov     edi, eax
0x180028b63  test    eax, eax
0x180028b65  jnz     short loc_180028B6E
0x180028b67  mov     edi, 80004005h
0x180028b6c  jmp     short loc_180028B79
0x180028b6e  jle     short loc_180028B79
0x180028b70  movzx   edi, ax
0x180028b73  or      edi, 80070000h
0x180028b79  cmp     [rsi+58h], r12
0x180028b7d  jz      loc_180028F7C
0x180028b83  mov     ecx, r12d
0x180028b86  test    edi, edi
0x180028b88  jns     loc_180028F77
0x180028b8e  mov     dword ptr [rsp+78h+var_50], edi
0x180028b92  mov     dword ptr [rsp+78h+var_58], 8CDh
0x180028b9a  jmp     loc_180028F50
0x180028b9f  mov     [rbp+arg_0], r12d
0x180028ba3  lea     r8, [rbp+arg_0]
0x180028ba7  lea     rdx, [rbp+hMem]
0x180028bab  mov     rcx, rbx
0x180028bae  call    cs:__imp_WIMGetImageInformation
0x180028bb4  test    eax, eax
0x180028bb6  jnz     short loc_180028BFC
0x180028bb8  call    cs:__imp_GetLastError
0x180028bbe  mov     edi, eax
0x180028bc0  test    eax, eax
0x180028bc2  jnz     short loc_180028BCB
0x180028bc4  mov     edi, 80004005h
0x180028bc9  jmp     short loc_180028BD6
0x180028bcb  jle     short loc_180028BD6
0x180028bcd  movzx   edi, ax
0x180028bd0  or      edi, 80070000h
0x180028bd6  cmp     [rsi+58h], r12
0x180028bda  jz      loc_180028F7C
0x180028be0  mov     ecx, r12d
0x180028be3  test    edi, edi
0x180028be5  jns     loc_180028F77
0x180028beb  mov     dword ptr [rsp+78h+var_50], edi
0x180028bef  mov     dword ptr [rsp+78h+var_58], 8D0h
0x180028bf7  jmp     loc_180028F50
0x180028bfc  mov     r8d, [rbp+arg_0]
0x180028c00  mov     rdx, [rbp+hMem]
0x180028c04  lea     rcx, [rbp+arg_18]
0x180028c08  call    cs:__imp_UnattendCtxDeserializeBuffer
0x180028c0e  mov     edi, eax
0x180028c10  test    eax, eax
0x180028c12  jns     short loc_180028C32
0x180028c14  mov     rcx, [rsi+58h]
0x180028c18  test    rcx, rcx
0x180028c1b  jz      loc_180028F7C
0x180028c21  mov     dword ptr [rsp+78h+var_50], eax
0x180028c25  mov     dword ptr [rsp+78h+var_58], 8D5h
0x180028c2d  jmp     loc_180028F54
0x180028c32  mov     r8d, [rsi+26Ch]
0x180028c39  lea     rdx, aD; "%d"
0x180028c40  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180028c44  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180028c49  mov     edi, eax
0x180028c4b  test    eax, eax
0x180028c4d  jns     short loc_180028C95
0x180028c4f  mov     rcx, [rsi+58h]
0x180028c53  test    rcx, rcx
0x180028c56  jz      short loc_180028C8C
0x180028c58  mov     dword ptr [rsp+78h+var_50], eax
0x180028c5c  mov     dword ptr [rsp+78h+var_58], 8D9h
0x180028c64  lea     r9, aCdlpactionreco_8; "CDlpActionRecoverCrypto::SaveEncryptedR"...
0x180028c6b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180028c72  mov     edx, 4
0x180028c77  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180028c7c  test    eax, eax
0x180028c7e  mov     ecx, eax
0x180028c80  jns     short loc_180028C87
0x180028c82  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028c87  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028c8c  mov     r14, [rbp+arg_10]
0x180028c90  jmp     loc_180028F7C
0x180028c95  mov     r14, [rbp+arg_10]
0x180028c99  mov     r9, r14
0x180028c9c  lea     r8, aCount; "Count"
0x180028ca3  lea     rdx, aWimEsdEncrypte_0; "WIM\\ESD\\ENCRYPTED"
0x180028caa  lea     rcx, [rbp+arg_18]
0x180028cae  call    cs:__imp_UnattendCtxSetString
0x180028cb4  mov     edi, eax
0x180028cb6  test    eax, eax
0x180028cb8  jns     short loc_180028CD8
0x180028cba  mov     rcx, [rsi+58h]
0x180028cbe  test    rcx, rcx
0x180028cc1  jz      loc_180028F7C
0x180028cc7  mov     dword ptr [rsp+78h+var_50], eax
0x180028ccb  mov     dword ptr [rsp+78h+var_58], 8DAh
0x180028cd3  jmp     loc_180028F54
0x180028cd8  mov     [rbp+arg_8], r12d
0x180028cdc  lea     rdx, [rbp+arg_8]
0x180028ce0  lea     rcx, aWimEsdEncrypte; "WIM\\ESD\\ENCRYPTED\\RANGE[*]"
0x180028ce7  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180028cec  mov     edi, eax
0x180028cee  test    eax, eax
0x180028cf0  js      short loc_180028D0B
0x180028cf2  lea     r8, [rbp+var_30]
0x180028cf6  mov     edx, [rbp+arg_8]
0x180028cf9  lea     rcx, aWimEsdEncrypte; "WIM\\ESD\\ENCRYPTED\\RANGE[*]"
0x180028d00  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180028d05  mov     edi, eax
0x180028d07  test    eax, eax
0x180028d09  jns     short loc_180028D12
0x180028d0b  mov     ecx, eax
0x180028d0d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028d12  mov     ecx, edi
0x180028d14  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028d19  test    edi, edi
0x180028d1b  jns     short loc_180028D3B
0x180028d1d  mov     rcx, [rsi+58h]
0x180028d21  test    rcx, rcx
0x180028d24  jz      loc_180028F7C
0x180028d2a  mov     dword ptr [rsp+78h+var_50], edi
0x180028d2e  mov     dword ptr [rsp+78h+var_58], 8E0h
0x180028d36  jmp     loc_180028F54
0x180028d3b  mov     r15d, r12d
0x180028d3e  cmp     [rsi+26Ch], r12d
0x180028d45  jle     loc_180028E4F
0x180028d4b  test    r14, r14
0x180028d4e  jz      short loc_180028D70
0x180028d50  call    cs:__imp_GetProcessHeap
0x180028d56  mov     rcx, rax; hHeap
0x180028d59  lea     r8, [r14-4]; lpMem
0x180028d5d  xor     edx, edx; dwFlags
0x180028d5f  call    cs:__imp_HeapFree
0x180028d65  xor     ecx, ecx
0x180028d67  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028d6c  mov     [rbp+arg_10], r12
0x180028d70  mov     r8, [rsi+270h]
0x180028d77  movsxd  r12, r15d
0x180028d7a  add     r12, r12
0x180028d7d  mov     r8, [r8+r12*8]
0x180028d81  lea     rdx, aI64u; "%I64u"
0x180028d88  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180028d8c  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180028d91  mov     edi, eax
0x180028d93  test    eax, eax
0x180028d95  js      loc_180028EE3
0x180028d9b  mov     r14, [rbp+arg_10]
0x180028d9f  mov     dword ptr [rsp+78h+var_58], r15d
0x180028da4  mov     r9, r14
0x180028da7  lea     r8, aOffset; "Offset"
0x180028dae  mov     rdx, [rbp+var_30]
0x180028db2  lea     rcx, [rbp+arg_18]
0x180028db6  call    cs:__imp_UnattendCtxSetString
0x180028dbc  mov     edi, eax
0x180028dbe  test    eax, eax
0x180028dc0  js      loc_180028EC5
0x180028dc6  test    r14, r14
0x180028dc9  jz      short loc_180028DEF
0x180028dcb  call    cs:__imp_GetProcessHeap
0x180028dd1  mov     rcx, rax; hHeap
0x180028dd4  lea     r8, [r14-4]; lpMem
0x180028dd8  xor     edx, edx; dwFlags
0x180028dda  call    cs:__imp_HeapFree
0x180028de0  xor     ecx, ecx
0x180028de2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028de7  mov     [rbp+arg_10], 0
0x180028def  mov     r8, [rsi+270h]
0x180028df6  mov     r8d, [r8+r12*8+8]
0x180028dfb  lea     rdx, aD; "%d"
0x180028e02  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180028e06  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180028e0b  mov     edi, eax
0x180028e0d  xor     r12d, r12d
0x180028e10  test    eax, eax
0x180028e12  js      loc_180028EA7
0x180028e18  mov     r14, [rbp+arg_10]
0x180028e1c  mov     dword ptr [rsp+78h+var_58], r15d
0x180028e21  mov     r9, r14
0x180028e24  lea     r8, aBytes; "Bytes"
0x180028e2b  mov     rdx, [rbp+var_30]
0x180028e2f  lea     rcx, [rbp+arg_18]
0x180028e33  call    cs:__imp_UnattendCtxSetString
0x180028e39  mov     edi, eax
0x180028e3b  test    eax, eax
0x180028e3d  js      short loc_180028E89
0x180028e3f  inc     r15d
0x180028e42  cmp     r15d, [rsi+26Ch]
0x180028e49  jl      loc_180028D4B
0x180028e4f  lea     r8, [rbp+var_28]
0x180028e53  lea     rdx, [rbp+lpMem]
0x180028e57  lea     rcx, [rbp+arg_18]
0x180028e5b  call    cs:__imp_UnattendCtxSerializeToBuffer
0x180028e61  mov     edi, eax
0x180028e63  test    eax, eax
0x180028e65  jns     loc_180028F04
0x180028e6b  mov     rcx, [rsi+58h]
0x180028e6f  test    rcx, rcx
0x180028e72  jz      loc_180028F7C
0x180028e78  mov     dword ptr [rsp+78h+var_50], eax
0x180028e7c  mov     dword ptr [rsp+78h+var_58], 8EFh
0x180028e84  jmp     loc_180028F54
0x180028e89  mov     rcx, [rsi+58h]
0x180028e8d  test    rcx, rcx
0x180028e90  jz      loc_180028F7C
0x180028e96  mov     dword ptr [rsp+78h+var_50], eax
0x180028e9a  mov     dword ptr [rsp+78h+var_58], 8EAh
0x180028ea2  jmp     loc_180028F54
0x180028ea7  mov     rcx, [rsi+58h]
0x180028eab  test    rcx, rcx
0x180028eae  jz      loc_180028C8C
0x180028eb4  mov     dword ptr [rsp+78h+var_50], eax
0x180028eb8  mov     dword ptr [rsp+78h+var_58], 8E9h
0x180028ec0  jmp     loc_180028C64
0x180028ec5  mov     rcx, [rsi+58h]
0x180028ec9  xor     r12d, r12d
0x180028ecc  test    rcx, rcx
0x180028ecf  jz      loc_180028F7C
0x180028ed5  mov     dword ptr [rsp+78h+var_50], eax
0x180028ed9  mov     dword ptr [rsp+78h+var_58], 8E6h
0x180028ee1  jmp     short loc_180028F54
0x180028ee3  mov     rcx, [rsi+58h]
0x180028ee7  xor     r12d, r12d
0x180028eea  test    rcx, rcx
0x180028eed  jz      loc_180028C8C
0x180028ef3  mov     dword ptr [rsp+78h+var_50], eax
  ... truncated ...
```
