# LCIEGetEDPHostPolicyForUrl

- ea: `0x18011b91c`
- end: `0x18011bb29`
- name: `LCIEGetEDPHostPolicyForUrl`
- size: `525`
- prototype: `__int64 __fastcall(WCHAR *pwzURI, int, BSTR *, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011bb30`

## callees

- `0x180013fd0`
- `0x18003e100`
- `0x18008046c`
- `0x18008f4f8`
- `0x1800a6490`
- `0x18011adac`
- `0x18011ae84`
- `0x18011b23c`
- `0x18011b91c`
- `0x18011bdd4`
- `0x180126edc`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18011b973`
- `iertutil!CreateUri` at `0x18011b973`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b9ce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011ba82`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011bab9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b9ce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011ba82`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011bab9`
- `OLEAUT32!__imp_SysAllocString` at `0x18011b9e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18011ba9a`
- `OLEAUT32!__imp_SysAllocString` at `0x18011bad1`
- `OLEAUT32!__imp_SysAllocString` at `0x18011b9e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18011ba9a`
- `OLEAUT32!__imp_SysAllocString` at `0x18011bad1`
- `OLEAUT32!__imp_SysFreeString` at `0x18011baf3`
- `OLEAUT32!__imp_SysFreeString` at `0x18011baf3`

## pseudocode

```c
__int64 __fastcall LCIEGetEDPHostPolicyForUrl(WCHAR *pwzURI, int a2, BSTR *a3, _BYTE *a4)
{
  int EDPHostPolicyForFile; // ebx
  DWORD v9; // eax
  int v10; // eax
  const OLECHAR *CurrentEnterpriseID; // rax
  IUri *v12; // rdi
  HRESULT (__stdcall *GetPropertyBSTR)(IUri *, Uri_PROPERTY, BSTR *, DWORD); // rbx
  const OLECHAR *v14; // rax
  const OLECHAR *v15; // rax
  LPCWSTR wszServerName[2]; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  IUri *ppURI; // [rsp+88h] [rbp+48h] BYREF

  EDPHostPolicyForFile = 0;
  *a4 = 0;
  if ( a3 && BrowserUtilEdp::IsEdpEnforcementEnabled((BrowserUtilEdp *)pwzURI) )
  {
    ppURI = 0;
    v9 = HelperAddUriDefaultFlags(50342784, 4u);
    if ( CreateUri(pwzURI, v9, 0, &ppURI) < 0 )
      goto LABEL_26;
    v18 = 0;
    if ( ((unsigned int (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v18) )
      goto LABEL_26;
    if ( v18 == 9 )
    {
      EDPHostPolicyForFile = GetEDPHostPolicyForFile(ppURI, (__int64)a3);
    }
    else
    {
      v10 = IsEDPModeNeutralIUri(ppURI);
      if ( !a2 )
      {
        if ( v10 )
        {
          *a4 = 1;
          if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
          {
            CurrentEnterpriseID = (const OLECHAR *)GetCurrentEnterpriseID();
            *a3 = SysAllocString(CurrentEnterpriseID);
          }
        }
      }
      if ( *a4 )
        goto LABEL_26;
      if ( !UriUsesNetwork(ppURI) )
      {
        if ( !a2 )
          *a4 = 1;
        if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
        {
          v15 = (const OLECHAR *)GetCurrentEnterpriseID();
          *a3 = SysAllocString(v15);
        }
        goto LABEL_26;
      }
      v12 = ppURI;
      wszServerName[0] = 0;
      GetPropertyBSTR = ppURI->lpVtbl->GetPropertyBSTR;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (OLECHAR **)wszServerName,
        0);
      EDPHostPolicyForFile = ((__int64 (__fastcall *)(IUri *, __int64, LPCWSTR *))GetPropertyBSTR)(
                               v12,
                               6,
                               wszServerName);
      if ( !EDPHostPolicyForFile )
      {
        EDPHostPolicyForFile = NetworkIsolationGetEnterpriseIdSync(wszServerName[0], a3);
        if ( EDPHostPolicyForFile == -2147023436 )
          EDPHostPolicyForFile = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)wszServerName);
      if ( EDPHostPolicyForFile == -2147013895 )
      {
        if ( a2 )
        {
LABEL_25:
          SysFreeString(*a3);
          EDPHostPolicyForFile = 0;
          *a3 = 0;
          *a4 = 0;
          goto LABEL_26;
        }
        *a4 = 1;
        EDPHostPolicyForFile = 0;
        if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) )
        {
LABEL_26:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppURI);
          return (unsigned int)EDPHostPolicyForFile;
        }
        v14 = (const OLECHAR *)GetCurrentEnterpriseID();
        *a3 = SysAllocString(v14);
      }
    }
    if ( EDPHostPolicyForFile < 0 )
      goto LABEL_25;
    goto LABEL_26;
  }
  return (unsigned int)EDPHostPolicyForFile;
}

```

