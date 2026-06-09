# WSP_FileServer_Invoke_CreateFileShare

- ea: `0x180043400`
- end: `0x180043536`
- name: `WSP_FileServer_Invoke_CreateFileShare`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x18003be1c`
- `0x1800417f0`
- `0x180041de0`
- `0x180042010`
- `0x180043400`

## import_xrefs

- `MISpace!WspProviderExit` at `0x180043512`
- `MISpace!WspProviderExit` at `0x180043512`
- `MISpace!WspInvokeRemoteMethod` at `0x180043499`
- `MISpace!WspInvokeRemoteMethod` at `0x180043499`
- `MISpace!WspIsRemoteInstance` at `0x180043472`
- `MISpace!WspIsRemoteInstance` at `0x180043472`
- `MISpace!WspProviderEnter` at `0x18004344f`
- `MISpace!WspProviderEnter` at `0x18004344f`

## string_xrefs

- `0x1800434ac`: `WSP_FileServer_Invoke_CreateFileShare`
- `0x1800434f8`: `WSP_FileServer_Invoke_CreateFileShare`

## pseudocode

```c
void __fastcall WSP_FileServer_Invoke_CreateFileShare(
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
  cxl::TextWriter::WriteLine<wchar_t,char [38],>(
    (struct cxl::TraceManager *)((char *)v12 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v17 )
  {
    v19[2] = a7;
    v16[0] = a2;
    v16[1] = 0;
    v19[0] = a2;
    v19[1] = v10;
    wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_941f312ef09c46ff43f1ace10ed0cf7e_>(
      v13,
      v16,
      v19);
  }
  v14 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [38],>(
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
0x180043400  mov     [rsp-20h+arg_0], rcx
0x180043405  push    rbp
0x180043406  push    rbx
0x180043407  push    rsi
0x180043408  push    rdi
0x180043409  mov     rbp, rsp
0x18004340c  sub     rsp, 78h
0x180043410  mov     rbx, rdx
0x180043413  lea     r8, [rbp+arg_0]
0x180043417  lea     rdx, [rbp+var_40]
0x18004341b  mov     rsi, r9
0x18004341e  call    ??$_Try_emplace@AEBQEAU_WSP_FileServer_Self@@$$V@?$map@PEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileServer_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileServer_Self@@@Z; std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(_WSP_FileServer_Self * const &)
0x180043423  lea     rcx, [rbp+var_30]
0x180043427  mov     rdx, [rax]
0x18004342a  add     rdx, 28h ; '('
0x18004342e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x180043433  mov     rdi, [rbp+arg_28]
0x180043437  lea     r9, [rbp+var_48]
0x18004343b  mov     r8d, 1
0x180043441  mov     [rbp+var_48], 0
0x180043448  mov     rcx, rbx
0x18004344b  mov     rdx, [rdi+40h]
0x18004344f  call    cs:__imp_WspProviderEnter
0x180043456  nop     dword ptr [rax+rax+00h]
0x18004345b  test    eax, eax
0x18004345d  jz      short loc_18004346E
0x18004345f  mov     edx, eax; result
0x180043461  mov     rcx, rbx; context
0x180043464  call    MI_Context_PostResult_0
0x180043469  jmp     loc_18004350F
0x18004346e  mov     rcx, [rdi+40h]
0x180043472  call    cs:__imp_WspIsRemoteInstance
0x180043479  nop     dword ptr [rax+rax+00h]
0x18004347e  test    al, al
0x180043480  jz      short loc_1800434A7
0x180043482  mov     rax, [rbp+arg_30]
0x180043486  mov     rdx, rsi
0x180043489  mov     r9, [rbp+arg_20]
0x18004348d  mov     rcx, rbx
0x180043490  mov     r8, [rdi+40h]
0x180043494  mov     [rsp+78h+var_58], rax
0x180043499  call    cs:__imp_WspInvokeRemoteMethod
0x1800434a0  nop     dword ptr [rax+rax+00h]
0x1800434a5  jmp     short loc_18004345F
0x1800434a7  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800434ac  lea     r8, aWspFileserverI_2; "WSP_FileServer_Invoke_CreateFileShare"
0x1800434b3  lea     rdx, aEntering0; "Entering {0}"
0x1800434ba  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x1800434be  call    ??$WriteLine@_W$$BY0CG@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CG@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [38],>(wchar_t const *,char const (&)[38])
0x1800434c3  cmp     [rbp+var_30], 0
0x1800434c8  jz      short loc_1800434F3
0x1800434ca  mov     rax, [rbp+arg_30]
0x1800434ce  lea     r8, [rbp+var_20]
0x1800434d2  lea     rdx, [rbp+var_40]
0x1800434d6  mov     [rbp+var_10], rax
0x1800434da  mov     [rbp+var_40], rbx
0x1800434de  mov     [rbp+var_38], 0
0x1800434e6  mov     [rbp+var_20], rbx
0x1800434ea  mov     [rbp+var_18], rdi
0x1800434ee  call    ??$ClassOperation@V_lambda_941f312ef09c46ff43f1ace10ed0cf7e_@@@?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_941f312ef09c46ff43f1ace10ed0cf7e_@@@Z; wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_941f312ef09c46ff43f1ace10ed0cf7e_>(mi::MiContext &,_lambda_941f312ef09c46ff43f1ace10ed0cf7e_ const &)
0x1800434f3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800434f8  lea     r8, aWspFileserverI_2; "WSP_FileServer_Invoke_CreateFileShare"
0x1800434ff  lea     rdx, aExiting0; "Exiting {0}"
0x180043506  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18004350a  call    ??$WriteLine@_W$$BY0CG@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CG@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [38],>(wchar_t const *,char const (&)[38])
0x18004350f  mov     ecx, [rbp+var_48]
0x180043512  call    cs:__imp_WspProviderExit
0x180043519  nop     dword ptr [rax+rax+00h]
0x18004351e  mov     rcx, [rbp+var_28]; this
0x180043522  test    rcx, rcx
0x180043525  jz      short loc_18004352C
0x180043527  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004352c  add     rsp, 78h
0x180043530  pop     rdi
0x180043531  pop     rsi
0x180043532  pop     rbx
0x180043533  pop     rbp
0x180043534  retn
```
