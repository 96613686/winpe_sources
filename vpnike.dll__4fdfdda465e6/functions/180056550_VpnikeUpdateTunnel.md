# VpnikeUpdateTunnel

- ea: `0x180056550`
- end: `0x180056878`
- name: `VpnikeUpdateTunnel`
- size: `808`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007590`
- `0x1800077bc`
- `0x180007a0c`
- `0x1800509f0`
- `0x180056550`
- `0x18005d9ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800566f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800566f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056710`
- `RPCRT4!RpcRaiseException` at `0x18005680e`
- `RPCRT4!RpcRaiseException` at `0x18005680e`

## string_xrefs

- `0x18005662e`: `VpnikeUpdateTunnel`

## pseudocode

```c
__int64 __fastcall VpnikeUpdateTunnel(__int64 a1, __int64 a2, struct _IKETUNNEL_PARAMETERS_ *a3)
{
  PVOID *v5; // rbx
  unsigned int v6; // edi
  char v7; // al
  __int16 v8; // cx
  struct _RTL_CRITICAL_SECTION *v9; // rax
  BaseConnection *v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v15; // [rsp+30h] [rbp-D0h]
  __int128 v16; // [rsp+40h] [rbp-C0h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  int v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+5Ch] [rbp-A4h]
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  v6 = 13;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v7 = byte_1800AA941;
  v14 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  v15 = 0;
  v16 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"VpnikeUpdateTunnel",
      &v13,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v7 = byte_1800AA941;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    v8 = *(_WORD *)a3;
    if ( *(_WORD *)a3 == *((_WORD *)a3 + 10) && (v8 == 2 || v8 == 23) )
    {
      if ( (v7 & 8) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"Tunnel ID: 0x%I64X", a2);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v20);
      }
      LogIkeTunnelParams(a3);
      v9 = (struct _RTL_CRITICAL_SECTION *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)VpnIkeProtocolEngine
                                                                                         + 1)
                                                                                      + 40LL))(
                                             *((_QWORD *)VpnIkeProtocolEngine + 1),
                                             a2);
      v10 = (BaseConnection *)v9;
      if ( v9 )
      {
        v11 = v9 + 4;
        EnterCriticalSection(v9 + 4);
        v13 = (*(__int64 (__fastcall **)(BaseConnection *, struct _IKETUNNEL_PARAMETERS_ *))(*(_QWORD *)v10 + 88LL))(
                v10,
                a3);
        LeaveCriticalSection(v11);
        BaseConnection::DeleteRef(v10);
LABEL_23:
        v6 = v13;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_27;
      }
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"Unable to get VPNIKEConnection handle for ConnectionId: %d", (unsigned int)a2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v20);
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      v6 = 837;
      v13 = 837;
    }
    else
    {
      v13 = 13;
      if ( (v7 & 4) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"Invalid Data: vpnIkeTunnelParams");
        goto LABEL_23;
      }
    }
LABEL_28:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    {
      WPP_SF_d(v5[2], 14, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, v6);
      v6 = v13;
    }
    RpcRaiseException(v6);
  }
  if ( (v7 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"Invalid Parameter");
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = 87;
  v13 = 87;
LABEL_27:
  if ( v6 )
    goto LABEL_28;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 15, &WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return 0;
}

