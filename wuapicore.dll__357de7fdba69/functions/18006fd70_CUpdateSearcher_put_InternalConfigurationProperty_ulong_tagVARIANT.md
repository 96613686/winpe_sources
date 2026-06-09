# CUpdateSearcher::put_InternalConfigurationProperty(ulong,tagVARIANT)

- ea: `0x18006fd70`
- end: `0x18007039f`
- name: `?put_InternalConfigurationProperty@CUpdateSearcher@@UEAAJKUtagVARIANT@@@Z`
- size: `1583`
- prototype: `int(CUpdateSearcher *__hidden this, unsigned int, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x1800220b0`
- `0x18002d988`
- `0x18003da48`
- `0x18006fcbc`
- `0x18006fd70`
- `0x180087438`
- `0x18008d284`
- `0x18009b050`
- `0x18009b0b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ff60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070167`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ff60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070167`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006feae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ffd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800700c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800702a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006feae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ffd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800700c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800702a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fed1`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18006ff2f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18006ff2f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800702b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800702b3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800700a1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800700a1`

## string_xrefs

- `0x18006fdbe`: `C:\__w\1\s\src\Client\comapi\UpdateSearcher.cpp`
- `0x18006fded`: `C:\__w\1\s\src\Client\comapi\UpdateSearcher.cpp`
- `0x18006ff05`: `C:\__w\1\s\src\Client\comapi\UpdateSearcher.cpp`
- `0x18006ff41`: `C:\__w\1\s\src\Client\comapi\UpdateSearcher.cpp`
- `0x18007014f`: `C:\__w\1\s\src\Client\comapi\UpdateSearcher.cpp`
- `0x1800702e2`: `C:\__w\1\s\src\Client\comapi\UpdateSearcher.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateSearcher::put_InternalConfigurationProperty(
        CUpdateSearcher *this,
        __int64 a2,
        struct tagVARIANT *a3)
{
  CUpdateSearcher *v3; // rsi
  unsigned int v5; // ebx
  int LastError; // ebx
  __int64 v8; // rdx
  int v10; // eax
  __int64 v11; // rdx
  void *v12; // r8
  unsigned int v13; // r14d
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  char *v21; // rbx
  char *v22; // r14
  struct _RTL_CRITICAL_SECTION *v23; // rsi
  void *v24; // rcx
  struct _RTL_CRITICAL_SECTION *v25; // rcx
  const char *v26; // r9
  unsigned int Lo; // esi
  char *v28; // rdi
  __int64 v29; // rbx
  bool v30; // zf
  unsigned int v31; // r8d
  char *v32; // rbx
  bool v33; // dl
  unsigned int v34; // edi
  __int64 v35; // rdx
  void **v36; // rbp
  struct TraceLoggingCorrelationVector *v37; // rax
  struct _RTL_CRITICAL_SECTION *v38; // rcx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  OLECHAR *v46; // rcx
  const wchar_t *bstrVal; // rdx
  int v48; // eax
  int v49[36]; // [rsp+20h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v3 = (CUpdateSearcher *)((char *)this - 232);
  v5 = a2;
  if ( *((_DWORD *)this - 54) == 1 )
  {
    LastError = -2145124298;
    v8 = 832;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateSearcher.cpp",
      (const char *)(unsigned int)LastError,
      v49[0]);
    return (unsigned int)LastError;
  }
  v10 = SecurityCheck(1, a2, a3);
  v13 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x343,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateSearcher.cpp",
      (const char *)(unsigned int)v10,
      v49[0]);
    return v13;
  }
  if ( v5 > 0x40007 )
  {
    v39 = v5 - 262152;
    if ( !v39 )
    {
      LastError = CUpdateSearcher::SetSearchFlag(v3, 0x10000000u, a3);
      if ( LastError < 0 )
      {
        v8 = 861;
        goto LABEL_3;
      }
      return 0;
    }
    v40 = v39 - 1;
    if ( !v40 )
    {
      LastError = CUpdateSearcher::SetSearchFlag(v3, 0x40000000u, a3);
      if ( LastError < 0 )
      {
        v8 = 923;
        goto LABEL_3;
      }
      return 0;
    }
    v41 = v40 - 2;
    if ( !v41 )
    {
      LastError = CUpdateSearcher::SetSearchFlag(v3, 0x80000000, a3);
      if ( LastError < 0 )
      {
        v8 = 937;
        goto LABEL_3;
      }
      return 0;
    }
    v42 = v41 - 1;
    if ( !v42 )
    {
      LastError = CUpdateSearcher::SetSearchFlag(v3, 0x400u, a3);
      if ( LastError < 0 )
      {
        v8 = 941;
        goto LABEL_3;
      }
      return 0;
    }
    v43 = v42 - 1;
    if ( v43 )
    {
      v44 = v43 - 1;
      if ( !v44 )
      {
        LastError = -2145124297;
        v8 = 946;
        goto LABEL_3;
      }
      v45 = v44 - 1;
      if ( !v45 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(
                                 `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl,
                                 v11) )
        {
          LastError = -2147024809;
          v8 = 956;
          goto LABEL_3;
        }
        LastError = CUpdateSearcher::SetSearchFlag(v3, 0x100000u, a3);
        if ( LastError < 0 )
        {
          v8 = 951;
          goto LABEL_3;
        }
        return 0;
      }
      if ( v45 == 1 )
      {
        LastError = CUpdateSearcher::SetSearchFlag(v3, 0x40000u, a3);
        if ( LastError < 0 )
        {
          v8 = 960;
          goto LABEL_3;
        }
        return 0;
      }
      goto LABEL_93;
    }
    goto LABEL_101;
  }
  if ( v5 == 262151 )
  {
    LastError = CUpdateSearcher::SetSearchFlag(v3, 0x8000000u, a3);
    if ( LastError < 0 )
    {
      v8 = 857;
      goto LABEL_3;
    }
    return 0;
  }
  v14 = v5 - 1;
  if ( v14 )
  {
    v15 = v14 - 2;
    if ( v15 )
    {
      v16 = v15 - 262142;
      if ( !v16 )
      {
        LastError = CUpdateSearcher::SetSearchFlag(v3, 0x10000u, a3);
        if ( LastError < 0 )
        {
          v8 = 841;
          goto LABEL_3;
        }
        return 0;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        LastError = CUpdateSearcher::SetSearchFlag(v3, 0x800u, a3);
        if ( LastError < 0 )
        {
          v8 = 845;
          goto LABEL_3;
        }
        return 0;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        LastError = CUpdateSearcher::SetSearchFlag(v3, 0x1000000u, a3);
        if ( LastError < 0 )
        {
          v8 = 849;
          goto LABEL_3;
        }
        return 0;
      }
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( !v20 )
        {
          LastError = CUpdateSearcher::SetSearchFlag(v3, 0x80u, a3);
          if ( LastError < 0 )
          {
            v8 = 853;
            goto LABEL_3;
          }
          return 0;
        }
        if ( v20 == 1 )
        {
          if ( a3->vt != 19 )
          {
            LastError = -2147024809;
            v8 = 877;
            goto LABEL_3;
          }
          LastError = SecurityCheck(8, v11, v12);
          if ( LastError < 0 )
          {
            v8 = 880;
            goto LABEL_3;
          }
          if ( v3 )
          {
            v21 = (char *)this + 8;
            v22 = (char *)this + 8;
            if ( this != (CUpdateSearcher *)-8LL )
            {
              v23 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
              goto LABEL_26;
            }
          }
          else
          {
            v22 = 0;
            v21 = 0;
          }
          v23 = (struct _RTL_CRITICAL_SECTION *)(v21 + 8);
LABEL_26:
          if ( !a3->lVal )
          {
            v24 = (void *)*((_QWORD *)this + 17);
            if ( v24 )
              CloseHandle(v24);
            *((_QWORD *)this + 17) = 0;
LABEL_30:
            if ( v22 )
            {
              v25 = v23;
LABEL_52:
              LeaveCriticalSection(v25);
              return 0;
            }
            return 0;
          }
          if ( *((_QWORD *)this + 17) )
          {
            LastError = -2145124298;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37F,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateSearcher.cpp",
              (const char *)0x80240036LL,
              v49[0]);
          }
          else
          {
            if ( DuplicateToken((HANDLE)a3->cyVal.Lo, SecurityImpersonation, (PHANDLE)this + 17) )
              goto LABEL_30;
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x385,
                          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateSearcher.cpp",
                          v26);
          }
          if ( v22 )
            LeaveCriticalSection(v23);
          return (unsigned int)LastError;
        }
LABEL_93:
        LastError = -2147024809;
        v8 = 964;
        goto LABEL_3;
      }
      if ( a3->vt != 19 )
      {
        LastError = -2147024809;
        v8 = 865;
        goto LABEL_3;
      }
      Lo = a3->cyVal.Lo;
      if ( Lo > 4 )
      {
        LastError = -2147024809;
        v8 = 866;
        goto LABEL_3;
      }
      if ( this == (CUpdateSearcher *)232 )
      {
        v28 = 0;
      }
      else
      {
        v28 = (char *)this + 8;
        if ( this != (CUpdateSearcher *)-8LL )
        {
          v29 = (__int64)this + 16;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
LABEL_49:
          *((_DWORD *)this + 30) = 1;
          v30 = v28 == 0;
          *((_DWORD *)this + 31) = Lo;
          goto LABEL_50;
        }
      }
      v29 = 8;
      goto LABEL_49;
    }
LABEL_101:
    v29 = 8;
    if ( a3->vt != 8 )
    {
      LastError = -2147024809;
      v8 = 929;
      goto LABEL_3;
    }
    if ( v3 )
    {
      v3 = (CUpdateSearcher *)((char *)this + 8);
      if ( this != (CUpdateSearcher *)-8LL )
      {
        v29 = (__int64)this + 16;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      }
    }
    v46 = (OLECHAR *)*((_QWORD *)this + 19);
    if ( a3->bstrVal == v46
      || (SysFreeString(v46),
          bstrVal = a3->bstrVal,
          *((_QWORD *)this + 19) = 0,
          v48 = CSusBSTR::Append((CUpdateSearcher *)((char *)this + 152), bstrVal),
          v34 = v48,
          v48 >= 0) )
    {
      v30 = v3 == 0;
LABEL_50:
      if ( !v30 )
      {
        v25 = (struct _RTL_CRITICAL_SECTION *)v29;
        goto LABEL_52;
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateSearcher.cpp",
      (const char *)(unsigned int)v48,
      v49[0]);
    if ( v3 )
    {
      v38 = (struct _RTL_CRITICAL_SECTION *)v29;
      goto LABEL_79;
    }
    return v34;
  }
  if ( a3->vt != 8 )
  {
    LastError = -2147024809;
    v8 = 908;
    goto LABEL_3;
  }
  if ( !SysStringLen(a3->bstrVal) )
    return 0;
  if ( this == (CUpdateSearcher *)232 )
  {
    v32 = 0;
  }
  else
  {
    v32 = (char *)this + 8;
    if ( this != (CUpdateSearcher *)-8LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  v34 = ConvertWideToAnsi(a3->bstrVal, (char *)v49, v31);
  if ( (v34 & 0x80000000) == 0 )
  {
    v36 = (void **)((char *)this + 144);
    if ( *v36 )
    {
      operator delete(*v36);
      *v36 = 0;
    }
    if ( v36 )
    {
      v30 = LOBYTE(v49[0]) == 0;
      *v36 = 0;
      if ( v30 || (v37 = TraceLoggingCorrelationVector::Extend((const char *)v49, v33), (*v36 = v37) != 0) )
      {
        if ( !v32 )
          return 0;
        v25 = (struct _RTL_CRITICAL_SECTION *)(v32 + 8);
        goto LABEL_52;
      }
      v34 = -2147024882;
    }
    else
    {
      v34 = -2147467261;
    }
    v35 = 918;
  }
  else
  {
    v35 = 916;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v35,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateSearcher.cpp",
    (const char *)v34,
    v49[0]);
  if ( v32 )
  {
    v38 = (struct _RTL_CRITICAL_SECTION *)(v32 + 8);
LABEL_79:
    LeaveCriticalSection(v38);
  }
  return v34;
}

```

## disassembly

```asm
0x18006fd70  mov     [rsp+arg_8], rbx
0x18006fd75  mov     [rsp+arg_18], rbp
0x18006fd7a  push    rsi
0x18006fd7b  push    rdi
0x18006fd7c  push    r14
0x18006fd7e  sub     rsp, 0C0h
0x18006fd85  mov     rax, cs:__security_cookie
0x18006fd8c  xor     rax, rsp
0x18006fd8f  mov     [rsp+0D8h+var_28], rax
0x18006fd97  lea     rsi, [rcx-0E8h]
0x18006fd9e  mov     rdi, r8
0x18006fda1  cmp     dword ptr [rsi+10h], 1
0x18006fda5  mov     ebx, edx
0x18006fda7  mov     rbp, rcx
0x18006fdaa  jnz     short loc_18006FDD4
0x18006fdac  mov     ebx, 80240036h
0x18006fdb1  mov     edx, 340h; void *
0x18006fdb6  mov     rcx, [rsp+0D8h]; this
0x18006fdbe  lea     r8, aCW1SSrcClientC_21; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006fdc5  mov     r9d, ebx; char *
0x18006fdc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fdcd  mov     eax, ebx
0x18006fdcf  jmp     loc_18006FFFC
0x18006fdd4  mov     ecx, 1; unsigned int
0x18006fdd9  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18006fdde  mov     r14d, eax
0x18006fde1  test    eax, eax
0x18006fde3  jns     short loc_18006FE09
0x18006fde5  mov     rcx, [rsp+0D8h]; this
0x18006fded  lea     r8, aCW1SSrcClientC_21; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006fdf4  mov     r9d, eax; char *
0x18006fdf7  mov     edx, 343h; void *
0x18006fdfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fe01  mov     eax, r14d
0x18006fe04  jmp     loc_18006FFFC
0x18006fe09  mov     eax, 40007h
0x18006fe0e  cmp     ebx, eax
0x18006fe10  ja      loc_1800701AA
0x18006fe16  jz      loc_180070186
0x18006fe1c  sub     ebx, 1
0x18006fe1f  jz      loc_180070084
0x18006fe25  sub     ebx, 2
0x18006fe28  jz      loc_180070272
0x18006fe2e  sub     ebx, 3FFFEh
0x18006fe34  jz      loc_180070064
0x18006fe3a  sub     ebx, 1
0x18006fe3d  jz      loc_180070044
0x18006fe43  sub     ebx, 1
0x18006fe46  jz      loc_180070024
0x18006fe4c  sub     ebx, 1
0x18006fe4f  jz      loc_18006FF8B
0x18006fe55  sub     ebx, 1
0x18006fe58  jz      loc_18006FF6B
0x18006fe5e  cmp     ebx, 1
0x18006fe61  jnz     loc_1800701ED
0x18006fe67  cmp     word ptr [rdi], 13h
0x18006fe6b  jz      short loc_18006FE7C
0x18006fe6d  mov     ebx, 80070057h
0x18006fe72  mov     edx, 36Dh
0x18006fe77  jmp     loc_18006FDB6
0x18006fe7c  mov     ecx, 8; unsigned int
0x18006fe81  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18006fe86  mov     ebx, eax
0x18006fe88  test    eax, eax
0x18006fe8a  jns     short loc_18006FE96
0x18006fe8c  mov     edx, 370h
0x18006fe91  jmp     loc_18006FDB6
0x18006fe96  test    rsi, rsi
0x18006fe99  jz      short loc_18006FEB6
0x18006fe9b  lea     rbx, [rbp+8]
0x18006fe9f  mov     r14, rbx
0x18006fea2  test    rbx, rbx
0x18006fea5  jz      short loc_18006FEBB
0x18006fea7  lea     rsi, [rbx+8]
0x18006feab  mov     rcx, rsi; lpCriticalSection
0x18006feae  call    cs:__imp_EnterCriticalSection
0x18006feb4  jmp     short loc_18006FEBF
0x18006feb6  xor     r14d, r14d
0x18006feb9  xor     ebx, ebx
0x18006febb  lea     rsi, [rbx+8]
0x18006febf  cmp     dword ptr [rdi+8], 0
0x18006fec3  jnz     short loc_18006FEF3
0x18006fec5  mov     rcx, [rbp+88h]; hObject
0x18006fecc  test    rcx, rcx
0x18006fecf  jz      short loc_18006FED7
0x18006fed1  call    cs:__imp_CloseHandle
0x18006fed7  mov     qword ptr [rbp+88h], 0
0x18006fee2  test    r14, r14
0x18006fee5  jz      loc_18006FFFA
0x18006feeb  mov     rcx, rsi
0x18006feee  jmp     loc_18006FFF4
0x18006fef3  cmp     qword ptr [rbp+88h], 0
0x18006fefb  jz      short loc_18006FF20
0x18006fefd  mov     rcx, [rsp+0D8h]; this
0x18006ff05  lea     r8, aCW1SSrcClientC_21; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006ff0c  mov     ebx, 80240036h
0x18006ff11  mov     edx, 37Fh; void *
0x18006ff16  mov     r9d, ebx; char *
0x18006ff19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ff1e  jmp     short loc_18006FF54
0x18006ff20  mov     ecx, [rdi+8]; ExistingTokenHandle
0x18006ff23  lea     r8, [rbp+88h]; DuplicateTokenHandle
0x18006ff2a  mov     edx, 2; ImpersonationLevel
0x18006ff2f  call    cs:__imp_DuplicateToken
0x18006ff35  test    eax, eax
0x18006ff37  jnz     short loc_18006FEE2
0x18006ff39  mov     rcx, [rsp+0D8h]; this
0x18006ff41  lea     r8, aCW1SSrcClientC_21; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006ff48  mov     edx, 385h; void *
0x18006ff4d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006ff52  mov     ebx, eax
0x18006ff54  test    r14, r14
0x18006ff57  jz      loc_18006FDCD
0x18006ff5d  mov     rcx, rsi; lpCriticalSection
0x18006ff60  call    cs:__imp_LeaveCriticalSection
0x18006ff66  jmp     loc_18006FDCD
0x18006ff6b  mov     r8, rdi; struct tagVARIANT *
0x18006ff6e  mov     edx, 80h; unsigned int
0x18006ff73  mov     rcx, rsi; this
0x18006ff76  call    ?SetSearchFlag@CUpdateSearcher@@AEAAJKAEBUtagVARIANT@@@Z; CUpdateSearcher::SetSearchFlag(ulong,tagVARIANT const &)
0x18006ff7b  mov     ebx, eax
0x18006ff7d  test    eax, eax
0x18006ff7f  jns     short loc_18006FFFA
0x18006ff81  mov     edx, 355h
0x18006ff86  jmp     loc_18006FDB6
0x18006ff8b  cmp     word ptr [rdi], 13h
0x18006ff8f  jz      short loc_18006FFA0
0x18006ff91  mov     ebx, 80070057h
0x18006ff96  mov     edx, 361h
0x18006ff9b  jmp     loc_18006FDB6
0x18006ffa0  mov     esi, [rdi+8]
0x18006ffa3  cmp     esi, 4
0x18006ffa6  jbe     short loc_18006FFB7
0x18006ffa8  mov     ebx, 80070057h
0x18006ffad  mov     edx, 362h
0x18006ffb2  jmp     loc_18006FDB6
0x18006ffb7  lea     rax, [rbp-0E8h]
0x18006ffbe  test    rax, rax
0x18006ffc1  jz      short loc_18006FFDB
0x18006ffc3  lea     rdi, [rbp+8]
0x18006ffc7  test    rdi, rdi
0x18006ffca  jz      short loc_18006FFDD
0x18006ffcc  lea     rbx, [rdi+8]
0x18006ffd0  mov     rcx, rbx; lpCriticalSection
0x18006ffd3  call    cs:__imp_EnterCriticalSection
0x18006ffd9  jmp     short loc_18006FFE2
0x18006ffdb  xor     edi, edi
0x18006ffdd  mov     ebx, 8
0x18006ffe2  mov     dword ptr [rbp+78h], 1
0x18006ffe9  test    rdi, rdi
0x18006ffec  mov     [rbp+7Ch], esi
0x18006ffef  jz      short loc_18006FFFA
0x18006fff1  mov     rcx, rbx; lpCriticalSection
0x18006fff4  call    cs:__imp_LeaveCriticalSection
0x18006fffa  xor     eax, eax
0x18006fffc  mov     rcx, [rsp+0D8h+var_28]
0x180070004  xor     rcx, rsp; StackCookie
0x180070007  call    __security_check_cookie
0x18007000c  lea     r11, [rsp+0D8h+var_18]
0x180070014  mov     rbx, [r11+28h]
0x180070018  mov     rbp, [r11+38h]
0x18007001c  mov     rsp, r11
0x18007001f  pop     r14
0x180070021  pop     rdi
0x180070022  pop     rsi
0x180070023  retn
0x180070024  mov     r8, rdi; struct tagVARIANT *
0x180070027  mov     edx, 1000000h; unsigned int
0x18007002c  mov     rcx, rsi; this
0x18007002f  call    ?SetSearchFlag@CUpdateSearcher@@AEAAJKAEBUtagVARIANT@@@Z; CUpdateSearcher::SetSearchFlag(ulong,tagVARIANT const &)
0x180070034  mov     ebx, eax
0x180070036  test    eax, eax
0x180070038  jns     short loc_18006FFFA
0x18007003a  mov     edx, 351h
0x18007003f  jmp     loc_18006FDB6
0x180070044  mov     r8, rdi; struct tagVARIANT *
0x180070047  mov     edx, 800h; unsigned int
0x18007004c  mov     rcx, rsi; this
0x18007004f  call    ?SetSearchFlag@CUpdateSearcher@@AEAAJKAEBUtagVARIANT@@@Z; CUpdateSearcher::SetSearchFlag(ulong,tagVARIANT const &)
0x180070054  mov     ebx, eax
0x180070056  test    eax, eax
0x180070058  jns     short loc_18006FFFA
0x18007005a  mov     edx, 34Dh
0x18007005f  jmp     loc_18006FDB6
0x180070064  mov     r8, rdi; struct tagVARIANT *
0x180070067  mov     edx, 10000h; unsigned int
0x18007006c  mov     rcx, rsi; this
0x18007006f  call    ?SetSearchFlag@CUpdateSearcher@@AEAAJKAEBUtagVARIANT@@@Z; CUpdateSearcher::SetSearchFlag(ulong,tagVARIANT const &)
0x180070074  mov     ebx, eax
0x180070076  test    eax, eax
0x180070078  jns     short loc_18006FFFA
0x18007007a  mov     edx, 349h
0x18007007f  jmp     loc_18006FDB6
0x180070084  mov     ebx, 8
0x180070089  cmp     [rdi], bx
0x18007008c  jz      short loc_18007009D
0x18007008e  mov     ebx, 80070057h
0x180070093  mov     edx, 38Ch
0x180070098  jmp     loc_18006FDB6
0x18007009d  mov     rcx, [rdi+8]; pbstr
0x1800700a1  call    cs:__imp_SysStringLen
0x1800700a7  test    eax, eax
0x1800700a9  jz      loc_18006FFFA
0x1800700af  lea     rax, [rbp-0E8h]
0x1800700b6  test    rax, rax
0x1800700b9  jz      short loc_1800700D0
0x1800700bb  lea     rbx, [rbp+8]
0x1800700bf  test    rbx, rbx
0x1800700c2  jz      short loc_1800700D2
0x1800700c4  lea     rcx, [rbx+8]; lpCriticalSection
0x1800700c8  call    cs:__imp_EnterCriticalSection
0x1800700ce  jmp     short loc_1800700D2
0x1800700d0  xor     ebx, ebx
0x1800700d2  mov     rcx, [rdi+8]; lpWideCharStr
0x1800700d6  lea     rdx, [rsp+0D8h+var_B8]; char *
0x1800700db  call    ?ConvertWideToAnsi@@YAJPEB_WPEADI@Z; ConvertWideToAnsi(wchar_t const *,char *,uint)
0x1800700e0  mov     edi, eax
0x1800700e2  test    eax, eax
0x1800700e4  jns     short loc_1800700ED
0x1800700e6  mov     edx, 394h
0x1800700eb  jmp     short loc_180070147
0x1800700ed  add     rbp, 90h
0x1800700f4  mov     rcx, [rbp+0]; Block
0x1800700f8  test    rcx, rcx
0x1800700fb  jz      short loc_18007010F
0x1800700fd  mov     edx, 90h
0x180070102  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180070107  mov     qword ptr [rbp+0], 0
0x18007010f  test    rbp, rbp
0x180070112  jnz     short loc_18007011B
0x180070114  mov     edi, 80004003h
0x180070119  jmp     short loc_180070142
0x18007011b  cmp     byte ptr [rsp+0D8h+var_B8], 0
0x180070120  mov     qword ptr [rbp+0], 0
0x180070128  jz      short loc_180070174
0x18007012a  lea     rcx, [rsp+0D8h+var_B8]; char *
0x18007012f  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180070134  mov     [rbp+0], rax
0x180070138  test    rax, rax
0x18007013b  jnz     short loc_180070174
0x18007013d  mov     edi, 8007000Eh
0x180070142  mov     edx, 396h; void *
0x180070147  mov     rcx, [rsp+0D8h]; this
0x18007014f  lea     r8, aCW1SSrcClientC_21; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180070156  mov     r9d, edi; char *
0x180070159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007015e  test    rbx, rbx
0x180070161  jz      short loc_18007016D
0x180070163  lea     rcx, [rbx+8]; lpCriticalSection
0x180070167  call    cs:__imp_LeaveCriticalSection
0x18007016d  mov     eax, edi
0x18007016f  jmp     loc_18006FFFC
0x180070174  test    rbx, rbx
0x180070177  jz      loc_18006FFFA
0x18007017d  lea     rcx, [rbx+8]
0x180070181  jmp     loc_18006FFF4
0x180070186  mov     r8, rdi; struct tagVARIANT *
0x180070189  mov     edx, 8000000h; unsigned int
0x18007018e  mov     rcx, rsi; this
0x180070191  call    ?SetSearchFlag@CUpdateSearcher@@AEAAJKAEBUtagVARIANT@@@Z; CUpdateSearcher::SetSearchFlag(ulong,tagVARIANT const &)
0x180070196  mov     ebx, eax
0x180070198  test    eax, eax
0x18007019a  jns     loc_18006FFFA
0x1800701a0  mov     edx, 359h
0x1800701a5  jmp     loc_18006FDB6
0x1800701aa  sub     ebx, 40008h
0x1800701b0  jz      loc_18007037B
0x1800701b6  sub     ebx, 1
0x1800701b9  jz      loc_180070357
0x1800701bf  sub     ebx, 2
0x1800701c2  jz      loc_180070333
0x1800701c8  sub     ebx, 1
0x1800701cb  jz      loc_18007030F
0x1800701d1  sub     ebx, 1
0x1800701d4  jz      loc_180070272
0x1800701da  sub     ebx, 1
0x1800701dd  jz      loc_180070263
0x1800701e3  sub     ebx, 1
0x1800701e6  jz      short loc_180070220
0x1800701e8  cmp     ebx, 1
0x1800701eb  jz      short loc_1800701FC
0x1800701ed  mov     ebx, 80070057h
0x1800701f2  mov     edx, 3C4h
0x1800701f7  jmp     loc_18006FDB6
0x1800701fc  mov     r8, rdi; struct tagVARIANT *
0x1800701ff  mov     edx, 40000h; unsigned int
0x180070204  mov     rcx, rsi; this
0x180070207  call    ?SetSearchFlag@CUpdateSearcher@@AEAAJKAEBUtagVARIANT@@@Z; CUpdateSearcher::SetSearchFlag(ulong,tagVARIANT const &)
0x18007020c  mov     ebx, eax
0x18007020e  test    eax, eax
0x180070210  jns     loc_18006FFFA
0x180070216  mov     edx, 3C0h
0x18007021b  jmp     loc_18006FDB6
0x180070220  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl(void)'::`2'::impl
0x180070227  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(void)
0x18007022c  test    al, al
0x18007022e  jz      short loc_180070254
0x180070230  mov     r8, rdi; struct tagVARIANT *
0x180070233  mov     edx, 100000h; unsigned int
0x180070238  mov     rcx, rsi; this
  ... truncated ...
```
