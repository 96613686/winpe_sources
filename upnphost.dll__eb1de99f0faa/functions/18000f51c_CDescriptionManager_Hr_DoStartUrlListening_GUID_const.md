# CDescriptionManager::Hr_DoStartUrlListening(_GUID const &)

- ea: `0x18000f51c`
- end: `0x18000f749`
- name: `?Hr_DoStartUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z`
- size: `557`
- prototype: `int(CDescriptionManager *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000f750`

## callees

- `0x18000db4c`
- `0x18000f51c`
- `0x180015d90`
- `0x180016af4`
- `0x180018b40`
- `0x18001ab90`
- `0x1800217f4`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f71b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f724`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f71b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f724`

## string_xrefs

- `0x18000f63e`: `CDescriptionManager::Hr_DoStartUrlListening: Already Listening on specified URL`
- `0x18000f6cb`: `CDescriptionManager::StartURLListening: Already Listening on specified URL`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::Hr_DoStartUrlListening(CDescriptionManager *this, struct _GUID *a2)
{
  void *v2; // rbx
  int ContentURL; // edi
  void *v5; // r8
  int v6; // r9d
  STRSAFE_PCNZWCH v7; // rcx
  void *v9; // [rsp+30h] [rbp-148h] BYREF
  void *Block; // [rsp+38h] [rbp-140h] BYREF
  char v11[256]; // [rsp+40h] [rbp-138h] BYREF

  v2 = 0;
  v9 = 0;
  Block = 0;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  ContentURL = HrGetContentURL(a2, (struct CUString *)&Block);
  if ( ContentURL < 0 )
    goto LABEL_24;
  ContentURL = CUString::HrAssign((CUString *)&v9, L"upnphost/");
  if ( ContentURL < 0
    || (ContentURL = CUString::HrAppend((CUString *)&v9, (const unsigned __int16 *)Block), ContentURL < 0) )
  {
    v2 = v9;
    goto LABEL_24;
  }
  v2 = v9;
  ContentURL = StringCbPrintfA(v11, 0x100u, "%S", (const wchar_t *)v9);
  if ( ContentURL < 0 )
  {
LABEL_24:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    if ( g_pVars )
    {
      ContentURL = BaseHttpListener::StartUrlListening(*(BaseHttpListener **)g_pVars, v11, v5, v6);
      if ( ContentURL == -2147024713 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            (unsigned int)WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
            (unsigned int)"CDescriptionManager::Hr_DoStartUrlListening: Already Listening on specified URL",
            183);
          v7 = WPP_GLOBAL_Control;
        }
        ContentURL = 0;
LABEL_25:
        if ( !ContentURL )
          goto LABEL_29;
LABEL_26:
        if ( v7 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v7[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)v7 + 2), 74, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)ContentURL);
        goto LABEL_29;
      }
    }
    else
    {
      ContentURL = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        goto LABEL_29;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_26;
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
        (unsigned int)"CDescriptionManager::Hr_DoStartUrlListening: g_pVars is null.",
        5);
    }
    goto LABEL_24;
  }
  ContentURL = BaseHttpListener::StartUrlListening(*(BaseHttpListener **)g_pVars, v11, v5, v6);
  if ( ContentURL != -2147024713 )
    goto LABEL_24;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      (unsigned int)WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)"CDescriptionManager::StartURLListening: Already Listening on specified URL",
      183);
  ContentURL = 0;
LABEL_29:
  free(Block);
  free(v2);
  return (unsigned int)ContentURL;
}

