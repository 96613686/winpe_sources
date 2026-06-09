# CDlpActionLayoutUsb::CopyFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)

- ea: `0x18000c4d8`
- end: `0x18000cacf`
- name: `?CopyFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z`
- size: `1527`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cad8`

## callees

- `0x18000aba4`
- `0x18000b7f8`
- `0x18000c4d8`
- `0x18000d888`
- `0x180012f5c`
- `0x18001fd60`
- `0x180020468`
- `0x180038b44`
- `0x18003a4c8`
- `0x18007ec9a`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c5e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c61a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c70d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c836`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c5e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c61a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c70d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c836`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c662`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c662`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6f4`

## string_xrefs

- `0x18000c552`: `CDlpActionLayoutUsb::CopyFileList`
- `0x18000c9e1`: `CDlpActionLayoutUsb::CopyFileList`
- `0x18000ca3b`: `CDlpActionLayoutUsb::CopyFileList`
- `0x18000c916`: `LayoutUsb: Path [%s] not found!`
- `0x18000c794`: `LayoutUsb: Copying folder [%s] to [%s]...`
- `0x18000c88e`: `LayoutUsb: Copying file [%s] to [%s]...`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDlpActionLayoutUsb::CopyFileList(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  LPCWSTR v8; // r15
  LPCWSTR v9; // rbx
  signed int v10; // edi
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r12
  DWORD FileAttributesW; // r14d
  int v17; // r14d
  DWORD v18; // eax
  BOOL v19; // edi
  HANDLE ProcessHeap; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rbx
  DWORD v24; // r14d
  int v25; // r14d
  int FolderPath; // eax
  __int64 v27; // r9
  __int64 v28; // rcx
  signed int LastError; // eax
  HANDLE v30; // rax
  int v31; // eax
  DWORD v32; // r14d
  int v33; // r14d
  int v34; // eax
  __int64 v35; // rcx
  signed int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  HANDLE v44; // rax
  HANDLE v45; // rax
  __int64 v47; // [rsp+28h] [rbp-89h]
  int v48; // [rsp+30h] [rbp-81h]
  int v49; // [rsp+30h] [rbp-81h]
  LPCWSTR lpFileName; // [rsp+38h] [rbp-79h] BYREF
  LPCWSTR v51; // [rsp+40h] [rbp-71h]
  __int64 v52; // [rsp+48h] [rbp-69h] BYREF
  __int64 v53; // [rsp+58h] [rbp-59h] BYREF
  _QWORD v54[2]; // [rsp+68h] [rbp-49h] BYREF
  int v55; // [rsp+7Ch] [rbp-35h]
  unsigned int (__fastcall *v56)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // [rsp+A0h] [rbp-11h]
  __int64 v57; // [rsp+A8h] [rbp-9h]
  int v58; // [rsp+C8h] [rbp+17h]
  unsigned int v59; // [rsp+120h] [rbp+6Fh]

  v8 = 0;
  v51 = 0;
  v9 = 0;
  lpFileName = 0;
  v53 = 0;
  v52 = 0;
  memset_0(v54, 0, 0x48u);
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = *(_QWORD *)(a1 + 88);
    if ( v11 )
    {
      v48 = -2147024809;
      LODWORD(v47) = 1113;
      goto LABEL_4;
    }
    goto LABEL_86;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = *(_QWORD *)(a1 + 88);
    if ( v11 )
    {
      v48 = -2147024809;
      LODWORD(v47) = 1114;
      goto LABEL_4;
    }
    goto LABEL_86;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    v11 = *(_QWORD *)(a1 + 88);
    if ( v11 )
    {
      v48 = -2147024809;
      LODWORD(v47) = 1115;
      goto LABEL_4;
    }
    goto LABEL_86;
  }
  v10 = 0;
  v14 = 0;
  v59 = 0;
  if ( !*(_DWORD *)(a2 + 4) )
    goto LABEL_86;
  while ( 1 )
  {
    v15 = (int)v14;
    FileAttributesW = GetFileAttributesW(*(LPCWSTR *)(*(_QWORD *)(a2 + 8) + 8LL * (int)v14));
    if ( FileAttributesW == -1 )
      v17 = 0;
    else
      v17 = (FileAttributesW >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v18 = GetFileAttributesW(*(LPCWSTR *)(*(_QWORD *)(a2 + 8) + 8 * v15));
    v19 = v18 != -1 && (v18 & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v17 && !v19 )
    {
      v37 = *(_QWORD *)(a1 + 88);
      if ( v37 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v37,
          2,
          L"LayoutUsb: Path [%s] not found!",
          *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15));
      v10 = -2147024893;
      v11 = *(_QWORD *)(a1 + 88);
      if ( v11 )
      {
        v48 = -2147024893;
        LODWORD(v47) = 1125;
        goto LABEL_4;
      }
      goto LABEL_86;
    }
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      lpFileName = 0;
    }
    v21 = CDlpHelpersT<CEmptyType>::CombinePath(a4, *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8 * v15), (__int64)&lpFileName);
    v10 = v21;
    if ( v21 < 0 )
    {
      v41 = *(_QWORD *)(a1 + 88);
      if ( v41 )
      {
        v49 = v21;
        LODWORD(v47) = 1129;
LABEL_82:
        v42 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v41,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::CopyFileList",
                v47,
                v49);
        v43 = (unsigned int)v42;
        if ( v42 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v42);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v43);
      }
