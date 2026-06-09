# CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180009cc0`
- end: `0x180009d12`
- name: `?Invoke@?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, int, const struct _GUID *, unsigned int, __int16, struct tagDISPPARAMS *, VARIANTARG *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006b50`

## pseudocode

```c
__int64 __fastcall CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Invoke(
        __int64 a1,
        int a2,
        const struct _GUID *a3,
        unsigned int a4,
        __int16 a5,
        struct tagDISPPARAMS *a6,
        VARIANTARG *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  return CFciPropertiesShellExt::DelegateInvoke(*(CFciPropertiesShellExt **)(a1 + 64), a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x180009cc0  mov     r11, rsp
0x180009cc3  sub     rsp, 58h
0x180009cc7  mov     rax, [rsp+58h+arg_40]
0x180009ccf  mov     rcx, [rcx+40h]; this
0x180009cd3  mov     [r11-18h], rax
0x180009cd7  mov     rax, [rsp+58h+arg_38]
0x180009cdf  mov     [r11-20h], rax
0x180009ce3  mov     rax, [rsp+58h+arg_30]
0x180009ceb  mov     [r11-28h], rax
0x180009cef  mov     rax, [rsp+58h+arg_28]
0x180009cf7  mov     [r11-30h], rax
0x180009cfb  movzx   eax, [rsp+58h+arg_20]
0x180009d03  mov     word ptr [rsp+58h+var_38], ax; char
0x180009d08  call    ?DelegateInvoke@CFciPropertiesShellExt@@AEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; CFciPropertiesShellExt::DelegateInvoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180009d0d  add     rsp, 58h
0x180009d11  retn
```