```

## disassembly

```asm
0x18000f51c  push    rbx
0x18000f51e  push    rsi
0x18000f51f  push    rdi
0x18000f520  push    r14
0x18000f522  sub     rsp, 158h
0x18000f529  mov     rax, cs:__security_cookie
0x18000f530  xor     rax, rsp
0x18000f533  mov     [rsp+178h+var_38], rax
0x18000f53b  xor     ebx, ebx
0x18000f53d  mov     rdi, rdx
0x18000f540  mov     [rsp+178h+var_148], rbx
0x18000f545  mov     [rsp+178h+Block], rbx
0x18000f54a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f551  lea     rsi, WPP_GLOBAL_Control
0x18000f558  lea     r14, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000f55f  cmp     rcx, rsi
0x18000f562  jz      short loc_18000F579
0x18000f564  test    byte ptr [rcx+1Ch], 40h
0x18000f568  jz      short loc_18000F579
0x18000f56a  mov     rcx, [rcx+10h]
0x18000f56e  lea     edx, [rbx+46h]
0x18000f571  mov     r8, r14
0x18000f574  call    WPP_SF_
0x18000f579  lea     rdx, [rsp+178h+Block]; this
0x18000f57e  mov     rcx, rdi; Uuid
0x18000f581  call    ?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetContentURL(_GUID const &,CUString &)
0x18000f586  mov     edi, eax
0x18000f588  test    eax, eax
0x18000f58a  js      loc_18000F6EC
0x18000f590  lea     rdx, aUpnphost_0; "upnphost/"
0x18000f597  lea     rcx, [rsp+178h+var_148]; this
0x18000f59c  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18000f5a1  mov     edi, eax
0x18000f5a3  test    eax, eax
0x18000f5a5  js      loc_18000F6E7
0x18000f5ab  mov     rdx, [rsp+178h+Block]; unsigned __int16 *
0x18000f5b0  lea     rcx, [rsp+178h+var_148]; this
0x18000f5b5  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000f5ba  mov     edi, eax
0x18000f5bc  test    eax, eax
0x18000f5be  js      loc_18000F6E7
0x18000f5c4  mov     rbx, [rsp+178h+var_148]
0x18000f5c9  lea     r8, aS_0; "%S"
0x18000f5d0  mov     r9, rbx
0x18000f5d3  lea     rcx, [rsp+178h+var_138]; char *
0x18000f5d8  mov     edx, 100h; unsigned __int64
0x18000f5dd  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18000f5e2  mov     edi, eax
0x18000f5e4  test    eax, eax
0x18000f5e6  js      loc_18000F6EC
0x18000f5ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18000f5f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18000f5f8  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x18000f5ff  test    al, al
0x18000f601  jz      loc_18000F69D
0x18000f607  test    rcx, rcx
0x18000f60a  jz      short loc_18000F664
0x18000f60c  mov     rcx, [rcx]; this
0x18000f60f  lea     rdx, [rsp+178h+var_138]; char *
0x18000f614  call    ?StartUrlListening@BaseHttpListener@@QEAAJPEBDPEAXH@Z; BaseHttpListener::StartUrlListening(char const *,void *,int)
0x18000f619  mov     edi, eax
0x18000f61b  mov     eax, 800700B7h
0x18000f620  cmp     edi, eax
0x18000f622  jnz     loc_18000F6EC
0x18000f628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f62f  cmp     rcx, rsi
0x18000f632  jz      short loc_18000F65D
0x18000f634  test    byte ptr [rcx+1Ch], 1
0x18000f638  jz      short loc_18000F65D
0x18000f63a  mov     rcx, [rcx+10h]
0x18000f63e  lea     r9, aCdescriptionma_1; "CDescriptionManager::Hr_DoStartUrlListe"...
0x18000f645  mov     edx, 47h ; 'G'
0x18000f64a  mov     [rsp+178h+var_158], eax
0x18000f64e  mov     r8, r14
0x18000f651  call    WPP_SF_sd
0x18000f656  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f65d  xor     edi, edi
0x18000f65f  jmp     loc_18000F6F3
0x18000f664  mov     edi, 80004005h
0x18000f669  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f670  cmp     rcx, rsi
0x18000f673  jz      loc_18000F716
0x18000f679  test    byte ptr [rcx+1Ch], 1
0x18000f67d  jz      short loc_18000F6F7
0x18000f67f  mov     rcx, [rcx+10h]
0x18000f683  lea     r9, aCdescriptionma_0; "CDescriptionManager::Hr_DoStartUrlListe"...
0x18000f68a  mov     edx, 48h ; 'H'
0x18000f68f  mov     [rsp+178h+var_158], edi
0x18000f693  mov     r8, r14
0x18000f696  call    WPP_SF_sd
0x18000f69b  jmp     short loc_18000F6EC
0x18000f69d  mov     rcx, [rcx]; this
0x18000f6a0  lea     rdx, [rsp+178h+var_138]; char *
0x18000f6a5  call    ?StartUrlListening@BaseHttpListener@@QEAAJPEBDPEAXH@Z; BaseHttpListener::StartUrlListening(char const *,void *,int)
0x18000f6aa  mov     edi, eax
0x18000f6ac  mov     eax, 800700B7h
0x18000f6b1  cmp     edi, eax
0x18000f6b3  jnz     short loc_18000F6EC
0x18000f6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6bc  cmp     rcx, rsi
0x18000f6bf  jz      short loc_18000F6E3
0x18000f6c1  test    byte ptr [rcx+1Ch], 1
0x18000f6c5  jz      short loc_18000F6E3
0x18000f6c7  mov     rcx, [rcx+10h]
0x18000f6cb  lea     r9, aCdescriptionma; "CDescriptionManager::StartURLListening:"...
0x18000f6d2  mov     edx, 49h ; 'I'
0x18000f6d7  mov     [rsp+178h+var_158], eax
0x18000f6db  mov     r8, r14
0x18000f6de  call    WPP_SF_sd
0x18000f6e3  xor     edi, edi
0x18000f6e5  jmp     short loc_18000F716
0x18000f6e7  mov     rbx, [rsp+178h+var_148]
0x18000f6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6f3  test    edi, edi
0x18000f6f5  jz      short loc_18000F716
0x18000f6f7  cmp     rcx, rsi
0x18000f6fa  jz      short loc_18000F716
0x18000f6fc  test    byte ptr [rcx+1Ch], 1
0x18000f700  jz      short loc_18000F716
0x18000f702  mov     rcx, [rcx+10h]
0x18000f706  mov     edx, 4Ah ; 'J'
0x18000f70b  mov     r9d, edi
0x18000f70e  mov     r8, r14
0x18000f711  call    WPP_SF_d
0x18000f716  mov     rcx, [rsp+178h+Block]; Block
0x18000f71b  call    cs:__imp_free
0x18000f721  mov     rcx, rbx; Block
0x18000f724  call    cs:__imp_free
0x18000f72a  mov     eax, edi
0x18000f72c  mov     rcx, [rsp+178h+var_38]
0x18000f734  xor     rcx, rsp; StackCookie
0x18000f737  call    __security_check_cookie
0x18000f73c  add     rsp, 158h
0x18000f743  pop     r14
0x18000f745  pop     rdi
0x18000f746  pop     rsi
0x18000f747  pop     rbx
0x18000f748  retn
```
