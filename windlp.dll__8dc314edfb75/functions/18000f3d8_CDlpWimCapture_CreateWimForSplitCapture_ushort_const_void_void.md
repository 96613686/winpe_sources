# CDlpWimCapture::CreateWimForSplitCapture(ushort const *,void * *,void * *)

- ea: `0x18000f3d8`
- end: `0x18000f919`
- name: `?CreateWimForSplitCapture@CDlpWimCapture@@AEAAJPEBGPEAPEAX1@Z`
- size: `1345`
- prototype: `__int64 __fastcall(CDlpWimCapture *this, unsigned __int16 *, void **, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18000a088`
- `0x18000efb8`

## callees

- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000ea20`
- `0x18000f3d8`
- `0x180012f5c`
- `0x180018cc4`
- `0x18001fd60`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18000f8c7`
- `WIMGAPI!WIMCloseHandle` at `0x18000f8f8`
- `WIMGAPI!WIMCloseHandle` at `0x18000f8c7`
- `WIMGAPI!WIMCloseHandle` at `0x18000f8f8`
- `WIMGAPI!WIMAddImagePath` at `0x18000f70f`
- `WIMGAPI!WIMAddImagePath` at `0x18000f70f`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000f51b`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18000f51b`
- `WIMGAPI!WIMSetReferenceFile` at `0x18000f780`
- `WIMGAPI!WIMSetReferenceFile` at `0x18000f780`
- `WIMGAPI!WIMCaptureImage` at `0x18000f69c`
- `WIMGAPI!WIMCaptureImage` at `0x18000f69c`
- `WIMGAPI!WIMCreateFile` at `0x18000f455`
- `WIMGAPI!WIMCreateFile` at `0x18000f455`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f625`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f625`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f5cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f5cc`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000f88a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000f88a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f9`

## string_xrefs

- `0x18000f4a7`: `CDlpWimCapture::CreateWimForSplitCapture`
- `0x18000f5a3`: `CDlpWimCapture::CreateWimForSplitCapture`
- `0x18000f4e5`: `Wim Capture: Successfully created WIM file.`
- `0x18000f503`: `Wim Capture: Setting temp path to [%s]`

## pseudocode

