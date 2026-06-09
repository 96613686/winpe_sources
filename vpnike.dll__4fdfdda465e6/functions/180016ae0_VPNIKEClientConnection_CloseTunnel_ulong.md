# VPNIKEClientConnection::CloseTunnel(ulong)

- ea: `0x180016ae0`
- end: `0x180016f40`
- name: `?CloseTunnel@VPNIKEClientConnection@@UEAAKK@Z`
- size: `1120`
- prototype: `__int64 __fastcall(void **this, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x1800077bc`
- `0x180016ae0`
- `0x18001a8a0`
- `0x18001f10c`
- `0x18002e6f4`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `fwpuclnt!FwpmNetEventUnsubscribe0` at `0x180016e5d`
- `fwpuclnt!FwpmNetEventUnsubscribe0` at `0x180016e5d`

## string_xrefs

- `0x180016c6e`: `ERROR_INVALID_OPERATION:CloseTunnel already called for this connection.`

## pseudocode

```c
__int64 __fastcall VPNIKEClientConnection::CloseTunnel(void **this, unsigned int a2)
{
  PVOID *v4; // rbx
  unsigned int v5; // esi
  char v6; // al
  _DWORD *v7; // rax
  void *v8; // rdx
  __int128 *v9; // r9
  _QWORD *v10; // rax
  __int64 v11; // rdx
  void *v12; // rdx
  __int128 *v13; // r9
  _DWORD *v14; // rax
  void *v15; // rdx
  __int128 *v16; // r9
  signed int v17; // eax
  unsigned int v18; // ebx
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE engineHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h]
  __int128 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+74h] [rbp-8Ch]
  __int128 v28; // [rsp+78h] [rbp-88h] BYREF
  int v29; // [rsp+88h] [rbp-78h] BYREF
  __int128 v30; // [rsp+8Ch] [rbp-74h]
  __int128 v31; // [rsp+9Ch] [rbp-64h]
  int v32; // [rsp+ACh] [rbp-54h]
  int v33; // [rsp+B0h] [rbp-50h] BYREF
  char v34[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v20 = 0;
  engineHandle = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v5 = -1;
  v26 = -1;
  v27 = 0;
  v6 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v22,
      L"VPNIKEClientConnection::CloseTunnel",
      &v20,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v6 = byte_1800AA941;
  }
  if ( ((_DWORD)this[19] & 0x800) != 0 )
  {
    if ( (v6 & 4) != 0 )
    {
      LOWORD(v29) = 0;
      v7 = this[14];
      if ( v7 && *((_QWORD *)v7 + 2) )
        v5 = v7[4];
      ConvertPortNoToString(&v29, v5);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v8 = this[14];
        LODWORD(v9) = (_DWORD)v8 + 2120;
        if ( !v8 )
          v9 = &v28;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"ERROR_INVALID_OPERATION:CloseTunnel already called for this connection.",
          (_DWORD)v9,
          ((unsigned __int64)v8 + 2686) & -(__int64)(v8 != 0),
          (__int64)&v29);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v20 = 4317;
  }
  else
  {
    VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 0x800u);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v33) = 0;
      LOWORD(v29) = 0;
      v10 = this[14];
      if ( v10 && v10[2] )
        v11 = *((unsigned int *)v10 + 4);
      else
        v11 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v29, v11);
      FormatRRASErrorString(&v33, L"Processing Close Tunnel with reason: %d", a2);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v12 = this[14];
        LODWORD(v13) = (_DWORD)v12 + 2120;
        if ( !v12 )
          v13 = &v28;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v33,
          (_DWORD)v13,
          ((unsigned __int64)v12 + 2686) & -(__int64)(v12 != 0),
          (__int64)&v29);
      }
    }
    if ( this[27] && *((_DWORD *)this[14] + 1063) == 1 )
    {
      BFEHandler::GetBfeHandle(&engineHandle);
      if ( engineHandle )
      {
        v17 = FwpmNetEventUnsubscribe0(engineHandle, this[27]);
        if ( v17 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids,
            (unsigned int)v17);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, 0);
        }
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v33) = 0;
          LOWORD(v29) = 0;
          v14 = this[14];
          if ( v14 && *((_QWORD *)v14 + 2) )
            v5 = v14[4];
          ConvertPortNoToString(&v29, v5);
          FormatRRASErrorString(&v33, L"Error BFEHandle Status = %!WINERROR!: %d", 0);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v15 = this[14];
            LODWORD(v16) = (_DWORD)v15 + 2120;
            if ( !v15 )
              v16 = &v28;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v33,
              (_DWORD)v16,
              ((unsigned __int64)v15 + 2686) & -(__int64)(v15 != 0),
              (__int64)&v29);
          }
        }
      }
    }
    *((_DWORD *)this + 90) = a2;
    (*((void (__fastcall **)(void **, __int64))*this + 18))(this, 2);
    if ( ((_DWORD)this[19] & 0x8000) == 0 )
      VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete((VPNIKEClientConnection *)this);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 59, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, v20);
  v18 = v20;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
  return v18;
}

```

