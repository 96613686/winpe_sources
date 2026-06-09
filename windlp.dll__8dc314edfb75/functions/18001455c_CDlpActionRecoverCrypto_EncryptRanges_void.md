# CDlpActionRecoverCrypto::EncryptRanges(void)

- ea: `0x18001455c`
- end: `0x180014cc5`
- name: `?EncryptRanges@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `1897`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013444`

## callees

- `0x18000aba4`
- `0x18000f920`
- `0x180012f5c`
- `0x18001455c`
- `0x18001c4f0`
- `0x18001cc44`
- `0x18001fd60`
- `0x180028640`
- `0x18002877c`
- `0x18002b728`
- `0x180038c34`
- `0x1800392f4`
- `0x180081010`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x180014c91`
- `WIMGAPI!WIMCloseHandle` at `0x180014c91`
- `WIMGAPI!WIMReadFileEx` at `0x180014820`
- `WIMGAPI!WIMReadFileEx` at `0x180014820`
- `WIMGAPI!WIMWriteFileWithIntegrity` at `0x18001473c`
- `WIMGAPI!WIMWriteFileWithIntegrity` at `0x18001494f`
- `WIMGAPI!WIMWriteFileWithIntegrity` at `0x18001473c`
- `WIMGAPI!WIMWriteFileWithIntegrity` at `0x18001494f`
- `WIMGAPI!WIMCreateFile` at `0x1800145a0`
- `WIMGAPI!WIMCreateFile` at `0x1800145a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014672`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014c9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014672`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014c9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014680`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800147b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014680`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800147b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014c30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014cab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014c30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b93`

## string_xrefs

- `0x180014b44`: `CDlpActionRecoverCrypto::DeleteSavedCryptedBuffer`
- `0x180014bd4`: `CDlpActionRecoverCrypto::DeleteSavedCryptedBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpActionRecoverCrypto::EncryptRanges(CDlpActionRecoverCrypto *this)
{
  void *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rdi
  signed int LastError; // eax
  signed int v6; // r14d
  __int64 v7; // rcx
  unsigned __int16 *v8; // rcx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  void *v13; // rax
  int SavedCryptedBuffer; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // eax
  int v18; // ecx
  signed int v19; // r12d
  unsigned int v20; // esi
  HANDLE v21; // rax
  void *v22; // rsi
  HANDLE v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  unsigned __int16 *v29; // rsi
  int v30; // eax
  __int64 v31; // r8
  int v32; // eax
  int v33; // eax
  unsigned __int16 *v34; // rsi
  int WorkingPath; // eax
  __int64 v36; // rcx
  signed int v37; // eax
  int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  signed int v42; // eax
  __int64 v43; // rcx
  int v44; // eax
  HANDLE v45; // rax
  int v46; // eax
  HANDLE v47; // rax
  __int64 v49; // [rsp+20h] [rbp-48h]
  __int64 v50; // [rsp+28h] [rbp-40h]
  __int128 v51; // [rsp+40h] [rbp-28h] BYREF
  __int128 v52; // [rsp+50h] [rbp-18h]
  unsigned __int16 *v53; // [rsp+B8h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v55; // [rsp+C8h] [rbp+60h]

  v2 = 0;
  v51 = 0;
  v52 = 0;
  v3 = WIMCreateFile(*((_QWORD *)this + 69), 0, 3, 0x20000000, 0, 0);
  v4 = v3;
  if ( !v3 )
  {
    v55 = 0;
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
        LODWORD(v50) = v6;
        LODWORD(v49) = 1176;
        goto LABEL_9;
      }
      goto LABEL_99;
    }
    goto LABEL_100;
  }
  v55 = v3;
  if ( !*((_DWORD *)this + 160) )
    goto LABEL_27;
  v9 = *((_DWORD *)this + 184);
  v10 = *((_DWORD *)this + 183);
  if ( v9 == -1 )
  {
    if ( v10 != -1 )
      goto LABEL_15;
  }
  else if ( v9 < v10 )
  {
LABEL_15:
    if ( *((_QWORD *)this + 11) )
    {
      LODWORD(v49) = *((_DWORD *)this + 184);
      CDlpLogT<CEmptyType>::DlpLogFormat(
        *((_QWORD *)this + 11),
        2u,
        (__int64)L"Encryption/decryption resumed. Saved range: [%d], last written range: [%d].",
        v10,
        v49);
      v10 = *((_DWORD *)this + 183);
    }
    v11 = *(_DWORD *)(*((_QWORD *)this + 78) + 16LL * (int)v10 + 8);
    ProcessHeap = GetProcessHeap();
    v13 = HeapAlloc(ProcessHeap, 0, v11);
    v2 = v13;
    if ( !v13 )
    {
      v6 = -2147024882;
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( v8 )
      {
        LODWORD(v50) = -2147024882;
        LODWORD(v49) = 1191;
        goto LABEL_97;
      }
      goto LABEL_100;
    }
    SavedCryptedBuffer = CDlpActionRecoverCrypto::GetSavedCryptedBuffer(
                           this,
                           v13,
                           *(_DWORD *)(*((_QWORD *)this + 78) + 16LL * *((int *)this + 183) + 8));
    v6 = SavedCryptedBuffer;
    if ( SavedCryptedBuffer < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( v8 )
      {
        LODWORD(v50) = SavedCryptedBuffer;
        LODWORD(v49) = 1195;
        goto LABEL_97;
      }
      goto LABEL_100;
    }
    v51 = 0;
    v52 = 0;
    v15 = *((_QWORD *)this + 78);
    v16 = 2LL * *((int *)this + 183);
    *(_QWORD *)&v52 = *(_QWORD *)(v15 + 16LL * *((int *)this + 183));
    v17 = WIMWriteFileWithIntegrity(v4, v2, *(unsigned int *)(v15 + 8 * v16 + 8), &v51);
    v6 = v17;
    if ( v17 < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( v8 )
      {
        LODWORD(v50) = v17;
        LODWORD(v49) = 1203;
        goto LABEL_97;
      }
      goto LABEL_100;
    }
    *((_DWORD *)this + 184) = *((_DWORD *)this + 183);
  }
