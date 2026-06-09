# CSdWin32WalkerHelper::NextChild(ISxWalkerNode *,ISxWalkerNode * *)

- ea: `0x1800350b0`
- end: `0x1800358ef`
- name: `?NextChild@CSdWin32WalkerHelper@@UEAAJPEAUISxWalkerNode@@PEAPEAU2@@Z`
- size: `2111`
- prototype: `__int64 __fastcall(CSdWin32WalkerHelper *__hidden this, struct ISxWalkerNode *, struct ISxWalkerNode **)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003520`
- `0x180003534`
- `0x180003c80`
- `0x180003c94`
- `0x1800083e4`
- `0x180009f0c`
- `0x180014c30`
- `0x180024ef4`
- `0x180033e88`
- `0x1800350b0`
- `0x180035ef8`
- `0x1800636dc`
- `0x1800637a4`
- `0x180063b34`
- `0x180072e08`
- `0x180072f14`
- `0x18008c5e8`
- `0x1800935fc`
- `0x180093698`
- `0x18009e208`
- `0x18009e8e4`
- `0x18009e904`
- `0x18009ea34`
- `0x18009eb08`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x180035632`
- `ntdll!NtQueryDirectoryFile` at `0x180035632`
- `KERNEL32!VirtualAlloc` at `0x1800355a2`
- `KERNEL32!VirtualAlloc` at `0x1800355a2`
- `KERNEL32!CreateFileW` at `0x1800354e6`
- `KERNEL32!CreateFileW` at `0x1800354e6`
- `KERNEL32!CloseHandle` at `0x18003556d`
- `KERNEL32!CloseHandle` at `0x180035676`
- `KERNEL32!CloseHandle` at `0x180035891`
- `KERNEL32!CloseHandle` at `0x18003556d`
- `KERNEL32!CloseHandle` at `0x180035676`
- `KERNEL32!CloseHandle` at `0x180035891`
- `ole32!CoTaskMemFree` at `0x180035385`
- `ole32!CoTaskMemFree` at `0x180035833`
- `ole32!CoTaskMemFree` at `0x180035843`
- `ole32!CoTaskMemFree` at `0x180035385`
- `ole32!CoTaskMemFree` at `0x180035833`
- `ole32!CoTaskMemFree` at `0x180035843`

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

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&DirectoryName,
    "CSdWin32WalkerHelper::NextChild",
    0x2CAu,
    1u);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v52);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v49);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  FileW = -1;
  IoStatusBlock = 0;
  v50 = 0;
  memset_0(v62, 0, 0x260u);
  v48 = 0;
  v56[0] = qword_1800EE510;
  v56[1] = 0;
  v60[0] = (unsigned __int16 *)qword_1800EE510;
  v60[1] = 0;
  v55 = 0;
  v59[0] = (unsigned __int16 *)qword_1800EE510;
  v59[1] = 0;
  v58[0] = qword_1800EE510;
  v58[1] = 0;
  v53[0] = (unsigned __int16 *)qword_1800EE510;
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
    ATL::CComPtr<ISdBackupSetRecord>::operator=(&v49, 0);
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
        if ( (unsigned __int8)ATL::CComPtrBase<ISdAsyncPriv>::operator!=((char *)this + 40, 0) )
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
    ATL::CComPtr<ISdBackupSetRecord>::operator=(&v49, 0);
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
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v49);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v52);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DirectoryName);
  return v28;
}

```

## disassembly

