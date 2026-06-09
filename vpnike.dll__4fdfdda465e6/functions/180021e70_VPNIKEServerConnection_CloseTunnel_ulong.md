# VPNIKEServerConnection::CloseTunnel(ulong)

- ea: `0x180021e70`
- end: `0x1800221a3`
- name: `?CloseTunnel@VPNIKEServerConnection@@UEAAKK@Z`
- size: `819`
- prototype: `__int64 __fastcall(void **this, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x1800077bc`
- `0x1800131c8`
- `0x180021e70`
- `0x180023db4`
- `0x18002e6f4`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `fwpuclnt!FwpmNetEventUnsubscribe0` at `0x180022111`
- `fwpuclnt!FwpmNetEventUnsubscribe0` at `0x180022111`

## string_xrefs

- `0x180021feb`: `ERROR_INVALID_OPERATION:CloseTunnel already called for this connection.`

## pseudocode

```c
__int64 __fastcall VPNIKEServerConnection::CloseTunnel(void **this, unsigned int a2)
{
  unsigned int v4; // edi
  char v5; // al
  _DWORD *v6; // rax
  void *v7; // rdx
  __int128 *v8; // r9
  unsigned int v9; // ebx
  _DWORD *v10; // rax
  void *v11; // rdx
  __int128 *v12; // r9
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  signed int v16; // eax
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE engineHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h]
  __int128 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+74h] [rbp-8Ch]
  __int128 v26; // [rsp+78h] [rbp-88h] BYREF
  int v27; // [rsp+88h] [rbp-78h] BYREF
  __int128 v28; // [rsp+8Ch] [rbp-74h]
  __int128 v29; // [rsp+9Ch] [rbp-64h]
  int v30; // [rsp+ACh] [rbp-54h]
  int v31; // [rsp+B0h] [rbp-50h] BYREF
  char v32[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, a2);
  }
  v18 = 0;
  engineHandle = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v26 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v4 = -1;
  v24 = -1;
  v25 = 0;
  v5 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v20,
      L"VPNIKEServerConnection::CloseTunnel",
      &v18,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
    v5 = byte_1800AA941;
  }
  if ( ((_DWORD)this[19] & 0x800) == 0 )
  {
    VPNIKEConnection::UpdateConnectionState((VPNIKEConnection *)this, 0x800u);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      v10 = this[14];
      if ( v10 && *((_QWORD *)v10 + 2) )
        v4 = v10[4];
      ConvertPortNoToString(&v27, v4);
      FormatRRASErrorString(&v31, L"Processing Close Tunnel with reason: %d", a2);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v11 = this[14];
        LODWORD(v12) = (_DWORD)v11 + 2120;
        if ( !v11 )
          v12 = &v26;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v31,
          (_DWORD)v12,
          ((unsigned __int64)v11 + 2686) & -(__int64)(v11 != 0),
          (__int64)&v27);
      }
    }
    if ( !this[27] || *((_DWORD *)this[14] + 1063) != 1 )
      goto LABEL_38;
    BFEHandler::GetBfeHandle(&engineHandle);
    if ( engineHandle )
    {
      v16 = FwpmNetEventUnsubscribe0(engineHandle, this[27]);
      if ( v16 >= 0 )
        goto LABEL_38;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        goto LABEL_38;
      }
      v14 = 56;
      v15 = (unsigned int)v16;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        goto LABEL_38;
      }
      v14 = 55;
      v15 = 0;
    }
    WPP_SF_d(v13[2], v14, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, v15);
LABEL_38:
    (*((void (__fastcall **)(void **, __int64))*this + 18))(this, 2);
    VPNIKEServerConnection::NotifyOnDisconnectCleanupComplete((VPNIKEServerConnection *)this, a2);
    v9 = v18;
    goto LABEL_39;
  }
  if ( (v5 & 4) != 0 )
  {
    LOWORD(v27) = 0;
    v6 = this[14];
    if ( v6 && *((_QWORD *)v6 + 2) )
      v4 = v6[4];
    ConvertPortNoToString(&v27, v4);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v7 = this[14];
      LODWORD(v8) = (_DWORD)v7 + 2120;
      if ( !v7 )
        v8 = &v26;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)L"ERROR_INVALID_OPERATION:CloseTunnel already called for this connection.",
        (_DWORD)v8,
        ((unsigned __int64)v7 + 2686) & -(__int64)(v7 != 0),
        (__int64)&v27);
    }
  }
  v9 = 4317;
  v18 = 4317;
LABEL_39:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v20);
  return v9;
}

```

