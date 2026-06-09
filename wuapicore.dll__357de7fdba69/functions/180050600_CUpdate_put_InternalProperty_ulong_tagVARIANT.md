# CUpdate::put_InternalProperty(ulong,tagVARIANT)

- ea: `0x180050600`
- end: `0x1800508f4`
- name: `?put_InternalProperty@CUpdate@@UEAAJKUtagVARIANT@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(CUpdate *this, __int64, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x18000ed90`
- `0x18002d988`
- `0x180050600`
- `0x180050bf4`
- `0x180060288`
- `0x1800602e4`
- `0x18008d284`
- `0x18009b024`
- `0x18009b050`
- `0x18009b0b8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005071c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005071c`
- `OLEAUT32!__imp_SysStringLen` at `0x180050699`
- `OLEAUT32!__imp_SysStringLen` at `0x1800506e5`
- `OLEAUT32!__imp_SysStringLen` at `0x180050790`
- `OLEAUT32!__imp_SysStringLen` at `0x18005082c`
- `OLEAUT32!__imp_SysStringLen` at `0x180050699`
- `OLEAUT32!__imp_SysStringLen` at `0x1800506e5`
- `OLEAUT32!__imp_SysStringLen` at `0x180050790`
- `OLEAUT32!__imp_SysStringLen` at `0x18005082c`

## string_xrefs

- `0x1800506bf`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x1800508bf`: `C:\__w\1\s\src\Client\comapi\Update.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
__int64 __fastcall CUpdate::put_InternalProperty(CUpdate *this, __int64 a2, struct tagVARIANT *a3)
{
  int v4; // esi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // esi
  int v9; // esi
  WCHAR *v10; // rbx
  OLECHAR *v11; // rcx
  CUpdate *v12; // rbp
  const WCHAR *v13; // r8
  int v14; // eax
  unsigned __int64 v15; // r9
  const wchar_t *v16; // rbx
  UINT v17; // eax
  bool v18; // dl
  struct TraceLoggingCorrelationVector *v19; // rbx
  void *v20; // rcx
  const wchar_t *bstrVal; // rbx
  UINT v22; // eax
  bool v23; // dl
  struct TraceLoggingCorrelationVector **v24; // rbx
  void *v25; // rcx
  struct TraceLoggingCorrelationVector *v26; // rax
  int lpString2; // [rsp+20h] [rbp-C8h]
  const char *cchCount2; // [rsp+28h] [rbp-C0h]
  char Dst[144]; // [rsp+30h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v4 = a2;
  v6 = SecurityCheck(1, a2, a3);
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = 1914;
LABEL_44:
    v15 = v6;
    goto LABEL_45;
  }
  v8 = v4 - 1;
  if ( !v8 )
  {
    if ( a3->vt != 8 )
    {
      v6 = -2147024809;
      v7 = 1919;
      goto LABEL_44;
    }
    bstrVal = a3->bstrVal;
    if ( bstrVal )
    {
      v22 = SysStringLen(a3->bstrVal);
      if ( wcstombs_s(0, Dst, 0x81u, bstrVal, v22) )
      {
        v6 = -2147418113;
        v7 = 1929;
        goto LABEL_44;
      }
      v24 = (struct TraceLoggingCorrelationVector **)((char *)this + 984);
      v25 = (void *)*((_QWORD *)this + 123);
      if ( v25 )
      {
        operator delete(v25);
        *v24 = 0;
      }
      if ( this == (CUpdate *)-984LL )
      {
        v6 = -2147467261;
      }
      else
      {
        *v24 = 0;
        if ( !Dst[0] )
          return 0;
        v26 = TraceLoggingCorrelationVector::Extend(Dst, v23);
        *v24 = v26;
        if ( v26 )
          return 0;
        v6 = -2147024882;
      }
      v7 = 1932;
      goto LABEL_44;
    }
    return 0;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( a3->vt != 8 )
    {
      v6 = -2147024809;
      v7 = 1938;
      goto LABEL_44;
    }
    v16 = a3->bstrVal;
    if ( v16 )
    {
      v17 = SysStringLen(a3->bstrVal);
      if ( wcstombs_s(0, Dst, 0x81u, v16, v17) )
      {
        v6 = -2147418113;
        v7 = 1948;
        goto LABEL_44;
      }
      v19 = TraceLoggingCorrelationVector::Set(Dst, v18);
      v20 = (void *)*((_QWORD *)this + 124);
      if ( v20 )
        operator delete(v20);
      *((_QWORD *)this + 124) = v19;
      if ( !v19 )
      {
        v6 = -2147024882;
        v7 = 1951;
        goto LABEL_44;
      }
    }
    return 0;
  }
  if ( v9 != 2 )
  {
    v6 = -2147024809;
    v7 = 1986;
    goto LABEL_44;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
  {
    v6 = -2147024809;
    v7 = 1979;
    goto LABEL_44;
  }
  if ( a3->vt != 8 )
  {
    v6 = -2147024809;
    v7 = 1959;
    goto LABEL_44;
  }
  v10 = a3->bstrVal;
  if ( SysStringLen(v10) )
  {
    v11 = (OLECHAR *)*((_QWORD *)this + 129);
    v12 = (CUpdate *)((char *)this - 56);
    if ( v11 && SysStringLen(v11) )
    {
      v13 = (const WCHAR *)*((_QWORD *)v12 + 136);
      if ( v13 != v10 && (!v13 || !v10 || CompareStringW(0x7Fu, 0, v13, -1, v10, -1) != 2) )
      {
        v6 = -2145124244;
        v7 = 1971;
        goto LABEL_44;
      }
    }
    else
    {
      v14 = CUpdate::SetSessionData(v12, a3);
      v6 = v14;
      if ( v14 < 0 )
      {
        v15 = (unsigned int)v14;
        v7 = 1975;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
          (const char *)v15,
          lpString2);
        return v6;
      }
    }
    return 0;
  }
  v6 = -2147024809;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x7AB,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
    (const char *)0x80070057LL,
    (int)"SessionData can't be nullptr or empty",
    cchCount2);
  return v6;
}

