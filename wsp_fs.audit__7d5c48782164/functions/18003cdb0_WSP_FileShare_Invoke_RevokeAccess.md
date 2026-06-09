# WSP_FileShare_Invoke_RevokeAccess

- ea: `0x18003cdb0`
- end: `0x18003cee6`
- name: `WSP_FileShare_Invoke_RevokeAccess`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x180039160`
- `0x180039bac`
- `0x180039f98`
- `0x18003be1c`
- `0x18003cdb0`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003cec2`
- `MISpace!WspProviderExit` at `0x18003cec2`
- `MISpace!WspInvokeRemoteMethod` at `0x18003ce49`
- `MISpace!WspInvokeRemoteMethod` at `0x18003ce49`
- `MISpace!WspIsRemoteInstance` at `0x18003ce22`
- `MISpace!WspIsRemoteInstance` at `0x18003ce22`
- `MISpace!WspProviderEnter` at `0x18003cdff`
- `MISpace!WspProviderEnter` at `0x18003cdff`

## string_xrefs

- `0x18003ce5c`: `WSP_FileShare_Invoke_RevokeAccess`
- `0x18003cea8`: `WSP_FileShare_Invoke_RevokeAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_RevokeAccess(
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
  cxl::TextWriter::WriteLine<wchar_t,char [34],>(
    (struct cxl::TraceManager *)((char *)v12 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v17 )
  {
    v19[2] = a7;
    v16[0] = a2;
    v16[1] = 0;
    v19[0] = a2;
    v19[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_>(
      v13,
      v16,
      v19);
  }
  v14 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [34],>(
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
0x18003cdb0  mov     [rsp-20h+arg_0], rcx
0x18003cdb5  push    rbp
0x18003cdb6  push    rbx
0x18003cdb7  push    rsi
0x18003cdb8  push    rdi
0x18003cdb9  mov     rbp, rsp
0x18003cdbc  sub     rsp, 78h
0x18003cdc0  mov     rbx, rdx
0x18003cdc3  lea     r8, [rbp+arg_0]
0x18003cdc7  lea     rdx, [rbp+var_40]
0x18003cdcb  mov     rsi, r9
0x18003cdce  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003cdd3  lea     rcx, [rbp+var_30]
0x18003cdd7  mov     rdx, [rax]
0x18003cdda  add     rdx, 28h ; '('
0x18003cdde  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003cde3  mov     rdi, [rbp+arg_28]
0x18003cde7  lea     r9, [rbp+var_48]
0x18003cdeb  mov     r8d, 1
0x18003cdf1  mov     [rbp+var_48], 0
0x18003cdf8  mov     rcx, rbx
0x18003cdfb  mov     rdx, [rdi+40h]
0x18003cdff  call    cs:__imp_WspProviderEnter
0x18003ce06  nop     dword ptr [rax+rax+00h]
0x18003ce0b  test    eax, eax
0x18003ce0d  jz      short loc_18003CE1E
0x18003ce0f  mov     edx, eax; result
0x18003ce11  mov     rcx, rbx; context
0x18003ce14  call    MI_Context_PostResult_0
0x18003ce19  jmp     loc_18003CEBF
0x18003ce1e  mov     rcx, [rdi+40h]
0x18003ce22  call    cs:__imp_WspIsRemoteInstance
0x18003ce29  nop     dword ptr [rax+rax+00h]
0x18003ce2e  test    al, al
0x18003ce30  jz      short loc_18003CE57
0x18003ce32  mov     rax, [rbp+arg_30]
0x18003ce36  mov     rdx, rsi
0x18003ce39  mov     r9, [rbp+arg_20]
0x18003ce3d  mov     rcx, rbx
0x18003ce40  mov     r8, [rdi+40h]
0x18003ce44  mov     [rsp+78h+var_58], rax
0x18003ce49  call    cs:__imp_WspInvokeRemoteMethod
0x18003ce50  nop     dword ptr [rax+rax+00h]
0x18003ce55  jmp     short loc_18003CE0F
0x18003ce57  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003ce5c  lea     r8, aWspFileshareIn_3; "WSP_FileShare_Invoke_RevokeAccess"
0x18003ce63  lea     rdx, aEntering0; "Entering {0}"
0x18003ce6a  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003ce6e  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003ce73  cmp     [rbp+var_30], 0
0x18003ce78  jz      short loc_18003CEA3
0x18003ce7a  mov     rax, [rbp+arg_30]
0x18003ce7e  lea     r8, [rbp+var_20]
0x18003ce82  lea     rdx, [rbp+var_40]
0x18003ce86  mov     [rbp+var_10], rax
0x18003ce8a  mov     [rbp+var_40], rbx
0x18003ce8e  mov     [rbp+var_38], 0
0x18003ce96  mov     [rbp+var_20], rbx
0x18003ce9a  mov     [rbp+var_18], rdi
0x18003ce9e  call    ??$ClassOperation@V_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_>(mi::MiContext &,_lambda_635abb22a2d65d36765e1cd3ae7eeaa1_ const &)
0x18003cea3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003cea8  lea     r8, aWspFileshareIn_3; "WSP_FileShare_Invoke_RevokeAccess"
0x18003ceaf  lea     rdx, aExiting0; "Exiting {0}"
0x18003ceb6  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003ceba  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003cebf  mov     ecx, [rbp+var_48]
0x18003cec2  call    cs:__imp_WspProviderExit
0x18003cec9  nop     dword ptr [rax+rax+00h]
0x18003cece  mov     rcx, [rbp+var_28]; this
0x18003ced2  test    rcx, rcx
0x18003ced5  jz      short loc_18003CEDC
0x18003ced7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cedc  add     rsp, 78h
0x18003cee0  pop     rdi
0x18003cee1  pop     rsi
0x18003cee2  pop     rbx
0x18003cee3  pop     rbp
0x18003cee4  retn
```
