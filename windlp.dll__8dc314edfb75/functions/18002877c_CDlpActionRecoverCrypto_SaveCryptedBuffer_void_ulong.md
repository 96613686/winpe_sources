# CDlpActionRecoverCrypto::SaveCryptedBuffer(void *,ulong)

- ea: `0x18002877c`
- end: `0x180028a29`
- name: `?SaveCryptedBuffer@CDlpActionRecoverCrypto@@AEAAJPEAXK@Z`
- size: `685`
- prototype: `int(CDlpActionRecoverCrypto *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001455c`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001cc44`
- `0x18001fd60`
- `0x180028640`
- `0x18002877c`
- `0x180038c34`
- `0x1800392f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x18002894d`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x18002894d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800288d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800288d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800289df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800289df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800289f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800289f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028a01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002886d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002886d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800289cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800289cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionRecoverCrypto::SaveCryptedBuffer(CDlpActionRecoverCrypto *this, void *a2, DWORD a3)
{
  const WCHAR *v6; // rsi
  __int64 v7; // rbx
  int WorkingPath; // eax
  signed int v9; // edi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  signed int v15; // eax
  __int64 v16; // rcx
  HANDLE FileW; // rax
  signed int v18; // eax
  signed int LastError; // eax
  int v20; // eax
  HANDLE ProcessHeap; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-50h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-48h]
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  __int64 v26; // [rsp+48h] [rbp-28h]
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpFileName; // [rsp+B8h] [rbp+48h] BYREF

  v6 = 0;
  lpFileName = 0;
  bstrString = 0;
  v7 = -1;
  v26 = -1;
  memset(&Overlapped, 0, sizeof(Overlapped));
  WorkingPath = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(
                  this,
                  &bstrString);
  v9 = WorkingPath;
  if ( WorkingPath < 0 )
  {
    v10 = *((_QWORD *)this + 11);
    if ( !v10 )
      goto LABEL_39;
    LODWORD(dwFlagsAndAttributes) = WorkingPath;
    dwCreationDisposition[0] = 1109;
    goto LABEL_36;
  }
  v11 = STRAPI_Format((unsigned __int16 **)&lpFileName, L"%s\\%s", bstrString, L"CryptoSavedBuffer.tmp");
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( v12 )
    {
      v13 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v12,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionRecoverCrypto::SaveCryptedBuffer",
              1110,
              v11);
      v14 = (unsigned int)v13;
      if ( v13 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
    }
    v6 = lpFileName;
    goto LABEL_39;
  }
  v6 = lpFileName;
  if ( !(unsigned int)FileExists(lpFileName) || DeleteFileEx2((__int64)v6, 0) )
  {
    FileW = CreateFileW(v6, 0x40000000u, 0, 0, 1u, 0x8000000u, 0);
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v7 = (__int64)FileW;
      v26 = (__int64)FileW;
      if ( !WriteFileEx(FileW, a2, a3, &Overlapped, 0) )
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
          v16 = 0;
          if ( v9 < 0 )
          {
            LODWORD(dwFlagsAndAttributes) = v9;
            dwCreationDisposition[0] = 1127;
            goto LABEL_35;
          }
          goto LABEL_38;
        }
      }
    }
    else
    {
      v26 = -1;
      v18 = GetLastError();
      v9 = v18;
      if ( v18 )
      {
        if ( v18 > 0 )
          v9 = (unsigned __int16)v18 | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v16 = 0;
        if ( v9 < 0 )
        {
          LODWORD(dwFlagsAndAttributes) = v9;
          dwCreationDisposition[0] = 1125;
          goto LABEL_35;
        }
LABEL_38:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
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
      v16 = 0;
      if ( v9 < 0 )
      {
        LODWORD(dwFlagsAndAttributes) = v9;
        dwCreationDisposition[0] = 1114;
LABEL_35:
        v10 = *((_QWORD *)this + 11);
LABEL_36:
        v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v10,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::SaveCryptedBuffer",
                *(_QWORD *)dwCreationDisposition,
                dwFlagsAndAttributes);
        v16 = (unsigned int)v20;
        if ( v20 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
        goto LABEL_38;
      }
      goto LABEL_38;
    }
  }
LABEL_39:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002877c  mov     [rsp-28h+arg_0], rbx
0x180028781  mov     [rsp-28h+arg_8], rsi
0x180028786  push    rbp
0x180028787  push    rdi
0x180028788  push    r12
0x18002878a  push    r14
0x18002878c  push    r15
0x18002878e  mov     rbp, rsp
0x180028791  sub     rsp, 70h
0x180028795  mov     r15d, r8d
0x180028798  mov     r12, rdx
0x18002879b  mov     r14, rcx
0x18002879e  xor     esi, esi
0x1800287a0  mov     [rbp+lpFileName], rsi
0x1800287a4  mov     [rbp+bstrString], rsi
0x1800287a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800287ac  mov     [rbp+var_28], rbx
0x1800287b0  xorps   xmm0, xmm0
0x1800287b3  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x1800287b7  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x1800287bb  lea     rdx, [rbp+bstrString]
0x1800287bf  call    ?GetWorkingPath@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJPEAPEAG@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(ushort * *)
0x1800287c4  mov     edi, eax
0x1800287c6  test    eax, eax
0x1800287c8  jns     short loc_1800287E8
0x1800287ca  mov     rcx, [r14+58h]
0x1800287ce  test    rcx, rcx
0x1800287d1  jz      loc_1800289BA
0x1800287d7  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x1800287db  mov     [rsp+70h+dwCreationDisposition], 455h
0x1800287e3  jmp     loc_180028992
0x1800287e8  lea     r9, aCryptosavedbuf; "CryptoSavedBuffer.tmp"
0x1800287ef  mov     r8, [rbp+bstrString]
0x1800287f3  lea     rdx, aSS; "%s\\%s"
0x1800287fa  lea     rcx, [rbp+lpFileName]; unsigned __int16 **
0x1800287fe  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180028803  mov     edi, eax
0x180028805  test    eax, eax
0x180028807  jns     short loc_18002884F
0x180028809  mov     rcx, [r14+58h]
0x18002880d  test    rcx, rcx
0x180028810  jz      short loc_180028846
0x180028812  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x180028816  mov     [rsp+70h+dwCreationDisposition], 456h
0x18002881e  lea     r9, aCdlpactionreco_2; "CDlpActionRecoverCrypto::SaveCryptedBuf"...
0x180028825  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002882c  mov     edx, 4
0x180028831  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180028836  mov     ecx, eax
0x180028838  test    eax, eax
0x18002883a  jns     short loc_180028841
0x18002883c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028841  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028846  mov     rsi, [rbp+lpFileName]
0x18002884a  jmp     loc_1800289BA
0x18002884f  mov     rsi, [rbp+lpFileName]
0x180028853  mov     rcx, rsi
0x180028856  call    FileExists
0x18002885b  test    eax, eax
0x18002885d  jz      short loc_1800288B1
0x18002885f  xor     edx, edx
0x180028861  mov     rcx, rsi
0x180028864  call    DeleteFileEx2
0x180028869  test    eax, eax
0x18002886b  jnz     short loc_1800288B1
0x18002886d  call    cs:__imp_GetLastError
0x180028873  mov     edi, eax
0x180028875  test    eax, eax
0x180028877  jnz     short loc_180028880
0x180028879  mov     edi, 80004005h
0x18002887e  jmp     short loc_18002888B
0x180028880  jle     short loc_18002888B
0x180028882  movzx   edi, ax
0x180028885  or      edi, 80070000h
0x18002888b  cmp     qword ptr [r14+58h], 0
0x180028890  jz      loc_1800289BA
0x180028896  xor     ecx, ecx
0x180028898  test    edi, edi
0x18002889a  jns     loc_1800289B5
0x1800288a0  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], edi
0x1800288a4  mov     [rsp+70h+dwCreationDisposition], 45Ah
0x1800288ac  jmp     loc_18002898E
0x1800288b1  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800288ba  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800288c2  mov     [rsp+70h+dwCreationDisposition], 1; dwCreationDisposition
0x1800288ca  xor     r9d, r9d; lpSecurityAttributes
0x1800288cd  xor     r8d, r8d; dwShareMode
0x1800288d0  mov     edx, 40000000h; dwDesiredAccess
0x1800288d5  mov     rcx, rsi; lpFileName
0x1800288d8  call    cs:__imp_CreateFileW
0x1800288de  lea     rcx, [rax+1]
0x1800288e2  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800288e9  jnz     short loc_180028930
0x1800288eb  mov     [rbp+var_28], rbx
0x1800288ef  call    cs:__imp_GetLastError
0x1800288f5  mov     edi, eax
0x1800288f7  test    eax, eax
0x1800288f9  jnz     short loc_180028902
0x1800288fb  mov     edi, 80004005h
0x180028900  jmp     short loc_18002890D
0x180028902  jle     short loc_18002890D
0x180028904  movzx   edi, ax
0x180028907  or      edi, 80070000h
0x18002890d  cmp     qword ptr [r14+58h], 0
0x180028912  jz      loc_1800289BA
0x180028918  xor     ecx, ecx
0x18002891a  test    edi, edi
0x18002891c  jns     loc_1800289B5
0x180028922  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], edi
0x180028926  mov     [rsp+70h+dwCreationDisposition], 465h
0x18002892e  jmp     short loc_18002898E
0x180028930  mov     rbx, rax
0x180028933  mov     [rbp+var_28], rax
0x180028937  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpCompletionRoutine
0x180028940  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180028944  mov     r8d, r15d; nNumberOfBytesToWrite
0x180028947  mov     rdx, r12; lpBuffer
0x18002894a  mov     rcx, rax; hFile
0x18002894d  call    cs:__imp_WriteFileEx
0x180028953  test    eax, eax
0x180028955  jnz     short loc_1800289BA
0x180028957  call    cs:__imp_GetLastError
0x18002895d  mov     edi, eax
0x18002895f  test    eax, eax
0x180028961  jnz     short loc_18002896A
0x180028963  mov     edi, 80004005h
0x180028968  jmp     short loc_180028975
0x18002896a  jle     short loc_180028975
0x18002896c  movzx   edi, ax
0x18002896f  or      edi, 80070000h
0x180028975  cmp     qword ptr [r14+58h], 0
0x18002897a  jz      short loc_1800289BA
0x18002897c  xor     ecx, ecx
0x18002897e  test    edi, edi
0x180028980  jns     short loc_1800289B5
0x180028982  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], edi
0x180028986  mov     [rsp+70h+dwCreationDisposition], 467h
0x18002898e  mov     rcx, [r14+58h]
0x180028992  lea     r9, aCdlpactionreco_2; "CDlpActionRecoverCrypto::SaveCryptedBuf"...
0x180028999  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800289a0  mov     edx, 4
0x1800289a5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800289aa  test    eax, eax
0x1800289ac  mov     ecx, eax
0x1800289ae  jns     short loc_1800289B5
0x1800289b0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800289b5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800289ba  mov     ecx, edi
0x1800289bc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800289c1  nop
0x1800289c2  lea     rax, [rbx-1]
0x1800289c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800289ca  ja      short loc_1800289D6
0x1800289cc  mov     rcx, rbx; hObject
0x1800289cf  call    cs:__imp_CloseHandle
0x1800289d5  nop
0x1800289d6  mov     rcx, [rbp+bstrString]; bstrString
0x1800289da  test    rcx, rcx
0x1800289dd  jz      short loc_1800289ED
0x1800289df  call    cs:__imp_SysFreeString
0x1800289e5  mov     [rbp+bstrString], 0
0x1800289ed  test    rsi, rsi
0x1800289f0  jz      short loc_180028A0E
0x1800289f2  call    cs:__imp_GetProcessHeap
0x1800289f8  mov     rcx, rax; hHeap
0x1800289fb  lea     r8, [rsi-4]; lpMem
0x1800289ff  xor     edx, edx; dwFlags
0x180028a01  call    cs:__imp_HeapFree
0x180028a07  xor     ecx, ecx
0x180028a09  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028a0e  mov     eax, edi
0x180028a10  lea     r11, [rsp+70h+var_s0]
0x180028a15  mov     rbx, [r11+30h]
0x180028a19  mov     rsi, [r11+38h]
0x180028a1d  mov     rsp, r11
0x180028a20  pop     r15
0x180028a22  pop     r14
0x180028a24  pop     r12
0x180028a26  pop     rdi
0x180028a27  pop     rbp
0x180028a28  retn
```
