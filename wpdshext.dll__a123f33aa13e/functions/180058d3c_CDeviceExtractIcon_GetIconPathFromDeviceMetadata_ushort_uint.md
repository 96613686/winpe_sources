# CDeviceExtractIcon::_GetIconPathFromDeviceMetadata(ushort *,uint)

- ea: `0x180058d3c`
- end: `0x180058ed7`
- name: `?_GetIconPathFromDeviceMetadata@CDeviceExtractIcon@@AEAAJPEAGI@Z`
- size: `411`
- prototype: `int(CDeviceExtractIcon *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800574b0`

## callees

- `0x180004110`
- `0x18002beb8`
- `0x18002ff5c`
- `0x180035590`
- `0x180058d3c`
- `0x180059a40`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058e35`
- `ole32!CoTaskMemFree` at `0x180058e6a`
- `ole32!CoTaskMemFree` at `0x180058e6a`
- `ole32!StringFromCLSID` at `0x180058dcb`
- `ole32!StringFromCLSID` at `0x180058dcb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeviceExtractIcon::_GetIconPathFromDeviceMetadata(
        CDeviceExtractIcon *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned __int64 v3; // rsi
  __int64 v6; // rcx
  HRESULT v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-28h] BYREF
  IID rclsid; // [rsp+50h] [rbp-20h] BYREF

  v3 = a3;
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v7 = CDeviceExtractIcon::_QueryProperty(v6, 1, (char *)this + 12, L"System.Devices.ContainerId", &v13);
  rclsid = 0;
  if ( v7 >= 0 )
    v7 = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v13 + 160LL))(v13, &rclsid);
  lpsz = 0;
  if ( v7 >= 0 )
    v7 = StringFromCLSID(&rclsid, &lpsz);
  v8 = 0;
  v12 = 0;
  if ( v7 >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    v7 = CDeviceExtractIcon::_QueryProperty(v9, 2, lpsz, L"System.Devices.Icon", &v12);
    v8 = v12;
  }
  string = 0;
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 152LL))(v8, &string);
    if ( v7 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( StringRawBuffer )
        v7 = StringCchCopyW(a2, v3, StringRawBuffer);
      else
        v7 = -2147467259;
    }
    if ( string )
      WindowsDeleteString(string);
  }
  CoTaskMemFree(lpsz);
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      187,
      WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
      (unsigned int)v7);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180058d3c  mov     [rsp-18h+arg_18], rbx
