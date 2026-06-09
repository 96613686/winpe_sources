# VPNIKEServerConnection::ProcessStart(_PROTOCOL_DDM_START &)

- ea: `0x180025a20`
- end: `0x180025e80`
- name: `?ProcessStart@VPNIKEServerConnection@@UEAAXAEAU_PROTOCOL_DDM_START@@@Z`
- size: `1120`
- prototype: `void __fastcall(VPNIKEServerConnection *__hidden this, struct _PROTOCOL_DDM_START *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800131c8`
- `0x180023a6c`
- `0x180023c64`
- `0x180025a20`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x180025cff`: `RasProtocolStarted failed: %d`
- `0x180025b09`: `User already cancelled this connection (hPort: %I64u, ConnectionState: 0x%08X). Hence exiting.`
- `0x180025bc1`: `User already stopped this connection (hPort: %I64u, ConnectionState: 0x%08X). Hence exiting.`

## pseudocode

```c
void __fastcall VPNIKEServerConnection::ProcessStart(VPNIKEServerConnection *this, struct _PROTOCOL_DDM_START *a2)
{
  unsigned int v3; // edi
  unsigned int v4; // esi
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int128 *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int128 *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int128 *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  __int128 *v22; // r9
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+44h] [rbp-BCh]
  __int128 v26; // [rsp+54h] [rbp-ACh]
  int v27; // [rsp+64h] [rbp-9Ch]
  int v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  v28 = 0;
  v3 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v27 = 0;
  v4 = -1;
  v5 = *((_DWORD *)this + 38);
  v25 = 0;
  v26 = 0;
  v23 = 0;
  if ( (v5 & 0x8000) != 0 )
  {
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_34;
    LOWORD(v28) = 0;
    LOWORD(v24) = 0;
    v6 = *((_QWORD *)this + 14);
    if ( v6 && *(_QWORD *)(v6 + 16) )
      v7 = *(unsigned int *)(v6 + 16);
    else
      v7 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v24, v7);
    FormatRRASErrorString(
      &v28,
      L"User already cancelled this connection (hPort: %I64u, ConnectionState: 0x%08X). Hence exiting.",
      *((_QWORD *)this + 3),
      *((unsigned int *)this + 38));
LABEL_12:
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v8 = *((_QWORD *)this + 14);
      LODWORD(v9) = v8 + 2120;
      if ( !v8 )
        v9 = &v23;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v28,
        (_DWORD)v9,
        (v8 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
        (__int64)&v24);
    }
    goto LABEL_34;
  }
  if ( (v5 & 0x1000) != 0 )
  {
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_34;
    LOWORD(v28) = 0;
    LOWORD(v24) = 0;
    v10 = *((_QWORD *)this + 14);
    if ( v10 && *(_QWORD *)(v10 + 16) )
      v11 = *(unsigned int *)(v10 + 16);
    else
      v11 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v24, v11);
    FormatRRASErrorString(
      &v28,
      L"User already stopped this connection (hPort: %I64u, ConnectionState: 0x%08X). Hence exiting.",
      *((_QWORD *)this + 3),
      *((unsigned int *)this + 38));
    goto LABEL_12;
  }
  VPNIKEConnection::UpdateConnectionState(this, 0x1000000u);
  v3 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))xmmword_1800AA980)(
         0,
         *(_QWORD *)(*((_QWORD *)this + 14) + 16LL),
         *((_QWORD *)this + 14) + 32LL);
  if ( v3 )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v28) = 0;
      LOWORD(v24) = 0;
      v12 = *((_QWORD *)this + 14);
      if ( v12 && *(_QWORD *)(v12 + 16) )
        v13 = *(unsigned int *)(v12 + 16);
      else
        v13 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v24, v13);
      FormatRRASErrorString(&v28, L"RasPortGetBundle failed: %d", v3);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v14 = *((_QWORD *)this + 14);
        LODWORD(v15) = v14 + 2120;
        if ( !v14 )
          v15 = &v23;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v28,
          (_DWORD)v15,
          (v14 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
          (__int64)&v24);
      }
    }
    VPNIKEServerConnection::MarkStopPending(this, v3);
  }
