# WSP_FileServer_Invoke_DeleteObject

- ea: `0x180042210`
- end: `0x180042347`
- name: `WSP_FileServer_Invoke_DeleteObject`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x1800388b0`
- `0x180040674`
- `0x180040cf0`
- `0x180042210`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18004232a`
- `MISpace!WspProviderExit` at `0x18004232a`
- `MISpace!WspInvokeRemoteMethod` at `0x1800422b5`
- `MISpace!WspInvokeRemoteMethod` at `0x1800422b5`
- `MISpace!WspIsRemoteInstance` at `0x180042294`
- `MISpace!WspIsRemoteInstance` at `0x180042294`
- `MISpace!WspProviderEnter` at `0x18004225f`
- `MISpace!WspProviderEnter` at `0x18004225f`

## string_xrefs

- `0x1800422c4`: `WSP_FileServer_Invoke_DeleteObject`
- `0x180042310`: `WSP_FileServer_Invoke_DeleteObject`

## pseudocode

```c
void __fastcall WSP_FileServer_Invoke_DeleteObject(
        __int64 a1,
        void (__fastcall ***a2)(_QWORD, __int64),
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v9; // rax
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
  v9 = std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(
         a1,
         v17,
         &v21);
  std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(&v18, (_QWORD *)(*(_QWORD *)v9 + 40LL));
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
    wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_ea68974f042e76aec7e266829bfff008_>(
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
0x180042210  mov     [rsp-20h+arg_0], rcx
0x180042215  push    rbp
0x180042216  push    rbx
0x180042217  push    rsi
0x180042218  push    rdi
0x180042219  mov     rbp, rsp
0x18004221c  sub     rsp, 78h
0x180042220  mov     rbx, rdx
0x180042223  lea     r8, [rbp+arg_0]
0x180042227  lea     rdx, [rbp+var_40]
0x18004222b  mov     rsi, r9
0x18004222e  call    ??$_Try_emplace@AEBQEAU_WSP_FileServer_Self@@$$V@?$map@PEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileServer_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileServer_Self@@@Z; std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(_WSP_FileServer_Self * const &)
0x180042233  lea     rcx, [rbp+var_30]
0x180042237  mov     rdx, [rax]
0x18004223a  add     rdx, 28h ; '('
0x18004223e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x180042243  mov     rdi, [rbp+arg_28]
0x180042247  lea     r9, [rbp+var_48]
0x18004224b  mov     r8d, 1
0x180042251  mov     [rbp+var_48], 0
0x180042258  mov     rcx, rbx
0x18004225b  mov     rdx, [rdi+40h]
0x18004225f  call    cs:__imp_WspProviderEnter
0x180042265  mov     edx, eax
0x180042267  test    eax, eax
0x180042269  jz      short loc_180042290
0x18004226b  test    rbx, rbx
0x18004226e  jz      loc_180042327
0x180042274  mov     rax, [rbx]
0x180042277  test    rax, rax
0x18004227a  jz      loc_180042327
0x180042280  mov     rax, [rax]
0x180042283  mov     rcx, rbx
0x180042286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004228b  jmp     loc_180042327
0x180042290  mov     rcx, [rdi+40h]
0x180042294  call    cs:__imp_WspIsRemoteInstance
0x18004229a  test    al, al
0x18004229c  jz      short loc_1800422BF
0x18004229e  mov     rax, [rbp+arg_30]
0x1800422a2  mov     rdx, rsi
0x1800422a5  mov     r9, [rbp+arg_20]
0x1800422a9  mov     rcx, rbx
0x1800422ac  mov     r8, [rdi+40h]
0x1800422b0  mov     [rsp+78h+var_58], rax
0x1800422b5  call    cs:__imp_WspInvokeRemoteMethod
0x1800422bb  mov     edx, eax
0x1800422bd  jmp     short loc_18004226B
0x1800422bf  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800422c4  lea     r8, aWspFileserverI_1; "WSP_FileServer_Invoke_DeleteObject"
0x1800422cb  lea     rdx, aEntering0; "Entering {0}"
0x1800422d2  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x1800422d6  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x1800422db  cmp     [rbp+var_30], 0
0x1800422e0  jz      short loc_18004230B
0x1800422e2  mov     rax, [rbp+arg_30]
0x1800422e6  lea     r8, [rbp+var_20]
0x1800422ea  lea     rdx, [rbp+var_40]
0x1800422ee  mov     [rbp+var_10], rax
0x1800422f2  mov     [rbp+var_40], rbx
0x1800422f6  mov     [rbp+var_38], 0
0x1800422fe  mov     [rbp+var_20], rbx
0x180042302  mov     [rbp+var_18], rdi
0x180042306  call    ??$ClassOperation@V_lambda_ea68974f042e76aec7e266829bfff008_@@@?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_ea68974f042e76aec7e266829bfff008_@@@Z; wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_ea68974f042e76aec7e266829bfff008_>(mi::MiContext &,_lambda_ea68974f042e76aec7e266829bfff008_ const &)
0x18004230b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180042310  lea     r8, aWspFileserverI_1; "WSP_FileServer_Invoke_DeleteObject"
0x180042317  lea     rdx, aExiting0; "Exiting {0}"
0x18004231e  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x180042322  call    ??$WriteLine@_W$$BY0CD@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CD@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [35],>(wchar_t const *,char const (&)[35])
0x180042327  mov     ecx, [rbp+var_48]
0x18004232a  call    cs:__imp_WspProviderExit
0x180042330  mov     rcx, [rbp+var_28]; this
0x180042334  test    rcx, rcx
0x180042337  jz      short loc_18004233E
0x180042339  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004233e  add     rsp, 78h
0x180042342  pop     rdi
0x180042343  pop     rsi
0x180042344  pop     rbx
0x180042345  pop     rbp
0x180042346  retn
```
