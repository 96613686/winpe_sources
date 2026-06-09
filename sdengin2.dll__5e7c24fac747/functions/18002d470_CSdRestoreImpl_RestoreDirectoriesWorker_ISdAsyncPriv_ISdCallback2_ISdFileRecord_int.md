# CSdRestoreImpl::_RestoreDirectoriesWorker(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,int *)

- ea: `0x18002d470`
- end: `0x18002dbb6`
- name: `?_RestoreDirectoriesWorker@CSdRestoreImpl@@AEAAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAH@Z`
- size: `1862`
- prototype: `__int64 __usercall@<rax>(CSdRestoreImpl *__hidden this@<rcx>, struct ISdAsyncPriv *@<rdx>, struct ISdCallback2 *@<r8>, struct ISdFileRecord *@<r9>, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d1a4`

## callees

- `0x180003430`
- `0x180003444`
- `0x180008240`
- `0x180021fc0`
- `0x180025794`
- `0x180025bb0`
- `0x180027bcc`
- `0x18002a66c`
- `0x18002c550`
- `0x18002d470`
- `0x18002dbbc`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070564`
- `0x18008f5d0`
- `0x180099484`
- `0x180099bdc`
- `0x18009a20c`
- `0x18009a608`
- `0x18009ae34`
- `0x1800b6568`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18002d7bf`
- `KERNEL32!GetVolumePathNameW` at `0x18002d7bf`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18002d7f9`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18002d7f9`
- `KERNEL32!GetVolumeInformationW` at `0x18002d852`
- `KERNEL32!GetVolumeInformationW` at `0x18002d852`
- `KERNEL32!LeaveCriticalSection` at `0x18002d772`
- `KERNEL32!LeaveCriticalSection` at `0x18002d772`
- `ole32!CoTaskMemFree` at `0x18002db28`
- `ole32!CoTaskMemFree` at `0x18002db3e`
- `ole32!CoTaskMemFree` at `0x18002db28`
- `ole32!CoTaskMemFree` at `0x18002db3e`

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
  CSdRestoreImpl *v41; // [rsp+120h] [rbp+20h] BYREF
  int v42; // [rsp+128h] [rbp+28h]
  WCHAR szVolumePathName[264]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR szVolumeName[264]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+550h] [rbp+450h] BYREF

  v36 = a3;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore,
    "CSdRestoreImpl::_RestoreDirectoriesWorker",
    3934,
    1);
  v41 = (CSdRestoreImpl *)((char *)this + 64);
  v42 = 0;
  pv = 0;
  v27 = 0;
  v9 = 0;
  v31 = 0;
  v30 = 0;
  v40[0] = qword_1800E8530;
  v40[1] = 0;
  lpszFileName[0] = (LPCWSTR)qword_1800E8530;
  lpszFileName[1] = 0;
  v38[0] = (unsigned __int16 *)qword_1800E8530;
  v38[1] = 0;
  v37[0] = (unsigned __int16 *)qword_1800E8530;
  v37[1] = 0;
  v33 = (unsigned __int16 *)qword_1800E8530;
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
                                                 this,
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
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v32);
  CBsString::_Release((CBsString *)&v33);
  CBsString::_Release((CBsString *)v37);
  CBsString::_Release((CBsString *)v38);
  CBsString::_Release((CBsString *)lpszFileName);
  CBsString::_Release((CBsString *)v40);
  CSdAutomaticLock::~CSdAutomaticLock((LPCRITICAL_SECTION *)&v41);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore);
  return v20;
}