LABEL_34:
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD))xmmword_1800AA990)(*((_QWORD *)this + 3))
    && (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v28) = 0;
    LOWORD(v24) = 0;
    v16 = *((_QWORD *)this + 14);
    if ( v16 && *(_QWORD *)(v16 + 16) )
      v17 = *(unsigned int *)(v16 + 16);
    else
      v17 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v24, v17);
    FormatRRASErrorString(&v28, L"RasProtocolStarted failed: %d", v3);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v18 = *((_QWORD *)this + 14);
      LODWORD(v19) = v18 + 2120;
      if ( !v18 )
        v19 = &v23;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v28,
        (_DWORD)v19,
        (v18 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
        (__int64)&v24);
    }
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 5) + 16LL))(
         *((_QWORD *)VpnIkeProtocolEngine + 5),
         *((unsigned int *)this + 2))
    && (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v28) = 0;
    LOWORD(v24) = 0;
    v20 = *((_QWORD *)this + 14);
    if ( v20 && *(_QWORD *)(v20 + 16) )
      v4 = *(_DWORD *)(v20 + 16);
    ConvertPortNoToString(&v24, v4);
    FormatRRASErrorString(&v28, L"SignalEventHandle: Sync Event signalling failed: %d", v3);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v21 = *((_QWORD *)this + 14);
      LODWORD(v22) = v21 + 2120;
      if ( !v21 )
        v22 = &v23;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v28,
        (_DWORD)v22,
        (v21 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
        (__int64)&v24);
    }
  }
  if ( v3 )
    VPNIKEServerConnection::NotifyError(this, v3);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
}

