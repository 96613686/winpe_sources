# CSdRestoreImpl::_ReApplyDirectoryTimesAndSD(ISdAsyncPriv *,ISdCallback2 *)

- ea: `0x18002b578`
- end: `0x18002bbf9`
- name: `?_ReApplyDirectoryTimesAndSD@CSdRestoreImpl@@AEAAJPEAUISdAsyncPriv@@PEAUISdCallback2@@@Z`
- size: `1665`
- prototype: `__int64 __fastcall(CSdRestoreImpl *__hidden this, struct ISdAsyncPriv *, struct ISdCallback2 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002c07c`

## callees

- `0x180003430`
- `0x180003444`
- `0x180009a98`
- `0x180014394`
- `0x180014bd8`
- `0x180025bb0`
- `0x180026408`
- `0x180026600`
- `0x180026640`
- `0x180027bcc`
- `0x18002b578`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070564`
- `0x18008f5d0`
- `0x180099484`
- `0x18009a20c`
- `0x18009ae34`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002b897`
- `KERNEL32!CreateFileW` at `0x18002b897`
- `KERNEL32!CloseHandle` at `0x18002b8ad`
- `KERNEL32!CloseHandle` at `0x18002baa7`
- `KERNEL32!CloseHandle` at `0x18002bbb2`
- `KERNEL32!CloseHandle` at `0x18002b8ad`
- `KERNEL32!CloseHandle` at `0x18002baa7`
- `KERNEL32!CloseHandle` at `0x18002bbb2`
- `KERNEL32!SetFileTime` at `0x18002b98f`
- `KERNEL32!SetFileTime` at `0x18002b98f`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002ba81`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002ba81`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002ba51`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002ba51`
- `ole32!CoTaskMemFree` at `0x18002b9dc`
- `ole32!CoTaskMemFree` at `0x18002bb5f`
- `ole32!CoTaskMemFree` at `0x18002b9dc`
- `ole32!CoTaskMemFree` at `0x18002bb5f`

## string_xrefs

