# SclStateRecordResults

- ea: `0x180003408`
- end: `0x180004384`
- name: `SclStateRecordResults`
- size: `3964`
- prototype: `__int64 __fastcall(int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800065f8`

## callees

- `0x1800014e8`
- `0x180001ec4`
- `0x180003408`
- `0x18000a334`
- `0x18000a524`
- `0x18000de94`

## import_xrefs

- `ntdll!NtClose` at `0x180004323`
- `ntdll!NtClose` at `0x180004323`
- `ntdll!NtFlushKey` at `0x18000430f`
- `ntdll!NtFlushKey` at `0x180004319`
- `ntdll!NtFlushKey` at `0x18000430f`
- `ntdll!NtFlushKey` at `0x180004319`

## string_xrefs

- `0x180003473`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL`
- `0x1800034ab`: `Number of registry keys processed`
- `0x1800034f2`: `Number of registry keys processed`
- `0x180003bad`: `Number of registry keys processed`
- `0x180003514`: `Number of registry keys renamed`
- `0x180003547`: `Number of registry keys renamed`
- `0x180003bcf`: `Number of registry keys renamed`
- `0x180003c09`: `Number of registry keys renamed`
- `0x180003553`: `RegKeyRenameCount`
- `0x180003c15`: `RegKeyRenameCount`
- `0x180003569`: `Number of registry values processed`
- `0x18000359c`: `Number of registry values processed`
- `0x180003c2b`: `Number of registry values processed`
- `0x180003c65`: `Number of registry values processed`
- `0x1800035be`: `Number of registry values renamed`
- `0x1800035f1`: `Number of registry values renamed`
- `0x180003c87`: `Number of registry values renamed`
- `0x180003cc1`: `Number of registry values renamed`
- `0x1800035fd`: `RegValueRenameCount`
- `0x180003ccd`: `RegValueRenameCount`
- `0x180003613`: `Number of registry values updated`
- `0x180003646`: `Number of registry values updated`
- `0x180003ce3`: `Number of registry values updated`
- `0x180003d1d`: `Number of registry values updated`
- `0x180003652`: `RegDataUpdateCount`
- `0x180003d29`: `RegDataUpdateCount`
- `0x180003668`: `Number of registry security descriptors updated`
- `0x18000369b`: `Number of registry security descriptors updated`
- `0x180003d3f`: `Number of registry security descriptors updated`
- `0x180003d79`: `Number of registry security descriptors updated`
- `0x1800036a7`: `SecObjectSDUpdateCount`
- `0x180003d85`: `SecObjectSDUpdateCount`
- `0x1800036bd`: `Number of registry security descriptors processed`
- `0x1800036f0`: `Number of registry security descriptors processed`
- `0x180003d9b`: `Number of registry security descriptors processed`
- `0x180003dd5`: `Number of registry security descriptors processed`
- `0x180003712`: `Number of $Secure security descriptors updated`
- `0x180003745`: `Number of $Secure security descriptors updated`
- `0x180003df7`: `Number of $Secure security descriptors updated`
- `0x180003e31`: `Number of $Secure security descriptors updated`
- `0x180003751`: `FsSecureSDUpdateCount`
- `0x180003e3d`: `FsSecureSDUpdateCount`
- `0x180003767`: `Number of $Secure security descriptors failed`
- `0x18000379a`: `Number of $Secure security descriptors failed`
- `0x180003e53`: `Number of $Secure security descriptors failed`
- `0x180003e8d`: `Number of $Secure security descriptors failed`
- `0x1800037a6`: `FsSecureSDFailedUpdateCount`
- `0x180003e99`: `FsSecureSDFailedUpdateCount`
- `0x1800037bc`: `Number of $Secure security descriptors processed`
- `0x1800037ef`: `Number of $Secure security descriptors processed`
- `0x180003eaf`: `Number of $Secure security descriptors processed`
- `0x180003ee9`: `Number of $Secure security descriptors processed`
- `0x180003811`: `Number of $MFT security descriptors updated`
- `0x180003844`: `Number of $MFT security descriptors updated`
- `0x180003f0b`: `Number of $MFT security descriptors updated`
- `0x180003f45`: `Number of $MFT security descriptors updated`
- `0x180003850`: `FsMftSDUpdateCount`
- `0x180003f51`: `FsMftSDUpdateCount`
- `0x180003866`: `Number of $MFT security descriptors failed`
- `0x180003899`: `Number of $MFT security descriptors failed`
- `0x180003f67`: `Number of $MFT security descriptors failed`
- `0x180003fa1`: `Number of $MFT security descriptors failed`
- `0x1800038a5`: `FsMftSDFailedUpdateCount`
- `0x180003fad`: `FsMftSDFailedUpdateCount`
- `0x1800038bb`: `Number of $MFT security descriptors processed`
- `0x1800038ee`: `Number of $MFT security descriptors processed`
- `0x180003fc3`: `Number of $MFT security descriptors processed`
- `0x180003ffd`: `Number of $MFT security descriptors processed`
- `0x180003910`: `Number of reparse points processed`
- `0x180003943`: `Number of reparse points processed`
- `0x18000401f`: `Number of reparse points processed`
- `0x180004059`: `Number of reparse points processed`
- `0x18000394f`: `ReparsePointProcessCount`
- `0x180004065`: `ReparsePointProcessCount`
- `0x180003965`: `Number of reparse points updated`
- `0x180003998`: `Number of reparse points updated`
- `0x18000407b`: `Number of reparse points updated`
- `0x1800040b5`: `Number of reparse points updated`
- `0x1800039a4`: `ReparsePointUpdateCount`
- `0x1800040c1`: `ReparsePointUpdateCount`
- `0x1800039d2`: `Time spent processing registry (in ms)`
- `0x180003a30`: `Time spent processing registry (in ms)`
- `0x1800040ed`: `Time spent processing registry (in ms)`
- `0x18000414c`: `Time spent processing registry (in ms)`
- `0x180003ab3`: `FileACLTime`
- `0x1800041cf`: `FileACLTime`

## pseudocode

```c
__int64 __fastcall SclStateRecordResults(int a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r10
  int v5; // r11d
  __int64 v6; // rcx
  const WCHAR *v7; // rdx
  int Key; // eax
  __int64 v9; // rbx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // rdx
  char v42; // r12
  __int64 v43; // rdx
  __int64 v44; // rdx
  char v45; // r15
  __int64 v46; // rdx
  __int64 v47; // r15
  __int64 v48; // rdx
  __int64 v49; // rbx
  __int64 v50; // rdx
  __int64 v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rbx
  __int64 v54; // rdx
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rbx
  __int64 v58; // rdx
  __int64 v59; // rbx
  __int64 v60; // rdx
  __int64 v61; // rbx
  __int64 v62; // rdx
  __int64 v63; // rbx
  __int64 v64; // rdx
  __int64 v65; // rbx
  __int64 v66; // rdx
  __int64 v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // rbx
  __int64 v70; // rdx
  __int64 v71; // rbx
  __int64 v72; // rdx
  __int64 v73; // rbx
  __int64 v74; // rdx
  __int64 v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rdx
  char v78; // r15
  __int64 v79; // rdx
  __int64 v80; // rdx
  char v81; // r13
  __int64 v82; // rdx
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  HANDLE v85; // [rsp+48h] [rbp-18h]
  HANDLE v86; // [rsp+50h] [rbp-10h]
  int v87; // [rsp+A0h] [rbp+40h] BYREF
  BOOL v88; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v89; // [rsp+B8h] [rbp+58h] BYREF

  v87 = a1;
  KeyHandle = 0;
  if ( !a2 || !SclOSIsValid(a3) )
    return 3221225485LL;
  v6 = 0;
  v88 = v5 >= 0;
  if ( v4 && *(_DWORD *)v4 == 2 )
    v6 = *(_QWORD *)(v4 + 56);
  v7 = L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL";
  if ( v6 )
    v7 = L"SETUP\\SETUPCL";
  Key = SclCreateKey(v6, v7, 0xF003Fu, (__int64)&KeyHandle);
  v9 = *(_QWORD *)(a2 + 1192);
  v10 = Key;
  v11 = a2 + 1152;
  if ( Key < 0 )
  {
    SclLogGenericMessage(
      v11,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry keys processed",
      v9);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v48,
      (__int64)L"RegKeyProcessCount",
      (__int64)L"Number of registry keys processed",
      v9);
    v49 = *(_QWORD *)(a2 + 1200);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry keys renamed",
      v49);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v50,
      (__int64)L"RegKeyRenameCount",
      (__int64)L"Number of registry keys renamed",
      v49);
    v51 = *(_QWORD *)(a2 + 1208);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry values processed",
      v51);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v52,
      (__int64)L"RegValueProcessCount",
      (__int64)L"Number of registry values processed",
      v51);
    v53 = *(_QWORD *)(a2 + 1216);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry values renamed",
      v53);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v54,
      (__int64)L"RegValueRenameCount",
      (__int64)L"Number of registry values renamed",
      v53);
    v55 = *(_QWORD *)(a2 + 1224);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry values updated",
      v55);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v56,
      (__int64)L"RegDataUpdateCount",
      (__int64)L"Number of registry values updated",
      v55);
    v57 = *(_QWORD *)(a2 + 1232);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry security descriptors updated",
      v57);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v58,
      (__int64)L"SecObjectSDUpdateCount",
      (__int64)L"Number of registry security descriptors updated",
      v57);
    v59 = *(_QWORD *)(a2 + 1240);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of registry security descriptors processed",
      v59);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v60,
      (__int64)L"SecObjectSDProcessCount",
      (__int64)L"Number of registry security descriptors processed",
      v59);
    v61 = *(_QWORD *)(a2 + 1248);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of $Secure security descriptors updated",
      v61);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v62,
      (__int64)L"FsSecureSDUpdateCount",
      (__int64)L"Number of $Secure security descriptors updated",
      v61);
    v63 = *(_QWORD *)(a2 + 1256);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of $Secure security descriptors failed",
      v63);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v64,
      (__int64)L"FsSecureSDFailedUpdateCount",
      (__int64)L"Number of $Secure security descriptors failed",
      v63);
    v65 = *(_QWORD *)(a2 + 1264);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of $Secure security descriptors processed",
      v65);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v66,
      (__int64)L"FsSecureSDProcessCount",
      (__int64)L"Number of $Secure security descriptors processed",
      v65);
    v67 = *(_QWORD *)(a2 + 1272);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of $MFT security descriptors updated",
      v67);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v68,
      (__int64)L"FsMftSDUpdateCount",
      (__int64)L"Number of $MFT security descriptors updated",
      v67);
    v69 = *(_QWORD *)(a2 + 1280);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of $MFT security descriptors failed",
      v69);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v70,
      (__int64)L"FsMftSDFailedUpdateCount",
      (__int64)L"Number of $MFT security descriptors failed",
      v69);
    v71 = *(_QWORD *)(a2 + 1288);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of $MFT security descriptors processed",
      v71);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v72,
      (__int64)L"FsMftSDProcessCount",
      (__int64)L"Number of $MFT security descriptors processed",
      v71);
    v73 = *(_QWORD *)(a2 + 1296);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of reparse points processed",
      v73);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v74,
      (__int64)L"ReparsePointProcessCount",
      (__int64)L"Number of reparse points processed",
      v73);
    v75 = *(_QWORD *)(a2 + 1304);
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Number of reparse points updated",
      v75);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v76,
      (__int64)L"ReparsePointUpdateCount",
      (__int64)L"Number of reparse points updated",
      v75);
    v89 = *(_QWORD *)(a2 + 1312);
    v86 = KeyHandle;
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Time spent processing registry (in ms)",
      v89);
    v78 = v89;
    if ( *(_BYTE *)a2 )
      SclRegSetValue(v86, v77, (__int64)L"HiveTime", &v89, 4u, 4u);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v77,
      (__int64)L"RegProcessingTimeInMS",
      (__int64)L"Time spent processing registry (in ms)",
      v78);
    goto LABEL_22;
  }
  SclLogGenericMessage(
    v11,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry keys processed",
    v9);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v12,
    (__int64)L"RegKeyProcessCount",
    (__int64)L"Number of registry keys processed",
    v9);
  v13 = *(_QWORD *)(a2 + 1200);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry keys renamed",
    v13);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v14,
    (__int64)L"RegKeyRenameCount",
    (__int64)L"Number of registry keys renamed",
    v13);
  v15 = *(_QWORD *)(a2 + 1208);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry values processed",
    v15);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v16,
    (__int64)L"RegValueProcessCount",
    (__int64)L"Number of registry values processed",
    v15);
  v17 = *(_QWORD *)(a2 + 1216);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry values renamed",
    v17);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v18,
    (__int64)L"RegValueRenameCount",
    (__int64)L"Number of registry values renamed",
    v17);
  v19 = *(_QWORD *)(a2 + 1224);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry values updated",
    v19);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v20,
    (__int64)L"RegDataUpdateCount",
    (__int64)L"Number of registry values updated",
    v19);
  v21 = *(_QWORD *)(a2 + 1232);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry security descriptors updated",
    v21);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v22,
    (__int64)L"SecObjectSDUpdateCount",
    (__int64)L"Number of registry security descriptors updated",
    v21);
  v23 = *(_QWORD *)(a2 + 1240);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of registry security descriptors processed",
    v23);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v24,
    (__int64)L"SecObjectSDProcessCount",
    (__int64)L"Number of registry security descriptors processed",
    v23);
  v25 = *(_QWORD *)(a2 + 1248);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of $Secure security descriptors updated",
    v25);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v26,
    (__int64)L"FsSecureSDUpdateCount",
    (__int64)L"Number of $Secure security descriptors updated",
    v25);
  v27 = *(_QWORD *)(a2 + 1256);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of $Secure security descriptors failed",
    v27);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v28,
    (__int64)L"FsSecureSDFailedUpdateCount",
    (__int64)L"Number of $Secure security descriptors failed",
    v27);
  v29 = *(_QWORD *)(a2 + 1264);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of $Secure security descriptors processed",
    v29);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v30,
    (__int64)L"FsSecureSDProcessCount",
    (__int64)L"Number of $Secure security descriptors processed",
    v29);
  v31 = *(_QWORD *)(a2 + 1272);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of $MFT security descriptors updated",
    v31);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v32,
    (__int64)L"FsMftSDUpdateCount",
    (__int64)L"Number of $MFT security descriptors updated",
    v31);
  v33 = *(_QWORD *)(a2 + 1280);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of $MFT security descriptors failed",
    v33);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v34,
    (__int64)L"FsMftSDFailedUpdateCount",
    (__int64)L"Number of $MFT security descriptors failed",
    v33);
  v35 = *(_QWORD *)(a2 + 1288);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of $MFT security descriptors processed",
    v35);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v36,
    (__int64)L"FsMftSDProcessCount",
    (__int64)L"Number of $MFT security descriptors processed",
    v35);
  v37 = *(_QWORD *)(a2 + 1296);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of reparse points processed",
    v37);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v38,
    (__int64)L"ReparsePointProcessCount",
    (__int64)L"Number of reparse points processed",
    v37);
  v39 = *(_QWORD *)(a2 + 1304);
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Number of reparse points updated",
    v39);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v40,
    (__int64)L"ReparsePointUpdateCount",
    (__int64)L"Number of reparse points updated",
    v39);
  v89 = *(_QWORD *)(a2 + 1312);
  v10 = 0;
  v85 = KeyHandle;
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Time spent processing registry (in ms)",
    v89);
  v42 = v89;
  if ( *(_BYTE *)a2 )
    v10 = SclRegSetValue(v85, v41, (__int64)L"HiveTime", &v89, 4u, 4u);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v41,
    (__int64)L"RegProcessingTimeInMS",
    (__int64)L"Time spent processing registry (in ms)",
    v42);
  if ( v10 < 0 )
  {
LABEL_22:
    v85 = *(HANDLE *)(a2 + 1320);
    v47 = a2 + 1152;
    v86 = KeyHandle;
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Time spent processing volumes (in ms)",
      v85);
    if ( *(_BYTE *)a2 )
    {
      LODWORD(v89) = (_DWORD)v85;
      SclRegSetValue(v86, v79, (__int64)L"FileACLTime", &v89, 4u, 4u);
    }
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v79,
      (__int64)L"FsProcessingTimeInMS",
      (__int64)L"Time spent processing volumes (in ms)",
      (char)v85);
    goto LABEL_25;
  }
  v10 = 0;
  v85 = *(HANDLE *)(a2 + 1320);
  v86 = KeyHandle;
  SclLogGenericMessage(
    a2 + 1152,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Time spent processing volumes (in ms)",
    v85);
  if ( *(_BYTE *)a2 )
  {
    LODWORD(v89) = (_DWORD)v85;
    v10 = SclRegSetValue(v86, v43, (__int64)L"FileACLTime", &v89, 4u, 4u);
  }
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v43,
    (__int64)L"FsProcessingTimeInMS",
    (__int64)L"Time spent processing volumes (in ms)",
    (char)v85);
  if ( v10 >= 0 )
  {
    v10 = 0;
    v89 = *(_QWORD *)(a2 + 1328);
    v86 = KeyHandle;
    SclLogGenericMessage(
      a2 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      227,
      (__int64)"SclpStateRecordStatField",
      "STAT: %ws = %I64u",
      L"Total time spent processing (in ms)",
      v89);
    v45 = v89;
    if ( *(_BYTE *)a2 )
      v10 = SclRegSetValue(v86, v44, (__int64)L"RunTime", &v89, 4u, 4u);
    SclEtwWriteStringStringUll(
      a2 + 1152,
      v44,
      (__int64)L"TotalProcessingTimeInMS",
      (__int64)L"Total time spent processing (in ms)",
      v45);
    v47 = a2 + 1152;
    goto LABEL_28;
  }
  v47 = a2 + 1152;