## disassembly

```asm
0x180016ae0  mov     [rsp-8+arg_10], rbx
0x180016ae5  mov     [rsp-8+arg_18], rsi
0x180016aea  push    rbp
0x180016aeb  push    rdi
0x180016aec  push    r14
0x180016aee  lea     rbp, [rsp-7C0h]
0x180016af6  sub     rsp, 8C0h
0x180016afd  mov     rax, cs:__security_cookie
0x180016b04  xor     rax, rsp
0x180016b07  mov     [rbp+7D0h+var_20], rax
0x180016b0e  mov     r14d, edx
0x180016b11  mov     rdi, rcx
0x180016b14  lea     rax, WPP_GLOBAL_Control
0x180016b1b  mov     rbx, cs:WPP_GLOBAL_Control
0x180016b22  cmp     rbx, rax
0x180016b25  jz      short loc_180016B52
0x180016b27  test    byte ptr [rbx+1Ch], 1
0x180016b2b  jz      short loc_180016B52
0x180016b2d  cmp     byte ptr [rbx+19h], 6
0x180016b31  jb      short loc_180016B52
0x180016b33  mov     edx, 38h ; '8'
0x180016b38  mov     r9d, r14d
0x180016b3b  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180016b42  mov     rcx, [rbx+10h]
0x180016b46  call    WPP_SF_d
0x180016b4b  mov     rbx, cs:WPP_GLOBAL_Control
0x180016b52  mov     [rsp+8D0h+var_8A0], 0
0x180016b5a  mov     [rsp+8D0h+engineHandle], 0
0x180016b63  xor     eax, eax
0x180016b65  mov     [rbp+7D0h+var_820], eax
0x180016b68  xor     edx, edx; Val
0x180016b6a  mov     r8d, 7FCh; Size
0x180016b70  lea     rcx, [rbp+7D0h+var_81C]; void *
0x180016b74  call    memset_0
0x180016b79  xor     eax, eax
0x180016b7b  mov     [rbp+7D0h+var_848], eax
0x180016b7e  xorps   xmm0, xmm0
0x180016b81  movups  [rbp+7D0h+var_844], xmm0
0x180016b85  movups  [rbp+7D0h+var_834], xmm0
0x180016b89  mov     [rbp+7D0h+var_824], eax
0x180016b8c  movups  [rsp+8D0h+var_858], xmm0
0x180016b91  xorps   xmm1, xmm1
0x180016b94  movdqu  [rsp+8D0h+var_888], xmm1
0x180016b9a  mov     [rsp+8D0h+var_890], rax
0x180016b9f  movdqu  [rsp+8D0h+var_878], xmm0
0x180016ba5  mov     [rsp+8D0h+var_868], rax
0x180016baa  or      esi, 0FFFFFFFFh
0x180016bad  mov     [rsp+8D0h+var_860], esi
0x180016bb1  mov     [rsp+8D0h+var_85C], eax
0x180016bb5  mov     al, cs:byte_1800AA941
0x180016bbb  test    al, 8
0x180016bbd  jz      short loc_180016BF2
0x180016bbf  mov     rax, [rdi+70h]
0x180016bc3  mov     [rsp+8D0h+var_8B0], rax; void *
0x180016bc8  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180016bcf  lea     r8, [rsp+8D0h+var_8A0]; unsigned int *
0x180016bd4  lea     rdx, aVpnikeclientco_1; "VPNIKEClientConnection::CloseTunnel"
0x180016bdb  lea     rcx, [rsp+8D0h+var_890]; this
0x180016be0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180016be5  mov     rbx, cs:WPP_GLOBAL_Control
0x180016bec  mov     al, cs:byte_1800AA941
0x180016bf2  mov     edx, 800h; unsigned int
0x180016bf7  test    [rdi+98h], edx
0x180016bfd  jz      loc_180016C9C
0x180016c03  test    al, 4
0x180016c05  jz      loc_180016C8F
0x180016c0b  xor     eax, eax
0x180016c0d  mov     word ptr [rbp+7D0h+var_848], ax
0x180016c11  mov     rax, [rdi+70h]
0x180016c15  test    rax, rax
0x180016c18  jz      short loc_180016C24
0x180016c1a  cmp     qword ptr [rax+10h], 0
0x180016c1f  jz      short loc_180016C24
0x180016c21  mov     esi, [rax+10h]
0x180016c24  mov     edx, esi
0x180016c26  lea     rcx, [rbp+7D0h+var_848]
0x180016c2a  call    ConvertPortNoToString
0x180016c2f  test    cs:byte_1800AA941, 4
0x180016c36  jz      short loc_180016C88
0x180016c38  mov     rdx, [rdi+70h]
0x180016c3c  mov     rax, rdx
0x180016c3f  lea     rcx, [rdx+0A7Eh]
0x180016c46  neg     rax
0x180016c49  sbb     r8, r8
0x180016c4c  and     r8, rcx
0x180016c4f  test    rdx, rdx
0x180016c52  lea     r9, [rdx+848h]
0x180016c59  jnz     short loc_180016C60
0x180016c5b  lea     r9, [rsp+8D0h+var_858]
0x180016c60  lea     rax, [rbp+7D0h+var_848]
0x180016c64  mov     [rsp+8D0h+var_8A8], rax
0x180016c69  mov     [rsp+8D0h+var_8B0], r8
0x180016c6e  lea     r8, aErrorInvalidOp; "ERROR_INVALID_OPERATION:CloseTunnel alr"...
0x180016c75  lea     rdx, RasVpnIkeParamTraceError
0x180016c7c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016c83  call    McTemplateU0zjzz_EventWriteTransfer
0x180016c88  mov     rbx, cs:WPP_GLOBAL_Control
0x180016c8f  mov     [rsp+8D0h+var_8A0], 10DDh
0x180016c97  jmp     loc_180016ED7
0x180016c9c  mov     rcx, rdi; this
0x180016c9f  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x180016ca4  test    cs:byte_1800AA941, 8
0x180016cab  jz      loc_180016D44
0x180016cb1  xor     eax, eax
0x180016cb3  mov     word ptr [rbp+7D0h+var_820], ax
0x180016cb7  mov     word ptr [rbp+7D0h+var_848], ax
0x180016cbb  mov     rax, [rdi+70h]
0x180016cbf  test    rax, rax
0x180016cc2  jz      short loc_180016CD0
0x180016cc4  cmp     qword ptr [rax+10h], 0
0x180016cc9  jz      short loc_180016CD0
0x180016ccb  mov     edx, [rax+10h]
0x180016cce  jmp     short loc_180016CD2
0x180016cd0  mov     edx, esi
0x180016cd2  lea     rcx, [rbp+7D0h+var_848]
0x180016cd6  call    ConvertPortNoToString
0x180016cdb  mov     r8d, r14d
0x180016cde  lea     rdx, aProcessingClos; "Processing Close Tunnel with reason: %d"
0x180016ce5  lea     rcx, [rbp+7D0h+var_820]
0x180016ce9  call    FormatRRASErrorString
0x180016cee  test    cs:byte_1800AA941, 8
0x180016cf5  jz      short loc_180016D44
0x180016cf7  mov     rdx, [rdi+70h]
0x180016cfb  mov     rax, rdx
0x180016cfe  lea     rcx, [rdx+0A7Eh]
0x180016d05  neg     rax
0x180016d08  sbb     r8, r8
0x180016d0b  and     r8, rcx
0x180016d0e  test    rdx, rdx
0x180016d11  lea     r9, [rdx+848h]
0x180016d18  jnz     short loc_180016D1F
0x180016d1a  lea     r9, [rsp+8D0h+var_858]
0x180016d1f  lea     rax, [rbp+7D0h+var_848]
0x180016d23  mov     [rsp+8D0h+var_8A8], rax
0x180016d28  mov     [rsp+8D0h+var_8B0], r8
0x180016d2d  lea     r8, [rbp+7D0h+var_820]
0x180016d31  lea     rdx, RasVpnIkeParamTraceInfo
0x180016d38  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016d3f  call    McTemplateU0zjzz_EventWriteTransfer
0x180016d44  cmp     qword ptr [rdi+0D8h], 0
0x180016d4c  jz      loc_180016E9E
0x180016d52  mov     rax, [rdi+70h]
0x180016d56  cmp     dword ptr [rax+109Ch], 1
0x180016d5d  jnz     loc_180016E9E
0x180016d63  lea     rcx, [rsp+8D0h+engineHandle]; void **
0x180016d68  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x180016d6d  mov     rcx, [rsp+8D0h+engineHandle]; engineHandle
0x180016d72  test    rcx, rcx
0x180016d75  jnz     loc_180016E56
0x180016d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d82  lea     rdx, WPP_GLOBAL_Control
0x180016d89  cmp     rcx, rdx
0x180016d8c  jz      short loc_180016DB2
0x180016d8e  test    byte ptr [rcx+1Ch], 1
0x180016d92  jz      short loc_180016DB2
0x180016d94  cmp     byte ptr [rcx+19h], 6
0x180016d98  jb      short loc_180016DB2
0x180016d9a  mov     edx, 39h ; '9'
0x180016d9f  xor     r9d, r9d
0x180016da2  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180016da9  mov     rcx, [rcx+10h]
0x180016dad  call    WPP_SF_d
0x180016db2  test    cs:byte_1800AA941, 8
0x180016db9  jz      loc_180016E9E
0x180016dbf  xor     eax, eax
0x180016dc1  mov     word ptr [rbp+7D0h+var_820], ax
0x180016dc5  mov     word ptr [rbp+7D0h+var_848], ax
0x180016dc9  mov     rax, [rdi+70h]
0x180016dcd  test    rax, rax
0x180016dd0  jz      short loc_180016DDC
0x180016dd2  cmp     qword ptr [rax+10h], 0
0x180016dd7  jz      short loc_180016DDC
0x180016dd9  mov     esi, [rax+10h]
0x180016ddc  mov     edx, esi
0x180016dde  lea     rcx, [rbp+7D0h+var_848]
0x180016de2  call    ConvertPortNoToString
0x180016de7  xor     r8d, r8d
0x180016dea  lea     rdx, aErrorBfehandle; "Error BFEHandle Status = %!WINERROR!: %"...
0x180016df1  lea     rcx, [rbp+7D0h+var_820]
0x180016df5  call    FormatRRASErrorString
0x180016dfa  test    cs:byte_1800AA941, 8
0x180016e01  jz      loc_180016E9E
0x180016e07  mov     rdx, [rdi+70h]
0x180016e0b  mov     rax, rdx
0x180016e0e  lea     rcx, [rdx+0A7Eh]
0x180016e15  neg     rax
0x180016e18  sbb     r8, r8
0x180016e1b  and     r8, rcx
0x180016e1e  test    rdx, rdx
0x180016e21  lea     r9, [rdx+848h]
0x180016e28  jnz     short loc_180016E2F
0x180016e2a  lea     r9, [rsp+8D0h+var_858]
0x180016e2f  lea     rax, [rbp+7D0h+var_848]
0x180016e33  mov     [rsp+8D0h+var_8A8], rax
0x180016e38  mov     [rsp+8D0h+var_8B0], r8
0x180016e3d  lea     r8, [rbp+7D0h+var_820]
0x180016e41  lea     rdx, RasVpnIkeParamTraceInfo
0x180016e48  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016e4f  call    McTemplateU0zjzz_EventWriteTransfer
0x180016e54  jmp     short loc_180016E9E
0x180016e56  mov     rdx, [rdi+0D8h]; eventsHandle
0x180016e5d  call    cs:__imp_FwpmNetEventUnsubscribe0
0x180016e63  test    eax, eax
0x180016e65  jns     short loc_180016E9E
0x180016e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e6e  lea     rdx, WPP_GLOBAL_Control
0x180016e75  cmp     rcx, rdx
0x180016e78  jz      short loc_180016E9E
0x180016e7a  test    byte ptr [rcx+1Ch], 1
0x180016e7e  jz      short loc_180016E9E
0x180016e80  cmp     byte ptr [rcx+19h], 6
0x180016e84  jb      short loc_180016E9E
0x180016e86  mov     edx, 3Ah ; ':'
0x180016e8b  mov     r9d, eax
0x180016e8e  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180016e95  mov     rcx, [rcx+10h]
0x180016e99  call    WPP_SF_d
0x180016e9e  mov     [rdi+168h], r14d
0x180016ea5  mov     rax, [rdi]
0x180016ea8  mov     edx, 2
0x180016ead  mov     rcx, rdi
0x180016eb0  mov     rax, [rax+90h]
0x180016eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ebc  test    dword ptr [rdi+98h], 8000h
0x180016ec6  jnz     short loc_180016ED0
0x180016ec8  mov     rcx, rdi; this
0x180016ecb  call    ?NotifyOnDisconnectCleanupComplete@VPNIKEClientConnection@@IEAAXXZ; VPNIKEClientConnection::NotifyOnDisconnectCleanupComplete(void)
0x180016ed0  mov     rbx, cs:WPP_GLOBAL_Control
0x180016ed7  lea     rax, WPP_GLOBAL_Control
0x180016ede  cmp     rbx, rax
0x180016ee1  jz      short loc_180016F09
0x180016ee3  test    byte ptr [rbx+1Ch], 1
0x180016ee7  jz      short loc_180016F09
0x180016ee9  cmp     byte ptr [rbx+19h], 6
0x180016eed  jb      short loc_180016F09
0x180016eef  mov     edx, 3Bh ; ';'
0x180016ef4  mov     r9d, [rsp+8D0h+var_8A0]
0x180016ef9  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180016f00  mov     rcx, [rbx+10h]
0x180016f04  call    WPP_SF_d
0x180016f09  mov     ebx, [rsp+8D0h+var_8A0]
0x180016f0d  lea     rcx, [rsp+8D0h+var_890]; this
0x180016f12  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180016f17  mov     eax, ebx
0x180016f19  mov     rcx, [rbp+7D0h+var_20]
0x180016f20  xor     rcx, rsp; StackCookie
0x180016f23  call    __security_check_cookie
0x180016f28  lea     r11, [rsp+8D0h+var_10]
0x180016f30  mov     rbx, [r11+30h]
0x180016f34  mov     rsi, [r11+38h]
0x180016f38  mov     rsp, r11
0x180016f3b  pop     r14
0x180016f3d  pop     rdi
0x180016f3e  pop     rbp
0x180016f3f  retn
```
