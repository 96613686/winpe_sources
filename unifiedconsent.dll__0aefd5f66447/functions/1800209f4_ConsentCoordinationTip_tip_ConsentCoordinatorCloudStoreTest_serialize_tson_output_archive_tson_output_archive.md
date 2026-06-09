# ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest::serialize<tson::output_archive>(tson::output_archive &)

- ea: `0x1800209f4`
- end: `0x18002111d`
- name: `??$serialize@Voutput_archive@tson@@@_tip_ConsentCoordinatorCloudStoreTest@ConsentCoordinationTip@@QEAAXAEAVoutput_archive@tson@@@Z`
- size: `1833`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800302c0`

## callees

- `0x1800100c8`
- `0x180011e84`
- `0x180012330`
- `0x1800194ec`
- `0x18002001c`
- `0x1800209f4`
- `0x18002d364`
- `0x18002d540`

## string_xrefs

- `0x180020b1d`: `consent_read_from_cache_count`
- `0x180020da0`: `consent_read_from_cache_count`
- `0x180020fa8`: `consent_read_from_cache_count`
- `0x180020a6f`: `cr_read_check`
- `0x180020b95`: `cr_read_check`
- `0x180020cd6`: `cr_read_check`
- `0x180020e3f`: `cr_read_check`
- `0x180020f11`: `cr_read_check`
- `0x180021021`: `cr_read_check`
- `0x180020a99`: `cr_all_accounts_read_failure`
- `0x180020bbc`: `cr_all_accounts_read_failure`
- `0x180020d26`: `cr_all_accounts_read_failure`
- `0x180020ebc`: `cr_all_accounts_read_failure`
- `0x180020f3c`: `cr_all_accounts_read_failure`
- `0x180021047`: `cr_all_accounts_read_failure`
- `0x180020a86`: `cr_consent_read_success`
- `0x180020ba9`: `cr_consent_read_success`
- `0x180020d40`: `cr_consent_read_success`
- `0x180020e52`: `cr_consent_read_success`
- `0x180020f28`: `cr_consent_read_success`
- `0x180021034`: `cr_consent_read_success`
- `0x180020c89`: `cr_notification_subscription_attempted`
- `0x180020e06`: `cr_notification_subscription_attempted`

## pseudocode

```c
__int64 __fastcall ConsentCoordinationTip::_tip_ConsentCoordinatorCloudStoreTest::serialize<tson::output_archive>(
        __int64 a1,
        __int64 a2)
{
  const char **v4; // rax
  const char **v5; // r9
  const char **v6; // r8
  const char **v7; // rdx
  const char *v9; // rax
  __int64 v10; // rdx
  const char *v11; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+68h] [rbp-98h]
  __int64 v13; // [rsp+70h] [rbp-90h]
  const char *v14; // [rsp+78h] [rbp-88h] BYREF
  char v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+88h] [rbp-78h]
  const char *v17; // [rsp+90h] [rbp-70h] BYREF
  char v18; // [rsp+98h] [rbp-68h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  const char *v20; // [rsp+A8h] [rbp-58h] BYREF
  char v21; // [rsp+B0h] [rbp-50h]
  __int64 v22; // [rsp+B8h] [rbp-48h]
  const char *v23; // [rsp+C0h] [rbp-40h] BYREF
  char v24; // [rsp+C8h] [rbp-38h]
  __int64 v25; // [rsp+D0h] [rbp-30h]
  const char *v26; // [rsp+D8h] [rbp-28h] BYREF
  char v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  const char *v29; // [rsp+F0h] [rbp-10h] BYREF
  char v30; // [rsp+F8h] [rbp-8h]
  __int64 v31; // [rsp+100h] [rbp+0h]
  const char *v32; // [rsp+108h] [rbp+8h] BYREF
  char v33; // [rsp+110h] [rbp+10h]
  __int64 v34; // [rsp+118h] [rbp+18h]
  const char *v35; // [rsp+120h] [rbp+20h] BYREF
  char v36; // [rsp+128h] [rbp+28h]
  __int64 v37; // [rsp+130h] [rbp+30h]
  const char *v38; // [rsp+138h] [rbp+38h] BYREF
  char v39; // [rsp+140h] [rbp+40h]
  __int64 v40; // [rsp+148h] [rbp+48h]
  const char *v41; // [rsp+150h] [rbp+50h] BYREF
  char v42; // [rsp+158h] [rbp+58h]
  __int64 v43; // [rsp+160h] [rbp+60h]
  const char *v44; // [rsp+168h] [rbp+68h] BYREF
  char v45; // [rsp+170h] [rbp+70h]
  __int64 v46; // [rsp+178h] [rbp+78h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableNotificationInCC>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DisableNotificationInCC>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl'::`2'::impl) )
      {
        v36 = 31;
        v35 = "consent_retrieved_from_cr_count";
        v33 = 29;
        v37 = a1 + 48;
        v30 = 21;
        v32 = "consent_read_from_cache_count";
        v34 = a1 + 44;
        v29 = "non_web_account_count";
        v31 = a1 + 36;
        v26 = "aad_account_count";
        v28 = a1 + 40;
        v41 = "msa_account_count";
        v43 = a1 + 32;
        v44 = "account_count";
        v46 = a1 + 28;
        v11 = "duplicate_version_found";
        v13 = a1 + 25;
        v14 = "cr_read_check";
        v16 = a1 + 24;
        v17 = "cr_consent_read_success";
        v19 = a1 + 23;
        v20 = "cr_all_accounts_read_failure";
        v22 = a1 + 22;
        v23 = "wnf_not_published";
        v25 = a1 + 21;
        v38 = "failure_hresult";
        v40 = a1 + 16;
        v27 = 17;
        v42 = 17;
        v45 = 13;
        v12 = 23;
        v15 = 13;
        v18 = 23;
        v21 = 28;
        v24 = 17;
        v39 = 15;
        tson::output_archive::process<tson::nvp<long &>>(a2, &v38);
        return tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>>(
                 a2,
                 (unsigned int)&v23,
                 (unsigned int)&v20,
                 (unsigned int)&v17,
                 (__int64)&v14,
                 (__int64)&v11,
                 (__int64)&v44,
                 (__int64)&v41,
                 (__int64)&v26,
                 (__int64)&v29,
                 (__int64)&v32,
                 (__int64)&v35);
      }
      v30 = 23;
      v29 = "duplicate_version_found";
      v33 = 13;
      v31 = a1 + 25;
      v36 = 23;
      v32 = "cr_read_check";
      v34 = a1 + 24;
      v35 = "cr_consent_read_success";
      v37 = a1 + 23;
      v38 = "cr_all_accounts_read_failure";
      v40 = a1 + 22;
      v26 = "failure_hresult";
      v28 = a1 + 16;
      v39 = 28;
      v27 = 15;
      tson::output_archive::process<tson::nvp<long &>>(a2, &v26);
      *(_BYTE *)(a2 + 8) = 17;
      *(_QWORD *)a2 = "wnf_not_published";
      tson::output_archive::operator()<bool &>(a2, a1 + 21);
      v4 = &v29;
      v5 = &v32;
      v6 = &v35;
      v7 = &v38;
      return tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>>(
               a2,
               (_DWORD)v7,
               (_DWORD)v6,
               (_DWORD)v5,
               (__int64)v4);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl'::`2'::impl) )
    {
      v21 = 38;
      v20 = "cr_notification_subscription_attempted";
      v18 = 36;
      v22 = a1 + 27;
      v15 = 23;
      v17 = "cr_notification_subscription_success";
      v19 = a1 + 26;
      v14 = "duplicate_version_found";
      v16 = a1 + 25;
      v11 = "cr_read_check";
      v13 = a1 + 24;
      v23 = "failure_hresult";
      v25 = a1 + 16;
      v12 = 13;
      v24 = 15;
      tson::output_archive::process<tson::nvp<long &>>(a2, &v23);
      *(_BYTE *)(a2 + 8) = 17;
      *(_QWORD *)a2 = "wnf_not_published";
      tson::output_archive::operator()<bool &>(a2, a1 + 21);
      *(_BYTE *)(a2 + 8) = 28;
      *(_QWORD *)a2 = "cr_all_accounts_read_failure";
      tson::output_archive::operator()<bool &>(a2, a1 + 22);
      v9 = "cr_consent_read_success";
      *(_BYTE *)(a2 + 8) = 23;
      v10 = a1 + 23;
LABEL_8:
      *(_QWORD *)a2 = v9;
      tson::output_archive::operator()<bool &>(a2, v10);
      v4 = &v20;
      v5 = &v17;
      v6 = &v14;
      v7 = &v11;
      return tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>>(
               a2,
               (_DWORD)v7,
               (_DWORD)v6,
               (_DWORD)v5,
               (__int64)v4);
    }
    v21 = 31;
    v20 = "consent_retrieved_from_cr_count";
    v18 = 29;
    v22 = a1 + 48;
    v15 = 21;
    v17 = "consent_read_from_cache_count";
    v19 = a1 + 44;
    v14 = "non_web_account_count";
    v16 = a1 + 36;
    v11 = "aad_account_count";
    v13 = a1 + 40;
    v44 = "msa_account_count";
    v46 = a1 + 32;
    v41 = "account_count";
    v43 = a1 + 28;
    v38 = "cr_notification_subscription_attempted";
    v40 = a1 + 27;
    v35 = "cr_notification_subscription_success";
    v37 = a1 + 26;
    v32 = "duplicate_version_found";
    v34 = a1 + 25;
    v29 = "cr_read_check";
    v31 = a1 + 24;
    v26 = "cr_consent_read_success";
    v28 = a1 + 23;
    v23 = "failure_hresult";
    v25 = a1 + 16;
    v12 = 17;
    v45 = 17;
    v42 = 13;
    v39 = 38;
    v36 = 36;
    v33 = 23;
    v30 = 13;
    v27 = 23;
    v24 = 15;
    tson::output_archive::process<tson::nvp<long &>>(a2, &v23);
    *(_BYTE *)(a2 + 8) = 17;
    *(_QWORD *)a2 = "wnf_not_published";
    tson::output_archive::operator()<bool &>(a2, a1 + 21);
    *(_BYTE *)(a2 + 8) = 28;
    *(_QWORD *)a2 = "cr_all_accounts_read_failure";
    tson::output_archive::operator()<bool &>(a2, a1 + 22);
  }
  else
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl'::`2'::impl) )
    {
      v21 = 23;
      v20 = "duplicate_version_found";
      v18 = 13;
      v22 = a1 + 25;
      v15 = 23;
      v17 = "cr_read_check";
      v19 = a1 + 24;
      v14 = "cr_consent_read_success";
      v16 = a1 + 23;
      v11 = "cr_all_accounts_read_failure";
      v13 = a1 + 22;
      v23 = "failure_hresult";
      v25 = a1 + 16;
      v12 = 28;
      v24 = 15;
      tson::output_archive::process<tson::nvp<long &>>(a2, &v23);
      v9 = "wnf_not_published";
      *(_BYTE *)(a2 + 8) = 17;
      v10 = a1 + 21;
      goto LABEL_8;
    }
    v21 = 31;
    v20 = "consent_retrieved_from_cr_count";
    v18 = 29;
    v22 = a1 + 48;
    v15 = 21;
    v17 = "consent_read_from_cache_count";
    v19 = a1 + 44;
    v14 = "non_web_account_count";
    v16 = a1 + 36;
    v11 = "aad_account_count";
    v13 = a1 + 40;
    v44 = "msa_account_count";
    v46 = a1 + 32;
    v41 = "account_count";
    v43 = a1 + 28;
    v38 = "duplicate_version_found";
    v40 = a1 + 25;
    v35 = "cr_read_check";
    v37 = a1 + 24;
    v32 = "cr_consent_read_success";
    v34 = a1 + 23;
    v29 = "cr_all_accounts_read_failure";
    v31 = a1 + 22;
    v26 = "wnf_not_published";
    v28 = a1 + 21;
    v23 = "failure_hresult";
    v25 = a1 + 16;
    v12 = 17;
    v45 = 17;
    v42 = 13;
    v39 = 23;
    v36 = 13;
    v33 = 23;
    v30 = 28;
    v27 = 17;
    v24 = 15;
    tson::output_archive::process<tson::nvp<long &>>(a2, &v23);
  }
  return tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>,tson::nvp<unsigned int &>>(
           a2,
           (unsigned int)&v26,
           (unsigned int)&v29,
           (unsigned int)&v32,
           (__int64)&v35,
           (__int64)&v38,
           (__int64)&v41,
           (__int64)&v44,
           (__int64)&v11,
           (__int64)&v14,
           (__int64)&v17,
           (__int64)&v20);
}

