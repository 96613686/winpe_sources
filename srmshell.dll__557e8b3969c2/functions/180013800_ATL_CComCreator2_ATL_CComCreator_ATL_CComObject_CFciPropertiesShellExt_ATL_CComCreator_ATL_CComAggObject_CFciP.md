# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFciPropertiesShellExt>>,ATL::CComCreator<ATL::CComAggObject<CFciPropertiesShellExt>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013800`
- end: `0x18001380e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCFciPropertiesShellExt@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013834`
- `0x180013a58`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFciPropertiesShellExt>>,ATL::CComCreator<ATL::CComAggObject<CFciPropertiesShellExt>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CFciPropertiesShellExt>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CFciPropertiesShellExt>>::CreateInstance();
}

```

## disassembly

```asm
0x180013800  test    rcx, rcx
0x180013803  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCFciPropertiesShellExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CFciPropertiesShellExt>>::CreateInstance(void *,_GUID const &,void * *)
0x180013809  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CFciPropertiesShellExt>>::CreateInstance(void *,_GUID const &,void * *)
```
