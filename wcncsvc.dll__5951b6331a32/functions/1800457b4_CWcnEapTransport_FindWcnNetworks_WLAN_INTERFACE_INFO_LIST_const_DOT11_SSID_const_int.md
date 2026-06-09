# CWcnEapTransport::FindWcnNetworks(_WLAN_INTERFACE_INFO_LIST const *,_DOT11_SSID const *,int)

- ea: `0x1800457b4`
- end: `0x180045952`
- name: `?FindWcnNetworks@CWcnEapTransport@@AEAAXPEBU_WLAN_INTERFACE_INFO_LIST@@PEBU_DOT11_SSID@@H@Z`
- size: `414`
- prototype: `void __fastcall(CWcnEapTransport *this, const struct _WLAN_INTERFACE_INFO_LIST *, struct _DOT11_SSID *, BOOL)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800450c4`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000ce18`
- `0x1800457b4`
- `0x180046598`
- `0x180053004`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x1800458b6`
- `wlanapi!WlanFreeMemory` at `0x1800458b6`
- `wlanapi!WlanGetNetworkBssList` at `0x180045868`
- `wlanapi!WlanGetNetworkBssList` at `0x180045868`

## pseudocode

```c
void __fastcall CWcnEapTransport::FindWcnNetworks(
        CWcnEapTransport *this,
        const struct _WLAN_INTERFACE_INFO_LIST *a2,
        struct _DOT11_SSID *a3,
        BOOL a4)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  DWORD i; // ebx
  void *v12; // rcx
  WLAN_INTERFACE_INFO *v13; // rbp
  PWLAN_BSS_LIST v14; // rdx
  DWORD j; // edi
  unsigned int v16; // eax
  __int64 v17; // r10
  unsigned int v18; // eax
  __int64 v19; // r10
  PWLAN_BSS_LIST ppWlanBssList; // [rsp+98h] [rbp+10h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 56, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  for ( i = 0; i < a2->dwNumberOfItems; ++i )
  {
    v12 = (void *)*((_QWORD *)this + 21);
    ppWlanBssList = 0;
    v13 = &a2->InterfaceInfo[i];
    if ( WlanGetNetworkBssList(v12, &v13->InterfaceGuid, a3, dot11_BSS_type_infrastructure, a4, 0, &ppWlanBssList)
      || (v14 = ppWlanBssList) == 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        continue;
      v16 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_(
        *(_QWORD *)(v17 + 16),
        57,
        (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids,
        v16,
        (__int64)v13);
    }
    else
    {
      for ( j = 0; j < ppWlanBssList->dwNumberOfItems; ++j )
      {
        CWcnEapTransport::ProcessWcnNetwork(this, &v13->InterfaceGuid, &v14->wlanBssEntries[j], a3);
        v14 = ppWlanBssList;
      }
      WlanFreeMemory(v14);
    }
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && v8[25] >= 6u )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 58, (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v18, 0);
  }
}

```

## disassembly

