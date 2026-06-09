# VPNIKEClientConnection::IkeReauthCompleteCallback(void *,IPSEC_NEGOTIATION_STATUS0_ const *)

- ea: `0x180019220`
- end: `0x1800194d6`
- name: `?IkeReauthCompleteCallback@VPNIKEClientConnection@@SAXPEAXPEBUIPSEC_NEGOTIATION_STATUS0_@@@Z`
- size: `694`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct IPSEC_NEGOTIATION_STATUS0_ *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x180007794`
- `0x180019220`
- `0x18001a8a0`
- `0x18001ad44`
- `0x18001f10c`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019331`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001941a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001941a`

## string_xrefs

- `0x1800192f7`: `VPNIKEClientConnection::IkeReauthCompleteCallback`
- `0x180019456`: `IkeReauthCompleteCallback invoked for invalid parameters. Ignoring callback.`
- `0x180019379`: `IkeReauthCompleteCallback: Status:%d for TunnelID: %I64X`

## pseudocode

```c
void __fastcall VPNIKEClientConnection::IkeReauthCompleteCallback(
        struct _RTL_CRITICAL_SECTION *this,
        const struct IPSEC_NEGOTIATION_STATUS0_ *a2)
{
  PVOID *v4; // rbx
  unsigned int v5; // r14d
  char v6; // al
  ULONG_PTR SpinCount; // rax
  ULONG_PTR v8; // rdx
  __int128 *v9; // r9
  __int64 v10; // rdx
  PVOID v11; // rcx
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h]
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  int v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+6Ch] [rbp-94h]
  __int128 v18; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+80h] [rbp-80h] BYREF
  __int128 v20; // [rsp+84h] [rbp-7Ch]
  __int128 v21; // [rsp+94h] [rbp-6Ch]
  int v22; // [rsp+A4h] [rbp-5Ch]
  int v23; // [rsp+B0h] [rbp-50h] BYREF
  char v24[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v18 = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v5 = -1;
  v16 = -1;
  v17 = 0;
  v6 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"VPNIKEClientConnection::IkeReauthCompleteCallback",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v6 = byte_1800AA941;
  }
  if ( this && a2 )
  {
    EnterCriticalSection(this + 4);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      LOWORD(v19) = 0;
      SpinCount = this[2].SpinCount;
      if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
        v5 = *(_DWORD *)(SpinCount + 16);
      ConvertPortNoToString(&v19, v5);
      FormatRRASErrorString(
        &v23,
        L"IkeReauthCompleteCallback: Status:%d for TunnelID: %I64X",
        *(unsigned int *)a2,
        *(_QWORD *)(this[2].SpinCount + 8));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v8 = this[2].SpinCount;
        LODWORD(v9) = v8 + 2120;
        if ( !v8 )
          v9 = &v18;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v23,
          (_DWORD)v9,
          (v8 + 2686) & -(__int64)(v8 != 0),
          (__int64)&v19);
      }
    }
    VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 2u);
    VPNIKEClientConnection::NotifyRenegotiateStatus((VPNIKEClientConnection *)this, *(_DWORD *)a2);
    if ( (this[3].SpinCount & 0x1800) != 0 && (this[3].SpinCount & 0x4000) == 0 )
      VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete((VPNIKEClientConnection *)this);
    LeaveCriticalSection(this + 4);
    BaseConnection::DeleteRef((BaseConnection *)this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v10 = 35;
      v11 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_29:
      WPP_SF_(v11, v10, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    }
  }
  else
  {
    if ( (v6 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"IkeReauthCompleteCallback invoked for invalid parameters. Ignoring callback.");
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    {
      v10 = 34;
      v11 = v4[2];
      goto LABEL_29;
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
}

```

## disassembly

```asm
0x180019220  mov     [rsp-8+arg_10], rbx
0x180019225  mov     [rsp-8+arg_18], rsi
0x18001922a  push    rbp
0x18001922b  push    rdi
0x18001922c  push    r14
0x18001922e  lea     rbp, [rsp-7C0h]
0x180019236  sub     rsp, 8C0h
0x18001923d  mov     rax, cs:__security_cookie
0x180019244  xor     rax, rsp
0x180019247  mov     [rbp+7D0h+var_20], rax
0x18001924e  mov     rsi, rdx
0x180019251  mov     rdi, rcx
0x180019254  lea     rax, WPP_GLOBAL_Control
0x18001925b  mov     rbx, cs:WPP_GLOBAL_Control
0x180019262  cmp     rbx, rax
0x180019265  jz      short loc_18001928F
0x180019267  test    byte ptr [rbx+1Ch], 1
0x18001926b  jz      short loc_18001928F
0x18001926d  cmp     byte ptr [rbx+19h], 6
0x180019271  jb      short loc_18001928F
0x180019273  mov     edx, 21h ; '!'
0x180019278  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001927f  mov     rcx, [rbx+10h]
0x180019283  call    WPP_SF_
0x180019288  mov     rbx, cs:WPP_GLOBAL_Control
0x18001928f  xor     eax, eax
0x180019291  mov     [rbp+7D0h+var_820], eax
0x180019294  xor     edx, edx; Val
0x180019296  mov     r8d, 7FCh; Size
0x18001929c  lea     rcx, [rbp+7D0h+var_81C]; void *
0x1800192a0  call    memset_0
0x1800192a5  xor     eax, eax
0x1800192a7  mov     [rbp+7D0h+var_850], eax
0x1800192aa  xorps   xmm0, xmm0
0x1800192ad  movups  [rbp+7D0h+var_84C], xmm0
0x1800192b1  movups  [rbp+7D0h+var_83C], xmm0
0x1800192b5  mov     [rbp+7D0h+var_82C], eax
0x1800192b8  movups  [rsp+8D0h+var_860], xmm0
0x1800192bd  xorps   xmm1, xmm1
0x1800192c0  movdqu  [rsp+8D0h+var_890], xmm1
0x1800192c6  mov     [rsp+8D0h+var_898], rax
0x1800192cb  movdqu  [rsp+8D0h+var_880], xmm0
0x1800192d1  mov     [rsp+8D0h+var_870], rax
0x1800192d6  or      r14d, 0FFFFFFFFh
0x1800192da  mov     [rsp+8D0h+var_868], r14d
0x1800192df  mov     [rsp+8D0h+var_864], eax
0x1800192e3  mov     al, cs:byte_1800AA941
0x1800192e9  test    al, 8
0x1800192eb  jz      short loc_180019315
0x1800192ed  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800192f4  xor     r8d, r8d; unsigned int *
0x1800192f7  lea     rdx, aVpnikeclientco_11; "VPNIKEClientConnection::IkeReauthComple"...
0x1800192fe  lea     rcx, [rsp+8D0h+var_898]; this
0x180019303  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180019308  mov     rbx, cs:WPP_GLOBAL_Control
0x18001930f  mov     al, cs:byte_1800AA941
0x180019315  test    rdi, rdi
0x180019318  jz      loc_180019452
0x18001931e  test    rsi, rsi
0x180019321  jz      loc_180019452
0x180019327  lea     rbx, [rdi+0A0h]
0x18001932e  mov     rcx, rbx; lpCriticalSection
0x180019331  call    cs:__imp_EnterCriticalSection
0x180019337  test    cs:byte_1800AA941, 8
0x18001933e  jz      loc_1800193DF
0x180019344  xor     eax, eax
0x180019346  mov     word ptr [rbp+7D0h+var_820], ax
0x18001934a  mov     word ptr [rbp+7D0h+var_850], ax
0x18001934e  mov     rax, [rdi+70h]
0x180019352  test    rax, rax
0x180019355  jz      short loc_180019362
0x180019357  cmp     qword ptr [rax+10h], 0
0x18001935c  jz      short loc_180019362
0x18001935e  mov     r14d, [rax+10h]
0x180019362  mov     edx, r14d
0x180019365  lea     rcx, [rbp+7D0h+var_850]
0x180019369  call    ConvertPortNoToString
0x18001936e  mov     r9, [rdi+70h]
0x180019372  mov     r9, [r9+8]
0x180019376  mov     r8d, [rsi]
0x180019379  lea     rdx, aIkereauthcompl; "IkeReauthCompleteCallback: Status:%d fo"...
0x180019380  lea     rcx, [rbp+7D0h+var_820]
0x180019384  call    FormatRRASErrorString
0x180019389  test    cs:byte_1800AA941, 8
0x180019390  jz      short loc_1800193DF
0x180019392  mov     rdx, [rdi+70h]
0x180019396  mov     rax, rdx
0x180019399  lea     rcx, [rdx+0A7Eh]
0x1800193a0  neg     rax
0x1800193a3  sbb     r8, r8
0x1800193a6  and     r8, rcx
0x1800193a9  test    rdx, rdx
0x1800193ac  lea     r9, [rdx+848h]
0x1800193b3  jnz     short loc_1800193BA
0x1800193b5  lea     r9, [rsp+8D0h+var_860]
0x1800193ba  lea     rax, [rbp+7D0h+var_850]
0x1800193be  mov     [rsp+8D0h+var_8A8], rax
0x1800193c3  mov     [rsp+8D0h+var_8B0], r8
0x1800193c8  lea     r8, [rbp+7D0h+var_820]
0x1800193cc  lea     rdx, RasVpnIkeParamTraceInfo
0x1800193d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800193da  call    McTemplateU0zjzz_EventWriteTransfer
0x1800193df  mov     edx, 2; unsigned int
0x1800193e4  mov     rcx, rdi; this
0x1800193e7  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x1800193ec  mov     edx, [rsi]; unsigned int
0x1800193ee  mov     rcx, rdi; this
0x1800193f1  call    ?NotifyRenegotiateStatus@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::NotifyRenegotiateStatus(ulong)
0x1800193f6  mov     eax, [rdi+98h]
0x1800193fc  test    eax, 1800h
0x180019401  setnz   dl
0x180019404  bt      eax, 0Eh
0x180019408  setnb   al
0x18001940b  test    al, dl
0x18001940d  jz      short loc_180019417
0x18001940f  mov     rcx, rdi; this
0x180019412  call    ?NotifyOnDisconnectCleanupComplete@VPNIKEClientConnection@@IEAAXXZ; VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete(void)
0x180019417  mov     rcx, rbx; lpCriticalSection
0x18001941a  call    cs:__imp_LeaveCriticalSection
0x180019420  mov     rcx, rdi; this
0x180019423  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180019428  mov     rcx, cs:WPP_GLOBAL_Control
0x18001942f  lea     rax, WPP_GLOBAL_Control
0x180019436  cmp     rcx, rax
0x180019439  jz      short loc_1800194A5
0x18001943b  test    byte ptr [rcx+1Ch], 1
0x18001943f  jz      short loc_1800194A5
0x180019441  cmp     byte ptr [rcx+19h], 6
0x180019445  jb      short loc_1800194A5
0x180019447  mov     edx, 23h ; '#'
0x18001944c  mov     rcx, [rcx+10h]
0x180019450  jmp     short loc_180019498
0x180019452  test    al, 4
0x180019454  jz      short loc_180019477
0x180019456  lea     r8, aIkereauthcompl_0; "IkeReauthCompleteCallback invoked for i"...
0x18001945d  lea     rdx, RasVpnIkeTraceError
0x180019464  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001946b  call    McTemplateU0z_EventWriteTransfer
0x180019470  mov     rbx, cs:WPP_GLOBAL_Control
0x180019477  lea     rax, WPP_GLOBAL_Control
0x18001947e  cmp     rbx, rax
0x180019481  jz      short loc_1800194A5
0x180019483  test    byte ptr [rbx+1Ch], 1
0x180019487  jz      short loc_1800194A5
0x180019489  cmp     byte ptr [rbx+19h], 6
0x18001948d  jb      short loc_1800194A5
0x18001948f  mov     edx, 22h ; '"'
0x180019494  mov     rcx, [rbx+10h]
0x180019498  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001949f  call    WPP_SF_
0x1800194a4  nop
0x1800194a5  lea     rcx, [rsp+8D0h+var_898]; this
0x1800194aa  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800194af  mov     rcx, [rbp+7D0h+var_20]
0x1800194b6  xor     rcx, rsp; StackCookie
0x1800194b9  call    __security_check_cookie
0x1800194be  lea     r11, [rsp+8D0h+var_10]
0x1800194c6  mov     rbx, [r11+30h]
0x1800194ca  mov     rsi, [r11+38h]
0x1800194ce  mov     rsp, r11
0x1800194d1  pop     r14
0x1800194d3  pop     rdi
0x1800194d4  pop     rbp
0x1800194d5  retn
```
