# CContentDropTarget::_CanCreateObject(ushort const *,ushort const *,IPortableDevice *,IPortableDeviceContent *,COPY_THREAD_DATA *,ushort *,uint,int *)

- ea: `0x180015a90`
- end: `0x1800161eb`
- name: `?_CanCreateObject@CContentDropTarget@@AEAAJPEBG0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEAVCOPY_THREAD_DATA@@PEAGIPEAH@Z`
- size: `1883`
- prototype: `int(CContentDropTarget *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IPortableDevice *, struct IPortableDeviceContent *, struct COPY_THREAD_DATA *, unsigned __int16 *, unsigned int, int *)`
- caller_count: `6`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180012974`
- `0x180019e44`
- `0x18003c074`
- `0x18003cce4`
- `0x18003ee9c`
- `0x1800405e8`

## callees

- `0x180004110`
- `0x180014b60`
- `0x180015a90`
- `0x180016200`
- `0x180016260`
- `0x1800177dc`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039d74`
- `0x180054524`
- `0x1800545c8`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180015bd0`
- `KERNEL32!Sleep` at `0x180015d94`
- `KERNEL32!Sleep` at `0x180015f12`
- `KERNEL32!Sleep` at `0x180015bd0`
- `KERNEL32!Sleep` at `0x180015d94`
- `KERNEL32!Sleep` at `0x180015f12`
- `SHLWAPI!StrCmpIW` at `0x180015fe3`
- `SHLWAPI!StrCmpIW` at `0x180015ffa`
- `SHLWAPI!StrCmpIW` at `0x180015fe3`
- `SHLWAPI!StrCmpIW` at `0x180015ffa`
- `ole32!CoTaskMemFree` at `0x18001601d`
- `ole32!CoTaskMemFree` at `0x180016034`
- `ole32!CoTaskMemFree` at `0x1800160b2`
- `ole32!CoTaskMemFree` at `0x18001601d`
- `ole32!CoTaskMemFree` at `0x180016034`
- `ole32!CoTaskMemFree` at `0x1800160b2`
- `ole32!CoCreateInstance` at `0x180015c65`
- `ole32!CoCreateInstance` at `0x180015c65`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CContentDropTarget::_CanCreateObject(
        CContentDropTarget *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IPortableDevice *a4,
        struct IPortableDeviceContent *a5,
        CProgressUI **a6,
        unsigned __int16 *a7,
        unsigned int a8,
        int *a9)
{
  CProgressUI *v12; // r13
  _DWORD *v13; // r14
  int v14; // edi
  int v15; // ebx
  int v16; // r12d
  int PortableDeviceProperties; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct IPortableDeviceProperties *v20; // rbx
  HRESULT v21; // eax
  int v22; // ebx
  int v23; // edi
  int v24; // r12d
  int v25; // r15d
  const unsigned __int16 **v26; // rsi
  int v27; // edi
  int v28; // r12d
  int v29; // r13d
  bool v30; // zf
  int v31; // eax
  const WCHAR *v32; // rcx
  int v33; // eax
  WCHAR *v34; // rdi
  unsigned int i; // edi
  void *v36; // rcx
  int v38; // [rsp+30h] [rbp-D0h]
  unsigned int v39; // [rsp+34h] [rbp-CCh] BYREF
  struct IUnknown *v40; // [rsp+38h] [rbp-C8h] BYREF
  int v41; // [rsp+40h] [rbp-C0h]
  struct IPortableDeviceProperties *v42; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR v45; // [rsp+60h] [rbp-A0h]
  PCWSTR psz2; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  CProgressUI *v48; // [rsp+78h] [rbp-88h]
  WCHAR *v49; // [rsp+80h] [rbp-80h]
  PCWSTR psz1; // [rsp+88h] [rbp-78h]
  struct COPY_THREAD_DATA *v51; // [rsp+90h] [rbp-70h]
  CPerfTraceHelper *v52; // [rsp+98h] [rbp-68h]
  int *v53; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v54; // [rsp+A8h] [rbp-58h]
  _QWORD v55[10]; // [rsp+B0h] [rbp-50h] BYREF

  psz1 = a2;
  v53 = a9;
  v51 = (struct COPY_THREAD_DATA *)a6;
  v54 = a7;
  v48 = a6[557];
  v12 = v48;
  v44 = 0;
  psz2 = 0;
  memset_0(v55, 0, sizeof(v55));
  v39 = 0;
  v47 = 0;
  v42 = 0;
  ppv = 0;
  v40 = 0;
  v52 = (CPerfTraceHelper *)(a6 + 560);
  CPerfTraceHelper::BeginOperation((CPerfTraceHelper *)(a6 + 560), 6u);
  *a9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const PROPERTYKEY *))(**((_QWORD **)this + 10) + 72LL))(
          *((_QWORD *)this + 10),
          *(_QWORD *)(*((_QWORD *)this + 10) + 64LL),
          &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS) != 0;
  v13 = (_DWORD *)((char *)v12 + 104);
  if ( v12 )
  {
    v15 = 0;
    v16 = 0;
    while ( 1 )
    {
      if ( *v13 )
      {
LABEL_10:
        v14 = -2147023673;
        goto LABEL_12;
      }
      PortableDeviceProperties = GetPortableDeviceProperties(a4, &v42);
      if ( PortableDeviceProperties != -2147024726 )
        break;
      if ( !v15 )
      {
        v15 = 1;
        v16 = 1;
        CProgressUI::_StartMarquee(v12);
      }
      if ( *v13 )
        goto LABEL_10;
      Sleep(0x5DCu);
    }
    v14 = PortableDeviceProperties;
LABEL_12:
    if ( v16 )
      CProgressUI::_StopMarquee(v12);
    if ( *v13 )
    {
      v14 = -2147023673;
      goto LABEL_17;
    }
  }
  else
  {
    v14 = GetPortableDeviceProperties(a4, &v42);
  }
  if ( v14 < 0 )
  {
LABEL_17:
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_21;
    v19 = 94;
LABEL_20:
    WPP_SF_d(v18[2], v19, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v14);
LABEL_21:
    v20 = v42;
    goto LABEL_100;
  }
  v21 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &ppv);
  v14 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v21);
    CPerfTraceHelper::ProcessPerformanceData(v52, 6u, v14, (const unsigned __int16 *)v51 + 1444);
    v20 = v42;
    goto LABEL_101;
  }
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_NAME);
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ORIGINAL_FILE_NAME);
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_CAN_DELETE);
  if ( v12 )
  {
    v22 = 0;
    v23 = 0;
    while ( !*v13 )
    {
      v38 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, _QWORD, const unsigned __int16 *, _QWORD, __int64 *))a5->lpVtbl->EnumObjects)(
              a5,
              0,
              a3,
              0,
              &v47);
      if ( v38 != -2147024726 )
        goto LABEL_37;
      if ( !v22 )
      {
        v22 = 1;
        v23 = 1;
        CProgressUI::_StartMarquee(v12);
      }
      if ( *v13 )
        break;
      Sleep(0x5DCu);
    }
    v38 = -2147023673;
LABEL_37:
    if ( v23 )
      CProgressUI::_StopMarquee(v12);
    if ( *v13 )
    {
      v14 = -2147023673;
      goto LABEL_43;
    }
    v14 = v38;
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, _QWORD, const unsigned __int16 *, _QWORD, __int64 *))a5->lpVtbl->EnumObjects)(
            a5,
            0,
            a3,
            0,
            &v47);
    v38 = v14;
  }
  if ( v14 < 0 )
  {
LABEL_43:
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_21;
    v19 = 96;
    goto LABEL_20;
  }
  v45 = 0;
  v49 = 0;
  v24 = 0;
  v41 = 0;
  v20 = v42;
  do
  {
    if ( (*(int (__fastcall **)(__int64, __int64, _QWORD *, unsigned int *))(*(_QWORD *)v47 + 24LL))(v47, 10, v55, &v39) < 0 )
      goto LABEL_99;
    if ( !v39 )
      break;
    v25 = 0;
    while ( 1 )
    {
      v26 = (const unsigned __int16 **)&v55[v25];
      if ( !*v26 )
      {
LABEL_96:
        if ( v24 )
          goto LABEL_89;
        goto LABEL_97;
      }
      if ( v40 )
      {
        ((void (__fastcall *)(struct IUnknown *))v40->lpVtbl->Release)(v40);
        v40 = 0;
      }
      if ( v12 )
      {
        v28 = 0;
        v29 = 0;
        while ( !*v13 )
        {
          v27 = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, LPVOID, struct IUnknown **))v20->lpVtbl->GetValues)(
                  v20,
                  *v26,
                  ppv,
                  &v40);
          if ( v27 != -2147024726 )
            goto LABEL_65;
          if ( v40 )
            ATL::AtlComPtrAssign(&v40, 0);
          if ( !v28 )
          {
            v28 = 1;
            v29 = 1;
            CProgressUI::_StartMarquee(v48);
          }
          if ( *v13 )
            break;
          Sleep(0x5DCu);
        }
        v27 = -2147023673;
LABEL_65:
        v30 = v29 == 0;
        v12 = v48;
        if ( !v30 )
          CProgressUI::_StopMarquee(v48);
        v24 = v41;
        if ( *v13 )
          goto LABEL_96;
      }
      else
      {
        v27 = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, LPVOID, struct IUnknown **))v20->lpVtbl->GetValues)(
                v20,
                *v26,
                ppv,
                &v40);
      }
      if ( v27 < 0 )
        goto LABEL_96;
      v31 = ((__int64 (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v40->lpVtbl[2].Release)(
              v40,
              &WPD_OBJECT_NAME,
              &psz2);
      v32 = v45;
      if ( v31 >= 0 )
        v32 = psz2;
      v45 = v32;
      v33 = ((__int64 (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v40->lpVtbl[2].Release)(
              v40,
              &WPD_OBJECT_ORIGINAL_FILE_NAME,
              &psz2);
      v34 = v49;
      if ( v33 >= 0 )
        v34 = (WCHAR *)psz2;
      v49 = v34;
      if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, int *))v40->lpVtbl[8].QueryInterface)(
             v40,
             &WPD_OBJECT_CAN_DELETE,
             &v44) >= 0 )
        *v53 = v44;
      if ( v34 )
      {
        if ( StrCmpIW(psz1, v34) )
          goto LABEL_81;
        v24 = 1;
      }
      else if ( !StrCmpIW(psz1, v45) )
      {
        v24 = 1;
      }
      v41 = v24;
LABEL_81:
      if ( v45 )
      {
        CoTaskMemFree((LPVOID)v45);
        v45 = 0;
      }
      if ( v34 )
      {
        CoTaskMemFree(v34);
        v49 = 0;
      }
      if ( v24 )
        break;
LABEL_97:
      if ( ++v25 >= v39 )
        goto LABEL_89;
    }
    StringCchCopyW(v54, 0x104u, *v26);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, psz1);
LABEL_89:
    for ( i = 0; i < v39; ++i )
    {
      v36 = (void *)v55[i];
      if ( v36 )
      {
        CoTaskMemFree(v36);
        v55[i] = 0;
      }
    }
  }
  while ( !v24 );
  if ( v24 == 1 )
  {
    v14 = -2147024713;
    CPerfTraceHelper::ProcessPerformanceData(v52, 6u, -2147024713, (const unsigned __int16 *)v51 + 1444);
    goto LABEL_101;
  }
LABEL_99:
  v14 = v38;
LABEL_100:
  CPerfTraceHelper::ProcessPerformanceData(v52, 6u, v14, (const unsigned __int16 *)v51 + 1444);
  if ( v14 < 0 )
  {
LABEL_101:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v14);
  }
  if ( v40 )
    ((void (__fastcall *)(struct IUnknown *))v40->lpVtbl->Release)(v40);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v20 )
    ((void (__fastcall *)(struct IPortableDeviceProperties *))v20->lpVtbl->Release)(v20);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180015a90  push    rbp
0x180015a92  push    rbx
0x180015a93  push    rsi
0x180015a94  push    rdi
0x180015a95  push    r12
0x180015a97  push    r13
0x180015a99  push    r14
0x180015a9b  push    r15
0x180015a9d  lea     rbp, [rsp-18h]
0x180015aa2  sub     rsp, 118h
0x180015aa9  mov     rax, cs:__security_cookie
0x180015ab0  xor     rax, rsp
0x180015ab3  mov     [rbp+50h+var_50], rax
0x180015ab7  mov     rdi, r9
0x180015aba  mov     r15, r8
0x180015abd  mov     [rbp+50h+psz1], rdx
0x180015ac1  mov     rbx, rcx
0x180015ac4  mov     r12, [rbp+50h+arg_40]
0x180015acb  mov     [rbp+50h+var_B0], r12
0x180015acf  mov     rsi, [rbp+50h+arg_20]
0x180015ad6  mov     r14, [rbp+50h+arg_28]
0x180015add  mov     [rbp+50h+var_C0], r14
0x180015ae1  mov     rax, [rbp+50h+arg_30]
0x180015ae8  mov     [rbp+50h+var_A8], rax
0x180015aec  mov     r13, [r14+1168h]
0x180015af3  mov     [rsp+150h+var_D8], r13
0x180015af8  xor     eax, eax
0x180015afa  mov     [rsp+150h+var_F8], eax
0x180015afe  mov     [rsp+150h+psz2], rax
0x180015b03  xor     edx, edx; Val
0x180015b05  mov     r8d, 50h ; 'P'; Size
0x180015b0b  lea     rcx, [rbp+50h+var_A0]; void *
0x180015b0f  call    memset_0
0x180015b14  xor     eax, eax
0x180015b16  mov     [rsp+150h+var_11C], eax
0x180015b1a  mov     [rsp+150h+var_E0], rax
0x180015b1f  mov     [rsp+150h+var_108], rax
0x180015b24  mov     [rsp+150h+var_100], rax
0x180015b29  mov     [rsp+150h+var_118], rax
0x180015b2e  lea     rax, [r14+1180h]
0x180015b35  mov     [rbp+50h+var_B8], rax
0x180015b39  mov     edx, 6; unsigned int
0x180015b3e  mov     rcx, rax; this
0x180015b41  call    ?BeginOperation@CPerfTraceHelper@@QEAAXK@Z; CPerfTraceHelper::BeginOperation(ulong)
0x180015b46  mov     rcx, [rbx+50h]
0x180015b4a  mov     rax, [rcx]
0x180015b4d  lea     r8, WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS
0x180015b54  mov     rdx, [rcx+40h]
0x180015b58  mov     rax, [rax+48h]
0x180015b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b61  xor     edx, edx
0x180015b63  test    eax, eax
0x180015b65  setnz   dl
0x180015b68  mov     [r12], edx
0x180015b6c  lea     r14, [r13+68h]
0x180015b70  mov     r12d, 1
0x180015b76  test    r13, r13
0x180015b79  jnz     short loc_180015B8C
0x180015b7b  lea     rdx, [rsp+150h+var_108]; struct IPortableDeviceProperties **
0x180015b80  mov     rcx, rdi; struct IPortableDevice *
0x180015b83  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180015b88  mov     edi, eax
0x180015b8a  jmp     short loc_180015C09
0x180015b8c  xor     ebx, ebx
0x180015b8e  xor     r12d, r12d
0x180015b91  cmp     dword ptr [r14], 0
0x180015b95  jnz     short loc_180015BE0
0x180015b97  lea     rdx, [rsp+150h+var_108]; struct IPortableDeviceProperties **
0x180015b9c  mov     rcx, rdi; struct IPortableDevice *
0x180015b9f  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180015ba4  mov     [rsp+150h+var_120], eax
0x180015ba8  cmp     eax, 800700AAh
0x180015bad  jnz     short loc_180015BE7
0x180015baf  test    ebx, ebx
0x180015bb1  jnz     short loc_180015BC5
0x180015bb3  mov     eax, 1
0x180015bb8  mov     ebx, eax
0x180015bba  mov     r12d, eax
0x180015bbd  mov     rcx, r13; this
0x180015bc0  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180015bc5  cmp     dword ptr [r14], 0
0x180015bc9  jnz     short loc_180015BE0
0x180015bcb  mov     ecx, 5DCh; dwMilliseconds
0x180015bd0  call    cs:__imp_Sleep
0x180015bd6  test    ebx, ebx
0x180015bd8  jnz     short loc_180015B91
0x180015bda  mov     edi, [rsp+150h+var_120]
0x180015bde  jmp     short loc_180015BE9
0x180015be0  mov     edi, 800704C7h
0x180015be5  jmp     short loc_180015BE9
0x180015be7  mov     edi, eax
0x180015be9  test    r12d, r12d
0x180015bec  jz      short loc_180015BF6
0x180015bee  mov     rcx, r13; this
0x180015bf1  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180015bf6  cmp     dword ptr [r14], 0
0x180015bfa  jz      short loc_180015C03
0x180015bfc  mov     edi, 800704C7h
0x180015c01  jmp     short loc_180015C0D
0x180015c03  mov     r12d, 1
0x180015c09  test    edi, edi
0x180015c0b  jns     short loc_180015C48
0x180015c0d  lea     rsi, WPP_GLOBAL_Control
0x180015c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c1b  cmp     rcx, rsi
0x180015c1e  jz      short loc_180015C3E
0x180015c20  test    byte ptr [rcx+1Ch], 2
0x180015c24  jz      short loc_180015C3E
0x180015c26  mov     edx, 5Eh ; '^'
0x180015c2b  mov     r9d, edi
0x180015c2e  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180015c35  mov     rcx, [rcx+10h]
0x180015c39  call    WPP_SF_d
0x180015c3e  mov     rbx, [rsp+150h+var_108]
0x180015c43  jmp     loc_180016124
0x180015c48  lea     rax, [rsp+150h+var_100]
0x180015c4d  mov     [rsp+150h+ppv], rax; ppv
0x180015c52  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180015c59  mov     r8d, r12d; dwClsContext
0x180015c5c  xor     edx, edx; pUnkOuter
0x180015c5e  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180015c65  call    cs:__imp_CoCreateInstance
0x180015c6b  mov     edi, eax
0x180015c6d  test    eax, eax
0x180015c6f  jns     short loc_180015CC8
0x180015c71  lea     rsi, WPP_GLOBAL_Control
0x180015c78  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c7f  cmp     rcx, rsi
0x180015c82  jz      short loc_180015CA2
0x180015c84  test    byte ptr [rcx+1Ch], 2
0x180015c88  jz      short loc_180015CA2
0x180015c8a  mov     edx, 5Fh ; '_'
0x180015c8f  mov     r9d, eax
0x180015c92  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180015c99  mov     rcx, [rcx+10h]
0x180015c9d  call    WPP_SF_d
0x180015ca2  mov     r9, [rbp+50h+var_C0]
0x180015ca6  add     r9, 0B48h; unsigned __int16 *
0x180015cad  mov     r8d, edi; int
0x180015cb0  mov     edx, 6; unsigned int
0x180015cb5  mov     rcx, [rbp+50h+var_B8]; this
0x180015cb9  call    ?ProcessPerformanceData@CPerfTraceHelper@@QEAAXKJPEBG@Z; CPerfTraceHelper::ProcessPerformanceData(ulong,long,ushort const *)
0x180015cbe  mov     rbx, [rsp+150h+var_108]
0x180015cc3  jmp     loc_180016144
0x180015cc8  mov     rcx, [rsp+150h+var_100]
0x180015ccd  mov     rax, [rcx]
0x180015cd0  lea     rdx, WPD_OBJECT_NAME
0x180015cd7  mov     rax, [rax+28h]
0x180015cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce0  mov     rcx, [rsp+150h+var_100]
0x180015ce5  mov     rax, [rcx]
0x180015ce8  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180015cef  mov     rax, [rax+28h]
0x180015cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cf8  mov     rcx, [rsp+150h+var_100]
0x180015cfd  mov     rax, [rcx]
0x180015d00  lea     rdx, WPD_OBJECT_CAN_DELETE
0x180015d07  mov     rax, [rax+28h]
0x180015d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d10  test    r13, r13
0x180015d13  jnz     short loc_180015D41
0x180015d15  mov     rax, [rsi]
0x180015d18  lea     rcx, [rsp+150h+var_E0]
0x180015d1d  mov     [rsp+150h+ppv], rcx
0x180015d22  xor     r9d, r9d
0x180015d25  mov     r8, r15
0x180015d28  xor     edx, edx
0x180015d2a  mov     rcx, rsi
0x180015d2d  mov     rax, [rax+18h]
0x180015d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d36  mov     edi, eax
0x180015d38  mov     [rsp+150h+var_120], eax
0x180015d3c  jmp     loc_180015DC5
0x180015d41  xor     ebx, ebx
0x180015d43  xor     edi, edi
0x180015d45  cmp     dword ptr [r14], 0
0x180015d49  jnz     short loc_180015DA0
0x180015d4b  mov     rax, [rsi]
0x180015d4e  lea     rcx, [rsp+150h+var_E0]
0x180015d53  mov     [rsp+150h+ppv], rcx
0x180015d58  xor     r9d, r9d
0x180015d5b  mov     r8, r15
0x180015d5e  xor     edx, edx
0x180015d60  mov     rcx, rsi
0x180015d63  mov     rax, [rax+18h]
0x180015d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d6c  mov     [rsp+150h+var_120], eax
0x180015d70  cmp     eax, 800700AAh
0x180015d75  jnz     short loc_180015DA8
0x180015d77  test    ebx, ebx
0x180015d79  jnz     short loc_180015D89
0x180015d7b  mov     ebx, r12d
0x180015d7e  mov     edi, r12d
0x180015d81  mov     rcx, r13; this
0x180015d84  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180015d89  cmp     dword ptr [r14], 0
0x180015d8d  jnz     short loc_180015DA0
0x180015d8f  mov     ecx, 5DCh; dwMilliseconds
0x180015d94  call    cs:__imp_Sleep
0x180015d9a  test    ebx, ebx
0x180015d9c  jnz     short loc_180015D45
0x180015d9e  jmp     short loc_180015DA8
0x180015da0  mov     [rsp+150h+var_120], 800704C7h
0x180015da8  test    edi, edi
0x180015daa  jz      short loc_180015DB4
0x180015dac  mov     rcx, r13; this
0x180015daf  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180015db4  cmp     dword ptr [r14], 0
0x180015db8  jz      short loc_180015DC1
0x180015dba  mov     edi, 800704C7h
0x180015dbf  jmp     short loc_180015DC9
0x180015dc1  mov     edi, [rsp+150h+var_120]
0x180015dc5  test    edi, edi
0x180015dc7  jns     short loc_180015DF4
0x180015dc9  lea     rsi, WPP_GLOBAL_Control
0x180015dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dd7  cmp     rcx, rsi
0x180015dda  jz      loc_180015C3E
0x180015de0  test    byte ptr [rcx+1Ch], 2
0x180015de4  jz      loc_180015C3E
0x180015dea  mov     edx, 60h ; '`'
0x180015def  jmp     loc_180015C2B
0x180015df4  xor     edi, edi
0x180015df6  mov     [rsp+150h+var_F0], rdi
0x180015dfb  mov     [rbp+50h+var_D0], rdi
0x180015dff  mov     r12d, edi
0x180015e02  mov     [rsp+150h+var_110], edi
0x180015e06  mov     rbx, [rsp+150h+var_108]
0x180015e0b  nop     dword ptr [rax+rax+00h]
0x180015e10  mov     rcx, [rsp+150h+var_E0]
0x180015e15  mov     rax, [rcx]
0x180015e18  lea     r9, [rsp+150h+var_11C]
0x180015e1d  lea     r8, [rbp+50h+var_A0]
0x180015e21  mov     edx, 0Ah
0x180015e26  mov     rax, [rax+18h]
0x180015e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e2f  test    eax, eax
0x180015e31  js      loc_180016119
0x180015e37  mov     eax, [rsp+150h+var_11C]
0x180015e3b  test    eax, eax
0x180015e3d  jz      loc_1800160CF
0x180015e43  mov     r15d, edi
0x180015e46  nop     word ptr [rax+rax+00000000h]
0x180015e50  mov     eax, r15d
0x180015e53  lea     rsi, [rbp+50h+var_A0]
0x180015e57  lea     rsi, [rsi+rax*8]
0x180015e5b  cmp     qword ptr [rsi], 0
0x180015e5f  jz      loc_1800160FF
0x180015e65  mov     rcx, [rsp+150h+var_118]
0x180015e6a  test    rcx, rcx
0x180015e6d  jz      short loc_180015E80
0x180015e6f  mov     rax, [rcx]
0x180015e72  mov     rax, [rax+10h]
0x180015e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7b  mov     [rsp+150h+var_118], rdi
0x180015e80  test    r13, r13
0x180015e83  jnz     short loc_180015EA8
0x180015e85  mov     rax, [rbx]
0x180015e88  lea     r9, [rsp+150h+var_118]
0x180015e8d  mov     r8, [rsp+150h+var_100]
0x180015e92  mov     rdx, [rsi]
0x180015e95  mov     rcx, rbx
0x180015e98  mov     rax, [rax+28h]
0x180015e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ea1  mov     edi, eax
0x180015ea3  jmp     loc_180015F45
0x180015ea8  mov     r12d, edi
0x180015eab  mov     r13d, edi
0x180015eae  cmp     dword ptr [r14], 0
0x180015eb2  jnz     short loc_180015F1F
0x180015eb4  mov     rax, [rbx]
0x180015eb7  lea     r9, [rsp+150h+var_118]
0x180015ebc  mov     r8, [rsp+150h+var_100]
0x180015ec1  mov     rdx, [rsi]
0x180015ec4  mov     rcx, rbx
0x180015ec7  mov     rax, [rax+28h]
0x180015ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed0  mov     edi, eax
0x180015ed2  cmp     eax, 800700AAh
0x180015ed7  jnz     short loc_180015F24
0x180015ed9  cmp     [rsp+150h+var_118], 0
0x180015edf  jz      short loc_180015EED
0x180015ee1  xor     edx, edx; struct IUnknown *
0x180015ee3  lea     rcx, [rsp+150h+var_118]; struct IUnknown **
0x180015ee8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180015eed  test    r12d, r12d
0x180015ef0  jnz     short loc_180015F07
0x180015ef2  mov     eax, 1
0x180015ef7  mov     r12d, eax
0x180015efa  mov     r13d, eax
0x180015efd  mov     rcx, [rsp+150h+var_D8]; this
0x180015f02  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180015f07  cmp     dword ptr [r14], 0
0x180015f0b  jnz     short loc_180015F1F
0x180015f0d  mov     ecx, 5DCh; dwMilliseconds
0x180015f12  call    cs:__imp_Sleep
0x180015f18  test    r12d, r12d
0x180015f1b  jnz     short loc_180015EAE
0x180015f1d  jmp     short loc_180015F24
0x180015f1f  mov     edi, 800704C7h
  ... truncated ...
```
