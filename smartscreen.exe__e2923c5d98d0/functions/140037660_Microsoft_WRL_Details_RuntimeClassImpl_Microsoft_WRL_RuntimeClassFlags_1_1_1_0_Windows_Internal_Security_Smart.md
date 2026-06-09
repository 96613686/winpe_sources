# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IEventLogger,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x140037660`
- end: `0x1400376bf`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIEventLogger@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400372c8`
- `0x140037660`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037682`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IEventLogger,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IEventLogger,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x140037660  mov     [rsp+arg_0], rbx
0x140037665  push    rdi
0x140037666  sub     rsp, 20h
0x14003766a  mov     qword ptr [r8], 0
0x140037671  mov     ecx, 20h ; ' '; cb
0x140037676  mov     dword ptr [rdx], 0
0x14003767c  mov     rbx, r8
0x14003767f  mov     rdi, rdx
0x140037682  call    cs:__imp_CoTaskMemAlloc
0x140037688  mov     r8, rax
0x14003768b  test    rax, rax
0x14003768e  jnz     short loc_140037697
0x140037690  mov     eax, 8007000Eh
0x140037695  jmp     short loc_1400376B4
0x140037697  lea     rdx, [rsp+28h+arg_8]
0x14003769c  mov     [rsp+28h+arg_8], 0
0x1400376a4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIEventLogger@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IEventLogger,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1400376a9  mov     dword ptr [rdi], 2
0x1400376af  xor     eax, eax
0x1400376b1  mov     [rbx], r8
0x1400376b4  mov     rbx, [rsp+28h+arg_0]
0x1400376b9  add     rsp, 20h
0x1400376bd  pop     rdi
0x1400376be  retn
```
