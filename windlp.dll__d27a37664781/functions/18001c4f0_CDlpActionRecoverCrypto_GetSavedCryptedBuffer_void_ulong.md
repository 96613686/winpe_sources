# CDlpActionRecoverCrypto::GetSavedCryptedBuffer(void *,ulong)

- ea: `0x18001c4f0`
- end: `0x18001c767`
- name: `?GetSavedCryptedBuffer@CDlpActionRecoverCrypto@@AEAAJPEAXK@Z`
- size: `631`
- prototype: `int(CDlpActionRecoverCrypto *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001455c`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001c4f0`
- `0x18001cc44`
- `0x18001fd60`
- `0x180028640`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x18001c68b`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x18001c68b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c616`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c616`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c71d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c71d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c730`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c73f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c70d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c70d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionRecoverCrypto::GetSavedCryptedBuffer(CDlpActionRecoverCrypto *this, void *a2, DWORD a3)
{
  LPCWSTR v6; // r14
  __int64 v7; // rbx
  signed int v8; // edi
  __int64 v9; // rcx
  int WorkingPath; // eax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  HANDLE FileW; // rax
  signed int v16; // eax
  __int64 v17; // rcx
  signed int LastError; // eax
  int v19; // eax
  HANDLE ProcessHeap; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-50h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-48h]
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+A8h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp+48h] BYREF

  v6 = 0;
  lpFileName = 0;
  bstrString = 0;
  v7 = -1;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_33;
    LODWORD(dwFlagsAndAttributes) = -2147024809;
    dwCreationDisposition[0] = 1073;
    goto LABEL_30;
  }
  WorkingPath = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(
                  this,
                  &bstrString);
  v8 = WorkingPath;
  if ( WorkingPath < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_33;
    LODWORD(dwFlagsAndAttributes) = WorkingPath;
    dwCreationDisposition[0] = 1075;
    goto LABEL_30;
  }
  v11 = STRAPI_Format((unsigned __int16 **)&lpFileName, L"%s\\%s", bstrString, L"CryptoSavedBuffer.tmp");
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( v12 )
    {
      v13 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v12,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionRecoverCrypto::GetSavedCryptedBuffer",
              1076,
              v11);
      v14 = (unsigned int)v13;
      if ( v13 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
    }
    v6 = lpFileName;
    goto LABEL_33;
  }
  v6 = lpFileName;
  FileW = CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 0x8000000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v7 = (__int64)FileW;
    if ( !ReadFileEx(FileW, a2, a3, &Overlapped, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v17 = 0;
        if ( v8 < 0 )
        {
          LODWORD(dwFlagsAndAttributes) = v8;
          dwCreationDisposition[0] = 1088;
          goto LABEL_29;
        }
LABEL_32:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
      }
    }
  }
  else
  {
    v16 = GetLastError();
    v8 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v17 = 0;
      if ( v8 < 0 )
      {
        LODWORD(dwFlagsAndAttributes) = v8;
        dwCreationDisposition[0] = 1086;
LABEL_29:
        v9 = *((_QWORD *)this + 11);
LABEL_30:
        v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v9,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::GetSavedCryptedBuffer",
                *(_QWORD *)dwCreationDisposition,
                dwFlagsAndAttributes);
        v17 = (unsigned int)v19;
        if ( v19 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v19);
        goto LABEL_32;
      }
      goto LABEL_32;
    }
  }
LABEL_33:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
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
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001c4f0  mov     rax, rsp
0x18001c4f3  mov     [rax+8], rbx
0x18001c4f7  mov     [rax+18h], rsi
0x18001c4fb  push    rbp
0x18001c4fc  push    rdi
0x18001c4fd  push    r12
0x18001c4ff  push    r14
0x18001c501  push    r15
0x18001c503  mov     rbp, rsp
0x18001c506  sub     rsp, 70h
0x18001c50a  mov     r12d, r8d
0x18001c50d  mov     r15, rdx
0x18001c510  mov     rsi, rcx
0x18001c513  xor     r14d, r14d
0x18001c516  mov     [rbp+lpFileName], r14
0x18001c51a  mov     [rbp+bstrString], r14
0x18001c51e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c522  mov     [rbp+var_30], rbx
0x18001c526  xorps   xmm0, xmm0
0x18001c529  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18001c52d  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18001c531  test    rdx, rdx
0x18001c534  jnz     short loc_18001C557
0x18001c536  mov     edi, 80070057h
0x18001c53b  mov     rcx, [rcx+58h]
0x18001c53f  test    rcx, rcx
0x18001c542  jz      loc_18001C6F8
0x18001c548  mov     [rax-70h], edi
0x18001c54b  mov     dword ptr [rax-78h], 431h
0x18001c552  jmp     loc_18001C6D0
0x18001c557  lea     rdx, [rbp+bstrString]
0x18001c55b  call    ?GetWorkingPath@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJPEAPEAG@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(ushort * *)
0x18001c560  mov     edi, eax
0x18001c562  test    eax, eax
0x18001c564  jns     short loc_18001C584
0x18001c566  mov     rcx, [rsi+58h]
0x18001c56a  test    rcx, rcx
0x18001c56d  jz      loc_18001C6F8
0x18001c573  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x18001c577  mov     [rsp+70h+dwCreationDisposition], 433h
0x18001c57f  jmp     loc_18001C6D0
0x18001c584  lea     r9, aCryptosavedbuf; "CryptoSavedBuffer.tmp"
0x18001c58b  mov     r8, [rbp+bstrString]
0x18001c58f  lea     rdx, aSS; "%s\\%s"
0x18001c596  lea     rcx, [rbp+lpFileName]; unsigned __int16 **
0x18001c59a  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18001c59f  mov     edi, eax
0x18001c5a1  test    eax, eax
0x18001c5a3  jns     short loc_18001C5EB
0x18001c5a5  mov     rcx, [rsi+58h]
0x18001c5a9  test    rcx, rcx
0x18001c5ac  jz      short loc_18001C5E2
0x18001c5ae  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x18001c5b2  mov     [rsp+70h+dwCreationDisposition], 434h
0x18001c5ba  lea     r9, aCdlpactionreco_20; "CDlpActionRecoverCrypto::GetSavedCrypte"...
0x18001c5c1  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001c5c8  mov     edx, 4
0x18001c5cd  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001c5d2  mov     ecx, eax
0x18001c5d4  test    eax, eax
0x18001c5d6  jns     short loc_18001C5DD
0x18001c5d8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c5dd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c5e2  mov     r14, [rbp+lpFileName]
0x18001c5e6  jmp     loc_18001C6F8
0x18001c5eb  mov     r14, [rbp+lpFileName]
0x18001c5ef  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18001c5f8  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18001c600  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18001c608  xor     r9d, r9d; lpSecurityAttributes
0x18001c60b  xor     r8d, r8d; dwShareMode
0x18001c60e  mov     edx, 80000000h; dwDesiredAccess
0x18001c613  mov     rcx, r14; lpFileName
0x18001c616  call    cs:__imp_CreateFileW
0x18001c61c  lea     rcx, [rax+1]
0x18001c620  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001c627  jnz     short loc_18001C66E
0x18001c629  mov     [rbp+var_30], rbx
0x18001c62d  call    cs:__imp_GetLastError
0x18001c633  mov     edi, eax
0x18001c635  test    eax, eax
0x18001c637  jnz     short loc_18001C640
0x18001c639  mov     edi, 80004005h
0x18001c63e  jmp     short loc_18001C64B
0x18001c640  jle     short loc_18001C64B
0x18001c642  movzx   edi, ax
0x18001c645  or      edi, 80070000h
0x18001c64b  cmp     qword ptr [rsi+58h], 0
0x18001c650  jz      loc_18001C6F8
0x18001c656  xor     ecx, ecx
0x18001c658  test    edi, edi
0x18001c65a  jns     loc_18001C6F3
0x18001c660  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], edi
0x18001c664  mov     [rsp+70h+dwCreationDisposition], 43Eh
0x18001c66c  jmp     short loc_18001C6CC
0x18001c66e  mov     rbx, rax
0x18001c671  mov     [rbp+var_30], rax
0x18001c675  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpCompletionRoutine
0x18001c67e  lea     r9, [rbp+Overlapped]; lpOverlapped
0x18001c682  mov     r8d, r12d; nNumberOfBytesToRead
0x18001c685  mov     rdx, r15; lpBuffer
0x18001c688  mov     rcx, rax; hFile
0x18001c68b  call    cs:__imp_ReadFileEx
0x18001c691  test    eax, eax
0x18001c693  jnz     short loc_18001C6F8
0x18001c695  call    cs:__imp_GetLastError
0x18001c69b  mov     edi, eax
0x18001c69d  test    eax, eax
0x18001c69f  jnz     short loc_18001C6A8
0x18001c6a1  mov     edi, 80004005h
0x18001c6a6  jmp     short loc_18001C6B3
0x18001c6a8  jle     short loc_18001C6B3
0x18001c6aa  movzx   edi, ax
0x18001c6ad  or      edi, 80070000h
0x18001c6b3  cmp     qword ptr [rsi+58h], 0
0x18001c6b8  jz      short loc_18001C6F8
0x18001c6ba  xor     ecx, ecx
0x18001c6bc  test    edi, edi
0x18001c6be  jns     short loc_18001C6F3
0x18001c6c0  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], edi
0x18001c6c4  mov     [rsp+70h+dwCreationDisposition], 440h
0x18001c6cc  mov     rcx, [rsi+58h]
0x18001c6d0  lea     r9, aCdlpactionreco_20; "CDlpActionRecoverCrypto::GetSavedCrypte"...
0x18001c6d7  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001c6de  mov     edx, 4
0x18001c6e3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001c6e8  test    eax, eax
0x18001c6ea  mov     ecx, eax
0x18001c6ec  jns     short loc_18001C6F3
0x18001c6ee  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c6f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c6f8  mov     ecx, edi
0x18001c6fa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c6ff  nop
0x18001c700  lea     rax, [rbx-1]
0x18001c704  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c708  ja      short loc_18001C714
0x18001c70a  mov     rcx, rbx; hObject
0x18001c70d  call    cs:__imp_CloseHandle
0x18001c713  nop
0x18001c714  mov     rcx, [rbp+bstrString]; bstrString
0x18001c718  test    rcx, rcx
0x18001c71b  jz      short loc_18001C72B
0x18001c71d  call    cs:__imp_SysFreeString
0x18001c723  mov     [rbp+bstrString], 0
0x18001c72b  test    r14, r14
0x18001c72e  jz      short loc_18001C74C
0x18001c730  call    cs:__imp_GetProcessHeap
0x18001c736  mov     rcx, rax; hHeap
0x18001c739  lea     r8, [r14-4]; lpMem
0x18001c73d  xor     edx, edx; dwFlags
0x18001c73f  call    cs:__imp_HeapFree
0x18001c745  xor     ecx, ecx
0x18001c747  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c74c  mov     eax, edi
0x18001c74e  lea     r11, [rsp+70h+var_s0]
0x18001c753  mov     rbx, [r11+30h]
0x18001c757  mov     rsi, [r11+40h]
0x18001c75b  mov     rsp, r11
0x18001c75e  pop     r15
0x18001c760  pop     r14
0x18001c762  pop     r12
0x18001c764  pop     rdi
0x18001c765  pop     rbp
0x18001c766  retn
```
