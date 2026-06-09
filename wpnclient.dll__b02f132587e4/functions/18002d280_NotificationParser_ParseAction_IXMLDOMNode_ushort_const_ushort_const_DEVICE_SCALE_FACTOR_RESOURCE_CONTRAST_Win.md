# NotificationParser::ParseAction(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18002d280`
- end: `0x18002d36a`
- name: `?ParseAction@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001780c`
- `0x18002d73c`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008fe0`
- `0x18000b440`
- `0x18000bbf0`
- `0x18000da20`
- `0x18002d1ac`
- `0x18002d280`

## string_xrefs

- `0x18002d303`: `imageUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NotificationParser::ParseAction(
        __int64 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-38h]
  _QWORD v15[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v16; // [rsp+98h] [rbp+40h] BYREF

  v15[0] = 0;
  v16 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
  NotificationParser::CreateValueSet(v10, v15, &v16);
  NotificationParser::GetAttributes(a1, a2, v16);
  NotificationParser::ResolveTextElement(a1, v16, L"content", (__int64)a3);
  NotificationParser::ResolveImageElement((__int64)a1, v16, L"imageUri", a3, v14, a5, a6, 1);
  NotificationParser::FixupActionArgumentsForLyncModern(a1, v16, (__int64)a3);
  if ( (unsigned __int8)NotificationParser::LookUpInvalidAttributes(v11, v16) )
  {
    *a7 = 0;
  }
  else
  {
    v12 = v15[0];
    v15[0] = 0;
    *a7 = v12;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
}

```

## disassembly

```asm
0x18002d280  mov     [rsp-20h+arg_18], r9
0x18002d285  push    rbp
0x18002d286  push    rbx
0x18002d287  push    rsi
0x18002d288  push    rdi
0x18002d289  mov     rbp, rsp
0x18002d28c  sub     rsp, 58h
0x18002d290  mov     rdi, r8
0x18002d293  mov     rbx, rdx
0x18002d296  mov     rsi, rcx
0x18002d299  mov     [rbp+var_18], 0
0x18002d2a1  mov     [rbp+arg_18], 0
0x18002d2a9  lea     rcx, [rbp+arg_18]
0x18002d2ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d2b2  lea     rcx, [rbp+var_18]
0x18002d2b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d2bb  lea     r8, [rbp+arg_18]
0x18002d2bf  lea     rdx, [rbp+var_18]
0x18002d2c3  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18002d2c8  mov     r8, [rbp+arg_18]
0x18002d2cc  mov     rdx, rbx
0x18002d2cf  mov     rcx, rsi
0x18002d2d2  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18002d2d7  mov     r9, rdi
0x18002d2da  lea     r8, aContent; "content"
0x18002d2e1  mov     rdx, [rbp+arg_18]
0x18002d2e5  mov     rcx, rsi
0x18002d2e8  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x18002d2ed  mov     [rsp+58h+var_20], 1
0x18002d2f2  mov     eax, [rbp+arg_28]
0x18002d2f5  mov     [rsp+58h+var_28], eax
0x18002d2f9  mov     eax, [rbp+arg_20]
0x18002d2fc  mov     [rsp+58h+var_30], eax
0x18002d300  mov     r9, rdi
0x18002d303  lea     r8, aImageuri; "imageUri"
0x18002d30a  mov     rdx, [rbp+arg_18]
0x18002d30e  mov     rcx, rsi
0x18002d311  call    ?ResolveImageElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@_N@Z; NotificationParser::ResolveImageElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,bool)
0x18002d316  mov     r8, rdi
0x18002d319  mov     rdx, [rbp+arg_18]
0x18002d31d  mov     rcx, rsi
0x18002d320  call    ?FixupActionArgumentsForLyncModern@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG@Z; NotificationParser::FixupActionArgumentsForLyncModern(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *)
0x18002d325  mov     rdx, [rbp+arg_18]
0x18002d329  call    ?LookUpInvalidAttributes@NotificationParser@@AEAA_NPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::LookUpInvalidAttributes(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18002d32e  test    al, al
0x18002d330  mov     rax, [rbp+arg_30]
0x18002d334  jz      short loc_18002D33F
0x18002d336  mov     qword ptr [rax], 0
0x18002d33d  jmp     short loc_18002D34E
0x18002d33f  mov     rcx, [rbp+var_18]
0x18002d343  mov     [rbp+var_18], 0
0x18002d34b  mov     [rax], rcx
0x18002d34e  lea     rcx, [rbp+arg_18]
0x18002d352  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d357  nop
0x18002d358  lea     rcx, [rbp+var_18]
0x18002d35c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d361  add     rsp, 58h
0x18002d365  pop     rdi
0x18002d366  pop     rsi
0x18002d367  pop     rbx
0x18002d368  pop     rbp
0x18002d369  retn
```
