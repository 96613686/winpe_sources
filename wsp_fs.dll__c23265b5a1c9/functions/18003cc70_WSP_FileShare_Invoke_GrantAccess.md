# WSP_FileShare_Invoke_GrantAccess

- ea: `0x18003cc70`
- end: `0x18003cda6`
- name: `WSP_FileShare_Invoke_GrantAccess`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c5c4`
- `0x18000eb18`
- `0x180019d00`
- `0x1800391dc`
- `0x180039aa8`
- `0x180039f98`
- `0x18003be1c`
- `0x18003cc70`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003cd82`
- `MISpace!WspProviderExit` at `0x18003cd82`
- `MISpace!WspInvokeRemoteMethod` at `0x18003cd09`
- `MISpace!WspInvokeRemoteMethod` at `0x18003cd09`
- `MISpace!WspIsRemoteInstance` at `0x18003cce2`
- `MISpace!WspIsRemoteInstance` at `0x18003cce2`
- `MISpace!WspProviderEnter` at `0x18003ccbf`
- `MISpace!WspProviderEnter` at `0x18003ccbf`

## string_xrefs

- `0x18003cd1c`: `WSP_FileShare_Invoke_GrantAccess`
- `0x18003cd68`: `WSP_FileShare_Invoke_GrantAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_GrantAccess(
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
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_9519f4677529ddcf48d9b929b85a37a6_>(
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
0x18003cc70  mov     [rsp-20h+arg_0], rcx
0x18003cc75  push    rbp
0x18003cc76  push    rbx
0x18003cc77  push    rsi
0x18003cc78  push    rdi
0x18003cc79  mov     rbp, rsp
0x18003cc7c  sub     rsp, 78h
0x18003cc80  mov     rbx, rdx
0x18003cc83  lea     r8, [rbp+arg_0]
0x18003cc87  lea     rdx, [rbp+var_40]
0x18003cc8b  mov     rsi, r9
0x18003cc8e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003cc93  lea     rcx, [rbp+var_30]
0x18003cc97  mov     rdx, [rax]
0x18003cc9a  add     rdx, 28h ; '('
0x18003cc9e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003cca3  mov     rdi, [rbp+arg_28]
0x18003cca7  lea     r9, [rbp+var_48]
0x18003ccab  mov     r8d, 1
0x18003ccb1  mov     [rbp+var_48], 0
0x18003ccb8  mov     rcx, rbx
0x18003ccbb  mov     rdx, [rdi+40h]
0x18003ccbf  call    cs:__imp_WspProviderEnter
0x18003ccc6  nop     dword ptr [rax+rax+00h]
0x18003cccb  test    eax, eax
0x18003cccd  jz      short loc_18003CCDE
0x18003cccf  mov     edx, eax; result
0x18003ccd1  mov     rcx, rbx; context
0x18003ccd4  call    MI_Context_PostResult_0
0x18003ccd9  jmp     loc_18003CD7F
0x18003ccde  mov     rcx, [rdi+40h]
0x18003cce2  call    cs:__imp_WspIsRemoteInstance
0x18003cce9  nop     dword ptr [rax+rax+00h]
0x18003ccee  test    al, al
0x18003ccf0  jz      short loc_18003CD17
0x18003ccf2  mov     rax, [rbp+arg_30]
0x18003ccf6  mov     rdx, rsi
0x18003ccf9  mov     r9, [rbp+arg_20]
0x18003ccfd  mov     rcx, rbx
0x18003cd00  mov     r8, [rdi+40h]
0x18003cd04  mov     [rsp+78h+var_58], rax
0x18003cd09  call    cs:__imp_WspInvokeRemoteMethod
0x18003cd10  nop     dword ptr [rax+rax+00h]
0x18003cd15  jmp     short loc_18003CCCF
0x18003cd17  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003cd1c  lea     r8, aWspFileshareIn_2; "WSP_FileShare_Invoke_GrantAccess"
0x18003cd23  lea     rdx, aEntering0; "Entering {0}"
0x18003cd2a  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003cd2e  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003cd33  cmp     [rbp+var_30], 0
0x18003cd38  jz      short loc_18003CD63
0x18003cd3a  mov     rax, [rbp+arg_30]
0x18003cd3e  lea     r8, [rbp+var_20]
0x18003cd42  lea     rdx, [rbp+var_40]
0x18003cd46  mov     [rbp+var_10], rax
0x18003cd4a  mov     [rbp+var_40], rbx
0x18003cd4e  mov     [rbp+var_38], 0
0x18003cd56  mov     [rbp+var_20], rbx
0x18003cd5a  mov     [rbp+var_18], rdi
0x18003cd5e  call    ??$ClassOperation@V_lambda_9519f4677529ddcf48d9b929b85a37a6_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_9519f4677529ddcf48d9b929b85a37a6_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_9519f4677529ddcf48d9b929b85a37a6_>(mi::MiContext &,_lambda_9519f4677529ddcf48d9b929b85a37a6_ const &)
0x18003cd63  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003cd68  lea     r8, aWspFileshareIn_2; "WSP_FileShare_Invoke_GrantAccess"
0x18003cd6f  lea     rdx, aExiting0; "Exiting {0}"
0x18003cd76  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003cd7a  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003cd7f  mov     ecx, [rbp+var_48]
0x18003cd82  call    cs:__imp_WspProviderExit
0x18003cd89  nop     dword ptr [rax+rax+00h]
0x18003cd8e  mov     rcx, [rbp+var_28]; this
0x18003cd92  test    rcx, rcx
0x18003cd95  jz      short loc_18003CD9C
0x18003cd97  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cd9c  add     rsp, 78h
0x18003cda0  pop     rdi
0x18003cda1  pop     rsi
0x18003cda2  pop     rbx
0x18003cda3  pop     rbp
0x18003cda4  retn
```
