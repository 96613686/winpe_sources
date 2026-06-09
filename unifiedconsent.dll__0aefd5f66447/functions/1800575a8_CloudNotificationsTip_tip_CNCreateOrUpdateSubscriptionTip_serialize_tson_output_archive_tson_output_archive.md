# CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::serialize<tson::output_archive>(tson::output_archive &)

- ea: `0x1800575a8`
- end: `0x180057910`
- name: `??$serialize@Voutput_archive@tson@@@_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@QEAAXAEAVoutput_archive@tson@@@Z`
- size: `872`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005fc10`

## callees

- `0x1800100c8`
- `0x180011e84`
- `0x18001b134`
- `0x180031cb8`
- `0x1800575a8`
- `0x18005e6d0`

## string_xrefs

- `0x1800575ff`: `channelUri`
- `0x180057798`: `channelUri`
- `0x18005773e`: `cachedEtag`
- `0x1800576ff`: `updatedEtag`
- `0x1800576dd`: `isCachedChannelStale`
- `0x180057885`: `isCachedChannelStale`
- `0x180057644`: `serviceName`
- `0x1800577da`: `serviceName`

## pseudocode

```c
__int64 __fastcall CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::serialize<tson::output_archive>(
        __int64 a1,
        tson::output_archive *a2)
{
  const char *v5; // [rsp+20h] [rbp-E0h] BYREF
  char v6; // [rsp+28h] [rbp-D8h]
  __int64 v7; // [rsp+30h] [rbp-D0h]
  const char *v8; // [rsp+38h] [rbp-C8h]
  char v9; // [rsp+40h] [rbp-C0h]
  __int64 v10; // [rsp+48h] [rbp-B8h]
  const char *v11; // [rsp+50h] [rbp-B0h]
  char v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h]
  const char *v14; // [rsp+68h] [rbp-98h]
  char v15; // [rsp+70h] [rbp-90h]
  __int64 v16; // [rsp+78h] [rbp-88h]
  const char *v17; // [rsp+80h] [rbp-80h]
  char v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  const char *v20; // [rsp+98h] [rbp-68h] BYREF
  char v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+A8h] [rbp-58h]
  const char *v23; // [rsp+B0h] [rbp-50h]
  char v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  const char *v26; // [rsp+C8h] [rbp-38h]
  char v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  const char *v29; // [rsp+E0h] [rbp-20h]
  char v30; // [rsp+E8h] [rbp-18h]
  __int64 v31; // [rsp+F0h] [rbp-10h]
  const char *v32; // [rsp+F8h] [rbp-8h] BYREF
  char v33; // [rsp+100h] [rbp+0h]
  __int64 v34; // [rsp+108h] [rbp+8h]
  const char *v35; // [rsp+110h] [rbp+10h]
  char v36; // [rsp+118h] [rbp+18h]
  __int64 v37; // [rsp+120h] [rbp+20h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::GetImpl'::`2'::impl) )
  {
    v36 = 11;
    v35 = "updatedEtag";
    v33 = 34;
    v37 = a1 + 272;
    v30 = 10;
    v32 = "sendSubscriptionRequestAsyncResult";
    v34 = a1 + 312;
    v29 = "cachedEtag";
    v31 = a1 + 240;
    v26 = "wnpAppId";
    v28 = a1 + 208;
    v23 = "packageFamilyName";
    v25 = a1 + 176;
    v5 = "failureHresult";
    v7 = a1 + 308;
    v8 = "channelUri";
    v10 = a1 + 144;
    v11 = "clientId";
    v13 = a1 + 112;
    v14 = "environmentName";
    v16 = a1 + 80;
    v17 = "serviceName";
    v19 = a1 + 48;
    v20 = "correlationVector";
    v22 = a1 + 16;
    v27 = 8;
    v24 = 17;
    v6 = 14;
    v9 = 10;
    v12 = 8;
    v15 = 15;
    v18 = 11;
    v21 = 17;
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    *((_BYTE *)a2 + 8) = 9;
    *(_QWORD *)a2 = "milestone";
    tson::output_archive::saveValue(a2, *(_DWORD *)(a1 + 304));
    tson::output_archive::process<tson::nvp<long &>>(a2, &v5);
    *(_QWORD *)a2 = "isCachedChannelStale";
    *((_BYTE *)a2 + 8) = 20;
    tson::output_archive::operator()<bool &>(a2, a1 + 316);
    *((_BYTE *)a2 + 8) = 19;
    *(_QWORD *)a2 = "isWebAccountIdValid";
    tson::output_archive::operator()<bool &>(a2, a1 + 317);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<long &>>(a2, &v32);
    return tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
  }
  else
  {
    v21 = 14;
    v20 = "failureHresult";
    v18 = 10;
    v22 = a1 + 308;
    v15 = 8;
    v17 = "channelUri";
    v19 = a1 + 144;
    v14 = "clientId";
    v16 = a1 + 112;
    v11 = "environmentName";
    v13 = a1 + 80;
    v8 = "serviceName";
    v10 = a1 + 48;
    v5 = "correlationVector";
    v7 = a1 + 16;
    v12 = 15;
    v9 = 11;
    v6 = 17;
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    tson::output_archive::process<tson::nvp<std::wstring &>>(a2);
    *((_BYTE *)a2 + 8) = 9;
    *(_QWORD *)a2 = "milestone";
    tson::output_archive::saveValue(a2, *(_DWORD *)(a1 + 304));
    tson::output_archive::process<tson::nvp<long &>>(a2, &v20);
    *((_BYTE *)a2 + 8) = 20;
    *(_QWORD *)a2 = "isCachedChannelStale";
    return tson::output_archive::operator()<bool &>(a2, a1 + 316);
  }
}

