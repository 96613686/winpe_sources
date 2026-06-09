# BFEHandler::SendAdditionalAddressesToPeer(IPSEC_ADDRESS_INFO0_ *)

- ea: `0x1800300f0`
- end: `0x18003036e`
- name: `?SendAdditionalAddressesToPeer@BFEHandler@@UEAAKPEAUIPSEC_ADDRESS_INFO0_@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(void **this, struct IPSEC_ADDRESS_INFO0_ *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x1800300f0`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!IkeextSaUpdateAdditionalAddressesByTunnelId0` at `0x180030202`
- `fwpuclnt!IkeextSaUpdateAdditionalAddressesByTunnelId0` at `0x180030202`

## string_xrefs

- `0x18003028e`: `IkeextSaUpdateAdditionalAddressesByTunnelId0 failed: %d`

## pseudocode

```c
__int64 __fastcall BFEHandler::SendAdditionalAddressesToPeer(void **this, struct IPSEC_ADDRESS_INFO0_ *a2)
{
  unsigned int v4; // esi
  unsigned int updated; // eax
  unsigned int v6; // edi
  _QWORD *v7; // rax
  __int64 v8; // rax
  char *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  __int128 *v12; // r9
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+38h] [rbp-C8h]
  __int128 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+78h] [rbp-88h] BYREF
  __int128 v22; // [rsp+7Ch] [rbp-84h]
  __int128 v23; // [rsp+8Ch] [rbp-74h]
  int v24; // [rsp+9Ch] [rbp-64h]
  int v25; // [rsp+A0h] [rbp-60h] BYREF
  char v26[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v20 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v4 = -1;
  v18 = -1;
  v19 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"BFEHandler::SendAdditionalAddressesToPeer",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
  _InterlockedIncrement((volatile signed __int32 *)this[6] + 51);
  updated = IkeextSaUpdateAdditionalAddressesByTunnelId0(
              BFEHandler::hFwpEngine,
              *((_QWORD *)this[6] + 1),
              a2,
              BFEHandler::NotifyAdditionalAddressesToPeerCallback,
              this[6]);
  v6 = updated;
  if ( updated )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, updated);
    }
    BaseConnection::DeleteRef((BaseConnection *)this[6]);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v25) = 0;
      LOWORD(v21) = 0;
      v7 = this[6];
      if ( v7 )
      {
        v8 = v7[14];
        if ( v8 )
        {
          if ( *(_QWORD *)(v8 + 16) )
            v4 = *(_DWORD *)(v8 + 16);
        }
      }
      ConvertPortNoToString(&v21, v4);
      FormatRRASErrorString(&v25, L"IkeextSaUpdateAdditionalAddressesByTunnelId0 failed: %d", v6);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v9 = (char *)this[6];
        v10 = v9 + 112;
        if ( v9 )
        {
          if ( *v10 )
            v11 = *v10 + 2686LL;
          else
            v11 = 0;
          if ( *v10 )
          {
            v12 = (__int128 *)(*v10 + 2120LL);
LABEL_26:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v25,
              (_DWORD)v12,
              v11,
              (__int64)&v21);
            goto LABEL_27;
          }
        }
        else
        {
          v11 = 0;
        }
        v12 = &v20;
        goto LABEL_26;
      }
    }
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v6);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v6;
}

