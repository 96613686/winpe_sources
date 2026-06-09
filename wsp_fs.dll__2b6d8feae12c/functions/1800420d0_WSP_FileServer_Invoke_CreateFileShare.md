# WSP_FileServer_Invoke_CreateFileShare

- ea: `0x1800420d0`
- end: `0x180042207`
- name: `WSP_FileServer_Invoke_CreateFileShare`
- size: `311`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x1800404e0`
- `0x180040ab4`
- `0x180040cf0`
- `0x1800420d0`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x1800421ea`
- `MISpace!WspProviderExit` at `0x1800421ea`
- `MISpace!WspInvokeRemoteMethod` at `0x180042175`
- `MISpace!WspInvokeRemoteMethod` at `0x180042175`
- `MISpace!WspIsRemoteInstance` at `0x180042154`
- `MISpace!WspIsRemoteInstance` at `0x180042154`
- `MISpace!WspProviderEnter` at `0x18004211f`
- `MISpace!WspProviderEnter` at `0x18004211f`

## string_xrefs

- `0x180042184`: `WSP_FileServer_Invoke_CreateFileShare`
- `0x1800421d0`: `WSP_FileServer_Invoke_CreateFileShare`

## pseudocode

```c
void __fastcall WSP_FileServer_Invoke_CreateFileShare(
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
  v9 = (_QWORD *)std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(
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
  cxl::TextWriter::WriteLine<wchar_t,char [38],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_941f312ef09c46ff43f1ace10ed0cf7e_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [38],>(
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
0x1800420d0  mov     [rsp-20h+arg_0], rcx
0x1800420d5  push    rbp
0x1800420d6  push    rbx
0x1800420d7  push    rsi
0x1800420d8  push    rdi
0x1800420d9  mov     rbp, rsp
0x1800420dc  sub     rsp, 78h
0x1800420e0  mov     rbx, rdx
0x1800420e3  lea     r8, [rbp+arg_0]
0x1800420e7  lea     rdx, [rbp+var_40]
0x1800420eb  mov     rsi, r9
0x1800420ee  call    ??$_Try_emplace@AEBQEAU_WSP_FileServer_Self@@$$V@?$map@PEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileServer_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileServer_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileServer_Self@@@Z; std::map<_WSP_FileServer_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileServerContext>>>::_Try_emplace<_WSP_FileServer_Self * const &,>(_WSP_FileServer_Self * const &)
0x1800420f3  lea     rcx, [rbp+var_30]
0x1800420f7  mov     rdx, [rax]
0x1800420fa  add     rdx, 28h ; '('
0x1800420fe  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x180042103  mov     rdi, [rbp+arg_28]
0x180042107  lea     r9, [rbp+var_48]
0x18004210b  mov     r8d, 1
0x180042111  mov     [rbp+var_48], 0
0x180042118  mov     rcx, rbx
0x18004211b  mov     rdx, [rdi+40h]
0x18004211f  call    cs:__imp_WspProviderEnter
0x180042125  mov     edx, eax
0x180042127  test    eax, eax
0x180042129  jz      short loc_180042150
0x18004212b  test    rbx, rbx
0x18004212e  jz      loc_1800421E7
0x180042134  mov     rax, [rbx]
0x180042137  test    rax, rax
0x18004213a  jz      loc_1800421E7
0x180042140  mov     rax, [rax]
0x180042143  mov     rcx, rbx
0x180042146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004214b  jmp     loc_1800421E7
0x180042150  mov     rcx, [rdi+40h]
0x180042154  call    cs:__imp_WspIsRemoteInstance
0x18004215a  test    al, al
0x18004215c  jz      short loc_18004217F
0x18004215e  mov     rax, [rbp+arg_30]
0x180042162  mov     rdx, rsi
0x180042165  mov     r9, [rbp+arg_20]
0x180042169  mov     rcx, rbx
0x18004216c  mov     r8, [rdi+40h]
0x180042170  mov     [rsp+78h+var_58], rax
0x180042175  call    cs:__imp_WspInvokeRemoteMethod
0x18004217b  mov     edx, eax
0x18004217d  jmp     short loc_18004212B
0x18004217f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180042184  lea     r8, aWspFileserverI_2; "WSP_FileServer_Invoke_CreateFileShare"
0x18004218b  lea     rdx, aEntering0; "Entering {0}"
0x180042192  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x180042196  call    ??$WriteLine@_W$$BY0CG@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CG@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [38],>(wchar_t const *,char const (&)[38])
0x18004219b  cmp     [rbp+var_30], 0
0x1800421a0  jz      short loc_1800421CB
0x1800421a2  mov     rax, [rbp+arg_30]
0x1800421a6  lea     r8, [rbp+var_20]
0x1800421aa  lea     rdx, [rbp+var_40]
0x1800421ae  mov     [rbp+var_10], rax
0x1800421b2  mov     [rbp+var_40], rbx
0x1800421b6  mov     [rbp+var_38], 0
0x1800421be  mov     [rbp+var_20], rbx
0x1800421c2  mov     [rbp+var_18], rdi
0x1800421c6  call    ??$ClassOperation@V_lambda_941f312ef09c46ff43f1ace10ed0cf7e_@@@?$WmiProviderClass@VFileServerContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_941f312ef09c46ff43f1ace10ed0cf7e_@@@Z; wmi::WmiProviderClass<smapi::FileServerContext>::ClassOperation<_lambda_941f312ef09c46ff43f1ace10ed0cf7e_>(mi::MiContext &,_lambda_941f312ef09c46ff43f1ace10ed0cf7e_ const &)
0x1800421cb  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800421d0  lea     r8, aWspFileserverI_2; "WSP_FileServer_Invoke_CreateFileShare"
0x1800421d7  lea     rdx, aExiting0; "Exiting {0}"
0x1800421de  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x1800421e2  call    ??$WriteLine@_W$$BY0CG@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CG@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [38],>(wchar_t const *,char const (&)[38])
0x1800421e7  mov     ecx, [rbp+var_48]
0x1800421ea  call    cs:__imp_WspProviderExit
0x1800421f0  mov     rcx, [rbp+var_28]; this
0x1800421f4  test    rcx, rcx
0x1800421f7  jz      short loc_1800421FE
0x1800421f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800421fe  add     rsp, 78h
0x180042202  pop     rdi
0x180042203  pop     rsi
0x180042204  pop     rbx
0x180042205  pop     rbp
0x180042206  retn
```
