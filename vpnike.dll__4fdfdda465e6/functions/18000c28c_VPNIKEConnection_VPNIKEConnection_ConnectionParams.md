# VPNIKEConnection::VPNIKEConnection(ConnectionParams *)

- ea: `0x18000c28c`
- end: `0x18000c6ae`
- name: `??0VPNIKEConnection@@QEAA@PEAVConnectionParams@@@Z`
- size: `1058`
- prototype: `VPNIKEConnection *__fastcall(VPNIKEConnection *__hidden this, struct ConnectionParams *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180015b90`
- `0x180021730`

## callees

- `0x180001514`
- `0x180001f78`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000aefc`
- `0x18000c28c`
- `0x18000c830`
- `0x180048274`
- `0x18004cad0`
- `0x180057744`
- `0x18005d134`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000c573`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000c573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c585`

## pseudocode

```c
VPNIKEConnection *__fastcall VPNIKEConnection::VPNIKEConnection(VPNIKEConnection *this, struct ConnectionParams *a2)
{
  VPNIKEConnection *v3; // rbx
  unsigned int v4; // r15d
  IPv4Helper *v5; // rax
  IPv4Helper *v6; // rax
  IPv6Helper *v7; // rax
  IPv6Helper *v8; // rax
  struct IPNotifications *Instance; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int128 *v12; // r9
  PVOID *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  PTP_WORK ThreadpoolWork; // rax
  DWORD LastError; // eax
  VPNIKEConnection *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int128 *v23; // r9
  unsigned int v24; // [rsp+30h] [rbp-A8h] BYREF
  ulong pExceptionObject; // [rsp+34h] [rbp-A4h] BYREF
  VPNIKEConnection *v26; // [rsp+38h] [rbp-A0h]
  IPv4Helper *v27; // [rsp+40h] [rbp-98h]
  __int64 v28; // [rsp+48h] [rbp-90h] BYREF
  __int128 v29; // [rsp+50h] [rbp-88h]
  __int128 v30; // [rsp+60h] [rbp-78h]
  __int64 v31; // [rsp+70h] [rbp-68h]
  int v32; // [rsp+78h] [rbp-60h]
  int v33; // [rsp+7Ch] [rbp-5Ch]
  __int128 v34; // [rsp+80h] [rbp-58h] BYREF
  int v35; // [rsp+90h] [rbp-48h] BYREF
  __int128 v36; // [rsp+94h] [rbp-44h]
  __int128 v37; // [rsp+A4h] [rbp-34h]
  int v38; // [rsp+B4h] [rbp-24h]

  v3 = this;
  v26 = this;
  BaseConnection::BaseConnection(this, a2);
  *(_QWORD *)v3 = &VPNIKEConnection::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  v24 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v34 = 0;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v4 = -1;
  v32 = -1;
  v33 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v28,
      L"VPNIKEConnection::VPNIKEConnection",
      &v24,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)v3 + 14));
  *((_QWORD *)v3 + 26) = 0;
  *((_QWORD *)v3 + 29) = 0;
  *((_QWORD *)v3 + 44) = 0;
  *((_DWORD *)v3 + 66) = 0;
  *(_QWORD *)((char *)v3 + 268) = 6;
  *((_QWORD *)v3 + 35) = 0;
  *((_DWORD *)v3 + 72) = 1;
  *(_OWORD *)((char *)v3 + 296) = 0;
  *((_QWORD *)v3 + 39) = 0;
  *((_OWORD *)v3 + 20) = 0;
  *((_OWORD *)v3 + 21) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *((_DWORD *)v3 + 38) = 0;
  *((_QWORD *)v3 + 32) = 0;
  *((_DWORD *)v3 + 34) = 1;
  *((_DWORD *)v3 + 35) = *((_DWORD *)v3 + 2);
  *((_DWORD *)v3 + 36) = 1;
  *((_QWORD *)v3 + 27) = 0;
  *((_QWORD *)v3 + 30) = VPNIKEIOCTLHelper::GetInstance();
  try
  {
    v5 = (IPv4Helper *)operator new(0x170u);
    v27 = v5;
    if ( v5 )
      v6 = IPv4Helper::IPv4Helper(v5, a2);
    else
      v6 = 0;
    *((_QWORD *)v3 + 4) = v6;
    v7 = (IPv6Helper *)operator new(0x1B8u);
    v27 = v7;
    if ( v7 )
      v8 = IPv6Helper::IPv6Helper(v7, a2);
    else
      v8 = 0;
    *((_QWORD *)v3 + 5) = v8;
  }
  catch ( ... )
  {
    v24 = 8;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v35) = 0;
      v19 = v26;
      if ( *((_QWORD *)v26 + 14) && (v20 = *((_QWORD *)v26 + 14), *(_QWORD *)(v20 + 16)) )
        v21 = *(unsigned int *)(v20 + 16);
      else
        v21 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v35, v21);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        if ( *((_QWORD *)v19 + 14) )
          v22 = *((_QWORD *)v19 + 14) + 2686LL;
        else
          v22 = 0;
        if ( *((_QWORD *)v19 + 14) )
          LODWORD(v23) = *((_QWORD *)v19 + 14) + 2120;
        else
          v23 = &v34;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Unable to get new IPv4Helper/IPv6Helper instance",
          (_DWORD)v23,
          v22,
          (__int64)&v35);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v24);
    }
    v3 = v26;
    goto LABEL_34;
  }
  Instance = IPNotifications::GetInstance();
  *((_QWORD *)v3 + 29) = Instance;
  if ( Instance )
  {
    ThreadpoolWork = CreateThreadpoolWork(VPNIKEConnection::s_DeleteIpAddressCallback, v3, 0);
    *((_QWORD *)v3 + 44) = ThreadpoolWork;
    if ( ThreadpoolWork )
      goto LABEL_34;
    LastError = GetLastError();
    v24 = LastError;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 13;
      v15 = LastError;
      goto LABEL_28;
    }
  }
  else
  {
    v24 = 8;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v35) = 0;
      v10 = *((_QWORD *)v3 + 14);
      if ( v10 && *(_QWORD *)(v10 + 16) )
        v4 = *(_DWORD *)(v10 + 16);
      ConvertPortNoToString(&v35, v4);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v11 = *((_QWORD *)v3 + 14);
        LODWORD(v12) = v11 + 2120;
        if ( !v11 )
          v12 = &v34;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"ERROR_NOT_ENOUGH_MEMORY",
          (_DWORD)v12,
          (v11 + 2686) & -(__int64)(v11 != 0),
          (__int64)&v35);
      }
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 12;
      v15 = v24;
