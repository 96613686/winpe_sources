# CDataPackageView::UnlockAndAssumeEnterpriseIdentity(Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)

- ea: `0x18004ff50`
- end: `0x1800505a2`
- name: `?UnlockAndAssumeEnterpriseIdentity@CDataPackageView@@UEAAJPEAW4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Z`
- size: `1618`
- prototype: `__int64 __fastcall(CDataPackageView *__hidden this, enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000dd24`
- `0x180043b6c`
- `0x180048480`
- `0x180048954`
- `0x18004ff50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005025d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005029d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005042b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005025d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005029d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005042b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ff98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800500a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ff98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800500a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180050318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180050318`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800500ce`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800500ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800500bd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800500bd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ffd2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ffd2`

## string_xrefs

- `0x18004ff91`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`
- `0x18005009d`: `This function must be called from a UI thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CDataPackageView::UnlockAndAssumeEnterpriseIdentity(
        CDataPackageView *this,
        enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 (__fastcall ***v39)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 (__fastcall ***v45)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v49; // [rsp+20h] [rbp-60h] BYREF
  __int64 v50; // [rsp+28h] [rbp-58h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-50h] BYREF
  HSTRING v52; // [rsp+38h] [rbp-48h] BYREF
  __int64 v53; // [rsp+40h] [rbp-40h] BYREF
  __int64 v54; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v49 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Security.EnterpriseData.ProtectionPolicyManager",
         0x37u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x1800505A1LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_c0bffc66_8c3d_4d56_8804_c68f0ad32ec5, &v49);
  v8 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v50 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 96LL))(v49, &v50);
    v8 = v10;
    if ( v10 >= 0 )
    {
      if ( v50 )
      {
        v51 = 0;
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)this + 16) + 48LL))(
                *((_QWORD *)this + 16),
                &v51);
        v8 = v15;
        if ( v15 >= 0 )
        {
          v53 = 0;
          v19 = (**v51)(v51, &GUID_db764ce5_d174_495c_84fc_1a51f6ab45d7, &v53);
          v8 = v19;
          if ( v19 >= 0 )
          {
            v52 = 0;
            v24 = v53;
            v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v53 + 48LL);
            WindowsDeleteString(0);
            v52 = 0;
            v26 = v25(v24, &v52);
            v8 = v26;
            if ( v26 >= 0 )
            {
              if ( WindowsGetStringLen(v52)
                && (v31 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v50 + 48LL))(v50, v52),
                    v8 = v31,
                    v31 < 0) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x13AC,
                  (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
                  (const char *)(unsigned int)v31,
                  v49);
                WindowsDeleteString(v52);
                v52 = 0;
                v32 = v53;
                if ( v53 )
                {
                  v53 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                }
                v33 = v51;
                if ( v51 )
                {
                  v51 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v33)[2])(v33);
                }
                v34 = v50;
                if ( v50 )
                {
                  v50 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
                v35 = v49;
                if ( v49 )
                {
                  v49 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                }
              }
              else
              {
                v54 = 0;
                v36 = CDataPackageView::RequestAccessWithEnterpriseIdAsync(this, 0, &v54);
                v8 = v36;
                if ( v36 >= 0 )
                {
                  v42 = v54;
                  v8 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>(v54);
                  if ( v8 < 0
                    || (v8 = (*(__int64 (__fastcall **)(__int64, enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *))(*(_QWORD *)v42 + 64LL))(
                               v42,
                               a2),
                        v8 < 0) )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x13B2,
                      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
                      (const char *)(unsigned int)v8,
                      v49);
                  }
                  v43 = v54;
                  if ( v54 )
                  {
                    v54 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                  }
                  WindowsDeleteString(v52);
                  v52 = 0;
                  v44 = v53;
                  if ( v53 )
                  {
                    v53 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                  }
                  v45 = v51;
                  if ( v51 )
                  {
                    v51 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v45)[2])(v45);
                  }
                  v46 = v50;
                  if ( v50 )
                  {
                    v50 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                  }
                  v47 = v49;
                  if ( v49 )
                  {
                    v49 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x13B0,
                    (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
                    (const char *)(unsigned int)v36,
                    v49);
                  v37 = v54;
                  if ( v54 )
                  {
                    v54 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                  }
                  WindowsDeleteString(v52);
                  v52 = 0;
                  v38 = v53;
                  if ( v53 )
                  {
                    v53 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                  }
                  v39 = v51;
                  if ( v51 )
                  {
                    v51 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v39)[2])(v39);
                  }
                  v40 = v50;
                  if ( v50 )
                  {
                    v50 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                  }
                  v41 = v49;
                  if ( v49 )
                  {
                    v49 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x13A8,
                (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
                (const char *)(unsigned int)v26,
                v49);
              WindowsDeleteString(v52);
              v52 = 0;
              v27 = v53;
              if ( v53 )
              {
                v53 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              }
              v28 = v51;
              if ( v51 )
              {
                v51 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v28)[2])(v28);
              }
              v29 = v50;
              if ( v50 )
              {
                v50 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              }
              v30 = v49;
              if ( v49 )
              {
                v49 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13A5,
              (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
              (const char *)(unsigned int)v19,
              v49);
            v20 = v53;
            if ( v53 )
            {
              v53 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
            v21 = v51;
            if ( v51 )
            {
              v51 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v21)[2])(v21);
            }
            v22 = v50;
            if ( v50 )
            {
              v50 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            v23 = v49;
            if ( v49 )
            {
              v49 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13A2,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v15,
            v49);
          v16 = v51;
          if ( v51 )
          {
            v51 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
          }
          v17 = v50;
          if ( v50 )
          {
            v50 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
          v18 = v49;
          if ( v49 )
          {
            v49 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
        }
      }
      else
      {
        if ( WindowsCreateStringReference(
               L"This function must be called from a UI thread",
               0x2Du,
               (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
               (HSTRING *)&hstringHeader) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v8 = -2147019873;
        RoOriginateError(2147947423LL, hstringHeader.Reserved.Reserved1);
        v13 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v14 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1399,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v10,
        v49);
      v11 = v50;
      if ( v50 )
      {
        v50 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1396,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v49);
    v9 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004ff50  mov     [rsp-28h+arg_10], rbx
0x18004ff55  push    rbp
0x18004ff56  push    rsi
0x18004ff57  push    rdi
0x18004ff58  push    r14
0x18004ff5a  push    r15
0x18004ff5c  mov     rbp, rsp
0x18004ff5f  sub     rsp, 80h
0x18004ff66  mov     rax, cs:__security_cookie
0x18004ff6d  xor     rax, rsp
0x18004ff70  mov     [rbp+var_10], rax
0x18004ff74  mov     r14, rdx
0x18004ff77  mov     rsi, rcx
0x18004ff7a  xor     r15d, r15d
0x18004ff7d  mov     [rbp+var_60], r15
0x18004ff81  mov     [rbp+string], r15
0x18004ff85  lea     r9, [rbp+string]; string
0x18004ff89  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004ff8d  lea     edx, [r15+37h]; length
0x18004ff91  lea     rcx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x18004ff98  call    cs:__imp_WindowsCreateStringReference
0x18004ff9e  test    eax, eax
0x18004ffa0  js      loc_18005059A
0x18004ffa6  mov     rbx, [rbp+string]
0x18004ffaa  mov     rcx, [rbp+var_60]
0x18004ffae  test    rcx, rcx
0x18004ffb1  jz      short loc_18004FFC4
0x18004ffb3  mov     [rbp+var_60], r15
0x18004ffb7  mov     rax, [rcx]
0x18004ffba  mov     rax, [rax+10h]
0x18004ffbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffc3  nop
0x18004ffc4  lea     r8, [rbp+var_60]
0x18004ffc8  lea     rdx, _GUID_c0bffc66_8c3d_4d56_8804_c68f0ad32ec5
0x18004ffcf  mov     rcx, rbx
0x18004ffd2  call    cs:__imp_RoGetActivationFactory
0x18004ffd8  mov     ebx, eax
0x18004ffda  test    eax, eax
0x18004ffdc  jns     short loc_180050016
0x18004ffde  mov     rcx, [rbp+28h]; this
0x18004ffe2  mov     r9d, eax; char *
0x18004ffe5  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18004ffec  mov     edx, 1396h; void *
0x18004fff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fff6  nop
0x18004fff7  mov     rcx, [rbp+var_60]
0x18004fffb  test    rcx, rcx
0x18004fffe  jz      short loc_180050011
0x180050000  mov     [rbp+var_60], r15
0x180050004  mov     rax, [rcx]
0x180050007  mov     rax, [rax+10h]
0x18005000b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050010  nop
0x180050011  jmp     loc_180050575
0x180050016  mov     [rbp+var_58], r15
0x18005001a  mov     rcx, [rbp+var_60]
0x18005001e  mov     rax, [rcx]
0x180050021  lea     rdx, [rbp+var_58]
0x180050025  mov     rax, [rax+60h]
0x180050029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005002e  mov     ebx, eax
0x180050030  test    eax, eax
0x180050032  jns     short loc_180050086
0x180050034  mov     rcx, [rbp+28h]; this
0x180050038  mov     r9d, eax; char *
0x18005003b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180050042  mov     edx, 1399h; void *
0x180050047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005004c  nop
0x18005004d  mov     rcx, [rbp+var_58]
0x180050051  test    rcx, rcx
0x180050054  jz      short loc_180050067
0x180050056  mov     [rbp+var_58], r15
0x18005005a  mov     rax, [rcx]
0x18005005d  mov     rax, [rax+10h]
0x180050061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050066  nop
0x180050067  mov     rcx, [rbp+var_60]
0x18005006b  test    rcx, rcx
0x18005006e  jz      short loc_180050081
0x180050070  mov     [rbp+var_60], r15
0x180050074  mov     rax, [rcx]
0x180050077  mov     rax, [rax+10h]
0x18005007b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050080  nop
0x180050081  jmp     loc_180050575
0x180050086  cmp     [rbp+var_58], r15
0x18005008a  jnz     loc_180050111
0x180050090  lea     r9, [rbp+hstringHeader]; string
0x180050094  lea     r8, [rbp+hstringHeader.Reserved+8]; hstringHeader
0x180050098  mov     edx, 2Dh ; '-'; length
0x18005009d  lea     rcx, aThisFunctionMu; "This function must be called from a UI "...
0x1800500a4  call    cs:__imp_WindowsCreateStringReference
0x1800500aa  test    eax, eax
0x1800500ac  jns     short loc_1800500C3
0x1800500ae  xor     r9d, r9d; lpArguments
0x1800500b1  xor     r8d, r8d; nNumberOfArguments
0x1800500b4  lea     edx, [r9+1]; dwExceptionFlags
0x1800500b8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800500bd  call    cs:__imp_RaiseException
0x1800500c3  mov     rdx, qword ptr [rbp+hstringHeader.Reserved]
0x1800500c7  mov     ebx, 8007139Fh
0x1800500cc  mov     ecx, ebx
0x1800500ce  call    cs:__imp_RoOriginateError
0x1800500d4  nop
0x1800500d5  mov     rcx, [rbp+var_58]
0x1800500d9  test    rcx, rcx
0x1800500dc  jz      short loc_1800500EF
0x1800500de  mov     [rbp+var_58], r15
0x1800500e2  mov     rax, [rcx]
0x1800500e5  mov     rax, [rax+10h]
0x1800500e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500ee  nop
0x1800500ef  mov     rdx, [rbp+var_60]
0x1800500f3  test    rdx, rdx
0x1800500f6  jz      short loc_18005010C
0x1800500f8  mov     [rbp+var_60], r15
0x1800500fc  mov     rcx, [rdx]
0x1800500ff  mov     rax, [rcx+10h]
0x180050103  mov     rcx, rdx
0x180050106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005010b  nop
0x18005010c  jmp     loc_180050575
0x180050111  mov     [rbp+var_50], r15
0x180050115  mov     rcx, [rsi+80h]
0x18005011c  mov     rax, [rcx]
0x18005011f  lea     rdx, [rbp+var_50]
0x180050123  mov     rax, [rax+30h]
0x180050127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005012c  mov     ebx, eax
0x18005012e  test    eax, eax
0x180050130  jns     short loc_18005019E
0x180050132  mov     rcx, [rbp+28h]; this
0x180050136  mov     r9d, eax; char *
0x180050139  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180050140  mov     edx, 13A2h; void *
0x180050145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005014a  nop
0x18005014b  mov     rcx, [rbp+var_50]
0x18005014f  test    rcx, rcx
0x180050152  jz      short loc_180050165
0x180050154  mov     [rbp+var_50], r15
0x180050158  mov     rax, [rcx]
0x18005015b  mov     rax, [rax+10h]
0x18005015f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050164  nop
0x180050165  mov     rcx, [rbp+var_58]
0x180050169  test    rcx, rcx
0x18005016c  jz      short loc_18005017F
0x18005016e  mov     [rbp+var_58], r15
0x180050172  mov     rax, [rcx]
0x180050175  mov     rax, [rax+10h]
0x180050179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005017e  nop
0x18005017f  mov     rcx, [rbp+var_60]
0x180050183  test    rcx, rcx
0x180050186  jz      short loc_180050199
0x180050188  mov     [rbp+var_60], r15
0x18005018c  mov     rax, [rcx]
0x18005018f  mov     rax, [rax+10h]
0x180050193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050198  nop
0x180050199  jmp     loc_180050575
0x18005019e  mov     [rbp+var_40], r15
0x1800501a2  mov     rcx, [rbp+var_50]
0x1800501a6  mov     rax, [rcx]
0x1800501a9  lea     r8, [rbp+var_40]
0x1800501ad  lea     rdx, _GUID_db764ce5_d174_495c_84fc_1a51f6ab45d7
0x1800501b4  mov     rax, [rax]
0x1800501b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501bc  mov     ebx, eax
0x1800501be  test    eax, eax
0x1800501c0  jns     loc_18005024C
0x1800501c6  mov     rcx, [rbp+28h]; this
0x1800501ca  mov     r9d, eax; char *
0x1800501cd  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800501d4  mov     edx, 13A5h; void *
0x1800501d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800501de  nop
0x1800501df  mov     rcx, [rbp+var_40]
0x1800501e3  test    rcx, rcx
0x1800501e6  jz      short loc_1800501F9
0x1800501e8  mov     [rbp+var_40], r15
0x1800501ec  mov     rax, [rcx]
0x1800501ef  mov     rax, [rax+10h]
0x1800501f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501f8  nop
0x1800501f9  mov     rcx, [rbp+var_50]
0x1800501fd  test    rcx, rcx
0x180050200  jz      short loc_180050213
0x180050202  mov     [rbp+var_50], r15
0x180050206  mov     rax, [rcx]
0x180050209  mov     rax, [rax+10h]
0x18005020d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050212  nop
0x180050213  mov     rcx, [rbp+var_58]
0x180050217  test    rcx, rcx
0x18005021a  jz      short loc_18005022D
0x18005021c  mov     [rbp+var_58], r15
0x180050220  mov     rax, [rcx]
0x180050223  mov     rax, [rax+10h]
0x180050227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005022c  nop
0x18005022d  mov     rcx, [rbp+var_60]
0x180050231  test    rcx, rcx
0x180050234  jz      short loc_180050247
0x180050236  mov     [rbp+var_60], r15
0x18005023a  mov     rax, [rcx]
0x18005023d  mov     rax, [rax+10h]
0x180050241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050246  nop
0x180050247  jmp     loc_180050575
0x18005024c  mov     [rbp+var_48], r15
0x180050250  mov     rdi, [rbp+var_40]
0x180050254  mov     rax, [rdi]
0x180050257  mov     rbx, [rax+30h]
0x18005025b  xor     ecx, ecx; string
0x18005025d  call    cs:__imp_WindowsDeleteString
0x180050263  mov     [rbp+var_48], r15
0x180050267  lea     rdx, [rbp+var_48]
0x18005026b  mov     rcx, rdi
0x18005026e  mov     rax, rbx
0x180050271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050276  mov     ebx, eax
0x180050278  test    eax, eax
0x18005027a  jns     loc_180050314
0x180050280  mov     rcx, [rbp+28h]; this
0x180050284  mov     r9d, eax; char *
0x180050287  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18005028e  mov     edx, 13A8h; void *
0x180050293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050298  nop
0x180050299  mov     rcx, [rbp+var_48]; string
0x18005029d  call    cs:__imp_WindowsDeleteString
0x1800502a3  mov     [rbp+var_48], r15
0x1800502a7  mov     rcx, [rbp+var_40]
0x1800502ab  test    rcx, rcx
0x1800502ae  jz      short loc_1800502C1
0x1800502b0  mov     [rbp+var_40], r15
0x1800502b4  mov     rax, [rcx]
0x1800502b7  mov     rax, [rax+10h]
0x1800502bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502c0  nop
0x1800502c1  mov     rcx, [rbp+var_50]
0x1800502c5  test    rcx, rcx
0x1800502c8  jz      short loc_1800502DB
0x1800502ca  mov     [rbp+var_50], r15
0x1800502ce  mov     rax, [rcx]
0x1800502d1  mov     rax, [rax+10h]
0x1800502d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502da  nop
0x1800502db  mov     rcx, [rbp+var_58]
0x1800502df  test    rcx, rcx
0x1800502e2  jz      short loc_1800502F5
0x1800502e4  mov     [rbp+var_58], r15
0x1800502e8  mov     rax, [rcx]
0x1800502eb  mov     rax, [rax+10h]
0x1800502ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502f4  nop
0x1800502f5  mov     rcx, [rbp+var_60]
0x1800502f9  test    rcx, rcx
0x1800502fc  jz      short loc_18005030F
0x1800502fe  mov     [rbp+var_60], r15
0x180050302  mov     rax, [rcx]
0x180050305  mov     rax, [rax+10h]
0x180050309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005030e  nop
0x18005030f  jmp     loc_180050575
0x180050314  mov     rcx, [rbp+var_48]; string
0x180050318  call    cs:__imp_WindowsGetStringLen
0x18005031e  test    eax, eax
0x180050320  jz      loc_1800503D8
0x180050326  mov     rcx, [rbp+var_58]
0x18005032a  mov     rax, [rcx]
0x18005032d  mov     rdx, [rbp+var_48]
0x180050331  mov     rax, [rax+30h]
0x180050335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005033a  mov     ebx, eax
0x18005033c  test    eax, eax
0x18005033e  jns     loc_1800503D8
0x180050344  mov     rcx, [rbp+28h]; this
0x180050348  mov     r9d, eax; char *
0x18005034b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180050352  mov     edx, 13ACh; void *
0x180050357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005035c  nop
0x18005035d  mov     rcx, [rbp+var_48]; string
0x180050361  call    cs:__imp_WindowsDeleteString
0x180050367  mov     [rbp+var_48], r15
0x18005036b  mov     rcx, [rbp+var_40]
0x18005036f  test    rcx, rcx
0x180050372  jz      short loc_180050385
0x180050374  mov     [rbp+var_40], r15
0x180050378  mov     rax, [rcx]
0x18005037b  mov     rax, [rax+10h]
0x18005037f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050384  nop
0x180050385  mov     rcx, [rbp+var_50]
0x180050389  test    rcx, rcx
0x18005038c  jz      short loc_18005039F
  ... truncated ...
```
