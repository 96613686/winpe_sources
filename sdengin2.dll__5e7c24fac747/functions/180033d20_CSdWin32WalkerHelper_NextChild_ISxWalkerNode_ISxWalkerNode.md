# CSdWin32WalkerHelper::NextChild(ISxWalkerNode *,ISxWalkerNode * *)

- ea: `0x180033d20`
- end: `0x180034528`
- name: `?NextChild@CSdWin32WalkerHelper@@UEAAJPEAUISxWalkerNode@@PEAPEAU2@@Z`
- size: `2056`
- prototype: `__int64 __fastcall(CSdWin32WalkerHelper *__hidden this, struct ISxWalkerNode *, struct ISxWalkerNode **)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003430`
- `0x180003444`
- `0x180003b60`
- `0x180003b74`
- `0x180008240`
- `0x180009c88`
- `0x180014394`
- `0x180024098`
- `0x180032b18`
- `0x180033d20`
- `0x180034b08`
- `0x180060e98`
- `0x180060f60`
- `0x1800612f0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088b44`
- `0x18008f5d0`
- `0x18008f660`
- `0x180099bb0`
- `0x18009a22c`
- `0x18009a24c`
- `0x18009a378`
- `0x18009a448`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x18003428a`
- `ntdll!NtQueryDirectoryFile` at `0x18003428a`
- `KERNEL32!VirtualAlloc` at `0x180034200`
- `KERNEL32!VirtualAlloc` at `0x180034200`
- `KERNEL32!CreateFileW` at `0x180034150`
- `KERNEL32!CreateFileW` at `0x180034150`
- `KERNEL32!CloseHandle` at `0x1800341d1`
- `KERNEL32!CloseHandle` at `0x1800342c8`
- `KERNEL32!CloseHandle` at `0x1800344d1`
- `KERNEL32!CloseHandle` at `0x1800341d1`
- `KERNEL32!CloseHandle` at `0x1800342c8`
- `KERNEL32!CloseHandle` at `0x1800344d1`
- `ole32!CoTaskMemFree` at `0x180033ff5`
- `ole32!CoTaskMemFree` at `0x18003447f`
- `ole32!CoTaskMemFree` at `0x180034489`
- `ole32!CoTaskMemFree` at `0x180033ff5`
- `ole32!CoTaskMemFree` at `0x18003447f`
- `ole32!CoTaskMemFree` at `0x180034489`

## pseudocode

```c
__int64 __fastcall CSdWin32WalkerHelper::NextChild(
        CSdWin32WalkerHelper *this,
        struct ISxWalkerNode *a2,
        struct ISxWalkerNode **a3)
{
  __int64 FileW; // rbx
  __int16 v7; // ax
  int TreeNode; // ecx
  void *v9; // rdi
  int v10; // eax
  __int16 v11; // ax
  HANDLE *v12; // r14
  __int64 v13; // rcx
  int LastFailureAsHRESULT; // eax
  int v15; // esi
  HANDLE v16; // rcx
  LPVOID v17; // rcx
  int v18; // r13d
  void *v19; // rcx
  unsigned int v20; // eax
  unsigned int *v21; // rcx
  unsigned __int64 v22; // rax
  _DWORD *v23; // rdx
  _DWORD *v24; // rax
  char *v25; // rsi
  CSdWin32WalkerHelper *v26; // rcx
  __int16 v27; // ax
  unsigned int v28; // edi
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *hTemplateFileb; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *FileInformationClass; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *FileInformationClassa; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *FileInformationClassb; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *ReturnSingleEntry; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *ReturnSingleEntrya; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *ReturnSingleEntryb; // [rsp+40h] [rbp-C0h]
  PUNICODE_STRING FileName; // [rsp+48h] [rbp-B8h]
  PUNICODE_STRING FileNamea; // [rsp+48h] [rbp-B8h]
  PUNICODE_STRING FileNameb; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *RestartScan; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *RestartScana; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *RestartScanb; // [rsp+50h] [rbp-B0h]
  int DirectoryName; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v46; // [rsp+64h] [rbp-9Ch]
  __int16 v47; // [rsp+66h] [rbp-9Ah]
  int v48; // [rsp+98h] [rbp-68h] BYREF
  struct ISdBackupNode *v49; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v50; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  struct ISdBackupNode *v52; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v53[2]; // [rsp+C0h] [rbp-40h] BYREF
  CSdPathTreeNode *v54; // [rsp+D0h] [rbp-30h] BYREF
  CSdPathTreeNode *v55; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v56[2]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v58[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v59[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v60[2]; // [rsp+120h] [rbp+20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+130h] [rbp+30h] BYREF
  _WORD v62[28]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v63[552]; // [rsp+178h] [rbp+78h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DirectoryName, "CSdWin32WalkerHelper::NextChild", 714, 1);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v52);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v49);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  FileW = -1;
  IoStatusBlock = 0;
  v50 = 0;
  memset_0(v62, 0, 0x260u);
  v48 = 0;
  v56[0] = qword_1800E8530;
  v56[1] = 0;
  v60[0] = (unsigned __int16 *)qword_1800E8530;
  v60[1] = 0;
  v55 = 0;
  v59[0] = (unsigned __int16 *)qword_1800E8530;
  v59[1] = 0;
  v58[0] = qword_1800E8530;
  v58[1] = 0;
  v53[0] = (unsigned __int16 *)qword_1800E8530;
  v53[1] = 0;
  v54 = 0;
  pv = 0;
  if ( a3 )
    *a3 = 0;
  v7 = 742;
  if ( !a2 || (v46 = 742, v7 = 743, !a3) )
  {
    DirectoryName = -2147024809;
    goto LABEL_5;
  }
  DirectoryName = 0;
  v46 = 743;
  DirectoryName = (**(__int64 (__fastcall ***)(struct ISxWalkerNode *, GUID *, struct ISdBackupNode **))a2)(
                    a2,
                    &IID_ISdBackupNode,
                    &v52);
  v7 = 745;
  if ( DirectoryName < 0 )
    goto LABEL_5;
  v46 = 745;
  DirectoryName = (*(__int64 (__fastcall **)(struct ISdBackupNode *, unsigned __int16 **))(*(_QWORD *)v52 + 80LL))(
                    v52,
                    &v50);
  v7 = 746;
  if ( DirectoryName < 0 )
    goto LABEL_5;
  v46 = 746;
  DirectoryName = CBsString::Set((CBsString *)v53, v50);
  v7 = 747;
  if ( DirectoryName < 0 )
    goto LABEL_5;
  v46 = 747;
  CBsString::TrimLeft((CBsString *)v53, L"\\");
  DirectoryName = CBsString::SetPath(
                    (CBsString *)v56,
                    *(const unsigned __int16 **)(*((_QWORD *)this + 6) + 64LL),
                    v53[0],
                    0,
                    0,
                    0,
                    hTemplateFile,
                    FileInformationClass,
                    ReturnSingleEntry,
                    &FileName->Length,
                    RestartScan);
  v7 = 749;
  if ( DirectoryName < 0 )
    goto LABEL_5;
  v46 = 749;
  DirectoryName = CBsString::SetPath(
                    (CBsString *)v60,
                    *(const unsigned __int16 **)(*((_QWORD *)this + 6) + 80LL),
                    v53[0],
                    0,
                    0,
                    0,
                    hTemplateFilea,
                    FileInformationClassa,
                    ReturnSingleEntrya,
                    &FileNamea->Length,
                    RestartScana);
  v7 = 750;
  if ( DirectoryName < 0 )
    goto LABEL_5;
  v46 = 750;
  TreeNode = CSdPathTree::GetTreeNode(*((CSdPathTree **)this + 11), (struct CBsString *)v56, &v48, &v54);
  DirectoryName = TreeNode;
  v7 = 751;
  if ( TreeNode < 0 )
    goto LABEL_5;
  v46 = 751;
  if ( TreeNode )
  {
    if ( !v48 )
    {
      v11 = 777;
      goto LABEL_90;
    }
  }
  else if ( !v48 )
  {
    v9 = pv;
    while ( 1 )
    {
      v10 = CSdPathTreeNode::NextChild(v54, &v55);
      DirectoryName = v10;
      if ( v10 < 0 )
      {
        v47 = 914;
        goto LABEL_92;
      }
      v46 = 914;
      if ( v10 )
      {
        v11 = 942;
        goto LABEL_90;
      }
      DirectoryName = CSdPathTreeNode::GetDirectoryName(v55, (struct CBsString *)v59);
      v7 = 917;
      if ( DirectoryName < 0 )
        goto LABEL_5;
      v46 = 917;
      DirectoryName = CBsString::SetPath(
                        (CBsString *)v58,
                        v60[0],
                        v59[0],
                        0,
                        0,
                        0,
                        hTemplateFileb,
                        FileInformationClassb,
                        ReturnSingleEntryb,
                        &FileNameb->Length,
                        RestartScanb);
      v7 = 918;
      if ( DirectoryName < 0 )
        goto LABEL_5;
      v46 = 918;
      CoTaskMemFree(v9);
      pv = 0;
      CBsString::Detach((CBsString *)v58, (unsigned __int16 **)&pv);
      v9 = pv;
      DirectoryName = SdGetFindData((LPCWSTR)pv, (struct _SX_FIND_DATA *)v62);
      if ( DirectoryName < 0 )
      {
        v47 = 923;
        goto LABEL_92;
      }
      v46 = 923;
      if ( (v62[0] & 0x400) == 0 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids, v9);
    }
    ATL::CComPtr<ISdBackupSetRecord>::operator=((struct IUnknown **)&v49, 0);
    DirectoryName = CSdBackupNode::CreateInstance(v52, (struct _SX_FIND_DATA *)v62, &v49);
    if ( DirectoryName < 0 )
    {
      v7 = 934;
      goto LABEL_5;
    }
    *a3 = (struct ISxWalkerNode *)ATL::CComPtrBase<ISdMediaRecord>::Detach(&v49);
    DirectoryName = 0;
    v11 = 937;
    goto LABEL_91;
  }
  v12 = (HANDLE *)((char *)this + 56);
  if ( ((*((_QWORD *)this + 7) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_47;
  DirectoryName = CBsString::Set(
                    (CBsString *)lpFileName,
                    *(const unsigned __int16 **)(*((_QWORD *)this + 6) + 80LL),
                    v50);
  v7 = 785;
  if ( DirectoryName < 0 )
  {
LABEL_5:
    v47 = v7;
    goto LABEL_92;
  }
  v46 = 785;
  FileW = (__int64)CreateFileW(lpFileName[0], 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_42:
    v16 = *v12;
    if ( *v12 == (HANDLE)-1LL )
    {
      if ( this == (CSdWin32WalkerHelper *)-56LL )
        goto LABEL_47;
    }
    else if ( v16 )
    {
      CloseHandle(v16);
    }
    *v12 = (HANDLE)FileW;
    FileW = -1;
LABEL_47:
    if ( !*((_QWORD *)this + 8) )
    {
      v17 = VirtualAlloc(0, 0x40000u, 0x1000u, 4u);
      *((_QWORD *)this + 8) = v17;
      v7 = 817;
      if ( !v17 )
      {
        DirectoryName = -2147024882;
        goto LABEL_5;
      }
      DirectoryName = 0;
      v46 = 817;
      *((_QWORD *)this + 9) = v17;
      *((_DWORD *)this + 20) = 0x40000;
    }
    v18 = v56[0];
    while ( 1 )
    {
      do
      {
        v19 = (void *)*((_QWORD *)this + 8);
        if ( v19 == *((void **)this + 9) )
        {
          v20 = NtQueryDirectoryFile(
                  *v12,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  v19,
                  *((_DWORD *)this + 20),
                  FileBothDirectoryInformation,
                  0,
                  &CSdWin32WalkerHelper::s_ustrFileMask,
                  0);
          if ( v20 == -2147483643 || v20 == -1073741789 || v20 == -1073741820 )
          {
            v21 = (unsigned int *)*((_QWORD *)this + 8);
            v22 = *v21;
            if ( (_DWORD)v22 )
            {
              do
              {
                v23 = v21;
                v21 += v22 >> 2;
                v22 = *v21;
              }
              while ( (_DWORD)v22 );
              if ( v23 )
                *v23 = 0;
            }
            v20 = 0;
          }
          else if ( v20 == -2147483642 || v20 == -1073741809 )
          {
            *((_QWORD *)this + 9) = *((_QWORD *)this + 8);
            if ( (char *)*v12 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              CloseHandle(*v12);
              *v12 = (HANDLE)-1LL;
            }
            v11 = 861;
            goto LABEL_90;
          }
          DirectoryName = HRESULTFromNTSTATUS(v20);
          if ( DirectoryName < 0 )
          {
            v47 = 864;
            goto LABEL_92;
          }
          v46 = 864;
        }
        v24 = (_DWORD *)*((_QWORD *)this + 9);
        if ( *v24 )
          v25 = (char *)v24 + (unsigned int)*v24;
        else
          v25 = (char *)*((_QWORD *)this + 8);
        *((_QWORD *)this + 9) = v25;
        if ( ATL::CComPtrBase<ISdAsyncPriv>::operator!=((_QWORD *)this + 5, 0) )
        {
          DirectoryName = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v26 + 160LL))(*(_QWORD *)v26, 1);
          v27 = 881;
          if ( DirectoryName < 0 )
            goto LABEL_85;
          v46 = 881;
        }
      }
      while ( *((_WORD *)v25 + 47) == 46
           && (*((_DWORD *)v25 + 15) == 2 || *((_DWORD *)v25 + 15) == 4 && *((_WORD *)v25 + 48) == 46) );
      DirectoryName = CSdWin32WalkerHelper::_GetFindData(
                        v26,
                        *(const unsigned __int16 **)(*((_QWORD *)this + 6) + 80LL),
                        v50,
                        (struct _FILE_BOTH_DIR_INFORMATION *)v25,
                        (struct _SX_FIND_DATA *)v62);
      v27 = 892;
      if ( DirectoryName < 0 )
      {
LABEL_85:
        v47 = v27;
        goto LABEL_92;
      }
      v46 = 892;
      if ( (v62[0] & 0x400) == 0 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids,
          v18,
          (__int64)v63);
    }
    ATL::CComPtr<ISdBackupSetRecord>::operator=((struct IUnknown **)&v49, 0);
    DirectoryName = CSdBackupNode::CreateInstance(v52, (struct _SX_FIND_DATA *)v62, &v49);
    if ( DirectoryName < 0 )
    {
      v7 = 902;
      goto LABEL_5;
    }
    *a3 = (struct ISxWalkerNode *)ATL::CComPtrBase<ISdMediaRecord>::Detach(&v49);
    DirectoryName = 0;
    v11 = 906;
    goto LABEL_91;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
  v15 = LastFailureAsHRESULT;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids,
      lpFileName[0],
      LastFailureAsHRESULT);
  if ( !*((_DWORD *)this + 21) )
  {
    DirectoryName = v15;
    v7 = 808;
    if ( v15 >= 0 )
    {
      v46 = 808;
      goto LABEL_42;
    }
    goto LABEL_5;
  }
  v11 = 805;
LABEL_90:
  DirectoryName = 1;
LABEL_91:
  v46 = v11;
LABEL_92:
  CoTaskMemFree(pv);
  CoTaskMemFree(v50);
  v50 = 0;
  v28 = DirectoryName;
  CBsString::_Release((CBsString *)v53);
  CBsString::_Release((CBsString *)v58);
  CBsString::_Release((CBsString *)v59);
  CBsString::_Release((CBsString *)v60);
  CBsString::_Release((CBsString *)v56);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)lpFileName);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v49);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v52);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DirectoryName);
  return v28;
}

