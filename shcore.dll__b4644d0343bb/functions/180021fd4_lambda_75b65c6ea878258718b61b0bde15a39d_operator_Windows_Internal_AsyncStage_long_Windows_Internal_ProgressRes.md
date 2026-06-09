# _lambda_75b65c6ea878258718b61b0bde15a39d_::operator()(Windows::Internal::AsyncStage,long,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IBuffer>,uint> &)

- ea: `0x180021fd4`
- end: `0x1800228d4`
- name: `??R_lambda_75b65c6ea878258718b61b0bde15a39d_@@QEAAJW4AsyncStage@Internal@Windows@@JAEAV?$ProgressResult@V?$CMarshaledInterfaceResult@UIBuffer@Streams@Storage@Windows@@@Internal@Windows@@I@23@@Z`
- size: `2304`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023750`

## callees

- `0x18000ddd4`
- `0x18000f900`
- `0x180021fd4`
- `0x180022c90`
- `0x1800231ac`
- `0x18002329c`
- `0x1800233b4`
- `0x1800234a0`
- `0x180023730`
- `0x1800246dc`
- `0x180031cb0`
- `0x180031d3c`
- `0x1800357c0`
- `0x180040500`
- `0x180041434`
- `0x18004a2dc`
- `0x180051914`
- `0x1800647a4`
- `0x180066cfc`
- `0x1800672e8`
- `0x18006d8cc`
- `0x180072978`
- `0x18007a03c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022274`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022274`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800222a0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800222a0`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002246c`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002246c`

## string_xrefs

- `0x180022014`: `ReadAsyncPriv.NonCached.MakeAsyncOperationWithProgress`
- `0x180022062`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x180022691`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall _lambda_75b65c6ea878258718b61b0bde15a39d_::operator()(bool *a1, int a2, signed int a3, __int64 a4)
{
  __int64 v7; // rdi
  int ShouldContinue; // eax
  int v9; // eax
  CFileInputStream *v10; // rcx
  __int64 v11; // rdx
  CRasFilePlaceholderParams *v12; // rcx
  DWORD v13; // r15d
  __int64 v14; // rdx
  CRasFilePlaceholderParams *v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, struct IFileHandle **); // rbx
  wil::details::in1diag3 *v18; // rcx
  int v19; // eax
  CFileInputStream *v20; // rdx
  void *v21; // rdi
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  void *v24; // rcx
  struct _OVERLAPPED *v25; // rbx
  void *v26; // r13
  BOOL File; // eax
  signed int v28; // eax
  BOOL OverlappedResult; // eax
  DWORD v30; // ecx
  __int64 v31; // rax
  struct IFileHandle *v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // ebx
  CFileInputStream *v35; // rdi
  __int64 v36; // rcx
  __int64 v37; // rdi
  __int64 v38; // rcx
  void *v40; // rcx
  int ValidSizeOfTransactedCopy; // eax
  wil::details::in1diag3 *v42; // rcx
  __int64 v43; // rcx
  DWORD v44; // eax
  HANDLE *v45; // r15
  int v46; // eax
  DWORD v47; // edi
  int v48; // eax
  wil::details::in1diag3 *v49; // rcx
  int v50; // eax
  unsigned __int64 v51; // rdx
  unsigned int v52; // ecx
  __int64 v53; // rdx
  unsigned int v54; // eax
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, _QWORD, struct IFileHandle **); // rbx
  unsigned __int64 v57; // r9
  __int64 v58; // rdx
  int v59; // eax
  unsigned __int64 v60; // rax
  unsigned __int64 v61; // r9
  __int64 v62; // rdx
  unsigned __int64 v63; // r9
  __int64 v64; // rdx
  int lpOverlapped; // [rsp+20h] [rbp-79h]
  struct IFileHandle *v66; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int64 v67; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int64 v68[2]; // [rsp+60h] [rbp-39h] BYREF
  int v69; // [rsp+70h] [rbp-29h] BYREF
  const char *v70; // [rsp+78h] [rbp-21h]
  __int64 v71; // [rsp+80h] [rbp-19h]
  char v72; // [rsp+88h] [rbp-11h]
  _QWORD v73[3]; // [rsp+90h] [rbp-9h] BYREF
  int v74; // [rsp+A8h] [rbp+Fh]
  int *v75; // [rsp+B0h] [rbp+17h]
  char v76; // [rsp+B8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  DWORD lpNumberOfBytesTransferred; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+110h] [rbp+77h] BYREF
  __int64 v80; // [rsp+118h] [rbp+7Fh]

  v80 = a4;
  v72 = 0;
  v69 = 0;
  v70 = "ReadAsyncPriv.NonCached.MakeAsyncOperationWithProgress";
  v71 = 0;
  v73[0] = 0;
  v73[1] = wil::details::static_lazy<StreamLibTelemetry>::get(
             a1,
             _lambda_f1899c0dfb02606298aff509d6a6be83_::_lambda_invoker_cdecl_);
  v73[2] = 0;
  v74 = 0;
  v75 = &v69;
  v76 = 0;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v73);
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      lpNumberOfBytesTransferred = 0;
      if ( a3 == -2147023673 )
        goto LABEL_68;
      if ( a3 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x537,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
          (const char *)(unsigned int)a3,
          lpOverlapped);
