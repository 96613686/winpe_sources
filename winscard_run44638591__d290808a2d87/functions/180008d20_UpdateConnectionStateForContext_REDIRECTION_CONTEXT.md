# UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)

- ea: `0x180008d20`
- end: `0x180008f10`
- name: `?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `496`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `6`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180006400`
- `0x180007940`
- `0x180007ec0`
- `0x180007f40`
- `0x1800176a0`
- `0x180021150`

## callees

- `0x180007bc0`
- `0x180008d20`
- `0x180017c48`
- `0x180019644`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008df1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008df1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008efa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008efa`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180008e15`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180008e15`
- `WTSAPI32!WTSFreeMemory` at `0x180008e84`
- `WTSAPI32!WTSFreeMemory` at `0x180008e84`

## pseudocode

```c
void __fastcall UpdateConnectionStateForContext(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rcx
  DWORD SpinCount; // edx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  char v7; // di
  __int64 v8; // rcx
  DWORD pBytesReturned; // [rsp+40h] [rbp+8h] BYREF
  LPWSTR ppBuffer; // [rsp+48h] [rbp+10h] BYREF

  ppBuffer = 0;
  pBytesReturned = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
    EnterCriticalSection(lpCriticalSection);
  SpinCount = lpCriticalSection[1].SpinCount;
  if ( !SpinCount )
  {
    WppTraceIndent(v2, 2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_15;
    }
    v5 = 10;
LABEL_14:
    WPP_SF_s(v4[2], v5, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids);
LABEL_15:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      EnterCriticalSection(lpCriticalSection);
    BYTE2(lpCriticalSection[1].DebugInfo) = 1;
    goto LABEL_32;
  }
  if ( g_bDisconnectedLocalSessionsAreAllowed && BYTE1(lpCriticalSection[1].DebugInfo) )
  {
    WppTraceIndent(v2, 2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_15;
    }
    v5 = 11;
    goto LABEL_14;
  }
  if ( WTSQuerySessionInformationW(0, SpinCount, WTSConnectState, &ppBuffer, &pBytesReturned) )
  {
    v7 = *(_DWORD *)ppBuffer <= 1u;
    WTSFreeMemory(ppBuffer);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      EnterCriticalSection(lpCriticalSection);
    BYTE2(lpCriticalSection[1].DebugInfo) = v7;
    WppTraceIndent(v8, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids,
        (_DWORD)WPP_pszIndent,
        lpCriticalSection[1].SpinCount,
        v7);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      EnterCriticalSection(lpCriticalSection);
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids);
    }
    BYTE2(lpCriticalSection[1].DebugInfo) = 0;
  }
