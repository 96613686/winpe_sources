# RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)

- ea: `0x1800093e4`
- end: `0x18000947a`
- name: `?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `150`
- prototype: `bool __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `27`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180006400`
- `0x180007f40`
- `0x18000e110`
- `0x18000e980`
- `0x180012e40`
- `0x180016560`
- `0x180017ac0`
- `0x18001a270`
- `0x180024f70`
- `0x180025170`
- `0x180025300`
- `0x180025490`
- `0x1800257b0`
- `0x180025980`
- `0x180025b30`
- `0x180025d30`
- `0x180026190`
- `0x1800262f0`
- `0x180026d80`
- `0x1800272a0`
- `0x1800274a0`
- `0x180027630`
- `0x180027960`
- `0x180027ad0`
- `0x180027c50`
- `0x180028000`
- `0x180028790`

## callees

- `0x18000605c`
- `0x180006c80`
- `0x1800093e4`
- `0x180013d34`
- `0x180017c48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000942f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000942f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009454`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009454`

## pseudocode

```c
char __fastcall RedirectionContextIsLocal(LPCRITICAL_SECTION lpCriticalSection)
{
  char v1; // si
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  char IsEnabled; // al
  char v5; // di
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v6 = lpCriticalSection;
  v2 = lpCriticalSection;
  if ( !lpCriticalSection )
  {
    if ( (unsigned int)RedirectionContextLookup(&v6) )
      return 0;
    v2 = v6;
    v1 = 1;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
    EnterCriticalSection(v2);
  UpdateRedirectionStateForContext(v2);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl);
  v5 = BYTE1(v2[1].DebugInfo);
  if ( !IsEnabled )
    LeaveCriticalSection(v2);
  if ( v1 )
    RedirectionContextRelease((struct _REDIRECTION_CONTEXT *)v2);
  return v5;
}

```

## disassembly

```asm
0x1800093e4  mov     rax, rsp
0x1800093e7  mov     [rax+10h], rbx
0x1800093eb  mov     [rax+18h], rsi
0x1800093ef  push    rdi
0x1800093f0  sub     rsp, 20h
0x1800093f4  xor     sil, sil
0x1800093f7  mov     [rax+8], rcx
0x1800093fb  mov     rbx, rcx
0x1800093fe  test    rcx, rcx
0x180009401  jnz     short loc_18000941C
0x180009403  lea     rcx, [rax+8]; struct _REDIRECTION_CONTEXT **
0x180009407  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x18000940c  test    eax, eax
0x18000940e  jz      short loc_180009414
0x180009410  xor     al, al
0x180009412  jmp     short loc_18000946A
0x180009414  mov     rbx, [rsp+28h+arg_0]
0x180009419  mov     sil, 1
0x18000941c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180009423  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180009428  test    al, al
0x18000942a  jnz     short loc_180009435
0x18000942c  mov     rcx, rbx; lpCriticalSection
0x18000942f  call    cs:__imp_EnterCriticalSection
0x180009435  mov     rcx, rbx; lpCriticalSection
0x180009438  call    ?UpdateRedirectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateRedirectionStateForContext(_REDIRECTION_CONTEXT *)
0x18000943d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180009444  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180009449  mov     dil, [rbx+29h]
0x18000944d  test    al, al
0x18000944f  jnz     short loc_18000945A
0x180009451  mov     rcx, rbx; lpCriticalSection
0x180009454  call    cs:__imp_LeaveCriticalSection
0x18000945a  test    sil, sil
0x18000945d  jz      short loc_180009467
0x18000945f  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180009462  call    ?RedirectionContextRelease@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextRelease(_REDIRECTION_CONTEXT *)
0x180009467  mov     al, dil
0x18000946a  mov     rbx, [rsp+28h+arg_8]
0x18000946f  mov     rsi, [rsp+28h+arg_10]
0x180009474  add     rsp, 20h
0x180009478  pop     rdi
0x180009479  retn
```