LABEL_65:
        if ( a3 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5EE,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)(unsigned int)a3,
            lpOverlapped);
        else
          *(_QWORD *)(*(_QWORD *)a1 + 216LL) += lpNumberOfBytesTransferred;
LABEL_68:
        _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)a1 + 168LL), 0, 1);
        v43 = *((_QWORD *)a1 + 10);
        if ( v43 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 24LL))(
            v43,
            (unsigned int)a3,
            lpNumberOfBytesTransferred);
        goto LABEL_56;
      }
      v7 = *((_QWORD *)a1 + 3);
      ShouldContinue = CRasFilePlaceholderParams::s_ShouldContinue(
                         a1[64],
                         *(struct CRasFilePlaceholderParams **)(*(_QWORD *)a1 + 248LL));
      a3 = ShouldContinue;
      if ( ShouldContinue < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x53A,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
          (const char *)(unsigned int)ShouldContinue,
          lpOverlapped);
        v67 = 0;
        goto LABEL_67;
      }
      if ( *((_QWORD *)a1 + 5) )
      {
        v66 = 0;
        v9 = CMarshaledInterface::Unmarshal<ISyncedStreamReaderInfo>((CMarshaledInterface *)(a1 + 40), (void **)&v66);
        a3 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x53E,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)(unsigned int)v9,
            lpOverlapped);
        }
        else
        {
          a3 = (*(__int64 (__fastcall **)(struct IFileHandle *, __int64))(*(_QWORD *)v66 + 32LL))(
                 v66,
                 v7 + *((unsigned int *)a1 + 5));
          if ( a3 >= 0 )
            a3 = CRasFilePlaceholderParams::s_ShouldContinue(
                   a1[64],
                   *(struct CRasFilePlaceholderParams **)(*(_QWORD *)a1 + 248LL));
        }
        if ( a3 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x543,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)(unsigned int)a3,
            lpOverlapped);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v66);
        v67 = 0;
        if ( a3 < 0 )
          goto LABEL_67;
      }
      else
      {
        v67 = 0;
      }
      v10 = *(CFileInputStream **)a1;
      if ( *(_DWORD *)(*(_QWORD *)a1 + 204LL) != 1 )
        goto LABEL_14;
      v68[0] = 0;
      ValidSizeOfTransactedCopy = CFileInputStream::_GetValidSizeOfTransactedCopy(v10, v68, &v67);
      a3 = ValidSizeOfTransactedCopy;
      v42 = retaddr;
      if ( ValidSizeOfTransactedCopy < 0 )
      {
        v53 = 1361;
LABEL_97:
        wil::details::in1diag3::_Log_Hr(
          v42,
          (void *)v53,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
          (const char *)(unsigned int)ValidSizeOfTransactedCopy,
          lpOverlapped);
        goto LABEL_67;
      }
      v51 = *((_QWORD *)a1 + 3);
      if ( v67 <= v51 )
        v52 = 0;
      else
        v52 = v67 - v51;
      v54 = *((_DWORD *)a1 + 5);
      if ( v54 >= v52 )
        v54 = v52;
      *((_DWORD *)a1 + 5) = v54;
      if ( v51 >= v68[0] )
      {
LABEL_14:
        if ( (unsigned __int8)anonymous_namespace_::_HasRemoteStream(*(_QWORD *)(*(_QWORD *)a1 + 248LL)) )
        {
          a3 = CRasFilePlaceholderParams::WriteFullContentsIntoFileIfRequired(
                 v12,
                 *(struct ISafeSaveHandleManager **)(v11 + 184),
                 (struct _OVERLAPPED *)(v11 + 136),
                 a1 + 64);
          if ( a3 < 0 )
            goto LABEL_67;
        }
        v13 = 0x10000;
        v68[0] = 0x10000;
        if ( (unsigned __int8)anonymous_namespace_::_HasRemoteStream(*(_QWORD *)(*(_QWORD *)a1 + 248LL)) )
        {
          v59 = CRasFilePlaceholderParams::ReadUsingRemoteStream(
                  v15,
                  *(struct ISafeSaveHandleManager **)(v14 + 184),
                  *((unsigned __int8 **)a1 + 1),
                  *((_DWORD *)a1 + 4),
                  *((_DWORD *)a1 + 5),
                  *((_QWORD *)a1 + 3),
                  v68,
                  &lpNumberOfBytesTransferred,
                  (struct _OVERLAPPED *)(v14 + 136),
                  a1 + 64);
          a3 = v59;
          if ( v59 != -2147024883 )
          {
            if ( v59 < 0 )
              goto LABEL_67;
            goto LABEL_63;
          }
          v60 = v68[0];
          if ( v68[0] >= 0x10000 )
            v60 = 0x10000;
          v13 = v60;
          if ( !v60 )
          {
            operator delete(*(void **)(*(_QWORD *)a1 + 224LL), (const struct std::nothrow_t *)1);
            *(_QWORD *)(*(_QWORD *)a1 + 224LL) = 0;
          }
        }
        else if ( a3 < 0 )
        {
          goto LABEL_67;
        }
        if ( !*((_DWORD *)a1 + 5) )
        {
LABEL_37:
          v33 = *((_DWORD *)a1 + 5);
          if ( v33 && *((_QWORD *)a1 + 3) < v67 )
          {
            if ( v33 >= (int)v67 - *((_DWORD *)a1 + 6) )
              v33 = v67 - *((_DWORD *)a1 + 6);
            v34 = v33;
            memset_0(*((void **)a1 + 1), 0, v33);
            lpNumberOfBytesTransferred += v34;
          }
LABEL_63:
          ValidSizeOfTransactedCopy = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 11) + 64LL))(*((_QWORD *)a1 + 11));
          a3 = ValidSizeOfTransactedCopy;
          v42 = retaddr;
          if ( ValidSizeOfTransactedCopy >= 0 )
          {
            Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IBuffer>::Set(
              v80 + 8,
              *((_QWORD *)a1 + 11));
            goto LABEL_65;
          }
          v53 = 1507;
          goto LABEL_97;
        }
        v66 = 0;
        v16 = *(_QWORD *)(*(_QWORD *)a1 + 184LL);
        v17 = *(__int64 (__fastcall **)(__int64, struct IFileHandle **))(*(_QWORD *)v16 + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v66);
        a3 = v17(v16, &v66);
        if ( a3 >= 0 )
          a3 = CRasFilePlaceholderParams::s_ShouldContinue(
                 a1[64],
                 *(struct CRasFilePlaceholderParams **)(*(_QWORD *)a1 + 248LL));
        v18 = retaddr;
        if ( a3 < 0 )
        {
          v61 = (unsigned int)a3;
          v62 = 1451;
        }
        else
        {
          v19 = LockHandle(v66, (void **)a1 + 7);
          a3 = v19;
          v18 = retaddr;
          if ( v19 >= 0 )
          {
            v20 = *(CFileInputStream **)a1;
            v21 = *(void **)(*(_QWORD *)a1 + 224LL);
            if ( !v21 )
            {
              v21 = (void *)*((_QWORD *)a1 + 1);
              v13 = *((_DWORD *)a1 + 5);
            }
            NumberOfBytesTransferred = 0;
            v22 = CRasFilePlaceholderParams::s_ShouldContinue(a1[64], *((struct CRasFilePlaceholderParams **)v20 + 31));
            a3 = v22;
            v23 = retaddr;
            if ( v22 < 0 )
            {
              v63 = (unsigned int)v22;
              v64 = 1463;
            }
            else
            {
              v24 = (void *)*((_QWORD *)a1 + 3);
              v25 = (struct _OVERLAPPED *)(*(_QWORD *)a1 + 136LL);
              v26 = (void *)*((_QWORD *)a1 + 7);
              NumberOfBytesTransferred = 0;
              v25->Pointer = v24;
              File = ReadFile(v26, v21, v13, 0, v25);
              v28 = ResultFromWin32Bool(File);
              if ( (int)(v28 + 0x80000000) < 0 || v28 == -2147023899 )
              {
                OverlappedResult = GetOverlappedResult(v26, v25, &NumberOfBytesTransferred, 1);
                v28 = ResultFromWin32Bool(OverlappedResult);
              }
              a3 = 0;
              if ( v28 != -2147024858 )
                a3 = v28;
              v23 = retaddr;
              if ( a3 >= 0 )
              {
                if ( *(_QWORD *)(*(_QWORD *)a1 + 224LL) )
                {
                  *(_QWORD *)(*(_QWORD *)a1 + 240LL) = *(_QWORD *)(*(_QWORD *)a1 + 232LL) + NumberOfBytesTransferred;
                  v44 = NumberOfBytesTransferred;
                  if ( NumberOfBytesTransferred >= *((_DWORD *)a1 + 5) )
                  {
                    v44 = *((_DWORD *)a1 + 5);
                    NumberOfBytesTransferred = v44;
                  }
                  memcpy_s_2(
                    *((void *const *)a1 + 1),
                    *((unsigned int *)a1 + 4),
                    *(const void *const *)(*(_QWORD *)a1 + 224LL),
                    v44);
                }
                v30 = NumberOfBytesTransferred;
                lpNumberOfBytesTransferred += NumberOfBytesTransferred;
                v31 = NumberOfBytesTransferred;
                *((_QWORD *)a1 + 3) += NumberOfBytesTransferred;
                *((_QWORD *)a1 + 1) += v31;
                *((_DWORD *)a1 + 5) -= v30;
                goto LABEL_33;
              }
              v63 = (unsigned int)a3;
              v64 = 1467;
            }
            wil::details::in1diag3::_Log_Hr(
              v23,
              (void *)v64,
              (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
              (const char *)v63,
              lpOverlapped);
LABEL_33:
            *((_QWORD *)a1 + 7) = -1;
            (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v66 + 32LL))(v66);
            goto LABEL_34;
          }
          v61 = (unsigned int)v19;
          v62 = 1456;
        }
        wil::details::in1diag3::_Log_Hr(
          v18,
          (void *)v62,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
          (const char *)v61,
          lpOverlapped);
