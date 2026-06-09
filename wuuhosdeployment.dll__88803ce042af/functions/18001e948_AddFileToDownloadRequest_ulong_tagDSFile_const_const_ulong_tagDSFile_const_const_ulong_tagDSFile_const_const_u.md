# AddFileToDownloadRequest(ulong,tagDSFile const * const,ulong,tagDSFile const * const,ulong,tagDSFile const * const,ulong,RemoteDeploymentDownloadRequest const &,ISusFileRequestList &,ISusFileRequestList &,ulong &)

- ea: `0x18001e948`
- end: `0x18001ee56`
- name: `?AddFileToDownloadRequest@@YAJKQEBUtagDSFile@@K0K0KAEBURemoteDeploymentDownloadRequest@@AEAUISusFileRequestList@@2AEAK@Z`
- size: `1294`
- prototype: `__int64 __fastcall(unsigned int, struct tagDSFile *, unsigned int, struct tagDSFile *, unsigned int, struct tagDSFile *, unsigned int, const struct RemoteDeploymentDownloadRequest *, struct ISusFileRequestList *, struct ISusFileRequestList *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180021730`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000e4d4`
- `0x18001e644`
- `0x18001e7c4`
- `0x18001e8f0`
- `0x18001e948`
- `0x180042630`
- `0x180042a24`
- `0x1800430d4`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ebda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ed62`
- `OLEAUT32!__imp_SysFreeString` at `0x18001edee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ebda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ed62`
- `OLEAUT32!__imp_SysFreeString` at `0x18001edee`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001ebf5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001ebf5`

## string_xrefs

- `0x18001ee0d`: `GetUpdateFileInfo failed for the file "%ws" (SHA2 hash: %ws) in scenario %d.`

## pseudocode

```c
__int64 __fastcall AddFileToDownloadRequest(
        unsigned int a1,
        struct tagDSFile *a2,
        unsigned int a3,
        struct tagDSFile *a4,
        unsigned int a5,
        struct tagDSFile *a6,
        unsigned int a7,
        const struct RemoteDeploymentDownloadRequest *a8,
        struct ISusFileRequestList *a9,
        struct ISusFileRequestList *a10,
        unsigned int *a11)
{
  unsigned int v11; // r10d
  const struct RemoteDeploymentDownloadRequest *v12; // rcx
  unsigned int v14; // r15d
  unsigned int v15; // eax
  __int64 v16; // r13
  unsigned int v17; // r14d
  unsigned int v18; // r12d
  int v19; // ebx
  const wchar_t *v20; // rsi
  int UpdateFileInfo; // edi
  int v22; // eax
  wchar_t *v23; // rax
  int v24; // ebx
  struct ISusFileRequestList *v25; // r14
  struct tagDSFile *v26; // rdx
  _OWORD *v27; // rax
  unsigned int v28; // ebx
  BSTR v29; // rax
  OLECHAR *v30; // rdi
  signed int v31; // esi
  unsigned __int64 v32; // r12
  __int64 v33; // rdx
  unsigned __int64 v34; // rax
  struct tagSusFileRange *v35; // rax
  struct tagSusFileRange *v36; // rbx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r15
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // eax
  const struct std::nothrow_t *v43; // rdx
  unsigned __int64 v44; // r9
  __int64 v45; // rdx
  const struct std::nothrow_t *v46; // rdx
  int v47; // [rsp+20h] [rbp-E0h]
  unsigned int v48; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v49; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 *v50; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v51; // [rsp+58h] [rbp-A8h]
  unsigned int v52; // [rsp+5Ch] [rbp-A4h]
  unsigned int v53; // [rsp+60h] [rbp-A0h]
  unsigned int v54; // [rsp+64h] [rbp-9Ch]
  __int64 v55; // [rsp+68h] [rbp-98h]
  struct tagDSFile *v56; // [rsp+70h] [rbp-90h]
  struct tagDSFile *v57; // [rsp+78h] [rbp-88h]
  struct ISusFileRequestList *v58; // [rsp+80h] [rbp-80h]
  struct tagDSFile *v59; // [rsp+88h] [rbp-78h]
  const struct RemoteDeploymentDownloadRequest *v60; // [rsp+90h] [rbp-70h]
  struct ISusFileRequestList *v61; // [rsp+98h] [rbp-68h]
  __int64 v62; // [rsp+A0h] [rbp-60h]
  unsigned int *v63; // [rsp+A8h] [rbp-58h]
  BSTR v64; // [rsp+B0h] [rbp-50h]
  struct tagSusFileRange *v65; // [rsp+B8h] [rbp-48h]
  __int128 len; // [rsp+C0h] [rbp-40h]
  __int128 v67; // [rsp+D0h] [rbp-30h]
  __int128 v68; // [rsp+E0h] [rbp-20h]
  __int128 v69; // [rsp+F0h] [rbp-10h]
  __int128 v70; // [rsp+100h] [rbp+0h]
  __int128 v71; // [rsp+110h] [rbp+10h]
  __int128 v72; // [rsp+120h] [rbp+20h]
  __int128 v73; // [rsp+130h] [rbp+30h]
  __int128 v74; // [rsp+140h] [rbp+40h]
  __int128 v75; // [rsp+150h] [rbp+50h]
  __int128 v76; // [rsp+160h] [rbp+60h]
  __int128 v77; // [rsp+170h] [rbp+70h]
  __int128 v78; // [rsp+180h] [rbp+80h]
  __int128 v79; // [rsp+190h] [rbp+90h]
  __int128 v80; // [rsp+1A0h] [rbp+A0h]
  __int64 v81; // [rsp+1B0h] [rbp+B0h]
  int v82; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v59 = a4;
  v54 = a3;
  v56 = a2;
  v11 = a1;
  v53 = a1;
  v57 = a6;
  v12 = a8;
  v60 = a8;
  v58 = a9;
  v61 = a10;
  v63 = a11;
  if ( a3 && a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)0x80242FFFLL,
      v47);
    return 2149855231LL;
  }
  *a11 = 0;
  v14 = *((_DWORD *)a8 + 6);
  v51 = v14;
  if ( v14 > a7 )
  {
    v47 = 0;
    WUTrace(0, 0, 4096, 4);
    v14 = a7;
    v51 = a7;
    v12 = v60;
    a2 = v56;
    v11 = v53;
  }
  v15 = 0;
  v52 = 0;
  if ( v14 )
  {
    while ( 1 )
    {
      v16 = 32LL * v15;
      v55 = *((_QWORD *)v12 + 4);
      v48 = 0;
      v17 = 0;
      LODWORD(v49) = 0;
      v18 = 0;
      LODWORD(v50) = 0;
      v19 = 0;
      v20 = *(const wchar_t **)(v55 + v16);
      UpdateFileInfo = GetUpdateFileInfo(v11, a2, v20, &v48);
      if ( UpdateFileInfo != -2145124344 )
        goto LABEL_13;
      if ( v54 )
      {
        v22 = GetUpdateFileInfo(v54, v59, v20, (unsigned int *)&v49);
        v19 = 1;
        v17 = (unsigned int)v49;
      }
      else
      {
        if ( !a5 )
          goto LABEL_13;
        v22 = GetUpdateFileInfo(a5, v57, v20, (unsigned int *)&v50);
        v19 = 2;
        v18 = (unsigned int)v50;
      }
      UpdateFileInfo = v22;
LABEL_13:
      v23 = *(wchar_t **)(v55 + v16 + 8);
      v49 = v23;
      if ( UpdateFileInfo < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xD7,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
          (const char *)(unsigned int)UpdateFileInfo,
          (int)"GetUpdateFileInfo failed for the file \"%ws\" (SHA2 hash: %ws) in scenario %d.",
          (const char *)v23,
          v20,
          v19);
        return (unsigned int)UpdateFileInfo;
      }
      v24 = v19 - 1;
      if ( v24 )
      {
        v25 = v58;
        if ( v24 == 1 )
        {
          v26 = v57;
        }
        else
        {
          v26 = v56;
          v18 = v48;
        }
      }
      else
      {
        v26 = v59;
        v18 = v17;
        v25 = v61;
      }
      v27 = (_OWORD *)((char *)v26 + 248 * v18);
      len = *v27;
      v67 = v27[1];
      v68 = v27[2];
      v69 = v27[3];
      v70 = v27[4];
      v71 = v27[5];
      v72 = v27[6];
      v73 = v27[7];
      v27 += 8;
      v74 = *v27;
      v75 = v27[1];
      v76 = v27[2];
      v77 = v27[3];
      v78 = v27[4];
      v79 = v27[5];
      v80 = v27[6];
      v81 = *((_QWORD *)v27 + 14);
      SysFreeString(0);
      v28 = len;
      v48 = len;
      v50 = (unsigned __int8 *)*((_QWORD *)&len + 1);
      v29 = SysAllocStringByteLen(*((LPCSTR *)&len + 1), len);
      v30 = v29;
      v64 = v29;
      if ( !v29 )
      {
        v31 = -2147024882;
        v33 = 245;
        goto LABEL_43;
      }
      v82 = 0;
      v31 = (*(__int64 (__fastcall **)(struct ISusFileRequestList *, BSTR, int *))(*(_QWORD *)v25 + 136LL))(
              v25,
              v29,
              &v82);
      if ( v31 < 0 )
      {
        v33 = 248;
        goto LABEL_43;
      }
      if ( !v82 )
      {
        v32 = *(unsigned int *)(v55 + v16 + 16);
        if ( (_DWORD)v32 )
        {
          v62 = *(unsigned int *)(v55 + v16 + 16);
          v34 = 16 * v32;
          if ( !is_mul_ok(v32, 0x10u) )
            v34 = -1;
          v35 = (struct tagSusFileRange *)operator new[](v34, (const struct std::nothrow_t *)&std::nothrow);
          v36 = v35;
          if ( v35 )
            memset(v35, 0, 16 * v32);
          v65 = v36;
          v31 = v36 == 0 ? 0x8007000E : 0;
          if ( !v36 )
          {
            v44 = (unsigned int)v31;
            v45 = 270;
            goto LABEL_39;
          }
          v37 = 0;
          v38 = v62;
          v39 = v55;
          do
          {
            v40 = *(_QWORD *)(v39 + v16 + 24);
            v41 = *(_QWORD *)(v37 + v40 + 8);
            *(_QWORD *)((char *)v36 + v37) = *(_QWORD *)(v37 + v40);
            *(_QWORD *)((char *)v36 + v37 + 8) = v41;
            v37 += 16;
            --v38;
          }
          while ( v38 );
          v14 = v51;
          v42 = AddFileToDownloadRequest(v25, v49, v50, v48, *((unsigned __int64 *)&v80 + 1), v36, v32);
          v31 = v42;
          if ( v42 < 0 )
          {
            v44 = (unsigned int)v42;
            v45 = 286;
LABEL_39:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v45,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
              (const char *)v44,
              v47);
            if ( v36 )
              operator delete(v36, v46);
LABEL_44:
            SysFreeString(v30);
            return (unsigned int)v31;
          }
          operator delete(v36, v43);
        }
        else
        {
          v31 = AddFileToDownloadRequest(v25, v49, v50, v28, *((unsigned __int64 *)&v80 + 1));
          if ( v31 < 0 )
          {
            v33 = 265;
LABEL_43:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v33,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
              (const char *)(unsigned int)v31,
              v47);
            goto LABEL_44;
          }
        }
        ++*v63;
      }
      SysFreeString(v30);
      v15 = v52 + 1;
      v52 = v15;
      if ( v15 >= v14 )
        return 0;
      v12 = v60;
      a2 = v56;
      v11 = v53;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e948  push    rbp
