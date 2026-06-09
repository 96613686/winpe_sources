# CArchiveItemDataObject::ComputeEnterpriseId(void)

- ea: `0x180032270`
- end: `0x180032478`
- name: `?ComputeEnterpriseId@CArchiveItemDataObject@@AEAAJXZ`
- size: `520`
- prototype: `__int64 __fastcall(CArchiveItemDataObject *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043aa0`

## callees

- `0x180014bf0`
- `0x180031e94`
- `0x180032270`
- `0x180032480`
- `0x1800324b8`
- `0x180036f50`
- `0x180039148`
- `0x180039bc8`
- `0x180043090`

## import_xrefs

- `PROPSYS!VariantToStringArrayAlloc` at `0x18003232d`
- `PROPSYS!VariantToStringArrayAlloc` at `0x18003232d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800323d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800323e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800323d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800323e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032435`
- `OLEAUT32!__imp_VariantClear` at `0x180032355`
- `OLEAUT32!__imp_VariantClear` at `0x1800323f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003243f`
- `OLEAUT32!__imp_VariantClear` at `0x180032355`
- `OLEAUT32!__imp_VariantClear` at `0x1800323f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003243f`

## pseudocode

```c
__int64 __fastcall CArchiveItemDataObject::ComputeEnterpriseId(
        CArchiveItemDataObject *this,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  __int64 *v5; // rax
  CZipFolder *v6; // rcx
  __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  HRESULT v10; // eax
  ULONG v11; // eax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rdi
  PWSTR *v14; // rsi
  PWSTR *v16; // rsi
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r14
  LPVOID pv; // [rsp+20h] [rbp-40h] BYREF
  __int64 v20; // [rsp+28h] [rbp-38h] BYREF
  PWSTR *pprgsz; // [rsp+30h] [rbp-30h] BYREF
  ULONG pcElem; // [rsp+38h] [rbp-28h] BYREF
  VARIANT var; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !*((_QWORD *)this + 81) )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xAF3, a3, a4);
  v20 = *((_QWORD *)this + 81);
  v5 = (__int64 *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                    &pv,
                    this);
  v6 = (CZipFolder *)*((_QWORD *)this + 6);
  v7 = *v5;
  memset(&var, 0, sizeof(var));
  v8 = CZipFolder::ComputePKEYFromParent(v6, &PKEY_Security_EncryptionOwners, &var);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"shell\\ext\\zip\\idataobj.cpp",
      (const char *)(unsigned int)v8,
      (int)pv);
LABEL_15:
    *(_BYTE *)(v7 + 656) = 1;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return v9;
  }
  if ( var.lVal )
  {
    pprgsz = 0;
    pcElem = 0;
    v10 = VariantToStringArrayAlloc(&var, &pprgsz, &pcElem);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"shell\\ext\\zip\\idataobj.cpp",
        (const char *)(unsigned int)v10,
        (int)pv);
      VariantClear(&var);
      goto LABEL_15;
    }
    v11 = pcElem;
    if ( pcElem )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        *pprgsz,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)this + 640,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
      if ( !*((_QWORD *)this + 80) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"shell\\ext\\zip\\idataobj.cpp",
          (const char *)0x8007000ELL,
          (int)pv);
        v12 = pcElem;
        v13 = 0;
        v14 = pprgsz;
        while ( v13 < v12 )
          CoTaskMemFree(v14[v13++]);
        CoTaskMemFree(v14);
        VariantClear(&var);
        v9 = -2147024882;
        goto LABEL_15;
      }
      v11 = pcElem;
    }
    v16 = pprgsz;
    v17 = 0;
    v18 = v11;
    while ( v17 < v18 )
      CoTaskMemFree(v16[v17++]);
    CoTaskMemFree(v16);
  }
  VariantClear(&var);
  *(_BYTE *)(v7 + 656) = 1;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return 0;
}

```

## disassembly

