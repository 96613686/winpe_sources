# WSP_FileShare_Invoke_RevokeAccess

- ea: `0x18003ba40`
- end: `0x18003bb77`
- name: `WSP_FileShare_Invoke_RevokeAccess`
- size: `311`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x180037e50`
- `0x180038874`
- `0x180038c58`
- `0x18003ba40`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003bb5a`
- `MISpace!WspProviderExit` at `0x18003bb5a`
- `MISpace!WspInvokeRemoteMethod` at `0x18003bae5`
- `MISpace!WspInvokeRemoteMethod` at `0x18003bae5`
- `MISpace!WspIsRemoteInstance` at `0x18003bac4`
- `MISpace!WspIsRemoteInstance` at `0x18003bac4`
- `MISpace!WspProviderEnter` at `0x18003ba8f`
- `MISpace!WspProviderEnter` at `0x18003ba8f`

## string_xrefs

- `0x18003baf4`: `WSP_FileShare_Invoke_RevokeAccess`
- `0x18003bb40`: `WSP_FileShare_Invoke_RevokeAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_RevokeAccess(
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
  cxl::TextWriter::WriteLine<wchar_t,char [34],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [34],>(
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
0x18003ba40  mov     [rsp-20h+arg_0], rcx
0x18003ba45  push    rbp
0x18003ba46  push    rbx
0x18003ba47  push    rsi
0x18003ba48  push    rdi
0x18003ba49  mov     rbp, rsp
0x18003ba4c  sub     rsp, 78h
0x18003ba50  mov     rbx, rdx
0x18003ba53  lea     r8, [rbp+arg_0]
0x18003ba57  lea     rdx, [rbp+var_40]
0x18003ba5b  mov     rsi, r9
0x18003ba5e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003ba63  lea     rcx, [rbp+var_30]
0x18003ba67  mov     rdx, [rax]
0x18003ba6a  add     rdx, 28h ; '('
0x18003ba6e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003ba73  mov     rdi, [rbp+arg_28]
0x18003ba77  lea     r9, [rbp+var_48]
0x18003ba7b  mov     r8d, 1
0x18003ba81  mov     [rbp+var_48], 0
0x18003ba88  mov     rcx, rbx
0x18003ba8b  mov     rdx, [rdi+40h]
0x18003ba8f  call    cs:__imp_WspProviderEnter
0x18003ba95  mov     edx, eax
0x18003ba97  test    eax, eax
0x18003ba99  jz      short loc_18003BAC0
0x18003ba9b  test    rbx, rbx
0x18003ba9e  jz      loc_18003BB57
0x18003baa4  mov     rax, [rbx]
0x18003baa7  test    rax, rax
0x18003baaa  jz      loc_18003BB57
0x18003bab0  mov     rax, [rax]
0x18003bab3  mov     rcx, rbx
0x18003bab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003babb  jmp     loc_18003BB57
0x18003bac0  mov     rcx, [rdi+40h]
0x18003bac4  call    cs:__imp_WspIsRemoteInstance
0x18003baca  test    al, al
0x18003bacc  jz      short loc_18003BAEF
0x18003bace  mov     rax, [rbp+arg_30]
0x18003bad2  mov     rdx, rsi
0x18003bad5  mov     r9, [rbp+arg_20]
0x18003bad9  mov     rcx, rbx
0x18003badc  mov     r8, [rdi+40h]
0x18003bae0  mov     [rsp+78h+var_58], rax
0x18003bae5  call    cs:__imp_WspInvokeRemoteMethod
0x18003baeb  mov     edx, eax
0x18003baed  jmp     short loc_18003BA9B
0x18003baef  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003baf4  lea     r8, aWspFileshareIn_3; "WSP_FileShare_Invoke_RevokeAccess"
0x18003bafb  lea     rdx, aEntering0; "Entering {0}"
0x18003bb02  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003bb06  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003bb0b  cmp     [rbp+var_30], 0
0x18003bb10  jz      short loc_18003BB3B
0x18003bb12  mov     rax, [rbp+arg_30]
0x18003bb16  lea     r8, [rbp+var_20]
0x18003bb1a  lea     rdx, [rbp+var_40]
0x18003bb1e  mov     [rbp+var_10], rax
0x18003bb22  mov     [rbp+var_40], rbx
0x18003bb26  mov     [rbp+var_38], 0
0x18003bb2e  mov     [rbp+var_20], rbx
0x18003bb32  mov     [rbp+var_18], rdi
0x18003bb36  call    ??$ClassOperation@V_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_>(mi::MiContext &,_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_ const &)
0x18003bb3b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003bb40  lea     r8, aWspFileshareIn_3; "WSP_FileShare_Invoke_RevokeAccess"
0x18003bb47  lea     rdx, aExiting0; "Exiting {0}"
0x18003bb4e  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003bb52  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003bb57  mov     ecx, [rbp+var_48]
0x18003bb5a  call    cs:__imp_WspProviderExit
0x18003bb60  mov     rcx, [rbp+var_28]; this
0x18003bb64  test    rcx, rcx
0x18003bb67  jz      short loc_18003BB6E
0x18003bb69  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bb6e  add     rsp, 78h
0x18003bb72  pop     rdi
0x18003bb73  pop     rsi
0x18003bb74  pop     rbx
0x18003bb75  pop     rbp
0x18003bb76  retn
```
