# IPv6Helper::Cleanup(ushort *,ushort *)

- ea: `0x18004f40c`
- end: `0x18004fc17`
- name: `?Cleanup@IPv6Helper@@QEAAKPEAG0@Z`
- size: `2059`
- prototype: `__int64 __fastcall(IPv6Helper *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e030`

## callees

- `0x180007610`
- `0x1800077bc`
- `0x180039fa8`
- `0x18004f40c`
- `0x180050068`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rasman!RasFreeInterfaceLuidIndex` at `0x18004f60f`
- `rasman!RasFreeInterfaceLuidIndex` at `0x18004f60f`

## string_xrefs

- `0x18004f581`: `RasUpdateDefaultRouteSettings failed: %d`

## pseudocode

```c
__int64 __fastcall IPv6Helper::Cleanup(IPv6Helper *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rdi
  int v7; // esi
  __int128 v8; // xmm6
  __int64 v9; // r9
  unsigned int v10; // r15d
  _DWORD *v11; // rsi
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int128 *v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int128 *v20; // r9
  __int128 *v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int128 *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int128 *v29; // r9
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int128 *v33; // r9
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int128 *v37; // r9
  __int64 v38; // rax
  __int64 v39; // rdx
  __int128 *v40; // r9
  unsigned int v41; // ebx
  unsigned int v43; // [rsp+38h] [rbp-D0h] BYREF
  int v44; // [rsp+3Ch] [rbp-CCh]
  __int128 v45; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v46; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v47[40]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+90h] [rbp-78h]
  int v49; // [rsp+98h] [rbp-70h]
  int v50; // [rsp+9Ch] [rbp-6Ch]
  __int64 v51; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v52; // [rsp+A8h] [rbp-60h] BYREF
  int v53; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v54; // [rsp+BCh] [rbp-4Ch]
  __int128 v55; // [rsp+CCh] [rbp-3Ch]
  int v56; // [rsp+DCh] [rbp-2Ch]
  int v57; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v58[2044]; // [rsp+ECh] [rbp-1Ch] BYREF

  v43 = 0;
  v6 = *((_QWORD *)this + 16);
  v7 = *(_DWORD *)(v6 + 1472);
  v44 = v7;
  v8 = *(_OWORD *)(v6 + 2120);
  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v52 = 0;
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  v10 = -1;
  v49 = -1;
  v50 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)v47,
      L"IPv6Helper::Cleanup",
      &v43,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      (void *)v6);
  if ( v7 != 2 )
  {
    v11 = (_DWORD *)((char *)this + 404);
    if ( !*((_DWORD *)this + 101) )
    {
      v12 = *((_DWORD *)this + 106);
      if ( (v12 & 1) != 0 )
      {
        LOBYTE(v9) = 1;
        v43 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))xmmword_1800AA9C0)(
                0,
                0,
                *((_QWORD *)this + 15),
                v9);
        if ( v43 && (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v57) = 0;
          LOWORD(v53) = 0;
          v13 = *((_QWORD *)this + 16);
          if ( v13 && *(_QWORD *)(v13 + 16) )
            v14 = *(unsigned int *)(v13 + 16);
          else
            v14 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v53, v14);
          FormatRRASErrorString(&v57, L"RasUpdateDefaultRouteSettings failed: %d", v43);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v15 = *((_QWORD *)this + 16);
            LODWORD(v16) = v15 + 2120;
            if ( !v15 )
              v16 = &v52;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v57,
              (_DWORD)v16,
              (v15 + 2686) & -(__int64)(v15 != 0),
              (__int64)&v53);
          }
        }
        *((_DWORD *)this + 106) &= ~1u;
        v12 = *((_DWORD *)this + 106);
      }
      if ( (v12 & 2) != 0 )
      {
        v43 = RasFreeInterfaceLuidIndex(
                *(_QWORD *)(*((_QWORD *)this + 16) + 16LL),
                (*((_QWORD *)this + 15) >> 24) & 0xFFFFFFLL);
        if ( v43 && (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v57) = 0;
          LOWORD(v53) = 0;
          v17 = *((_QWORD *)this + 16);
          if ( v17 && *(_QWORD *)(v17 + 16) )
            v18 = *(unsigned int *)(v17 + 16);
          else
            v18 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v53, v18);
          FormatRRASErrorString(&v57, L"RasFreeInterfaceLuidIndex failed: %d", v43);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v19 = *((_QWORD *)this + 16);
            LODWORD(v20) = v19 + 2120;
            if ( !v19 )
              v20 = &v52;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v57,
              (_DWORD)v20,
              (v19 + 2686) & -(__int64)(v19 != 0),
              (__int64)&v53);
          }
        }
        *((_DWORD *)this + 106) &= ~2u;
      }