```asm
0x1800350b0  mov     [rsp-8+arg_18], rbx
0x1800350b5  push    rbp
0x1800350b6  push    rsi
0x1800350b7  push    rdi
0x1800350b8  push    r12
0x1800350ba  push    r13
0x1800350bc  push    r14
0x1800350be  push    r15
0x1800350c0  lea     rbp, [rsp-2B0h]
0x1800350c8  sub     rsp, 3B0h
0x1800350cf  mov     rax, cs:__security_cookie
0x1800350d6  xor     rax, rsp
0x1800350d9  mov     [rbp+2E0h+var_40], rax
0x1800350e0  mov     r15, r8
0x1800350e3  mov     rsi, rdx
0x1800350e6  mov     rdi, rcx
0x1800350e9  mov     r9d, 1; unsigned __int16
0x1800350ef  mov     r8d, 2CAh; unsigned __int16
0x1800350f5  lea     rdx, aCsdwin32walker_3; "CSdWin32WalkerHelper::NextChild"
0x1800350fc  lea     rcx, [rsp+3E0h+var_380]; this
0x180035101  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180035106  lea     rcx, [rbp+2E0h+var_328]; void *
0x18003510a  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18003510f  lea     rcx, [rbp+2E0h+var_340]; void *
0x180035113  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180035118  lea     r14, qword_1800EE510
0x18003511f  mov     [rbp+2E0h+lpFileName], r14
0x180035123  xor     r13d, r13d
0x180035126  mov     [rbp+2E0h+var_2E8], r13
0x18003512a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003512e  xorps   xmm0, xmm0
0x180035131  movups  xmmword ptr [rbp+2E0h+IoStatusBlock], xmm0
0x180035135  mov     [rbp+2E0h+var_338], r13
0x180035139  xor     edx, edx; Val
0x18003513b  mov     r8d, 260h; Size
0x180035141  lea     rcx, [rbp+2E0h+var_2A0]; void *
0x180035145  call    memset_0
0x18003514a  mov     [rbp+2E0h+var_348], r13d
0x18003514e  mov     [rbp+2E0h+var_300], r14
0x180035152  mov     [rbp+2E0h+var_2F8], r13
0x180035156  mov     [rbp+2E0h+var_2C0], r14
0x18003515a  mov     [rbp+2E0h+var_2B8], r13
0x18003515e  mov     [rbp+2E0h+var_308], r13
0x180035162  mov     [rbp+2E0h+var_2D0], r14
0x180035166  mov     [rbp+2E0h+var_2C8], r13
0x18003516a  mov     [rbp+2E0h+var_2E0], r14
0x18003516e  mov     [rbp+2E0h+var_2D8], r13
0x180035172  mov     [rbp+2E0h+var_320], r14
0x180035176  mov     [rbp+2E0h+var_318], r13
0x18003517a  mov     [rbp+2E0h+var_310], r13
0x18003517e  mov     [rbp+2E0h+pv], r13
0x180035182  test    r15, r15
0x180035185  jz      short loc_18003518A
0x180035187  mov     [r15], r13
0x18003518a  mov     eax, 2E6h
0x18003518f  test    rsi, rsi
0x180035192  jnz     short loc_1800351A6
0x180035194  mov     [rsp+3E0h+var_380], 80070057h
0x18003519c  mov     [rsp+3E0h+var_37A], ax
0x1800351a1  jmp     loc_18003582F
0x1800351a6  mov     [rsp+3E0h+var_37C], ax
0x1800351ab  mov     eax, 2E7h
0x1800351b0  test    r15, r15
0x1800351b3  jz      short loc_180035194
0x1800351b5  mov     [rsp+3E0h+var_380], r13d
0x1800351ba  mov     [rsp+3E0h+var_37C], ax
0x1800351bf  mov     rax, [rsi]
0x1800351c2  lea     r8, [rbp+2E0h+var_328]
0x1800351c6  lea     rdx, IID_ISdBackupNode
0x1800351cd  mov     rcx, rsi
0x1800351d0  mov     rax, [rax]
0x1800351d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351d8  mov     [rsp+3E0h+var_380], eax
0x1800351dc  test    eax, eax
0x1800351de  mov     eax, 2E9h
0x1800351e3  js      short loc_18003519C
0x1800351e5  mov     [rsp+3E0h+var_37C], ax
0x1800351ea  mov     rcx, [rbp+2E0h+var_328]
0x1800351ee  mov     rax, [rcx]
0x1800351f1  lea     rdx, [rbp+2E0h+var_338]
0x1800351f5  mov     rax, [rax+50h]
0x1800351f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351fe  mov     [rsp+3E0h+var_380], eax
0x180035202  test    eax, eax
0x180035204  mov     eax, 2EAh
0x180035209  js      short loc_18003519C
0x18003520b  mov     [rsp+3E0h+var_37C], ax
0x180035210  mov     rdx, [rbp+2E0h+var_338]; unsigned __int16 *
0x180035214  lea     rcx, [rbp+2E0h+var_320]; this
0x180035218  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003521d  mov     [rsp+3E0h+var_380], eax
0x180035221  test    eax, eax
0x180035223  mov     eax, 2EBh
0x180035228  js      loc_18003519C
0x18003522e  mov     [rsp+3E0h+var_37C], ax
0x180035233  lea     rdx, Str; "\\"
0x18003523a  lea     rcx, [rbp+2E0h+var_320]; this
0x18003523e  call    ?TrimLeft@CBsString@@QEAAXPEBG@Z; CBsString::TrimLeft(ushort const *)
0x180035243  mov     rdx, [rdi+30h]
0x180035247  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003524c  mov     qword ptr [rsp+3E0h+dwCreationDisposition], r13; unsigned __int16 *
0x180035251  xor     r9d, r9d; unsigned __int16 *
0x180035254  mov     r8, [rbp+2E0h+var_320]; unsigned __int16 *
0x180035258  mov     rdx, [rdx+40h]; unsigned __int16 *
0x18003525c  lea     rcx, [rbp+2E0h+var_300]; this
0x180035260  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180035265  mov     [rsp+3E0h+var_380], eax
0x180035269  test    eax, eax
0x18003526b  mov     eax, 2EDh
0x180035270  js      loc_18003519C
0x180035276  mov     [rsp+3E0h+var_37C], ax
0x18003527b  mov     rdx, [rdi+30h]
0x18003527f  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180035284  mov     qword ptr [rsp+3E0h+dwCreationDisposition], r13; unsigned __int16 *
0x180035289  xor     r9d, r9d; unsigned __int16 *
0x18003528c  mov     r8, [rbp+2E0h+var_320]; unsigned __int16 *
0x180035290  mov     rdx, [rdx+50h]; unsigned __int16 *
0x180035294  lea     rcx, [rbp+2E0h+var_2C0]; this
0x180035298  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003529d  mov     [rsp+3E0h+var_380], eax
0x1800352a1  test    eax, eax
0x1800352a3  mov     eax, 2EEh
0x1800352a8  js      loc_18003519C
0x1800352ae  mov     [rsp+3E0h+var_37C], ax
0x1800352b3  lea     r9, [rbp+2E0h+var_310]; struct CSdPathTreeNode **
0x1800352b7  lea     r8, [rbp+2E0h+var_348]; int *
0x1800352bb  lea     rdx, [rbp+2E0h+var_300]; struct CBsString *
0x1800352bf  mov     rcx, [rdi+58h]; this
0x1800352c3  call    ?GetTreeNode@CSdPathTree@@QEAAJPEAVCBsString@@PEAHPEAPEAVCSdPathTreeNode@@@Z; CSdPathTree::GetTreeNode(CBsString *,int *,CSdPathTreeNode * *)
0x1800352c8  mov     ecx, eax
0x1800352ca  mov     [rsp+3E0h+var_380], eax
0x1800352ce  test    eax, eax
0x1800352d0  mov     eax, 2EFh
0x1800352d5  js      loc_18003519C
0x1800352db  mov     [rsp+3E0h+var_37C], ax
0x1800352e0  test    ecx, ecx
0x1800352e2  jnz     loc_18003546F
0x1800352e8  cmp     [rbp+2E0h+var_348], r13d
0x1800352ec  jnz     loc_180035479
0x1800352f2  mov     esi, 39Bh
0x1800352f7  lea     r14d, [rsi-9]
0x1800352fb  lea     r12, WPP_GLOBAL_Control
0x180035302  mov     rdi, [rbp+2E0h+pv]
0x180035306  lea     rdx, [rbp+2E0h+var_308]; struct CSdPathTreeNode **
0x18003530a  mov     rcx, [rbp+2E0h+var_310]; this
0x18003530e  call    ?NextChild@CSdPathTreeNode@@QEAAJPEAPEAV1@@Z; CSdPathTreeNode::NextChild(CSdPathTreeNode * *)
0x180035313  mov     [rsp+3E0h+var_380], eax
0x180035317  test    eax, eax
0x180035319  js      loc_180035464
0x18003531f  mov     [rsp+3E0h+var_37C], r14w
0x180035325  jnz     loc_18003545A
0x18003532b  lea     rdx, [rbp+2E0h+var_2D0]; struct CBsString *
0x18003532f  mov     rcx, [rbp+2E0h+var_308]; this
0x180035333  call    ?GetDirectoryName@CSdPathTreeNode@@QEAAJPEAVCBsString@@@Z; CSdPathTreeNode::GetDirectoryName(CBsString *)
0x180035338  mov     [rsp+3E0h+var_380], eax
0x18003533c  test    eax, eax
0x18003533e  mov     eax, 395h
0x180035343  js      loc_18003519C
0x180035349  mov     [rsp+3E0h+var_37C], ax
0x18003534e  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180035353  mov     qword ptr [rsp+3E0h+dwCreationDisposition], r13; unsigned __int16 *
0x180035358  xor     r9d, r9d; unsigned __int16 *
0x18003535b  mov     r8, [rbp+2E0h+var_2D0]; unsigned __int16 *
0x18003535f  mov     rdx, [rbp+2E0h+var_2C0]; unsigned __int16 *
0x180035363  lea     rcx, [rbp+2E0h+var_2E0]; this
0x180035367  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003536c  mov     [rsp+3E0h+var_380], eax
0x180035370  test    eax, eax
0x180035372  mov     eax, 396h
0x180035377  js      loc_18003519C
0x18003537d  mov     [rsp+3E0h+var_37C], ax
0x180035382  mov     rcx, rdi; pv
0x180035385  call    cs:__imp_CoTaskMemFree
0x18003538c  nop     dword ptr [rax+rax+00h]
0x180035391  mov     [rbp+2E0h+pv], r13
0x180035395  lea     rdx, [rbp+2E0h+pv]; unsigned __int16 **
0x180035399  lea     rcx, [rbp+2E0h+var_2E0]; this
0x18003539d  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x1800353a2  lea     rdx, [rbp+2E0h+var_2A0]; struct _SX_FIND_DATA *
0x1800353a6  mov     rdi, [rbp+2E0h+pv]
0x1800353aa  mov     [rbp+2E0h+pv], rdi
0x1800353ae  mov     rcx, rdi; lpFileName
0x1800353b1  call    ?SdGetFindData@@YAJPEBGPEAU_SX_FIND_DATA@@@Z; SdGetFindData(ushort const *,_SX_FIND_DATA *)
0x1800353b6  mov     [rsp+3E0h+var_380], eax
0x1800353ba  test    eax, eax
0x1800353bc  js      loc_180035450
0x1800353c2  mov     [rsp+3E0h+var_37C], si
0x1800353c7  test    dword ptr [rbp+2E0h+var_2A0], 400h
0x1800353ce  jz      short loc_180035407
0x1800353d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353d7  cmp     rcx, r12
0x1800353da  jz      loc_180035306
0x1800353e0  test    byte ptr [rcx+1Ch], 40h
0x1800353e4  jz      loc_180035306
0x1800353ea  mov     edx, 0Eh
0x1800353ef  mov     r9, rdi
0x1800353f2  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x1800353f9  mov     rcx, [rcx+10h]
0x1800353fd  call    WPP_SF_S
0x180035402  jmp     loc_180035306
0x180035407  xor     edx, edx
0x180035409  lea     rcx, [rbp+2E0h+var_340]
0x18003540d  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x180035412  lea     r8, [rbp+2E0h+var_340]; struct ISdBackupNode **
0x180035416  lea     rdx, [rbp+2E0h+var_2A0]; struct _SX_FIND_DATA *
0x18003541a  mov     rcx, [rbp+2E0h+var_328]; struct ISdBackupNode *
0x18003541e  call    ?CreateInstance@CSdBackupNode@@SAJPEAUISdBackupNode@@PEAU_SX_FIND_DATA@@PEAPEAU2@@Z; CSdBackupNode::CreateInstance(ISdBackupNode *,_SX_FIND_DATA *,ISdBackupNode * *)
0x180035423  mov     [rsp+3E0h+var_380], eax
0x180035427  test    eax, eax
0x180035429  jns     short loc_180035435
0x18003542b  mov     eax, 3A6h
0x180035430  jmp     loc_18003519C
0x180035435  lea     rcx, [rbp+2E0h+var_340]
0x180035439  call    ?Detach@?$CComPtrBase@UISdMediaRecord@@@ATL@@QEAAPEAUISdMediaRecord@@XZ; ATL::CComPtrBase<ISdMediaRecord>::Detach(void)
0x18003543e  mov     [r15], rax
0x180035441  mov     [rsp+3E0h+var_380], r13d
0x180035446  mov     eax, 3A9h
0x18003544b  jmp     loc_18003582A
0x180035450  mov     [rsp+3E0h+var_37A], si
0x180035455  jmp     loc_18003582F
0x18003545a  mov     eax, 3AEh
0x18003545f  jmp     loc_180035822
0x180035464  mov     [rsp+3E0h+var_37A], r14w
0x18003546a  jmp     loc_18003582F
0x18003546f  cmp     [rbp+2E0h+var_348], r13d
0x180035473  jz      loc_18003581D
0x180035479  lea     r14, [rdi+38h]
0x18003547d  mov     rax, [r14]
0x180035480  inc     rax
0x180035483  lea     r12, WPP_GLOBAL_Control
0x18003548a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180035490  jnz     loc_180035587
0x180035496  mov     rdx, [rdi+30h]
0x18003549a  mov     r8, [rbp+2E0h+var_338]; unsigned __int16 *
0x18003549e  mov     rdx, [rdx+50h]; unsigned __int16 *
0x1800354a2  lea     rcx, [rbp+2E0h+lpFileName]; this
0x1800354a6  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x1800354ab  mov     [rsp+3E0h+var_380], eax
0x1800354af  test    eax, eax
0x1800354b1  mov     eax, 311h
0x1800354b6  js      loc_18003519C
0x1800354bc  mov     [rsp+3E0h+var_37C], ax
0x1800354c1  mov     [rsp+3E0h+hTemplateFile], r13; hTemplateFile
0x1800354c6  mov     [rsp+3E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800354ce  mov     [rsp+3E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800354d6  xor     r9d, r9d; lpSecurityAttributes
0x1800354d9  mov     edx, 80000000h; dwDesiredAccess
0x1800354de  lea     r8d, [r9+7]; dwShareMode
0x1800354e2  mov     rcx, [rbp+2E0h+lpFileName]; lpFileName
0x1800354e6  call    cs:__imp_CreateFileW
0x1800354ed  nop     dword ptr [rax+rax+00h]
0x1800354f2  mov     rbx, rax
0x1800354f5  inc     rax
0x1800354f8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800354fe  jnz     short loc_18003555F
0x180035500  call    GetLastFailureAsHRESULT
0x180035505  mov     esi, eax
0x180035507  mov     rcx, cs:WPP_GLOBAL_Control
0x18003550e  cmp     rcx, r12
0x180035511  jz      short loc_180035539
0x180035513  test    dword ptr [rcx+1Ch], 2000000h
0x18003551a  jz      short loc_180035539
0x18003551c  mov     edx, 0Ch
0x180035521  mov     [rsp+3E0h+dwCreationDisposition], eax
0x180035525  mov     r9, [rbp+2E0h+lpFileName]
0x180035529  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x180035530  mov     rcx, [rcx+10h]
0x180035534  call    WPP_SF_Sd
0x180035539  cmp     [rdi+54h], r13d
0x18003553d  jz      short loc_180035549
0x18003553f  mov     eax, 325h
0x180035544  jmp     loc_180035822
0x180035549  mov     [rsp+3E0h+var_380], esi
0x18003554d  mov     eax, 328h
0x180035552  test    esi, esi
0x180035554  js      loc_18003519C
0x18003555a  mov     [rsp+3E0h+var_37C], ax
0x18003555f  mov     rcx, [r14]; hObject
0x180035562  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035566  jz      short loc_18003557B
0x180035568  test    rcx, rcx
0x18003556b  jz      short loc_180035580
0x18003556d  call    cs:__imp_CloseHandle
0x180035574  nop     dword ptr [rax+rax+00h]
0x180035579  jmp     short loc_180035580
0x18003557b  test    r14, r14
0x18003557e  jz      short loc_180035587
0x180035580  mov     [r14], rbx
0x180035583  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180035587  cmp     [rdi+40h], r13
0x18003558b  jnz     short loc_1800355DD
0x18003558d  mov     esi, 40000h
0x180035592  mov     r9d, 4; flProtect
0x180035598  mov     r8d, 1000h; flAllocationType
0x18003559e  mov     edx, esi; dwSize
0x1800355a0  xor     ecx, ecx; lpAddress
0x1800355a2  call    cs:__imp_VirtualAlloc
0x1800355a9  nop     dword ptr [rax+rax+00h]
0x1800355ae  mov     rcx, rax
0x1800355b1  mov     [rdi+40h], rax
  ... truncated ...
```