```

## disassembly

```asm
0x180025a20  push    rbp
0x180025a22  push    rbx
0x180025a23  push    rsi
0x180025a24  push    rdi
0x180025a25  push    r12
0x180025a27  push    r13
0x180025a29  lea     rbp, [rsp-788h]
0x180025a31  sub     rsp, 888h
0x180025a38  mov     rax, cs:__security_cookie
0x180025a3f  xor     rax, rsp
0x180025a42  mov     [rbp+7B0h+var_40], rax
0x180025a49  mov     rbx, rcx
0x180025a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a53  lea     r13, WPP_GLOBAL_Control
0x180025a5a  cmp     rcx, r13
0x180025a5d  jz      short loc_180025A80
0x180025a5f  test    byte ptr [rcx+1Ch], 1
0x180025a63  jz      short loc_180025A80
0x180025a65  cmp     byte ptr [rcx+19h], 6
0x180025a69  jb      short loc_180025A80
0x180025a6b  mov     rcx, [rcx+10h]
0x180025a6f  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180025a76  mov     edx, 0Fh
0x180025a7b  call    WPP_SF_
0x180025a80  xor     eax, eax
0x180025a82  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180025a87  xor     edx, edx; Val
0x180025a89  mov     [rsp+8B0h+var_840], eax
0x180025a8d  mov     r8d, 7FCh; Size
0x180025a93  xor     edi, edi
0x180025a95  call    memset_0
0x180025a9a  xor     eax, eax
0x180025a9c  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025aa3  xorps   xmm0, xmm0
0x180025aa6  mov     [rsp+8B0h+var_870], eax
0x180025aaa  mov     [rsp+8B0h+var_84C], eax
0x180025aae  or      esi, 0FFFFFFFFh
0x180025ab1  mov     eax, [rbx+98h]
0x180025ab7  movups  [rsp+8B0h+var_86C], xmm0
0x180025abc  movups  [rsp+8B0h+var_85C], xmm0
0x180025ac1  movups  [rsp+8B0h+var_880], xmm0
0x180025ac6  bt      eax, 0Fh
0x180025aca  jnb     loc_180025B82
0x180025ad0  test    cs:byte_1800AA941, 8
0x180025ad7  jz      loc_180025CAA
0x180025add  xor     eax, eax
0x180025adf  mov     word ptr [rsp+8B0h+var_840], ax
0x180025ae4  mov     word ptr [rsp+8B0h+var_870], ax
0x180025ae9  mov     rax, [rbx+70h]
0x180025aed  test    rax, rax
0x180025af0  jz      short loc_180025AFD
0x180025af2  cmp     [rax+10h], rdi
0x180025af6  jz      short loc_180025AFD
0x180025af8  mov     edx, [rax+10h]
0x180025afb  jmp     short loc_180025AFF
0x180025afd  mov     edx, esi
0x180025aff  lea     rcx, [rsp+8B0h+var_870]
0x180025b04  call    ConvertPortNoToString
0x180025b09  lea     rdx, aUserAlreadyCan_0; "User already cancelled this connection "...
0x180025b10  mov     r9d, [rbx+98h]
0x180025b17  lea     rcx, [rsp+8B0h+var_840]
0x180025b1c  mov     r8, [rbx+18h]
0x180025b20  call    FormatRRASErrorString
0x180025b25  test    cs:byte_1800AA941, 8
0x180025b2c  jz      loc_180025CAA
0x180025b32  mov     rdx, [rbx+70h]
0x180025b36  mov     rax, rdx
0x180025b39  neg     rax
0x180025b3c  sbb     r8, r8
0x180025b3f  lea     rcx, [rdx+0A7Eh]
0x180025b46  and     r8, rcx
0x180025b49  lea     r9, [rdx+848h]
0x180025b50  test    rdx, rdx
0x180025b53  jnz     short loc_180025B5A
0x180025b55  lea     r9, [rsp+8B0h+var_880]
0x180025b5a  lea     rax, [rsp+8B0h+var_870]
0x180025b5f  mov     rcx, r12
0x180025b62  mov     [rsp+8B0h+var_888], rax
0x180025b67  lea     rdx, RasVpnIkeParamTraceInfo
0x180025b6e  mov     [rsp+8B0h+var_890], r8
0x180025b73  lea     r8, [rsp+8B0h+var_840]
0x180025b78  call    McTemplateU0zjzz_EventWriteTransfer
0x180025b7d  jmp     loc_180025CAA
0x180025b82  bt      eax, 0Ch
0x180025b86  jnb     short loc_180025BCD
0x180025b88  test    cs:byte_1800AA941, 8
0x180025b8f  jz      loc_180025CAA
0x180025b95  xor     eax, eax
0x180025b97  mov     word ptr [rsp+8B0h+var_840], ax
0x180025b9c  mov     word ptr [rsp+8B0h+var_870], ax
0x180025ba1  mov     rax, [rbx+70h]
0x180025ba5  test    rax, rax
0x180025ba8  jz      short loc_180025BB5
0x180025baa  cmp     [rax+10h], rdi
0x180025bae  jz      short loc_180025BB5
0x180025bb0  mov     edx, [rax+10h]
0x180025bb3  jmp     short loc_180025BB7
0x180025bb5  mov     edx, esi
0x180025bb7  lea     rcx, [rsp+8B0h+var_870]
0x180025bbc  call    ConvertPortNoToString
0x180025bc1  lea     rdx, aUserAlreadySto; "User already stopped this connection (h"...
0x180025bc8  jmp     loc_180025B10
0x180025bcd  mov     edx, 1000000h; unsigned int
0x180025bd2  mov     rcx, rbx; this
0x180025bd5  call    ?UpdateConnectionState@VPNIKEConnection@@IEAAXK@Z; VPNIKEConnection::UpdateConnectionState(ulong)
0x180025bda  mov     rdx, [rbx+70h]
0x180025bde  xor     ecx, ecx
0x180025be0  mov     rax, qword ptr cs:xmmword_1800AA980
0x180025be7  lea     r8, [rdx+20h]
0x180025beb  mov     rdx, [rdx+10h]
0x180025bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bf4  mov     edi, eax
0x180025bf6  test    eax, eax
0x180025bf8  jz      loc_180025CAA
0x180025bfe  test    cs:byte_1800AA941, 4
0x180025c05  jz      loc_180025CA0
0x180025c0b  xor     ecx, ecx
0x180025c0d  mov     word ptr [rsp+8B0h+var_840], cx
0x180025c12  mov     word ptr [rsp+8B0h+var_870], cx
0x180025c17  mov     rcx, [rbx+70h]
0x180025c1b  test    rcx, rcx
0x180025c1e  jz      short loc_180025C2C
0x180025c20  cmp     qword ptr [rcx+10h], 0
0x180025c25  jz      short loc_180025C2C
0x180025c27  mov     edx, [rcx+10h]
0x180025c2a  jmp     short loc_180025C2E
0x180025c2c  mov     edx, esi
0x180025c2e  lea     rcx, [rsp+8B0h+var_870]
0x180025c33  call    ConvertPortNoToString
0x180025c38  mov     r8d, edi
0x180025c3b  lea     rdx, aRasportgetbund; "RasPortGetBundle failed: %d"
0x180025c42  lea     rcx, [rsp+8B0h+var_840]
0x180025c47  call    FormatRRASErrorString
0x180025c4c  test    cs:byte_1800AA941, 4
0x180025c53  jz      short loc_180025CA0
0x180025c55  mov     rdx, [rbx+70h]
0x180025c59  mov     rax, rdx
0x180025c5c  neg     rax
0x180025c5f  sbb     r8, r8
0x180025c62  lea     rcx, [rdx+0A7Eh]
0x180025c69  and     r8, rcx
0x180025c6c  lea     r9, [rdx+848h]
0x180025c73  test    rdx, rdx
0x180025c76  jnz     short loc_180025C7D
0x180025c78  lea     r9, [rsp+8B0h+var_880]
0x180025c7d  lea     rax, [rsp+8B0h+var_870]
0x180025c82  mov     rcx, r12
0x180025c85  mov     [rsp+8B0h+var_888], rax
0x180025c8a  lea     rdx, RasVpnIkeParamTraceError
0x180025c91  mov     [rsp+8B0h+var_890], r8
0x180025c96  lea     r8, [rsp+8B0h+var_840]
0x180025c9b  call    McTemplateU0zjzz_EventWriteTransfer
0x180025ca0  mov     edx, edi; unsigned int
0x180025ca2  mov     rcx, rbx; this
0x180025ca5  call    ?MarkStopPending@VPNIKEServerConnection@@QEAAXK@Z; VPNIKEServerConnection::MarkStopPending(ulong)
0x180025caa  mov     rcx, [rbx+18h]
0x180025cae  mov     rax, qword ptr cs:xmmword_1800AA990
0x180025cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cba  test    eax, eax
0x180025cbc  jz      loc_180025D64
0x180025cc2  test    cs:byte_1800AA941, 4
0x180025cc9  jz      loc_180025D64
0x180025ccf  xor     eax, eax
0x180025cd1  mov     word ptr [rsp+8B0h+var_840], ax
0x180025cd6  mov     word ptr [rsp+8B0h+var_870], ax
0x180025cdb  mov     rax, [rbx+70h]
0x180025cdf  test    rax, rax
0x180025ce2  jz      short loc_180025CF0
0x180025ce4  cmp     qword ptr [rax+10h], 0
0x180025ce9  jz      short loc_180025CF0
0x180025ceb  mov     edx, [rax+10h]
0x180025cee  jmp     short loc_180025CF2
0x180025cf0  mov     edx, esi
0x180025cf2  lea     rcx, [rsp+8B0h+var_870]
0x180025cf7  call    ConvertPortNoToString
0x180025cfc  mov     r8d, edi
0x180025cff  lea     rdx, aRasprotocolsta; "RasProtocolStarted failed: %d"
0x180025d06  lea     rcx, [rsp+8B0h+var_840]
0x180025d0b  call    FormatRRASErrorString
0x180025d10  test    cs:byte_1800AA941, 4
0x180025d17  jz      short loc_180025D64
0x180025d19  mov     rdx, [rbx+70h]
0x180025d1d  mov     rax, rdx
0x180025d20  neg     rax
0x180025d23  sbb     r8, r8
0x180025d26  lea     rcx, [rdx+0A7Eh]
0x180025d2d  and     r8, rcx
0x180025d30  lea     r9, [rdx+848h]
0x180025d37  test    rdx, rdx
0x180025d3a  jnz     short loc_180025D41
0x180025d3c  lea     r9, [rsp+8B0h+var_880]
0x180025d41  lea     rax, [rsp+8B0h+var_870]
0x180025d46  mov     rcx, r12
0x180025d49  mov     [rsp+8B0h+var_888], rax
0x180025d4e  lea     rdx, RasVpnIkeParamTraceError
0x180025d55  mov     [rsp+8B0h+var_890], r8
0x180025d5a  lea     r8, [rsp+8B0h+var_840]
0x180025d5f  call    McTemplateU0zjzz_EventWriteTransfer
0x180025d64  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180025d6b  mov     edx, [rbx+8]
0x180025d6e  mov     rcx, [rax+28h]
0x180025d72  mov     rax, [rcx]
0x180025d75  mov     rax, [rax+10h]
0x180025d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d7e  test    eax, eax
0x180025d80  jz      loc_180025E26
0x180025d86  test    cs:byte_1800AA941, 4
0x180025d8d  jz      loc_180025E26
0x180025d93  xor     eax, eax
0x180025d95  mov     word ptr [rsp+8B0h+var_840], ax
0x180025d9a  mov     word ptr [rsp+8B0h+var_870], ax
0x180025d9f  mov     rax, [rbx+70h]
0x180025da3  test    rax, rax
0x180025da6  jz      short loc_180025DB2
0x180025da8  cmp     qword ptr [rax+10h], 0
0x180025dad  jz      short loc_180025DB2
0x180025daf  mov     esi, [rax+10h]
0x180025db2  mov     edx, esi
0x180025db4  lea     rcx, [rsp+8B0h+var_870]
0x180025db9  call    ConvertPortNoToString
0x180025dbe  mov     r8d, edi
0x180025dc1  lea     rdx, aSignaleventhan_0; "SignalEventHandle: Sync Event signallin"...
0x180025dc8  lea     rcx, [rsp+8B0h+var_840]
0x180025dcd  call    FormatRRASErrorString
0x180025dd2  test    cs:byte_1800AA941, 4
0x180025dd9  jz      short loc_180025E26
0x180025ddb  mov     rdx, [rbx+70h]
0x180025ddf  mov     rax, rdx
0x180025de2  neg     rax
0x180025de5  sbb     r8, r8
0x180025de8  lea     rcx, [rdx+0A7Eh]
0x180025def  and     r8, rcx
0x180025df2  lea     r9, [rdx+848h]
0x180025df9  test    rdx, rdx
0x180025dfc  jnz     short loc_180025E03
0x180025dfe  lea     r9, [rsp+8B0h+var_880]
0x180025e03  lea     rax, [rsp+8B0h+var_870]
0x180025e08  mov     rcx, r12
0x180025e0b  mov     [rsp+8B0h+var_888], rax
0x180025e10  lea     rdx, RasVpnIkeParamTraceError
0x180025e17  mov     [rsp+8B0h+var_890], r8
0x180025e1c  lea     r8, [rsp+8B0h+var_840]
0x180025e21  call    McTemplateU0zjzz_EventWriteTransfer
0x180025e26  test    edi, edi
0x180025e28  jz      short loc_180025E34
0x180025e2a  mov     edx, edi; unsigned int
0x180025e2c  mov     rcx, rbx; this
0x180025e2f  call    ?NotifyError@VPNIKEServerConnection@@IEAAXK@Z; VPNIKEServerConnection::NotifyError(ulong)
0x180025e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e3b  cmp     rcx, r13
0x180025e3e  jz      short loc_180025E61
0x180025e40  test    byte ptr [rcx+1Ch], 1
0x180025e44  jz      short loc_180025E61
0x180025e46  cmp     byte ptr [rcx+19h], 6
0x180025e4a  jb      short loc_180025E61
0x180025e4c  mov     rcx, [rcx+10h]
0x180025e50  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180025e57  mov     edx, 10h
0x180025e5c  call    WPP_SF_
0x180025e61  mov     rcx, [rbp+7B0h+var_40]
0x180025e68  xor     rcx, rsp; StackCookie
0x180025e6b  call    __security_check_cookie
0x180025e70  add     rsp, 888h
0x180025e77  pop     r13
0x180025e79  pop     r12
0x180025e7b  pop     rdi
0x180025e7c  pop     rsi
0x180025e7d  pop     rbx
0x180025e7e  pop     rbp
0x180025e7f  retn
```