```

## disassembly

```asm
0x1800209f4  mov     [rsp-8+arg_0], rbx
0x1800209f9  mov     [rsp-8+arg_8], rdi
0x1800209fe  push    rbp
0x1800209ff  lea     rbp, [rsp-80h]
0x180020a04  sub     rsp, 180h
0x180020a0b  mov     rdi, rdx
0x180020a0e  mov     rbx, rcx
0x180020a11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification> `wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl(void)'::`2'::impl
0x180020a18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(void)
0x180020a1d  test    al, al
0x180020a1f  jz      loc_180020EDB
0x180020a25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableNotificationInCC@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableNotificationInCC@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableNotificationInCC> `wil::Feature<__WilFeatureTraits_Feature_DisableNotificationInCC>::GetImpl(void)'::`2'::impl
0x180020a2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableNotificationInCC@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableNotificationInCC>::__private_IsEnabled(void)
0x180020a31  test    al, al
0x180020a33  jz      loc_180020C75
0x180020a39  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl(void)'::`2'::impl
0x180020a40  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(void)
0x180020a45  test    al, al
0x180020a47  jnz     loc_180020AFB
0x180020a4d  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x180020a54  mov     [rbp+80h+var_88], 17h
0x180020a58  mov     [rbp+80h+var_90], rax
0x180020a5c  lea     rdx, [rbp+80h+var_A8]
0x180020a60  lea     rax, [rbx+19h]
0x180020a64  mov     [rbp+80h+var_70], 0Dh
0x180020a68  mov     [rbp+80h+var_80], rax
0x180020a6c  mov     rcx, rdi
0x180020a6f  lea     rax, aCrReadCheck; "cr_read_check"
0x180020a76  mov     [rbp+80h+var_58], 17h
0x180020a7a  mov     [rbp+80h+var_78], rax
0x180020a7e  lea     rax, [rbx+18h]
0x180020a82  mov     [rbp+80h+var_68], rax
0x180020a86  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020a8d  mov     [rbp+80h+var_60], rax
0x180020a91  lea     rax, [rbx+17h]
0x180020a95  mov     [rbp+80h+var_50], rax
0x180020a99  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020aa0  mov     [rbp+80h+var_48], rax
0x180020aa4  lea     rax, [rbx+16h]
0x180020aa8  mov     [rbp+80h+var_38], rax
0x180020aac  lea     rax, aFailureHresult; "failure_hresult"
0x180020ab3  mov     [rbp+80h+var_A8], rax
0x180020ab7  lea     rax, [rbx+10h]
0x180020abb  mov     [rbp+80h+var_98], rax
0x180020abf  mov     [rbp+80h+var_40], 1Ch
0x180020ac3  mov     [rbp+80h+var_A0], 0Fh
0x180020ac7  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x180020acc  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x180020ad3  mov     byte ptr [rdi+8], 11h
0x180020ad7  lea     rdx, [rbx+15h]
0x180020adb  mov     [rdi], rax
0x180020ade  mov     rcx, rdi
0x180020ae1  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x180020ae6  lea     rax, [rbp+80h+var_90]
0x180020aea  lea     r9, [rbp+80h+var_78]
0x180020aee  lea     r8, [rbp+80h+var_60]
0x180020af2  lea     rdx, [rbp+80h+var_48]
0x180020af6  jmp     loc_180020D6C
0x180020afb  lea     rax, aConsentRetriev; "consent_retrieved_from_cr_count"
0x180020b02  mov     [rbp+80h+var_58], 1Fh
0x180020b06  mov     [rbp+80h+var_60], rax
0x180020b0a  lea     rdx, [rbp+80h+var_48]
0x180020b0e  lea     rax, [rbx+30h]
0x180020b12  mov     [rbp+80h+var_70], 1Dh
0x180020b16  mov     [rbp+80h+var_50], rax
0x180020b1a  mov     rcx, rdi
0x180020b1d  lea     rax, aConsentReadFro_1; "consent_read_from_cache_count"
0x180020b24  mov     [rbp+80h+var_88], 15h
0x180020b28  mov     [rbp+80h+var_78], rax
0x180020b2c  lea     rax, [rbx+2Ch]
0x180020b30  mov     [rbp+80h+var_68], rax
0x180020b34  lea     rax, aNonWebAccountC; "non_web_account_count"
0x180020b3b  mov     [rbp+80h+var_90], rax
0x180020b3f  lea     rax, [rbx+24h]
0x180020b43  mov     [rbp+80h+var_80], rax
0x180020b47  lea     rax, aAadAccountCoun; "aad_account_count"
0x180020b4e  mov     [rbp+80h+var_A8], rax
0x180020b52  lea     rax, [rbx+28h]
0x180020b56  mov     [rbp+80h+var_98], rax
0x180020b5a  lea     rax, aMsaAccountCoun; "msa_account_count"
0x180020b61  mov     [rbp+80h+var_30], rax
0x180020b65  lea     rax, [rbx+20h]
0x180020b69  mov     [rbp+80h+var_20], rax
0x180020b6d  lea     rax, aAccountCount; "account_count"
0x180020b74  mov     [rbp+80h+var_18], rax
0x180020b78  lea     rax, [rbx+1Ch]
0x180020b7c  mov     [rbp+80h+var_8], rax
0x180020b80  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x180020b87  mov     [rsp+180h+var_120], rax
0x180020b8c  lea     rax, [rbx+19h]
0x180020b90  mov     [rsp+180h+var_110], rax
0x180020b95  lea     rax, aCrReadCheck; "cr_read_check"
0x180020b9c  mov     [rsp+180h+var_108], rax
0x180020ba1  lea     rax, [rbx+18h]
0x180020ba5  mov     [rbp+80h+var_F8], rax
0x180020ba9  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020bb0  mov     [rbp+80h+var_F0], rax
0x180020bb4  lea     rax, [rbx+17h]
0x180020bb8  mov     [rbp+80h+var_E0], rax
0x180020bbc  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020bc3  mov     [rbp+80h+var_D8], rax
0x180020bc7  lea     rax, [rbx+16h]
0x180020bcb  mov     [rbp+80h+var_C8], rax
0x180020bcf  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x180020bd6  mov     [rbp+80h+var_C0], rax
0x180020bda  lea     rax, [rbx+15h]
0x180020bde  mov     [rbp+80h+var_B0], rax
0x180020be2  lea     rax, aFailureHresult; "failure_hresult"
0x180020be9  mov     [rbp+80h+var_48], rax
0x180020bed  lea     rax, [rbx+10h]
0x180020bf1  mov     [rbp+80h+var_38], rax
0x180020bf5  mov     [rbp+80h+var_A0], 11h
0x180020bf9  mov     [rbp+80h+var_28], 11h
0x180020bfd  mov     [rbp+80h+var_10], 0Dh
0x180020c01  mov     [rsp+180h+var_118], 17h
0x180020c06  mov     [rbp+80h+var_100], 0Dh
0x180020c0a  mov     [rbp+80h+var_E8], 17h
0x180020c0e  mov     [rbp+80h+var_D0], 1Ch
0x180020c12  mov     [rbp+80h+var_B8], 11h
0x180020c16  mov     [rbp+80h+var_40], 0Fh
0x180020c1a  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x180020c1f  lea     rax, [rbp+80h+var_60]
0x180020c23  mov     [rsp+180h+var_128], rax
0x180020c28  lea     r9, [rbp+80h+var_F0]
0x180020c2c  lea     rax, [rbp+80h+var_78]
0x180020c30  mov     [rsp+180h+var_130], rax
0x180020c35  lea     r8, [rbp+80h+var_D8]
0x180020c39  lea     rax, [rbp+80h+var_90]
0x180020c3d  mov     [rsp+180h+var_138], rax
0x180020c42  lea     rdx, [rbp+80h+var_C0]
0x180020c46  lea     rax, [rbp+80h+var_A8]
0x180020c4a  mov     [rsp+180h+var_140], rax
0x180020c4f  lea     rax, [rbp+80h+var_30]
0x180020c53  mov     [rsp+180h+var_148], rax
0x180020c58  lea     rax, [rbp+80h+var_18]
0x180020c5c  mov     [rsp+180h+var_150], rax
0x180020c61  lea     rax, [rsp+180h+var_120]
0x180020c66  mov     [rsp+180h+var_158], rax
0x180020c6b  lea     rax, [rsp+180h+var_108]
0x180020c70  jmp     loc_1800210FB
0x180020c75  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl(void)'::`2'::impl
0x180020c7c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(void)
0x180020c81  test    al, al
0x180020c83  jnz     loc_180020D7E
0x180020c89  lea     rax, aCrNotification_0; "cr_notification_subscription_attempted"
0x180020c90  mov     [rbp+80h+var_D0], 26h ; '&'
0x180020c94  mov     [rbp+80h+var_D8], rax
0x180020c98  lea     rdx, [rbp+80h+var_C0]
0x180020c9c  lea     rax, [rbx+1Bh]
0x180020ca0  mov     [rbp+80h+var_E8], 24h ; '$'
0x180020ca4  mov     [rbp+80h+var_C8], rax
0x180020ca8  mov     rcx, rdi
0x180020cab  lea     rax, aCrNotification; "cr_notification_subscription_success"
0x180020cb2  mov     [rbp+80h+var_100], 17h
0x180020cb6  mov     [rbp+80h+var_F0], rax
0x180020cba  lea     rax, [rbx+1Ah]
0x180020cbe  mov     [rbp+80h+var_E0], rax
0x180020cc2  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x180020cc9  mov     [rsp+180h+var_108], rax
0x180020cce  lea     rax, [rbx+19h]
0x180020cd2  mov     [rbp+80h+var_F8], rax
0x180020cd6  lea     rax, aCrReadCheck; "cr_read_check"
0x180020cdd  mov     [rsp+180h+var_120], rax
0x180020ce2  lea     rax, [rbx+18h]
0x180020ce6  mov     [rsp+180h+var_110], rax
0x180020ceb  lea     rax, aFailureHresult; "failure_hresult"
0x180020cf2  mov     [rbp+80h+var_C0], rax
0x180020cf6  lea     rax, [rbx+10h]
0x180020cfa  mov     [rbp+80h+var_B0], rax
0x180020cfe  mov     [rsp+180h+var_118], 0Dh
0x180020d03  mov     [rbp+80h+var_B8], 0Fh
0x180020d07  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x180020d0c  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x180020d13  mov     byte ptr [rdi+8], 11h
0x180020d17  lea     rdx, [rbx+15h]
0x180020d1b  mov     [rdi], rax
0x180020d1e  mov     rcx, rdi
0x180020d21  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x180020d26  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020d2d  mov     byte ptr [rdi+8], 1Ch
0x180020d31  lea     rdx, [rbx+16h]
0x180020d35  mov     [rdi], rax
0x180020d38  mov     rcx, rdi
0x180020d3b  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x180020d40  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020d47  mov     byte ptr [rdi+8], 17h
0x180020d4b  lea     rdx, [rbx+17h]
0x180020d4f  mov     rcx, rdi
0x180020d52  mov     [rdi], rax
0x180020d55  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x180020d5a  lea     rax, [rbp+80h+var_D8]
0x180020d5e  lea     r9, [rbp+80h+var_F0]
0x180020d62  lea     r8, [rsp+180h+var_108]
0x180020d67  lea     rdx, [rsp+180h+var_120]
0x180020d6c  mov     rcx, rdi
0x180020d6f  mov     [rsp+180h+var_160], rax
0x180020d74  call    ??$process@V?$nvp@AEA_N@tson@@V12@V12@V12@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@000@Z; tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>>(tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&)
0x180020d79  jmp     loc_180021108
0x180020d7e  lea     rax, aConsentRetriev; "consent_retrieved_from_cr_count"
0x180020d85  mov     [rbp+80h+var_D0], 1Fh
0x180020d89  mov     [rbp+80h+var_D8], rax
0x180020d8d  lea     rdx, [rbp+80h+var_C0]
0x180020d91  lea     rax, [rbx+30h]
0x180020d95  mov     [rbp+80h+var_E8], 1Dh
0x180020d99  mov     [rbp+80h+var_C8], rax
0x180020d9d  mov     rcx, rdi
0x180020da0  lea     rax, aConsentReadFro_1; "consent_read_from_cache_count"
0x180020da7  mov     [rbp+80h+var_100], 15h
0x180020dab  mov     [rbp+80h+var_F0], rax
0x180020daf  lea     rax, [rbx+2Ch]
0x180020db3  mov     [rbp+80h+var_E0], rax
0x180020db7  lea     rax, aNonWebAccountC; "non_web_account_count"
0x180020dbe  mov     [rsp+180h+var_108], rax
0x180020dc3  lea     rax, [rbx+24h]
0x180020dc7  mov     [rbp+80h+var_F8], rax
0x180020dcb  lea     rax, aAadAccountCoun; "aad_account_count"
0x180020dd2  mov     [rsp+180h+var_120], rax
0x180020dd7  lea     rax, [rbx+28h]
0x180020ddb  mov     [rsp+180h+var_110], rax
0x180020de0  lea     rax, aMsaAccountCoun; "msa_account_count"
0x180020de7  mov     [rbp+80h+var_18], rax
0x180020deb  lea     rax, [rbx+20h]
0x180020def  mov     [rbp+80h+var_8], rax
0x180020df3  lea     rax, aAccountCount; "account_count"
0x180020dfa  mov     [rbp+80h+var_30], rax
0x180020dfe  lea     rax, [rbx+1Ch]
0x180020e02  mov     [rbp+80h+var_20], rax
0x180020e06  lea     rax, aCrNotification_0; "cr_notification_subscription_attempted"
0x180020e0d  mov     [rbp+80h+var_48], rax
0x180020e11  lea     rax, [rbx+1Bh]
0x180020e15  mov     [rbp+80h+var_38], rax
0x180020e19  lea     rax, aCrNotification; "cr_notification_subscription_success"
0x180020e20  mov     [rbp+80h+var_60], rax
0x180020e24  lea     rax, [rbx+1Ah]
0x180020e28  mov     [rbp+80h+var_50], rax
0x180020e2c  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x180020e33  mov     [rbp+80h+var_78], rax
0x180020e37  lea     rax, [rbx+19h]
0x180020e3b  mov     [rbp+80h+var_68], rax
0x180020e3f  lea     rax, aCrReadCheck; "cr_read_check"
0x180020e46  mov     [rbp+80h+var_90], rax
0x180020e4a  lea     rax, [rbx+18h]
0x180020e4e  mov     [rbp+80h+var_80], rax
0x180020e52  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020e59  mov     [rbp+80h+var_A8], rax
0x180020e5d  lea     rax, [rbx+17h]
0x180020e61  mov     [rbp+80h+var_98], rax
0x180020e65  lea     rax, aFailureHresult; "failure_hresult"
0x180020e6c  mov     [rbp+80h+var_C0], rax
0x180020e70  lea     rax, [rbx+10h]
0x180020e74  mov     [rbp+80h+var_B0], rax
0x180020e78  mov     [rsp+180h+var_118], 11h
0x180020e7d  mov     [rbp+80h+var_10], 11h
0x180020e81  mov     [rbp+80h+var_28], 0Dh
0x180020e85  mov     [rbp+80h+var_40], 26h ; '&'
0x180020e89  mov     [rbp+80h+var_58], 24h ; '$'
0x180020e8d  mov     [rbp+80h+var_70], 17h
0x180020e91  mov     [rbp+80h+var_88], 0Dh
0x180020e95  mov     [rbp+80h+var_A0], 17h
0x180020e99  mov     [rbp+80h+var_B8], 0Fh
0x180020e9d  call    ??$process@V?$nvp@AEAJ@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAJ@1@@Z; tson::output_archive::process<tson::nvp<long &>>(tson::nvp<long &> &&)
0x180020ea2  lea     rax, aWnfNotPublishe; "wnf_not_published"
0x180020ea9  mov     byte ptr [rdi+8], 11h
0x180020ead  lea     rdx, [rbx+15h]
0x180020eb1  mov     [rdi], rax
0x180020eb4  mov     rcx, rdi
0x180020eb7  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x180020ebc  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020ec3  mov     byte ptr [rdi+8], 1Ch
0x180020ec7  lea     rdx, [rbx+16h]
0x180020ecb  mov     [rdi], rax
0x180020ece  mov     rcx, rdi
0x180020ed1  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x180020ed6  jmp     loc_1800210AA
0x180020edb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::GetImpl(void)'::`2'::impl
0x180020ee2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCRReadFailureCountFix>::__private_IsEnabled(void)
0x180020ee7  test    al, al
0x180020ee9  jnz     loc_180020F86
0x180020eef  lea     rax, aDuplicateVersi_0; "duplicate_version_found"
0x180020ef6  mov     [rbp+80h+var_D0], 17h
0x180020efa  mov     [rbp+80h+var_D8], rax
0x180020efe  lea     rdx, [rbp+80h+var_C0]
0x180020f02  lea     rax, [rbx+19h]
0x180020f06  mov     [rbp+80h+var_E8], 0Dh
0x180020f0a  mov     [rbp+80h+var_C8], rax
0x180020f0e  mov     rcx, rdi
0x180020f11  lea     rax, aCrReadCheck; "cr_read_check"
0x180020f18  mov     [rbp+80h+var_100], 17h
0x180020f1c  mov     [rbp+80h+var_F0], rax
0x180020f20  lea     rax, [rbx+18h]
0x180020f24  mov     [rbp+80h+var_E0], rax
0x180020f28  lea     rax, aCrConsentReadS; "cr_consent_read_success"
0x180020f2f  mov     [rsp+180h+var_108], rax
0x180020f34  lea     rax, [rbx+17h]
0x180020f38  mov     [rbp+80h+var_F8], rax
0x180020f3c  lea     rax, aCrAllAccountsR; "cr_all_accounts_read_failure"
0x180020f43  mov     [rsp+180h+var_120], rax
0x180020f48  lea     rax, [rbx+16h]
0x180020f4c  mov     [rsp+180h+var_110], rax
0x180020f51  lea     rax, aFailureHresult; "failure_hresult"
  ... truncated ...
```
