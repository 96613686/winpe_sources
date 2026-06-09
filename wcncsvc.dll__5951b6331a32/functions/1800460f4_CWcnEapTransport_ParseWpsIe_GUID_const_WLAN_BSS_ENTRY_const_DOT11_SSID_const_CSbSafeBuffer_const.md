# CWcnEapTransport::ParseWpsIe(_GUID const *,_WLAN_BSS_ENTRY const *,_DOT11_SSID const *,CSbSafeBuffer const *)

- ea: `0x1800460f4`
- end: `0x1800464dc`
- name: `?ParseWpsIe@CWcnEapTransport@@AEAAJPEBU_GUID@@PEBU_WLAN_BSS_ENTRY@@PEBU_DOT11_SSID@@PEBVCSbSafeBuffer@@@Z`
- size: `1000`
- prototype: `int(CWcnEapTransport *__hidden this, const struct _GUID *, const struct _WLAN_BSS_ENTRY *, const struct _DOT11_SSID *, const struct CSbSafeBuffer *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180046598`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000ebe0`
- `0x18001de10`
- `0x18001de78`
- `0x1800460f4`
- `0x180048c94`
- `0x180053004`
- `0x180056dcf`
- `0x180056de6`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046207`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046207`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046468`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046468`

## pseudocode

```c
__int64 __fastcall CWcnEapTransport::ParseWpsIe(
        CWcnEapTransport *this,
        const struct _GUID *a2,
        const struct _WLAN_BSS_ENTRY *a3,
        const struct _DOT11_SSID *a4,
        const struct CSbSafeBuffer *a5)
{
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  const char *v13; // r9
  int v15; // eax
  struct _RTL_CRITICAL_SECTION *v16; // r15
  int v17; // eax
  CWcnPeer *v18; // rdi
  int v19; // ebx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  CWcnPeer *v23; // rax
  const char *v24; // rax
  __int64 v25; // r10
  const char *v26; // rax
  __int64 v27; // r10
  int updated; // eax
  unsigned int v29; // eax
  __int64 v30; // r10
  CWcnPeer *v31; // [rsp+30h] [rbp-58h] BYREF
  __int128 v32; // [rsp+38h] [rbp-50h] BYREF

  v32 = 0;
  v31 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 64, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 65;
    v13 = "pBssEntry";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v9 + 2), v12, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v13);
    return 2147500035LL;
  }
  if ( !a5 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 66;
    v13 = "pWpsIe";
    goto LABEL_12;
  }
  v15 = *(_DWORD *)a3->dot11Bssid;
  v16 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)g_pWcnService + 7) + 192LL);
  v32 = 0;
  LODWORD(v32) = v15;
  WORD2(v32) = *(_WORD *)&a3->dot11Bssid[4];
  EnterCriticalSection(v16);
  v17 = CWcnPeerCache::GetOrCreatePeer((__int64)v16, &v32, &v31);
  v18 = v31;
  v19 = v17;
  if ( v17 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_43;
    v21 = 67;
    goto LABEL_42;
  }
  v22 = _RTDynamicCast_0(
          *((_QWORD *)v31 + *((unsigned int *)this + 2) + 7),
          0,
          &IWcnTransportPeer `RTTI Type Descriptor',
          &CWcnEapPeer `RTTI Type Descriptor',
          0);
  if ( !v22 )
  {
    v23 = (CWcnPeer *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v23;
    v22 = (__int64)v23;
    if ( !v23 )
    {
      v19 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids,
          "pNewEapPeer");
      goto LABEL_43;
    }
    *((_BYTE *)v23 + 8) = 0;
    *(_QWORD *)v23 = &CWcnEapPeer::`vftable';
    *((_BYTE *)v23 + 68) = 0;
    *((_DWORD *)v23 + 8) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v24 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v25 + 16), 10, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids, v24);
    }
    *(_QWORD *)(v22 + 88) = this;
    *(_QWORD *)(v22 + 16) = v18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v26 = GetIndent(-1);
      WPP_SF_s(*(_QWORD *)(v27 + 16), 11, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids, v26);
    }
    CWcnPeer::SetTransportData(v18, *((_DWORD *)this + 2), (struct IWcnTransportPeer *)v22);
  }
  *(_BYTE *)(v22 + 8) = 1;
  updated = CWcnEapPeer::UpdateSsid((CWcnEapPeer *)v22, a2, a3);
  if ( updated < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids,
      (unsigned int)updated);
  if ( a4
    && a4->uSSIDLength == a3->dot11Ssid.uSSIDLength
    && !memcmp_0(a4->ucSSID, a3->dot11Ssid.ucSSID, a4->uSSIDLength) )
  {
    CWcnPeer::SetTargetedDiscoveryPeerValue(v18, 1);
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, char *, CWcnPeer *, const struct CSbSafeBuffer *, _QWORD))(**((_QWORD **)v18 + 15) + 16LL))(
          *((_QWORD *)v18 + 15),
          (char *)this + 48,
          v18,
          a5,
          0);
  v19 = v17;
  if ( v17 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 70;
LABEL_42:
      WPP_SF_d(v20[2], v21, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, (unsigned int)v17);
    }
  }
LABEL_43:
  LeaveCriticalSection(v16);
  if ( v18 )
    _InterlockedDecrement((volatile signed __int32 *)v18 + 66);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v19 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v29 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v30 + 16), 71, (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v29, v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800460f4  mov     [rsp+arg_18], rbx
0x1800460f9  push    rbp
0x1800460fa  push    rsi
0x1800460fb  push    rdi
0x1800460fc  push    r12
0x1800460fe  push    r13
0x180046100  push    r14
0x180046102  push    r15
0x180046104  sub     rsp, 50h
0x180046108  mov     rax, cs:__security_cookie
0x18004610f  xor     rax, rsp
0x180046112  mov     [rsp+88h+var_40], rax
0x180046117  mov     r12, [rsp+88h+arg_20]
0x18004611f  xorps   xmm0, xmm0
0x180046122  movups  [rsp+88h+var_50], xmm0
0x180046127  mov     r14, r9
0x18004612a  mov     [rsp+88h+var_58], 0
0x180046133  mov     rsi, r8
0x180046136  mov     r13, rdx
0x180046139  mov     rbp, rcx
0x18004613c  mov     r10, cs:WPP_GLOBAL_Control
0x180046143  lea     rax, WPP_GLOBAL_Control
0x18004614a  cmp     r10, rax
0x18004614d  jz      short loc_180046186
0x18004614f  cmp     byte ptr [r10+19h], 6
0x180046154  jb      short loc_180046186
0x180046156  mov     ecx, 1; int
0x18004615b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180046160  mov     rcx, [r10+10h]
0x180046164  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x18004616b  mov     edx, 40h ; '@'
0x180046170  mov     r9, rax
0x180046173  call    WPP_SF_s
0x180046178  mov     r10, cs:WPP_GLOBAL_Control
0x18004617f  lea     rax, WPP_GLOBAL_Control
0x180046186  test    rsi, rsi
0x180046189  jnz     short loc_1800461A3
0x18004618b  cmp     r10, rax
0x18004618e  jz      short loc_1800461D0
0x180046190  cmp     byte ptr [r10+19h], 2
0x180046195  jb      short loc_1800461D0
0x180046197  lea     edx, [rsi+41h]
0x18004619a  lea     r9, aPbssentry; "pBssEntry"
0x1800461a1  jmp     short loc_1800461C0
0x1800461a3  test    r12, r12
0x1800461a6  jnz     short loc_1800461DA
0x1800461a8  cmp     r10, rax
0x1800461ab  jz      short loc_1800461D0
0x1800461ad  cmp     byte ptr [r10+19h], 2
0x1800461b2  jb      short loc_1800461D0
0x1800461b4  lea     edx, [r12+42h]
0x1800461b9  lea     r9, aPwpsie; "pWpsIe"
0x1800461c0  mov     rcx, [r10+10h]
0x1800461c4  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800461cb  call    WPP_SF_s
0x1800461d0  mov     eax, 80004003h
0x1800461d5  jmp     loc_1800464B7
0x1800461da  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x1800461e1  xorps   xmm0, xmm0
0x1800461e4  mov     r15, [rax+38h]
0x1800461e8  mov     eax, [rsi+28h]
0x1800461eb  add     r15, 0C0h
0x1800461f2  movups  [rsp+88h+var_50], xmm0
0x1800461f7  mov     dword ptr [rsp+88h+var_50], eax
0x1800461fb  mov     rcx, r15; lpCriticalSection
0x1800461fe  movzx   eax, word ptr [rsi+2Ch]
0x180046202  mov     word ptr [rsp+88h+var_50+4], ax
0x180046207  call    cs:__imp_EnterCriticalSection
0x18004620d  lea     r8, [rsp+88h+var_58]
0x180046212  mov     rcx, r15
0x180046215  lea     rdx, [rsp+88h+var_50]
0x18004621a  call    ?GetOrCreatePeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z; CWcnPeerCache::GetOrCreatePeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)
0x18004621f  mov     rdi, [rsp+88h+var_58]
0x180046224  mov     ebx, eax
0x180046226  test    eax, eax
0x180046228  jns     short loc_180046255
0x18004622a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046231  lea     r13, WPP_GLOBAL_Control
0x180046238  cmp     rcx, r13
0x18004623b  jz      loc_180046465
0x180046241  cmp     byte ptr [rcx+19h], 2
0x180046245  jb      loc_180046465
0x18004624b  mov     edx, 43h ; 'C'
0x180046250  jmp     loc_180046452
0x180046255  mov     ecx, [rbp+8]
0x180046258  lea     r9, ??_R0?AVCWcnEapPeer@@@8; CWcnEapPeer `RTTI Type Descriptor'
0x18004625f  lea     r8, ??_R0?AVIWcnTransportPeer@@@8; IWcnTransportPeer `RTTI Type Descriptor'
0x180046266  mov     dword ptr [rsp+88h+var_68], 0
0x18004626e  xor     edx, edx
0x180046270  mov     rcx, [rdi+rcx*8+38h]
0x180046275  call    __RTDynamicCast_0
0x18004627a  mov     rbx, rax
0x18004627d  test    rax, rax
0x180046280  jnz     loc_180046350
0x180046286  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004628d  lea     ecx, [rax+60h]; unsigned __int64
0x180046290  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046295  xor     ecx, ecx
0x180046297  mov     [rsp+88h+var_58], rax
0x18004629c  mov     rbx, rax
0x18004629f  test    rax, rax
0x1800462a2  jz      loc_180046399
0x1800462a8  mov     [rax+8], cl
0x1800462ab  lea     rax, ??_7CWcnEapPeer@@6B@; const CWcnEapPeer::`vftable'
0x1800462b2  mov     [rbx], rax
0x1800462b5  mov     [rbx+44h], cl
0x1800462b8  mov     [rbx+20h], ecx
0x1800462bb  test    rbx, rbx
0x1800462be  jz      loc_180046399
0x1800462c4  mov     r10, cs:WPP_GLOBAL_Control
0x1800462cb  lea     rax, WPP_GLOBAL_Control
0x1800462d2  cmp     r10, rax
0x1800462d5  jz      short loc_180046307
0x1800462d7  cmp     byte ptr [r10+19h], 6
0x1800462dc  jb      short loc_180046307
0x1800462de  mov     ecx, 1; int
0x1800462e3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800462e8  mov     rcx, [r10+10h]
0x1800462ec  lea     r8, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids
0x1800462f3  mov     edx, 0Ah
0x1800462f8  mov     r9, rax
0x1800462fb  call    WPP_SF_s
0x180046300  lea     rax, WPP_GLOBAL_Control
0x180046307  mov     [rbx+58h], rbp
0x18004630b  mov     [rbx+10h], rdi
0x18004630f  mov     r10, cs:WPP_GLOBAL_Control
0x180046316  cmp     r10, rax
0x180046319  jz      short loc_180046342
0x18004631b  cmp     byte ptr [r10+19h], 6
0x180046320  jb      short loc_180046342
0x180046322  or      ecx, 0FFFFFFFFh; int
0x180046325  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004632a  mov     rcx, [r10+10h]
0x18004632e  lea     r8, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids
0x180046335  mov     edx, 0Bh
0x18004633a  mov     r9, rax
0x18004633d  call    WPP_SF_s
0x180046342  mov     edx, [rbp+8]; unsigned int
0x180046345  mov     r8, rbx; struct IWcnTransportPeer *
0x180046348  mov     rcx, rdi; this
0x18004634b  call    ?SetTransportData@CWcnPeer@@QEAAXKPEAVIWcnTransportPeer@@@Z; CWcnPeer::SetTransportData(ulong,IWcnTransportPeer *)
0x180046350  mov     r8, rsi; struct _WLAN_BSS_ENTRY *
0x180046353  mov     byte ptr [rbx+8], 1
0x180046357  mov     rdx, r13; struct _GUID *
0x18004635a  mov     rcx, rbx; this
0x18004635d  call    ?UpdateSsid@CWcnEapPeer@@QEAAJPEBU_GUID@@PEBU_WLAN_BSS_ENTRY@@@Z; CWcnEapPeer::UpdateSsid(_GUID const *,_WLAN_BSS_ENTRY const *)
0x180046362  test    eax, eax
0x180046364  jns     short loc_1800463E0
0x180046366  mov     rcx, cs:WPP_GLOBAL_Control
0x18004636d  lea     r13, WPP_GLOBAL_Control
0x180046374  cmp     rcx, r13
0x180046377  jz      short loc_1800463E7
0x180046379  cmp     byte ptr [rcx+19h], 3
0x18004637d  jb      short loc_1800463E7
0x18004637f  mov     rcx, [rcx+10h]
0x180046383  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x18004638a  mov     edx, 45h ; 'E'
0x18004638f  mov     r9d, eax
0x180046392  call    WPP_SF_d
0x180046397  jmp     short loc_1800463E7
0x180046399  mov     ebx, 8007000Eh
0x18004639e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463a5  lea     r13, WPP_GLOBAL_Control
0x1800463ac  cmp     rcx, r13
0x1800463af  jz      loc_180046465
0x1800463b5  cmp     byte ptr [rcx+19h], 2
0x1800463b9  jb      loc_180046465
0x1800463bf  mov     rcx, [rcx+10h]
0x1800463c3  lea     r9, aPneweappeer; "pNewEapPeer"
0x1800463ca  mov     edx, 44h ; 'D'
0x1800463cf  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800463d6  call    WPP_SF_s
0x1800463db  jmp     loc_180046465
0x1800463e0  lea     r13, WPP_GLOBAL_Control
0x1800463e7  test    r14, r14
0x1800463ea  jz      short loc_180046412
0x1800463ec  mov     eax, [r14]
0x1800463ef  cmp     eax, [rsi]
0x1800463f1  jnz     short loc_180046412
0x1800463f3  mov     r8d, eax; Size
0x1800463f6  lea     rdx, [rsi+4]; Buf2
0x1800463fa  lea     rcx, [r14+4]; Buf1
0x1800463fe  call    memcmp_0
0x180046403  test    eax, eax
0x180046405  jnz     short loc_180046412
0x180046407  lea     edx, [rax+1]; int
0x18004640a  mov     rcx, rdi; this
0x18004640d  call    ?SetTargetedDiscoveryPeerValue@CWcnPeer@@QEAAXH@Z; CWcnPeer::SetTargetedDiscoveryPeerValue(int)
0x180046412  mov     rcx, [rdi+78h]
0x180046416  lea     rdx, [rbp+30h]
0x18004641a  mov     r9, r12
0x18004641d  mov     [rsp+88h+var_68], 0
0x180046426  mov     r8, rdi
0x180046429  mov     rax, [rcx]
0x18004642c  mov     rax, [rax+10h]
0x180046430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046435  mov     ebx, eax
0x180046437  test    eax, eax
0x180046439  jns     short loc_180046465
0x18004643b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046442  cmp     rcx, r13
0x180046445  jz      short loc_180046465
0x180046447  cmp     byte ptr [rcx+19h], 2
0x18004644b  jb      short loc_180046465
0x18004644d  mov     edx, 46h ; 'F'
0x180046452  mov     rcx, [rcx+10h]
0x180046456  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x18004645d  mov     r9d, eax
0x180046460  call    WPP_SF_d
0x180046465  mov     rcx, r15; lpCriticalSection
0x180046468  call    cs:__imp_LeaveCriticalSection
0x18004646e  test    rdi, rdi
0x180046471  jz      short loc_18004647A
0x180046473  lock dec dword ptr [rdi+108h]
0x18004647a  mov     r10, cs:WPP_GLOBAL_Control
0x180046481  cmp     r10, r13
0x180046484  jz      short loc_1800464B5
0x180046486  test    ebx, ebx
0x180046488  js      short loc_180046491
0x18004648a  cmp     byte ptr [r10+19h], 6
0x18004648f  jb      short loc_1800464B5
0x180046491  or      ecx, 0FFFFFFFFh; int
0x180046494  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180046499  mov     rcx, [r10+10h]
0x18004649d  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800464a4  mov     edx, 47h ; 'G'
0x1800464a9  mov     dword ptr [rsp+88h+var_68], ebx
0x1800464ad  mov     r9, rax
0x1800464b0  call    WPP_SF_sd
0x1800464b5  mov     eax, ebx
0x1800464b7  mov     rcx, [rsp+88h+var_40]
0x1800464bc  xor     rcx, rsp; StackCookie
0x1800464bf  call    __security_check_cookie
0x1800464c4  mov     rbx, [rsp+88h+arg_18]
0x1800464cc  add     rsp, 50h
0x1800464d0  pop     r15
0x1800464d2  pop     r14
0x1800464d4  pop     r13
0x1800464d6  pop     r12
0x1800464d8  pop     rdi
0x1800464d9  pop     rsi
0x1800464da  pop     rbp
0x1800464db  retn
```
