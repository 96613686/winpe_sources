# CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession(_TS_SESSION_INFORMATION_0 *,ulong *)

- ea: `0x180078bd0`
- end: `0x180078e4d`
- name: `?Sessions_SendRequestToSession@CDefaultSessionArbitrationHelper@@UEAAJPEAU_TS_SESSION_INFORMATION_0@@PEAK@Z`
- size: `637`
- prototype: `__int64 __fastcall(CDefaultSessionArbitrationHelper *__hidden this, struct _TS_SESSION_INFORMATION_0 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a210`
- `0x180013150`
- `0x180014a2c`
- `0x180015ab0`
- `0x180077c18`
- `0x180078bd0`
- `0x1800c8010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180078d8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180078d8d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180078d43`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180078d43`
- `OLEAUT32!__imp_SysFreeString` at `0x180078e27`
- `OLEAUT32!__imp_SysFreeString` at `0x180078e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078e19`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession(
        CDefaultSessionArbitrationHelper *this,
        struct _TS_SESSION_INFORMATION_0 *a2,
        unsigned int *a3)
{
  unsigned __int16 *v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // r11
  __int64 v17; // rbx
  int v18; // eax
  CDefaultSessionArbitrationHelper *v19; // rcx
  int RequestDialogObject; // eax
  int v21; // eax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  void *v24; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-8h] BYREF
  int v27; // [rsp+80h] [rbp+30h] BYREF
  int v28; // [rsp+90h] [rbp+40h] BYREF
  OLECHAR *psz; // [rsp+98h] [rbp+48h] BYREF

  psz = 0;
  pv = 0;
  v26 = 0;
  v25 = 0;
  v6 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  *a3 = 7;
  v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 200) + 104LL))(*((_QWORD *)this + 200), &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    _DbgPrintMessage(
      8,
      "pUserName->IsConnectedUser failed: 0x%x in %s",
      (unsigned int)v7,
      "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
    goto LABEL_30;
  }
  v9 = (__int64 *)*((_QWORD *)this + 200);
  v10 = *v9;
  if ( v28 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR **))(v10 + 56))(v9, &psz);
    v8 = v11;
    if ( v11 < 0 )
    {
      _DbgPrintMessage(
        8,
        "m_ptrUserName->GetInternetPrincipalStr failed: 0x%x in %s",
        (unsigned int)v11,
        "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
      goto LABEL_30;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 200) + 64LL))(*((_QWORD *)this + 200), &pv);
    v8 = v12;
    if ( v12 < 0 )
    {
      _DbgPrintMessage(
        8,
        "m_ptrUserName->GetInternetProviderStr failed: 0x%x in %s",
        (unsigned int)v12,
        "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
      goto LABEL_30;
    }
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR **))(v10 + 40))(v9, &psz);
    v8 = v13;
    if ( v13 < 0 )
    {
      _DbgPrintMessage(
        8,
        "m_ptrUserName->GetUserStr failed: 0x%x in %s",
        (unsigned int)v13,
        "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
      goto LABEL_30;
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 200) + 48LL))(*((_QWORD *)this + 200), &pv);
    v8 = v14;
    if ( v14 < 0 )
    {
      _DbgPrintMessage(
        8,
        "m_ptrUserName->GetDomainStr failed: 0x%x in %s",
        (unsigned int)v14,
        "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
      goto LABEL_30;
    }
  }
  v15 = StringCchLengthW((const unsigned __int16 *)pv, 0x105u, &v25);
  v8 = v15;
  if ( v15 < 0 )
  {
LABEL_14:
    _DbgPrintMessage(
      8,
      "StringCchLength failed: 0x%x in %s",
      (unsigned int)v15,
      "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
    goto LABEL_30;
  }
  if ( v25 )
  {
    v15 = StringCchLengthW(psz, 0x105u, &v26);
    v8 = v15;
    if ( v15 < 0 )
      goto LABEL_14;
    v17 = v16 + v26;
    v6 = SysAllocStringLen(0, (int)v16 + (int)v26 + 3);
    if ( !v6 )
    {
LABEL_18:
      v8 = -2147024882;
      goto LABEL_30;
    }
    v18 = StringCchPrintfW(v6, v17 + 3, L"%s\\%s", pv, psz);
    v8 = v18;
    if ( v18 < 0 )
    {
      _DbgPrintMessage(
        8,
        "StringCchPrintf failed: 0x%x in %s",
        (unsigned int)v18,
        "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
      goto LABEL_30;
    }
  }
  else
  {
    v6 = SysAllocString(psz);
    if ( !v6 )
      goto LABEL_18;
  }
  RequestDialogObject = CDefaultSessionArbitrationHelper::GetRequestDialogObject(v19, *(_DWORD *)a2, &v24);
  v8 = RequestDialogObject;
  if ( RequestDialogObject >= 0 )
  {
    v21 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, int *))(*(_QWORD *)v24 + 24LL))(v24, v6, &v27);
    v8 = v21;
    if ( v21 >= 0 )
    {
      if ( v27 == 1 || v27 == 32000 )
        *a3 = 6;
      else
        *a3 = 7;
    }
    else
    {
      _DbgPrintMessage(
        8,
        "ptrRequestDialog->ShowBumpDialog failed: 0x%x in %s",
        (unsigned int)v21,
        "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "GetRequestDialogObject failed: 0x%x in %s",
      (unsigned int)RequestDialogObject,
      "CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession");
  }
LABEL_30:
  if ( psz )
    CoTaskMemFree(psz);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v6 )
    SysFreeString(v6);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v24);
  return v8;
}

```

