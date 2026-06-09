# VPNIKEClientConnection::NotifyUpdateConnectionStatus(ulong)

- ea: `0x18001af98`
- end: `0x18001b235`
- name: `?NotifyUpdateConnectionStatus@VPNIKEClientConnection@@IEAAXK@Z`
- size: `669`
- prototype: `void __fastcall(VPNIKEClientConnection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800194e0`
- `0x18001ca90`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18001af98`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `rasman!RasSetPortUserData` at `0x18001b115`
- `rasman!RasSetPortUserData` at `0x18001b115`

## string_xrefs

- `0x18001b166`: `UpdateConnection failed, close the connection. ErrorCode: %d`

## pseudocode

```c
void __fastcall VPNIKEClientConnection::NotifyUpdateConnectionStatus(VPNIKEClientConnection *this, unsigned int a2)
{
  int v4; // eax
  unsigned int v5; // esi
  __int64 v6; // rax
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  __int64 v9; // rdx
  __int128 *v10; // r9
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int128 *v14; // r9
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+4Ch] [rbp-B4h]
  __int128 v20; // [rsp+5Ch] [rbp-A4h]
  int v21; // [rsp+6Ch] [rbp-94h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, a2);
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v18 = 0;
  v21 = 0;
  v4 = 0x2000;
  if ( a2 )
    v4 = 1;
  v5 = -1;
  v19 = 0;
  v15 = v4;
  v20 = 0;
  v17 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v22) = 0;
    LOWORD(v18) = 0;
    v6 = *((_QWORD *)this + 14);
    if ( v6 && *(_QWORD *)(v6 + 16) )
      v7 = *(unsigned int *)(v6 + 16);
    else
      v7 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v18, v7);
    v8 = L"RASCSS_Reconnected";
    if ( a2 )
      v8 = L"RASCSS_Dormant";
    FormatRRASErrorString(&v22, L"Setting RASPortSubStatus to %s", v8);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v9 = *((_QWORD *)this + 14);
      LODWORD(v10) = v9 + 2120;
      if ( !v9 )
        v10 = &v17;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v22,
        (_DWORD)v10,
        (v9 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
        (__int64)&v18);
    }
  }
  RasSetPortUserData(*((_QWORD *)this + 3), 14, &v15);
  v16 = a2;
  if ( a2 )
  {
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v22) = 0;
      LOWORD(v18) = 0;
      v12 = *((_QWORD *)this + 14);
      if ( v12 && *(_QWORD *)(v12 + 16) )
        v5 = *(_DWORD *)(v12 + 16);
      ConvertPortNoToString(&v18, v5);
      FormatRRASErrorString(&v22, L"UpdateConnection failed, close the connection. ErrorCode: %d", a2);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v13 = *((_QWORD *)this + 14);
        LODWORD(v14) = v13 + 2120;
        if ( !v13 )
          v14 = &v17;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)&v22,
          (_DWORD)v14,
          (v13 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
          (__int64)&v18);
      }
    }
    v11 = 10;
  }
  else
  {
    v11 = 17;
  }
  VPNIKEProtocolEngine::NotifyCaller(*((_QWORD *)this + 3), v11, &v16);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
  }
}

