# CSdRestoreImpl::_ReApplyDirectoryTimesAndSD(ISdAsyncPriv *,ISdCallback2 *)

- ea: `0x18002c62c`
- end: `0x18002cce4`
- name: `?_ReApplyDirectoryTimesAndSD@CSdRestoreImpl@@AEAAJPEAUISdAsyncPriv@@PEAUISdCallback2@@@Z`
- size: `1720`
- prototype: `__int64 __fastcall(CSdRestoreImpl *__hidden this, struct ISdAsyncPriv *, struct ISdCallback2 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d16c`

## callees

- `0x180003520`
- `0x180003534`
- `0x180009d0c`
- `0x180014c30`
- `0x1800154cc`
- `0x180026b6c`
- `0x1800273fc`
- `0x180027600`
- `0x180027640`
- `0x180028c08`
- `0x18002c62c`
- `0x180072e08`
- `0x180072f14`
- `0x18007351c`
- `0x1800935fc`
- `0x18009da98`
- `0x18009e8c4`
- `0x18009f560`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002c94b`
- `KERNEL32!CreateFileW` at `0x18002c94b`
- `KERNEL32!CloseHandle` at `0x18002c967`
- `KERNEL32!CloseHandle` at `0x18002cb7f`
- `KERNEL32!CloseHandle` at `0x18002cc96`
- `KERNEL32!CloseHandle` at `0x18002c967`
- `KERNEL32!CloseHandle` at `0x18002cb7f`
- `KERNEL32!CloseHandle` at `0x18002cc96`
- `KERNEL32!SetFileTime` at `0x18002ca4f`
- `KERNEL32!SetFileTime` at `0x18002ca4f`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002cb53`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002cb53`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002cb1d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002cb1d`
- `ole32!CoTaskMemFree` at `0x18002caa2`
- `ole32!CoTaskMemFree` at `0x18002cc3d`
- `ole32!CoTaskMemFree` at `0x18002caa2`
- `ole32!CoTaskMemFree` at `0x18002cc3d`

## string_xrefs

