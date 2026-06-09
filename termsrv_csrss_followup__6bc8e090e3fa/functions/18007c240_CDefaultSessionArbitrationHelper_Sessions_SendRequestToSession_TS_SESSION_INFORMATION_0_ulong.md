# CDefaultSessionArbitrationHelper::Sessions_SendRequestToSession(_TS_SESSION_INFORMATION_0 *,ulong *)

- ea: `0x18007c240`
- end: `0x18007c4dc`
- name: `?Sessions_SendRequestToSession@CDefaultSessionArbitrationHelper@@UEAAJPEAU_TS_SESSION_INFORMATION_0@@PEAK@Z`
- size: `668`
- prototype: `__int64 __fastcall(CDefaultSessionArbitrationHelper *__hidden this, struct _TS_SESSION_INFORMATION_0 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x180015044`
- `0x180016558`
- `0x18007b230`
- `0x18007c240`
- `0x1800ce010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007c403`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c403`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18007c3b3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18007c3b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c4af`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c49b`

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
0x18007c240  mov     [rsp-28h+arg_8], rbx
0x18007c245  push    rbp
0x18007c246  push    rsi
0x18007c247  push    rdi
0x18007c248  push    r14
0x18007c24a  push    r15
0x18007c24c  mov     rbp, rsp
0x18007c24f  sub     rsp, 50h
0x18007c253  mov     r14, r8
0x18007c256  mov     r15, rdx
0x18007c259  mov     rsi, rcx
0x18007c25c  mov     [rbp+psz], 0
0x18007c264  mov     [rbp+pv], 0
0x18007c26c  mov     [rbp+var_8], 0
0x18007c274  mov     [rbp+var_10], 0
0x18007c27c  xor     edi, edi
0x18007c27e  mov     [rbp+var_18], rdi
0x18007c282  mov     [rbp+arg_0], edi
0x18007c285  mov     [rbp+arg_10], edi
0x18007c288  mov     dword ptr [r8], 7
0x18007c28f  mov     rcx, [rcx+640h]
0x18007c296  mov     rax, [rcx]
0x18007c299  lea     rdx, [rbp+arg_10]
0x18007c29d  mov     rax, [rax+68h]
0x18007c2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c2a6  mov     ebx, eax
0x18007c2a8  test    eax, eax
0x18007c2aa  jns     short loc_18007C2CC
0x18007c2ac  lea     rdx, aPusernameIscon; "pUserName->IsConnectedUser failed: 0x%x"...
0x18007c2b3  lea     r9, aCdefaultsessio_4; "CDefaultSessionArbitrationHelper::Sessi"...
0x18007c2ba  mov     r8d, eax
0x18007c2bd  mov     ecx, 8; int
0x18007c2c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007c2c7  jmp     loc_18007C47D
0x18007c2cc  mov     rcx, [rsi+640h]
0x18007c2d3  mov     rax, [rcx]
0x18007c2d6  lea     rdx, [rbp+psz]
0x18007c2da  cmp     [rbp+arg_10], 0
0x18007c2de  jz      short loc_18007C31E
0x18007c2e0  mov     rax, [rax+38h]
0x18007c2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c2e9  mov     ebx, eax
0x18007c2eb  test    eax, eax
0x18007c2ed  jns     short loc_18007C2F8
0x18007c2ef  lea     rdx, aMPtrusernameGe; "m_ptrUserName->GetInternetPrincipalStr "...
0x18007c2f6  jmp     short loc_18007C2B3
0x18007c2f8  mov     rcx, [rsi+640h]
0x18007c2ff  mov     rax, [rcx]
0x18007c302  lea     rdx, [rbp+pv]
0x18007c306  mov     rax, [rax+40h]
0x18007c30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c30f  mov     ebx, eax
0x18007c311  test    eax, eax
0x18007c313  jns     short loc_18007C362
0x18007c315  lea     rdx, aMPtrusernameGe_0; "m_ptrUserName->GetInternetProviderStr f"...
0x18007c31c  jmp     short loc_18007C2B3
0x18007c31e  mov     rax, [rax+28h]
0x18007c322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c327  mov     ebx, eax
0x18007c329  test    eax, eax
0x18007c32b  jns     short loc_18007C339
0x18007c32d  lea     rdx, aMPtrusernameGe_1; "m_ptrUserName->GetUserStr failed: 0x%x "...
0x18007c334  jmp     loc_18007C2B3
0x18007c339  mov     rcx, [rsi+640h]
0x18007c340  mov     rax, [rcx]
0x18007c343  lea     rdx, [rbp+pv]
0x18007c347  mov     rax, [rax+30h]
0x18007c34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c350  mov     ebx, eax
0x18007c352  test    eax, eax
0x18007c354  jns     short loc_18007C362
0x18007c356  lea     rdx, aMPtrusernameGe_3; "m_ptrUserName->GetDomainStr failed: 0x%"...
0x18007c35d  jmp     loc_18007C2B3
0x18007c362  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18007c366  mov     esi, 105h
0x18007c36b  mov     edx, esi; unsigned __int64
0x18007c36d  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18007c371  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007c376  mov     ebx, eax
0x18007c378  test    eax, eax
0x18007c37a  jns     short loc_18007C388
0x18007c37c  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18007c383  jmp     loc_18007C2B3
0x18007c388  mov     r11, [rbp+var_10]
0x18007c38c  mov     rcx, [rbp+psz]; unsigned __int16 *
0x18007c390  test    r11, r11
0x18007c393  jz      short loc_18007C403
0x18007c395  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18007c399  mov     rdx, rsi; unsigned __int64
0x18007c39c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007c3a1  mov     ebx, eax
0x18007c3a3  test    eax, eax
0x18007c3a5  js      short loc_18007C37C
0x18007c3a7  mov     rbx, [rbp+var_8]
0x18007c3ab  add     rbx, r11
0x18007c3ae  lea     edx, [rbx+3]; ui
0x18007c3b1  xor     ecx, ecx; strIn
0x18007c3b3  call    cs:__imp_SysAllocStringLen
0x18007c3ba  nop     dword ptr [rax+rax+00h]
0x18007c3bf  mov     rdi, rax
0x18007c3c2  test    rax, rax
0x18007c3c5  jnz     short loc_18007C3D1
0x18007c3c7  mov     ebx, 8007000Eh
0x18007c3cc  jmp     loc_18007C47D
0x18007c3d1  mov     rax, [rbp+psz]
0x18007c3d5  mov     [rsp+50h+var_30], rax
0x18007c3da  mov     r9, [rbp+pv]
0x18007c3de  lea     r8, aSS_0; "%s\\%s"
0x18007c3e5  lea     rdx, [rbx+3]; unsigned __int64
0x18007c3e9  mov     rcx, rdi; unsigned __int16 *
0x18007c3ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c3f1  mov     ebx, eax
0x18007c3f3  test    eax, eax
0x18007c3f5  jns     short loc_18007C417
0x18007c3f7  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18007c3fe  jmp     loc_18007C2B3
0x18007c403  call    cs:__imp_SysAllocString
0x18007c40a  nop     dword ptr [rax+rax+00h]
0x18007c40f  mov     rdi, rax
0x18007c412  test    rax, rax
0x18007c415  jz      short loc_18007C3C7
0x18007c417  lea     r8, [rbp+var_18]; void **
0x18007c41b  mov     edx, [r15]; int
0x18007c41e  call    ?GetRequestDialogObject@CDefaultSessionArbitrationHelper@@AEAAJJPEAPEAX@Z; CDefaultSessionArbitrationHelper::GetRequestDialogObject(long,void * *)
0x18007c423  mov     ebx, eax
0x18007c425  test    eax, eax
0x18007c427  jns     short loc_18007C435
0x18007c429  lea     rdx, aGetrequestdial; "GetRequestDialogObject failed: 0x%x in "...
0x18007c430  jmp     loc_18007C2B3
0x18007c435  mov     rcx, [rbp+var_18]
0x18007c439  mov     rax, [rcx]
0x18007c43c  lea     r8, [rbp+arg_0]
0x18007c440  mov     rdx, rdi
0x18007c443  mov     rax, [rax+18h]
0x18007c447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c44c  mov     ebx, eax
0x18007c44e  test    eax, eax
0x18007c450  jns     short loc_18007C45E
0x18007c452  lea     rdx, aPtrrequestdial; "ptrRequestDialog->ShowBumpDialog failed"...
0x18007c459  jmp     loc_18007C2B3
0x18007c45e  cmp     [rbp+arg_0], 1
0x18007c462  jz      short loc_18007C476
0x18007c464  cmp     [rbp+arg_0], 7D00h
0x18007c46b  jz      short loc_18007C476
0x18007c46d  mov     dword ptr [r14], 7
0x18007c474  jmp     short loc_18007C47D
0x18007c476  mov     dword ptr [r14], 6
0x18007c47d  mov     rcx, [rbp+psz]; pv
0x18007c481  test    rcx, rcx
0x18007c484  jz      short loc_18007C492
0x18007c486  call    cs:__imp_CoTaskMemFree
0x18007c48d  nop     dword ptr [rax+rax+00h]
0x18007c492  mov     rcx, [rbp+pv]; pv
0x18007c496  test    rcx, rcx
0x18007c499  jz      short loc_18007C4A7
0x18007c49b  call    cs:__imp_CoTaskMemFree
0x18007c4a2  nop     dword ptr [rax+rax+00h]
0x18007c4a7  test    rdi, rdi
0x18007c4aa  jz      short loc_18007C4BC
0x18007c4ac  mov     rcx, rdi; bstrString
0x18007c4af  call    cs:__imp_SysFreeString
0x18007c4b6  nop     dword ptr [rax+rax+00h]
0x18007c4bb  nop
0x18007c4bc  lea     rcx, [rbp+var_18]; void *
0x18007c4c0  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18007c4c5  mov     eax, ebx
0x18007c4c7  mov     rbx, [rsp+50h+arg_8]
0x18007c4cf  add     rsp, 50h
0x18007c4d3  pop     r15
0x18007c4d5  pop     r14
0x18007c4d7  pop     rdi
0x18007c4d8  pop     rsi
0x18007c4d9  pop     rbp
0x18007c4da  retn
```
