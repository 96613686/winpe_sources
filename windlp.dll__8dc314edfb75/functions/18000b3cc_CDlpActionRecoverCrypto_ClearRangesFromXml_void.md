# CDlpActionRecoverCrypto::ClearRangesFromXml(void)

- ea: `0x18000b3cc`
- end: `0x18000b7f0`
- name: `?ClearRangesFromXml@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `1060`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013444`

## callees

- `0x18000aba4`
- `0x18000b3cc`
- `0x180012f5c`
- `0x18001c9d0`
- `0x18001fd60`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18000b7db`
- `WIMGAPI!WIMCloseHandle` at `0x18000b7db`
- `WIMGAPI!WIMGetImageInformation` at `0x18000b547`
- `WIMGAPI!WIMGetImageInformation` at `0x18000b547`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000b4ea`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000b4ea`
- `WIMGAPI!WIMSetImageInformation` at `0x18000b6fe`
- `WIMGAPI!WIMSetImageInformation` at `0x18000b6fe`
- `WIMGAPI!WIMCreateFile` at `0x18000b42e`
- `WIMGAPI!WIMCreateFile` at `0x18000b42e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b708`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b7c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b7c9`
- `UNATTEND!UnattendFreeNode` at `0x18000b668`
- `UNATTEND!UnattendFreeNode` at `0x18000b668`
- `UNATTEND!UnattendCtxOpenNode` at `0x18000b5da`
- `UNATTEND!UnattendCtxOpenNode` at `0x18000b5da`
- `UNATTEND!UnattendCtxCleanup` at `0x18000b76f`
- `UNATTEND!UnattendCtxCleanup` at `0x18000b76f`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x18000b6cc`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x18000b6cc`
- `UNATTEND!UnattendCtxRemoveNode` at `0x18000b63a`
- `UNATTEND!UnattendCtxRemoveNode` at `0x18000b63a`
- `UNATTEND!UnattendCtxBeginModify` at `0x18000b608`
- `UNATTEND!UnattendCtxBeginModify` at `0x18000b608`
- `UNATTEND!UnattendCtxCommitModify` at `0x18000b696`
- `UNATTEND!UnattendCtxCommitModify` at `0x18000b696`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18000b5a1`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18000b5a1`

## string_xrefs

