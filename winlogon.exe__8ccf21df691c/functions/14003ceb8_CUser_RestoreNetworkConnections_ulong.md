# CUser::RestoreNetworkConnections(ulong)

- ea: `0x14003ceb8`
- end: `0x14003d165`
- name: `?RestoreNetworkConnections@CUser@@QEAAXK@Z`
- size: `685`
- prototype: `void __fastcall(CUser *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017240`

## callees

- `0x1400057f4`
- `0x14003ceb8`
- `0x140041c34`
- `0x14004f03c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003d04c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003d04c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003d10a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003d10a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003cf27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003cfa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003cf27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003cfa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d0f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d0f5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003cf1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003cf98`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003cf1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003cf98`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003d14b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14009e774`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003d14b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14009e774`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x14003d0a8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x14003d0a8`
- `ntdll!NtClose` at `0x14003cf87`
- `ntdll!NtClose` at `0x14003cf87`

## pseudocode

```c
void __fastcall CUser::RestoreNetworkConnections(CUser *this, unsigned int a2)
{
  int v2; // r15d
  HANDLE *v3; // rsi
  DWORD v4; // r14d
  DWORD v5; // edi
  void *v6; // rbx
  DWORD v7; // eax
  CUser *v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  HANDLE EventW; // rax
  DWORD v13; // eax
  DWORD v14; // eax

  v2 = 0;
  v3 = (HANDLE *)((char *)this + 472);
  *((_QWORD *)this + 59) = 0;
  if ( a2 <= 0x1E )
    v4 = 1000 * a2;
  else
    v4 = -1;
  v5 = 0;
  v6 = (void *)*((_QWORD *)this + 17);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    if ( !ImpersonateLoggedOnUser(v6) )
    {
      LastError = GetLastError();
      v5 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
    }
    v8 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  if ( ImpersonateLoggedOnUser(v6) )
  {
LABEL_10:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v7 = GetLastError();
  v5 = v7;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v7);
    goto LABEL_10;
  }
LABEL_18:
  if ( v5 )
  {
    if ( v8 == (CUser *)&WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x1000) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_40;
    v10 = 175;
    v11 = v5;
    goto LABEL_23;
  }
  v2 = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *v3 = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v13 = GetLastError();
    v10 = 176;
    v11 = v13;
    v8 = WPP_GLOBAL_Control;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v8 + 2), v10, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v11);
    goto LABEL_40;
  }
  if ( QueueUserWorkItem(RestoreConnections, v3, 0x100u) )
  {
    if ( WaitForSingleObject(*v3, v4) == 258
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v14);
    }
    CloseHandle(*v3);
    *v3 = 0;
  }
LABEL_40:
  if ( v2 )
    RevertToSelf();
}

```

## disassembly

