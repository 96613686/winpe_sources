# AddFileToDownloadRequest(ulong,tagDSFile const * const,ISusFileRequestList *,ulong,tagDSFile const * const,ISusFileRequestList *,ulong,tagDSFile const * const,IDeploymentDownloadRequest *,ulong)

- ea: `0x18001ee5c`
- end: `0x18001f722`
- name: `?AddFileToDownloadRequest@@YAJKQEBUtagDSFile@@PEAUISusFileRequestList@@K01K0PEAUIDeploymentDownloadRequest@@K@Z`
- size: `2246`
- prototype: `int(unsigned int, const struct tagDSFile *const, struct ISusFileRequestList *, unsigned int, const struct tagDSFile *const, struct ISusFileRequestList *, unsigned int, const struct tagDSFile *const, struct IDeploymentDownloadRequest *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021d90`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18001e644`
- `0x18001e7c4`
- `0x18001e8f0`
- `0x18001ee5c`
- `0x180042630`
- `0x180042a24`
- `0x1800430d4`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f65d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f65d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f694`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f1b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f215`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f486`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f5e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f1b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f215`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f486`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f5e8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f1c2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001f1c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=50
__int64 __fastcall AddFileToDownloadRequest(
        unsigned int a1,
        struct tagDSFile *a2,
        struct ISusFileRequestList *a3,
        unsigned int a4,
        struct tagDSFile *a5,
        struct ISusFileRequestList *a6,
        unsigned int a7,
        struct tagDSFile *a8,
        struct IDeploymentDownloadRequest *a9,
        unsigned int a10)
{
  unsigned int v10; // r15d
  struct ISusFileRequestList *v11; // r13
  unsigned int v12; // r14d
  signed int UpdateFileInfo; // esi
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // r12d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned int v21; // edi
  int v22; // ebx
  struct tagDSFile *v23; // r15
  int v24; // ebx
  struct tagDSFile *v25; // rdx
  struct ISusFileRequestList *v26; // r15
  _OWORD *v27; // rax
  UINT v28; // r13d
  BSTR v29; // rax
  OLECHAR *v30; // rdi
  __int64 v31; // rdx
  int v32; // eax
  void *v33; // rbx
  unsigned int v34; // eax
  __int64 v35; // rsi
  unsigned __int64 v36; // rax
  void *v37; // rax
  int v38; // eax
  int v39; // eax
  const struct std::nothrow_t *v40; // rdx
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  const struct std::nothrow_t *v43; // rdx
  unsigned __int64 v44; // r9
  __int64 v45; // rdx
  unsigned __int64 v46; // r9
  __int64 v47; // rdx
  int v48; // [rsp+20h] [rbp-E0h]
  unsigned int v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v50[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v51; // [rsp+60h] [rbp-A0h]
  unsigned int v52; // [rsp+64h] [rbp-9Ch]
  struct tagDSFile *v53; // [rsp+68h] [rbp-98h]
  struct tagDSFile *v54; // [rsp+70h] [rbp-90h]
  struct tagDSFile *v55; // [rsp+78h] [rbp-88h]
  struct ISusFileRequestList *v56; // [rsp+80h] [rbp-80h]
  struct ISusFileRequestList *v57; // [rsp+88h] [rbp-78h]
  __int128 len; // [rsp+90h] [rbp-70h]
  __int128 v59; // [rsp+A0h] [rbp-60h]
  __int128 v60; // [rsp+B0h] [rbp-50h]
  __int128 v61; // [rsp+C0h] [rbp-40h]
  __int128 v62; // [rsp+D0h] [rbp-30h]
  __int128 v63; // [rsp+E0h] [rbp-20h]
  __int128 v64; // [rsp+F0h] [rbp-10h]
  __int128 v65; // [rsp+100h] [rbp+0h]
  __int128 v66; // [rsp+110h] [rbp+10h]
  __int128 v67; // [rsp+120h] [rbp+20h]
  __int128 v68; // [rsp+130h] [rbp+30h]
  __int128 v69; // [rsp+140h] [rbp+40h]
  __int128 v70; // [rsp+150h] [rbp+50h]
  __int128 v71; // [rsp+160h] [rbp+60h]
  __int128 v72; // [rsp+170h] [rbp+70h]
  __int64 v73; // [rsp+180h] [rbp+80h]
  LPVOID pv; // [rsp+190h] [rbp+90h] BYREF
  wchar_t *v75; // [rsp+198h] [rbp+98h] BYREF
  unsigned int v76; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v77; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned int v78[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v79; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v80; // [rsp+1B8h] [rbp+B8h] BYREF
  int v81; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v82; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v83; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v10 = a4;
  v52 = a4;
  v11 = a3;
  v57 = a3;
  v54 = a2;
  v51 = a1;
  v55 = a5;
  v56 = a6;
  v53 = a8;
  v12 = 0;
  if ( a4 && a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)0x80242FFFLL,
      v48);
    return 2149855231LL;
  }
  v82 = 0;
  UpdateFileInfo = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)a9 + 40LL))(
                     a9,
                     &v82);
  if ( UpdateFileInfo < 0 )
  {
    v15 = 308;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)(unsigned int)UpdateFileInfo,
      v48);
    goto LABEL_104;
  }
  v77 = 0;
  UpdateFileInfo = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v82 + 24LL))(v82, &v77);
  if ( UpdateFileInfo < 0 )
  {
    v15 = 311;
    goto LABEL_8;
  }
  v16 = v77;
  if ( v77 > a10 )
  {
    v48 = 0;
    WUTrace(0, 0, 4096, 4);
    v16 = a10;
    v77 = a10;
  }
  v17 = 0;
  if ( !v16 )
  {
LABEL_103:
    UpdateFileInfo = 0;
    goto LABEL_104;
  }
  while ( 1 )
  {
    v80 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v82 + 32LL))(v82, v17, &v80);
    UpdateFileInfo = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x153,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v18,
        v48);
      goto LABEL_100;
    }
    v75 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v80 + 40LL))(v80, &v75);
    UpdateFileInfo = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)v19,
        v48);
      goto LABEL_97;
    }
    pv = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v80 + 24LL))(v80, &pv);
    UpdateFileInfo = v20;
    if ( v20 < 0 )
      break;
    v78[0] = 0;
    v50[0] = 0;
    v21 = 0;
    v49[0] = 0;
    v22 = 0;
    UpdateFileInfo = GetUpdateFileInfo(v51, v54, (const wchar_t *)pv, v78);
    if ( UpdateFileInfo != -2145124344 )
      goto LABEL_18;
    if ( v10 )
    {
      UpdateFileInfo = GetUpdateFileInfo(v10, v55, (const wchar_t *)pv, v50);
      v22 = 1;
      v12 = v50[0];
LABEL_18:
      v23 = v53;
      goto LABEL_19;
    }
    if ( !a7 )
    {
LABEL_92:
      WUTrace(0, 0, 4096, 1);
      goto LABEL_94;
    }
    v23 = v53;
    UpdateFileInfo = GetUpdateFileInfo(a7, v53, (const wchar_t *)pv, v49);
    v22 = 2;
    v21 = v49[0];