```

## disassembly

```asm
0x180056550  mov     [rsp-8+arg_0], rbx
0x180056555  mov     [rsp-8+arg_18], rsi
0x18005655a  push    rbp
0x18005655b  push    rdi
0x18005655c  push    r14
0x18005655e  lea     rbp, [rsp-770h]
0x180056566  sub     rsp, 870h
0x18005656d  mov     rax, cs:__security_cookie
0x180056574  xor     rax, rsp
0x180056577  mov     [rbp+780h+var_20], rax
0x18005657e  mov     r14, r8
0x180056581  mov     rsi, rdx
0x180056584  mov     rbx, cs:WPP_GLOBAL_Control
0x18005658b  lea     rax, WPP_GLOBAL_Control
0x180056592  mov     edi, 0Dh
0x180056597  cmp     rbx, rax
0x18005659a  jz      short loc_1800565C4
0x18005659c  test    byte ptr [rbx+1Ch], 1
0x1800565a0  jz      short loc_1800565C4
0x1800565a2  cmp     byte ptr [rbx+19h], 6
0x1800565a6  jb      short loc_1800565C4
0x1800565a8  mov     rcx, [rbx+10h]
0x1800565ac  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800565b3  mov     edx, edi
0x1800565b5  mov     r9, rsi
0x1800565b8  call    WPP_SF_q
0x1800565bd  mov     rbx, cs:WPP_GLOBAL_Control
0x1800565c4  xor     eax, eax
0x1800565c6  mov     [rsp+880h+var_860], 0
0x1800565ce  xor     edx, edx; Val
0x1800565d0  mov     [rsp+880h+var_820], eax
0x1800565d4  mov     r8d, 7FCh; Size
0x1800565da  lea     rcx, [rsp+880h+var_81C]; void *
0x1800565df  call    memset_0
0x1800565e4  mov     al, cs:byte_1800AA941
0x1800565ea  xorps   xmm0, xmm0
0x1800565ed  mov     [rsp+880h+var_858], 0
0x1800565f6  xorps   xmm1, xmm1
0x1800565f9  mov     [rsp+880h+var_830], 0
0x180056602  mov     [rsp+880h+var_828], 0FFFFFFFFh
0x18005660a  mov     [rsp+880h+var_824], 0
0x180056612  movdqu  [rsp+880h+var_850], xmm0
0x180056618  movdqu  [rsp+880h+var_840], xmm1
0x18005661e  test    al, 8
0x180056620  jz      short loc_18005664C
0x180056622  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180056629  lea     r8, [rsp+880h+var_860]; unsigned int *
0x18005662e  lea     rdx, aVpnikeupdatetu; "VpnikeUpdateTunnel"
0x180056635  lea     rcx, [rsp+880h+var_858]; this
0x18005663a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005663f  mov     al, cs:byte_1800AA941
0x180056645  mov     rbx, cs:WPP_GLOBAL_Control
0x18005664c  test    rsi, rsi
0x18005664f  jz      loc_1800567A6
0x180056655  test    r14, r14
0x180056658  jz      loc_1800567A6
0x18005665e  movzx   ecx, word ptr [r14]
0x180056662  cmp     cx, [r14+14h]
0x180056667  jnz     loc_180056777
0x18005666d  cmp     cx, 2
0x180056671  jz      short loc_18005667D
0x180056673  cmp     cx, 17h
0x180056677  jnz     loc_180056777
0x18005667d  test    al, 8
0x18005667f  jz      short loc_1800566BD
0x180056681  xor     eax, eax
0x180056683  lea     rdx, aTunnelId0xI64x; "Tunnel ID: 0x%I64X"
0x18005668a  mov     r8, rsi
0x18005668d  mov     word ptr [rsp+880h+var_820], ax
0x180056692  lea     rcx, [rsp+880h+var_820]
0x180056697  call    FormatRRASErrorString
0x18005669c  test    cs:byte_1800AA941, 8
0x1800566a3  jz      short loc_1800566BD
0x1800566a5  lea     r8, [rsp+880h+var_820]
0x1800566aa  lea     rdx, RasVpnIkeTraceInfo
0x1800566b1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800566b8  call    McTemplateU0z_EventWriteTransfer
0x1800566bd  mov     rcx, r14; struct _IKETUNNEL_PARAMETERS_ *
0x1800566c0  call    ?LogIkeTunnelParams@@YAXPEAU_IKETUNNEL_PARAMETERS_@@@Z; LogIkeTunnelParams(_IKETUNNEL_PARAMETERS_ *)
0x1800566c5  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800566cc  mov     rdx, rsi
0x1800566cf  mov     rcx, [rax+8]
0x1800566d3  mov     rax, [rcx]
0x1800566d6  mov     rax, [rax+28h]
0x1800566da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566df  mov     rdi, rax
0x1800566e2  test    rax, rax
0x1800566e5  jz      short loc_180056720
0x1800566e7  lea     rbx, [rax+0A0h]
0x1800566ee  mov     rcx, rbx; lpCriticalSection
0x1800566f1  call    cs:__imp_EnterCriticalSection
0x1800566f7  mov     r8, [rdi]
0x1800566fa  mov     rdx, r14
0x1800566fd  mov     rcx, rdi
0x180056700  mov     rax, [r8+58h]
0x180056704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056709  mov     rcx, rbx; lpCriticalSection
0x18005670c  mov     [rsp+880h+var_860], eax
0x180056710  call    cs:__imp_LeaveCriticalSection
0x180056716  mov     rcx, rdi; this
0x180056719  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18005671e  jmp     short loc_180056799
0x180056720  test    cs:byte_1800AA941, 4
0x180056727  jz      short loc_180056765
0x180056729  xor     eax, eax
0x18005672b  mov     r8d, esi
0x18005672e  lea     rdx, aUnableToGetVpn_0; "Unable to get VPNIKEConnection handle f"...
0x180056735  mov     word ptr [rsp+880h+var_820], ax
0x18005673a  lea     rcx, [rsp+880h+var_820]
0x18005673f  call    FormatRRASErrorString
0x180056744  test    cs:byte_1800AA941, 4
0x18005674b  jz      short loc_180056765
0x18005674d  lea     r8, [rsp+880h+var_820]
0x180056752  lea     rdx, RasVpnIkeTraceError
0x180056759  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056760  call    McTemplateU0z_EventWriteTransfer
0x180056765  mov     rbx, cs:WPP_GLOBAL_Control
0x18005676c  mov     edi, 345h
0x180056771  mov     [rsp+880h+var_860], edi
0x180056775  jmp     short loc_1800567D8
0x180056777  mov     [rsp+880h+var_860], edi
0x18005677b  test    al, 4
0x18005677d  jz      short loc_1800567D8
0x18005677f  lea     r8, aInvalidDataVpn; "Invalid Data: vpnIkeTunnelParams"
0x180056786  lea     rdx, RasVpnIkeTraceError
0x18005678d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056794  call    McTemplateU0z_EventWriteTransfer
0x180056799  mov     edi, [rsp+880h+var_860]
0x18005679d  mov     rbx, cs:WPP_GLOBAL_Control
0x1800567a4  jmp     short loc_1800567D4
0x1800567a6  test    al, 4
0x1800567a8  jz      short loc_1800567CB
0x1800567aa  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x1800567b1  lea     rdx, RasVpnIkeTraceError
0x1800567b8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800567bf  call    McTemplateU0z_EventWriteTransfer
0x1800567c4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800567cb  mov     edi, 57h ; 'W'
0x1800567d0  mov     [rsp+880h+var_860], edi
0x1800567d4  test    edi, edi
0x1800567d6  jz      short loc_180056815
0x1800567d8  lea     rax, WPP_GLOBAL_Control
0x1800567df  cmp     rbx, rax
0x1800567e2  jz      short loc_18005680C
0x1800567e4  test    byte ptr [rbx+1Ch], 1
0x1800567e8  jz      short loc_18005680C
0x1800567ea  cmp     byte ptr [rbx+19h], 6
0x1800567ee  jb      short loc_18005680C
0x1800567f0  mov     rcx, [rbx+10h]
0x1800567f4  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x1800567fb  mov     edx, 0Eh
0x180056800  mov     r9d, edi
0x180056803  call    WPP_SF_d
0x180056808  mov     edi, [rsp+880h+var_860]
0x18005680c  mov     ecx, edi; exception
0x18005680e  call    cs:__imp_RpcRaiseException
0x180056814  int     3; Trap to Debugger
0x180056815  lea     rax, WPP_GLOBAL_Control
0x18005681c  cmp     rbx, rax
0x18005681f  jz      short loc_180056845
0x180056821  test    byte ptr [rbx+1Ch], 1
0x180056825  jz      short loc_180056845
0x180056827  cmp     byte ptr [rbx+19h], 6
0x18005682b  jb      short loc_180056845
0x18005682d  mov     rcx, [rbx+10h]
0x180056831  lea     r8, WPP_47fbe1c0916b3209fa6d6edae468283f_Traceguids
0x180056838  mov     edx, 0Fh
0x18005683d  xor     r9d, r9d
0x180056840  call    WPP_SF_d
0x180056845  lea     rcx, [rsp+880h+var_858]; this
0x18005684a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005684f  xor     eax, eax
0x180056851  mov     rcx, [rbp+780h+var_20]
0x180056858  xor     rcx, rsp; StackCookie
0x18005685b  call    __security_check_cookie
0x180056860  lea     r11, [rsp+880h+var_10]
0x180056868  mov     rbx, [r11+20h]
0x18005686c  mov     rsi, [r11+38h]
0x180056870  mov     rsp, r11
0x180056873  pop     r14
0x180056875  pop     rdi
0x180056876  pop     rbp
0x180056877  retn
```
