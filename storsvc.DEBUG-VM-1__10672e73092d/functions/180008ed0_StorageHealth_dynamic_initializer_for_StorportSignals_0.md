# StorageHealth::_dynamic_initializer_for__StorportSignals___0

- ea: `0x180008ed0`
- end: `0x1800097af`
- name: `StorageHealth::_dynamic_initializer_for__StorportSignals___0`
- size: `2271`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d3e0`
- `0x18001f634`

## string_xrefs

- `0x18000905c`: `SrbStatusCommandTimeout`
- `0x180009129`: `SenseKeyNotReady`
- `0x18000921f`: `SenseKeyAbortedCommand`
- `0x180009271`: `MediumErrorUnrecoveredRead`
- `0x180009367`: `HardwareErrorDefectListUpdateFailure`
- `0x1800092ec`: `MediumErrorDefectListUpdateFailure`
- `0x18000940b`: `HardwareErrorDataPathFailure`
- `0x1800093e2`: `HardwareErrorLogicalUnitErrorFailedUpdate`
- `0x1800094af`: `HardwareErrorFailedSelfConfiguration`
- `0x1800095f7`: `WriteIOCount`
- `0x1800095ce`: `ReadIOCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=107
int StorageHealth::_dynamic_initializer_for__StorportSignals___0()
{
  std::wstring::wstring(qword_1800C55D0, L"VendorId");
  std::wstring::wstring(qword_1800C55F0, L"StorportErrPerf");
  dword_1800C5610 = 3;
  std::wstring::wstring(qword_1800C5618, L"MiniportName");
  std::wstring::wstring(qword_1800C5638, L"StorportErrPerf");
  dword_1800C5658 = 3;
  std::wstring::wstring(qword_1800C5660, L"SrbStatusAborted");
  std::wstring::wstring(qword_1800C5680, L"StorportErrPerf");
  dword_1800C56A0 = 0;
  std::wstring::wstring(qword_1800C56A8, L"SrbStatusError");
  std::wstring::wstring(qword_1800C56C8, L"StorportErrPerf");
  dword_1800C56E8 = 0;
  std::wstring::wstring(qword_1800C56F0, L"SrbStatusBusy");
  std::wstring::wstring(qword_1800C5710, L"StorportErrPerf");
  dword_1800C5730 = 0;
  std::wstring::wstring(qword_1800C5738, L"SrbStatusInvalidRequest");
  std::wstring::wstring(qword_1800C5758, L"StorportErrPerf");
  dword_1800C5778 = 0;
  std::wstring::wstring(qword_1800C5780, L"SrbStatusNoDevice");
  std::wstring::wstring(qword_1800C57A0, L"StorportErrPerf");
  dword_1800C57C0 = 0;
  std::wstring::wstring(qword_1800C57C8, L"SrbStatusTimeout");
  std::wstring::wstring(qword_1800C57E8, L"StorportErrPerf");
  dword_1800C5808 = 0;
  std::wstring::wstring(qword_1800C5810, L"SrbStatusSelectionTimeout");
  std::wstring::wstring(qword_1800C5830, L"StorportErrPerf");
  dword_1800C5850 = 0;
  std::wstring::wstring(qword_1800C5858, L"SrbStatusCommandTimeout");
  std::wstring::wstring(qword_1800C5878, L"StorportErrPerf");
  dword_1800C5898 = 0;
  std::wstring::wstring(qword_1800C58A0, L"SrbStatusBusReset");
  std::wstring::wstring(qword_1800C58C0, L"StorportErrPerf");
  dword_1800C58E0 = 0;
  std::wstring::wstring(qword_1800C58E8, L"SrbStatusParityError");
  std::wstring::wstring(qword_1800C5908, L"StorportErrPerf");
  dword_1800C5928 = 0;
  std::wstring::wstring(qword_1800C5930, L"SrbStatusNoHba");
  std::wstring::wstring(qword_1800C5950, L"StorportErrPerf");
  dword_1800C5970 = 0;
  std::wstring::wstring(qword_1800C5978, L"SenseKeyRecoveredError");
  std::wstring::wstring(qword_1800C5998, L"StorportErrPerf");
  dword_1800C59B8 = 0;
  std::wstring::wstring(qword_1800C59C0, L"SenseKeyNotReady");
  std::wstring::wstring(qword_1800C59E0, L"StorportErrPerf");
  dword_1800C5A00 = 0;
  std::wstring::wstring(qword_1800C5A08, L"SenseKeyMediumError");
  std::wstring::wstring(qword_1800C5A28, L"StorportErrPerf");
  dword_1800C5A48 = 0;
  std::wstring::wstring(qword_1800C5A50, L"SenseKeyHardwareError");
  std::wstring::wstring(qword_1800C5A70, L"StorportErrPerf");
  dword_1800C5A90 = 0;
  std::wstring::wstring(qword_1800C5A98, L"SenseKeyIllegalRequest");
  std::wstring::wstring(qword_1800C5AB8, L"StorportErrPerf");
  dword_1800C5AD8 = 0;
  std::wstring::wstring(qword_1800C5AE0, L"SenseKeyUnitAttention");
  std::wstring::wstring(qword_1800C5B00, L"StorportErrPerf");
  dword_1800C5B20 = 0;
  std::wstring::wstring(qword_1800C5B28, L"SenseKeyDataProtect");
  std::wstring::wstring(qword_1800C5B48, L"StorportErrPerf");
  dword_1800C5B68 = 0;
  std::wstring::wstring(qword_1800C5B70, L"SenseKeyAbortedCommand");
  std::wstring::wstring(qword_1800C5B90, L"StorportErrPerf");
  dword_1800C5BB0 = 0;
  std::wstring::wstring(qword_1800C5BB8, L"MediumErrorCRC");
  std::wstring::wstring(qword_1800C5BD8, L"StorportErrPerf");
  dword_1800C5BF8 = 0;
  std::wstring::wstring(qword_1800C5C00, L"MediumErrorUnrecoveredRead");
  std::wstring::wstring(qword_1800C5C20, L"StorportErrPerf");
  dword_1800C5C40 = 0;
  std::wstring::wstring(qword_1800C5C48, L"MediumErrorDefectList");
  std::wstring::wstring(qword_1800C5C68, L"StorportErrPerf");
  dword_1800C5C88 = 0;
  std::wstring::wstring(qword_1800C5C90, L"MediumErrorDefectListNoSpare");
  std::wstring::wstring(qword_1800C5CB0, L"StorportErrPerf");
  dword_1800C5CD0 = 0;
  std::wstring::wstring(qword_1800C5CD8, L"MediumErrorDefectListUpdateFailure");
  std::wstring::wstring(qword_1800C5CF8, L"StorportErrPerf");
  dword_1800C5D18 = 0;
  std::wstring::wstring(qword_1800C5D20, L"HardwareErrorDefectList");
  std::wstring::wstring(qword_1800C5D40, L"StorportErrPerf");
  dword_1800C5D60 = 0;
  std::wstring::wstring(qword_1800C5D68, L"HardwareErrorDefectListNoSpare");
  std::wstring::wstring(qword_1800C5D88, L"StorportErrPerf");
  dword_1800C5DA8 = 0;
  std::wstring::wstring(qword_1800C5DB0, L"HardwareErrorDefectListUpdateFailure");
  std::wstring::wstring(qword_1800C5DD0, L"StorportErrPerf");
  dword_1800C5DF0 = 0;
  std::wstring::wstring(qword_1800C5DF8, L"HardwareErrorLogicalUnitError");
  std::wstring::wstring(qword_1800C5E18, L"StorportErrPerf");
  dword_1800C5E38 = 0;
  std::wstring::wstring(qword_1800C5E40, L"HardwareErrorLogicalUnitErrorFailedSelf");
  std::wstring::wstring(qword_1800C5E60, L"StorportErrPerf");
  dword_1800C5E80 = 0;
  std::wstring::wstring(qword_1800C5E88, L"HardwareErrorLogicalUnitErrorFailedUpdate");
  std::wstring::wstring(qword_1800C5EA8, L"StorportErrPerf");
  dword_1800C5EC8 = 0;
  std::wstring::wstring(qword_1800C5ED0, L"HardwareErrorDataPathFailure");
  std::wstring::wstring(qword_1800C5EF0, L"StorportErrPerf");
  dword_1800C5F10 = 0;
  std::wstring::wstring(qword_1800C5F18, L"HardwareErrorPowerOnSelfTestFailure");
  std::wstring::wstring(qword_1800C5F38, L"StorportErrPerf");
  dword_1800C5F58 = 0;
  std::wstring::wstring(qword_1800C5F60, L"HardwareErrorInternalTargetFailure");
  std::wstring::wstring(qword_1800C5F80, L"StorportErrPerf");
  dword_1800C5FA0 = 0;
  std::wstring::wstring(qword_1800C5FA8, L"HardwareErrorInternalTargetFailureInternal");
  std::wstring::wstring(qword_1800C5FC8, L"StorportErrPerf");
  dword_1800C5FE8 = 0;
  std::wstring::wstring(qword_1800C5FF0, L"HardwareErrorFailedSelfConfiguration");
  std::wstring::wstring(qword_1800C6010, L"StorportErrPerf");
  dword_1800C6030 = 0;
  std::wstring::wstring(qword_1800C6038, L"HardwareErrorResourceFailure");
  std::wstring::wstring(qword_1800C6058, L"StorportErrPerf");
  dword_1800C6078 = 0;
  std::wstring::wstring(qword_1800C6080, L"HardwareErrorResourceFailureFailure");
  std::wstring::wstring(qword_1800C60A0, L"StorportErrPerf");
  dword_1800C60C0 = 0;
  std::wstring::wstring(qword_1800C60C8, L"StRtlTotalDeviceFailure");
  std::wstring::wstring(qword_1800C60E8, L"StorportErrPerf");
  dword_1800C6108 = 0;
  std::wstring::wstring(qword_1800C6110, L"ErrorHours");
  std::wstring::wstring(qword_1800C6130, L"StorportErrPerf");
  dword_1800C6150 = 0;
  std::wstring::wstring(qword_1800C6158, L"PerfHours");
  std::wstring::wstring(qword_1800C6178, L"StorportErrPerf");
  dword_1800C6198 = 0;
  std::wstring::wstring(qword_1800C61A0, L"IOCount");
  std::wstring::wstring(qword_1800C61C0, L"StorportErrPerf");
  dword_1800C61E0 = 0;
  std::wstring::wstring(qword_1800C61E8, L"ReadIOCount");
  std::wstring::wstring(qword_1800C6208, L"StorportErrPerf");
  dword_1800C6228 = 0;
  std::wstring::wstring(qword_1800C6230, L"WriteIOCount");
  std::wstring::wstring(qword_1800C6250, L"StorportErrPerf");
  dword_1800C6270 = 0;
  std::wstring::wstring(qword_1800C6278, L"AverageMaxIOLatency");
  std::wstring::wstring(qword_1800C6298, L"StorportErrPerf");
  dword_1800C62B8 = 2;
  std::wstring::wstring(qword_1800C62C0, L"PeakIOCount");
  std::wstring::wstring(qword_1800C62E0, L"StorportErrPerf");
  dword_1800C6300 = 0;
  std::wstring::wstring(qword_1800C6308, L"PerfPercent");
  std::wstring::wstring(qword_1800C6328, L"StorportErrPerf");
  dword_1800C6348 = 0;
  std::wstring::wstring(qword_1800C6350, L"BucketIOLatency");
  std::wstring::wstring(qword_1800C6370, L"StorportErrPerf");
  dword_1800C6390 = 3;
  std::wstring::wstring(qword_1800C6398, L"BucketIOCount0");
  std::wstring::wstring(qword_1800C63B8, L"StorportErrPerf");
  dword_1800C63D8 = 0;
  std::wstring::wstring(qword_1800C63E0, L"BucketIOCount1");
  std::wstring::wstring(qword_1800C6400, L"StorportErrPerf");
  dword_1800C6420 = 0;
  std::wstring::wstring(qword_1800C6428, L"BucketIOCount2");
  std::wstring::wstring(qword_1800C6448, L"StorportErrPerf");
  dword_1800C6468 = 0;
  std::wstring::wstring(qword_1800C6470, L"BucketIOCount3");
  std::wstring::wstring(qword_1800C6490, L"StorportErrPerf");
  dword_1800C64B0 = 0;
  std::wstring::wstring(qword_1800C64B8, L"BucketIOCount4");
  std::wstring::wstring(qword_1800C64D8, L"StorportErrPerf");
  dword_1800C64F8 = 0;
  return atexit((void (__cdecl *)())StorageHealth::_dynamic_atexit_destructor_for__StorportSignals___0);
}

