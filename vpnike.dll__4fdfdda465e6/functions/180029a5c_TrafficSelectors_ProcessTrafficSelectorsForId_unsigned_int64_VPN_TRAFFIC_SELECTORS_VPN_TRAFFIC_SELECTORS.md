# TrafficSelectors::ProcessTrafficSelectorsForId(unsigned __int64 *,_VPN_TRAFFIC_SELECTORS_ *,_VPN_TRAFFIC_SELECTORS_ * *)

- ea: `0x180029a5c`
- end: `0x18002a011`
- name: `?ProcessTrafficSelectorsForId@TrafficSelectors@@QEAAKPEA_KPEAU_VPN_TRAFFIC_SELECTORS_@@PEAPEAU2@@Z`
- size: `1461`
- prototype: `__int64 __fastcall(TrafficSelectors *this, unsigned __int64 *, struct _VPN_TRAFFIC_SELECTORS_ *, struct _VPN_TRAFFIC_SELECTORS_ **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002fe0c`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002831c`
- `0x1800284e0`
- `0x180029a5c`
- `0x18002c048`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029fa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029fa0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029da3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029da3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f92`

## string_xrefs

- `0x180029c6f`: `ProcessTrafficSelectorsForId: Update failed for payload [%I64u]`
- `0x180029ee2`: `UpdateVPNTrafficSelectors failed`

## pseudocode