```

## disassembly

```asm
0x1800575a8  mov     [rsp-8+arg_0], rbx
0x1800575ad  mov     [rsp-8+arg_8], rdi
0x1800575b2  push    rbp
0x1800575b3  lea     rbp, [rsp-30h]
0x1800575b8  sub     rsp, 130h
0x1800575bf  mov     rbx, rdx
0x1800575c2  mov     rdi, rcx
0x1800575c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests> `wil::Feature<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::GetImpl(void)'::`2'::impl
0x1800575cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::__private_IsEnabled(void)
0x1800575d1  test    al, al
0x1800575d3  jnz     loc_1800576FF
0x1800575d9  lea     rax, aFailurehresult; "failureHresult"
0x1800575e0  mov     [rbp+30h+var_90], 0Eh
0x1800575e4  mov     [rbp+30h+var_98], rax
0x1800575e8  lea     rdx, [rsp+130h+var_110]
0x1800575ed  lea     rax, [rdi+134h]
0x1800575f4  mov     [rbp+30h+var_A8], 0Ah
0x1800575f8  mov     [rbp+30h+var_88], rax
0x1800575fc  mov     rcx, rbx; this
0x1800575ff  lea     rax, aChanneluri; "channelUri"
0x180057606  mov     [rsp+130h+var_C0], 8
0x18005760b  mov     [rbp+30h+var_B0], rax
0x18005760f  lea     rax, [rdi+90h]
0x180057616  mov     [rbp+30h+var_A0], rax
0x18005761a  lea     rax, aClientid; "clientId"
0x180057621  mov     [rsp+130h+var_C8], rax
0x180057626  lea     rax, [rdi+70h]
0x18005762a  mov     [rsp+130h+var_B8], rax
0x18005762f  lea     rax, aEnvironmentnam; "environmentName"
0x180057636  mov     [rsp+130h+var_E0], rax
0x18005763b  lea     rax, [rdi+50h]
0x18005763f  mov     [rsp+130h+var_D0], rax
0x180057644  lea     rax, aServicename; "serviceName"
0x18005764b  mov     [rsp+130h+var_F8], rax
0x180057650  lea     rax, [rdi+30h]
0x180057654  mov     [rsp+130h+var_E8], rax
0x180057659  lea     rax, aCorrelationvec; "correlationVector"
0x180057660  mov     [rsp+130h+var_110], rax
0x180057665  lea     rax, [rdi+10h]
0x180057669  mov     [rsp+130h+var_100], rax
0x18005766e  mov     [rsp+130h+var_D8], 0Fh
0x180057673  mov     [rsp+130h+var_F0], 0Bh
0x180057678  mov     [rsp+130h+var_108], 11h
0x18005767d  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x180057682  lea     rdx, [rsp+130h+var_F8]
0x180057687  mov     rcx, rbx; this
0x18005768a  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x18005768f  lea     rdx, [rsp+130h+var_E0]
0x180057694  mov     rcx, rbx; this
0x180057697  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x18005769c  lea     rdx, [rsp+130h+var_C8]
0x1800576a1  mov     rcx, rbx; this
0x1800576a4  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x1800576a9  lea     rdx, [rbp+30h+var_B0]
0x1800576ad  mov     rcx, rbx; this
0x1800576b0  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x1800576b5  lea     rax, aMilestone; "milestone"
0x1800576bc  mov     byte ptr [rbx+8], 9
0x1800576c0  mov     [rbx], rax
0x1800576c3  mov     rcx, rbx; this
0x1800576c6  mov     edx, [rdi+130h]; unsigned int
0x1800576cc  call    ?saveValue@output_archive@tson@@QEAAXK@Z; tson::output_archive::saveValue(ulong)
0x1800576d1  lea     rdx, [rbp+30h+var_98]
0x1800576d5  mov     rcx, rbx
0x1800576d8  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x1800576dd  lea     rax, aIscachedchanne; "isCachedChannelStale"
0x1800576e4  mov     byte ptr [rbx+8], 14h
0x1800576e8  lea     rdx, [rdi+13Ch]
0x1800576ef  mov     [rbx], rax
0x1800576f2  mov     rcx, rbx
0x1800576f5  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x1800576fa  jmp     loc_1800578FB
0x1800576ff  lea     rax, aUpdatedetag; "updatedEtag"
0x180057706  mov     [rbp+30h+var_18], 0Bh
0x18005770a  mov     [rbp+30h+var_20], rax
0x18005770e  lea     rdx, [rbp+30h+var_98]
0x180057712  lea     rax, [rdi+110h]
0x180057719  mov     [rbp+30h+var_30], 22h ; '"'
0x18005771d  mov     [rbp+30h+var_10], rax
0x180057721  mov     rcx, rbx; this
0x180057724  lea     rax, aSendsubscripti; "sendSubscriptionRequestAsyncResult"
0x18005772b  mov     [rbp+30h+var_48], 0Ah
0x18005772f  mov     [rbp+30h+var_38], rax
0x180057733  lea     rax, [rdi+138h]
0x18005773a  mov     [rbp+30h+var_28], rax
0x18005773e  lea     rax, aCachedetag; "cachedEtag"
0x180057745  mov     [rbp+30h+var_50], rax
0x180057749  lea     rax, [rdi+0F0h]
0x180057750  mov     [rbp+30h+var_40], rax
0x180057754  lea     rax, aWnpappid; "wnpAppId"
0x18005775b  mov     [rbp+30h+var_68], rax
0x18005775f  lea     rax, [rdi+0D0h]
0x180057766  mov     [rbp+30h+var_58], rax
0x18005776a  lea     rax, aPackagefamilyn; "packageFamilyName"
0x180057771  mov     [rbp+30h+var_80], rax
0x180057775  lea     rax, [rdi+0B0h]
0x18005777c  mov     [rbp+30h+var_70], rax
0x180057780  lea     rax, aFailurehresult; "failureHresult"
0x180057787  mov     [rsp+130h+var_110], rax
0x18005778c  lea     rax, [rdi+134h]
0x180057793  mov     [rsp+130h+var_100], rax
0x180057798  lea     rax, aChanneluri; "channelUri"
0x18005779f  mov     [rsp+130h+var_F8], rax
0x1800577a4  lea     rax, [rdi+90h]
0x1800577ab  mov     [rsp+130h+var_E8], rax
0x1800577b0  lea     rax, aClientid; "clientId"
0x1800577b7  mov     [rsp+130h+var_E0], rax
0x1800577bc  lea     rax, [rdi+70h]
0x1800577c0  mov     [rsp+130h+var_D0], rax
0x1800577c5  lea     rax, aEnvironmentnam; "environmentName"
0x1800577cc  mov     [rsp+130h+var_C8], rax
0x1800577d1  lea     rax, [rdi+50h]
0x1800577d5  mov     [rsp+130h+var_B8], rax
0x1800577da  lea     rax, aServicename; "serviceName"
0x1800577e1  mov     [rbp+30h+var_B0], rax
0x1800577e5  lea     rax, [rdi+30h]
0x1800577e9  mov     [rbp+30h+var_A0], rax
0x1800577ed  lea     rax, aCorrelationvec; "correlationVector"
0x1800577f4  mov     [rbp+30h+var_98], rax
0x1800577f8  lea     rax, [rdi+10h]
0x1800577fc  mov     [rbp+30h+var_88], rax
0x180057800  mov     [rbp+30h+var_60], 8
0x180057804  mov     [rbp+30h+var_78], 11h
0x180057808  mov     [rsp+130h+var_108], 0Eh
0x18005780d  mov     [rsp+130h+var_F0], 0Ah
0x180057812  mov     [rsp+130h+var_D8], 8
0x180057817  mov     [rsp+130h+var_C0], 0Fh
0x18005781c  mov     [rbp+30h+var_A8], 0Bh
0x180057820  mov     [rbp+30h+var_90], 11h
0x180057824  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x180057829  lea     rdx, [rbp+30h+var_B0]
0x18005782d  mov     rcx, rbx; this
0x180057830  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x180057835  lea     rdx, [rsp+130h+var_C8]
0x18005783a  mov     rcx, rbx; this
0x18005783d  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x180057842  lea     rdx, [rsp+130h+var_E0]
0x180057847  mov     rcx, rbx; this
0x18005784a  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x18005784f  lea     rdx, [rsp+130h+var_F8]
0x180057854  mov     rcx, rbx; this
0x180057857  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x18005785c  lea     rax, aMilestone; "milestone"
0x180057863  mov     byte ptr [rbx+8], 9
0x180057867  mov     [rbx], rax
0x18005786a  mov     rcx, rbx; this
0x18005786d  mov     edx, [rdi+130h]; unsigned int
0x180057873  call    ?saveValue@output_archive@tson@@QEAAXK@Z; tson::output_archive::saveValue(ulong)
0x180057878  lea     rdx, [rsp+130h+var_110]
0x18005787d  mov     rcx, rbx
0x180057880  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x180057885  lea     rax, aIscachedchanne; "isCachedChannelStale"
0x18005788c  mov     [rbx], rax
0x18005788f  lea     rdx, [rdi+13Ch]
0x180057896  mov     byte ptr [rbx+8], 14h
0x18005789a  mov     rcx, rbx
0x18005789d  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x1800578a2  lea     rax, aIswebaccountid; "isWebAccountIdValid"
0x1800578a9  mov     byte ptr [rbx+8], 13h
0x1800578ad  lea     rdx, [rdi+13Dh]
0x1800578b4  mov     [rbx], rax
0x1800578b7  mov     rcx, rbx
0x1800578ba  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x1800578bf  lea     rdx, [rbp+30h+var_80]
0x1800578c3  mov     rcx, rbx; this
0x1800578c6  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x1800578cb  lea     rdx, [rbp+30h+var_68]
0x1800578cf  mov     rcx, rbx; this
0x1800578d2  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x1800578d7  lea     rdx, [rbp+30h+var_50]
0x1800578db  mov     rcx, rbx; this
0x1800578de  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x1800578e3  lea     rdx, [rbp+30h+var_38]
0x1800578e7  mov     rcx, rbx
0x1800578ea  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x1800578ef  lea     rdx, [rbp+30h+var_20]
0x1800578f3  mov     rcx, rbx; this
0x1800578f6  call    ??$process@V?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&)
0x1800578fb  lea     r11, [rsp+130h+var_s0]
0x180057903  mov     rbx, [r11+10h]
0x180057907  mov     rdi, [r11+18h]
0x18005790b  mov     rsp, r11
0x18005790e  pop     rbp
0x18005790f  retn
```
