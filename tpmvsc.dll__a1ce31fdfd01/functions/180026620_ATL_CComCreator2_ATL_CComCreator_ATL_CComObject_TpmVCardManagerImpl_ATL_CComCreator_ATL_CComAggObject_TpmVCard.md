# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<TpmVCardManagerImpl>>,ATL::CComCreator<ATL::CComAggObject<TpmVCardManagerImpl>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180026620`
- end: `0x18002662e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VTpmVCardManagerImpl@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180026634`
- `0x18002671c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<TpmVCardManagerImpl>>,ATL::CComCreator<ATL::CComAggObject<TpmVCardManagerImpl>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<TpmVCardManagerImpl>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<TpmVCardManagerImpl>>::CreateInstance();
}

```

## disassembly

```asm
0x180026620  test    rcx, rcx
0x180026623  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VTpmVCardManagerImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<TpmVCardManagerImpl>>::CreateInstance(void *,_GUID const &,void * *)
0x180026629  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<TpmVCardManagerImpl>>::CreateInstance(void *,_GUID const &,void * *)
```
