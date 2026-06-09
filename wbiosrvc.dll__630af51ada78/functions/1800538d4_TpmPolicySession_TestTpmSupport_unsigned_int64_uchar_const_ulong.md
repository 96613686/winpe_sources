# TpmPolicySession::TestTpmSupport(unsigned __int64,uchar const *,ulong)

- ea: `0x1800538d4`
- end: `0x180053f83`
- name: `?TestTpmSupport@TpmPolicySession@@YAJ_KPEBEK@Z`
- size: `1711`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, TpmPolicySession *this, ULONG cbSecret, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800683fc`

## callees

- `0x1800058ec`
- `0x180006958`
- `0x1800069b0`
- `0x180013b40`
- `0x180027c0c`
- `0x18003a51c`
- `0x18003b770`
- `0x18003c468`
- `0x180040278`
- `0x18005388c`
- `0x1800538d4`
- `0x180053fb0`
- `0x1800549c4`
- `0x180055cf8`
- `0x1800702a8`
- `0x1800b8768`
- `0x1800b87e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005399b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053a83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053aa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053b40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053f26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005399b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053a83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053aa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053b40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053f26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053f4a`

## string_xrefs

- `0x18005397a`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180053a62`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180053b11`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180053c00`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180053d22`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180053e24`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TpmPolicySession::TestTpmSupport(TpmPolicySession *hObject, UCHAR *this, ULONG cbSecret)
{
  int PolicyInfo; // ebx
  __int64 v7; // rdx
  HLOCAL v8; // rcx
  const struct TpmPolicySession::PolicyInfo *v9; // rdx
  HLOCAL v10; // rcx
  HLOCAL v11; // rcx
  int v12; // eax
  HLOCAL v13; // rcx
  HLOCAL v14; // rcx
  int AuthorizationHmac; // eax
  HLOCAL v16; // rcx
  HLOCAL v17; // rcx
  __int64 v18; // rcx
  TpmPolicySession *v19; // rdx
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  void *v24; // rdx
  TpmPolicySession *v25; // rdx
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  const char *v28; // r9
  __int64 result; // rax
  void *v30; // rdx
  TpmPolicySession *v31; // rdx
  HLOCAL v32; // rcx
  HLOCAL v33; // rcx
  int v34; // [rsp+20h] [rbp-108h]
  unsigned int *v35; // [rsp+20h] [rbp-108h]
  int v36; // [rsp+20h] [rbp-108h]
  int v37; // [rsp+20h] [rbp-108h]
  int v38; // [rsp+20h] [rbp-108h]
  int v39; // [rsp+20h] [rbp-108h]
  unsigned int *v40; // [rsp+28h] [rbp-100h]
  ULONG v41[2]; // [rsp+28h] [rbp-100h]
  const unsigned __int8 *cbOutput; // [rsp+38h] [rbp-F0h]
  HLOCAL hMem; // [rsp+50h] [rbp-D8h] BYREF
  HLOCAL v44; // [rsp+58h] [rbp-D0h] BYREF
  TpmPolicySession *v45; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE *p_hMem; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v47[2]; // [rsp+70h] [rbp-B8h] BYREF
  char v48; // [rsp+78h] [rbp-B0h]
  UCHAR v49[4]; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v50[12]; // [rsp+84h] [rbp-A4h] BYREF
  PUCHAR v51; // [rsp+90h] [rbp-98h] BYREF
  int v52; // [rsp+98h] [rbp-90h]
  PUCHAR pbInput; // [rsp+A8h] [rbp-80h] BYREF
  int v54; // [rsp+B0h] [rbp-78h]
  PUCHAR v55; // [rsp+C0h] [rbp-68h] BYREF
  int v56; // [rsp+C8h] [rbp-60h]
  unsigned int v57[2]; // [rsp+D8h] [rbp-50h] BYREF
  int v58; // [rsp+E0h] [rbp-48h]
  unsigned __int8 *v59; // [rsp+F0h] [rbp-38h] BYREF
  const void *v60[3]; // [rsp+F8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  unsigned __int8 *v62; // [rsp+148h] [rbp+20h] BYREF

  LOBYTE(v62) = 2;
  try
  {
    std::vector<unsigned char>::vector<unsigned char>(&v51, 32, &v62);
    hMem = 0;
    LODWORD(v62) = 0;
    p_hMem = &hMem;
    *(_QWORD *)v47 = 0;
    v48 = 1;
    PolicyInfo = TpmPolicySession::GetPolicyInfo(
                   (NCRYPT_HANDLE)hObject,
                   v51,
                   v52 - (int)v51,
                   (unsigned int)v47,
                   &v62,
                   v40);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21A,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        v34);
      v8 = hMem;
      hMem = 0;
      if ( v8 )
        LocalFree(v8);
LABEL_41:
      std::vector<unsigned char>::_Tidy(&v51);
      return (unsigned int)PolicyInfo;
    }
    LODWORD(v60[0]) = (_DWORD)v62;
    v60[1] = hMem;
    LOBYTE(v62) = 3;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      v57,
      v7,
      &v62);
    v44 = 0;
    LODWORD(v62) = 0;
    p_hMem = &v44;
    *(_QWORD *)v47 = 0;
    v48 = 1;
    PolicyInfo = TpmPolicySession::SealWithPolicyInfo(
                   v60,
                   v9,
                   *(BYTE **)v57,
                   (const unsigned __int8 *)(v58 - v57[0]),
                   (PBYTE *)v47,
                   &v62);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        (int)v35);
      v10 = v44;
      v44 = 0;
      if ( v10 )
        LocalFree(v10);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v57);
      v11 = hMem;
      hMem = 0;
      if ( v11 )
        LocalFree(v11);
      goto LABEL_41;
    }
    std::vector<unsigned char>::vector<unsigned char>(&pbInput, 32);
    *(_DWORD *)v49 = 0;
    v12 = TpmPolicySession::OpenSession(
            hObject,
            (unsigned __int64)pbInput,
            (unsigned __int8 *)(unsigned int)(v54 - (_DWORD)pbInput),
            (unsigned int)v49,
            v35);
    PolicyInfo = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x237,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)v12,
        v36);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v13 = v44;
      v44 = 0;
      if ( v13 )
        LocalFree(v13);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v57);
      v14 = hMem;
      hMem = 0;
      if ( v14 )
        LocalFree(v14);
      goto LABEL_41;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v55);
    AuthorizationHmac = TpmPolicySession::GenerateAuthorizationHmac(
                          this,
                          cbSecret,
                          pbInput,
                          v54 - (int)pbInput,
                          v51,
                          v52 - (int)v51,
                          v55,
                          v56 - (int)v55,
                          v49);
    PolicyInfo = AuthorizationHmac;
    if ( AuthorizationHmac < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)AuthorizationHmac,
        v37);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v55);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v16 = v44;
      v44 = 0;
      if ( v16 )
        LocalFree(v16);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v57);
      v17 = hMem;
      hMem = 0;
      if ( v17 )
        LocalFree(v17);
      goto LABEL_41;
    }
    v45 = 0;
    *(_DWORD *)v50 = 0;
    p_hMem = &v45;
    *(_QWORD *)v47 = 0;
    v48 = 1;
    LODWORD(cbOutput) = v56 - (_DWORD)v55;
    v41[0] = v52 - (_DWORD)v51;
    PolicyInfo = TpmPolicySession::GetTpmTicket(
                   (NCRYPT_HANDLE)hObject,
                   (unsigned __int64)v55,
                   (int)pbInput,
                   (const unsigned __int8 *)(unsigned int)(v54 - (_DWORD)pbInput),
                   v51,
                   *(rsize_t *)v41,
                   v55,
                   cbOutput,
                   (unsigned int)v47,
                   (unsigned __int8 **)v50,
                   (unsigned int *)hMem);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        v38);
      v19 = v45;
      v45 = 0;
      if ( v19 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v18, v19);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v55);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v20 = v44;
      v44 = 0;
      if ( v20 )
        LocalFree(v20);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v57);
      v21 = hMem;
      hMem = 0;
      if ( v21 )
        LocalFree(v21);
      goto LABEL_41;
    }
    *(_QWORD *)&v50[4] = 0;
    p_hMem = &v50[4];
    *(_QWORD *)v47 = 0;
    v48 = 1;
    PolicyInfo = TpmPolicySession::UnSealWithTpmTicket(
                   v45,
                   (const unsigned __int8 *)*(unsigned int *)v50,
                   (BYTE *)v44,
                   (const unsigned __int8 *)(unsigned int)v62,
                   (PBYTE *)v47,
                   &v59);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x264,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        v39);
      v24 = *(void **)&v50[4];
      *(_QWORD *)&v50[4] = 0;
      if ( v24 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v23, v24);
      v25 = v45;
      v45 = 0;
      if ( v25 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v23, v25);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v55);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v26 = v44;
      v44 = 0;
      if ( v26 )
        LocalFree(v26);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v57);
      v27 = hMem;
      hMem = 0;
      if ( v27 )
        LocalFree(v27);
      goto LABEL_41;
    }
    v30 = *(void **)&v50[4];
    *(_QWORD *)&v50[4] = 0;
    if ( v30 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v22, v30);
    v31 = v45;
    v45 = 0;
    if ( v31 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v22, v31);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v55);
    std::vector<unsigned char>::_Tidy(&pbInput);
    v32 = v44;
    v44 = 0;
    if ( v32 )
      LocalFree(v32);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v57);
    v33 = hMem;
    hMem = 0;
    if ( v33 )
      LocalFree(v33);
    std::vector<unsigned char>::_Tidy(&v51);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v62) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x266,
                     (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                     v28);
    return (unsigned int)v62;
  }
  return result;
}

