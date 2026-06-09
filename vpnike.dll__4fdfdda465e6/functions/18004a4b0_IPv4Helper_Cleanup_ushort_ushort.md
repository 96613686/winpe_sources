# IPv4Helper::Cleanup(ushort *,ushort *)

- ea: `0x18004a4b0`
- end: `0x18004ac74`
- name: `?Cleanup@IPv4Helper@@QEAAKPEAG0@Z`
- size: `1988`
- prototype: `__int64 __fastcall(IPv4Helper *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e030`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18004a4b0`
- `0x18004c488`
- `0x180069b40`
- `0x180070498`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004abeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004abeb`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18004a6e1`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18004a6e1`

## string_xrefs

- `0x18004a655`: `RasUpdateDefaultRouteSettings failed: %d`

## pseudocode

```c
__int64 __fastcall IPv4Helper::Cleanup(IPv4Helper *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rdi
  int v7; // r12d
  __int128 v8; // xmm6
  __int64 v9; // rdx
  unsigned int v10; // r15d
  _DWORD *v11; // rdi
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int128 *v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int128 *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int128 *v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int128 *v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int128 *v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int128 *v38; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  __int128 *v41; // r9
  unsigned int v42; // ebx
  unsigned int v44; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v45[3]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v46[40]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+80h] [rbp-88h]
  int v48; // [rsp+88h] [rbp-80h]
  int v49; // [rsp+8Ch] [rbp-7Ch]
  __int128 v50; // [rsp+90h] [rbp-78h] BYREF
  __int128 v51; // [rsp+A8h] [rbp-60h]
  int v52; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v53; // [rsp+BCh] [rbp-4Ch]
  __int128 v54; // [rsp+CCh] [rbp-3Ch]
  int v55; // [rsp+DCh] [rbp-2Ch]
  int v56; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v57[2044]; // [rsp+ECh] [rbp-1Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids);
  }
  v44 = 0;
  v6 = *((_QWORD *)this + 7);
  v7 = *(_DWORD *)(v6 + 1472);
  v51 = 0;
  v8 = *(_OWORD *)(v6 + 2120);
  v51 = v8;
  v56 = 0;
  memset_0(v57, 0, sizeof(v57));
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v50 = 0;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v10 = -1;
  v48 = -1;
  v49 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)v46,
      L"IPv4Helper::Cleanup",
      &v44,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      (void *)v6);
    v8 = v51;
  }
  if ( v7 == 2 || (v11 = (_DWORD *)((char *)this + 76), *((_DWORD *)this + 19)) )
  {
    v21 = *((unsigned int *)this + 5);
    if ( (_DWORD)v21 )
    {
      *(_OWORD *)&v45[1] = v8;
      (*(void (__fastcall **)(_QWORD *, __int64, unsigned __int16 *, unsigned __int16 *, int))(*((_QWORD *)this + 43)
                                                                                             + 24LL))(
        &v45[1],
        v21,
        a2,
        a3,
        1);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v52) = 0;
        v22 = *((_QWORD *)this + 7);
        if ( v22 && *(_QWORD *)(v22 + 16) )
          v23 = *(unsigned int *)(v22 + 16);
        else
          v23 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v52, v23);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v24 = *((_QWORD *)this + 7);
          LODWORD(v25) = v24 + 2120;
          if ( !v24 )
            v25 = &v50;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"ReleaseIpv4AddressOfClient done",
            (_DWORD)v25,
            (v24 + 2686) & -(__int64)(v24 != 0),
            (__int64)&v52);
        }
      }
      *((_DWORD *)this + 5) = 0;
      v8 = v51;
    }
    if ( v7 != 2 )
    {
      v11 = (_DWORD *)((char *)this + 76);
      if ( *((_DWORD *)this + 19) )
      {
        *((_DWORD *)this + 85) = 0;
        goto LABEL_72;
      }
      goto LABEL_73;
    }
    v26 = *(unsigned int *)this;
    if ( (_DWORD)v26 )
    {
      *(_OWORD *)&v45[1] = v8;
      (*(void (__fastcall **)(_QWORD *, __int64, unsigned __int16 *, unsigned __int16 *, int))(*((_QWORD *)this + 43)
                                                                                             + 24LL))(
        &v45[1],
        v26,
        a2,
        a3,
        1);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v52) = 0;
        v27 = *((_QWORD *)this + 7);
        if ( v27 && *(_QWORD *)(v27 + 16) )
          v28 = *(unsigned int *)(v27 + 16);
        else
          v28 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v52, v28);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v29 = *((_QWORD *)this + 7);
          LODWORD(v30) = v29 + 2120;
          if ( !v29 )
            v30 = &v50;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"ReleaseIpv4AddressOfClient done",
            (_DWORD)v30,
            (v29 + 2686) & -(__int64)(v29 != 0),
            (__int64)&v52);
        }
      }
      *(_DWORD *)this = 0;
    }
    v11 = (_DWORD *)((char *)this + 76);
    if ( (*((_BYTE *)this + 360) & 8) != 0 )
    {
      v44 = ResetIpAddressOnInterface((*((_QWORD *)this + 6) >> 24) & 0xFFFFFFLL, *(unsigned int *)this);
      if ( v44 && (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v56) = 0;
        LOWORD(v52) = 0;
        v31 = *((_QWORD *)this + 7);
        if ( v31 && *(_QWORD *)(v31 + 16) )
          v32 = *(unsigned int *)(v31 + 16);
        else
          v32 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v52, v32);
        FormatRRASErrorString(&v56, L"ResetIpAddressOnInterface failed: %d", v44);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v33 = *((_QWORD *)this + 7);
          LODWORD(v34) = v33 + 2120;
          if ( !v33 )
            v34 = &v50;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v56,
            (_DWORD)v34,
            (v33 + 2686) & -(__int64)(v33 != 0),
            (__int64)&v52);
        }
      }
      *((_DWORD *)this + 90) &= ~8u;
      goto LABEL_73;
    }
  }
  else
  {
    v12 = *((_DWORD *)this + 90);
    if ( (v12 & 1) != 0 )
    {
      LOBYTE(v9) = 1;
      v44 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD))xmmword_1800AA9C0)(0, v9, *((_QWORD *)this + 6));
      if ( v44 && (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v56) = 0;
        LOWORD(v52) = 0;
        v13 = *((_QWORD *)this + 7);
        if ( v13 && *(_QWORD *)(v13 + 16) )
          v14 = *(unsigned int *)(v13 + 16);
        else
          v14 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v52, v14);
        FormatRRASErrorString(&v56, L"RasUpdateDefaultRouteSettings failed: %d", v44);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v15 = *((_QWORD *)this + 7);
          LODWORD(v16) = v15 + 2120;
          if ( !v15 )
            v16 = &v50;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v56,
            (_DWORD)v16,
            (v15 + 2686) & -(__int64)(v15 != 0),
            (__int64)&v52);
        }
      }
      *((_DWORD *)this + 90) &= ~1u;
      v12 = *((_DWORD *)this + 90);
    }
    if ( (v12 & 2) != 0 )
    {
      v44 = RasFreeInterfaceLuidIndex(
              *(_QWORD *)(*((_QWORD *)this + 7) + 16LL),
              (*((_QWORD *)this + 6) >> 24) & 0xFFFFFFLL);
      if ( v44 && (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v56) = 0;
        LOWORD(v52) = 0;
        v17 = *((_QWORD *)this + 7);
        if ( v17 && *(_QWORD *)(v17 + 16) )
          v18 = *(unsigned int *)(v17 + 16);
        else
          v18 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v52, v18);
        FormatRRASErrorString(&v56, L"RasFreeInterfaceLuidIndex failed: %d", v44);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v19 = *((_QWORD *)this + 7);
          LODWORD(v20) = v19 + 2120;
          if ( !v19 )
            v20 = &v50;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v56,
            (_DWORD)v20,
            (v19 + 2686) & -(__int64)(v19 != 0),
            (__int64)&v52);
        }
      }
      *((_DWORD *)this + 90) &= ~2u;
LABEL_72:
      if ( *v11 )
        goto LABEL_74;
      goto LABEL_73;
    }
  }
  if ( v7 != 2 )
    goto LABEL_72;
LABEL_73:
  IPv4Helper::ResetIPv4Settings(this);
LABEL_74:
  if ( (*((_BYTE *)this + 360) & 4) != 0 )
  {
    v44 = ((__int64 (__fastcall *)(_QWORD, __int64))xmmword_1800AA9B0)(*(_QWORD *)(*((_QWORD *)this + 7) + 32LL), 2048);
    if ( v44 && (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v56) = 0;
      LOWORD(v52) = 0;
      v35 = *((_QWORD *)this + 7);
      if ( v35 && *(_QWORD *)(v35 + 16) )
        v36 = *(unsigned int *)(v35 + 16);
      else
        v36 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v52, v36);
      FormatRRASErrorString(&v56, L"RasDeAllocateRoute failed: %d", v44);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v37 = *((_QWORD *)this + 7);
        LODWORD(v38) = v37 + 2120;
        if ( !v37 )
          v38 = &v50;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v56,
          (_DWORD)v38,
          (v37 + 2686) & -(__int64)(v37 != 0),
          (__int64)&v52);
      }
    }
    *((_DWORD *)this + 90) &= ~4u;
  }
  if ( *((_QWORD *)this + 44) )
  {
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v52) = 0;
      v39 = *((_QWORD *)this + 7);
      if ( v39 && *(_QWORD *)(v39 + 16) )
        v10 = *(_DWORD *)(v39 + 16);
      ConvertPortNoToString(&v52, v10);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v40 = *((_QWORD *)this + 7);
        LODWORD(v41) = v40 + 2120;
        if ( !v40 )
          v41 = &v50;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L" RasDeAllocateDhcpRoute...",
          (_DWORD)v41,
          (v40 + 2686) & -(__int64)(v40 != 0),
          (__int64)&v52);
      }
    }
    RasTcpSetDhcpRoutes(*((_QWORD *)this + 44), *(unsigned int *)this, 0);
    LocalFree(*((HLOCAL *)this + 44));
    *((_QWORD *)this + 44) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids, v44);
  }
  v42 = v44;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)v46);
  return v42;
}

```

