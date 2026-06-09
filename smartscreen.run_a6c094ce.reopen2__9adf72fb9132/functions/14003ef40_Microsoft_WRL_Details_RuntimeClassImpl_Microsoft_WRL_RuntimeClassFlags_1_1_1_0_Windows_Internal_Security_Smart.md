# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14003ef40`
- end: `0x14003efa6`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003da28`
- `0x14003ef40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003ef62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003ef62`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14003ef40  mov     [rsp+arg_0], rbx
0x14003ef45  push    rdi
0x14003ef46  sub     rsp, 20h
0x14003ef4a  mov     qword ptr [r8], 0
0x14003ef51  mov     ecx, 20h ; ' '; cb
0x14003ef56  mov     dword ptr [rdx], 0
0x14003ef5c  mov     rbx, r8
0x14003ef5f  mov     rdi, rdx
0x14003ef62  call    cs:__imp_CoTaskMemAlloc
0x14003ef69  nop     dword ptr [rax+rax+00h]
0x14003ef6e  mov     r8, rax
0x14003ef71  test    rax, rax
0x14003ef74  jnz     short loc_14003EF7D
0x14003ef76  mov     eax, 8007000Eh
0x14003ef7b  jmp     short loc_14003EF9A
0x14003ef7d  lea     rdx, [rsp+28h+arg_8]
0x14003ef82  mov     [rsp+28h+arg_8], 0
0x14003ef8a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003ef8f  mov     dword ptr [rdi], 2
0x14003ef95  xor     eax, eax
0x14003ef97  mov     [rbx], r8
0x14003ef9a  mov     rbx, [rsp+28h+arg_0]
0x14003ef9f  add     rsp, 20h
0x14003efa3  pop     rdi
0x14003efa4  retn
```
