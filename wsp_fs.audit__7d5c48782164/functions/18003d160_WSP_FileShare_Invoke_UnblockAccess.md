# WSP_FileShare_Invoke_UnblockAccess

- ea: `0x18003d160`
- end: `0x18003d296`
- name: `WSP_FileShare_Invoke_UnblockAccess`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x1800390e4`
- `0x180039be8`
- `0x180039f98`
- `0x18003be1c`
- `0x18003d160`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003d272`
- `MISpace!WspProviderExit` at `0x18003d272`
- `MISpace!WspInvokeRemoteMethod` at `0x18003d1f9`
- `MISpace!WspInvokeRemoteMethod` at `0x18003d1f9`
- `MISpace!WspIsRemoteInstance` at `0x18003d1d2`
- `MISpace!WspIsRemoteInstance` at `0x18003d1d2`
- `MISpace!WspProviderEnter` at `0x18003d1af`
- `MISpace!WspProviderEnter` at `0x18003d1af`

## string_xrefs

- `0x18003d20c`: `WSP_FileShare_Invoke_UnblockAccess`
- `0x18003d258`: `WSP_FileShare_Invoke_UnblockAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_UnblockAccess(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v9; // rax
  __int64 v10; // rdi
  MI_Result v11; // eax
  struct cxl::TraceManager *v12; // rax
  __int64 v13; // rcx
  struct cxl::TraceManager *v14; // rax
  unsigned int v15; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v18; // [rsp+50h] [rbp-28h]
  _QWORD v19[4]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+28h] BYREF

  v20 = a1;
  v9 = (_QWORD *)std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(
                   a1,
                   v16,
                   &v20);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v17, *v9 + 40LL);
  v10 = a6;
  v15 = 0;
  v11 = (unsigned int)WspProviderEnter(a2, *(_QWORD *)(a6 + 64), 1, &v15);
  if ( v11 )
    goto LABEL_2;
  if ( (unsigned __int8)WspIsRemoteInstance(*(_QWORD *)(v10 + 64)) )
  {
    v11 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *(_QWORD *)(v10 + 64), a5, a7);
LABEL_2:
    MI_Context_PostResult_0(a2, v11);
    goto LABEL_8;
  }
  v12 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [35],>(
    (struct cxl::TraceManager *)((char *)v12 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v17 )
  {
    v19[2] = a7;
    v16[0] = a2;
    v16[1] = 0;
    v19[0] = a2;
    v19[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_59f2f45d6a776f14b9616afea8647aba_>(
      v13,
      v16,
      v19);
  }
  v14 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [35],>(
    (struct cxl::TraceManager *)((char *)v14 + 120),
    (wchar_t *)L"Exiting {0}");
LABEL_8:
  WspProviderExit(v15);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x18003d160  mov     [rsp-20h+arg_0], rcx
0x18003d165  push    rbp
0x18003d166  push    rbx
0x18003d167  push    rsi
0x18003d168  push    rdi
0x18003d169  mov     rbp, rsp
0x18003d16c  sub     rsp, 78h
0x18003d170  mov     rbx, rdx
0x18003d173  lea     r8, [rbp+arg_0]
0x18003d177  lea     rdx, [rbp+var_40]
0x18003d17b  mov     rsi, r9
0x18003d17e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003d183  lea     rcx, [rbp+var_30]
0x18003d187  mov     rdx, [rax]
0x18003d18a  add     rdx, 28h ; '('
0x18003d18e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003d193  mov     rdi, [rbp+arg_28]
0x18003d197  lea     r9, [rbp+var_48]
0x18003d19b  mov     r8d, 1
0x18003d1a1  mov     [rbp+var_48], 0
0x18003d1a8  mov     rcx, rbx
0x18003d1ab  mov     rdx, [rdi+40h]
0x18003d1af  call    cs:__imp_WspProviderEnter
0x18003d1b6  nop     dword ptr [rax+rax+00h]
0x18003d1bb  test    eax, eax
0x18003d1bd  jz      short loc_18003D1CE
0x18003d1bf  mov     edx, eax; result
0x18003d1c1  mov     rcx, rbx; context
0x18003d1c4  call    MI_Context_PostResult_0
0x18003d1c9  jmp     loc_18003D26F
0x18003d1ce  mov     rcx, [rdi+40h]
0x18003d1d2  call    cs:__imp_WspIsRemoteInstance
0x18003d1d9  nop     dword ptr [rax+rax+00h]
0x18003d1de  test    al, al
0x18003d1e0  jz      short loc_18003D207
0x18003d1e2  mov     rax, [rbp+arg_30]
0x18003d1e6  mov     rdx, rsi
0x18003d1e9  mov     r9, [rbp+arg_20]
0x18003d1ed  mov     rcx, rbx
0x18003d1f0  mov     r8, [rdi+40h]
0x18003d1f4  mov     [rsp+78h+var_58], rax
0x18003d1f9  call    cs:__imp_WspInvokeRemoteMethod
0x18003d200  nop     dword ptr [rax+rax+00h]
0x18003d205  jmp     short loc_18003D1BF
0x18003d207  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003d20c  lea     r8, aWspFileshareIn; "WSP_FileShare_Invoke_UnblockAccess"
0x18003d213  lea     rdx, aEntering0; "Entering {0}"
0x18003d21a  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003d21e  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x18003d223  cmp     [rbp+var_30], 0
0x18003d228  jz      short loc_18003D253
0x18003d22a  mov     rax, [rbp+arg_30]
0x18003d22e  lea     r8, [rbp+var_20]
0x18003d232  lea     rdx, [rbp+var_40]
0x18003d236  mov     [rbp+var_10], rax
0x18003d23a  mov     [rbp+var_40], rbx
0x18003d23e  mov     [rbp+var_38], 0
0x18003d246  mov     [rbp+var_20], rbx
0x18003d24a  mov     [rbp+var_18], rdi
0x18003d24e  call    ??$ClassOperation@V_lambda_59f2f45d6a776f14b9616afea8647aba_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_59f2f45d6a776f14b9616afea8647aba_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_59f2f45d6a776f14b9616afea8647aba_>(mi::MiContext &,_lambda_59f2f45d6a776f14b9616afea8647aba_ const &)
0x18003d253  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003d258  lea     r8, aWspFileshareIn; "WSP_FileShare_Invoke_UnblockAccess"
0x18003d25f  lea     rdx, aExiting0; "Exiting {0}"
0x18003d266  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003d26a  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x18003d26f  mov     ecx, [rbp+var_48]
0x18003d272  call    cs:__imp_WspProviderExit
0x18003d279  nop     dword ptr [rax+rax+00h]
0x18003d27e  mov     rcx, [rbp+var_28]; this
0x18003d282  test    rcx, rcx
0x18003d285  jz      short loc_18003D28C
0x18003d287  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003d28c  add     rsp, 78h
0x18003d290  pop     rdi
0x18003d291  pop     rsi
0x18003d292  pop     rbx
0x18003d293  pop     rbp
0x18003d294  retn
```
