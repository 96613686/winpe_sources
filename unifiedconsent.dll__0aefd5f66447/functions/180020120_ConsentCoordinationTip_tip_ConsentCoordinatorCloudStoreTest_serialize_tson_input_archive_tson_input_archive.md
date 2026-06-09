# ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest::serialize<tson::input_archive>(tson::input_archive &)

- ea: `0x180020120`
- end: `0x1800209ed`
- name: `??$serialize@Vinput_archive@tson@@@_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@QEAAXAEAVinput_archive@tson@@@Z`
- size: `2253`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002df60`

## callees

- `0x180011df0`
- `0x18001229c`
- `0x1800194ec`
- `0x18001ff88`
- `0x180020120`
- `0x18002d364`
- `0x18002d540`

## string_xrefs

- `0x180020273`: `consent_read_from_cache_count`
- `0x180020564`: `consent_read_from_cache_count`
- `0x180020846`: `consent_read_from_cache_count`
- `0x18002019f`: `cr_read_check`
- `0x1800202ee`: `cr_read_check`
- `0x180020467`: `cr_read_check`
- `0x180020604`: `cr_read_check`
- `0x180020773`: `cr_read_check`
- `0x1800208c3`: `cr_read_check`
- `0x1800201cb`: `cr_all_accounts_read_failure`
- `0x180020314`: `cr_all_accounts_read_failure`
- `0x18002048f`: `cr_all_accounts_read_failure`
- `0x18002062c`: `cr_all_accounts_read_failure`
- `0x18002079f`: `cr_all_accounts_read_failure`
- `0x1800208eb`: `cr_all_accounts_read_failure`
- `0x1800201b8`: `cr_consent_read_success`
- `0x180020301`: `cr_consent_read_success`
- `0x18002047a`: `cr_consent_read_success`
- `0x180020617`: `cr_consent_read_success`
- `0x18002078c`: `cr_consent_read_success`
- `0x1800208d8`: `cr_consent_read_success`
- `0x180020415`: `cr_notification_subscription_attempted`
- `0x1800205c7`: `cr_notification_subscription_attempted`

## pseudocode

```c
__int64 __fastcall ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest::serialize<tson::input_archive>(
        __int64 a1,
        __int64 a2)
{
  const char **v4; // rdx
  const char **v5; // rdx
  const char *v7; // [rsp+20h] [rbp-E0h] BYREF
  char v8; // [rsp+28h] [rbp-D8h]
  __int64 v9; // [rsp+30h] [rbp-D0h]
  const char *v10; // [rsp+38h] [rbp-C8h] BYREF
  char v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+48h] [rbp-B8h]
  const char *v13; // [rsp+50h] [rbp-B0h] BYREF
  char v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  const char *v16; // [rsp+68h] [rbp-98h] BYREF
  char v17; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  const char *v19; // [rsp+80h] [rbp-80h] BYREF
  char v20; // [rsp+88h] [rbp-78h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  const char *v22; // [rsp+98h] [rbp-68h] BYREF
  char v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  const char *v25; // [rsp+B0h] [rbp-50h] BYREF
  char v26; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  const char *v28; // [rsp+C8h] [rbp-38h] BYREF
  char v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  const char *v31; // [rsp+E0h] [rbp-20h] BYREF
  char v32; // [rsp+E8h] [rbp-18h]
  __int64 v33; // [rsp+F0h] [rbp-10h]
  const char *v34; // [rsp+F8h] [rbp-8h] BYREF
  char v35; // [rsp+100h] [rbp+0h]
  __int64 v36; // [rsp+108h] [rbp+8h]
  const char *v37; // [rsp+110h] [rbp+10h] BYREF
  char v38; // [rsp+118h] [rbp+18h]
  __int64 v39; // [rsp+120h] [rbp+20h]
  const char *v40; // [rsp+128h] [rbp+28h] BYREF
  char v41; // [rsp+130h] [rbp+30h]
  __int64 v42; // [rsp+138h] [rbp+38h]
  const char *v43; // [rsp+140h] [rbp+40h] BYREF
  char v44; // [rsp+148h] [rbp+48h]
  __int64 v45; // [rsp+150h] [rbp+50h]
  const char *v46; // [rsp+158h] [rbp+58h] BYREF
  char v47; // [rsp+160h] [rbp+60h]
  __int64 v48; // [rsp+168h] [rbp+68h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableNotificationInCC>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DisableNotificationInCC>::GetImpl'::`2'::impl) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl'::`2'::impl) )
      {
        v11 = 23;
        v10 = "duplicate_version_found";
        v8 = 13;
        v12 = a1 + 25;
        v29 = 23;
        v7 = "cr_read_check";
        v9 = a1 + 24;
        v28 = "cr_consent_read_success";
        v30 = a1 + 23;
        v25 = "cr_all_accounts_read_failure";
        v27 = a1 + 22;
        v40 = "wnf_not_published";
        v42 = a1 + 21;
        v37 = "failure_hresult";
        v39 = a1 + 16;
        v26 = 28;
        v41 = 17;
        v38 = 15;
        tson::input_archive::process<tson::nvp<long &>>(a2, &v37);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v40);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v25);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v28);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v7);
        v4 = &v10;
        return tson::input_archive::process<tson::nvp<bool &>>(a2, v4);
      }
      v23 = 31;
      v22 = "consent_retrieved_from_cr_count";
      v20 = 29;
      v24 = a1 + 48;
      v17 = 21;
      v19 = "consent_read_from_cache_count";
      v21 = a1 + 44;
      v16 = "non_web_account_count";
      v18 = a1 + 36;
      v13 = "aad_account_count";
      v15 = a1 + 40;
      v34 = "msa_account_count";
      v36 = a1 + 32;
      v31 = "account_count";
      v33 = a1 + 28;
      v37 = "duplicate_version_found";
      v39 = a1 + 25;
      v40 = "cr_read_check";
      v42 = a1 + 24;
      v25 = "cr_consent_read_success";
      v27 = a1 + 23;
      v28 = "cr_all_accounts_read_failure";
      v30 = a1 + 22;
      v7 = "wnf_not_published";
      v9 = a1 + 21;
      v10 = "failure_hresult";
      v12 = a1 + 16;
      v14 = 17;
      v35 = 17;
      v32 = 13;
      v38 = 23;
      v41 = 13;
      v26 = 23;
      v29 = 28;
      v8 = 17;
      v11 = 15;
      tson::input_archive::process<tson::nvp<long &>>(a2, &v10);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v7);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v28);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v25);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v40);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v37);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v31);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v34);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v13);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v16);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v19);
      v5 = &v22;
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl'::`2'::impl) )
      {
        v8 = 38;
        v7 = "cr_notification_subscription_attempted";
        v11 = 36;
        v9 = a1 + 27;
        v32 = 23;
        v10 = "cr_notification_subscription_success";
        v12 = a1 + 26;
        v31 = "duplicate_version_found";
        v33 = a1 + 25;
        v34 = "cr_read_check";
        v36 = a1 + 24;
        v13 = "cr_consent_read_success";
        v15 = a1 + 23;
        v16 = "cr_all_accounts_read_failure";
        v18 = a1 + 22;
        v19 = "wnf_not_published";
        v21 = a1 + 21;
        v22 = "failure_hresult";
        v24 = a1 + 16;
        v35 = 13;
        v14 = 23;
        v17 = 28;
        v20 = 17;
        v23 = 15;
        tson::input_archive::process<tson::nvp<long &>>(a2, &v22);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v19);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v16);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v13);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v34);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v31);
        tson::input_archive::process<tson::nvp<bool &>>(a2, &v10);
        v4 = &v7;
        return tson::input_archive::process<tson::nvp<bool &>>(a2, v4);
      }
      v47 = 31;
      v46 = "consent_retrieved_from_cr_count";
      v44 = 29;
      v48 = a1 + 48;
      v38 = 21;
      v43 = "consent_read_from_cache_count";
      v45 = a1 + 44;
      v37 = "non_web_account_count";
      v39 = a1 + 36;
      v40 = "aad_account_count";
      v42 = a1 + 40;
      v25 = "msa_account_count";
      v27 = a1 + 32;
      v28 = "account_count";
      v30 = a1 + 28;
      v7 = "cr_notification_subscription_attempted";
      v9 = a1 + 27;
      v10 = "cr_notification_subscription_success";
      v12 = a1 + 26;
      v31 = "duplicate_version_found";
      v33 = a1 + 25;
      v34 = "cr_read_check";
      v36 = a1 + 24;
      v13 = "cr_consent_read_success";
      v15 = a1 + 23;
      v16 = "cr_all_accounts_read_failure";
      v18 = a1 + 22;
      v19 = "wnf_not_published";
      v21 = a1 + 21;
      v22 = "failure_hresult";
      v24 = a1 + 16;
      v41 = 17;
      v26 = 17;
      v29 = 13;
      v8 = 38;
      v11 = 36;
      v32 = 23;
      v35 = 13;
      v14 = 23;
      v17 = 28;
      v20 = 17;
      v23 = 15;
      tson::input_archive::process<tson::nvp<long &>>(a2, &v22);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v19);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v16);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v13);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v34);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v31);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v10);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v7);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v28);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v25);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v40);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v37);
      tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v43);
      v5 = &v46;
    }
  }
  else
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl'::`2'::impl) )
    {
      v14 = 23;
      v13 = "duplicate_version_found";
      v17 = 13;
      v15 = a1 + 25;
      v20 = 23;
      v16 = "cr_read_check";
      v18 = a1 + 24;
      v19 = "cr_consent_read_success";
      v21 = a1 + 23;
      v22 = "cr_all_accounts_read_failure";
      v24 = a1 + 22;
      v43 = "wnf_not_published";
      v45 = a1 + 21;
      v46 = "failure_hresult";
      v48 = a1 + 16;
      v23 = 28;
      v44 = 17;
      v47 = 15;
      tson::input_archive::process<tson::nvp<long &>>(a2, &v46);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v43);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v22);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v19);
      tson::input_archive::process<tson::nvp<bool &>>(a2, &v16);
      v4 = &v13;
      return tson::input_archive::process<tson::nvp<bool &>>(a2, v4);
    }
    v26 = 31;
    v25 = "consent_retrieved_from_cr_count";
    v29 = 29;
    v27 = a1 + 48;
    v8 = 21;
    v28 = "consent_read_from_cache_count";
    v30 = a1 + 44;
    v7 = "non_web_account_count";
    v9 = a1 + 36;
    v10 = "aad_account_count";
    v12 = a1 + 40;
    v31 = "msa_account_count";
    v33 = a1 + 32;
    v34 = "account_count";
    v36 = a1 + 28;
    v13 = "duplicate_version_found";
    v15 = a1 + 25;
    v16 = "cr_read_check";
    v18 = a1 + 24;
    v19 = "cr_consent_read_success";
    v21 = a1 + 23;
    v22 = "cr_all_accounts_read_failure";
    v24 = a1 + 22;
    v43 = "wnf_not_published";
    v45 = a1 + 21;
    v46 = "failure_hresult";
    v48 = a1 + 16;
    v11 = 17;
    v32 = 17;
    v35 = 13;
    v14 = 23;
    v17 = 13;
    v20 = 23;
    v23 = 28;
    v44 = 17;
    v47 = 15;
    tson::input_archive::process<tson::nvp<long &>>(a2, &v46);
    tson::input_archive::process<tson::nvp<bool &>>(a2, &v43);
    tson::input_archive::process<tson::nvp<bool &>>(a2, &v22);
    tson::input_archive::process<tson::nvp<bool &>>(a2, &v19);
    tson::input_archive::process<tson::nvp<bool &>>(a2, &v16);
    tson::input_archive::process<tson::nvp<bool &>>(a2, &v13);
    tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v34);
    tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v31);
    tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v10);
    tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v7);
    tson::input_archive::process<tson::nvp<unsigned int &>>(a2, &v28);
    v5 = &v25;
  }
  return tson::input_archive::process<tson::nvp<unsigned int &>>(a2, v5);
}

