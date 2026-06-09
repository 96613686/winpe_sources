# WSP_FileShare_Invoke_GrantAccess

- ea: `0x18003b900`
- end: `0x18003ba37`
- name: `WSP_FileShare_Invoke_GrantAccess`
- size: `311`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x180037ec8`
- `0x180038770`
- `0x180038c58`
- `0x18003b900`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003ba1a`
- `MISpace!WspProviderExit` at `0x18003ba1a`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b9a5`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b9a5`
- `MISpace!WspIsRemoteInstance` at `0x18003b984`
- `MISpace!WspIsRemoteInstance` at `0x18003b984`
- `MISpace!WspProviderEnter` at `0x18003b94f`
- `MISpace!WspProviderEnter` at `0x18003b94f`

## string_xrefs

- `0x18003b9b4`: `WSP_FileShare_Invoke_GrantAccess`
- `0x18003ba00`: `WSP_FileShare_Invoke_GrantAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_GrantAccess(
        __int64 a1,
        void (__fastcall ***a2)(_QWORD, __int64),
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v9; // rax
  __int64 v10; // rdi
  unsigned int v11; // eax
  __int64 v12; // rdx
  struct cxl::TraceManager *v13; // rax
  __int64 v14; // rcx
  struct cxl::TraceManager *v15; // rax
  unsigned int v16; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v19; // [rsp+50h] [rbp-28h]
  _QWORD v20[4]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+28h] BYREF

  v21 = a1;
  v9 = (_QWORD *)std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(
                   a1,
                   v17,
                   &v21);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v18, *v9 + 40LL);
  v10 = a6;
  v16 = 0;
  v11 = WspProviderEnter(a2, *(_QWORD *)(a6 + 64), 1, &v16);
  v12 = v11;
  if ( v11 )
  {
LABEL_2:
    if ( a2 && *a2 )
      (**a2)(a2, v12);
    goto LABEL_10;
  }
  if ( (unsigned __int8)WspIsRemoteInstance(*(_QWORD *)(v10 + 64), 0) )
  {
    v12 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *(_QWORD *)(v10 + 64), a5, a7);
    goto LABEL_2;
  }
  v13 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [33],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_9519f4677529ddcf48d9b929b85a37a6_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [33],>(
    (struct cxl::TraceManager *)((char *)v15 + 120),
    (wchar_t *)L"Exiting {0}");
LABEL_10:
  WspProviderExit(v16, v12);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
}

```

## disassembly

```asm
0x18003b900  mov     [rsp-20h+arg_0], rcx
0x18003b905  push    rbp
0x18003b906  push    rbx
0x18003b907  push    rsi
0x18003b908  push    rdi
0x18003b909  mov     rbp, rsp
0x18003b90c  sub     rsp, 78h
0x18003b910  mov     rbx, rdx
0x18003b913  lea     r8, [rbp+arg_0]
0x18003b917  lea     rdx, [rbp+var_40]
0x18003b91b  mov     rsi, r9
0x18003b91e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003b923  lea     rcx, [rbp+var_30]
0x18003b927  mov     rdx, [rax]
0x18003b92a  add     rdx, 28h ; '('
0x18003b92e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003b933  mov     rdi, [rbp+arg_28]
0x18003b937  lea     r9, [rbp+var_48]
0x18003b93b  mov     r8d, 1
0x18003b941  mov     [rbp+var_48], 0
0x18003b948  mov     rcx, rbx
0x18003b94b  mov     rdx, [rdi+40h]
0x18003b94f  call    cs:__imp_WspProviderEnter
0x18003b955  mov     edx, eax
0x18003b957  test    eax, eax
0x18003b959  jz      short loc_18003B980
0x18003b95b  test    rbx, rbx
0x18003b95e  jz      loc_18003BA17
0x18003b964  mov     rax, [rbx]
0x18003b967  test    rax, rax
0x18003b96a  jz      loc_18003BA17
0x18003b970  mov     rax, [rax]
0x18003b973  mov     rcx, rbx
0x18003b976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b97b  jmp     loc_18003BA17
0x18003b980  mov     rcx, [rdi+40h]
0x18003b984  call    cs:__imp_WspIsRemoteInstance
0x18003b98a  test    al, al
0x18003b98c  jz      short loc_18003B9AF
0x18003b98e  mov     rax, [rbp+arg_30]
0x18003b992  mov     rdx, rsi
0x18003b995  mov     r9, [rbp+arg_20]
0x18003b999  mov     rcx, rbx
0x18003b99c  mov     r8, [rdi+40h]
0x18003b9a0  mov     [rsp+78h+var_58], rax
0x18003b9a5  call    cs:__imp_WspInvokeRemoteMethod
0x18003b9ab  mov     edx, eax
0x18003b9ad  jmp     short loc_18003B95B
0x18003b9af  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b9b4  lea     r8, aWspFileshareIn_2; "WSP_FileShare_Invoke_GrantAccess"
0x18003b9bb  lea     rdx, aEntering0; "Entering {0}"
0x18003b9c2  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b9c6  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003b9cb  cmp     [rbp+var_30], 0
0x18003b9d0  jz      short loc_18003B9FB
0x18003b9d2  mov     rax, [rbp+arg_30]
0x18003b9d6  lea     r8, [rbp+var_20]
0x18003b9da  lea     rdx, [rbp+var_40]
0x18003b9de  mov     [rbp+var_10], rax
0x18003b9e2  mov     [rbp+var_40], rbx
0x18003b9e6  mov     [rbp+var_38], 0
0x18003b9ee  mov     [rbp+var_20], rbx
0x18003b9f2  mov     [rbp+var_18], rdi
0x18003b9f6  call    ??$ClassOperation@V_lambda_9519f4677529ddcf48d9b929b85a37a6_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_9519f4677529ddcf48d9b929b85a37a6_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_9519f4677529ddcf48d9b929b85a37a6_>(mi::MiContext &,_lambda_9519f4677529ddcf48d9b929b85a37a6_ const &)
0x18003b9fb  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003ba00  lea     r8, aWspFileshareIn_2; "WSP_FileShare_Invoke_GrantAccess"
0x18003ba07  lea     rdx, aExiting0; "Exiting {0}"
0x18003ba0e  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003ba12  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003ba17  mov     ecx, [rbp+var_48]
0x18003ba1a  call    cs:__imp_WspProviderExit
0x18003ba20  mov     rcx, [rbp+var_28]; this
0x18003ba24  test    rcx, rcx
0x18003ba27  jz      short loc_18003BA2E
0x18003ba29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ba2e  add     rsp, 78h
0x18003ba32  pop     rdi
0x18003ba33  pop     rsi
0x18003ba34  pop     rbx
0x18003ba35  pop     rbp
0x18003ba36  retn
```
