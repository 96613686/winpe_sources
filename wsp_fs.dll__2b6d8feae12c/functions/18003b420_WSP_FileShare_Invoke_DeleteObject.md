# WSP_FileShare_Invoke_DeleteObject

- ea: `0x18003b420`
- end: `0x18003b557`
- name: `WSP_FileShare_Invoke_DeleteObject`
- size: `311`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000c284`
- `0x18000e6f4`
- `0x1800192f0`
- `0x180037f40`
- `0x180038874`
- `0x180038c58`
- `0x18003b420`
- `0x1800a9010`

## import_xrefs

- `MISpace!WspProviderExit` at `0x18003b53a`
- `MISpace!WspProviderExit` at `0x18003b53a`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b4c5`
- `MISpace!WspInvokeRemoteMethod` at `0x18003b4c5`
- `MISpace!WspIsRemoteInstance` at `0x18003b4a4`
- `MISpace!WspIsRemoteInstance` at `0x18003b4a4`
- `MISpace!WspProviderEnter` at `0x18003b46f`
- `MISpace!WspProviderEnter` at `0x18003b46f`

## string_xrefs

- `0x18003b4d4`: `WSP_FileShare_Invoke_DeleteObject`
- `0x18003b520`: `WSP_FileShare_Invoke_DeleteObject`

## pseudocode

```c
void __fastcall WSP_FileShare_Invoke_DeleteObject(
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
  cxl::TextWriter::WriteLine<wchar_t,char [34],>(
    (struct cxl::TraceManager *)((char *)v13 + 120),
    (wchar_t *)L"Entering {0}");
  if ( v18 )
  {
    v20[2] = a7;
    v17[0] = a2;
    v17[1] = 0;
    v20[0] = a2;
    v20[1] = v10;
    wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_>(
      v14,
      v17,
      v20);
  }
  v15 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [34],>(
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
0x18003b420  mov     [rsp-20h+arg_0], rcx
0x18003b425  push    rbp
0x18003b426  push    rbx
0x18003b427  push    rsi
0x18003b428  push    rdi
0x18003b429  mov     rbp, rsp
0x18003b42c  sub     rsp, 78h
0x18003b430  mov     rbx, rdx
0x18003b433  lea     r8, [rbp+arg_0]
0x18003b437  lea     rdx, [rbp+var_40]
0x18003b43b  mov     rsi, r9
0x18003b43e  call    ??$_Try_emplace@AEBQEAU_WSP_FileShare_Self@@$$V@?$map@PEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@U?$less@PEAU_WSP_FileShare_Self@@@3@V?$allocator@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_WSP_FileShare_Self@@V?$shared_ptr@V?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_WSP_FileShare_Self@@@Z; std::map<_WSP_FileShare_Self *,std::shared_ptr<wmi::WmiProviderClass<smapi::FileShareContext>>>::_Try_emplace<_WSP_FileShare_Self * const &,>(_WSP_FileShare_Self * const &)
0x18003b443  lea     rcx, [rbp+var_30]
0x18003b447  mov     rdx, [rax]
0x18003b44a  add     rdx, 28h ; '('
0x18003b44e  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18003b453  mov     rdi, [rbp+arg_28]
0x18003b457  lea     r9, [rbp+var_48]
0x18003b45b  mov     r8d, 1
0x18003b461  mov     [rbp+var_48], 0
0x18003b468  mov     rcx, rbx
0x18003b46b  mov     rdx, [rdi+40h]
0x18003b46f  call    cs:__imp_WspProviderEnter
0x18003b475  mov     edx, eax
0x18003b477  test    eax, eax
0x18003b479  jz      short loc_18003B4A0
0x18003b47b  test    rbx, rbx
0x18003b47e  jz      loc_18003B537
0x18003b484  mov     rax, [rbx]
0x18003b487  test    rax, rax
0x18003b48a  jz      loc_18003B537
0x18003b490  mov     rax, [rax]
0x18003b493  mov     rcx, rbx
0x18003b496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b49b  jmp     loc_18003B537
0x18003b4a0  mov     rcx, [rdi+40h]
0x18003b4a4  call    cs:__imp_WspIsRemoteInstance
0x18003b4aa  test    al, al
0x18003b4ac  jz      short loc_18003B4CF
0x18003b4ae  mov     rax, [rbp+arg_30]
0x18003b4b2  mov     rdx, rsi
0x18003b4b5  mov     r9, [rbp+arg_20]
0x18003b4b9  mov     rcx, rbx
0x18003b4bc  mov     r8, [rdi+40h]
0x18003b4c0  mov     [rsp+78h+var_58], rax
0x18003b4c5  call    cs:__imp_WspInvokeRemoteMethod
0x18003b4cb  mov     edx, eax
0x18003b4cd  jmp     short loc_18003B47B
0x18003b4cf  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b4d4  lea     r8, aWspFileshareIn_7; "WSP_FileShare_Invoke_DeleteObject"
0x18003b4db  lea     rdx, aEntering0; "Entering {0}"
0x18003b4e2  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b4e6  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003b4eb  cmp     [rbp+var_30], 0
0x18003b4f0  jz      short loc_18003B51B
0x18003b4f2  mov     rax, [rbp+arg_30]
0x18003b4f6  lea     r8, [rbp+var_20]
0x18003b4fa  lea     rdx, [rbp+var_40]
0x18003b4fe  mov     [rbp+var_10], rax
0x18003b502  mov     [rbp+var_40], rbx
0x18003b506  mov     [rbp+var_38], 0
0x18003b50e  mov     [rbp+var_20], rbx
0x18003b512  mov     [rbp+var_18], rdi
0x18003b516  call    ??$ClassOperation@V_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_@@@?$WmiProviderClass@VFileShareContext@smapi@@@wmi@@AEAAXAEAVMiContext@mi@@AEBV_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_@@@Z; wmi::WmiProviderClass<smapi::FileShareContext>::ClassOperation<_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_>(mi::MiContext &,_lambda_96b05d2dd9b1fde8aa5aa467f575e05f_ const &)
0x18003b51b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18003b520  lea     r8, aWspFileshareIn_7; "WSP_FileShare_Invoke_DeleteObject"
0x18003b527  lea     rdx, aExiting0; "Exiting {0}"
0x18003b52e  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18003b532  call    ??$WriteLine@_W$$BY0CC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [34],>(wchar_t const *,char const (&)[34])
0x18003b537  mov     ecx, [rbp+var_48]
0x18003b53a  call    cs:__imp_WspProviderExit
0x18003b540  mov     rcx, [rbp+var_28]; this
0x18003b544  test    rcx, rcx
0x18003b547  jz      short loc_18003B54E
0x18003b549  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b54e  add     rsp, 78h
0x18003b552  pop     rdi
0x18003b553  pop     rsi
0x18003b554  pop     rbx
0x18003b555  pop     rbp
0x18003b556  retn
```