```c
__int64 __fastcall TrafficSelectors::ProcessTrafficSelectorsForId(
        TrafficSelectors *this,
        unsigned __int64 *a2,
        struct _VPN_TRAFFIC_SELECTORS_ *a3,
        struct _VPN_TRAFFIC_SELECTORS_ **a4)
{
  unsigned __int64 *v6; // r13
  PVOID *v8; // rbx
  struct _VPN_TRAFFIC_SELECTORS_ **v9; // r12
  char v10; // al
  __int64 i; // r13
  unsigned __int64 v12; // rbx
  unsigned int *v13; // r9
  __int64 j; // rbx
  HANDLE ProcessHeap; // rax
  struct _VPN_TRAFFIC_SELECTORS_ **v16; // rax
  const wchar_t *v17; // r8
  unsigned int TrafficSelectorsForId; // eax
  HANDLE v19; // rax
  unsigned int v20; // ebx
  int v22; // [rsp+38h] [rbp-C8h]
  unsigned int v23; // [rsp+50h] [rbp-B0h] BYREF
  struct _VPN_TRAFFIC_SELECTORS_ *v24; // [rsp+58h] [rbp-A8h]
  struct _VPN_TRAFFIC_SELECTORS_ **v25; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v26; // [rsp+68h] [rbp-98h]
  unsigned __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v28; // [rsp+78h] [rbp-88h]
  unsigned __int64 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  __int128 v31; // [rsp+90h] [rbp-70h]
  __int128 v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+BCh] [rbp-44h]
  _BYTE v36[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v37; // [rsp+D0h] [rbp-30h] BYREF
  char v38[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v25 = a4;
  v24 = a3;
  v6 = a2;
  v26 = (unsigned __int64)a2;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_51611fa0845035ef13311412203ffa0b_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = 0;
  v9 = 0;
  v37 = 0;
  memset_0(v38, 0, sizeof(v38));
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v34 = -1;
  v35 = 0;
  v10 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"TrafficSelectors::ProcessTrafficSelectorsForId",
      &v23,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v10 = byte_1800AA941;
  }
  if ( !v6 || !a3 || !a4 )
  {
    v23 = 87;
    if ( (v10 & 4) == 0 )
      goto LABEL_56;
    goto LABEL_53;
  }
  if ( !*v6 )
  {
    if ( !TrafficSelectors::GetCurrentTsId(this) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
      {
        v12 = ++*((_QWORD *)this + 1);
        v29 = v12;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v37) = 0;
          FormatRRASErrorString(&v37, L"ProcessTrafficSelectorsForId: Updating for payload [%I64u]", (unsigned int)i);
          if ( (byte_1800AA941 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v37);
        }
        v27 = v12;
        v28 = (unsigned int)i;
        std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::insert(
          (char *)this + 48,
          v36,
          &v27);
        v13 = *(unsigned int **)(*((_QWORD *)this + 2) + 8 * i);
        LOBYTE(v22) = 0;
        if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, _QWORD, unsigned int, _QWORD, int))(**((_QWORD **)this + 5) + 48LL))(
               *((_QWORD *)this + 5),
               *((_QWORD *)this + 4),
               v29,
               *v13,
               *((_QWORD *)v13 + 1),
               v13[4],
               *((_QWORD *)v13 + 3),
               v22)
          && (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v37) = 0;
          FormatRRASErrorString(
            &v37,
            L"ProcessTrafficSelectorsForId: Update failed for payload [%I64u]",
            (unsigned int)i);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v37);
        }
      }
      v6 = (unsigned __int64 *)v26;
    }
    *v6 = ++*((_QWORD *)this + 1);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v37, L"ProcessTrafficSelectorsForId: Generating new TS ID [%I64u]");
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v37);
    }
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 6); j = (unsigned int)(j + 1) )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v37) = 0;
        FormatRRASErrorString(&v37, L"ProcessTrafficSelectorsForId: Matching payload [%I64u]", (unsigned int)j);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v37);
      }
      v26 = (unsigned int)j;
      v23 = (*(__int64 (__fastcall **)(TrafficSelectors *, unsigned __int64 *, __int64, struct _VPN_TRAFFIC_SELECTORS_ *, struct _VPN_TRAFFIC_SELECTORS_ **))(*(_QWORD *)this + 8LL))(
              this,
              v6,
              *((_QWORD *)this + 2) + 8 * j,
              v24,
              v25);
      if ( !v23 )
      {
        v27 = *v6;
        v28 = v26;
        std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::insert(
          (char *)this + 48,
          v36,
          &v27);
        goto LABEL_41;
      }
    }
    goto LABEL_41;
  }
  ProcessHeap = GetProcessHeap();
  v16 = (struct _VPN_TRAFFIC_SELECTORS_ **)HeapAlloc(ProcessHeap, 8u, 8u);
  v9 = v16;
  if ( !v16 )
  {
    v23 = 8;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v37, L"ProcessTrafficSelectorsForId: VPNIKE_MALLOC failed with error %d", 8);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_55;
      v17 = (const wchar_t *)&v37;
      goto LABEL_54;
    }
    goto LABEL_57;
  }
  TrafficSelectorsForId = TrafficSelectors::GetTrafficSelectorsForId(this, v6, v16);
  v23 = TrafficSelectorsForId;
  if ( !*v9 || TrafficSelectorsForId )
  {
    v23 = 87;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_57;
LABEL_53:
    v17 = L"ProcessTrafficSelectorsForId: ERROR_INVALID_PARAMETER";
    goto LABEL_54;
  }
  v23 = (*(__int64 (__fastcall **)(TrafficSelectors *, unsigned __int64 *, struct _VPN_TRAFFIC_SELECTORS_ **, struct _VPN_TRAFFIC_SELECTORS_ *, struct _VPN_TRAFFIC_SELECTORS_ **))(*(_QWORD *)this + 8LL))(
          this,
          v6,
          v9,
          v24,
          v25);
LABEL_41:
  if ( v23 )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_55;
    v17 = L"ProcessTrafficSelectorsForId: Negotiating Traffic Selection failed";
    goto LABEL_54;
  }
  if ( *v25 )
  {
    LOBYTE(v22) = 0;
    v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, _QWORD, _DWORD, _QWORD, int))(**((_QWORD **)this + 5) + 40LL))(
            *((_QWORD *)this + 5),
            *((_QWORD *)this + 4),
            *v6,
            *((unsigned int *)*v25 + 4),
            *((_QWORD *)*v25 + 3),
            *(_DWORD *)*v25,
            *((_QWORD *)*v25 + 1),
            v22);
    if ( !v23 || (byte_1800AA941 & 4) == 0 )
    {
LABEL_55:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( !v23 )
        goto LABEL_58;
LABEL_56:
      if ( !v25 )
        goto LABEL_58;
      goto LABEL_57;
    }
    v17 = L"UpdateVPNTrafficSelectors failed";
LABEL_54:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, v17);
    goto LABEL_55;
  }
  v23 = 8;
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v17 = L"ProcessTrafficSelectorsForId: NarrowTrafficSelectorRequest failed";
    goto LABEL_54;
  }
LABEL_57:
  (*(void (__fastcall **)(TrafficSelectors *, struct _VPN_TRAFFIC_SELECTORS_ *))(*(_QWORD *)this + 24LL))(this, *v25);
  *v25 = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_58:
  if ( v9 )
  {
    if ( *v9 )
    {
      (*(void (__fastcall **)(TrafficSelectors *))(*(_QWORD *)this + 24LL))(this);
      *v9 = 0;
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v9);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 22, WPP_51611fa0845035ef13311412203ffa0b_Traceguids, v23);
  v20 = v23;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
  return v20;
}

```

