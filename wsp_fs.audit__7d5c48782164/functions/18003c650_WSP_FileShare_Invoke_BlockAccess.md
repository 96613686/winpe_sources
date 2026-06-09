# WSP_FileShare_Invoke_BlockAccess

- ea: `0x18003c650`
- end: `0x18003c786`
- name: `WSP_FileShare_Invoke_BlockAccess`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x180038e54`
- `0x180039aa8`
- `0x180039f98`
- `0x18003be1c`
- `0x18003c650`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003c762`
- `MISpace!WspProviderExit` at `0x18003c762`
- `MISpace!WspInvokeRemoteMethod` at `0x18003c6e9`
- `MISpace!WspInvokeRemoteMethod` at `0x18003c6e9`
- `MISpace!WspIsRemoteInstance` at `0x18003c6c2`
- `MISpace!WspIsRemoteInstance` at `0x18003c6c2`
- `MISpace!WspProviderEnter` at `0x18003c69f`
- `MISpace!WspProviderEnter` at `0x18003c69f`

## string_xrefs

- `0x18003c6fc`: `WSP_FileShare_Invoke_BlockAccess`
- `0x18003c748`: `WSP_FileShare_Invoke_BlockAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_BlockAccess(
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
  cxl::TextWriter::WriteLine<wchar_t,char [33],>(
    (struct cxl::TraceManager *)((char *)v12 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v17 )
  {
    v19[2] = a7;
    v16[0] = a2;
    v16[1] = 0;
    v19[0] = a2;
    v19[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_0231df34eb653dd4df0d150427b3c942_>(
      v13,
      v16,
      v19);
  }
  v14 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [33],>(
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
0x18003c650  mov     [rsp-20h+arg_0], rcx
0x18003c655  push    rbp
0x18003c656  push    rbx
0x18003c657  push    rsi
0x18003c658  push    rdi
0x18003c659  mov     rbp, rsp
0x18003c65c  sub     rsp, 78h
0x18003c660  mov     rbx, rdx
0x18003c663  lea     r8, [rbp+arg_0]
0x18003c667  lea     rdx, [rbp+var_40]
0x18003c66b  mov     rsi, r9
0x18003c66e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003c673  lea     rcx, [rbp+var_30]
0x18003c677  mov     rdx, [rax]
0x18003c67a  add     rdx, 28h ; '('
0x18003c67e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003c683  mov     rdi, [rbp+arg_28]
0x18003c687  lea     r9, [rbp+var_48]
0x18003c68b  mov     r8d, 1
0x18003c691  mov     [rbp+var_48], 0
0x18003c698  mov     rcx, rbx
0x18003c69b  mov     rdx, [rdi+40h]
0x18003c69f  call    cs:__imp_WspProviderEnter
0x18003c6a6  nop     dword ptr [rax+rax+00h]
0x18003c6ab  test    eax, eax
0x18003c6ad  jz      short loc_18003C6BE
0x18003c6af  mov     edx, eax; result
0x18003c6b1  mov     rcx, rbx; context
0x18003c6b4  call    MI_Context_PostResult_0
0x18003c6b9  jmp     loc_18003C75F
0x18003c6be  mov     rcx, [rdi+40h]
0x18003c6c2  call    cs:__imp_WspIsRemoteInstance
0x18003c6c9  nop     dword ptr [rax+rax+00h]
0x18003c6ce  test    al, al
0x18003c6d0  jz      short loc_18003C6F7
0x18003c6d2  mov     rax, [rbp+arg_30]
0x18003c6d6  mov     rdx, rsi
0x18003c6d9  mov     r9, [rbp+arg_20]
0x18003c6dd  mov     rcx, rbx
0x18003c6e0  mov     r8, [rdi+40h]
0x18003c6e4  mov     [rsp+78h+var_58], rax
0x18003c6e9  call    cs:__imp_WspInvokeRemoteMethod
0x18003c6f0  nop     dword ptr [rax+rax+00h]
0x18003c6f5  jmp     short loc_18003C6AF
0x18003c6f7  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003c6fc  lea     r8, aWspFileshareIn_6; "WSP_FileShare_Invoke_BlockAccess"
0x18003c703  lea     rdx, aEntering0; "Entering {0}"
0x18003c70a  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003c70e  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003c713  cmp     [rbp+var_30], 0
0x18003c718  jz      short loc_18003C743
0x18003c71a  mov     rax, [rbp+arg_30]
0x18003c71e  lea     r8, [rbp+var_20]
0x18003c722  lea     rdx, [rbp+var_40]
0x18003c726  mov     [rbp+var_10], rax
0x18003c72a  mov     [rbp+var_40], rbx
0x18003c72e  mov     [rbp+var_38], 0
0x18003c736  mov     [rbp+var_20], rbx
0x18003c73a  mov     [rbp+var_18], rdi
0x18003c73e  call    ??$ClassOperation@V_lambda_0231df34eb653dd4df0d150427b3c942_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_0231df34eb653dd4df0d150427b3c942_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_0231df34eb653dd4df0d150427b3c942_>(mi::MiContext &,_lambda_0231df34eb653dd4df0d150427b3c942_ const &)
0x18003c743  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003c748  lea     r8, aWspFileshareIn_6; "WSP_FileShare_Invoke_BlockAccess"
0x18003c74f  lea     rdx, aExiting0; "Exiting {0}"
0x18003c756  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003c75a  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003c75f  mov     ecx, [rbp+var_48]
0x18003c762  call    cs:__imp_WspProviderExit
0x18003c769  nop     dword ptr [rax+rax+00h]
0x18003c76e  mov     rcx, [rbp+var_28]; this
0x18003c772  test    rcx, rcx
0x18003c775  jz      short loc_18003C77C
0x18003c777  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c77c  add     rsp, 78h
0x18003c780  pop     rdi
0x18003c781  pop     rsi
0x18003c782  pop     rbx
0x18003c783  pop     rbp
0x18003c784  retn
```