LABEL_32:
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180008d20  mov     rax, rsp
0x180008d23  mov     [rax+18h], rbx
0x180008d27  mov     [rax+20h], rbp
0x180008d2b  push    rdi
0x180008d2c  sub     rsp, 30h
0x180008d30  mov     rbx, rcx
0x180008d33  mov     qword ptr [rax+10h], 0
0x180008d3b  mov     dword ptr [rax+8], 0
0x180008d42  lea     rbp, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180008d49  mov     rcx, rbp
0x180008d4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180008d51  test    al, al
0x180008d53  jnz     short loc_180008D5E
0x180008d55  mov     rcx, rbx; lpCriticalSection
0x180008d58  call    cs:__imp_EnterCriticalSection
0x180008d5e  mov     edx, [rbx+48h]; SessionId
0x180008d61  test    edx, edx
0x180008d63  jnz     short loc_180008D95
0x180008d65  mov     edx, 2
0x180008d6a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d76  lea     rax, WPP_GLOBAL_Control
0x180008d7d  cmp     rcx, rax
0x180008d80  jz      short loc_180008DE2
0x180008d82  test    byte ptr [rcx+1Ch], 4
0x180008d86  jz      short loc_180008DE2
0x180008d88  cmp     byte ptr [rcx+19h], 4
0x180008d8c  jb      short loc_180008DE2
0x180008d8e  mov     edx, 0Ah
0x180008d93  jmp     short loc_180008DD2
0x180008d95  cmp     cs:?g_bDisconnectedLocalSessionsAreAllowed@@3_NA, 0; bool g_bDisconnectedLocalSessionsAreAllowed
0x180008d9c  jz      short loc_180008E00
0x180008d9e  cmp     byte ptr [rbx+29h], 0
0x180008da2  jz      short loc_180008E00
0x180008da4  mov     edx, 2
0x180008da9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180008db5  lea     rax, WPP_GLOBAL_Control
0x180008dbc  cmp     rcx, rax
0x180008dbf  jz      short loc_180008DE2
0x180008dc1  test    byte ptr [rcx+1Ch], 4
0x180008dc5  jz      short loc_180008DE2
0x180008dc7  cmp     byte ptr [rcx+19h], 4
0x180008dcb  jb      short loc_180008DE2
0x180008dcd  mov     edx, 0Bh
0x180008dd2  mov     rcx, [rcx+10h]
0x180008dd6  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180008ddd  call    WPP_SF_s
0x180008de2  mov     rcx, rbp
0x180008de5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180008dea  test    al, al
0x180008dec  jz      short loc_180008DF7
0x180008dee  mov     rcx, rbx; lpCriticalSection
0x180008df1  call    cs:__imp_EnterCriticalSection
0x180008df7  mov     byte ptr [rbx+2Ah], 1
0x180008dfb  jmp     loc_180008EF7
0x180008e00  xor     ecx, ecx; hServer
0x180008e02  lea     rax, [rsp+38h+arg_0]
0x180008e07  lea     r9, [rsp+38h+ppBuffer]; ppBuffer
0x180008e0c  mov     [rsp+38h+pBytesReturned], rax; pBytesReturned
0x180008e11  lea     r8d, [rcx+8]; WTSInfoClass
0x180008e15  call    cs:__imp_WTSQuerySessionInformationW
0x180008e1b  test    eax, eax
0x180008e1d  jnz     short loc_180008E78
0x180008e1f  mov     rcx, rbp
0x180008e22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180008e27  test    al, al
0x180008e29  jz      short loc_180008E34
0x180008e2b  mov     rcx, rbx; lpCriticalSection
0x180008e2e  call    cs:__imp_EnterCriticalSection
0x180008e34  mov     edx, 2
0x180008e39  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e45  lea     rax, WPP_GLOBAL_Control
0x180008e4c  cmp     rcx, rax
0x180008e4f  jz      short loc_180008E72
0x180008e51  test    byte ptr [rcx+1Ch], 4
0x180008e55  jz      short loc_180008E72
0x180008e57  cmp     byte ptr [rcx+19h], 2
0x180008e5b  jb      short loc_180008E72
0x180008e5d  mov     rcx, [rcx+10h]
0x180008e61  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180008e68  mov     edx, 0Ch
0x180008e6d  call    WPP_SF_s
0x180008e72  mov     byte ptr [rbx+2Ah], 0
0x180008e76  jmp     short loc_180008EF7
0x180008e78  mov     rcx, [rsp+38h+ppBuffer]; pMemory
0x180008e7d  cmp     dword ptr [rcx], 1
0x180008e80  setbe   dil
0x180008e84  call    cs:__imp_WTSFreeMemory
0x180008e8a  mov     rcx, rbp
0x180008e8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180008e92  test    al, al
0x180008e94  jz      short loc_180008E9F
0x180008e96  mov     rcx, rbx; lpCriticalSection
0x180008e99  call    cs:__imp_EnterCriticalSection
0x180008e9f  mov     edx, 2
0x180008ea4  mov     [rbx+2Ah], dil
0x180008ea8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eb4  lea     rax, WPP_GLOBAL_Control
0x180008ebb  cmp     rcx, rax
0x180008ebe  jz      short loc_180008EF7
0x180008ec0  test    byte ptr [rcx+1Ch], 4
0x180008ec4  jz      short loc_180008EF7
0x180008ec6  cmp     byte ptr [rcx+19h], 4
0x180008eca  jb      short loc_180008EF7
0x180008ecc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008ed3  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180008eda  mov     rcx, [rcx+10h]
0x180008ede  mov     edx, 0Dh
0x180008ee3  movzx   eax, dil
0x180008ee7  mov     [rsp+38h+var_10], eax
0x180008eeb  mov     eax, [rbx+48h]
0x180008eee  mov     dword ptr [rsp+38h+pBytesReturned], eax
0x180008ef2  call    WPP_SF_sDD
0x180008ef7  mov     rcx, rbx; lpCriticalSection
0x180008efa  call    cs:__imp_LeaveCriticalSection
0x180008f00  mov     rbx, [rsp+38h+arg_10]
0x180008f05  mov     rbp, [rsp+38h+arg_18]
0x180008f0a  add     rsp, 30h
0x180008f0e  pop     rdi
0x180008f0f  retn
```
