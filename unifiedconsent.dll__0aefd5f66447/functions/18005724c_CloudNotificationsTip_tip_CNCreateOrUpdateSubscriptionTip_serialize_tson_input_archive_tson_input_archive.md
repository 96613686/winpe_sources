# CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::serialize<tson::input_archive>(tson::input_archive &)

- ea: `0x18005724c`
- end: `0x1800575a2`
- name: `??$serialize@Vinput_archive@tson@@@_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@QEAAXAEAVinput_archive@tson@@@Z`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005e770`

## callees

- `0x180011df0`
- `0x18001229c`
- `0x180039f0c`
- `0x18003a0b4`
- `0x180056950`
- `0x18005724c`
- `0x18005e6d0`

## string_xrefs

- `0x180057320`: `channelUri`
- `0x180057459`: `channelUri`
- `0x1800573bf`: `cachedEtag`
- `0x18005738f`: `updatedEtag`
- `0x180057280`: `isCachedChannelStale`
- `0x180057417`: `isCachedChannelStale`
- `0x1800572cf`: `serviceName`
- `0x18005749e`: `serviceName`

## pseudocode

```c
__int64 __fastcall CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::serialize<tson::input_archive>(
        _DWORD *a1,
        __int64 a2)
{
  __int64 v5; // [rsp+80h] [rbp-80h] BYREF
  char v6; // [rsp+88h] [rbp-78h]
  _DWORD *v7; // [rsp+90h] [rbp-70h]
  __int64 v8; // [rsp+98h] [rbp-68h] BYREF
  char v9; // [rsp+A0h] [rbp-60h]
  _DWORD *v10; // [rsp+A8h] [rbp-58h]
  __int64 v11; // [rsp+B0h] [rbp-50h] BYREF
  char v12; // [rsp+B8h] [rbp-48h]
  _DWORD *v13; // [rsp+C0h] [rbp-40h]
  __int64 v14; // [rsp+C8h] [rbp-38h] BYREF
  char v15; // [rsp+D0h] [rbp-30h]
  _DWORD *v16; // [rsp+D8h] [rbp-28h]
  __int64 v17; // [rsp+E0h] [rbp-20h] BYREF
  char v18; // [rsp+E8h] [rbp-18h]
  _DWORD *v19; // [rsp+F0h] [rbp-10h]
  __int64 v20; // [rsp+F8h] [rbp-8h] BYREF
  char v21; // [rsp+100h] [rbp+0h]
  char *v22; // [rsp+108h] [rbp+8h]
  __int64 v23; // [rsp+110h] [rbp+10h] BYREF
  char v24; // [rsp+118h] [rbp+18h]
  _DWORD *v25; // [rsp+120h] [rbp+20h]
  __int64 v26; // [rsp+128h] [rbp+28h] BYREF
  char v27; // [rsp+130h] [rbp+30h]
  _DWORD *v28; // [rsp+138h] [rbp+38h]
  __int64 v29; // [rsp+140h] [rbp+40h] BYREF
  char v30; // [rsp+148h] [rbp+48h]
  _DWORD *v31; // [rsp+150h] [rbp+50h]
  __int64 v32; // [rsp+158h] [rbp+58h] BYREF
  char v33; // [rsp+160h] [rbp+60h]
  _DWORD *v34; // [rsp+168h] [rbp+68h]
  unsigned int v35[2]; // [rsp+170h] [rbp+70h] BYREF
  char v36; // [rsp+178h] [rbp+78h]
  _DWORD *v37; // [rsp+180h] [rbp+80h]
  const char *v38; // [rsp+188h] [rbp+88h]
  char v39; // [rsp+190h] [rbp+90h]
  _DWORD *v40; // [rsp+198h] [rbp+98h]
  const char *v41; // [rsp+1A0h] [rbp+A0h]
  char v42; // [rsp+1A8h] [rbp+A8h]
  _DWORD *v43; // [rsp+1B0h] [rbp+B0h]
  const char *v44; // [rsp+1B8h] [rbp+B8h]
  char v45; // [rsp+1C0h] [rbp+C0h]
  _DWORD *v46; // [rsp+1C8h] [rbp+C8h]
  unsigned int v47; // [rsp+1F0h] [rbp+F0h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::GetImpl'::`2'::impl) )
  {
    v9 = 11;
    v8 = (__int64)"updatedEtag";
    v10 = a1 + 68;
    v5 = (__int64)"sendSubscriptionRequestAsyncResult";
    v7 = a1 + 78;
    v11 = (__int64)"cachedEtag";
    v13 = a1 + 60;
    v14 = (__int64)"wnpAppId";
    v16 = a1 + 52;
    v17 = (__int64)"packageFamilyName";
    v19 = a1 + 44;
    v20 = (__int64)"isWebAccountIdValid";
    v22 = (char *)a1 + 317;
    v23 = (__int64)"isCachedChannelStale";
    v25 = a1 + 79;
    v26 = (__int64)"failureHresult";
    v28 = a1 + 77;
    v29 = (__int64)"milestone";
    v31 = a1 + 76;
    v32 = (__int64)"channelUri";
    v34 = a1 + 36;
    *(_QWORD *)v35 = "clientId";
    v37 = a1 + 28;
    v38 = "environmentName";
    v40 = a1 + 20;
    v41 = "serviceName";
    v43 = a1 + 12;
    v44 = "correlationVector";
    v46 = a1 + 4;
    v6 = 34;
    v12 = 10;
    v15 = 8;
    v18 = 17;
    v21 = 19;
    v24 = 20;
    v27 = 14;
    v30 = 9;
    v33 = 10;
    v36 = 8;
    v39 = 15;
    v42 = 11;
    v45 = 17;
    return tson::input_archive::operator()<tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<enum CloudNotificationsTip::TipMilestone &>,tson::nvp<long &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<long &>,tson::nvp<std::wstring &>>(
             (tson::input_archive *)a2,
             (unsigned int)v35,
             (__int64)&v32,
             (__int64)&v29,
             (__int64)&v26,
             (__int64)&v23,
             (__int64)&v20,
             (__int64)&v17,
             (__int64)&v14,
             (__int64)&v11,
             (__int64)&v5,
             (__int64)&v8);
  }
  else
  {
    v9 = 20;
    v8 = (__int64)"isCachedChannelStale";
    v6 = 14;
    v10 = a1 + 79;
    *(_BYTE *)(a2 + 24) = 17;
    v5 = (__int64)"failureHresult";
    v7 = a1 + 77;
    *(_QWORD *)(a2 + 16) = "correlationVector";
    tson::load_nothrow((tson::input_archive *)a2, a1 + 4);
    *(_BYTE *)(a2 + 24) = 11;
    *(_QWORD *)(a2 + 16) = "serviceName";
    tson::load_nothrow((tson::input_archive *)a2, a1 + 12);
    *(_BYTE *)(a2 + 24) = 15;
    *(_QWORD *)(a2 + 16) = "environmentName";
    tson::load_nothrow((tson::input_archive *)a2, a1 + 20);
    *(_BYTE *)(a2 + 24) = 8;
    *(_QWORD *)(a2 + 16) = "clientId";
    tson::load_nothrow((tson::input_archive *)a2, a1 + 28);
    *(_BYTE *)(a2 + 24) = 10;
    *(_QWORD *)(a2 + 16) = "channelUri";
    tson::load_nothrow((tson::input_archive *)a2, a1 + 36);
    *(_BYTE *)(a2 + 24) = 9;
    *(_QWORD *)(a2 + 16) = "milestone";
    v47 = 0;
    tson::input_archive::loadValue((tson::input_archive *)a2, &v47);
    a1[76] = v47;
    tson::input_archive::process<tson::nvp<long &>>(a2, &v5);
    return tson::input_archive::process<tson::nvp<bool &>>(a2, &v8);
  }
}

