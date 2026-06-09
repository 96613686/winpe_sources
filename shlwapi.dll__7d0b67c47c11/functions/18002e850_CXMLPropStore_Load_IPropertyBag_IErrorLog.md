# CXMLPropStore::Load(IPropertyBag *,IErrorLog *)

- ea: `0x18002e850`
- end: `0x18002e94c`
- name: `?Load@CXMLPropStore@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `252`
- prototype: `int(CXMLPropStore *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012550`
- `0x18002d55c`
- `0x18002d858`
- `0x18002e850`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e8e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e8e6`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18002e90e`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18002e90e`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::Load(HKEY *this, struct IPropertyBag *a2, struct IErrorLog *a3)
{
  __int64 (__fastcall ***v5)(struct IPropertyBag *, GUID *, __int64 *); // rdx
  int v6; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BOOL value; // [rsp+38h] [rbp-20h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h] BYREF

  ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v10);
  v6 = (**v5)(a2, &GUID_d960050c_f4e1_4294_ac4b_598913605923, &v10);
  if ( v6 >= 0 )
  {
    hKey = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v10 + 32LL))(v10, 131097, &hKey);
    if ( v6 >= 0 )
    {
      RegOpenKeyExW(hKey, L"PropertySetStorage", 0, 0x20019u, this + 8);
      RegCloseKey(hKey);
    }
  }
  value = 0;
  if ( PSPropertyBag_ReadBOOL(a2, L"LoadWithSAX", &value) >= 0 )
    *((_BYTE *)this + 88) = value;
  ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e850  mov     [rsp+arg_10], rbx
0x18002e855  mov     [rsp+arg_18], rsi
0x18002e85a  push    rdi
0x18002e85b  sub     rsp, 50h
0x18002e85f  mov     rax, cs:__security_cookie
0x18002e866  xor     rax, rsp
0x18002e869  mov     [rsp+58h+var_10], rax
0x18002e86e  mov     rdi, rcx
0x18002e871  mov     rsi, rdx
0x18002e874  lea     rcx, [rsp+58h+var_18]
0x18002e879  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x18002e87e  mov     rdx, [rdx]
0x18002e881  lea     r8, [rsp+58h+var_18]
0x18002e886  mov     rcx, rsi
0x18002e889  mov     rax, [rdx]
0x18002e88c  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x18002e893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e898  mov     ebx, eax
0x18002e89a  test    eax, eax
0x18002e89c  js      short loc_18002E8F7
0x18002e89e  mov     rcx, [rsp+58h+var_18]
0x18002e8a3  lea     r8, [rsp+58h+hKey]
0x18002e8a8  mov     [rsp+58h+hKey], 0
0x18002e8b1  mov     edx, 20019h
0x18002e8b6  mov     rax, [rcx]
0x18002e8b9  mov     rax, [rax+20h]
0x18002e8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c2  mov     ebx, eax
0x18002e8c4  test    eax, eax
0x18002e8c6  js      short loc_18002E8F7
0x18002e8c8  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e8cd  lea     rax, [rdi+40h]
0x18002e8d1  mov     r9d, 20019h; samDesired
0x18002e8d7  mov     [rsp+58h+phkResult], rax; phkResult
0x18002e8dc  xor     r8d, r8d; ulOptions
0x18002e8df  lea     rdx, aPropertysetsto; "PropertySetStorage"
0x18002e8e6  call    cs:__imp_RegOpenKeyExW
0x18002e8ec  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e8f1  call    cs:__imp_RegCloseKey
0x18002e8f7  lea     r8, [rsp+58h+value]; value
0x18002e8fc  mov     [rsp+58h+value], 0
0x18002e904  lea     rdx, propName; "LoadWithSAX"
0x18002e90b  mov     rcx, rsi; propBag
0x18002e90e  call    cs:__imp_PSPropertyBag_ReadBOOL
0x18002e914  test    eax, eax
0x18002e916  js      short loc_18002E923
0x18002e918  cmp     [rsp+58h+value], 0
0x18002e91d  setnz   al
0x18002e920  mov     [rdi+58h], al
0x18002e923  lea     rcx, [rsp+58h+var_18]
0x18002e928  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x18002e92d  mov     eax, ebx
0x18002e92f  mov     rcx, [rsp+58h+var_10]
0x18002e934  xor     rcx, rsp; StackCookie
0x18002e937  call    __security_check_cookie
0x18002e93c  mov     rbx, [rsp+58h+arg_10]
0x18002e941  mov     rsi, [rsp+58h+arg_18]
0x18002e946  add     rsp, 50h
0x18002e94a  pop     rdi
0x18002e94b  retn
```
