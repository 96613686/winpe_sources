# SetChannelCommand::SetProperties(void *,IXMLDOMElement *)

- ea: `0x140027f70`
- end: `0x1400283d3`
- name: `?SetProperties@SetChannelCommand@@AEAAXPEAXPEAUIXMLDOMElement@@@Z`
- size: `1123`
- prototype: `void __fastcall(SetChannelCommand *__hidden this, void *, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fc50`

## callees

- `0x1400104f8`
- `0x140010c90`
- `0x140010f08`
- `0x14001117c`
- `0x140011f60`
- `0x1400124fc`

## string_xrefs

- `0x140028374`: `ChannelAccess`
- `0x140028369`: `@access`

## pseudocode

```c
void __fastcall SetChannelCommand::SetProperties(SetChannelCommand *this, void *a2, struct IXMLDOMElement *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  char v8; // [rsp+38h] [rbp-38h]
  __int128 v9; // [rsp+40h] [rbp-30h] BYREF
  __int128 v10; // [rsp+50h] [rbp-20h] BYREF
  __int128 v11; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)&v9 = L"@enabled";
  *((_QWORD *)&v9 + 1) = 8;
  *((_QWORD *)&v10 + 1) = 1;
  *((_QWORD *)&v11 + 1) = 7;
  *(_QWORD *)&v10 = L"e";
  *(_QWORD *)&v11 = L"Enabled";
  SetChannelCommand::SetPropertyBoolean(
    (__int64)this,
    L"Enabled",
    a2,
    &v11,
    &v10,
    (__int64)a3,
    &v9,
    EvtChannelConfigEnabled);
  *(_QWORD *)&v11 = L"ns:logging/ns:retention";
  *((_QWORD *)&v10 + 1) = 2;
  *(_QWORD *)&v10 = L"rt";
  *(_QWORD *)&v9 = L"Retention";
  *((_QWORD *)&v11 + 1) = 23;
  *((_QWORD *)&v9 + 1) = 9;
  SetChannelCommand::SetPropertyBoolean(
    (__int64)this,
    L"Retention",
    a2,
    &v9,
    &v10,
    (__int64)a3,
    &v11,
    EvtChannelLoggingConfigRetention);
  *(_QWORD *)&v11 = L"ns:logging/ns:autoBackup";
  *((_QWORD *)&v10 + 1) = 2;
  *(_QWORD *)&v10 = L"ab";
  *((_QWORD *)&v11 + 1) = 24;
  *(_QWORD *)&v9 = L"AutoBackup";
  *((_QWORD *)&v9 + 1) = 10;
  SetChannelCommand::SetPropertyBoolean(
    (__int64)this,
    L"AutoBackup",
    a2,
    &v9,
    &v10,
    (__int64)a3,
    &v11,
    EvtChannelLoggingConfigAutoBackup);
  *(_QWORD *)&v11 = L"ns:logging/@logFileName";
  *((_QWORD *)&v11 + 1) = 23;
  *(_QWORD *)&v10 = L"lfn";
  *((_QWORD *)&v10 + 1) = 3;
  *(_QWORD *)&v9 = L"LogFileName";
  *((_QWORD *)&v9 + 1) = 11;
  SetChannelCommand::SetPropertyString(
    (__int64)this,
    L"LogFileName",
    a2,
    &v9,
    &v10,
    (__int64)a3,
    &v11,
    EvtChannelLoggingConfigLogFilePath);
  *(_QWORD *)&v11 = L"ns:logging/ns:maxSize";
  *((_QWORD *)&v11 + 1) = 21;
  *(_QWORD *)&v10 = L"ms";
  *((_QWORD *)&v10 + 1) = 2;
  *(_QWORD *)&v9 = L"MaxSize";
  *((_QWORD *)&v9 + 1) = 7;
  SetChannelCommand::SetPropertyUInt64(
    (__int64)this,
    L"MaxSize",
    a2,
    &v9,
    (BSTR)&v10,
    (__int64)a3,
    &v11,
    EvtChannelLoggingConfigMaxSize);
  *((_QWORD *)&v11 + 1) = 24;
  *(_QWORD *)&v11 = L"ns:publishing/@isolation";
  *((_QWORD *)&v10 + 1) = 1;
  *(_QWORD *)&v10 = L"i";
  *((_QWORD *)&v9 + 1) = 9;
  *(_QWORD *)&v9 = L"Isolation";
  SetChannelCommand::SetPropertyEnum((__int64)this, v6, a2, &v9, &v10, (__int64)a3, &v11, v8);
  *(_QWORD *)&v11 = L"ns:publishing/ns:fileMax";
  *((_QWORD *)&v11 + 1) = 24;
  *(_QWORD *)&v10 = L"fm";
  *((_QWORD *)&v10 + 1) = 2;
  *(_QWORD *)&v9 = L"FileMax";
  *((_QWORD *)&v9 + 1) = 7;
  SetChannelCommand::SetPropertyUInt32(
    (__int64)this,
    L"FileMax",
    a2,
    &v9,
    (BSTR)&v10,
    (__int64)a3,
    &v11,
    EvtChannelPublishingConfigFileMax);
  *(_QWORD *)&v11 = L"ns:publishing/ns:level";
  *((_QWORD *)&v10 + 1) = 1;
  *(_QWORD *)&v10 = L"L";
  *((_QWORD *)&v11 + 1) = 22;
  *(_QWORD *)&v9 = L"Level";
  *((_QWORD *)&v9 + 1) = 5;
  SetChannelCommand::SetPropertyUInt32(
    (__int64)this,
    L"Level",
    a2,
    &v9,
    (BSTR)&v10,
    (__int64)a3,
    &v11,
    EvtChannelPublishingConfigLevel);
  *((_QWORD *)&v11 + 1) = 25;
  *(_QWORD *)&v11 = L"ns:publishing/ns:keywords";
  *((_QWORD *)&v10 + 1) = 1;
  *(_QWORD *)&v10 = L"k";
  *(_QWORD *)&v9 = L"Keywords";
  *((_QWORD *)&v9 + 1) = 8;
  SetChannelCommand::SetPropertyUInt64(
    (__int64)this,
    L"Keywords",
    a2,
    &v9,
    (BSTR)&v10,
    (__int64)a3,
    &v11,
    EvtChannelPublishingConfigKeywords);
  *((_QWORD *)&v11 + 1) = 28;
  *(_QWORD *)&v11 = L"ns:publishing/ns:controlGuid";
  *((_QWORD *)&v10 + 1) = 2;
  *(_QWORD *)&v10 = L"cg";
  *((_QWORD *)&v9 + 1) = 11;
  *(_QWORD *)&v9 = L"ControlGuid";
  SetChannelCommand::SetPropertyGuid((__int64)this, v7, a2, &v9, &v10, (__int64)a3, &v11);
  *(_QWORD *)&v11 = L"@access";
  *((_QWORD *)&v11 + 1) = 7;
  *(_QWORD *)&v10 = L"ca";
  *((_QWORD *)&v10 + 1) = 2;
  *(_QWORD *)&v9 = L"ChannelAccess";
  *((_QWORD *)&v9 + 1) = 13;
  SetChannelCommand::SetPropertyString(
    (__int64)this,
    L"ChannelAccess",
    a2,
    &v9,
    &v10,
    (__int64)a3,
    &v11,
    EvtChannelConfigAccess);
}

```

