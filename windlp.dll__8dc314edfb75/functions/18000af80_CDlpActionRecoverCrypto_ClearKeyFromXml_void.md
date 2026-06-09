# CDlpActionRecoverCrypto::ClearKeyFromXml(void)

- ea: `0x18000af80`
- end: `0x18000b3c5`
- name: `?ClearKeyFromXml@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `1093`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fb18`

## callees

- `0x18000aba4`
- `0x18000af80`
- `0x180012f5c`
- `0x18001c9d0`
- `0x18001fd60`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18000b3b0`
- `WIMGAPI!WIMCloseHandle` at `0x18000b3b0`
- `WIMGAPI!WIMGetImageInformation` at `0x18000b11c`
- `WIMGAPI!WIMGetImageInformation` at `0x18000b11c`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000b0bf`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000b0bf`
- `WIMGAPI!WIMSetImageInformation` at `0x18000b2d3`
- `WIMGAPI!WIMSetImageInformation` at `0x18000b2d3`
- `WIMGAPI!WIMCreateFile` at `0x18000b003`
- `WIMGAPI!WIMCreateFile` at `0x18000b003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b35b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b35b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b369`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b387`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b369`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b39e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b39e`
- `UNATTEND!UnattendFreeNode` at `0x18000b23d`
- `UNATTEND!UnattendFreeNode` at `0x18000b23d`
- `UNATTEND!UnattendCtxOpenNode` at `0x18000b1af`
- `UNATTEND!UnattendCtxOpenNode` at `0x18000b1af`
- `UNATTEND!UnattendCtxCleanup` at `0x18000b344`
- `UNATTEND!UnattendCtxCleanup` at `0x18000b344`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x18000b2a1`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x18000b2a1`
- `UNATTEND!UnattendCtxRemoveNode` at `0x18000b20f`
- `UNATTEND!UnattendCtxRemoveNode` at `0x18000b20f`
- `UNATTEND!UnattendCtxBeginModify` at `0x18000b1dd`
- `UNATTEND!UnattendCtxBeginModify` at `0x18000b1dd`
- `UNATTEND!UnattendCtxCommitModify` at `0x18000b26b`
- `UNATTEND!UnattendCtxCommitModify` at `0x18000b26b`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18000b176`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18000b176`

## string_xrefs