LABEL_19:
    if ( UpdateFileInfo < 0 )
      goto LABEL_92;
    v24 = v22 - 1;
    if ( v24 )
    {
      if ( v24 == 1 )
      {
        v25 = v23;
      }
      else
      {
        v25 = v54;
        v21 = v78[0];
      }
      v26 = v11;
    }
    else
    {
      v25 = v55;
      v21 = v12;
      v26 = v56;
    }
    v27 = (_OWORD *)((char *)v25 + 248 * v21);
    len = *v27;
    v59 = v27[1];
    v60 = v27[2];
    v61 = v27[3];
    v62 = v27[4];
    v63 = v27[5];
    v64 = v27[6];
    v65 = v27[7];
    v27 += 8;
    v66 = *v27;
    v67 = v27[1];
    v68 = v27[2];
    v69 = v27[3];
    v70 = v27[4];
    v71 = v27[5];
    v72 = v27[6];
    v73 = *((_QWORD *)v27 + 14);
    SysFreeString(0);
    v28 = len;
    v29 = SysAllocStringByteLen(*((LPCSTR *)&len + 1), len);
    v30 = v29;
    *(_QWORD *)v50 = v29;
    v12 = 0;
    if ( !v29 )
    {
      UpdateFileInfo = -2147024882;
      v47 = 408;
LABEL_90:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)(unsigned int)UpdateFileInfo,
        v48);
