# CTDCCtl::SecurityMatchAllowDomainList(void)

- ea: `0x180008d70`
- end: `0x180008e2f`
- name: `?SecurityMatchAllowDomainList@CTDCCtl@@EEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(CTDCCtl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005bd4`
- `0x180008d70`
- `0x18000e524`
- `0x180014270`

## import_xrefs

- `urlmon!CoInternetParseUrl` at `0x180008de2`
- `urlmon!CoInternetParseUrl` at `0x180008de2`
- `ole32!CoTaskMemFree` at `0x180008e06`
- `ole32!CoTaskMemFree` at `0x180008e06`

## pseudocode

```c
__int64 __fastcall CTDCCtl::SecurityMatchAllowDomainList(CTDCCtl *this)
{
  struct IOleClientSite *v2; // rcx
  HRESULT HostURL; // ebx
  DWORD cchResult; // [rsp+40h] [rbp-228h] BYREF
  LPCWSTR pwzUrl; // [rsp+48h] [rbp-220h] BYREF
  WCHAR pszResult[256]; // [rsp+50h] [rbp-218h] BYREF

  cchResult = 256;
  v2 = (struct IOleClientSite *)*((_QWORD *)this + 4);
  pwzUrl = 0;
  HostURL = GetHostURL(v2, (unsigned __int16 **)&pwzUrl);
  if ( HostURL >= 0 )
  {
    HostURL = CoInternetParseUrl(pwzUrl, PARSE_DOMAIN, 0, pszResult, cchResult, &cchResult, 0);
    if ( HostURL >= 0 )
      HostURL = CTDCUnify::MatchAllowDomainList(*((CTDCUnify **)this + 71), pszResult);
  }
  CoTaskMemFree((LPVOID)pwzUrl);
  return (unsigned int)HostURL;
}

```

## disassembly

```asm
0x180008d70  mov     [rsp+arg_8], rbx
0x180008d75  push    rdi
0x180008d76  sub     rsp, 260h
0x180008d7d  mov     rax, cs:__security_cookie
0x180008d84  xor     rax, rsp
0x180008d87  mov     [rsp+268h+var_18], rax
0x180008d8f  mov     rdi, rcx
0x180008d92  mov     [rsp+268h+var_228], 100h
0x180008d9a  mov     rcx, [rcx+20h]; struct IOleClientSite *
0x180008d9e  lea     rdx, [rsp+268h+pwzUrl]; unsigned __int16 **
0x180008da3  mov     [rsp+268h+pwzUrl], 0
0x180008dac  call    ?GetHostURL@@YAJPEAUIOleClientSite@@PEAPEAG@Z; GetHostURL(IOleClientSite *,ushort * *)
0x180008db1  mov     ebx, eax
0x180008db3  test    eax, eax
0x180008db5  js      short loc_180008E01
0x180008db7  mov     rcx, [rsp+268h+pwzUrl]; pwzUrl
0x180008dbc  lea     rax, [rsp+268h+var_228]
0x180008dc1  xor     r8d, r8d; dwFlags
0x180008dc4  mov     [rsp+268h+dwReserved], 0; dwReserved
0x180008dcc  mov     [rsp+268h+pcchResult], rax; pcchResult
0x180008dd1  lea     r9, [rsp+268h+pszResult]; pszResult
0x180008dd6  mov     eax, [rsp+268h+var_228]
0x180008dda  mov     [rsp+268h+cchResult], eax; cchResult
0x180008dde  lea     edx, [r8+0Fh]; ParseAction
0x180008de2  call    cs:__imp_CoInternetParseUrl
0x180008de8  mov     ebx, eax
0x180008dea  test    eax, eax
0x180008dec  js      short loc_180008E01
0x180008dee  mov     rcx, [rdi+238h]; this
0x180008df5  lea     rdx, [rsp+268h+pszResult]; unsigned __int16 *
0x180008dfa  call    ?MatchAllowDomainList@CTDCUnify@@QEAAJPEBG@Z; CTDCUnify::MatchAllowDomainList(ushort const *)
0x180008dff  mov     ebx, eax
0x180008e01  mov     rcx, [rsp+268h+pwzUrl]; pv
0x180008e06  call    cs:__imp_CoTaskMemFree
0x180008e0c  mov     eax, ebx
0x180008e0e  mov     rcx, [rsp+268h+var_18]
0x180008e16  xor     rcx, rsp; StackCookie
0x180008e19  call    __security_check_cookie
0x180008e1e  mov     rbx, [rsp+268h+arg_8]
0x180008e26  add     rsp, 260h
0x180008e2d  pop     rdi
0x180008e2e  retn
```
