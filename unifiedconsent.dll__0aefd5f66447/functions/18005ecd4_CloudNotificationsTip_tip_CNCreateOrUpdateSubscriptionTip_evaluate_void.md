# CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::evaluate(void)

- ea: `0x18005ecd4`
- end: `0x18005f305`
- name: `?evaluate@_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@QEAAXXZ`
- size: `1585`
- prototype: `void __fastcall(CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18005ec80`

## callees

- `0x18002d324`
- `0x18005ce10`
- `0x18005e6d0`
- `0x18005ecd4`
- `0x18007d010`

## string_xrefs

- `0x18005eec4`: `reason::cachedChannelCheckFailed`
- `0x18005f150`: `reason::cachedChannelCheckFailed`
- `0x18005f0bf`: `reason::createChannelFailedDueToMismatchedPackageFamilyName`
- `0x18005ef5c`: `reason::cachedDataUpdateFailed`
- `0x18005f1bd`: `reason::cachedDataUpdateFailed`

## pseudocode

```c
void __fastcall CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::evaluate(
        CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip *this)
{
  int v2; // eax
  const char *v3; // rcx
  char v4; // al
  const char *v5; // rdx
  __int64 v6; // rax
  const char *v7; // rcx
  char v8; // al
  const char *v9; // rcx
  char v10; // al
  const char *v11; // rcx
  char v12; // al
  const char *v13; // rcx
  char v14; // al
  const char *v15; // rcx
  char v16; // al
  const char *v17; // rcx
  char v18; // al
  __int16 v19; // r8
  const char *v20; // rcx
  char v21; // al
  int v22; // eax
  const char *v23; // rcx
  char v24; // al
  const char *v25; // rcx
  char v26; // al
  const char *v27; // rcx
  char v28; // al
  const char *v29; // rcx
  char v30; // al
  const char *v31; // rcx
  char v32; // al
  int v33; // eax
  const char *v34; // rcx
  char v35; // al
  const char *v36; // rcx
  char v37; // al
  const char *v38; // rcx
  char v39; // al
  const char *v40; // rcx
  char v41; // al
  const char *v42; // rcx
  char v43; // al
  const char *v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  char v47; // cl
  const char *v48; // rcx
  char v49; // al
  const char *v50; // rcx
  char v51; // al

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudDirectNotification>::GetImpl'::`2'::impl) )
  {
    v50 = "reason::none";
    v51 = 114;
    v44 = "reason::none";
    do
    {
      ++v50;
      if ( v51 == 58 )
        v44 = v50;
      v51 = *v50;
    }
    while ( *v50 );
    v45 = *((_QWORD *)this + 1);
    if ( *(_BYTE *)(v45 + 152) )
      return;
    *(_BYTE *)(v45 + 152) = 4;
    goto LABEL_158;
  }
  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    v48 = "reason::processShutDown";
    v49 = 114;
    v5 = "reason::processShutDown";
    do
    {
      ++v48;
      if ( v49 == 58 )
        v5 = v48;
      v49 = *v48;
    }
    while ( *v48 );
    v6 = *((_QWORD *)this + 1);
    if ( !*(_BYTE *)(v6 + 152) )
    {
      *(_BYTE *)(v6 + 152) = 4;
      *(_WORD *)(v6 + 154) = 1;
      goto LABEL_151;
    }
    return;
  }
  if ( *((int *)this + 77) < 0 && (unsigned int)CloudNotificationsTip::GetFailureReportMode() == 1 )
  {
    v2 = *((_DWORD *)this + 76);
    switch ( v2 )
    {
      case 2:
        v3 = "reason::invalidClientId";
        v4 = 114;
        v5 = "reason::invalidClientId";
        do
        {
          ++v3;
          if ( v4 == 58 )
            v5 = v3;
          v4 = *v3;
        }
        while ( *v3 );
        v6 = *((_QWORD *)this + 1);
        if ( !*(_BYTE *)(v6 + 152) )
        {
          *(_BYTE *)(v6 + 152) = 2;
LABEL_14:
          *(_WORD *)(v6 + 154) = 2;
LABEL_151:
          *(_QWORD *)(v6 + 160) = v5;
          return;
        }
        return;
      case 3:
        v7 = "reason::mutexCreationFailed";
        v8 = 114;
        v5 = "reason::mutexCreationFailed";
        do
        {
          ++v7;
          if ( v8 == 58 )
            v5 = v7;
          v8 = *v7;
        }
        while ( *v7 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 2;
        goto LABEL_22;
      case 4:
        v9 = "reason::mutexAcquisitionFailed";
        v10 = 114;
        v5 = "reason::mutexAcquisitionFailed";
        do
        {
          ++v9;
          if ( v10 == 58 )
            v5 = v9;
          v10 = *v9;
        }
        while ( *v9 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 2;
        goto LABEL_30;
      case 5:
        v11 = "reason::wnpEndpointRegistrationFailed";
        v12 = 114;
        v5 = "reason::wnpEndpointRegistrationFailed";
        do
        {
          ++v11;
          if ( v12 == 58 )
            v5 = v11;
          v12 = *v11;
        }
        while ( *v11 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 2;
        goto LABEL_38;
      case 6:
        v13 = "reason::wnpChannelCreationFailed";
        v14 = 114;
        v5 = "reason::wnpChannelCreationFailed";
        do
        {
          ++v13;
          if ( v14 == 58 )
            v5 = v13;
          v14 = *v13;
        }
        while ( *v13 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 2;
        goto LABEL_46;
      case 7:
        v15 = "reason::cachedChannelCheckFailed";
        v16 = 114;
        v5 = "reason::cachedChannelCheckFailed";
        do
        {
          ++v15;
          if ( v16 == 58 )
            v5 = v15;
          v16 = *v15;
        }
        while ( *v15 );
        v6 = *((_QWORD *)this + 1);
        if ( !*(_BYTE *)(v6 + 152) )
        {
          *(_BYTE *)(v6 + 152) = 2;
          *(_WORD *)(v6 + 154) = 7;
          goto LABEL_151;
        }
        return;
      case 8:
        v17 = "reason::subscriptionRequestFailed";
        v18 = 114;
        v5 = "reason::subscriptionRequestFailed";
        do
        {
          ++v17;
          if ( v18 == 58 )
            v5 = v17;
          v18 = *v17;
        }
        while ( *v17 );
        v6 = *((_QWORD *)this + 1);
        if ( !*(_BYTE *)(v6 + 152) )
        {
          *(_BYTE *)(v6 + 152) = 2;
          *(_WORD *)(v6 + 154) = 8;
          goto LABEL_151;
        }
        return;
    }
    v19 = 9;
    if ( v2 == 9 )
    {
      v20 = "reason::cachedDataUpdateFailed";
      v21 = 114;
      v5 = "reason::cachedDataUpdateFailed";
      do
      {
        ++v20;
        if ( v21 == 58 )
          v5 = v20;
        v21 = *v20;
      }
      while ( *v20 );
      v6 = *((_QWORD *)this + 1);
      if ( *(_BYTE *)(v6 + 152) )
        return;
      *(_BYTE *)(v6 + 152) = 2;
LABEL_68:
      *(_WORD *)(v6 + 154) = v19;
      goto LABEL_151;
    }
  }
  v22 = *((_DWORD *)this + 76);
  if ( v22 != 2 )
  {
    switch ( v22 )
    {
      case 3:
        v25 = "reason::mutexCreationFailed";
        v26 = 114;
        v5 = "reason::mutexCreationFailed";
        do
        {
          ++v25;
          if ( v26 == 58 )
            v5 = v25;
          v26 = *v25;
        }
        while ( *v25 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 3;
LABEL_22:
        *(_WORD *)(v6 + 154) = 3;
        goto LABEL_151;
      case 4:
        v27 = "reason::mutexAcquisitionFailed";
        v28 = 114;
        v5 = "reason::mutexAcquisitionFailed";
        do
        {
          ++v27;
          if ( v28 == 58 )
            v5 = v27;
          v28 = *v27;
        }
        while ( *v27 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 3;
LABEL_30:
        *(_WORD *)(v6 + 154) = 4;
        goto LABEL_151;
      case 5:
        v29 = "reason::wnpEndpointRegistrationFailed";
        v30 = 114;
        v5 = "reason::wnpEndpointRegistrationFailed";
        do
        {
          ++v29;
          if ( v30 == 58 )
            v5 = v29;
          v30 = *v29;
        }
        while ( *v29 );
        v6 = *((_QWORD *)this + 1);
        if ( *(_BYTE *)(v6 + 152) )
          return;
        *(_BYTE *)(v6 + 152) = 3;
LABEL_38:
        *(_WORD *)(v6 + 154) = 5;
        goto LABEL_151;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::GetImpl'::`2'::impl)
      && *((_DWORD *)this + 76) == 6
      && *((_DWORD *)this + 77) == -2147023728 )
    {
      v31 = "reason::createChannelFailedDueToMismatchedPackageFamilyName";
      v32 = 114;
      v5 = "reason::createChannelFailedDueToMismatchedPackageFamilyName";
      do
      {
        ++v31;
        if ( v32 == 58 )
          v5 = v31;
        v32 = *v31;
      }
      while ( *v31 );
      v6 = *((_QWORD *)this + 1);
      if ( !*(_BYTE *)(v6 + 152) )
      {
        *(_BYTE *)(v6 + 152) = 2;
        *(_WORD *)(v6 + 154) = 11;
        goto LABEL_151;
      }
      return;
    }
    v33 = *((_DWORD *)this + 76);
    if ( v33 == 6 )
    {
      v34 = "reason::wnpChannelCreationFailed";
      v35 = 114;
      v5 = "reason::wnpChannelCreationFailed";
      do
      {
        ++v34;
        if ( v35 == 58 )
          v5 = v34;
        v35 = *v34;
      }
      while ( *v34 );
      v6 = *((_QWORD *)this + 1);
      if ( *(_BYTE *)(v6 + 152) )
        return;
      *(_BYTE *)(v6 + 152) = 3;
LABEL_46:
      *(_WORD *)(v6 + 154) = 6;
      goto LABEL_151;
    }
    v19 = 7;
    if ( v33 == 7 )
    {
      v36 = "reason::cachedChannelCheckFailed";
      v37 = 114;
      v5 = "reason::cachedChannelCheckFailed";
      do
      {
        ++v36;
        if ( v37 == 58 )
          v5 = v36;
        v37 = *v36;
      }
      while ( *v36 );
LABEL_118:
      v6 = *((_QWORD *)this + 1);
      if ( *(_BYTE *)(v6 + 152) )
        return;
      *(_BYTE *)(v6 + 152) = 3;
      goto LABEL_68;
    }
    v19 = 8;
    if ( v33 == 8 )
    {
      v38 = "reason::subscriptionRequestFailed";
      v39 = 114;
      v5 = "reason::subscriptionRequestFailed";
      do
      {
        ++v38;
        if ( v39 == 58 )
          v5 = v38;
        v39 = *v38;
      }
      while ( *v38 );
      goto LABEL_118;
    }
    v19 = 9;
    if ( v33 == 9 )
    {
      v40 = "reason::cachedDataUpdateFailed";
      v41 = 114;
      v5 = "reason::cachedDataUpdateFailed";
      do
      {
        ++v40;
        if ( v41 == 58 )
          v5 = v40;
        v41 = *v40;
      }
      while ( *v40 );
      goto LABEL_118;
    }
    if ( v33 != 0xFFFF )
    {
      v46 = *((_QWORD *)this + 1);
      v47 = *(_BYTE *)(v46 + 152);
      if ( (*(_DWORD *)(v46 + 56) & 0x200) != 0 )
      {
        if ( v47 )
          return;
        *(_BYTE *)(v46 + 152) = 1;
        *(_WORD *)(v46 + 154) = 0x8000;
      }
      else
      {
        if ( v47 )
          return;
        *(_BYTE *)(v46 + 152) = 3;
        *(_WORD *)(v46 + 154) = 16385;
      }
      *(_QWORD *)(v46 + 160) = 0;
      return;
    }
    v42 = "reason::none";
    v43 = 114;
    v44 = "reason::none";
    do
    {
      ++v42;
      if ( v43 == 58 )
        v44 = v42;
      v43 = *v42;
    }
    while ( *v42 );
    v45 = *((_QWORD *)this + 1);
    if ( *(_BYTE *)(v45 + 152) )
      return;
    *(_BYTE *)(v45 + 152) = 1;
LABEL_158:
    *(_QWORD *)(v45 + 160) = v44;
    *(_WORD *)(v45 + 154) = 0;
    return;
  }
  v23 = "reason::invalidClientId";
  v24 = 114;
  v5 = "reason::invalidClientId";
  do
  {
    ++v23;
    if ( v24 == 58 )
      v5 = v23;
    v24 = *v23;
  }
  while ( *v23 );
  v6 = *((_QWORD *)this + 1);
  if ( !*(_BYTE *)(v6 + 152) )
  {
    *(_BYTE *)(v6 + 152) = 3;
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x18005ecd4  push    rbx
0x18005ecd6  push    rbp
0x18005ecd7  push    rsi
0x18005ecd8  push    rdi
0x18005ecd9  push    r12
0x18005ecdb  push    r13
0x18005ecdd  push    r14
0x18005ecdf  push    r15
0x18005ece1  sub     rsp, 28h
0x18005ece5  mov     rbx, rcx
0x18005ece8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDirectNotification@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectNotification@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectNotification> `wil::Feature<__WilFeatureTraits_Feature_CloudDirectNotification>::GetImpl(void)'::`2'::impl
0x18005ecef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectNotification@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectNotification>::__private_IsEnabled(void)
0x18005ecf4  xor     ebp, ebp
0x18005ecf6  test    al, al
0x18005ecf8  jz      loc_18005F2B1
0x18005ecfe  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bpl; bool wil::details::g_processShutdownInProgress
0x18005ed05  jnz     loc_18005F26C
0x18005ed0b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18005ed12  test    rax, rax
0x18005ed15  jz      short loc_18005ED24
0x18005ed17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed1c  test    al, al
0x18005ed1e  jnz     loc_18005F26C
0x18005ed24  mov     ecx, [rbx+134h]
0x18005ed2a  mov     edi, 1
0x18005ed2f  lea     esi, [rdi+3]
0x18005ed32  lea     r14d, [rdi+1]
0x18005ed36  lea     r15d, [rdi+2]
0x18005ed3a  lea     r13d, [rdi+4]
0x18005ed3e  lea     r12d, [rdi+5]
0x18005ed42  test    ecx, ecx
0x18005ed44  jns     loc_18005EF9D
0x18005ed4a  call    CloudNotificationsTip__GetFailureReportMode
0x18005ed4f  cmp     eax, edi
0x18005ed51  jnz     loc_18005EF9D
0x18005ed57  mov     eax, [rbx+130h]
0x18005ed5d  cmp     eax, r14d
0x18005ed60  jnz     short loc_18005EDA3
0x18005ed62  lea     rcx, aReasonInvalidc; "reason::invalidClientId"
0x18005ed69  mov     al, 72h ; 'r'
0x18005ed6b  mov     rdx, rcx
0x18005ed6e  add     rcx, rdi
0x18005ed71  cmp     al, 3Ah ; ':'
0x18005ed73  jnz     short loc_18005ED78
0x18005ed75  mov     rdx, rcx
0x18005ed78  mov     al, [rcx]
0x18005ed7a  test    al, al
0x18005ed7c  jnz     short loc_18005ED6E
0x18005ed7e  mov     rax, [rbx+8]
0x18005ed82  cmp     [rax+98h], bpl
0x18005ed89  jnz     loc_18005F2F4
0x18005ed8f  mov     [rax+98h], r14b
0x18005ed96  mov     [rax+9Ah], r14w
0x18005ed9e  jmp     loc_18005F2A8
0x18005eda3  cmp     eax, r15d
0x18005eda6  jnz     short loc_18005EDE9
0x18005eda8  lea     rcx, aReasonMutexcre; "reason::mutexCreationFailed"
0x18005edaf  mov     al, 72h ; 'r'
0x18005edb1  mov     rdx, rcx
0x18005edb4  add     rcx, rdi
0x18005edb7  cmp     al, 3Ah ; ':'
0x18005edb9  jnz     short loc_18005EDBE
0x18005edbb  mov     rdx, rcx
0x18005edbe  mov     al, [rcx]
0x18005edc0  test    al, al
0x18005edc2  jnz     short loc_18005EDB4
0x18005edc4  mov     rax, [rbx+8]
0x18005edc8  cmp     [rax+98h], bpl
0x18005edcf  jnz     loc_18005F2F4
0x18005edd5  mov     [rax+98h], r14b
0x18005eddc  mov     [rax+9Ah], r15w
0x18005ede4  jmp     loc_18005F2A8
0x18005ede9  cmp     eax, esi
0x18005edeb  jnz     short loc_18005EE2D
0x18005eded  lea     rcx, aReasonMutexacq; "reason::mutexAcquisitionFailed"
0x18005edf4  mov     al, 72h ; 'r'
0x18005edf6  mov     rdx, rcx
0x18005edf9  add     rcx, rdi
0x18005edfc  cmp     al, 3Ah ; ':'
0x18005edfe  jnz     short loc_18005EE03
0x18005ee00  mov     rdx, rcx
0x18005ee03  mov     al, [rcx]
0x18005ee05  test    al, al
0x18005ee07  jnz     short loc_18005EDF9
0x18005ee09  mov     rax, [rbx+8]
0x18005ee0d  cmp     [rax+98h], bpl
0x18005ee14  jnz     loc_18005F2F4
0x18005ee1a  mov     [rax+98h], r14b
0x18005ee21  mov     [rax+9Ah], si
0x18005ee28  jmp     loc_18005F2A8
0x18005ee2d  cmp     eax, r13d
0x18005ee30  jnz     short loc_18005EE73
0x18005ee32  lea     rcx, aReasonWnpendpo; "reason::wnpEndpointRegistrationFailed"
0x18005ee39  mov     al, 72h ; 'r'
0x18005ee3b  mov     rdx, rcx
0x18005ee3e  add     rcx, rdi
0x18005ee41  cmp     al, 3Ah ; ':'
0x18005ee43  jnz     short loc_18005EE48
0x18005ee45  mov     rdx, rcx
0x18005ee48  mov     al, [rcx]
0x18005ee4a  test    al, al
0x18005ee4c  jnz     short loc_18005EE3E
0x18005ee4e  mov     rax, [rbx+8]
0x18005ee52  cmp     [rax+98h], bpl
0x18005ee59  jnz     loc_18005F2F4
0x18005ee5f  mov     [rax+98h], r14b
0x18005ee66  mov     [rax+9Ah], r13w
0x18005ee6e  jmp     loc_18005F2A8
0x18005ee73  cmp     eax, r12d
0x18005ee76  jnz     short loc_18005EEB9
0x18005ee78  lea     rcx, aReasonWnpchann; "reason::wnpChannelCreationFailed"
0x18005ee7f  mov     al, 72h ; 'r'
0x18005ee81  mov     rdx, rcx
0x18005ee84  add     rcx, rdi
0x18005ee87  cmp     al, 3Ah ; ':'
0x18005ee89  jnz     short loc_18005EE8E
0x18005ee8b  mov     rdx, rcx
0x18005ee8e  mov     al, [rcx]
0x18005ee90  test    al, al
0x18005ee92  jnz     short loc_18005EE84
0x18005ee94  mov     rax, [rbx+8]
0x18005ee98  cmp     [rax+98h], bpl
0x18005ee9f  jnz     loc_18005F2F4
0x18005eea5  mov     [rax+98h], r14b
0x18005eeac  mov     [rax+9Ah], r12w
0x18005eeb4  jmp     loc_18005F2A8
0x18005eeb9  mov     r10d, 7
0x18005eebf  cmp     eax, r10d
0x18005eec2  jnz     short loc_18005EF05
0x18005eec4  lea     rcx, aReasonCachedch; "reason::cachedChannelCheckFailed"
0x18005eecb  mov     al, 72h ; 'r'
0x18005eecd  mov     rdx, rcx
0x18005eed0  add     rcx, rdi
0x18005eed3  cmp     al, 3Ah ; ':'
0x18005eed5  jnz     short loc_18005EEDA
0x18005eed7  mov     rdx, rcx
0x18005eeda  mov     al, [rcx]
0x18005eedc  test    al, al
0x18005eede  jnz     short loc_18005EED0
0x18005eee0  mov     rax, [rbx+8]
0x18005eee4  cmp     [rax+98h], bpl
0x18005eeeb  jnz     loc_18005F2F4
0x18005eef1  mov     [rax+98h], r14b
0x18005eef8  mov     [rax+9Ah], r10w
0x18005ef00  jmp     loc_18005F2A8
0x18005ef05  mov     r9d, 8
0x18005ef0b  cmp     eax, r9d
0x18005ef0e  jnz     short loc_18005EF51
0x18005ef10  lea     rcx, aReasonSubscrip; "reason::subscriptionRequestFailed"
0x18005ef17  mov     al, 72h ; 'r'
0x18005ef19  mov     rdx, rcx
0x18005ef1c  add     rcx, rdi
0x18005ef1f  cmp     al, 3Ah ; ':'
0x18005ef21  jnz     short loc_18005EF26
0x18005ef23  mov     rdx, rcx
0x18005ef26  mov     al, [rcx]
0x18005ef28  test    al, al
0x18005ef2a  jnz     short loc_18005EF1C
0x18005ef2c  mov     rax, [rbx+8]
0x18005ef30  cmp     [rax+98h], bpl
0x18005ef37  jnz     loc_18005F2F4
0x18005ef3d  mov     [rax+98h], r14b
0x18005ef44  mov     [rax+9Ah], r9w
0x18005ef4c  jmp     loc_18005F2A8
0x18005ef51  mov     r8d, 9
0x18005ef57  cmp     eax, r8d
0x18005ef5a  jnz     short loc_18005EF9D
0x18005ef5c  lea     rcx, aReasonCachedda; "reason::cachedDataUpdateFailed"
0x18005ef63  mov     al, 72h ; 'r'
0x18005ef65  mov     rdx, rcx
0x18005ef68  add     rcx, rdi
0x18005ef6b  cmp     al, 3Ah ; ':'
0x18005ef6d  jnz     short loc_18005EF72
0x18005ef6f  mov     rdx, rcx
0x18005ef72  mov     al, [rcx]
0x18005ef74  test    al, al
0x18005ef76  jnz     short loc_18005EF68
0x18005ef78  mov     rax, [rbx+8]
0x18005ef7c  cmp     [rax+98h], bpl
0x18005ef83  jnz     loc_18005F2F4
0x18005ef89  mov     [rax+98h], r14b
0x18005ef90  mov     [rax+9Ah], r8w
0x18005ef98  jmp     loc_18005F2A8
0x18005ef9d  mov     eax, [rbx+130h]
0x18005efa3  cmp     eax, r14d
0x18005efa6  jnz     short loc_18005EFE1
0x18005efa8  lea     rcx, aReasonInvalidc; "reason::invalidClientId"
0x18005efaf  mov     al, 72h ; 'r'
0x18005efb1  mov     rdx, rcx
0x18005efb4  add     rcx, rdi
0x18005efb7  cmp     al, 3Ah ; ':'
0x18005efb9  jnz     short loc_18005EFBE
0x18005efbb  mov     rdx, rcx
0x18005efbe  mov     al, [rcx]
0x18005efc0  test    al, al
0x18005efc2  jnz     short loc_18005EFB4
0x18005efc4  mov     rax, [rbx+8]
0x18005efc8  cmp     [rax+98h], bpl
0x18005efcf  jnz     loc_18005F2F4
0x18005efd5  mov     [rax+98h], r15b
0x18005efdc  jmp     loc_18005ED96
0x18005efe1  cmp     eax, r15d
0x18005efe4  jnz     short loc_18005F01F
0x18005efe6  lea     rcx, aReasonMutexcre; "reason::mutexCreationFailed"
0x18005efed  mov     al, 72h ; 'r'
0x18005efef  mov     rdx, rcx
0x18005eff2  add     rcx, rdi
0x18005eff5  cmp     al, 3Ah ; ':'
0x18005eff7  jnz     short loc_18005EFFC
0x18005eff9  mov     rdx, rcx
0x18005effc  mov     al, [rcx]
0x18005effe  test    al, al
0x18005f000  jnz     short loc_18005EFF2
0x18005f002  mov     rax, [rbx+8]
0x18005f006  cmp     [rax+98h], bpl
0x18005f00d  jnz     loc_18005F2F4
0x18005f013  mov     [rax+98h], r15b
0x18005f01a  jmp     loc_18005EDDC
0x18005f01f  cmp     eax, esi
0x18005f021  jnz     short loc_18005F05C
0x18005f023  lea     rcx, aReasonMutexacq; "reason::mutexAcquisitionFailed"
0x18005f02a  mov     al, 72h ; 'r'
0x18005f02c  mov     rdx, rcx
0x18005f02f  add     rcx, rdi
0x18005f032  cmp     al, 3Ah ; ':'
0x18005f034  jnz     short loc_18005F039
0x18005f036  mov     rdx, rcx
0x18005f039  mov     al, [rcx]
0x18005f03b  test    al, al
0x18005f03d  jnz     short loc_18005F02F
0x18005f03f  mov     rax, [rbx+8]
0x18005f043  cmp     [rax+98h], bpl
0x18005f04a  jnz     loc_18005F2F4
0x18005f050  mov     [rax+98h], r15b
0x18005f057  jmp     loc_18005EE21
0x18005f05c  cmp     eax, r13d
0x18005f05f  jnz     short loc_18005F09A
0x18005f061  lea     rcx, aReasonWnpendpo; "reason::wnpEndpointRegistrationFailed"
0x18005f068  mov     al, 72h ; 'r'
0x18005f06a  mov     rdx, rcx
0x18005f06d  add     rcx, rdi
0x18005f070  cmp     al, 3Ah ; ':'
0x18005f072  jnz     short loc_18005F077
0x18005f074  mov     rdx, rcx
0x18005f077  mov     al, [rcx]
0x18005f079  test    al, al
0x18005f07b  jnz     short loc_18005F06D
0x18005f07d  mov     rax, [rbx+8]
0x18005f081  cmp     [rax+98h], bpl
0x18005f088  jnz     loc_18005F2F4
0x18005f08e  mov     [rax+98h], r15b
0x18005f095  jmp     loc_18005EE66
0x18005f09a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests> `wil::Feature<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::GetImpl(void)'::`2'::impl
0x18005f0a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudNotificationsAdditionalTipTests>::__private_IsEnabled(void)
0x18005f0a6  test    al, al
0x18005f0a8  jz      short loc_18005F101
0x18005f0aa  cmp     [rbx+130h], r12d
0x18005f0b1  jnz     short loc_18005F101
0x18005f0b3  cmp     dword ptr [rbx+134h], 80070490h
0x18005f0bd  jnz     short loc_18005F101
0x18005f0bf  lea     rcx, aReasonCreatech_0; "reason::createChannelFailedDueToMismatc"...
0x18005f0c6  mov     al, 72h ; 'r'
0x18005f0c8  mov     rdx, rcx
0x18005f0cb  add     rcx, rdi
0x18005f0ce  cmp     al, 3Ah ; ':'
0x18005f0d0  jnz     short loc_18005F0D5
0x18005f0d2  mov     rdx, rcx
0x18005f0d5  mov     al, [rcx]
0x18005f0d7  test    al, al
0x18005f0d9  jnz     short loc_18005F0CB
0x18005f0db  mov     rax, [rbx+8]
0x18005f0df  cmp     [rax+98h], bpl
0x18005f0e6  jnz     loc_18005F2F4
0x18005f0ec  mov     [rax+98h], r14b
0x18005f0f3  mov     word ptr [rax+9Ah], 0Bh
0x18005f0fc  jmp     loc_18005F2A8
0x18005f101  mov     eax, [rbx+130h]
0x18005f107  cmp     eax, r12d
0x18005f10a  jnz     short loc_18005F145
0x18005f10c  lea     rcx, aReasonWnpchann; "reason::wnpChannelCreationFailed"
0x18005f113  mov     al, 72h ; 'r'
0x18005f115  mov     rdx, rcx
0x18005f118  add     rcx, rdi
0x18005f11b  cmp     al, 3Ah ; ':'
0x18005f11d  jnz     short loc_18005F122
0x18005f11f  mov     rdx, rcx
0x18005f122  mov     al, [rcx]
0x18005f124  test    al, al
0x18005f126  jnz     short loc_18005F118
0x18005f128  mov     rax, [rbx+8]
0x18005f12c  cmp     [rax+98h], bpl
0x18005f133  jnz     loc_18005F2F4
0x18005f139  mov     [rax+98h], r15b
0x18005f140  jmp     loc_18005EEAC
0x18005f145  mov     r8d, 7
0x18005f14b  cmp     eax, r8d
0x18005f14e  jnz     short loc_18005F189
0x18005f150  lea     rcx, aReasonCachedch; "reason::cachedChannelCheckFailed"
0x18005f157  mov     al, 72h ; 'r'
0x18005f159  mov     rdx, rcx
  ... truncated ...
```
