# CDlpActionRecoverCrypto::GetKeyFromWim(ushort const *,uchar * *,ulong *)

- ea: `0x18001b020`
- end: `0x18001b47e`
- name: `?GetKeyFromWim@CDlpActionRecoverCrypto@@AEAAJPEBGPEAPEAEPEAK@Z`
- size: `1118`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18000fb18`
- `0x1800131ec`

## callees

- `0x180002898`
- `0x180009030`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001b020`
- `0x18001c9d0`
- `0x18001fd60`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18001b45a`
- `WIMGAPI!WIMCloseHandle` at `0x18001b45a`
- `WIMGAPI!WIMGetImageInformation` at `0x18001b1dd`
- `WIMGAPI!WIMGetImageInformation` at `0x18001b1dd`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18001b17a`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18001b17a`
- `WIMGAPI!WIMCreateFile` at `0x18001b08f`
- `WIMGAPI!WIMCreateFile` at `0x18001b08f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b427`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b3d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b3f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b410`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b435`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b3d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b3f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b410`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b448`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b448`
- `UNATTEND!UnattendCtxCleanup` at `0x18001b3b0`
- `UNATTEND!UnattendCtxCleanup` at `0x18001b3b0`
- `UNATTEND!UnattendCtxGetString` at `0x18001b27a`
- `UNATTEND!UnattendCtxGetString` at `0x18001b27a`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18001b23d`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18001b23d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpActionRecoverCrypto::GetKeyFromWim(
        CDlpActionRecoverCrypto *this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  __int64 v5; // r12
  unsigned __int8 *v6; // rdi
  WCHAR *v7; // r13
  __int64 v8; // rax
  __int64 v9; // rbx
  signed int v10; // eax
  signed int v11; // r14d
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  int TempDir; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  signed int v19; // eax
  signed int LastError; // eax
  int v21; // eax
  int String; // eax
  void *v23; // r15
  int Internal; // eax
  int StringCch; // eax
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v31; // rax
  HANDLE v32; // rax
  void *v33; // rdi
  HANDLE v34; // rax
  __int64 v36; // [rsp+20h] [rbp-60h]
  __int64 v37; // [rsp+28h] [rbp-58h]
  __int64 v38; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v39; // [rsp+38h] [rbp-48h] BYREF
  WCHAR *v40; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int8 *v41; // [rsp+48h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-28h] BYREF
  __int64 v44; // [rsp+60h] [rbp-20h]
  __int64 v45; // [rsp+68h] [rbp-18h] BYREF
  __int64 v46; // [rsp+70h] [rbp-10h]

  hMem = 0;
  lpMem = 0;
  v5 = 0;
  v44 = 0;
  v6 = 0;
  v41 = 0;
  v7 = 0;
  v40 = 0;
  LODWORD(v38) = 0;
  v39 = 0;
  v45 = 0;
  v8 = WIMCreateFile(a2, 0, 3, 0x20000000, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v46 = v8;
    TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v40);
    v11 = TempDir;
    if ( TempDir < 0 )
    {
      v16 = *((_QWORD *)this + 11);
      if ( v16 )
      {
        LODWORD(v37) = TempDir;
        LODWORD(v36) = 2011;
        v17 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v16,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::GetKeyFromWim",
                v36,
                v37,
                v38);
        v18 = (unsigned int)v17;
        if ( v17 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
      }
      v7 = v40;
      goto LABEL_60;
    }
    v7 = v40;
    if ( (unsigned int)WIMSetTemporaryPath(v9, v40) )
    {
      LODWORD(v38) = 0;
      if ( (unsigned int)WIMGetImageInformation(v9, &hMem, &v38) )
      {
        v21 = UnattendCtxDeserializeBuffer(&v45, hMem, (unsigned int)v38);
        v11 = v21;
        if ( v21 >= 0 )
        {
          String = UnattendCtxGetString(&v45, L"WIM\\ESD\\KEY", 0, &lpMem);
          v11 = String;
          if ( String >= 0 )
          {
            if ( String )
            {
              v11 = -1048575725;
              goto LABEL_60;
            }
            v23 = lpMem;
            if ( lpMem
              && (HIDWORD(v38) = 0,
                  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(lpMem, (char *)&v38 + 4),
                  v11 = StringCch,
                  StringCch < 0) )
            {
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
            }
            else
            {
              Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v23);
              v11 = Internal;
              if ( Internal < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
              v5 = v44;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
            if ( v11 >= 0 )
            {
              v26 = CStringConvertT<unsigned long>::Base64Decode(v5, &v41, &v39);
              v11 = v26;
              if ( v26 >= 0 )
              {
                v6 = 0;
                *a3 = v41;
                *a4 = v39;
              }
              else
              {
                v27 = *((_QWORD *)this + 11);
                if ( v27 )
                {
                  LODWORD(v37) = v26;
                  LODWORD(v36) = 2029;
                  v28 = CDlpLogT<CEmptyType>::DlpLogFormat(
                          v27,
                          4,
                          L"%s(%d): Result = 0x%X",
                          L"CDlpActionRecoverCrypto::GetKeyFromWim",
                          v36,
                          v37);
                  v29 = (unsigned int)v28;
                  if ( v28 < 0 )
                    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v28);
                  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v29);
                }
                v6 = v41;
              }
              goto LABEL_60;
            }
            v13 = *((_QWORD *)this + 11);
            if ( !v13 )
              goto LABEL_60;
            LODWORD(v37) = v11;
            LODWORD(v36) = 2028;
          }
          else
          {
            v13 = *((_QWORD *)this + 11);
            if ( !v13 )
              goto LABEL_60;
            LODWORD(v37) = String;
            LODWORD(v36) = 2020;
          }
        }
        else
        {
          v13 = *((_QWORD *)this + 11);
          if ( !v13 )
            goto LABEL_60;
          LODWORD(v37) = v21;
          LODWORD(v36) = 2019;
        }
LABEL_10:
        v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v13,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::GetKeyFromWim",
                v36,
                v37,
                v38);
        v12 = (unsigned int)v14;
        if ( v14 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
        goto LABEL_12;
      }
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v12 = 0;
        if ( v11 < 0 )
        {
          LODWORD(v37) = v11;
          LODWORD(v36) = 2015;
          goto LABEL_9;
        }
        goto LABEL_12;
      }
    }
    else
    {
      v19 = GetLastError();
      v11 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v11 = (unsigned __int16)v19 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v12 = 0;
        if ( v11 < 0 )
        {
          LODWORD(v37) = v11;
          LODWORD(v36) = 2012;
          goto LABEL_9;
        }
LABEL_12:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
      }
    }
  }
  else
  {
    v9 = 0;
    v46 = 0;
    v10 = GetLastError();
    v11 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v12 = 0;
      if ( v11 < 0 )
      {
        LODWORD(v37) = v11;
        LODWORD(v36) = 2009;
LABEL_9:
        v13 = *((_QWORD *)this + 11);
        goto LABEL_10;
      }
      goto LABEL_12;
    }
  }
LABEL_60:
  UnattendCtxCleanup(&v45);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v6);
  }
  if ( v5 )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
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
  if ( v9 )
    WIMCloseHandle(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b020  mov     [rsp-38h+arg_0], rbx
0x18001b025  mov     [rsp-38h+arg_18], r9
0x18001b02a  mov     [rsp-38h+arg_10], r8
0x18001b02f  push    rbp
0x18001b030  push    rsi
0x18001b031  push    rdi
0x18001b032  push    r12
0x18001b034  push    r13
0x18001b036  push    r14
0x18001b038  push    r15
0x18001b03a  mov     rbp, rsp
0x18001b03d  sub     rsp, 80h
0x18001b044  mov     rax, rdx
0x18001b047  mov     rsi, rcx
0x18001b04a  xor     r15d, r15d
0x18001b04d  mov     [rbp+hMem], r15
0x18001b051  mov     [rbp+lpMem], r15
0x18001b055  mov     r12d, r15d
0x18001b058  mov     [rbp+var_20], r15
0x18001b05c  mov     edi, r15d
0x18001b05f  mov     [rbp+var_38], r15
0x18001b063  mov     r13d, r15d
0x18001b066  mov     [rbp+var_40], r15
0x18001b06a  mov     [rbp+var_50], r15d
0x18001b06e  mov     [rbp+var_48], r15d
0x18001b072  mov     [rbp+var_18], r15
0x18001b076  mov     [rsp+80h+var_58], r15
0x18001b07b  mov     dword ptr [rsp+80h+var_60], r15d
0x18001b080  xor     edx, edx
0x18001b082  mov     r9d, 20000000h
0x18001b088  lea     r8d, [r15+3]
0x18001b08c  mov     rcx, rax
0x18001b08f  call    cs:__imp_WIMCreateFile
0x18001b095  mov     rbx, rax
0x18001b098  test    rax, rax
0x18001b09b  jnz     short loc_18001B116
0x18001b09d  mov     ebx, r15d
0x18001b0a0  mov     [rbp+var_10], rbx
0x18001b0a4  call    cs:__imp_GetLastError
0x18001b0aa  mov     r14d, eax
0x18001b0ad  test    eax, eax
0x18001b0af  jnz     short loc_18001B0B9
0x18001b0b1  mov     r14d, 80004005h
0x18001b0b7  jmp     short loc_18001B0C6
0x18001b0b9  jle     short loc_18001B0C6
0x18001b0bb  movzx   r14d, ax
0x18001b0bf  or      r14d, 80070000h
0x18001b0c6  cmp     [rsi+58h], r15
0x18001b0ca  jz      loc_18001B3AC
0x18001b0d0  mov     ecx, r15d
0x18001b0d3  test    r14d, r14d
0x18001b0d6  jns     short loc_18001B10C
0x18001b0d8  mov     dword ptr [rsp+80h+var_58], r14d
0x18001b0dd  mov     dword ptr [rsp+80h+var_60], 7D9h
0x18001b0e5  mov     rcx, [rsi+58h]
0x18001b0e9  mov     edx, 4
0x18001b0ee  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001b0f5  lea     r9, aCdlpactionreco_0; "CDlpActionRecoverCrypto::GetKeyFromWim"
0x18001b0fc  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001b101  test    eax, eax
0x18001b103  mov     ecx, eax
0x18001b105  jns     short loc_18001B10C
0x18001b107  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b10c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b111  jmp     loc_18001B3AC
0x18001b116  mov     [rbp+var_10], rbx
0x18001b11a  lea     rcx, [rbp+var_40]
0x18001b11e  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x18001b123  mov     r14d, eax
0x18001b126  test    eax, eax
0x18001b128  jns     short loc_18001B170
0x18001b12a  mov     rcx, [rsi+58h]
0x18001b12e  test    rcx, rcx
0x18001b131  jz      short loc_18001B167
0x18001b133  mov     dword ptr [rsp+80h+var_58], eax
0x18001b137  mov     dword ptr [rsp+80h+var_60], 7DBh
0x18001b13f  lea     r9, aCdlpactionreco_0; "CDlpActionRecoverCrypto::GetKeyFromWim"
0x18001b146  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001b14d  mov     edx, 4
0x18001b152  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001b157  mov     ecx, eax
0x18001b159  test    eax, eax
0x18001b15b  jns     short loc_18001B162
0x18001b15d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b162  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b167  mov     r13, [rbp+var_40]
0x18001b16b  jmp     loc_18001B3AC
0x18001b170  mov     r13, [rbp+var_40]
0x18001b174  mov     rdx, r13
0x18001b177  mov     rcx, rbx
0x18001b17a  call    cs:__imp_WIMSetTemporaryPath
0x18001b180  test    eax, eax
0x18001b182  jnz     short loc_18001B1CE
0x18001b184  call    cs:__imp_GetLastError
0x18001b18a  mov     r14d, eax
0x18001b18d  test    eax, eax
0x18001b18f  jnz     short loc_18001B199
0x18001b191  mov     r14d, 80004005h
0x18001b197  jmp     short loc_18001B1A6
0x18001b199  jle     short loc_18001B1A6
0x18001b19b  movzx   r14d, ax
0x18001b19f  or      r14d, 80070000h
0x18001b1a6  cmp     [rsi+58h], r15
0x18001b1aa  jz      loc_18001B3AC
0x18001b1b0  mov     ecx, r15d
0x18001b1b3  test    r14d, r14d
0x18001b1b6  jns     loc_18001B10C
0x18001b1bc  mov     dword ptr [rsp+80h+var_58], r14d
0x18001b1c1  mov     dword ptr [rsp+80h+var_60], 7DCh
0x18001b1c9  jmp     loc_18001B0E5
0x18001b1ce  mov     [rbp+var_50], r15d
0x18001b1d2  lea     r8, [rbp+var_50]
0x18001b1d6  lea     rdx, [rbp+hMem]
0x18001b1da  mov     rcx, rbx
0x18001b1dd  call    cs:__imp_WIMGetImageInformation
0x18001b1e3  test    eax, eax
0x18001b1e5  jnz     short loc_18001B231
0x18001b1e7  call    cs:__imp_GetLastError
0x18001b1ed  mov     r14d, eax
0x18001b1f0  test    eax, eax
0x18001b1f2  jnz     short loc_18001B1FC
0x18001b1f4  mov     r14d, 80004005h
0x18001b1fa  jmp     short loc_18001B209
0x18001b1fc  jle     short loc_18001B209
0x18001b1fe  movzx   r14d, ax
0x18001b202  or      r14d, 80070000h
0x18001b209  cmp     [rsi+58h], r15
0x18001b20d  jz      loc_18001B3AC
0x18001b213  mov     ecx, r15d
0x18001b216  test    r14d, r14d
0x18001b219  jns     loc_18001B10C
0x18001b21f  mov     dword ptr [rsp+80h+var_58], r14d
0x18001b224  mov     dword ptr [rsp+80h+var_60], 7DFh
0x18001b22c  jmp     loc_18001B0E5
0x18001b231  mov     r8d, [rbp+var_50]
0x18001b235  mov     rdx, [rbp+hMem]
0x18001b239  lea     rcx, [rbp+var_18]
0x18001b23d  call    cs:__imp_UnattendCtxDeserializeBuffer
0x18001b243  mov     r14d, eax
0x18001b246  test    eax, eax
0x18001b248  jns     short loc_18001B268
0x18001b24a  mov     rcx, [rsi+58h]
0x18001b24e  test    rcx, rcx
0x18001b251  jz      loc_18001B3AC
0x18001b257  mov     dword ptr [rsp+80h+var_58], eax
0x18001b25b  mov     dword ptr [rsp+80h+var_60], 7E3h
0x18001b263  jmp     loc_18001B0E9
0x18001b268  lea     r9, [rbp+lpMem]
0x18001b26c  xor     r8d, r8d
0x18001b26f  lea     rdx, aWimEsdKey; "WIM\\ESD\\KEY"
0x18001b276  lea     rcx, [rbp+var_18]
0x18001b27a  call    cs:__imp_UnattendCtxGetString
0x18001b280  mov     r14d, eax
0x18001b283  test    eax, eax
0x18001b285  jns     short loc_18001B2A5
0x18001b287  mov     rcx, [rsi+58h]
0x18001b28b  test    rcx, rcx
0x18001b28e  jz      loc_18001B3AC
0x18001b294  mov     dword ptr [rsp+80h+var_58], eax
0x18001b298  mov     dword ptr [rsp+80h+var_60], 7E4h
0x18001b2a0  jmp     loc_18001B0E9
0x18001b2a5  jnz     loc_18001B3A6
0x18001b2ab  mov     r15, [rbp+lpMem]
0x18001b2af  test    r15, r15
0x18001b2b2  jnz     short loc_18001B303
0x18001b2b4  xor     edx, edx
0x18001b2b6  lea     r8, [rbp+var_20]
0x18001b2ba  mov     rcx, r15; Src
0x18001b2bd  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001b2c2  mov     r14d, eax
0x18001b2c5  xor     r15d, r15d
0x18001b2c8  test    eax, eax
0x18001b2ca  jns     short loc_18001B2D3
0x18001b2cc  mov     ecx, eax
0x18001b2ce  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b2d3  mov     r12, [rbp+var_20]
0x18001b2d7  mov     ecx, r14d
0x18001b2da  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b2df  test    r14d, r14d
0x18001b2e2  jns     short loc_18001B333
0x18001b2e4  mov     rcx, [rsi+58h]
0x18001b2e8  test    rcx, rcx
0x18001b2eb  jz      loc_18001B3AC
0x18001b2f1  mov     dword ptr [rsp+80h+var_58], r14d
0x18001b2f6  mov     dword ptr [rsp+80h+var_60], 7ECh
0x18001b2fe  jmp     loc_18001B0E9
0x18001b303  mov     [rbp+var_4C], 0
0x18001b30a  test    r15, r15
0x18001b30d  jz      short loc_18001B2B4
0x18001b30f  lea     rdx, [rbp+var_4C]
0x18001b313  mov     rcx, r15
0x18001b316  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001b31b  mov     r14d, eax
0x18001b31e  test    eax, eax
0x18001b320  jns     short loc_18001B32E
0x18001b322  mov     ecx, eax
0x18001b324  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b329  xor     r15d, r15d
0x18001b32c  jmp     short loc_18001B2D7
0x18001b32e  mov     edx, [rbp+var_4C]
0x18001b331  jmp     short loc_18001B2B6
0x18001b333  lea     r8, [rbp+var_48]
0x18001b337  lea     rdx, [rbp+var_38]
0x18001b33b  mov     rcx, r12
0x18001b33e  call    ?Base64Decode@?$CStringConvertT@K@@SAJPEAGPEAPEAEPEAK@Z; CStringConvertT<ulong>::Base64Decode(ushort *,uchar * *,ulong *)
0x18001b343  mov     r14d, eax
0x18001b346  test    eax, eax
0x18001b348  jns     short loc_18001B38D
0x18001b34a  mov     rcx, [rsi+58h]
0x18001b34e  test    rcx, rcx
0x18001b351  jz      short loc_18001B387
0x18001b353  mov     dword ptr [rsp+80h+var_58], eax
0x18001b357  mov     dword ptr [rsp+80h+var_60], 7EDh
0x18001b35f  lea     r9, aCdlpactionreco_0; "CDlpActionRecoverCrypto::GetKeyFromWim"
0x18001b366  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001b36d  mov     edx, 4
0x18001b372  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001b377  mov     ecx, eax
0x18001b379  test    eax, eax
0x18001b37b  jns     short loc_18001B382
0x18001b37d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b382  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b387  mov     rdi, [rbp+var_38]
0x18001b38b  jmp     short loc_18001B3AC
0x18001b38d  mov     rax, [rbp+var_38]
0x18001b391  mov     rdi, r15
0x18001b394  mov     rcx, [rbp+arg_10]
0x18001b398  mov     [rcx], rax
0x18001b39b  mov     eax, [rbp+var_48]
0x18001b39e  mov     rcx, [rbp+arg_18]
0x18001b3a2  mov     [rcx], eax
0x18001b3a4  jmp     short loc_18001B3AC
0x18001b3a6  mov     r14d, 0C1800113h
0x18001b3ac  lea     rcx, [rbp+var_18]
0x18001b3b0  call    cs:__imp_UnattendCtxCleanup
0x18001b3b6  mov     ecx, r14d
0x18001b3b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b3be  nop
0x18001b3bf  test    r13, r13
0x18001b3c2  jz      short loc_18001B3E1
0x18001b3c4  call    cs:__imp_GetProcessHeap
0x18001b3ca  mov     rcx, rax; hHeap
0x18001b3cd  lea     r8, [r13-4]; lpMem
0x18001b3d1  xor     edx, edx; dwFlags
0x18001b3d3  call    cs:__imp_HeapFree
0x18001b3d9  xor     ecx, ecx
0x18001b3db  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b3e0  nop
0x18001b3e1  test    rdi, rdi
0x18001b3e4  jz      short loc_18001B3FB
0x18001b3e6  call    cs:__imp_GetProcessHeap
0x18001b3ec  mov     rcx, rax; hHeap
0x18001b3ef  mov     r8, rdi; lpMem
0x18001b3f2  xor     edx, edx; dwFlags
0x18001b3f4  call    cs:__imp_HeapFree
0x18001b3fa  nop
0x18001b3fb  test    r12, r12
0x18001b3fe  jz      short loc_18001B41E
0x18001b400  call    cs:__imp_GetProcessHeap
0x18001b406  mov     rcx, rax; hHeap
0x18001b409  lea     r8, [r12-4]; lpMem
0x18001b40e  xor     edx, edx; dwFlags
0x18001b410  call    cs:__imp_HeapFree
0x18001b416  xor     ecx, ecx
0x18001b418  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b41d  nop
0x18001b41e  mov     rdi, [rbp+lpMem]
0x18001b422  test    rdi, rdi
0x18001b425  jz      short loc_18001B43F
0x18001b427  call    cs:__imp_GetProcessHeap
0x18001b42d  mov     rcx, rax; hHeap
0x18001b430  mov     r8, rdi; lpMem
0x18001b433  xor     edx, edx; dwFlags
0x18001b435  call    cs:__imp_HeapFree
0x18001b43b  mov     [rbp+lpMem], r15
0x18001b43f  mov     rcx, [rbp+hMem]; hMem
0x18001b443  test    rcx, rcx
0x18001b446  jz      short loc_18001B452
0x18001b448  call    cs:__imp_LocalFree
0x18001b44e  mov     [rbp+hMem], r15
0x18001b452  test    rbx, rbx
0x18001b455  jz      short loc_18001B460
0x18001b457  mov     rcx, rbx
0x18001b45a  call    cs:__imp_WIMCloseHandle
0x18001b460  mov     eax, r14d
0x18001b463  mov     rbx, [rsp+80h+arg_0]
0x18001b46b  add     rsp, 80h
0x18001b472  pop     r15
0x18001b474  pop     r14
0x18001b476  pop     r13
0x18001b478  pop     r12
0x18001b47a  pop     rdi
0x18001b47b  pop     rsi
0x18001b47c  pop     rbp
0x18001b47d  retn
```
