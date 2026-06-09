# com::application_reputation::GetIids(ulong *,_GUID * *)

- ea: `0x140033cd0`
- end: `0x140033d3a`
- name: `?GetIids@application_reputation@com@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(com::application_reputation *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140033d40`

## callees

- `0x140033638`
- `0x140033cd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033cf2`

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
0x140033cd0  mov     [rsp+arg_0], rbx
0x140033cd5  push    rdi
0x140033cd6  sub     rsp, 20h
0x140033cda  mov     qword ptr [r8], 0
0x140033ce1  mov     ecx, 30h ; '0'; cb
0x140033ce6  mov     dword ptr [rdx], 0
0x140033cec  mov     rbx, r8
0x140033cef  mov     rdi, rdx
0x140033cf2  call    cs:__imp_CoTaskMemAlloc
0x140033cf8  mov     r8, rax
0x140033cfb  test    rax, rax
0x140033cfe  jnz     short loc_140033D07
0x140033d00  mov     eax, 8007000Eh
0x140033d05  jmp     short loc_140033D2F
0x140033d07  movups  xmm0, xmmword ptr cs:_GUID_d9dc3975_1062_470a_994c_409151ff8f54.Data1
0x140033d0e  lea     rdx, [rsp+28h+arg_8]
0x140033d13  mov     [rsp+28h+arg_8], 1
0x140033d1b  movdqu  xmmword ptr [rax], xmm0
0x140033d1f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x140033d24  mov     dword ptr [rdi], 3
0x140033d2a  xor     eax, eax
0x140033d2c  mov     [rbx], r8
0x140033d2f  mov     rbx, [rsp+28h+arg_0]
0x140033d34  add     rsp, 20h
0x140033d38  pop     rdi
0x140033d39  retn
```
