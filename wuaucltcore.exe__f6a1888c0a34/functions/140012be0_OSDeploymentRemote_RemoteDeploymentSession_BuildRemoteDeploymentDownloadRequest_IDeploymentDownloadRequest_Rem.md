# OSDeploymentRemote::RemoteDeploymentSession::BuildRemoteDeploymentDownloadRequest(IDeploymentDownloadRequest &,RemoteDeploymentDownloadRequest * *)

- ea: `0x140012be0`
- end: `0x1400132a4`
- name: `?BuildRemoteDeploymentDownloadRequest@RemoteDeploymentSession@OSDeploymentRemote@@AEAAJAEAUIDeploymentDownloadRequest@@PEAPEAURemoteDeploymentDownloadRequest@@@Z`
- size: `1732`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteDeploymentSession *__hidden this, struct IDeploymentDownloadRequest *, struct RemoteDeploymentDownloadRequest **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140012990`

## callees

- `0x140002ac0`
- `0x14000b1f4`
- `0x14000c980`
- `0x140012be0`
- `0x140013558`
- `0x140013680`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012fbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001301c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400130fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001312c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012fbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001301c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400130fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001312c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012e88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012e88`

## pseudocode

```c
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSession::BuildRemoteDeploymentDownloadRequest(
        OSDeploymentRemote::RemoteDeploymentSession *this,
        struct IDeploymentDownloadRequest *a2,
        struct RemoteDeploymentDownloadRequest **a3)
{
  struct RemoteDeploymentDownloadRequest **v3; // r14
  unsigned int v5; // r15d
  _DWORD *v7; // rsi
  signed int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  SIZE_T v12; // rbx
  _OWORD *v13; // rax
  _OWORD *v14; // rcx
  unsigned int v15; // r13d
  unsigned int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // r14
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // eax
  SIZE_T v24; // rdi
  char *v25; // rax
  char *v26; // rbx
  char *i; // rcx
  unsigned int v28; // ecx
  __int64 v29; // rax
  int v30; // eax
  LPVOID v31; // rax
  void *v32; // rcx
  unsigned __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  void *v38; // rcx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  _DWORD *v42; // [rsp+20h] [rbp-69h] BYREF
  char *v43; // [rsp+28h] [rbp-61h]
  struct RemoteDeploymentDownloadRequest **v44; // [rsp+30h] [rbp-59h]
  _QWORD v45[2]; // [rsp+38h] [rbp-51h] BYREF
  char v46; // [rsp+48h] [rbp-41h]
  char *v47; // [rsp+50h] [rbp-39h]
  unsigned int v48; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v49; // [rsp+5Ch] [rbp-2Dh] BYREF
  LPVOID v50; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v51; // [rsp+68h] [rbp-21h] BYREF
  __int64 v52; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v53; // [rsp+78h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-9h] BYREF
  wchar_t *v55; // [rsp+88h] [rbp-1h] BYREF
  __int64 *v56; // [rsp+90h] [rbp+7h] BYREF
  wchar_t *v57; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = a3;
  v44 = a3;
  v5 = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)0x80004003LL,
      (int)v42);
    return 2147500035LL;
  }
  v42 = 0;
  WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(&v42);
  v7 = CoTaskMemAlloc(0x28u);
  *(_QWORD *)v7 = 0;
  v7[6] = 0;
  *((_QWORD *)v7 + 4) = 0;
  v42 = v7;
  v8 = v7 == 0 ? 0x8007000E : 0;
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)(unsigned int)v8,
      0);
    goto LABEL_99;
  }
  v9 = *(_QWORD *)a2;
  v56 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 **))(v9 + 40))(a2, &v56);
  if ( v8 < 0 )
  {
    v10 = 353;
LABEL_9:
    v11 = (unsigned int)v8;
LABEL_85:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)v11,
      (int)v42);
    goto LABEL_97;
  }
  v48 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v56 + 24))(v56, &v48);
  if ( v8 < 0 )
  {
    v10 = 356;
    goto LABEL_9;
  }
  if ( !v48 )
  {
    v7[6] = 0;
    *((_QWORD *)v7 + 4) = 0;
    goto LABEL_83;
  }
  v12 = 2LL * v48;
  v13 = CoTaskMemAlloc(v12 * 16);
  v50 = v13;
  if ( v13 )
  {
    v14 = &v13[v12];
    if ( v13 != &v13[v12] )
    {
      do
      {
        *v13 = 0;
        v13[1] = 0;
        v13 += 2;
      }
      while ( v13 != v14 );
      v13 = v50;
    }
  }
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)0x8007000ELL,
      (int)v42);
    v8 = -2147024882;
    goto LABEL_81;
  }
  v45[0] = &v48;
  v45[1] = &v50;
  v46 = 1;
  v15 = 0;
  v16 = v48;
  if ( !v48 )
  {
LABEL_49:
    v7[6] = v16;
    v31 = v50;
    v50 = 0;
    *((_QWORD *)v7 + 4) = v31;
    v46 = 0;
    wil::details::lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___::_lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___(v45);
    v32 = v50;
    v50 = 0;
    if ( v32 )
      CoTaskMemFree(v32);
LABEL_83:
    v39 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, _DWORD *))(*(_QWORD *)a2 + 32LL))(a2, v7 + 2);
    v8 = v39;
    if ( v39 < 0 )
    {
      v11 = (unsigned int)v39;
      v10 = 436;
      goto LABEL_85;
    }
    *((_QWORD *)v7 + 2) = 0;
    v40 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, _DWORD *))(*(_QWORD *)a2 + 56LL))(a2, v7 + 4);
    if ( v40 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v40,
        (int)v42);
      *((_QWORD *)v7 + 2) = 0;
    }
    v57 = 0;
    if ( (*(int (__fastcall **)(struct IDeploymentDownloadRequest *, wchar_t **))(*(_QWORD *)a2 + 24LL))(a2, &v57) >= 0
      && v57 )
    {
      v41 = CoDuplicateString(v57, (wchar_t **)v7);
      v8 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C0,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
          (const char *)(unsigned int)v41,
          (int)v42);
LABEL_94:
        v38 = v57;
        goto LABEL_95;
      }
    }
    else
    {
      *(_QWORD *)v7 = 0;
    }
    v42 = 0;
    *v3 = (struct RemoteDeploymentDownloadRequest *)v7;
    v8 = 0;
    goto LABEL_94;
  }
  while ( 1 )
  {
    v51 = 0;
    v17 = *v56;
    v51 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v17 + 32))(v56, v15, &v51);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v18,
        (int)v42);
      goto LABEL_78;
    }
    v55 = 0;
    v19 = *v51;
    v55 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v19 + 40))(v51, &v55);
    if ( v8 < 0 )
    {
      v37 = 387;
      goto LABEL_74;
    }
    v20 = 32LL * v15;
    v8 = CoDuplicateString(v55, (wchar_t **)((char *)v50 + v20 + 8));
    if ( v8 < 0 )
    {
      v37 = 388;
LABEL_74:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v8,
        (int)v42);
      goto LABEL_75;
    }
    pv = 0;
    v21 = *v51;
    pv = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v21 + 24))(v51, &pv);
    if ( v8 < 0 )
    {
      v36 = 391;
      goto LABEL_69;
    }
    v8 = CoDuplicateString((const wchar_t *)pv, (wchar_t **)((char *)v50 + v20));
    if ( v8 < 0 )
    {
      v36 = 392;
LABEL_69:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v8,
        (int)v42);
      goto LABEL_70;
    }
    v53 = 0;
    v22 = *v51;
    v53 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v22 + 48))(v51, &v53);
    v8 = v23;
    if ( v23 < 0 )
    {
      v35 = 395;
      goto LABEL_63;
    }
    if ( !v53 )
    {
      *(_DWORD *)((char *)v50 + v20 + 16) = 0;
      *(_QWORD *)((char *)v50 + v20 + 24) = 0;
      goto LABEL_39;
    }
    v49 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v53 + 24))(v53, &v49);
    v8 = v23;
    if ( v23 < 0 )
    {
      v35 = 401;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)(unsigned int)v23,
        (int)v42);
      goto LABEL_64;
    }
    v24 = 16LL * v49;
    v25 = (char *)CoTaskMemAlloc(v24);
    v26 = v25;
    v47 = v25;
    if ( v25 )
    {
      for ( i = &v25[v24]; v25 != i; v25 += 16 )
        *(_OWORD *)v25 = 0;
    }
    if ( !v26 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
        (const char *)0x8007000ELL,
        (int)v42);
      goto LABEL_59;
    }
    v28 = v49;
    if ( v49 )
      break;
LABEL_37:
    *(_DWORD *)((char *)v50 + v20 + 16) = v28;
    *(_QWORD *)((char *)v50 + v20 + 24) = v26;
    v5 = 0;
LABEL_39:
    if ( v53 )
      (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v55 )
      CoTaskMemFree(v55);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    ++v15;
    v16 = v48;
    if ( v15 >= v48 )
    {
      v3 = v44;
      goto LABEL_49;
    }
  }
  while ( 1 )
  {
    v52 = 0;
    v29 = *v53;
    v52 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v29 + 32))(v53, v5, &v52);
    if ( v8 < 0 )
      break;
    v43 = &v26[16 * v5];
    v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v52 + 32LL))(v52, v43 + 8);
    if ( v8 < 0 )
    {
      v34 = 411;
      goto LABEL_54;
    }
    v30 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v52 + 24LL))(v52, v43);
    v8 = v30;
    if ( v30 < 0 )
    {
      v33 = (unsigned int)v30;
      v34 = 412;
      goto LABEL_55;
    }
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    ++v5;
    v28 = v49;
    if ( v5 >= v49 )
      goto LABEL_37;
  }
  v34 = 409;
LABEL_54:
  v33 = (unsigned int)v8;
LABEL_55:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v34,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
    (const char *)v33,
    (int)v42);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
LABEL_59:
  if ( v26 )
    CoTaskMemFree(v26);
LABEL_64:
  if ( v53 )
    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
LABEL_70:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_75:
  if ( v55 )
    CoTaskMemFree(v55);
LABEL_78:
  if ( v51 )
    (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
  wil::details::lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___::_lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___(v45);
LABEL_81:
  v38 = v50;
  v50 = 0;
LABEL_95:
  if ( v38 )
    CoTaskMemFree(v38);
LABEL_97:
  if ( v56 )
    (*(void (__fastcall **)(__int64 *))(*v56 + 16))(v56);
LABEL_99:
  WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(&v42);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140012be0  mov     [rsp-8+arg_0], rbx
0x140012be5  push    rbp
0x140012be6  push    rsi
0x140012be7  push    rdi
0x140012be8  push    r12
0x140012bea  push    r13
0x140012bec  push    r14
0x140012bee  push    r15
0x140012bf0  lea     rbp, [rsp-27h]
0x140012bf5  sub     rsp, 0B0h
0x140012bfc  mov     rax, cs:__security_cookie
0x140012c03  xor     rax, rsp
0x140012c06  mov     [rbp+57h+var_40], rax
0x140012c0a  mov     r14, r8
0x140012c0d  mov     [rbp+57h+var_B0], r8
0x140012c11  mov     r12, rdx
0x140012c14  xor     r15d, r15d
0x140012c17  test    r8, r8
0x140012c1a  jnz     short loc_140012C40
0x140012c1c  mov     rcx, [rbp+5Fh]; this
0x140012c20  mov     ebx, 80004003h
0x140012c25  mov     r9d, ebx; char *
0x140012c28  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012c2f  mov     edx, 15Bh; void *
0x140012c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c39  mov     eax, ebx
0x140012c3b  jmp     loc_14001327D
0x140012c40  mov     [rbp+57h+var_C0], r15
0x140012c44  lea     rcx, [rbp+57h+var_C0]
0x140012c48  call    ?InternalRelease@?$XPtrBase@URemoteDeploymentDownloadRequest@@URemoteDeploymentRequestPolicy@OSDeploymentRemote@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(void)
0x140012c4d  mov     ecx, 28h ; '('; cb
0x140012c52  call    cs:__imp_CoTaskMemAlloc
0x140012c58  mov     rsi, rax
0x140012c5b  mov     [rax], r15
0x140012c5e  mov     [rax+18h], r15d
0x140012c62  mov     [rax+20h], r15
0x140012c66  mov     [rbp+57h+var_C0], rax
0x140012c6a  mov     rcx, rax
0x140012c6d  neg     rcx
0x140012c70  sbb     edi, edi
0x140012c72  not     edi
0x140012c74  mov     r13d, 8007000Eh
0x140012c7a  and     edi, r13d
0x140012c7d  test    rax, rax
0x140012c80  jnz     short loc_140012C9F
0x140012c82  mov     rcx, [rbp+5Fh]; this
0x140012c86  mov     r9d, edi; char *
0x140012c89  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012c90  mov     edx, 15Eh; void *
0x140012c95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c9a  jmp     loc_140013272
0x140012c9f  mov     rax, [r12]
0x140012ca3  mov     [rbp+57h+var_50], r15
0x140012ca7  lea     rdx, [rbp+57h+var_50]
0x140012cab  mov     rcx, r12
0x140012cae  mov     rax, [rax+28h]
0x140012cb2  call    _guard_dispatch_icall
0x140012cb7  mov     edi, eax
0x140012cb9  test    eax, eax
0x140012cbb  jns     short loc_140012CC4
0x140012cbd  mov     edx, 161h
0x140012cc2  jmp     short loc_140012CE7
0x140012cc4  mov     [rbp+57h+var_88], r15d
0x140012cc8  mov     rcx, [rbp+57h+var_50]
0x140012ccc  mov     rax, [rcx]
0x140012ccf  lea     rdx, [rbp+57h+var_88]
0x140012cd3  mov     rax, [rax+18h]
0x140012cd7  call    _guard_dispatch_icall
0x140012cdc  mov     edi, eax
0x140012cde  test    eax, eax
0x140012ce0  jns     short loc_140012CEF
0x140012ce2  mov     edx, 164h
0x140012ce7  mov     r9d, edi
0x140012cea  jmp     loc_1400131A4
0x140012cef  mov     eax, [rbp+57h+var_88]
0x140012cf2  test    eax, eax
0x140012cf4  jz      loc_14001317A
0x140012cfa  mov     ebx, eax
0x140012cfc  shl     rbx, 5
0x140012d00  mov     rcx, rbx; cb
0x140012d03  call    cs:__imp_CoTaskMemAlloc
0x140012d09  mov     [rbp+57h+var_80], rax
0x140012d0d  test    rax, rax
0x140012d10  jz      short loc_140012D32
0x140012d12  lea     rcx, [rbx+rax]
0x140012d16  cmp     rax, rcx
0x140012d19  jz      short loc_140012D32
0x140012d1b  xorps   xmm0, xmm0
0x140012d1e  movups  xmmword ptr [rax], xmm0
0x140012d21  movups  xmmword ptr [rax+10h], xmm0
0x140012d25  add     rax, 20h ; ' '
0x140012d29  cmp     rax, rcx
0x140012d2c  jnz     short loc_140012D1B
0x140012d2e  mov     rax, [rbp+57h+var_80]
0x140012d32  test    rax, rax
0x140012d35  jnz     short loc_140012D57
0x140012d37  mov     rcx, [rbp+5Fh]; this
0x140012d3b  mov     r9d, r13d; char *
0x140012d3e  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012d45  mov     edx, 169h; void *
0x140012d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012d4f  mov     edi, r13d
0x140012d52  jmp     loc_14001316D
0x140012d57  lea     rax, [rbp+57h+var_88]
0x140012d5b  mov     [rbp+57h+var_A8], rax
0x140012d5f  lea     rax, [rbp+57h+var_80]
0x140012d63  mov     [rbp+57h+var_A0], rax
0x140012d67  mov     [rbp+57h+var_98], 1
0x140012d6b  mov     r13d, r15d
0x140012d6e  mov     eax, [rbp+57h+var_88]
0x140012d71  test    eax, eax
0x140012d73  jz      loc_140012FEE
0x140012d79  mov     [rbp+57h+var_78], r15
0x140012d7d  mov     rcx, [rbp+57h+var_50]
0x140012d81  mov     rax, [rcx]
0x140012d84  mov     [rbp+57h+var_78], r15
0x140012d88  lea     r8, [rbp+57h+var_78]
0x140012d8c  mov     edx, r13d
0x140012d8f  mov     rax, [rax+20h]
0x140012d93  call    _guard_dispatch_icall
0x140012d98  mov     edi, eax
0x140012d9a  test    eax, eax
0x140012d9c  js      loc_140013134
0x140012da2  mov     [rbp+57h+var_58], r15
0x140012da6  mov     rcx, [rbp+57h+var_78]
0x140012daa  mov     rax, [rcx]
0x140012dad  mov     [rbp+57h+var_58], r15
0x140012db1  lea     rdx, [rbp+57h+var_58]
0x140012db5  mov     rax, [rax+28h]
0x140012db9  call    _guard_dispatch_icall
0x140012dbe  mov     edi, eax
0x140012dc0  test    eax, eax
0x140012dc2  js      loc_14001310A
0x140012dc8  mov     r14d, r13d
0x140012dcb  shl     r14, 5
0x140012dcf  mov     rdx, [rbp+57h+var_80]
0x140012dd3  add     rdx, 8
0x140012dd7  add     rdx, r14; wchar_t **
0x140012dda  mov     rcx, [rbp+57h+var_58]; wchar_t *
0x140012dde  call    ?CoDuplicateString@@YAJPEB_WPEAPEA_W@Z; CoDuplicateString(wchar_t const *,wchar_t * *)
0x140012de3  mov     edi, eax
0x140012de5  test    eax, eax
0x140012de7  js      loc_140013103
0x140012ded  mov     [rbp+57h+pv], r15
0x140012df1  mov     rcx, [rbp+57h+var_78]
0x140012df5  mov     rax, [rcx]
0x140012df8  mov     [rbp+57h+pv], r15
0x140012dfc  lea     rdx, [rbp+57h+pv]
0x140012e00  mov     rax, [rax+18h]
0x140012e04  call    _guard_dispatch_icall
0x140012e09  mov     edi, eax
0x140012e0b  test    eax, eax
0x140012e0d  js      loc_1400130D9
0x140012e13  mov     rdx, [rbp+57h+var_80]
0x140012e17  add     rdx, r14; wchar_t **
0x140012e1a  mov     rcx, [rbp+57h+pv]; wchar_t *
0x140012e1e  call    ?CoDuplicateString@@YAJPEB_WPEAPEA_W@Z; CoDuplicateString(wchar_t const *,wchar_t * *)
0x140012e23  mov     edi, eax
0x140012e25  test    eax, eax
0x140012e27  js      loc_1400130D2
0x140012e2d  mov     [rbp+57h+var_68], r15
0x140012e31  mov     rcx, [rbp+57h+var_78]
0x140012e35  mov     rax, [rcx]
0x140012e38  mov     [rbp+57h+var_68], r15
0x140012e3c  lea     rdx, [rbp+57h+var_68]
0x140012e40  mov     rax, [rax+30h]
0x140012e44  call    _guard_dispatch_icall
0x140012e49  mov     edi, eax
0x140012e4b  test    eax, eax
0x140012e4d  js      loc_1400130A1
0x140012e53  mov     rcx, [rbp+57h+var_68]
0x140012e57  test    rcx, rcx
0x140012e5a  jz      loc_140012F7D
0x140012e60  mov     [rbp+57h+var_84], r15d
0x140012e64  mov     rax, [rcx]
0x140012e67  lea     rdx, [rbp+57h+var_84]
0x140012e6b  mov     rax, [rax+18h]
0x140012e6f  call    _guard_dispatch_icall
0x140012e74  mov     edi, eax
0x140012e76  test    eax, eax
0x140012e78  js      loc_14001309A
0x140012e7e  mov     edi, [rbp+57h+var_84]
0x140012e81  shl     rdi, 4
0x140012e85  mov     rcx, rdi; cb
0x140012e88  call    cs:__imp_CoTaskMemAlloc
0x140012e8e  mov     rbx, rax
0x140012e91  mov     [rbp+57h+var_90], rax
0x140012e95  test    rax, rax
0x140012e98  jz      short loc_140012EB2
0x140012e9a  lea     rcx, [rdi+rax]
0x140012e9e  cmp     rax, rcx
0x140012ea1  jz      short loc_140012EB2
0x140012ea3  xorps   xmm0, xmm0
0x140012ea6  movups  xmmword ptr [rax], xmm0
0x140012ea9  add     rax, 10h
0x140012ead  cmp     rax, rcx
0x140012eb0  jnz     short loc_140012EA3
0x140012eb2  test    rbx, rbx
0x140012eb5  jz      loc_14001306C
0x140012ebb  mov     ecx, [rbp+57h+var_84]
0x140012ebe  test    ecx, ecx
0x140012ec0  jz      loc_140012F66
0x140012ec6  mov     [rbp+57h+var_70], 0
0x140012ece  mov     rcx, [rbp+57h+var_68]
0x140012ed2  mov     rax, [rcx]
0x140012ed5  mov     [rbp+57h+var_70], 0
0x140012edd  lea     r8, [rbp+57h+var_70]
0x140012ee1  mov     edx, r15d
0x140012ee4  mov     rax, [rax+20h]
0x140012ee8  call    _guard_dispatch_icall
0x140012eed  mov     edi, eax
0x140012eef  test    eax, eax
0x140012ef1  js      loc_140013038
0x140012ef7  mov     eax, r15d
0x140012efa  shl     rax, 4
0x140012efe  add     rax, rbx
0x140012f01  mov     [rbp+57h+var_B8], rax
0x140012f05  lea     rdx, [rax+8]
0x140012f09  mov     rcx, [rbp+57h+var_70]
0x140012f0d  mov     rax, [rcx]
0x140012f10  mov     rax, [rax+20h]
0x140012f14  call    _guard_dispatch_icall
0x140012f19  mov     edi, eax
0x140012f1b  test    eax, eax
0x140012f1d  js      loc_140013031
0x140012f23  mov     rcx, [rbp+57h+var_70]
0x140012f27  mov     rax, [rcx]
0x140012f2a  mov     rdx, [rbp+57h+var_B8]
0x140012f2e  mov     rax, [rax+18h]
0x140012f32  call    _guard_dispatch_icall
0x140012f37  mov     edi, eax
0x140012f39  test    eax, eax
0x140012f3b  js      loc_140013027
0x140012f41  mov     rcx, [rbp+57h+var_70]
0x140012f45  test    rcx, rcx
0x140012f48  jz      short loc_140012F57
0x140012f4a  mov     rax, [rcx]
0x140012f4d  mov     rax, [rax+10h]
0x140012f51  call    _guard_dispatch_icall
0x140012f56  nop
0x140012f57  inc     r15d
0x140012f5a  mov     ecx, [rbp+57h+var_84]
0x140012f5d  cmp     r15d, ecx
0x140012f60  jb      loc_140012EC6
0x140012f66  mov     rax, [rbp+57h+var_80]
0x140012f6a  mov     [r14+rax+10h], ecx
0x140012f6f  mov     rax, [rbp+57h+var_80]
0x140012f73  mov     [r14+rax+18h], rbx
0x140012f78  xor     r15d, r15d
0x140012f7b  jmp     short loc_140012F8F
0x140012f7d  mov     rax, [rbp+57h+var_80]
0x140012f81  mov     [r14+rax+10h], r15d
0x140012f86  mov     rax, [rbp+57h+var_80]
0x140012f8a  mov     [r14+rax+18h], r15
0x140012f8f  mov     rcx, [rbp+57h+var_68]
0x140012f93  test    rcx, rcx
0x140012f96  jz      short loc_140012FA5
0x140012f98  mov     rax, [rcx]
0x140012f9b  mov     rax, [rax+10h]
0x140012f9f  call    _guard_dispatch_icall
0x140012fa4  nop
0x140012fa5  mov     rcx, [rbp+57h+pv]; pv
0x140012fa9  test    rcx, rcx
0x140012fac  jz      short loc_140012FB5
0x140012fae  call    cs:__imp_CoTaskMemFree
0x140012fb4  nop
0x140012fb5  mov     rcx, [rbp+57h+var_58]; pv
0x140012fb9  test    rcx, rcx
0x140012fbc  jz      short loc_140012FC5
0x140012fbe  call    cs:__imp_CoTaskMemFree
0x140012fc4  nop
0x140012fc5  mov     rcx, [rbp+57h+var_78]
0x140012fc9  test    rcx, rcx
0x140012fcc  jz      short loc_140012FDB
0x140012fce  mov     rax, [rcx]
0x140012fd1  mov     rax, [rax+10h]
0x140012fd5  call    _guard_dispatch_icall
0x140012fda  nop
0x140012fdb  inc     r13d
0x140012fde  mov     eax, [rbp+57h+var_88]
0x140012fe1  cmp     r13d, eax
0x140012fe4  jb      loc_140012D79
0x140012fea  mov     r14, [rbp+57h+var_B0]
0x140012fee  mov     [rsi+18h], eax
0x140012ff1  mov     rax, [rbp+57h+var_80]
0x140012ff5  mov     [rbp+57h+var_80], r15
0x140012ff9  mov     [rsi+20h], rax
0x140012ffd  mov     [rbp+57h+var_98], r15b
0x140013001  lea     rcx, [rbp+57h+var_A8]
0x140013005  call    wil__details__lambda_call__lambda_6a1a599239bac35a2a982a97986e3018______lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___
0x14001300a  nop
0x14001300b  mov     rcx, [rbp+57h+var_80]; pv
0x14001300f  mov     [rbp+57h+var_80], r15
0x140013013  test    rcx, rcx
0x140013016  jz      loc_140013182
0x14001301c  call    cs:__imp_CoTaskMemFree
0x140013022  jmp     loc_140013182
0x140013027  mov     r9d, eax
0x14001302a  mov     edx, 19Ch
0x14001302f  jmp     short loc_140013040
  ... truncated ...
```