```asm
0x180032270  mov     [rsp-18h+arg_8], rbx
0x180032275  mov     [rsp-18h+arg_10], rsi
0x18003227a  push    rbp
0x18003227b  push    rdi
0x18003227c  push    r14
0x18003227e  mov     rbp, rsp
0x180032281  sub     rsp, 60h
0x180032285  mov     rax, cs:__security_cookie
0x18003228c  xor     rax, rsp
0x18003228f  mov     [rbp+var_8], rax
0x180032293  mov     rax, [rcx+288h]
0x18003229a  mov     rsi, rcx
0x18003229d  test    rax, rax
0x1800322a0  jnz     short loc_1800322B1
0x1800322a2  mov     rcx, [rbp+18h]; this
0x1800322a6  mov     edx, 0AF3h; void *
0x1800322ab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800322b1  mov     rdx, rsi
0x1800322b4  mov     [rbp+var_38], rax
0x1800322b8  lea     rcx, [rbp+pv]
0x1800322bc  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800322c1  mov     rcx, [rsi+30h]; this
0x1800322c5  lea     r8, [rbp+var]; struct tagVARIANT *
0x1800322c9  xorps   xmm0, xmm0
0x1800322cc  lea     rdx, PKEY_Security_EncryptionOwners; struct _tagpropertykey *
0x1800322d3  mov     rbx, [rax]
0x1800322d6  xor     eax, eax
0x1800322d8  mov     qword ptr [rbp+var+10h], rax
0x1800322dc  movups  xmmword ptr [rbp+var], xmm0
0x1800322e0  call    ?ComputePKEYFromParent@CZipFolder@@QEAAJAEBU_tagpropertykey@@PEAUtagVARIANT@@@Z; CZipFolder::ComputePKEYFromParent(_tagpropertykey const &,tagVARIANT *)
0x1800322e5  mov     edi, eax
0x1800322e7  test    eax, eax
0x1800322e9  jns     short loc_180032308
0x1800322eb  mov     rcx, [rbp+18h]; this
0x1800322ef  lea     r8, aShellExtZipIda; "shell\\ext\\zip\\idataobj.cpp"
0x1800322f6  mov     r9d, eax; char *
0x1800322f9  mov     edx, 10Ch; void *
0x1800322fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032303  jmp     loc_1800323FC
0x180032308  cmp     dword ptr [rbp+var+8], 0
0x18003230c  jz      loc_18003243B
0x180032312  lea     r8, [rbp+pcElem]; pcElem
0x180032316  mov     [rbp+pprgsz], 0
0x18003231e  lea     rdx, [rbp+pprgsz]; pprgsz
0x180032322  mov     [rbp+pcElem], 0
0x180032329  lea     rcx, [rbp+var]; var
0x18003232d  call    cs:__imp_VariantToStringArrayAlloc
0x180032333  mov     edi, eax
0x180032335  test    eax, eax
0x180032337  jns     short loc_180032360
0x180032339  mov     rcx, [rbp+18h]; this
0x18003233d  lea     r8, aShellExtZipIda; "shell\\ext\\zip\\idataobj.cpp"
0x180032344  mov     r9d, eax; char *
0x180032347  mov     edx, 118h; void *
0x18003234c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032351  lea     rcx, [rbp+var]; pvarg
0x180032355  call    cs:__imp_VariantClear
0x18003235b  jmp     loc_1800323FC
0x180032360  mov     eax, [rbp+pcElem]
0x180032363  test    eax, eax
0x180032365  jz      loc_180032413
0x18003236b  mov     rdx, [rbp+pprgsz]
0x18003236f  lea     rcx, [rbp+pv]
0x180032373  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032377  mov     rdx, [rdx]
0x18003237a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003237f  lea     rdx, [rbp+pv]
0x180032383  lea     rcx, [rsi+280h]
0x18003238a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003238f  mov     rcx, [rbp+pv]; pv
0x180032393  test    rcx, rcx
0x180032396  jz      short loc_18003239E
0x180032398  call    cs:__imp_CoTaskMemFree
0x18003239e  cmp     qword ptr [rsi+280h], 0
0x1800323a6  jnz     short loc_180032410
0x1800323a8  mov     rcx, [rbp+18h]; this
0x1800323ac  lea     r8, aShellExtZipIda; "shell\\ext\\zip\\idataobj.cpp"
0x1800323b3  mov     r9d, 8007000Eh; char *
0x1800323b9  mov     edx, 122h; void *
0x1800323be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800323c3  mov     r14d, [rbp+pcElem]
0x1800323c7  xor     edi, edi
0x1800323c9  mov     rsi, [rbp+pprgsz]
0x1800323cd  test    r14, r14
0x1800323d0  jz      short loc_1800323E4
0x1800323d2  mov     rcx, [rsi+rdi*8]; pv
0x1800323d6  call    cs:__imp_CoTaskMemFree
0x1800323dc  inc     rdi
0x1800323df  cmp     rdi, r14
0x1800323e2  jb      short loc_1800323D2
0x1800323e4  mov     rcx, rsi; pv
0x1800323e7  call    cs:__imp_CoTaskMemFree
0x1800323ed  lea     rcx, [rbp+var]; pvarg
0x1800323f1  call    cs:__imp_VariantClear
0x1800323f7  mov     edi, 8007000Eh
0x1800323fc  lea     rcx, [rbp+var_38]
0x180032400  mov     byte ptr [rbx+290h], 1
0x180032407  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003240c  mov     eax, edi
0x18003240e  jmp     short loc_180032457
0x180032410  mov     eax, [rbp+pcElem]
0x180032413  mov     rsi, [rbp+pprgsz]
0x180032417  xor     edi, edi
0x180032419  mov     r14d, eax
0x18003241c  test    eax, eax
0x18003241e  jz      short loc_180032432
0x180032420  mov     rcx, [rsi+rdi*8]; pv
0x180032424  call    cs:__imp_CoTaskMemFree
0x18003242a  inc     rdi
0x18003242d  cmp     rdi, r14
0x180032430  jb      short loc_180032420
0x180032432  mov     rcx, rsi; pv
0x180032435  call    cs:__imp_CoTaskMemFree
0x18003243b  lea     rcx, [rbp+var]; pvarg
0x18003243f  call    cs:__imp_VariantClear
0x180032445  lea     rcx, [rbp+var_38]
0x180032449  mov     byte ptr [rbx+290h], 1
0x180032450  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032455  xor     eax, eax
0x180032457  mov     rcx, [rbp+var_8]
0x18003245b  xor     rcx, rsp; StackCookie
0x18003245e  call    __security_check_cookie
0x180032463  lea     r11, [rsp+60h+var_s0]
0x180032468  mov     rbx, [r11+28h]
0x18003246c  mov     rsi, [r11+30h]
0x180032470  mov     rsp, r11
0x180032473  pop     r14
0x180032475  pop     rdi
0x180032476  pop     rbp
0x180032477  retn
```