- `0x18002b5a9`: `CSdRestoreImpl::_ReApplyDirectoryTimesAndSD`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::_ReApplyDirectoryTimesAndSD(
        CSdRestoreImpl *this,
        struct ISdAsyncPriv *a2,
        struct ISdCallback2 *a3)
{
  __int64 v6; // rdi
  PSECURITY_DESCRIPTOR v7; // r15
  __int16 v8; // ax
  __int16 v9; // ax
  __int64 v10; // rax
  int v11; // eax
  __int16 v12; // cx
  struct ISdFileRecord *v13; // rbx
  LPCWSTR v14; // r14
  HANDLE FileW; // rsi
  __int64 v16; // rcx
  int LastFailureAsHRESULT; // eax
  __int16 v18; // ax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  CSdDirEntry *v22; // rcx
  unsigned int v23; // ebx
  int RelativeSDFromFileRecordForUserModeRestore; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v26; // [rsp+44h] [rbp-BCh]
  __int16 v27; // [rsp+46h] [rbp-BAh]
  CSdDirEntry *v28; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  unsigned int v32; // [rsp+98h] [rbp-68h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int16 *v34; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v35; // [rsp+A8h] [rbp-58h] BYREF
  struct ISdFileRecord *v36; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+B8h] [rbp-48h] BYREF
  CSdDirectoryMap *v38[2]; // [rsp+C0h] [rbp-40h]
  FILETIME LastWriteTime; // [rsp+D0h] [rbp-30h] BYREF
  FILETIME LastAccessTime; // [rsp+D8h] [rbp-28h] BYREF
  FILETIME CreationTime; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v42[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v43[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v44[2]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int8 *v45; // [rsp+118h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v47; // [rsp+178h] [rbp+78h] BYREF
  WINBOOL bDaclPresent; // [rsp+188h] [rbp+88h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore,
    "CSdRestoreImpl::_ReApplyDirectoryTimesAndSD",
    0xFFCu,
    1u);
  v37 = 0;
  *(_OWORD *)v38 = 0;
  v35 = 0;
  v34 = 0;
  LastAccessTime = 0;
  LastWriteTime = 0;
  CreationTime = 0;
  v6 = -1;
  lpFileName = (LPCWSTR)qword_1800E8530;
  v31 = 0;
  v44[0] = (unsigned __int16 *)qword_1800E8530;
  v44[1] = 0;
  v43[0] = (unsigned __int16 *)qword_1800E8530;
  v43[1] = 0;
  v42[0] = (unsigned __int16 *)qword_1800E8530;
  v42[1] = 0;
  v28 = 0;
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v36);
  v7 = 0;
  v47 = 0;
  v45 = 0;
  v32 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  v8 = 4117;
  if ( a2 )
  {
    v26 = 4117;
    v8 = 4118;
    if ( a3 )
    {
      RelativeSDFromFileRecordForUserModeRestore = 0;
      v26 = 4118;
      if ( (*((_BYTE *)this + 384) & 4) != 0 )
      {
        v9 = 4122;
LABEL_56:
        v26 = v9;
        goto LABEL_57;
      }
      v10 = *((_QWORD *)this + 51);
      if ( v10 )
      {
        v38[0] = *((CSdDirectoryMap **)this + 51);
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 24));
        v37 = *((_DWORD *)v38[0] + 4);
        v38[1] = 0;
        RelativeSDFromFileRecordForUserModeRestore = 0;
        v26 = 4125;
        v11 = CSxRefMap<CSdFileMap,CSdFileEntry>::CSxIter::Next(&v37, &v28);
        RelativeSDFromFileRecordForUserModeRestore = v11;
        v12 = 4126;
        if ( v11 < 0 )
        {
          v27 = 4126;
          goto LABEL_57;
        }
        while ( 1 )
        {
          v26 = v12;
          if ( v11 == 1 )
            break;
          RelativeSDFromFileRecordForUserModeRestore = CSxFunctionTracer::_SetContextHelper(
                                                         (CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore,
                                                         hInstance,
                                                         0x4E90u,
                                                         0,
                                                         0);
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
          {
            v27 = 4129;
            goto LABEL_57;
          }
          v26 = 4129;
          ATL::CComPtr<ISdGlobalCatalog>::operator=(&v36, (char *)v28 + 24);
          RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)a2 + 120LL))(a2);
          v8 = 4133;
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
            goto LABEL_3;
          v26 = 4133;
          SdFreeString(&v34);
          SdFreeString(&v35);
          v13 = v36;
          RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)v36 + 32LL))(
                                                         v36,
                                                         &v34);
          v8 = 4137;
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
            goto LABEL_3;
          v26 = 4137;
          RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)v13 + 24LL))(
                                                         v13,
                                                         &v35);
          v8 = 4138;
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
            goto LABEL_3;
          v26 = 4138;
          RelativeSDFromFileRecordForUserModeRestore = CSdRestoreImpl::_BuildDestinationStrings(
                                                         this,
                                                         v13,
                                                         (struct CBsString *)v44,
                                                         (struct CBsString *)v43,
                                                         (struct CBsString *)v42);
          v8 = 4140;
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
            goto LABEL_3;
          v26 = 4140;
          RelativeSDFromFileRecordForUserModeRestore = CBsString::Set((CBsString *)&lpFileName, v44[0], v43[0], v42[0]);
          v8 = 4142;
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
            goto LABEL_3;
          v26 = 4142;
          pSecurityDescriptor = (PSECURITY_DESCRIPTOR)lpFileName;
          RelativeSDFromFileRecordForUserModeRestore = CSxFunctionTracer::_SetContextHelper(
                                                         (CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore,
                                                         hInstance,
                                                         0x4E91u,
                                                         1u,
                                                         (const unsigned __int16 **)&pSecurityDescriptor);
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
          {
            v27 = 4144;
            goto LABEL_57;
          }
          v26 = 4144;
          RelativeSDFromFileRecordForUserModeRestore = CBsString::AntiCanonicalize((CBsString *)&lpFileName);
          v8 = 4146;
          if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
            goto LABEL_3;
          v26 = 4146;
          v14 = lpFileName;
          FileW = CreateFileW(lpFileName, 0x140180u, 7u, 0, 3u, 0x2000000u, 0);
          v16 = v6 - 1;
          if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle((HANDLE)v6);
          v6 = (__int64)FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16);
            RelativeSDFromFileRecordForUserModeRestore = LastFailureAsHRESULT;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                85,
                (unsigned int)&WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids,
                (_DWORD)v14,
                LastFailureAsHRESULT);
            RelativeSDFromFileRecordForUserModeRestore = 0;
          }
          else
          {
            RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdFileRecord *, FILETIME *))(*(_QWORD *)v13 + 64LL))(
                                                           v13,
                                                           &CreationTime);
            v18 = 4157;
            if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
              goto LABEL_52;
            v26 = 4157;
            RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdFileRecord *, FILETIME *))(*(_QWORD *)v13 + 120LL))(
                                                           v13,
                                                           &LastAccessTime);
            v18 = 4158;
            if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
              goto LABEL_52;
            v26 = 4158;
            RelativeSDFromFileRecordForUserModeRestore = (*(__int64 (__fastcall **)(struct ISdFileRecord *, FILETIME *))(*(_QWORD *)v13 + 72LL))(
                                                           v13,
                                                           &LastWriteTime);
            v18 = 4159;
            if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
              goto LABEL_52;
            v26 = 4159;
            if ( !SetFileTime(FileW, &CreationTime, &LastAccessTime, &LastWriteTime) )
            {
              RelativeSDFromFileRecordForUserModeRestore = GetLastFailureAsHRESULT(v19);
              v18 = 4162;
LABEL_52:
              v27 = v18;
              goto LABEL_57;
            }
            RelativeSDFromFileRecordForUserModeRestore = 0;
            v26 = 4162;
            if ( *((_DWORD *)this + 14) == 11
              && ((unsigned int)v31 < 2 || v14[(unsigned int)v31 - 1] != 46 || v14[(unsigned int)v31 - 2] != 92) )
            {
              CoTaskMemFree(v7);
              pSecurityDescriptor = 0;
              RelativeSDFromFileRecordForUserModeRestore = GetRelativeSDFromFileRecordForUserModeRestore(
                                                             *((PSID *)this + 66),
                                                             v13,
                                                             0,
                                                             (unsigned __int8 **)&pSecurityDescriptor,
                                                             &v47,
                                                             &v45,
                                                             &v32);
              v7 = pSecurityDescriptor;
              v8 = 4172;
              if ( RelativeSDFromFileRecordForUserModeRestore < 0 )
                goto LABEL_3;
              v26 = 4172;
              if ( pSecurityDescriptor )
              {
                if ( v47 )
                {
                  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
                  {
                    RelativeSDFromFileRecordForUserModeRestore = GetLastFailureAsHRESULT(v20);
                    v8 = 4177;
                    goto LABEL_3;
                  }
                  RelativeSDFromFileRecordForUserModeRestore = 0;
                  v26 = 4177;
                  if ( bDaclPresent )
                  {
                    if ( !SetKernelObjectSecurity(FileW, 4u, v7) )
                    {
                      RelativeSDFromFileRecordForUserModeRestore = GetLastFailureAsHRESULT(v21);
                      v8 = 4180;
                      goto LABEL_3;
                    }
                    RelativeSDFromFileRecordForUserModeRestore = 0;
                    v26 = 4180;
                  }
                }
              }
            }
            if ( FileW )
            {
              CloseHandle(FileW);
              v6 = -1;
            }
          }
          v22 = v28;
          if ( v28 )
          {
            v28 = 0;
            CSdDirEntry::Release(v22);
          }
          v11 = CSxRefMap<CSdFileMap,CSdFileEntry>::CSxIter::Next(&v37, &v28);
          RelativeSDFromFileRecordForUserModeRestore = v11;
          if ( v11 < 0 )
          {
            v8 = 4191;
            goto LABEL_3;
          }
          v12 = 4191;
        }
        RelativeSDFromFileRecordForUserModeRestore = 0;
        v9 = 4195;
        goto LABEL_56;
      }
      v8 = 4125;
    }
  }
  RelativeSDFromFileRecordForUserModeRestore = -2147024809;
