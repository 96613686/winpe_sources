# CUpdateDeferralPolicyChecker::CUpdateDeferralPolicyChecker(void)

- ea: `0x1800c8d74`
- end: `0x1800c904c`
- name: `??0CUpdateDeferralPolicyChecker@@QEAA@XZ`
- size: `728`
- prototype: `CUpdateDeferralPolicyChecker *__fastcall(CUpdateDeferralPolicyChecker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1800c8030`
- `0x1800d0bf0`

## callees

- `0x180015c04`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800c8fcd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8fe9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8ff7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c9008`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8fcd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8fe9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c8ff7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c9008`

## string_xrefs

- `0x1800c8e54`: `DeferFeatureUpdates`
- `0x1800c8da9`: `DeferQualityUpdates`
- `0x1800c8e70`: `FeatureUpdatesDeferralInDays`
- `0x1800c8e62`: `QualityUpdatesDeferralInDays`
- `0x1800c8e8c`: `QualityUpdatesPaused`
- `0x1800c8e7e`: `BranchReadinessLevel`
- `0x1800c8e9a`: `FeatureUpdatesPaused`
- `0x1800c8ec4`: `FeatureUpdatePausePeriodInDays`
- `0x1800c8eb6`: `QualityUpdatePausePeriodInDays`
- `0x1800c8ee0`: `PauseFeatureUpdatesEndTime`
- `0x1800c8ed2`: `PauseFeatureUpdatesStartTime`
- `0x1800c8efc`: `PauseQualityUpdatesEndTime`
- `0x1800c8eee`: `PauseQualityUpdatesStartTime`
- `0x1800c8f18`: `IsWUfBConfigured`
- `0x1800c8f79`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1800c8f66`: `UseUpdateClassPolicySource`
- `0x1800c8f95`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1800c8f87`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1800c8fb1`: `TemporaryEnterpriseFeatureControlState`
- `0x1800c8fa3`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1800c8fbf`: `TemporaryEnterpriseFeatureControlState_Mirrored`

## pseudocode

