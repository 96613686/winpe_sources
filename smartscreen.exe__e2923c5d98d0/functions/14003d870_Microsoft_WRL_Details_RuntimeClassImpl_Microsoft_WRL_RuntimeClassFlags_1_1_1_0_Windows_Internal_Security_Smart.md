# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14003d870`
- end: `0x14003d8cf`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c358`
- `0x14003d870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003d892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003d892`

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
0x14003d870  mov     [rsp+arg_0], rbx
0x14003d875  push    rdi
0x14003d876  sub     rsp, 20h
0x14003d87a  mov     qword ptr [r8], 0
0x14003d881  mov     ecx, 20h ; ' '; cb
0x14003d886  mov     dword ptr [rdx], 0
0x14003d88c  mov     rbx, r8
0x14003d88f  mov     rdi, rdx
0x14003d892  call    cs:__imp_CoTaskMemAlloc
0x14003d898  mov     r8, rax
0x14003d89b  test    rax, rax
0x14003d89e  jnz     short loc_14003D8A7
0x14003d8a0  mov     eax, 8007000Eh
0x14003d8a5  jmp     short loc_14003D8C4
0x14003d8a7  lea     rdx, [rsp+28h+arg_8]
0x14003d8ac  mov     [rsp+28h+arg_8], 0
0x14003d8b4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003d8b9  mov     dword ptr [rdi], 2
0x14003d8bf  xor     eax, eax
0x14003d8c1  mov     [rbx], r8
0x14003d8c4  mov     rbx, [rsp+28h+arg_0]
0x14003d8c9  add     rsp, 20h
0x14003d8cd  pop     rdi
0x14003d8ce  retn
```