```

## disassembly

```asm
0x18005724c  mov     [rsp-8+arg_0], rbx
0x180057251  mov     [rsp-8+arg_8], rdi
0x180057256  push    rbp
0x180057257  lea     rbp, [rsp-0D0h]
0x18005725f  sub     rsp, 1D0h
0x180057266  mov     rbx, rdx
0x180057269  mov     rdi, rcx
0x18005726c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests> `wil::Feature<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::GetImpl(void)'::`2'::impl
0x180057273  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::__private_IsEnabled(void)
0x180057278  test    al, al
0x18005727a  jnz     loc_18005738F
0x180057280  lea     rax, aIscachedchanne; "isCachedChannelStale"
0x180057287  mov     [rbp+0D0h+var_130], 14h
0x18005728b  mov     [rbp+0D0h+var_138], rax
0x18005728f  lea     rdx, [rdi+10h]; Src
0x180057293  lea     rax, [rdi+13Ch]
0x18005729a  mov     [rbp+0D0h+var_148], 0Eh
0x18005729e  mov     [rbp+0D0h+var_128], rax
0x1800572a2  mov     rcx, rbx; this
0x1800572a5  lea     rax, aFailurehresult; "failureHresult"
0x1800572ac  mov     byte ptr [rbx+18h], 11h
0x1800572b0  mov     [rbp+0D0h+var_150], rax
0x1800572b4  lea     rax, [rdi+134h]
0x1800572bb  mov     [rbp+0D0h+var_140], rax
0x1800572bf  lea     rax, aCorrelationvec; "correlationVector"
0x1800572c6  mov     [rbx+10h], rax
0x1800572ca  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; tson::load_nothrow(tson::input_archive &,std::wstring &)
0x1800572cf  lea     rax, aServicename; "serviceName"
0x1800572d6  mov     byte ptr [rbx+18h], 0Bh
0x1800572da  lea     rdx, [rdi+30h]; Src
0x1800572de  mov     [rbx+10h], rax
0x1800572e2  mov     rcx, rbx; this
0x1800572e5  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; tson::load_nothrow(tson::input_archive &,std::wstring &)
0x1800572ea  lea     rax, aEnvironmentnam; "environmentName"
0x1800572f1  mov     byte ptr [rbx+18h], 0Fh
0x1800572f5  lea     rdx, [rdi+50h]; Src
0x1800572f9  mov     [rbx+10h], rax
0x1800572fd  mov     rcx, rbx; this
0x180057300  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; tson::load_nothrow(tson::input_archive &,std::wstring &)
0x180057305  lea     rax, aClientid; "clientId"
0x18005730c  mov     byte ptr [rbx+18h], 8
0x180057310  lea     rdx, [rdi+70h]; Src
0x180057314  mov     [rbx+10h], rax
0x180057318  mov     rcx, rbx; this
0x18005731b  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; tson::load_nothrow(tson::input_archive &,std::wstring &)
0x180057320  lea     rax, aChanneluri; "channelUri"
0x180057327  mov     byte ptr [rbx+18h], 0Ah
0x18005732b  lea     rdx, [rdi+90h]; Src
0x180057332  mov     [rbx+10h], rax
0x180057336  mov     rcx, rbx; this
0x180057339  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; tson::load_nothrow(tson::input_archive &,std::wstring &)
0x18005733e  lea     rax, aMilestone; "milestone"
0x180057345  mov     byte ptr [rbx+18h], 9
0x180057349  lea     rdx, [rbp+0D0h+arg_10]; unsigned int *
0x180057350  mov     [rbx+10h], rax
0x180057354  mov     rcx, rbx; this
0x180057357  mov     [rbp+0D0h+arg_10], 0
0x180057361  call    ?loadValue@input_archive@tson@@QEAAXAEAK@Z; tson::input_archive::loadValue(ulong &)
0x180057366  mov     eax, [rbp+0D0h+arg_10]
0x18005736c  lea     rdx, [rbp+0D0h+var_150]
0x180057370  mov     rcx, rbx
0x180057373  mov     [rdi+130h], eax
0x180057379  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x18005737e  lea     rdx, [rbp+0D0h+var_138]
0x180057382  mov     rcx, rbx
0x180057385  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18005738a  jmp     loc_18005758D
0x18005738f  lea     rax, aUpdatedetag; "updatedEtag"
0x180057396  mov     [rbp+0D0h+var_130], 0Bh
0x18005739a  mov     [rbp+0D0h+var_138], rax
0x18005739e  lea     rax, [rdi+110h]
0x1800573a5  mov     [rbp+0D0h+var_128], rax
0x1800573a9  lea     rax, aSendsubscripti; "sendSubscriptionRequestAsyncResult"
0x1800573b0  mov     [rbp+0D0h+var_150], rax
0x1800573b4  lea     rax, [rdi+138h]
0x1800573bb  mov     [rbp+0D0h+var_140], rax
0x1800573bf  lea     rax, aCachedetag; "cachedEtag"
0x1800573c6  mov     [rbp+0D0h+var_120], rax
0x1800573ca  lea     rax, [rdi+0F0h]
0x1800573d1  mov     [rbp+0D0h+var_110], rax
0x1800573d5  lea     rax, aWnpappid; "wnpAppId"
0x1800573dc  mov     [rbp+0D0h+var_108], rax
0x1800573e0  lea     rax, [rdi+0D0h]
0x1800573e7  mov     [rbp+0D0h+var_F8], rax
0x1800573eb  lea     rax, aPackagefamilyn; "packageFamilyName"
0x1800573f2  mov     [rbp+0D0h+var_F0], rax
0x1800573f6  lea     rax, [rdi+0B0h]
0x1800573fd  mov     [rbp+0D0h+var_E0], rax
0x180057401  lea     rax, aIswebaccountid; "isWebAccountIdValid"
0x180057408  mov     [rbp+0D0h+var_D8], rax
0x18005740c  lea     rax, [rdi+13Dh]
0x180057413  mov     [rbp+0D0h+var_C8], rax
0x180057417  lea     rax, aIscachedchanne; "isCachedChannelStale"
0x18005741e  mov     [rbp+0D0h+var_C0], rax
0x180057422  lea     rax, [rdi+13Ch]
0x180057429  mov     [rbp+0D0h+var_B0], rax
0x18005742d  lea     rax, aFailurehresult; "failureHresult"
0x180057434  mov     [rbp+0D0h+var_A8], rax
0x180057438  lea     rax, [rdi+134h]
0x18005743f  mov     [rbp+0D0h+var_98], rax
0x180057443  lea     rax, aMilestone; "milestone"
0x18005744a  mov     [rbp+0D0h+var_90], rax
0x18005744e  lea     rax, [rdi+130h]
0x180057455  mov     [rbp+0D0h+var_80], rax
0x180057459  lea     rax, aChanneluri; "channelUri"
0x180057460  mov     [rbp+0D0h+var_78], rax
0x180057464  lea     rax, [rdi+90h]
0x18005746b  mov     [rbp+0D0h+var_68], rax
0x18005746f  lea     rax, aClientid; "clientId"
0x180057476  mov     qword ptr [rbp+0D0h+var_60], rax
0x18005747a  lea     rax, [rdi+70h]
0x18005747e  mov     [rbp+0D0h+var_50], rax
0x180057485  lea     rax, aEnvironmentnam; "environmentName"
0x18005748c  mov     [rbp+0D0h+var_48], rax
0x180057493  lea     rax, [rdi+50h]
0x180057497  mov     [rbp+0D0h+var_38], rax
0x18005749e  lea     rax, aServicename; "serviceName"
0x1800574a5  mov     [rbp+0D0h+var_30], rax
0x1800574ac  lea     rax, [rdi+30h]
0x1800574b0  mov     [rbp+0D0h+var_20], rax
0x1800574b7  lea     rax, aCorrelationvec; "correlationVector"
0x1800574be  mov     [rbp+0D0h+var_18], rax
0x1800574c5  lea     rax, [rdi+10h]
0x1800574c9  mov     [rbp+0D0h+var_8], rax
0x1800574d0  lea     rax, [rbp+0D0h+var_138]
0x1800574d4  mov     [rsp+1D0h+var_160], rax; __int64
0x1800574d9  lea     rax, [rbp+0D0h+var_150]
0x1800574dd  mov     [rsp+1D0h+var_168], rax; __int64
0x1800574e2  lea     rax, [rbp+0D0h+var_120]
0x1800574e6  mov     [rsp+1D0h+var_170], rax; __int64
0x1800574eb  lea     rax, [rbp+0D0h+var_108]
0x1800574ef  mov     [rsp+1D0h+var_178], rax; __int64
0x1800574f4  lea     rax, [rbp+0D0h+var_F0]
0x1800574f8  mov     [rsp+1D0h+var_180], rax; __int64
0x1800574fd  lea     rax, [rbp+0D0h+var_D8]
0x180057501  mov     [rbp+0D0h+var_148], 22h ; '"'
0x180057505  mov     [rbp+0D0h+var_118], 0Ah
0x180057509  mov     [rbp+0D0h+var_100], 8
0x18005750d  mov     [rbp+0D0h+var_E8], 11h
0x180057511  mov     [rbp+0D0h+var_D0], 13h
0x180057515  mov     [rbp+0D0h+var_B8], 14h
0x180057519  mov     [rbp+0D0h+var_A0], 0Eh
0x18005751d  mov     [rbp+0D0h+var_88], 9
0x180057521  mov     [rbp+0D0h+var_70], 0Ah
0x180057525  mov     [rbp+0D0h+var_58], 8
0x180057529  mov     [rbp+0D0h+var_40], 0Fh
0x180057530  mov     [rbp+0D0h+var_28], 0Bh
0x180057537  mov     [rbp+0D0h+var_10], 11h
0x18005753e  mov     [rsp+1D0h+var_188], rax; __int64
0x180057543  lea     r9, [rbp+0D0h+var_48]
0x18005754a  lea     rax, [rbp+0D0h+var_C0]
0x18005754e  mov     rcx, rbx; this
0x180057551  mov     [rsp+1D0h+var_190], rax; __int64
0x180057556  lea     r8, [rbp+0D0h+var_30]
0x18005755d  lea     rax, [rbp+0D0h+var_A8]
0x180057561  mov     [rsp+1D0h+var_198], rax; __int64
0x180057566  lea     rdx, [rbp+0D0h+var_18]
0x18005756d  lea     rax, [rbp+0D0h+var_90]
0x180057571  mov     [rsp+1D0h+var_1A0], rax; __int64
0x180057576  lea     rax, [rbp+0D0h+var_78]
0x18005757a  mov     [rsp+1D0h+var_1A8], rax; __int64
0x18005757f  lea     rax, [rbp+0D0h+var_60]
0x180057583  mov     qword ptr [rsp+1D0h+var_1B0], rax; unsigned int
0x180057588  call    ??$?RV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tson@@V01@V01@V01@V01@V?$nvp@AEAW4TipMilestone@CloudNotificationsTip@@@1@V?$nvp@AEAJ@1@V?$nvp@AEA_N@1@V41@V01@V01@V01@V31@V01@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@0000$$QEAV?$nvp@AEAW4TipMilestone@CloudNotificationsTip@@@1@$$QEAV?$nvp@AEAJ@1@$$QEAV?$nvp@AEA_N@1@300020@Z; tson::input_archive::operator()<tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<CloudNotificationsTip::TipMilestone &>,tson::nvp<long &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<std::wstring &>,tson::nvp<long &>,tson::nvp<std::wstring &>>(tson::nvp<std::wstring &> &&,tson::nvp<std::wstring &> &&,tson::nvp<std::wstring &> &&,tson::nvp<std::wstring &> &&,tson::nvp<std::wstring &> &&,tson::nvp<CloudNotificationsTip::TipMilestone &> &&,tson::nvp<long &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<std::wstring &> &&,tson::nvp<std::wstring &> &&,tson::nvp<std::wstring &> &&,tson::nvp<long &> &&,tson::nvp<std::wstring &> &&)
0x18005758d  lea     r11, [rsp+1D0h+var_s0]
0x180057595  mov     rbx, [r11+10h]
0x180057599  mov     rdi, [r11+18h]
0x18005759d  mov     rsp, r11
0x1800575a0  pop     rbp
0x1800575a1  retn
```