```asm
0x14003ceb8  mov     [rsp+arg_8], rbx
0x14003cebd  mov     [rsp+arg_10], rsi
0x14003cec2  push    rdi
0x14003cec3  push    r14
0x14003cec5  push    r15
0x14003cec7  sub     rsp, 30h
0x14003cecb  xor     r15d, r15d
0x14003cece  mov     [rsp+48h+var_24], r15d
0x14003ced3  lea     rsi, [rcx+1D8h]
0x14003ceda  mov     [rsi], r15
0x14003cedd  cmp     edx, 1Eh
0x14003cee0  jbe     short loc_14003CEE8
0x14003cee2  or      r14d, 0FFFFFFFFh
0x14003cee6  jmp     short loc_14003CEEF
0x14003cee8  imul    r14d, edx, 3E8h
0x14003ceef  xor     edi, edi
0x14003cef1  mov     [rsp+48h+var_28], edi
0x14003cef5  mov     rbx, [rcx+88h]
0x14003cefc  mov     [rsp+48h+var_20], rbx
0x14003cf01  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14003cf08  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14003cf0d  mov     rcx, rbx; hToken
0x14003cf10  test    al, al
0x14003cf12  jz      loc_14003CF98
0x14003cf18  mov     [rsp+48h+Handle], rdi
0x14003cf1d  call    cs:__imp_ImpersonateLoggedOnUser
0x14003cf23  test    eax, eax
0x14003cf25  jnz     short loc_14003CF6C
0x14003cf27  call    cs:__imp_GetLastError
0x14003cf2d  mov     edi, eax
0x14003cf2f  mov     [rsp+48h+var_28], eax
0x14003cf33  lea     rbx, WPP_GLOBAL_Control
0x14003cf3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf41  cmp     rcx, rbx
0x14003cf44  jz      short loc_14003CF7A
0x14003cf46  test    byte ptr [rcx+1Ch], 20h
0x14003cf4a  jz      short loc_14003CF7A
0x14003cf4c  cmp     byte ptr [rcx+19h], 2
0x14003cf50  jb      short loc_14003CF7A
0x14003cf52  mov     edx, 19h
0x14003cf57  mov     r9d, eax
0x14003cf5a  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003cf61  mov     rcx, [rcx+10h]
0x14003cf65  call    WPP_SF_d
0x14003cf6a  jmp     short loc_14003CF73
0x14003cf6c  lea     rbx, WPP_GLOBAL_Control
0x14003cf73  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf7a  mov     rax, [rsp+48h+Handle]
0x14003cf7f  test    rax, rax
0x14003cf82  jz      short loc_14003CFF5
0x14003cf84  mov     rcx, rax; Handle
0x14003cf87  call    cs:__imp_NtClose
0x14003cf8d  mov     [rsp+48h+Handle], 0
0x14003cf96  jmp     short loc_14003CFEE
0x14003cf98  call    cs:__imp_ImpersonateLoggedOnUser
0x14003cf9e  test    eax, eax
0x14003cfa0  jnz     short loc_14003CFE7
0x14003cfa2  call    cs:__imp_GetLastError
0x14003cfa8  mov     edi, eax
0x14003cfaa  mov     [rsp+48h+var_28], eax
0x14003cfae  lea     rbx, WPP_GLOBAL_Control
0x14003cfb5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfbc  cmp     rcx, rbx
0x14003cfbf  jz      short loc_14003CFF5
0x14003cfc1  test    byte ptr [rcx+1Ch], 20h
0x14003cfc5  jz      short loc_14003CFF5
0x14003cfc7  cmp     byte ptr [rcx+19h], 2
0x14003cfcb  jb      short loc_14003CFF5
0x14003cfcd  mov     edx, 1Bh
0x14003cfd2  mov     r9d, eax
0x14003cfd5  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003cfdc  mov     rcx, [rcx+10h]
0x14003cfe0  call    WPP_SF_d
0x14003cfe5  jmp     short loc_14003CFEE
0x14003cfe7  lea     rbx, WPP_GLOBAL_Control
0x14003cfee  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cff5  test    edi, edi
0x14003cff7  jz      short loc_14003D036
0x14003cff9  cmp     rcx, rbx
0x14003cffc  jz      loc_14003D146
0x14003d002  test    dword ptr [rcx+1Ch], 1000h
0x14003d009  jz      loc_14003D146
0x14003d00f  cmp     byte ptr [rcx+19h], 2
0x14003d013  jb      loc_14003D146
0x14003d019  mov     edx, 0AFh
0x14003d01e  mov     r9d, edi
0x14003d021  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d028  mov     rcx, [rcx+10h]
0x14003d02c  call    WPP_SF_d
0x14003d031  jmp     loc_14003D146
0x14003d036  mov     r15d, 1
0x14003d03c  mov     [rsp+48h+var_24], r15d
0x14003d041  xor     r9d, r9d; lpName
0x14003d044  xor     r8d, r8d; bInitialState
0x14003d047  mov     edx, r15d; bManualReset
0x14003d04a  xor     ecx, ecx; lpEventAttributes
0x14003d04c  call    cs:__imp_CreateEventW
0x14003d052  mov     [rsi], rax
0x14003d055  test    rax, rax
0x14003d058  jnz     short loc_14003D098
0x14003d05a  mov     rax, cs:WPP_GLOBAL_Control
0x14003d061  cmp     rax, rbx
0x14003d064  jz      loc_14003D146
0x14003d06a  test    dword ptr [rax+1Ch], 1000h
0x14003d071  jz      loc_14003D146
0x14003d077  cmp     byte ptr [rax+19h], 2
0x14003d07b  jb      loc_14003D146
0x14003d081  call    cs:__imp_GetLastError
0x14003d087  mov     edx, 0B0h
0x14003d08c  mov     r9d, eax
0x14003d08f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d096  jmp     short loc_14003D021
0x14003d098  mov     r8d, 100h; Flags
0x14003d09e  mov     rdx, rsi; Context
0x14003d0a1  lea     rcx, ?RestoreConnections@@YAKPEAX@Z; Function
0x14003d0a8  call    cs:__imp_QueueUserWorkItem
0x14003d0ae  test    eax, eax
0x14003d0b0  jnz     short loc_14003D104
0x14003d0b2  mov     rax, cs:WPP_GLOBAL_Control
0x14003d0b9  cmp     rax, rbx
0x14003d0bc  jz      short loc_14003D0F2
0x14003d0be  test    dword ptr [rax+1Ch], 1000h
0x14003d0c5  jz      short loc_14003D0F2
0x14003d0c7  cmp     byte ptr [rax+19h], 2
0x14003d0cb  jb      short loc_14003D0F2
0x14003d0cd  call    cs:__imp_GetLastError
0x14003d0d3  mov     edx, 0B1h
0x14003d0d8  mov     r9d, eax
0x14003d0db  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d0e9  mov     rcx, [rcx+10h]
0x14003d0ed  call    WPP_SF_d
0x14003d0f2  mov     rcx, [rsi]; hObject
0x14003d0f5  call    cs:__imp_CloseHandle
0x14003d0fb  mov     qword ptr [rsi], 0
0x14003d102  jmp     short loc_14003D146
0x14003d104  mov     edx, r14d; dwMilliseconds
0x14003d107  mov     rcx, [rsi]; hHandle
0x14003d10a  call    cs:__imp_WaitForSingleObject
0x14003d110  cmp     eax, 102h
0x14003d115  jnz     short loc_14003D146
0x14003d117  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d11e  cmp     rcx, rbx
0x14003d121  jz      short loc_14003D146
0x14003d123  test    dword ptr [rcx+1Ch], 1000h
0x14003d12a  jz      short loc_14003D146
0x14003d12c  cmp     byte ptr [rcx+19h], 4
0x14003d130  jb      short loc_14003D146
0x14003d132  lea     edx, [rax-50h]
0x14003d135  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d13c  mov     rcx, [rcx+10h]
0x14003d140  call    WPP_SF_
0x14003d145  nop
0x14003d146  test    r15d, r15d
0x14003d149  jz      short loc_14003D151
0x14003d14b  call    cs:__imp_RevertToSelf
0x14003d151  mov     rbx, [rsp+48h+arg_8]
0x14003d156  mov     rsi, [rsp+48h+arg_10]
0x14003d15b  add     rsp, 30h
0x14003d15f  pop     r15
0x14003d161  pop     r14
0x14003d163  pop     rdi
0x14003d164  retn
0x14009e765  push    rbp
0x14009e767  sub     rsp, 20h
0x14009e76b  mov     rbp, rdx
0x14009e76e  cmp     dword ptr [rbp+24h], 0
0x14009e772  jz      short loc_14009E77B
0x14009e774  call    cs:__imp_RevertToSelf
0x14009e77a  nop
0x14009e77b  add     rsp, 20h
0x14009e77f  pop     rbp
0x14009e780  retn
```
