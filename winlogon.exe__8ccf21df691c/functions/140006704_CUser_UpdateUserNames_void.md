# CUser::UpdateUserNames(void)

- ea: `0x140006704`
- end: `0x14000695f`
- name: `?UpdateUserNames@CUser@@AEAAKXZ`
- size: `603`
- prototype: `unsigned int __fastcall(CUser *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000b73c`
- `0x140081d40`

## callees

- `0x1400057f4`
- `0x140006704`
- `0x140006970`
- `0x1400069d8`
- `0x140006a5c`
- `0x140006b30`
- `0x140006bb8`
- `0x14004f03c`
- `0x140053720`
- `0x1400544e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000688a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000688a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000677b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400067ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000677b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400067ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006809`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006771`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400067a2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006771`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400067a2`
- `SspiCli!GetUserNameExW` at `0x1400067ff`
- `SspiCli!GetUserNameExW` at `0x1400067ff`

## pseudocode

```c
__int64 __fastcall CUser::UpdateUserNames(CUser *this)
{
  void *v2; // rbx
  DWORD LastError; // eax
  DWORD v4; // ebx
  CUser *v5; // rcx
  __int64 v6; // rdx
  DWORD v7; // eax
  CUser *v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // rax
  WCHAR *v11; // rdi
  WCHAR *v12; // rbx
  unsigned __int16 *FriendlyName; // rax
  ULONG nSize[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR NameBuffer[280]; // [rsp+30h] [rbp-258h] BYREF

  memset_0(NameBuffer, 0, 0x222u);
  v2 = (void *)*((_QWORD *)this + 17);
  nSize[0] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    if ( ImpersonateLoggedOnUser(v2) )
      goto LABEL_14;
    LastError = GetLastError();
    v4 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v6 = 27;
    goto LABEL_12;
  }
  if ( ImpersonateLoggedOnUser(v2) )
    goto LABEL_14;
  LastError = GetLastError();
  v4 = LastError;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 25;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
  }
LABEL_13:
  if ( !v4 )
  {
LABEL_14:
    nSize[0] = 273;
    if ( GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
    {
      v7 = CUser::SetSamCompatibleUserName(this, NameBuffer);
      v4 = v7;
      if ( v7 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v9 = 13;
      }
      else
      {
        v10 = wcschr(NameBuffer, 0x5Cu);
        if ( v10 )
        {
          v11 = NameBuffer;
          *v10 = 0;
          v12 = v10 + 1;
        }
        else
        {
          v12 = NameBuffer;
          v11 = (WCHAR *)&pPassword;
        }
        FriendlyName = GetFriendlyName();
        if ( FriendlyName )
          *((_QWORD *)this + 14) = FriendlyName;
        v7 = CUser::SetUserName(this, v12);
        v4 = v7;
        if ( v7 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_40;
          }
          v9 = 14;
        }
        else
        {
          v7 = CUser::SetDomainName(this, v11);
          v4 = v7;
          if ( !v7 )
            goto LABEL_40;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_40;
          }
          v9 = 15;
        }
      }
    }
    else
    {
      v7 = GetLastError();
      v4 = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v9 = 12;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v7);
LABEL_40:
    CUser::StopImpersonating(v8);
  }
  return v4;
}