LABEL_27:
  v53 = 0;
  v18 = *((_DWORD *)this + 184);
  v19 = 0;
  if ( v18 != -1 )
    v19 = v18 + 1;
  while ( 1 )
  {
    if ( v19 >= *((_DWORD *)this + 155) )
    {
      v34 = 0;
      v53 = 0;
      bstrString = 0;
      WorkingPath = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(
                      this,
                      &bstrString);
      v6 = WorkingPath;
      if ( WorkingPath < 0 )
      {
        v36 = *((_QWORD *)this + 11);
        if ( !v36 )
          goto LABEL_90;
        LODWORD(v50) = WorkingPath;
        LODWORD(v49) = 1141;
        goto LABEL_87;
      }
      v38 = STRAPI_Format(&v53, L"%s\\%s", bstrString, L"CryptoSavedBuffer.tmp");
      v6 = v38;
      if ( v38 >= 0 )
      {
        v34 = v53;
        if ( (unsigned int)FileExists(v53) && !DeleteFileEx2((__int64)v34, 0) )
        {
          v42 = GetLastError();
          v6 = v42;
          if ( v42 )
          {
            if ( v42 > 0 )
              v6 = (unsigned __int16)v42 | 0x80070000;
          }
          else
          {
            v6 = -2147467259;
          }
          if ( *((_QWORD *)this + 11) )
          {
            v43 = 0;
            if ( v6 >= 0 )
            {
LABEL_89:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v43);
              goto LABEL_90;
            }
            LODWORD(v50) = v6;
            LODWORD(v49) = 1146;
            v36 = *((_QWORD *)this + 11);
LABEL_87:
            v44 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v36,
                    4u,
                    (__int64)L"%s(%d): Result = 0x%X",
                    L"CDlpActionRecoverCrypto::DeleteSavedCryptedBuffer",
                    v49,
                    v50);
            v43 = (unsigned int)v44;
            if ( v44 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v44);
            goto LABEL_89;
          }
        }
      }
      else
      {
        v39 = *((_QWORD *)this + 11);
        if ( v39 )
        {
          LODWORD(v50) = v38;
          LODWORD(v49) = 1142;
          v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v39,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionRecoverCrypto::DeleteSavedCryptedBuffer",
                  v49,
                  v50);
          v41 = (unsigned int)v40;
          if ( v40 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v40);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v41);
        }
        v34 = v53;
      }
