# WSP_FileShare_Invoke_DeleteObject

- ea: `0x18003c790`
- end: `0x18003c8c6`
- name: `WSP_FileShare_Invoke_DeleteObject`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x180039258`
- `0x180039bac`
- `0x180039f98`
- `0x18003be1c`
- `0x18003c790`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003c8a2`
- `MISpace!WspProviderExit` at `0x18003c8a2`
- `MISpace!WspInvokeRemoteMethod` at `0x18003c829`
- `MISpace!WspInvokeRemoteMethod` at `0x18003c829`
- `MISpace!WspIsRemoteInstance` at `0x18003c802`
- `MISpace!WspIsRemoteInstance` at `0x18003c802`
- `MISpace!WspProviderEnter` at `0x18003c7df`
- `MISpace!WspProviderEnter` at `0x18003c7df`

## string_xrefs

- `0x18003c83c`: `WSP_FileShare_Invoke_DeleteObject`
- `0x18003c888`: `WSP_FileShare_Invoke_DeleteObject`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_DeleteObject(
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
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_>(
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
0x18003c790  mov     [rsp-20h+arg_0], rcx
0x18003c795  push    rbp
0x18003c796  push    rbx
0x18003c797  push    rsi
0x18003c798  push    rdi
0x18003c799  mov     rbp, rsp
0x18003c79c  sub     rsp, 78h
0x18003c7a0  mov     rbx, rdx
0x18003c7a3  lea     r8, [rbp+arg_0]
0x18003c7a7  lea     rdx, [rbp+var_40]
0x18003c7ab  mov     rsi, r9
0x18003c7ae  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003c7b3  lea     rcx, [rbp+var_30]
0x18003c7b7  mov     rdx, [rax]
0x18003c7ba  add     rdx, 28h ; '('
0x18003c7be  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003c7c3  mov     rdi, [rbp+arg_28]
0x18003c7c7  lea     r9, [rbp+var_48]
0x18003c7cb  mov     r8d, 1
0x18003c7d1  mov     [rbp+var_48], 0
0x18003c7d8  mov     rcx, rbx
0x18003c7db  mov     rdx, [rdi+40h]
0x18003c7df  call    cs:__imp_WspProviderEnter
0x18003c7e6  nop     dword ptr [rax+rax+00h]
0x18003c7eb  test    eax, eax
0x18003c7ed  jz      short loc_18003C7FE
0x18003c7ef  mov     edx, eax; result
0x18003c7f1  mov     rcx, rbx; context
0x18003c7f4  call    MI_Context_PostResult_0
0x18003c7f9  jmp     loc_18003C89F
0x18003c7fe  mov     rcx, [rdi+40h]
0x18003c802  call    cs:__imp_WspIsRemoteInstance
0x18003c809  nop     dword ptr [rax+rax+00h]
0x18003c80e  test    al, al
0x18003c810  jz      short loc_18003C837
0x18003c812  mov     rax, [rbp+arg_30]
0x18003c816  mov     rdx, rsi
0x18003c819  mov     r9, [rbp+arg_20]
0x18003c81d  mov     rcx, rbx
0x18003c820  mov     r8, [rdi+40h]
0x18003c824  mov     [rsp+78h+var_58], rax
0x18003c829  call    cs:__imp_WspInvokeRemoteMethod
0x18003c830  nop     dword ptr [rax+rax+00h]
0x18003c835  jmp     short loc_18003C7EF
0x18003c837  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003c83c  lea     r8, aWspFileshareIn_7; "WSP_FileShare_Invoke_DeleteObject"
0x18003c843  lea     rdx, aEntering0; "Entering {0}"
0x18003c84a  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003c84e  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003c853  cmp     [rbp+var_30], 0
0x18003c858  jz      short loc_18003C883
0x18003c85a  mov     rax, [rbp+arg_30]
0x18003c85e  lea     r8, [rbp+var_20]
0x18003c862  lea     rdx, [rbp+var_40]
0x18003c866  mov     [rbp+var_10], rax
0x18003c86a  mov     [rbp+var_40], rbx
0x18003c86e  mov     [rbp+var_38], 0
0x18003c876  mov     [rbp+var_20], rbx
0x18003c87a  mov     [rbp+var_18], rdi
0x18003c87e  call    ??$ClassOperation@V_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_>(mi::MiContext &,_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_ const &)
0x18003c883  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003c888  lea     r8, aWspFileshareIn_7; "WSP_FileShare_Invoke_DeleteObject"
0x18003c88f  lea     rdx, aExiting0; "Exiting {0}"
0x18003c896  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003c89a  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003c89f  mov     ecx, [rbp+var_48]
0x18003c8a2  call    cs:__imp_WspProviderExit
0x18003c8a9  nop     dword ptr [rax+rax+00h]
0x18003c8ae  mov     rcx, [rbp+var_28]; this
0x18003c8b2  test    rcx, rcx
0x18003c8b5  jz      short loc_18003C8BC
0x18003c8b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c8bc  add     rsp, 78h
0x18003c8c0  pop     rdi
0x18003c8c1  pop     rsi
0x18003c8c2  pop     rbx
0x18003c8c3  pop     rbp
0x18003c8c4  retn
```