LABEL_91:
      SysFreeString(v30);
      goto LABEL_94;
    }
    v81 = 0;
    UpdateFileInfo = (*(__int64 (__fastcall **)(struct ISusFileRequestList *, BSTR, int *))(*(_QWORD *)v26 + 136LL))(
                       v26,
                       v29,
                       &v81);
    if ( UpdateFileInfo < 0 )
    {
      v47 = 411;
      goto LABEL_90;
    }
    if ( v81 )
    {
      SysFreeString(v30);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v75 )
      {
        CoTaskMemFree(v75);
        v75 = 0;
      }
    }
    else
    {
      v79 = 0;
      UpdateFileInfo = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v80 + 48LL))(v80, &v79);
      if ( UpdateFileInfo < 0 )
      {
        v31 = 424;
        goto LABEL_83;
      }
      if ( v79 )
      {
        v76 = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v79 + 24LL))(v79, &v76);
        UpdateFileInfo = v32;
        if ( v32 < 0 )
        {
          v46 = (unsigned int)v32;
          v31 = 435;
LABEL_84:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)v46,
            v48);
          goto LABEL_85;
        }
        v33 = 0;
        *(_QWORD *)v49 = 0;
        v34 = v76;
        v35 = v76;
        if ( v76 )
        {
          v36 = 16LL * v76;
          if ( !is_mul_ok(v76, 0x10u) )
            v36 = -1;
          v37 = operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
          v33 = v37;
          if ( v37 )
            memset(v37, 0, 16 * v35);
          *(_QWORD *)v49 = v33;
          UpdateFileInfo = v33 == 0 ? 0x8007000E : 0;
          v34 = v76;
        }
        else
        {
          UpdateFileInfo = 0;
        }
        if ( UpdateFileInfo < 0 )
        {
          v44 = (unsigned int)UpdateFileInfo;
          v45 = 438;
LABEL_78:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v45,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)v44,
            v48);
LABEL_79:
          if ( v33 )
            operator delete(v33, v43);
LABEL_85:
          if ( v79 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            v79 = 0;
          }
          goto LABEL_91;
        }
        if ( v34 )
        {
          while ( 1 )
          {
            *(_QWORD *)v78 = 0;
            UpdateFileInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v79 + 32LL))(
                               v79,
                               v12,
                               v78);
            if ( UpdateFileInfo < 0 )
              break;
            v83 = 0;
            UpdateFileInfo = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)v78 + 32LL))(
                               *(_QWORD *)v78,
                               (char *)&v83 + 8);
            if ( UpdateFileInfo < 0 )
            {
              v42 = 446;
              goto LABEL_72;
            }
            v38 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v78 + 24LL))(*(_QWORD *)v78, &v83);
            UpdateFileInfo = v38;
            if ( v38 < 0 )
            {
              v41 = (unsigned int)v38;
              v42 = 447;
              goto LABEL_73;
            }
            *((_OWORD *)v33 + v12) = v83;
            if ( *(_QWORD *)v78 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v78 + 16LL))(*(_QWORD *)v78);
            ++v12;
            v34 = v76;
            if ( v12 >= v76 )
              goto LABEL_56;
          }
          v42 = 443;
LABEL_72:
          v41 = (unsigned int)UpdateFileInfo;
LABEL_73:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v42,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)v41,
            v48);
          if ( *(_QWORD *)v78 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v78 + 16LL))(*(_QWORD *)v78);
          goto LABEL_79;
        }