LABEL_25:
  v89 = *(_QWORD *)(a2 + 1328);
  v86 = KeyHandle;
  SclLogGenericMessage(
    v47,
    1,
    (int)SclEvent_Generic_Info,
    227,
    (__int64)"SclpStateRecordStatField",
    "STAT: %ws = %I64u",
    L"Total time spent processing (in ms)",
    v89);
  v81 = v89;
  if ( *(_BYTE *)a2 )
    SclRegSetValue(v86, v80, (__int64)L"RunTime", &v89, 4u, 4u);
  SclEtwWriteStringStringUll(
    a2 + 1152,
    v80,
    (__int64)L"TotalProcessingTimeInMS",
    (__int64)L"Total time spent processing (in ms)",
    v81);
LABEL_28:
  if ( *(_BYTE *)a2 )
  {
    if ( v10 < 0 )
    {
      SclRegSetValue(KeyHandle, v46, (__int64)L"ExecutionSuccessful", &v88, 4u, 4u);
    }
    else
    {
      v10 = SclRegSetValue(KeyHandle, v46, (__int64)L"ExecutionSuccessful", &v88, 4u, 4u);
      if ( v10 >= 0 )
      {
        v10 = SclRegSetValue(KeyHandle, v82, (__int64)L"NTSTATUS", &v87, 4u, 4u);
        goto LABEL_34;
      }
    }
    SclRegSetValue(KeyHandle, v82, (__int64)L"NTSTATUS", &v87, 4u, 4u);
  }
