# CDlpActionRecoverCrypto::SaveKeyToWim(ushort const *,uchar *,ulong)

- ea: `0x180029058`
- end: `0x18002941c`
- name: `?SaveKeyToWim@CDlpActionRecoverCrypto@@AEAAJPEBGPEAEK@Z`
- size: `964`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000fb18`

## callees

- `0x1800094c0`
- `0x18000aba4`
- `0x180012f5c`
- `0x18001c9d0`
- `0x18001fd60`
- `0x180029058`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x1800293bb`
- `WIMGAPI!WIMCloseHandle` at `0x1800293bb`
- `WIMGAPI!WIMGetImageInformation` at `0x1800291cf`
- `WIMGAPI!WIMGetImageInformation` at `0x1800291cf`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180029172`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180029172`
- `WIMGAPI!WIMSetImageInformation` at `0x180029300`
- `WIMGAPI!WIMSetImageInformation` at `0x180029300`
- `WIMGAPI!WIMCreateFile` at `0x1800290b6`
- `WIMGAPI!WIMCreateFile` at `0x1800290b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029388`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800293c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800293ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029388`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800293c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800293ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800293d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800293fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800293d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800293fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002917c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002930a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002917c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002930a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293a9`
- `UNATTEND!UnattendCtxSetString` at `0x180029298`
- `UNATTEND!UnattendCtxSetString` at `0x180029298`
- `UNATTEND!UnattendCtxCleanup` at `0x180029371`
- `UNATTEND!UnattendCtxCleanup` at `0x180029371`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x1800292ce`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x1800292ce`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18002925c`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18002925c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpActionRecoverCrypto::SaveKeyToWim(
        CDlpActionRecoverCrypto *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  WCHAR *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rbx
  signed int v10; // eax
  signed int v11; // edi
  __int64 v12; // rcx
  int TempDir; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  signed int v17; // eax
  __int64 v18; // r8
  signed int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  signed int LastError; // eax
  int v26; // eax
  void *v27; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  __int64 v30; // rbx
  HANDLE v31; // rax
  __int64 v33; // [rsp+20h] [rbp-58h]
  __int64 v34; // [rsp+28h] [rbp-50h]
  __int64 v35; // [rsp+30h] [rbp-48h] BYREF
  WCHAR *v36; // [rsp+38h] [rbp-40h] BYREF
  __int64 v37; // [rsp+40h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-28h] BYREF
  __int64 v40; // [rsp+58h] [rbp-20h] BYREF
  __int64 v41; // [rsp+60h] [rbp-18h] BYREF
  __int64 v42; // [rsp+68h] [rbp-10h]

  v40 = 0;
  v7 = 0;
  v36 = 0;
  hMem = 0;
  LODWORD(v35) = 0;
  lpMem = 0;
  v41 = 0;
  v37 = 0;
  v8 = WIMCreateFile(a2, 3221225472LL, 3, 0x20000000, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v42 = v8;
    TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v36);
    v11 = TempDir;
    if ( TempDir >= 0 )
    {
      v7 = v36;
      if ( (unsigned int)WIMSetTemporaryPath(v9, v36) )
      {
        LODWORD(v35) = 0;
        if ( (unsigned int)WIMGetImageInformation(v9, &hMem, &v35) )
        {
          v20 = CStringConvertT<unsigned long>::Base64Encode(a3, a4, v18, &v40);
          v11 = v20;
          if ( v20 < 0 )
          {
            v21 = *((_QWORD *)this + 11);
            if ( !v21 )
              goto LABEL_55;
            LODWORD(v34) = v20;
            LODWORD(v33) = 2339;
            goto LABEL_52;
          }
          v22 = UnattendCtxDeserializeBuffer(&v37, hMem, (unsigned int)v35);
          v11 = v22;
          if ( v22 < 0 )
          {
            v21 = *((_QWORD *)this + 11);
            if ( !v21 )
              goto LABEL_55;
            LODWORD(v34) = v22;
            LODWORD(v33) = 2344;
            goto LABEL_52;
          }
          v23 = UnattendCtxSetString(&v37, L"WIM\\ESD\\KEY", 0, v40);
          v11 = v23;
          if ( v23 < 0 )
          {
            v21 = *((_QWORD *)this + 11);
            if ( !v21 )
              goto LABEL_55;
            LODWORD(v34) = v23;
            LODWORD(v33) = 2345;
            goto LABEL_52;
          }
          v24 = UnattendCtxSerializeToBuffer(&v37, &lpMem, &v41);
          v11 = v24;
          if ( v24 < 0 )
          {
            v21 = *((_QWORD *)this + 11);
            if ( !v21 )
              goto LABEL_55;
            LODWORD(v34) = v24;
            LODWORD(v33) = 2346;
            goto LABEL_52;
          }
          if ( !(unsigned int)WIMSetImageInformation(v9, lpMem, (unsigned int)v41) )
          {
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
                LODWORD(v34) = v11;
                LODWORD(v33) = 2347;
                goto LABEL_51;
              }
              goto LABEL_54;
            }
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
              LODWORD(v34) = v11;
              LODWORD(v33) = 2335;
              goto LABEL_51;
            }
            goto LABEL_54;
          }
        }
      }
      else
      {
        v17 = GetLastError();
        v11 = v17;
        if ( v17 )
        {
          if ( v17 > 0 )
            v11 = (unsigned __int16)v17 | 0x80070000;
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
            LODWORD(v34) = v11;
            LODWORD(v33) = 2332;
            goto LABEL_51;
          }
LABEL_54:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
        }
      }
    }
    else
    {
      v14 = *((_QWORD *)this + 11);
      if ( v14 )
      {
        LODWORD(v34) = TempDir;
        LODWORD(v33) = 2331;
        v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v14,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::SaveKeyToWim",
                v33,
                v34,
                v35);
        v16 = (unsigned int)v15;
        if ( v15 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
      }
      v7 = v36;
    }
  }
  else
  {
    v9 = 0;
    v42 = 0;
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
        LODWORD(v34) = v11;
        LODWORD(v33) = 2329;
LABEL_51:
        v21 = *((_QWORD *)this + 11);
LABEL_52:
        v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v21,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::SaveKeyToWim",
                v33,
                v34,
                v35);
        v12 = (unsigned int)v26;
        if ( v26 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
  }
LABEL_55:
  UnattendCtxCleanup(&v37);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  v27 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v27);
    lpMem = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v9 )
    WIMCloseHandle(v9);
  if ( v7 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v7 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v30 = v40;
  if ( v40 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, (LPVOID)(v30 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180029058  push    rbp
0x18002905a  push    rbx
0x18002905b  push    rsi
0x18002905c  push    rdi
0x18002905d  push    r12
0x18002905f  push    r13
0x180029061  push    r14
0x180029063  push    r15
0x180029065  mov     rbp, rsp
0x180029068  sub     rsp, 78h
0x18002906c  mov     r15d, r9d
0x18002906f  mov     r12, r8
0x180029072  mov     rax, rdx
0x180029075  mov     rsi, rcx
0x180029078  xor     r13d, r13d
0x18002907b  mov     [rbp+var_20], r13
0x18002907f  mov     r14d, r13d
0x180029082  mov     [rbp+var_40], r13
0x180029086  mov     [rbp+hMem], r13
0x18002908a  mov     dword ptr [rbp+var_48], r13d
0x18002908e  mov     [rbp+lpMem], r13
0x180029092  mov     [rbp+var_18], r13
0x180029096  mov     [rbp+var_38], r13
0x18002909a  mov     [rsp+78h+var_50], r13
0x18002909f  mov     dword ptr [rsp+78h+var_58], r13d
0x1800290a4  mov     edx, 0C0000000h
0x1800290a9  mov     r9d, 20000000h
0x1800290af  lea     r8d, [r13+3]
0x1800290b3  mov     rcx, rax
0x1800290b6  call    cs:__imp_WIMCreateFile
0x1800290bc  mov     rbx, rax
0x1800290bf  test    rax, rax
0x1800290c2  jnz     short loc_18002910F
0x1800290c4  mov     ebx, r13d
0x1800290c7  mov     [rbp+var_10], rbx
0x1800290cb  call    cs:__imp_GetLastError
0x1800290d1  mov     edi, eax
0x1800290d3  test    eax, eax
0x1800290d5  jnz     short loc_1800290DE
0x1800290d7  mov     edi, 80004005h
0x1800290dc  jmp     short loc_1800290E9
0x1800290de  jle     short loc_1800290E9
0x1800290e0  movzx   edi, ax
0x1800290e3  or      edi, 80070000h
0x1800290e9  cmp     [rsi+58h], r13
0x1800290ed  jz      loc_18002936D
0x1800290f3  mov     ecx, r13d
0x1800290f6  test    edi, edi
0x1800290f8  jns     loc_180029368
0x1800290fe  mov     dword ptr [rsp+78h+var_50], edi
0x180029102  mov     dword ptr [rsp+78h+var_58], 919h
0x18002910a  jmp     loc_180029341
0x18002910f  mov     [rbp+var_10], rbx
0x180029113  lea     rcx, [rbp+var_40]
0x180029117  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x18002911c  mov     edi, eax
0x18002911e  test    eax, eax
0x180029120  jns     short loc_180029168
0x180029122  mov     rcx, [rsi+58h]
0x180029126  test    rcx, rcx
0x180029129  jz      short loc_18002915F
0x18002912b  mov     dword ptr [rsp+78h+var_50], eax
0x18002912f  mov     dword ptr [rsp+78h+var_58], 91Bh
0x180029137  lea     r9, aCdlpactionreco_18; "CDlpActionRecoverCrypto::SaveKeyToWim"
0x18002913e  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180029145  mov     edx, 4
0x18002914a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002914f  mov     ecx, eax
0x180029151  test    eax, eax
0x180029153  jns     short loc_18002915A
0x180029155  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002915a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002915f  mov     r14, [rbp+var_40]
0x180029163  jmp     loc_18002936D
0x180029168  mov     r14, [rbp+var_40]
0x18002916c  mov     rdx, r14
0x18002916f  mov     rcx, rbx
0x180029172  call    cs:__imp_WIMSetTemporaryPath
0x180029178  test    eax, eax
0x18002917a  jnz     short loc_1800291C0
0x18002917c  call    cs:__imp_GetLastError
0x180029182  mov     edi, eax
0x180029184  test    eax, eax
0x180029186  jnz     short loc_18002918F
0x180029188  mov     edi, 80004005h
0x18002918d  jmp     short loc_18002919A
0x18002918f  jle     short loc_18002919A
0x180029191  movzx   edi, ax
0x180029194  or      edi, 80070000h
0x18002919a  cmp     [rsi+58h], r13
0x18002919e  jz      loc_18002936D
0x1800291a4  mov     ecx, r13d
0x1800291a7  test    edi, edi
0x1800291a9  jns     loc_180029368
0x1800291af  mov     dword ptr [rsp+78h+var_50], edi
0x1800291b3  mov     dword ptr [rsp+78h+var_58], 91Ch
0x1800291bb  jmp     loc_180029341
0x1800291c0  mov     dword ptr [rbp+var_48], r13d
0x1800291c4  lea     r8, [rbp+var_48]
0x1800291c8  lea     rdx, [rbp+hMem]
0x1800291cc  mov     rcx, rbx
0x1800291cf  call    cs:__imp_WIMGetImageInformation
0x1800291d5  test    eax, eax
0x1800291d7  jnz     short loc_18002921D
0x1800291d9  call    cs:__imp_GetLastError
0x1800291df  mov     edi, eax
0x1800291e1  test    eax, eax
0x1800291e3  jnz     short loc_1800291EC
0x1800291e5  mov     edi, 80004005h
0x1800291ea  jmp     short loc_1800291F7
0x1800291ec  jle     short loc_1800291F7
0x1800291ee  movzx   edi, ax
0x1800291f1  or      edi, 80070000h
0x1800291f7  cmp     [rsi+58h], r13
0x1800291fb  jz      loc_18002936D
0x180029201  mov     ecx, r13d
0x180029204  test    edi, edi
0x180029206  jns     loc_180029368
0x18002920c  mov     dword ptr [rsp+78h+var_50], edi
0x180029210  mov     dword ptr [rsp+78h+var_58], 91Fh
0x180029218  jmp     loc_180029341
0x18002921d  lea     r9, [rbp+var_20]
0x180029221  mov     edx, r15d
0x180029224  mov     rcx, r12
0x180029227  call    ?Base64Encode@?$CStringConvertT@K@@SAJPEBXKKPEAPEAG@Z; CStringConvertT<ulong>::Base64Encode(void const *,ulong,ulong,ushort * *)
0x18002922c  mov     edi, eax
0x18002922e  test    eax, eax
0x180029230  jns     short loc_180029250
0x180029232  mov     rcx, [rsi+58h]
0x180029236  test    rcx, rcx
0x180029239  jz      loc_18002936D
0x18002923f  mov     dword ptr [rsp+78h+var_50], eax
0x180029243  mov     dword ptr [rsp+78h+var_58], 923h
0x18002924b  jmp     loc_180029345
0x180029250  mov     r8d, dword ptr [rbp+var_48]
0x180029254  mov     rdx, [rbp+hMem]
0x180029258  lea     rcx, [rbp+var_38]
0x18002925c  call    cs:__imp_UnattendCtxDeserializeBuffer
0x180029262  mov     edi, eax
0x180029264  test    eax, eax
0x180029266  jns     short loc_180029286
0x180029268  mov     rcx, [rsi+58h]
0x18002926c  test    rcx, rcx
0x18002926f  jz      loc_18002936D
0x180029275  mov     dword ptr [rsp+78h+var_50], eax
0x180029279  mov     dword ptr [rsp+78h+var_58], 928h
0x180029281  jmp     loc_180029345
0x180029286  mov     r9, [rbp+var_20]
0x18002928a  xor     r8d, r8d
0x18002928d  lea     rdx, aWimEsdKey; "WIM\\ESD\\KEY"
0x180029294  lea     rcx, [rbp+var_38]
0x180029298  call    cs:__imp_UnattendCtxSetString
0x18002929e  mov     edi, eax
0x1800292a0  test    eax, eax
0x1800292a2  jns     short loc_1800292C2
0x1800292a4  mov     rcx, [rsi+58h]
0x1800292a8  test    rcx, rcx
0x1800292ab  jz      loc_18002936D
0x1800292b1  mov     dword ptr [rsp+78h+var_50], eax
0x1800292b5  mov     dword ptr [rsp+78h+var_58], 929h
0x1800292bd  jmp     loc_180029345
0x1800292c2  lea     r8, [rbp+var_18]
0x1800292c6  lea     rdx, [rbp+lpMem]
0x1800292ca  lea     rcx, [rbp+var_38]
0x1800292ce  call    cs:__imp_UnattendCtxSerializeToBuffer
0x1800292d4  mov     edi, eax
0x1800292d6  test    eax, eax
0x1800292d8  jns     short loc_1800292F5
0x1800292da  mov     rcx, [rsi+58h]
0x1800292de  test    rcx, rcx
0x1800292e1  jz      loc_18002936D
0x1800292e7  mov     dword ptr [rsp+78h+var_50], eax
0x1800292eb  mov     dword ptr [rsp+78h+var_58], 92Ah
0x1800292f3  jmp     short loc_180029345
0x1800292f5  mov     r8d, dword ptr [rbp+var_18]
0x1800292f9  mov     rdx, [rbp+lpMem]
0x1800292fd  mov     rcx, rbx
0x180029300  call    cs:__imp_WIMSetImageInformation
0x180029306  test    eax, eax
0x180029308  jnz     short loc_18002936D
0x18002930a  call    cs:__imp_GetLastError
0x180029310  mov     edi, eax
0x180029312  test    eax, eax
0x180029314  jnz     short loc_18002931D
0x180029316  mov     edi, 80004005h
0x18002931b  jmp     short loc_180029328
0x18002931d  jle     short loc_180029328
0x18002931f  movzx   edi, ax
0x180029322  or      edi, 80070000h
0x180029328  cmp     [rsi+58h], r13
0x18002932c  jz      short loc_18002936D
0x18002932e  mov     ecx, r13d
0x180029331  test    edi, edi
0x180029333  jns     short loc_180029368
0x180029335  mov     dword ptr [rsp+78h+var_50], edi
0x180029339  mov     dword ptr [rsp+78h+var_58], 92Bh
0x180029341  mov     rcx, [rsi+58h]
0x180029345  lea     r9, aCdlpactionreco_18; "CDlpActionRecoverCrypto::SaveKeyToWim"
0x18002934c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180029353  mov     edx, 4
0x180029358  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002935d  test    eax, eax
0x18002935f  mov     ecx, eax
0x180029361  jns     short loc_180029368
0x180029363  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029368  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002936d  lea     rcx, [rbp+var_38]
0x180029371  call    cs:__imp_UnattendCtxCleanup
0x180029377  mov     ecx, edi
0x180029379  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002937e  nop
0x18002937f  mov     rsi, [rbp+lpMem]
0x180029383  test    rsi, rsi
0x180029386  jz      short loc_1800293A0
0x180029388  call    cs:__imp_GetProcessHeap
0x18002938e  mov     rcx, rax; hHeap
0x180029391  mov     r8, rsi; lpMem
0x180029394  xor     edx, edx; dwFlags
0x180029396  call    cs:__imp_HeapFree
0x18002939c  mov     [rbp+lpMem], r13
0x1800293a0  mov     rcx, [rbp+hMem]; hMem
0x1800293a4  test    rcx, rcx
0x1800293a7  jz      short loc_1800293B3
0x1800293a9  call    cs:__imp_LocalFree
0x1800293af  mov     [rbp+hMem], r13
0x1800293b3  test    rbx, rbx
0x1800293b6  jz      short loc_1800293C2
0x1800293b8  mov     rcx, rbx
0x1800293bb  call    cs:__imp_WIMCloseHandle
0x1800293c1  nop
0x1800293c2  test    r14, r14
0x1800293c5  jz      short loc_1800293E4
0x1800293c7  call    cs:__imp_GetProcessHeap
0x1800293cd  mov     rcx, rax; hHeap
0x1800293d0  lea     r8, [r14-4]; lpMem
0x1800293d4  xor     edx, edx; dwFlags
0x1800293d6  call    cs:__imp_HeapFree
0x1800293dc  xor     ecx, ecx
0x1800293de  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800293e3  nop
0x1800293e4  mov     rbx, [rbp+var_20]
0x1800293e8  test    rbx, rbx
0x1800293eb  jz      short loc_180029409
0x1800293ed  call    cs:__imp_GetProcessHeap
0x1800293f3  mov     rcx, rax; hHeap
0x1800293f6  lea     r8, [rbx-4]; lpMem
0x1800293fa  xor     edx, edx; dwFlags
0x1800293fc  call    cs:__imp_HeapFree
0x180029402  xor     ecx, ecx
0x180029404  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029409  mov     eax, edi
0x18002940b  add     rsp, 78h
0x18002940f  pop     r15
0x180029411  pop     r14
0x180029413  pop     r13
0x180029415  pop     r12
0x180029417  pop     rdi
0x180029418  pop     rsi
0x180029419  pop     rbx
0x18002941a  pop     rbp
0x18002941b  retn
```
