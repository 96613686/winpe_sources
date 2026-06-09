# com::uri_reputation::GetIids(ulong *,_GUID * *)

- ea: `0x14003f020`
- end: `0x14003f086`
- name: `?GetIids@uri_reputation@com@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(com::uri_reputation *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003da70`
- `0x14003f020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f042`

## pseudocode

```c
__int64 __fastcall com::uri_reputation::GetIids(com::uri_reputation *this, unsigned int *a2, struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationService,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14003f020  mov     [rsp+arg_0], rbx
0x14003f025  push    rdi
0x14003f026  sub     rsp, 20h
0x14003f02a  mov     qword ptr [r8], 0
0x14003f031  mov     ecx, 20h ; ' '; cb
0x14003f036  mov     dword ptr [rdx], 0
0x14003f03c  mov     rbx, r8
0x14003f03f  mov     rdi, rdx
0x14003f042  call    cs:__imp_CoTaskMemAlloc
0x14003f049  nop     dword ptr [rax+rax+00h]
0x14003f04e  mov     r8, rax
0x14003f051  test    rax, rax
0x14003f054  jnz     short loc_14003F05D
0x14003f056  mov     eax, 8007000Eh
0x14003f05b  jmp     short loc_14003F07A
0x14003f05d  lea     rdx, [rsp+28h+arg_8]
0x14003f062  mov     [rsp+28h+arg_8], 0
0x14003f06a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationService@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationService,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003f06f  mov     dword ptr [rdi], 2
0x14003f075  xor     eax, eax
0x14003f077  mov     [rbx], r8
0x14003f07a  mov     rbx, [rsp+28h+arg_0]
0x14003f07f  add     rsp, 20h
0x14003f083  pop     rdi
0x14003f084  retn
```