LABEL_90:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v34 )
      {
        v45 = GetProcessHeap();
        HeapFree(v45, 0, v34 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      if ( v6 < 0 )
      {
        v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
        if ( v8 )
        {
          LODWORD(v50) = v6;
          LODWORD(v49) = 1269;
          goto LABEL_97;
        }
      }
      goto LABEL_100;
    }
    v20 = *(_DWORD *)(*((_QWORD *)this + 78) + 16LL * v19 + 8);
    v21 = GetProcessHeap();
    v22 = HeapAlloc(v21, 0, v20);
    if ( v2 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v2);
    }
    if ( !v22 )
    {
      v2 = 0;
      v6 = -2147024882;
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = -2147024882;
      LODWORD(v49) = 1219;
      goto LABEL_97;
    }
    v2 = v22;
    v51 = 0;
    v52 = 0;
    v24 = *((_QWORD *)this + 78);
    *(_QWORD *)&v52 = *(_QWORD *)(v24 + 16LL * v19);
    if ( !(unsigned int)WIMReadFileEx(v4, v22, *(unsigned int *)(v24 + 16LL * v19 + 8), &v51, 0) )
      break;
    v25 = *((_QWORD *)this + 78);
    if ( (*(_BYTE *)(v25 + 16LL * v19 + 8) & 0xF) != 0 )
    {
      v26 = *((_QWORD *)this + 11);
      if ( v26 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v26,
          3u,
          (__int64)L"Not crypting [%d] bytes at the end of the buffer.",
          *(_DWORD *)(v25 + 16LL * v19 + 8) & 0xF);
    }
    v27 = CDlpCryptoApiHelperT<CEmptyType>::CryptDataInPlace(
            *((_QWORD *)this + 86),
            *((unsigned int *)this + 176),
            *((_QWORD *)this + 87),
            v22,
            *(_DWORD *)(*((_QWORD *)this + 78) + 16LL * v19 + 8) & 0xFFFFFFF0);
    v6 = v27;
    if ( v27 < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = v27;
      LODWORD(v49) = 1237;
      goto LABEL_97;
    }
    v28 = CDlpActionRecoverCrypto::SaveCryptedBuffer(this, v22, *(_DWORD *)(*((_QWORD *)this + 78) + 16LL * v19 + 8));
    v6 = v28;
    v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
    if ( v28 < 0 )
    {
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = v28;
      LODWORD(v49) = 1239;
      goto LABEL_97;
    }
    *((_DWORD *)this + 183) = v19;
    if ( v8 )
    {
      v6 = 0;
      v29 = v8;
      v53 = v8;
    }
    else
    {
      v6 = -2147483638;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147483638);
      v29 = v53;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
    if ( v6 < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = v6;
      LODWORD(v49) = 1247;
      goto LABEL_97;
    }
    v30 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v29 + 280LL))(v29, 1);
    v6 = v30;
    if ( v30 < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = v30;
      LODWORD(v49) = 1248;
      goto LABEL_97;
    }
    v51 = 0;
    v52 = 0;
    v31 = *((_QWORD *)this + 78);
    *(_QWORD *)&v52 = *(_QWORD *)(v31 + 16LL * v19);
    v32 = WIMWriteFileWithIntegrity(v4, v2, *(unsigned int *)(v31 + 16LL * v19 + 8), &v51);
    v6 = v32;
    if ( v32 < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = v32;
      LODWORD(v49) = 1256;
      goto LABEL_97;
    }
    *((_DWORD *)this + 184) = v19;
    v33 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v29 + 280LL))(v29, 1);
    v6 = v33;
    if ( v33 < 0 )
    {
      v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_100;
      LODWORD(v50) = v33;
      LODWORD(v49) = 1264;
      goto LABEL_97;
    }
    CDlpActionRecoverCrypto::SetProgressData(this, v19++, *((_DWORD *)this + 155));
  }
  v37 = GetLastError();
  v6 = v37;
  if ( v37 )
  {
    if ( v37 > 0 )
      v6 = (unsigned __int16)v37 | 0x80070000;
  }
  else
  {
    v6 = -2147467259;
  }
  if ( !*((_QWORD *)this + 11) )
    goto LABEL_100;
  v7 = 0;
  if ( v6 >= 0 )
    goto LABEL_99;
  LODWORD(v50) = v6;
  LODWORD(v49) = 1225;
LABEL_9:
  v8 = (unsigned __int16 *)*((_QWORD *)this + 11);