## disassembly

```asm
0x140027f70  push    rbp
0x140027f72  push    rbx
0x140027f73  push    rsi
0x140027f74  push    rdi
0x140027f75  push    r12
0x140027f77  push    r14
0x140027f79  push    r15
0x140027f7b  mov     rbp, rsp
0x140027f7e  sub     rsp, 70h
0x140027f82  mov     dword ptr [rsp+70h+var_38], 0
0x140027f8a  lea     rax, aEnabled_1; "@enabled"
0x140027f91  mov     [rbp+var_30], rax
0x140027f95  lea     r9, [rbp+var_10]
0x140027f99  mov     rbx, r8
0x140027f9c  mov     [rbp+var_28], 8
0x140027fa4  mov     rdi, rdx
0x140027fa7  mov     [rbp+var_18], 1
0x140027faf  lea     rax, aE_0; "e"
0x140027fb6  mov     [rbp+var_8], 7
0x140027fbe  mov     [rbp+var_20], rax
0x140027fc2  lea     rdx, aEnabled; "Enabled"
0x140027fc9  lea     rax, [rbp+var_30]
0x140027fcd  mov     [rbp+var_10], rdx
0x140027fd1  mov     [rsp+70h+var_40], rax
0x140027fd6  mov     r8, rdi
0x140027fd9  lea     rax, [rbp+var_20]
0x140027fdd  mov     [rsp+70h+var_48], rbx
0x140027fe2  mov     [rsp+70h+var_50], rax
0x140027fe7  mov     rsi, rcx
0x140027fea  call    ?SetPropertyBoolean@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyBoolean(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x140027fef  mov     dword ptr [rsp+70h+var_38], 6
0x140027ff7  lea     rax, aNsLoggingNsRet; "ns:logging/ns:retention"
0x140027ffe  mov     [rbp+var_10], rax
0x140028002  lea     rdx, aRetention; "Retention"
0x140028009  lea     rax, aRt_0; "rt"
0x140028010  mov     [rbp+var_18], 2
0x140028018  mov     [rbp+var_20], rax
0x14002801c  lea     r9, [rbp+var_30]
0x140028020  mov     r14d, 17h
0x140028026  mov     [rbp+var_30], rdx
0x14002802a  lea     rax, [rbp+var_10]
0x14002802e  mov     [rbp+var_8], r14
0x140028032  mov     [rsp+70h+var_40], rax
0x140028037  mov     r8, rdi
0x14002803a  lea     rax, [rbp+var_20]
0x14002803e  mov     [rsp+70h+var_48], rbx
0x140028043  lea     r12d, [r14-0Eh]
0x140028047  mov     [rsp+70h+var_50], rax
0x14002804c  mov     rcx, rsi
0x14002804f  mov     [rbp+var_28], r12
0x140028053  call    ?SetPropertyBoolean@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyBoolean(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x140028058  mov     dword ptr [rsp+70h+var_38], 7
0x140028060  lea     rax, aNsLoggingNsAut; "ns:logging/ns:autoBackup"
0x140028067  mov     [rbp+var_10], rax
0x14002806b  lea     rdx, aAutobackup_0; "AutoBackup"
0x140028072  lea     rax, aAb; "ab"
0x140028079  mov     [rbp+var_18], 2
0x140028081  mov     [rbp+var_20], rax
0x140028085  lea     r15d, [r14+1]
0x140028089  lea     rax, [rbp+var_10]
0x14002808d  mov     [rbp+var_8], r15
0x140028091  mov     [rsp+70h+var_40], rax
0x140028096  lea     r9, [rbp+var_30]
0x14002809a  lea     rax, [rbp+var_20]
0x14002809e  mov     [rsp+70h+var_48], rbx
0x1400280a3  mov     r8, rdi
0x1400280a6  mov     [rsp+70h+var_50], rax
0x1400280ab  mov     rcx, rsi
0x1400280ae  mov     [rbp+var_30], rdx
0x1400280b2  mov     [rbp+var_28], 0Ah
0x1400280ba  call    ?SetPropertyBoolean@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyBoolean(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x1400280bf  mov     dword ptr [rsp+70h+var_38], r12d
0x1400280c4  lea     rax, aNsLoggingLogfi; "ns:logging/@logFileName"
0x1400280cb  mov     [rbp+var_10], rax
0x1400280cf  lea     rdx, aLogfilename; "LogFileName"
0x1400280d6  lea     rax, aLfn_0; "lfn"
0x1400280dd  mov     [rbp+var_8], r14
0x1400280e1  mov     [rbp+var_20], rax
0x1400280e5  lea     r9, [rbp+var_30]
0x1400280e9  lea     rax, [rbp+var_10]
0x1400280ed  mov     [rbp+var_18], 3
0x1400280f5  mov     [rsp+70h+var_40], rax
0x1400280fa  mov     r8, rdi
0x1400280fd  lea     rax, [rbp+var_20]
0x140028101  mov     [rsp+70h+var_48], rbx
0x140028106  mov     rcx, rsi
0x140028109  mov     [rsp+70h+var_50], rax
0x14002810e  mov     [rbp+var_30], rdx
0x140028112  mov     [rbp+var_28], 0Bh
0x14002811a  call    ?SetPropertyString@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyString(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x14002811f  mov     dword ptr [rsp+70h+var_38], 8
0x140028127  lea     rax, aNsLoggingNsMax; "ns:logging/ns:maxSize"
0x14002812e  mov     [rbp+var_10], rax
0x140028132  lea     rdx, aMaxsize_0; "MaxSize"
0x140028139  lea     rax, aMs; "ms"
0x140028140  mov     [rbp+var_8], 15h
0x140028148  mov     [rbp+var_20], rax
0x14002814c  lea     r9, [rbp+var_30]
0x140028150  lea     rax, [rbp+var_10]
0x140028154  mov     [rbp+var_18], 2
0x14002815c  mov     [rsp+70h+var_40], rax
0x140028161  mov     r8, rdi
0x140028164  lea     rax, [rbp+var_20]
0x140028168  mov     [rsp+70h+var_48], rbx
0x14002816d  mov     rcx, rsi
0x140028170  mov     [rsp+70h+var_50], rax
0x140028175  mov     [rbp+var_30], rdx
0x140028179  mov     [rbp+var_28], 7
0x140028181  call    ?SetPropertyUInt64@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyUInt64(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x140028186  lea     rax, aNsPublishingIs; "ns:publishing/@isolation"
0x14002818d  mov     [rbp+var_8], r15
0x140028191  mov     [rbp+var_10], rax
0x140028195  lea     r14d, [r12-8]
0x14002819a  lea     rax, aI; "i"
0x1400281a1  mov     [rbp+var_18], r14
0x1400281a5  mov     [rbp+var_20], rax
0x1400281a9  lea     r9, [rbp+var_30]
0x1400281ad  lea     rax, aIsolation; "Isolation"
0x1400281b4  mov     [rbp+var_28], r12
0x1400281b8  mov     [rbp+var_30], rax
0x1400281bc  mov     r8, rdi
0x1400281bf  lea     rax, [rbp+var_10]
0x1400281c3  mov     rcx, rsi
0x1400281c6  mov     [rsp+70h+var_40], rax
0x1400281cb  lea     rax, [rbp+var_20]
0x1400281cf  mov     [rsp+70h+var_48], rbx
0x1400281d4  mov     [rsp+70h+var_50], rax
0x1400281d9  call    ?SetPropertyEnum@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyEnum(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x1400281de  mov     dword ptr [rsp+70h+var_38], 14h
0x1400281e6  lea     rax, aNsPublishingNs_2; "ns:publishing/ns:fileMax"
0x1400281ed  mov     [rbp+var_10], rax
0x1400281f1  lea     rdx, aFilemax; "FileMax"
0x1400281f8  lea     rax, aFm; "fm"
0x1400281ff  mov     [rbp+var_8], r15
0x140028203  mov     [rbp+var_20], rax
0x140028207  lea     r12d, [r15-16h]
0x14002820b  lea     rax, [rbp+var_10]
0x14002820f  mov     [rbp+var_18], r12
0x140028213  mov     [rsp+70h+var_40], rax
0x140028218  lea     r9, [rbp+var_30]
0x14002821c  lea     rax, [rbp+var_20]
0x140028220  mov     [rsp+70h+var_48], rbx
0x140028225  mov     r8, rdi
0x140028228  mov     [rsp+70h+var_50], rax
0x14002822d  mov     rcx, rsi
0x140028230  mov     [rbp+var_30], rdx
0x140028234  mov     [rbp+var_28], 7
0x14002823c  call    ?SetPropertyUInt32@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyUInt32(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x140028241  mov     dword ptr [rsp+70h+var_38], 0Ah
0x140028249  lea     rax, aNsPublishingNs_0; "ns:publishing/ns:level"
0x140028250  mov     [rbp+var_10], rax
0x140028254  lea     rdx, aLevel_0; "Level"
0x14002825b  lea     rax, asc_140039250; "L"
0x140028262  mov     [rbp+var_18], r14
0x140028266  mov     [rbp+var_20], rax
0x14002826a  lea     r14d, [r15-13h]
0x14002826e  lea     rax, [rbp+var_10]
0x140028272  mov     [rbp+var_8], 16h
0x14002827a  mov     [rsp+70h+var_40], rax
0x14002827f  lea     r9, [rbp+var_30]
0x140028283  lea     rax, [rbp+var_20]
0x140028287  mov     [rsp+70h+var_48], rbx
0x14002828c  mov     r8, rdi
0x14002828f  mov     [rsp+70h+var_50], rax
0x140028294  mov     rcx, rsi
0x140028297  mov     [rbp+var_30], rdx
0x14002829b  mov     [rbp+var_28], r14
0x14002829f  call    ?SetPropertyUInt32@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyUInt32(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x1400282a4  lea     rax, aNsPublishingNs_1; "ns:publishing/ns:keywords"
0x1400282ab  mov     [rbp+var_8], 19h
0x1400282b3  mov     [rbp+var_10], rax
0x1400282b7  lea     rax, aK_0; "k"
0x1400282be  mov     [rbp+var_18], 1
0x1400282c6  mov     [rbp+var_20], rax
0x1400282ca  lea     rdx, aKeywords_0; "Keywords"
0x1400282d1  lea     rax, [rbp+var_10]
0x1400282d5  mov     [rbp+var_30], rdx
0x1400282d9  lea     r15d, [r12+9]
0x1400282de  mov     [rbp+var_28], 8
0x1400282e6  mov     dword ptr [rsp+70h+var_38], r15d
0x1400282eb  lea     r9, [rbp+var_30]
0x1400282ef  mov     [rsp+70h+var_40], rax
0x1400282f4  mov     r8, rdi
0x1400282f7  lea     rax, [rbp+var_20]
0x1400282fb  mov     [rsp+70h+var_48], rbx
0x140028300  mov     rcx, rsi
0x140028303  mov     [rsp+70h+var_50], rax
0x140028308  call    ?SetPropertyUInt64@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyUInt64(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x14002830d  lea     rax, aNsPublishingNs; "ns:publishing/ns:controlGuid"
0x140028314  mov     [rbp+var_8], 1Ch
0x14002831c  mov     [rbp+var_10], rax
0x140028320  lea     r9, [rbp+var_30]
0x140028324  lea     rax, aCg; "cg"
0x14002832b  mov     [rbp+var_18], r12
0x14002832f  mov     [rbp+var_20], rax
0x140028333  mov     r8, rdi
0x140028336  lea     rax, aControlguid; "ControlGuid"
0x14002833d  mov     [rbp+var_28], r15
0x140028341  mov     [rbp+var_30], rax
0x140028345  mov     rcx, rsi
0x140028348  lea     rax, [rbp+var_10]
0x14002834c  mov     [rsp+70h+var_40], rax
0x140028351  lea     rax, [rbp+var_20]
0x140028355  mov     [rsp+70h+var_48], rbx
0x14002835a  mov     [rsp+70h+var_50], rax
0x14002835f  call    ?SetPropertyGuid@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyGuid(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x140028364  mov     dword ptr [rsp+70h+var_38], r14d
0x140028369  lea     rax, aAccess; "@access"
0x140028370  mov     [rbp+var_10], rax
0x140028374  lea     rdx, aChannelaccess_0; "ChannelAccess"
0x14002837b  lea     rax, aCa_0; "ca"
0x140028382  mov     [rbp+var_8], 7
0x14002838a  mov     [rbp+var_20], rax
0x14002838e  lea     r9, [rbp+var_30]
0x140028392  lea     rax, [rbp+var_10]
0x140028396  mov     [rbp+var_18], r12
0x14002839a  mov     [rsp+70h+var_40], rax
0x14002839f  mov     r8, rdi
0x1400283a2  lea     rax, [rbp+var_20]
0x1400283a6  mov     [rsp+70h+var_48], rbx
0x1400283ab  mov     rcx, rsi
0x1400283ae  mov     [rsp+70h+var_50], rax
0x1400283b3  mov     [rbp+var_30], rdx
0x1400283b7  mov     [rbp+var_28], 0Dh
0x1400283bf  call    ?SetPropertyString@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; SetChannelCommand::SetPropertyString(wchar_t const *,void *,std::wstring_view,std::wstring_view,IXMLDOMElement *,std::wstring_view,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x1400283c4  add     rsp, 70h
0x1400283c8  pop     r15
0x1400283ca  pop     r14
0x1400283cc  pop     r12
0x1400283ce  pop     rdi
0x1400283cf  pop     rsi
0x1400283d0  pop     rbx
0x1400283d1  pop     rbp
0x1400283d2  retn
```