## disassembly

```asm
0x18011b91c  mov     [rsp-28h+arg_0], rbx
0x18011b921  push    rbp
0x18011b922  push    rsi
0x18011b923  push    rdi
0x18011b924  push    r14
0x18011b926  push    r15
0x18011b928  mov     rbp, rsp
0x18011b92b  sub     rsp, 40h
0x18011b92f  xor     ebx, ebx
0x18011b931  mov     r14, r9
0x18011b934  mov     [r9], bl
0x18011b937  mov     rsi, r8
0x18011b93a  mov     r15d, edx
0x18011b93d  mov     rdi, rcx
0x18011b940  test    r8, r8
0x18011b943  jz      loc_18011BB15
0x18011b949  call    ?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpEnforcementEnabled(void)
0x18011b94e  test    al, al
0x18011b950  jz      loc_18011BB15
0x18011b956  lea     edx, [rbx+4]; unsigned int
0x18011b959  mov     [rbp+ppURI], rbx
0x18011b95d  mov     ecx, 3002B80h; unsigned int
0x18011b962  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18011b967  mov     edx, eax; dwFlags
0x18011b969  lea     r9, [rbp+ppURI]; ppURI
0x18011b96d  mov     rcx, rdi; pwzURI
0x18011b970  xor     r8d, r8d; dwReserved
0x18011b973  call    cs:__imp_CreateUri
0x18011b97a  nop     dword ptr [rax+rax+00h]
0x18011b97f  test    eax, eax
0x18011b981  js      loc_18011BB0C
0x18011b987  mov     rcx, [rbp+ppURI]
0x18011b98b  lea     rdx, [rbp+arg_10]
0x18011b98f  mov     [rbp+arg_10], ebx
0x18011b992  mov     rax, [rcx]
0x18011b995  mov     rax, [rax+0C0h]
0x18011b99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011b9a1  test    eax, eax
0x18011b9a3  jnz     loc_18011BB0C
0x18011b9a9  cmp     [rbp+arg_10], 9
0x18011b9ad  mov     rcx, [rbp+ppURI]; struct IUri *
0x18011b9b1  jz      loc_18011BAE2
0x18011b9b7  call    ?IsEDPModeNeutralIUri@@YAHPEAUIUri@@@Z; IsEDPModeNeutralIUri(IUri *)
0x18011b9bc  test    r15d, r15d
0x18011b9bf  jnz     short loc_18011B9F5
0x18011b9c1  test    eax, eax
0x18011b9c3  jz      short loc_18011B9F5
0x18011b9c5  mov     ecx, 20000002h
0x18011b9ca  mov     byte ptr [r14], 1
0x18011b9ce  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b9d5  nop     dword ptr [rax+rax+00h]
0x18011b9da  test    al, al
0x18011b9dc  jz      short loc_18011B9F5
0x18011b9de  call    GetCurrentEnterpriseID
0x18011b9e3  mov     rcx, rax; psz
0x18011b9e6  call    cs:__imp_SysAllocString
0x18011b9ed  nop     dword ptr [rax+rax+00h]
0x18011b9f2  mov     [rsi], rax
0x18011b9f5  cmp     [r14], bl
0x18011b9f8  jnz     loc_18011BB0C
0x18011b9fe  mov     rcx, [rbp+ppURI]; struct IUri *
0x18011ba02  call    UriUsesNetwork
0x18011ba07  test    al, al
0x18011ba09  jz      loc_18011BAAB
0x18011ba0f  mov     rdi, [rbp+ppURI]
0x18011ba13  lea     rcx, [rbp+wszServerName]
0x18011ba17  mov     [rbp+wszServerName], rbx
0x18011ba1b  xor     edx, edx
0x18011ba1d  mov     rax, [rdi]
0x18011ba20  mov     rbx, [rax+18h]
0x18011ba24  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18011ba29  mov     r9d, 2
0x18011ba2f  lea     r8, [rbp+wszServerName]
0x18011ba33  mov     rcx, rdi
0x18011ba36  mov     rax, rbx
0x18011ba39  lea     edx, [r9+4]
0x18011ba3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ba42  mov     ebx, eax
0x18011ba44  test    eax, eax
0x18011ba46  jnz     short loc_18011BA61
0x18011ba48  mov     rcx, [rbp+wszServerName]; wszServerName
0x18011ba4c  mov     rdx, rsi
0x18011ba4f  call    NetworkIsolationGetEnterpriseIdSync
0x18011ba54  mov     ebx, eax
0x18011ba56  xor     eax, eax
0x18011ba58  cmp     ebx, 800705B4h
0x18011ba5e  cmovz   ebx, eax
0x18011ba61  lea     rcx, [rbp+wszServerName]
0x18011ba65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18011ba6a  cmp     ebx, 80072AF9h
0x18011ba70  jnz     short loc_18011BAEC
0x18011ba72  test    r15d, r15d
0x18011ba75  jnz     short loc_18011BAF0
0x18011ba77  mov     ecx, 20000002h
0x18011ba7c  mov     byte ptr [r14], 1
0x18011ba80  xor     ebx, ebx
0x18011ba82  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011ba89  nop     dword ptr [rax+rax+00h]
0x18011ba8e  test    al, al
0x18011ba90  jz      short loc_18011BB0C
0x18011ba92  call    GetCurrentEnterpriseID
0x18011ba97  mov     rcx, rax; psz
0x18011ba9a  call    cs:__imp_SysAllocString
0x18011baa1  nop     dword ptr [rax+rax+00h]
0x18011baa6  mov     [rsi], rax
0x18011baa9  jmp     short loc_18011BAEC
0x18011baab  test    r15d, r15d
0x18011baae  jnz     short loc_18011BAB4
0x18011bab0  mov     byte ptr [r14], 1
0x18011bab4  mov     ecx, 20000002h
0x18011bab9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011bac0  nop     dword ptr [rax+rax+00h]
0x18011bac5  test    al, al
0x18011bac7  jz      short loc_18011BB0C
0x18011bac9  call    GetCurrentEnterpriseID
0x18011bace  mov     rcx, rax; psz
0x18011bad1  call    cs:__imp_SysAllocString
0x18011bad8  nop     dword ptr [rax+rax+00h]
0x18011badd  mov     [rsi], rax
0x18011bae0  jmp     short loc_18011BB0C
0x18011bae2  mov     rdx, rsi
0x18011bae5  call    GetEDPHostPolicyForFile
0x18011baea  mov     ebx, eax
0x18011baec  test    ebx, ebx
0x18011baee  jns     short loc_18011BB0C
0x18011baf0  mov     rcx, [rsi]; bstrString
0x18011baf3  call    cs:__imp_SysFreeString
0x18011bafa  nop     dword ptr [rax+rax+00h]
0x18011baff  xor     ebx, ebx
0x18011bb01  mov     qword ptr [rsi], 0
0x18011bb08  mov     byte ptr [r14], 0
0x18011bb0c  lea     rcx, [rbp+ppURI]
0x18011bb10  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18011bb15  mov     eax, ebx
0x18011bb17  mov     rbx, [rsp+40h+arg_0]
0x18011bb1c  add     rsp, 40h
0x18011bb20  pop     r15
0x18011bb22  pop     r14
0x18011bb24  pop     rdi
0x18011bb25  pop     rsi
0x18011bb26  pop     rbp
0x18011bb27  retn
```
