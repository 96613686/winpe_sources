# WSP_FileShare_Invoke_GetAccessControlEntries

- ea: `0x18003b690`
- end: `0x18003b7c7`
- name: `WSP_FileShare_Invoke_GetAccessControlEntries`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x1800380d4`
- `0x180038930`
- `0x180038c58`
- `0x18003b690`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003b7aa`
- `MISpace!WspProviderExit` at `0x18003b7aa`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b735`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b735`
- `MISpace!WspIsRemoteInstance` at `0x18003b714`
- `MISpace!WspIsRemoteInstance` at `0x18003b714`
- `MISpace!WspProviderEnter` at `0x18003b6df`
- `MISpace!WspProviderEnter` at `0x18003b6df`

## string_xrefs

- `0x18003b744`: `WSP_FileShare_Invoke_GetAccessControlEntries`
- `0x18003b790`: `WSP_FileShare_Invoke_GetAccessControlEntries`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_GetAccessControlEntries(
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
  v9 = std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(
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
  cxl::TextWriter::WriteLine<wchar_t,char [45],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_e3fc6eb21050ecb0736c7706b0831c8c_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [45],>(
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
0x18003b690  mov     [rsp-20h+arg_0], rcx
0x18003b695  push    rbp
0x18003b696  push    rbx
0x18003b697  push    rsi
0x18003b698  push    rdi
0x18003b699  mov     rbp, rsp
0x18003b69c  sub     rsp, 78h
0x18003b6a0  mov     rbx, rdx
0x18003b6a3  lea     r8, [rbp+arg_0]
0x18003b6a7  lea     rdx, [rbp+var_40]
0x18003b6ab  mov     rsi, r9
0x18003b6ae  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003b6b3  lea     rcx, [rbp+var_30]
0x18003b6b7  mov     rdx, [rax]
0x18003b6ba  add     rdx, 28h ; '('
0x18003b6be  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003b6c3  mov     rdi, [rbp+arg_28]
0x18003b6c7  lea     r9, [rbp+var_48]
0x18003b6cb  mov     r8d, 1
0x18003b6d1  mov     [rbp+var_48], 0
0x18003b6d8  mov     rcx, rbx
0x18003b6db  mov     rdx, [rdi+40h]
0x18003b6df  call    cs:__imp_WspProviderEnter
0x18003b6e5  mov     edx, eax
0x18003b6e7  test    eax, eax
0x18003b6e9  jz      short loc_18003B710
0x18003b6eb  test    rbx, rbx
0x18003b6ee  jz      loc_18003B7A7
0x18003b6f4  mov     rax, [rbx]
0x18003b6f7  test    rax, rax
0x18003b6fa  jz      loc_18003B7A7
0x18003b700  mov     rax, [rax]
0x18003b703  mov     rcx, rbx
0x18003b706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b70b  jmp     loc_18003B7A7
0x18003b710  mov     rcx, [rdi+40h]
0x18003b714  call    cs:__imp_WspIsRemoteInstance
0x18003b71a  test    al, al
0x18003b71c  jz      short loc_18003B73F
0x18003b71e  mov     rax, [rbp+arg_30]
0x18003b722  mov     rdx, rsi
0x18003b725  mov     r9, [rbp+arg_20]
0x18003b729  mov     rcx, rbx
0x18003b72c  mov     r8, [rdi+40h]
0x18003b730  mov     [rsp+78h+var_58], rax
0x18003b735  call    cs:__imp_WspInvokeRemoteMethod
0x18003b73b  mov     edx, eax
0x18003b73d  jmp     short loc_18003B6EB
0x18003b73f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b744  lea     r8, aWspFileshareIn_5; "WSP_FileShare_Invoke_GetAccessControlEn"...
0x18003b74b  lea     rdx, aEntering0; "Entering {0}"
0x18003b752  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b756  call    ??$WriteLine@_W$$BY0CN@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CN@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [45],>(wchar_t const *,char const (&)[45])
0x18003b75b  cmp     [rbp+var_30], 0
0x18003b760  jz      short loc_18003B78B
0x18003b762  mov     rax, [rbp+arg_30]
0x18003b766  lea     r8, [rbp+var_20]
0x18003b76a  lea     rdx, [rbp+var_40]
0x18003b76e  mov     [rbp+var_10], rax
0x18003b772  mov     [rbp+var_40], rbx
0x18003b776  mov     [rbp+var_38], 0
0x18003b77e  mov     [rbp+var_20], rbx
0x18003b782  mov     [rbp+var_18], rdi
0x18003b786  call    ??$ClassOperation@V_lambda_e3fc6eb21050ecb0736c7706b0831c8c_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_e3fc6eb21050ecb0736c7706b0831c8c_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_e3fc6eb21050ecb0736c7706b0831c8c_>(mi::MiContext &,_lambda_e3fc6eb21050ecb0736c7706b0831c8c_ const &)
0x18003b78b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b790  lea     r8, aWspFileshareIn_5; "WSP_FileShare_Invoke_GetAccessControlEn"...
0x18003b797  lea     rdx, aExiting0; "Exiting {0}"
0x18003b79e  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b7a2  call    ??$WriteLine@_W$$BY0CN@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CN@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [45],>(wchar_t const *,char const (&)[45])
0x18003b7a7  mov     ecx, [rbp+var_48]
0x18003b7aa  call    cs:__imp_WspProviderExit
0x18003b7b0  mov     rcx, [rbp+var_28]; this
0x18003b7b4  test    rcx, rcx
0x18003b7b7  jz      short loc_18003B7BE
0x18003b7b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b7be  add     rsp, 78h
0x18003b7c2  pop     rdi
0x18003b7c3  pop     rsi
0x18003b7c4  pop     rbx
0x18003b7c5  pop     rbp
0x18003b7c6  retn
```
