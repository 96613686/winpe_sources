# WSP_FileShare_Invoke_BlockAccess

- ea: `0x18003b2e0`
- end: `0x18003b417`
- name: `WSP_FileShare_Invoke_BlockAccess`
- size: `311`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x180037b58`
- `0x180038770`
- `0x180038c58`
- `0x18003b2e0`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003b3fa`
- `MISpace!WspProviderExit` at `0x18003b3fa`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b385`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b385`
- `MISpace!WspIsRemoteInstance` at `0x18003b364`
- `MISpace!WspIsRemoteInstance` at `0x18003b364`
- `MISpace!WspProviderEnter` at `0x18003b32f`
- `MISpace!WspProviderEnter` at `0x18003b32f`

## string_xrefs

- `0x18003b394`: `WSP_FileShare_Invoke_BlockAccess`
- `0x18003b3e0`: `WSP_FileShare_Invoke_BlockAccess`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_BlockAccess(
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
  v9 = (_QWORD *)std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(
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
  cxl::TextWriter::WriteLine<wchar_t,char [33],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_0231df34eb653dd4df0d150427b3c942_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [33],>(
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
0x18003b2e0  mov     [rsp-20h+arg_0], rcx
0x18003b2e5  push    rbp
0x18003b2e6  push    rbx
0x18003b2e7  push    rsi
0x18003b2e8  push    rdi
0x18003b2e9  mov     rbp, rsp
0x18003b2ec  sub     rsp, 78h
0x18003b2f0  mov     rbx, rdx
0x18003b2f3  lea     r8, [rbp+arg_0]
0x18003b2f7  lea     rdx, [rbp+var_40]
0x18003b2fb  mov     rsi, r9
0x18003b2fe  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003b303  lea     rcx, [rbp+var_30]
0x18003b307  mov     rdx, [rax]
0x18003b30a  add     rdx, 28h ; '('
0x18003b30e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003b313  mov     rdi, [rbp+arg_28]
0x18003b317  lea     r9, [rbp+var_48]
0x18003b31b  mov     r8d, 1
0x18003b321  mov     [rbp+var_48], 0
0x18003b328  mov     rcx, rbx
0x18003b32b  mov     rdx, [rdi+40h]
0x18003b32f  call    cs:__imp_WspProviderEnter
0x18003b335  mov     edx, eax
0x18003b337  test    eax, eax
0x18003b339  jz      short loc_18003B360
0x18003b33b  test    rbx, rbx
0x18003b33e  jz      loc_18003B3F7
0x18003b344  mov     rax, [rbx]
0x18003b347  test    rax, rax
0x18003b34a  jz      loc_18003B3F7
0x18003b350  mov     rax, [rax]
0x18003b353  mov     rcx, rbx
0x18003b356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b35b  jmp     loc_18003B3F7
0x18003b360  mov     rcx, [rdi+40h]
0x18003b364  call    cs:__imp_WspIsRemoteInstance
0x18003b36a  test    al, al
0x18003b36c  jz      short loc_18003B38F
0x18003b36e  mov     rax, [rbp+arg_30]
0x18003b372  mov     rdx, rsi
0x18003b375  mov     r9, [rbp+arg_20]
0x18003b379  mov     rcx, rbx
0x18003b37c  mov     r8, [rdi+40h]
0x18003b380  mov     [rsp+78h+var_58], rax
0x18003b385  call    cs:__imp_WspInvokeRemoteMethod
0x18003b38b  mov     edx, eax
0x18003b38d  jmp     short loc_18003B33B
0x18003b38f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b394  lea     r8, aWspFileshareIn_6; "WSP_FileShare_Invoke_BlockAccess"
0x18003b39b  lea     rdx, aEntering0; "Entering {0}"
0x18003b3a2  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b3a6  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003b3ab  cmp     [rbp+var_30], 0
0x18003b3b0  jz      short loc_18003B3DB
0x18003b3b2  mov     rax, [rbp+arg_30]
0x18003b3b6  lea     r8, [rbp+var_20]
0x18003b3ba  lea     rdx, [rbp+var_40]
0x18003b3be  mov     [rbp+var_10], rax
0x18003b3c2  mov     [rbp+var_40], rbx
0x18003b3c6  mov     [rbp+var_38], 0
0x18003b3ce  mov     [rbp+var_20], rbx
0x18003b3d2  mov     [rbp+var_18], rdi
0x18003b3d6  call    ??$ClassOperation@V_lambda_0231df34eb653dd4df0d150427b3c942_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_0231df34eb653dd4df0d150427b3c942_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_0231df34eb653dd4df0d150427b3c942_>(mi::MiContext &,_lambda_0231df34eb653dd4df0d150427b3c942_ const &)
0x18003b3db  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b3e0  lea     r8, aWspFileshareIn_6; "WSP_FileShare_Invoke_BlockAccess"
0x18003b3e7  lea     rdx, aExiting0; "Exiting {0}"
0x18003b3ee  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b3f2  call    ??$WriteLine@_W$$BY0CB@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CB@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [33],>(wchar_t const *,char const (&)[33])
0x18003b3f7  mov     ecx, [rbp+var_48]
0x18003b3fa  call    cs:__imp_WspProviderExit
0x18003b400  mov     rcx, [rbp+var_28]; this
0x18003b404  test    rcx, rcx
0x18003b407  jz      short loc_18003B40E
0x18003b409  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b40e  add     rsp, 78h
0x18003b412  pop     rdi
0x18003b413  pop     rsi
0x18003b414  pop     rbx
0x18003b415  pop     rbp
0x18003b416  retn
```