LABEL_97:
  v46 = CDlpLogT<CEmptyType>::DlpLogFormat(
          (__int64)v8,
          4u,
          (__int64)L"%s(%d): Result = 0x%X",
          L"CDlpActionRecoverCrypto::EncryptRanges",
          v49,
          v50);
  v7 = (unsigned int)v46;
  if ( v46 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v46);
LABEL_99:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
LABEL_100:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v4 )
    WIMCloseHandle(v4);
  if ( v2 )
  {
    v47 = GetProcessHeap();
    HeapFree(v47, 0, v2);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001455c  push    rbp
0x18001455e  push    rbx
0x18001455f  push    rsi
0x180014560  push    rdi
0x180014561  push    r12
0x180014563  push    r13
0x180014565  push    r14
0x180014567  push    r15
0x180014569  mov     rbp, rsp
0x18001456c  sub     rsp, 68h
0x180014570  mov     r15, rcx
0x180014573  xor     ebx, ebx
0x180014575  mov     [rbp+arg_0], rbx
0x180014579  xorps   xmm0, xmm0
0x18001457c  movups  [rbp+var_28], xmm0
0x180014580  movups  [rbp+var_18], xmm0
0x180014584  mov     [rsp+68h+var_40], rbx
0x180014589  mov     dword ptr [rsp+68h+var_48], ebx
0x18001458d  xor     edx, edx
0x18001458f  mov     r9d, 20000000h
0x180014595  lea     r8d, [rbx+3]
0x180014599  mov     rcx, [rcx+228h]
0x1800145a0  call    cs:__imp_WIMCreateFile
0x1800145a6  mov     rdi, rax
0x1800145a9  test    rax, rax
0x1800145ac  jnz     short loc_1800145FF
0x1800145ae  mov     [rbp+arg_18], rax
0x1800145b2  call    cs:__imp_GetLastError
0x1800145b8  mov     r14d, eax
0x1800145bb  test    eax, eax
0x1800145bd  jnz     short loc_1800145C7
0x1800145bf  mov     r14d, 80004005h
0x1800145c5  jmp     short loc_1800145D4
0x1800145c7  jle     short loc_1800145D4
0x1800145c9  movzx   r14d, ax
0x1800145cd  or      r14d, 80070000h
0x1800145d4  cmp     [r15+58h], rdi
0x1800145d8  jz      loc_180014C80
0x1800145de  xor     ecx, ecx
0x1800145e0  test    r14d, r14d
0x1800145e3  jns     loc_180014C7B
0x1800145e9  mov     dword ptr [rsp+68h+var_40], r14d
0x1800145ee  mov     dword ptr [rsp+68h+var_48], 498h
0x1800145f6  mov     rcx, [r15+58h]
0x1800145fa  jmp     loc_180014C58
0x1800145ff  mov     [rbp+arg_18], rdi
0x180014603  or      esi, 0FFFFFFFFh
0x180014606  cmp     dword ptr [r15+280h], 0
0x18001460e  jz      loc_180014775
0x180014614  mov     ecx, [r15+2E0h]
0x18001461b  mov     eax, [r15+2DCh]
0x180014622  cmp     ecx, esi
0x180014624  jnz     short loc_180014630
0x180014626  cmp     eax, esi
0x180014628  jz      loc_180014775
0x18001462e  jmp     short loc_180014638
0x180014630  cmp     ecx, eax
0x180014632  jnb     loc_180014775
0x180014638  cmp     qword ptr [r15+58h], 0
0x18001463d  jz      short loc_180014662
0x18001463f  mov     dword ptr [rsp+68h+var_48], ecx
0x180014643  mov     r9d, eax
0x180014646  lea     r8, aEncryptionDecr; "Encryption/decryption resumed. Saved ra"...
0x18001464d  mov     edx, 2
0x180014652  mov     rcx, [r15+58h]
0x180014656  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001465b  mov     eax, [r15+2DCh]
0x180014662  mov     rcx, [r15+270h]
0x180014669  cdqe
0x18001466b  add     rax, rax
0x18001466e  mov     ebx, [rcx+rax*8+8]
0x180014672  call    cs:__imp_GetProcessHeap
0x180014678  mov     rcx, rax; hHeap
0x18001467b  mov     r8d, ebx; dwBytes
0x18001467e  xor     edx, edx; dwFlags
0x180014680  call    cs:__imp_HeapAlloc
0x180014686  mov     rbx, rax
0x180014689  test    rax, rax
0x18001468c  jnz     short loc_1800146B8
0x18001468e  mov     [rbp+arg_0], rax
0x180014692  mov     eax, 8007000Eh
0x180014697  mov     r14d, eax
0x18001469a  mov     rcx, [r15+58h]
0x18001469e  test    rcx, rcx
0x1800146a1  jz      loc_180014C80
0x1800146a7  mov     dword ptr [rsp+68h+var_40], eax
0x1800146ab  mov     dword ptr [rsp+68h+var_48], 4A7h
0x1800146b3  jmp     loc_180014C58
0x1800146b8  mov     [rbp+arg_0], rbx
0x1800146bc  mov     rax, [r15+270h]
0x1800146c3  movsxd  r8, dword ptr [r15+2DCh]
0x1800146ca  add     r8, r8
0x1800146cd  mov     r8d, [rax+r8*8+8]; unsigned int
0x1800146d2  mov     rdx, rbx; void *
0x1800146d5  mov     rcx, r15; this
0x1800146d8  call    ?GetSavedCryptedBuffer@CDlpActionRecoverCrypto@@AEAAJPEAXK@Z; CDlpActionRecoverCrypto::GetSavedCryptedBuffer(void *,ulong)
0x1800146dd  mov     r14d, eax
0x1800146e0  test    eax, eax
0x1800146e2  jns     short loc_180014702
0x1800146e4  mov     rcx, [r15+58h]
0x1800146e8  test    rcx, rcx
0x1800146eb  jz      loc_180014C80
0x1800146f1  mov     dword ptr [rsp+68h+var_40], eax
0x1800146f5  mov     dword ptr [rsp+68h+var_48], 4ABh
0x1800146fd  jmp     loc_180014C58
0x180014702  xorps   xmm0, xmm0
0x180014705  movups  [rbp+var_28], xmm0
0x180014709  movups  [rbp+var_18], xmm0
0x18001470d  mov     rcx, [r15+270h]
0x180014714  movsxd  r8, dword ptr [r15+2DCh]
0x18001471b  add     r8, r8
0x18001471e  mov     eax, [rcx+r8*8]
0x180014722  mov     dword ptr [rbp+var_18], eax
0x180014725  mov     eax, [rcx+r8*8+4]
0x18001472a  mov     dword ptr [rbp+var_18+4], eax
0x18001472d  lea     r9, [rbp+var_28]
0x180014731  mov     r8d, [rcx+r8*8+8]
0x180014736  mov     rdx, rbx
0x180014739  mov     rcx, rdi
0x18001473c  call    cs:__imp_WIMWriteFileWithIntegrity
0x180014742  mov     r14d, eax
0x180014745  test    eax, eax
0x180014747  jns     short loc_180014767
0x180014749  mov     rcx, [r15+58h]
0x18001474d  test    rcx, rcx
0x180014750  jz      loc_180014C80
0x180014756  mov     dword ptr [rsp+68h+var_40], eax
0x18001475a  mov     dword ptr [rsp+68h+var_48], 4B3h
0x180014762  jmp     loc_180014C58
0x180014767  mov     eax, [r15+2DCh]
0x18001476e  mov     [r15+2E0h], eax
0x180014775  mov     [rbp+arg_8], 0
0x18001477d  mov     ecx, [r15+2E0h]
0x180014784  lea     eax, [rcx+1]
0x180014787  xor     r12d, r12d
0x18001478a  cmp     ecx, esi
0x18001478c  cmovnz  r12d, eax
0x180014790  jmp     loc_18001499A
0x180014795  mov     rax, [r15+270h]
0x18001479c  movsxd  r13, r12d
0x18001479f  add     r13, r13
0x1800147a2  mov     esi, [rax+r13*8+8]
0x1800147a7  call    cs:__imp_GetProcessHeap
0x1800147ad  mov     rcx, rax; hHeap
0x1800147b0  mov     r8d, esi; dwBytes
0x1800147b3  xor     edx, edx; dwFlags
0x1800147b5  call    cs:__imp_HeapAlloc
0x1800147bb  mov     rsi, rax
0x1800147be  test    rbx, rbx
0x1800147c1  jz      short loc_1800147D7
0x1800147c3  call    cs:__imp_GetProcessHeap
0x1800147c9  mov     rcx, rax; hHeap
0x1800147cc  mov     r8, rbx; lpMem
0x1800147cf  xor     edx, edx; dwFlags
0x1800147d1  call    cs:__imp_HeapFree
0x1800147d7  test    rsi, rsi
0x1800147da  jz      loc_180014AE1
0x1800147e0  mov     rbx, rsi
0x1800147e3  mov     [rbp+arg_0], rbx
0x1800147e7  xorps   xmm0, xmm0
0x1800147ea  movups  [rbp+var_28], xmm0
0x1800147ee  movups  [rbp+var_18], xmm0
0x1800147f2  mov     r8, [r15+270h]
0x1800147f9  mov     eax, [r8+r13*8]
0x1800147fd  mov     dword ptr [rbp+var_18], eax
0x180014800  mov     eax, [r8+r13*8+4]
0x180014805  mov     dword ptr [rbp+var_18+4], eax
0x180014808  mov     [rsp+68h+var_48], 0
0x180014811  lea     r9, [rbp+var_28]
0x180014815  mov     r8d, [r8+r13*8+8]
0x18001481a  mov     rdx, rsi
0x18001481d  mov     rcx, rdi
0x180014820  call    cs:__imp_WIMReadFileEx
0x180014826  test    eax, eax
0x180014828  jz      loc_180014A97
0x18001482e  mov     r9, [r15+270h]
0x180014835  test    byte ptr [r9+r13*8+8], 0Fh
0x18001483b  jz      short loc_180014860
0x18001483d  mov     rcx, [r15+58h]
0x180014841  test    rcx, rcx
0x180014844  jz      short loc_180014860
0x180014846  mov     r9d, [r9+r13*8+8]
0x18001484b  and     r9d, 0Fh
0x18001484f  lea     r8, aNotCryptingDBy; "Not crypting [%d] bytes at the end of t"...
0x180014856  mov     edx, 3
0x18001485b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180014860  mov     rax, [r15+270h]
0x180014867  mov     edx, [rax+r13*8+8]
0x18001486c  and     edx, 0FFFFFFF0h
0x18001486f  mov     dword ptr [rsp+68h+var_48], edx
0x180014873  mov     r9, rbx
0x180014876  mov     r8, [r15+2B8h]
0x18001487d  mov     edx, [r15+2C0h]
0x180014884  mov     rcx, [r15+2B0h]
0x18001488b  call    ?CryptDataInPlace@?$CDlpCryptoApiHelperT@VCEmptyType@@@@QEAAJHPEAVCSymmetricKeyValue@@PEBXKKK@Z; CDlpCryptoApiHelperT<CEmptyType>::CryptDataInPlace(int,CSymmetricKeyValue *,void const *,ulong,ulong,ulong)
0x180014890  mov     r14d, eax
0x180014893  test    eax, eax
0x180014895  js      loc_180014A79
0x18001489b  mov     r8, [r15+270h]
0x1800148a2  mov     r8d, [r8+r13*8+8]; unsigned int
0x1800148a7  mov     rdx, rbx; void *
0x1800148aa  mov     rcx, r15; this
0x1800148ad  call    ?SaveCryptedBuffer@CDlpActionRecoverCrypto@@AEAAJPEAXK@Z; CDlpActionRecoverCrypto::SaveCryptedBuffer(void *,ulong)
0x1800148b2  mov     r14d, eax
0x1800148b5  mov     rcx, [r15+58h]
0x1800148b9  test    eax, eax
0x1800148bb  js      loc_180014A5F
0x1800148c1  mov     [r15+2DCh], r12d
0x1800148c8  test    rcx, rcx
0x1800148cb  jnz     short loc_1800148E2
0x1800148cd  mov     eax, 8000000Ah
0x1800148d2  mov     r14d, eax
0x1800148d5  mov     ecx, eax
0x1800148d7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800148dc  mov     rsi, [rbp+arg_8]
0x1800148e0  jmp     short loc_1800148EC
0x1800148e2  xor     r14d, r14d
0x1800148e5  mov     rsi, rcx
0x1800148e8  mov     [rbp+arg_8], rcx
0x1800148ec  mov     ecx, r14d
0x1800148ef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800148f4  test    r14d, r14d
0x1800148f7  js      loc_180014A40
0x1800148fd  mov     rax, [rsi]
0x180014900  mov     edx, 1
0x180014905  mov     rcx, rsi
0x180014908  mov     rax, [rax+118h]
0x18001490f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014914  mov     r14d, eax
0x180014917  test    eax, eax
0x180014919  js      loc_180014A22
0x18001491f  xorps   xmm0, xmm0
0x180014922  movups  [rbp+var_28], xmm0
0x180014926  movups  [rbp+var_18], xmm0
0x18001492a  mov     r8, [r15+270h]
0x180014931  mov     eax, [r8+r13*8]
0x180014935  mov     dword ptr [rbp+var_18], eax
0x180014938  mov     eax, [r8+r13*8+4]
0x18001493d  mov     dword ptr [rbp+var_18+4], eax
0x180014940  lea     r9, [rbp+var_28]
0x180014944  mov     r8d, [r8+r13*8+8]
0x180014949  mov     rdx, rbx
0x18001494c  mov     rcx, rdi
0x18001494f  call    cs:__imp_WIMWriteFileWithIntegrity
0x180014955  mov     r14d, eax
0x180014958  test    eax, eax
0x18001495a  js      loc_180014A04
0x180014960  mov     [r15+2E0h], r12d
0x180014967  mov     rax, [rsi]
0x18001496a  mov     edx, 1
0x18001496f  mov     rcx, rsi
0x180014972  mov     rax, [rax+118h]
0x180014979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001497e  mov     r14d, eax
0x180014981  test    eax, eax
0x180014983  js      short loc_1800149E6
0x180014985  mov     r8d, [r15+26Ch]; unsigned int
0x18001498c  mov     edx, r12d; unsigned int
0x18001498f  mov     rcx, r15; this
0x180014992  call    ?SetProgressData@CDlpActionRecoverCrypto@@AEAAJKK@Z; CDlpActionRecoverCrypto::SetProgressData(ulong,ulong)
0x180014997  inc     r12d
0x18001499a  cmp     r12d, [r15+26Ch]
0x1800149a1  jl      loc_180014795
0x1800149a7  xor     esi, esi
0x1800149a9  mov     [rbp+arg_8], rsi
0x1800149ad  mov     [rbp+bstrString], rsi
0x1800149b1  lea     rdx, [rbp+bstrString]
0x1800149b5  mov     rcx, r15
0x1800149b8  call    ?GetWorkingPath@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJPEAPEAG@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(ushort * *)
0x1800149bd  mov     r14d, eax
0x1800149c0  test    eax, eax
0x1800149c2  jns     loc_180014B0D
0x1800149c8  mov     rcx, [r15+58h]
0x1800149cc  test    rcx, rcx
0x1800149cf  jz      loc_180014BFC
0x1800149d5  mov     dword ptr [rsp+68h+var_40], eax
0x1800149d9  mov     dword ptr [rsp+68h+var_48], 475h
0x1800149e1  jmp     loc_180014BD4
0x1800149e6  mov     rcx, [r15+58h]
0x1800149ea  test    rcx, rcx
0x1800149ed  jz      loc_180014C80
0x1800149f3  mov     dword ptr [rsp+68h+var_40], eax
0x1800149f7  mov     dword ptr [rsp+68h+var_48], 4F0h
0x1800149ff  jmp     loc_180014C58
0x180014a04  mov     rcx, [r15+58h]
0x180014a08  test    rcx, rcx
0x180014a0b  jz      loc_180014C80
0x180014a11  mov     dword ptr [rsp+68h+var_40], eax
0x180014a15  mov     dword ptr [rsp+68h+var_48], 4E8h
0x180014a1d  jmp     loc_180014C58
0x180014a22  mov     rcx, [r15+58h]
0x180014a26  test    rcx, rcx
0x180014a29  jz      loc_180014C80
0x180014a2f  mov     dword ptr [rsp+68h+var_40], eax
0x180014a33  mov     dword ptr [rsp+68h+var_48], 4E0h
0x180014a3b  jmp     loc_180014C58
0x180014a40  mov     rcx, [r15+58h]
0x180014a44  test    rcx, rcx
0x180014a47  jz      loc_180014C80
0x180014a4d  mov     dword ptr [rsp+68h+var_40], r14d
  ... truncated ...
```
