# CSdRestoreImpl::_RestoreDirectoriesWorker(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,int *)

- ea: `0x18002e620`
- end: `0x18002ed8b`
- name: `?_RestoreDirectoriesWorker@CSdRestoreImpl@@AEAAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAH@Z`
- size: `1899`
- prototype: `__int64 __usercall@<rax>(CSdRestoreImpl *__hidden this@<rcx>, struct ISdAsyncPriv *@<rdx>, struct ISdCallback2 *@<r8>, struct ISdFileRecord *@<r9>, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002e350`

## callees

- `0x180003520`
- `0x180003534`
- `0x1800083e4`
- `0x180022c34`
- `0x180026738`
- `0x180026b6c`
- `0x180028c08`
- `0x18002b70c`
- `0x18002d6c4`
- `0x18002e620`
- `0x18002ed94`
- `0x180072e08`
- `0x180072f14`
- `0x18007351c`
- `0x1800935fc`
- `0x18009da98`
- `0x18009e234`
- `0x18009e8c4`
- `0x18009ece8`
- `0x18009f560`
- `0x1800bbfe0`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18002e975`
- `KERNEL32!GetVolumePathNameW` at `0x18002e975`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18002e9b5`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18002e9b5`
- `KERNEL32!GetVolumeInformationW` at `0x18002ea14`
- `KERNEL32!GetVolumeInformationW` at `0x18002ea14`
- `KERNEL32!LeaveCriticalSection` at `0x18002e922`
- `KERNEL32!LeaveCriticalSection` at `0x18002e922`
- `ole32!CoTaskMemFree` at `0x18002ecf0`
- `ole32!CoTaskMemFree` at `0x18002ed0c`
- `ole32!CoTaskMemFree` at `0x18002ecf0`
- `ole32!CoTaskMemFree` at `0x18002ed0c`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::_RestoreDirectoriesWorker(
        CSdRestoreImpl *this,
        struct ISdAsyncPriv *a2,
        struct ISdCallback2 *a3,
        struct ISdFileRecord *a4,
        int *a5)
{
  unsigned __int8 *v9; // r12
  __int16 v10; // ax
  unsigned __int16 v11; // dx
  unsigned __int16 *v12; // rdi
  WCHAR *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  bool v17; // sf
  unsigned __int8 *v18; // r9
  int v19; // esi
  unsigned int v20; // ebx
  __int16 v22; // [rsp+50h] [rbp-B0h] BYREF
  int RelativeSDFromFileRecordForUserModeRestore; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v24; // [rsp+5Ch] [rbp-A4h]
  __int16 v25; // [rsp+5Eh] [rbp-A2h]
  DWORD FileSystemFlags; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v27; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v28; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v31; // [rsp+B0h] [rbp-50h] BYREF
  struct ISdGlobalCatalog *v32; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v33; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpszFileName[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct ISdCallback2 *v36; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v37[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v38[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v39; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v40[2]; // [rsp+110h] [rbp+10h] BYREF
  char *v41; // [rsp+120h] [rbp+20h] BYREF
  int v42; // [rsp+128h] [rbp+28h]
  WCHAR szVolumePathName[264]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR szVolumeName[264]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+550h] [rbp+450h] BYREF

  v36 = a3;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore,
    "CSdRestoreImpl::_RestoreDirectoriesWorker",
    0xF5Eu,
    1u);
  v41 = (char *)this + 64;
  v42 = 0;
  pv = 0;
  v27 = 0;
  v9 = 0;
  v31 = 0;
  v30 = 0;
  v40[0] = qword_1800EE510;
  v40[1] = 0;
  lpszFileName[0] = (LPCWSTR)qword_1800EE510;
  lpszFileName[1] = 0;
  v38[0] = (unsigned __int16 *)qword_1800EE510;
  v38[1] = 0;
  v37[0] = (unsigned __int16 *)qword_1800EE510;
  v37[1] = 0;
  v33 = (unsigned __int16 *)qword_1800EE510;
  v34 = 0;
  FileSystemFlags = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(FileSystemNameBuffer, 0, 0x208u);
  v28 = 0;
  v22 = 0;
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v32);
  if ( a5 )
    *a5 = 0;
  v10 = 3960;
  if ( !a2 )
    goto LABEL_4;
  v24 = 3960;
  v10 = 3961;
  if ( !a3 )
    goto LABEL_4;
  v24 = 3961;
  v10 = 3962;
  if ( !a4 )
    goto LABEL_4;
  v24 = 3962;
  v10 = 3963;
  if ( !a5 )
    goto LABEL_4;
  RelativeSDFromFileRecordForUserModeRestore = 0;
  v24 = 3963;
  RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(_QWORD, struct ISdGlobalCatalog **))(**((_QWORD **)this + 54) + 168LL))(
                                                 *((_QWORD *)this + 54),
                                                 &v32);
  v10 = 3966;
  if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
    goto LABEL_5;
  v24 = 3966;
  RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdFileRecord *, __int16 *))(*(_QWORD *)a4 + 56LL))(
                                                 a4,
                                                 &v22);
  v10 = 3968;
  if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
    goto LABEL_5;
  v24 = 3968;
  v10 = 3969;
  if ( (v22 & 6) != 4 )
  {
LABEL_4:
    RelativeSDFromFileRecordForUserModeRestore = -2147024809;
LABEL_5:
    v25 = v10;
    goto LABEL_60;
  }
  RelativeSDFromFileRecordForUserModeRestore = 0;
  v24 = 3969;
  RelativeSDFromFileRecordForUserModeRestore = CSdRestoreImpl::_BuildDestinationStrings(
                                                 (const unsigned __int16 **)this,
                                                 a4,
                                                 (struct CBsString *)v38,
                                                 (struct CBsString *)v37,
                                                 (struct CBsString *)&v33);
  v10 = 3971;
  if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
    goto LABEL_5;
  v24 = 3971;
  if ( (_DWORD)v34 != 1 || *v33 != 46 )
    goto LABEL_18;
  if ( *((_DWORD *)this + 42) )
  {
    CBsString::Empty((CBsString *)&v33);
    CBsString::UnTrailing((CBsString *)v37, v11);
LABEL_18:
    RelativeSDFromFileRecordForUserModeRestore = CBsString::Set((CBsString *)lpszFileName, v38[0], v37[0], v33);
    v10 = 3989;
    if ( RelativeSDFromFileRecordForUserModeRestore >= 0 )
    {
      v24 = 3989;
      v12 = (unsigned __int16 *)lpszFileName[0];
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
          lpszFileName[0]);
      v39 = v12;
      RelativeSDFromFileRecordForUserModeRestore = CSxFunctionTracer::_SetContextHelper(
                                                     (CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore,
                                                     hInstance,
                                                     0x4E8Cu,
                                                     1u,
                                                     (const unsigned __int16 **)&v39);
      v10 = 3992;
      if ( RelativeSDFromFileRecordForUserModeRestore >= 0 )
      {
        v24 = 3992;
        CSdCriticalSection::Lock((CSdRestoreImpl *)((char *)this + 64));
        RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *, unsigned __int16 *))(*(_QWORD *)a2 + 224LL))(
                                                       a2,
                                                       v12);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        v10 = 3997;
        if ( RelativeSDFromFileRecordForUserModeRestore >= 0 )
        {
          v24 = 3997;
          RelativeSDFromFileRecordForUserModeRestore = CBsString::AntiCanonicalize((CBsString *)lpszFileName);
          v10 = 3999;
          if ( RelativeSDFromFileRecordForUserModeRestore >= 0 )
          {
            v24 = 3999;
            v13 = (WCHAR *)lpszFileName[0];
            if ( GetVolumePathNameW(lpszFileName[0], szVolumePathName, 0x104u) )
            {
              RelativeSDFromFileRecordForUserModeRestore = 0;
              v24 = 4002;
              if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
              {
                RelativeSDFromFileRecordForUserModeRestore = 0;
                v24 = 4003;
                if ( GetVolumeInformationW(szVolumeName, 0, 0, 0, 0, &FileSystemFlags, FileSystemNameBuffer, 0x104u) )
                {
                  RelativeSDFromFileRecordForUserModeRestore = 0;
                  v24 = 4004;
                  if ( (FileSystemFlags & 8) == 0 )
                    goto LABEL_36;
                  if ( *((_DWORD *)this + 14) == 11 )
                  {
                    RelativeSDFromFileRecordForUserModeRestore = GetRelativeSDFromFileRecordForUserModeRestore(
                                                                   *((PSID *)this + 66),
                                                                   a4,
                                                                   1,
                                                                   (unsigned __int8 **)&pv,
                                                                   &v27,
                                                                   &v31,
                                                                   &v30);
                    v9 = v31;
                    v17 = RelativeSDFromFileRecordForUserModeRestore < 0;
                    v10 = 4018;
                  }
                  else
                  {
                    RelativeSDFromFileRecordForUserModeRestore = GetRelativeSDFromFileRecordForAdminRestore(
                                                                   a2,
                                                                   v36,
                                                                   a4,
                                                                   v32,
                                                                   *((struct CSdUserSidList **)this + 56),
                                                                   (unsigned __int8 **)&pv,
                                                                   &v27);
                    v17 = RelativeSDFromFileRecordForUserModeRestore < 0;
                    v10 = 4012;
                  }
                  if ( !v17 )
                  {
                    v24 = v10;
                    while ( 1 )
                    {
LABEL_36:
                      RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)a2 + 120LL))(a2);
                      if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
                      {
                        v25 = 4025;
                        goto LABEL_60;
                      }
                      v24 = 4025;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          82,
                          &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
                          v13);
                      v18 = (unsigned __int8 *)pv;
                      if ( v9 )
                        v18 = v9;
                      v19 = CSdRestoreImpl::_RestoreDirectory(this, a4, v13, v18, FileSystemFlags, FileSystemNameBuffer);
                      if ( v19 >= 0 )
                      {
                        *a5 = v19 == 0;
                        goto LABEL_60;
                      }
                      if ( v19 == -2130706432 )
                      {
                        RelativeSDFromFileRecordForUserModeRestore = -2130706432;
                        v10 = 4032;
                        goto LABEL_5;
                      }
                      RelativeSDFromFileRecordForUserModeRestore = 0;
                      v24 = 4032;
                      RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)a2 + 120LL))(a2);
                      v10 = 4033;
                      if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
                        goto LABEL_5;
                      v24 = 4033;
                      RelativeSDFromFileRecordForUserModeRestore = CSdRestoreImpl::_RestoreAskUIWhatToDo(
                                                                     this,
                                                                     a2,
                                                                     v19,
                                                                     v36,
                                                                     v13,
                                                                     v13,
                                                                     a4,
                                                                     9u,
                                                                     (struct CBsString *)v40,
                                                                     &v28);
                      v10 = 4035;
                      if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
                        goto LABEL_5;
                      v24 = 4035;
                      if ( v28 == 1 )
                        break;
                      if ( v28 == 8
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                      {
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          84,
                          &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
                          v13);
                      }
                    }
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        83,
                        &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
                        v13);
                    RelativeSDFromFileRecordForUserModeRestore = 0;
                    RelativeSDFromFileRecordForUserModeRestore = CSdRestoreImpl::_LogSkippedFile(this, v13, v19);
                    v10 = 4043;
                    if ( RelativeSDFromFileRecordForUserModeRestore >= 0 )
                    {
                      v24 = 4043;
                      *((_DWORD *)this + 39) = 1;
                      goto LABEL_60;
                    }
                  }
                }
                else
                {
                  RelativeSDFromFileRecordForUserModeRestore = GetLastFailureAsHRESULT(v16);
                  v10 = 4004;
                }
              }
              else
              {
                RelativeSDFromFileRecordForUserModeRestore = GetLastFailureAsHRESULT(v15);
                v10 = 4003;
              }
            }
            else
            {
              RelativeSDFromFileRecordForUserModeRestore = GetLastFailureAsHRESULT(v14);
              v10 = 4002;
            }
          }
        }
      }
    }
    goto LABEL_5;
  }
  RelativeSDFromFileRecordForUserModeRestore = 0;
  v24 = 3979;
LABEL_60:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v9 )
    CoTaskMemFree(v9);
  v20 = RelativeSDFromFileRecordForUserModeRestore;
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v32);
  CBsString::_Release((CBsString *)&v33);
  CBsString::_Release((CBsString *)v37);
  CBsString::_Release((CBsString *)v38);
  CBsString::_Release((CBsString *)lpszFileName);
  CBsString::_Release((CBsString *)v40);
  CSdAutomaticLock::~CSdAutomaticLock((CSdAutomaticLock *)&v41);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore);
  return v20;
}

```

