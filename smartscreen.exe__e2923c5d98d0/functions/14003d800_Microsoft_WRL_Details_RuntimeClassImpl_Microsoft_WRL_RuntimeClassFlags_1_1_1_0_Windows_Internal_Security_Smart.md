# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IPopupButtonInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14003d800`
- end: `0x14003d85f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPopupButtonInfo@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c334`
- `0x14003d800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003d822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003d822`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IPopupButtonInfo,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IPopupButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x14003d800  mov     [rsp+arg_0], rbx
0x14003d805  push    rdi
0x14003d806  sub     rsp, 20h
0x14003d80a  mov     qword ptr [r8], 0
0x14003d811  mov     ecx, 20h ; ' '; cb
0x14003d816  mov     dword ptr [rdx], 0
0x14003d81c  mov     rbx, r8
0x14003d81f  mov     rdi, rdx
0x14003d822  call    cs:__imp_CoTaskMemAlloc
0x14003d828  mov     r8, rax
0x14003d82b  test    rax, rax
0x14003d82e  jnz     short loc_14003D837
0x14003d830  mov     eax, 8007000Eh
0x14003d835  jmp     short loc_14003D854
0x14003d837  lea     rdx, [rsp+28h+arg_8]
0x14003d83c  mov     [rsp+28h+arg_8], 0
0x14003d844  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIPopupButtonInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IPopupButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003d849  mov     dword ptr [rdi], 2
0x14003d84f  xor     eax, eax
0x14003d851  mov     [rbx], r8
0x14003d854  mov     rbx, [rsp+28h+arg_0]
0x14003d859  add     rsp, 20h
0x14003d85d  pop     rdi
0x14003d85e  retn
```
