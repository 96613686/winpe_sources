# CAppxDeploymentOperation::PackageStagingProgressCallback(ABI::Windows::ApplicationModel::IPackageCatalog *,ABI::Windows::ApplicationModel::IPackageStagingEventArgs *)

- ea: `0x18020fd90`
- end: `0x18021058b`
- name: `?PackageStagingProgressCallback@CAppxDeploymentOperation@@AEAAJPEAUIPackageCatalog@ApplicationModel@Windows@ABI@@PEAUIPackageStagingEventArgs@345@@Z`
- size: `2043`
- prototype: `__int64 __fastcall(CAppxDeploymentOperation *__hidden this, struct ABI::Windows::ApplicationModel::IPackageCatalog *, struct ABI::Windows::ApplicationModel::IPackageStagingEventArgs *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x1800ae39c`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x18012bf80`
- `0x18020fd90`
- `0x18021b228`
- `0x18021f5fc`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802103da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802103da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802104b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802104b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180210419`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180210419`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020feee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802101be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802101ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021021a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802102ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802102f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210325`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020feee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802101be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802101ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021021a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802102ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802102f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180210325`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020ff1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180210307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020ff1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180210307`

## string_xrefs

- `0x18021001d`: `AppX progress for update {%ws}, subpackage(%lu/%lu): PFaN=%ws, Downloaded=%I64u/%I64u`
- `0x18021039f`: `AppX progress for update {%ws}: PFaN=%ws, %I64u / %I64u (%lu%%), subPhase=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CAppxDeploymentOperation::PackageStagingProgressCallback(
        CAppxDeploymentOperation *this,
        struct ABI::Windows::ApplicationModel::IPackageCatalog *a2,
        struct ABI::Windows::ApplicationModel::IPackageStagingEventArgs *a3)
{
  struct ABI::Windows::ApplicationModel::IPackageStagingEventArgs *v3; // r12
  char *v5; // rdi
  signed int v6; // r14d
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, __int64 *); // rsi
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // r13d
  char *v12; // r12
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rsi
  const WCHAR *StringRawBuffer; // rax
  const wchar_t *v16; // rdx
  wchar_t *v17; // r9
  __int64 *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rsi
  int v21; // r14d
  __int64 updated; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rsi
  const WCHAR *v33; // rax
  const wchar_t *v34; // rdx
  wchar_t *v35; // r9
  int v36; // r13d
  char *v37; // rsi
  void *v38; // rcx
  unsigned int *v39; // r8
  __int64 v40; // rdx
  _WORD *v41; // rcx
  __int16 v42; // ax
  _WORD *v43; // rax
  const wchar_t *v44; // r9
  __int64 v45; // rcx
  __int64 v46; // rcx
  struct ISusHandlerNotification *v48; // [rsp+20h] [rbp-E0h]
  unsigned int v49; // [rsp+28h] [rbp-D8h]
  __int64 v50; // [rsp+38h] [rbp-C8h]
  __int64 v51; // [rsp+40h] [rbp-C0h]
  _BYTE v53[112]; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v55; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING string; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v57; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v58; // [rsp+100h] [rbp+0h] BYREF
  __int64 v59; // [rsp+108h] [rbp+8h] BYREF
  __int64 v60; // [rsp+110h] [rbp+10h] BYREF
  __int64 v61; // [rsp+118h] [rbp+18h] BYREF
  double v62; // [rsp+120h] [rbp+20h] BYREF
  __int64 v63; // [rsp+128h] [rbp+28h] BYREF
  _WORD v64[72]; // [rsp+130h] [rbp+30h] BYREF

  v3 = a3;
  v58 = 0;
  v60 = 0;
  v5 = 0;
  LODWORD(v57) = 0;
  v6 = (**(__int64 (__fastcall ***)(struct ABI::Windows::ApplicationModel::IPackageStagingEventArgs *, GUID *, __int64 *))a3)(
         a3,
         &GUID_1c76ab32_3c4f_452d_a2cb_9be2f17fb900,
         &v58);
  if ( v6 < 0 )
    goto LABEL_78;
  v7 = v58;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 104LL);
  v9 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v6 = v8(v7, &v60);
  if ( v6 < 0 )
    goto LABEL_78;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v60 + 56LL))(v60, &v57);
  if ( v6 < 0 )
    goto LABEL_78;
  v10 = v57;
  if ( (_DWORD)v57 )
  {
    v5 = (char *)SafeSusAllocArray((unsigned int)v57, 0xA8u);
    v6 = v5 == 0 ? 0x8007000E : 0;
    if ( !v5 )
      goto LABEL_78;
    v10 = v57;
  }
  v11 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      v55 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v60 + 48LL))(v60, v11, &v55);
      if ( v6 < 0 )
        break;
      v12 = &v5[168 * v11];
      string = 0;
      v13 = v55;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v6 = v14(v13, &string);
      if ( v6 < 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        v29 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        goto LABEL_77;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( (int)AppXUtil::GetPackageFamilyNameFromPackageFullName(
                  StringRawBuffer,
                  v16,
                  (unsigned int)v5 + 168 * v11,
                  v17) < 0 )
        *(_WORD *)v12 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 64LL))(v55, v12 + 136);
      if ( v6 < 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        v28 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        goto LABEL_77;
      }
      v18 = (__int64 *)(v12 + 144);
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 72LL))(v55, v12 + 144);
      if ( v6 < 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        v27 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        goto LABEL_77;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 80LL))(v55, v12 + 152);
      if ( v6 < 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        v26 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        goto LABEL_77;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 88LL))(v55, v12 + 152);
      if ( v6 < 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        v25 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        goto LABEL_77;
      }
      if ( *((_BYTE *)this + 560) )
        *v18 += *((_QWORD *)v12 + 20);
      v19 = *v18;
      v20 = *((_QWORD *)v12 + 17);
      v21 = v57;
      updated = Trace::UpdateIdToString::UpdateIdToString(
                  (Trace::UpdateIdToString *)v53,
                  (CAppxDeploymentOperation *)((char *)this + 176));
      ++v11;
      LODWORD(v51) = v21;
      LODWORD(v50) = v11;
      WUTrace(
        0,
        0,
        4096,
        0,
        0,
        L"AppX progress for update {%ws}, subpackage(%lu/%lu): PFaN=%ws, Downloaded=%I64u/%I64u",
        updated,
        v50,
        v51,
        v12,
        v20,
        v19);
      WindowsDeleteString(string);
      string = 0;
      v23 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      if ( v11 >= (unsigned int)v57 )
      {
        v3 = a3;
        goto LABEL_24;
      }
    }
    v30 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
LABEL_77:
    if ( v6 >= 0 )
      goto LABEL_79;
    goto LABEL_78;
  }
LABEL_24:
  v62 = 0.0;
  v61 = 0;
  v59 = 0;
  v63 = 0;
  v54 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ABI::Windows::ApplicationModel::IPackageStagingEventArgs *, double *))(*(_QWORD *)v3 + 64LL))(
         v3,
         &v62);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 72LL))(v58, &v61);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 80LL))(v58, &v59);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 88LL))(v58, &v63);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 96LL))(v58, (char *)this + 552);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 64LL))(v58, &v54);
            if ( v6 >= 0 )
            {
              v24 = v59;
              if ( *((_BYTE *)this + 560) )
              {
                v24 = *((_QWORD *)this + 69) + v59;
                v59 = v24;
              }
              if ( v54 )
              {
                if ( (unsigned int)(v54 - 1) >= 2 )
                {
                  v6 = -2145112065;
                  goto LABEL_78;
                }
                LODWORD(v55) = 4;
                *((_BYTE *)this + 544) |= v24 != 0;
              }
              else
              {
                LODWORD(v55) = 2;
              }
              memset(v64, 0, 0x82u);
              string = 0;
              v31 = v58;
              v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v58 + 48LL);
              WindowsDeleteString(0);
              string = 0;
              v6 = v32(v31, &string);
              if ( v6 >= 0 )
              {
                v33 = WindowsGetStringRawBuffer(string, 0);
                if ( (int)AppXUtil::GetPackageFamilyNameFromPackageFullName(v33, v34, (unsigned int)v64, v35) < 0 )
                  v64[0] = 0;
                WindowsDeleteString(string);
                v36 = (int)v62;
                Trace::UpdateIdToString::UpdateIdToString(
                  (Trace::UpdateIdToString *)v53,
                  (CAppxDeploymentOperation *)((char *)this + 176));
                WUTrace(
                  0,
                  0,
                  4096,
                  0,
                  0,
                  L"AppX progress for update {%ws}: PFaN=%ws, %I64u / %I64u (%lu%%), subPhase=%ws");
                if ( this != (CAppxDeploymentOperation *)-296LL )
                  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
                *((_DWORD *)this + 86) = v36;
                *((_QWORD *)this + 44) = v61;
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ByteRangeProcessingTelemetry_58081463>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ByteRangeProcessingTelemetry_58081463>::GetImpl'::`2'::impl)
                  && v59
                  && !*((_QWORD *)this + 45) )
                {
                  GetSystemTimeAsFileTime((LPFILETIME)this + 66);
                }
                *((_QWORD *)this + 45) = v59;
                *((_DWORD *)this + 92) = v55;
                *((_DWORD *)this + 93) = v36;
                v37 = v5;
                v5 = 0;
                v38 = (void *)*((_QWORD *)this + 47);
                if ( v38 )
                  SusFree(v38);
                *((_QWORD *)this + 47) = v37;
                *((_DWORD *)this + 96) = v57;
                v39 = (unsigned int *)v64;
                v40 = 65;
                v41 = (_WORD *)((char *)this + 388);
                do
                {
                  if ( v40 == -2147483581 )
                    break;
                  v42 = *(_WORD *)v39;
                  if ( !*(_WORD *)v39 )
                    break;
                  v39 = (unsigned int *)((char *)v39 + 2);
                  *v41++ = v42;
                  --v40;
                }
                while ( v40 );
                v43 = v41 - 1;
                if ( v40 )
                  v43 = v41;
                *v43 = 0;
                if ( this != (CAppxDeploymentOperation *)-296LL )
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
                v44 = (const wchar_t *)*((_QWORD *)this + 21);
                if ( v44 )
                {
                  LODWORD(v48) = v36;
                  AppxDownloadUtils::RaiseReadyForProgress(
                    (CAppxDeploymentOperation *)((char *)this + 276),
                    (const struct _GUID *)this + 11,
                    *((const struct tagDSGlobalUpdateId **)this + 67),
                    v44,
                    v48,
                    v49);
                }
              }
              else
              {
                WindowsDeleteString(string);
              }
              goto LABEL_77;
            }
          }
        }
      }
    }
  }
