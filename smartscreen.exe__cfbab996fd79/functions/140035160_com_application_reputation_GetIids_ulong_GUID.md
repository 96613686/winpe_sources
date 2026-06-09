# com::application_reputation::GetIids(ulong *,_GUID * *)

- ea: `0x140035160`
- end: `0x1400351d1`
- name: `?GetIids@application_reputation@com@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(com::application_reputation *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400351e0`

## callees

- `0x140034aac`
- `0x140035160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140035182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140035182`

## pseudocode

```c
__int64 __fastcall com::application_reputation::GetIids(
        com::application_reputation *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_d9dc3975_1062_470a_994c_409151ff8f54;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x140035160  mov     [rsp+arg_0], rbx
0x140035165  push    rdi
0x140035166  sub     rsp, 20h
0x14003516a  mov     qword ptr [r8], 0
0x140035171  mov     ecx, 30h ; '0'; cb
0x140035176  mov     dword ptr [rdx], 0
0x14003517c  mov     rbx, r8
0x14003517f  mov     rdi, rdx
0x140035182  call    cs:__imp_CoTaskMemAlloc
0x140035189  nop     dword ptr [rax+rax+00h]
0x14003518e  mov     r8, rax
0x140035191  test    rax, rax
0x140035194  jnz     short loc_14003519D
0x140035196  mov     eax, 8007000Eh
0x14003519b  jmp     short loc_1400351C5
0x14003519d  movups  xmm0, xmmword ptr cs:_GUID_d9dc3975_1062_470a_994c_409151ff8f54.Data1
0x1400351a4  lea     rdx, [rsp+28h+arg_8]
0x1400351a9  mov     [rsp+28h+arg_8], 1
0x1400351b1  movdqu  xmmword ptr [rax], xmm0
0x1400351b5  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1400351ba  mov     dword ptr [rdi], 3
0x1400351c0  xor     eax, eax
0x1400351c2  mov     [rbx], r8
0x1400351c5  mov     rbx, [rsp+28h+arg_0]
0x1400351ca  add     rsp, 20h
0x1400351ce  pop     rdi
0x1400351cf  retn
```
