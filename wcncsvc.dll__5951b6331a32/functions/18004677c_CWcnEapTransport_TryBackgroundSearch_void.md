# CWcnEapTransport::TryBackgroundSearch(void)

- ea: `0x18004677c`
- end: `0x180046912`
- name: `?TryBackgroundSearch@CWcnEapTransport@@AEAAXXZ`
- size: `406`
- prototype: `void __fastcall(CWcnEapTransport *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180046920`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x18000fab8`
- `0x1800450c4`
- `0x1800454a0`
- `0x18004677c`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046890`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046890`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046858`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046858`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800468b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800468b0`
- `wlanapi!WlanFreeMemory` at `0x1800468c9`
- `wlanapi!WlanFreeMemory` at `0x1800468c9`

## pseudocode

```c
void __fastcall CWcnEapTransport::TryBackgroundSearch(CWcnEapTransport *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  int v4; // eax
  __int64 v5; // rdi
  struct _TP_TIMER *v6; // rcx
  const char *v7; // rax
  __int64 v8; // r10
  PVOID pMemory; // [rsp+38h] [rbp+10h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF

  pMemory = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 53, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
  }
  v4 = CWcnEapTransport::EnumWlanInterfaces(this, (PWLAN_INTERFACE_INFO_LIST *)&pMemory);
  if ( v4 >= 0 )
  {
    if ( *(_DWORD *)pMemory )
    {
      v5 = *((_QWORD *)this + 34);
      if ( v5 && GetTickCount64() <= v5 + 300000 )
      {
        CWcnEapTransport::DoDiscoveryInternalWithList(this, (const struct _WLAN_INTERFACE_INFO_LIST *)pMemory, 0, 0);
        pftDueTime = (struct _FILETIME)-400000000LL;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
        v6 = (struct _TP_TIMER *)*((_QWORD *)this + 22);
        if ( v6 )
          SetThreadpoolTimer(v6, &pftDueTime, 0, 0x1388u);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
      }
    }
    else
    {
      CWcnPeerCache::WalkListOfPeers(
        (LPCRITICAL_SECTION)(*((_QWORD *)g_pWcnService + 7) + 192LL),
        (void (*)(void *, const struct _GUID *, struct CWcnPeer *))CWcnEapTransport::TurnOffEapTransportInformationOnPeer,
        0,
        1);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, (unsigned int)v4);
  }
  if ( pMemory )
    WlanFreeMemory(pMemory);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v7 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 55, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v7);
  }
}

```

## disassembly