```c
__int64 __fastcall CDlpWimCapture::CreateWimForSplitCapture(
        CDlpWimCapture *this,
        unsigned __int16 *a2,
        void **a3,
        void **a4)
{
  const WCHAR *v7; // r15
  void *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  signed int LastError; // eax
  signed int v13; // r14d
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  signed int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  signed int v24; // eax
  signed int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  signed int v28; // eax
  signed int v29; // eax
  int v30; // r14d
  unsigned int v31; // edx
  int StringCch; // eax
  signed int v33; // eax
  int v34; // eax
  void *v35; // rax
  void *v36; // rax
  __int64 v37; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v39; // rax
  __int64 v41; // [rsp+20h] [rbp-30h]
  __int64 v42; // [rsp+28h] [rbp-28h]
  __int64 v43; // [rsp+30h] [rbp-20h] BYREF
  __int64 v44; // [rsp+38h] [rbp-18h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-10h] BYREF
  __int64 v46; // [rsp+48h] [rbp-8h]
  unsigned int v47; // [rsp+90h] [rbp+40h] BYREF
  void **v48; // [rsp+A0h] [rbp+50h]

  v48 = a3;
  v44 = 0;
  v7 = 0;
  lpFileName = 0;
  v8 = 0;
  v46 = 0;
  v43 = 0;
  v9 = *((_QWORD *)this + 15);
  if ( v9 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v9, 2, L"Wim Capture: Creating a new WIM file: [%s]", a2);
  v10 = WIMCreateFile(a2, 3221225472LL, 2, *((unsigned int *)this + 34), *((_DWORD *)this + 32), 0);
  v11 = v10;
  if ( !v10 )
  {
    v44 = 0;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    if ( *((_QWORD *)this + 15) )
    {
      v14 = 0;
      if ( v13 < 0 )
      {
        LODWORD(v42) = v13;
        LODWORD(v41) = 680;
        goto LABEL_11;
      }
      goto LABEL_13;
    }
    goto LABEL_91;
  }
  v44 = v10;
  v16 = *((_QWORD *)this + 15);
  if ( v16 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v16, 2, L"Wim Capture: Successfully created WIM file.");
  v17 = *((_QWORD *)this + 15);
  if ( v17 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v17, 2, L"Wim Capture: Setting temp path to [%s]", *((_QWORD *)this + 9));
  if ( (unsigned int)WIMSetTemporaryPath(v11, *((_QWORD *)this + 9)) )
  {
    v20 = CMiscHelpersT<CEmptyType>::GenerateTempFileName(v18, &lpFileName);
    v13 = v20;
    v7 = lpFileName;
    if ( v20 < 0 )
    {
      v21 = *((_QWORD *)this + 15);
      if ( !v21 )
        goto LABEL_89;
      LODWORD(v42) = v20;
      LODWORD(v41) = 690;
      goto LABEL_29;
    }
    if ( !DeleteFileW(lpFileName) )
    {
      v24 = GetLastError();
      v13 = v24;
      if ( v24 )
      {
        if ( v24 > 0 )
          v13 = (unsigned __int16)v24 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_89;
      v23 = 0;
      if ( v13 >= 0 )
        goto LABEL_31;
      LODWORD(v42) = v13;
      LODWORD(v41) = 691;
LABEL_40:
      v21 = *((_QWORD *)this + 15);
      goto LABEL_29;
    }
    if ( !CreateDirectoryW(v7, 0) )
    {
      v25 = GetLastError();
      v13 = v25;
      if ( v25 )
      {
        if ( v25 > 0 )
          v13 = (unsigned __int16)v25 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_89;
      v23 = 0;
      if ( v13 >= 0 )
        goto LABEL_31;
      LODWORD(v42) = v13;
      LODWORD(v41) = 692;
      goto LABEL_40;
    }
    v26 = *((_QWORD *)this + 15);
    if ( v26 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v26, 2, L"Wim Capture: Seeding WIM with an empty image [%s]", v7);
    v27 = WIMCaptureImage(v11, v7, 0);
    v8 = (void *)v27;
    if ( !v27 )
    {
      v46 = 0;
      v28 = GetLastError();
      v13 = v28;
      if ( v28 )
      {
        if ( v28 > 0 )
          v13 = (unsigned __int16)v28 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_89;
      v23 = 0;
      if ( v13 >= 0 )
        goto LABEL_31;
      LODWORD(v42) = v13;
      LODWORD(v41) = 696;
      goto LABEL_40;
    }
    v46 = v27;
    if ( !(unsigned int)WIMAddImagePath(v27, *((_QWORD *)this + 7), L"\\", 201326592) )
    {
      v29 = GetLastError();
      v13 = v29;
      if ( v29 )
      {
        if ( v29 > 0 )
          v13 = (unsigned __int16)v29 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_89;
      v23 = 0;
      if ( v13 >= 0 )
        goto LABEL_31;
      LODWORD(v42) = v13;
      LODWORD(v41) = 703;
      goto LABEL_40;
    }
    v30 = 0;
    if ( *((_DWORD *)this + 9) )
    {
      while ( (unsigned int)WIMSetReferenceFile(v11, *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * v30), 0x10000) )
      {
        if ( (unsigned int)++v30 >= *((_DWORD *)this + 9) )
          goto LABEL_70;
      }
      v33 = GetLastError();
      v13 = v33;
      if ( v33 )
      {
        if ( v33 > 0 )
          v13 = (unsigned __int16)v33 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_89;
      v23 = 0;
      if ( v13 >= 0 )
        goto LABEL_31;
      LODWORD(v42) = v13;
      LODWORD(v41) = 709;
      goto LABEL_40;
    }
LABEL_70:
    v31 = 0;
    v47 = 0;
    if ( a2 )
    {
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a2, &v47);
      v13 = StringCch;
      if ( StringCch < 0 )
      {
LABEL_74:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
LABEL_75:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
        if ( v13 >= 0 )
        {
          v34 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((__int64)this + 32, &v43);
          v13 = v34;
          if ( v34 >= 0 )
          {
            v35 = (void *)v11;
            v11 = 0;
            *v48 = v35;
            v36 = v8;
            v8 = 0;
            *a4 = v36;
          }
          else
          {
            v21 = *((_QWORD *)this + 15);
            if ( v21 )
            {
              LODWORD(v42) = v34;
              LODWORD(v41) = 715;
LABEL_29:
              v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
                      v21,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDlpWimCapture::CreateWimForSplitCapture",
                      v41,
                      v42);
              v23 = (unsigned int)v22;
              if ( v22 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v22);
LABEL_31:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
            }
          }
        }
        else
        {
          v21 = *((_QWORD *)this + 15);
          if ( v21 )
          {
            LODWORD(v42) = v13;
            LODWORD(v41) = 714;
            goto LABEL_29;
          }
        }
LABEL_89:
        if ( v7 )
          RemoveDirectoryW(v7);
        goto LABEL_91;
      }
      v31 = v47;
    }
    StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a2, v31, &v43);
    v13 = StringCch;
    if ( StringCch >= 0 )
      goto LABEL_75;
    goto LABEL_74;
  }
  v19 = GetLastError();
  v13 = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      v13 = (unsigned __int16)v19 | 0x80070000;
  }
  else
  {
    v13 = -2147467259;
  }
  if ( *((_QWORD *)this + 15) )
  {
    v14 = 0;
    if ( v13 < 0 )
    {
      LODWORD(v42) = v13;
      LODWORD(v41) = 686;
LABEL_11:
      v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *((_QWORD *)this + 15),
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpWimCapture::CreateWimForSplitCapture",
              v41,
              v42);
      v14 = (unsigned int)v15;
      if ( v15 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
    }
LABEL_13:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_91:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
  v37 = v43;
  if ( v43 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v37 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
    WIMCloseHandle(v8);
  if ( v7 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v11 )
    WIMCloseHandle(v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000f3d8  mov     [rsp-38h+arg_8], rbx
0x18000f3dd  mov     [rsp-38h+arg_10], r8
0x18000f3e2  push    rbp
0x18000f3e3  push    rsi
0x18000f3e4  push    rdi
0x18000f3e5  push    r12
0x18000f3e7  push    r13
0x18000f3e9  push    r14
0x18000f3eb  push    r15
0x18000f3ed  mov     rbp, rsp
0x18000f3f0  sub     rsp, 50h
0x18000f3f4  mov     r13, r9
0x18000f3f7  mov     r12, rdx
0x18000f3fa  mov     rsi, rcx
0x18000f3fd  xor     r14d, r14d
0x18000f400  mov     [rbp+var_18], r14
0x18000f404  mov     r15d, r14d
0x18000f407  mov     [rbp+lpFileName], r14
0x18000f40b  mov     ebx, r14d
0x18000f40e  mov     [rbp+var_8], rbx
0x18000f412  mov     [rbp+var_20], r14
0x18000f416  mov     rcx, [rcx+78h]
0x18000f41a  lea     edi, [r14+2]
0x18000f41e  test    rcx, rcx
0x18000f421  jz      short loc_18000F434
0x18000f423  mov     r9, rdx
0x18000f426  lea     r8, aWimCaptureCrea_0; "Wim Capture: Creating a new WIM file: ["...
0x18000f42d  mov     edx, edi
0x18000f42f  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000f434  mov     [rsp+50h+var_28], r14
0x18000f439  mov     eax, [rsi+80h]
0x18000f43f  mov     dword ptr [rsp+50h+var_30], eax
0x18000f443  mov     r9d, [rsi+88h]
0x18000f44a  mov     r8d, edi
0x18000f44d  mov     edx, 0C0000000h
0x18000f452  mov     rcx, r12
0x18000f455  call    cs:__imp_WIMCreateFile
0x18000f45b  mov     rdi, rax
0x18000f45e  test    rax, rax
0x18000f461  jnz     short loc_18000F4D8
0x18000f463  mov     [rbp+var_18], rax
0x18000f467  call    cs:__imp_GetLastError
0x18000f46d  mov     r14d, eax
0x18000f470  test    eax, eax
0x18000f472  jnz     short loc_18000F47C
0x18000f474  mov     r14d, 80004005h
0x18000f47a  jmp     short loc_18000F489
0x18000f47c  jle     short loc_18000F489
0x18000f47e  movzx   r14d, ax
0x18000f482  or      r14d, 80070000h
0x18000f489  cmp     [rsi+78h], rdi
0x18000f48d  jz      loc_18000F890
0x18000f493  xor     ecx, ecx
0x18000f495  test    r14d, r14d
0x18000f498  jns     short loc_18000F4CE
0x18000f49a  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f49f  mov     dword ptr [rsp+50h+var_30], 2A8h
0x18000f4a7  lea     r9, aCdlpwimcapture_8; "CDlpWimCapture::CreateWimForSplitCaptur"...
0x18000f4ae  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000f4b5  mov     edx, 4
0x18000f4ba  mov     rcx, [rsi+78h]
0x18000f4be  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000f4c3  test    eax, eax
0x18000f4c5  mov     ecx, eax
0x18000f4c7  jns     short loc_18000F4CE
0x18000f4c9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f4ce  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f4d3  jmp     loc_18000F890
0x18000f4d8  mov     [rbp+var_18], rdi
0x18000f4dc  mov     rcx, [rsi+78h]
0x18000f4e0  test    rcx, rcx
0x18000f4e3  jz      short loc_18000F4F6
0x18000f4e5  lea     r8, aWimCaptureSucc_1; "Wim Capture: Successfully created WIM f"...
0x18000f4ec  mov     edx, 2
0x18000f4f1  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000f4f6  mov     rcx, [rsi+78h]
0x18000f4fa  test    rcx, rcx
0x18000f4fd  jz      short loc_18000F514
0x18000f4ff  mov     r9, [rsi+48h]
0x18000f503  lea     r8, aWimCaptureSett; "Wim Capture: Setting temp path to [%s]"
0x18000f50a  mov     edx, 2
0x18000f50f  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000f514  mov     rdx, [rsi+48h]
0x18000f518  mov     rcx, rdi
0x18000f51b  call    cs:__imp_WIMSetTemporaryPath
0x18000f521  test    eax, eax
0x18000f523  jnz     short loc_18000F56F
0x18000f525  call    cs:__imp_GetLastError
0x18000f52b  mov     r14d, eax
0x18000f52e  test    eax, eax
0x18000f530  jnz     short loc_18000F53A
0x18000f532  mov     r14d, 80004005h
0x18000f538  jmp     short loc_18000F547
0x18000f53a  jle     short loc_18000F547
0x18000f53c  movzx   r14d, ax
0x18000f540  or      r14d, 80070000h
0x18000f547  cmp     qword ptr [rsi+78h], 0
0x18000f54c  jz      loc_18000F890
0x18000f552  xor     ecx, ecx
0x18000f554  test    r14d, r14d
0x18000f557  jns     loc_18000F4CE
0x18000f55d  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f562  mov     dword ptr [rsp+50h+var_30], 2AEh
0x18000f56a  jmp     loc_18000F4A7
0x18000f56f  lea     rdx, [rbp+lpFileName]
0x18000f573  call    ?GenerateTempFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GenerateTempFileName(ushort const *,ushort * *)
0x18000f578  mov     r14d, eax
0x18000f57b  mov     r15, [rbp+lpFileName]
0x18000f57f  test    eax, eax
0x18000f581  jns     short loc_18000F5C9
0x18000f583  mov     rcx, [rsi+78h]
0x18000f587  test    rcx, rcx
0x18000f58a  jz      loc_18000F882
0x18000f590  mov     dword ptr [rsp+50h+var_28], eax
0x18000f594  mov     dword ptr [rsp+50h+var_30], 2B2h
0x18000f59c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000f5a3  lea     r9, aCdlpwimcapture_8; "CDlpWimCapture::CreateWimForSplitCaptur"...
0x18000f5aa  mov     edx, 4
0x18000f5af  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000f5b4  test    eax, eax
0x18000f5b6  mov     ecx, eax
0x18000f5b8  jns     short loc_18000F5BF
0x18000f5ba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f5bf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f5c4  jmp     loc_18000F882
0x18000f5c9  mov     rcx, r15; lpFileName
0x18000f5cc  call    cs:__imp_DeleteFileW
0x18000f5d2  test    eax, eax
0x18000f5d4  jnz     short loc_18000F620
0x18000f5d6  call    cs:__imp_GetLastError
0x18000f5dc  mov     r14d, eax
0x18000f5df  test    eax, eax
0x18000f5e1  jnz     short loc_18000F5EB
0x18000f5e3  mov     r14d, 80004005h
0x18000f5e9  jmp     short loc_18000F5F8
0x18000f5eb  jle     short loc_18000F5F8
0x18000f5ed  movzx   r14d, ax
0x18000f5f1  or      r14d, 80070000h
0x18000f5f8  cmp     qword ptr [rsi+78h], 0
0x18000f5fd  jz      loc_18000F882
0x18000f603  xor     ecx, ecx
0x18000f605  test    r14d, r14d
0x18000f608  jns     short loc_18000F5BF
0x18000f60a  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f60f  mov     dword ptr [rsp+50h+var_30], 2B3h
0x18000f617  mov     rcx, [rsi+78h]
0x18000f61b  jmp     loc_18000F59C
0x18000f620  xor     edx, edx; lpSecurityAttributes
0x18000f622  mov     rcx, r15; lpPathName
0x18000f625  call    cs:__imp_CreateDirectoryW
0x18000f62b  test    eax, eax
0x18000f62d  jnz     short loc_18000F676
0x18000f62f  call    cs:__imp_GetLastError
0x18000f635  mov     r14d, eax
0x18000f638  test    eax, eax
0x18000f63a  jnz     short loc_18000F644
0x18000f63c  mov     r14d, 80004005h
0x18000f642  jmp     short loc_18000F651
0x18000f644  jle     short loc_18000F651
0x18000f646  movzx   r14d, ax
0x18000f64a  or      r14d, 80070000h
0x18000f651  cmp     qword ptr [rsi+78h], 0
0x18000f656  jz      loc_18000F882
0x18000f65c  xor     ecx, ecx
0x18000f65e  test    r14d, r14d
0x18000f661  jns     loc_18000F5BF
0x18000f667  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f66c  mov     dword ptr [rsp+50h+var_30], 2B4h
0x18000f674  jmp     short loc_18000F617
0x18000f676  mov     rcx, [rsi+78h]
0x18000f67a  test    rcx, rcx
0x18000f67d  jz      short loc_18000F693
0x18000f67f  mov     r9, r15
0x18000f682  lea     r8, aWimCaptureSeed; "Wim Capture: Seeding WIM with an empty "...
0x18000f689  mov     edx, 2
0x18000f68e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000f693  xor     r8d, r8d
0x18000f696  mov     rdx, r15
0x18000f699  mov     rcx, rdi
0x18000f69c  call    cs:__imp_WIMCaptureImage
0x18000f6a2  mov     rbx, rax
0x18000f6a5  test    rax, rax
0x18000f6a8  jnz     short loc_18000F6F7
0x18000f6aa  mov     [rbp+var_8], rax
0x18000f6ae  call    cs:__imp_GetLastError
0x18000f6b4  mov     r14d, eax
0x18000f6b7  test    eax, eax
0x18000f6b9  jnz     short loc_18000F6C3
0x18000f6bb  mov     r14d, 80004005h
0x18000f6c1  jmp     short loc_18000F6D0
0x18000f6c3  jle     short loc_18000F6D0
0x18000f6c5  movzx   r14d, ax
0x18000f6c9  or      r14d, 80070000h
0x18000f6d0  cmp     [rsi+78h], rbx
0x18000f6d4  jz      loc_18000F882
0x18000f6da  xor     ecx, ecx
0x18000f6dc  test    r14d, r14d
0x18000f6df  jns     loc_18000F5BF
0x18000f6e5  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f6ea  mov     dword ptr [rsp+50h+var_30], 2B8h
0x18000f6f2  jmp     loc_18000F617
0x18000f6f7  mov     [rbp+var_8], rbx
0x18000f6fb  mov     r9d, 0C000000h
0x18000f701  lea     r8, asc_180084C70; "\\"
0x18000f708  mov     rdx, [rsi+38h]
0x18000f70c  mov     rcx, rbx
0x18000f70f  call    cs:__imp_WIMAddImagePath
0x18000f715  test    eax, eax
0x18000f717  jnz     short loc_18000F763
0x18000f719  call    cs:__imp_GetLastError
0x18000f71f  mov     r14d, eax
0x18000f722  test    eax, eax
0x18000f724  jnz     short loc_18000F72E
0x18000f726  mov     r14d, 80004005h
0x18000f72c  jmp     short loc_18000F73B
0x18000f72e  jle     short loc_18000F73B
0x18000f730  movzx   r14d, ax
0x18000f734  or      r14d, 80070000h
0x18000f73b  cmp     qword ptr [rsi+78h], 0
0x18000f740  jz      loc_18000F882
0x18000f746  xor     ecx, ecx
0x18000f748  test    r14d, r14d
0x18000f74b  jns     loc_18000F5BF
0x18000f751  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f756  mov     dword ptr [rsp+50h+var_30], 2BFh
0x18000f75e  jmp     loc_18000F617
0x18000f763  xor     r14d, r14d
0x18000f766  cmp     [rsi+24h], r14d
0x18000f76a  jbe     short loc_18000F793
0x18000f76c  mov     rcx, [rsi+28h]
0x18000f770  movsxd  rax, r14d
0x18000f773  mov     r8d, 10000h
0x18000f779  mov     rdx, [rcx+rax*8]
0x18000f77d  mov     rcx, rdi
0x18000f780  call    cs:__imp_WIMSetReferenceFile
0x18000f786  test    eax, eax
0x18000f788  jz      short loc_18000F7F9
0x18000f78a  inc     r14d
0x18000f78d  cmp     r14d, [rsi+24h]
0x18000f791  jb      short loc_18000F76C
0x18000f793  xor     edx, edx
0x18000f795  mov     [rbp+arg_0], edx
0x18000f798  test    r12, r12
0x18000f79b  jz      short loc_18000F7B3
0x18000f79d  lea     rdx, [rbp+arg_0]
0x18000f7a1  mov     rcx, r12
0x18000f7a4  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18000f7a9  mov     r14d, eax
0x18000f7ac  test    eax, eax
0x18000f7ae  js      short loc_18000F7C6
0x18000f7b0  mov     edx, [rbp+arg_0]
0x18000f7b3  lea     r8, [rbp+var_20]
0x18000f7b7  mov     rcx, r12; Src
0x18000f7ba  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18000f7bf  mov     r14d, eax
0x18000f7c2  test    eax, eax
0x18000f7c4  jns     short loc_18000F7CD
0x18000f7c6  mov     ecx, eax
0x18000f7c8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f7cd  mov     ecx, r14d
0x18000f7d0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f7d5  test    r14d, r14d
0x18000f7d8  jns     short loc_18000F83F
0x18000f7da  mov     rcx, [rsi+78h]
0x18000f7de  test    rcx, rcx
0x18000f7e1  jz      loc_18000F882
0x18000f7e7  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f7ec  mov     dword ptr [rsp+50h+var_30], 2CAh
0x18000f7f4  jmp     loc_18000F59C
0x18000f7f9  call    cs:__imp_GetLastError
0x18000f7ff  mov     r14d, eax
0x18000f802  test    eax, eax
0x18000f804  jnz     short loc_18000F80E
0x18000f806  mov     r14d, 80004005h
0x18000f80c  jmp     short loc_18000F81B
0x18000f80e  jle     short loc_18000F81B
0x18000f810  movzx   r14d, ax
0x18000f814  or      r14d, 80070000h
0x18000f81b  cmp     qword ptr [rsi+78h], 0
0x18000f820  jz      short loc_18000F882
0x18000f822  xor     ecx, ecx
0x18000f824  test    r14d, r14d
0x18000f827  jns     loc_18000F5BF
0x18000f82d  mov     dword ptr [rsp+50h+var_28], r14d
0x18000f832  mov     dword ptr [rsp+50h+var_30], 2C5h
0x18000f83a  jmp     loc_18000F617
0x18000f83f  lea     rcx, [rsi+20h]
0x18000f843  lea     rdx, [rbp+var_20]
0x18000f847  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x18000f84c  mov     r14d, eax
0x18000f84f  test    eax, eax
0x18000f851  jns     short loc_18000F86D
0x18000f853  mov     rcx, [rsi+78h]
0x18000f857  test    rcx, rcx
0x18000f85a  jz      short loc_18000F882
0x18000f85c  mov     dword ptr [rsp+50h+var_28], eax
0x18000f860  mov     dword ptr [rsp+50h+var_30], 2CBh
0x18000f868  jmp     loc_18000F59C
0x18000f86d  mov     rax, rdi
0x18000f870  xor     edi, edi
  ... truncated ...
```