0x180058d41  push    rbp
0x180058d42  push    rsi
0x180058d43  push    rdi
0x180058d44  mov     rbp, rsp
0x180058d47  sub     rsp, 70h
0x180058d4b  mov     rax, cs:__security_cookie
0x180058d52  xor     rax, rsp
0x180058d55  mov     [rbp+var_10], rax
0x180058d59  mov     esi, r8d
0x180058d5c  mov     rdi, rdx
0x180058d5f  mov     rbx, rcx
0x180058d62  mov     [rbp+var_38], 0
0x180058d6a  lea     rcx, [rbp+var_38]
0x180058d6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058d73  lea     r8, [rbx+0Ch]
0x180058d77  lea     rax, [rbp+var_38]
0x180058d7b  mov     [rsp+70h+var_50], rax
0x180058d80  lea     r9, aSystemDevicesC; "System.Devices.ContainerId"
0x180058d87  mov     edx, 1
0x180058d8c  call    ?_QueryProperty@CDeviceExtractIcon@@AEAAJW4PnpObjectType@Pnp@Enumeration@Devices@Windows@@PEBG1PEAPEAUIPropertyValue@Foundation@6@@Z; CDeviceExtractIcon::_QueryProperty(Windows::Devices::Enumeration::Pnp::PnpObjectType,ushort const *,ushort const *,Windows::Foundation::IPropertyValue * *)
0x180058d91  mov     ebx, eax
0x180058d93  xorps   xmm0, xmm0
0x180058d96  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180058d9a  test    eax, eax
0x180058d9c  js      short loc_180058DB7
0x180058d9e  mov     rcx, [rbp+var_38]
0x180058da2  mov     rax, [rcx]
0x180058da5  lea     rdx, [rbp+rclsid]
0x180058da9  mov     rax, [rax+0A0h]
0x180058db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058db5  mov     ebx, eax
0x180058db7  mov     [rbp+lpsz], 0
0x180058dbf  test    ebx, ebx
0x180058dc1  js      short loc_180058DD3
0x180058dc3  lea     rdx, [rbp+lpsz]; lplpsz
0x180058dc7  lea     rcx, [rbp+rclsid]; rclsid
0x180058dcb  call    cs:__imp_StringFromCLSID
0x180058dd1  mov     ebx, eax
0x180058dd3  xor     ecx, ecx
0x180058dd5  mov     [rbp+var_40], rcx
0x180058dd9  test    ebx, ebx
0x180058ddb  js      short loc_180058E0A
0x180058ddd  lea     rcx, [rbp+var_40]
0x180058de1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058de6  lea     rax, [rbp+var_40]
0x180058dea  mov     [rsp+70h+var_50], rax
0x180058def  lea     r9, aSystemDevicesI; "System.Devices.Icon"
0x180058df6  mov     r8, [rbp+lpsz]
0x180058dfa  mov     edx, 2
0x180058dff  call    ?_QueryProperty@CDeviceExtractIcon@@AEAAJW4PnpObjectType@Pnp@Enumeration@Devices@Windows@@PEBG1PEAPEAUIPropertyValue@Foundation@6@@Z; CDeviceExtractIcon::_QueryProperty(Windows::Devices::Enumeration::Pnp::PnpObjectType,ushort const *,ushort const *,Windows::Foundation::IPropertyValue * *)
0x180058e04  mov     ebx, eax
0x180058e06  mov     rcx, [rbp+var_40]
0x180058e0a  mov     [rbp+string], 0
0x180058e12  test    ebx, ebx
0x180058e14  js      short loc_180058E66
0x180058e16  mov     rax, [rcx]
0x180058e19  lea     rdx, [rbp+string]
0x180058e1d  mov     rax, [rax+98h]
0x180058e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e29  mov     ebx, eax
0x180058e2b  test    eax, eax
0x180058e2d  js      short loc_180058E57
0x180058e2f  xor     edx, edx; length
0x180058e31  mov     rcx, [rbp+string]; string
0x180058e35  call    cs:__imp_WindowsGetStringRawBuffer
0x180058e3b  test    rax, rax
0x180058e3e  jnz     short loc_180058E47
0x180058e40  mov     ebx, 80004005h
0x180058e45  jmp     short loc_180058E57
0x180058e47  mov     rdx, rsi; unsigned __int64
0x180058e4a  mov     r8, rax; unsigned __int16 *
0x180058e4d  mov     rcx, rdi; unsigned __int16 *
0x180058e50  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058e55  mov     ebx, eax
0x180058e57  mov     rcx, [rbp+string]; string
0x180058e5b  test    rcx, rcx
0x180058e5e  jz      short loc_180058E66
0x180058e60  call    cs:__imp_WindowsDeleteString
0x180058e66  mov     rcx, [rbp+lpsz]; pv
0x180058e6a  call    cs:__imp_CoTaskMemFree
0x180058e70  test    ebx, ebx
0x180058e72  jns     short loc_180058EA6
0x180058e74  lea     rax, WPP_GLOBAL_Control
0x180058e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058e82  cmp     rcx, rax
0x180058e85  jz      short loc_180058EA6
0x180058e87  test    byte ptr [rcx+1Ch], 2
0x180058e8b  jz      short loc_180058EA6
0x180058e8d  mov     edx, 0BBh
0x180058e92  mov     r9d, ebx
0x180058e95  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180058e9c  mov     rcx, [rcx+10h]
0x180058ea0  call    WPP_SF_d
0x180058ea5  nop
0x180058ea6  lea     rcx, [rbp+var_40]
0x180058eaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058eaf  nop
0x180058eb0  lea     rcx, [rbp+var_38]
0x180058eb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058eb9  mov     eax, ebx
0x180058ebb  mov     rcx, [rbp+var_10]
0x180058ebf  xor     rcx, rsp; StackCookie
0x180058ec2  call    __security_check_cookie
0x180058ec7  mov     rbx, [rsp+70h+arg_18]
0x180058ecf  add     rsp, 70h
0x180058ed3  pop     rdi
0x180058ed4  pop     rsi
0x180058ed5  pop     rbp
0x180058ed6  retn
```