```

## disassembly

```asm
0x1800300f0  mov     [rsp-8+arg_10], rbx
0x1800300f5  mov     [rsp-8+arg_18], rsi
0x1800300fa  push    rbp
0x1800300fb  push    rdi
0x1800300fc  push    r15
0x1800300fe  lea     rbp, [rsp-7B0h]
0x180030106  sub     rsp, 8B0h
0x18003010d  mov     rax, cs:__security_cookie
0x180030114  xor     rax, rsp
0x180030117  mov     [rbp+7C0h+var_20], rax
0x18003011e  mov     rdi, rdx
0x180030121  mov     rbx, rcx
0x180030124  lea     r15, WPP_GLOBAL_Control
0x18003012b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030132  cmp     rcx, r15
0x180030135  jz      short loc_180030158
0x180030137  test    byte ptr [rcx+1Ch], 1
0x18003013b  jz      short loc_180030158
0x18003013d  cmp     byte ptr [rcx+19h], 6
0x180030141  jb      short loc_180030158
0x180030143  mov     edx, 4Ch ; 'L'
0x180030148  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18003014f  mov     rcx, [rcx+10h]
0x180030153  call    WPP_SF_
0x180030158  xor     eax, eax
0x18003015a  mov     [rbp+7C0h+var_820], eax
0x18003015d  xor     edx, edx; Val
0x18003015f  mov     r8d, 7FCh; Size
0x180030165  lea     rcx, [rbp+7C0h+var_81C]; void *
0x180030169  call    memset_0
0x18003016e  xor     eax, eax
0x180030170  mov     [rsp+8C0h+var_848], eax
0x180030174  xorps   xmm0, xmm0
0x180030177  movups  [rsp+8C0h+var_844], xmm0
0x18003017c  movups  [rbp+7C0h+var_834], xmm0
0x180030180  mov     [rbp+7C0h+var_824], eax
0x180030183  movups  [rsp+8C0h+var_858], xmm0
0x180030188  xorps   xmm1, xmm1
0x18003018b  movdqu  [rsp+8C0h+var_888], xmm1
0x180030191  mov     [rsp+8C0h+var_890], rax
0x180030196  movdqu  [rsp+8C0h+var_878], xmm0
0x18003019c  mov     [rsp+8C0h+var_868], rax
0x1800301a1  or      esi, 0FFFFFFFFh
0x1800301a4  mov     [rsp+8C0h+var_860], esi
0x1800301a8  mov     [rsp+8C0h+var_85C], eax
0x1800301ac  test    cs:byte_1800AA941, 8
0x1800301b3  jz      short loc_1800301D9
0x1800301b5  mov     rax, [rbx+30h]
0x1800301b9  mov     [rsp+8C0h+var_8A0], rax; void *
0x1800301be  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800301c5  xor     r8d, r8d; unsigned int *
0x1800301c8  lea     rdx, aBfehandlerSend; "BFEHandler::SendAdditionalAddressesToPe"...
0x1800301cf  lea     rcx, [rsp+8C0h+var_890]; this
0x1800301d4  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800301d9  mov     rax, [rbx+30h]
0x1800301dd  lock inc dword ptr [rax+0CCh]
0x1800301e4  mov     rdx, [rbx+30h]
0x1800301e8  mov     [rsp+8C0h+var_8A0], rdx
0x1800301ed  lea     r9, ?NotifyAdditionalAddressesToPeerCallback@BFEHandler@@SAXPEAXK@Z; BFEHandler::NotifyAdditionalAddressesToPeerCallback(void *,ulong)
0x1800301f4  mov     r8, rdi
0x1800301f7  mov     rdx, [rdx+8]
0x1800301fb  mov     rcx, cs:?hFwpEngine@BFEHandler@@0PEAXEA; void * BFEHandler::hFwpEngine
0x180030202  call    cs:__imp_IkeextSaUpdateAdditionalAddressesByTunnelId0
0x180030208  mov     edi, eax
0x18003020a  test    eax, eax
0x18003020c  jz      loc_18003030A
0x180030212  mov     rcx, cs:WPP_GLOBAL_Control
0x180030219  cmp     rcx, r15
0x18003021c  jz      short loc_180030242
0x18003021e  test    byte ptr [rcx+1Ch], 1
0x180030222  jz      short loc_180030242
0x180030224  cmp     byte ptr [rcx+19h], 2
0x180030228  jb      short loc_180030242
0x18003022a  mov     edx, 4Dh ; 'M'
0x18003022f  mov     r9d, eax
0x180030232  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x180030239  mov     rcx, [rcx+10h]
0x18003023d  call    WPP_SF_d
0x180030242  mov     rcx, [rbx+30h]; this
0x180030246  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18003024b  test    cs:byte_1800AA941, 4
0x180030252  jz      loc_18003030A
0x180030258  xor     eax, eax
0x18003025a  mov     word ptr [rbp+7C0h+var_820], ax
0x18003025e  mov     word ptr [rsp+8C0h+var_848], ax
0x180030263  mov     rax, [rbx+30h]
0x180030267  test    rax, rax
0x18003026a  jz      short loc_18003027F
0x18003026c  mov     rax, [rax+70h]
0x180030270  test    rax, rax
0x180030273  jz      short loc_18003027F
0x180030275  cmp     qword ptr [rax+10h], 0
0x18003027a  jz      short loc_18003027F
0x18003027c  mov     esi, [rax+10h]
0x18003027f  mov     edx, esi
0x180030281  lea     rcx, [rsp+8C0h+var_848]
0x180030286  call    ConvertPortNoToString
0x18003028b  mov     r8d, edi
0x18003028e  lea     rdx, aIkeextsaupdate; "IkeextSaUpdateAdditionalAddressesByTunn"...
0x180030295  lea     rcx, [rbp+7C0h+var_820]
0x180030299  call    FormatRRASErrorString
0x18003029e  test    cs:byte_1800AA941, 4
0x1800302a5  jz      short loc_18003030A
0x1800302a7  mov     rcx, [rbx+30h]
0x1800302ab  lea     rax, [rcx+70h]
0x1800302af  test    rcx, rcx
0x1800302b2  jz      short loc_1800302DD
0x1800302b4  mov     rdx, [rax]
0x1800302b7  test    rdx, rdx
0x1800302ba  jz      short loc_1800302C5
0x1800302bc  lea     rcx, [rdx+0A7Eh]
0x1800302c3  jmp     short loc_1800302CC
0x1800302c5  test    rcx, rcx
0x1800302c8  jz      short loc_1800302DD
0x1800302ca  xor     ecx, ecx
0x1800302cc  mov     rdx, [rax]
0x1800302cf  test    rdx, rdx
0x1800302d2  jz      short loc_1800302DF
0x1800302d4  lea     r9, [rdx+848h]
0x1800302db  jmp     short loc_1800302E4
0x1800302dd  xor     ecx, ecx
0x1800302df  lea     r9, [rsp+8C0h+var_858]
0x1800302e4  lea     rax, [rsp+8C0h+var_848]
0x1800302e9  mov     [rsp+8C0h+var_898], rax
0x1800302ee  mov     [rsp+8C0h+var_8A0], rcx
0x1800302f3  lea     r8, [rbp+7C0h+var_820]
0x1800302f7  lea     rdx, RasVpnIkeParamTraceError
0x1800302fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180030305  call    McTemplateU0zjzz_EventWriteTransfer
0x18003030a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030311  cmp     rcx, r15
0x180030314  jz      short loc_18003033B
0x180030316  test    byte ptr [rcx+1Ch], 1
0x18003031a  jz      short loc_18003033B
0x18003031c  cmp     byte ptr [rcx+19h], 6
0x180030320  jb      short loc_18003033B
0x180030322  mov     edx, 4Eh ; 'N'
0x180030327  mov     r9d, edi
0x18003032a  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x180030331  mov     rcx, [rcx+10h]
0x180030335  call    WPP_SF_d
0x18003033a  nop
0x18003033b  lea     rcx, [rsp+8C0h+var_890]; this
0x180030340  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180030345  mov     eax, edi
0x180030347  mov     rcx, [rbp+7C0h+var_20]
0x18003034e  xor     rcx, rsp; StackCookie
0x180030351  call    __security_check_cookie
0x180030356  lea     r11, [rsp+8C0h+var_10]
0x18003035e  mov     rbx, [r11+30h]
0x180030362  mov     rsi, [r11+38h]
0x180030366  mov     rsp, r11
0x180030369  pop     r15
0x18003036b  pop     rdi
0x18003036c  pop     rbp
0x18003036d  retn
```