```

## disassembly

```asm
0x18002d470  push    rbp
0x18002d472  push    rbx
0x18002d473  push    rsi
0x18002d474  push    rdi
0x18002d475  push    r12
0x18002d477  push    r13
0x18002d479  push    r14
0x18002d47b  push    r15
0x18002d47d  lea     rbp, [rsp-678h]
0x18002d485  sub     rsp, 778h
0x18002d48c  mov     rax, cs:__security_cookie
0x18002d493  xor     rax, rsp
0x18002d496  mov     [rbp+6B0h+var_50], rax
0x18002d49d  mov     r14, r9
0x18002d4a0  mov     rdi, r8
0x18002d4a3  mov     [rbp+6B0h+var_6D0], r8
0x18002d4a7  mov     r15, rdx
0x18002d4aa  mov     rbx, rcx
0x18002d4ad  mov     r13, [rbp+6B0h+arg_20]
0x18002d4b4  mov     r9d, 1; unsigned __int16
0x18002d4ba  mov     r8d, 0F5Eh; unsigned __int16
0x18002d4c0  lea     rdx, aCsdrestoreimpl_2; "CSdRestoreImpl::_RestoreDirectoriesWork"...
0x18002d4c7  lea     rcx, [rsp+7B0h+var_758]; this
0x18002d4cc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002d4d1  lea     rsi, [rbx+40h]
0x18002d4d5  mov     [rbp+6B0h+var_690], rsi
0x18002d4d9  xor     ecx, ecx
0x18002d4db  mov     [rbp+6B0h+var_688], ecx
0x18002d4de  mov     [rbp+6B0h+pv], rcx
0x18002d4e2  mov     [rbp+6B0h+var_71C], ecx
0x18002d4e5  mov     r12d, ecx
0x18002d4e8  mov     [rbp+6B0h+var_700], rcx
0x18002d4ec  mov     [rbp+6B0h+var_708], ecx
0x18002d4ef  lea     rax, qword_1800E8530
0x18002d4f6  mov     [rbp+6B0h+var_6A0], rax
0x18002d4fa  mov     [rbp+6B0h+var_698], rcx
0x18002d4fe  mov     [rbp+6B0h+lpszFileName], rax
0x18002d502  mov     [rbp+6B0h+var_6D8], rcx
0x18002d506  mov     [rbp+6B0h+var_6B8], rax
0x18002d50a  mov     [rbp+6B0h+var_6B0], rcx
0x18002d50e  mov     [rbp+6B0h+var_6C8], rax
0x18002d512  mov     [rbp+6B0h+var_6C0], rcx
0x18002d516  mov     [rbp+6B0h+var_6F0], rax
0x18002d51a  mov     [rbp+6B0h+var_6E8], rcx
0x18002d51e  mov     [rbp+6B0h+FileSystemFlags], ecx
0x18002d521  xor     edx, edx; Val
0x18002d523  mov     r8d, 208h; Size
0x18002d529  lea     rcx, [rbp+6B0h+szVolumePathName]; void *
0x18002d52d  call    memset_0
0x18002d532  xor     edx, edx; Val
0x18002d534  mov     r8d, 208h; Size
0x18002d53a  lea     rcx, [rbp+6B0h+szVolumeName]; void *
0x18002d541  call    memset_0
0x18002d546  xor     edx, edx; Val
0x18002d548  mov     r8d, 208h; Size
0x18002d54e  lea     rcx, [rbp+6B0h+FileSystemNameBuffer]; void *
0x18002d555  call    memset_0
0x18002d55a  mov     [rbp+6B0h+var_718], r12d
0x18002d55e  xor     eax, eax
0x18002d560  mov     [rsp+7B0h+var_760], ax
0x18002d565  lea     rcx, [rbp+6B0h+var_6F8]; void *
0x18002d569  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18002d56e  test    r13, r13
0x18002d571  jz      short loc_18002D577
0x18002d573  mov     [r13+0], r12d
0x18002d577  mov     eax, 0F78h
0x18002d57c  test    r15, r15
0x18002d57f  jnz     short loc_18002D593
0x18002d581  mov     [rsp+7B0h+var_758], 80070057h
0x18002d589  mov     [rsp+7B0h+var_752], ax
0x18002d58e  jmp     loc_18002DB1F
0x18002d593  mov     [rsp+7B0h+var_754], ax
0x18002d598  mov     eax, 0F79h
0x18002d59d  test    rdi, rdi
0x18002d5a0  jz      short loc_18002D581
0x18002d5a2  mov     [rsp+7B0h+var_754], ax
0x18002d5a7  mov     eax, 0F7Ah
0x18002d5ac  test    r14, r14
0x18002d5af  jz      short loc_18002D581
0x18002d5b1  mov     [rsp+7B0h+var_754], ax
0x18002d5b6  mov     eax, 0F7Bh
0x18002d5bb  test    r13, r13
0x18002d5be  jz      short loc_18002D581
0x18002d5c0  mov     [rsp+7B0h+var_758], r12d
0x18002d5c5  mov     [rsp+7B0h+var_754], ax
0x18002d5ca  mov     rcx, [rbx+1B0h]
0x18002d5d1  mov     rax, [rcx]
0x18002d5d4  lea     rdx, [rbp+6B0h+var_6F8]
0x18002d5d8  mov     rax, [rax+0A8h]
0x18002d5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5e4  mov     [rsp+7B0h+var_758], eax
0x18002d5e8  test    eax, eax
0x18002d5ea  mov     eax, 0F7Eh
0x18002d5ef  js      short loc_18002D589
0x18002d5f1  mov     [rsp+7B0h+var_754], ax
0x18002d5f6  mov     rax, [r14]
0x18002d5f9  lea     rdx, [rsp+7B0h+var_760]
0x18002d5fe  mov     rcx, r14
0x18002d601  mov     rax, [rax+38h]
0x18002d605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d60a  mov     [rsp+7B0h+var_758], eax
0x18002d60e  test    eax, eax
0x18002d610  mov     eax, 0F80h
0x18002d615  js      loc_18002D589
0x18002d61b  mov     [rsp+7B0h+var_754], ax
0x18002d620  mov     al, byte ptr [rsp+7B0h+var_760]
0x18002d624  and     al, 6
0x18002d626  cmp     al, 4
0x18002d628  mov     eax, 0F81h
0x18002d62d  jnz     loc_18002D581
0x18002d633  mov     [rsp+7B0h+var_758], r12d
0x18002d638  mov     [rsp+7B0h+var_754], ax
0x18002d63d  lea     rax, [rbp+6B0h+var_6F0]
0x18002d641  mov     [rsp+7B0h+lpMaximumComponentLength], rax; struct CBsString *
0x18002d646  lea     r9, [rbp+6B0h+var_6C8]; struct CBsString *
0x18002d64a  lea     r8, [rbp+6B0h+var_6B8]; struct CBsString *
0x18002d64e  mov     rdx, r14; struct ISdFileRecord *
0x18002d651  mov     rcx, rbx; this
0x18002d654  call    ?_BuildDestinationStrings@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEAVCBsString@@11@Z; CSdRestoreImpl::_BuildDestinationStrings(ISdFileRecord *,CBsString *,CBsString *,CBsString *)
0x18002d659  mov     [rsp+7B0h+var_758], eax
0x18002d65d  test    eax, eax
0x18002d65f  mov     eax, 0F83h
0x18002d664  js      loc_18002D589
0x18002d66a  mov     [rsp+7B0h+var_754], ax
0x18002d66f  cmp     dword ptr [rbp+6B0h+var_6E8], 1
0x18002d673  jnz     short loc_18002D6AE
0x18002d675  mov     rax, [rbp+6B0h+var_6F0]
0x18002d679  cmp     word ptr [rax], 2Eh ; '.'
0x18002d67d  jnz     short loc_18002D6AE
0x18002d67f  cmp     [rbx+0A8h], r12d
0x18002d686  jnz     short loc_18002D69C
0x18002d688  mov     [rsp+7B0h+var_758], r12d
0x18002d68d  mov     eax, 0F8Bh
0x18002d692  mov     [rsp+7B0h+var_754], ax
0x18002d697  jmp     loc_18002DB1F
0x18002d69c  lea     rcx, [rbp+6B0h+var_6F0]; this
0x18002d6a0  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18002d6a5  lea     rcx, [rbp+6B0h+var_6C8]; this
0x18002d6a9  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x18002d6ae  mov     r9, [rbp+6B0h+var_6F0]; unsigned __int16 *
0x18002d6b2  mov     r8, [rbp+6B0h+var_6C8]; unsigned __int16 *
0x18002d6b6  mov     rdx, [rbp+6B0h+var_6B8]; unsigned __int16 *
0x18002d6ba  lea     rcx, [rbp+6B0h+lpszFileName]; this
0x18002d6be  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x18002d6c3  mov     [rsp+7B0h+var_758], eax
0x18002d6c7  test    eax, eax
0x18002d6c9  mov     eax, 0F95h
0x18002d6ce  js      loc_18002D589
0x18002d6d4  mov     [rsp+7B0h+var_754], ax
0x18002d6d9  lea     rax, WPP_GLOBAL_Control
0x18002d6e0  mov     rdi, [rbp+6B0h+lpszFileName]
0x18002d6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6eb  cmp     rcx, rax
0x18002d6ee  jz      short loc_18002D70E
0x18002d6f0  test    byte ptr [rcx+1Ch], 80h
0x18002d6f4  jz      short loc_18002D70E
0x18002d6f6  mov     edx, 51h ; 'Q'
0x18002d6fb  mov     r9, rdi
0x18002d6fe  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002d705  mov     rcx, [rcx+10h]
0x18002d709  call    WPP_SF_S
0x18002d70e  mov     [rbp+6B0h+var_6A8], rdi
0x18002d712  lea     rax, [rbp+6B0h+var_6A8]
0x18002d716  mov     [rsp+7B0h+lpMaximumComponentLength], rax; unsigned __int16 **
0x18002d71b  mov     r9d, 1; unsigned int
0x18002d721  mov     r8d, 4E8Ch; unsigned int
0x18002d727  mov     rdx, cs:hInstance; HINSTANCE
0x18002d72e  lea     rcx, [rsp+7B0h+var_758]; this
0x18002d733  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002d738  mov     [rsp+7B0h+var_758], eax
0x18002d73c  test    eax, eax
0x18002d73e  mov     eax, 0F98h
0x18002d743  js      loc_18002D589
0x18002d749  mov     [rsp+7B0h+var_754], ax
0x18002d74e  mov     rcx, rsi; this
0x18002d751  call    ?Lock@CSdCriticalSection@@QEAAXXZ; CSdCriticalSection::Lock(void)
0x18002d756  mov     rax, [r15]
0x18002d759  mov     rdx, rdi
0x18002d75c  mov     rcx, r15
0x18002d75f  mov     rax, [rax+0E0h]
0x18002d766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d76b  mov     [rsp+7B0h+var_758], eax
0x18002d76f  mov     rcx, rsi; lpCriticalSection
0x18002d772  call    cs:__imp_LeaveCriticalSection
0x18002d778  mov     eax, 0F9Dh
0x18002d77d  cmp     [rsp+7B0h+var_758], r12d
0x18002d782  jl      loc_18002D589
0x18002d788  mov     [rsp+7B0h+var_754], ax
0x18002d78d  lea     rcx, [rbp+6B0h+lpszFileName]; this
0x18002d791  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18002d796  mov     [rsp+7B0h+var_758], eax
0x18002d79a  test    eax, eax
0x18002d79c  mov     eax, 0F9Fh
0x18002d7a1  js      loc_18002D589
0x18002d7a7  mov     [rsp+7B0h+var_754], ax
0x18002d7ac  mov     esi, 104h
0x18002d7b1  mov     r8d, esi; cchBufferLength
0x18002d7b4  lea     rdx, [rbp+6B0h+szVolumePathName]; lpszVolumePathName
0x18002d7b8  mov     rdi, [rbp+6B0h+lpszFileName]
0x18002d7bc  mov     rcx, rdi; lpszFileName
0x18002d7bf  call    cs:__imp_GetVolumePathNameW
0x18002d7c5  test    eax, eax
0x18002d7c7  jnz     short loc_18002D7DC
0x18002d7c9  call    GetLastFailureAsHRESULT
0x18002d7ce  mov     [rsp+7B0h+var_758], eax
0x18002d7d2  mov     eax, 0FA2h
0x18002d7d7  jmp     loc_18002D589
0x18002d7dc  mov     [rsp+7B0h+var_758], r12d
0x18002d7e1  mov     eax, 0FA2h
0x18002d7e6  mov     [rsp+7B0h+var_754], ax
0x18002d7eb  mov     r8d, esi; cchBufferLength
0x18002d7ee  lea     rdx, [rbp+6B0h+szVolumeName]; lpszVolumeName
0x18002d7f5  lea     rcx, [rbp+6B0h+szVolumePathName]; lpszVolumeMountPoint
0x18002d7f9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002d7ff  test    eax, eax
0x18002d801  jnz     short loc_18002D816
0x18002d803  call    GetLastFailureAsHRESULT
0x18002d808  mov     [rsp+7B0h+var_758], eax
0x18002d80c  mov     eax, 0FA3h
0x18002d811  jmp     loc_18002D589
0x18002d816  mov     [rsp+7B0h+var_758], r12d
0x18002d81b  mov     eax, 0FA3h
0x18002d820  mov     [rsp+7B0h+var_754], ax
0x18002d825  mov     [rsp+7B0h+nFileSystemNameSize], esi; nFileSystemNameSize
0x18002d829  lea     rax, [rbp+6B0h+FileSystemNameBuffer]
0x18002d830  mov     [rsp+7B0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18002d835  lea     rax, [rbp+6B0h+FileSystemFlags]
0x18002d839  mov     [rsp+7B0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18002d83e  mov     [rsp+7B0h+lpMaximumComponentLength], r12; lpMaximumComponentLength
0x18002d843  xor     r9d, r9d; lpVolumeSerialNumber
0x18002d846  xor     r8d, r8d; nVolumeNameSize
0x18002d849  xor     edx, edx; lpVolumeNameBuffer
0x18002d84b  lea     rcx, [rbp+6B0h+szVolumeName]; lpRootPathName
0x18002d852  call    cs:__imp_GetVolumeInformationW
0x18002d858  test    eax, eax
0x18002d85a  jnz     short loc_18002D86F
0x18002d85c  call    GetLastFailureAsHRESULT
0x18002d861  mov     [rsp+7B0h+var_758], eax
0x18002d865  mov     eax, 0FA4h
0x18002d86a  jmp     loc_18002D589
0x18002d86f  mov     [rsp+7B0h+var_758], r12d
0x18002d874  mov     eax, 0FA4h
0x18002d879  mov     [rsp+7B0h+var_754], ax
0x18002d87e  test    byte ptr [rbp+6B0h+FileSystemFlags], 8
0x18002d882  jz      short loc_18002D8D5
0x18002d884  cmp     dword ptr [rbx+38h], 0Bh
0x18002d888  jz      loc_18002DA4E
0x18002d88e  lea     rax, [rbp+6B0h+var_71C]
0x18002d892  mov     [rsp+7B0h+lpFileSystemNameBuffer], rax; unsigned int *
0x18002d897  lea     rax, [rbp+6B0h+pv]
0x18002d89b  mov     [rsp+7B0h+lpFileSystemFlags], rax; unsigned __int8 **
0x18002d8a0  mov     rax, [rbx+1C0h]
0x18002d8a7  mov     [rsp+7B0h+lpMaximumComponentLength], rax; struct CSdUserSidList *
0x18002d8ac  mov     r9, [rbp+6B0h+var_6F8]; struct ISdGlobalCatalog *
0x18002d8b0  mov     r8, r14; struct ISdFileRecord *
0x18002d8b3  mov     rdx, [rbp+6B0h+var_6D0]; struct ISdCallback2 *
0x18002d8b7  mov     rcx, r15; struct ISdAsyncPriv *
0x18002d8ba  call    ?GetRelativeSDFromFileRecordForAdminRestore@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@PEAPEAEPEAK@Z; GetRelativeSDFromFileRecordForAdminRestore(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,uchar * *,ulong *)
0x18002d8bf  mov     [rsp+7B0h+var_758], eax
0x18002d8c3  test    eax, eax
0x18002d8c5  mov     eax, 0FACh
0x18002d8ca  js      loc_18002D589
0x18002d8d0  mov     [rsp+7B0h+var_754], ax
0x18002d8d5  mov     esi, 0FB9h
0x18002d8da  mov     rax, [r15]
0x18002d8dd  mov     rcx, r15
0x18002d8e0  mov     rax, [rax+78h]
0x18002d8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8e9  mov     [rsp+7B0h+var_758], eax
0x18002d8ed  test    eax, eax
0x18002d8ef  js      loc_18002DB1A
0x18002d8f5  mov     [rsp+7B0h+var_754], si
0x18002d8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d901  lea     rax, WPP_GLOBAL_Control
0x18002d908  cmp     rcx, rax
0x18002d90b  jz      short loc_18002D92B
0x18002d90d  test    byte ptr [rcx+1Ch], 80h
0x18002d911  jz      short loc_18002D92B
0x18002d913  mov     edx, 52h ; 'R'
0x18002d918  mov     r9, rdi
0x18002d91b  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002d922  mov     rcx, [rcx+10h]
0x18002d926  call    WPP_SF_S
0x18002d92b  mov     eax, [rbp+6B0h+FileSystemFlags]
0x18002d92e  mov     r9, [rbp+6B0h+pv]
0x18002d932  test    r12, r12
0x18002d935  cmovnz  r9, r12; unsigned __int8 *
0x18002d939  lea     rcx, [rbp+6B0h+FileSystemNameBuffer]
0x18002d940  mov     [rsp+7B0h+lpFileSystemFlags], rcx; unsigned __int16 *
0x18002d945  mov     dword ptr [rsp+7B0h+lpMaximumComponentLength], eax; unsigned int
0x18002d949  mov     r8, rdi; unsigned __int16 *
0x18002d94c  mov     rdx, r14; struct ISdFileRecord *
0x18002d94f  mov     rcx, rbx; this
0x18002d952  call    ?_RestoreDirectory@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEBGPEBEK1@Z; CSdRestoreImpl::_RestoreDirectory(ISdFileRecord *,ushort const *,uchar const *,ulong,ushort const *)
0x18002d957  mov     esi, eax
0x18002d959  test    eax, eax
0x18002d95b  jns     loc_18002DB0D
0x18002d961  mov     eax, 81000000h
0x18002d966  cmp     esi, eax
0x18002d968  jz      loc_18002DAFF
  ... truncated ...
```