## disassembly

```asm
0x18002e620  push    rbp
0x18002e622  push    rbx
0x18002e623  push    rsi
0x18002e624  push    rdi
0x18002e625  push    r12
0x18002e627  push    r13
0x18002e629  push    r14
0x18002e62b  push    r15
0x18002e62d  lea     rbp, [rsp-678h]
0x18002e635  sub     rsp, 778h
0x18002e63c  mov     rax, cs:__security_cookie
0x18002e643  xor     rax, rsp
0x18002e646  mov     [rbp+6B0h+var_50], rax
0x18002e64d  mov     r14, r9
0x18002e650  mov     rdi, r8
0x18002e653  mov     [rbp+6B0h+var_6D0], r8
0x18002e657  mov     r15, rdx
0x18002e65a  mov     rbx, rcx
0x18002e65d  mov     r13, [rbp+6B0h+arg_20]
0x18002e664  mov     r9d, 1; unsigned __int16
0x18002e66a  mov     r8d, 0F5Eh; unsigned __int16
0x18002e670  lea     rdx, aCsdrestoreimpl_2; "CSdRestoreImpl::_RestoreDirectoriesWork"...
0x18002e677  lea     rcx, [rsp+7B0h+var_758]; this
0x18002e67c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002e681  lea     rsi, [rbx+40h]
0x18002e685  mov     [rbp+6B0h+var_690], rsi
0x18002e689  xor     ecx, ecx
0x18002e68b  mov     [rbp+6B0h+var_688], ecx
0x18002e68e  mov     [rbp+6B0h+pv], rcx
0x18002e692  mov     [rbp+6B0h+var_71C], ecx
0x18002e695  mov     r12d, ecx
0x18002e698  mov     [rbp+6B0h+var_700], rcx
0x18002e69c  mov     [rbp+6B0h+var_708], ecx
0x18002e69f  lea     rax, qword_1800EE510
0x18002e6a6  mov     [rbp+6B0h+var_6A0], rax
0x18002e6aa  mov     [rbp+6B0h+var_698], rcx
0x18002e6ae  mov     [rbp+6B0h+lpszFileName], rax
0x18002e6b2  mov     [rbp+6B0h+var_6D8], rcx
0x18002e6b6  mov     [rbp+6B0h+var_6B8], rax
0x18002e6ba  mov     [rbp+6B0h+var_6B0], rcx
0x18002e6be  mov     [rbp+6B0h+var_6C8], rax
0x18002e6c2  mov     [rbp+6B0h+var_6C0], rcx
0x18002e6c6  mov     [rbp+6B0h+var_6F0], rax
0x18002e6ca  mov     [rbp+6B0h+var_6E8], rcx
0x18002e6ce  mov     [rbp+6B0h+FileSystemFlags], ecx
0x18002e6d1  xor     edx, edx; Val
0x18002e6d3  mov     r8d, 208h; Size
0x18002e6d9  lea     rcx, [rbp+6B0h+szVolumePathName]; void *
0x18002e6dd  call    memset_0
0x18002e6e2  xor     edx, edx; Val
0x18002e6e4  mov     r8d, 208h; Size
0x18002e6ea  lea     rcx, [rbp+6B0h+szVolumeName]; void *
0x18002e6f1  call    memset_0
0x18002e6f6  xor     edx, edx; Val
0x18002e6f8  mov     r8d, 208h; Size
0x18002e6fe  lea     rcx, [rbp+6B0h+FileSystemNameBuffer]; void *
0x18002e705  call    memset_0
0x18002e70a  mov     [rbp+6B0h+var_718], r12d
0x18002e70e  xor     eax, eax
0x18002e710  mov     [rsp+7B0h+var_760], ax
0x18002e715  lea     rcx, [rbp+6B0h+var_6F8]; void *
0x18002e719  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18002e71e  test    r13, r13
0x18002e721  jz      short loc_18002E727
0x18002e723  mov     [r13+0], r12d
0x18002e727  mov     eax, 0F78h
0x18002e72c  test    r15, r15
0x18002e72f  jnz     short loc_18002E743
0x18002e731  mov     [rsp+7B0h+var_758], 80070057h
0x18002e739  mov     [rsp+7B0h+var_752], ax
0x18002e73e  jmp     loc_18002ECE7
0x18002e743  mov     [rsp+7B0h+var_754], ax
0x18002e748  mov     eax, 0F79h
0x18002e74d  test    rdi, rdi
0x18002e750  jz      short loc_18002E731
0x18002e752  mov     [rsp+7B0h+var_754], ax
0x18002e757  mov     eax, 0F7Ah
0x18002e75c  test    r14, r14
0x18002e75f  jz      short loc_18002E731
0x18002e761  mov     [rsp+7B0h+var_754], ax
0x18002e766  mov     eax, 0F7Bh
0x18002e76b  test    r13, r13
0x18002e76e  jz      short loc_18002E731
0x18002e770  mov     [rsp+7B0h+var_758], r12d
0x18002e775  mov     [rsp+7B0h+var_754], ax
0x18002e77a  mov     rcx, [rbx+1B0h]
0x18002e781  mov     rax, [rcx]
0x18002e784  lea     rdx, [rbp+6B0h+var_6F8]
0x18002e788  mov     rax, [rax+0A8h]
0x18002e78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e794  mov     [rsp+7B0h+var_758], eax
0x18002e798  test    eax, eax
0x18002e79a  mov     eax, 0F7Eh
0x18002e79f  js      short loc_18002E739
0x18002e7a1  mov     [rsp+7B0h+var_754], ax
0x18002e7a6  mov     rax, [r14]
0x18002e7a9  lea     rdx, [rsp+7B0h+var_760]
0x18002e7ae  mov     rcx, r14
0x18002e7b1  mov     rax, [rax+38h]
0x18002e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7ba  mov     [rsp+7B0h+var_758], eax
0x18002e7be  test    eax, eax
0x18002e7c0  mov     eax, 0F80h
0x18002e7c5  js      loc_18002E739
0x18002e7cb  mov     [rsp+7B0h+var_754], ax
0x18002e7d0  mov     al, byte ptr [rsp+7B0h+var_760]
0x18002e7d4  and     al, 6
0x18002e7d6  cmp     al, 4
0x18002e7d8  mov     eax, 0F81h
0x18002e7dd  jnz     loc_18002E731
0x18002e7e3  mov     [rsp+7B0h+var_758], r12d
0x18002e7e8  mov     [rsp+7B0h+var_754], ax
0x18002e7ed  lea     rax, [rbp+6B0h+var_6F0]
0x18002e7f1  mov     [rsp+7B0h+lpMaximumComponentLength], rax; struct CBsString *
0x18002e7f6  lea     r9, [rbp+6B0h+var_6C8]; struct CBsString *
0x18002e7fa  lea     r8, [rbp+6B0h+var_6B8]; struct CBsString *
0x18002e7fe  mov     rdx, r14; struct ISdFileRecord *
0x18002e801  mov     rcx, rbx; this
0x18002e804  call    ?_BuildDestinationStrings@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEAVCBsString@@11@Z; CSdRestoreImpl::_BuildDestinationStrings(ISdFileRecord *,CBsString *,CBsString *,CBsString *)
0x18002e809  mov     [rsp+7B0h+var_758], eax
0x18002e80d  test    eax, eax
0x18002e80f  mov     eax, 0F83h
0x18002e814  js      loc_18002E739
0x18002e81a  mov     [rsp+7B0h+var_754], ax
0x18002e81f  cmp     dword ptr [rbp+6B0h+var_6E8], 1
0x18002e823  jnz     short loc_18002E85E
0x18002e825  mov     rax, [rbp+6B0h+var_6F0]
0x18002e829  cmp     word ptr [rax], 2Eh ; '.'
0x18002e82d  jnz     short loc_18002E85E
0x18002e82f  cmp     [rbx+0A8h], r12d
0x18002e836  jnz     short loc_18002E84C
0x18002e838  mov     [rsp+7B0h+var_758], r12d
0x18002e83d  mov     eax, 0F8Bh
0x18002e842  mov     [rsp+7B0h+var_754], ax
0x18002e847  jmp     loc_18002ECE7
0x18002e84c  lea     rcx, [rbp+6B0h+var_6F0]; this
0x18002e850  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18002e855  lea     rcx, [rbp+6B0h+var_6C8]; this
0x18002e859  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x18002e85e  mov     r9, [rbp+6B0h+var_6F0]; unsigned __int16 *
0x18002e862  mov     r8, [rbp+6B0h+var_6C8]; unsigned __int16 *
0x18002e866  mov     rdx, [rbp+6B0h+var_6B8]; unsigned __int16 *
0x18002e86a  lea     rcx, [rbp+6B0h+lpszFileName]; this
0x18002e86e  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x18002e873  mov     [rsp+7B0h+var_758], eax
0x18002e877  test    eax, eax
0x18002e879  mov     eax, 0F95h
0x18002e87e  js      loc_18002E739
0x18002e884  mov     [rsp+7B0h+var_754], ax
0x18002e889  lea     rax, WPP_GLOBAL_Control
0x18002e890  mov     rdi, [rbp+6B0h+lpszFileName]
0x18002e894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e89b  cmp     rcx, rax
0x18002e89e  jz      short loc_18002E8BE
0x18002e8a0  test    byte ptr [rcx+1Ch], 80h
0x18002e8a4  jz      short loc_18002E8BE
0x18002e8a6  mov     edx, 51h ; 'Q'
0x18002e8ab  mov     r9, rdi
0x18002e8ae  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002e8b5  mov     rcx, [rcx+10h]
0x18002e8b9  call    WPP_SF_S
0x18002e8be  mov     [rbp+6B0h+var_6A8], rdi
0x18002e8c2  lea     rax, [rbp+6B0h+var_6A8]
0x18002e8c6  mov     [rsp+7B0h+lpMaximumComponentLength], rax; unsigned __int16 **
0x18002e8cb  mov     r9d, 1; unsigned int
0x18002e8d1  mov     r8d, 4E8Ch; unsigned int
0x18002e8d7  mov     rdx, cs:hInstance; HINSTANCE
0x18002e8de  lea     rcx, [rsp+7B0h+var_758]; this
0x18002e8e3  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002e8e8  mov     [rsp+7B0h+var_758], eax
0x18002e8ec  test    eax, eax
0x18002e8ee  mov     eax, 0F98h
0x18002e8f3  js      loc_18002E739
0x18002e8f9  mov     [rsp+7B0h+var_754], ax
0x18002e8fe  mov     rcx, rsi; this
0x18002e901  call    ?Lock@CSdCriticalSection@@QEAAXXZ; CSdCriticalSection::Lock(void)
0x18002e906  mov     rax, [r15]
0x18002e909  mov     rdx, rdi
0x18002e90c  mov     rcx, r15
0x18002e90f  mov     rax, [rax+0E0h]
0x18002e916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e91b  mov     [rsp+7B0h+var_758], eax
0x18002e91f  mov     rcx, rsi; lpCriticalSection
0x18002e922  call    cs:__imp_LeaveCriticalSection
0x18002e929  nop     dword ptr [rax+rax+00h]
0x18002e92e  mov     eax, 0F9Dh
0x18002e933  cmp     [rsp+7B0h+var_758], r12d
0x18002e938  jl      loc_18002E739
0x18002e93e  mov     [rsp+7B0h+var_754], ax
0x18002e943  lea     rcx, [rbp+6B0h+lpszFileName]; this
0x18002e947  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18002e94c  mov     [rsp+7B0h+var_758], eax
0x18002e950  test    eax, eax
0x18002e952  mov     eax, 0F9Fh
0x18002e957  js      loc_18002E739
0x18002e95d  mov     [rsp+7B0h+var_754], ax
0x18002e962  mov     esi, 104h
0x18002e967  mov     r8d, esi; cchBufferLength
0x18002e96a  lea     rdx, [rbp+6B0h+szVolumePathName]; lpszVolumePathName
0x18002e96e  mov     rdi, [rbp+6B0h+lpszFileName]
0x18002e972  mov     rcx, rdi; lpszFileName
0x18002e975  call    cs:__imp_GetVolumePathNameW
0x18002e97c  nop     dword ptr [rax+rax+00h]
0x18002e981  test    eax, eax
0x18002e983  jnz     short loc_18002E998
0x18002e985  call    GetLastFailureAsHRESULT
0x18002e98a  mov     [rsp+7B0h+var_758], eax
0x18002e98e  mov     eax, 0FA2h
0x18002e993  jmp     loc_18002E739
0x18002e998  mov     [rsp+7B0h+var_758], r12d
0x18002e99d  mov     eax, 0FA2h
0x18002e9a2  mov     [rsp+7B0h+var_754], ax
0x18002e9a7  mov     r8d, esi; cchBufferLength
0x18002e9aa  lea     rdx, [rbp+6B0h+szVolumeName]; lpszVolumeName
0x18002e9b1  lea     rcx, [rbp+6B0h+szVolumePathName]; lpszVolumeMountPoint
0x18002e9b5  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002e9bc  nop     dword ptr [rax+rax+00h]
0x18002e9c1  test    eax, eax
0x18002e9c3  jnz     short loc_18002E9D8
0x18002e9c5  call    GetLastFailureAsHRESULT
0x18002e9ca  mov     [rsp+7B0h+var_758], eax
0x18002e9ce  mov     eax, 0FA3h
0x18002e9d3  jmp     loc_18002E739
0x18002e9d8  mov     [rsp+7B0h+var_758], r12d
0x18002e9dd  mov     eax, 0FA3h
0x18002e9e2  mov     [rsp+7B0h+var_754], ax
0x18002e9e7  mov     [rsp+7B0h+nFileSystemNameSize], esi; nFileSystemNameSize
0x18002e9eb  lea     rax, [rbp+6B0h+FileSystemNameBuffer]
0x18002e9f2  mov     [rsp+7B0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18002e9f7  lea     rax, [rbp+6B0h+FileSystemFlags]
0x18002e9fb  mov     [rsp+7B0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18002ea00  mov     [rsp+7B0h+lpMaximumComponentLength], r12; lpMaximumComponentLength
0x18002ea05  xor     r9d, r9d; lpVolumeSerialNumber
0x18002ea08  xor     r8d, r8d; nVolumeNameSize
0x18002ea0b  xor     edx, edx; lpVolumeNameBuffer
0x18002ea0d  lea     rcx, [rbp+6B0h+szVolumeName]; lpRootPathName
0x18002ea14  call    cs:__imp_GetVolumeInformationW
0x18002ea1b  nop     dword ptr [rax+rax+00h]
0x18002ea20  test    eax, eax
0x18002ea22  jnz     short loc_18002EA37
0x18002ea24  call    GetLastFailureAsHRESULT
0x18002ea29  mov     [rsp+7B0h+var_758], eax
0x18002ea2d  mov     eax, 0FA4h
0x18002ea32  jmp     loc_18002E739
0x18002ea37  mov     [rsp+7B0h+var_758], r12d
0x18002ea3c  mov     eax, 0FA4h
0x18002ea41  mov     [rsp+7B0h+var_754], ax
0x18002ea46  test    byte ptr [rbp+6B0h+FileSystemFlags], 8
0x18002ea4a  jz      short loc_18002EA9D
0x18002ea4c  cmp     dword ptr [rbx+38h], 0Bh
0x18002ea50  jz      loc_18002EC16
0x18002ea56  lea     rax, [rbp+6B0h+var_71C]
0x18002ea5a  mov     [rsp+7B0h+lpFileSystemNameBuffer], rax; unsigned int *
0x18002ea5f  lea     rax, [rbp+6B0h+pv]
0x18002ea63  mov     [rsp+7B0h+lpFileSystemFlags], rax; unsigned __int8 **
0x18002ea68  mov     rax, [rbx+1C0h]
0x18002ea6f  mov     [rsp+7B0h+lpMaximumComponentLength], rax; struct CSdUserSidList *
0x18002ea74  mov     r9, [rbp+6B0h+var_6F8]; struct ISdGlobalCatalog *
0x18002ea78  mov     r8, r14; struct ISdFileRecord *
0x18002ea7b  mov     rdx, [rbp+6B0h+var_6D0]; struct ISdCallback2 *
0x18002ea7f  mov     rcx, r15; struct ISdAsyncPriv *
0x18002ea82  call    ?GetRelativeSDFromFileRecordForAdminRestore@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@PEAPEAEPEAK@Z; GetRelativeSDFromFileRecordForAdminRestore(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,uchar * *,ulong *)
0x18002ea87  mov     [rsp+7B0h+var_758], eax
0x18002ea8b  test    eax, eax
0x18002ea8d  mov     eax, 0FACh
0x18002ea92  js      loc_18002E739
0x18002ea98  mov     [rsp+7B0h+var_754], ax
0x18002ea9d  mov     esi, 0FB9h
0x18002eaa2  mov     rax, [r15]
0x18002eaa5  mov     rcx, r15
0x18002eaa8  mov     rax, [rax+78h]
0x18002eaac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eab1  mov     [rsp+7B0h+var_758], eax
0x18002eab5  test    eax, eax
0x18002eab7  js      loc_18002ECE2
0x18002eabd  mov     [rsp+7B0h+var_754], si
0x18002eac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eac9  lea     rax, WPP_GLOBAL_Control
0x18002ead0  cmp     rcx, rax
0x18002ead3  jz      short loc_18002EAF3
0x18002ead5  test    byte ptr [rcx+1Ch], 80h
0x18002ead9  jz      short loc_18002EAF3
0x18002eadb  mov     edx, 52h ; 'R'
0x18002eae0  mov     r9, rdi
0x18002eae3  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002eaea  mov     rcx, [rcx+10h]
0x18002eaee  call    WPP_SF_S
0x18002eaf3  mov     eax, [rbp+6B0h+FileSystemFlags]
0x18002eaf6  mov     r9, [rbp+6B0h+pv]
0x18002eafa  test    r12, r12
0x18002eafd  cmovnz  r9, r12; unsigned __int8 *
0x18002eb01  lea     rcx, [rbp+6B0h+FileSystemNameBuffer]
0x18002eb08  mov     [rsp+7B0h+lpFileSystemFlags], rcx; unsigned __int16 *
0x18002eb0d  mov     dword ptr [rsp+7B0h+lpMaximumComponentLength], eax; unsigned int
0x18002eb11  mov     r8, rdi; unsigned __int16 *
0x18002eb14  mov     rdx, r14; struct ISdFileRecord *
0x18002eb17  mov     rcx, rbx; this
0x18002eb1a  call    ?_RestoreDirectory@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEBGPEBEK1@Z; CSdRestoreImpl::_RestoreDirectory(ISdFileRecord *,ushort const *,uchar const *,ulong,ushort const *)
0x18002eb1f  mov     esi, eax
0x18002eb21  test    eax, eax
  ... truncated ...
```