LABEL_85:
      v9 = lpFileName;
      goto LABEL_86;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, &v53, &v52, 0);
    v10 = v22;
    if ( v22 < 0 )
    {
      v41 = *(_QWORD *)(a1 + 88);
      if ( v41 )
      {
        v49 = v22;
        LODWORD(v47) = 1133;
        goto LABEL_82;
      }
      goto LABEL_85;
    }
    v23 = v52;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 752));
    v58 = 1;
    *(_QWORD *)(a1 + 736) = v23;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v10 = 0;
    if ( v58 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 752));
      v58 = 0;
    }
    if ( !v17 )
      break;
    v9 = lpFileName;
    v24 = GetFileAttributesW(lpFileName);
    if ( v24 == -1 )
      v25 = 0;
    else
      v25 = (v24 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v25 )
    {
      FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v9);
      v10 = FolderPath;
      if ( FolderPath < 0 )
      {
        v11 = *(_QWORD *)(a1 + 88);
        if ( !v11 )
          goto LABEL_86;
        v48 = FolderPath;
        LODWORD(v47) = 1143;
        goto LABEL_4;
      }
    }
    memset_0(v54, 0, 0x48u);
    v27 = *(_QWORD *)(a2 + 8);
    v54[0] = *(_QWORD *)(v27 + 8 * v15);
    v54[1] = v9;
    v56 = CDlpActionLayoutUsb::CopyProgressRoutine;
    v57 = a1;
    v55 = 10;
    v28 = *(_QWORD *)(a1 + 88);
    if ( v28 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v28,
        2,
        L"LayoutUsb: Copying folder [%s] to [%s]...",
        *(_QWORD *)(v27 + 8 * v15),
        v9);
    if ( !(unsigned int)CopyDirectoryEx2(v54) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 == -2147023673 )
      {
        v10 = -2147023661;
LABEL_66:
        v11 = *(_QWORD *)(a1 + 88);
        if ( !v11 )
          goto LABEL_86;
        v48 = v10;
        LODWORD(v47) = 1161;
        goto LABEL_4;
      }
      if ( v10 < 0 )
        goto LABEL_66;
    }
LABEL_57:
    v14 = v59 + 1;
    v59 = v14;
    if ( v14 >= *(_DWORD *)(a2 + 4) )
      goto LABEL_86;
  }
  if ( v8 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, (LPVOID)(v8 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v51 = 0;
  }
  v9 = lpFileName;
  v31 = CMiscHelpersT<CEmptyType>::ParseFileName((void *)lpFileName, 0);
  v10 = v31;
  if ( v31 < 0 )
  {
    v38 = *(_QWORD *)(a1 + 88);
    if ( v38 )
    {
      LODWORD(v47) = 1173;
      v39 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v38,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::CopyFileList",
              v47,
              v31);
      v40 = (unsigned int)v39;
      if ( v39 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v39);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v40);
    }
    v8 = v51;
    goto LABEL_86;
  }
  v8 = v51;
  v32 = GetFileAttributesW(v51);
  if ( v32 == -1 )
    v33 = 0;
  else
    v33 = (v32 >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v10 = 0;
  if ( !v33 )
  {
    v34 = CMiscHelpersT<CEmptyType>::CreateFolderPath(v8);
    v10 = v34;
    if ( v34 < 0 )
    {
      v11 = *(_QWORD *)(a1 + 88);
      if ( !v11 )
        goto LABEL_86;
      v48 = v34;
      LODWORD(v47) = 1180;
      goto LABEL_4;
    }
  }
  v35 = *(_QWORD *)(a1 + 88);
  if ( v35 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v35,
      2,
      L"LayoutUsb: Copying file [%s] to [%s]...",
      *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15),
      v9);
  if ( (unsigned int)CopyFileWithAttributesEx2(
                       *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15),
                       v9,
                       8,
                       CDlpActionLayoutUsb::CopyProgressRoutine,
                       a1) )
    goto LABEL_57;
  v36 = GetLastError();
  v10 = v36;
  if ( v36 > 0 )
    v10 = (unsigned __int16)v36 | 0x80070000;
  if ( v10 != -2147023673 )
  {
    if ( v10 < 0 )
      goto LABEL_71;
    goto LABEL_57;
  }
  v10 = -2147023661;