- `0x18000b4af`: `CDlpActionRecoverCrypto::ClearRangesFromXml`
- `0x18000b743`: `CDlpActionRecoverCrypto::ClearRangesFromXml`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::ClearRangesFromXml(CDlpActionRecoverCrypto *this)
{
  __int64 v2; // r14
  __int64 v3; // rax
  __int64 v4; // rbx
  signed int v5; // eax
  signed int v6; // esi
  __int64 v7; // rcx
  int TempDir; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  signed int v12; // eax
  signed int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  signed int LastError; // eax
  int v23; // eax
  void *v24; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v26; // rax
  __int64 v28; // [rsp+20h] [rbp-58h]
  __int64 v29; // [rsp+28h] [rbp-50h]
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  __int64 v31; // [rsp+38h] [rbp-40h] BYREF
  __int64 v32; // [rsp+40h] [rbp-38h]
  _OWORD v33[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v34; // [rsp+68h] [rbp-10h]
  unsigned int v35; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+40h] BYREF
  __int64 v37; // [rsp+C0h] [rbp+48h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp+50h] BYREF

  hMem = 0;
  v35 = 0;
  v2 = 0;
  v37 = 0;
  lpMem = 0;
  v31 = 0;
  memset(v33, 0, sizeof(v33));
  v34 = 0;
  v36 = 0;
  v3 = WIMCreateFile(*((_QWORD *)this + 69), 3221225472LL, 3, 0x20000000, 0, 0);
  v4 = v3;
  if ( v3 )
  {
    v32 = v3;
    TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v37);
    v6 = TempDir;
    if ( TempDir >= 0 )
    {
      v2 = v37;
      if ( (unsigned int)WIMSetTemporaryPath(v4, v37) )
      {
        v35 = 0;
        if ( (unsigned int)WIMGetImageInformation(v4, &hMem, &v35) )
        {
          v14 = UnattendCtxDeserializeBuffer(&v36, hMem, v35);
          v6 = v14;
          if ( v14 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v14;
            LODWORD(v28) = 1310;
            goto LABEL_61;
          }
          v16 = UnattendCtxOpenNode(&v36, L"WIM\\ESD\\ENCRYPTED", v33);
          v6 = v16;
          if ( v16 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v16;
            LODWORD(v28) = 1311;
            goto LABEL_61;
          }
          v17 = UnattendCtxBeginModify(&v36);
          v6 = v17;
          if ( v17 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v17;
            LODWORD(v28) = 1315;
            goto LABEL_61;
          }
          v18 = UnattendCtxRemoveNode(&v36, v33);
          v6 = v18;
          if ( v18 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v18;
            LODWORD(v28) = 1316;
            goto LABEL_61;
          }
          v19 = UnattendFreeNode(v33);
          v6 = v19;
          if ( v19 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v19;
            LODWORD(v28) = 1320;
            goto LABEL_61;
          }
          v20 = UnattendCtxCommitModify(&v36);
          v6 = v20;
          if ( v20 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v20;
            LODWORD(v28) = 1324;
            goto LABEL_61;
          }
          v21 = UnattendCtxSerializeToBuffer(&v36, &lpMem, &v31);
          v6 = v21;
          if ( v21 < 0 )
          {
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_64;
            LODWORD(v29) = v21;
            LODWORD(v28) = 1328;
            goto LABEL_61;
          }
          if ( !(unsigned int)WIMSetImageInformation(v4, lpMem, (unsigned int)v31) )
          {
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError )
            {
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v6 = -2147467259;
            }
            if ( *((_QWORD *)this + 11) )
            {
              v7 = 0;
              if ( v6 < 0 )
              {
                LODWORD(v29) = v6;
                LODWORD(v28) = 1329;
                goto LABEL_60;
              }
              goto LABEL_63;
            }
          }
        }
        else
        {
          v13 = GetLastError();
          v6 = v13;
          if ( v13 )
          {
            if ( v13 > 0 )
              v6 = (unsigned __int16)v13 | 0x80070000;
          }
          else
          {
            v6 = -2147467259;
          }
          if ( *((_QWORD *)this + 11) )
          {
            v7 = 0;
            if ( v6 < 0 )
            {
              LODWORD(v29) = v6;
              LODWORD(v28) = 1306;
              goto LABEL_60;
            }
            goto LABEL_63;
          }
        }
      }
      else
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v6 = (unsigned __int16)v12 | 0x80070000;
        }
        else
        {
          v6 = -2147467259;
        }
        if ( *((_QWORD *)this + 11) )
        {
          v7 = 0;
          if ( v6 < 0 )
          {
            LODWORD(v29) = v6;
            LODWORD(v28) = 1303;
            goto LABEL_60;
          }
LABEL_63:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
        }
      }
    }
    else
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        LODWORD(v29) = TempDir;
        LODWORD(v28) = 1302;
        v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v9,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::ClearRangesFromXml",
                v28,
                v29);
        v11 = (unsigned int)v10;
        if ( v10 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
      }
      v2 = v37;
    }
  }
  else
  {
    v4 = 0;
    v32 = 0;
    v5 = GetLastError();
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v7 = 0;
      if ( v6 < 0 )
      {
        LODWORD(v29) = v6;
        LODWORD(v28) = 1300;
LABEL_60:
        v15 = *((_QWORD *)this + 11);
LABEL_61:
        v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v15,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::ClearRangesFromXml",
                v28,
                v29);
        v7 = (unsigned int)v23;
        if ( v23 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
        goto LABEL_63;
      }
      goto LABEL_63;
    }
  }