```c
CUpdateDeferralPolicyChecker *__fastcall CUpdateDeferralPolicyChecker::CUpdateDeferralPolicyChecker(
        CUpdateDeferralPolicyChecker *this)
{
  *(_WORD *)this = 0;
  *((_QWORD *)this + 5) = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
  *((_QWORD *)this + 9) = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *(GUID *)((char *)this + 168) = GUID_ebfc1fc5_71a4_4f7b_9aca_3b9a503104a0;
  *((_WORD *)this + 1) = -1;
  *((_WORD *)this + 2) = -1;
  *((_DWORD *)this + 3) = 0;
  *((_BYTE *)this + 24) = -1;
  *((_BYTE *)this + 25) = -1;
  *((_BYTE *)this + 26) = -1;
  *(_WORD *)((char *)this + 27) = 0;
  *((_BYTE *)this + 29) = 0;
  *((_WORD *)this + 15) = -1;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 152) = 0;
  *((_BYTE *)this + 153) = -1;
  *((_BYTE *)this + 154) = -1;
  *((_BYTE *)this + 155) = -1;
  *((_BYTE *)this + 156) = -1;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 41) = 5;
  *((_QWORD *)this + 25) = L"DeferQualityUpdates";
  *((_QWORD *)this + 26) = L"DeferFeatureUpdates";
  *((_QWORD *)this + 27) = L"QualityUpdatesDeferralInDays";
  *((_QWORD *)this + 28) = L"FeatureUpdatesDeferralInDays";
  *((_QWORD *)this + 29) = L"BranchReadinessLevel";
  *((_QWORD *)this + 30) = L"QualityUpdatesPaused";
  *((_QWORD *)this + 31) = L"FeatureUpdatesPaused";
  *((_QWORD *)this + 32) = L"ExcludeWUDrivers";
  *((_QWORD *)this + 33) = L"QualityUpdatePausePeriodInDays";
  *((_QWORD *)this + 34) = L"FeatureUpdatePausePeriodInDays";
  *((_QWORD *)this + 35) = L"PauseFeatureUpdatesStartTime";
  *((_QWORD *)this + 36) = L"PauseFeatureUpdatesEndTime";
  *((_QWORD *)this + 37) = L"PauseQualityUpdatesStartTime";
  *((_QWORD *)this + 38) = L"PauseQualityUpdatesEndTime";
  *((_QWORD *)this + 39) = L"IsDeferralIsActive";
  *((_QWORD *)this + 40) = L"IsWUfBConfigured";
  *((_QWORD *)this + 41) = L"IsWUfBDualScanActive";
  *((_QWORD *)this + 42) = L"TargetProductVersion";
  *((_QWORD *)this + 43) = L"TargetReleaseVersion";
  *((_QWORD *)this + 44) = L"PolicySources";
  *(GUID *)((char *)this + 184) = GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 45) = L"UseUpdateClassPolicySource";
  *((_QWORD *)this + 46) = L"SetPolicyDrivenUpdateSourceForFeatureUpdates";
  *((_QWORD *)this + 47) = L"SetPolicyDrivenUpdateSourceForQualityUpdates";
  *((_QWORD *)this + 48) = L"SetPolicyDrivenUpdateSourceForDriverUpdates";
  *((_QWORD *)this + 49) = L"SetPolicyDrivenUpdateSourceForOtherUpdates";
  *((_QWORD *)this + 50) = L"TemporaryEnterpriseFeatureControlState";
  *((_QWORD *)this + 51) = L"TemporaryEnterpriseFeatureControlState_Mirrored";
  SysFreeString(0);
  *((_QWORD *)this + 2) = 0;
  SysFreeString(*((BSTR *)this + 13));
  *((_QWORD *)this + 13) = 0;
  SysFreeString(*((BSTR *)this + 14));
  *((_QWORD *)this + 14) = 0;
  SysFreeString(*((BSTR *)this + 15));
  *((_QWORD *)this + 15) = 0;
  SysFreeString(*((BSTR *)this + 16));
  *((_QWORD *)this + 16) = 0;
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::RemoveArraySection((char *)this + 40, 0, 0xFFFFFFFFLL);
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::RemoveArraySection((char *)this + 72, 0, 0xFFFFFFFFLL);
  return this;
}

```

## disassembly