LABEL_71:
  v11 = *(_QWORD *)(a1 + 88);
  if ( !v11 )
    goto LABEL_86;
  v48 = v10;
  LODWORD(v47) = 1195;
LABEL_4:
  v12 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v11,
          4,
          L"%s(%d): Result = 0x%X",
          L"CDlpActionLayoutUsb::CopyFileList",
          v47,
          v48);
  v13 = (unsigned int)v12;
  if ( v12 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
LABEL_86:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v9 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, (LPVOID)(v9 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, (LPVOID)(v8 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c4d8  mov     rax, rsp
0x18000c4db  mov     [rax+8], rbx
0x18000c4df  mov     [rax+20h], r9
0x18000c4e3  mov     [rax+18h], r8
0x18000c4e7  push    rbp
0x18000c4e8  push    rsi
0x18000c4e9  push    rdi
0x18000c4ea  push    r12
0x18000c4ec  push    r13
0x18000c4ee  push    r14
0x18000c4f0  push    r15
0x18000c4f2  lea     rbp, [rax-5Fh]
0x18000c4f6  sub     rsp, 0D0h
0x18000c4fd  mov     rdi, r9
0x18000c500  mov     r14, r8
0x18000c503  mov     r13, rdx
0x18000c506  mov     rsi, rcx
0x18000c509  xor     r15d, r15d
0x18000c50c  mov     [rbp+57h+var_C8], r15
0x18000c510  xor     ebx, ebx
0x18000c512  mov     [rbp+57h+lpFileName], rbx
0x18000c516  mov     [rbp+57h+var_B0], rbx
0x18000c51a  mov     [rbp+57h+var_C0], rbx
0x18000c51e  xor     edx, edx; Val
0x18000c520  lea     r8d, [r15+48h]; Size
0x18000c524  lea     rcx, [rbp+57h+var_A0]; void *
0x18000c528  call    memset_0
0x18000c52d  test    r13, r13
0x18000c530  jnz     short loc_18000C57F
0x18000c532  mov     eax, 80070057h
0x18000c537  mov     edi, eax
0x18000c539  mov     rcx, [rsi+58h]
0x18000c53d  test    rcx, rcx
0x18000c540  jz      loc_18000CA67
0x18000c546  mov     [rsp+28h], eax
0x18000c54a  mov     dword ptr [rsp+100h+var_E0], 459h
0x18000c552  lea     r9, aCdlpactionlayo_4; "CDlpActionLayoutUsb::CopyFileList"
0x18000c559  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000c560  mov     edx, 4
0x18000c565  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c56a  test    eax, eax
0x18000c56c  mov     ecx, eax
0x18000c56e  jns     short loc_18000C575
0x18000c570  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c575  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c57a  jmp     loc_18000CA67
0x18000c57f  test    r14, r14
0x18000c582  jnz     short loc_18000C5A6
0x18000c584  mov     eax, 80070057h
0x18000c589  mov     edi, eax
0x18000c58b  mov     rcx, [rsi+58h]
0x18000c58f  test    rcx, rcx
0x18000c592  jz      loc_18000CA67
0x18000c598  mov     [rsp+28h], eax
0x18000c59c  mov     dword ptr [rsp+100h+var_E0], 45Ah
0x18000c5a4  jmp     short loc_18000C552
0x18000c5a6  test    rdi, rdi
0x18000c5a9  jnz     short loc_18000C5CD
0x18000c5ab  mov     eax, 80070057h
0x18000c5b0  mov     edi, eax
0x18000c5b2  mov     rcx, [rsi+58h]
0x18000c5b6  test    rcx, rcx
0x18000c5b9  jz      loc_18000CA67
0x18000c5bf  mov     [rsp+28h], eax
0x18000c5c3  mov     dword ptr [rsp+100h+var_E0], 45Bh
0x18000c5cb  jmp     short loc_18000C552
0x18000c5cd  xor     edi, edi
0x18000c5cf  xor     eax, eax
0x18000c5d1  mov     [rbp+57h+arg_8], eax
0x18000c5d4  cmp     [r13+4], eax
0x18000c5d8  jbe     loc_18000CA67
0x18000c5de  mov     rcx, [r13+8]
0x18000c5e2  movsxd  r12, eax
0x18000c5e5  mov     rcx, [rcx+r12*8]; lpFileName
0x18000c5e9  call    cs:__imp_GetFileAttributesW
0x18000c5ef  mov     r14d, eax
0x18000c5f2  cmp     eax, 0FFFFFFFFh
0x18000c5f5  jz      short loc_18000C601
0x18000c5f7  shr     r14d, 4
0x18000c5fb  and     r14d, 1
0x18000c5ff  jmp     short loc_18000C604
0x18000c601  xor     r14d, r14d
0x18000c604  xor     ecx, ecx
0x18000c606  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c60b  xor     ecx, ecx
0x18000c60d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c612  mov     rax, [r13+8]
0x18000c616  mov     rcx, [rax+r12*8]; lpFileName
0x18000c61a  call    cs:__imp_GetFileAttributesW
0x18000c620  mov     edi, eax
0x18000c622  cmp     eax, 0FFFFFFFFh
0x18000c625  jz      short loc_18000C631
0x18000c627  shr     edi, 4
0x18000c62a  not     edi
0x18000c62c  and     edi, 1
0x18000c62f  jmp     short loc_18000C633
0x18000c631  xor     edi, edi
0x18000c633  xor     ecx, ecx
0x18000c635  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c63a  xor     ecx, ecx
0x18000c63c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c641  test    r14d, r14d
0x18000c644  jnz     short loc_18000C64E
0x18000c646  test    edi, edi
0x18000c648  jz      loc_18000C905
0x18000c64e  test    rbx, rbx
0x18000c651  jz      short loc_18000C677
0x18000c653  call    cs:__imp_GetProcessHeap
0x18000c659  mov     rcx, rax; hHeap
0x18000c65c  lea     r8, [rbx-4]; lpMem
0x18000c660  xor     edx, edx; dwFlags
0x18000c662  call    cs:__imp_HeapFree
0x18000c668  xor     ecx, ecx
0x18000c66a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c66f  mov     [rbp+57h+lpFileName], 0
0x18000c677  mov     rax, [rbp+57h+arg_10]
0x18000c67b  mov     rax, [rax+8]
0x18000c67f  lea     r8, [rbp+57h+lpFileName]
0x18000c683  mov     rdx, [rax+r12*8]
0x18000c687  mov     rcx, [rbp+57h+arg_18]
0x18000c68b  call    ?CombinePath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBG0PEAPEAG@Z; CDlpHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort * *)
0x18000c690  mov     edi, eax
0x18000c692  test    eax, eax
0x18000c694  js      loc_18000CA26
0x18000c69a  mov     rax, [rsi]
0x18000c69d  xor     r9d, r9d
0x18000c6a0  lea     r8, [rbp+57h+var_C0]
0x18000c6a4  lea     rdx, [rbp+57h+var_B0]
0x18000c6a8  mov     rcx, rsi
0x18000c6ab  mov     rax, [rax+48h]
0x18000c6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b4  mov     edi, eax
0x18000c6b6  test    eax, eax
0x18000c6b8  js      loc_18000CA0F
0x18000c6be  mov     rbx, [rbp+57h+var_C0]
0x18000c6c2  lea     rcx, [rsi+2F0h]; lpCriticalSection
0x18000c6c9  call    cs:__imp_EnterCriticalSection
0x18000c6cf  mov     [rbp+57h+var_40], 1
0x18000c6d6  mov     [rsi+2E0h], rbx
0x18000c6dd  xor     ecx, ecx
0x18000c6df  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c6e4  mov     eax, [rbp+57h+var_40]
0x18000c6e7  xor     edi, edi
0x18000c6e9  test    eax, eax
0x18000c6eb  jz      short loc_18000C6FD
0x18000c6ed  lea     rcx, [rsi+2F0h]; lpCriticalSection
0x18000c6f4  call    cs:__imp_LeaveCriticalSection
0x18000c6fa  mov     [rbp+57h+var_40], edi
0x18000c6fd  test    r14d, r14d
0x18000c700  jz      loc_18000C7E4
0x18000c706  mov     rbx, [rbp+57h+lpFileName]
0x18000c70a  mov     rcx, rbx; lpFileName
0x18000c70d  call    cs:__imp_GetFileAttributesW
0x18000c713  mov     r14d, eax
0x18000c716  cmp     eax, 0FFFFFFFFh
0x18000c719  jz      short loc_18000C725
0x18000c71b  shr     r14d, 4
0x18000c71f  and     r14d, 1
0x18000c723  jmp     short loc_18000C728
0x18000c725  mov     r14d, edi
0x18000c728  xor     ecx, ecx
0x18000c72a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c72f  xor     ecx, ecx
0x18000c731  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c736  test    r14d, r14d
0x18000c739  jnz     short loc_18000C74D
0x18000c73b  mov     rcx, rbx
0x18000c73e  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000c743  mov     edi, eax
0x18000c745  test    eax, eax
0x18000c747  js      loc_18000C94A
0x18000c74d  xor     edx, edx; Val
0x18000c74f  lea     r8d, [rdx+48h]; Size
0x18000c753  lea     rcx, [rbp+57h+var_A0]; void *
0x18000c757  call    memset_0
0x18000c75c  mov     r9, [r13+8]
0x18000c760  mov     rax, [r9+r12*8]
0x18000c764  mov     [rbp+57h+var_A0], rax
0x18000c768  mov     [rbp+57h+var_98], rbx
0x18000c76c  lea     rax, ?CopyProgressRoutine@CDlpActionLayoutUsb@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; CDlpActionLayoutUsb::CopyProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x18000c773  mov     [rbp+57h+var_68], rax
0x18000c777  mov     [rbp+57h+var_60], rsi
0x18000c77b  mov     [rbp+57h+var_8C], 0Ah
0x18000c782  mov     rcx, [rsi+58h]
0x18000c786  test    rcx, rcx
0x18000c789  jz      short loc_18000C7A5
0x18000c78b  mov     [rsp+100h+var_E0], rbx
0x18000c790  mov     r9, [r9+r12*8]
0x18000c794  lea     r8, aLayoutusbCopyi; "LayoutUsb: Copying folder [%s] to [%s]."...
0x18000c79b  mov     edx, 2
0x18000c7a0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c7a5  lea     rcx, [rbp+57h+var_A0]
0x18000c7a9  call    CopyDirectoryEx2
0x18000c7ae  test    eax, eax
0x18000c7b0  jnz     loc_18000C8EE
0x18000c7b6  call    cs:__imp_GetLastError
0x18000c7bc  mov     edi, eax
0x18000c7be  test    eax, eax
0x18000c7c0  jle     short loc_18000C7CB
0x18000c7c2  movzx   edi, ax
0x18000c7c5  or      edi, 80070000h
0x18000c7cb  cmp     edi, 800704C7h
0x18000c7d1  jz      loc_18000C968
0x18000c7d7  test    edi, edi
0x18000c7d9  js      loc_18000C96D
0x18000c7df  jmp     loc_18000C8EE
0x18000c7e4  test    r15, r15
0x18000c7e7  jz      short loc_18000C809
0x18000c7e9  call    cs:__imp_GetProcessHeap
0x18000c7ef  mov     rcx, rax; hHeap
0x18000c7f2  lea     r8, [r15-4]; lpMem
0x18000c7f6  xor     edx, edx; dwFlags
0x18000c7f8  call    cs:__imp_HeapFree
0x18000c7fe  xor     ecx, ecx
0x18000c800  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c805  mov     [rbp+57h+var_C8], rdi
0x18000c809  mov     rbx, [rbp+57h+lpFileName]
0x18000c80d  mov     [rsp+100h+var_E0], rdi; __int64
0x18000c812  xor     r9d, r9d
0x18000c815  lea     r8, [rbp+57h+var_C8]
0x18000c819  lea     rdx, [rbp+57h+var_B8]
0x18000c81d  mov     rcx, rbx; Src
0x18000c820  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x18000c825  mov     edi, eax
0x18000c827  test    eax, eax
0x18000c829  js      loc_18000C9CC
0x18000c82f  mov     r15, [rbp+57h+var_C8]
0x18000c833  mov     rcx, r15; lpFileName
0x18000c836  call    cs:__imp_GetFileAttributesW
0x18000c83c  mov     r14d, eax
0x18000c83f  cmp     eax, 0FFFFFFFFh
0x18000c842  jz      short loc_18000C84E
0x18000c844  shr     r14d, 4
0x18000c848  and     r14d, 1
0x18000c84c  jmp     short loc_18000C851
0x18000c84e  xor     r14d, r14d
0x18000c851  xor     ecx, ecx
0x18000c853  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c858  xor     ecx, ecx
0x18000c85a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c85f  xor     edi, edi
0x18000c861  test    r14d, r14d
0x18000c864  jnz     short loc_18000C878
0x18000c866  mov     rcx, r15
0x18000c869  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000c86e  mov     edi, eax
0x18000c870  test    eax, eax
0x18000c872  js      loc_18000C98B
0x18000c878  mov     rcx, [rsi+58h]
0x18000c87c  test    rcx, rcx
0x18000c87f  jz      short loc_18000C89F
0x18000c881  mov     rax, [r13+8]
0x18000c885  mov     [rsp+100h+var_E0], rbx
0x18000c88a  mov     r9, [rax+r12*8]
0x18000c88e  lea     r8, aLayoutusbCopyi_0; "LayoutUsb: Copying file [%s] to [%s]..."
0x18000c895  mov     edx, 2
0x18000c89a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c89f  mov     rax, [r13+8]
0x18000c8a3  mov     [rsp+100h+var_E0], rsi
0x18000c8a8  lea     r9, ?CopyProgressRoutine@CDlpActionLayoutUsb@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; CDlpActionLayoutUsb::CopyProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x18000c8af  mov     r8d, 8
0x18000c8b5  mov     rdx, rbx
0x18000c8b8  mov     rcx, [rax+r12*8]
0x18000c8bc  call    CopyFileWithAttributesEx2
0x18000c8c1  test    eax, eax
0x18000c8c3  jnz     short loc_18000C8EE
0x18000c8c5  call    cs:__imp_GetLastError
0x18000c8cb  mov     edi, eax
0x18000c8cd  test    eax, eax
0x18000c8cf  jle     short loc_18000C8DA
0x18000c8d1  movzx   edi, ax
0x18000c8d4  or      edi, 80070000h
0x18000c8da  cmp     edi, 800704C7h
0x18000c8e0  jz      loc_18000C9A9
0x18000c8e6  test    edi, edi
0x18000c8e8  js      loc_18000C9AE
0x18000c8ee  mov     eax, [rbp+57h+arg_8]
0x18000c8f1  inc     eax
0x18000c8f3  mov     [rbp+57h+arg_8], eax
0x18000c8f6  cmp     eax, [r13+4]
0x18000c8fa  jb      loc_18000C5DE
0x18000c900  jmp     loc_18000CA67
0x18000c905  mov     rcx, [rsi+58h]
0x18000c909  test    rcx, rcx
0x18000c90c  jz      short loc_18000C927
0x18000c90e  mov     rax, [r13+8]
0x18000c912  mov     r9, [rax+r12*8]
0x18000c916  lea     r8, aLayoutusbPathS; "LayoutUsb: Path [%s] not found!"
0x18000c91d  mov     edx, 2
0x18000c922  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c927  mov     edi, 80070003h
0x18000c92c  mov     rcx, [rsi+58h]
0x18000c930  test    rcx, rcx
0x18000c933  jz      loc_18000CA67
0x18000c939  mov     [rsp+28h], edi
0x18000c93d  mov     dword ptr [rsp+100h+var_E0], 465h
0x18000c945  jmp     loc_18000C552
0x18000c94a  mov     rcx, [rsi+58h]
0x18000c94e  test    rcx, rcx
0x18000c951  jz      loc_18000CA67
  ... truncated ...
```
