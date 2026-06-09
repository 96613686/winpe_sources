# VPNIKEServerConnection::IkeUpdateMobikeCompleteCallback(void *,ulong)

- ea: `0x1800234a0`
- end: `0x1800236f1`
- name: `?IkeUpdateMobikeCompleteCallback@VPNIKEServerConnection@@KAXPEAXK@Z`
- size: `593`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007590`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x1800131c8`
- `0x1800234a0`
- `0x18002422c`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800235bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800235bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023685`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023685`

## string_xrefs

- `0x180023594`: `IkeUpdateMobikeCompleteCallback invoked for invalid parameters. Ignoring callback.`
- `0x180023605`: `IkeUpdateMobikeCompleteCallback: Status:%d for TunnelID: %I64X`
- `0x180023570`: `VPNIKEServerConnection::IkeUpdateMobikeCompleteCallback`

## pseudocode

```c
void __fastcall VPNIKEServerConnection::IkeUpdateMobikeCompleteCallback(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2)
{
  unsigned int v4; // r14d
  char v5; // al
  ULONG_PTR SpinCount; // rax
  ULONG_PTR v7; // rdx
  __int128 *v8; // r9
  __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v10; // [rsp+40h] [rbp-C0h]
  __int128 v11; // [rsp+50h] [rbp-B0h]
  __int64 v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+68h] [rbp-98h]
  int v14; // [rsp+6Ch] [rbp-94h]
  __int128 v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+80h] [rbp-80h] BYREF
  __int128 v17; // [rsp+84h] [rbp-7Ch]
  __int128 v18; // [rsp+94h] [rbp-6Ch]
  int v19; // [rsp+A4h] [rbp-5Ch]
  int v20; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v21[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, a2);
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v15 = 0;
  v10 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v4 = -1;
  v13 = -1;
  v14 = 0;
  v5 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v9,
      L"VPNIKEServerConnection::IkeUpdateMobikeCompleteCallback",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v5 = byte_1800AA941;
  }
  if ( this )
  {
    EnterCriticalSection(this + 4);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v20) = 0;
      LOWORD(v16) = 0;
      SpinCount = this[2].SpinCount;
      if ( SpinCount && *(_QWORD *)(SpinCount + 16) )
        v4 = *(_DWORD *)(SpinCount + 16);
      ConvertPortNoToString(&v16, v4);
      FormatRRASErrorString(
        &v20,
        L"IkeUpdateMobikeCompleteCallback: Status:%d for TunnelID: %I64X",
        a2,
        *(_QWORD *)(this[2].SpinCount + 8));
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v7 = this[2].SpinCount;
        LODWORD(v8) = v7 + 2120;
        if ( !v7 )
          v8 = &v15;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v20,
          (_DWORD)v8,
          (v7 + 2686) & -(__int64)(v7 != 0),
          (__int64)&v16);
      }
    }
    VPNIKEConnection::UpdateConnectionState((VPNIKEConnection *)this, 0x100u);
    VPNIKEServerConnection::NotifyUpdateConnectionStatus((VPNIKEServerConnection *)this, a2);
    LeaveCriticalSection(this + 4);
    BaseConnection::DeleteRef((BaseConnection *)this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
    }
  }
  else if ( (v5 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"IkeUpdateMobikeCompleteCallback invoked for invalid parameters. Ignoring callback.");
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v9);
}

```

## disassembly