LABEL_28:
      WPP_SF_d(v13[2], v14, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v15);
LABEL_34:
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v24 )
  {
    VPNIKEConnection::Cleanup(v3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, v24);
    }
    pExceptionObject = v24;
    throw &pExceptionObject;
  }
  if ( v13 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 6u )
    {
      WPP_SF_d(v13[2], 15, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, 0);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 6u )
      WPP_SF_(v13[2], 16, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v28);
  return v3;
}

```

## disassembly

```asm
0x18000c28c  mov     [rsp+arg_10], rbx
0x18000c291  mov     [rsp+arg_18], rsi
0x18000c296  push    rdi
0x18000c297  push    r14
0x18000c299  push    r15
0x18000c29b  sub     rsp, 0C0h
0x18000c2a2  mov     rax, cs:__security_cookie
0x18000c2a9  xor     rax, rsp
0x18000c2ac  mov     [rsp+0D8h+var_20], rax
0x18000c2b4  mov     r14, rdx
0x18000c2b7  mov     rbx, rcx
0x18000c2ba  mov     [rsp+0D8h+var_A0], rcx
0x18000c2bf  call    ??0BaseConnection@@QEAA@PEAVConnectionParams@@@Z; BaseConnection::BaseConnection(ConnectionParams *)
0x18000c2c4  nop
0x18000c2c5  lea     rax, ??_7VPNIKEConnection@@6B@; const VPNIKEConnection::`vftable'
0x18000c2cc  mov     [rbx], rax
0x18000c2cf  lea     rsi, WPP_GLOBAL_Control
0x18000c2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2dd  cmp     rcx, rsi
0x18000c2e0  jz      short loc_18000C303
0x18000c2e2  test    byte ptr [rcx+1Ch], 1
0x18000c2e6  jz      short loc_18000C303
0x18000c2e8  cmp     byte ptr [rcx+19h], 6
0x18000c2ec  jb      short loc_18000C303
0x18000c2ee  mov     edx, 0Ah
0x18000c2f3  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000c2fa  mov     rcx, [rcx+10h]
0x18000c2fe  call    WPP_SF_
0x18000c303  xor     edi, edi
0x18000c305  mov     [rsp+0D8h+var_A8], edi
0x18000c309  mov     [rsp+0D8h+var_48], edi
0x18000c310  xorps   xmm0, xmm0
0x18000c313  xor     eax, eax
0x18000c315  movups  [rsp+0D8h+var_44], xmm0
0x18000c31d  movups  [rsp+0D8h+var_34], xmm0
0x18000c325  mov     [rsp+0D8h+var_24], eax
0x18000c32c  movups  [rsp+0D8h+var_58], xmm0
0x18000c334  xorps   xmm1, xmm1
0x18000c337  movdqu  [rsp+0D8h+var_88], xmm1
0x18000c33d  mov     [rsp+0D8h+var_90], rdi
0x18000c342  movdqu  [rsp+0D8h+var_78], xmm0
0x18000c348  mov     [rsp+0D8h+var_68], rdi
0x18000c34d  or      r15d, 0FFFFFFFFh
0x18000c351  mov     [rsp+0D8h+var_60], r15d
0x18000c356  mov     [rsp+0D8h+var_5C], edi
0x18000c35a  test    cs:byte_1800AA941, 8
0x18000c361  jz      short loc_18000C389
0x18000c363  mov     rax, [rbx+70h]
0x18000c367  mov     [rsp+0D8h+var_B8], rax; void *
0x18000c36c  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000c373  lea     r8, [rsp+0D8h+var_A8]; unsigned int *
0x18000c378  lea     rdx, aVpnikeconnecti_17; "VPNIKEConnection::VPNIKEConnection"
0x18000c37f  lea     rcx, [rsp+0D8h+var_90]; this
0x18000c384  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18000c389  mov     [rbx+0D0h], rdi
0x18000c390  mov     [rbx+0E8h], rdi
0x18000c397  mov     [rbx+160h], rdi
0x18000c39e  mov     [rbx+108h], edi
0x18000c3a4  mov     qword ptr [rbx+10Ch], 6
0x18000c3af  mov     [rbx+118h], rdi
0x18000c3b6  mov     dword ptr [rbx+120h], 1
0x18000c3c0  xorps   xmm0, xmm0
0x18000c3c3  xor     eax, eax
0x18000c3c5  movups  xmmword ptr [rbx+128h], xmm0
0x18000c3cc  mov     [rbx+138h], rax
0x18000c3d3  movups  xmmword ptr [rbx+140h], xmm0
0x18000c3da  movups  xmmword ptr [rbx+150h], xmm0
0x18000c3e1  mov     [rbx+0F8h], rdi
0x18000c3e8  mov     [rbx+98h], edi
0x18000c3ee  mov     [rbx+100h], rdi
0x18000c3f5  mov     dword ptr [rbx+88h], 1
0x18000c3ff  mov     eax, [rbx+8]
0x18000c402  mov     [rbx+8Ch], eax
0x18000c408  mov     dword ptr [rbx+90h], 1
0x18000c412  mov     [rbx+0D8h], rdi
0x18000c419  call    ?GetInstance@VPNIKEIOCTLHelper@@SAPEAV1@XZ; VPNIKEIOCTLHelper::GetInstance(void)
0x18000c41e  mov     [rbx+0F0h], rax
0x18000c425  mov     ecx, 170h; Size
0x18000c42a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c42f  mov     [rsp+0D8h+var_98], rax
0x18000c434  test    rax, rax
0x18000c437  jz      short loc_18000C446
0x18000c439  mov     rdx, r14; struct ConnectionParams *
0x18000c43c  mov     rcx, rax; this
0x18000c43f  call    ??0IPv4Helper@@QEAA@PEAVConnectionParams@@@Z; IPv4Helper::IPv4Helper(ConnectionParams *)
0x18000c444  jmp     short loc_18000C449
0x18000c446  mov     rax, rdi
0x18000c449  mov     [rbx+20h], rax
0x18000c44d  mov     ecx, 1B8h; Size
0x18000c452  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c457  mov     [rsp+0D8h+var_98], rax
0x18000c45c  test    rax, rax
0x18000c45f  jz      short loc_18000C46E
0x18000c461  mov     rdx, r14; struct ConnectionParams *
0x18000c464  mov     rcx, rax; this
0x18000c467  call    ??0IPv6Helper@@QEAA@PEAVConnectionParams@@@Z; IPv6Helper::IPv6Helper(ConnectionParams *)
0x18000c46c  jmp     short loc_18000C471
0x18000c46e  mov     rax, rdi
0x18000c471  mov     [rbx+28h], rax
0x18000c475  call    ?GetInstance@IPNotifications@@SAPEAV1@XZ; IPNotifications::GetInstance(void)
0x18000c47a  mov     [rbx+0E8h], rax
0x18000c481  test    rax, rax
0x18000c484  jnz     loc_18000C566
0x18000c48a  mov     [rsp+0D8h+var_A8], 8
0x18000c492  test    cs:byte_1800AA941, 4
0x18000c499  jz      loc_18000C52A
0x18000c49f  mov     word ptr [rsp+0D8h+var_48], di
0x18000c4a7  mov     rax, [rbx+70h]
0x18000c4ab  test    rax, rax
0x18000c4ae  jz      short loc_18000C4BA
0x18000c4b0  cmp     [rax+10h], rdi
0x18000c4b4  jz      short loc_18000C4BA
0x18000c4b6  mov     r15d, [rax+10h]
0x18000c4ba  mov     edx, r15d
0x18000c4bd  lea     rcx, [rsp+0D8h+var_48]
0x18000c4c5  call    ConvertPortNoToString
0x18000c4ca  test    cs:byte_1800AA941, 4
0x18000c4d1  jz      short loc_18000C52A
0x18000c4d3  mov     rdx, [rbx+70h]
0x18000c4d7  mov     rax, rdx
0x18000c4da  lea     rcx, [rdx+0A7Eh]
0x18000c4e1  neg     rax
0x18000c4e4  sbb     r8, r8
0x18000c4e7  and     r8, rcx
0x18000c4ea  test    rdx, rdx
0x18000c4ed  lea     r9, [rdx+848h]
0x18000c4f4  jnz     short loc_18000C4FE
0x18000c4f6  lea     r9, [rsp+0D8h+var_58]
0x18000c4fe  lea     rax, [rsp+0D8h+var_48]
0x18000c506  mov     [rsp+0D8h+var_B0], rax
0x18000c50b  mov     [rsp+0D8h+var_B8], r8
0x18000c510  lea     r8, aErrorNotEnough; "ERROR_NOT_ENOUGH_MEMORY"
0x18000c517  lea     rdx, RasVpnIkeParamTraceError
0x18000c51e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c525  call    McTemplateU0zjzz_EventWriteTransfer
0x18000c52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c531  cmp     rcx, rsi
0x18000c534  jz      loc_18000C5C6
0x18000c53a  test    byte ptr [rcx+1Ch], 1
0x18000c53e  jz      loc_18000C5C6
0x18000c544  cmp     byte ptr [rcx+19h], 2
0x18000c548  jb      short loc_18000C5C6
0x18000c54a  mov     edx, 0Ch
0x18000c54f  mov     r9d, [rsp+0D8h+var_A8]
0x18000c554  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000c55b  mov     rcx, [rcx+10h]
0x18000c55f  call    WPP_SF_d
0x18000c564  jmp     short loc_18000C5BF
0x18000c566  xor     r8d, r8d; pcbe
0x18000c569  mov     rdx, rbx; pv
0x18000c56c  lea     rcx, ?s_DeleteIpAddressCallback@VPNIKEConnection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000c573  call    cs:__imp_CreateThreadpoolWork
0x18000c579  mov     [rbx+160h], rax
0x18000c580  test    rax, rax
0x18000c583  jnz     short loc_18000C5BF
0x18000c585  call    cs:__imp_GetLastError
0x18000c58b  mov     [rsp+0D8h+var_A8], eax
0x18000c58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c596  cmp     rcx, rsi
0x18000c599  jz      short loc_18000C5C6
0x18000c59b  test    byte ptr [rcx+1Ch], 1
0x18000c59f  jz      short loc_18000C5C6
0x18000c5a1  cmp     byte ptr [rcx+19h], 2
0x18000c5a5  jb      short loc_18000C5C6
0x18000c5a7  mov     edx, 0Dh
0x18000c5ac  mov     r9d, eax
0x18000c5af  jmp     short loc_18000C554
0x18000c5b1  lea     rsi, WPP_GLOBAL_Control
0x18000c5b8  xor     edi, edi
0x18000c5ba  mov     rbx, [rsp+0D8h+var_A0]
0x18000c5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5c6  cmp     [rsp+0D8h+var_A8], edi
0x18000c5ca  jz      short loc_18000C620
0x18000c5cc  mov     rcx, rbx; this
0x18000c5cf  call    ?Cleanup@VPNIKEConnection@@AEAAXXZ; VPNIKEConnection::Cleanup(void)
0x18000c5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5db  cmp     rcx, rsi
0x18000c5de  jz      short loc_18000C606
0x18000c5e0  test    byte ptr [rcx+1Ch], 1
0x18000c5e4  jz      short loc_18000C606
0x18000c5e6  cmp     byte ptr [rcx+19h], 6
0x18000c5ea  jb      short loc_18000C606
0x18000c5ec  mov     edx, 0Eh
0x18000c5f1  mov     r9d, [rsp+0D8h+var_A8]
0x18000c5f6  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000c5fd  mov     rcx, [rcx+10h]
0x18000c601  call    WPP_SF_d
0x18000c606  mov     eax, [rsp+0D8h+var_A8]
0x18000c60a  mov     [rsp+0D8h+pExceptionObject], eax
0x18000c60e  lea     rdx, _TI1K; pThrowInfo
0x18000c615  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000c61a  call    _CxxThrowException_0
0x18000c620  cmp     rcx, rsi
0x18000c623  jz      short loc_18000C677
0x18000c625  test    byte ptr [rcx+1Ch], 1
0x18000c629  jz      short loc_18000C650
0x18000c62b  cmp     byte ptr [rcx+19h], 6
0x18000c62f  jb      short loc_18000C650
0x18000c631  mov     edx, 0Fh
0x18000c636  xor     r9d, r9d
0x18000c639  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000c640  mov     rcx, [rcx+10h]
0x18000c644  call    WPP_SF_d
0x18000c649  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c650  cmp     rcx, rsi
0x18000c653  jz      short loc_18000C677
0x18000c655  test    byte ptr [rcx+1Ch], 1
0x18000c659  jz      short loc_18000C677
0x18000c65b  cmp     byte ptr [rcx+19h], 6
0x18000c65f  jb      short loc_18000C677
0x18000c661  mov     edx, 10h
0x18000c666  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000c66d  mov     rcx, [rcx+10h]
0x18000c671  call    WPP_SF_
0x18000c676  nop
0x18000c677  lea     rcx, [rsp+0D8h+var_90]; this
0x18000c67c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000c681  nop
0x18000c682  mov     rax, rbx
0x18000c685  mov     rcx, [rsp+0D8h+var_20]
0x18000c68d  xor     rcx, rsp; StackCookie
0x18000c690  call    __security_check_cookie
0x18000c695  lea     r11, [rsp+0D8h+var_18]
0x18000c69d  mov     rbx, [r11+30h]
0x18000c6a1  mov     rsi, [r11+38h]
0x18000c6a5  mov     rsp, r11
0x18000c6a8  pop     r15
0x18000c6aa  pop     r14
0x18000c6ac  pop     rdi
0x18000c6ad  retn
```