```

## disassembly

```asm
0x18001af98  mov     [rsp-8+arg_10], rbx
0x18001af9d  push    rbp
0x18001af9e  push    rsi
0x18001af9f  push    rdi
0x18001afa0  push    r12
0x18001afa2  push    r14
0x18001afa4  lea     rbp, [rsp-780h]
0x18001afac  sub     rsp, 880h
0x18001afb3  mov     rax, cs:__security_cookie
0x18001afba  xor     rax, rsp
0x18001afbd  mov     [rbp+7A0h+var_30], rax
0x18001afc4  mov     edi, edx
0x18001afc6  mov     rbx, rcx
0x18001afc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afd0  lea     r12, WPP_GLOBAL_Control
0x18001afd7  mov     r14d, 1
0x18001afdd  cmp     rcx, r12
0x18001afe0  jz      short loc_18001B005
0x18001afe2  test    [rcx+1Ch], r14b
0x18001afe6  jz      short loc_18001B005
0x18001afe8  cmp     byte ptr [rcx+19h], 6
0x18001afec  jb      short loc_18001B005
0x18001afee  mov     rcx, [rcx+10h]
0x18001aff2  lea     edx, [r14+48h]
0x18001aff6  mov     r9d, edi
0x18001aff9  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001b000  call    WPP_SF_d
0x18001b005  xor     eax, eax
0x18001b007  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18001b00c  xor     edx, edx; Val
0x18001b00e  mov     [rsp+8A0h+var_830], eax
0x18001b012  mov     r8d, 7FCh; Size
0x18001b018  call    memset_0
0x18001b01d  xor     eax, eax
0x18001b01f  xorps   xmm0, xmm0
0x18001b022  mov     [rsp+8A0h+var_858], eax
0x18001b026  test    edi, edi
0x18001b028  mov     [rsp+8A0h+var_834], eax
0x18001b02c  mov     eax, 2000h
0x18001b031  cmovnz  eax, r14d
0x18001b035  or      esi, 0FFFFFFFFh
0x18001b038  test    cs:byte_1800AA941, 8
0x18001b03f  movups  [rsp+8A0h+var_854], xmm0
0x18001b044  mov     [rsp+8A0h+var_870], eax
0x18001b048  movups  [rsp+8A0h+var_844], xmm0
0x18001b04d  movups  [rsp+8A0h+var_868], xmm0
0x18001b052  jz      loc_18001B102
0x18001b058  xor     eax, eax
0x18001b05a  mov     word ptr [rsp+8A0h+var_830], ax
0x18001b05f  mov     word ptr [rsp+8A0h+var_858], ax
0x18001b064  mov     rax, [rbx+70h]
0x18001b068  test    rax, rax
0x18001b06b  jz      short loc_18001B079
0x18001b06d  cmp     qword ptr [rax+10h], 0
0x18001b072  jz      short loc_18001B079
0x18001b074  mov     edx, [rax+10h]
0x18001b077  jmp     short loc_18001B07B
0x18001b079  mov     edx, esi
0x18001b07b  lea     rcx, [rsp+8A0h+var_858]
0x18001b080  call    ConvertPortNoToString
0x18001b085  lea     rax, aRascssDormant; "RASCSS_Dormant"
0x18001b08c  test    edi, edi
0x18001b08e  lea     r8, aRascssReconnec; "RASCSS_Reconnected"
0x18001b095  cmovnz  r8, rax
0x18001b099  lea     rdx, aSettingRasport_0; "Setting RASPortSubStatus to %s"
0x18001b0a0  lea     rcx, [rsp+8A0h+var_830]
0x18001b0a5  call    FormatRRASErrorString
0x18001b0aa  test    cs:byte_1800AA941, 8
0x18001b0b1  jz      short loc_18001B102
0x18001b0b3  mov     rdx, [rbx+70h]
0x18001b0b7  mov     rax, rdx
0x18001b0ba  neg     rax
0x18001b0bd  sbb     r8, r8
0x18001b0c0  lea     rcx, [rdx+0A7Eh]
0x18001b0c7  and     r8, rcx
0x18001b0ca  lea     r9, [rdx+848h]
0x18001b0d1  test    rdx, rdx
0x18001b0d4  jnz     short loc_18001B0DB
0x18001b0d6  lea     r9, [rsp+8A0h+var_868]
0x18001b0db  lea     rax, [rsp+8A0h+var_858]
0x18001b0e0  mov     [rsp+8A0h+var_878], rax
0x18001b0e5  lea     rdx, RasVpnIkeParamTraceInfo
0x18001b0ec  mov     [rsp+8A0h+var_880], r8
0x18001b0f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b0f8  lea     r8, [rsp+8A0h+var_830]
0x18001b0fd  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b102  mov     rcx, [rbx+18h]
0x18001b106  lea     r8, [rsp+8A0h+var_870]
0x18001b10b  mov     r9d, 4
0x18001b111  lea     edx, [r9+0Ah]
0x18001b115  call    cs:__imp_RasSetPortUserData
0x18001b11b  mov     [rsp+8A0h+var_86C], edi
0x18001b11f  test    edi, edi
0x18001b121  jnz     short loc_18001B12B
0x18001b123  lea     edx, [rdi+11h]
0x18001b126  jmp     loc_18001B1D4
0x18001b12b  test    cs:byte_1800AA941, 8
0x18001b132  jz      loc_18001B1CF
0x18001b138  xor     eax, eax
0x18001b13a  mov     word ptr [rsp+8A0h+var_830], ax
0x18001b13f  mov     word ptr [rsp+8A0h+var_858], ax
0x18001b144  mov     rax, [rbx+70h]
0x18001b148  test    rax, rax
0x18001b14b  jz      short loc_18001B157
0x18001b14d  cmp     qword ptr [rax+10h], 0
0x18001b152  jz      short loc_18001B157
0x18001b154  mov     esi, [rax+10h]
0x18001b157  mov     edx, esi
0x18001b159  lea     rcx, [rsp+8A0h+var_858]
0x18001b15e  call    ConvertPortNoToString
0x18001b163  mov     r8d, edi
0x18001b166  lea     rdx, aUpdateconnecti; "UpdateConnection failed, close the conn"...
0x18001b16d  lea     rcx, [rsp+8A0h+var_830]
0x18001b172  call    FormatRRASErrorString
0x18001b177  test    cs:byte_1800AA941, 8
0x18001b17e  jz      short loc_18001B1CF
0x18001b180  mov     rdx, [rbx+70h]
0x18001b184  mov     rax, rdx
0x18001b187  neg     rax
0x18001b18a  sbb     r8, r8
0x18001b18d  lea     rcx, [rdx+0A7Eh]
0x18001b194  and     r8, rcx
0x18001b197  lea     r9, [rdx+848h]
0x18001b19e  test    rdx, rdx
0x18001b1a1  jnz     short loc_18001B1A8
0x18001b1a3  lea     r9, [rsp+8A0h+var_868]
0x18001b1a8  lea     rax, [rsp+8A0h+var_858]
0x18001b1ad  mov     [rsp+8A0h+var_878], rax
0x18001b1b2  lea     rdx, RasVpnIkeParamTraceInfo
0x18001b1b9  mov     [rsp+8A0h+var_880], r8
0x18001b1be  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b1c5  lea     r8, [rsp+8A0h+var_830]
0x18001b1ca  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b1cf  mov     edx, 0Ah
0x18001b1d4  mov     rcx, [rbx+18h]
0x18001b1d8  lea     r8, [rsp+8A0h+var_86C]
0x18001b1dd  call    ?NotifyCaller@VPNIKEProtocolEngine@@SAXPEAXW4_PROTOCOL_RESULT_ID@@0@Z; VPNIKEProtocolEngine::NotifyCaller(void *,_PROTOCOL_RESULT_ID,void *)
0x18001b1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1e9  cmp     rcx, r12
0x18001b1ec  jz      short loc_18001B20F
0x18001b1ee  test    [rcx+1Ch], r14b
0x18001b1f2  jz      short loc_18001B20F
0x18001b1f4  cmp     byte ptr [rcx+19h], 6
0x18001b1f8  jb      short loc_18001B20F
0x18001b1fa  mov     rcx, [rcx+10h]
0x18001b1fe  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001b205  mov     edx, 4Ah ; 'J'
0x18001b20a  call    WPP_SF_
0x18001b20f  mov     rcx, [rbp+7A0h+var_30]
0x18001b216  xor     rcx, rsp; StackCookie
0x18001b219  call    __security_check_cookie
0x18001b21e  mov     rbx, [rsp+8A0h+arg_10]
0x18001b226  add     rsp, 880h
0x18001b22d  pop     r14
0x18001b22f  pop     r12
0x18001b231  pop     rdi
0x18001b232  pop     rsi
0x18001b233  pop     rbp
0x18001b234  retn
```