- `0x18002c65d`: `CSdRestoreImpl::_ReApplyDirectoryTimesAndSD`

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
  lpFileName = (LPCWSTR)qword_1800EE510;
  v31 = 0;
  v44[0] = (unsigned __int16 *)qword_1800EE510;
  v44[1] = 0;
  v43[0] = (unsigned __int16 *)qword_1800EE510;
  v43[1] = 0;
  v42[0] = (unsigned __int16 *)qword_1800EE510;
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
0x18002c62c  mov     [rsp-8+arg_0], rbx
0x18002c631  push    rbp
0x18002c632  push    rsi
0x18002c633  push    rdi
0x18002c634  push    r12
0x18002c636  push    r13
0x18002c638  push    r14
0x18002c63a  push    r15
0x18002c63c  lea     rbp, [rsp-30h]
0x18002c641  sub     rsp, 130h
0x18002c648  mov     rbx, r8
0x18002c64b  mov     r12, rdx
0x18002c64e  mov     r13, rcx
0x18002c651  mov     r9d, 1; unsigned __int16
0x18002c657  mov     r8d, 0FFCh; unsigned __int16
0x18002c65d  lea     rdx, aCsdrestoreimpl_31; "CSdRestoreImpl::_ReApplyDirectoryTimesA"...
0x18002c664  lea     rcx, [rsp+160h+var_120]; this
0x18002c669  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002c66e  xor     r14d, r14d
0x18002c671  mov     [rbp+60h+var_A8], r14d
0x18002c675  xorps   xmm0, xmm0
0x18002c678  movdqu  xmmword ptr [rbp+60h+var_A0], xmm0
0x18002c67d  mov     [rbp+60h+var_B8], r14
0x18002c681  mov     [rbp+60h+var_C0], r14
0x18002c685  mov     qword ptr [rbp+60h+LastAccessTime.dwLowDateTime], r14
0x18002c689  mov     qword ptr [rbp+60h+LastWriteTime.dwLowDateTime], r14
0x18002c68d  mov     qword ptr [rbp+60h+CreationTime.dwLowDateTime], r14
0x18002c691  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c695  lea     rax, qword_1800EE510
0x18002c69c  mov     [rbp+60h+lpFileName], rax
0x18002c6a0  mov     [rbp+60h+var_D0], r14
0x18002c6a4  mov     [rbp+60h+var_58], rax
0x18002c6a8  mov     [rbp+60h+var_50], r14
0x18002c6ac  mov     [rbp+60h+var_68], rax
0x18002c6b0  mov     [rbp+60h+var_60], r14
0x18002c6b4  mov     [rbp+60h+var_78], rax
0x18002c6b8  mov     [rbp+60h+var_70], r14
0x18002c6bc  mov     [rsp+160h+var_E8], r14
0x18002c6c1  lea     rcx, [rbp+60h+var_B0]; void *
0x18002c6c5  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18002c6ca  mov     r15d, r14d
0x18002c6cd  mov     [rbp+60h+arg_8], r14d
0x18002c6d1  mov     [rbp+60h+var_48], r14
0x18002c6d5  mov     [rbp+60h+var_C8], r14d
0x18002c6d9  mov     [rbp+60h+bDaclPresent], r14d
0x18002c6e0  mov     [rbp+60h+bDaclDefaulted], r14d
0x18002c6e4  mov     [rbp+60h+pDacl], r14
0x18002c6e8  mov     eax, 1015h
0x18002c6ed  test    r12, r12
0x18002c6f0  jnz     short loc_18002C704
0x18002c6f2  mov     [rsp+160h+var_120], 80070057h
0x18002c6fa  mov     [rsp+160h+var_11A], ax
0x18002c6ff  jmp     loc_18002CC28
0x18002c704  mov     [rsp+160h+var_11C], ax
0x18002c709  mov     eax, 1016h
0x18002c70e  test    rbx, rbx
0x18002c711  jz      short loc_18002C6F2
0x18002c713  mov     [rsp+160h+var_120], r14d
0x18002c718  mov     [rsp+160h+var_11C], ax
0x18002c71d  test    byte ptr [r13+180h], 4
0x18002c725  jz      short loc_18002C731
0x18002c727  mov     eax, 101Ah
0x18002c72c  jmp     loc_18002CC23
0x18002c731  mov     rax, [r13+198h]
0x18002c738  test    rax, rax
0x18002c73b  jnz     short loc_18002C744
0x18002c73d  mov     eax, 101Dh
0x18002c742  jmp     short loc_18002C6F2
0x18002c744  mov     [rbp+60h+var_A0], rax
0x18002c748  lock inc dword ptr [rax+18h]
0x18002c74c  mov     rax, [rbp+60h+var_A0]
0x18002c750  mov     ecx, [rax+10h]
0x18002c753  mov     [rbp+60h+var_A8], ecx
0x18002c756  mov     [rbp+60h+var_A0+8], r14
0x18002c75a  mov     [rsp+160h+var_120], r14d
0x18002c75f  mov     eax, 101Dh
0x18002c764  mov     [rsp+160h+var_11C], ax
0x18002c769  lea     rdx, [rsp+160h+var_E8]
0x18002c76e  lea     rcx, [rbp+60h+var_A8]
0x18002c772  call    ?Next@CSxIter@?$CSxRefMap@VCSdFileMap@@VCSdFileEntry@@@@QEAAJPEAPEAVCSdFileEntry@@@Z; CSxRefMap<CSdFileMap,CSdFileEntry>::CSxIter::Next(CSdFileEntry * *)
0x18002c777  mov     [rsp+160h+var_120], eax
0x18002c77b  mov     ecx, 101Eh
0x18002c780  test    eax, eax
0x18002c782  jns     short loc_18002C78E
0x18002c784  mov     [rsp+160h+var_11A], cx
0x18002c789  jmp     loc_18002CC28
0x18002c78e  mov     esi, 1030h
0x18002c793  lea     ebx, [rsi-0Fh]
0x18002c796  mov     [rsp+160h+var_11C], cx
0x18002c79b  cmp     eax, 1
0x18002c79e  jz      loc_18002CC19
0x18002c7a4  mov     qword ptr [rsp+160h+dwCreationDisposition], r14; unsigned __int16 **
0x18002c7a9  xor     r9d, r9d; unsigned int
0x18002c7ac  mov     r8d, 4E90h; unsigned int
0x18002c7b2  mov     rdx, cs:hInstance; HINSTANCE
0x18002c7b9  lea     rcx, [rsp+160h+var_120]; this
0x18002c7be  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002c7c3  mov     [rsp+160h+var_120], eax
0x18002c7c7  test    eax, eax
0x18002c7c9  js      loc_18002CC12
0x18002c7cf  mov     [rsp+160h+var_11C], bx
0x18002c7d4  mov     rdx, [rsp+160h+var_E8]
0x18002c7d9  add     rdx, 18h
0x18002c7dd  lea     rcx, [rbp+60h+var_B0]
0x18002c7e1  call    ??4?$CComPtr@UISdGlobalCatalog@@@ATL@@QEAAPEAUISdGlobalCatalog@@AEBV01@@Z; ATL::CComPtr<ISdGlobalCatalog>::operator=(ATL::CComPtr<ISdGlobalCatalog> const &)
0x18002c7e6  mov     rax, [r12]
0x18002c7ea  mov     rcx, r12
0x18002c7ed  mov     rax, [rax+78h]
0x18002c7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7f6  mov     [rsp+160h+var_120], eax
0x18002c7fa  test    eax, eax
0x18002c7fc  lea     eax, [rsi-0Bh]
0x18002c7ff  js      loc_18002C6FA
0x18002c805  mov     [rsp+160h+var_11C], ax
0x18002c80a  lea     rcx, [rbp+60h+var_C0]; unsigned __int16 **
0x18002c80e  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18002c813  lea     rcx, [rbp+60h+var_B8]; unsigned __int16 **
0x18002c817  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18002c81c  mov     rbx, [rbp+60h+var_B0]
0x18002c820  mov     rax, [rbx]
0x18002c823  lea     rdx, [rbp+60h+var_C0]
0x18002c827  mov     rcx, rbx
0x18002c82a  mov     rax, [rax+20h]
0x18002c82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c833  mov     [rsp+160h+var_120], eax
0x18002c837  test    eax, eax
0x18002c839  lea     eax, [rsi-7]
0x18002c83c  js      loc_18002C6FA
0x18002c842  mov     [rsp+160h+var_11C], ax
0x18002c847  mov     rax, [rbx]
0x18002c84a  lea     rdx, [rbp+60h+var_B8]
0x18002c84e  mov     rcx, rbx
0x18002c851  mov     rax, [rax+18h]
0x18002c855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c85a  mov     [rsp+160h+var_120], eax
0x18002c85e  test    eax, eax
0x18002c860  lea     eax, [rsi-6]
0x18002c863  js      loc_18002C6FA
0x18002c869  mov     [rsp+160h+var_11C], ax
0x18002c86e  lea     rax, [rbp+60h+var_78]
0x18002c872  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; struct CBsString *
0x18002c877  lea     r9, [rbp+60h+var_68]; struct CBsString *
0x18002c87b  lea     r8, [rbp+60h+var_58]; struct CBsString *
0x18002c87f  mov     rdx, rbx; struct ISdFileRecord *
0x18002c882  mov     rcx, r13; this
0x18002c885  call    ?_BuildDestinationStrings@CSdRestoreImpl@@AEAAJPEAUISdFileRecord@@PEAVCBsString@@11@Z; CSdRestoreImpl::_BuildDestinationStrings(ISdFileRecord *,CBsString *,CBsString *,CBsString *)
0x18002c88a  mov     [rsp+160h+var_120], eax
0x18002c88e  test    eax, eax
0x18002c890  lea     eax, [rsi-4]
0x18002c893  js      loc_18002C6FA
0x18002c899  mov     [rsp+160h+var_11C], ax
0x18002c89e  mov     r9, [rbp+60h+var_78]; unsigned __int16 *
0x18002c8a2  mov     r8, [rbp+60h+var_68]; unsigned __int16 *
0x18002c8a6  mov     rdx, [rbp+60h+var_58]; unsigned __int16 *
0x18002c8aa  lea     rcx, [rbp+60h+lpFileName]; this
0x18002c8ae  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x18002c8b3  mov     [rsp+160h+var_120], eax
0x18002c8b7  test    eax, eax
0x18002c8b9  lea     eax, [rsi-2]
0x18002c8bc  js      loc_18002C6FA
0x18002c8c2  mov     [rsp+160h+var_11C], ax
0x18002c8c7  mov     rax, [rbp+60h+lpFileName]
0x18002c8cb  mov     [rbp+60h+pSecurityDescriptor], rax
0x18002c8cf  lea     rax, [rbp+60h+pSecurityDescriptor]
0x18002c8d3  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; unsigned __int16 **
0x18002c8d8  mov     r9d, 1; unsigned int
0x18002c8de  mov     r8d, 4E91h; unsigned int
0x18002c8e4  mov     rdx, cs:hInstance; HINSTANCE
0x18002c8eb  lea     rcx, [rsp+160h+var_120]; this
0x18002c8f0  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18002c8f5  mov     [rsp+160h+var_120], eax
0x18002c8f9  test    eax, eax
0x18002c8fb  js      loc_18002CC0B
0x18002c901  mov     [rsp+160h+var_11C], si
0x18002c906  lea     rcx, [rbp+60h+lpFileName]; this
0x18002c90a  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18002c90f  mov     [rsp+160h+var_120], eax
0x18002c913  test    eax, eax
0x18002c915  lea     eax, [rsi+2]
0x18002c918  js      loc_18002C6FA
0x18002c91e  mov     [rsp+160h+var_11C], ax
0x18002c923  mov     [rsp+160h+hTemplateFile], r14; hTemplateFile
0x18002c928  mov     [rsp+160h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002c930  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c938  xor     r9d, r9d; lpSecurityAttributes
0x18002c93b  mov     edx, 140180h; dwDesiredAccess
0x18002c940  lea     r8d, [r9+7]; dwShareMode
0x18002c944  mov     r14, [rbp+60h+lpFileName]
0x18002c948  mov     rcx, r14; lpFileName
0x18002c94b  call    cs:__imp_CreateFileW
0x18002c952  nop     dword ptr [rax+rax+00h]
0x18002c957  mov     rsi, rax
0x18002c95a  lea     rcx, [rdi-1]
0x18002c95e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c962  ja      short loc_18002C973
0x18002c964  mov     rcx, rdi; hObject
0x18002c967  call    cs:__imp_CloseHandle
0x18002c96e  nop     dword ptr [rax+rax+00h]
0x18002c973  mov     rdi, rsi
0x18002c976  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002c97a  jnz     short loc_18002C9C5
0x18002c97c  call    GetLastFailureAsHRESULT
0x18002c981  mov     [rsp+160h+var_120], eax
0x18002c985  lea     rdx, WPP_GLOBAL_Control
0x18002c98c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c993  cmp     rcx, rdx
0x18002c996  jz      short loc_18002C9B8
0x18002c998  test    byte ptr [rcx+1Ch], 80h
0x18002c99c  jz      short loc_18002C9B8
0x18002c99e  lea     edx, [rsi+56h]
0x18002c9a1  mov     [rsp+160h+dwCreationDisposition], eax
0x18002c9a5  mov     r9, r14
0x18002c9a8  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002c9af  mov     rcx, [rcx+10h]
0x18002c9b3  call    WPP_SF_Sd
0x18002c9b8  xor     r14d, r14d
0x18002c9bb  mov     [rsp+160h+var_120], r14d
0x18002c9c0  jmp     loc_18002CB8F
0x18002c9c5  mov     rax, [rbx]
0x18002c9c8  lea     rdx, [rbp+60h+CreationTime]
0x18002c9cc  mov     rcx, rbx
0x18002c9cf  mov     rax, [rax+40h]
0x18002c9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9d8  mov     [rsp+160h+var_120], eax
0x18002c9dc  test    eax, eax
0x18002c9de  mov     eax, 103Dh
0x18002c9e3  js      loc_18002CC01
0x18002c9e9  mov     [rsp+160h+var_11C], ax
0x18002c9ee  mov     rax, [rbx]
0x18002c9f1  lea     rdx, [rbp+60h+LastAccessTime]
0x18002c9f5  mov     rcx, rbx
0x18002c9f8  mov     rax, [rax+78h]
0x18002c9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca01  mov     [rsp+160h+var_120], eax
0x18002ca05  test    eax, eax
0x18002ca07  mov     eax, 103Eh
0x18002ca0c  js      loc_18002CC01
0x18002ca12  mov     [rsp+160h+var_11C], ax
0x18002ca17  mov     rax, [rbx]
0x18002ca1a  lea     rdx, [rbp+60h+LastWriteTime]
0x18002ca1e  mov     rcx, rbx
0x18002ca21  mov     rax, [rax+48h]
0x18002ca25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca2a  mov     [rsp+160h+var_120], eax
0x18002ca2e  test    eax, eax
0x18002ca30  mov     eax, 103Fh
0x18002ca35  js      loc_18002CC01
0x18002ca3b  mov     [rsp+160h+var_11C], ax
0x18002ca40  lea     r9, [rbp+60h+LastWriteTime]; lpLastWriteTime
0x18002ca44  lea     r8, [rbp+60h+LastAccessTime]; lpLastAccessTime
0x18002ca48  lea     rdx, [rbp+60h+CreationTime]; lpCreationTime
0x18002ca4c  mov     rcx, rsi; hFile
0x18002ca4f  call    cs:__imp_SetFileTime
0x18002ca56  nop     dword ptr [rax+rax+00h]
0x18002ca5b  test    eax, eax
0x18002ca5d  jz      loc_18002CBF3
0x18002ca63  mov     [rsp+160h+var_120], 0
0x18002ca6b  mov     eax, 1042h
0x18002ca70  mov     [rsp+160h+var_11C], ax
0x18002ca75  cmp     dword ptr [r13+38h], 0Bh
0x18002ca7a  jnz     loc_18002CB74
0x18002ca80  cmp     dword ptr [rbp+60h+var_D0], 2
0x18002ca84  jb      short loc_18002CA9F
0x18002ca86  mov     eax, dword ptr [rbp+60h+var_D0]
0x18002ca89  cmp     word ptr [r14+rax*2-2], 2Eh ; '.'
0x18002ca90  jnz     short loc_18002CA9F
0x18002ca92  cmp     word ptr [r14+rax*2-4], 5Ch ; '\'
0x18002ca99  jz      loc_18002CB74
0x18002ca9f  mov     rcx, r15; pv
0x18002caa2  call    cs:__imp_CoTaskMemFree
0x18002caa9  nop     dword ptr [rax+rax+00h]
0x18002caae  xor     r14d, r14d
0x18002cab1  mov     [rbp+60h+pSecurityDescriptor], r14
0x18002cab5  lea     rax, [rbp+60h+var_C8]
0x18002cab9  mov     [rsp+160h+hTemplateFile], rax; unsigned int *
0x18002cabe  lea     rax, [rbp+60h+var_48]
0x18002cac2  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x18002cac7  lea     rax, [rbp+60h+arg_8]
0x18002cacb  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; unsigned int *
0x18002cad0  lea     r9, [rbp+60h+pSecurityDescriptor]; unsigned __int8 **
0x18002cad4  xor     r8d, r8d; int
0x18002cad7  mov     rdx, rbx; struct ISdFileRecord *
0x18002cada  mov     rcx, [r13+210h]; pSid
0x18002cae1  call    ?GetRelativeSDFromFileRecordForUserModeRestore@@YAJPEBU_SID@@PEAUISdFileRecord@@HPEAPEAEPEAK23@Z; GetRelativeSDFromFileRecordForUserModeRestore(_SID const *,ISdFileRecord *,int,uchar * *,ulong *,uchar * *,ulong *)
0x18002cae6  mov     [rsp+160h+var_120], eax
0x18002caea  mov     r15, [rbp+60h+pSecurityDescriptor]
0x18002caee  test    eax, eax
0x18002caf0  mov     eax, 104Ch
0x18002caf5  js      loc_18002C6FA
0x18002cafb  mov     [rsp+160h+var_11C], ax
0x18002cb00  test    r15, r15
0x18002cb03  jz      short loc_18002CB77
0x18002cb05  cmp     [rbp+60h+arg_8], r14d
0x18002cb09  jz      short loc_18002CB77
0x18002cb0b  lea     r9, [rbp+60h+bDaclDefaulted]; lpbDaclDefaulted
0x18002cb0f  lea     r8, [rbp+60h+pDacl]; pDacl
0x18002cb13  lea     rdx, [rbp+60h+bDaclPresent]; lpbDaclPresent
0x18002cb1a  mov     rcx, r15; pSecurityDescriptor
0x18002cb1d  call    cs:__imp_GetSecurityDescriptorDacl
0x18002cb24  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
