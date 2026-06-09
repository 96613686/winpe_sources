# CDescriptionManager::Hr_DoStartUrlListening(_GUID const &)

- ea: `0x1800373d8`
- end: `0x180037612`
- name: `?Hr_DoStartUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z`
- size: `570`
- prototype: `int(CDescriptionManager *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000c940`

## callees

- `0x18000a060`
- `0x18000ae60`
- `0x18000d058`
- `0x18000f8a0`
- `0x1800200f4`
- `0x1800223c4`
- `0x1800373d8`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18004e098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800375d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800375e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800375d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800375e6`

## string_xrefs

- `0x1800374fa`: `CDescriptionManager::Hr_DoStartUrlListening: Already Listening on specified URL`
- `0x180037587`: `CDescriptionManager::StartURLListening: Already Listening on specified URL`

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
0x1800373d8  push    rbx
0x1800373da  push    rsi
0x1800373db  push    rdi
0x1800373dc  push    r14
0x1800373de  sub     rsp, 158h
0x1800373e5  mov     rax, cs:__security_cookie
0x1800373ec  xor     rax, rsp
0x1800373ef  mov     [rsp+178h+var_38], rax
0x1800373f7  xor     ebx, ebx
0x1800373f9  mov     rdi, rdx
0x1800373fc  mov     [rsp+178h+var_148], rbx
0x180037401  mov     [rsp+178h+Block], rbx
0x180037406  mov     rcx, cs:WPP_GLOBAL_Control
0x18003740d  lea     rsi, WPP_GLOBAL_Control
0x180037414  lea     r14, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18003741b  cmp     rcx, rsi
0x18003741e  jz      short loc_180037435
0x180037420  test    byte ptr [rcx+1Ch], 40h
0x180037424  jz      short loc_180037435
0x180037426  mov     rcx, [rcx+10h]
0x18003742a  lea     edx, [rbx+46h]
0x18003742d  mov     r8, r14
0x180037430  call    WPP_SF_
0x180037435  lea     rdx, [rsp+178h+Block]; this
0x18003743a  mov     rcx, rdi; Uuid
0x18003743d  call    ?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetContentURL(_GUID const &,CUString &)
0x180037442  mov     edi, eax
0x180037444  test    eax, eax
0x180037446  js      loc_1800375A8
0x18003744c  lea     rdx, aUpnphost_0; "upnphost/"
0x180037453  lea     rcx, [rsp+178h+var_148]; this
0x180037458  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18003745d  mov     edi, eax
0x18003745f  test    eax, eax
0x180037461  js      loc_1800375A3
0x180037467  mov     rdx, [rsp+178h+Block]; unsigned __int16 *
0x18003746c  lea     rcx, [rsp+178h+var_148]; this
0x180037471  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180037476  mov     edi, eax
0x180037478  test    eax, eax
0x18003747a  js      loc_1800375A3
0x180037480  mov     rbx, [rsp+178h+var_148]
0x180037485  lea     r8, aS_0; "%S"
0x18003748c  mov     r9, rbx
0x18003748f  lea     rcx, [rsp+178h+var_138]; char *
0x180037494  mov     edx, 100h; unsigned __int64
0x180037499  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18003749e  mov     edi, eax
0x1800374a0  test    eax, eax
0x1800374a2  js      loc_1800375A8
0x1800374a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x1800374af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x1800374b4  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x1800374bb  test    al, al
0x1800374bd  jz      loc_180037559
0x1800374c3  test    rcx, rcx
0x1800374c6  jz      short loc_180037520
0x1800374c8  mov     rcx, [rcx]; this
0x1800374cb  lea     rdx, [rsp+178h+var_138]; char *
0x1800374d0  call    ?StartUrlListening@BaseHttpListener@@QEAAJPEBDPEAXH@Z; BaseHttpListener::StartUrlListening(char const *,void *,int)
0x1800374d5  mov     edi, eax
0x1800374d7  mov     eax, 800700B7h
0x1800374dc  cmp     edi, eax
0x1800374de  jnz     loc_1800375A8
0x1800374e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374eb  cmp     rcx, rsi
0x1800374ee  jz      short loc_180037519
0x1800374f0  test    byte ptr [rcx+1Ch], 1
0x1800374f4  jz      short loc_180037519
0x1800374f6  mov     rcx, [rcx+10h]
0x1800374fa  lea     r9, aCdescriptionma_1; "CDescriptionManager::Hr_DoStartUrlListe"...
0x180037501  mov     edx, 47h ; 'G'
0x180037506  mov     [rsp+178h+var_158], eax
0x18003750a  mov     r8, r14
0x18003750d  call    WPP_SF_sd
0x180037512  mov     rcx, cs:WPP_GLOBAL_Control
0x180037519  xor     edi, edi
0x18003751b  jmp     loc_1800375AF
0x180037520  mov     edi, 80004005h
0x180037525  mov     rcx, cs:WPP_GLOBAL_Control
0x18003752c  cmp     rcx, rsi
0x18003752f  jz      loc_1800375D2
0x180037535  test    byte ptr [rcx+1Ch], 1
0x180037539  jz      short loc_1800375B3
0x18003753b  mov     rcx, [rcx+10h]
0x18003753f  lea     r9, aCdescriptionma_0; "CDescriptionManager::Hr_DoStartUrlListe"...
0x180037546  mov     edx, 48h ; 'H'
0x18003754b  mov     [rsp+178h+var_158], edi
0x18003754f  mov     r8, r14
0x180037552  call    WPP_SF_sd
0x180037557  jmp     short loc_1800375A8
0x180037559  mov     rcx, [rcx]; this
0x18003755c  lea     rdx, [rsp+178h+var_138]; char *
0x180037561  call    ?StartUrlListening@BaseHttpListener@@QEAAJPEBDPEAXH@Z; BaseHttpListener::StartUrlListening(char const *,void *,int)
0x180037566  mov     edi, eax
0x180037568  mov     eax, 800700B7h
0x18003756d  cmp     edi, eax
0x18003756f  jnz     short loc_1800375A8
0x180037571  mov     rcx, cs:WPP_GLOBAL_Control
0x180037578  cmp     rcx, rsi
0x18003757b  jz      short loc_18003759F
0x18003757d  test    byte ptr [rcx+1Ch], 1
0x180037581  jz      short loc_18003759F
0x180037583  mov     rcx, [rcx+10h]
0x180037587  lea     r9, aCdescriptionma; "CDescriptionManager::StartURLListening:"...
0x18003758e  mov     edx, 49h ; 'I'
0x180037593  mov     [rsp+178h+var_158], eax
0x180037597  mov     r8, r14
0x18003759a  call    WPP_SF_sd
0x18003759f  xor     edi, edi
0x1800375a1  jmp     short loc_1800375D2
0x1800375a3  mov     rbx, [rsp+178h+var_148]
0x1800375a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375af  test    edi, edi
0x1800375b1  jz      short loc_1800375D2
0x1800375b3  cmp     rcx, rsi
0x1800375b6  jz      short loc_1800375D2
0x1800375b8  test    byte ptr [rcx+1Ch], 1
0x1800375bc  jz      short loc_1800375D2
0x1800375be  mov     rcx, [rcx+10h]
0x1800375c2  mov     edx, 4Ah ; 'J'
0x1800375c7  mov     r9d, edi
0x1800375ca  mov     r8, r14
0x1800375cd  call    WPP_SF_d
0x1800375d2  mov     rcx, [rsp+178h+Block]; Block
0x1800375d7  call    cs:__imp_free
0x1800375de  nop     dword ptr [rax+rax+00h]
0x1800375e3  mov     rcx, rbx; Block
0x1800375e6  call    cs:__imp_free
0x1800375ed  nop     dword ptr [rax+rax+00h]
0x1800375f2  mov     eax, edi
0x1800375f4  mov     rcx, [rsp+178h+var_38]
0x1800375fc  xor     rcx, rsp; StackCookie
0x1800375ff  call    __security_check_cookie
0x180037604  add     rsp, 158h
0x18003760b  pop     r14
0x18003760d  pop     rdi
0x18003760e  pop     rsi
0x18003760f  pop     rbx
0x180037610  retn
```