```asm
0x1800234a0  mov     [rsp-8+arg_10], rbx
0x1800234a5  push    rbp
0x1800234a6  push    rsi
0x1800234a7  push    rdi
0x1800234a8  push    r13
0x1800234aa  push    r14
0x1800234ac  lea     rbp, [rsp-7C0h]
0x1800234b4  sub     rsp, 8C0h
0x1800234bb  mov     rax, cs:__security_cookie
0x1800234c2  xor     rax, rsp
0x1800234c5  mov     [rbp+7E0h+var_30], rax
0x1800234cc  mov     edi, edx
0x1800234ce  mov     rbx, rcx
0x1800234d1  lea     r13, WPP_GLOBAL_Control
0x1800234d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234df  cmp     rcx, r13
0x1800234e2  jz      short loc_180023508
0x1800234e4  test    byte ptr [rcx+1Ch], 1
0x1800234e8  jz      short loc_180023508
0x1800234ea  cmp     byte ptr [rcx+19h], 6
0x1800234ee  jb      short loc_180023508
0x1800234f0  mov     edx, 11h
0x1800234f5  mov     r9d, edi
0x1800234f8  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x1800234ff  mov     rcx, [rcx+10h]
0x180023503  call    WPP_SF_d
0x180023508  xor     eax, eax
0x18002350a  mov     [rbp+7E0h+var_830], eax
0x18002350d  xor     edx, edx; Val
0x18002350f  mov     r8d, 7FCh; Size
0x180023515  lea     rcx, [rbp+7E0h+var_82C]; void *
0x180023519  call    memset_0
0x18002351e  xor     eax, eax
0x180023520  mov     [rbp+7E0h+var_860], eax
0x180023523  xorps   xmm0, xmm0
0x180023526  movups  [rbp+7E0h+var_85C], xmm0
0x18002352a  movups  [rbp+7E0h+var_84C], xmm0
0x18002352e  mov     [rbp+7E0h+var_83C], eax
0x180023531  movups  [rsp+8E0h+var_870], xmm0
0x180023536  xorps   xmm1, xmm1
0x180023539  movdqu  [rsp+8E0h+var_8A0], xmm1
0x18002353f  mov     [rsp+8E0h+var_8A8], rax
0x180023544  movdqu  [rsp+8E0h+var_890], xmm0
0x18002354a  mov     [rsp+8E0h+var_880], rax
0x18002354f  or      r14d, 0FFFFFFFFh
0x180023553  mov     [rsp+8E0h+var_878], r14d
0x180023558  mov     [rsp+8E0h+var_874], eax
0x18002355c  mov     al, cs:byte_1800AA941
0x180023562  test    al, 8
0x180023564  jz      short loc_180023587
0x180023566  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002356d  xor     r8d, r8d; unsigned int *
0x180023570  lea     rdx, aVpnikeserverco_8; "VPNIKEServerConnection::IkeUpdateMobike"...
0x180023577  lea     rcx, [rsp+8E0h+var_8A8]; this
0x18002357c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180023581  mov     al, cs:byte_1800AA941
0x180023587  test    rbx, rbx
0x18002358a  jnz     short loc_1800235B3
0x18002358c  test    al, 4
0x18002358e  jz      loc_1800236C1
0x180023594  lea     r8, aIkeupdatemobik_0; "IkeUpdateMobikeCompleteCallback invoked"...
0x18002359b  lea     rdx, RasVpnIkeTraceError
0x1800235a2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800235a9  call    McTemplateU0z_EventWriteTransfer
0x1800235ae  jmp     loc_1800236C1
0x1800235b3  lea     rsi, [rbx+0A0h]
0x1800235ba  mov     rcx, rsi; lpCriticalSection
0x1800235bd  call    cs:__imp_EnterCriticalSection
0x1800235c3  test    cs:byte_1800AA941, 8
0x1800235ca  jz      loc_18002366B
0x1800235d0  xor     eax, eax
0x1800235d2  mov     word ptr [rbp+7E0h+var_830], ax
0x1800235d6  mov     word ptr [rbp+7E0h+var_860], ax
0x1800235da  mov     rax, [rbx+70h]
0x1800235de  test    rax, rax
0x1800235e1  jz      short loc_1800235EE
0x1800235e3  cmp     qword ptr [rax+10h], 0
0x1800235e8  jz      short loc_1800235EE
0x1800235ea  mov     r14d, [rax+10h]
0x1800235ee  mov     edx, r14d
0x1800235f1  lea     rcx, [rbp+7E0h+var_860]
0x1800235f5  call    ConvertPortNoToString
0x1800235fa  mov     r9, [rbx+70h]
0x1800235fe  mov     r9, [r9+8]
0x180023602  mov     r8d, edi
0x180023605  lea     rdx, aIkeupdatemobik; "IkeUpdateMobikeCompleteCallback: Status"...
0x18002360c  lea     rcx, [rbp+7E0h+var_830]
0x180023610  call    FormatRRASErrorString
0x180023615  test    cs:byte_1800AA941, 8
0x18002361c  jz      short loc_18002366B
0x18002361e  mov     rdx, [rbx+70h]
0x180023622  mov     rax, rdx
0x180023625  lea     rcx, [rdx+0A7Eh]
0x18002362c  neg     rax
0x18002362f  sbb     r8, r8
0x180023632  and     r8, rcx
0x180023635  test    rdx, rdx
0x180023638  lea     r9, [rdx+848h]
0x18002363f  jnz     short loc_180023646
0x180023641  lea     r9, [rsp+8E0h+var_870]
0x180023646  lea     rax, [rbp+7E0h+var_860]
0x18002364a  mov     [rsp+8E0h+var_8B8], rax
0x18002364f  mov     [rsp+8E0h+var_8C0], r8
0x180023654  lea     r8, [rbp+7E0h+var_830]
0x180023658  lea     rdx, RasVpnIkeParamTraceInfo
0x18002365f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180023666  call    McTemplateU0zjzz_EventWriteTransfer
0x18002366b  mov     edx, 100h; unsigned int
0x180023670  mov     rcx, rbx; this
0x180023673  call    ?UpdateConnectionState@VPNIKEConnection@@IEAAXK@Z; VPNIKEConnection::UpdateConnectionState(ulong)
0x180023678  mov     edx, edi; unsigned int
0x18002367a  mov     rcx, rbx; this
0x18002367d  call    ?NotifyUpdateConnectionStatus@VPNIKEServerConnection@@IEAAXK@Z; VPNIKEServerConnection::NotifyUpdateConnectionStatus(ulong)
0x180023682  mov     rcx, rsi; lpCriticalSection
0x180023685  call    cs:__imp_LeaveCriticalSection
0x18002368b  mov     rcx, rbx; this
0x18002368e  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180023693  mov     rcx, cs:WPP_GLOBAL_Control
0x18002369a  cmp     rcx, r13
0x18002369d  jz      short loc_1800236C1
0x18002369f  test    byte ptr [rcx+1Ch], 1
0x1800236a3  jz      short loc_1800236C1
0x1800236a5  cmp     byte ptr [rcx+19h], 6
0x1800236a9  jb      short loc_1800236C1
0x1800236ab  mov     edx, 12h
0x1800236b0  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x1800236b7  mov     rcx, [rcx+10h]
0x1800236bb  call    WPP_SF_
0x1800236c0  nop
0x1800236c1  lea     rcx, [rsp+8E0h+var_8A8]; this
0x1800236c6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800236cb  mov     rcx, [rbp+7E0h+var_30]
0x1800236d2  xor     rcx, rsp; StackCookie
0x1800236d5  call    __security_check_cookie
0x1800236da  mov     rbx, [rsp+8E0h+arg_10]
0x1800236e2  add     rsp, 8C0h
0x1800236e9  pop     r14
0x1800236eb  pop     r13
0x1800236ed  pop     rdi
0x1800236ee  pop     rsi
0x1800236ef  pop     rbp
0x1800236f0  retn
```
