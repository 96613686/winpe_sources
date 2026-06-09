# CreateStockEventTraceExtender

- ea: `0x18000ee20`
- end: `0x18000f0a5`
- name: `CreateStockEventTraceExtender`
- size: `645`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000bc6c`
- `0x18000f0ac`

## callees

- `0x18000acfc`
- `0x18000aed8`
- `0x18000ee20`
- `0x1800120a0`
- `0x180018c2c`
- `0x18001ee4c`
- `0x180021090`
- `0x180024dc0`
- `0x180029e24`
- `0x18002b244`
- `0x18002bdf0`
- `0x18002d8e4`

## pseudocode

```c
__int64 __fastcall CreateStockEventTraceExtender(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  switch ( *a1 )
  {
    case 0x1D6CD37C:
      if ( a1[1] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
        && a1[2] == *(_DWORD *)GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
        && a1[3] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x8105C558:
      if ( a1[1] == *(_DWORD *)&GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
        && a1[2] == *(_DWORD *)GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
        && a1[3] == *(_DWORD *)&GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xB620D9A6:
      if ( a1[1] == *(_DWORD *)&GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
        && a1[2] == *(_DWORD *)GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
        && a1[3] == *(_DWORD *)&GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xB33AC241:
      if ( a1[1] == *(_DWORD *)&GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
        && a1[2] == *(_DWORD *)GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
        && a1[3] == *(_DWORD *)&GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xAA981571:
      if ( a1[1] == *(_DWORD *)&GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
        && a1[2] == *(_DWORD *)GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
        && a1[3] == *(_DWORD *)&GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xCF8B21C:
      if ( a1[1] == *(_DWORD *)&GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
        && a1[2] == *(_DWORD *)GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
        && a1[3] == *(_DWORD *)&GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x40C4F4F6:
      if ( a1[1] == *(_DWORD *)&GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
        && a1[2] == *(_DWORD *)GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
        && a1[3] == *(_DWORD *)&GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xAD4F7AB3:
      if ( a1[1] == *(_DWORD *)&GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
        && a1[2] == *(_DWORD *)GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
        && a1[3] == *(_DWORD *)&GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x164122F2:
      if ( a1[1] == *(_DWORD *)&GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
        && a1[2] == *(_DWORD *)GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
        && a1[3] == *(_DWORD *)&GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x88B342B3:
      if ( a1[1] == *(_DWORD *)&GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
        && a1[2] == *(_DWORD *)GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
        && a1[3] == *(_DWORD *)&GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    default:
      if ( *a1 == 278897245
        && a1[1] == *(_DWORD *)&GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
        && a1[2] == *(_DWORD *)GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
        && a1[3] == *(_DWORD *)&GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x18000ee20  cmp     dword ptr [rcx], 1D6CD37Ch
0x18000ee26  jnz     short loc_18000EE5D
0x18000ee28  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
0x18000ee2e  cmp     [rcx+4], eax
0x18000ee31  jnz     loc_18000F09F
0x18000ee37  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
0x18000ee3d  cmp     [rcx+8], eax
0x18000ee40  jnz     loc_18000F09F
0x18000ee46  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4+4
0x18000ee4c  cmp     [rcx+0Ch], eax
0x18000ee4f  jnz     loc_18000F09F
0x18000ee55  mov     r8, r9
0x18000ee58  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000ee5d  cmp     dword ptr [rcx], 8105C558h
0x18000ee63  jnz     short loc_18000EE9A
0x18000ee65  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
0x18000ee6b  cmp     [rcx+4], eax
0x18000ee6e  jnz     loc_18000F09F
0x18000ee74  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
0x18000ee7a  cmp     [rcx+8], eax
0x18000ee7d  jnz     loc_18000F09F
0x18000ee83  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4+4
0x18000ee89  cmp     [rcx+0Ch], eax
0x18000ee8c  jnz     loc_18000F09F
0x18000ee92  mov     r8, r9
0x18000ee95  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000ee9a  cmp     dword ptr [rcx], 0B620D9A6h
0x18000eea0  jnz     short loc_18000EED7
0x18000eea2  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
0x18000eea8  cmp     [rcx+4], eax
0x18000eeab  jnz     loc_18000F09F
0x18000eeb1  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
0x18000eeb7  cmp     [rcx+8], eax
0x18000eeba  jnz     loc_18000F09F
0x18000eec0  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4+4
0x18000eec6  cmp     [rcx+0Ch], eax
0x18000eec9  jnz     loc_18000F09F
0x18000eecf  mov     r8, r9
0x18000eed2  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000eed7  cmp     dword ptr [rcx], 0B33AC241h
0x18000eedd  jnz     short loc_18000EF14
0x18000eedf  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
0x18000eee5  cmp     [rcx+4], eax
0x18000eee8  jnz     loc_18000F09F
0x18000eeee  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
0x18000eef4  cmp     [rcx+8], eax
0x18000eef7  jnz     loc_18000F09F
0x18000eefd  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4+4
0x18000ef03  cmp     [rcx+0Ch], eax
0x18000ef06  jnz     loc_18000F09F
0x18000ef0c  mov     r8, r9
0x18000ef0f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000ef14  cmp     dword ptr [rcx], 0AA981571h
0x18000ef1a  jnz     short loc_18000EF51
0x18000ef1c  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
0x18000ef22  cmp     [rcx+4], eax
0x18000ef25  jnz     loc_18000F09F
0x18000ef2b  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
0x18000ef31  cmp     [rcx+8], eax
0x18000ef34  jnz     loc_18000F09F
0x18000ef3a  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4+4
0x18000ef40  cmp     [rcx+0Ch], eax
0x18000ef43  jnz     loc_18000F09F
0x18000ef49  mov     r8, r9
0x18000ef4c  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000ef51  cmp     dword ptr [rcx], 0CF8B21Ch
0x18000ef57  jnz     short loc_18000EF8E
0x18000ef59  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
0x18000ef5f  cmp     [rcx+4], eax
0x18000ef62  jnz     loc_18000F09F
0x18000ef68  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
0x18000ef6e  cmp     [rcx+8], eax
0x18000ef71  jnz     loc_18000F09F
0x18000ef77  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4+4
0x18000ef7d  cmp     [rcx+0Ch], eax
0x18000ef80  jnz     loc_18000F09F
0x18000ef86  mov     r8, r9
0x18000ef89  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000ef8e  cmp     dword ptr [rcx], 40C4F4F6h
0x18000ef94  jnz     short loc_18000EFCB
0x18000ef96  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
0x18000ef9c  cmp     [rcx+4], eax
0x18000ef9f  jnz     loc_18000F09F
0x18000efa5  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
0x18000efab  cmp     [rcx+8], eax
0x18000efae  jnz     loc_18000F09F
0x18000efb4  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4+4
0x18000efba  cmp     [rcx+0Ch], eax
0x18000efbd  jnz     loc_18000F09F
0x18000efc3  mov     r8, r9
0x18000efc6  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000efcb  cmp     dword ptr [rcx], 0AD4F7AB3h
0x18000efd1  jnz     short loc_18000F008
0x18000efd3  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
0x18000efd9  cmp     [rcx+4], eax
0x18000efdc  jnz     loc_18000F09F
0x18000efe2  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
0x18000efe8  cmp     [rcx+8], eax
0x18000efeb  jnz     loc_18000F09F
0x18000eff1  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4+4
0x18000eff7  cmp     [rcx+0Ch], eax
0x18000effa  jnz     loc_18000F09F
0x18000f000  mov     r8, r9
0x18000f003  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f008  cmp     dword ptr [rcx], 164122F2h
0x18000f00e  jnz     short loc_18000F03D
0x18000f010  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
0x18000f016  cmp     [rcx+4], eax
0x18000f019  jnz     loc_18000F09F
0x18000f01f  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
0x18000f025  cmp     [rcx+8], eax
0x18000f028  jnz     short loc_18000F09F
0x18000f02a  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4+4
0x18000f030  cmp     [rcx+0Ch], eax
0x18000f033  jnz     short loc_18000F09F
0x18000f035  mov     r8, r9
0x18000f038  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f03d  cmp     dword ptr [rcx], 88B342B3h
0x18000f043  jnz     short loc_18000F06E
0x18000f045  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
0x18000f04b  cmp     [rcx+4], eax
0x18000f04e  jnz     short loc_18000F09F
0x18000f050  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
0x18000f056  cmp     [rcx+8], eax
0x18000f059  jnz     short loc_18000F09F
0x18000f05b  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4+4
0x18000f061  cmp     [rcx+0Ch], eax
0x18000f064  jnz     short loc_18000F09F
0x18000f066  mov     r8, r9
0x18000f069  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f06e  cmp     dword ptr [rcx], 109FA25Dh
0x18000f074  jnz     short loc_18000F09F
0x18000f076  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
0x18000f07c  cmp     [rcx+4], eax
0x18000f07f  jnz     short loc_18000F09F
0x18000f081  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
0x18000f087  cmp     [rcx+8], eax
0x18000f08a  jnz     short loc_18000F09F
0x18000f08c  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4+4
0x18000f092  cmp     [rcx+0Ch], eax
0x18000f095  jnz     short loc_18000F09F
0x18000f097  mov     r8, r9
0x18000f09a  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f09f  mov     eax, 80040111h
0x18000f0a4  retn
```