LABEL_77:
      if ( *v11 )
        goto LABEL_79;
      goto LABEL_78;
    }
  }
  v21 = (__int128 *)((char *)this + 52);
  if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)((char *)this + 52)) )
  {
    v46 = *v21;
    v45 = v8;
    (*(void (__fastcall **)(__int128 *, __int128 *, unsigned __int16 *, unsigned __int16 *, int))(*((_QWORD *)this + 52)
                                                                                                + 32LL))(
      &v45,
      &v46,
      a2,
      a3,
      1);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v53) = 0;
      v22 = *((_QWORD *)this + 16);
      if ( v22 && *(_QWORD *)(v22 + 16) )
        v23 = *(unsigned int *)(v22 + 16);
      else
        v23 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v53, v23);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v24 = *((_QWORD *)this + 16);
        LODWORD(v25) = v24 + 2120;
        if ( !v24 )
          v25 = &v52;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"lpfnReleaseIpv6AddressOfClient done",
          (_DWORD)v25,
          (v24 + 2686) & -(__int64)(v24 != 0),
          (__int64)&v53);
      }
    }
  }
  if ( v44 == 2 )
  {
    if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)this) )
    {
      v45 = *(_OWORD *)this;
      v46 = v8;
      (*(void (__fastcall **)(__int128 *, __int128 *, unsigned __int16 *, unsigned __int16 *, int))(*((_QWORD *)this + 52)
                                                                                                  + 32LL))(
        &v46,
        &v45,
        a2,
        a3,
        1);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v53) = 0;
        v26 = *((_QWORD *)this + 16);
        if ( v26 && *(_QWORD *)(v26 + 16) )
          v27 = *(unsigned int *)(v26 + 16);
        else
          v27 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v53, v27);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v28 = *((_QWORD *)this + 16);
          LODWORD(v29) = v28 + 2120;
          if ( !v28 )
            v29 = &v52;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)L"lpfnReleaseIpv6AddressOfClient done",
            (_DWORD)v29,
            (v28 + 2686) & -(__int64)(v28 != 0),
            (__int64)&v53);
        }
      }
    }
    if ( *((_DWORD *)this + 101) )
    {
      v45 = *(_OWORD *)this;
      v46 = *v21;
      (*(void (__fastcall **)(__int128 *, __int128 *, char *, _QWORD))(*((_QWORD *)this + 52) + 160LL))(
        &v46,
        &v45,
        (char *)this + 120,
        0);
    }
  }
  v51 = *(_QWORD *)((char *)this + 60);
  if ( v51 )
  {
    v45 = v8;
    v43 = (*(__int64 (__fastcall **)(__int128 *, __int64 *))(*((_QWORD *)this + 52) + 40LL))(&v45, &v51);
    if ( v43 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        v30 = *((_QWORD *)this + 16);
        if ( v30 && *(_QWORD *)(v30 + 16) )
          v31 = *(unsigned int *)(v30 + 16);
        else
          v31 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v53, v31);
        FormatRRASErrorString(&v57, L"lpfnInterfaceIdInsert failed: %d", v43);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v32 = *((_QWORD *)this + 16);
          LODWORD(v33) = v32 + 2120;
          if ( !v32 )
            v33 = &v52;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v57,
            (_DWORD)v33,
            (v32 + 2686) & -(__int64)(v32 != 0),
            (__int64)&v53);
        }
      }
    }
  }
  *v21 = 0;
  v51 = *((_QWORD *)this + 1);
  if ( v51 )
  {
    v45 = v8;
    v43 = (*(__int64 (__fastcall **)(__int128 *, __int64 *))(*((_QWORD *)this + 52) + 40LL))(&v45, &v51);
    if ( v43 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        v34 = *((_QWORD *)this + 16);
        if ( v34 && *(_QWORD *)(v34 + 16) )
          v35 = *(unsigned int *)(v34 + 16);
        else
          v35 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v53, v35);
        FormatRRASErrorString(&v57, L"lpfnInterfaceIdInsert failed: %d", v43);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v36 = *((_QWORD *)this + 16);
          LODWORD(v37) = v36 + 2120;
          if ( !v36 )
            v37 = &v52;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v57,
            (_DWORD)v37,
            (v36 + 2686) & -(__int64)(v36 != 0),
            (__int64)&v53);
        }
      }
    }
  }
  *(_OWORD *)this = 0;
  if ( v44 != 2 )
  {
    v11 = (_DWORD *)((char *)this + 404);
    if ( *((_DWORD *)this + 101) )
    {
      *((_DWORD *)this + 102) = 0;
      goto LABEL_77;
    }
  }
