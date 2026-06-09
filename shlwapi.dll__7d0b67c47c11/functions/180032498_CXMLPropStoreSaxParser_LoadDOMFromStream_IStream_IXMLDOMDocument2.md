# CXMLPropStoreSaxParser::_LoadDOMFromStream(IStream *,IXMLDOMDocument2 * *)

- ea: `0x180032498`
- end: `0x18003255e`
- name: `?_LoadDOMFromStream@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *__hidden this, struct IStream *, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800301f0`
- `0x1800321ec`

## callees

- `0x180012550`
- `0x180023940`
- `0x180032498`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800324f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800324f3`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_LoadDOMFromStream(
        CXMLPropStoreSaxParser *this,
        struct IStream *a2,
        struct IXMLDOMDocument2 **a3)
{
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF

  *a3 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&ppv);
  v5 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_7fd52380_4e07_101b_ae2d_08002b2ec713, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, struct IStream *))(*(_QWORD *)ppv + 40LL))(ppv, a2);
    if ( v5 >= 0 )
      v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IXMLDOMDocument2 **))ppv)(
             ppv,
             &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
             a3);
  }
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032498  mov     r11, rsp
0x18003249b  mov     [r11+8], rbx
0x18003249f  mov     [r11+20h], rsi
0x1800324a3  push    rdi
0x1800324a4  sub     rsp, 40h
0x1800324a8  mov     rax, cs:__security_cookie
0x1800324af  xor     rax, rsp
0x1800324b2  mov     [rsp+48h+var_10], rax
0x1800324b7  lea     rcx, [r11-18h]
0x1800324bb  mov     qword ptr [r8], 0
0x1800324c2  mov     rdi, r8
0x1800324c5  mov     qword ptr [r11-18h], 0
0x1800324cd  mov     rsi, rdx
0x1800324d0  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x1800324d5  xor     edx, edx; pUnkOuter
0x1800324d7  lea     rax, [rsp+48h+var_18]
0x1800324dc  lea     r9, _GUID_7fd52380_4e07_101b_ae2d_08002b2ec713; riid
0x1800324e3  mov     [rsp+48h+ppv], rax; ppv
0x1800324e8  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800324ef  lea     r8d, [rdx+1]; dwClsContext
0x1800324f3  call    cs:__imp_CoCreateInstance
0x1800324f9  mov     ebx, eax
0x1800324fb  test    eax, eax
0x1800324fd  js      short loc_180032535
0x1800324ff  mov     rcx, [rsp+48h+var_18]
0x180032504  mov     rdx, rsi
0x180032507  mov     rax, [rcx]
0x18003250a  mov     rax, [rax+28h]
0x18003250e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032513  mov     ebx, eax
0x180032515  test    eax, eax
0x180032517  js      short loc_180032535
0x180032519  mov     rcx, [rsp+48h+var_18]
0x18003251e  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x180032525  mov     r8, rdi
0x180032528  mov     rax, [rcx]
0x18003252b  mov     rax, [rax]
0x18003252e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032533  mov     ebx, eax
0x180032535  lea     rcx, [rsp+48h+var_18]
0x18003253a  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18003253f  mov     eax, ebx
0x180032541  mov     rcx, [rsp+48h+var_10]
0x180032546  xor     rcx, rsp; StackCookie
0x180032549  call    __security_check_cookie
0x18003254e  mov     rbx, [rsp+48h+arg_0]
0x180032553  mov     rsi, [rsp+48h+arg_18]
0x180032558  add     rsp, 40h
0x18003255c  pop     rdi
0x18003255d  retn
```