LABEL_56:
        v39 = AddFileToDownloadRequest(
                v26,
                v75,
                *((const CHAR **)&len + 1),
                v28,
                *((unsigned __int64 *)&v72 + 1),
                (struct tagSusFileRange *const)v33,
                v34);
        UpdateFileInfo = v39;
        v12 = 0;
        if ( v39 < 0 )
        {
          v44 = (unsigned int)v39;
          v45 = 457;
          goto LABEL_78;
        }
        if ( v33 )
          operator delete(v33, v40);
      }
      else
      {
        UpdateFileInfo = AddFileToDownloadRequest(
                           v26,
                           v75,
                           *((const CHAR **)&len + 1),
                           v28,
                           *((unsigned __int64 *)&v72 + 1));
        if ( UpdateFileInfo < 0 )
        {
          v31 = 430;
LABEL_83:
          v46 = (unsigned int)UpdateFileInfo;
          goto LABEL_84;
        }
      }
      if ( v79 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        v79 = 0;
      }
      SysFreeString(v30);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v75 )
      {
        CoTaskMemFree(v75);
        v75 = 0;
      }
    }
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    if ( ++v17 >= v77 )
      goto LABEL_103;
    v10 = v52;
    v11 = v57;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15A,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
    (const char *)(unsigned int)v20,
    v48);
LABEL_94:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
LABEL_97:
  if ( v75 )
  {
    CoTaskMemFree(v75);
    v75 = 0;
  }
LABEL_100:
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
LABEL_104:
  if ( v82 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  return (unsigned int)UpdateFileInfo;
}