0x18001e94a  push    rbx
0x18001e94b  push    rsi
0x18001e94c  push    rdi
0x18001e94d  push    r12
0x18001e94f  push    r13
0x18001e951  push    r14
0x18001e953  push    r15
0x18001e955  lea     rbp, [rsp-0D8h]
0x18001e95d  sub     rsp, 1D8h
0x18001e964  mov     rax, cs:__security_cookie
0x18001e96b  xor     rax, rsp
0x18001e96e  mov     [rbp+110h+var_48], rax
0x18001e975  mov     [rbp+110h+var_188], r9
0x18001e979  mov     [rsp+210h+var_1AC], r8d
0x18001e97e  mov     [rsp+210h+var_1A0], rdx
0x18001e983  mov     r10d, ecx
0x18001e986  mov     [rsp+210h+var_1B0], ecx
0x18001e98a  mov     rax, [rbp+110h+arg_28]
0x18001e991  mov     [rsp+210h+var_198], rax
0x18001e996  mov     rcx, [rbp+110h+arg_38]
0x18001e99d  mov     [rbp+110h+var_180], rcx
0x18001e9a1  mov     rax, [rbp+110h+arg_40]
0x18001e9a8  mov     [rbp+110h+var_190], rax
0x18001e9ac  mov     rax, [rbp+110h+arg_48]
0x18001e9b3  mov     [rbp+110h+var_178], rax
0x18001e9b7  mov     rax, [rbp+110h+arg_50]
0x18001e9be  mov     [rbp+110h+var_168], rax
0x18001e9c2  test    r8d, r8d
0x18001e9c5  jz      short loc_18001E9F7
0x18001e9c7  cmp     [rbp+110h+arg_20], 0
0x18001e9ce  jbe     short loc_18001E9F7
0x18001e9d0  mov     rcx, [rbp+118h]; this
0x18001e9d7  mov     ebx, 80242FFFh
0x18001e9dc  mov     r9d, ebx; char *
0x18001e9df  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001e9e6  mov     edx, 9Eh; void *
0x18001e9eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9f0  mov     eax, ebx
0x18001e9f2  jmp     loc_18001EE33
0x18001e9f7  mov     dword ptr [rax], 0
0x18001e9fd  mov     r15d, [rcx+18h]
0x18001ea01  mov     [rsp+210h+var_1B8], r15d
0x18001ea06  mov     ebx, [rbp+110h+arg_30]
0x18001ea0c  cmp     r15d, ebx
0x18001ea0f  jbe     short loc_18001EA57
0x18001ea11  mov     [rsp+210h+var_1D8], ebx
0x18001ea15  mov     [rsp+210h+var_1E0], r15d
0x18001ea1a  lea     rax, aAddfiletodownl; "AddFileToDownloadRequest requires %d fi"...
0x18001ea21  mov     [rsp+210h+var_1E8], rax
0x18001ea26  mov     [rsp+210h+var_1F0], 0; int
0x18001ea2f  xor     edx, edx
0x18001ea31  xor     ecx, ecx
0x18001ea33  lea     r9d, [rdx+4]
0x18001ea37  mov     r8d, 1000h
0x18001ea3d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001ea42  mov     r15d, ebx
0x18001ea45  mov     [rsp+210h+var_1B8], ebx
0x18001ea49  mov     rcx, [rbp+110h+var_180]
0x18001ea4d  mov     rdx, [rsp+210h+var_1A0]; struct tagDSFile *
0x18001ea52  mov     r10d, [rsp+210h+var_1B0]
0x18001ea57  xor     eax, eax
0x18001ea59  mov     [rsp+210h+var_1B4], eax
0x18001ea5d  test    r15d, r15d
0x18001ea60  jz      loc_18001EE31
0x18001ea66  mov     r13d, eax
0x18001ea69  shl     r13, 5
0x18001ea6d  mov     rax, [rcx+20h]
0x18001ea71  mov     [rsp+210h+var_1A8], rax
0x18001ea76  mov     [rsp+210h+var_1D0], 0
0x18001ea7e  xor     r14d, r14d
0x18001ea81  mov     dword ptr [rsp+210h+var_1C8], r14d
0x18001ea86  xor     r12d, r12d
0x18001ea89  mov     dword ptr [rsp+210h+var_1C0], r12d
0x18001ea8e  xor     ebx, ebx
0x18001ea90  mov     rsi, [rax+r13]
0x18001ea94  lea     r9, [rsp+210h+var_1D0]; unsigned int *
0x18001ea99  mov     r8, rsi; wchar_t *
0x18001ea9c  mov     ecx, r10d; unsigned int
0x18001ea9f  call    ?GetUpdateFileInfo@@YAJKQEBUtagDSFile@@PEB_WPEAK@Z; GetUpdateFileInfo(ulong,tagDSFile const * const,wchar_t const *,ulong *)
0x18001eaa4  mov     edi, eax
0x18001eaa6  cmp     eax, 80240008h
0x18001eaab  jnz     short loc_18001EAFD
0x18001eaad  mov     eax, [rsp+210h+var_1AC]
0x18001eab1  test    eax, eax
0x18001eab3  jz      short loc_18001EAD3
0x18001eab5  lea     r9, [rsp+210h+var_1C8]; unsigned int *
0x18001eaba  mov     r8, rsi; wchar_t *
0x18001eabd  mov     rdx, [rbp+110h+var_188]; struct tagDSFile *
0x18001eac1  mov     ecx, eax; unsigned int
0x18001eac3  call    ?GetUpdateFileInfo@@YAJKQEBUtagDSFile@@PEB_WPEAK@Z; GetUpdateFileInfo(ulong,tagDSFile const * const,wchar_t const *,ulong *)
0x18001eac8  lea     ebx, [r14+1]
0x18001eacc  mov     r14d, dword ptr [rsp+210h+var_1C8]
0x18001ead1  jmp     short loc_18001EAFB
0x18001ead3  mov     eax, [rbp+110h+arg_20]
0x18001ead9  test    eax, eax
0x18001eadb  jz      short loc_18001EAFD
0x18001eadd  lea     r9, [rsp+210h+var_1C0]; unsigned int *
0x18001eae2  mov     r8, rsi; wchar_t *
0x18001eae5  mov     rdx, [rsp+210h+var_198]; struct tagDSFile *
0x18001eaea  mov     ecx, eax; unsigned int
0x18001eaec  call    ?GetUpdateFileInfo@@YAJKQEBUtagDSFile@@PEB_WPEAK@Z; GetUpdateFileInfo(ulong,tagDSFile const * const,wchar_t const *,ulong *)
0x18001eaf1  mov     ebx, 2
0x18001eaf6  mov     r12d, dword ptr [rsp+210h+var_1C0]
0x18001eafb  mov     edi, eax
0x18001eafd  mov     rax, [rsp+210h+var_1A8]
0x18001eb02  mov     rax, [rax+r13+8]
0x18001eb07  mov     [rsp+210h+var_1C8], rax
0x18001eb0c  test    edi, edi
0x18001eb0e  js      loc_18001EDF8
0x18001eb14  sub     ebx, 1
0x18001eb17  jz      short loc_18001EB35
0x18001eb19  mov     r14, [rbp+110h+var_190]
0x18001eb1d  cmp     ebx, 1
0x18001eb20  jz      short loc_18001EB2E
0x18001eb22  mov     rdx, [rsp+210h+var_1A0]
0x18001eb27  mov     r12d, [rsp+210h+var_1D0]
0x18001eb2c  jmp     short loc_18001EB40
0x18001eb2e  mov     rdx, [rsp+210h+var_198]
0x18001eb33  jmp     short loc_18001EB40
0x18001eb35  mov     rdx, [rbp+110h+var_188]
0x18001eb39  mov     r12d, r14d
0x18001eb3c  mov     r14, [rbp+110h+var_178]
0x18001eb40  mov     eax, r12d
0x18001eb43  imul    rax, 0F8h
0x18001eb4a  add     rax, rdx
0x18001eb4d  lea     rcx, [rbp+110h+len]
0x18001eb51  movups  xmm0, xmmword ptr [rax]
0x18001eb54  movups  xmmword ptr [rcx], xmm0
0x18001eb57  movups  xmm1, xmmword ptr [rax+10h]
0x18001eb5b  movups  xmmword ptr [rcx+10h], xmm1
0x18001eb5f  movups  xmm0, xmmword ptr [rax+20h]
0x18001eb63  movups  xmmword ptr [rcx+20h], xmm0
0x18001eb67  movups  xmm1, xmmword ptr [rax+30h]
0x18001eb6b  movups  xmmword ptr [rcx+30h], xmm1
0x18001eb6f  movups  xmm0, xmmword ptr [rax+40h]
0x18001eb73  movups  xmmword ptr [rcx+40h], xmm0
0x18001eb77  movups  xmm1, xmmword ptr [rax+50h]
0x18001eb7b  movups  xmmword ptr [rcx+50h], xmm1
0x18001eb7f  movups  xmm0, xmmword ptr [rax+60h]
0x18001eb83  movups  xmmword ptr [rcx+60h], xmm0
0x18001eb87  mov     edx, 80h
0x18001eb8c  add     rcx, rdx
0x18001eb8f  movups  xmm1, xmmword ptr [rax+70h]
0x18001eb93  movups  xmmword ptr [rcx-10h], xmm1
0x18001eb97  add     rax, rdx
0x18001eb9a  movups  xmm0, xmmword ptr [rax]
0x18001eb9d  movups  xmmword ptr [rcx], xmm0
0x18001eba0  movups  xmm1, xmmword ptr [rax+10h]
0x18001eba4  movups  xmmword ptr [rcx+10h], xmm1
0x18001eba8  movups  xmm0, xmmword ptr [rax+20h]
0x18001ebac  movups  xmmword ptr [rcx+20h], xmm0
0x18001ebb0  movups  xmm1, xmmword ptr [rax+30h]
0x18001ebb4  movups  xmmword ptr [rcx+30h], xmm1
0x18001ebb8  movups  xmm0, xmmword ptr [rax+40h]
0x18001ebbc  movups  xmmword ptr [rcx+40h], xmm0
0x18001ebc0  movups  xmm1, xmmword ptr [rax+50h]
0x18001ebc4  movups  xmmword ptr [rcx+50h], xmm1
0x18001ebc8  movups  xmm0, xmmword ptr [rax+60h]
0x18001ebcc  movups  xmmword ptr [rcx+60h], xmm0
0x18001ebd0  mov     rax, [rax+70h]
0x18001ebd4  mov     [rcx+70h], rax
0x18001ebd8  xor     ecx, ecx; bstrString
0x18001ebda  call    cs:__imp_SysFreeString
0x18001ebe0  mov     ebx, [rbp+110h+len]
0x18001ebe3  mov     [rsp+210h+var_1D0], ebx
0x18001ebe7  mov     edx, ebx; len
0x18001ebe9  mov     rax, [rbp+110h+psz]
0x18001ebed  mov     [rsp+210h+var_1C0], rax
0x18001ebf2  mov     rcx, rax; psz
0x18001ebf5  call    cs:__imp_SysAllocStringByteLen
0x18001ebfb  mov     rdi, rax
0x18001ebfe  mov     [rbp+110h+var_160], rax
0x18001ec02  test    rax, rax
0x18001ec05  jz      loc_18001EDCA
0x18001ec0b  mov     [rbp+110h+var_50], 0
0x18001ec15  mov     rax, [r14]
0x18001ec18  lea     r8, [rbp+110h+var_50]
0x18001ec1f  mov     rdx, rdi
0x18001ec22  mov     rcx, r14
0x18001ec25  mov     rax, [rax+88h]
0x18001ec2c  call    _guard_dispatch_icall
0x18001ec31  mov     esi, eax
0x18001ec33  test    eax, eax
0x18001ec35  js      loc_18001EDC3
0x18001ec3b  cmp     [rbp+110h+var_50], 0
0x18001ec42  jnz     loc_18001ED5F
0x18001ec48  mov     rax, [rsp+210h+var_1A8]
0x18001ec4d  mov     r12d, [rax+r13+10h]
0x18001ec52  test    r12d, r12d
0x18001ec55  jnz     short loc_18001EC8C
0x18001ec57  mov     rax, [rbp+110h+var_68]
0x18001ec5e  mov     [rsp+210h+var_1F0], rax; unsigned __int64
0x18001ec63  mov     r9d, ebx; unsigned int
0x18001ec66  mov     r8, [rsp+210h+var_1C0]; unsigned __int8 *
0x18001ec6b  mov     rdx, [rsp+210h+var_1C8]; wchar_t *
0x18001ec70  mov     rcx, r14; struct ISusFileRequestList *
0x18001ec73  call    ?AddFileToDownloadRequest@@YAJPEAUISusFileRequestList@@PEB_WQEAEK_K@Z; AddFileToDownloadRequest(ISusFileRequestList *,wchar_t const *,uchar * const,ulong,unsigned __int64)
0x18001ec78  mov     esi, eax
0x18001ec7a  test    eax, eax
0x18001ec7c  jns     loc_18001ED59
0x18001ec82  mov     edx, 109h
0x18001ec87  jmp     loc_18001EDD4
0x18001ec8c  mov     [rbp+110h+var_170], r12
0x18001ec90  mov     eax, 10h
0x18001ec95  mul     r12
0x18001ec98  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ec9f  cmovb   rax, rcx
0x18001eca3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ecaa  mov     rcx, rax; unsigned __int64
0x18001ecad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ecb2  mov     rbx, rax
0x18001ecb5  test    rax, rax
0x18001ecb8  jz      short loc_18001ECCB
0x18001ecba  mov     r8, r12
0x18001ecbd  shl     r8, 4; Size
0x18001ecc1  xor     edx, edx; Val
0x18001ecc3  mov     rcx, rax; void *
0x18001ecc6  call    memset
0x18001eccb  mov     [rbp+110h+var_158], rbx
0x18001eccf  mov     rax, rbx
0x18001ecd2  neg     rax
0x18001ecd5  sbb     esi, esi
0x18001ecd7  not     esi
0x18001ecd9  and     esi, 8007000Eh
0x18001ecdf  test    rbx, rbx
0x18001ece2  jz      loc_18001ED98
0x18001ece8  test    r12d, r12d
0x18001eceb  jz      short loc_18001ED1E
0x18001eced  xor     edx, edx
0x18001ecef  mov     r8, [rbp+110h+var_170]
0x18001ecf3  mov     r15, [rsp+210h+var_1A8]
0x18001ecf8  mov     rax, [r15+r13+18h]
0x18001ecfd  mov     rcx, [rdx+rax+8]
0x18001ed02  mov     rax, [rdx+rax]
0x18001ed06  mov     [rdx+rbx], rax
0x18001ed0a  mov     [rdx+rbx+8], rcx
0x18001ed0f  lea     rdx, [rdx+10h]
0x18001ed13  sub     r8, 1
0x18001ed17  jnz     short loc_18001ECF8
0x18001ed19  mov     r15d, [rsp+210h+var_1B8]
0x18001ed1e  mov     [rsp+210h+var_1E0], r12d; unsigned int
0x18001ed23  mov     [rsp+210h+var_1E8], rbx; struct tagSusFileRange *
0x18001ed28  mov     rax, [rbp+110h+var_68]
0x18001ed2f  mov     [rsp+210h+var_1F0], rax; unsigned __int64
0x18001ed34  mov     r9d, [rsp+210h+var_1D0]; unsigned int
0x18001ed39  mov     r8, [rsp+210h+var_1C0]; unsigned __int8 *
0x18001ed3e  mov     rdx, [rsp+210h+var_1C8]; wchar_t *
0x18001ed43  mov     rcx, r14; struct ISusFileRequestList *
0x18001ed46  call    ?AddFileToDownloadRequest@@YAJPEAUISusFileRequestList@@PEB_WQEAEK_KQEAUtagSusFileRange@@K@Z; AddFileToDownloadRequest(ISusFileRequestList *,wchar_t const *,uchar * const,ulong,unsigned __int64,tagSusFileRange * const,ulong)
0x18001ed4b  mov     esi, eax
0x18001ed4d  test    eax, eax
0x18001ed4f  js      short loc_18001ED8E
0x18001ed51  mov     rcx, rbx; void *
0x18001ed54  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ed59  mov     rax, [rbp+110h+var_168]
0x18001ed5d  inc     dword ptr [rax]
0x18001ed5f  mov     rcx, rdi; bstrString
0x18001ed62  call    cs:__imp_SysFreeString
0x18001ed68  mov     eax, [rsp+210h+var_1B4]
0x18001ed6c  inc     eax
0x18001ed6e  mov     [rsp+210h+var_1B4], eax
0x18001ed72  cmp     eax, r15d
0x18001ed75  jnb     loc_18001EE31
0x18001ed7b  mov     rcx, [rbp+110h+var_180]
0x18001ed7f  mov     rdx, [rsp+210h+var_1A0]
0x18001ed84  mov     r10d, [rsp+210h+var_1B0]
0x18001ed89  jmp     loc_18001EA66
0x18001ed8e  mov     r9d, eax
0x18001ed91  mov     edx, 11Eh
0x18001ed96  jmp     short loc_18001EDA0
0x18001ed98  mov     r9d, esi; char *
0x18001ed9b  mov     edx, 10Eh; void *
0x18001eda0  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001eda7  mov     rcx, [rbp+118h]; this
0x18001edae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001edb3  nop
0x18001edb4  test    rbx, rbx
0x18001edb7  jz      short loc_18001EDEB
0x18001edb9  mov     rcx, rbx; void *
0x18001edbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001edc1  jmp     short loc_18001EDEB
0x18001edc3  mov     edx, 0F8h
0x18001edc8  jmp     short loc_18001EDD4
0x18001edca  mov     esi, 8007000Eh
0x18001edcf  mov     edx, 0F5h; void *
0x18001edd4  mov     rcx, [rbp+118h]; this
0x18001eddb  mov     r9d, esi; char *
0x18001edde  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001ede5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001edea  nop
0x18001edeb  mov     rcx, rdi; bstrString
0x18001edee  call    cs:__imp_SysFreeString
0x18001edf4  mov     eax, esi
0x18001edf6  jmp     short loc_18001EE33
0x18001edf8  mov     rcx, [rbp+118h]; this
0x18001edff  mov     [rsp+210h+var_1D8], ebx
0x18001ee03  mov     qword ptr [rsp+210h+var_1E0], rsi
0x18001ee08  mov     [rsp+210h+var_1E8], rax; char *
0x18001ee0d  lea     rax, aGetupdatefilei; "GetUpdateFileInfo failed for the file "...
  ... truncated ...
```
