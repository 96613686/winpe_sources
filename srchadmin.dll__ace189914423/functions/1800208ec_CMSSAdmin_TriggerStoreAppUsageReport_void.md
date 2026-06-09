# CMSSAdmin::TriggerStoreAppUsageReport(void)

- ea: `0x1800208ec`
- end: `0x18002099a`
- name: `?TriggerStoreAppUsageReport@CMSSAdmin@@QEAAXXZ`
- size: `174`
- prototype: `void __fastcall(CMSSAdmin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018730`

## callees

- `0x1800181fc`
- `0x1800208ec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002092b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002092b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMSSAdmin::TriggerStoreAppUsageReport(CMSSAdmin *this)
{
  LPVOID v1; // rdi
  int (__fastcall *v2)(LPVOID, CMSSAdmin **); // rbx
  CMSSAdmin *v3; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v3 = this;
  ppv = 0;
  Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(&ppv);
  if ( CoCreateInstance(
         &GUID_b52d54bb_4818_4eb9_aa80_f9eacd371df8,
         0,
         0x15u,
         &GUID_993eceb0_6f1b_49fe_8ba2_21b6a5317de1,
         &ppv) >= 0 )
  {
    v3 = 0;
    v1 = ppv;
    v2 = *(int (__fastcall **)(LPVOID, CMSSAdmin **))(*(_QWORD *)ppv + 56LL);
    Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(&v3);
    if ( v2(v1, &v3) >= 0 )
      (*(void (__fastcall **)(CMSSAdmin *))(*(_QWORD *)v3 + 32LL))(v3);
    Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(&v3);
  }
  Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(&ppv);
}

```

## disassembly

```asm
0x1800208ec  mov     rax, rsp
0x1800208ef  mov     [rax+18h], rbx
0x1800208f3  mov     [rax+8], rcx
0x1800208f7  push    rdi
0x1800208f8  sub     rsp, 30h
0x1800208fc  mov     qword ptr [rax+10h], 0
0x180020904  lea     rcx, [rax+10h]
0x180020908  call    ?InternalRelease@?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(void)
0x18002090d  lea     rax, [rsp+38h+arg_8]
0x180020912  mov     [rsp+38h+ppv], rax; ppv
0x180020917  lea     r9, _GUID_993eceb0_6f1b_49fe_8ba2_21b6a5317de1; riid
0x18002091e  xor     edx, edx; pUnkOuter
0x180020920  lea     r8d, [rdx+15h]; dwClsContext
0x180020924  lea     rcx, _GUID_b52d54bb_4818_4eb9_aa80_f9eacd371df8; rclsid
0x18002092b  call    cs:__imp_CoCreateInstance
0x180020931  test    eax, eax
0x180020933  js      short loc_180020985
0x180020935  mov     [rsp+38h+arg_0], 0
0x18002093e  mov     rdi, [rsp+38h+arg_8]
0x180020943  mov     rax, [rdi]
0x180020946  mov     rbx, [rax+38h]
0x18002094a  lea     rcx, [rsp+38h+arg_0]
0x18002094f  call    ?InternalRelease@?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(void)
0x180020954  lea     rdx, [rsp+38h+arg_0]
0x180020959  mov     rcx, rdi
0x18002095c  mov     rax, rbx
0x18002095f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020964  test    eax, eax
0x180020966  js      short loc_18002097A
0x180020968  mov     rcx, [rsp+38h+arg_0]
0x18002096d  mov     rax, [rcx]
0x180020970  mov     rax, [rax+20h]
0x180020974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020979  nop
0x18002097a  lea     rcx, [rsp+38h+arg_0]
0x18002097f  call    ?InternalRelease@?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(void)
0x180020984  nop
0x180020985  lea     rcx, [rsp+38h+arg_8]
0x18002098a  call    ?InternalRelease@?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(void)
0x18002098f  mov     rbx, [rsp+38h+arg_10]
0x180020994  add     rsp, 30h
0x180020998  pop     rdi
0x180020999  retn
```