```

## disassembly

```asm
0x180033d20  mov     [rsp-8+arg_18], rbx
0x180033d25  push    rbp
0x180033d26  push    rsi
0x180033d27  push    rdi
0x180033d28  push    r12
0x180033d2a  push    r13
0x180033d2c  push    r14
0x180033d2e  push    r15
0x180033d30  lea     rbp, [rsp-2B0h]
0x180033d38  sub     rsp, 3B0h
0x180033d3f  mov     rax, cs:__security_cookie
0x180033d46  xor     rax, rsp
0x180033d49  mov     [rbp+2E0h+var_40], rax
0x180033d50  mov     r15, r8
0x180033d53  mov     rsi, rdx
0x180033d56  mov     rdi, rcx
0x180033d59  mov     r9d, 1; unsigned __int16
0x180033d5f  mov     r8d, 2CAh; unsigned __int16
0x180033d65  lea     rdx, aCsdwin32walker_3; "CSdWin32WalkerHelper::NextChild"
0x180033d6c  lea     rcx, [rsp+3E0h+var_380]; this
0x180033d71  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180033d76  lea     rcx, [rbp+2E0h+var_328]; void *
0x180033d7a  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180033d7f  lea     rcx, [rbp+2E0h+var_340]; void *
0x180033d83  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180033d88  lea     r14, qword_1800E8530
0x180033d8f  mov     [rbp+2E0h+lpFileName], r14
0x180033d93  xor     r13d, r13d
0x180033d96  mov     [rbp+2E0h+var_2E8], r13
0x180033d9a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180033d9e  xorps   xmm0, xmm0
0x180033da1  movups  xmmword ptr [rbp+2E0h+IoStatusBlock], xmm0
0x180033da5  mov     [rbp+2E0h+var_338], r13
0x180033da9  xor     edx, edx; Val
0x180033dab  mov     r8d, 260h; Size
0x180033db1  lea     rcx, [rbp+2E0h+var_2A0]; void *
0x180033db5  call    memset_0
0x180033dba  mov     [rbp+2E0h+var_348], r13d
0x180033dbe  mov     [rbp+2E0h+var_300], r14
0x180033dc2  mov     [rbp+2E0h+var_2F8], r13
0x180033dc6  mov     [rbp+2E0h+var_2C0], r14
0x180033dca  mov     [rbp+2E0h+var_2B8], r13
0x180033dce  mov     [rbp+2E0h+var_308], r13
0x180033dd2  mov     [rbp+2E0h+var_2D0], r14
0x180033dd6  mov     [rbp+2E0h+var_2C8], r13
0x180033dda  mov     [rbp+2E0h+var_2E0], r14
0x180033dde  mov     [rbp+2E0h+var_2D8], r13
0x180033de2  mov     [rbp+2E0h+var_320], r14
0x180033de6  mov     [rbp+2E0h+var_318], r13
0x180033dea  mov     [rbp+2E0h+var_310], r13
0x180033dee  mov     [rbp+2E0h+pv], r13
0x180033df2  test    r15, r15
0x180033df5  jz      short loc_180033DFA
0x180033df7  mov     [r15], r13
0x180033dfa  mov     eax, 2E6h
0x180033dff  test    rsi, rsi
0x180033e02  jnz     short loc_180033E16
0x180033e04  mov     [rsp+3E0h+var_380], 80070057h
0x180033e0c  mov     [rsp+3E0h+var_37A], ax
0x180033e11  jmp     loc_18003447B
0x180033e16  mov     [rsp+3E0h+var_37C], ax
0x180033e1b  mov     eax, 2E7h
0x180033e20  test    r15, r15
0x180033e23  jz      short loc_180033E04
0x180033e25  mov     [rsp+3E0h+var_380], r13d
0x180033e2a  mov     [rsp+3E0h+var_37C], ax
0x180033e2f  mov     rax, [rsi]
0x180033e32  lea     r8, [rbp+2E0h+var_328]
0x180033e36  lea     rdx, IID_ISdBackupNode
0x180033e3d  mov     rcx, rsi
0x180033e40  mov     rax, [rax]
0x180033e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e48  mov     [rsp+3E0h+var_380], eax
0x180033e4c  test    eax, eax
0x180033e4e  mov     eax, 2E9h
0x180033e53  js      short loc_180033E0C
0x180033e55  mov     [rsp+3E0h+var_37C], ax
0x180033e5a  mov     rcx, [rbp+2E0h+var_328]
0x180033e5e  mov     rax, [rcx]
0x180033e61  lea     rdx, [rbp+2E0h+var_338]
0x180033e65  mov     rax, [rax+50h]
0x180033e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e6e  mov     [rsp+3E0h+var_380], eax
0x180033e72  test    eax, eax
0x180033e74  mov     eax, 2EAh
0x180033e79  js      short loc_180033E0C
0x180033e7b  mov     [rsp+3E0h+var_37C], ax
0x180033e80  mov     rdx, [rbp+2E0h+var_338]; unsigned __int16 *
0x180033e84  lea     rcx, [rbp+2E0h+var_320]; this
0x180033e88  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180033e8d  mov     [rsp+3E0h+var_380], eax
0x180033e91  test    eax, eax
0x180033e93  mov     eax, 2EBh
0x180033e98  js      loc_180033E0C
0x180033e9e  mov     [rsp+3E0h+var_37C], ax
0x180033ea3  lea     rdx, Str; "\\"
0x180033eaa  lea     rcx, [rbp+2E0h+var_320]; this
0x180033eae  call    ?TrimLeft@CBsString@@QEAAXPEBG@Z; CBsString::TrimLeft(ushort const *)
0x180033eb3  mov     rdx, [rdi+30h]
0x180033eb7  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180033ebc  mov     qword ptr [rsp+3E0h+dwCreationDisposition], r13; unsigned __int16 *
0x180033ec1  xor     r9d, r9d; unsigned __int16 *
0x180033ec4  mov     r8, [rbp+2E0h+var_320]; unsigned __int16 *
0x180033ec8  mov     rdx, [rdx+40h]; unsigned __int16 *
0x180033ecc  lea     rcx, [rbp+2E0h+var_300]; this
0x180033ed0  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180033ed5  mov     [rsp+3E0h+var_380], eax
0x180033ed9  test    eax, eax
0x180033edb  mov     eax, 2EDh
0x180033ee0  js      loc_180033E0C
0x180033ee6  mov     [rsp+3E0h+var_37C], ax
0x180033eeb  mov     rdx, [rdi+30h]
0x180033eef  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180033ef4  mov     qword ptr [rsp+3E0h+dwCreationDisposition], r13; unsigned __int16 *
0x180033ef9  xor     r9d, r9d; unsigned __int16 *
0x180033efc  mov     r8, [rbp+2E0h+var_320]; unsigned __int16 *
0x180033f00  mov     rdx, [rdx+50h]; unsigned __int16 *
0x180033f04  lea     rcx, [rbp+2E0h+var_2C0]; this
0x180033f08  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180033f0d  mov     [rsp+3E0h+var_380], eax
0x180033f11  test    eax, eax
0x180033f13  mov     eax, 2EEh
0x180033f18  js      loc_180033E0C
0x180033f1e  mov     [rsp+3E0h+var_37C], ax
0x180033f23  lea     r9, [rbp+2E0h+var_310]; struct CSdPathTreeNode **
0x180033f27  lea     r8, [rbp+2E0h+var_348]; int *
0x180033f2b  lea     rdx, [rbp+2E0h+var_300]; struct CBsString *
0x180033f2f  mov     rcx, [rdi+58h]; this
0x180033f33  call    ?GetTreeNode@CSdPathTree@@QEAAJPEAVCBsString@@PEAHPEAPEAVCSdPathTreeNode@@@Z; CSdPathTree::GetTreeNode(CBsString *,int *,CSdPathTreeNode * *)
0x180033f38  mov     ecx, eax
0x180033f3a  mov     [rsp+3E0h+var_380], eax
0x180033f3e  test    eax, eax
0x180033f40  mov     eax, 2EFh
0x180033f45  js      loc_180033E0C
0x180033f4b  mov     [rsp+3E0h+var_37C], ax
0x180033f50  test    ecx, ecx
0x180033f52  jnz     loc_1800340D9
0x180033f58  cmp     [rbp+2E0h+var_348], r13d
0x180033f5c  jnz     loc_1800340E3
0x180033f62  mov     esi, 39Bh
0x180033f67  lea     r14d, [rsi-9]
0x180033f6b  lea     r12, WPP_GLOBAL_Control
0x180033f72  mov     rdi, [rbp+2E0h+pv]
0x180033f76  lea     rdx, [rbp+2E0h+var_308]; struct CSdPathTreeNode **
0x180033f7a  mov     rcx, [rbp+2E0h+var_310]; this
0x180033f7e  call    ?NextChild@CSdPathTreeNode@@QEAAJPEAPEAV1@@Z; CSdPathTreeNode::NextChild(CSdPathTreeNode * *)
0x180033f83  mov     [rsp+3E0h+var_380], eax
0x180033f87  test    eax, eax
0x180033f89  js      loc_1800340CE
0x180033f8f  mov     [rsp+3E0h+var_37C], r14w
0x180033f95  jnz     loc_1800340C4
0x180033f9b  lea     rdx, [rbp+2E0h+var_2D0]; struct CBsString *
0x180033f9f  mov     rcx, [rbp+2E0h+var_308]; this
0x180033fa3  call    ?GetDirectoryName@CSdPathTreeNode@@QEAAJPEAVCBsString@@@Z; CSdPathTreeNode::GetDirectoryName(CBsString *)
0x180033fa8  mov     [rsp+3E0h+var_380], eax
0x180033fac  test    eax, eax
0x180033fae  mov     eax, 395h
0x180033fb3  js      loc_180033E0C
0x180033fb9  mov     [rsp+3E0h+var_37C], ax
0x180033fbe  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180033fc3  mov     qword ptr [rsp+3E0h+dwCreationDisposition], r13; unsigned __int16 *
0x180033fc8  xor     r9d, r9d; unsigned __int16 *
0x180033fcb  mov     r8, [rbp+2E0h+var_2D0]; unsigned __int16 *
0x180033fcf  mov     rdx, [rbp+2E0h+var_2C0]; unsigned __int16 *
0x180033fd3  lea     rcx, [rbp+2E0h+var_2E0]; this
0x180033fd7  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180033fdc  mov     [rsp+3E0h+var_380], eax
0x180033fe0  test    eax, eax
0x180033fe2  mov     eax, 396h
0x180033fe7  js      loc_180033E0C
0x180033fed  mov     [rsp+3E0h+var_37C], ax
0x180033ff2  mov     rcx, rdi; pv
0x180033ff5  call    cs:__imp_CoTaskMemFree
0x180033ffb  mov     [rbp+2E0h+pv], r13
0x180033fff  lea     rdx, [rbp+2E0h+pv]; unsigned __int16 **
0x180034003  lea     rcx, [rbp+2E0h+var_2E0]; this
0x180034007  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003400c  lea     rdx, [rbp+2E0h+var_2A0]; struct _SX_FIND_DATA *
0x180034010  mov     rdi, [rbp+2E0h+pv]
0x180034014  mov     [rbp+2E0h+pv], rdi
0x180034018  mov     rcx, rdi; lpFileName
0x18003401b  call    ?SdGetFindData@@YAJPEBGPEAU_SX_FIND_DATA@@@Z; SdGetFindData(ushort const *,_SX_FIND_DATA *)
0x180034020  mov     [rsp+3E0h+var_380], eax
0x180034024  test    eax, eax
0x180034026  js      loc_1800340BA
0x18003402c  mov     [rsp+3E0h+var_37C], si
0x180034031  test    dword ptr [rbp+2E0h+var_2A0], 400h
0x180034038  jz      short loc_180034071
0x18003403a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034041  cmp     rcx, r12
0x180034044  jz      loc_180033F76
0x18003404a  test    byte ptr [rcx+1Ch], 40h
0x18003404e  jz      loc_180033F76
0x180034054  mov     edx, 0Eh
0x180034059  mov     r9, rdi
0x18003405c  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x180034063  mov     rcx, [rcx+10h]
0x180034067  call    WPP_SF_S
0x18003406c  jmp     loc_180033F76
0x180034071  xor     edx, edx
0x180034073  lea     rcx, [rbp+2E0h+var_340]
0x180034077  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x18003407c  lea     r8, [rbp+2E0h+var_340]; struct ISdBackupNode **
0x180034080  lea     rdx, [rbp+2E0h+var_2A0]; struct _SX_FIND_DATA *
0x180034084  mov     rcx, [rbp+2E0h+var_328]; struct ISdBackupNode *
0x180034088  call    ?CreateInstance@CSdBackupNode@@SAJPEAUISdBackupNode@@PEAU_SX_FIND_DATA@@PEAPEAU2@@Z; CSdBackupNode::CreateInstance(ISdBackupNode *,_SX_FIND_DATA *,ISdBackupNode * *)
0x18003408d  mov     [rsp+3E0h+var_380], eax
0x180034091  test    eax, eax
0x180034093  jns     short loc_18003409F
0x180034095  mov     eax, 3A6h
0x18003409a  jmp     loc_180033E0C
0x18003409f  lea     rcx, [rbp+2E0h+var_340]
0x1800340a3  call    ?Detach@?$CComPtrBase@UISdMediaRecord@@@ATL@@QEAAPEAUISdMediaRecord@@XZ; ATL::CComPtrBase<ISdMediaRecord>::Detach(void)
0x1800340a8  mov     [r15], rax
0x1800340ab  mov     [rsp+3E0h+var_380], r13d
0x1800340b0  mov     eax, 3A9h
0x1800340b5  jmp     loc_180034476
0x1800340ba  mov     [rsp+3E0h+var_37A], si
0x1800340bf  jmp     loc_18003447B
0x1800340c4  mov     eax, 3AEh
0x1800340c9  jmp     loc_18003446E
0x1800340ce  mov     [rsp+3E0h+var_37A], r14w
0x1800340d4  jmp     loc_18003447B
0x1800340d9  cmp     [rbp+2E0h+var_348], r13d
0x1800340dd  jz      loc_180034469
0x1800340e3  lea     r14, [rdi+38h]
0x1800340e7  mov     rax, [r14]
0x1800340ea  inc     rax
0x1800340ed  lea     r12, WPP_GLOBAL_Control
0x1800340f4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800340fa  jnz     loc_1800341E5
0x180034100  mov     rdx, [rdi+30h]
0x180034104  mov     r8, [rbp+2E0h+var_338]; unsigned __int16 *
0x180034108  mov     rdx, [rdx+50h]; unsigned __int16 *
0x18003410c  lea     rcx, [rbp+2E0h+lpFileName]; this
0x180034110  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x180034115  mov     [rsp+3E0h+var_380], eax
0x180034119  test    eax, eax
0x18003411b  mov     eax, 311h
0x180034120  js      loc_180033E0C
0x180034126  mov     [rsp+3E0h+var_37C], ax
0x18003412b  mov     [rsp+3E0h+hTemplateFile], r13; hTemplateFile
0x180034130  mov     [rsp+3E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180034138  mov     [rsp+3E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180034140  xor     r9d, r9d; lpSecurityAttributes
0x180034143  mov     edx, 80000000h; dwDesiredAccess
0x180034148  lea     r8d, [r9+7]; dwShareMode
0x18003414c  mov     rcx, [rbp+2E0h+lpFileName]; lpFileName
0x180034150  call    cs:__imp_CreateFileW
0x180034156  mov     rbx, rax
0x180034159  inc     rax
0x18003415c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180034162  jnz     short loc_1800341C3
0x180034164  call    GetLastFailureAsHRESULT
0x180034169  mov     esi, eax
0x18003416b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034172  cmp     rcx, r12
0x180034175  jz      short loc_18003419D
0x180034177  test    dword ptr [rcx+1Ch], 2000000h
0x18003417e  jz      short loc_18003419D
0x180034180  mov     edx, 0Ch
0x180034185  mov     [rsp+3E0h+dwCreationDisposition], eax
0x180034189  mov     r9, [rbp+2E0h+lpFileName]
0x18003418d  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x180034194  mov     rcx, [rcx+10h]
0x180034198  call    WPP_SF_Sd
0x18003419d  cmp     [rdi+54h], r13d
0x1800341a1  jz      short loc_1800341AD
0x1800341a3  mov     eax, 325h
0x1800341a8  jmp     loc_18003446E
0x1800341ad  mov     [rsp+3E0h+var_380], esi
0x1800341b1  mov     eax, 328h
0x1800341b6  test    esi, esi
0x1800341b8  js      loc_180033E0C
0x1800341be  mov     [rsp+3E0h+var_37C], ax
0x1800341c3  mov     rcx, [r14]; hObject
0x1800341c6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800341ca  jz      short loc_1800341D9
0x1800341cc  test    rcx, rcx
0x1800341cf  jz      short loc_1800341DE
0x1800341d1  call    cs:__imp_CloseHandle
0x1800341d7  jmp     short loc_1800341DE
0x1800341d9  test    r14, r14
0x1800341dc  jz      short loc_1800341E5
0x1800341de  mov     [r14], rbx
0x1800341e1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800341e5  cmp     [rdi+40h], r13
0x1800341e9  jnz     short loc_180034235
0x1800341eb  mov     esi, 40000h
0x1800341f0  mov     r9d, 4; flProtect
0x1800341f6  mov     r8d, 1000h; flAllocationType
0x1800341fc  mov     edx, esi; dwSize
0x1800341fe  xor     ecx, ecx; lpAddress
0x180034200  call    cs:__imp_VirtualAlloc
0x180034206  mov     rcx, rax
0x180034209  mov     [rdi+40h], rax
0x18003420d  test    rax, rax
0x180034210  mov     eax, 331h
0x180034215  jnz     short loc_180034224
0x180034217  mov     [rsp+3E0h+var_380], 8007000Eh
  ... truncated ...
```