```

## disassembly

```asm
0x140006704  mov     [rsp+arg_8], rbx
0x140006709  mov     [rsp+arg_10], rsi
0x14000670e  push    rdi
0x14000670f  push    r12
0x140006711  push    r15
0x140006713  sub     rsp, 270h
0x14000671a  mov     rax, cs:__security_cookie
0x140006721  xor     rax, rsp
0x140006724  mov     [rsp+288h+var_28], rax
0x14000672c  mov     rsi, rcx
0x14000672f  xor     edx, edx; Val
0x140006731  lea     rcx, [rsp+288h+NameBuffer]; void *
0x140006736  mov     r8d, 222h; Size
0x14000673c  call    memset_0
0x140006741  mov     rbx, [rsi+88h]
0x140006748  mov     [rsp+288h+nSize], 0
0x140006750  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x140006757  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000675c  lea     r15, WPP_GLOBAL_Control
0x140006763  mov     rcx, rbx; hToken
0x140006766  lea     r12, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000676d  test    al, al
0x14000676f  jz      short loc_1400067A2
0x140006771  call    cs:__imp_ImpersonateLoggedOnUser
0x140006777  test    eax, eax
0x140006779  jnz     short loc_1400067E8
0x14000677b  call    cs:__imp_GetLastError
0x140006781  mov     ebx, eax
0x140006783  mov     rcx, cs:WPP_GLOBAL_Control
0x14000678a  cmp     rcx, r15
0x14000678d  jz      short loc_1400067E0
0x14000678f  test    byte ptr [rcx+1Ch], 20h
0x140006793  jz      short loc_1400067E0
0x140006795  cmp     byte ptr [rcx+19h], 2
0x140006799  jb      short loc_1400067E0
0x14000679b  mov     edx, 19h
0x1400067a0  jmp     short loc_1400067D1
0x1400067a2  call    cs:__imp_ImpersonateLoggedOnUser
0x1400067a8  test    eax, eax
0x1400067aa  jnz     short loc_1400067E8
0x1400067ac  call    cs:__imp_GetLastError
0x1400067b2  mov     ebx, eax
0x1400067b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067bb  cmp     rcx, r15
0x1400067be  jz      short loc_1400067E0
0x1400067c0  test    byte ptr [rcx+1Ch], 20h
0x1400067c4  jz      short loc_1400067E0
0x1400067c6  cmp     byte ptr [rcx+19h], 2
0x1400067ca  jb      short loc_1400067E0
0x1400067cc  mov     edx, 1Bh
0x1400067d1  mov     rcx, [rcx+10h]
0x1400067d5  mov     r9d, eax
0x1400067d8  mov     r8, r12
0x1400067db  call    WPP_SF_d
0x1400067e0  test    ebx, ebx
0x1400067e2  jnz     loc_140006934
0x1400067e8  lea     r8, [rsp+288h+nSize]; nSize
0x1400067ed  mov     [rsp+288h+nSize], 111h
0x1400067f5  lea     rdx, [rsp+288h+NameBuffer]; lpNameBuffer
0x1400067fa  mov     ecx, 2; NameFormat
0x1400067ff  call    cs:__imp_GetUserNameExW
0x140006805  test    al, al
0x140006807  jnz     short loc_14000683F
0x140006809  call    cs:__imp_GetLastError
0x14000680f  mov     ebx, eax
0x140006811  mov     rcx, cs:WPP_GLOBAL_Control
0x140006818  cmp     rcx, r15
0x14000681b  jz      loc_14000692F
0x140006821  test    byte ptr [rcx+1Ch], 20h
0x140006825  jz      loc_14000692F
0x14000682b  cmp     byte ptr [rcx+19h], 2
0x14000682f  jb      loc_14000692F
0x140006835  mov     edx, 0Ch
0x14000683a  jmp     loc_140006920
0x14000683f  lea     rdx, [rsp+288h+NameBuffer]; unsigned __int16 *
0x140006844  mov     rcx, rsi; this
0x140006847  call    ?SetSamCompatibleUserName@CUser@@QEAAKPEBG@Z; CUser::SetSamCompatibleUserName(ushort const *)
0x14000684c  mov     ebx, eax
0x14000684e  test    eax, eax
0x140006850  jz      short loc_140006880
0x140006852  mov     rcx, cs:WPP_GLOBAL_Control
0x140006859  cmp     rcx, r15
0x14000685c  jz      loc_14000692F
0x140006862  test    byte ptr [rcx+1Ch], 20h
0x140006866  jz      loc_14000692F
0x14000686c  cmp     byte ptr [rcx+19h], 2
0x140006870  jb      loc_14000692F
0x140006876  mov     edx, 0Dh
0x14000687b  jmp     loc_140006920
0x140006880  mov     edx, 5Ch ; '\'; Ch
0x140006885  lea     rcx, [rsp+288h+NameBuffer]; Str
0x14000688a  call    cs:__imp_wcschr
0x140006890  mov     rbx, rax
0x140006893  test    rax, rax
0x140006896  jz      short loc_1400068A8
0x140006898  xor     ecx, ecx
0x14000689a  lea     rdi, [rsp+288h+NameBuffer]
0x14000689f  mov     [rax], cx
0x1400068a2  add     rbx, 2
0x1400068a6  jmp     short loc_1400068B4
0x1400068a8  lea     rbx, [rsp+288h+NameBuffer]
0x1400068ad  lea     rdi, pPassword
0x1400068b4  call    ?GetFriendlyName@@YAPEAGXZ; GetFriendlyName(void)
0x1400068b9  test    rax, rax
0x1400068bc  jz      short loc_1400068C2
0x1400068be  mov     [rsi+70h], rax
0x1400068c2  mov     rdx, rbx; unsigned __int16 *
0x1400068c5  mov     rcx, rsi; this
0x1400068c8  call    ?SetUserName@CUser@@QEAAKPEBG@Z; CUser::SetUserName(ushort const *)
0x1400068cd  mov     ebx, eax
0x1400068cf  test    eax, eax
0x1400068d1  jz      short loc_1400068F2
0x1400068d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068da  cmp     rcx, r15
0x1400068dd  jz      short loc_14000692F
0x1400068df  test    byte ptr [rcx+1Ch], 20h
0x1400068e3  jz      short loc_14000692F
0x1400068e5  cmp     byte ptr [rcx+19h], 2
0x1400068e9  jb      short loc_14000692F
0x1400068eb  mov     edx, 0Eh
0x1400068f0  jmp     short loc_140006920
0x1400068f2  mov     rdx, rdi; unsigned __int16 *
0x1400068f5  mov     rcx, rsi; this
0x1400068f8  call    ?SetDomainName@CUser@@QEAAKPEBG@Z; CUser::SetDomainName(ushort const *)
0x1400068fd  mov     ebx, eax
0x1400068ff  test    eax, eax
0x140006901  jz      short loc_14000692F
0x140006903  mov     rcx, cs:WPP_GLOBAL_Control
0x14000690a  cmp     rcx, r15
0x14000690d  jz      short loc_14000692F
0x14000690f  test    byte ptr [rcx+1Ch], 20h
0x140006913  jz      short loc_14000692F
0x140006915  cmp     byte ptr [rcx+19h], 2
0x140006919  jb      short loc_14000692F
0x14000691b  mov     edx, 0Fh
0x140006920  mov     rcx, [rcx+10h]
0x140006924  mov     r9d, eax
0x140006927  mov     r8, r12
0x14000692a  call    WPP_SF_d
0x14000692f  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x140006934  mov     eax, ebx
0x140006936  mov     rcx, [rsp+288h+var_28]
0x14000693e  xor     rcx, rsp; StackCookie
0x140006941  call    __security_check_cookie
0x140006946  lea     r11, [rsp+288h+var_18]
0x14000694e  mov     rbx, [r11+28h]
0x140006952  mov     rsi, [r11+30h]
0x140006956  mov     rsp, r11
0x140006959  pop     r15
0x14000695b  pop     r12
0x14000695d  pop     rdi
0x14000695e  retn
```