```

## disassembly

```asm
0x1800538d4  mov     rax, rsp
0x1800538d7  mov     [rax+8], rbx
0x1800538db  mov     [rax+10h], rsi
0x1800538df  push    rdi
0x1800538e0  push    r14
0x1800538e2  push    r15
0x1800538e4  sub     rsp, 110h
0x1800538eb  mov     esi, r8d
0x1800538ee  mov     r14, rdx
0x1800538f1  mov     rdi, rcx
0x1800538f4  mov     byte ptr [rax+20h], 2
0x1800538f8  lea     r8, [rax+20h]
0x1800538fc  mov     edx, 20h ; ' '
0x180053901  lea     rcx, [rax-98h]
0x180053908  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18005390d  nop
0x18005390e  xor     r15d, r15d
0x180053911  mov     [rsp+128h+hMem], r15; unsigned int *
0x180053916  mov     dword ptr [rsp+128h+arg_18], r15d
0x18005391e  lea     rax, [rsp+128h+hMem]
0x180053923  mov     [rsp+128h+var_C0], rax
0x180053928  mov     qword ptr [rsp+128h+var_B8], r15
0x18005392d  mov     [rsp+128h+var_B0], 1
0x180053932  mov     rdx, [rsp+128h+var_98]; pbInput
0x18005393a  mov     r8d, [rsp+128h+var_90]
0x180053942  sub     r8d, edx; cbInput
0x180053945  lea     rax, [rsp+128h+arg_18]
0x18005394d  mov     [rsp+128h+var_108], rax; int
0x180053952  lea     r9, [rsp+128h+var_B8]; unsigned int
0x180053957  mov     rcx, rdi; hObject
0x18005395a  call    ?GetPolicyInfo@TpmPolicySession@@YAJ_KPEBEKPEAPEAEPEAK@Z; TpmPolicySession::GetPolicyInfo(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)
0x18005395f  mov     ebx, eax
0x180053961  lea     rcx, [rsp+128h+var_C0]
0x180053966  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18005396b  test    ebx, ebx
0x18005396d  jns     short loc_1800539B6
0x18005396f  mov     rcx, [rsp+128h]; this
0x180053977  mov     r9d, ebx; char *
0x18005397a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180053981  mov     edx, 21Ah; void *
0x180053986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005398b  nop
0x18005398c  mov     rcx, [rsp+128h+hMem]; hMem
0x180053991  mov     [rsp+128h+hMem], r15
0x180053996  test    rcx, rcx
0x180053999  jz      short loc_1800539A2
0x18005399b  call    cs:__imp_LocalFree
0x1800539a1  nop
0x1800539a2  lea     rcx, [rsp+128h+var_98]
0x1800539aa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800539af  mov     eax, ebx
0x1800539b1  jmp     loc_180053F6A
0x1800539b6  mov     eax, dword ptr [rsp+128h+arg_18]
0x1800539bd  mov     [rsp+128h+var_30], eax
0x1800539c4  mov     rax, [rsp+128h+hMem]
0x1800539c9  mov     [rsp+128h+var_28], rax
0x1800539d1  mov     byte ptr [rsp+128h+arg_18], 3
0x1800539d9  lea     r8, [rsp+128h+arg_18]
0x1800539e1  lea     rcx, [rsp+128h+var_50]
0x1800539e9  call    ??$?0U?$secure_allocator@E@wil@@$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBEAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,uchar const &,wil::secure_allocator<uchar> const &)
0x1800539ee  nop
0x1800539ef  mov     [rsp+128h+var_D0], r15
0x1800539f4  mov     dword ptr [rsp+128h+arg_18], r15d
0x1800539fc  lea     rax, [rsp+128h+var_D0]
0x180053a01  mov     [rsp+128h+var_C0], rax
0x180053a06  mov     qword ptr [rsp+128h+var_B8], r15
0x180053a0b  mov     [rsp+128h+var_B0], 1
0x180053a10  mov     r8, qword ptr [rsp+128h+var_50]; unsigned int
0x180053a18  mov     r9d, [rsp+128h+var_48]
0x180053a20  sub     r9d, r8d; unsigned __int8 *
0x180053a23  lea     rax, [rsp+128h+arg_18]
0x180053a2b  mov     qword ptr [rsp+128h+var_100], rax; unsigned __int8 **
0x180053a30  lea     rax, [rsp+128h+var_B8]
0x180053a35  mov     [rsp+128h+var_108], rax; int
0x180053a3a  lea     rcx, [rsp+128h+var_30]; this
0x180053a42  call    ?SealWithPolicyInfo@TpmPolicySession@@YAJPEBUPolicyInfo@1@KPEBEKPEAPEAEPEAK@Z; TpmPolicySession::SealWithPolicyInfo(TpmPolicySession::PolicyInfo const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x180053a47  mov     ebx, eax
0x180053a49  lea     rcx, [rsp+128h+var_C0]
0x180053a4e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180053a53  test    ebx, ebx
0x180053a55  jns     short loc_180053AC2
0x180053a57  mov     rcx, [rsp+128h]; this
0x180053a5f  mov     r9d, ebx; char *
0x180053a62  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180053a69  mov     edx, 22Ch; void *
0x180053a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053a73  nop
0x180053a74  mov     rcx, [rsp+128h+var_D0]; hMem
0x180053a79  mov     [rsp+128h+var_D0], r15
0x180053a7e  test    rcx, rcx
0x180053a81  jz      short loc_180053A8A
0x180053a83  call    cs:__imp_LocalFree
0x180053a89  nop
0x180053a8a  lea     rcx, [rsp+128h+var_50]
0x180053a92  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180053a97  nop
0x180053a98  mov     rcx, [rsp+128h+hMem]; hMem
0x180053a9d  mov     [rsp+128h+hMem], r15
0x180053aa2  test    rcx, rcx
0x180053aa5  jz      short loc_180053AAE
0x180053aa7  call    cs:__imp_LocalFree
0x180053aad  nop
0x180053aae  lea     rcx, [rsp+128h+var_98]
0x180053ab6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053abb  mov     eax, ebx
0x180053abd  jmp     loc_180053F6A
0x180053ac2  mov     edx, 20h ; ' '
0x180053ac7  lea     rcx, [rsp+128h+pbInput]
0x180053acf  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180053ad4  nop
0x180053ad5  mov     dword ptr [rsp+128h+var_A8], r15d
0x180053add  mov     rdx, [rsp+128h+pbInput]; unsigned __int64
0x180053ae5  mov     r8d, [rsp+128h+var_78]
0x180053aed  sub     r8d, edx; unsigned __int8 *
0x180053af0  lea     r9, [rsp+128h+var_A8]; unsigned int
0x180053af8  mov     rcx, rdi; this
0x180053afb  call    ?OpenSession@TpmPolicySession@@YAJ_KPEAEKPEAK@Z; TpmPolicySession::OpenSession(unsigned __int64,uchar *,ulong,ulong *)
0x180053b00  mov     ebx, eax
0x180053b02  test    eax, eax
0x180053b04  jns     short loc_180053B7F
0x180053b06  mov     rcx, [rsp+128h]; this
0x180053b0e  mov     r9d, eax; char *
0x180053b11  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180053b18  mov     edx, 237h; void *
0x180053b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053b22  nop
0x180053b23  lea     rcx, [rsp+128h+pbInput]
0x180053b2b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053b30  nop
0x180053b31  mov     rcx, [rsp+128h+var_D0]; hMem
0x180053b36  mov     [rsp+128h+var_D0], r15
0x180053b3b  test    rcx, rcx
0x180053b3e  jz      short loc_180053B47
0x180053b40  call    cs:__imp_LocalFree
0x180053b46  nop
0x180053b47  lea     rcx, [rsp+128h+var_50]
0x180053b4f  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180053b54  nop
0x180053b55  mov     rcx, [rsp+128h+hMem]; hMem
0x180053b5a  mov     [rsp+128h+hMem], r15
0x180053b5f  test    rcx, rcx
0x180053b62  jz      short loc_180053B6B
0x180053b64  call    cs:__imp_LocalFree
0x180053b6a  nop
0x180053b6b  lea     rcx, [rsp+128h+var_98]
0x180053b73  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053b78  mov     eax, ebx
0x180053b7a  jmp     loc_180053F6A
0x180053b7f  lea     rcx, [rsp+128h+var_68]
0x180053b87  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x180053b8c  mov     rdx, [rsp+128h+var_68]
0x180053b94  mov     r10, [rsp+128h+var_98]
0x180053b9c  mov     r8, [rsp+128h+pbInput]; pbInput
0x180053ba4  mov     ecx, [rsp+128h+var_60]
0x180053bab  sub     ecx, edx
0x180053bad  mov     eax, [rsp+128h+var_90]
0x180053bb4  sub     eax, r10d
0x180053bb7  mov     r9d, [rsp+128h+var_78]
0x180053bbf  sub     r9d, r8d; cbInput
0x180053bc2  lea     r11, [rsp+128h+var_A8]
0x180053bca  mov     qword ptr [rsp+128h+var_E8], r11; UCHAR
0x180053bcf  mov     dword ptr [rsp+128h+cbOutput], ecx; cbOutput
0x180053bd3  mov     [rsp+128h+var_F8], rdx; PUCHAR
0x180053bd8  mov     [rsp+128h+var_100], eax; ULONG
0x180053bdc  mov     [rsp+128h+var_108], r10; int
0x180053be1  mov     edx, esi; cbSecret
0x180053be3  mov     rcx, r14; this
0x180053be6  call    ?GenerateAuthorizationHmac@TpmPolicySession@@YAJPEBEK0K0KPEAEKPEAK@Z; TpmPolicySession::GenerateAuthorizationHmac(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar *,ulong,ulong *)
0x180053beb  mov     ebx, eax
0x180053bed  test    eax, eax
0x180053bef  jns     loc_180053C7B
0x180053bf5  mov     rcx, [rsp+128h]; this
0x180053bfd  mov     r9d, eax; char *
0x180053c00  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180053c07  mov     edx, 246h; void *
0x180053c0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053c11  lea     rcx, [rsp+128h+var_68]
0x180053c19  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180053c1e  nop
0x180053c1f  lea     rcx, [rsp+128h+pbInput]
0x180053c27  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053c2c  nop
0x180053c2d  mov     rcx, [rsp+128h+var_D0]; hMem
0x180053c32  mov     [rsp+128h+var_D0], r15
0x180053c37  test    rcx, rcx
0x180053c3a  jz      short loc_180053C43
0x180053c3c  call    cs:__imp_LocalFree
0x180053c42  nop
0x180053c43  lea     rcx, [rsp+128h+var_50]
0x180053c4b  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180053c50  nop
0x180053c51  mov     rcx, [rsp+128h+hMem]; hMem
0x180053c56  mov     [rsp+128h+hMem], r15
0x180053c5b  test    rcx, rcx
0x180053c5e  jz      short loc_180053C67
0x180053c60  call    cs:__imp_LocalFree
0x180053c66  nop
0x180053c67  lea     rcx, [rsp+128h+var_98]
0x180053c6f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053c74  mov     eax, ebx
0x180053c76  jmp     loc_180053F6A
0x180053c7b  mov     [rsp+128h+var_C8], r15
0x180053c80  mov     dword ptr [rsp+128h+var_A4], r15d
0x180053c88  lea     rax, [rsp+128h+var_C8]
0x180053c8d  mov     [rsp+128h+var_C0], rax
0x180053c92  mov     qword ptr [rsp+128h+var_B8], r15
0x180053c97  mov     [rsp+128h+var_B0], 1
0x180053c9c  mov     rdx, [rsp+128h+var_68]; unsigned __int64
0x180053ca4  mov     r10, [rsp+128h+var_98]
0x180053cac  mov     r8, [rsp+128h+pbInput]; int
0x180053cb4  mov     ecx, [rsp+128h+var_60]
0x180053cbb  sub     ecx, edx
0x180053cbd  mov     eax, [rsp+128h+var_90]
0x180053cc4  sub     eax, r10d
0x180053cc7  mov     r9d, [rsp+128h+var_78]
0x180053ccf  sub     r9d, r8d; unsigned __int8 *
0x180053cd2  lea     r11, [rsp+128h+var_A4]
0x180053cda  mov     [rsp+128h+var_E0], r11; unsigned __int8 **
0x180053cdf  lea     r11, [rsp+128h+var_B8]
0x180053ce4  mov     qword ptr [rsp+128h+var_E8], r11; unsigned int
0x180053ce9  mov     dword ptr [rsp+128h+cbOutput], ecx; unsigned __int8 *
0x180053ced  mov     [rsp+128h+var_F8], rdx; unsigned int *
0x180053cf2  mov     [rsp+128h+var_100], eax; SourceSize
0x180053cf6  mov     [rsp+128h+var_108], r10; int
0x180053cfb  mov     rcx, rdi; hObject
0x180053cfe  call    ?GetTpmTicket@TpmPolicySession@@YAJ_KHPEBEK1K1KPEAPEAEPEAK@Z; TpmPolicySession::GetTpmTicket(unsigned __int64,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x180053d03  mov     ebx, eax
0x180053d05  lea     rcx, [rsp+128h+var_C0]
0x180053d0a  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x180053d0f  test    ebx, ebx
0x180053d11  jns     loc_180053DB1
0x180053d17  mov     rcx, [rsp+128h]; this
0x180053d1f  mov     r9d, ebx; char *
0x180053d22  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180053d29  mov     edx, 257h; void *
0x180053d2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053d33  mov     rdx, [rsp+128h+var_C8]
0x180053d38  mov     [rsp+128h+var_C8], r15
0x180053d3d  test    rdx, rdx
0x180053d40  jz      short loc_180053D47
0x180053d42  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x180053d47  lea     rcx, [rsp+128h+var_68]
0x180053d4f  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180053d54  nop
0x180053d55  lea     rcx, [rsp+128h+pbInput]
0x180053d5d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053d62  nop
0x180053d63  mov     rcx, [rsp+128h+var_D0]; hMem
0x180053d68  mov     [rsp+128h+var_D0], r15
0x180053d6d  test    rcx, rcx
0x180053d70  jz      short loc_180053D79
0x180053d72  call    cs:__imp_LocalFree
0x180053d78  nop
0x180053d79  lea     rcx, [rsp+128h+var_50]
0x180053d81  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180053d86  nop
0x180053d87  mov     rcx, [rsp+128h+hMem]; hMem
0x180053d8c  mov     [rsp+128h+hMem], r15
0x180053d91  test    rcx, rcx
0x180053d94  jz      short loc_180053D9D
0x180053d96  call    cs:__imp_LocalFree
0x180053d9c  nop
0x180053d9d  lea     rcx, [rsp+128h+var_98]
0x180053da5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180053daa  mov     eax, ebx
0x180053dac  jmp     loc_180053F6A
0x180053db1  mov     qword ptr [rsp+128h+var_A4+4], r15
0x180053db9  lea     rax, [rsp+128h+var_A4+4]
0x180053dc1  mov     [rsp+128h+var_C0], rax
0x180053dc6  mov     qword ptr [rsp+128h+var_B8], r15
0x180053dcb  mov     [rsp+128h+var_B0], 1
0x180053dd0  lea     rax, [rsp+128h+var_38]
0x180053dd8  mov     qword ptr [rsp+128h+var_100], rax; unsigned __int8 **
0x180053ddd  lea     rax, [rsp+128h+var_B8]
0x180053de2  mov     [rsp+128h+var_108], rax; int
0x180053de7  mov     r9d, dword ptr [rsp+128h+arg_18]; unsigned __int8 *
0x180053def  mov     r8, [rsp+128h+var_D0]; unsigned int
0x180053df4  mov     edx, dword ptr [rsp+128h+var_A4]; unsigned __int8 *
0x180053dfb  mov     rcx, [rsp+128h+var_C8]; this
0x180053e00  call    ?UnSealWithTpmTicket@TpmPolicySession@@YAJPEBEK0KPEAPEAEPEAK@Z; TpmPolicySession::UnSealWithTpmTicket(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x180053e05  mov     ebx, eax
0x180053e07  lea     rcx, [rsp+128h+var_C0]
0x180053e0c  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x180053e11  test    ebx, ebx
0x180053e13  jns     loc_180053ECD
0x180053e19  mov     rcx, [rsp+128h]; this
0x180053e21  mov     r9d, ebx; char *
0x180053e24  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180053e2b  mov     edx, 264h; void *
0x180053e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053e35  mov     rdx, qword ptr [rsp+128h+var_A4+4]
0x180053e3d  mov     qword ptr [rsp+128h+var_A4+4], r15
0x180053e45  test    rdx, rdx
0x180053e48  jz      short loc_180053E4F
0x180053e4a  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x180053e4f  mov     rdx, [rsp+128h+var_C8]
0x180053e54  mov     [rsp+128h+var_C8], r15
0x180053e59  test    rdx, rdx
0x180053e5c  jz      short loc_180053E63
0x180053e5e  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
  ... truncated ...
```
