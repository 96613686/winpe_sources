# WSP_FileServer_Invoke_DeleteObject

- ea: `0x180043540`
- end: `0x180043676`
- name: `WSP_FileServer_Invoke_DeleteObject`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x180039be8`
- `0x18003be1c`
- `0x18004198c`
- `0x180042010`
- `0x180043540`

## import_xrefs

- `MISpace!WspProviderExit` at `0x180043652`
- `MISpace!WspProviderExit` at `0x180043652`
- `MISpace!WspInvokeRemoteMethod` at `0x1800435d9`
- `MISpace!WspInvokeRemoteMethod` at `0x1800435d9`
- `MISpace!WspIsRemoteInstance` at `0x1800435b2`
- `MISpace!WspIsRemoteInstance` at `0x1800435b2`
- `MISpace!WspProviderEnter` at `0x18004358f`
- `MISpace!WspProviderEnter` at `0x18004358f`

## string_xrefs

- `0x1800435ec`: `WSP_FileServer_Invoke_DeleteObject`
- `0x180043638`: `WSP_FileServer_Invoke_DeleteObject`

## pseudocode

```c
void __fastcall WSP_FileServer_Invoke_DeleteObject(
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
  v9 = (_QWORD *)std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(
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
    wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_ea68974f042e76aec7e266829bfff008_>(
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
0x180043540  mov     [rsp-20h+arg_0], rcx
0x180043545  push    rbp
0x180043546  push    rbx
0x180043547  push    rsi
0x180043548  push    rdi
0x180043549  mov     rbp, rsp
0x18004354c  sub     rsp, 78h
0x180043550  mov     rbx, rdx
0x180043553  lea     r8, [rbp+arg_0]
0x180043557  lea     rdx, [rbp+var_40]
0x18004355b  mov     rsi, r9
0x18004355e  call    ??$_Try_emplace@AEBQEAU_WSP_FileServer_Self@@$$V@?$map@PEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileServer_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileServer_Self@@@Z; std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(_WSP_FileServer_Self * const &)
0x180043563  lea     rcx, [rbp+var_30]
0x180043567  mov     rdx, [rax]
0x18004356a  add     rdx, 28h ; '('
0x18004356e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x180043573  mov     rdi, [rbp+arg_28]
0x180043577  lea     r9, [rbp+var_48]
0x18004357b  mov     r8d, 1
0x180043581  mov     [rbp+var_48], 0
0x180043588  mov     rcx, rbx
0x18004358b  mov     rdx, [rdi+40h]
0x18004358f  call    cs:__imp_WspProviderEnter
0x180043596  nop     dword ptr [rax+rax+00h]
0x18004359b  test    eax, eax
0x18004359d  jz      short loc_1800435AE
0x18004359f  mov     edx, eax; result
0x1800435a1  mov     rcx, rbx; context
0x1800435a4  call    MI_Context_PostResult_0
0x1800435a9  jmp     loc_18004364F
0x1800435ae  mov     rcx, [rdi+40h]
0x1800435b2  call    cs:__imp_WspIsRemoteInstance
0x1800435b9  nop     dword ptr [rax+rax+00h]
0x1800435be  test    al, al
0x1800435c0  jz      short loc_1800435E7
0x1800435c2  mov     rax, [rbp+arg_30]
0x1800435c6  mov     rdx, rsi
0x1800435c9  mov     r9, [rbp+arg_20]
0x1800435cd  mov     rcx, rbx
0x1800435d0  mov     r8, [rdi+40h]
0x1800435d4  mov     [rsp+78h+var_58], rax
0x1800435d9  call    cs:__imp_WspInvokeRemoteMethod
0x1800435e0  nop     dword ptr [rax+rax+00h]
0x1800435e5  jmp     short loc_18004359F
0x1800435e7  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800435ec  lea     r8, aWspFileserverI_1; "WSP_FileServer_Invoke_DeleteObject"
0x1800435f3  lea     rdx, aEntering0; "Entering {0}"
0x1800435fa  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x1800435fe  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x180043603  cmp     [rbp+var_30], 0
0x180043608  jz      short loc_180043633
0x18004360a  mov     rax, [rbp+arg_30]
0x18004360e  lea     r8, [rbp+var_20]
0x180043612  lea     rdx, [rbp+var_40]
0x180043616  mov     [rbp+var_10], rax
0x18004361a  mov     [rbp+var_40], rbx
0x18004361e  mov     [rbp+var_38], 0
0x180043626  mov     [rbp+var_20], rbx
0x18004362a  mov     [rbp+var_18], rdi
0x18004362e  call    ??$ClassOperation@V_lambda_ea68974f042e76aec7e266829bfff008_@@@?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_ea68974f042e76aec7e266829bfff008_@@@Z; wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_ea68974f042e76aec7e266829bfff008_>(mi::MiContext &,_lambda_ea68974f042e76aec7e266829bfff008_ const &)
0x180043633  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180043638  lea     r8, aWspFileserverI_1; "WSP_FileServer_Invoke_DeleteObject"
0x18004363f  lea     rdx, aExiting0; "Exiting {0}"
0x180043646  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18004364a  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x18004364f  mov     ecx, [rbp+var_48]
0x180043652  call    cs:__imp_WspProviderExit
0x180043659  nop     dword ptr [rax+rax+00h]
0x18004365e  mov     rcx, [rbp+var_28]; this
0x180043662  test    rcx, rcx
0x180043665  jz      short loc_18004366C
0x180043667  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004366c  add     rsp, 78h
0x180043670  pop     rdi
0x180043671  pop     rsi
0x180043672  pop     rbx
0x180043673  pop     rbp
0x180043674  retn
```