```

## disassembly

```asm
0x180008ed0  mov     [rsp+arg_0], rsi
0x180008ed5  push    rdi
0x180008ed6  sub     rsp, 20h
0x180008eda  lea     rdx, aVendorid; "VendorId"
0x180008ee1  lea     rcx, qword_1800C55D0
0x180008ee8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008eed  nop
0x180008eee  lea     rsi, aStorporterrper; "StorportErrPerf"
0x180008ef5  mov     rdx, rsi
0x180008ef8  lea     rcx, qword_1800C55F0
0x180008eff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f04  mov     cs:dword_1800C5610, 3
0x180008f0e  lea     rdx, aMiniportname; "MiniportName"
0x180008f15  lea     rcx, qword_1800C5618
0x180008f1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f21  nop
0x180008f22  mov     rdx, rsi
0x180008f25  lea     rcx, qword_1800C5638
0x180008f2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f31  mov     cs:dword_1800C5658, 3
0x180008f3b  lea     rdx, aSrbstatusabort_19; "SrbStatusAborted"
0x180008f42  lea     rcx, qword_1800C5660
0x180008f49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f4e  nop
0x180008f4f  mov     rdx, rsi
0x180008f52  lea     rcx, qword_1800C5680
0x180008f59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f5e  xor     edi, edi
0x180008f60  mov     cs:dword_1800C56A0, edi
0x180008f66  lea     rdx, aSrbstatuserror; "SrbStatusError"
0x180008f6d  lea     rcx, qword_1800C56A8
0x180008f74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f79  nop
0x180008f7a  mov     rdx, rsi
0x180008f7d  lea     rcx, qword_1800C56C8
0x180008f84  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008f89  mov     cs:dword_1800C56E8, edi
0x180008f8f  lea     rdx, aSrbstatusbusy; "SrbStatusBusy"
0x180008f96  lea     rcx, qword_1800C56F0
0x180008f9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008fa2  nop
0x180008fa3  mov     rdx, rsi
0x180008fa6  lea     rcx, qword_1800C5710
0x180008fad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008fb2  mov     cs:dword_1800C5730, edi
0x180008fb8  lea     rdx, aSrbstatusinval_5; "SrbStatusInvalidRequest"
0x180008fbf  lea     rcx, qword_1800C5738
0x180008fc6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008fcb  nop
0x180008fcc  mov     rdx, rsi
0x180008fcf  lea     rcx, qword_1800C5758
0x180008fd6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008fdb  mov     cs:dword_1800C5778, edi
0x180008fe1  lea     rdx, aSrbstatusnodev_7; "SrbStatusNoDevice"
0x180008fe8  lea     rcx, qword_1800C5780
0x180008fef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008ff4  nop
0x180008ff5  mov     rdx, rsi
0x180008ff8  lea     rcx, qword_1800C57A0
0x180008fff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009004  mov     cs:dword_1800C57C0, edi
0x18000900a  lea     rdx, aSrbstatustimeo_8; "SrbStatusTimeout"
0x180009011  lea     rcx, qword_1800C57C8
0x180009018  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000901d  nop
0x18000901e  mov     rdx, rsi
0x180009021  lea     rcx, qword_1800C57E8
0x180009028  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000902d  mov     cs:dword_1800C5808, edi
0x180009033  lea     rdx, aSrbstatusselec_6; "SrbStatusSelectionTimeout"
0x18000903a  lea     rcx, qword_1800C5810
0x180009041  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009046  nop
0x180009047  mov     rdx, rsi
0x18000904a  lea     rcx, qword_1800C5830
0x180009051  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009056  mov     cs:dword_1800C5850, edi
0x18000905c  lea     rdx, aSrbstatuscomma_2; "SrbStatusCommandTimeout"
0x180009063  lea     rcx, qword_1800C5858
0x18000906a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000906f  nop
0x180009070  mov     rdx, rsi
0x180009073  lea     rcx, qword_1800C5878
0x18000907a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000907f  mov     cs:dword_1800C5898, edi
0x180009085  lea     rdx, aSrbstatusbusre_3; "SrbStatusBusReset"
0x18000908c  lea     rcx, qword_1800C58A0
0x180009093  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009098  nop
0x180009099  mov     rdx, rsi
0x18000909c  lea     rcx, qword_1800C58C0
0x1800090a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800090a8  mov     cs:dword_1800C58E0, edi
0x1800090ae  lea     rdx, aSrbstatusparit_5; "SrbStatusParityError"
0x1800090b5  lea     rcx, qword_1800C58E8
0x1800090bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800090c1  nop
0x1800090c2  mov     rdx, rsi
0x1800090c5  lea     rcx, qword_1800C5908
0x1800090cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800090d1  mov     cs:dword_1800C5928, edi
0x1800090d7  lea     rdx, aSrbstatusnohba_5; "SrbStatusNoHba"
0x1800090de  lea     rcx, qword_1800C5930
0x1800090e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800090ea  nop
0x1800090eb  mov     rdx, rsi
0x1800090ee  lea     rcx, qword_1800C5950
0x1800090f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800090fa  mov     cs:dword_1800C5970, edi
0x180009100  lea     rdx, aSensekeyrecove; "SenseKeyRecoveredError"
0x180009107  lea     rcx, qword_1800C5978
0x18000910e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009113  nop
0x180009114  mov     rdx, rsi
0x180009117  lea     rcx, qword_1800C5998
0x18000911e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009123  mov     cs:dword_1800C59B8, edi
0x180009129  lea     rdx, aSensekeynotrea; "SenseKeyNotReady"
0x180009130  lea     rcx, qword_1800C59C0
0x180009137  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000913c  nop
0x18000913d  mov     rdx, rsi
0x180009140  lea     rcx, qword_1800C59E0
0x180009147  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000914c  mov     cs:dword_1800C5A00, edi
0x180009152  lea     rdx, aSensekeymedium; "SenseKeyMediumError"
0x180009159  lea     rcx, qword_1800C5A08
0x180009160  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009165  nop
0x180009166  mov     rdx, rsi
0x180009169  lea     rcx, qword_1800C5A28
0x180009170  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009175  mov     cs:dword_1800C5A48, edi
0x18000917b  lea     rdx, aSensekeyhardwa; "SenseKeyHardwareError"
0x180009182  lea     rcx, qword_1800C5A50
0x180009189  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000918e  nop
0x18000918f  mov     rdx, rsi
0x180009192  lea     rcx, qword_1800C5A70
0x180009199  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000919e  mov     cs:dword_1800C5A90, edi
0x1800091a4  lea     rdx, aSensekeyillega; "SenseKeyIllegalRequest"
0x1800091ab  lea     rcx, qword_1800C5A98
0x1800091b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800091b7  nop
0x1800091b8  mov     rdx, rsi
0x1800091bb  lea     rcx, qword_1800C5AB8
0x1800091c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800091c7  mov     cs:dword_1800C5AD8, edi
0x1800091cd  lea     rdx, aSensekeyunitat; "SenseKeyUnitAttention"
0x1800091d4  lea     rcx, qword_1800C5AE0
0x1800091db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800091e0  nop
0x1800091e1  mov     rdx, rsi
0x1800091e4  lea     rcx, qword_1800C5B00
0x1800091eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800091f0  mov     cs:dword_1800C5B20, edi
0x1800091f6  lea     rdx, aSensekeydatapr; "SenseKeyDataProtect"
0x1800091fd  lea     rcx, qword_1800C5B28
0x180009204  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009209  nop
0x18000920a  mov     rdx, rsi
0x18000920d  lea     rcx, qword_1800C5B48
0x180009214  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009219  mov     cs:dword_1800C5B68, edi
0x18000921f  lea     rdx, aSensekeyaborte; "SenseKeyAbortedCommand"
0x180009226  lea     rcx, qword_1800C5B70
0x18000922d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009232  nop
0x180009233  mov     rdx, rsi
0x180009236  lea     rcx, qword_1800C5B90
0x18000923d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009242  mov     cs:dword_1800C5BB0, edi
0x180009248  lea     rdx, aMediumerrorcrc_3; "MediumErrorCRC"
0x18000924f  lea     rcx, qword_1800C5BB8
0x180009256  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000925b  nop
0x18000925c  mov     rdx, rsi
0x18000925f  lea     rcx, qword_1800C5BD8
0x180009266  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000926b  mov     cs:dword_1800C5BF8, edi
0x180009271  lea     rdx, aMediumerrorunr_2; "MediumErrorUnrecoveredRead"
0x180009278  lea     rcx, qword_1800C5C00
0x18000927f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009284  nop
0x180009285  mov     rdx, rsi
0x180009288  lea     rcx, qword_1800C5C20
0x18000928f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009294  mov     cs:dword_1800C5C40, edi
0x18000929a  lea     rdx, aMediumerrordef_19; "MediumErrorDefectList"
0x1800092a1  lea     rcx, qword_1800C5C48
0x1800092a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800092ad  nop
0x1800092ae  mov     rdx, rsi
0x1800092b1  lea     rcx, qword_1800C5C68
0x1800092b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800092bd  mov     cs:dword_1800C5C88, edi
0x1800092c3  lea     rdx, aMediumerrordef_0; "MediumErrorDefectListNoSpare"
0x1800092ca  lea     rcx, qword_1800C5C90
0x1800092d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800092d6  nop
0x1800092d7  mov     rdx, rsi
0x1800092da  lea     rcx, qword_1800C5CB0
0x1800092e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800092e6  mov     cs:dword_1800C5CD0, edi
0x1800092ec  lea     rdx, aMediumerrordef_1; "MediumErrorDefectListUpdateFailure"
0x1800092f3  lea     rcx, qword_1800C5CD8
0x1800092fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800092ff  nop
0x180009300  mov     rdx, rsi
0x180009303  lea     rcx, qword_1800C5CF8
0x18000930a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000930f  mov     cs:dword_1800C5D18, edi
0x180009315  lea     rdx, aHardwareerrord; "HardwareErrorDefectList"
0x18000931c  lea     rcx, qword_1800C5D20
0x180009323  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009328  nop
0x180009329  mov     rdx, rsi
0x18000932c  lea     rcx, qword_1800C5D40
0x180009333  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009338  mov     cs:dword_1800C5D60, edi
0x18000933e  lea     rdx, aHardwareerrord_1; "HardwareErrorDefectListNoSpare"
0x180009345  lea     rcx, qword_1800C5D68
0x18000934c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009351  nop
0x180009352  mov     rdx, rsi
0x180009355  lea     rcx, qword_1800C5D88
0x18000935c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009361  mov     cs:dword_1800C5DA8, edi
0x180009367  lea     rdx, aHardwareerrord_0; "HardwareErrorDefectListUpdateFailure"
0x18000936e  lea     rcx, qword_1800C5DB0
0x180009375  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000937a  nop
0x18000937b  mov     rdx, rsi
0x18000937e  lea     rcx, qword_1800C5DD0
0x180009385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000938a  mov     cs:dword_1800C5DF0, edi
0x180009390  lea     rdx, aHardwareerrorl; "HardwareErrorLogicalUnitError"
0x180009397  lea     rcx, qword_1800C5DF8
0x18000939e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800093a3  nop
0x1800093a4  mov     rdx, rsi
0x1800093a7  lea     rcx, qword_1800C5E18
0x1800093ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800093b3  mov     cs:dword_1800C5E38, edi
0x1800093b9  lea     rdx, aHardwareerrorl_1; "HardwareErrorLogicalUnitErrorFailedSelf"
0x1800093c0  lea     rcx, qword_1800C5E40
0x1800093c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800093cc  nop
0x1800093cd  mov     rdx, rsi
0x1800093d0  lea     rcx, qword_1800C5E60
0x1800093d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800093dc  mov     cs:dword_1800C5E80, edi
0x1800093e2  lea     rdx, aHardwareerrorl_0; "HardwareErrorLogicalUnitErrorFailedUpda"...
0x1800093e9  lea     rcx, qword_1800C5E88
0x1800093f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800093f5  nop
0x1800093f6  mov     rdx, rsi
0x1800093f9  lea     rcx, qword_1800C5EA8
0x180009400  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009405  mov     cs:dword_1800C5EC8, edi
0x18000940b  lea     rdx, aHardwareerrord_2; "HardwareErrorDataPathFailure"
0x180009412  lea     rcx, qword_1800C5ED0
0x180009419  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000941e  nop
0x18000941f  mov     rdx, rsi
0x180009422  lea     rcx, qword_1800C5EF0
0x180009429  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000942e  mov     cs:dword_1800C5F10, edi
0x180009434  lea     rdx, aHardwareerrorp; "HardwareErrorPowerOnSelfTestFailure"
0x18000943b  lea     rcx, qword_1800C5F18
0x180009442  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009447  nop
0x180009448  mov     rdx, rsi
0x18000944b  lea     rcx, qword_1800C5F38
0x180009452  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009457  mov     cs:dword_1800C5F58, edi
0x18000945d  lea     rdx, aHardwareerrori; "HardwareErrorInternalTargetFailure"
0x180009464  lea     rcx, qword_1800C5F60
0x18000946b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009470  nop
0x180009471  mov     rdx, rsi
0x180009474  lea     rcx, qword_1800C5F80
0x18000947b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009480  mov     cs:dword_1800C5FA0, edi
0x180009486  lea     rdx, aHardwareerrori_0; "HardwareErrorInternalTargetFailureInter"...
0x18000948d  lea     rcx, qword_1800C5FA8
0x180009494  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009499  nop
0x18000949a  mov     rdx, rsi
0x18000949d  lea     rcx, qword_1800C5FC8
0x1800094a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800094a9  mov     cs:dword_1800C5FE8, edi
0x1800094af  lea     rdx, aHardwareerrorf; "HardwareErrorFailedSelfConfiguration"
0x1800094b6  lea     rcx, qword_1800C5FF0
0x1800094bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800094c2  nop
0x1800094c3  mov     rdx, rsi
0x1800094c6  lea     rcx, qword_1800C6010
0x1800094cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