LABEL_34:
  if ( KeyHandle )
  {
    if ( v10 < 0 )
      NtFlushKey(KeyHandle);
    else
      v10 = NtFlushKey(KeyHandle);
    NtClose(KeyHandle);
  }
  if ( v10 < 0 )
    SclLogGenericMessage(
      v47,
      3,
      (int)SclEvent_Generic_Error,
      195,
      (__int64)"SclStateRecordResults",
      "(%lx): Failed to record perf results",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003408  mov     [rsp-38h+arg_10], rbx
0x18000340d  mov     [rsp-38h+arg_0], ecx
0x180003411  push    rbp
0x180003412  push    rsi
0x180003413  push    rdi
0x180003414  push    r12
0x180003416  push    r13
0x180003418  push    r14
0x18000341a  push    r15
0x18000341c  mov     rbp, rsp
0x18000341f  sub     rsp, 60h
0x180003423  mov     [rbp+KeyHandle], 0
0x18000342b  mov     r10, r8
0x18000342e  mov     r14, rdx
0x180003431  mov     r11d, ecx
0x180003434  test    rdx, rdx
0x180003437  jz      loc_180004367
0x18000343d  mov     rcx, r8
0x180003440  call    SclOSIsValid
0x180003445  test    al, al
0x180003447  jz      loc_180004367
0x18000344d  xor     eax, eax
0x18000344f  xor     ecx, ecx
0x180003451  test    r11d, r11d
0x180003454  setns   al
0x180003457  mov     [rbp+arg_8], eax
0x18000345a  test    r10, r10
0x18000345d  jz      short loc_180003469
0x18000345f  cmp     dword ptr [r10], 2
0x180003463  jnz     short loc_180003469
0x180003465  mov     rcx, [r10+38h]
0x180003469  test    rcx, rcx
0x18000346c  lea     rax, aSetupSetupcl; "SETUP\\SETUPCL"
0x180003473  lea     rdx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x18000347a  mov     r8d, 0F003Fh
0x180003480  cmovnz  rdx, rax
0x180003484  lea     r9, [rbp+KeyHandle]
0x180003488  call    SclCreateKey
0x18000348d  mov     rbx, [r14+4A8h]
0x180003494  lea     rsi, [r14+480h]
0x18000349b  mov     edi, eax
0x18000349d  mov     [rsp+60h+var_28], rbx
0x1800034a2  test    eax, eax
0x1800034a4  lea     r15, SclEvent_Generic_Info
0x1800034ab  lea     rax, aNumberOfRegist_0; "Number of registry keys processed"
0x1800034b2  mov     r13d, 0E3h
0x1800034b8  mov     r12d, 1
0x1800034be  mov     [rsp+60h+var_30], rax
0x1800034c3  mov     rcx, rsi
0x1800034c6  mov     r9d, r13d
0x1800034c9  mov     r8, r15
0x1800034cc  mov     edx, r12d
0x1800034cf  js      loc_180003B90
0x1800034d5  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x1800034dc  lea     rdi, aStatWsI64u; "STAT: %ws = %I64u"
0x1800034e3  mov     [rsp+60h+var_38], rdi
0x1800034e8  mov     [rsp+60h+var_40], rax
0x1800034ed  call    SclLogGenericMessage
0x1800034f2  lea     r9, aNumberOfRegist_0; "Number of registry keys processed"
0x1800034f9  mov     [rsp+60h+var_40], rbx
0x1800034fe  lea     r8, aRegkeyprocessc; "RegKeyProcessCount"
0x180003505  mov     rcx, rsi
0x180003508  call    SclEtwWriteStringStringUll
0x18000350d  mov     rbx, [r14+4B0h]
0x180003514  lea     rax, aNumberOfRegist; "Number of registry keys renamed"
0x18000351b  mov     [rsp+60h+var_28], rbx
0x180003520  mov     r9d, r13d
0x180003523  mov     [rsp+60h+var_30], rax
0x180003528  mov     r8, r15
0x18000352b  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003532  mov     [rsp+60h+var_38], rdi
0x180003537  mov     edx, r12d
0x18000353a  mov     [rsp+60h+var_40], rax
0x18000353f  mov     rcx, rsi
0x180003542  call    SclLogGenericMessage
0x180003547  lea     r9, aNumberOfRegist; "Number of registry keys renamed"
0x18000354e  mov     [rsp+60h+var_40], rbx
0x180003553  lea     r8, aRegkeyrenameco; "RegKeyRenameCount"
0x18000355a  mov     rcx, rsi
0x18000355d  call    SclEtwWriteStringStringUll
0x180003562  mov     rbx, [r14+4B8h]
0x180003569  lea     rax, aNumberOfRegist_2; "Number of registry values processed"
0x180003570  mov     [rsp+60h+var_28], rbx
0x180003575  mov     r9d, r13d
0x180003578  mov     [rsp+60h+var_30], rax
0x18000357d  mov     r8, r15
0x180003580  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003587  mov     [rsp+60h+var_38], rdi
0x18000358c  mov     edx, r12d
0x18000358f  mov     [rsp+60h+var_40], rax
0x180003594  mov     rcx, rsi
0x180003597  call    SclLogGenericMessage
0x18000359c  lea     r9, aNumberOfRegist_2; "Number of registry values processed"
0x1800035a3  mov     [rsp+60h+var_40], rbx
0x1800035a8  lea     r8, aRegvalueproces; "RegValueProcessCount"
0x1800035af  mov     rcx, rsi
0x1800035b2  call    SclEtwWriteStringStringUll
0x1800035b7  mov     rbx, [r14+4C0h]
0x1800035be  lea     rax, aNumberOfRegist_4; "Number of registry values renamed"
0x1800035c5  mov     [rsp+60h+var_28], rbx
0x1800035ca  mov     r9d, r13d
0x1800035cd  mov     [rsp+60h+var_30], rax
0x1800035d2  mov     r8, r15
0x1800035d5  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x1800035dc  mov     [rsp+60h+var_38], rdi
0x1800035e1  mov     edx, r12d
0x1800035e4  mov     [rsp+60h+var_40], rax
0x1800035e9  mov     rcx, rsi
0x1800035ec  call    SclLogGenericMessage
0x1800035f1  lea     r9, aNumberOfRegist_4; "Number of registry values renamed"
0x1800035f8  mov     [rsp+60h+var_40], rbx
0x1800035fd  lea     r8, aRegvaluerename; "RegValueRenameCount"
0x180003604  mov     rcx, rsi
0x180003607  call    SclEtwWriteStringStringUll
0x18000360c  mov     rbx, [r14+4C8h]
0x180003613  lea     rax, aNumberOfRegist_3; "Number of registry values updated"
0x18000361a  mov     [rsp+60h+var_28], rbx
0x18000361f  mov     r9d, r13d
0x180003622  mov     [rsp+60h+var_30], rax
0x180003627  mov     r8, r15
0x18000362a  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003631  mov     [rsp+60h+var_38], rdi
0x180003636  mov     edx, r12d
0x180003639  mov     [rsp+60h+var_40], rax
0x18000363e  mov     rcx, rsi
0x180003641  call    SclLogGenericMessage
0x180003646  lea     r9, aNumberOfRegist_3; "Number of registry values updated"
0x18000364d  mov     [rsp+60h+var_40], rbx
0x180003652  lea     r8, aRegdataupdatec; "RegDataUpdateCount"
0x180003659  mov     rcx, rsi
0x18000365c  call    SclEtwWriteStringStringUll
0x180003661  mov     rbx, [r14+4D0h]
0x180003668  lea     rax, aNumberOfRegist_1; "Number of registry security descriptors"...
0x18000366f  mov     [rsp+60h+var_28], rbx
0x180003674  mov     [rsp+60h+var_30], rax
0x180003679  mov     r9d, r13d
0x18000367c  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003683  mov     [rsp+60h+var_38], rdi
0x180003688  mov     r8, r15
0x18000368b  mov     [rsp+60h+var_40], rax
0x180003690  mov     edx, r12d
0x180003693  mov     rcx, rsi
0x180003696  call    SclLogGenericMessage
0x18000369b  lea     r9, aNumberOfRegist_1; "Number of registry security descriptors"...
0x1800036a2  mov     [rsp+60h+var_40], rbx
0x1800036a7  lea     r8, aSecobjectsdupd; "SecObjectSDUpdateCount"
0x1800036ae  mov     rcx, rsi
0x1800036b1  call    SclEtwWriteStringStringUll
0x1800036b6  mov     rbx, [r14+4D8h]
0x1800036bd  lea     rax, aNumberOfRegist_5; "Number of registry security descriptors"...
0x1800036c4  mov     [rsp+60h+var_28], rbx
0x1800036c9  mov     r9d, r13d
0x1800036cc  mov     [rsp+60h+var_30], rax
0x1800036d1  mov     r8, r15
0x1800036d4  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x1800036db  mov     [rsp+60h+var_38], rdi
0x1800036e0  mov     edx, r12d
0x1800036e3  mov     [rsp+60h+var_40], rax
0x1800036e8  mov     rcx, rsi
0x1800036eb  call    SclLogGenericMessage
0x1800036f0  lea     r9, aNumberOfRegist_5; "Number of registry security descriptors"...
0x1800036f7  mov     [rsp+60h+var_40], rbx
0x1800036fc  lea     r8, aSecobjectsdpro; "SecObjectSDProcessCount"
0x180003703  mov     rcx, rsi
0x180003706  call    SclEtwWriteStringStringUll
0x18000370b  mov     rbx, [r14+4E0h]
0x180003712  lea     rax, aNumberOfSecure_1; "Number of $Secure security descriptors "...
0x180003719  mov     [rsp+60h+var_28], rbx
0x18000371e  mov     r9d, r13d
0x180003721  mov     [rsp+60h+var_30], rax
0x180003726  mov     r8, r15
0x180003729  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003730  mov     [rsp+60h+var_38], rdi
0x180003735  mov     edx, r12d
0x180003738  mov     [rsp+60h+var_40], rax
0x18000373d  mov     rcx, rsi
0x180003740  call    SclLogGenericMessage
0x180003745  lea     r9, aNumberOfSecure_1; "Number of $Secure security descriptors "...
0x18000374c  mov     [rsp+60h+var_40], rbx
0x180003751  lea     r8, aFssecuresdupda; "FsSecureSDUpdateCount"
0x180003758  mov     rcx, rsi
0x18000375b  call    SclEtwWriteStringStringUll
0x180003760  mov     rbx, [r14+4E8h]
0x180003767  lea     rax, aNumberOfSecure; "Number of $Secure security descriptors "...
0x18000376e  mov     [rsp+60h+var_28], rbx
0x180003773  mov     r9d, r13d
0x180003776  mov     [rsp+60h+var_30], rax
0x18000377b  mov     r8, r15
0x18000377e  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003785  mov     [rsp+60h+var_38], rdi
0x18000378a  mov     edx, r12d
0x18000378d  mov     [rsp+60h+var_40], rax
0x180003792  mov     rcx, rsi
0x180003795  call    SclLogGenericMessage
0x18000379a  lea     r9, aNumberOfSecure; "Number of $Secure security descriptors "...
0x1800037a1  mov     [rsp+60h+var_40], rbx
0x1800037a6  lea     r8, aFssecuresdfail; "FsSecureSDFailedUpdateCount"
0x1800037ad  mov     rcx, rsi
0x1800037b0  call    SclEtwWriteStringStringUll
0x1800037b5  mov     rbx, [r14+4F0h]
0x1800037bc  lea     rax, aNumberOfSecure_0; "Number of $Secure security descriptors "...
0x1800037c3  mov     [rsp+60h+var_28], rbx
0x1800037c8  mov     r9d, r13d
0x1800037cb  mov     [rsp+60h+var_30], rax
0x1800037d0  mov     r8, r15
0x1800037d3  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x1800037da  mov     [rsp+60h+var_38], rdi
0x1800037df  mov     edx, r12d
0x1800037e2  mov     [rsp+60h+var_40], rax
0x1800037e7  mov     rcx, rsi
0x1800037ea  call    SclLogGenericMessage
0x1800037ef  lea     r9, aNumberOfSecure_0; "Number of $Secure security descriptors "...
0x1800037f6  mov     [rsp+60h+var_40], rbx
0x1800037fb  lea     r8, aFssecuresdproc; "FsSecureSDProcessCount"
0x180003802  mov     rcx, rsi
0x180003805  call    SclEtwWriteStringStringUll
0x18000380a  mov     rbx, [r14+4F8h]
0x180003811  lea     rax, aNumberOfMftSec; "Number of $MFT security descriptors upd"...
0x180003818  mov     [rsp+60h+var_28], rbx
0x18000381d  mov     r9d, r13d
0x180003820  mov     [rsp+60h+var_30], rax
0x180003825  mov     r8, r15
0x180003828  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x18000382f  mov     [rsp+60h+var_38], rdi
0x180003834  mov     edx, r12d
0x180003837  mov     [rsp+60h+var_40], rax
0x18000383c  mov     rcx, rsi
0x18000383f  call    SclLogGenericMessage
0x180003844  lea     r9, aNumberOfMftSec; "Number of $MFT security descriptors upd"...
0x18000384b  mov     [rsp+60h+var_40], rbx
0x180003850  lea     r8, aFsmftsdupdatec; "FsMftSDUpdateCount"
0x180003857  mov     rcx, rsi
0x18000385a  call    SclEtwWriteStringStringUll
0x18000385f  mov     rbx, [r14+500h]
0x180003866  lea     rax, aNumberOfMftSec_1; "Number of $MFT security descriptors fai"...
0x18000386d  mov     [rsp+60h+var_28], rbx
0x180003872  mov     r9d, r13d
0x180003875  mov     [rsp+60h+var_30], rax
0x18000387a  mov     r8, r15
0x18000387d  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003884  mov     [rsp+60h+var_38], rdi
0x180003889  mov     edx, r12d
0x18000388c  mov     [rsp+60h+var_40], rax
0x180003891  mov     rcx, rsi
0x180003894  call    SclLogGenericMessage
0x180003899  lea     r9, aNumberOfMftSec_1; "Number of $MFT security descriptors fai"...
0x1800038a0  mov     [rsp+60h+var_40], rbx
0x1800038a5  lea     r8, aFsmftsdfailedu; "FsMftSDFailedUpdateCount"
0x1800038ac  mov     rcx, rsi
0x1800038af  call    SclEtwWriteStringStringUll
0x1800038b4  mov     rbx, [r14+508h]
0x1800038bb  lea     rax, aNumberOfMftSec_0; "Number of $MFT security descriptors pro"...
0x1800038c2  mov     [rsp+60h+var_28], rbx
0x1800038c7  mov     r9d, r13d
0x1800038ca  mov     [rsp+60h+var_30], rax
0x1800038cf  mov     r8, r15
0x1800038d2  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x1800038d9  mov     [rsp+60h+var_38], rdi
0x1800038de  mov     edx, r12d
0x1800038e1  mov     [rsp+60h+var_40], rax
0x1800038e6  mov     rcx, rsi
0x1800038e9  call    SclLogGenericMessage
0x1800038ee  lea     r9, aNumberOfMftSec_0; "Number of $MFT security descriptors pro"...
0x1800038f5  mov     [rsp+60h+var_40], rbx
0x1800038fa  lea     r8, aFsmftsdprocess; "FsMftSDProcessCount"
0x180003901  mov     rcx, rsi
0x180003904  call    SclEtwWriteStringStringUll
0x180003909  mov     rbx, [r14+510h]
0x180003910  lea     rax, aNumberOfRepars_0; "Number of reparse points processed"
0x180003917  mov     [rsp+60h+var_28], rbx
0x18000391c  mov     r9d, r13d
0x18000391f  mov     [rsp+60h+var_30], rax
0x180003924  mov     r8, r15
0x180003927  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x18000392e  mov     [rsp+60h+var_38], rdi
0x180003933  mov     edx, r12d
0x180003936  mov     [rsp+60h+var_40], rax
0x18000393b  mov     rcx, rsi
0x18000393e  call    SclLogGenericMessage
0x180003943  lea     r9, aNumberOfRepars_0; "Number of reparse points processed"
0x18000394a  mov     [rsp+60h+var_40], rbx
0x18000394f  lea     r8, aReparsepointpr; "ReparsePointProcessCount"
0x180003956  mov     rcx, rsi
0x180003959  call    SclEtwWriteStringStringUll
0x18000395e  mov     rbx, [r14+518h]
0x180003965  lea     rax, aNumberOfRepars; "Number of reparse points updated"
0x18000396c  mov     [rsp+60h+var_28], rbx
0x180003971  mov     r9d, r13d
0x180003974  mov     [rsp+60h+var_30], rax
0x180003979  mov     r8, r15
0x18000397c  lea     rax, aSclpstaterecor; "SclpStateRecordStatField"
0x180003983  mov     [rsp+60h+var_38], rdi
0x180003988  mov     edx, r12d
0x18000398b  mov     [rsp+60h+var_40], rax
0x180003990  mov     rcx, rsi
0x180003993  call    SclLogGenericMessage
0x180003998  lea     r9, aNumberOfRepars; "Number of reparse points updated"
0x18000399f  mov     [rsp+60h+var_40], rbx
0x1800039a4  lea     r8, aReparsepointup; "ReparsePointUpdateCount"
0x1800039ab  mov     rcx, rsi
  ... truncated ...
```