LABEL_78:
  WUTrace("CAppxDeploymentOperation::PackageStagingProgressCallback", 482, 4096, 2, v6, L"Method failed");
LABEL_79:
  if ( v5 )
    SusFree(v5);
  v45 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18020fd90  mov     [rsp-8+arg_8], rbx
0x18020fd95  push    rbp
0x18020fd96  push    rsi
0x18020fd97  push    rdi
0x18020fd98  push    r12
0x18020fd9a  push    r13
0x18020fd9c  push    r14
0x18020fd9e  push    r15
0x18020fda0  lea     rbp, [rsp-0D0h]
0x18020fda8  sub     rsp, 1D0h
0x18020fdaf  mov     rax, cs:__security_cookie
0x18020fdb6  xor     rax, rsp
0x18020fdb9  mov     [rbp+100h+var_40], rax
0x18020fdc0  mov     r12, r8
0x18020fdc3  mov     [rsp+200h+var_198], r8
0x18020fdc8  mov     r15, rcx
0x18020fdcb  xor     esi, esi
0x18020fdcd  mov     [rbp+100h+var_100], rsi
0x18020fdd1  mov     [rbp+100h+var_F0], rsi
0x18020fdd5  mov     edi, esi
0x18020fdd7  mov     [rsp+200h+var_1A0], rsi
0x18020fddc  mov     dword ptr [rbp+100h+var_108], esi
0x18020fddf  mov     rax, [r8]
0x18020fde2  lea     r8, [rbp+100h+var_100]
0x18020fde6  lea     rdx, _GUID_1c76ab32_3c4f_452d_a2cb_9be2f17fb900
0x18020fded  mov     rcx, r12
0x18020fdf0  mov     rax, [rax]
0x18020fdf3  call    _guard_dispatch_icall
0x18020fdf8  mov     r14d, eax
0x18020fdfb  test    eax, eax
0x18020fdfd  js      loc_1802104ED
0x18020fe03  mov     rbx, [rbp+100h+var_100]
0x18020fe07  mov     rax, [rbx]
0x18020fe0a  mov     rsi, [rax+68h]
0x18020fe0e  mov     rcx, [rbp+100h+var_F0]
0x18020fe12  xor     eax, eax
0x18020fe14  test    rcx, rcx
0x18020fe17  jz      short loc_18020FE2A
0x18020fe19  mov     [rbp+100h+var_F0], rax
0x18020fe1d  mov     rax, [rcx]
0x18020fe20  mov     rax, [rax+10h]
0x18020fe24  call    _guard_dispatch_icall
0x18020fe29  nop
0x18020fe2a  lea     rdx, [rbp+100h+var_F0]
0x18020fe2e  mov     rcx, rbx
0x18020fe31  mov     rax, rsi
0x18020fe34  call    _guard_dispatch_icall
0x18020fe39  mov     r14d, eax
0x18020fe3c  xor     esi, esi
0x18020fe3e  test    eax, eax
0x18020fe40  js      loc_1802104ED
0x18020fe46  mov     rcx, [rbp+100h+var_F0]
0x18020fe4a  mov     rax, [rcx]
0x18020fe4d  lea     rdx, [rbp+100h+var_108]
0x18020fe51  mov     rax, [rax+38h]
0x18020fe55  call    _guard_dispatch_icall
0x18020fe5a  mov     r14d, eax
0x18020fe5d  test    eax, eax
0x18020fe5f  js      loc_1802104ED
0x18020fe65  mov     eax, dword ptr [rbp+100h+var_108]
0x18020fe68  mov     ecx, eax; unsigned __int64
0x18020fe6a  test    eax, eax
0x18020fe6c  jz      short loc_18020FE9F
0x18020fe6e  mov     edx, 0A8h; unsigned __int64
0x18020fe73  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18020fe78  mov     rdi, rax
0x18020fe7b  mov     [rsp+200h+var_1A0], rax
0x18020fe80  mov     rcx, rax
0x18020fe83  neg     rcx
0x18020fe86  sbb     r14d, r14d
0x18020fe89  not     r14d
0x18020fe8c  and     r14d, 8007000Eh
0x18020fe93  test    rax, rax
0x18020fe96  jz      loc_1802104ED
0x18020fe9c  mov     eax, dword ptr [rbp+100h+var_108]
0x18020fe9f  mov     r13d, esi
0x18020fea2  test    eax, eax
0x18020fea4  jz      loc_18021007A
0x18020feaa  mov     [rbp+100h+var_118], rsi
0x18020feae  mov     rcx, [rbp+100h+var_F0]
0x18020feb2  mov     rax, [rcx]
0x18020feb5  lea     r8, [rbp+100h+var_118]
0x18020feb9  mov     edx, r13d
0x18020febc  mov     rax, [rax+30h]
0x18020fec0  call    _guard_dispatch_icall
0x18020fec5  mov     r14d, eax
0x18020fec8  test    eax, eax
0x18020feca  js      loc_180210270
0x18020fed0  mov     eax, r13d
0x18020fed3  imul    r12, rax, 0A8h
0x18020feda  add     r12, rdi
0x18020fedd  mov     [rbp+100h+string], rsi
0x18020fee1  mov     rbx, [rbp+100h+var_118]
0x18020fee5  mov     rax, [rbx]
0x18020fee8  mov     rsi, [rax+30h]
0x18020feec  xor     ecx, ecx; string
0x18020feee  call    cs:__imp_WindowsDeleteString
0x18020fef4  xor     eax, eax
0x18020fef6  mov     [rbp+100h+string], rax
0x18020fefa  lea     rdx, [rbp+100h+string]
0x18020fefe  mov     rcx, rbx
0x18020ff01  mov     rax, rsi
0x18020ff04  call    _guard_dispatch_icall
0x18020ff09  mov     r14d, eax
0x18020ff0c  xor     esi, esi
0x18020ff0e  test    eax, eax
0x18020ff10  js      loc_180210243
0x18020ff16  xor     edx, edx; length
0x18020ff18  mov     rcx, [rbp+100h+string]; string
0x18020ff1c  call    cs:__imp_WindowsGetStringRawBuffer
0x18020ff22  mov     r8, r12; unsigned int
0x18020ff25  mov     rcx, rax; packageFullName
0x18020ff28  call    ?GetPackageFamilyNameFromPackageFullName@AppXUtil@@YAJPEB_WIPEA_W@Z; AppXUtil::GetPackageFamilyNameFromPackageFullName(wchar_t const *,uint,wchar_t *)
0x18020ff2d  test    eax, eax
0x18020ff2f  jns     short loc_18020FF36
0x18020ff31  mov     [r12], si
0x18020ff36  lea     rdx, [r12+88h]
0x18020ff3e  mov     rcx, [rbp+100h+var_118]
0x18020ff42  mov     rax, [rcx]
0x18020ff45  mov     rax, [rax+40h]
0x18020ff49  call    _guard_dispatch_icall
0x18020ff4e  mov     r14d, eax
0x18020ff51  test    eax, eax
0x18020ff53  js      loc_180210216
0x18020ff59  lea     rbx, [r12+90h]
0x18020ff61  mov     rcx, [rbp+100h+var_118]
0x18020ff65  mov     rax, [rcx]
0x18020ff68  mov     rdx, rbx
0x18020ff6b  mov     rax, [rax+48h]
0x18020ff6f  call    _guard_dispatch_icall
0x18020ff74  mov     r14d, eax
0x18020ff77  test    eax, eax
0x18020ff79  js      loc_1802101E9
0x18020ff7f  lea     rsi, [r12+98h]
0x18020ff87  mov     rcx, [rbp+100h+var_118]
0x18020ff8b  mov     rax, [rcx]
0x18020ff8e  mov     rdx, rsi
0x18020ff91  mov     rax, [rax+50h]
0x18020ff95  call    _guard_dispatch_icall
0x18020ff9a  mov     r14d, eax
0x18020ff9d  test    eax, eax
0x18020ff9f  js      loc_1802101BA
0x18020ffa5  mov     rcx, [rbp+100h+var_118]
0x18020ffa9  mov     rax, [rcx]
0x18020ffac  mov     rdx, rsi
0x18020ffaf  mov     rax, [rax+58h]
0x18020ffb3  call    _guard_dispatch_icall
0x18020ffb8  mov     r14d, eax
0x18020ffbb  xor     esi, esi
0x18020ffbd  test    eax, eax
0x18020ffbf  js      loc_18021018D
0x18020ffc5  cmp     [r15+230h], sil
0x18020ffcc  jz      short loc_18020FFD9
0x18020ffce  mov     rax, [r12+0A0h]
0x18020ffd6  add     [rbx], rax
0x18020ffd9  mov     rbx, [rbx]
0x18020ffdc  mov     rsi, [r12+88h]
0x18020ffe4  mov     r14d, dword ptr [rbp+100h+var_108]
0x18020ffe8  lea     rdx, [r15+0B0h]; struct tagDSGlobalUpdateId *
0x18020ffef  lea     rcx, [rsp+200h+var_190]; this
0x18020fff4  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18020fff9  lea     ecx, [r13+1]
0x18020fffd  mov     r13d, ecx
0x180210000  mov     [rsp+200h+var_1A8], rbx
0x180210005  mov     [rsp+200h+var_1B0], rsi
0x18021000a  mov     [rsp+200h+var_1B8], r12
0x18021000f  mov     dword ptr [rsp+200h+var_1C0], r14d
0x180210014  mov     dword ptr [rsp+200h+var_1C8], ecx
0x180210018  mov     [rsp+200h+var_1D0], rax
0x18021001d  lea     rax, aAppxProgressFo_0; "AppX progress for update {%ws}, subpack"...
0x180210024  mov     qword ptr [rsp+200h+var_1D8], rax
0x180210029  xor     esi, esi
0x18021002b  mov     [rsp+200h+var_1E0], rsi
0x180210030  xor     r9d, r9d
0x180210033  xor     edx, edx
0x180210035  xor     ecx, ecx
0x180210037  mov     r8d, 1000h
0x18021003d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180210042  nop
0x180210043  mov     rcx, [rbp+100h+string]; string
0x180210047  call    cs:__imp_WindowsDeleteString
0x18021004d  mov     [rbp+100h+string], rsi
0x180210051  mov     rcx, [rbp+100h+var_118]
0x180210055  test    rcx, rcx
0x180210058  jz      short loc_18021006B
0x18021005a  mov     [rbp+100h+var_118], rsi
0x18021005e  mov     rax, [rcx]
0x180210061  mov     rax, [rax+10h]
0x180210065  call    _guard_dispatch_icall
0x18021006a  nop
0x18021006b  cmp     r13d, dword ptr [rbp+100h+var_108]
0x18021006f  jb      loc_18020FEAA
0x180210075  mov     r12, [rsp+200h+var_198]
0x18021007a  xorps   xmm0, xmm0
0x18021007d  movsd   [rbp+100h+var_E0], xmm0
0x180210082  mov     [rbp+100h+var_E8], rsi
0x180210086  mov     [rbp+100h+var_F8], rsi
0x18021008a  mov     [rbp+100h+var_D8], rsi
0x18021008e  mov     [rbp+100h+var_120], esi
0x180210091  mov     rax, [r12]
0x180210095  lea     rdx, [rbp+100h+var_E0]
0x180210099  mov     rcx, r12
0x18021009c  mov     rax, [rax+40h]
0x1802100a0  call    _guard_dispatch_icall
0x1802100a5  mov     r14d, eax
0x1802100a8  test    eax, eax
0x1802100aa  js      loc_1802104ED
0x1802100b0  mov     rcx, [rbp+100h+var_100]
0x1802100b4  mov     rax, [rcx]
0x1802100b7  lea     rdx, [rbp+100h+var_E8]
0x1802100bb  mov     rax, [rax+48h]
0x1802100bf  call    _guard_dispatch_icall
0x1802100c4  mov     r14d, eax
0x1802100c7  test    eax, eax
0x1802100c9  js      loc_1802104ED
0x1802100cf  mov     rcx, [rbp+100h+var_100]
0x1802100d3  mov     rax, [rcx]
0x1802100d6  lea     rdx, [rbp+100h+var_F8]
0x1802100da  mov     rax, [rax+50h]
0x1802100de  call    _guard_dispatch_icall
0x1802100e3  mov     r14d, eax
0x1802100e6  test    eax, eax
0x1802100e8  js      loc_1802104ED
0x1802100ee  mov     rcx, [rbp+100h+var_100]
0x1802100f2  mov     rax, [rcx]
0x1802100f5  lea     rdx, [rbp+100h+var_D8]
0x1802100f9  mov     rax, [rax+58h]
0x1802100fd  call    _guard_dispatch_icall
0x180210102  mov     r14d, eax
0x180210105  test    eax, eax
0x180210107  js      loc_1802104ED
0x18021010d  lea     rbx, [r15+228h]
0x180210114  mov     rcx, [rbp+100h+var_100]
0x180210118  mov     rax, [rcx]
0x18021011b  mov     rdx, rbx
0x18021011e  mov     rax, [rax+60h]
0x180210122  call    _guard_dispatch_icall
0x180210127  mov     r14d, eax
0x18021012a  test    eax, eax
0x18021012c  js      loc_1802104ED
0x180210132  mov     rcx, [rbp+100h+var_100]
0x180210136  mov     rax, [rcx]
0x180210139  lea     rdx, [rbp+100h+var_120]
0x18021013d  mov     rax, [rax+40h]
0x180210141  call    _guard_dispatch_icall
0x180210146  mov     r14d, eax
0x180210149  test    eax, eax
0x18021014b  js      loc_1802104ED
0x180210151  mov     rdx, [rbp+100h+var_F8]
0x180210155  cmp     [r15+230h], sil
0x18021015c  jz      short loc_180210165
0x18021015e  add     rdx, [rbx]
0x180210161  mov     [rbp+100h+var_F8], rdx
0x180210165  mov     ecx, [rbp+100h+var_120]
0x180210168  test    ecx, ecx
0x18021016a  jz      loc_1802102A5
0x180210170  sub     ecx, 1
0x180210173  jz      loc_18021028F
0x180210179  cmp     ecx, 1
0x18021017c  jz      loc_18021028F
0x180210182  mov     r14d, 80242FFFh
0x180210188  jmp     loc_1802104ED
0x18021018d  mov     rcx, [rbp+100h+string]; string
0x180210191  call    cs:__imp_WindowsDeleteString
0x180210197  mov     [rbp+100h+string], rsi
0x18021019b  mov     rcx, [rbp+100h+var_118]
0x18021019f  test    rcx, rcx
0x1802101a2  jz      short loc_1802101B5
0x1802101a4  mov     [rbp+100h+var_118], rsi
0x1802101a8  mov     rax, [rcx]
0x1802101ab  mov     rax, [rax+10h]
0x1802101af  call    _guard_dispatch_icall
0x1802101b4  nop
0x1802101b5  jmp     loc_1802104E8
0x1802101ba  mov     rcx, [rbp+100h+string]; string
0x1802101be  call    cs:__imp_WindowsDeleteString
0x1802101c4  xor     esi, esi
0x1802101c6  mov     [rbp+100h+string], rsi
0x1802101ca  mov     rcx, [rbp+100h+var_118]
0x1802101ce  test    rcx, rcx
0x1802101d1  jz      short loc_1802101E4
0x1802101d3  mov     [rbp+100h+var_118], rsi
0x1802101d7  mov     rax, [rcx]
0x1802101da  mov     rax, [rax+10h]
0x1802101de  call    _guard_dispatch_icall
0x1802101e3  nop
0x1802101e4  jmp     loc_1802104E8
0x1802101e9  mov     rcx, [rbp+100h+string]; string
0x1802101ed  call    cs:__imp_WindowsDeleteString
0x1802101f3  mov     [rbp+100h+string], rsi
0x1802101f7  mov     rcx, [rbp+100h+var_118]
0x1802101fb  test    rcx, rcx
0x1802101fe  jz      short loc_180210211
0x180210200  mov     [rbp+100h+var_118], rsi
0x180210204  mov     rax, [rcx]
0x180210207  mov     rax, [rax+10h]
0x18021020b  call    _guard_dispatch_icall
0x180210210  nop
0x180210211  jmp     loc_1802104E8
0x180210216  mov     rcx, [rbp+100h+string]; string
  ... truncated ...
```
