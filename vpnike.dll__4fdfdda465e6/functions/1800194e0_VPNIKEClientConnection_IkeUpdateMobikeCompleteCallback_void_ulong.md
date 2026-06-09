# VPNIKEClientConnection::IkeUpdateMobikeCompleteCallback(void *,ulong)

- ea: `0x1800194e0`
- end: `0x180019795`
- name: `?IkeUpdateMobikeCompleteCallback@VPNIKEClientConnection@@SAXPEAXK@Z`
- size: `693`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x180007794`
- `0x1800194e0`
- `0x18001a8a0`
- `0x18001af98`
- `0x18001f10c`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019639`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019721`

## string_xrefs

- `0x1800195b5`: `VPNIKEClientConnection::IkeUpdateMobikeCompleteCallback`
- `0x1800195dc`: `IkeUpdateMobikeCompleteCallback invoked for invalid parameters. Ignoring callback.`
- `0x18001967f`: `IkeUpdateMobikeCompleteCallback: Status:%d for TunnelID: %I64X`

## pseudocode

```c
void __fastcall VPNIKEClientConnection::IkeUpdateMobikeCompleteCallback(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2)
{
  PVOID *v4; // rbx
  unsigned int v5; // esi
  char v6; // al
  __int64 v7; // rdx
  PVOID v8; // rcx
  ULONG_PTR SpinCount; // rax
  ULONG_PTR v10; // rdx
  __int128 *v11; // r9
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
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
      L"VPNIKEClientConnection::IkeUpdateMobikeCompleteCallback",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v6 = byte_1800AA941;
  }
  if ( this )
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
        L"IkeUpdateMobikeCompleteCallback: Status:%d for TunnelID: %I64X",
        a2,
        *(_QWORD *)(this[2].SpinCount + 8));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v10 = this[2].SpinCount;
        LODWORD(v11) = v10 + 2120;
        if ( !v10 )
          v11 = &v18;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v23,
          (_DWORD)v11,
          (v10 + 2686) & -(__int64)(v10 != 0),
          (__int64)&v19);
      }
    }
    VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 0x100u);
    VPNIKEClientConnection::NotifyUpdateConnectionStatus((VPNIKEClientConnection *)this, a2);
    if ( (this[3].SpinCount & 0x1800) != 0 && (this[3].SpinCount & 0x4000) == 0 )
      VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete((VPNIKEClientConnection *)this);
    LeaveCriticalSection(this + 4);
    BaseConnection::DeleteRef((BaseConnection *)this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v7 = 29;
      v8 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
      goto LABEL_28;
    }
  }
  else
  {
    if ( (v6 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"IkeUpdateMobikeCompleteCallback invoked for invalid parameters. Ignoring callback.");
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    {
      v7 = 28;
      v8 = v4[2];
LABEL_28:
      WPP_SF_(v8, v7, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
}

```

## disassembly

```asm
0x1800194e0  mov     [rsp-8+arg_10], rbx
0x1800194e5  mov     [rsp-8+arg_18], rsi
0x1800194ea  push    rbp
0x1800194eb  push    rdi
0x1800194ec  push    r14
0x1800194ee  lea     rbp, [rsp-7C0h]
0x1800194f6  sub     rsp, 8C0h
0x1800194fd  mov     rax, cs:__security_cookie
0x180019504  xor     rax, rsp
0x180019507  mov     [rbp+7D0h+var_20], rax
0x18001950e  mov     r14d, edx
0x180019511  mov     rdi, rcx
0x180019514  lea     rax, WPP_GLOBAL_Control
0x18001951b  mov     rbx, cs:WPP_GLOBAL_Control
0x180019522  cmp     rbx, rax
0x180019525  jz      short loc_18001954F
0x180019527  test    byte ptr [rbx+1Ch], 1
0x18001952b  jz      short loc_18001954F
0x18001952d  cmp     byte ptr [rbx+19h], 6
0x180019531  jb      short loc_18001954F
0x180019533  mov     edx, 1Bh
0x180019538  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001953f  mov     rcx, [rbx+10h]
0x180019543  call    WPP_SF_
0x180019548  mov     rbx, cs:WPP_GLOBAL_Control
0x18001954f  xor     eax, eax
0x180019551  mov     [rbp+7D0h+var_820], eax
0x180019554  xor     edx, edx; Val
0x180019556  mov     r8d, 7FCh; Size
0x18001955c  lea     rcx, [rbp+7D0h+var_81C]; void *
0x180019560  call    memset_0
0x180019565  xor     eax, eax
0x180019567  mov     [rbp+7D0h+var_850], eax
0x18001956a  xorps   xmm0, xmm0
0x18001956d  movups  [rbp+7D0h+var_84C], xmm0
0x180019571  movups  [rbp+7D0h+var_83C], xmm0
0x180019575  mov     [rbp+7D0h+var_82C], eax
0x180019578  movups  [rsp+8D0h+var_860], xmm0
0x18001957d  xorps   xmm1, xmm1
0x180019580  movdqu  [rsp+8D0h+var_890], xmm1
0x180019586  mov     [rsp+8D0h+var_898], rax
0x18001958b  movdqu  [rsp+8D0h+var_880], xmm0
0x180019591  mov     [rsp+8D0h+var_870], rax
0x180019596  or      esi, 0FFFFFFFFh
0x180019599  mov     [rsp+8D0h+var_868], esi
0x18001959d  mov     [rsp+8D0h+var_864], eax
0x1800195a1  mov     al, cs:byte_1800AA941
0x1800195a7  test    al, 8
0x1800195a9  jz      short loc_1800195D3
0x1800195ab  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800195b2  xor     r8d, r8d; unsigned int *
0x1800195b5  lea     rdx, aVpnikeclientco; "VPNIKEClientConnection::IkeUpdateMobike"...
0x1800195bc  lea     rcx, [rsp+8D0h+var_898]; this
0x1800195c1  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800195c6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800195cd  mov     al, cs:byte_1800AA941
0x1800195d3  test    rdi, rdi
0x1800195d6  jnz     short loc_18001962F
0x1800195d8  test    al, 4
0x1800195da  jz      short loc_1800195FD
0x1800195dc  lea     r8, aIkeupdatemobik_0; "IkeUpdateMobikeCompleteCallback invoked"...
0x1800195e3  lea     rdx, RasVpnIkeTraceError
0x1800195ea  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800195f1  call    McTemplateU0z_EventWriteTransfer
0x1800195f6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800195fd  lea     rax, WPP_GLOBAL_Control
0x180019604  cmp     rbx, rax
0x180019607  jz      loc_180019764
0x18001960d  test    byte ptr [rbx+1Ch], 1
0x180019611  jz      loc_180019764
0x180019617  cmp     byte ptr [rbx+19h], 6
0x18001961b  jb      loc_180019764
0x180019621  mov     edx, 1Ch
0x180019626  mov     rcx, [rbx+10h]
0x18001962a  jmp     loc_180019757
0x18001962f  lea     rbx, [rdi+0A0h]
0x180019636  mov     rcx, rbx; lpCriticalSection
0x180019639  call    cs:__imp_EnterCriticalSection
0x18001963f  test    cs:byte_1800AA941, 8
0x180019646  jz      loc_1800196E5
0x18001964c  xor     eax, eax
0x18001964e  mov     word ptr [rbp+7D0h+var_820], ax
0x180019652  mov     word ptr [rbp+7D0h+var_850], ax
0x180019656  mov     rax, [rdi+70h]
0x18001965a  test    rax, rax
0x18001965d  jz      short loc_180019669
0x18001965f  cmp     qword ptr [rax+10h], 0
0x180019664  jz      short loc_180019669
0x180019666  mov     esi, [rax+10h]
0x180019669  mov     edx, esi
0x18001966b  lea     rcx, [rbp+7D0h+var_850]
0x18001966f  call    ConvertPortNoToString
0x180019674  mov     r9, [rdi+70h]
0x180019678  mov     r9, [r9+8]
0x18001967c  mov     r8d, r14d
0x18001967f  lea     rdx, aIkeupdatemobik; "IkeUpdateMobikeCompleteCallback: Status"...
0x180019686  lea     rcx, [rbp+7D0h+var_820]
0x18001968a  call    FormatRRASErrorString
0x18001968f  test    cs:byte_1800AA941, 8
0x180019696  jz      short loc_1800196E5
0x180019698  mov     rdx, [rdi+70h]
0x18001969c  mov     rax, rdx
0x18001969f  lea     rcx, [rdx+0A7Eh]
0x1800196a6  neg     rax
0x1800196a9  sbb     r8, r8
0x1800196ac  and     r8, rcx
0x1800196af  test    rdx, rdx
0x1800196b2  lea     r9, [rdx+848h]
0x1800196b9  jnz     short loc_1800196C0
0x1800196bb  lea     r9, [rsp+8D0h+var_860]
0x1800196c0  lea     rax, [rbp+7D0h+var_850]
0x1800196c4  mov     [rsp+8D0h+var_8A8], rax
0x1800196c9  mov     [rsp+8D0h+var_8B0], r8
0x1800196ce  lea     r8, [rbp+7D0h+var_820]
0x1800196d2  lea     rdx, RasVpnIkeParamTraceInfo
0x1800196d9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800196e0  call    McTemplateU0zjzz_EventWriteTransfer
0x1800196e5  mov     edx, 100h; unsigned int
0x1800196ea  mov     rcx, rdi; this
0x1800196ed  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x1800196f2  mov     edx, r14d; unsigned int
0x1800196f5  mov     rcx, rdi; this
0x1800196f8  call    ?NotifyUpdateConnectionStatus@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::NotifyUpdateConnectionStatus(ulong)
0x1800196fd  mov     eax, [rdi+98h]
0x180019703  test    eax, 1800h
0x180019708  setnz   dl
0x18001970b  bt      eax, 0Eh
0x18001970f  setnb   al
0x180019712  test    al, dl
0x180019714  jz      short loc_18001971E
0x180019716  mov     rcx, rdi; this
0x180019719  call    ?NotifyOnDisconnectCleanupComplete@VPNIKEClientConnection@@IEAAXXZ; VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete(void)
0x18001971e  mov     rcx, rbx; lpCriticalSection
0x180019721  call    cs:__imp_LeaveCriticalSection
0x180019727  mov     rcx, rdi; this
0x18001972a  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18001972f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019736  lea     rax, WPP_GLOBAL_Control
0x18001973d  cmp     rcx, rax
0x180019740  jz      short loc_180019764
0x180019742  test    byte ptr [rcx+1Ch], 1
0x180019746  jz      short loc_180019764
0x180019748  cmp     byte ptr [rcx+19h], 6
0x18001974c  jb      short loc_180019764
0x18001974e  mov     edx, 1Dh
0x180019753  mov     rcx, [rcx+10h]
0x180019757  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001975e  call    WPP_SF_
0x180019763  nop
0x180019764  lea     rcx, [rsp+8D0h+var_898]; this
0x180019769  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18001976e  mov     rcx, [rbp+7D0h+var_20]
0x180019775  xor     rcx, rsp; StackCookie
0x180019778  call    __security_check_cookie
0x18001977d  lea     r11, [rsp+8D0h+var_10]
0x180019785  mov     rbx, [r11+30h]
0x180019789  mov     rsi, [r11+38h]
0x18001978d  mov     rsp, r11
0x180019790  pop     r14
0x180019792  pop     rdi
0x180019793  pop     rbp
0x180019794  retn
```