```

## disassembly

```asm
0x180050600  mov     [rsp+arg_8], rbx
0x180050605  push    rbp
0x180050606  push    rsi
0x180050607  push    rdi
0x180050608  sub     rsp, 0D0h
0x18005060f  mov     rax, cs:__security_cookie
0x180050616  xor     rax, rsp
0x180050619  mov     [rsp+0E8h+var_28], rax
0x180050621  mov     rdi, r8
0x180050624  mov     esi, edx
0x180050626  mov     rbp, rcx
0x180050629  mov     ecx, 1; unsigned int
0x18005062e  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x180050633  mov     ebx, eax
0x180050635  test    eax, eax
0x180050637  jns     short loc_180050643
0x180050639  mov     edx, 77Ah
0x18005063e  jmp     loc_1800508B4
0x180050643  sub     esi, 1
0x180050646  jz      loc_180050807
0x18005064c  sub     esi, 1
0x18005064f  jz      loc_18005076B
0x180050655  cmp     esi, 2
0x180050658  jz      short loc_180050669
0x18005065a  mov     ebx, 80070057h
0x18005065f  mov     edx, 7C2h
0x180050664  jmp     loc_1800508B4
0x180050669  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x180050670  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x180050675  test    al, al
0x180050677  jz      loc_18005075C
0x18005067d  cmp     word ptr [rdi], 8
0x180050681  jz      short loc_180050692
0x180050683  mov     ebx, 80070057h
0x180050688  mov     edx, 7A7h
0x18005068d  jmp     loc_1800508B4
0x180050692  mov     rbx, [rdi+8]
0x180050696  mov     rcx, rbx; pbstr
0x180050699  call    cs:__imp_SysStringLen
0x18005069f  test    eax, eax
0x1800506a1  jnz     short loc_1800506D5
0x1800506a3  mov     rcx, [rsp+0E8h]; this
0x1800506ab  lea     rax, aSessiondataCan; "SessionData can't be nullptr or empty"
0x1800506b2  mov     [rsp+0E8h+lpString2], rax; int
0x1800506b7  mov     ebx, 80070057h
0x1800506bc  mov     r9d, ebx; char *
0x1800506bf  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800506c6  mov     edx, 7ABh; void *
0x1800506cb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800506d0  jmp     loc_1800508CF
0x1800506d5  mov     rcx, [rbp+408h]; pbstr
0x1800506dc  add     rbp, 0FFFFFFFFFFFFFFC8h
0x1800506e0  test    rcx, rcx
0x1800506e3  jz      short loc_18005073A
0x1800506e5  call    cs:__imp_SysStringLen
0x1800506eb  test    eax, eax
0x1800506ed  jz      short loc_18005073A
0x1800506ef  mov     r8, [rbp+440h]; lpString1
0x1800506f6  cmp     r8, rbx
0x1800506f9  jz      loc_1800508CD
0x1800506ff  test    r8, r8
0x180050702  jz      short loc_18005072B
0x180050704  test    rbx, rbx
0x180050707  jz      short loc_18005072B
0x180050709  or      r9d, 0FFFFFFFFh; cchCount1
0x18005070d  mov     dword ptr [rsp+0E8h+cchCount2], r9d; cchCount2
0x180050712  mov     [rsp+0E8h+lpString2], rbx; lpString2
0x180050717  xor     edx, edx; dwCmpFlags
0x180050719  lea     ecx, [rdx+7Fh]; Locale
0x18005071c  call    cs:__imp_CompareStringW
0x180050722  cmp     eax, 2
0x180050725  jz      loc_1800508CD
0x18005072b  mov     ebx, 8024006Ch
0x180050730  mov     edx, 7B3h
0x180050735  jmp     loc_1800508B4
0x18005073a  mov     rdx, rdi; struct tagVARIANT *
0x18005073d  mov     rcx, rbp; this
0x180050740  call    ?SetSessionData@CUpdate@@AEAAJAEBUtagVARIANT@@@Z; CUpdate::SetSessionData(tagVARIANT const &)
0x180050745  mov     ebx, eax
0x180050747  test    eax, eax
0x180050749  jns     loc_1800508CD
0x18005074f  mov     r9d, eax
0x180050752  mov     edx, 7B7h
0x180050757  jmp     loc_1800508B7
0x18005075c  mov     ebx, 80070057h
0x180050761  mov     edx, 7BBh
0x180050766  jmp     loc_1800508B4
0x18005076b  cmp     word ptr [rdi], 8
0x18005076f  jz      short loc_180050780
0x180050771  mov     ebx, 80070057h
0x180050776  mov     edx, 792h
0x18005077b  jmp     loc_1800508B4
0x180050780  mov     rbx, [rdi+8]
0x180050784  test    rbx, rbx
0x180050787  jz      loc_1800508CD
0x18005078d  mov     rcx, rbx; pbstr
0x180050790  call    cs:__imp_SysStringLen
0x180050796  mov     eax, eax
0x180050798  mov     [rsp+0E8h+lpString2], rax; MaxCountInBytes
0x18005079d  mov     r9, rbx; Src
0x1800507a0  mov     r8d, 81h; DstSizeInBytes
0x1800507a6  lea     rdx, [rsp+0E8h+Dst]; Dst
0x1800507ab  xor     ecx, ecx; PtNumOfCharConverted
0x1800507ad  call    wcstombs_s
0x1800507b2  test    eax, eax
0x1800507b4  jz      short loc_1800507C5
0x1800507b6  mov     ebx, 8000FFFFh
0x1800507bb  mov     edx, 79Ch
0x1800507c0  jmp     loc_1800508B4
0x1800507c5  lea     rcx, [rsp+0E8h+Dst]; Str
0x1800507ca  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x1800507cf  mov     rbx, rax
0x1800507d2  mov     rcx, [rbp+3E0h]; Block
0x1800507d9  test    rcx, rcx
0x1800507dc  jz      short loc_1800507E8
0x1800507de  mov     edx, 90h
0x1800507e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800507e8  mov     [rbp+3E0h], rbx
0x1800507ef  test    rbx, rbx
0x1800507f2  jnz     loc_1800508CD
0x1800507f8  mov     ebx, 8007000Eh
0x1800507fd  mov     edx, 79Fh
0x180050802  jmp     loc_1800508B4
0x180050807  cmp     word ptr [rdi], 8
0x18005080b  jz      short loc_18005081C
0x18005080d  mov     ebx, 80070057h
0x180050812  mov     edx, 77Fh
0x180050817  jmp     loc_1800508B4
0x18005081c  mov     rbx, [rdi+8]
0x180050820  test    rbx, rbx
0x180050823  jz      loc_1800508CD
0x180050829  mov     rcx, rbx; pbstr
0x18005082c  call    cs:__imp_SysStringLen
0x180050832  mov     eax, eax
0x180050834  mov     [rsp+0E8h+lpString2], rax; int
0x180050839  mov     r9, rbx; Src
0x18005083c  mov     r8d, 81h; DstSizeInBytes
0x180050842  lea     rdx, [rsp+0E8h+Dst]; Dst
0x180050847  xor     ecx, ecx; PtNumOfCharConverted
0x180050849  call    wcstombs_s
0x18005084e  test    eax, eax
0x180050850  jz      short loc_18005085E
0x180050852  mov     ebx, 8000FFFFh
0x180050857  mov     edx, 789h
0x18005085c  jmp     short loc_1800508B4
0x18005085e  lea     rbx, [rbp+3D8h]
0x180050865  mov     rcx, [rbx]; Block
0x180050868  test    rcx, rcx
0x18005086b  jz      short loc_18005087E
0x18005086d  mov     edx, 90h
0x180050872  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180050877  mov     qword ptr [rbx], 0
0x18005087e  test    rbx, rbx
0x180050881  jnz     short loc_18005088A
0x180050883  mov     ebx, 80004003h
0x180050888  jmp     short loc_1800508AF
0x18005088a  mov     qword ptr [rbx], 0
0x180050891  cmp     [rsp+0E8h+Dst], 0
0x180050896  jz      short loc_1800508CD
0x180050898  lea     rcx, [rsp+0E8h+Dst]; char *
0x18005089d  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800508a2  mov     [rbx], rax
0x1800508a5  test    rax, rax
0x1800508a8  jnz     short loc_1800508CD
0x1800508aa  mov     ebx, 8007000Eh
0x1800508af  mov     edx, 78Ch; void *
0x1800508b4  mov     r9d, ebx; char *
0x1800508b7  mov     rcx, [rsp+0E8h]; this
0x1800508bf  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800508c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800508cb  jmp     short loc_1800508CF
0x1800508cd  xor     ebx, ebx
0x1800508cf  mov     eax, ebx
0x1800508d1  mov     rcx, [rsp+0E8h+var_28]
0x1800508d9  xor     rcx, rsp; StackCookie
0x1800508dc  call    __security_check_cookie
0x1800508e1  mov     rbx, [rsp+0E8h+arg_8]
0x1800508e9  add     rsp, 0D0h
0x1800508f0  pop     rdi
0x1800508f1  pop     rsi
0x1800508f2  pop     rbp
0x1800508f3  retn
```
