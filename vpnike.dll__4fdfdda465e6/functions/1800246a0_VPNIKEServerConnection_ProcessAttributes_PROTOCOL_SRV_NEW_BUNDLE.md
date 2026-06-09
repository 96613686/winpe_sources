# VPNIKEServerConnection::ProcessAttributes(_PROTOCOL_SRV_NEW_BUNDLE &)

- ea: `0x1800246a0`
- end: `0x180024bfc`
- name: `?ProcessAttributes@VPNIKEServerConnection@@QEAAKAEAU_PROTOCOL_SRV_NEW_BUNDLE@@@Z`
- size: `1372`
- prototype: `__int64 __fastcall(VPNIKEServerConnection *this, struct _PROTOCOL_SRV_NEW_BUNDLE *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800242d4`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000eb54`
- `0x18000ee60`
- `0x1800246a0`
- `0x18002676c`
- `0x180026a7c`
- `0x180064f5c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x180024816`: `Configured QuarantineSessionTimeout: [%u sec]`
- `0x1800249fa`: `Configured SessionTimeout: [%u sec]`
- `0x180024a79`: `Configured IdleTimeOut: [%u sec]`

## pseudocode

```c
__int64 __fastcall VPNIKEServerConnection::ProcessAttributes(
        VPNIKEServerConnection *this,
        struct _PROTOCOL_SRV_NEW_BUNDLE *a2)
{
  unsigned int v4; // r15d
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned __int8 v7; // dl
  unsigned int v8; // esi
  char v9; // al
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int128 *v13; // r9
  unsigned int v14; // r14d
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int128 *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int128 *v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  __int128 *v27; // r9
  unsigned int v28; // ebx
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h]
  __int128 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  int v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+6Ch] [rbp-94h]
  __int128 v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+80h] [rbp-80h] BYREF
  __int128 v39; // [rsp+84h] [rbp-7Ch]
  __int128 v40; // [rsp+94h] [rbp-6Ch]
  int v41; // [rsp+A4h] [rbp-5Ch]
  int v42; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v43[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  v30 = 0;
  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v37 = 0;
  v32 = 0;
  v31 = 0;
  v33 = 0;
  v34 = 0;
  v4 = -1;
  v35 = -1;
  v36 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v31,
      L"VPNIKEServerConnection::ProcessAttributes",
      &v30,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
  *((_DWORD *)a2 + 11) = *((_DWORD *)this + 91);
  v5 = *((_QWORD *)this + 15);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v30 = ProcessNPSAuthAttributes(*((_QWORD *)this + 3), v6, a2);
    if ( !v30 )
    {
      if ( (*(_BYTE *)a2 & 3) != 0 )
      {
        v8 = *((_DWORD *)a2 + 16);
        v9 = byte_1800AA941;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          v10 = *((_QWORD *)this + 14);
          if ( v10 && *(_QWORD *)(v10 + 16) )
            v11 = *(unsigned int *)(v10 + 16);
          else
            v11 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v38, v11);
          FormatRRASErrorString(&v42, L"Configured QuarantineSessionTimeout: [%u sec]", v8);
          v9 = byte_1800AA941;
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v12 = *((_QWORD *)this + 14);
            LODWORD(v13) = v12 + 2120;
            if ( !v12 )
              v13 = &v37;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v42,
              (_DWORD)v13,
              (v12 + 2686) & -(__int64)(v12 != 0),
              (__int64)&v38);
            v9 = byte_1800AA941;
          }
        }
        if ( (*(_BYTE *)a2 & 4) == 0 )
          goto LABEL_30;
        v14 = *((_DWORD *)a2 + 15);
        if ( v8 <= v14 )
          goto LABEL_30;
        v8 = *((_DWORD *)a2 + 15);
        if ( (v9 & 8) == 0 )
          goto LABEL_30;
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        v15 = *((_QWORD *)this + 14);
        if ( v15 && *(_QWORD *)(v15 + 16) )
          v16 = *(unsigned int *)(v15 + 16);
        else
          v16 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v38, v16);
        FormatRRASErrorString(
          &v42,
          L"SessionTimeout < QuarantineSessionTimeout: Hence use SessionTime [%u sec] as QuarantineSessionTimeout.",
          v14);
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_30;
        v17 = *((_QWORD *)this + 14);
        LODWORD(v18) = v17 + 2120;
        if ( !v17 )
          v18 = &v37;
      }
      else
      {
        v8 = 0;
        if ( (*(_BYTE *)a2 & 4) == 0 )
          goto LABEL_30;
        v8 = *((_DWORD *)a2 + 15);
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_30;
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        v21 = *((_QWORD *)this + 14);
        if ( v21 && *(_QWORD *)(v21 + 16) )
          v22 = *(unsigned int *)(v21 + 16);
        else
          v22 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v38, v22);
        FormatRRASErrorString(&v42, L"Configured SessionTimeout: [%u sec]", v8);
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_30;
        v17 = *((_QWORD *)this + 14);
        LODWORD(v18) = v17 + 2120;
        if ( !v17 )
          v18 = &v37;
      }
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v42,
        (_DWORD)v18,
        (v17 + 2686) & -(__int64)(v17 != 0),
        (__int64)&v38);