```asm
0x1800c8d74  mov     [rsp+arg_0], rbx
0x1800c8d79  mov     [rsp+arg_8], rbp
0x1800c8d7e  mov     [rsp+arg_10], rsi
0x1800c8d83  push    rdi
0x1800c8d84  sub     rsp, 20h
0x1800c8d88  mov     rsi, rcx
0x1800c8d8b  lea     rax, ??_7?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@6B@; const CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable'
0x1800c8d92  movups  xmm0, xmmword ptr cs:_GUID_ebfc1fc5_71a4_4f7b_9aca_3b9a503104a0.Data1
0x1800c8d99  xor     ebp, ebp
0x1800c8d9b  mov     [rcx], bp
0x1800c8d9e  or      ecx, 0FFFFFFFFh
0x1800c8da1  mov     [rsi+28h], rax
0x1800c8da5  mov     [rsi+48h], rax
0x1800c8da9  lea     rax, aDeferqualityup; "DeferQualityUpdates"
0x1800c8db0  mov     [rsi+10h], rbp
0x1800c8db4  mov     [rsi+30h], rbp
0x1800c8db8  mov     [rsi+38h], rbp
0x1800c8dbc  mov     [rsi+40h], ebp
0x1800c8dbf  mov     [rsi+50h], rbp
0x1800c8dc3  mov     [rsi+58h], rbp
0x1800c8dc7  mov     [rsi+60h], ebp
0x1800c8dca  mov     [rsi+68h], rbp
0x1800c8dce  mov     [rsi+70h], rbp
0x1800c8dd2  mov     [rsi+78h], rbp
0x1800c8dd6  mov     [rsi+80h], rbp
0x1800c8ddd  mov     [rsi+88h], rbp
0x1800c8de4  mov     [rsi+90h], rbp
0x1800c8deb  movdqu  xmmword ptr [rsi+0A8h], xmm0
0x1800c8df3  mov     [rsi+2], cx
0x1800c8df7  mov     [rsi+4], cx
0x1800c8dfb  mov     [rsi+0Ch], ebp
0x1800c8dfe  mov     [rsi+18h], cl
0x1800c8e01  mov     [rsi+19h], cl
0x1800c8e04  mov     [rsi+1Ah], cl
0x1800c8e07  mov     [rsi+1Bh], bp
0x1800c8e0b  mov     [rsi+1Dh], bpl
0x1800c8e0f  mov     [rsi+1Eh], cx
0x1800c8e13  mov     [rsi+20h], rbp
0x1800c8e17  mov     [rsi+98h], bpl
0x1800c8e1e  mov     [rsi+99h], cl
0x1800c8e24  mov     [rsi+9Ah], cl
0x1800c8e2a  mov     [rsi+9Bh], cl
0x1800c8e30  mov     [rsi+9Ch], cl
0x1800c8e36  mov     [rsi+0A0h], ebp
0x1800c8e3c  mov     dword ptr [rsi+0A4h], 5
0x1800c8e46  movups  xmm1, xmmword ptr cs:_GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data1
0x1800c8e4d  mov     [rsi+0C8h], rax
0x1800c8e54  lea     rax, aDeferfeatureup; "DeferFeatureUpdates"
0x1800c8e5b  mov     [rsi+0D0h], rax
0x1800c8e62  lea     rax, aQualityupdates_1; "QualityUpdatesDeferralInDays"
0x1800c8e69  mov     [rsi+0D8h], rax
0x1800c8e70  lea     rax, aFeatureupdates_0; "FeatureUpdatesDeferralInDays"
0x1800c8e77  mov     [rsi+0E0h], rax
0x1800c8e7e  lea     rax, aBranchreadines; "BranchReadinessLevel"
0x1800c8e85  mov     [rsi+0E8h], rax
0x1800c8e8c  lea     rax, aQualityupdates_0; "QualityUpdatesPaused"
0x1800c8e93  mov     [rsi+0F0h], rax
0x1800c8e9a  lea     rax, aFeatureupdates; "FeatureUpdatesPaused"
0x1800c8ea1  mov     [rsi+0F8h], rax
0x1800c8ea8  lea     rax, aExcludewudrive; "ExcludeWUDrivers"
0x1800c8eaf  mov     [rsi+100h], rax
0x1800c8eb6  lea     rax, aQualityupdatep; "QualityUpdatePausePeriodInDays"
0x1800c8ebd  mov     [rsi+108h], rax
0x1800c8ec4  lea     rax, aFeatureupdatep; "FeatureUpdatePausePeriodInDays"
0x1800c8ecb  mov     [rsi+110h], rax
0x1800c8ed2  lea     rax, aPausefeatureup_0; "PauseFeatureUpdatesStartTime"
0x1800c8ed9  mov     [rsi+118h], rax
0x1800c8ee0  lea     rax, aPausefeatureup; "PauseFeatureUpdatesEndTime"
0x1800c8ee7  mov     [rsi+120h], rax
0x1800c8eee  lea     rax, aPausequalityup_0; "PauseQualityUpdatesStartTime"
0x1800c8ef5  mov     [rsi+128h], rax
0x1800c8efc  lea     rax, aPausequalityup; "PauseQualityUpdatesEndTime"
0x1800c8f03  mov     [rsi+130h], rax
0x1800c8f0a  lea     rax, aIsdeferralisac; "IsDeferralIsActive"
0x1800c8f11  mov     [rsi+138h], rax
0x1800c8f18  lea     rax, aIswufbconfigur; "IsWUfBConfigured"
0x1800c8f1f  mov     [rsi+140h], rax
0x1800c8f26  lea     rax, aIswufbdualscan; "IsWUfBDualScanActive"
0x1800c8f2d  mov     [rsi+148h], rax
0x1800c8f34  lea     rax, aTargetproductv; "TargetProductVersion"
0x1800c8f3b  mov     [rsi+150h], rax
0x1800c8f42  lea     rax, aTargetreleasev; "TargetReleaseVersion"
0x1800c8f49  mov     [rsi+158h], rax
0x1800c8f50  lea     rax, aPolicysources; "PolicySources"
0x1800c8f57  mov     [rsi+160h], rax
0x1800c8f5e  movdqu  xmmword ptr [rsi+0B8h], xmm1
0x1800c8f66  lea     rax, aUseupdateclass; "UseUpdateClassPolicySource"
0x1800c8f6d  mov     [rsi+8], ebp
0x1800c8f70  mov     [rsi+168h], rax
0x1800c8f77  xor     ecx, ecx; bstrString
0x1800c8f79  lea     rax, aSetpolicydrive_1; "SetPolicyDrivenUpdateSourceForFeatureUp"...
0x1800c8f80  mov     [rsi+170h], rax
0x1800c8f87  lea     rax, aSetpolicydrive_2; "SetPolicyDrivenUpdateSourceForQualityUp"...
0x1800c8f8e  mov     [rsi+178h], rax
0x1800c8f95  lea     rax, aSetpolicydrive_0; "SetPolicyDrivenUpdateSourceForDriverUpd"...
0x1800c8f9c  mov     [rsi+180h], rax
0x1800c8fa3  lea     rax, aSetpolicydrive; "SetPolicyDrivenUpdateSourceForOtherUpda"...
0x1800c8faa  mov     [rsi+188h], rax
0x1800c8fb1  lea     rax, aTemporaryenter_0; "TemporaryEnterpriseFeatureControlState"
0x1800c8fb8  mov     [rsi+190h], rax
0x1800c8fbf  lea     rax, aTemporaryenter; "TemporaryEnterpriseFeatureControlState_"...
0x1800c8fc6  mov     [rsi+198h], rax
0x1800c8fcd  call    cs:__imp_SysFreeString
0x1800c8fd3  mov     [rsi+10h], rbp
0x1800c8fd7  mov     rcx, [rsi+68h]; bstrString
0x1800c8fdb  call    cs:__imp_SysFreeString
0x1800c8fe1  mov     [rsi+68h], rbp
0x1800c8fe5  mov     rcx, [rsi+70h]; bstrString
0x1800c8fe9  call    cs:__imp_SysFreeString
0x1800c8fef  mov     [rsi+70h], rbp
0x1800c8ff3  mov     rcx, [rsi+78h]; bstrString
0x1800c8ff7  call    cs:__imp_SysFreeString
0x1800c8ffd  mov     [rsi+78h], rbp
0x1800c9001  mov     rcx, [rsi+80h]; bstrString
0x1800c9008  call    cs:__imp_SysFreeString
0x1800c900e  mov     [rsi+80h], rbp
0x1800c9015  lea     rcx, [rsi+28h]
0x1800c9019  or      ebp, 0FFFFFFFFh
0x1800c901c  xor     edx, edx
0x1800c901e  mov     r8d, ebp
0x1800c9021  call    ?RemoveArraySection@?$CSusArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@IEAAXKKH@Z; CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::RemoveArraySection(ulong,ulong,int)
0x1800c9026  mov     r8d, ebp
0x1800c9029  lea     rcx, [rsi+48h]
0x1800c902d  xor     edx, edx
0x1800c902f  call    ?RemoveArraySection@?$CSusArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@IEAAXKKH@Z; CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::RemoveArraySection(ulong,ulong,int)
0x1800c9034  mov     rbx, [rsp+28h+arg_0]
0x1800c9039  mov     rax, rsi
0x1800c903c  mov     rsi, [rsp+28h+arg_10]
0x1800c9041  mov     rbp, [rsp+28h+arg_8]
0x1800c9046  add     rsp, 20h
0x1800c904a  pop     rdi
0x1800c904b  retn
```
