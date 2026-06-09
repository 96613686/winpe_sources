# CUpdateDownloader::put_InternalConfigurationProperty(ulong,tagVARIANT)

- ea: `0x1800648a0`
- end: `0x180065086`
- name: `?put_InternalConfigurationProperty@CUpdateDownloader@@UEAAJKUtagVARIANT@@@Z`
- size: `2022`
- prototype: `__int64 __fastcall(CUpdateDownloader *__hidden this, unsigned int, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x18002d988`
- `0x18003da48`
- `0x1800648a0`
- `0x180081a38`
- `0x180082720`
- `0x180082b68`
- `0x180087438`
- `0x180088388`
- `0x18008d284`
- `0x18008e070`
- `0x18009b050`
- `0x18009b0b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006502c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006502c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064954`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064cb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064cb9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180064cfc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180064cfc`
- `OLEAUT32!__imp_SysStringLen` at `0x180064ab5`
- `OLEAUT32!__imp_SysStringLen` at `0x180064ab5`

## string_xrefs

- `0x180064922`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180064a59`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180064bf3`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180064d11`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180064f54`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180064ffa`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateDownloader::put_InternalConfigurationProperty(
        CUpdateDownloader *this,
        __int64 a2,
        struct tagVARIANT *a3)
{
  bool v4; // zf
  unsigned int v5; // r15d
  void *v7; // rbx
  void *v8; // rdi
  void *v9; // rsi
  int LastError; // r14d
  __int64 v11; // rdx
  void *v12; // r8
  wchar_t *v13; // r9
  unsigned int v14; // r15d
  unsigned int v15; // r15d
  unsigned int v16; // r15d
  unsigned int v17; // r15d
  __int64 v18; // rdx
  int v19; // eax
  void *v20; // rcx
  void *v21; // r14
  unsigned int v22; // r8d
  int v23; // eax
  bool v24; // dl
  unsigned __int64 v25; // r9
  void **v26; // r12
  struct TraceLoggingCorrelationVector *v27; // rax
  unsigned int v28; // r15d
  unsigned int v29; // r15d
  unsigned int v30; // r15d
  VolumeUtil *llVal; // rcx
  int VolumeIdForPath; // eax
  int v33; // eax
  void *v34; // r14
  void *v35; // rcx
  HANDLE *phNewToken; // r12
  const char *v37; // r9
  unsigned int Lo; // eax
  unsigned int v39; // r15d
  unsigned int v40; // r15d
  unsigned int v41; // r15d
  unsigned int v42; // r15d
  unsigned int v43; // r15d
  unsigned int v44; // r15d
  unsigned int v45; // r15d
  unsigned int v46; // r15d
  IRecordInfo *pRecInfo; // xmm1_8
  int v48; // eax
  IRecordInfo *v49; // xmm1_8
  int v50; // eax
  IRecordInfo *v51; // xmm1_8
  int v52; // eax
  int v53; // eax
  void *v54; // rcx
  void *v55; // r14
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-E0h]
  void *v58; // [rsp+30h] [rbp-D0h] BYREF
  void *v59; // [rsp+38h] [rbp-C8h] BYREF
  void *v60; // [rsp+40h] [rbp-C0h] BYREF
  struct tagVARIANT v61; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v62; // [rsp+70h] [rbp-90h]
  char v63[144]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v64[66]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v4 = *((_DWORD *)this - 6) == 1;
  v5 = a2;
  v59 = 0;
  v7 = 0;
  v60 = 0;
  v8 = 0;
  v58 = 0;
  v9 = 0;
  if ( v4 )
  {
    LastError = -2145124298;
    v11 = 689;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
      (const char *)(unsigned int)LastError,
      TokenType);
    goto LABEL_133;
  }
  LastError = SecurityCheck(1, a2, a3);
  if ( LastError < 0 )
  {
    v11 = 692;
    goto LABEL_5;
  }
  v62 = ((unsigned __int64)this + 16) & -(__int64)(this != (CUpdateDownloader *)40);
  if ( v62 )
    EnterCriticalSection((LPCRITICAL_SECTION)((((unsigned __int64)this + 16)
                                             & -(__int64)(this != (CUpdateDownloader *)40))
                                            + 8));
  if ( v5 > 0x30009 )
  {
    v39 = v5 - 196618;
    if ( !v39 )
    {
      if ( a3->vt != 11 )
      {
        v18 = 782;
        goto LABEL_126;
      }
      *((_BYTE *)this + 206) = a3->iVal != 0;
      goto LABEL_130;
    }
    v40 = v39 - 1;
    if ( !v40 )
    {
      if ( a3->vt != 11 )
      {
        v18 = 787;
        goto LABEL_126;
      }
      *((_BYTE *)this + 207) = a3->iVal != 0;
      goto LABEL_130;
    }
    v41 = v40 - 1;
    if ( !v41 )
    {
      if ( a3->vt != 11 )
      {
        v18 = 792;
        goto LABEL_126;
      }
      *((_DWORD *)this + 53) = 2 - (a3->iVal != 0);
      goto LABEL_130;
    }
    v42 = v41 - 1;
    if ( !v42 )
    {
      if ( a3->vt != 8 )
      {
        v18 = 811;
        goto LABEL_126;
      }
      v53 = DuplicateOptionalString<wchar_t *,wchar_t *>(a3->llVal, &v60);
      LastError = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32D,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
          (const char *)(unsigned int)v53,
          TokenType);
        v8 = v60;
        goto LABEL_131;
      }
      v54 = (void *)*((_QWORD *)this + 19);
      v55 = v60;
      if ( v54 )
        SusFree(v54);
      *((_QWORD *)this + 19) = v55;
      goto LABEL_130;
    }
    v43 = v42 - 1;
    if ( !v43 )
    {
      if ( a3->vt != 11 )
      {
        v18 = 824;
        goto LABEL_126;
      }
      *((_BYTE *)this + 210) = a3->iVal != 0;
      goto LABEL_130;
    }
    v44 = v43 - 1;
    if ( v44 )
    {
      v45 = v44 - 1;
      if ( v45 )
      {
        v46 = v45 - 1;
        if ( v46 )
        {
          if ( v46 == 1 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(
                                     `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl,
                                     0) )
            {
              v18 = 849;
              goto LABEL_126;
            }
            if ( a3->vt != 11 )
            {
              v18 = 843;
              goto LABEL_126;
            }
            *((_BYTE *)this + 136) = a3->iVal == 0xFFFF;
            goto LABEL_130;
          }
          goto LABEL_96;
        }
        pRecInfo = a3->pRecInfo;
        *(_OWORD *)&v61.vt = *(_OWORD *)&a3->vt;
        v61.pRecInfo = pRecInfo;
        v48 = VariantToBool(&v61, (bool *)this + 211);
        LastError = v48;
        if ( v48 >= 0 )
          goto LABEL_130;
        v25 = (unsigned int)v48;
        v18 = 837;
      }
      else
      {
        v49 = a3->pRecInfo;
        *(_OWORD *)&v61.vt = *(_OWORD *)&a3->vt;
        v61.pRecInfo = v49;
        v50 = VariantToBool(&v61, (bool *)this + 209);
        LastError = v50;
        if ( v50 >= 0 )
          goto LABEL_130;
        v25 = (unsigned int)v50;
        v18 = 833;
      }
    }
    else
    {
      v51 = a3->pRecInfo;
      *(_OWORD *)&v61.vt = *(_OWORD *)&a3->vt;
      v61.pRecInfo = v51;
      v52 = VariantToBool(&v61, (bool *)this + 208);
      LastError = v52;
      if ( v52 >= 0 )
        goto LABEL_130;
      v25 = (unsigned int)v52;
      v18 = 829;
    }
LABEL_128:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
      (const char *)v25,
      TokenType);
    goto LABEL_131;
  }
  if ( v5 == 196617 )
  {
    if ( a3->vt != 11 )
    {
      v18 = 777;
      goto LABEL_126;
    }
    *((_BYTE *)this + 205) = a3->iVal != 0;
    goto LABEL_130;
  }
  if ( v5 > 0x30004 )
  {
    v28 = v5 - 196613;
    if ( !v28 )
    {
      if ( a3->vt != 19 )
      {
        v18 = 720;
        goto LABEL_126;
      }
      Lo = a3->cyVal.Lo;
      if ( Lo > 4 )
      {
        v18 = 721;
        goto LABEL_126;
      }
      *((_DWORD *)this + 27) = 1;
      *((_DWORD *)this + 28) = Lo;
      goto LABEL_130;
    }
    v29 = v28 - 1;
    if ( v29 )
    {
      v30 = v29 - 1;
      if ( !v30 )
      {
        if ( a3->vt != 11 )
        {
          v18 = 756;
          goto LABEL_126;
        }
        *((_DWORD *)this + 50) = 2 - (a3->iVal != 0);
        goto LABEL_130;
      }
      if ( v30 != 1 )
        goto LABEL_96;
      if ( a3->vt != 8 )
      {
        v18 = 761;
        goto LABEL_126;
      }
      llVal = (VolumeUtil *)a3->llVal;
      if ( llVal )
      {
        VolumeIdForPath = VolumeUtil::GetVolumeIdForPath(llVal, 0, (unsigned __int64)v64, v13);
        LastError = VolumeIdForPath;
        if ( VolumeIdForPath < 0 )
        {
          v25 = (unsigned int)VolumeIdForPath;
          v18 = 768;
          goto LABEL_128;
        }
        v33 = DuplicateString<wchar_t *,wchar_t *>(v64, &v59);
        LastError = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x301,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
            (const char *)(unsigned int)v33,
            TokenType);
          v7 = v59;
          goto LABEL_131;
        }
        v7 = v59;
      }
      *((_DWORD *)this + 33) = 1;
      v34 = v7;
      v35 = (void *)*((_QWORD *)this + 18);
      v7 = 0;
      if ( v35 )
        SusFree(v35);
      *((_QWORD *)this + 18) = v34;
      goto LABEL_130;
    }
    if ( a3->vt != 19 )
    {
      v18 = 727;
      goto LABEL_126;
    }
    LastError = SecurityCheck(8, 0, v12);
    if ( LastError >= 0 )
    {
      phNewToken = (HANDLE *)((char *)this + 192);
      if ( !a3->lVal )
      {
        if ( *phNewToken )
          CloseHandle(*phNewToken);
        *phNewToken = 0;
        goto LABEL_130;
      }
      if ( !*phNewToken )
      {
        if ( !DuplicateTokenEx((HANDLE)a3->cyVal.Lo, 0xEu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x2EF,
                        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
                        v37);
          goto LABEL_131;
        }
        goto LABEL_130;
      }
      LastError = -2145124298;
      v18 = 742;
    }
    else
    {
      v18 = 730;
    }
    goto LABEL_127;
  }
  if ( v5 == 196612 )
  {
    if ( a3->vt != 11 )
    {
      v18 = 715;
      goto LABEL_126;
    }
    *((_DWORD *)this + 32) = a3->iVal != 0;
    goto LABEL_130;
  }
  v14 = v5 - 1;
  if ( !v14 )
  {
    if ( a3->vt != 8 )
    {
      v18 = 797;
      goto LABEL_126;
    }
    if ( !SysStringLen(a3->bstrVal) )
      goto LABEL_130;
    v23 = ConvertWideToAnsi(a3->bstrVal, v63, v22);
    LastError = v23;
    if ( v23 < 0 )
    {
      v25 = (unsigned int)v23;
      v18 = 803;
      goto LABEL_128;
    }
    v26 = (void **)((char *)this + 216);
    if ( *v26 )
    {
      operator delete(*v26);
      *v26 = 0;
    }
    if ( v26 )
    {
      *v26 = 0;
      if ( !v63[0] )
        goto LABEL_130;
      v27 = TraceLoggingCorrelationVector::Extend(v63, v24);
      *v26 = v27;
      if ( v27 )
        goto LABEL_130;
      LastError = -2147024882;
    }
    else
    {
      LastError = -2147467261;
    }
    v18 = 806;
LABEL_127:
    v25 = (unsigned int)LastError;
    goto LABEL_128;
  }
  v15 = v14 - 2;
  if ( !v15 )
  {
    if ( a3->vt != 8 )
    {
      v18 = 818;
      goto LABEL_126;
    }
    v19 = DuplicateOptionalString<wchar_t *,wchar_t *>(a3->llVal, &v58);
    LastError = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x333,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)(unsigned int)v19,
        TokenType);
      v9 = v58;
      goto LABEL_131;
    }
    v20 = (void *)*((_QWORD *)this + 20);
    v21 = v58;
    if ( v20 )
      SusFree(v20);
    *((_QWORD *)this + 20) = v21;
    goto LABEL_130;
  }
  v16 = v15 - 196606;
  if ( !v16 )
  {
    if ( a3->vt != 11 )
    {
      v18 = 700;
      goto LABEL_126;
    }
    *((_DWORD *)this + 30) = a3->iVal != 0;
    goto LABEL_130;
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    if ( v17 == 1 )
    {
      if ( a3->vt != 11 )
      {
        v18 = 710;
LABEL_126:
        LastError = -2147024809;
        goto LABEL_127;
      }
      *((_DWORD *)this + 31) = a3->iVal != 0;
      goto LABEL_130;
    }
LABEL_96:
    v18 = 853;
    goto LABEL_126;
  }
  if ( a3->vt != 11 )
  {
    v18 = 705;
    goto LABEL_126;
  }
  *((_BYTE *)this + 204) = a3->iVal != 0;
LABEL_130:
  LastError = 0;
LABEL_131:
  if ( v62 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v62 + 8));
LABEL_133:
  if ( v9 )
    SusFree(v9);
  if ( v8 )
    SusFree(v8);
  if ( v7 )
    SusFree(v7);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800648a0  mov     [rsp-8+arg_8], rbx
0x1800648a5  push    rbp
0x1800648a6  push    rsi
0x1800648a7  push    rdi
0x1800648a8  push    r12
0x1800648aa  push    r13
0x1800648ac  push    r14
0x1800648ae  push    r15
0x1800648b0  lea     rbp, [rsp-230h]
0x1800648b8  sub     rsp, 330h
0x1800648bf  mov     rax, cs:__security_cookie
0x1800648c6  xor     rax, rsp
0x1800648c9  mov     [rbp+260h+var_40], rax
0x1800648d0  xor     eax, eax
0x1800648d2  mov     r13, r8
0x1800648d5  cmp     dword ptr [rcx-18h], 1
0x1800648d9  mov     r15d, edx
0x1800648dc  mov     r12, rcx
0x1800648df  mov     [rsp+360h+var_328], rax
0x1800648e4  mov     ebx, eax
0x1800648e6  mov     [rsp+360h+var_320], rax
0x1800648eb  mov     edi, eax
0x1800648ed  mov     [rsp+360h+var_330], rax
0x1800648f2  mov     esi, eax
0x1800648f4  jnz     short loc_180064903
0x1800648f6  mov     r14d, 80240036h
0x1800648fc  mov     edx, 2B1h
0x180064901  jmp     short loc_18006491B
0x180064903  mov     ecx, 1; unsigned int
0x180064908  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18006490d  xor     edx, edx
0x18006490f  mov     r14d, eax
0x180064912  test    eax, eax
0x180064914  jns     short loc_180064936
0x180064916  mov     edx, 2B4h; void *
0x18006491b  mov     rcx, [rbp+268h]; this
0x180064922  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180064929  mov     r9d, r14d; char *
0x18006492c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064931  jmp     loc_180065032
0x180064936  lea     rax, [r12-28h]
0x18006493b  neg     rax
0x18006493e  lea     rcx, [r12+10h]
0x180064943  sbb     rax, rax
0x180064946  and     rax, rcx
0x180064949  mov     [rsp+360h+var_2F0], rax
0x18006494e  jz      short loc_18006495C
0x180064950  lea     rcx, [rax+8]; lpCriticalSection
0x180064954  call    cs:__imp_EnterCriticalSection
0x18006495a  xor     edx, edx; wchar_t *
0x18006495c  mov     eax, 30009h
0x180064961  cmp     r15d, eax
0x180064964  ja      loc_180064D89
0x18006496a  jz      loc_180064D62
0x180064970  mov     eax, 30004h
0x180064975  cmp     r15d, eax
0x180064978  ja      loc_180064B6F
0x18006497e  jz      loc_180064B46
0x180064984  sub     r15d, 1
0x180064988  jz      loc_180064A9B
0x18006498e  sub     r15d, 2
0x180064992  jz      loc_180064A24
0x180064998  sub     r15d, 2FFFEh
0x18006499f  jz      short loc_1800649FE
0x1800649a1  sub     r15d, 1
0x1800649a5  jz      short loc_1800649D7
0x1800649a7  cmp     r15d, 1
0x1800649ab  jnz     loc_180064DDE
0x1800649b1  cmp     word ptr [r13+0], 0Bh
0x1800649b7  jz      short loc_1800649C3
0x1800649b9  mov     edx, 2C6h
0x1800649be  jmp     loc_180064FEA
0x1800649c3  cmp     [r13+8], dx
0x1800649c8  mov     eax, edx
0x1800649ca  setnz   al
0x1800649cd  mov     [r12+7Ch], eax
0x1800649d2  jmp     loc_180065018
0x1800649d7  cmp     word ptr [r13+0], 0Bh
0x1800649dd  jz      short loc_1800649E9
0x1800649df  mov     edx, 2C1h
0x1800649e4  jmp     loc_180064FEA
0x1800649e9  cmp     [r13+8], dx
0x1800649ee  setnz   al
0x1800649f1  mov     [r12+0CCh], al
0x1800649f9  jmp     loc_180065018
0x1800649fe  cmp     word ptr [r13+0], 0Bh
0x180064a04  jz      short loc_180064A10
0x180064a06  mov     edx, 2BCh
0x180064a0b  jmp     loc_180064FEA
0x180064a10  cmp     [r13+8], dx
0x180064a15  mov     eax, edx
0x180064a17  setnz   al
0x180064a1a  mov     [r12+78h], eax
0x180064a1f  jmp     loc_180065018
0x180064a24  mov     eax, 8
0x180064a29  cmp     [r13+0], ax
0x180064a2e  jz      short loc_180064A3A
0x180064a30  mov     edx, 332h
0x180064a35  jmp     loc_180064FEA
0x180064a3a  mov     rcx, [r13+8]
0x180064a3e  lea     rdx, [rsp+360h+var_330]
0x180064a43  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180064a48  xor     r15d, r15d
0x180064a4b  mov     r14d, eax
0x180064a4e  test    eax, eax
0x180064a50  jns     short loc_180064A77
0x180064a52  mov     rcx, [rbp+268h]; this
0x180064a59  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180064a60  mov     r9d, eax; char *
0x180064a63  mov     edx, 333h; void *
0x180064a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064a6d  mov     rsi, [rsp+360h+var_330]
0x180064a72  jmp     loc_18006501E
0x180064a77  mov     rcx, [r12+0A0h]; lpMem
0x180064a7f  mov     r14, [rsp+360h+var_330]
0x180064a84  test    rcx, rcx
0x180064a87  jz      short loc_180064A8E
0x180064a89  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180064a8e  mov     [r12+0A0h], r14
0x180064a96  jmp     loc_18006501B
0x180064a9b  mov     eax, 8
0x180064aa0  cmp     [r13+0], ax
0x180064aa5  jz      short loc_180064AB1
0x180064aa7  mov     edx, 31Dh
0x180064aac  jmp     loc_180064FEA
0x180064ab1  mov     rcx, [r13+8]; pbstr
0x180064ab5  call    cs:__imp_SysStringLen
0x180064abb  xor     r15d, r15d
0x180064abe  test    eax, eax
0x180064ac0  jz      loc_18006501B
0x180064ac6  mov     rcx, [r13+8]; lpWideCharStr
0x180064aca  lea     rdx, [rbp+260h+var_2E0]; char *
0x180064ace  call    ?ConvertWideToAnsi@@YAJPEB_WPEADI@Z; ConvertWideToAnsi(wchar_t const *,char *,uint)
0x180064ad3  mov     r14d, eax
0x180064ad6  test    eax, eax
0x180064ad8  jns     short loc_180064AE7
0x180064ada  mov     r9d, eax
0x180064add  mov     edx, 323h
0x180064ae2  jmp     loc_180064FF3
0x180064ae7  add     r12, 0D8h
0x180064aee  mov     rcx, [r12]; Block
0x180064af2  test    rcx, rcx
0x180064af5  jz      short loc_180064B05
0x180064af7  mov     edx, 90h
0x180064afc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180064b01  mov     [r12], r15
0x180064b05  test    r12, r12
0x180064b08  jnz     short loc_180064B12
0x180064b0a  mov     r14d, 80004003h
0x180064b10  jmp     short loc_180064B3C
0x180064b12  mov     [r12], r15
0x180064b16  cmp     [rbp+260h+var_2E0], r15b
0x180064b1a  jz      loc_18006501B
0x180064b20  lea     rcx, [rbp+260h+var_2E0]; char *
0x180064b24  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180064b29  mov     [r12], rax
0x180064b2d  test    rax, rax
0x180064b30  jnz     loc_18006501B
0x180064b36  mov     r14d, 8007000Eh
0x180064b3c  mov     edx, 326h
0x180064b41  jmp     loc_180064FF0
0x180064b46  cmp     word ptr [r13+0], 0Bh
0x180064b4c  jz      short loc_180064B58
0x180064b4e  mov     edx, 2CBh
0x180064b53  jmp     loc_180064FEA
0x180064b58  cmp     [r13+8], dx
0x180064b5d  mov     eax, edx
0x180064b5f  setnz   al
0x180064b62  mov     [r12+80h], eax
0x180064b6a  jmp     loc_180065018
0x180064b6f  sub     r15d, 30005h
0x180064b76  jz      loc_180064D2A
0x180064b7c  sub     r15d, 1
0x180064b80  jz      loc_180064C73
0x180064b86  sub     r15d, 1
0x180064b8a  jz      loc_180064C47
0x180064b90  cmp     r15d, 1
0x180064b94  jnz     loc_180064DDE
0x180064b9a  lea     eax, [r15+7]
0x180064b9e  cmp     [r13+0], ax
0x180064ba3  jz      short loc_180064BAF
0x180064ba5  mov     edx, 2F9h
0x180064baa  jmp     loc_180064FEA
0x180064baf  mov     rcx, [r13+8]; this
0x180064bb3  test    rcx, rcx
0x180064bb6  jz      short loc_180064C16
0x180064bb8  lea     r8, [rbp+260h+var_250]; unsigned __int64
0x180064bbc  call    ?GetVolumeIdForPath@VolumeUtil@@YAJPEB_W_KPEA_W@Z; VolumeUtil::GetVolumeIdForPath(wchar_t const *,unsigned __int64,wchar_t *)
0x180064bc1  mov     r14d, eax
0x180064bc4  test    eax, eax
0x180064bc6  jns     short loc_180064BD5
0x180064bc8  mov     r9d, eax
0x180064bcb  mov     edx, 300h
0x180064bd0  jmp     loc_180064FF3
0x180064bd5  lea     rdx, [rsp+360h+var_328]
0x180064bda  lea     rcx, [rbp+260h+var_250]
0x180064bde  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180064be3  xor     edx, edx
0x180064be5  mov     r14d, eax
0x180064be8  test    eax, eax
0x180064bea  jns     short loc_180064C11
0x180064bec  mov     rcx, [rbp+268h]; this
0x180064bf3  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180064bfa  mov     r9d, eax; char *
0x180064bfd  mov     edx, 301h; void *
0x180064c02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064c07  mov     rbx, [rsp+360h+var_328]
0x180064c0c  jmp     loc_18006501E
0x180064c11  mov     rbx, [rsp+360h+var_328]
0x180064c16  mov     dword ptr [r12+84h], 1
0x180064c22  mov     r14, rbx
0x180064c25  mov     rcx, [r12+90h]; lpMem
0x180064c2d  mov     rbx, rdx
0x180064c30  test    rcx, rcx
0x180064c33  jz      short loc_180064C3A
0x180064c35  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180064c3a  mov     [r12+90h], r14
0x180064c42  jmp     loc_180065018
0x180064c47  cmp     word ptr [r13+0], 0Bh
0x180064c4d  jz      short loc_180064C59
0x180064c4f  mov     edx, 2F4h
0x180064c54  jmp     loc_180064FEA
0x180064c59  movzx   eax, word ptr [r13+8]
0x180064c5e  neg     ax
0x180064c61  sbb     ecx, ecx
0x180064c63  add     ecx, 2
0x180064c66  mov     [r12+0C8h], ecx
0x180064c6e  jmp     loc_180065018
0x180064c73  cmp     word ptr [r13+0], 13h
0x180064c79  jz      short loc_180064C85
0x180064c7b  mov     edx, 2D7h
0x180064c80  jmp     loc_180064FEA
0x180064c85  mov     ecx, 8; unsigned int
0x180064c8a  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x180064c8f  xor     r15d, r15d
0x180064c92  mov     r14d, eax
0x180064c95  test    eax, eax
0x180064c97  jns     short loc_180064CA3
0x180064c99  mov     edx, 2DAh
0x180064c9e  jmp     loc_180064FF0
0x180064ca3  add     r12, 0C0h
0x180064caa  cmp     [r13+8], r15d
0x180064cae  jnz     short loc_180064CC8
0x180064cb0  mov     rcx, [r12]; hObject
0x180064cb4  test    rcx, rcx
0x180064cb7  jz      short loc_180064CBF
0x180064cb9  call    cs:__imp_CloseHandle
0x180064cbf  mov     [r12], r15
0x180064cc3  jmp     loc_18006501B
0x180064cc8  cmp     [r12], r15
0x180064ccc  jz      short loc_180064CDE
0x180064cce  mov     r14d, 80240036h
0x180064cd4  mov     edx, 2E6h
0x180064cd9  jmp     loc_180064FF0
0x180064cde  mov     ecx, [r13+8]; hExistingToken
0x180064ce2  mov     r9d, 2; ImpersonationLevel
0x180064ce8  mov     [rsp+360h+phNewToken], r12; phNewToken
0x180064ced  xor     r8d, r8d; lpTokenAttributes
0x180064cf0  mov     [rsp+360h+TokenType], 2; TokenType
0x180064cf8  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180064cfc  call    cs:__imp_DuplicateTokenEx
0x180064d02  test    eax, eax
0x180064d04  jnz     loc_18006501B
0x180064d0a  mov     rcx, [rbp+268h]; this
0x180064d11  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180064d18  mov     edx, 2EFh; void *
0x180064d1d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180064d22  mov     r14d, eax
0x180064d25  jmp     loc_18006501E
0x180064d2a  cmp     word ptr [r13+0], 13h
0x180064d30  jz      short loc_180064D3C
0x180064d32  mov     edx, 2D0h
0x180064d37  jmp     loc_180064FEA
0x180064d3c  mov     eax, [r13+8]
0x180064d40  cmp     eax, 4
0x180064d43  jbe     short loc_180064D4F
0x180064d45  mov     edx, 2D1h
0x180064d4a  jmp     loc_180064FEA
0x180064d4f  mov     dword ptr [r12+6Ch], 1
0x180064d58  mov     [r12+70h], eax
0x180064d5d  jmp     loc_180065018
0x180064d62  cmp     word ptr [r13+0], 0Bh
0x180064d68  jz      short loc_180064D74
0x180064d6a  mov     edx, 309h
0x180064d6f  jmp     loc_180064FEA
0x180064d74  cmp     [r13+8], dx
0x180064d79  setnz   al
0x180064d7c  mov     [r12+0CDh], al
0x180064d84  jmp     loc_180065018
0x180064d89  sub     r15d, 3000Ah
0x180064d90  jz      loc_180064FDD
0x180064d96  sub     r15d, 1
0x180064d9a  jz      loc_180064FBC
0x180064da0  sub     r15d, 1
0x180064da4  jz      loc_180064F96
0x180064daa  sub     r15d, 1
0x180064dae  jz      loc_180064F1F
0x180064db4  sub     r15d, 1
0x180064db8  jz      loc_180064EF8
0x180064dbe  sub     r15d, 1
  ... truncated ...
```