```

## disassembly

```asm
0x18001ee5c  mov     [rsp-8+arg_0], rbx
0x18001ee61  push    rbp
0x18001ee62  push    rsi
0x18001ee63  push    rdi
0x18001ee64  push    r12
0x18001ee66  push    r13
0x18001ee68  push    r14
0x18001ee6a  push    r15
0x18001ee6c  lea     rbp, [rsp-0F0h]
0x18001ee74  sub     rsp, 1F0h
0x18001ee7b  mov     rax, cs:__security_cookie
0x18001ee82  xor     rax, rsp
0x18001ee85  mov     [rbp+120h+var_40], rax
0x18001ee8c  mov     r15d, r9d
0x18001ee8f  mov     [rsp+220h+var_1BC], r9d
0x18001ee94  mov     r13, r8
0x18001ee97  mov     [rbp+120h+var_198], r8
0x18001ee9b  mov     [rsp+220h+var_1B0], rdx
0x18001eea0  mov     [rsp+220h+var_1C0], ecx
0x18001eea4  mov     rax, [rbp+120h+arg_20]
0x18001eeab  mov     [rsp+220h+var_1A8], rax
0x18001eeb0  mov     rax, [rbp+120h+arg_28]
0x18001eeb7  mov     [rbp+120h+var_1A0], rax
0x18001eebb  mov     rax, [rbp+120h+arg_38]
0x18001eec2  mov     [rsp+220h+var_1B8], rax
0x18001eec7  mov     rcx, [rbp+120h+arg_40]
0x18001eece  xor     r14d, r14d
0x18001eed1  test    r9d, r9d
0x18001eed4  jz      short loc_18001EF06
0x18001eed6  cmp     [rbp+120h+arg_30], r14d
0x18001eedd  jbe     short loc_18001EF06
0x18001eedf  mov     rcx, [rbp+128h]; this
0x18001eee6  mov     ebx, 80242FFFh
0x18001eeeb  mov     r9d, ebx; char *
0x18001eeee  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001eef5  mov     edx, 132h; void *
0x18001eefa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eeff  mov     eax, ebx
0x18001ef01  jmp     loc_18001F6F8
0x18001ef06  mov     [rbp+120h+var_58], r14
0x18001ef0d  mov     rax, [rcx]
0x18001ef10  lea     rdx, [rbp+120h+var_58]
0x18001ef17  mov     rax, [rax+28h]
0x18001ef1b  call    _guard_dispatch_icall
0x18001ef20  mov     esi, eax
0x18001ef22  test    eax, eax
0x18001ef24  jns     short loc_18001EF2D
0x18001ef26  mov     edx, 134h
0x18001ef2b  jmp     short loc_18001EF59
0x18001ef2d  mov     [rbp+120h+var_7C], r14d
0x18001ef34  mov     rcx, [rbp+120h+var_58]
0x18001ef3b  mov     rax, [rcx]
0x18001ef3e  lea     rdx, [rbp+120h+var_7C]
0x18001ef45  mov     rax, [rax+18h]
0x18001ef49  call    _guard_dispatch_icall
0x18001ef4e  mov     esi, eax
0x18001ef50  test    eax, eax
0x18001ef52  jns     short loc_18001EF74
0x18001ef54  mov     edx, 137h; void *
0x18001ef59  mov     rcx, [rbp+128h]; this
0x18001ef60  mov     r9d, esi; char *
0x18001ef63  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001ef6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef6f  jmp     loc_18001F6DD
0x18001ef74  mov     eax, [rbp+120h+var_7C]
0x18001ef7a  mov     ebx, [rbp+120h+arg_48]
0x18001ef80  cmp     eax, ebx
0x18001ef82  jbe     short loc_18001EFB8
0x18001ef84  mov     dword ptr [rsp+220h+var_1E8], ebx
0x18001ef88  mov     [rsp+220h+var_1F0], eax
0x18001ef8c  lea     rax, aAddfiletodownl; "AddFileToDownloadRequest requires %d fi"...
0x18001ef93  mov     [rsp+220h+var_1F8], rax
0x18001ef98  mov     [rsp+220h+var_200], r14; int
0x18001ef9d  xor     edx, edx
0x18001ef9f  xor     ecx, ecx
0x18001efa1  lea     r9d, [rdx+4]
0x18001efa5  mov     r8d, 1000h
0x18001efab  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001efb0  mov     eax, ebx
0x18001efb2  mov     [rbp+120h+var_7C], ebx
0x18001efb8  mov     r12d, r14d
0x18001efbb  test    eax, eax
0x18001efbd  jz      loc_18001F6DA
0x18001efc3  mov     [rbp+120h+var_68], r14
0x18001efca  mov     rcx, [rbp+120h+var_58]
0x18001efd1  mov     rax, [rcx]
0x18001efd4  lea     r8, [rbp+120h+var_68]
0x18001efdb  mov     edx, r12d
0x18001efde  mov     rax, [rax+20h]
0x18001efe2  call    _guard_dispatch_icall
0x18001efe7  mov     esi, eax
0x18001efe9  test    eax, eax
0x18001efeb  js      loc_18001F6A3
0x18001eff1  mov     [rbp+120h+var_88], r14
0x18001eff8  mov     rcx, [rbp+120h+var_68]
0x18001efff  mov     rax, [rcx]
0x18001f002  lea     rdx, [rbp+120h+var_88]
0x18001f009  mov     rax, [rax+28h]
0x18001f00d  call    _guard_dispatch_icall
0x18001f012  mov     esi, eax
0x18001f014  test    eax, eax
0x18001f016  js      loc_18001F66C
0x18001f01c  mov     [rbp+120h+pv], r14
0x18001f023  mov     rcx, [rbp+120h+var_68]
0x18001f02a  mov     rax, [rcx]
0x18001f02d  lea     rdx, [rbp+120h+pv]
0x18001f034  mov     rax, [rax+18h]
0x18001f038  call    _guard_dispatch_icall
0x18001f03d  mov     esi, eax
0x18001f03f  test    eax, eax
0x18001f041  js      loc_18001F635
0x18001f047  mov     [rbp+120h+var_78], r14d
0x18001f04e  mov     [rsp+220h+var_1C8], r14d
0x18001f053  xor     edi, edi
0x18001f055  mov     [rsp+220h+var_1D0], edi
0x18001f059  xor     ebx, ebx
0x18001f05b  lea     r9, [rbp+120h+var_78]; unsigned int *
0x18001f062  mov     r8, [rbp+120h+pv]; wchar_t *
0x18001f069  mov     rdx, [rsp+220h+var_1B0]; struct tagDSFile *
0x18001f06e  mov     ecx, [rsp+220h+var_1C0]; unsigned int
0x18001f072  call    ?GetUpdateFileInfo@@YAJKQEBUtagDSFile@@PEB_WPEAK@Z; GetUpdateFileInfo(ulong,tagDSFile const * const,wchar_t const *,ulong *)
0x18001f077  mov     esi, eax
0x18001f079  cmp     eax, 80240008h
0x18001f07e  jnz     short loc_18001F0A8
0x18001f080  test    r15d, r15d
0x18001f083  jz      short loc_18001F0CC
0x18001f085  lea     r9, [rsp+220h+var_1C8]; unsigned int *
0x18001f08a  mov     r8, [rbp+120h+pv]; wchar_t *
0x18001f091  mov     rdx, [rsp+220h+var_1A8]; struct tagDSFile *
0x18001f096  mov     ecx, r15d; unsigned int
0x18001f099  call    ?GetUpdateFileInfo@@YAJKQEBUtagDSFile@@PEB_WPEAK@Z; GetUpdateFileInfo(ulong,tagDSFile const * const,wchar_t const *,ulong *)
0x18001f09e  mov     esi, eax
0x18001f0a0  lea     ebx, [rdi+1]
0x18001f0a3  mov     r14d, [rsp+220h+var_1C8]
0x18001f0a8  mov     r15, [rsp+220h+var_1B8]
0x18001f0ad  test    esi, esi
0x18001f0af  js      loc_18001F5F0
0x18001f0b5  sub     ebx, 1
0x18001f0b8  jz      short loc_18001F10C
0x18001f0ba  cmp     ebx, 1
0x18001f0bd  jz      short loc_18001F104
0x18001f0bf  mov     rdx, [rsp+220h+var_1B0]
0x18001f0c4  mov     edi, [rbp+120h+var_78]
0x18001f0ca  jmp     short loc_18001F107
0x18001f0cc  cmp     [rbp+120h+arg_30], ebx
0x18001f0d2  jbe     loc_18001F5F0
0x18001f0d8  lea     r9, [rsp+220h+var_1D0]; unsigned int *
0x18001f0dd  mov     r8, [rbp+120h+pv]; wchar_t *
0x18001f0e4  mov     r15, [rsp+220h+var_1B8]
0x18001f0e9  mov     rdx, r15; struct tagDSFile *
0x18001f0ec  mov     ecx, [rbp+120h+arg_30]; unsigned int
0x18001f0f2  call    ?GetUpdateFileInfo@@YAJKQEBUtagDSFile@@PEB_WPEAK@Z; GetUpdateFileInfo(ulong,tagDSFile const * const,wchar_t const *,ulong *)
0x18001f0f7  mov     esi, eax
0x18001f0f9  mov     ebx, 2
0x18001f0fe  mov     edi, [rsp+220h+var_1D0]
0x18001f102  jmp     short loc_18001F0AD
0x18001f104  mov     rdx, r15
0x18001f107  mov     r15, r13
0x18001f10a  jmp     short loc_18001F118
0x18001f10c  mov     rdx, [rsp+220h+var_1A8]
0x18001f111  mov     edi, r14d
0x18001f114  mov     r15, [rbp+120h+var_1A0]
0x18001f118  mov     eax, edi
0x18001f11a  imul    rax, 0F8h
0x18001f121  add     rax, rdx
0x18001f124  lea     rcx, [rbp+120h+len]
0x18001f128  movups  xmm0, xmmword ptr [rax]
0x18001f12b  movups  xmmword ptr [rcx], xmm0
0x18001f12e  movups  xmm1, xmmword ptr [rax+10h]
0x18001f132  movups  xmmword ptr [rcx+10h], xmm1
0x18001f136  movups  xmm0, xmmword ptr [rax+20h]
0x18001f13a  movups  xmmword ptr [rcx+20h], xmm0
0x18001f13e  movups  xmm1, xmmword ptr [rax+30h]
0x18001f142  movups  xmmword ptr [rcx+30h], xmm1
0x18001f146  movups  xmm0, xmmword ptr [rax+40h]
0x18001f14a  movups  xmmword ptr [rcx+40h], xmm0
0x18001f14e  movups  xmm1, xmmword ptr [rax+50h]
0x18001f152  movups  xmmword ptr [rcx+50h], xmm1
0x18001f156  movups  xmm0, xmmword ptr [rax+60h]
0x18001f15a  movups  xmmword ptr [rcx+60h], xmm0
0x18001f15e  mov     ebx, 80h
0x18001f163  add     rcx, rbx
0x18001f166  movups  xmm1, xmmword ptr [rax+70h]
0x18001f16a  movups  xmmword ptr [rcx-10h], xmm1
0x18001f16e  add     rax, rbx
0x18001f171  movups  xmm0, xmmword ptr [rax]
0x18001f174  movups  xmmword ptr [rcx], xmm0
0x18001f177  movups  xmm1, xmmword ptr [rax+10h]
0x18001f17b  movups  xmmword ptr [rcx+10h], xmm1
0x18001f17f  movups  xmm0, xmmword ptr [rax+20h]
0x18001f183  movups  xmmword ptr [rcx+20h], xmm0
0x18001f187  movups  xmm1, xmmword ptr [rax+30h]
0x18001f18b  movups  xmmword ptr [rcx+30h], xmm1
0x18001f18f  movups  xmm0, xmmword ptr [rax+40h]
0x18001f193  movups  xmmword ptr [rcx+40h], xmm0
0x18001f197  movups  xmm1, xmmword ptr [rax+50h]
0x18001f19b  movups  xmmword ptr [rcx+50h], xmm1
0x18001f19f  movups  xmm0, xmmword ptr [rax+60h]
0x18001f1a3  movups  xmmword ptr [rcx+60h], xmm0
0x18001f1a7  mov     rax, [rax+70h]
0x18001f1ab  mov     [rcx+70h], rax
0x18001f1af  xor     ecx, ecx; bstrString
0x18001f1b1  call    cs:__imp_SysFreeString
0x18001f1b7  mov     r13d, [rbp+120h+len]
0x18001f1bb  mov     edx, r13d; len
0x18001f1be  mov     rcx, [rbp+120h+psz]; psz
0x18001f1c2  call    cs:__imp_SysAllocStringByteLen
0x18001f1c8  mov     rdi, rax
0x18001f1cb  mov     qword ptr [rsp+220h+var_1C8], rax
0x18001f1d0  xor     r14d, r14d
0x18001f1d3  test    rax, rax
0x18001f1d6  jz      loc_18001F5C4
0x18001f1dc  mov     [rbp+120h+var_60], r14d
0x18001f1e3  mov     rax, [r15]
0x18001f1e6  lea     r8, [rbp+120h+var_60]
0x18001f1ed  mov     rdx, rdi
0x18001f1f0  mov     rcx, r15
0x18001f1f3  mov     rax, [rax+88h]
0x18001f1fa  call    _guard_dispatch_icall
0x18001f1ff  mov     esi, eax
0x18001f201  test    eax, eax
0x18001f203  js      loc_18001F5BD
0x18001f209  cmp     [rbp+120h+var_60], r14d
0x18001f210  jz      short loc_18001F253
0x18001f212  mov     rcx, rdi; bstrString
0x18001f215  call    cs:__imp_SysFreeString
0x18001f21b  nop
0x18001f21c  mov     rcx, [rbp+120h+pv]; pv
0x18001f223  test    rcx, rcx
0x18001f226  jz      short loc_18001F235
0x18001f228  call    cs:__imp_CoTaskMemFree
0x18001f22e  mov     [rbp+120h+pv], r14
0x18001f235  mov     rcx, [rbp+120h+var_88]; pv
0x18001f23c  test    rcx, rcx
0x18001f23f  jz      short loc_18001F24E
0x18001f241  call    cs:__imp_CoTaskMemFree
0x18001f247  mov     [rbp+120h+var_88], r14
0x18001f24e  jmp     loc_18001F4BF
0x18001f253  mov     [rbp+120h+var_70], r14
0x18001f25a  mov     rcx, [rbp+120h+var_68]
0x18001f261  mov     rax, [rcx]
0x18001f264  lea     rdx, [rbp+120h+var_70]
0x18001f26b  mov     rax, [rax+30h]
0x18001f26f  call    _guard_dispatch_icall
0x18001f274  mov     esi, eax
0x18001f276  test    eax, eax
0x18001f278  js      loc_18001F580
0x18001f27e  mov     rcx, [rbp+120h+var_70]
0x18001f285  test    rcx, rcx
0x18001f288  jnz     short loc_18001F2BD
0x18001f28a  mov     rax, [rbp+120h+var_A8]
0x18001f28e  mov     [rsp+220h+var_200], rax; unsigned __int64
0x18001f293  mov     r9d, r13d; unsigned int
0x18001f296  mov     r8, [rbp+120h+psz]; unsigned __int8 *
0x18001f29a  mov     rdx, [rbp+120h+var_88]; wchar_t *
0x18001f2a1  mov     rcx, r15; struct ISusFileRequestList *
0x18001f2a4  call    ?AddFileToDownloadRequest@@YAJPEAUISusFileRequestList@@PEB_WQEAEK_K@Z; AddFileToDownloadRequest(ISusFileRequestList *,wchar_t const *,uchar * const,ulong,unsigned __int64)
0x18001f2a9  mov     esi, eax
0x18001f2ab  test    eax, eax
0x18001f2ad  jns     loc_18001F464
0x18001f2b3  mov     edx, 1AEh
0x18001f2b8  jmp     loc_18001F585
0x18001f2bd  mov     [rbp+120h+var_80], r14d
0x18001f2c4  mov     rax, [rcx]
0x18001f2c7  lea     rdx, [rbp+120h+var_80]
0x18001f2ce  mov     rax, [rax+18h]
0x18001f2d2  call    _guard_dispatch_icall
0x18001f2d7  mov     esi, eax
0x18001f2d9  test    eax, eax
0x18001f2db  js      loc_18001F576
0x18001f2e1  mov     rbx, r14
0x18001f2e4  mov     qword ptr [rsp+220h+var_1D0], rbx
0x18001f2e9  mov     eax, [rbp+120h+var_80]
0x18001f2ef  mov     esi, eax
0x18001f2f1  test    eax, eax
0x18001f2f3  jnz     short loc_18001F2FA
0x18001f2f5  mov     esi, r14d
0x18001f2f8  jmp     short loc_18001F350
0x18001f2fa  mov     eax, 10h
0x18001f2ff  mul     rsi
0x18001f302  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f309  cmovb   rax, rcx
0x18001f30d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f314  mov     rcx, rax; unsigned __int64
0x18001f317  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f31c  mov     rbx, rax
0x18001f31f  test    rax, rax
0x18001f322  jz      short loc_18001F335
0x18001f324  shl     rsi, 4
0x18001f328  mov     r8, rsi; Size
0x18001f32b  xor     edx, edx; Val
0x18001f32d  mov     rcx, rax; void *
0x18001f330  call    memset
0x18001f335  mov     qword ptr [rsp+220h+var_1D0], rbx
0x18001f33a  mov     rax, rbx
0x18001f33d  neg     rax
0x18001f340  sbb     esi, esi
0x18001f342  not     esi
0x18001f344  and     esi, 8007000Eh
0x18001f34a  mov     eax, [rbp+120h+var_80]
  ... truncated ...
```