LABEL_3:
  v27 = v8;
LABEL_57:
  SdFreeString(&v34);
  SdFreeString(&v35);
  CoTaskMemFree(v7);
  v23 = RelativeSDFromFileRecordForUserModeRestore;
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v36);
  if ( v28 )
    CSdDirEntry::Release(v28);
  CBsString::_Release((CBsString *)v42);
  CBsString::_Release((CBsString *)v43);
  CBsString::_Release((CBsString *)v44);
  CBsString::_Release((CBsString *)&lpFileName);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  if ( v38[0] )
  {
    CSdDirectoryMap::Release(v38[0]);
    v38[0] = 0;
  }
  v37 = 0;
  v38[1] = 0;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&RelativeSDFromFileRecordForUserModeRestore);
  return v23;
}

```

## disassembly

```asm
0x18002b578  mov     [rsp-8+arg_0], rbx
0x18002b57d  push    rbp
0x18002b57e  push    rsi
0x18002b57f  push    rdi
0x18002b580  push    r12
0x18002b582  push    r13
0x18002b584  push    r14
0x18002b586  push    r15
0x18002b588  lea     rbp, [rsp-30h]
0x18002b58d  sub     rsp, 130h
0x18002b594  mov     rbx, r8
0x18002b597  mov     r12, rdx
0x18002b59a  mov     r13, rcx
0x18002b59d  mov     r9d, 1; unsigned __int16
0x18002b5a3  mov     r8d, 0FFCh; unsigned __int16
0x18002b5a9  lea     rdx, aCsdrestoreimpl_31; "CSdRestoreImpl::_ReApplyDirectoryTimesA"...
0x18002b5b0  lea     rcx, [rsp+160h+var_120]; this
0x18002b5b5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002b5ba  xor     r14d, r14d
0x18002b5bd  mov     [rbp+60h+var_A8], r14d
0x18002b5c1  xorps   xmm0, xmm0
0x18002b5c4  movdqu  xmmword ptr [rbp+60h+var_A0], xmm0
0x18002b5c9  mov     [rbp+60h+var_B8], r14
0x18002b5cd  mov     [rbp+60h+var_C0], r14
0x18002b5d1  mov     qword ptr [rbp+60h+LastAccessTime.dwLowDateTime], r14
0x18002b5d5  mov     qword ptr [rbp+60h+LastWriteTime.dwLowDateTime], r14
0x18002b5d9  mov     qword ptr [rbp+60h+CreationTime.dwLowDateTime], r14
0x18002b5dd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002b5e1  lea     rax, qword_1800E8530
0x18002b5e8  mov     [rbp+60h+lpFileName], rax
0x18002b5ec  mov     [rbp+60h+var_D0], r14
0x18002b5f0  mov     [rbp+60h+var_58], rax
0x18002b5f4  mov     [rbp+60h+var_50], r14
0x18002b5f8  mov     [rbp+60h+var_68], rax
0x18002b5fc  mov     [rbp+60h+var_60], r14
0x18002b600  mov     [rbp+60h+var_78], rax
0x18002b604  mov     [rbp+60h+var_70], r14
0x18002b608  mov     [rsp+160h+var_E8], r14
0x18002b60d  lea     rcx, [rbp+60h+var_B0]; void *
0x18002b611  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18002b616  mov     r15d, r14d
0x18002b619  mov     [rbp+60h+arg_8], r14d
0x18002b61d  mov     [rbp+60h+var_48], r14
0x18002b621  mov     [rbp+60h+var_C8], r14d
0x18002b625  mov     [rbp+60h+bDaclPresent], r14d
0x18002b62c  mov     [rbp+60h+bDaclDefaulted], r14d
0x18002b630  mov     [rbp+60h+pDacl], r14
0x18002b634  mov     eax, 1015h
0x18002b639  test    r12, r12
0x18002b63c  jnz     short loc_18002B650
0x18002b63e  mov     [rsp+160h+var_120], 80070057h
0x18002b646  mov     [rsp+160h+var_11A], ax
0x18002b64b  jmp     loc_18002BB4A
0x18002b650  mov     [rsp+160h+var_11C], ax
0x18002b655  mov     eax, 1016h
0x18002b65a  test    rbx, rbx
0x18002b65d  jz      short loc_18002B63E
0x18002b65f  mov     [rsp+160h+var_120], r14d
0x18002b664  mov     [rsp+160h+var_11C], ax
0x18002b669  test    byte ptr [r13+180h], 4
0x18002b671  jz      short loc_18002B67D
0x18002b673  mov     eax, 101Ah
0x18002b678  jmp     loc_18002BB45
0x18002b67d  mov     rax, [r13+198h]
0x18002b684  test    rax, rax
0x18002b687  jnz     short loc_18002B690
0x18002b689  mov     eax, 101Dh
0x18002b68e  jmp     short loc_18002B63E
0x18002b690  mov     [rbp+60h+var_A0], rax
0x18002b694  lock inc dword ptr [rax+18h]
0x18002b698  mov     rax, [rbp+60h+var_A0]
0x18002b69c  mov     ecx, [rax+10h]
0x18002b69f  mov     [rbp+60h+var_A8], ecx
0x18002b6a2  mov     [rbp+60h+var_A0+8], r14
0x18002b6a6  mov     [rsp+160h+var_120], r14d
0x18002b6ab  mov     eax, 101Dh
0x18002b6b0  mov     [rsp+160h+var_11C], ax
0x18002b6b5  lea     rdx, [rsp+160h+var_E8]
0x18002b6ba  lea     rcx, [rbp+60h+var_A8]
0x18002b6be  call    ?Next@CSxIter@?$CSxRefMap@VCSdFileMap@@VCSdFileEntry@@@@QEAAJPEAPEAVCSdFileEntry@@@Z; CSxRefMap<CSdFileMap,CSdFileEntry>::CSxIter::Next(CSdFileEntry * *)
0x18002b6c3  mov     [rsp+160h+var_120], eax
0x18002b6c7  mov     ecx, 101Eh
0x18002b6cc  test    eax, eax
0x18002b6ce  jns     short loc_18002B6DA
0x18002b6d0  mov     [rsp+160h+var_11A], cx
0x18002b6d5  jmp     loc_18002BB4A
0x18002b6da  mov     esi, 1030h
0x18002b6df  lea     ebx, [rsi-0Fh]
0x18002b6e2  mov     [rsp+160h+var_11C], cx
0x18002b6e7  cmp     eax, 1
0x18002b6ea  jz      loc_18002BB3B
0x18002b6f0  mov     qword ptr [rsp+160h+dwCreationDisposition], r14; unsigned __int16 **
0x18002b6f5  xor     r9d, r9d; unsigned int
0x18002b6f8  mov     r8d, 4E90h; unsigned int
0x18002b6fe  mov     rdx, cs:hInstance; HINSTANCE
0x18002b705  lea     rcx, [rsp+160h+var_120]; this
0x18002b70a  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002b70f  mov     [rsp+160h+var_120], eax
0x18002b713  test    eax, eax
0x18002b715  js      loc_18002BB34
0x18002b71b  mov     [rsp+160h+var_11C], bx
0x18002b720  mov     rdx, [rsp+160h+var_E8]
0x18002b725  add     rdx, 18h
0x18002b729  lea     rcx, [rbp+60h+var_B0]
0x18002b72d  call    ??4?$CComPtr@UISdGlobalCatalog@@@ATL@@QEAAPEAUISdGlobalCatalog@@AEBV01@@Z; ATL::CComPtr<ISdGlobalCatalog>::operator=(ATL::CComPtr<ISdGlobalCatalog> const &)
0x18002b732  mov     rax, [r12]
0x18002b736  mov     rcx, r12
0x18002b739  mov     rax, [rax+78h]
0x18002b73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b742  mov     [rsp+160h+var_120], eax
0x18002b746  test    eax, eax
0x18002b748  lea     eax, [rsi-0Bh]
0x18002b74b  js      loc_18002B646
0x18002b751  mov     [rsp+160h+var_11C], ax
0x18002b756  lea     rcx, [rbp+60h+var_C0]; unsigned __int16 **
0x18002b75a  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18002b75f  lea     rcx, [rbp+60h+var_B8]; unsigned __int16 **
0x18002b763  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18002b768  mov     rbx, [rbp+60h+var_B0]
0x18002b76c  mov     rax, [rbx]
0x18002b76f  lea     rdx, [rbp+60h+var_C0]
0x18002b773  mov     rcx, rbx
0x18002b776  mov     rax, [rax+20h]
0x18002b77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b77f  mov     [rsp+160h+var_120], eax
0x18002b783  test    eax, eax
0x18002b785  lea     eax, [rsi-7]
0x18002b788  js      loc_18002B646
0x18002b78e  mov     [rsp+160h+var_11C], ax
0x18002b793  mov     rax, [rbx]
0x18002b796  lea     rdx, [rbp+60h+var_B8]
0x18002b79a  mov     rcx, rbx
0x18002b79d  mov     rax, [rax+18h]
0x18002b7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a6  mov     [rsp+160h+var_120], eax
0x18002b7aa  test    eax, eax
0x18002b7ac  lea     eax, [rsi-6]
0x18002b7af  js      loc_18002B646
0x18002b7b5  mov     [rsp+160h+var_11C], ax
0x18002b7ba  lea     rax, [rbp+60h+var_78]
0x18002b7be  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; struct CBsString *
0x18002b7c3  lea     r9, [rbp+60h+var_68]; struct CBsString *
0x18002b7c7  lea     r8, [rbp+60h+var_58]; struct CBsString *
0x18002b7cb  mov     rdx, rbx; struct ISdFileRecord *
0x18002b7ce  mov     rcx, r13; this
0x18002b7d1  call    ?_BuildDestinationStrings@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEAVCBsString@@11@Z; CSdRestoreImpl::_BuildDestinationStrings(ISdFileRecord *,CBsString *,CBsString *,CBsString *)
0x18002b7d6  mov     [rsp+160h+var_120], eax
0x18002b7da  test    eax, eax
0x18002b7dc  lea     eax, [rsi-4]
0x18002b7df  js      loc_18002B646
0x18002b7e5  mov     [rsp+160h+var_11C], ax
0x18002b7ea  mov     r9, [rbp+60h+var_78]; unsigned __int16 *
0x18002b7ee  mov     r8, [rbp+60h+var_68]; unsigned __int16 *
0x18002b7f2  mov     rdx, [rbp+60h+var_58]; unsigned __int16 *
0x18002b7f6  lea     rcx, [rbp+60h+lpFileName]; this
0x18002b7fa  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x18002b7ff  mov     [rsp+160h+var_120], eax
0x18002b803  test    eax, eax
0x18002b805  lea     eax, [rsi-2]
0x18002b808  js      loc_18002B646
0x18002b80e  mov     [rsp+160h+var_11C], ax
0x18002b813  mov     rax, [rbp+60h+lpFileName]
0x18002b817  mov     [rbp+60h+pSecurityDescriptor], rax
0x18002b81b  lea     rax, [rbp+60h+pSecurityDescriptor]
0x18002b81f  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; unsigned __int16 **
0x18002b824  mov     r9d, 1; unsigned int
0x18002b82a  mov     r8d, 4E91h; unsigned int
0x18002b830  mov     rdx, cs:hInstance; HINSTANCE
0x18002b837  lea     rcx, [rsp+160h+var_120]; this
0x18002b83c  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002b841  mov     [rsp+160h+var_120], eax
0x18002b845  test    eax, eax
0x18002b847  js      loc_18002BB2D
0x18002b84d  mov     [rsp+160h+var_11C], si
0x18002b852  lea     rcx, [rbp+60h+lpFileName]; this
0x18002b856  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18002b85b  mov     [rsp+160h+var_120], eax
0x18002b85f  test    eax, eax
0x18002b861  lea     eax, [rsi+2]
0x18002b864  js      loc_18002B646
0x18002b86a  mov     [rsp+160h+var_11C], ax
0x18002b86f  mov     [rsp+160h+hTemplateFile], r14; hTemplateFile
0x18002b874  mov     [rsp+160h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002b87c  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b884  xor     r9d, r9d; lpSecurityAttributes
0x18002b887  mov     edx, 140180h; dwDesiredAccess
0x18002b88c  lea     r8d, [r9+7]; dwShareMode
0x18002b890  mov     r14, [rbp+60h+lpFileName]
0x18002b894  mov     rcx, r14; lpFileName
0x18002b897  call    cs:__imp_CreateFileW
0x18002b89d  mov     rsi, rax
0x18002b8a0  lea     rcx, [rdi-1]
0x18002b8a4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002b8a8  ja      short loc_18002B8B3
0x18002b8aa  mov     rcx, rdi; hObject
0x18002b8ad  call    cs:__imp_CloseHandle
0x18002b8b3  mov     rdi, rsi
0x18002b8b6  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002b8ba  jnz     short loc_18002B905
0x18002b8bc  call    GetLastFailureAsHRESULT
0x18002b8c1  mov     [rsp+160h+var_120], eax
0x18002b8c5  lea     rdx, WPP_GLOBAL_Control
0x18002b8cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8d3  cmp     rcx, rdx
0x18002b8d6  jz      short loc_18002B8F8
0x18002b8d8  test    byte ptr [rcx+1Ch], 80h
0x18002b8dc  jz      short loc_18002B8F8
0x18002b8de  lea     edx, [rsi+56h]
0x18002b8e1  mov     [rsp+160h+dwCreationDisposition], eax
0x18002b8e5  mov     r9, r14
0x18002b8e8  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002b8ef  mov     rcx, [rcx+10h]
0x18002b8f3  call    WPP_SF_Sd
0x18002b8f8  xor     r14d, r14d
0x18002b8fb  mov     [rsp+160h+var_120], r14d
0x18002b900  jmp     loc_18002BAB1
0x18002b905  mov     rax, [rbx]
0x18002b908  lea     rdx, [rbp+60h+CreationTime]
0x18002b90c  mov     rcx, rbx
0x18002b90f  mov     rax, [rax+40h]
0x18002b913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b918  mov     [rsp+160h+var_120], eax
0x18002b91c  test    eax, eax
0x18002b91e  mov     eax, 103Dh
0x18002b923  js      loc_18002BB23
0x18002b929  mov     [rsp+160h+var_11C], ax
0x18002b92e  mov     rax, [rbx]
0x18002b931  lea     rdx, [rbp+60h+LastAccessTime]
0x18002b935  mov     rcx, rbx
0x18002b938  mov     rax, [rax+78h]
0x18002b93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b941  mov     [rsp+160h+var_120], eax
0x18002b945  test    eax, eax
0x18002b947  mov     eax, 103Eh
0x18002b94c  js      loc_18002BB23
0x18002b952  mov     [rsp+160h+var_11C], ax
0x18002b957  mov     rax, [rbx]
0x18002b95a  lea     rdx, [rbp+60h+LastWriteTime]
0x18002b95e  mov     rcx, rbx
0x18002b961  mov     rax, [rax+48h]
0x18002b965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b96a  mov     [rsp+160h+var_120], eax
0x18002b96e  test    eax, eax
0x18002b970  mov     eax, 103Fh
0x18002b975  js      loc_18002BB23
0x18002b97b  mov     [rsp+160h+var_11C], ax
0x18002b980  lea     r9, [rbp+60h+LastWriteTime]; lpLastWriteTime
0x18002b984  lea     r8, [rbp+60h+LastAccessTime]; lpLastAccessTime
0x18002b988  lea     rdx, [rbp+60h+CreationTime]; lpCreationTime
0x18002b98c  mov     rcx, rsi; hFile
0x18002b98f  call    cs:__imp_SetFileTime
0x18002b995  test    eax, eax
0x18002b997  jz      loc_18002BB15
0x18002b99d  mov     [rsp+160h+var_120], 0
0x18002b9a5  mov     eax, 1042h
0x18002b9aa  mov     [rsp+160h+var_11C], ax
0x18002b9af  cmp     dword ptr [r13+38h], 0Bh
0x18002b9b4  jnz     loc_18002BA9C
0x18002b9ba  cmp     dword ptr [rbp+60h+var_D0], 2
0x18002b9be  jb      short loc_18002B9D9
0x18002b9c0  mov     eax, dword ptr [rbp+60h+var_D0]
0x18002b9c3  cmp     word ptr [r14+rax*2-2], 2Eh ; '.'
0x18002b9ca  jnz     short loc_18002B9D9
0x18002b9cc  cmp     word ptr [r14+rax*2-4], 5Ch ; '\'
0x18002b9d3  jz      loc_18002BA9C
0x18002b9d9  mov     rcx, r15; pv
0x18002b9dc  call    cs:__imp_CoTaskMemFree
0x18002b9e2  xor     r14d, r14d
0x18002b9e5  mov     [rbp+60h+pSecurityDescriptor], r14
0x18002b9e9  lea     rax, [rbp+60h+var_C8]
0x18002b9ed  mov     [rsp+160h+hTemplateFile], rax; unsigned int *
0x18002b9f2  lea     rax, [rbp+60h+var_48]
0x18002b9f6  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x18002b9fb  lea     rax, [rbp+60h+arg_8]
0x18002b9ff  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; unsigned int *
0x18002ba04  lea     r9, [rbp+60h+pSecurityDescriptor]; unsigned __int8 **
0x18002ba08  xor     r8d, r8d; int
0x18002ba0b  mov     rdx, rbx; struct ISdFileRecord *
0x18002ba0e  mov     rcx, [r13+210h]; pSid
0x18002ba15  call    ?GetRelativeSDFromFileRecordForUserModeRestore@@YAJPEBU_SID@@PEAUISdFileRecord@@HPEAPEAEPEAK23@Z; GetRelativeSDFromFileRecordForUserModeRestore(_SID const *,ISdFileRecord *,int,uchar * *,ulong *,uchar * *,ulong *)
0x18002ba1a  mov     [rsp+160h+var_120], eax
0x18002ba1e  mov     r15, [rbp+60h+pSecurityDescriptor]
0x18002ba22  test    eax, eax
0x18002ba24  mov     eax, 104Ch
0x18002ba29  js      loc_18002B646
0x18002ba2f  mov     [rsp+160h+var_11C], ax
0x18002ba34  test    r15, r15
0x18002ba37  jz      short loc_18002BA9F
0x18002ba39  cmp     [rbp+60h+arg_8], r14d
0x18002ba3d  jz      short loc_18002BA9F
0x18002ba3f  lea     r9, [rbp+60h+bDaclDefaulted]; lpbDaclDefaulted
0x18002ba43  lea     r8, [rbp+60h+pDacl]; pDacl
0x18002ba47  lea     rdx, [rbp+60h+bDaclPresent]; lpbDaclPresent
0x18002ba4e  mov     rcx, r15; pSecurityDescriptor
0x18002ba51  call    cs:__imp_GetSecurityDescriptorDacl
0x18002ba57  test    eax, eax
0x18002ba59  jz      loc_18002BAF8
0x18002ba5f  mov     [rsp+160h+var_120], r14d
0x18002ba64  mov     eax, 1051h
0x18002ba69  mov     [rsp+160h+var_11C], ax
  ... truncated ...
```