```asm
0x1800457b4  push    rbx
0x1800457b6  push    rbp
0x1800457b7  push    rsi
0x1800457b8  push    rdi
0x1800457b9  push    r12
0x1800457bb  push    r13
0x1800457bd  push    r14
0x1800457bf  push    r15
0x1800457c1  sub     rsp, 48h
0x1800457c5  mov     r12d, r9d
0x1800457c8  mov     r15, r8
0x1800457cb  mov     rsi, rdx
0x1800457ce  mov     r13, rcx
0x1800457d1  mov     r10, cs:WPP_GLOBAL_Control
0x1800457d8  lea     rdi, WPP_GLOBAL_Control
0x1800457df  cmp     r10, rdi
0x1800457e2  jz      short loc_180045814
0x1800457e4  cmp     byte ptr [r10+19h], 6
0x1800457e9  jb      short loc_180045814
0x1800457eb  mov     ecx, 1; int
0x1800457f0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800457f5  mov     rcx, [r10+10h]
0x1800457f9  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x180045800  mov     edx, 38h ; '8'
0x180045805  mov     r9, rax
0x180045808  call    WPP_SF_s
0x18004580d  mov     r10, cs:WPP_GLOBAL_Control
0x180045814  xor     ebx, ebx
0x180045816  cmp     [rsi], ebx
0x180045818  jbe     loc_18004590D
0x18004581e  lea     r14, [rsi+8]
0x180045822  mov     rcx, [r13+0A8h]; hClientHandle
0x180045829  mov     r9d, 1; dot11BssType
0x18004582f  mov     eax, ebx
0x180045831  mov     r8, r15; pDot11Ssid
0x180045834  imul    rbp, rax, 214h
0x18004583b  lea     rax, [rsp+88h+arg_8]
0x180045843  mov     [rsp+88h+arg_8], 0
0x18004584f  mov     [rsp+88h+ppWlanBssList], rax; ppWlanBssList
0x180045854  add     rbp, r14
0x180045857  mov     rdx, rbp; pInterfaceGuid
0x18004585a  mov     [rsp+88h+pReserved], 0; pReserved
0x180045863  mov     [rsp+88h+bSecurityEnabled], r12d; bSecurityEnabled
0x180045868  call    cs:__imp_WlanGetNetworkBssList
0x18004586e  test    eax, eax
0x180045870  jnz     short loc_1800458C5
0x180045872  mov     rdx, [rsp+88h+arg_8]
0x18004587a  test    rdx, rdx
0x18004587d  jz      short loc_1800458C5
0x18004587f  xor     edi, edi
0x180045881  cmp     [rdx+4], edi
0x180045884  jbe     short loc_1800458B3
0x180045886  lea     r8, [rdx+8]
0x18004588a  mov     eax, edi
0x18004588c  imul    rcx, rax, 168h
0x180045893  mov     r9, r15; struct _DOT11_SSID *
0x180045896  mov     rdx, rbp; struct _GUID *
0x180045899  add     r8, rcx; struct _WLAN_BSS_ENTRY *
0x18004589c  mov     rcx, r13; this
0x18004589f  call    ?ProcessWcnNetwork@CWcnEapTransport@@AEAAXPEBU_GUID@@PEBU_WLAN_BSS_ENTRY@@PEBU_DOT11_SSID@@@Z; CWcnEapTransport::ProcessWcnNetwork(_GUID const *,_WLAN_BSS_ENTRY const *,_DOT11_SSID const *)
0x1800458a4  mov     rdx, [rsp+88h+arg_8]
0x1800458ac  inc     edi
0x1800458ae  cmp     edi, [rdx+4]
0x1800458b1  jb      short loc_180045886
0x1800458b3  mov     rcx, rdx; pMemory
0x1800458b6  call    cs:__imp_WlanFreeMemory
0x1800458bc  lea     rdi, WPP_GLOBAL_Control
0x1800458c3  jmp     short loc_1800458FC
0x1800458c5  mov     r10, cs:WPP_GLOBAL_Control
0x1800458cc  cmp     r10, rdi
0x1800458cf  jz      short loc_180045903
0x1800458d1  cmp     byte ptr [r10+19h], 2
0x1800458d6  jb      short loc_180045903
0x1800458d8  xor     ecx, ecx; int
0x1800458da  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800458df  mov     rcx, [r10+10h]
0x1800458e3  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800458ea  mov     edx, 39h ; '9'
0x1800458ef  mov     qword ptr [rsp+88h+bSecurityEnabled], rbp
0x1800458f4  mov     r9, rax
0x1800458f7  call    WPP_SF_s_guid_
0x1800458fc  mov     r10, cs:WPP_GLOBAL_Control
0x180045903  inc     ebx
0x180045905  cmp     ebx, [rsi]
0x180045907  jb      loc_180045822
0x18004590d  cmp     r10, rdi
0x180045910  jz      short loc_180045941
0x180045912  cmp     byte ptr [r10+19h], 6
0x180045917  jb      short loc_180045941
0x180045919  or      ecx, 0FFFFFFFFh; int
0x18004591c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180045921  mov     rcx, [r10+10h]
0x180045925  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x18004592c  mov     edx, 3Ah ; ':'
0x180045931  mov     [rsp+88h+bSecurityEnabled], 0
0x180045939  mov     r9, rax
0x18004593c  call    WPP_SF_sd
0x180045941  add     rsp, 48h
0x180045945  pop     r15
0x180045947  pop     r14
0x180045949  pop     r13
0x18004594b  pop     r12
0x18004594d  pop     rdi
0x18004594e  pop     rsi
0x18004594f  pop     rbp
0x180045950  pop     rbx
0x180045951  retn
```