## disassembly

```asm
0x18004a4b0  mov     rax, rsp
0x18004a4b3  mov     [rax+20h], rbx
0x18004a4b7  push    rbp
0x18004a4b8  push    rsi
0x18004a4b9  push    rdi
0x18004a4ba  push    r12
0x18004a4bc  push    r13
0x18004a4be  push    r14
0x18004a4c0  push    r15
0x18004a4c2  lea     rbp, [rax-838h]
0x18004a4c9  sub     rsp, 900h
0x18004a4d0  movaps  xmmword ptr [rax-48h], xmm6
0x18004a4d4  mov     rax, cs:__security_cookie
0x18004a4db  xor     rax, rsp
0x18004a4de  mov     [rbp+830h+var_50], rax
0x18004a4e5  mov     r14, r8
0x18004a4e8  mov     rsi, rdx
0x18004a4eb  mov     rbx, rcx
0x18004a4ee  lea     rax, WPP_GLOBAL_Control
0x18004a4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4fc  cmp     rcx, rax
0x18004a4ff  jz      short loc_18004A522
0x18004a501  test    byte ptr [rcx+1Ch], 1
0x18004a505  jz      short loc_18004A522
0x18004a507  cmp     byte ptr [rcx+19h], 6
0x18004a50b  jb      short loc_18004A522
0x18004a50d  mov     edx, 1Fh
0x18004a512  lea     r8, WPP_9b65cff8e2b438daa92b03f64bab9903_Traceguids
0x18004a519  mov     rcx, [rcx+10h]
0x18004a51d  call    WPP_SF_
0x18004a522  xor     r13d, r13d
0x18004a525  mov     [rsp+930h+var_900], r13d
0x18004a52a  mov     rdi, [rbx+38h]
0x18004a52e  mov     r12d, [rdi+5C0h]
0x18004a535  xorps   xmm0, xmm0
0x18004a538  movups  [rbp+830h+var_890], xmm0
0x18004a53c  movups  xmm6, xmmword ptr [rdi+848h]
0x18004a543  movaps  [rbp+830h+var_890], xmm6
0x18004a547  mov     [rbp+830h+var_850], r13d
0x18004a54b  xor     edx, edx; Val
0x18004a54d  mov     r8d, 7FCh; Size
0x18004a553  lea     rcx, [rbp+830h+var_84C]; void *
0x18004a557  call    memset_0
0x18004a55c  mov     [rbp+830h+var_880], r13d
0x18004a560  xorps   xmm0, xmm0
0x18004a563  xor     eax, eax
0x18004a565  movups  [rbp+830h+var_87C], xmm0
0x18004a569  movups  [rbp+830h+var_86C], xmm0
0x18004a56d  mov     [rbp+830h+var_85C], eax
0x18004a570  movups  [rbp+830h+var_8A8], xmm0
0x18004a574  xorps   xmm1, xmm1
0x18004a577  movdqu  [rsp+930h+var_8E0+8], xmm1
0x18004a57d  mov     qword ptr [rsp+930h+var_8E0], r13
0x18004a582  movdqu  xmmword ptr [rsp+930h+var_8D0+8], xmm0
0x18004a588  mov     [rsp+930h+var_8B8], r13
0x18004a58d  or      r15d, 0FFFFFFFFh
0x18004a591  mov     [rbp+830h+var_8B0], r15d
0x18004a595  mov     [rbp+830h+var_8AC], r13d
0x18004a599  test    cs:byte_1800AA941, 8
0x18004a5a0  jz      short loc_18004A5C8
0x18004a5a2  mov     [rsp+930h+var_910], rdi; void *
0x18004a5a7  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18004a5ae  lea     r8, [rsp+930h+var_900]; unsigned int *
0x18004a5b3  lea     rdx, aIpv4helperClea; "IPv4Helper::Cleanup"
0x18004a5ba  lea     rcx, [rsp+930h+var_8E0]; this
0x18004a5bf  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004a5c4  movaps  xmm6, [rbp+830h+var_890]
0x18004a5c8  cmp     r12d, 2
0x18004a5cc  jz      loc_18004A79D
0x18004a5d2  lea     rdi, [rbx+4Ch]
0x18004a5d6  cmp     [rdi], r13d
0x18004a5d9  jnz     loc_18004A79D
0x18004a5df  mov     eax, [rbx+168h]
0x18004a5e5  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a5ec  test    al, 1
0x18004a5ee  jz      loc_18004A6C3
0x18004a5f4  mov     r9b, 1
0x18004a5f7  mov     r8, [rbx+30h]
0x18004a5fb  mov     dl, r9b
0x18004a5fe  xor     ecx, ecx
0x18004a600  mov     rax, qword ptr cs:xmmword_1800AA9C0
0x18004a607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a60c  mov     [rsp+930h+var_900], eax
0x18004a610  test    eax, eax
0x18004a612  jz      loc_18004A6B6
0x18004a618  test    cs:byte_1800AA941, 4
0x18004a61f  jz      loc_18004A6B6
0x18004a625  xor     eax, eax
0x18004a627  mov     word ptr [rbp+830h+var_850], ax
0x18004a62b  mov     word ptr [rbp+830h+var_880], ax
0x18004a62f  mov     rax, [rbx+38h]
0x18004a633  test    rax, rax
0x18004a636  jz      short loc_18004A644
0x18004a638  cmp     qword ptr [rax+10h], 0
0x18004a63d  jz      short loc_18004A644
0x18004a63f  mov     edx, [rax+10h]
0x18004a642  jmp     short loc_18004A647
0x18004a644  mov     edx, r15d
0x18004a647  lea     rcx, [rbp+830h+var_880]
0x18004a64b  call    ConvertPortNoToString
0x18004a650  mov     r8d, [rsp+930h+var_900]
0x18004a655  lea     rdx, aRasupdatedefau_1; "RasUpdateDefaultRouteSettings failed: %"...
0x18004a65c  lea     rcx, [rbp+830h+var_850]
0x18004a660  call    FormatRRASErrorString
0x18004a665  test    cs:byte_1800AA941, 4
0x18004a66c  jz      short loc_18004A6B6
0x18004a66e  mov     rdx, [rbx+38h]
0x18004a672  mov     rax, rdx
0x18004a675  lea     rcx, [rdx+0A7Eh]
0x18004a67c  neg     rax
0x18004a67f  sbb     r8, r8
0x18004a682  and     r8, rcx
0x18004a685  test    rdx, rdx
0x18004a688  lea     r9, [rdx+848h]
0x18004a68f  jnz     short loc_18004A695
0x18004a691  lea     r9, [rbp+830h+var_8A8]
0x18004a695  lea     rax, [rbp+830h+var_880]
0x18004a699  mov     qword ptr [rsp+930h+var_908], rax
0x18004a69e  mov     [rsp+930h+var_910], r8
0x18004a6a3  lea     r8, [rbp+830h+var_850]
0x18004a6a7  lea     rdx, RasVpnIkeParamTraceError
0x18004a6ae  mov     rcx, r13
0x18004a6b1  call    McTemplateU0zjzz_EventWriteTransfer
0x18004a6b6  and     dword ptr [rbx+168h], 0FFFFFFFEh
0x18004a6bd  mov     eax, [rbx+168h]
0x18004a6c3  test    al, 2
0x18004a6c5  jz      loc_18004AA40
0x18004a6cb  mov     rdx, [rbx+30h]
0x18004a6cf  shr     rdx, 18h
0x18004a6d3  and     edx, 0FFFFFFh
0x18004a6d9  mov     rcx, [rbx+38h]
0x18004a6dd  mov     rcx, [rcx+10h]
0x18004a6e1  call    cs:__imp_RasFreeInterfaceLuidIndex
0x18004a6e7  mov     [rsp+930h+var_900], eax
0x18004a6eb  test    eax, eax
0x18004a6ed  jz      loc_18004A791
0x18004a6f3  test    cs:byte_1800AA941, 4
0x18004a6fa  jz      loc_18004A791
0x18004a700  xor     eax, eax
0x18004a702  mov     word ptr [rbp+830h+var_850], ax
0x18004a706  mov     word ptr [rbp+830h+var_880], ax
0x18004a70a  mov     rax, [rbx+38h]
0x18004a70e  test    rax, rax
0x18004a711  jz      short loc_18004A71F
0x18004a713  cmp     qword ptr [rax+10h], 0
0x18004a718  jz      short loc_18004A71F
0x18004a71a  mov     edx, [rax+10h]
0x18004a71d  jmp     short loc_18004A722
0x18004a71f  mov     edx, r15d
0x18004a722  lea     rcx, [rbp+830h+var_880]
0x18004a726  call    ConvertPortNoToString
0x18004a72b  mov     r8d, [rsp+930h+var_900]
0x18004a730  lea     rdx, aRasfreeinterfa; "RasFreeInterfaceLuidIndex failed: %d"
0x18004a737  lea     rcx, [rbp+830h+var_850]
0x18004a73b  call    FormatRRASErrorString
0x18004a740  test    cs:byte_1800AA941, 4
0x18004a747  jz      short loc_18004A791
0x18004a749  mov     rdx, [rbx+38h]
0x18004a74d  mov     rax, rdx
0x18004a750  lea     rcx, [rdx+0A7Eh]
0x18004a757  neg     rax
0x18004a75a  sbb     r8, r8
0x18004a75d  and     r8, rcx
0x18004a760  test    rdx, rdx
0x18004a763  lea     r9, [rdx+848h]
0x18004a76a  jnz     short loc_18004A770
0x18004a76c  lea     r9, [rbp+830h+var_8A8]
0x18004a770  lea     rax, [rbp+830h+var_880]
0x18004a774  mov     qword ptr [rsp+930h+var_908], rax
0x18004a779  mov     [rsp+930h+var_910], r8
0x18004a77e  lea     r8, [rbp+830h+var_850]
0x18004a782  lea     rdx, RasVpnIkeParamTraceError
0x18004a789  mov     rcx, r13
0x18004a78c  call    McTemplateU0zjzz_EventWriteTransfer
0x18004a791  and     dword ptr [rbx+168h], 0FFFFFFFDh
0x18004a798  jmp     loc_18004AA5B
0x18004a79d  mov     edx, [rbx+14h]
0x18004a7a0  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a7a7  test    edx, edx
0x18004a7a9  jz      loc_18004A865
0x18004a7af  movdqa  xmmword ptr [rsp+930h+var_8F8+8], xmm6
0x18004a7b5  mov     rax, [rbx+158h]
0x18004a7bc  mov     dword ptr [rsp+930h+var_910], 1
0x18004a7c4  mov     r9, r14
0x18004a7c7  mov     r8, rsi
0x18004a7ca  lea     rcx, [rsp+930h+var_8F8+8]
0x18004a7cf  mov     rax, [rax+18h]
0x18004a7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7d8  test    cs:byte_1800AA941, 8
0x18004a7df  jz      short loc_18004A85C
0x18004a7e1  xor     eax, eax
0x18004a7e3  mov     word ptr [rbp+830h+var_880], ax
0x18004a7e7  mov     rax, [rbx+38h]
0x18004a7eb  test    rax, rax
0x18004a7ee  jz      short loc_18004A7FC
0x18004a7f0  cmp     qword ptr [rax+10h], 0
0x18004a7f5  jz      short loc_18004A7FC
0x18004a7f7  mov     edx, [rax+10h]
0x18004a7fa  jmp     short loc_18004A7FF
0x18004a7fc  mov     edx, r15d
0x18004a7ff  lea     rcx, [rbp+830h+var_880]
0x18004a803  call    ConvertPortNoToString
0x18004a808  test    cs:byte_1800AA941, 8
0x18004a80f  jz      short loc_18004A85C
0x18004a811  mov     rdx, [rbx+38h]
0x18004a815  mov     rax, rdx
0x18004a818  lea     rcx, [rdx+0A7Eh]
0x18004a81f  neg     rax
0x18004a822  sbb     r8, r8
0x18004a825  and     r8, rcx
0x18004a828  test    rdx, rdx
0x18004a82b  lea     r9, [rdx+848h]
0x18004a832  jnz     short loc_18004A838
0x18004a834  lea     r9, [rbp+830h+var_8A8]
0x18004a838  lea     rax, [rbp+830h+var_880]
0x18004a83c  mov     qword ptr [rsp+930h+var_908], rax
0x18004a841  mov     [rsp+930h+var_910], r8
0x18004a846  lea     r8, aReleaseipv4add; "ReleaseIpv4AddressOfClient done"
0x18004a84d  lea     rdx, RasVpnIkeParamTraceInfo
0x18004a854  mov     rcx, r13
0x18004a857  call    McTemplateU0zjzz_EventWriteTransfer
0x18004a85c  xor     eax, eax
0x18004a85e  mov     [rbx+14h], eax
0x18004a861  movaps  xmm6, [rbp+830h+var_890]
0x18004a865  cmp     r12d, 2
0x18004a869  jnz     loc_18004AA48
0x18004a86f  mov     edx, [rbx]
0x18004a871  test    edx, edx
0x18004a873  jz      loc_18004A931
0x18004a879  movdqa  xmmword ptr [rsp+930h+var_8F8+8], xmm6
0x18004a87f  mov     rax, [rbx+158h]
0x18004a886  mov     dword ptr [rsp+930h+var_910], 1
0x18004a88e  mov     r9, r14
0x18004a891  mov     r8, rsi
0x18004a894  lea     rcx, [rsp+930h+var_8F8+8]
0x18004a899  mov     rax, [rax+18h]
0x18004a89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8a2  mov     sil, 8
0x18004a8a5  test    cs:byte_1800AA941, sil
0x18004a8ac  jz      short loc_18004A929
0x18004a8ae  xor     eax, eax
0x18004a8b0  mov     word ptr [rbp+830h+var_880], ax
0x18004a8b4  mov     rax, [rbx+38h]
0x18004a8b8  test    rax, rax
0x18004a8bb  jz      short loc_18004A8C9
0x18004a8bd  cmp     qword ptr [rax+10h], 0
0x18004a8c2  jz      short loc_18004A8C9
0x18004a8c4  mov     edx, [rax+10h]
0x18004a8c7  jmp     short loc_18004A8CC
0x18004a8c9  mov     edx, r15d
0x18004a8cc  lea     rcx, [rbp+830h+var_880]
0x18004a8d0  call    ConvertPortNoToString
0x18004a8d5  test    cs:byte_1800AA941, sil
0x18004a8dc  jz      short loc_18004A929
0x18004a8de  mov     rdx, [rbx+38h]
0x18004a8e2  mov     rax, rdx
0x18004a8e5  lea     rcx, [rdx+0A7Eh]
0x18004a8ec  neg     rax
0x18004a8ef  sbb     r8, r8
0x18004a8f2  and     r8, rcx
0x18004a8f5  test    rdx, rdx
0x18004a8f8  lea     r9, [rdx+848h]
0x18004a8ff  jnz     short loc_18004A905
0x18004a901  lea     r9, [rbp+830h+var_8A8]
0x18004a905  lea     rax, [rbp+830h+var_880]
0x18004a909  mov     qword ptr [rsp+930h+var_908], rax
0x18004a90e  mov     [rsp+930h+var_910], r8
0x18004a913  lea     r8, aReleaseipv4add; "ReleaseIpv4AddressOfClient done"
0x18004a91a  lea     rdx, RasVpnIkeParamTraceInfo
0x18004a921  mov     rcx, r13
0x18004a924  call    McTemplateU0zjzz_EventWriteTransfer
0x18004a929  xor     eax, eax
0x18004a92b  mov     [rbx], eax
0x18004a92d  xor     edx, edx
0x18004a92f  jmp     short loc_18004A934
0x18004a931  mov     sil, 8
0x18004a934  lea     rdi, [rbx+4Ch]
0x18004a938  cmp     dword ptr [rdi], 0
0x18004a93b  jz      short loc_18004A96B
0x18004a93d  test    edx, edx
0x18004a93f  jz      short loc_18004A96B
0x18004a941  mov     ecx, [rbx+14h]
0x18004a944  test    ecx, ecx
0x18004a946  jz      short loc_18004A96B
0x18004a948  mov     rax, [rbx+158h]
0x18004a94f  lea     r8, [rbx+30h]
0x18004a953  lea     r9, [rbp+830h+var_890]
0x18004a957  mov     [rsp+930h+var_910], r9
0x18004a95c  mov     r9b, 1
0x18004a95f  mov     rax, [rax+0A8h]
0x18004a966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a96b  test    [rbx+168h], sil
0x18004a972  jz      loc_18004AA40
0x18004a978  mov     rcx, [rbx+30h]
0x18004a97c  shr     rcx, 18h
0x18004a980  and     ecx, 0FFFFFFh
0x18004a986  mov     edx, [rbx]
0x18004a988  call    ResetIpAddressOnInterface
0x18004a98d  mov     [rsp+930h+var_900], eax
0x18004a991  test    eax, eax
  ... truncated ...
```