- `0x18000b084`: `CDlpActionRecoverCrypto::ClearKeyFromXml`
- `0x18000b318`: `CDlpActionRecoverCrypto::ClearKeyFromXml`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::ClearKeyFromXml(CDlpActionRecoverCrypto *this)
{
  __int64 v2; // r14
  __int64 v3; // rax
  char v4; // dl
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  signed int v8; // eax
  signed int v9; // esi
  __int64 v10; // rcx
  int TempDir; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  signed int v15; // eax
  signed int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  signed int LastError; // eax
  int v26; // eax
  void *v27; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  __int64 v31; // [rsp+20h] [rbp-58h]
  __int64 v32; // [rsp+28h] [rbp-50h]
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  __int64 v34; // [rsp+38h] [rbp-40h] BYREF
  __int64 v35; // [rsp+40h] [rbp-38h]
  _OWORD v36[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v37; // [rsp+68h] [rbp-10h]
  unsigned int v38; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v39; // [rsp+B8h] [rbp+40h] BYREF
  __int64 v40; // [rsp+C0h] [rbp+48h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp+50h] BYREF

  hMem = 0;
  v38 = 0;
  v2 = 0;
  v40 = 0;
  lpMem = 0;
  v34 = 0;
  memset(v36, 0, sizeof(v36));
  v37 = 0;
  v39 = 0;
  v3 = *((_QWORD *)this + 70);
  if ( v3 || (v3 = *((_QWORD *)this + 69), v4 = 1, v3) )
    v4 = 0;
  v5 = 0;
  if ( !v4 )
    v5 = v3;
  v6 = WIMCreateFile(v5, 3221225472LL, 3, 0x20000000, 0, 0);
  v7 = v6;
  if ( v6 )
  {
    v35 = v6;
    TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v40);
    v9 = TempDir;
    if ( TempDir >= 0 )
    {
      v2 = v40;
      if ( (unsigned int)WIMSetTemporaryPath(v7, v40) )
      {
        v38 = 0;
        if ( (unsigned int)WIMGetImageInformation(v7, &hMem, &v38) )
        {
          v17 = UnattendCtxDeserializeBuffer(&v39, hMem, v38);
          v9 = v17;
          if ( v17 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v17;
            LODWORD(v31) = 1947;
            goto LABEL_66;
          }
          v19 = UnattendCtxOpenNode(&v39, L"WIM\\ESD\\KEY", v36);
          v9 = v19;
          if ( v19 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v19;
            LODWORD(v31) = 1948;
            goto LABEL_66;
          }
          v20 = UnattendCtxBeginModify(&v39);
          v9 = v20;
          if ( v20 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v20;
            LODWORD(v31) = 1952;
            goto LABEL_66;
          }
          v21 = UnattendCtxRemoveNode(&v39, v36);
          v9 = v21;
          if ( v21 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v21;
            LODWORD(v31) = 1953;
            goto LABEL_66;
          }
          v22 = UnattendFreeNode(v36);
          v9 = v22;
          if ( v22 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v22;
            LODWORD(v31) = 1957;
            goto LABEL_66;
          }
          v23 = UnattendCtxCommitModify(&v39);
          v9 = v23;
          if ( v23 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v23;
            LODWORD(v31) = 1961;
            goto LABEL_66;
          }
          v24 = UnattendCtxSerializeToBuffer(&v39, &lpMem, &v34);
          v9 = v24;
          if ( v24 < 0 )
          {
            v18 = *((_QWORD *)this + 11);
            if ( !v18 )
              goto LABEL_69;
            LODWORD(v32) = v24;
            LODWORD(v31) = 1965;
            goto LABEL_66;
          }
          if ( !(unsigned int)WIMSetImageInformation(v7, lpMem, (unsigned int)v34) )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError )
            {
              if ( LastError > 0 )
                v9 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v9 = -2147467259;
            }
            if ( *((_QWORD *)this + 11) )
            {
              v10 = 0;
              if ( v9 < 0 )
              {
                LODWORD(v32) = v9;
                LODWORD(v31) = 1966;
                goto LABEL_65;
              }
              goto LABEL_68;
            }
          }
        }
        else
        {
          v16 = GetLastError();
          v9 = v16;
          if ( v16 )
          {
            if ( v16 > 0 )
              v9 = (unsigned __int16)v16 | 0x80070000;
          }
          else
          {
            v9 = -2147467259;
          }
          if ( *((_QWORD *)this + 11) )
          {
            v10 = 0;
            if ( v9 < 0 )
            {
              LODWORD(v32) = v9;
              LODWORD(v31) = 1943;
              goto LABEL_65;
            }
            goto LABEL_68;
          }
        }
      }
      else
      {
        v15 = GetLastError();
        v9 = v15;
        if ( v15 )
        {
          if ( v15 > 0 )
            v9 = (unsigned __int16)v15 | 0x80070000;
        }
        else
        {
          v9 = -2147467259;
        }
        if ( *((_QWORD *)this + 11) )
        {
          v10 = 0;
          if ( v9 < 0 )
          {
            LODWORD(v32) = v9;
            LODWORD(v31) = 1940;
            goto LABEL_65;
          }
LABEL_68:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
        }
      }
    }
    else
    {
      v12 = *((_QWORD *)this + 11);
      if ( v12 )
      {
        LODWORD(v32) = TempDir;
        LODWORD(v31) = 1939;
        v13 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v12,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::ClearKeyFromXml",
                v31,
                v32);
        v14 = (unsigned int)v13;
        if ( v13 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
      }
      v2 = v40;
    }
  }
  else
  {
    v7 = 0;
    v35 = 0;
    v8 = GetLastError();
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v10 = 0;
      if ( v9 < 0 )
      {
        LODWORD(v32) = v9;
        LODWORD(v31) = 1937;
LABEL_65:
        v18 = *((_QWORD *)this + 11);
LABEL_66:
        v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v18,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::ClearKeyFromXml",
                v31,
                v32);
        v10 = (unsigned int)v26;
        if ( v26 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
        goto LABEL_68;
      }
      goto LABEL_68;
    }
  }