LABEL_34:
        v32 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v32 + 16LL))(v32);
        }
        if ( a3 >= 0 )
          goto LABEL_37;
LABEL_67:
        if ( a3 == -2147023673 )
          goto LABEL_68;
        goto LABEL_65;
      }
      v66 = 0;
      v55 = *(_QWORD *)(*(_QWORD *)a1 + 184LL);
      v56 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IFileHandle **))(*(_QWORD *)v55 + 32LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v66);
      a3 = v56(v55, *(unsigned int *)(*(_QWORD *)a1 + 204LL), &v66);
      if ( a3 >= 0 )
        a3 = CRasFilePlaceholderParams::s_ShouldContinue(
               a1[64],
               *(struct CRasFilePlaceholderParams **)(*(_QWORD *)a1 + 248LL));
      if ( a3 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x55E,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
          (const char *)(unsigned int)a3,
          lpOverlapped);
      }
      else
      {
        v45 = (HANDLE *)(a1 + 56);
        v46 = LockHandle(v66, (void **)a1 + 7);
        a3 = v46;
        if ( v46 >= 0 )
        {
          v47 = *((_DWORD *)a1 + 5);
          if ( v47 >= LODWORD(v68[0]) - *((_DWORD *)a1 + 6) )
            v47 = LODWORD(v68[0]) - *((_DWORD *)a1 + 6);
          v48 = CRasFilePlaceholderParams::s_ShouldContinue(
                  a1[64],
                  *(struct CRasFilePlaceholderParams **)(*(_QWORD *)a1 + 248LL));
          a3 = v48;
          v49 = retaddr;
          if ( v48 < 0 )
          {
            v57 = (unsigned int)v48;
            v58 = 1383;
          }
          else
          {
            v50 = ReadFromFile(*v45, (LPOVERLAPPED)(*(_QWORD *)a1 + 136LL), v47, &lpNumberOfBytesTransferred);
            a3 = v50;
            v49 = retaddr;
            if ( v50 < 0 )
            {
              v57 = (unsigned int)v50;
              v58 = 1387;
            }
            else
            {
              a3 = v47 != lpNumberOfBytesTransferred ? 0x8000FFFF : 0;
              v49 = retaddr;
              if ( v47 == lpNumberOfBytesTransferred )
              {
                *((_QWORD *)a1 + 3) += v47;
                *((_QWORD *)a1 + 1) += v47;
                *((_DWORD *)a1 + 5) -= v47;
LABEL_85:
                *v45 = (HANDLE)-1LL;
                (*(void (__fastcall **)(struct IFileHandle *))(*(_QWORD *)v66 + 32LL))(v66);
                goto LABEL_86;
              }
              v57 = (unsigned int)a3;
              v58 = 1390;
            }
          }
          wil::details::in1diag3::_Log_Hr(
            v49,
            (void *)v58,
            (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
            (const char *)v57,
            lpOverlapped);
          goto LABEL_85;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x563,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
          (const char *)(unsigned int)v46,
          lpOverlapped);
      }
LABEL_86:
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v66);
      if ( a3 < 0 )
        goto LABEL_67;
      goto LABEL_14;
    }
    if ( a2 == 2 )
    {
      v40 = (void *)*((_QWORD *)a1 + 7);
      if ( v40 != (void *)-1LL )
        CancelIoEx(v40, (LPOVERLAPPED)(*(_QWORD *)a1 + 136LL));
      a1[64] = 1;
    }
  }
  else if ( a3 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x519,
      (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
      (const char *)(unsigned int)a3,
      lpOverlapped);
  }
  else
  {
    v35 = *(CFileInputStream **)a1;
    if ( *((_QWORD *)a1 + 6) != *(_QWORD *)a1 )
    {
      if ( v35 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 8LL))(*(_QWORD *)a1);
      v36 = *((_QWORD *)a1 + 6);
      *((_QWORD *)a1 + 6) = v35;
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::operator=(a1 + 40, *(_QWORD *)a1 + 192LL);
    v37 = *((_QWORD *)a1 + 9);
    if ( *((_QWORD *)a1 + 10) != v37 )
    {
      if ( v37 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37 + 8LL))(*((_QWORD *)a1 + 9));
      v38 = *((_QWORD *)a1 + 10);
      *((_QWORD *)a1 + 10) = v37;
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    Microsoft::WRL::ComPtr<IRWLock>::operator=(a1 + 88, *((_QWORD *)a1 + 4));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)a1 + 168LL), 1, 0) )
      a3 = -2147483636;
    else
      CFileInputStream::_SetupCache(*(CFileInputStream **)a1, *((_DWORD *)a1 + 5));
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(*((Microsoft::WRL::Wrappers::Details::SyncLockExclusive **)a1
                                                                         + 12));
  }
