# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRecoExt>>,ATL::CComCreator<ATL::CComAggObject<CRecoExt>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001760`
- end: `0x18000176e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRecoExt@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRecoExt@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800016e0`

## callees

- `0x180001780`
- `0x180006b88`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRecoExt>>,ATL::CComCreator<ATL::CComAggObject<CRecoExt>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CRecoExt>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CRecoExt>>::CreateInstance();
}

```

## disassembly

```asm
0x180001760  test    rcx, rcx
0x180001763  jnz     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCRecoExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CRecoExt>>::CreateInstance(void *,_GUID const &,void * *)
0x180001769  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCRecoExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CRecoExt>>::CreateInstance(void *,_GUID const &,void * *)
```