LABEL_64:
  UnattendCtxCleanup(&v36);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  v24 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    lpMem = 0;
  }
  if ( v2 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, (LPVOID)(v2 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v4 )
    WIMCloseHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b3cc  push    rbp
0x18000b3ce  push    rbx
0x18000b3cf  push    rsi
0x18000b3d0  push    rdi
0x18000b3d1  push    r14
0x18000b3d3  push    r15
0x18000b3d5  mov     rbp, rsp
0x18000b3d8  sub     rsp, 78h
0x18000b3dc  mov     rdi, rcx
0x18000b3df  xor     r15d, r15d
0x18000b3e2  mov     [rbp+hMem], r15
0x18000b3e6  mov     [rbp+arg_0], r15d
0x18000b3ea  mov     r14d, r15d
0x18000b3ed  mov     [rbp+arg_10], r15
0x18000b3f1  mov     [rbp+lpMem], r15
0x18000b3f5  mov     [rbp+var_40], r15
0x18000b3f9  xorps   xmm0, xmm0
0x18000b3fc  xor     eax, eax
0x18000b3fe  movups  [rbp+var_30], xmm0
0x18000b402  movups  [rbp+var_20], xmm0
0x18000b406  mov     [rbp+var_10], rax
0x18000b40a  mov     [rbp+arg_8], r15
0x18000b40e  mov     [rsp+78h+var_50], r15
0x18000b413  mov     dword ptr [rsp+78h+var_58], r15d
0x18000b418  mov     edx, 0C0000000h
0x18000b41d  mov     r9d, 20000000h
0x18000b423  lea     r8d, [r15+3]
0x18000b427  mov     rcx, [rcx+228h]
0x18000b42e  call    cs:__imp_WIMCreateFile
0x18000b434  mov     rbx, rax
0x18000b437  test    rax, rax
0x18000b43a  jnz     short loc_18000B487
0x18000b43c  mov     ebx, r15d
0x18000b43f  mov     [rbp+var_38], rbx
0x18000b443  call    cs:__imp_GetLastError
0x18000b449  mov     esi, eax
0x18000b44b  test    eax, eax
0x18000b44d  jnz     short loc_18000B456
0x18000b44f  mov     esi, 80004005h
0x18000b454  jmp     short loc_18000B461
0x18000b456  jle     short loc_18000B461
0x18000b458  movzx   esi, ax
0x18000b45b  or      esi, 80070000h
0x18000b461  cmp     [rdi+58h], r15
0x18000b465  jz      loc_18000B76B
0x18000b46b  mov     ecx, r15d
0x18000b46e  test    esi, esi
0x18000b470  jns     loc_18000B766
0x18000b476  mov     dword ptr [rsp+78h+var_50], esi
0x18000b47a  mov     dword ptr [rsp+78h+var_58], 514h
0x18000b482  jmp     loc_18000B73F
0x18000b487  mov     [rbp+var_38], rbx
0x18000b48b  lea     rcx, [rbp+arg_10]
0x18000b48f  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x18000b494  mov     esi, eax
0x18000b496  test    eax, eax
0x18000b498  jns     short loc_18000B4E0
0x18000b49a  mov     rcx, [rdi+58h]
0x18000b49e  test    rcx, rcx
0x18000b4a1  jz      short loc_18000B4D7
0x18000b4a3  mov     dword ptr [rsp+78h+var_50], eax
0x18000b4a7  mov     dword ptr [rsp+78h+var_58], 516h
0x18000b4af  lea     r9, aCdlpactionreco_21; "CDlpActionRecoverCrypto::ClearRangesFro"...
0x18000b4b6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000b4bd  mov     edx, 4
0x18000b4c2  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000b4c7  mov     ecx, eax
0x18000b4c9  test    eax, eax
0x18000b4cb  jns     short loc_18000B4D2
0x18000b4cd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b4d2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b4d7  mov     r14, [rbp+arg_10]
0x18000b4db  jmp     loc_18000B76B
0x18000b4e0  mov     r14, [rbp+arg_10]
0x18000b4e4  mov     rdx, r14
0x18000b4e7  mov     rcx, rbx
0x18000b4ea  call    cs:__imp_WIMSetTemporaryPath
0x18000b4f0  test    eax, eax
0x18000b4f2  jnz     short loc_18000B538
0x18000b4f4  call    cs:__imp_GetLastError
0x18000b4fa  mov     esi, eax
0x18000b4fc  test    eax, eax
0x18000b4fe  jnz     short loc_18000B507
0x18000b500  mov     esi, 80004005h
0x18000b505  jmp     short loc_18000B512
0x18000b507  jle     short loc_18000B512
0x18000b509  movzx   esi, ax
0x18000b50c  or      esi, 80070000h
0x18000b512  cmp     [rdi+58h], r15
0x18000b516  jz      loc_18000B76B
0x18000b51c  mov     ecx, r15d
0x18000b51f  test    esi, esi
0x18000b521  jns     loc_18000B766
0x18000b527  mov     dword ptr [rsp+78h+var_50], esi
0x18000b52b  mov     dword ptr [rsp+78h+var_58], 517h
0x18000b533  jmp     loc_18000B73F
0x18000b538  mov     [rbp+arg_0], r15d
0x18000b53c  lea     r8, [rbp+arg_0]
0x18000b540  lea     rdx, [rbp+hMem]
0x18000b544  mov     rcx, rbx
0x18000b547  call    cs:__imp_WIMGetImageInformation
0x18000b54d  test    eax, eax
0x18000b54f  jnz     short loc_18000B595
0x18000b551  call    cs:__imp_GetLastError
0x18000b557  mov     esi, eax
0x18000b559  test    eax, eax
0x18000b55b  jnz     short loc_18000B564
0x18000b55d  mov     esi, 80004005h
0x18000b562  jmp     short loc_18000B56F
0x18000b564  jle     short loc_18000B56F
0x18000b566  movzx   esi, ax
0x18000b569  or      esi, 80070000h
0x18000b56f  cmp     [rdi+58h], r15
0x18000b573  jz      loc_18000B76B
0x18000b579  mov     ecx, r15d
0x18000b57c  test    esi, esi
0x18000b57e  jns     loc_18000B766
0x18000b584  mov     dword ptr [rsp+78h+var_50], esi
0x18000b588  mov     dword ptr [rsp+78h+var_58], 51Ah
0x18000b590  jmp     loc_18000B73F
0x18000b595  mov     r8d, [rbp+arg_0]
0x18000b599  mov     rdx, [rbp+hMem]
0x18000b59d  lea     rcx, [rbp+arg_8]
0x18000b5a1  call    cs:__imp_UnattendCtxDeserializeBuffer
0x18000b5a7  mov     esi, eax
0x18000b5a9  test    eax, eax
0x18000b5ab  jns     short loc_18000B5CB
0x18000b5ad  mov     rcx, [rdi+58h]
0x18000b5b1  test    rcx, rcx
0x18000b5b4  jz      loc_18000B76B
0x18000b5ba  mov     dword ptr [rsp+78h+var_50], eax
0x18000b5be  mov     dword ptr [rsp+78h+var_58], 51Eh
0x18000b5c6  jmp     loc_18000B743
0x18000b5cb  lea     r8, [rbp+var_30]
0x18000b5cf  lea     rdx, aWimEsdEncrypte_0; "WIM\\ESD\\ENCRYPTED"
0x18000b5d6  lea     rcx, [rbp+arg_8]
0x18000b5da  call    cs:__imp_UnattendCtxOpenNode
0x18000b5e0  mov     esi, eax
0x18000b5e2  test    eax, eax
0x18000b5e4  jns     short loc_18000B604
0x18000b5e6  mov     rcx, [rdi+58h]
0x18000b5ea  test    rcx, rcx
0x18000b5ed  jz      loc_18000B76B
0x18000b5f3  mov     dword ptr [rsp+78h+var_50], eax
0x18000b5f7  mov     dword ptr [rsp+78h+var_58], 51Fh
0x18000b5ff  jmp     loc_18000B743
0x18000b604  lea     rcx, [rbp+arg_8]
0x18000b608  call    cs:__imp_UnattendCtxBeginModify
0x18000b60e  mov     esi, eax
0x18000b610  test    eax, eax
0x18000b612  jns     short loc_18000B632
0x18000b614  mov     rcx, [rdi+58h]
0x18000b618  test    rcx, rcx
0x18000b61b  jz      loc_18000B76B
0x18000b621  mov     dword ptr [rsp+78h+var_50], eax
0x18000b625  mov     dword ptr [rsp+78h+var_58], 523h
0x18000b62d  jmp     loc_18000B743
0x18000b632  lea     rdx, [rbp+var_30]
0x18000b636  lea     rcx, [rbp+arg_8]
0x18000b63a  call    cs:__imp_UnattendCtxRemoveNode
0x18000b640  mov     esi, eax
0x18000b642  test    eax, eax
0x18000b644  jns     short loc_18000B664
0x18000b646  mov     rcx, [rdi+58h]
0x18000b64a  test    rcx, rcx
0x18000b64d  jz      loc_18000B76B
0x18000b653  mov     dword ptr [rsp+78h+var_50], eax
0x18000b657  mov     dword ptr [rsp+78h+var_58], 524h
0x18000b65f  jmp     loc_18000B743
0x18000b664  lea     rcx, [rbp+var_30]
0x18000b668  call    cs:__imp_UnattendFreeNode
0x18000b66e  mov     esi, eax
0x18000b670  test    eax, eax
0x18000b672  jns     short loc_18000B692
0x18000b674  mov     rcx, [rdi+58h]
0x18000b678  test    rcx, rcx
0x18000b67b  jz      loc_18000B76B
0x18000b681  mov     dword ptr [rsp+78h+var_50], eax
0x18000b685  mov     dword ptr [rsp+78h+var_58], 528h
0x18000b68d  jmp     loc_18000B743
0x18000b692  lea     rcx, [rbp+arg_8]
0x18000b696  call    cs:__imp_UnattendCtxCommitModify
0x18000b69c  mov     esi, eax
0x18000b69e  test    eax, eax
0x18000b6a0  jns     short loc_18000B6C0
0x18000b6a2  mov     rcx, [rdi+58h]
0x18000b6a6  test    rcx, rcx
0x18000b6a9  jz      loc_18000B76B
0x18000b6af  mov     dword ptr [rsp+78h+var_50], eax
0x18000b6b3  mov     dword ptr [rsp+78h+var_58], 52Ch
0x18000b6bb  jmp     loc_18000B743
0x18000b6c0  lea     r8, [rbp+var_40]
0x18000b6c4  lea     rdx, [rbp+lpMem]
0x18000b6c8  lea     rcx, [rbp+arg_8]
0x18000b6cc  call    cs:__imp_UnattendCtxSerializeToBuffer
0x18000b6d2  mov     esi, eax
0x18000b6d4  test    eax, eax
0x18000b6d6  jns     short loc_18000B6F3
0x18000b6d8  mov     rcx, [rdi+58h]
0x18000b6dc  test    rcx, rcx
0x18000b6df  jz      loc_18000B76B
0x18000b6e5  mov     dword ptr [rsp+78h+var_50], eax
0x18000b6e9  mov     dword ptr [rsp+78h+var_58], 530h
0x18000b6f1  jmp     short loc_18000B743
0x18000b6f3  mov     r8d, dword ptr [rbp+var_40]
0x18000b6f7  mov     rdx, [rbp+lpMem]
0x18000b6fb  mov     rcx, rbx
0x18000b6fe  call    cs:__imp_WIMSetImageInformation
0x18000b704  test    eax, eax
0x18000b706  jnz     short loc_18000B76B
0x18000b708  call    cs:__imp_GetLastError
0x18000b70e  mov     esi, eax
0x18000b710  test    eax, eax
0x18000b712  jnz     short loc_18000B71B
0x18000b714  mov     esi, 80004005h
0x18000b719  jmp     short loc_18000B726
0x18000b71b  jle     short loc_18000B726
0x18000b71d  movzx   esi, ax
0x18000b720  or      esi, 80070000h
0x18000b726  cmp     [rdi+58h], r15
0x18000b72a  jz      short loc_18000B76B
0x18000b72c  mov     ecx, r15d
0x18000b72f  test    esi, esi
0x18000b731  jns     short loc_18000B766
0x18000b733  mov     dword ptr [rsp+78h+var_50], esi
0x18000b737  mov     dword ptr [rsp+78h+var_58], 531h
0x18000b73f  mov     rcx, [rdi+58h]
0x18000b743  lea     r9, aCdlpactionreco_21; "CDlpActionRecoverCrypto::ClearRangesFro"...
0x18000b74a  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000b751  mov     edx, 4
0x18000b756  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000b75b  mov     ecx, eax
0x18000b75d  test    eax, eax
0x18000b75f  jns     short loc_18000B766
0x18000b761  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b766  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b76b  lea     rcx, [rbp+arg_8]
0x18000b76f  call    cs:__imp_UnattendCtxCleanup
0x18000b775  mov     ecx, esi
0x18000b777  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b77c  nop
0x18000b77d  mov     rdi, [rbp+lpMem]
0x18000b781  test    rdi, rdi
0x18000b784  jz      short loc_18000B79E
0x18000b786  call    cs:__imp_GetProcessHeap
0x18000b78c  mov     rcx, rax; hHeap
0x18000b78f  mov     r8, rdi; lpMem
0x18000b792  xor     edx, edx; dwFlags
0x18000b794  call    cs:__imp_HeapFree
0x18000b79a  mov     [rbp+lpMem], r15
0x18000b79e  test    r14, r14
0x18000b7a1  jz      short loc_18000B7C0
0x18000b7a3  call    cs:__imp_GetProcessHeap
0x18000b7a9  mov     rcx, rax; hHeap
0x18000b7ac  lea     r8, [r14-4]; lpMem
0x18000b7b0  xor     edx, edx; dwFlags
0x18000b7b2  call    cs:__imp_HeapFree
0x18000b7b8  xor     ecx, ecx
0x18000b7ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b7bf  nop
0x18000b7c0  mov     rcx, [rbp+hMem]; hMem
0x18000b7c4  test    rcx, rcx
0x18000b7c7  jz      short loc_18000B7D3
0x18000b7c9  call    cs:__imp_LocalFree
0x18000b7cf  mov     [rbp+hMem], r15
0x18000b7d3  test    rbx, rbx
0x18000b7d6  jz      short loc_18000B7E1
0x18000b7d8  mov     rcx, rbx
0x18000b7db  call    cs:__imp_WIMCloseHandle
0x18000b7e1  mov     eax, esi
0x18000b7e3  add     rsp, 78h
0x18000b7e7  pop     r15
0x18000b7e9  pop     r14
0x18000b7eb  pop     rdi
0x18000b7ec  pop     rsi
0x18000b7ed  pop     rbx
0x18000b7ee  pop     rbp
0x18000b7ef  retn
```
