# WSP_FileShare_Invoke_UnblockAccess

- ea: `0x18003bdf0`
- end: `0x18003bf27`
- name: `WSP_FileShare_Invoke_UnblockAccess`
- size: `311`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x180037dd8`
- `0x1800388b0`
- `0x180038c58`
- `0x18003bdf0`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003bf0a`
- `MISpace!WspProviderExit` at `0x18003bf0a`
- `MISpace!WspInvokeRemoteMethod` at `0x18003be95`
- `MISpace!WspInvokeRemoteMethod` at `0x18003be95`
- `MISpace!WspIsRemoteInstance` at `0x18003be74`
- `MISpace!WspIsRemoteInstance` at `0x18003be74`
- `MISpace!WspProviderEnter` at `0x18003be3f`
- `MISpace!WspProviderEnter` at `0x18003be3f`

## string_xrefs

- `0x18003bea4`: `WSP_FileShare_Invoke_UnblockAccess`
- `0x18003bef0`: `WSP_FileShare_Invoke_UnblockAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_UnblockAccess(
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
  cxl::TextWriter::WriteLine<wchar_t,char [35],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_59f2f45d6a776f14b9616afea8647aba_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [35],>(
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
0x18003bdf0  mov     [rsp-20h+arg_0], rcx
0x18003bdf5  push    rbp
0x18003bdf6  push    rbx
0x18003bdf7  push    rsi
0x18003bdf8  push    rdi
0x18003bdf9  mov     rbp, rsp
0x18003bdfc  sub     rsp, 78h
0x18003be00  mov     rbx, rdx
0x18003be03  lea     r8, [rbp+arg_0]
0x18003be07  lea     rdx, [rbp+var_40]
0x18003be0b  mov     rsi, r9
0x18003be0e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003be13  lea     rcx, [rbp+var_30]
0x18003be17  mov     rdx, [rax]
0x18003be1a  add     rdx, 28h ; '('
0x18003be1e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003be23  mov     rdi, [rbp+arg_28]
0x18003be27  lea     r9, [rbp+var_48]
0x18003be2b  mov     r8d, 1
0x18003be31  mov     [rbp+var_48], 0
0x18003be38  mov     rcx, rbx
0x18003be3b  mov     rdx, [rdi+40h]
0x18003be3f  call    cs:__imp_WspProviderEnter
0x18003be45  mov     edx, eax
0x18003be47  test    eax, eax
0x18003be49  jz      short loc_18003BE70
0x18003be4b  test    rbx, rbx
0x18003be4e  jz      loc_18003BF07
0x18003be54  mov     rax, [rbx]
0x18003be57  test    rax, rax
0x18003be5a  jz      loc_18003BF07
0x18003be60  mov     rax, [rax]
0x18003be63  mov     rcx, rbx
0x18003be66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be6b  jmp     loc_18003BF07
0x18003be70  mov     rcx, [rdi+40h]
0x18003be74  call    cs:__imp_WspIsRemoteInstance
0x18003be7a  test    al, al
0x18003be7c  jz      short loc_18003BE9F
0x18003be7e  mov     rax, [rbp+arg_30]
0x18003be82  mov     rdx, rsi
0x18003be85  mov     r9, [rbp+arg_20]
0x18003be89  mov     rcx, rbx
0x18003be8c  mov     r8, [rdi+40h]
0x18003be90  mov     [rsp+78h+var_58], rax
0x18003be95  call    cs:__imp_WspInvokeRemoteMethod
0x18003be9b  mov     edx, eax
0x18003be9d  jmp     short loc_18003BE4B
0x18003be9f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003bea4  lea     r8, aWspFileshareIn; "WSP_FileShare_Invoke_UnblockAccess"
0x18003beab  lea     rdx, aEntering0; "Entering {0}"
0x18003beb2  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003beb6  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x18003bebb  cmp     [rbp+var_30], 0
0x18003bec0  jz      short loc_18003BEEB
0x18003bec2  mov     rax, [rbp+arg_30]
0x18003bec6  lea     r8, [rbp+var_20]
0x18003beca  lea     rdx, [rbp+var_40]
0x18003bece  mov     [rbp+var_10], rax
0x18003bed2  mov     [rbp+var_40], rbx
0x18003bed6  mov     [rbp+var_38], 0
0x18003bede  mov     [rbp+var_20], rbx
0x18003bee2  mov     [rbp+var_18], rdi
0x18003bee6  call    ??$ClassOperation@V_lambda_59f2f45d6a776f14b9616afea8647aba_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_59f2f45d6a776f14b9616afea8647aba_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_59f2f45d6a776f14b9616afea8647aba_>(mi::MiContext &,_lambda_59f2f45d6a776f14b9616afea8647aba_ const &)
0x18003beeb  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003bef0  lea     r8, aWspFileshareIn; "WSP_FileShare_Invoke_UnblockAccess"
0x18003bef7  lea     rdx, aExiting0; "Exiting {0}"
0x18003befe  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003bf02  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x18003bf07  mov     ecx, [rbp+var_48]
0x18003bf0a  call    cs:__imp_WspProviderExit
0x18003bf10  mov     rcx, [rbp+var_28]; this
0x18003bf14  test    rcx, rcx
0x18003bf17  jz      short loc_18003BF1E
0x18003bf19  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bf1e  add     rsp, 78h
0x18003bf22  pop     rdi
0x18003bf23  pop     rsi
0x18003bf24  pop     rbx
0x18003bf25  pop     rbp
0x18003bf26  retn
```