```asm
0x18004677c  mov     [rsp+arg_0], rbx
0x180046781  mov     [rsp+arg_18], rsi
0x180046786  push    rdi
0x180046787  sub     rsp, 20h
0x18004678b  mov     rbx, rcx
0x18004678e  mov     [rsp+28h+pMemory], 0
0x180046797  mov     r10, cs:WPP_GLOBAL_Control
0x18004679e  lea     rsi, WPP_GLOBAL_Control
0x1800467a5  cmp     r10, rsi
0x1800467a8  jz      short loc_1800467D3
0x1800467aa  cmp     byte ptr [r10+19h], 6
0x1800467af  jb      short loc_1800467D3
0x1800467b1  mov     ecx, 1; int
0x1800467b6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800467bb  mov     rcx, [r10+10h]
0x1800467bf  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800467c6  mov     edx, 35h ; '5'
0x1800467cb  mov     r9, rax
0x1800467ce  call    WPP_SF_s
0x1800467d3  lea     rdx, [rsp+28h+pMemory]; ppInterfaceList
0x1800467d8  mov     rcx, rbx; pCallbackContext
0x1800467db  call    ?EnumWlanInterfaces@CWcnEapTransport@@AEAAJPEAPEAU_WLAN_INTERFACE_INFO_LIST@@@Z; CWcnEapTransport::EnumWlanInterfaces(_WLAN_INTERFACE_INFO_LIST * *)
0x1800467e0  test    eax, eax
0x1800467e2  jns     short loc_18004681C
0x1800467e4  mov     r10, cs:WPP_GLOBAL_Control
0x1800467eb  cmp     r10, rsi
0x1800467ee  jz      loc_1800468BF
0x1800467f4  cmp     byte ptr [r10+19h], 2
0x1800467f9  jb      loc_1800468BF
0x1800467ff  mov     rcx, [r10+10h]
0x180046803  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x18004680a  mov     edx, 36h ; '6'
0x18004680f  mov     r9d, eax
0x180046812  call    WPP_SF_d
0x180046817  jmp     loc_1800468BF
0x18004681c  mov     rax, [rsp+28h+pMemory]
0x180046821  cmp     dword ptr [rax], 0
0x180046824  jnz     short loc_18004684C
0x180046826  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18004682d  lea     rdx, ?TurnOffEapTransportInformationOnPeer@CWcnEapTransport@@CAXPEAXPEBU_GUID@@PEAVCWcnPeer@@@Z; void (*)(void *, const struct _GUID *, struct CWcnPeer *)
0x180046834  mov     r9b, 1; bool
0x180046837  xor     r8d, r8d; void *
0x18004683a  mov     rcx, [rax+38h]
0x18004683e  add     rcx, 0C0h; lpCriticalSection
0x180046845  call    ?WalkListOfPeers@CWcnPeerCache@@QEAAXP6AXPEAXPEBU_GUID@@PEAVCWcnPeer@@@Z0_N@Z; CWcnPeerCache::WalkListOfPeers(void (*)(void *,_GUID const *,CWcnPeer *),void *,bool)
0x18004684a  jmp     short loc_1800468BF
0x18004684c  mov     rdi, [rbx+110h]
0x180046853  test    rdi, rdi
0x180046856  jz      short loc_1800468BF
0x180046858  call    cs:__imp_GetTickCount64
0x18004685e  lea     rcx, [rdi+493E0h]
0x180046865  cmp     rax, rcx
0x180046868  ja      short loc_1800468BF
0x18004686a  mov     rdx, [rsp+28h+pMemory]; struct _WLAN_INTERFACE_INFO_LIST *
0x18004686f  xor     r9d, r9d; bool
0x180046872  xor     r8d, r8d; struct _DOT11_SSID *
0x180046875  mov     rcx, rbx; this
0x180046878  call    ?DoDiscoveryInternalWithList@CWcnEapTransport@@AEAAXPEBU_WLAN_INTERFACE_INFO_LIST@@PEBU_DOT11_SSID@@_N@Z; CWcnEapTransport::DoDiscoveryInternalWithList(_WLAN_INTERFACE_INFO_LIST const *,_DOT11_SSID const *,bool)
0x18004687d  lea     rdi, [rbx+0B8h]
0x180046884  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFE8287C00h
0x18004688d  mov     rcx, rdi; lpCriticalSection
0x180046890  call    cs:__imp_EnterCriticalSection
0x180046896  mov     rcx, [rbx+0B0h]; pti
0x18004689d  test    rcx, rcx
0x1800468a0  jz      short loc_1800468B6
0x1800468a2  mov     r9d, 1388h; msWindowLength
0x1800468a8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800468ad  xor     r8d, r8d; msPeriod
0x1800468b0  call    cs:__imp_SetThreadpoolTimer
0x1800468b6  mov     rcx, rdi; lpCriticalSection
0x1800468b9  call    cs:__imp_LeaveCriticalSection
0x1800468bf  mov     rcx, [rsp+28h+pMemory]; pMemory
0x1800468c4  test    rcx, rcx
0x1800468c7  jz      short loc_1800468CF
0x1800468c9  call    cs:__imp_WlanFreeMemory
0x1800468cf  mov     r10, cs:WPP_GLOBAL_Control
0x1800468d6  cmp     r10, rsi
0x1800468d9  jz      short loc_180046902
0x1800468db  cmp     byte ptr [r10+19h], 6
0x1800468e0  jb      short loc_180046902
0x1800468e2  or      ecx, 0FFFFFFFFh; int
0x1800468e5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800468ea  mov     rcx, [r10+10h]
0x1800468ee  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800468f5  mov     edx, 37h ; '7'
0x1800468fa  mov     r9, rax
0x1800468fd  call    WPP_SF_s
0x180046902  mov     rbx, [rsp+28h+arg_0]
0x180046907  mov     rsi, [rsp+28h+arg_18]
0x18004690c  add     rsp, 20h
0x180046910  pop     rdi
0x180046911  retn
```