LABEL_78:
  IPv6Helper::ResetIPv6Settings(this);
LABEL_79:
  if ( (*((_BYTE *)this + 424) & 4) != 0 )
  {
    v43 = ((__int64 (__fastcall *)(_QWORD, __int64))xmmword_1800AA9B0)(
            *(_QWORD *)(*((_QWORD *)this + 16) + 32LL),
            34525);
    if ( v43 && (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v57) = 0;
      LOWORD(v53) = 0;
      v38 = *((_QWORD *)this + 16);
      if ( v38 && *(_QWORD *)(v38 + 16) )
        v10 = *(_DWORD *)(v38 + 16);
      ConvertPortNoToString(&v53, v10);
      FormatRRASErrorString(&v57, L"RasDeAllocateRoute failed: %d", v43);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v39 = *((_QWORD *)this + 16);
        LODWORD(v40) = v39 + 2120;
        if ( !v39 )
          v40 = &v52;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v57,
          (_DWORD)v40,
          (v39 + 2686) & -(__int64)(v39 != 0),
          (__int64)&v53);
      }
    }
    *((_DWORD *)this + 106) &= ~4u;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_66f280efc6d63f258d12e6ab97837239_Traceguids, v43);
  }
  v41 = v43;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)v47);
  return v41;
}