## disassembly

```asm
0x180021e70  mov     [rsp-8+arg_10], rbx
0x180021e75  mov     [rsp-8+arg_18], rsi
0x180021e7a  push    rbp
0x180021e7b  push    rdi
0x180021e7c  push    r12
0x180021e7e  lea     rbp, [rsp-7C0h]
0x180021e86  sub     rsp, 8C0h
0x180021e8d  mov     rax, cs:__security_cookie
0x180021e94  xor     rax, rsp
0x180021e97  mov     [rbp+7D0h+var_20], rax
0x180021e9e  mov     esi, edx
0x180021ea0  mov     rbx, rcx
0x180021ea3  lea     r12, WPP_GLOBAL_Control
0x180021eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021eb1  cmp     rcx, r12
0x180021eb4  jz      short loc_180021EDA
0x180021eb6  test    byte ptr [rcx+1Ch], 1
0x180021eba  jz      short loc_180021EDA
0x180021ebc  cmp     byte ptr [rcx+19h], 6
0x180021ec0  jb      short loc_180021EDA
0x180021ec2  mov     edx, 36h ; '6'
0x180021ec7  mov     r9d, esi
0x180021eca  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180021ed1  mov     rcx, [rcx+10h]
0x180021ed5  call    WPP_SF_d
0x180021eda  mov     [rsp+8D0h+var_8A0], 0
0x180021ee2  mov     [rsp+8D0h+engineHandle], 0
0x180021eeb  xor     eax, eax
0x180021eed  mov     [rbp+7D0h+var_820], eax
0x180021ef0  xor     edx, edx; Val
0x180021ef2  mov     r8d, 7FCh; Size
0x180021ef8  lea     rcx, [rbp+7D0h+var_81C]; void *
0x180021efc  call    memset_0
0x180021f01  xor     eax, eax
0x180021f03  mov     [rbp+7D0h+var_848], eax
0x180021f06  xorps   xmm0, xmm0
0x180021f09  movups  [rbp+7D0h+var_844], xmm0
0x180021f0d  movups  [rbp+7D0h+var_834], xmm0
0x180021f11  mov     [rbp+7D0h+var_824], eax
0x180021f14  movups  [rsp+8D0h+var_858], xmm0
0x180021f19  xorps   xmm1, xmm1
0x180021f1c  movdqu  [rsp+8D0h+var_888], xmm1
0x180021f22  mov     [rsp+8D0h+var_890], rax
0x180021f27  movdqu  [rsp+8D0h+var_878], xmm0
0x180021f2d  mov     [rsp+8D0h+var_868], rax
0x180021f32  or      edi, 0FFFFFFFFh
0x180021f35  mov     [rsp+8D0h+var_860], edi
0x180021f39  mov     [rsp+8D0h+var_85C], eax
0x180021f3d  mov     al, cs:byte_1800AA941
0x180021f43  test    al, 8
0x180021f45  jz      short loc_180021F73
0x180021f47  mov     rax, [rbx+70h]
0x180021f4b  mov     [rsp+8D0h+var_8B0], rax; void *
0x180021f50  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180021f57  lea     r8, [rsp+8D0h+var_8A0]; unsigned int *
0x180021f5c  lea     rdx, aVpnikeserverco_16; "VPNIKEServerConnection::CloseTunnel"
0x180021f63  lea     rcx, [rsp+8D0h+var_890]; this
0x180021f68  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180021f6d  mov     al, cs:byte_1800AA941
0x180021f73  mov     edx, 800h; unsigned int
0x180021f78  test    [rbx+98h], edx
0x180021f7e  jz      loc_180022013
0x180021f84  test    al, 4
0x180021f86  jz      short loc_180022005
0x180021f88  xor     eax, eax
0x180021f8a  mov     word ptr [rbp+7D0h+var_848], ax
0x180021f8e  mov     rax, [rbx+70h]
0x180021f92  test    rax, rax
0x180021f95  jz      short loc_180021FA1
0x180021f97  cmp     qword ptr [rax+10h], 0
0x180021f9c  jz      short loc_180021FA1
0x180021f9e  mov     edi, [rax+10h]
0x180021fa1  mov     edx, edi
0x180021fa3  lea     rcx, [rbp+7D0h+var_848]
0x180021fa7  call    ConvertPortNoToString
0x180021fac  test    cs:byte_1800AA941, 4
0x180021fb3  jz      short loc_180022005
0x180021fb5  mov     rdx, [rbx+70h]
0x180021fb9  mov     rax, rdx
0x180021fbc  lea     rcx, [rdx+0A7Eh]
0x180021fc3  neg     rax
0x180021fc6  sbb     r8, r8
0x180021fc9  and     r8, rcx
0x180021fcc  test    rdx, rdx
0x180021fcf  lea     r9, [rdx+848h]
0x180021fd6  jnz     short loc_180021FDD
0x180021fd8  lea     r9, [rsp+8D0h+var_858]
0x180021fdd  lea     rax, [rbp+7D0h+var_848]
0x180021fe1  mov     [rsp+8D0h+var_8A8], rax
0x180021fe6  mov     [rsp+8D0h+var_8B0], r8
0x180021feb  lea     r8, aErrorInvalidOp; "ERROR_INVALID_OPERATION:CloseTunnel alr"...
0x180021ff2  lea     rdx, RasVpnIkeParamTraceError
0x180021ff9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022000  call    McTemplateU0zjzz_EventWriteTransfer
0x180022005  mov     ebx, 10DDh
0x18002200a  mov     [rsp+8D0h+var_8A0], ebx
0x18002200e  jmp     loc_180022170
0x180022013  mov     rcx, rbx; this
0x180022016  call    ?UpdateConnectionState@VPNIKEConnection@@IEAAXK@Z; VPNIKEConnection::UpdateConnectionState(ulong)
0x18002201b  test    cs:byte_1800AA941, 8
0x180022022  jz      loc_1800220B9
0x180022028  xor     eax, eax
0x18002202a  mov     word ptr [rbp+7D0h+var_820], ax
0x18002202e  mov     word ptr [rbp+7D0h+var_848], ax
0x180022032  mov     rax, [rbx+70h]
0x180022036  test    rax, rax
0x180022039  jz      short loc_180022045
0x18002203b  cmp     qword ptr [rax+10h], 0
0x180022040  jz      short loc_180022045
0x180022042  mov     edi, [rax+10h]
0x180022045  mov     edx, edi
0x180022047  lea     rcx, [rbp+7D0h+var_848]
0x18002204b  call    ConvertPortNoToString
0x180022050  mov     r8d, esi
0x180022053  lea     rdx, aProcessingClos; "Processing Close Tunnel with reason: %d"
0x18002205a  lea     rcx, [rbp+7D0h+var_820]
0x18002205e  call    FormatRRASErrorString
0x180022063  test    cs:byte_1800AA941, 8
0x18002206a  jz      short loc_1800220B9
0x18002206c  mov     rdx, [rbx+70h]
0x180022070  mov     rax, rdx
0x180022073  lea     rcx, [rdx+0A7Eh]
0x18002207a  neg     rax
0x18002207d  sbb     r8, r8
0x180022080  and     r8, rcx
0x180022083  test    rdx, rdx
0x180022086  lea     r9, [rdx+848h]
0x18002208d  jnz     short loc_180022094
0x18002208f  lea     r9, [rsp+8D0h+var_858]
0x180022094  lea     rax, [rbp+7D0h+var_848]
0x180022098  mov     [rsp+8D0h+var_8A8], rax
0x18002209d  mov     [rsp+8D0h+var_8B0], r8
0x1800220a2  lea     r8, [rbp+7D0h+var_820]
0x1800220a6  lea     rdx, RasVpnIkeParamTraceInfo
0x1800220ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800220b4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800220b9  cmp     qword ptr [rbx+0D8h], 0
0x1800220c1  jz      loc_18002214B
0x1800220c7  mov     rax, [rbx+70h]
0x1800220cb  cmp     dword ptr [rax+109Ch], 1
0x1800220d2  jnz     short loc_18002214B
0x1800220d4  lea     rcx, [rsp+8D0h+engineHandle]; void **
0x1800220d9  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x1800220de  mov     rcx, [rsp+8D0h+engineHandle]; engineHandle
0x1800220e3  test    rcx, rcx
0x1800220e6  jnz     short loc_18002210A
0x1800220e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220ef  cmp     rcx, r12
0x1800220f2  jz      short loc_18002214B
0x1800220f4  test    byte ptr [rcx+1Ch], 1
0x1800220f8  jz      short loc_18002214B
0x1800220fa  cmp     byte ptr [rcx+19h], 6
0x1800220fe  jb      short loc_18002214B
0x180022100  mov     edx, 37h ; '7'
0x180022105  xor     r9d, r9d
0x180022108  jmp     short loc_18002213B
0x18002210a  mov     rdx, [rbx+0D8h]; eventsHandle
0x180022111  call    cs:__imp_FwpmNetEventUnsubscribe0
0x180022117  test    eax, eax
0x180022119  jns     short loc_18002214B
0x18002211b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022122  cmp     rcx, r12
0x180022125  jz      short loc_18002214B
0x180022127  test    byte ptr [rcx+1Ch], 1
0x18002212b  jz      short loc_18002214B
0x18002212d  cmp     byte ptr [rcx+19h], 6
0x180022131  jb      short loc_18002214B
0x180022133  mov     edx, 38h ; '8'
0x180022138  mov     r9d, eax
0x18002213b  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180022142  mov     rcx, [rcx+10h]
0x180022146  call    WPP_SF_d
0x18002214b  mov     rax, [rbx]
0x18002214e  mov     edx, 2
0x180022153  mov     rcx, rbx
0x180022156  mov     rax, [rax+90h]
0x18002215d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022162  mov     edx, esi; unsigned int
0x180022164  mov     rcx, rbx; this
0x180022167  call    ?NotifyOnDisconnectCleanupComplete@VPNIKEServerConnection@@IEAAXK@Z; VPNIKEServerConnection::NotifyOnDisconnectCleanupComplete(ulong)
0x18002216c  mov     ebx, [rsp+8D0h+var_8A0]
0x180022170  lea     rcx, [rsp+8D0h+var_890]; this
0x180022175  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18002217a  mov     eax, ebx
0x18002217c  mov     rcx, [rbp+7D0h+var_20]
0x180022183  xor     rcx, rsp; StackCookie
0x180022186  call    __security_check_cookie
0x18002218b  lea     r11, [rsp+8D0h+var_10]
0x180022193  mov     rbx, [r11+30h]
0x180022197  mov     rsi, [r11+38h]
0x18002219b  mov     rsp, r11
0x18002219e  pop     r12
0x1800221a0  pop     rdi
0x1800221a1  pop     rbp
0x1800221a2  retn
```
