# VPNIKEClientConnection::InitiateIkeCompleteCallback(void *,IPSEC_NEGOTIATION_STATUS0_ const *)

- ea: `0x1800197a0`
- end: `0x180019cc4`
- name: `?InitiateIkeCompleteCallback@VPNIKEClientConnection@@SAXPEAXPEBUIPSEC_NEGOTIATION_STATUS0_@@@Z`
- size: `1316`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct IPSEC_NEGOTIATION_STATUS0_ *)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x180007794`
- `0x1800197a0`
- `0x18001a5f0`
- `0x18001a76c`
- `0x18001a8a0`
- `0x18001f10c`
- `0x180020d94`
- `0x180020e68`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800198d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800198d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019bde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019bde`

## string_xrefs

- `0x180019874`: `VPNIKEClientConnection::InitiateIkeCompleteCallback`
- `0x180019c1f`: `InitiateIkeCompleteCallback invoked for invalid parameters. Ignoring callback.`
- `0x18001991d`: `InitiateIkeCompleteCallback:SA negotiation failure Status:%d for TunnelID: %I64X`
- `0x180019a44`: `InitiateIkeCompleteCallback:All SA negotiation completed. Status:%d for TunnelID: %I64X`
- `0x180019b8b`: `InitiateIkeCompleteCallback called before CreateTunnel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VPNIKEClientConnection::InitiateIkeCompleteCallback(
        struct _RTL_CRITICAL_SECTION *this,
        const struct IPSEC_NEGOTIATION_STATUS0_ *a2)
{
  PVOID *v4; // rdi
  unsigned int v5; // r14d
  char v6; // al
  __int64 v7; // r8
  ULONG_PTR SpinCount; // rax
  __int64 v9; // rdx
  ULONG_PTR v10; // rdx
  __int128 *v11; // r9
  char v12; // cl
  ULONG_PTR v13; // rax
  __int64 v14; // rdx
  ULONG_PTR v15; // rdx
  __int128 *v16; // r9
  unsigned int DebugInfo; // edx
  ULONG_PTR v18; // rax
  ULONG_PTR v19; // rdx
  __int128 *v20; // r9
  __int64 v21; // rdx
  PVOID v22; // rcx
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  __int128 v29; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+94h] [rbp-6Ch]
  __int128 v32; // [rsp+A4h] [rbp-5Ch]
  int v33; // [rsp+B4h] [rbp-4Ch]
  int v34; // [rsp+C0h] [rbp-40h] BYREF
  char v35[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v29 = 0;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v5 = -1;
  v27 = -1;
  v28 = 0;
  v6 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v23,
      L"VPNIKEClientConnection::InitiateIkeCompleteCallback",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v6 = byte_1800AA941;
  }
  if ( this && a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      WPP_SF_(v4[2], 23, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    EnterCriticalSection(this + 4);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      SpinCount = this[2].SpinCount;
      if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
        v9 = *(unsigned int *)(SpinCount + 16);
      else
        v9 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v30, v9);
      FormatRRASErrorString(
        &v34,
        L"InitiateIkeCompleteCallback:SA negotiation failure Status:%d for TunnelID: %I64X",
        *(unsigned int *)a2,
        *(_QWORD *)(this[2].SpinCount + 8));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v10 = this[2].SpinCount;
        LODWORD(v11) = v10 + 2120;
        if ( !v10 )
          v11 = &v29;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v34,
          (_DWORD)v11,
          (v10 + 2686) & -(__int64)(v10 != 0),
          (__int64)&v30);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_DiDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        WPP_GLOBAL_Control,
        v7,
        *(unsigned int *)a2,
        *(_QWORD *)(this[2].SpinCount + 8),
        this[3].SpinCount,
        HIDWORD(this[9].DebugInfo));
    }
    if ( HIDWORD(this[9].DebugInfo) )
      HIDWORD(this[9].DebugInfo) = *(_DWORD *)a2;
    v12 = this[3].SpinCount & 1;
    if ( _InterlockedExchangeAdd(&this[9].LockCount, 0xFFFFFFFF) == 1 && v12 )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v34) = 0;
        LOWORD(v30) = 0;
        v13 = this[2].SpinCount;
        if ( v13 && *(_QWORD *)(v13 + 16) )
          v14 = *(unsigned int *)(v13 + 16);
        else
          v14 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v30, v14);
        FormatRRASErrorString(
          &v34,
          L"InitiateIkeCompleteCallback:All SA negotiation completed. Status:%d for TunnelID: %I64X",
          HIDWORD(this[9].DebugInfo),
          *(_QWORD *)(this[2].SpinCount + 8));
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v15 = this[2].SpinCount;
          LODWORD(v16) = v15 + 2120;
          if ( !v15 )
            v16 = &v29;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v34,
            (_DWORD)v16,
            (v15 + 2686) & -(__int64)(v15 != 0),
            (__int64)&v30);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_di(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          WPP_GLOBAL_Control,
          v7,
          HIDWORD(this[9].DebugInfo),
          *(_QWORD *)(this[2].SpinCount + 8));
      }
      if ( HIDWORD(this[9].DebugInfo) )
      {
        VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 0x402u);
        DebugInfo = (unsigned int)this[9].DebugInfo;
        if ( !DebugInfo )
          DebugInfo = HIDWORD(this[9].DebugInfo);
        VPNIKEClientConnection::NotifyError((VPNIKEClientConnection *)this, DebugInfo);
      }
      else
      {
        if ( (this[3].SpinCount & 4) == 0 && (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v30) = 0;
          v18 = this[2].SpinCount;
          if ( v18 && *(_QWORD *)(v18 + 16) )
            v5 = *(_DWORD *)(v18 + 16);
          ConvertPortNoToString(&v30, v5);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v19 = this[2].SpinCount;
            LODWORD(v20) = v19 + 2120;
            if ( !v19 )
              v20 = &v29;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"InitiateIkeCompleteCallback called before CreateTunnel",
              (_DWORD)v20,
              (v19 + 2686) & -(__int64)(v19 != 0),
              (__int64)&v30);
          }
        }
        VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 0x202u);
        VPNIKEClientConnection::NotifyDone((VPNIKEClientConnection *)this);
      }
      if ( (this[3].SpinCount & 0x1800) != 0 && (this[3].SpinCount & 0x4000) == 0 )
        VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete((VPNIKEClientConnection *)this);
    }
    LeaveCriticalSection(this + 4);
    BaseConnection::DeleteRef((BaseConnection *)this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v21 = 26;
      v22 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_73:
      WPP_SF_(v22, v21, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    }
  }
  else
  {
    if ( (v6 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"InitiateIkeCompleteCallback invoked for invalid parameters. Ignoring callback.");
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_(v4[2], 21, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v21 = 22;
        v22 = v4[2];
        goto LABEL_73;
      }
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v23);
}

```