## disassembly

```asm
0x180029a5c  push    rbp
0x180029a5e  push    rbx
0x180029a5f  push    rsi
0x180029a60  push    rdi
0x180029a61  push    r12
0x180029a63  push    r13
0x180029a65  push    r14
0x180029a67  push    r15
0x180029a69  lea     rbp, [rsp-7E8h]
0x180029a71  sub     rsp, 8E8h
0x180029a78  mov     rax, cs:__security_cookie
0x180029a7f  xor     rax, rsp
0x180029a82  mov     [rbp+820h+var_50], rax
0x180029a89  mov     rsi, r9
0x180029a8c  mov     [rsp+920h+var_8C0], r9
0x180029a91  mov     r14, r8
0x180029a94  mov     [rsp+920h+var_8C8], r8
0x180029a99  mov     r13, rdx
0x180029a9c  mov     [rsp+920h+var_8B8], rdx
0x180029aa1  mov     rdi, rcx
0x180029aa4  lea     rax, WPP_GLOBAL_Control
0x180029aab  mov     rbx, cs:WPP_GLOBAL_Control
0x180029ab2  cmp     rbx, rax
0x180029ab5  jz      short loc_180029ADF
0x180029ab7  test    byte ptr [rbx+1Ch], 1
0x180029abb  jz      short loc_180029ADF
0x180029abd  cmp     byte ptr [rbx+19h], 6
0x180029ac1  jb      short loc_180029ADF
0x180029ac3  mov     edx, 15h
0x180029ac8  lea     r8, WPP_51611fa0845035ef13311412203ffa0b_Traceguids
0x180029acf  mov     rcx, [rbx+10h]
0x180029ad3  call    WPP_SF_
0x180029ad8  mov     rbx, cs:WPP_GLOBAL_Control
0x180029adf  mov     [rsp+920h+var_8D0], 0
0x180029ae7  xor     r12d, r12d
0x180029aea  xor     eax, eax
0x180029aec  mov     [rbp+820h+var_850], eax
0x180029aef  xor     edx, edx; Val
0x180029af1  mov     r8d, 7FCh; Size
0x180029af7  lea     rcx, [rbp+820h+var_84C]; void *
0x180029afb  call    memset_0
0x180029b00  xorps   xmm0, xmm0
0x180029b03  movdqu  [rbp+820h+var_890], xmm0
0x180029b08  mov     [rbp+820h+var_898], r12
0x180029b0c  xorps   xmm1, xmm1
0x180029b0f  movdqu  [rbp+820h+var_880], xmm1
0x180029b14  mov     [rbp+820h+var_870], r12
0x180029b18  mov     [rbp+820h+var_868], 0FFFFFFFFh
0x180029b1f  mov     [rbp+820h+var_864], r12d
0x180029b23  mov     al, cs:byte_1800AA941
0x180029b29  test    al, 8
0x180029b2b  jz      short loc_180029B56
0x180029b2d  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180029b34  lea     r8, [rsp+920h+var_8D0]; unsigned int *
0x180029b39  lea     rdx, aTrafficselecto_6; "TrafficSelectors::ProcessTrafficSelecto"...
0x180029b40  lea     rcx, [rbp+820h+var_898]; this
0x180029b44  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180029b49  mov     rbx, cs:WPP_GLOBAL_Control
0x180029b50  mov     al, cs:byte_1800AA941
0x180029b56  test    r13, r13
0x180029b59  jz      loc_180029F07
0x180029b5f  test    r14, r14
0x180029b62  jz      loc_180029F07
0x180029b68  test    rsi, rsi
0x180029b6b  jz      loc_180029F07
0x180029b71  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180029b78  mov     sil, 4
0x180029b7b  lea     r15, RasVpnIkeTraceError
0x180029b82  cmp     qword ptr [r13+0], 0
0x180029b87  jnz     loc_180029D92
0x180029b8d  mov     rcx, rdi; this
0x180029b90  call    ?GetCurrentTsId@TrafficSelectors@@QEAA_KXZ; TrafficSelectors::GetCurrentTsId(void)
0x180029b95  test    rax, rax
0x180029b98  jnz     loc_180029CA4
0x180029b9e  xor     r13d, r13d
0x180029ba1  cmp     r13d, [rdi+18h]
0x180029ba5  jnb     loc_180029C9F
0x180029bab  inc     qword ptr [rdi+8]
0x180029baf  mov     rbx, [rdi+8]
0x180029bb3  mov     [rbp+820h+var_8A0], rbx
0x180029bb7  test    cs:byte_1800AA941, 8
0x180029bbe  jz      short loc_180029BF5
0x180029bc0  xor     eax, eax
0x180029bc2  mov     word ptr [rbp+820h+var_850], ax
0x180029bc6  mov     r8d, r13d
0x180029bc9  lea     rdx, aProcesstraffic; "ProcessTrafficSelectorsForId: Updating "...
0x180029bd0  lea     rcx, [rbp+820h+var_850]
0x180029bd4  call    FormatRRASErrorString
0x180029bd9  test    cs:byte_1800AA941, 8
0x180029be0  jz      short loc_180029BF5
0x180029be2  lea     r8, [rbp+820h+var_850]
0x180029be6  lea     rdx, RasVpnIkeTraceInfo
0x180029bed  mov     rcx, r14
0x180029bf0  call    McTemplateU0z_EventWriteTransfer
0x180029bf5  mov     [rsp+920h+var_8B0], rbx
0x180029bfa  mov     ebx, r13d
0x180029bfd  mov     [rsp+920h+var_8A8], rbx
0x180029c02  lea     rcx, [rdi+30h]
0x180029c06  lea     r8, [rsp+920h+var_8B0]
0x180029c0b  lea     rdx, [rbp+820h+var_860]
0x180029c0f  call    ?insert@?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CB_K_K@2@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::insert(std::pair<unsigned __int64 const,unsigned __int64> const &)
0x180029c14  mov     r10, [rdi+28h]
0x180029c18  mov     rax, [rdi+10h]
0x180029c1c  mov     r9, [rax+r13*8]
0x180029c20  mov     rax, [r10]
0x180029c23  mov     byte ptr [rsp+920h+var_8E8], 0
0x180029c28  mov     rcx, [r9+18h]
0x180029c2c  mov     [rsp+920h+var_8F0], rcx
0x180029c31  mov     ecx, [r9+10h]
0x180029c35  mov     [rsp+920h+var_8F8], ecx
0x180029c39  mov     rcx, [r9+8]
0x180029c3d  mov     [rsp+920h+var_900], rcx
0x180029c42  mov     r9d, [r9]
0x180029c45  mov     r8, [rbp+820h+var_8A0]
0x180029c49  mov     rdx, [rdi+20h]
0x180029c4d  mov     rcx, r10
0x180029c50  mov     rax, [rax+30h]
0x180029c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c59  test    eax, eax
0x180029c5b  jz      short loc_180029C97
0x180029c5d  test    cs:byte_1800AA941, sil
0x180029c64  jz      short loc_180029C97
0x180029c66  xor     eax, eax
0x180029c68  mov     word ptr [rbp+820h+var_850], ax
0x180029c6c  mov     r8d, r13d
0x180029c6f  lea     rdx, aProcesstraffic_5; "ProcessTrafficSelectorsForId: Update fa"...
0x180029c76  lea     rcx, [rbp+820h+var_850]
0x180029c7a  call    FormatRRASErrorString
0x180029c7f  test    cs:byte_1800AA941, sil
0x180029c86  jz      short loc_180029C97
0x180029c88  lea     r8, [rbp+820h+var_850]
0x180029c8c  mov     rdx, r15
0x180029c8f  mov     rcx, r14
0x180029c92  call    McTemplateU0z_EventWriteTransfer
0x180029c97  inc     r13d
0x180029c9a  jmp     loc_180029BA1
0x180029c9f  mov     r13, [rsp+920h+var_8B8]
0x180029ca4  inc     qword ptr [rdi+8]
0x180029ca8  mov     r8, [rdi+8]
0x180029cac  mov     [r13+0], r8
0x180029cb0  test    cs:byte_1800AA941, sil
0x180029cb7  jz      short loc_180029CE7
0x180029cb9  xor     eax, eax
0x180029cbb  mov     word ptr [rbp+820h+var_850], ax
0x180029cbf  lea     rdx, aProcesstraffic_1; "ProcessTrafficSelectorsForId: Generatin"...
0x180029cc6  lea     rcx, [rbp+820h+var_850]
0x180029cca  call    FormatRRASErrorString
0x180029ccf  test    cs:byte_1800AA941, sil
0x180029cd6  jz      short loc_180029CE7
0x180029cd8  lea     r8, [rbp+820h+var_850]
0x180029cdc  mov     rdx, r15
0x180029cdf  mov     rcx, r14
0x180029ce2  call    McTemplateU0z_EventWriteTransfer
0x180029ce7  xor     ebx, ebx
0x180029ce9  cmp     ebx, [rdi+18h]
0x180029cec  jnb     loc_180029E49
0x180029cf2  test    cs:byte_1800AA941, sil
0x180029cf9  jz      short loc_180029D2C
0x180029cfb  xor     eax, eax
0x180029cfd  mov     word ptr [rbp+820h+var_850], ax
0x180029d01  mov     r8d, ebx
0x180029d04  lea     rdx, aProcesstraffic_0; "ProcessTrafficSelectorsForId: Matching "...
0x180029d0b  lea     rcx, [rbp+820h+var_850]
0x180029d0f  call    FormatRRASErrorString
0x180029d14  test    cs:byte_1800AA941, sil
0x180029d1b  jz      short loc_180029D2C
0x180029d1d  lea     r8, [rbp+820h+var_850]
0x180029d21  mov     rdx, r15
0x180029d24  mov     rcx, r14
0x180029d27  call    McTemplateU0z_EventWriteTransfer
0x180029d2c  mov     edx, ebx
0x180029d2e  mov     [rsp+920h+var_8B8], rdx
0x180029d33  mov     rcx, [rdi]
0x180029d36  mov     rax, [rdi+10h]
0x180029d3a  lea     r8, [rax+rbx*8]
0x180029d3e  mov     rax, [rcx+8]
0x180029d42  mov     rcx, [rsp+920h+var_8C0]
0x180029d47  mov     [rsp+920h+var_900], rcx
0x180029d4c  mov     r9, [rsp+920h+var_8C8]
0x180029d51  mov     rdx, r13
0x180029d54  mov     rcx, rdi
0x180029d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d5c  mov     [rsp+920h+var_8D0], eax
0x180029d60  test    eax, eax
0x180029d62  jz      short loc_180029D68
0x180029d64  inc     ebx
0x180029d66  jmp     short loc_180029CE9
0x180029d68  mov     rax, [r13+0]
0x180029d6c  mov     [rsp+920h+var_8B0], rax
0x180029d71  mov     rax, [rsp+920h+var_8B8]
0x180029d76  mov     [rsp+920h+var_8A8], rax
0x180029d7b  lea     rcx, [rdi+30h]
0x180029d7f  lea     r8, [rsp+920h+var_8B0]
0x180029d84  lea     rdx, [rbp+820h+var_860]
0x180029d88  call    ?insert@?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CB_K_K@2@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::insert(std::pair<unsigned __int64 const,unsigned __int64> const &)
0x180029d8d  jmp     loc_180029E49
0x180029d92  call    cs:__imp_GetProcessHeap
0x180029d98  mov     rcx, rax; hHeap
0x180029d9b  mov     edx, 8; dwFlags
0x180029da0  mov     r8d, edx; dwBytes
0x180029da3  call    cs:__imp_HeapAlloc
0x180029da9  mov     r12, rax
0x180029dac  test    rax, rax
0x180029daf  jnz     short loc_180029DFC
0x180029db1  mov     [rsp+920h+var_8D0], 8
0x180029db9  test    cs:byte_1800AA941, sil
0x180029dc0  jz      loc_180029F43
0x180029dc6  xor     ecx, ecx
0x180029dc8  mov     word ptr [rbp+820h+var_850], cx
0x180029dcc  lea     r8d, [rax+8]
0x180029dd0  lea     rdx, aProcesstraffic_2; "ProcessTrafficSelectorsForId: VPNIKE_MA"...
0x180029dd7  lea     rcx, [rbp+820h+var_850]
0x180029ddb  call    FormatRRASErrorString
0x180029de0  test    cs:byte_1800AA941, sil
0x180029de7  jz      loc_180029F2D
0x180029ded  lea     r8, [rbp+820h+var_850]
0x180029df1  mov     rdx, r15
0x180029df4  mov     rcx, r14
0x180029df7  jmp     loc_180029F28
0x180029dfc  mov     r8, r12; struct _VPN_TRAFFIC_SELECTORS_ **
0x180029dff  mov     rdx, r13; unsigned __int64 *
0x180029e02  mov     rcx, rdi; this
0x180029e05  call    ?GetTrafficSelectorsForId@TrafficSelectors@@QEAAKPEA_KPEAPEAU_VPN_TRAFFIC_SELECTORS_@@@Z; TrafficSelectors::GetTrafficSelectorsForId(unsigned __int64 *,_VPN_TRAFFIC_SELECTORS_ * *)
0x180029e0a  mov     [rsp+920h+var_8D0], eax
0x180029e0e  cmp     qword ptr [r12], 0
0x180029e13  jz      loc_180029EEE
0x180029e19  test    eax, eax
0x180029e1b  jnz     loc_180029EEE
0x180029e21  mov     rax, [rdi]
0x180029e24  mov     rcx, [rsp+920h+var_8C0]
0x180029e29  mov     [rsp+920h+var_900], rcx
0x180029e2e  mov     r9, [rsp+920h+var_8C8]
0x180029e33  mov     r8, r12
0x180029e36  mov     rdx, r13
0x180029e39  mov     rcx, rdi
0x180029e3c  mov     rax, [rax+8]
0x180029e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e45  mov     [rsp+920h+var_8D0], eax
0x180029e49  cmp     [rsp+920h+var_8D0], 0
0x180029e4e  jz      short loc_180029E66
0x180029e50  test    cs:byte_1800AA941, sil
0x180029e57  jz      loc_180029F2D
0x180029e5d  lea     r8, aProcesstraffic_4; "ProcessTrafficSelectorsForId: Negotiati"...
0x180029e64  jmp     short loc_180029DF1
0x180029e66  mov     rax, [rsp+920h+var_8C0]
0x180029e6b  mov     r9, [rax]
0x180029e6e  test    r9, r9
0x180029e71  jnz     short loc_180029E94
0x180029e73  mov     [rsp+920h+var_8D0], 8
0x180029e7b  test    cs:byte_1800AA941, sil
0x180029e82  jz      loc_180029F43
0x180029e88  lea     r8, aProcesstraffic_6; "ProcessTrafficSelectorsForId: NarrowTra"...
0x180029e8f  jmp     loc_180029DF1
0x180029e94  mov     r10, [rdi+28h]
0x180029e98  mov     rax, [r10]
0x180029e9b  mov     byte ptr [rsp+920h+var_8E8], 0
0x180029ea0  mov     rcx, [r9+8]
0x180029ea4  mov     [rsp+920h+var_8F0], rcx
0x180029ea9  mov     ecx, [r9]
0x180029eac  mov     [rsp+920h+var_8F8], ecx
0x180029eb0  mov     rcx, [r9+18h]
0x180029eb4  mov     [rsp+920h+var_900], rcx
0x180029eb9  mov     r9d, [r9+10h]
0x180029ebd  mov     r8, [r13+0]
0x180029ec1  mov     rdx, [rdi+20h]
0x180029ec5  mov     rcx, r10
0x180029ec8  mov     rax, [rax+28h]
0x180029ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ed1  mov     [rsp+920h+var_8D0], eax
0x180029ed5  test    eax, eax
0x180029ed7  jz      short loc_180029F2D
0x180029ed9  test    cs:byte_1800AA941, sil
0x180029ee0  jz      short loc_180029F2D
0x180029ee2  lea     r8, aUpdatevpntraff; "UpdateVPNTrafficSelectors failed"
0x180029ee9  jmp     loc_180029DF1
0x180029eee  mov     [rsp+920h+var_8D0], 57h ; 'W'
0x180029ef6  test    cs:byte_1800AA941, sil
0x180029efd  jz      short loc_180029F43
0x180029eff  mov     rdx, r15
0x180029f02  mov     rcx, r14
0x180029f05  jmp     short loc_180029F21
0x180029f07  mov     [rsp+920h+var_8D0], 57h ; 'W'
0x180029f0f  test    al, 4
0x180029f11  jz      short loc_180029F3B
0x180029f13  lea     rdx, RasVpnIkeTraceError
0x180029f1a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180029f21  lea     r8, aProcesstraffic_3; "ProcessTrafficSelectorsForId: ERROR_INV"...
0x180029f28  call    McTemplateU0z_EventWriteTransfer
0x180029f2d  mov     rbx, cs:WPP_GLOBAL_Control
0x180029f34  cmp     [rsp+920h+var_8D0], 0
0x180029f39  jz      short loc_180029F6D
0x180029f3b  cmp     [rsp+920h+var_8C0], 0
0x180029f41  jz      short loc_180029F6D
0x180029f43  mov     rax, [rdi]
0x180029f46  mov     rcx, [rsp+920h+var_8C0]
0x180029f4b  mov     rdx, [rcx]
0x180029f4e  mov     rcx, rdi
0x180029f51  mov     rax, [rax+18h]
0x180029f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f5a  mov     rax, [rsp+920h+var_8C0]
  ... truncated ...
```