```

## disassembly

```asm
0x18004f40c  mov     rax, rsp
0x18004f40f  mov     [rax+20h], rbx
0x18004f413  push    rbp
0x18004f414  push    rsi
0x18004f415  push    rdi
0x18004f416  push    r12
0x18004f418  push    r13
0x18004f41a  push    r14
0x18004f41c  push    r15
0x18004f41e  lea     rbp, [rax-838h]
0x18004f425  sub     rsp, 900h
0x18004f42c  movaps  xmmword ptr [rax-48h], xmm6
0x18004f430  mov     rax, cs:__security_cookie
0x18004f437  xor     rax, rsp
0x18004f43a  mov     [rbp+830h+var_50], rax
0x18004f441  mov     r13, r8
0x18004f444  mov     r14, rdx
0x18004f447  mov     rbx, rcx
0x18004f44a  xor     r12d, r12d
0x18004f44d  mov     [rsp+930h+var_900], r12d
0x18004f452  mov     rdi, [rcx+80h]
0x18004f459  mov     esi, [rdi+5C0h]
0x18004f45f  mov     [rsp+930h+var_8FC], esi
0x18004f463  movups  xmm6, xmmword ptr [rdi+848h]
0x18004f46a  mov     [rbp+830h+var_850], r12d
0x18004f46e  xor     edx, edx; Val
0x18004f470  mov     r8d, 7FCh; Size
0x18004f476  lea     rcx, [rbp+830h+var_84C]; void *
0x18004f47a  call    memset_0
0x18004f47f  mov     [rbp+830h+var_880], r12d
0x18004f483  xorps   xmm0, xmm0
0x18004f486  xor     eax, eax
0x18004f488  movups  [rbp+830h+var_87C], xmm0
0x18004f48c  movups  [rbp+830h+var_86C], xmm0
0x18004f490  mov     [rbp+830h+var_85C], eax
0x18004f493  movups  [rbp+830h+var_890], xmm0
0x18004f497  xorps   xmm1, xmm1
0x18004f49a  movdqu  [rsp+930h+var_8D0+8], xmm1
0x18004f4a0  mov     qword ptr [rsp+930h+var_8D0], r12
0x18004f4a5  movdqu  xmmword ptr [rsp+930h+var_8C0+8], xmm0
0x18004f4ab  mov     [rbp+830h+var_8A8], r12
0x18004f4af  or      r15d, 0FFFFFFFFh
0x18004f4b3  mov     [rbp+830h+var_8A0], r15d
0x18004f4b7  mov     [rbp+830h+var_89C], r12d
0x18004f4bb  test    cs:byte_1800AA941, 8
0x18004f4c2  jz      short loc_18004F4E6
0x18004f4c4  mov     [rsp+930h+var_910], rdi; void *
0x18004f4c9  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18004f4d0  lea     r8, [rsp+930h+var_900]; unsigned int *
0x18004f4d5  lea     rdx, aIpv6helperClea; "IPv6Helper::Cleanup"
0x18004f4dc  lea     rcx, [rsp+930h+var_8D0]; this
0x18004f4e1  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18004f4e6  cmp     esi, 2
0x18004f4e9  jz      loc_18004F6CD
0x18004f4ef  lea     rsi, [rbx+194h]
0x18004f4f6  cmp     [rsi], r12d
0x18004f4f9  jnz     loc_18004F6CD
0x18004f4ff  mov     eax, [rbx+1A8h]
0x18004f505  mov     dil, 4
0x18004f508  lea     r14, RasVpnIkeParamTraceError
0x18004f50f  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f516  test    al, 1
0x18004f518  jz      loc_18004F5EE
0x18004f51e  mov     r9b, 1
0x18004f521  mov     r8, [rbx+78h]
0x18004f525  xor     edx, edx
0x18004f527  xor     ecx, ecx
0x18004f529  mov     rax, qword ptr cs:xmmword_1800AA9C0
0x18004f530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f535  mov     [rsp+930h+var_900], eax
0x18004f539  test    eax, eax
0x18004f53b  jz      loc_18004F5E1
0x18004f541  test    cs:byte_1800AA941, dil
0x18004f548  jz      loc_18004F5E1
0x18004f54e  xor     eax, eax
0x18004f550  mov     word ptr [rbp+830h+var_850], ax
0x18004f554  mov     word ptr [rbp+830h+var_880], ax
0x18004f558  mov     rax, [rbx+80h]
0x18004f55f  test    rax, rax
0x18004f562  jz      short loc_18004F570
0x18004f564  cmp     qword ptr [rax+10h], 0
0x18004f569  jz      short loc_18004F570
0x18004f56b  mov     edx, [rax+10h]
0x18004f56e  jmp     short loc_18004F573
0x18004f570  mov     edx, r15d
0x18004f573  lea     rcx, [rbp+830h+var_880]
0x18004f577  call    ConvertPortNoToString
0x18004f57c  mov     r8d, [rsp+930h+var_900]
0x18004f581  lea     rdx, aRasupdatedefau_1; "RasUpdateDefaultRouteSettings failed: %"...
0x18004f588  lea     rcx, [rbp+830h+var_850]
0x18004f58c  call    FormatRRASErrorString
0x18004f591  test    cs:byte_1800AA941, dil
0x18004f598  jz      short loc_18004F5E1
0x18004f59a  mov     rdx, [rbx+80h]
0x18004f5a1  mov     rax, rdx
0x18004f5a4  lea     rcx, [rdx+0A7Eh]
0x18004f5ab  neg     rax
0x18004f5ae  sbb     r8, r8
0x18004f5b1  and     r8, rcx
0x18004f5b4  test    rdx, rdx
0x18004f5b7  lea     r9, [rdx+848h]
0x18004f5be  jnz     short loc_18004F5C4
0x18004f5c0  lea     r9, [rbp+830h+var_890]
0x18004f5c4  lea     rax, [rbp+830h+var_880]
0x18004f5c8  mov     qword ptr [rsp+930h+var_908], rax
0x18004f5cd  mov     [rsp+930h+var_910], r8
0x18004f5d2  lea     r8, [rbp+830h+var_850]
0x18004f5d6  mov     rdx, r14
0x18004f5d9  mov     rcx, r12
0x18004f5dc  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f5e1  and     dword ptr [rbx+1A8h], 0FFFFFFFEh
0x18004f5e8  mov     eax, [rbx+1A8h]
0x18004f5ee  test    al, 2
0x18004f5f0  jz      loc_18004FAB7
0x18004f5f6  mov     rdx, [rbx+78h]
0x18004f5fa  shr     rdx, 18h
0x18004f5fe  and     edx, 0FFFFFFh
0x18004f604  mov     rcx, [rbx+80h]
0x18004f60b  mov     rcx, [rcx+10h]
0x18004f60f  call    cs:__imp_RasFreeInterfaceLuidIndex
0x18004f615  mov     [rsp+930h+var_900], eax
0x18004f619  test    eax, eax
0x18004f61b  jz      loc_18004F6C1
0x18004f621  test    cs:byte_1800AA941, dil
0x18004f628  jz      loc_18004F6C1
0x18004f62e  xor     eax, eax
0x18004f630  mov     word ptr [rbp+830h+var_850], ax
0x18004f634  mov     word ptr [rbp+830h+var_880], ax
0x18004f638  mov     rax, [rbx+80h]
0x18004f63f  test    rax, rax
0x18004f642  jz      short loc_18004F650
0x18004f644  cmp     qword ptr [rax+10h], 0
0x18004f649  jz      short loc_18004F650
0x18004f64b  mov     edx, [rax+10h]
0x18004f64e  jmp     short loc_18004F653
0x18004f650  mov     edx, r15d
0x18004f653  lea     rcx, [rbp+830h+var_880]
0x18004f657  call    ConvertPortNoToString
0x18004f65c  mov     r8d, [rsp+930h+var_900]
0x18004f661  lea     rdx, aRasfreeinterfa; "RasFreeInterfaceLuidIndex failed: %d"
0x18004f668  lea     rcx, [rbp+830h+var_850]
0x18004f66c  call    FormatRRASErrorString
0x18004f671  test    cs:byte_1800AA941, dil
0x18004f678  jz      short loc_18004F6C1
0x18004f67a  mov     rdx, [rbx+80h]
0x18004f681  mov     rax, rdx
0x18004f684  lea     rcx, [rdx+0A7Eh]
0x18004f68b  neg     rax
0x18004f68e  sbb     r8, r8
0x18004f691  and     r8, rcx
0x18004f694  test    rdx, rdx
0x18004f697  lea     r9, [rdx+848h]
0x18004f69e  jnz     short loc_18004F6A4
0x18004f6a0  lea     r9, [rbp+830h+var_890]
0x18004f6a4  lea     rax, [rbp+830h+var_880]
0x18004f6a8  mov     qword ptr [rsp+930h+var_908], rax
0x18004f6ad  mov     [rsp+930h+var_910], r8
0x18004f6b2  lea     r8, [rbp+830h+var_850]
0x18004f6b6  mov     rdx, r14
0x18004f6b9  mov     rcx, r12
0x18004f6bc  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f6c1  and     dword ptr [rbx+1A8h], 0FFFFFFFDh
0x18004f6c8  jmp     loc_18004FAB7
0x18004f6cd  lea     rsi, [rbx+34h]
0x18004f6d1  mov     rcx, rsi; a
0x18004f6d4  call    IN6_IS_ADDR_UNSPECIFIED
0x18004f6d9  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f6e0  test    al, al
0x18004f6e2  jnz     loc_18004F7AD
0x18004f6e8  movups  xmm0, xmmword ptr [rsi]
0x18004f6eb  movdqu  xmmword ptr [rsp+930h+var_8E8+8], xmm0
0x18004f6f1  movdqa  [rsp+930h+var_8F8+8], xmm6
0x18004f6f7  mov     rax, [rbx+1A0h]
0x18004f6fe  mov     dword ptr [rsp+930h+var_910], 1
0x18004f706  mov     r9, r13
0x18004f709  mov     r8, r14
0x18004f70c  lea     rdx, [rsp+930h+var_8E8+8]
0x18004f711  lea     rcx, [rsp+930h+var_8F8+8]
0x18004f716  mov     rax, [rax+20h]
0x18004f71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f71f  test    cs:byte_1800AA941, 8
0x18004f726  jz      loc_18004F7AD
0x18004f72c  xor     eax, eax
0x18004f72e  mov     word ptr [rbp+830h+var_880], ax
0x18004f732  mov     rax, [rbx+80h]
0x18004f739  test    rax, rax
0x18004f73c  jz      short loc_18004F74A
0x18004f73e  cmp     qword ptr [rax+10h], 0
0x18004f743  jz      short loc_18004F74A
0x18004f745  mov     edx, [rax+10h]
0x18004f748  jmp     short loc_18004F74D
0x18004f74a  mov     edx, r15d
0x18004f74d  lea     rcx, [rbp+830h+var_880]
0x18004f751  call    ConvertPortNoToString
0x18004f756  test    cs:byte_1800AA941, 8
0x18004f75d  jz      short loc_18004F7AD
0x18004f75f  mov     rdx, [rbx+80h]
0x18004f766  mov     rax, rdx
0x18004f769  lea     rcx, [rdx+0A7Eh]
0x18004f770  neg     rax
0x18004f773  sbb     r8, r8
0x18004f776  and     r8, rcx
0x18004f779  test    rdx, rdx
0x18004f77c  lea     r9, [rdx+848h]
0x18004f783  jnz     short loc_18004F789
0x18004f785  lea     r9, [rbp+830h+var_890]
0x18004f789  lea     rax, [rbp+830h+var_880]
0x18004f78d  mov     qword ptr [rsp+930h+var_908], rax
0x18004f792  mov     [rsp+930h+var_910], r8
0x18004f797  lea     r8, aLpfnreleaseipv; "lpfnReleaseIpv6AddressOfClient done"
0x18004f79e  lea     rdx, RasVpnIkeParamTraceInfo
0x18004f7a5  mov     rcx, r12
0x18004f7a8  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f7ad  cmp     [rsp+930h+var_8FC], 2
0x18004f7b2  jnz     loc_18004F8CC
0x18004f7b8  mov     rcx, rbx; a
0x18004f7bb  call    IN6_IS_ADDR_UNSPECIFIED
0x18004f7c0  test    al, al
0x18004f7c2  jnz     loc_18004F88D
0x18004f7c8  movups  xmm0, xmmword ptr [rbx]
0x18004f7cb  movdqu  [rsp+930h+var_8F8+8], xmm0
0x18004f7d1  movdqa  xmmword ptr [rsp+930h+var_8E8+8], xmm6
0x18004f7d7  mov     rax, [rbx+1A0h]
0x18004f7de  mov     dword ptr [rsp+930h+var_910], 1
0x18004f7e6  mov     r9, r13
0x18004f7e9  mov     r8, r14
0x18004f7ec  lea     rdx, [rsp+930h+var_8F8+8]
0x18004f7f1  lea     rcx, [rsp+930h+var_8E8+8]
0x18004f7f6  mov     rax, [rax+20h]
0x18004f7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7ff  test    cs:byte_1800AA941, 8
0x18004f806  jz      loc_18004F88D
0x18004f80c  xor     eax, eax
0x18004f80e  mov     word ptr [rbp+830h+var_880], ax
0x18004f812  mov     rax, [rbx+80h]
0x18004f819  test    rax, rax
0x18004f81c  jz      short loc_18004F82A
0x18004f81e  cmp     qword ptr [rax+10h], 0
0x18004f823  jz      short loc_18004F82A
0x18004f825  mov     edx, [rax+10h]
0x18004f828  jmp     short loc_18004F82D
0x18004f82a  mov     edx, r15d
0x18004f82d  lea     rcx, [rbp+830h+var_880]
0x18004f831  call    ConvertPortNoToString
0x18004f836  test    cs:byte_1800AA941, 8
0x18004f83d  jz      short loc_18004F88D
0x18004f83f  mov     rdx, [rbx+80h]
0x18004f846  mov     rax, rdx
0x18004f849  lea     rcx, [rdx+0A7Eh]
0x18004f850  neg     rax
0x18004f853  sbb     r8, r8
0x18004f856  and     r8, rcx
0x18004f859  test    rdx, rdx
0x18004f85c  lea     r9, [rdx+848h]
0x18004f863  jnz     short loc_18004F869
0x18004f865  lea     r9, [rbp+830h+var_890]
0x18004f869  lea     rax, [rbp+830h+var_880]
0x18004f86d  mov     qword ptr [rsp+930h+var_908], rax
0x18004f872  mov     [rsp+930h+var_910], r8
0x18004f877  lea     r8, aLpfnreleaseipv; "lpfnReleaseIpv6AddressOfClient done"
0x18004f87e  lea     rdx, RasVpnIkeParamTraceInfo
0x18004f885  mov     rcx, r12
0x18004f888  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f88d  cmp     dword ptr [rbx+194h], 0
0x18004f894  jz      short loc_18004F8CC
0x18004f896  movups  xmm0, xmmword ptr [rbx]
0x18004f899  movdqu  [rsp+930h+var_8F8+8], xmm0
0x18004f89f  movups  xmm1, xmmword ptr [rsi]
0x18004f8a2  movdqu  xmmword ptr [rsp+930h+var_8E8+8], xmm1
0x18004f8a8  mov     rax, [rbx+1A0h]
0x18004f8af  lea     r8, [rbx+78h]
0x18004f8b3  xor     r9d, r9d
0x18004f8b6  lea     rdx, [rsp+930h+var_8F8+8]
0x18004f8bb  lea     rcx, [rsp+930h+var_8E8+8]
0x18004f8c0  mov     rax, [rax+0A0h]
0x18004f8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8cc  mov     rax, [rbx+3Ch]
0x18004f8d0  mov     [rbp+830h+var_898], rax
0x18004f8d4  lea     r14, RasVpnIkeParamTraceError
0x18004f8db  mov     dil, 4
0x18004f8de  test    rax, rax
0x18004f8e1  jz      loc_18004F9B2
0x18004f8e7  movdqa  [rsp+930h+var_8F8+8], xmm6
0x18004f8ed  mov     rax, [rbx+1A0h]
0x18004f8f4  lea     rdx, [rbp+830h+var_898]
0x18004f8f8  lea     rcx, [rsp+930h+var_8F8+8]
0x18004f8fd  mov     rax, [rax+28h]
0x18004f901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f906  mov     [rsp+930h+var_900], eax
0x18004f90a  test    eax, eax
0x18004f90c  jz      loc_18004F9B2
0x18004f912  test    cs:byte_1800AA941, dil
0x18004f919  jz      loc_18004F9B2
0x18004f91f  xor     eax, eax
0x18004f921  mov     word ptr [rbp+830h+var_850], ax
0x18004f925  mov     word ptr [rbp+830h+var_880], ax
0x18004f929  mov     rax, [rbx+80h]
0x18004f930  test    rax, rax
0x18004f933  jz      short loc_18004F941
0x18004f935  cmp     qword ptr [rax+10h], 0
  ... truncated ...
```