## disassembly

```asm
0x1800197a0  mov     [rsp-8+arg_10], rbx
0x1800197a5  push    rbp
0x1800197a6  push    rsi
0x1800197a7  push    rdi
0x1800197a8  push    r13
0x1800197aa  push    r14
0x1800197ac  lea     rbp, [rsp-7D0h]
0x1800197b4  sub     rsp, 8D0h
0x1800197bb  mov     rax, cs:__security_cookie
0x1800197c2  xor     rax, rsp
0x1800197c5  mov     [rbp+7F0h+var_30], rax
0x1800197cc  mov     rsi, rdx
0x1800197cf  mov     rbx, rcx
0x1800197d2  lea     r13, WPP_GLOBAL_Control
0x1800197d9  mov     rdi, cs:WPP_GLOBAL_Control
0x1800197e0  cmp     rdi, r13
0x1800197e3  jz      short loc_18001980D
0x1800197e5  test    byte ptr [rdi+1Ch], 1
0x1800197e9  jz      short loc_18001980D
0x1800197eb  cmp     byte ptr [rdi+19h], 6
0x1800197ef  jb      short loc_18001980D
0x1800197f1  mov     edx, 14h
0x1800197f6  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x1800197fd  mov     rcx, [rdi+10h]
0x180019801  call    WPP_SF_
0x180019806  mov     rdi, cs:WPP_GLOBAL_Control
0x18001980d  xor     eax, eax
0x18001980f  mov     [rbp+7F0h+var_830], eax
0x180019812  xor     edx, edx; Val
0x180019814  mov     r8d, 7FCh; Size
0x18001981a  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18001981e  call    memset_0
0x180019823  xor     eax, eax
0x180019825  mov     [rbp+7F0h+var_860], eax
0x180019828  xorps   xmm0, xmm0
0x18001982b  movups  [rbp+7F0h+var_85C], xmm0
0x18001982f  movups  [rbp+7F0h+var_84C], xmm0
0x180019833  mov     [rbp+7F0h+var_83C], eax
0x180019836  movups  [rbp+7F0h+var_870], xmm0
0x18001983a  xorps   xmm1, xmm1
0x18001983d  movdqu  [rsp+8F0h+var_8A0], xmm1
0x180019843  mov     [rsp+8F0h+var_8A8], rax
0x180019848  movdqu  [rsp+8F0h+var_890], xmm0
0x18001984e  mov     [rsp+8F0h+var_880], rax
0x180019853  or      r14d, 0FFFFFFFFh
0x180019857  mov     [rsp+8F0h+var_878], r14d
0x18001985c  mov     [rsp+8F0h+var_874], eax
0x180019860  mov     al, cs:byte_1800AA941
0x180019866  test    al, 8
0x180019868  jz      short loc_180019892
0x18001986a  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180019871  xor     r8d, r8d; unsigned int *
0x180019874  lea     rdx, aVpnikeclientco_3; "VPNIKEClientConnection::InitiateIkeComp"...
0x18001987b  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180019880  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180019885  mov     rdi, cs:WPP_GLOBAL_Control
0x18001988c  mov     al, cs:byte_1800AA941
0x180019892  test    rbx, rbx
0x180019895  jz      loc_180019C1B
0x18001989b  test    rsi, rsi
0x18001989e  jz      loc_180019C1B
0x1800198a4  cmp     rdi, r13
0x1800198a7  jz      short loc_1800198CA
0x1800198a9  test    byte ptr [rdi+1Ch], 1
0x1800198ad  jz      short loc_1800198CA
0x1800198af  cmp     byte ptr [rdi+19h], 5
0x1800198b3  jb      short loc_1800198CA
0x1800198b5  mov     edx, 17h
0x1800198ba  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x1800198c1  mov     rcx, [rdi+10h]
0x1800198c5  call    WPP_SF_
0x1800198ca  lea     rdi, [rbx+0A0h]
0x1800198d1  mov     rcx, rdi; lpCriticalSection
0x1800198d4  call    cs:__imp_EnterCriticalSection
0x1800198da  test    cs:byte_1800AA941, 8
0x1800198e1  jz      loc_180019982
0x1800198e7  xor     eax, eax
0x1800198e9  mov     word ptr [rbp+7F0h+var_830], ax
0x1800198ed  mov     word ptr [rbp+7F0h+var_860], ax
0x1800198f1  mov     rax, [rbx+70h]
0x1800198f5  test    rax, rax
0x1800198f8  jz      short loc_180019906
0x1800198fa  cmp     qword ptr [rax+10h], 0
0x1800198ff  jz      short loc_180019906
0x180019901  mov     edx, [rax+10h]
0x180019904  jmp     short loc_180019909
0x180019906  mov     edx, r14d
0x180019909  lea     rcx, [rbp+7F0h+var_860]
0x18001990d  call    ConvertPortNoToString
0x180019912  mov     r9, [rbx+70h]
0x180019916  mov     r9, [r9+8]
0x18001991a  mov     r8d, [rsi]
0x18001991d  lea     rdx, aInitiateikecom_0; "InitiateIkeCompleteCallback:SA negotiat"...
0x180019924  lea     rcx, [rbp+7F0h+var_830]
0x180019928  call    FormatRRASErrorString
0x18001992d  test    cs:byte_1800AA941, 8
0x180019934  jz      short loc_180019982
0x180019936  mov     rdx, [rbx+70h]
0x18001993a  mov     rax, rdx
0x18001993d  lea     rcx, [rdx+0A7Eh]
0x180019944  neg     rax
0x180019947  sbb     r8, r8
0x18001994a  and     r8, rcx
0x18001994d  test    rdx, rdx
0x180019950  lea     r9, [rdx+848h]
0x180019957  jnz     short loc_18001995D
0x180019959  lea     r9, [rbp+7F0h+var_870]
0x18001995d  lea     rax, [rbp+7F0h+var_860]
0x180019961  mov     [rsp+8F0h+var_8C8], rax
0x180019966  mov     [rsp+8F0h+var_8D0], r8
0x18001996b  lea     r8, [rbp+7F0h+var_830]
0x18001996f  lea     rdx, RasVpnIkeParamTraceInfo
0x180019976  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001997d  call    McTemplateU0zjzz_EventWriteTransfer
0x180019982  mov     rdx, cs:WPP_GLOBAL_Control
0x180019989  cmp     rdx, r13
0x18001998c  jz      short loc_1800199C7
0x18001998e  test    byte ptr [rdx+1Ch], 1
0x180019992  jz      short loc_1800199C7
0x180019994  cmp     byte ptr [rdx+19h], 5
0x180019998  jb      short loc_1800199C7
0x18001999a  mov     rcx, [rbx+70h]
0x18001999e  mov     eax, [rbx+16Ch]
0x1800199a4  mov     [rsp+8F0h+var_8C0], eax
0x1800199a8  mov     eax, [rbx+98h]
0x1800199ae  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x1800199b2  mov     rax, [rcx+8]
0x1800199b6  mov     [rsp+8F0h+var_8D0], rax
0x1800199bb  mov     r9d, [rsi]
0x1800199be  mov     rcx, [rdx+10h]
0x1800199c2  call    WPP_SF_DiDD
0x1800199c7  cmp     dword ptr [rbx+16Ch], 0
0x1800199ce  jz      short loc_1800199D8
0x1800199d0  mov     eax, [rsi]
0x1800199d2  mov     [rbx+16Ch], eax
0x1800199d8  mov     cl, [rbx+98h]
0x1800199de  and     cl, 1
0x1800199e1  or      eax, 0FFFFFFFFh
0x1800199e4  lock xadd [rbx+170h], eax
0x1800199ec  cmp     eax, 1
0x1800199ef  jnz     loc_180019BDB
0x1800199f5  test    cl, cl
0x1800199f7  jz      loc_180019BDB
0x1800199fd  test    cs:byte_1800AA941, 8
0x180019a04  jz      loc_180019AA9
0x180019a0a  xor     eax, eax
0x180019a0c  mov     word ptr [rbp+7F0h+var_830], ax
0x180019a10  mov     word ptr [rbp+7F0h+var_860], ax
0x180019a14  mov     rax, [rbx+70h]
0x180019a18  test    rax, rax
0x180019a1b  jz      short loc_180019A29
0x180019a1d  cmp     qword ptr [rax+10h], 0
0x180019a22  jz      short loc_180019A29
0x180019a24  mov     edx, [rax+10h]
0x180019a27  jmp     short loc_180019A2C
0x180019a29  mov     edx, r14d
0x180019a2c  lea     rcx, [rbp+7F0h+var_860]
0x180019a30  call    ConvertPortNoToString
0x180019a35  mov     r9, [rbx+70h]
0x180019a39  mov     r9, [r9+8]
0x180019a3d  mov     r8d, [rbx+16Ch]
0x180019a44  lea     rdx, aInitiateikecom_2; "InitiateIkeCompleteCallback:All SA nego"...
0x180019a4b  lea     rcx, [rbp+7F0h+var_830]
0x180019a4f  call    FormatRRASErrorString
0x180019a54  test    cs:byte_1800AA941, 8
0x180019a5b  jz      short loc_180019AA9
0x180019a5d  mov     rdx, [rbx+70h]
0x180019a61  mov     rax, rdx
0x180019a64  lea     rcx, [rdx+0A7Eh]
0x180019a6b  neg     rax
0x180019a6e  sbb     r8, r8
0x180019a71  and     r8, rcx
0x180019a74  test    rdx, rdx
0x180019a77  lea     r9, [rdx+848h]
0x180019a7e  jnz     short loc_180019A84
0x180019a80  lea     r9, [rbp+7F0h+var_870]
0x180019a84  lea     rax, [rbp+7F0h+var_860]
0x180019a88  mov     [rsp+8F0h+var_8C8], rax
0x180019a8d  mov     [rsp+8F0h+var_8D0], r8
0x180019a92  lea     r8, [rbp+7F0h+var_830]
0x180019a96  lea     rdx, RasVpnIkeParamTraceInfo
0x180019a9d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019aa4  call    McTemplateU0zjzz_EventWriteTransfer
0x180019aa9  mov     rdx, cs:WPP_GLOBAL_Control
0x180019ab0  cmp     rdx, r13
0x180019ab3  jz      short loc_180019ADE
0x180019ab5  test    byte ptr [rdx+1Ch], 1
0x180019ab9  jz      short loc_180019ADE
0x180019abb  cmp     byte ptr [rdx+19h], 5
0x180019abf  jb      short loc_180019ADE
0x180019ac1  mov     rax, [rbx+70h]
0x180019ac5  mov     rcx, [rax+8]
0x180019ac9  mov     [rsp+8F0h+var_8D0], rcx
0x180019ace  mov     r9d, [rbx+16Ch]
0x180019ad5  mov     rcx, [rdx+10h]
0x180019ad9  call    WPP_SF_di
0x180019ade  cmp     dword ptr [rbx+16Ch], 0
0x180019ae5  jz      short loc_180019B11
0x180019ae7  mov     edx, 402h; unsigned int
0x180019aec  mov     rcx, rbx; this
0x180019aef  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x180019af4  mov     edx, [rbx+168h]
0x180019afa  test    edx, edx
0x180019afc  jnz     short loc_180019B04
0x180019afe  mov     edx, [rbx+16Ch]; unsigned int
0x180019b04  mov     rcx, rbx; this
0x180019b07  call    ?NotifyError@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::NotifyError(ulong)
0x180019b0c  jmp     loc_180019BBA
0x180019b11  test    byte ptr [rbx+98h], 4
0x180019b18  jnz     loc_180019BA5
0x180019b1e  test    cs:byte_1800AA941, 4
0x180019b25  jz      short loc_180019BA5
0x180019b27  xor     eax, eax
0x180019b29  mov     word ptr [rbp+7F0h+var_860], ax
0x180019b2d  mov     rax, [rbx+70h]
0x180019b31  test    rax, rax
0x180019b34  jz      short loc_180019B41
0x180019b36  cmp     qword ptr [rax+10h], 0
0x180019b3b  jz      short loc_180019B41
0x180019b3d  mov     r14d, [rax+10h]
0x180019b41  mov     edx, r14d
0x180019b44  lea     rcx, [rbp+7F0h+var_860]
0x180019b48  call    ConvertPortNoToString
0x180019b4d  test    cs:byte_1800AA941, 4
0x180019b54  jz      short loc_180019BA5
0x180019b56  mov     rdx, [rbx+70h]
0x180019b5a  mov     rax, rdx
0x180019b5d  lea     rcx, [rdx+0A7Eh]
0x180019b64  neg     rax
0x180019b67  sbb     r8, r8
0x180019b6a  and     r8, rcx
0x180019b6d  test    rdx, rdx
0x180019b70  lea     r9, [rdx+848h]
0x180019b77  jnz     short loc_180019B7D
0x180019b79  lea     r9, [rbp+7F0h+var_870]
0x180019b7d  lea     rax, [rbp+7F0h+var_860]
0x180019b81  mov     [rsp+8F0h+var_8C8], rax
0x180019b86  mov     [rsp+8F0h+var_8D0], r8
0x180019b8b  lea     r8, aInitiateikecom_1; "InitiateIkeCompleteCallback called befo"...
0x180019b92  lea     rdx, RasVpnIkeParamTraceError
0x180019b99  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019ba0  call    McTemplateU0zjzz_EventWriteTransfer
0x180019ba5  mov     edx, 202h; unsigned int
0x180019baa  mov     rcx, rbx; this
0x180019bad  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x180019bb2  mov     rcx, rbx; this
0x180019bb5  call    ?NotifyDone@VPNIKEClientConnection@@IEAAXXZ; VPNIKEClientConnection::NotifyDone(void)
0x180019bba  mov     eax, [rbx+98h]
0x180019bc0  test    eax, 1800h
0x180019bc5  setnz   dl
0x180019bc8  bt      eax, 0Eh
0x180019bcc  setnb   al
0x180019bcf  test    al, dl
0x180019bd1  jz      short loc_180019BDB
0x180019bd3  mov     rcx, rbx; this
0x180019bd6  call    ?NotifyOnDisconnectCleanupComplete@VPNIKEClientConnection@@IEAAXXZ; VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete(void)
0x180019bdb  mov     rcx, rdi; lpCriticalSection
0x180019bde  call    cs:__imp_LeaveCriticalSection
0x180019be4  mov     rcx, rbx; this
0x180019be7  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180019bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bf3  cmp     rcx, r13
0x180019bf6  jz      loc_180019C94
0x180019bfc  test    byte ptr [rcx+1Ch], 1
0x180019c00  jz      loc_180019C94
0x180019c06  cmp     byte ptr [rcx+19h], 6
0x180019c0a  jb      loc_180019C94
0x180019c10  mov     edx, 1Ah
0x180019c15  mov     rcx, [rcx+10h]
0x180019c19  jmp     short loc_180019C87
0x180019c1b  test    al, 4
0x180019c1d  jz      short loc_180019C40
0x180019c1f  lea     r8, aInitiateikecom; "InitiateIkeCompleteCallback invoked for"...
0x180019c26  lea     rdx, RasVpnIkeTraceError
0x180019c2d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019c34  call    McTemplateU0z_EventWriteTransfer
0x180019c39  mov     rdi, cs:WPP_GLOBAL_Control
0x180019c40  cmp     rdi, r13
0x180019c43  jz      short loc_180019C94
0x180019c45  test    byte ptr [rdi+1Ch], 1
0x180019c49  jz      short loc_180019C6D
0x180019c4b  cmp     byte ptr [rdi+19h], 2
0x180019c4f  jb      short loc_180019C6D
0x180019c51  mov     edx, 15h
0x180019c56  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180019c5d  mov     rcx, [rdi+10h]
0x180019c61  call    WPP_SF_
0x180019c66  mov     rdi, cs:WPP_GLOBAL_Control
0x180019c6d  cmp     rdi, r13
0x180019c70  jz      short loc_180019C94
0x180019c72  test    byte ptr [rdi+1Ch], 1
0x180019c76  jz      short loc_180019C94
0x180019c78  cmp     byte ptr [rdi+19h], 6
0x180019c7c  jb      short loc_180019C94
0x180019c7e  mov     edx, 16h
0x180019c83  mov     rcx, [rdi+10h]
0x180019c87  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180019c8e  call    WPP_SF_
0x180019c93  nop
0x180019c94  lea     rcx, [rsp+8F0h+var_8A8]; this
  ... truncated ...
```