LABEL_69:
  UnattendCtxCleanup(&v39);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  v27 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v27);
    lpMem = 0;
  }
  if ( v2 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, (LPVOID)(v2 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v7 )
    WIMCloseHandle(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000af80  push    rbp
0x18000af82  push    rbx
0x18000af83  push    rsi
0x18000af84  push    rdi
0x18000af85  push    r14
0x18000af87  push    r15
0x18000af89  mov     rbp, rsp
0x18000af8c  sub     rsp, 78h
0x18000af90  mov     rdi, rcx
0x18000af93  xor     r15d, r15d
0x18000af96  mov     [rbp+hMem], r15
0x18000af9a  mov     [rbp+arg_0], r15d
0x18000af9e  mov     r14d, r15d
0x18000afa1  mov     [rbp+arg_10], r15
0x18000afa5  mov     [rbp+lpMem], r15
0x18000afa9  mov     [rbp+var_40], r15
0x18000afad  xorps   xmm0, xmm0
0x18000afb0  xor     eax, eax
0x18000afb2  movups  [rbp+var_30], xmm0
0x18000afb6  movups  [rbp+var_20], xmm0
0x18000afba  mov     [rbp+var_10], rax
0x18000afbe  mov     [rbp+arg_8], r15
0x18000afc2  mov     rax, [rcx+230h]
0x18000afc9  test    rax, rax
0x18000afcc  jnz     short loc_18000AFDC
0x18000afce  mov     rax, [rcx+228h]
0x18000afd5  test    rax, rax
0x18000afd8  mov     dl, 1
0x18000afda  jz      short loc_18000AFDF
0x18000afdc  mov     dl, r15b
0x18000afdf  mov     rcx, r15
0x18000afe2  test    dl, dl
0x18000afe4  cmovz   rcx, rax
0x18000afe8  mov     [rsp+78h+var_50], r15
0x18000afed  mov     dword ptr [rsp+78h+var_58], r15d
0x18000aff2  mov     edx, 0C0000000h
0x18000aff7  mov     r9d, 20000000h
0x18000affd  mov     r8d, 3
0x18000b003  call    cs:__imp_WIMCreateFile
0x18000b009  mov     rbx, rax
0x18000b00c  test    rax, rax
0x18000b00f  jnz     short loc_18000B05C
0x18000b011  mov     rbx, r15
0x18000b014  mov     [rbp+var_38], rbx
0x18000b018  call    cs:__imp_GetLastError
0x18000b01e  mov     esi, eax
0x18000b020  test    eax, eax
0x18000b022  jnz     short loc_18000B02B
0x18000b024  mov     esi, 80004005h
0x18000b029  jmp     short loc_18000B036
0x18000b02b  jle     short loc_18000B036
0x18000b02d  movzx   esi, ax
0x18000b030  or      esi, 80070000h
0x18000b036  cmp     [rdi+58h], r15
0x18000b03a  jz      loc_18000B340
0x18000b040  mov     ecx, r15d
0x18000b043  test    esi, esi
0x18000b045  jns     loc_18000B33B
0x18000b04b  mov     dword ptr [rsp+78h+var_50], esi
0x18000b04f  mov     dword ptr [rsp+78h+var_58], 791h
0x18000b057  jmp     loc_18000B314
0x18000b05c  mov     [rbp+var_38], rbx
0x18000b060  lea     rcx, [rbp+arg_10]
0x18000b064  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x18000b069  mov     esi, eax
0x18000b06b  test    eax, eax
0x18000b06d  jns     short loc_18000B0B5
0x18000b06f  mov     rcx, [rdi+58h]
0x18000b073  test    rcx, rcx
0x18000b076  jz      short loc_18000B0AC
0x18000b078  mov     dword ptr [rsp+78h+var_50], eax
0x18000b07c  mov     dword ptr [rsp+78h+var_58], 793h
0x18000b084  lea     r9, aCdlpactionreco; "CDlpActionRecoverCrypto::ClearKeyFromXm"...
0x18000b08b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000b092  mov     edx, 4
0x18000b097  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000b09c  mov     ecx, eax
0x18000b09e  test    eax, eax
0x18000b0a0  jns     short loc_18000B0A7
0x18000b0a2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b0a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b0ac  mov     r14, [rbp+arg_10]
0x18000b0b0  jmp     loc_18000B340
0x18000b0b5  mov     r14, [rbp+arg_10]
0x18000b0b9  mov     rdx, r14
0x18000b0bc  mov     rcx, rbx
0x18000b0bf  call    cs:__imp_WIMSetTemporaryPath
0x18000b0c5  test    eax, eax
0x18000b0c7  jnz     short loc_18000B10D
0x18000b0c9  call    cs:__imp_GetLastError
0x18000b0cf  mov     esi, eax
0x18000b0d1  test    eax, eax
0x18000b0d3  jnz     short loc_18000B0DC
0x18000b0d5  mov     esi, 80004005h
0x18000b0da  jmp     short loc_18000B0E7
0x18000b0dc  jle     short loc_18000B0E7
0x18000b0de  movzx   esi, ax
0x18000b0e1  or      esi, 80070000h
0x18000b0e7  cmp     [rdi+58h], r15
0x18000b0eb  jz      loc_18000B340
0x18000b0f1  mov     ecx, r15d
0x18000b0f4  test    esi, esi
0x18000b0f6  jns     loc_18000B33B
0x18000b0fc  mov     dword ptr [rsp+78h+var_50], esi
0x18000b100  mov     dword ptr [rsp+78h+var_58], 794h
0x18000b108  jmp     loc_18000B314
0x18000b10d  mov     [rbp+arg_0], r15d
0x18000b111  lea     r8, [rbp+arg_0]
0x18000b115  lea     rdx, [rbp+hMem]
0x18000b119  mov     rcx, rbx
0x18000b11c  call    cs:__imp_WIMGetImageInformation
0x18000b122  test    eax, eax
0x18000b124  jnz     short loc_18000B16A
0x18000b126  call    cs:__imp_GetLastError
0x18000b12c  mov     esi, eax
0x18000b12e  test    eax, eax
0x18000b130  jnz     short loc_18000B139
0x18000b132  mov     esi, 80004005h
0x18000b137  jmp     short loc_18000B144
0x18000b139  jle     short loc_18000B144
0x18000b13b  movzx   esi, ax
0x18000b13e  or      esi, 80070000h
0x18000b144  cmp     [rdi+58h], r15
0x18000b148  jz      loc_18000B340
0x18000b14e  mov     ecx, r15d
0x18000b151  test    esi, esi
0x18000b153  jns     loc_18000B33B
0x18000b159  mov     dword ptr [rsp+78h+var_50], esi
0x18000b15d  mov     dword ptr [rsp+78h+var_58], 797h
0x18000b165  jmp     loc_18000B314
0x18000b16a  mov     r8d, [rbp+arg_0]
0x18000b16e  mov     rdx, [rbp+hMem]
0x18000b172  lea     rcx, [rbp+arg_8]
0x18000b176  call    cs:__imp_UnattendCtxDeserializeBuffer
0x18000b17c  mov     esi, eax
0x18000b17e  test    eax, eax
0x18000b180  jns     short loc_18000B1A0
0x18000b182  mov     rcx, [rdi+58h]
0x18000b186  test    rcx, rcx
0x18000b189  jz      loc_18000B340
0x18000b18f  mov     dword ptr [rsp+78h+var_50], eax
0x18000b193  mov     dword ptr [rsp+78h+var_58], 79Bh
0x18000b19b  jmp     loc_18000B318
0x18000b1a0  lea     r8, [rbp+var_30]
0x18000b1a4  lea     rdx, aWimEsdKey; "WIM\\ESD\\KEY"
0x18000b1ab  lea     rcx, [rbp+arg_8]
0x18000b1af  call    cs:__imp_UnattendCtxOpenNode
0x18000b1b5  mov     esi, eax
0x18000b1b7  test    eax, eax
0x18000b1b9  jns     short loc_18000B1D9
0x18000b1bb  mov     rcx, [rdi+58h]
0x18000b1bf  test    rcx, rcx
0x18000b1c2  jz      loc_18000B340
0x18000b1c8  mov     dword ptr [rsp+78h+var_50], eax
0x18000b1cc  mov     dword ptr [rsp+78h+var_58], 79Ch
0x18000b1d4  jmp     loc_18000B318
0x18000b1d9  lea     rcx, [rbp+arg_8]
0x18000b1dd  call    cs:__imp_UnattendCtxBeginModify
0x18000b1e3  mov     esi, eax
0x18000b1e5  test    eax, eax
0x18000b1e7  jns     short loc_18000B207
0x18000b1e9  mov     rcx, [rdi+58h]
0x18000b1ed  test    rcx, rcx
0x18000b1f0  jz      loc_18000B340
0x18000b1f6  mov     dword ptr [rsp+78h+var_50], eax
0x18000b1fa  mov     dword ptr [rsp+78h+var_58], 7A0h
0x18000b202  jmp     loc_18000B318
0x18000b207  lea     rdx, [rbp+var_30]
0x18000b20b  lea     rcx, [rbp+arg_8]
0x18000b20f  call    cs:__imp_UnattendCtxRemoveNode
0x18000b215  mov     esi, eax
0x18000b217  test    eax, eax
0x18000b219  jns     short loc_18000B239
0x18000b21b  mov     rcx, [rdi+58h]
0x18000b21f  test    rcx, rcx
0x18000b222  jz      loc_18000B340
0x18000b228  mov     dword ptr [rsp+78h+var_50], eax
0x18000b22c  mov     dword ptr [rsp+78h+var_58], 7A1h
0x18000b234  jmp     loc_18000B318
0x18000b239  lea     rcx, [rbp+var_30]
0x18000b23d  call    cs:__imp_UnattendFreeNode
0x18000b243  mov     esi, eax
0x18000b245  test    eax, eax
0x18000b247  jns     short loc_18000B267
0x18000b249  mov     rcx, [rdi+58h]
0x18000b24d  test    rcx, rcx
0x18000b250  jz      loc_18000B340
0x18000b256  mov     dword ptr [rsp+78h+var_50], eax
0x18000b25a  mov     dword ptr [rsp+78h+var_58], 7A5h
0x18000b262  jmp     loc_18000B318
0x18000b267  lea     rcx, [rbp+arg_8]
0x18000b26b  call    cs:__imp_UnattendCtxCommitModify
0x18000b271  mov     esi, eax
0x18000b273  test    eax, eax
0x18000b275  jns     short loc_18000B295
0x18000b277  mov     rcx, [rdi+58h]
0x18000b27b  test    rcx, rcx
0x18000b27e  jz      loc_18000B340
0x18000b284  mov     dword ptr [rsp+78h+var_50], eax
0x18000b288  mov     dword ptr [rsp+78h+var_58], 7A9h
0x18000b290  jmp     loc_18000B318
0x18000b295  lea     r8, [rbp+var_40]
0x18000b299  lea     rdx, [rbp+lpMem]
0x18000b29d  lea     rcx, [rbp+arg_8]
0x18000b2a1  call    cs:__imp_UnattendCtxSerializeToBuffer
0x18000b2a7  mov     esi, eax
0x18000b2a9  test    eax, eax
0x18000b2ab  jns     short loc_18000B2C8
0x18000b2ad  mov     rcx, [rdi+58h]
0x18000b2b1  test    rcx, rcx
0x18000b2b4  jz      loc_18000B340
0x18000b2ba  mov     dword ptr [rsp+78h+var_50], eax
0x18000b2be  mov     dword ptr [rsp+78h+var_58], 7ADh
0x18000b2c6  jmp     short loc_18000B318
0x18000b2c8  mov     r8d, dword ptr [rbp+var_40]
0x18000b2cc  mov     rdx, [rbp+lpMem]
0x18000b2d0  mov     rcx, rbx
0x18000b2d3  call    cs:__imp_WIMSetImageInformation
0x18000b2d9  test    eax, eax
0x18000b2db  jnz     short loc_18000B340
0x18000b2dd  call    cs:__imp_GetLastError
0x18000b2e3  mov     esi, eax
0x18000b2e5  test    eax, eax
0x18000b2e7  jnz     short loc_18000B2F0
0x18000b2e9  mov     esi, 80004005h
0x18000b2ee  jmp     short loc_18000B2FB
0x18000b2f0  jle     short loc_18000B2FB
0x18000b2f2  movzx   esi, ax
0x18000b2f5  or      esi, 80070000h
0x18000b2fb  cmp     [rdi+58h], r15
0x18000b2ff  jz      short loc_18000B340
0x18000b301  mov     ecx, r15d
0x18000b304  test    esi, esi
0x18000b306  jns     short loc_18000B33B
0x18000b308  mov     dword ptr [rsp+78h+var_50], esi
0x18000b30c  mov     dword ptr [rsp+78h+var_58], 7AEh
0x18000b314  mov     rcx, [rdi+58h]
0x18000b318  lea     r9, aCdlpactionreco; "CDlpActionRecoverCrypto::ClearKeyFromXm"...
0x18000b31f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000b326  mov     edx, 4
0x18000b32b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000b330  mov     ecx, eax
0x18000b332  test    eax, eax
0x18000b334  jns     short loc_18000B33B
0x18000b336  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b33b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b340  lea     rcx, [rbp+arg_8]
0x18000b344  call    cs:__imp_UnattendCtxCleanup
0x18000b34a  mov     ecx, esi
0x18000b34c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b351  nop
0x18000b352  mov     rdi, [rbp+lpMem]
0x18000b356  test    rdi, rdi
0x18000b359  jz      short loc_18000B373
0x18000b35b  call    cs:__imp_GetProcessHeap
0x18000b361  mov     rcx, rax; hHeap
0x18000b364  mov     r8, rdi; lpMem
0x18000b367  xor     edx, edx; dwFlags
0x18000b369  call    cs:__imp_HeapFree
0x18000b36f  mov     [rbp+lpMem], r15
0x18000b373  test    r14, r14
0x18000b376  jz      short loc_18000B395
0x18000b378  call    cs:__imp_GetProcessHeap
0x18000b37e  mov     rcx, rax; hHeap
0x18000b381  lea     r8, [r14-4]; lpMem
0x18000b385  xor     edx, edx; dwFlags
0x18000b387  call    cs:__imp_HeapFree
0x18000b38d  xor     ecx, ecx
0x18000b38f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b394  nop
0x18000b395  mov     rcx, [rbp+hMem]; hMem
0x18000b399  test    rcx, rcx
0x18000b39c  jz      short loc_18000B3A8
0x18000b39e  call    cs:__imp_LocalFree
0x18000b3a4  mov     [rbp+hMem], r15
0x18000b3a8  test    rbx, rbx
0x18000b3ab  jz      short loc_18000B3B6
0x18000b3ad  mov     rcx, rbx
0x18000b3b0  call    cs:__imp_WIMCloseHandle
0x18000b3b6  mov     eax, esi
0x18000b3b8  add     rsp, 78h
0x18000b3bc  pop     r15
0x18000b3be  pop     r14
0x18000b3c0  pop     rdi
0x18000b3c1  pop     rsi
0x18000b3c2  pop     rbx
0x18000b3c3  pop     rbp
0x18000b3c4  retn
```