LABEL_30:
      if ( *((_DWORD *)this + 25) != v8 || *((_DWORD *)this + 91) != *((_DWORD *)a2 + 11) )
      {
        VPNIKEServerConnection::SessionTimerStop(this, 1u);
        *((_DWORD *)this + 25) = v8;
        VPNIKEServerConnection::SessionTimerStart(this);
      }
      if ( *((_DWORD *)this + 24) != *((_DWORD *)a2 + 14) )
      {
        VPNIKEConnection::IdleTimerStop(this, v7);
        *((_DWORD *)this + 24) = *((_DWORD *)a2 + 14);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          v19 = *((_QWORD *)this + 14);
          if ( v19 && *(_QWORD *)(v19 + 16) )
            v20 = *(unsigned int *)(v19 + 16);
          else
            v20 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v38, v20);
          FormatRRASErrorString(&v42, L"Configured IdleTimeOut: [%u sec]", *((unsigned int *)this + 24));
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v23 = *((_QWORD *)this + 14);
            LODWORD(v24) = v23 + 2120;
            if ( !v23 )
              v24 = &v37;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v42,
              (_DWORD)v24,
              (v23 + 2686) & -(__int64)(v23 != 0),
              (__int64)&v38);
          }
        }
        VPNIKEConnection::IdleTimerStart(this);
      }
      *((_DWORD *)this + 91) = *((_DWORD *)a2 + 11);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        v25 = *((_QWORD *)this + 14);
        if ( v25 && *(_QWORD *)(v25 + 16) )
          v4 = *(_DWORD *)(v25 + 16);
        ConvertPortNoToString(&v38, v4);
        FormatRRASErrorString(&v42, L"QuarantineState: %u", *((unsigned int *)this + 91));
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v26 = *((_QWORD *)this + 14);
          LODWORD(v27) = v26 + 2120;
          if ( !v26 )
            v27 = &v37;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v42,
            (_DWORD)v27,
            (v26 + 2686) & -(__int64)(v26 != 0),
            (__int64)&v38);
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids, v30);
  }
  v28 = v30;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v31);
  return v28;
}

