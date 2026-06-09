# WSP_FileShare_Invoke_GetAccessControlEntries

- ea: `0x18003ca00`
- end: `0x18003cb36`
- name: `WSP_FileShare_Invoke_GetAccessControlEntries`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x1800393f4`
- `0x180039c68`
- `0x180039f98`
- `0x18003be1c`
- `0x18003ca00`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003cb12`
- `MISpace!WspProviderExit` at `0x18003cb12`
- `MISpace!WspInvokeRemoteMethod` at `0x18003ca99`
- `MISpace!WspInvokeRemoteMethod` at `0x18003ca99`
- `MISpace!WspIsRemoteInstance` at `0x18003ca72`
- `MISpace!WspIsRemoteInstance` at `0x18003ca72`
- `MISpace!WspProviderEnter` at `0x18003ca4f`
- `MISpace!WspProviderEnter` at `0x18003ca4f`

## string_xrefs

- `0x18003caac`: `WSP_FileShare_Invoke_GetAccessControlEntries`
- `0x18003caf8`: `WSP_FileShare_Invoke_GetAccessControlEntries`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_GetAccessControlEntries(
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
  cxl::TextWriter::WriteLine<wchar_t,char [45],>(
    (struct cxl::TraceManager *)((char *)v12 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v17 )
  {
    v19[2] = a7;
    v16[0] = a2;
    v16[1] = 0;
    v19[0] = a2;
    v19[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_e3fc6eb21050ecb0736c7706b0831c8c_>(
      v13,
      v16,
      v19);
  }
  v14 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [45],>(
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
0x18003ca00  mov     [rsp-20h+arg_0], rcx
0x18003ca05  push    rbp
0x18003ca06  push    rbx
0x18003ca07  push    rsi
0x18003ca08  push    rdi
0x18003ca09  mov     rbp, rsp
0x18003ca0c  sub     rsp, 78h
0x18003ca10  mov     rbx, rdx
0x18003ca13  lea     r8, [rbp+arg_0]
0x18003ca17  lea     rdx, [rbp+var_40]
0x18003ca1b  mov     rsi, r9
0x18003ca1e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003ca23  lea     rcx, [rbp+var_30]
0x18003ca27  mov     rdx, [rax]
0x18003ca2a  add     rdx, 28h ; '('
0x18003ca2e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003ca33  mov     rdi, [rbp+arg_28]
0x18003ca37  lea     r9, [rbp+var_48]
0x18003ca3b  mov     r8d, 1
0x18003ca41  mov     [rbp+var_48], 0
0x18003ca48  mov     rcx, rbx
0x18003ca4b  mov     rdx, [rdi+40h]
0x18003ca4f  call    cs:__imp_WspProviderEnter
0x18003ca56  nop     dword ptr [rax+rax+00h]
0x18003ca5b  test    eax, eax
0x18003ca5d  jz      short loc_18003CA6E
0x18003ca5f  mov     edx, eax; result
0x18003ca61  mov     rcx, rbx; context
0x18003ca64  call    MI_Context_PostResult_0
0x18003ca69  jmp     loc_18003CB0F
0x18003ca6e  mov     rcx, [rdi+40h]
0x18003ca72  call    cs:__imp_WspIsRemoteInstance
0x18003ca79  nop     dword ptr [rax+rax+00h]
0x18003ca7e  test    al, al
0x18003ca80  jz      short loc_18003CAA7
0x18003ca82  mov     rax, [rbp+arg_30]
0x18003ca86  mov     rdx, rsi
0x18003ca89  mov     r9, [rbp+arg_20]
0x18003ca8d  mov     rcx, rbx
0x18003ca90  mov     r8, [rdi+40h]
0x18003ca94  mov     [rsp+78h+var_58], rax
0x18003ca99  call    cs:__imp_WspInvokeRemoteMethod
0x18003caa0  nop     dword ptr [rax+rax+00h]
0x18003caa5  jmp     short loc_18003CA5F
0x18003caa7  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003caac  lea     r8, aWspFileshareIn_5; "WSP_FileShare_Invoke_GetAccessControlEn"...
0x18003cab3  lea     rdx, aEntering0; "Entering {0}"
0x18003caba  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003cabe  call    ??$WriteLine@_W$$BY0CN@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CN@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [45],>(wchar_t const *,char const (&)[45])
0x18003cac3  cmp     [rbp+var_30], 0
0x18003cac8  jz      short loc_18003CAF3
0x18003caca  mov     rax, [rbp+arg_30]
0x18003cace  lea     r8, [rbp+var_20]
0x18003cad2  lea     rdx, [rbp+var_40]
0x18003cad6  mov     [rbp+var_10], rax
0x18003cada  mov     [rbp+var_40], rbx
0x18003cade  mov     [rbp+var_38], 0
0x18003cae6  mov     [rbp+var_20], rbx
0x18003caea  mov     [rbp+var_18], rdi
0x18003caee  call    ??$ClassOperation@V_lambda_e3fc6eb21050ecb0736c7706b0831c8c_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_e3fc6eb21050ecb0736c7706b0831c8c_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_e3fc6eb21050ecb0736c7706b0831c8c_>(mi::MiContext &,_lambda_e3fc6eb21050ecb0736c7706b0831c8c_ const &)
0x18003caf3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003caf8  lea     r8, aWspFileshareIn_5; "WSP_FileShare_Invoke_GetAccessControlEn"...
0x18003caff  lea     rdx, aExiting0; "Exiting {0}"
0x18003cb06  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003cb0a  call    ??$WriteLine@_W$$BY0CN@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CN@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [45],>(wchar_t const *,char const (&)[45])
0x18003cb0f  mov     ecx, [rbp+var_48]
0x18003cb12  call    cs:__imp_WspProviderExit
0x18003cb19  nop     dword ptr [rax+rax+00h]
0x18003cb1e  mov     rcx, [rbp+var_28]; this
0x18003cb22  test    rcx, rcx
0x18003cb25  jz      short loc_18003CB2C
0x18003cb27  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cb2c  add     rsp, 78h
0x18003cb30  pop     rdi
0x18003cb31  pop     rsi
0x18003cb32  pop     rbx
0x18003cb33  pop     rbp
0x18003cb34  retn
```