```

## disassembly

```asm
0x180020120  mov     [rsp-8+arg_0], rbx
0x180020125  mov     [rsp-8+arg_8], rdi
0x18002012a  push    rbp
0x18002012b  lea     rbp, [rsp-70h]
0x180020130  sub     rsp, 170h
0x180020137  mov     rbx, rdx
0x18002013a  mov     rdi, rcx
0x18002013d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification> `wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl(void)'::`2'::impl
0x180020144  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(void)
0x180020149  test    al, al
0x18002014b  jz      loc_180020739
0x180020151  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableNotificationInCC@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableNotificationInCC@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableNotificationInCC> `wil::Feature<__WilFeatureTraits_Feature_DisableNotificationInCC>::GetImpl(void)'::`2'::impl
0x180020158  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableNotificationInCC@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableNotificationInCC>::__private_IsEnabled(void)
0x18002015d  test    al, al
0x18002015f  jz      loc_180020401
0x180020165  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl(void)'::`2'::impl
0x18002016c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(void)
0x180020171  test    al, al
0x180020173  jnz     loc_180020250
0x180020179  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x180020180  mov     [rsp+170h+var_130], 17h
0x180020185  mov     [rsp+170h+var_138], rax
0x18002018a  lea     rdx, [rbp+70h+var_60]
0x18002018e  lea     rax, [rdi+19h]
0x180020192  mov     [rsp+170h+var_148], 0Dh
0x180020197  mov     [rsp+170h+var_128], rax
0x18002019c  mov     rcx, rbx
0x18002019f  lea     rax, aCrReadCheck; "cr_read_check"
0x1800201a6  mov     [rbp+70h+var_A0], 17h
0x1800201aa  mov     [rsp+170h+var_150], rax
0x1800201af  lea     rax, [rdi+18h]
0x1800201b3  mov     [rsp+170h+var_140], rax
0x1800201b8  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x1800201bf  mov     [rbp+70h+var_A8], rax
0x1800201c3  lea     rax, [rdi+17h]
0x1800201c7  mov     [rbp+70h+var_98], rax
0x1800201cb  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x1800201d2  mov     [rbp+70h+var_C0], rax
0x1800201d6  lea     rax, [rdi+16h]
0x1800201da  mov     [rbp+70h+var_B0], rax
0x1800201de  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x1800201e5  mov     [rbp+70h+var_48], rax
0x1800201e9  lea     rax, [rdi+15h]
0x1800201ed  mov     [rbp+70h+var_38], rax
0x1800201f1  lea     rax, aFailureHresult; "failure_hresult"
0x1800201f8  mov     [rbp+70h+var_60], rax
0x1800201fc  lea     rax, [rdi+10h]
0x180020200  mov     [rbp+70h+var_50], rax
0x180020204  mov     [rbp+70h+var_B8], 1Ch
0x180020208  mov     [rbp+70h+var_40], 11h
0x18002020c  mov     [rbp+70h+var_58], 0Fh
0x180020210  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x180020215  lea     rdx, [rbp+70h+var_48]
0x180020219  mov     rcx, rbx
0x18002021c  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020221  lea     rdx, [rbp+70h+var_C0]
0x180020225  mov     rcx, rbx
0x180020228  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18002022d  lea     rdx, [rbp+70h+var_A8]
0x180020231  mov     rcx, rbx
0x180020234  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020239  lea     rdx, [rsp+170h+var_150]
0x18002023e  mov     rcx, rbx
0x180020241  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020246  lea     rdx, [rsp+170h+var_138]
0x18002024b  jmp     loc_180020535
0x180020250  lea     rax, aConsentRetriev; "consent_retrieved_from_cr_count"
0x180020257  mov     [rbp+70h+var_D0], 1Fh
0x18002025b  mov     [rbp+70h+var_D8], rax
0x18002025f  lea     rdx, [rsp+170h+var_138]
0x180020264  lea     rax, [rdi+30h]
0x180020268  mov     [rbp+70h+var_E8], 1Dh
0x18002026c  mov     [rbp+70h+var_C8], rax
0x180020270  mov     rcx, rbx
0x180020273  lea     rax, aConsentReadFro_1; "consent_read_from_cache_count"
0x18002027a  mov     [rsp+170h+var_100], 15h
0x18002027f  mov     [rbp+70h+var_F0], rax
0x180020283  lea     rax, [rdi+2Ch]
0x180020287  mov     [rbp+70h+var_E0], rax
0x18002028b  lea     rax, aNonWebAccountC; "non_web_account_count"
0x180020292  mov     [rsp+170h+var_108], rax
0x180020297  lea     rax, [rdi+24h]
0x18002029b  mov     [rsp+170h+var_F8], rax
0x1800202a0  lea     rax, aAadAccountCoun; "aad_account_count"
0x1800202a7  mov     [rsp+170h+var_120], rax
0x1800202ac  lea     rax, [rdi+28h]
0x1800202b0  mov     [rsp+170h+var_110], rax
0x1800202b5  lea     rax, aMsaAccountCoun; "msa_account_count"
0x1800202bc  mov     [rbp+70h+var_78], rax
0x1800202c0  lea     rax, [rdi+20h]
0x1800202c4  mov     [rbp+70h+var_68], rax
0x1800202c8  lea     rax, aAccountCount; "account_count"
0x1800202cf  mov     [rbp+70h+var_90], rax
0x1800202d3  lea     rax, [rdi+1Ch]
0x1800202d7  mov     [rbp+70h+var_80], rax
0x1800202db  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x1800202e2  mov     [rbp+70h+var_60], rax
0x1800202e6  lea     rax, [rdi+19h]
0x1800202ea  mov     [rbp+70h+var_50], rax
0x1800202ee  lea     rax, aCrReadCheck; "cr_read_check"
0x1800202f5  mov     [rbp+70h+var_48], rax
0x1800202f9  lea     rax, [rdi+18h]
0x1800202fd  mov     [rbp+70h+var_38], rax
0x180020301  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020308  mov     [rbp+70h+var_C0], rax
0x18002030c  lea     rax, [rdi+17h]
0x180020310  mov     [rbp+70h+var_B0], rax
0x180020314  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x18002031b  mov     [rbp+70h+var_A8], rax
0x18002031f  lea     rax, [rdi+16h]
0x180020323  mov     [rbp+70h+var_98], rax
0x180020327  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x18002032e  mov     [rsp+170h+var_150], rax
0x180020333  lea     rax, [rdi+15h]
0x180020337  mov     [rsp+170h+var_140], rax
0x18002033c  lea     rax, aFailureHresult; "failure_hresult"
0x180020343  mov     [rsp+170h+var_138], rax
0x180020348  lea     rax, [rdi+10h]
0x18002034c  mov     [rsp+170h+var_128], rax
0x180020351  mov     [rsp+170h+var_118], 11h
0x180020356  mov     [rbp+70h+var_70], 11h
0x18002035a  mov     [rbp+70h+var_88], 0Dh
0x18002035e  mov     [rbp+70h+var_58], 17h
0x180020362  mov     [rbp+70h+var_40], 0Dh
0x180020366  mov     [rbp+70h+var_B8], 17h
0x18002036a  mov     [rbp+70h+var_A0], 1Ch
0x18002036e  mov     [rsp+170h+var_148], 11h
0x180020373  mov     [rsp+170h+var_130], 0Fh
0x180020378  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x18002037d  lea     rdx, [rsp+170h+var_150]
0x180020382  mov     rcx, rbx
0x180020385  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18002038a  lea     rdx, [rbp+70h+var_A8]
0x18002038e  mov     rcx, rbx
0x180020391  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020396  lea     rdx, [rbp+70h+var_C0]
0x18002039a  mov     rcx, rbx
0x18002039d  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800203a2  lea     rdx, [rbp+70h+var_48]
0x1800203a6  mov     rcx, rbx
0x1800203a9  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800203ae  lea     rdx, [rbp+70h+var_60]
0x1800203b2  mov     rcx, rbx
0x1800203b5  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800203ba  lea     rdx, [rbp+70h+var_90]
0x1800203be  mov     rcx, rbx
0x1800203c1  call    ??$process@V?$nvp@AEAI@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAI@1@@Z; tson::input_archive::process<tson::nvp<uint &>>(tson::nvp<uint &> &&)
0x1800203c6  lea     rdx, [rbp+70h+var_78]
0x1800203ca  mov     rcx, rbx
0x1800203cd  call    ??$process@V?$nvp@AEAI@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAI@1@@Z; tson::input_archive::process<tson::nvp<uint &>>(tson::nvp<uint &> &&)
0x1800203d2  lea     rdx, [rsp+170h+var_120]
0x1800203d7  mov     rcx, rbx
0x1800203da  call    ??$process@V?$nvp@AEAI@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAI@1@@Z; tson::input_archive::process<tson::nvp<uint &>>(tson::nvp<uint &> &&)
0x1800203df  lea     rdx, [rsp+170h+var_108]
0x1800203e4  mov     rcx, rbx
0x1800203e7  call    ??$process@V?$nvp@AEAI@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAI@1@@Z; tson::input_archive::process<tson::nvp<uint &>>(tson::nvp<uint &> &&)
0x1800203ec  lea     rdx, [rbp+70h+var_F0]
0x1800203f0  mov     rcx, rbx
0x1800203f3  call    ??$process@V?$nvp@AEAI@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAI@1@@Z; tson::input_archive::process<tson::nvp<uint &>>(tson::nvp<uint &> &&)
0x1800203f8  lea     rdx, [rbp+70h+var_D8]
0x1800203fc  jmp     loc_1800209D0
0x180020401  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl(void)'::`2'::impl
0x180020408  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(void)
0x18002040d  test    al, al
0x18002040f  jnz     loc_180020542
0x180020415  lea     rax, aCrNotification_0; "cr_notification_subscription_attempted"
0x18002041c  mov     [rsp+170h+var_148], 26h ; '&'
0x180020421  mov     [rsp+170h+var_150], rax
0x180020426  lea     rdx, [rbp+70h+var_D8]
0x18002042a  lea     rax, [rdi+1Bh]
0x18002042e  mov     [rsp+170h+var_130], 24h ; '$'
0x180020433  mov     [rsp+170h+var_140], rax
0x180020438  mov     rcx, rbx
0x18002043b  lea     rax, aCrNotification; "cr_notification_subscription_success"
0x180020442  mov     [rbp+70h+var_88], 17h
0x180020446  mov     [rsp+170h+var_138], rax
0x18002044b  lea     rax, [rdi+1Ah]
0x18002044f  mov     [rsp+170h+var_128], rax
0x180020454  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x18002045b  mov     [rbp+70h+var_90], rax
0x18002045f  lea     rax, [rdi+19h]
0x180020463  mov     [rbp+70h+var_80], rax
0x180020467  lea     rax, aCrReadCheck; "cr_read_check"
0x18002046e  mov     [rbp+70h+var_78], rax
0x180020472  lea     rax, [rdi+18h]
0x180020476  mov     [rbp+70h+var_68], rax
0x18002047a  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020481  mov     [rsp+170h+var_120], rax
0x180020486  lea     rax, [rdi+17h]
0x18002048a  mov     [rsp+170h+var_110], rax
0x18002048f  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020496  mov     [rsp+170h+var_108], rax
0x18002049b  lea     rax, [rdi+16h]
0x18002049f  mov     [rsp+170h+var_F8], rax
0x1800204a4  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x1800204ab  mov     [rbp+70h+var_F0], rax
0x1800204af  lea     rax, [rdi+15h]
0x1800204b3  mov     [rbp+70h+var_E0], rax
0x1800204b7  lea     rax, aFailureHresult; "failure_hresult"
0x1800204be  mov     [rbp+70h+var_D8], rax
0x1800204c2  lea     rax, [rdi+10h]
0x1800204c6  mov     [rbp+70h+var_C8], rax
0x1800204ca  mov     [rbp+70h+var_70], 0Dh
0x1800204ce  mov     [rsp+170h+var_118], 17h
0x1800204d3  mov     [rsp+170h+var_100], 1Ch
0x1800204d8  mov     [rbp+70h+var_E8], 11h
0x1800204dc  mov     [rbp+70h+var_D0], 0Fh
0x1800204e0  call    ??$process@V?$nvp@AEAJ@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::input_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x1800204e5  lea     rdx, [rbp+70h+var_F0]
0x1800204e9  mov     rcx, rbx
0x1800204ec  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800204f1  lea     rdx, [rsp+170h+var_108]
0x1800204f6  mov     rcx, rbx
0x1800204f9  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800204fe  lea     rdx, [rsp+170h+var_120]
0x180020503  mov     rcx, rbx
0x180020506  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18002050b  lea     rdx, [rbp+70h+var_78]
0x18002050f  mov     rcx, rbx
0x180020512  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020517  lea     rdx, [rbp+70h+var_90]
0x18002051b  mov     rcx, rbx
0x18002051e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020523  lea     rdx, [rsp+170h+var_138]
0x180020528  mov     rcx, rbx
0x18002052b  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180020530  lea     rdx, [rsp+170h+var_150]
0x180020535  mov     rcx, rbx
0x180020538  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18002053d  jmp     loc_1800209D8
0x180020542  lea     rax, aConsentRetriev; "consent_retrieved_from_cr_count"
0x180020549  mov     [rbp+70h+var_10], 1Fh
0x18002054d  mov     [rbp+70h+var_18], rax
0x180020551  lea     rdx, [rbp+70h+var_D8]
0x180020555  lea     rax, [rdi+30h]
0x180020559  mov     [rbp+70h+var_28], 1Dh
0x18002055d  mov     [rbp+70h+var_8], rax
0x180020561  mov     rcx, rbx
0x180020564  lea     rax, aConsentReadFro_1; "consent_read_from_cache_count"
0x18002056b  mov     [rbp+70h+var_58], 15h
0x18002056f  mov     [rbp+70h+var_30], rax
0x180020573  lea     rax, [rdi+2Ch]
0x180020577  mov     [rbp+70h+var_20], rax
0x18002057b  lea     rax, aNonWebAccountC; "non_web_account_count"
0x180020582  mov     [rbp+70h+var_60], rax
0x180020586  lea     rax, [rdi+24h]
0x18002058a  mov     [rbp+70h+var_50], rax
0x18002058e  lea     rax, aAadAccountCoun; "aad_account_count"
0x180020595  mov     [rbp+70h+var_48], rax
0x180020599  lea     rax, [rdi+28h]
0x18002059d  mov     [rbp+70h+var_38], rax
0x1800205a1  lea     rax, aMsaAccountCoun; "msa_account_count"
0x1800205a8  mov     [rbp+70h+var_C0], rax
0x1800205ac  lea     rax, [rdi+20h]
0x1800205b0  mov     [rbp+70h+var_B0], rax
0x1800205b4  lea     rax, aAccountCount; "account_count"
0x1800205bb  mov     [rbp+70h+var_A8], rax
0x1800205bf  lea     rax, [rdi+1Ch]
0x1800205c3  mov     [rbp+70h+var_98], rax
0x1800205c7  lea     rax, aCrNotification_0; "cr_notification_subscription_attempted"
0x1800205ce  mov     [rsp+170h+var_150], rax
0x1800205d3  lea     rax, [rdi+1Bh]
0x1800205d7  mov     [rsp+170h+var_140], rax
0x1800205dc  lea     rax, aCrNotification; "cr_notification_subscription_success"
0x1800205e3  mov     [rsp+170h+var_138], rax
0x1800205e8  lea     rax, [rdi+1Ah]
0x1800205ec  mov     [rsp+170h+var_128], rax
0x1800205f1  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x1800205f8  mov     [rbp+70h+var_90], rax
0x1800205fc  lea     rax, [rdi+19h]
0x180020600  mov     [rbp+70h+var_80], rax
0x180020604  lea     rax, aCrReadCheck; "cr_read_check"
0x18002060b  mov     [rbp+70h+var_78], rax
0x18002060f  lea     rax, [rdi+18h]
0x180020613  mov     [rbp+70h+var_68], rax
0x180020617  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x18002061e  mov     [rsp+170h+var_120], rax
0x180020623  lea     rax, [rdi+17h]
0x180020627  mov     [rsp+170h+var_110], rax
0x18002062c  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020633  mov     [rsp+170h+var_108], rax
0x180020638  lea     rax, [rdi+16h]
0x18002063c  mov     [rsp+170h+var_F8], rax
0x180020641  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x180020648  mov     [rbp+70h+var_F0], rax
0x18002064c  lea     rax, [rdi+15h]
0x180020650  mov     [rbp+70h+var_E0], rax
0x180020654  lea     rax, aFailureHresult; "failure_hresult"
0x18002065b  mov     [rbp+70h+var_D8], rax
0x18002065f  lea     rax, [rdi+10h]
0x180020663  mov     [rbp+70h+var_C8], rax
0x180020667  mov     [rbp+70h+var_40], 11h
0x18002066b  mov     [rbp+70h+var_B8], 11h
0x18002066f  mov     [rbp+70h+var_A0], 0Dh
0x180020673  mov     [rsp+170h+var_148], 26h ; '&'
0x180020678  mov     [rsp+170h+var_130], 24h ; '$'
0x18002067d  mov     [rbp+70h+var_88], 17h
0x180020681  mov     [rbp+70h+var_70], 0Dh
0x180020685  mov     [rsp+170h+var_118], 17h
0x18002068a  mov     [rsp+170h+var_100], 1Ch
  ... truncated ...
```
