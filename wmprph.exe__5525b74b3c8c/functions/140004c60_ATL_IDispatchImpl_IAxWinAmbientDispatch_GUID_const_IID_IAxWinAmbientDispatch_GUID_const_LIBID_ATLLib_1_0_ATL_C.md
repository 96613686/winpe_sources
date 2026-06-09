# ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140004c60`
- end: `0x140004c6c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004c94`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x140004c60  lea     rcx, ?_tih@?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140004c67  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)
```