LABEL_56:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v69);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x180021fd4  mov     [rsp-8+arg_0], rbx
0x180021fd9  mov     [rsp-8+arg_18], r9
0x180021fde  push    rbp
0x180021fdf  push    rsi
0x180021fe0  push    rdi
0x180021fe1  push    r12
0x180021fe3  push    r13
0x180021fe5  push    r14
0x180021fe7  push    r15
0x180021fe9  lea     rbp, [rsp-27h]
0x180021fee  sub     rsp, 0C0h
0x180021ff5  mov     ebx, r8d
0x180021ff8  mov     edi, edx
0x180021ffa  mov     rsi, rcx
0x180021ffd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f1899c0dfb02606298aff509d6a6be83_@@CA@XZ; _lambda_f1899c0dfb02606298aff509d6a6be83_::_lambda_invoker_cdecl_(void)
0x180022004  call    ?get@?$static_lazy@VStreamLibTelemetry@@@details@wil@@QEAAPEAVStreamLibTelemetry@@P6AXXZ@Z; wil::details::static_lazy<StreamLibTelemetry>::get(void (*)(void))
0x180022009  xor     r15d, r15d
0x18002200c  mov     [rbp+57h+var_68], r15b
0x180022010  mov     [rbp+57h+var_80], r15d
0x180022014  lea     rcx, aReadasyncprivN; "ReadAsyncPriv.NonCached.MakeAsyncOperat"...
0x18002201b  mov     [rbp+57h+var_78], rcx
0x18002201f  mov     [rbp+57h+var_70], r15
0x180022023  mov     [rbp+57h+var_60], r15
0x180022027  mov     [rbp+57h+var_58], rax
0x18002202b  mov     [rbp+57h+var_50], r15
0x18002202f  mov     [rbp+57h+var_48], r15d
0x180022033  lea     rax, [rbp+57h+var_80]
0x180022037  mov     [rbp+57h+var_40], rax
0x18002203b  mov     [rbp+57h+var_38], r15b
0x18002203f  lea     rcx, [rbp+57h+var_60]; this
0x180022043  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180022048  nop
0x180022049  test    edi, edi
0x18002204b  jz      loc_180022363
0x180022051  lea     r12d, [r15+1]
0x180022055  cmp     edi, r12d
0x180022058  jnz     loc_180022453
0x18002205e  mov     [rbp+57h+arg_8], r15d
0x180022062  lea     r14, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x180022069  cmp     ebx, 800704C7h
0x18002206f  jz      loc_1800224DD
0x180022075  mov     rcx, [rbp+5Fh]; this
0x180022079  test    ebx, ebx
0x18002207b  js      loc_1800226A7
0x180022081  mov     rdi, [rsi+18h]
0x180022085  mov     rax, [rsi]
0x180022088  mov     rdx, [rax+0F8h]; struct CRasFilePlaceholderParams *
0x18002208f  lea     r13, [rsi+40h]
0x180022093  mov     cl, [r13+0]; bool
0x180022097  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x18002209c  mov     ebx, eax
0x18002209e  mov     rcx, [rbp+5Fh]; this
0x1800220a2  test    eax, eax
0x1800220a4  js      loc_1800226BC
0x1800220aa  lea     rcx, [rsi+28h]; this
0x1800220ae  cmp     [rcx], r15
0x1800220b1  jz      loc_180022478
0x1800220b7  mov     [rbp+57h+var_A0], r15
0x1800220bb  lea     rdx, [rbp+57h+var_A0]; void **
0x1800220bf  call    ??$Unmarshal@UISyncedStreamReaderInfo@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@UISyncedStreamReaderInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<ISyncedStreamReaderInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncedStreamReaderInfo>>)
0x1800220c4  mov     ebx, eax
0x1800220c6  mov     rcx, [rbp+5Fh]; this
0x1800220ca  test    eax, eax
0x1800220cc  js      loc_1800226D5
0x1800220d2  mov     rcx, [rbp+57h+var_A0]
0x1800220d6  mov     rax, [rcx]
0x1800220d9  mov     edx, [rsi+14h]
0x1800220dc  add     rdx, rdi
0x1800220df  mov     rax, [rax+20h]
0x1800220e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e8  mov     ebx, eax
0x1800220ea  test    eax, eax
0x1800220ec  js      short loc_180022102
0x1800220ee  mov     rax, [rsi]
0x1800220f1  mov     rdx, [rax+0F8h]; struct CRasFilePlaceholderParams *
0x1800220f8  mov     cl, [rsi+40h]; bool
0x1800220fb  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x180022100  mov     ebx, eax
0x180022102  mov     rcx, [rbp+5Fh]; this
0x180022106  test    ebx, ebx
0x180022108  js      loc_1800226EA
0x18002210e  lea     rcx, [rbp+57h+var_A0]
0x180022112  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180022117  mov     [rbp+57h+var_98], r15
0x18002211b  test    ebx, ebx
0x18002211d  js      loc_1800224D5
0x180022123  mov     rcx, [rsi]; this
0x180022126  cmp     [rcx+0CCh], r12d
0x18002212d  jz      loc_180022656
0x180022133  mov     rdx, [rsi]
0x180022136  mov     rcx, [rdx+0F8h]
0x18002213d  call    _anonymous_namespace____HasRemoteStream
0x180022142  test    al, al
0x180022144  jz      short loc_180022166
0x180022146  lea     r8, [rdx+88h]; struct _OVERLAPPED *
0x18002214d  mov     r9, r13; volatile bool *
0x180022150  mov     rdx, [rdx+0B8h]; struct ISafeSaveHandleManager *
0x180022157  call    ?WriteFullContentsIntoFileIfRequired@CRasFilePlaceholderParams@@QEAAJPEAUISafeSaveHandleManager@@PEAU_OVERLAPPED@@AED_N@Z; CRasFilePlaceholderParams::WriteFullContentsIntoFileIfRequired(ISafeSaveHandleManager *,_OVERLAPPED *,bool const volatile &)
0x18002215c  mov     ebx, eax
0x18002215e  test    eax, eax
0x180022160  js      loc_1800224D5
0x180022166  mov     r15d, 10000h
0x18002216c  mov     [rbp+57h+var_90], r15
0x180022170  mov     rdx, [rsi]
0x180022173  mov     rcx, [rdx+0F8h]
0x18002217a  call    _anonymous_namespace____HasRemoteStream
0x18002217f  xor     edi, edi
0x180022181  test    al, al
0x180022183  jnz     loc_1800227DF
0x180022189  test    ebx, ebx
0x18002218b  js      loc_1800228B6
0x180022191  cmp     [rsi+14h], edi
0x180022194  jbe     loc_180022512
0x18002219a  mov     [rbp+57h+var_A0], rdi
0x18002219e  mov     rax, [rsi]
0x1800221a1  mov     rdi, [rax+0B8h]
0x1800221a8  mov     rax, [rdi]
0x1800221ab  mov     rbx, [rax+18h]
0x1800221af  lea     rcx, [rbp+57h+var_A0]
0x1800221b3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800221b8  lea     rdx, [rbp+57h+var_A0]
0x1800221bc  mov     rcx, rdi
0x1800221bf  mov     rax, rbx
0x1800221c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221c7  mov     ebx, eax
0x1800221c9  test    eax, eax
0x1800221cb  js      short loc_1800221E1
0x1800221cd  mov     rax, [rsi]
0x1800221d0  mov     rdx, [rax+0F8h]; struct CRasFilePlaceholderParams *
0x1800221d7  mov     cl, [rsi+40h]; bool
0x1800221da  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x1800221df  mov     ebx, eax
0x1800221e1  mov     rcx, [rbp+5Fh]
0x1800221e5  test    ebx, ebx
0x1800221e7  js      loc_18002286B
0x1800221ed  lea     rdx, [rsi+38h]; void **
0x1800221f1  mov     rcx, [rbp+57h+var_A0]; struct IFileHandle *
0x1800221f5  call    ?LockHandle@@YAJPEAUIFileHandle@@PEAPEAX@Z; LockHandle(IFileHandle *,void * *)
0x1800221fa  mov     ebx, eax
0x1800221fc  mov     rcx, [rbp+5Fh]; this
0x180022200  test    eax, eax
0x180022202  js      loc_180022875
0x180022208  mov     rdx, [rsi]
0x18002220b  mov     rdi, [rdx+0E0h]
0x180022212  xor     eax, eax
0x180022214  test    rdi, rdi
0x180022217  jz      loc_18002288A
0x18002221d  mov     [rbp+57h+NumberOfBytesTransferred], eax
0x180022220  mov     rdx, [rdx+0F8h]; struct CRasFilePlaceholderParams *
0x180022227  mov     cl, [rsi+40h]; bool
0x18002222a  call    ?s_ShouldContinue@CRasFilePlaceholderParams@@SAJ_NPEAV1@@Z; CRasFilePlaceholderParams::s_ShouldContinue(bool,CRasFilePlaceholderParams *)
0x18002222f  mov     ebx, eax
0x180022231  mov     rcx, [rbp+5Fh]
0x180022235  test    eax, eax
0x180022237  js      loc_180022897
0x18002223d  mov     rcx, [rsi+18h]
0x180022241  mov     rbx, [rsi]
0x180022244  add     rbx, 88h
0x18002224b  mov     r13, [rsi+38h]
0x18002224f  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x180022256  mov     rax, rcx
0x180022259  sar     rax, 20h
0x18002225d  mov     [rbx+10h], ecx
0x180022260  mov     [rbx+14h], eax
0x180022263  mov     [rsp+0F0h+lpOverlapped], rbx; int
0x180022268  xor     r9d, r9d; lpNumberOfBytesRead
0x18002226b  mov     r8d, r15d; nNumberOfBytesToRead
0x18002226e  mov     rdx, rdi; lpBuffer
0x180022271  mov     rcx, r13; hFile
0x180022274  call    cs:__imp_ReadFile
0x18002227a  mov     ecx, eax; int
0x18002227c  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180022281  mov     ecx, 80000000h
0x180022286  lea     r8d, [rax+rcx]
0x18002228a  test    ecx, r8d
0x18002228d  jz      loc_180022551
0x180022293  mov     r9d, r12d; bWait
0x180022296  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002229a  mov     rdx, rbx; lpOverlapped
0x18002229d  mov     rcx, r13; hFile
0x1800222a0  call    cs:__imp_GetOverlappedResult
0x1800222a6  mov     ecx, eax; int
0x1800222a8  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800222ad  xor     ebx, ebx
0x1800222af  cmp     eax, 80070026h
0x1800222b4  cmovnz  ebx, eax
0x1800222b7  mov     rcx, [rbp+5Fh]; this
0x1800222bb  test    ebx, ebx
0x1800222bd  js      loc_1800228A1
0x1800222c3  mov     rcx, [rsi]
0x1800222c6  cmp     qword ptr [rcx+0E0h], 0
0x1800222ce  jnz     loc_18002251A
0x1800222d4  mov     ecx, [rbp+57h+NumberOfBytesTransferred]
0x1800222d7  add     [rbp+57h+arg_8], ecx
0x1800222da  mov     eax, ecx
0x1800222dc  add     [rsi+18h], rax
0x1800222e0  add     [rsi+8], rax
0x1800222e4  sub     [rsi+14h], ecx
0x1800222e7  mov     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFFFh
0x1800222ef  mov     rcx, [rbp+57h+var_A0]
0x1800222f3  mov     rax, [rcx]
0x1800222f6  mov     rax, [rax+20h]
0x1800222fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ff  nop
0x180022300  mov     rcx, [rbp+57h+var_A0]
0x180022304  xor     r15d, r15d
0x180022307  test    rcx, rcx
0x18002230a  jz      short loc_18002231D
0x18002230c  mov     [rbp+57h+var_A0], r15
0x180022310  mov     rax, [rcx]
0x180022313  mov     rax, [rax+10h]
0x180022317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002231c  nop
0x18002231d  test    ebx, ebx
0x18002231f  js      loc_1800224D5
0x180022325  mov     eax, [rsi+14h]
0x180022328  test    eax, eax
0x18002232a  jz      loc_180022488
0x180022330  mov     rcx, [rbp+57h+var_98]
0x180022334  cmp     [rsi+18h], rcx
0x180022338  jnb     loc_180022488
0x18002233e  sub     ecx, [rsi+18h]
0x180022341  cmp     eax, ecx
0x180022343  cmovnb  eax, ecx
0x180022346  mov     ebx, eax
0x180022348  mov     r8d, eax; Size
0x18002234b  xor     edx, edx; Val
0x18002234d  mov     rcx, [rsi+8]; void *
0x180022351  call    memset_0
0x180022356  mov     edx, [rbp+57h+arg_8]
0x180022359  add     edx, ebx
0x18002235b  mov     [rbp+57h+arg_8], edx
0x18002235e  jmp     loc_18002248B
0x180022363  mov     rcx, [rbp+5Fh]; this
0x180022367  test    ebx, ebx
0x180022369  js      loc_18002268E
0x18002236f  mov     rdi, [rsi]
0x180022372  cmp     [rsi+30h], rdi
0x180022376  jz      short loc_1800223A7
0x180022378  test    rdi, rdi
0x18002237b  jz      short loc_18002238D
0x18002237d  mov     rax, [rdi]
0x180022380  mov     rcx, rdi
0x180022383  mov     rax, [rax+8]
0x180022387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002238c  nop
0x18002238d  mov     rcx, [rsi+30h]
0x180022391  mov     [rsi+30h], rdi
0x180022395  test    rcx, rcx
0x180022398  jz      short loc_1800223A7
0x18002239a  mov     rax, [rcx]
0x18002239d  mov     rax, [rax+10h]
0x1800223a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a6  nop
0x1800223a7  mov     rdx, [rsi]
0x1800223aa  add     rdx, 0C0h
0x1800223b1  lea     rcx, [rsi+28h]
0x1800223b5  call    ??4?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::operator=(Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream> const &)
0x1800223ba  mov     rdi, [rsi+48h]
0x1800223be  cmp     [rsi+50h], rdi
0x1800223c2  jz      short loc_1800223F3
0x1800223c4  test    rdi, rdi
0x1800223c7  jz      short loc_1800223D9
0x1800223c9  mov     rax, [rdi]
0x1800223cc  mov     rcx, rdi
0x1800223cf  mov     rax, [rax+8]
0x1800223d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223d8  nop
0x1800223d9  mov     rcx, [rsi+50h]
0x1800223dd  mov     [rsi+50h], rdi
0x1800223e1  test    rcx, rcx
0x1800223e4  jz      short loc_1800223F3
0x1800223e6  mov     rax, [rcx]
0x1800223e9  mov     rax, [rax+10h]
0x1800223ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223f2  nop
0x1800223f3  lea     rcx, [rsi+58h]
0x1800223f7  mov     rdx, [rsi+20h]
0x1800223fb  call    ??4?$ComPtr@UIRWLock@@@WRL@Microsoft@@QEAAAEAV012@PEAUIRWLock@@@Z; Microsoft::WRL::ComPtr<IRWLock>::operator=(IRWLock *)
0x180022400  mov     rcx, [rsi]
0x180022403  xor     eax, eax
0x180022405  lea     r12d, [rax+1]
0x180022409  lock cmpxchg [rcx+0A8h], r12d
0x180022412  jnz     loc_180022569
0x180022418  mov     edx, [rsi+14h]; unsigned int
0x18002241b  mov     rcx, [rsi]; this
0x18002241e  call    ?_SetupCache@CFileInputStream@@AEAAXK@Z; CFileInputStream::_SetupCache(ulong)
0x180022423  mov     rcx, [rsi+60h]; this
0x180022427  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18002242c  nop
0x18002242d  lea     rcx, [rbp+57h+var_80]; this
0x180022431  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180022436  mov     eax, ebx
0x180022438  mov     rbx, [rsp+0F0h+arg_0]
0x180022440  add     rsp, 0C0h
0x180022447  pop     r15
0x180022449  pop     r14
0x18002244b  pop     r13
0x18002244d  pop     r12
0x18002244f  pop     rdi
  ... truncated ...
```
