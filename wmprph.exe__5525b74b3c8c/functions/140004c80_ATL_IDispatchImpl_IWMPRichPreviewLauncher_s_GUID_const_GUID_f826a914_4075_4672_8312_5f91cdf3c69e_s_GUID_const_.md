# ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140004c80`
- end: `0x140004c8c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004c94`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x140004c80  lea     rcx, ?_tih@?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140004c87  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)
```