```

## disassembly

```asm
0x1800246a0  mov     [rsp-8+arg_10], rbx
0x1800246a5  push    rbp
0x1800246a6  push    rsi
0x1800246a7  push    rdi
0x1800246a8  push    r14
0x1800246aa  push    r15
0x1800246ac  lea     rbp, [rsp-7C0h]
0x1800246b4  sub     rsp, 8C0h
0x1800246bb  mov     rax, cs:__security_cookie
0x1800246c2  xor     rax, rsp
0x1800246c5  mov     [rbp+7E0h+var_30], rax
0x1800246cc  mov     rdi, rdx
0x1800246cf  mov     rbx, rcx
0x1800246d2  lea     r14, WPP_GLOBAL_Control
0x1800246d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246e0  cmp     rcx, r14
0x1800246e3  jz      short loc_180024706
0x1800246e5  test    byte ptr [rcx+1Ch], 1
0x1800246e9  jz      short loc_180024706
0x1800246eb  cmp     byte ptr [rcx+19h], 6
0x1800246ef  jb      short loc_180024706
0x1800246f1  mov     edx, 49h ; 'I'
0x1800246f6  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x1800246fd  mov     rcx, [rcx+10h]
0x180024701  call    WPP_SF_
0x180024706  mov     [rsp+8E0h+var_8B0], 0
0x18002470e  xor     eax, eax
0x180024710  mov     [rbp+7E0h+var_830], eax
0x180024713  xor     edx, edx; Val
0x180024715  mov     r8d, 7FCh; Size
0x18002471b  lea     rcx, [rbp+7E0h+var_82C]; void *
0x18002471f  call    memset_0
0x180024724  xor     eax, eax
0x180024726  mov     [rbp+7E0h+var_860], eax
0x180024729  xorps   xmm0, xmm0
0x18002472c  movups  [rbp+7E0h+var_85C], xmm0
0x180024730  movups  [rbp+7E0h+var_84C], xmm0
0x180024734  mov     [rbp+7E0h+var_83C], eax
0x180024737  movups  [rsp+8E0h+var_870], xmm0
0x18002473c  xorps   xmm1, xmm1
0x18002473f  movdqu  [rsp+8E0h+var_8A0], xmm1
0x180024745  mov     [rsp+8E0h+var_8A8], rax
0x18002474a  movdqu  [rsp+8E0h+var_890], xmm0
0x180024750  mov     [rsp+8E0h+var_880], rax
0x180024755  or      r15d, 0FFFFFFFFh
0x180024759  mov     [rsp+8E0h+var_878], r15d
0x18002475e  mov     [rsp+8E0h+var_874], eax
0x180024762  test    cs:byte_1800AA941, 8
0x180024769  jz      short loc_180024791
0x18002476b  mov     rax, [rbx+70h]
0x18002476f  mov     [rsp+8E0h+var_8C0], rax; void *
0x180024774  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002477b  lea     r8, [rsp+8E0h+var_8B0]; unsigned int *
0x180024780  lea     rdx, aVpnikeserverco_11; "VPNIKEServerConnection::ProcessAttribut"...
0x180024787  lea     rcx, [rsp+8E0h+var_8A8]; this
0x18002478c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180024791  mov     eax, [rbx+16Ch]
0x180024797  mov     [rdi+2Ch], eax
0x18002479a  mov     rcx, [rbx+78h]
0x18002479e  test    rcx, rcx
0x1800247a1  jz      loc_180024B94
0x1800247a7  mov     rax, [rcx]
0x1800247aa  mov     rax, [rax+10h]
0x1800247ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247b3  mov     r8, rdi
0x1800247b6  mov     rdx, rax
0x1800247b9  mov     rcx, [rbx+18h]
0x1800247bd  call    ProcessNPSAuthAttributes
0x1800247c2  mov     [rsp+8E0h+var_8B0], eax
0x1800247c6  test    eax, eax
0x1800247c8  jnz     loc_180024B94
0x1800247ce  test    byte ptr [rdi], 3
0x1800247d1  jz      loc_1800249B5
0x1800247d7  mov     esi, [rdi+40h]
0x1800247da  mov     al, cs:byte_1800AA941
0x1800247e0  test    al, 8
0x1800247e2  jz      loc_180024883
0x1800247e8  xor     eax, eax
0x1800247ea  mov     word ptr [rbp+7E0h+var_830], ax
0x1800247ee  mov     word ptr [rbp+7E0h+var_860], ax
0x1800247f2  mov     rax, [rbx+70h]
0x1800247f6  test    rax, rax
0x1800247f9  jz      short loc_180024807
0x1800247fb  cmp     qword ptr [rax+10h], 0
0x180024800  jz      short loc_180024807
0x180024802  mov     edx, [rax+10h]
0x180024805  jmp     short loc_18002480A
0x180024807  mov     edx, r15d
0x18002480a  lea     rcx, [rbp+7E0h+var_860]
0x18002480e  call    ConvertPortNoToString
0x180024813  mov     r8d, esi
0x180024816  lea     rdx, aConfiguredQuar; "Configured QuarantineSessionTimeout: [%"...
0x18002481d  lea     rcx, [rbp+7E0h+var_830]
0x180024821  call    FormatRRASErrorString
0x180024826  mov     al, cs:byte_1800AA941
0x18002482c  test    al, 8
0x18002482e  jz      short loc_180024883
0x180024830  mov     rdx, [rbx+70h]
0x180024834  mov     rax, rdx
0x180024837  lea     rcx, [rdx+0A7Eh]
0x18002483e  neg     rax
0x180024841  sbb     r8, r8
0x180024844  and     r8, rcx
0x180024847  test    rdx, rdx
0x18002484a  lea     r9, [rdx+848h]
0x180024851  jnz     short loc_180024858
0x180024853  lea     r9, [rsp+8E0h+var_870]
0x180024858  lea     rax, [rbp+7E0h+var_860]
0x18002485c  mov     [rsp+8E0h+var_8B8], rax
0x180024861  mov     [rsp+8E0h+var_8C0], r8
0x180024866  lea     r8, [rbp+7E0h+var_830]
0x18002486a  lea     rdx, RasVpnIkeParamTraceInfo
0x180024871  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024878  call    McTemplateU0zjzz_EventWriteTransfer
0x18002487d  mov     al, cs:byte_1800AA941
0x180024883  test    byte ptr [rdi], 4
0x180024886  jz      loc_18002493F
0x18002488c  mov     r14d, [rdi+3Ch]
0x180024890  cmp     esi, r14d
0x180024893  jbe     loc_180024938
0x180024899  mov     esi, r14d
0x18002489c  test    al, 8
0x18002489e  jz      loc_180024938
0x1800248a4  xor     eax, eax
0x1800248a6  mov     word ptr [rbp+7E0h+var_830], ax
0x1800248aa  mov     word ptr [rbp+7E0h+var_860], ax
0x1800248ae  mov     rax, [rbx+70h]
0x1800248b2  test    rax, rax
0x1800248b5  jz      short loc_1800248C3
0x1800248b7  cmp     qword ptr [rax+10h], 0
0x1800248bc  jz      short loc_1800248C3
0x1800248be  mov     edx, [rax+10h]
0x1800248c1  jmp     short loc_1800248C6
0x1800248c3  mov     edx, r15d
0x1800248c6  lea     rcx, [rbp+7E0h+var_860]
0x1800248ca  call    ConvertPortNoToString
0x1800248cf  mov     r8d, r14d
0x1800248d2  lea     rdx, aSessiontimeout; "SessionTimeout < QuarantineSessionTimeo"...
0x1800248d9  lea     rcx, [rbp+7E0h+var_830]
0x1800248dd  call    FormatRRASErrorString
0x1800248e2  test    cs:byte_1800AA941, 8
0x1800248e9  jz      short loc_180024938
0x1800248eb  mov     rdx, [rbx+70h]
0x1800248ef  mov     rax, rdx
0x1800248f2  lea     rcx, [rdx+0A7Eh]
0x1800248f9  neg     rax
0x1800248fc  sbb     r8, r8
0x1800248ff  and     r8, rcx
0x180024902  test    rdx, rdx
0x180024905  lea     r9, [rdx+848h]
0x18002490c  jnz     short loc_180024913
0x18002490e  lea     r9, [rsp+8E0h+var_870]
0x180024913  lea     rax, [rbp+7E0h+var_860]
0x180024917  mov     [rsp+8E0h+var_8B8], rax
0x18002491c  mov     [rsp+8E0h+var_8C0], r8
0x180024921  lea     r8, [rbp+7E0h+var_830]
0x180024925  lea     rdx, RasVpnIkeParamTraceInfo
0x18002492c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024933  call    McTemplateU0zjzz_EventWriteTransfer
0x180024938  lea     r14, WPP_GLOBAL_Control
0x18002493f  cmp     [rbx+64h], esi
0x180024942  jnz     short loc_18002494F
0x180024944  mov     eax, [rdi+2Ch]
0x180024947  cmp     [rbx+16Ch], eax
0x18002494d  jz      short loc_180024964
0x18002494f  mov     dl, 1; unsigned __int8
0x180024951  mov     rcx, rbx; this
0x180024954  call    ?SessionTimerStop@VPNIKEServerConnection@@IEAAKE@Z; VPNIKEServerConnection::SessionTimerStop(uchar)
0x180024959  mov     [rbx+64h], esi
0x18002495c  mov     rcx, rbx; this
0x18002495f  call    ?SessionTimerStart@VPNIKEServerConnection@@IEAAKXZ; VPNIKEServerConnection::SessionTimerStart(void)
0x180024964  mov     eax, [rdi+38h]
0x180024967  cmp     [rbx+60h], eax
0x18002496a  jz      loc_180024AE7
0x180024970  mov     rcx, rbx; this
0x180024973  call    ?IdleTimerStop@VPNIKEConnection@@QEAAKE@Z; VPNIKEConnection::IdleTimerStop(uchar)
0x180024978  mov     eax, [rdi+38h]
0x18002497b  mov     [rbx+60h], eax
0x18002497e  test    cs:byte_1800AA941, 8
0x180024985  jz      loc_180024ADF
0x18002498b  xor     eax, eax
0x18002498d  mov     word ptr [rbp+7E0h+var_830], ax
0x180024991  mov     word ptr [rbp+7E0h+var_860], ax
0x180024995  mov     rax, [rbx+70h]
0x180024999  test    rax, rax
0x18002499c  jz      loc_180024A69
0x1800249a2  cmp     qword ptr [rax+10h], 0
0x1800249a7  jz      loc_180024A69
0x1800249ad  mov     edx, [rax+10h]
0x1800249b0  jmp     loc_180024A6C
0x1800249b5  xor     esi, esi
0x1800249b7  test    byte ptr [rdi], 4
0x1800249ba  jz      short loc_18002493F
0x1800249bc  mov     esi, [rdi+3Ch]
0x1800249bf  test    cs:byte_1800AA941, 8
0x1800249c6  jz      loc_18002493F
0x1800249cc  xor     eax, eax
0x1800249ce  mov     word ptr [rbp+7E0h+var_830], ax
0x1800249d2  mov     word ptr [rbp+7E0h+var_860], ax
0x1800249d6  mov     rax, [rbx+70h]
0x1800249da  test    rax, rax
0x1800249dd  jz      short loc_1800249EB
0x1800249df  cmp     qword ptr [rax+10h], 0
0x1800249e4  jz      short loc_1800249EB
0x1800249e6  mov     edx, [rax+10h]
0x1800249e9  jmp     short loc_1800249EE
0x1800249eb  mov     edx, r15d
0x1800249ee  lea     rcx, [rbp+7E0h+var_860]
0x1800249f2  call    ConvertPortNoToString
0x1800249f7  mov     r8d, esi
0x1800249fa  lea     rdx, aConfiguredSess; "Configured SessionTimeout: [%u sec]"
0x180024a01  lea     rcx, [rbp+7E0h+var_830]
0x180024a05  call    FormatRRASErrorString
0x180024a0a  test    cs:byte_1800AA941, 8
0x180024a11  jz      loc_18002493F
0x180024a17  mov     rdx, [rbx+70h]
0x180024a1b  mov     rax, rdx
0x180024a1e  lea     rcx, [rdx+0A7Eh]
0x180024a25  neg     rax
0x180024a28  sbb     r8, r8
0x180024a2b  and     r8, rcx
0x180024a2e  test    rdx, rdx
0x180024a31  lea     r9, [rdx+848h]
0x180024a38  jnz     short loc_180024A3F
0x180024a3a  lea     r9, [rsp+8E0h+var_870]
0x180024a3f  lea     rax, [rbp+7E0h+var_860]
0x180024a43  mov     [rsp+8E0h+var_8B8], rax
0x180024a48  mov     [rsp+8E0h+var_8C0], r8
0x180024a4d  lea     r8, [rbp+7E0h+var_830]
0x180024a51  lea     rdx, RasVpnIkeParamTraceInfo
0x180024a58  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024a5f  call    McTemplateU0zjzz_EventWriteTransfer
0x180024a64  jmp     loc_18002493F
0x180024a69  mov     edx, r15d
0x180024a6c  lea     rcx, [rbp+7E0h+var_860]
0x180024a70  call    ConvertPortNoToString
0x180024a75  mov     r8d, [rbx+60h]
0x180024a79  lea     rdx, aConfiguredIdle_0; "Configured IdleTimeOut: [%u sec]"
0x180024a80  lea     rcx, [rbp+7E0h+var_830]
0x180024a84  call    FormatRRASErrorString
0x180024a89  test    cs:byte_1800AA941, 8
0x180024a90  jz      short loc_180024ADF
0x180024a92  mov     rdx, [rbx+70h]
0x180024a96  mov     rax, rdx
0x180024a99  lea     rcx, [rdx+0A7Eh]
0x180024aa0  neg     rax
0x180024aa3  sbb     r8, r8
0x180024aa6  and     r8, rcx
0x180024aa9  test    rdx, rdx
0x180024aac  lea     r9, [rdx+848h]
0x180024ab3  jnz     short loc_180024ABA
0x180024ab5  lea     r9, [rsp+8E0h+var_870]
0x180024aba  lea     rax, [rbp+7E0h+var_860]
0x180024abe  mov     [rsp+8E0h+var_8B8], rax
0x180024ac3  mov     [rsp+8E0h+var_8C0], r8
0x180024ac8  lea     r8, [rbp+7E0h+var_830]
0x180024acc  lea     rdx, RasVpnIkeParamTraceInfo
0x180024ad3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024ada  call    McTemplateU0zjzz_EventWriteTransfer
0x180024adf  mov     rcx, rbx; this
0x180024ae2  call    ?IdleTimerStart@VPNIKEConnection@@IEAAKXZ; VPNIKEConnection::IdleTimerStart(void)
0x180024ae7  mov     eax, [rdi+2Ch]
0x180024aea  mov     [rbx+16Ch], eax
0x180024af0  test    cs:byte_1800AA941, 8
0x180024af7  jz      loc_180024B94
0x180024afd  xor     eax, eax
0x180024aff  mov     word ptr [rbp+7E0h+var_830], ax
0x180024b03  mov     word ptr [rbp+7E0h+var_860], ax
0x180024b07  mov     rax, [rbx+70h]
0x180024b0b  test    rax, rax
0x180024b0e  jz      short loc_180024B1B
0x180024b10  cmp     qword ptr [rax+10h], 0
0x180024b15  jz      short loc_180024B1B
0x180024b17  mov     r15d, [rax+10h]
0x180024b1b  mov     edx, r15d
0x180024b1e  lea     rcx, [rbp+7E0h+var_860]
0x180024b22  call    ConvertPortNoToString
0x180024b27  mov     r8d, [rbx+16Ch]
0x180024b2e  lea     rdx, aQuarantinestat; "QuarantineState: %u"
0x180024b35  lea     rcx, [rbp+7E0h+var_830]
0x180024b39  call    FormatRRASErrorString
0x180024b3e  test    cs:byte_1800AA941, 8
0x180024b45  jz      short loc_180024B94
0x180024b47  mov     rdx, [rbx+70h]
0x180024b4b  mov     rax, rdx
0x180024b4e  lea     rcx, [rdx+0A7Eh]
0x180024b55  neg     rax
0x180024b58  sbb     r8, r8
0x180024b5b  and     r8, rcx
0x180024b5e  test    rdx, rdx
0x180024b61  lea     r9, [rdx+848h]
0x180024b68  jnz     short loc_180024B6F
0x180024b6a  lea     r9, [rsp+8E0h+var_870]
0x180024b6f  lea     rax, [rbp+7E0h+var_860]
0x180024b73  mov     [rsp+8E0h+var_8B8], rax
0x180024b78  mov     [rsp+8E0h+var_8C0], r8
0x180024b7d  lea     r8, [rbp+7E0h+var_830]
0x180024b81  lea     rdx, RasVpnIkeParamTraceInfo
0x180024b88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024b8f  call    McTemplateU0zjzz_EventWriteTransfer
  ... truncated ...
```