## disassembly

```asm
0x180078bd0  mov     [rsp-28h+arg_8], rbx
0x180078bd5  push    rbp
0x180078bd6  push    rsi
0x180078bd7  push    rdi
0x180078bd8  push    r14
0x180078bda  push    r15
0x180078bdc  mov     rbp, rsp
0x180078bdf  sub     rsp, 50h
0x180078be3  mov     r14, r8
0x180078be6  mov     r15, rdx
0x180078be9  mov     rsi, rcx
0x180078bec  mov     [rbp+psz], 0
0x180078bf4  mov     [rbp+pv], 0
0x180078bfc  mov     [rbp+var_8], 0
0x180078c04  mov     [rbp+var_10], 0
0x180078c0c  xor     edi, edi
0x180078c0e  mov     [rbp+var_18], rdi
0x180078c12  mov     [rbp+arg_0], edi
0x180078c15  mov     [rbp+arg_10], edi
0x180078c18  mov     dword ptr [r8], 7
0x180078c1f  mov     rcx, [rcx+640h]
0x180078c26  mov     rax, [rcx]
0x180078c29  lea     rdx, [rbp+arg_10]
0x180078c2d  mov     rax, [rax+68h]
0x180078c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c36  mov     ebx, eax
0x180078c38  test    eax, eax
0x180078c3a  jns     short loc_180078C5C
0x180078c3c  lea     rdx, aPusernameIscon; "pUserName->IsConnectedUser failed: 0x%x"...
0x180078c43  lea     r9, aCdefaultsessio_4; "CDefaultSessionArbitrationHelper::Sessi"...
0x180078c4a  mov     r8d, eax
0x180078c4d  mov     ecx, 8; int
0x180078c52  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180078c57  jmp     loc_180078E01
0x180078c5c  mov     rcx, [rsi+640h]
0x180078c63  mov     rax, [rcx]
0x180078c66  lea     rdx, [rbp+psz]
0x180078c6a  cmp     [rbp+arg_10], 0
0x180078c6e  jz      short loc_180078CAE
0x180078c70  mov     rax, [rax+38h]
0x180078c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c79  mov     ebx, eax
0x180078c7b  test    eax, eax
0x180078c7d  jns     short loc_180078C88
0x180078c7f  lea     rdx, aMPtrusernameGe; "m_ptrUserName->GetInternetPrincipalStr "...
0x180078c86  jmp     short loc_180078C43
0x180078c88  mov     rcx, [rsi+640h]
0x180078c8f  mov     rax, [rcx]
0x180078c92  lea     rdx, [rbp+pv]
0x180078c96  mov     rax, [rax+40h]
0x180078c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c9f  mov     ebx, eax
0x180078ca1  test    eax, eax
0x180078ca3  jns     short loc_180078CF2
0x180078ca5  lea     rdx, aMPtrusernameGe_0; "m_ptrUserName->GetInternetProviderStr f"...
0x180078cac  jmp     short loc_180078C43
0x180078cae  mov     rax, [rax+28h]
0x180078cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cb7  mov     ebx, eax
0x180078cb9  test    eax, eax
0x180078cbb  jns     short loc_180078CC9
0x180078cbd  lea     rdx, aMPtrusernameGe_1; "m_ptrUserName->GetUserStr failed: 0x%x "...
0x180078cc4  jmp     loc_180078C43
0x180078cc9  mov     rcx, [rsi+640h]
0x180078cd0  mov     rax, [rcx]
0x180078cd3  lea     rdx, [rbp+pv]
0x180078cd7  mov     rax, [rax+30h]
0x180078cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ce0  mov     ebx, eax
0x180078ce2  test    eax, eax
0x180078ce4  jns     short loc_180078CF2
0x180078ce6  lea     rdx, aMPtrusernameGe_3; "m_ptrUserName->GetDomainStr failed: 0x%"...
0x180078ced  jmp     loc_180078C43
0x180078cf2  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180078cf6  mov     esi, 105h
0x180078cfb  mov     edx, esi; unsigned __int64
0x180078cfd  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180078d01  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180078d06  mov     ebx, eax
0x180078d08  test    eax, eax
0x180078d0a  jns     short loc_180078D18
0x180078d0c  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x180078d13  jmp     loc_180078C43
0x180078d18  mov     r11, [rbp+var_10]
0x180078d1c  mov     rcx, [rbp+psz]; unsigned __int16 *
0x180078d20  test    r11, r11
0x180078d23  jz      short loc_180078D8D
0x180078d25  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180078d29  mov     rdx, rsi; unsigned __int64
0x180078d2c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180078d31  mov     ebx, eax
0x180078d33  test    eax, eax
0x180078d35  js      short loc_180078D0C
0x180078d37  mov     rbx, [rbp+var_8]
0x180078d3b  add     rbx, r11
0x180078d3e  lea     edx, [rbx+3]; ui
0x180078d41  xor     ecx, ecx; strIn
0x180078d43  call    cs:__imp_SysAllocStringLen
0x180078d49  mov     rdi, rax
0x180078d4c  test    rax, rax
0x180078d4f  jnz     short loc_180078D5B
0x180078d51  mov     ebx, 8007000Eh
0x180078d56  jmp     loc_180078E01
0x180078d5b  mov     rax, [rbp+psz]
0x180078d5f  mov     [rsp+50h+var_30], rax
0x180078d64  mov     r9, [rbp+pv]
0x180078d68  lea     r8, aSS_0; "%s\\%s"
0x180078d6f  lea     rdx, [rbx+3]; unsigned __int64
0x180078d73  mov     rcx, rdi; unsigned __int16 *
0x180078d76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078d7b  mov     ebx, eax
0x180078d7d  test    eax, eax
0x180078d7f  jns     short loc_180078D9B
0x180078d81  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x180078d88  jmp     loc_180078C43
0x180078d8d  call    cs:__imp_SysAllocString
0x180078d93  mov     rdi, rax
0x180078d96  test    rax, rax
0x180078d99  jz      short loc_180078D51
0x180078d9b  lea     r8, [rbp+var_18]; void **
0x180078d9f  mov     edx, [r15]; int
0x180078da2  call    ?GetRequestDialogObject@CDefaultSessionArbitrationHelper@@AEAAJJPEAPEAX@Z; CDefaultSessionArbitrationHelper::GetRequestDialogObject(long,void * *)
0x180078da7  mov     ebx, eax
0x180078da9  test    eax, eax
0x180078dab  jns     short loc_180078DB9
0x180078dad  lea     rdx, aGetrequestdial; "GetRequestDialogObject failed: 0x%x in "...
0x180078db4  jmp     loc_180078C43
0x180078db9  mov     rcx, [rbp+var_18]
0x180078dbd  mov     rax, [rcx]
0x180078dc0  lea     r8, [rbp+arg_0]
0x180078dc4  mov     rdx, rdi
0x180078dc7  mov     rax, [rax+18h]
0x180078dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078dd0  mov     ebx, eax
0x180078dd2  test    eax, eax
0x180078dd4  jns     short loc_180078DE2
0x180078dd6  lea     rdx, aPtrrequestdial; "ptrRequestDialog->ShowBumpDialog failed"...
0x180078ddd  jmp     loc_180078C43
0x180078de2  cmp     [rbp+arg_0], 1
0x180078de6  jz      short loc_180078DFA
0x180078de8  cmp     [rbp+arg_0], 7D00h
0x180078def  jz      short loc_180078DFA
0x180078df1  mov     dword ptr [r14], 7
0x180078df8  jmp     short loc_180078E01
0x180078dfa  mov     dword ptr [r14], 6
0x180078e01  mov     rcx, [rbp+psz]; pv
0x180078e05  test    rcx, rcx
0x180078e08  jz      short loc_180078E10
0x180078e0a  call    cs:__imp_CoTaskMemFree
0x180078e10  mov     rcx, [rbp+pv]; pv
0x180078e14  test    rcx, rcx
0x180078e17  jz      short loc_180078E1F
0x180078e19  call    cs:__imp_CoTaskMemFree
0x180078e1f  test    rdi, rdi
0x180078e22  jz      short loc_180078E2E
0x180078e24  mov     rcx, rdi; bstrString
0x180078e27  call    cs:__imp_SysFreeString
0x180078e2d  nop
0x180078e2e  lea     rcx, [rbp+var_18]; void *
0x180078e32  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180078e37  mov     eax, ebx
0x180078e39  mov     rbx, [rsp+50h+arg_8]
0x180078e41  add     rsp, 50h
0x180078e45  pop     r15
0x180078e47  pop     r14
0x180078e49  pop     rdi
0x180078e4a  pop     rsi
0x180078e4b  pop     rbp
0x180078e4c  retn
```
