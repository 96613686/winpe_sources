# VPNIKEClientConnection::UpdatePeerAdditionalAddresses(_ADDITIONAL_ADDRESSES_ &)

- ea: `0x18001f240`
- end: `0x18001facc`
- name: `?UpdatePeerAdditionalAddresses@VPNIKEClientConnection@@UEAAXAEAU_ADDITIONAL_ADDRESSES_@@@Z`
- size: `2188`
- prototype: `void __fastcall(VPNIKEClientConnection *__hidden this, struct _ADDITIONAL_ADDRESSES_ *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x180013450`
- `0x18001f240`
- `0x180031220`
- `0x180032690`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## string_xrefs

- `0x18001f331`: `VPNIKEClientConnection::UpdatePeerAdditionalAddresses`
- `0x18001f3cb`: `Connection already in disconnecting phase. Hence ignore processing.`
- `0x18001f5ea`: `DeletePolicy failed: %d`
- `0x18001f84c`: `DeletePolicy failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VPNIKEClientConnection::UpdatePeerAdditionalAddresses(
        VPNIKEClientConnection *this,
        struct _ADDITIONAL_ADDRESSES_ *a2)
{
  PVOID *v4; // rbx
  unsigned int v5; // r15d
  char v6; // al
  __int64 v7; // rax
  __int64 v8; // rdx
  __int128 *v9; // r9
  __int64 v10; // rdx
  PVOID v11; // rcx
  _QWORD *v12; // r14
  unsigned int v13; // ebx
  unsigned int v14; // edx
  unsigned int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int128 *v19; // r9
  unsigned int i; // ebx
  unsigned int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int128 *v25; // r9
  unsigned int v26; // ebx
  unsigned int v27; // r8d
  unsigned int v28; // edx
  __int64 v29; // r10
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int128 *v34; // r9
  unsigned int v35; // ebx
  unsigned int v36; // edx
  __int64 v37; // r8
  _QWORD *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int128 *v42; // r9
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int128 *v46; // r9
  __int64 v47; // rax
  __int64 v48; // rdx
  __int128 *v49; // r9
  unsigned int v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v52; // [rsp+40h] [rbp-C0h]
  __int128 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+60h] [rbp-A0h]
  int v55; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+6Ch] [rbp-94h]
  __int128 v57; // [rsp+70h] [rbp-90h] BYREF
  int v58; // [rsp+80h] [rbp-80h] BYREF
  __int128 v59; // [rsp+84h] [rbp-7Ch]
  __int128 v60; // [rsp+94h] [rbp-6Ch]
  int v61; // [rsp+A4h] [rbp-5Ch]
  int v62; // [rsp+B0h] [rbp-50h] BYREF
  char v63[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v50 = 0;
  v62 = 0;
  memset_0(v63, 0, sizeof(v63));
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v57 = 0;
  v52 = 0;
  v51 = 0;
  v53 = 0;
  v54 = 0;
  v5 = -1;
  v55 = -1;
  v56 = 0;
  v6 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v51,
      L"VPNIKEClientConnection::UpdatePeerAdditionalAddresses",
      &v50,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v6 = byte_1800AA941;
  }
  if ( (*((_DWORD *)this + 38) & 0x100000) != 0 )
  {
    if ( (v6 & 8) != 0 )
    {
      LOWORD(v58) = 0;
      v7 = *((_QWORD *)this + 14);
      if ( v7 && *(_QWORD *)(v7 + 16) )
        v5 = *(_DWORD *)(v7 + 16);
      ConvertPortNoToString(&v58, v5);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v8 = *((_QWORD *)this + 14);
        LODWORD(v9) = v8 + 2120;
        if ( !v8 )
          v9 = &v57;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Connection already in disconnecting phase. Hence ignore processing.",
          (_DWORD)v9,
          (v8 + 2686) & -(__int64)(v8 != 0),
          (__int64)&v58);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    {
      v10 = 63;
      v11 = v4[2];
LABEL_113:
      WPP_SF_(v11, v10, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    }
  }
  else
  {
    v12 = (_QWORD *)((char *)this + 304);
    if ( *(_DWORD *)a2 )
    {
      v13 = 0;
      do
      {
        v14 = *((_DWORD *)this + 74);
        if ( v14 )
        {
          v15 = 0;
          while ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 4LL * v13) != *(_DWORD *)(*v12 + 4LL * v15) )
          {
            if ( ++v15 >= v14 )
              goto LABEL_27;
          }
        }
        else
        {
LABEL_27:
          v50 = ClientBFEHandler::PlumbPolicy(
                  *((ClientBFEHandler **)this + 26),
                  1,
                  (struct in_addr *)(*((_QWORD *)a2 + 1) + 4LL * v13),
                  0,
                  (unsigned __int8 *)(*((_QWORD *)this + 14) + 914LL),
                  *(_DWORD *)(*((_QWORD *)this + 14) + 1172LL));
          if ( v50 && (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v62) = 0;
            LOWORD(v58) = 0;
            v16 = *((_QWORD *)this + 14);
            if ( v16 && *(_QWORD *)(v16 + 16) )
              v17 = *(unsigned int *)(v16 + 16);
            else
              v17 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v58, v17);
            FormatRRASErrorString(&v62, L"PlumbPolicy failed: %d", v50);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v18 = *((_QWORD *)this + 14);
              LODWORD(v19) = v18 + 2120;
              if ( !v18 )
                v19 = &v57;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v62,
                (_DWORD)v19,
                (v18 + 2686) & -(__int64)(v18 != 0),
                (__int64)&v58);
            }
          }
        }
        ++v13;
      }
      while ( v13 < *(_DWORD *)a2 );
    }
    for ( i = 0; i < *((_DWORD *)this + 74); ++i )
    {
      if ( *(_DWORD *)a2 )
      {
        v21 = 0;
        while ( *(_DWORD *)(*v12 + 4LL * i) != *(_DWORD *)(*((_QWORD *)a2 + 1) + 4LL * v21) )
        {
          if ( ++v21 >= *(_DWORD *)a2 )
            goto LABEL_43;
        }
      }
      else
      {
LABEL_43:
        v12 = (_QWORD *)((char *)this + 304);
        v50 = ClientBFEHandler::DeletePolicy(
                *((ClientBFEHandler **)this + 26),
                1,
                (struct in_addr *)(*((_QWORD *)this + 38) + 4LL * i),
                0);
        if ( v50 && (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v62) = 0;
          LOWORD(v58) = 0;
          v22 = *((_QWORD *)this + 14);
          if ( v22 && *(_QWORD *)(v22 + 16) )
            v23 = *(unsigned int *)(v22 + 16);
          else
            v23 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v58, v23);
          FormatRRASErrorString(&v62, L"DeletePolicy failed: %d", v50);
          if ( (byte_1800AA941 & 4) != 0 )
          {
            v24 = *((_QWORD *)this + 14);
            LODWORD(v25) = v24 + 2120;
            if ( !v24 )
              v25 = &v57;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v62,
              (_DWORD)v25,
              (v24 + 2686) & -(__int64)(v24 != 0),
              (__int64)&v58);
          }
        }
      }
    }
    if ( *((_DWORD *)a2 + 1) )
    {
      v26 = 0;
      do
      {
        v27 = *((_DWORD *)this + 75);
        if ( v27 )
        {
          v28 = 0;
          v29 = *((_QWORD *)this + 39);
          v30 = (_QWORD *)(*((_QWORD *)a2 + 2) + 16LL * v26);
          while ( v30[1] != *(_QWORD *)(v29 + 16LL * v28 + 8) || *v30 != *(_QWORD *)(v29 + 16LL * v28) )
          {
            if ( ++v28 >= v27 )
              goto LABEL_61;
          }
        }
        else
        {
LABEL_61:
          v50 = ClientBFEHandler::PlumbPolicy(
                  *((ClientBFEHandler **)this + 26),
                  0,
                  0,
                  (struct in6_addr *)(*((_QWORD *)a2 + 2) + 16LL * v26),
                  (unsigned __int8 *)(*((_QWORD *)this + 14) + 914LL),
                  *(_DWORD *)(*((_QWORD *)this + 14) + 1172LL));
          if ( v50 && (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v62) = 0;
            LOWORD(v58) = 0;
            v31 = *((_QWORD *)this + 14);
            if ( v31 && *(_QWORD *)(v31 + 16) )
              v32 = *(unsigned int *)(v31 + 16);
            else
              v32 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v58, v32);
            FormatRRASErrorString(&v62, L"PlumbPolicy failed: %d", v50);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v33 = *((_QWORD *)this + 14);
              LODWORD(v34) = v33 + 2120;
              if ( !v33 )
                v34 = &v57;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v62,
                (_DWORD)v34,
                (v33 + 2686) & -(__int64)(v33 != 0),
                (__int64)&v58);
            }
          }
        }
        ++v26;
      }
      while ( v26 < *((_DWORD *)a2 + 1) );
    }
    if ( *((_DWORD *)this + 75) )
    {
      v35 = 0;
      do
      {
        if ( *((_DWORD *)a2 + 1) )
        {
          v36 = 0;
          v37 = *((_QWORD *)a2 + 2);
          v38 = (_QWORD *)(*((_QWORD *)this + 39) + 16LL * v35);
          while ( v38[1] != *(_QWORD *)(v37 + 16LL * v36 + 8) || *v38 != *(_QWORD *)(v37 + 16LL * v36) )
          {
            if ( ++v36 >= *((_DWORD *)a2 + 1) )
              goto LABEL_79;
          }
        }
        else
        {
LABEL_79:
          v50 = ClientBFEHandler::DeletePolicy(
                  *((ClientBFEHandler **)this + 26),
                  0,
                  0,
                  (struct in6_addr *)(*((_QWORD *)this + 39) + 16LL * v35));
          if ( v50 && (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v62) = 0;
            LOWORD(v58) = 0;
            v39 = *((_QWORD *)this + 14);
            if ( v39 && *(_QWORD *)(v39 + 16) )
              v40 = *(unsigned int *)(v39 + 16);
            else
              v40 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v58, v40);
            FormatRRASErrorString(&v62, L"DeletePolicy failed: %d", v50);
            if ( (byte_1800AA941 & 4) != 0 )
            {
              v41 = *((_QWORD *)this + 14);
              LODWORD(v42) = v41 + 2120;
              if ( !v41 )
                v42 = &v57;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v62,
                (_DWORD)v42,
                (v41 + 2686) & -(__int64)(v41 != 0),
                (__int64)&v58);
            }
          }
        }
        ++v35;
      }
      while ( v35 < *((_DWORD *)this + 75) );
    }
    VPNIKEConnection::UpdatePeerAdditionalAddresses(this, a2);
    v50 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))&xmmword_1800AA980 + 1))(
            *(_QWORD *)(*((_QWORD *)this + 14) + 24LL),
            2,
            *((_QWORD *)a2 + 1),
            (unsigned int)(4 * *(_DWORD *)a2));
    if ( v50 && (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v62) = 0;
      LOWORD(v58) = 0;
      v43 = *((_QWORD *)this + 14);
      if ( v43 && *(_QWORD *)(v43 + 16) )
        v44 = *(unsigned int *)(v43 + 16);
      else
        v44 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v58, v44);
      FormatRRASErrorString(&v62, L"RasSetConnectionUserData failed for v4: %d", v50);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v45 = *((_QWORD *)this + 14);
        LODWORD(v46) = v45 + 2120;
        if ( !v45 )
          v46 = &v57;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v62,
          (_DWORD)v46,
          (v45 + 2686) & -(__int64)(v45 != 0),
          (__int64)&v58);
      }
    }
    v50 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))&xmmword_1800AA980 + 1))(
            *(_QWORD *)(*((_QWORD *)this + 14) + 24LL),
            3,
            *((_QWORD *)a2 + 2),
            (unsigned int)(16 * *((_DWORD *)a2 + 1)));
    if ( v50 && (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v62) = 0;
      LOWORD(v58) = 0;
      v47 = *((_QWORD *)this + 14);
      if ( v47 && *(_QWORD *)(v47 + 16) )
        v5 = *(_DWORD *)(v47 + 16);
      ConvertPortNoToString(&v58, v5);
      FormatRRASErrorString(&v62, L"RasSetConnectionUserData failed for v6: %d", v50);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v48 = *((_QWORD *)this + 14);
        LODWORD(v49) = v48 + 2120;
        if ( !v48 )
          v49 = &v57;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v62,
          (_DWORD)v49,
          (v48 + 2686) & -(__int64)(v48 != 0),
          (__int64)&v58);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v10 = 64;
      v11 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
      goto LABEL_113;
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v51);
}

```

## disassembly

```asm
0x18001f240  mov     [rsp-8+arg_10], rbx
0x18001f245  push    rbp
0x18001f246  push    rsi
0x18001f247  push    rdi
0x18001f248  push    r12
0x18001f24a  push    r13
0x18001f24c  push    r14
0x18001f24e  push    r15
0x18001f250  lea     rbp, [rsp-7C0h]
0x18001f258  sub     rsp, 8C0h
0x18001f25f  mov     rax, cs:__security_cookie
0x18001f266  xor     rax, rsp
0x18001f269  mov     [rbp+7F0h+var_40], rax
0x18001f270  mov     rsi, rdx
0x18001f273  mov     rdi, rcx
0x18001f276  lea     rax, WPP_GLOBAL_Control
0x18001f27d  mov     rbx, cs:WPP_GLOBAL_Control
0x18001f284  cmp     rbx, rax
0x18001f287  jz      short loc_18001F2B1
0x18001f289  test    byte ptr [rbx+1Ch], 1
0x18001f28d  jz      short loc_18001F2B1
0x18001f28f  cmp     byte ptr [rbx+19h], 6
0x18001f293  jb      short loc_18001F2B1
0x18001f295  mov     edx, 3Eh ; '>'
0x18001f29a  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001f2a1  mov     rcx, [rbx+10h]
0x18001f2a5  call    WPP_SF_
0x18001f2aa  mov     rbx, cs:WPP_GLOBAL_Control
0x18001f2b1  xor     r13d, r13d
0x18001f2b4  mov     [rsp+8F0h+var_8C0], r13d
0x18001f2b9  mov     [rbp+7F0h+var_840], r13d
0x18001f2bd  xor     edx, edx; Val
0x18001f2bf  mov     r8d, 7FCh; Size
0x18001f2c5  lea     rcx, [rbp+7F0h+var_83C]; void *
0x18001f2c9  call    memset_0
0x18001f2ce  mov     [rbp+7F0h+var_870], r13d
0x18001f2d2  xorps   xmm0, xmm0
0x18001f2d5  xor     eax, eax
0x18001f2d7  movups  [rbp+7F0h+var_86C], xmm0
0x18001f2db  movups  [rbp+7F0h+var_85C], xmm0
0x18001f2df  mov     [rbp+7F0h+var_84C], eax
0x18001f2e2  movups  [rsp+8F0h+var_880], xmm0
0x18001f2e7  xorps   xmm1, xmm1
0x18001f2ea  movdqu  [rsp+8F0h+var_8B0], xmm1
0x18001f2f0  mov     [rsp+8F0h+var_8B8], r13
0x18001f2f5  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18001f2fb  mov     [rsp+8F0h+var_890], r13
0x18001f300  or      r15d, 0FFFFFFFFh
0x18001f304  mov     [rsp+8F0h+var_888], r15d
0x18001f309  mov     [rsp+8F0h+var_884], r13d
0x18001f30e  mov     al, cs:byte_1800AA941
0x18001f314  mov     r14b, 8
0x18001f317  test    r14b, al
0x18001f31a  jz      short loc_18001F34F
0x18001f31c  mov     rax, [rdi+70h]
0x18001f320  mov     [rsp+8F0h+var_8D0], rax; void *
0x18001f325  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001f32c  lea     r8, [rsp+8F0h+var_8C0]; unsigned int *
0x18001f331  lea     rdx, aVpnikeclientco_16; "VPNIKEClientConnection::UpdatePeerAddit"...
0x18001f338  lea     rcx, [rsp+8F0h+var_8B8]; this
0x18001f33d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18001f342  mov     rbx, cs:WPP_GLOBAL_Control
0x18001f349  mov     al, cs:byte_1800AA941
0x18001f34f  test    dword ptr [rdi+98h], 100000h
0x18001f359  jz      loc_18001F41E
0x18001f35f  test    r14b, al
0x18001f362  jz      loc_18001F3EC
0x18001f368  mov     word ptr [rbp+7F0h+var_870], r13w
0x18001f36d  mov     rax, [rdi+70h]
0x18001f371  test    rax, rax
0x18001f374  jz      short loc_18001F380
0x18001f376  cmp     [rax+10h], r13
0x18001f37a  jz      short loc_18001F380
0x18001f37c  mov     r15d, [rax+10h]
0x18001f380  mov     edx, r15d
0x18001f383  lea     rcx, [rbp+7F0h+var_870]
0x18001f387  call    ConvertPortNoToString
0x18001f38c  test    cs:byte_1800AA941, r14b
0x18001f393  jz      short loc_18001F3E5
0x18001f395  mov     rdx, [rdi+70h]
0x18001f399  mov     rax, rdx
0x18001f39c  lea     rcx, [rdx+0A7Eh]
0x18001f3a3  neg     rax
0x18001f3a6  sbb     r8, r8
0x18001f3a9  and     r8, rcx
0x18001f3ac  test    rdx, rdx
0x18001f3af  lea     r9, [rdx+848h]
0x18001f3b6  jnz     short loc_18001F3BD
0x18001f3b8  lea     r9, [rsp+8F0h+var_880]
0x18001f3bd  lea     rax, [rbp+7F0h+var_870]
0x18001f3c1  mov     qword ptr [rsp+8F0h+var_8C8], rax
0x18001f3c6  mov     [rsp+8F0h+var_8D0], r8
0x18001f3cb  lea     r8, aConnectionAlre; "Connection already in disconnecting pha"...
0x18001f3d2  lea     rdx, RasVpnIkeParamTraceInfo
0x18001f3d9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f3e0  call    McTemplateU0zjzz_EventWriteTransfer
0x18001f3e5  mov     rbx, cs:WPP_GLOBAL_Control
0x18001f3ec  lea     rax, WPP_GLOBAL_Control
0x18001f3f3  cmp     rbx, rax
0x18001f3f6  jz      loc_18001FA98
0x18001f3fc  test    byte ptr [rbx+1Ch], 1
0x18001f400  jz      loc_18001FA98
0x18001f406  cmp     byte ptr [rbx+19h], 6
0x18001f40a  jb      loc_18001FA98
0x18001f410  mov     edx, 3Fh ; '?'
0x18001f415  mov     rcx, [rbx+10h]
0x18001f419  jmp     loc_18001FA8B
0x18001f41e  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f425  lea     r14, [rdi+130h]
0x18001f42c  cmp     [rsi], r13d
0x18001f42f  jbe     loc_18001F54C
0x18001f435  mov     ebx, r13d
0x18001f438  mov     edx, [rdi+128h]
0x18001f43e  mov     r8d, ebx
0x18001f441  test    edx, edx
0x18001f443  jz      short loc_18001F465
0x18001f445  mov     ecx, r13d
0x18001f448  mov     r9, [r14]
0x18001f44b  mov     rax, [rsi+8]
0x18001f44f  mov     r10d, [rax+r8*4]
0x18001f453  mov     eax, ecx
0x18001f455  cmp     r10d, [r9+rax*4]
0x18001f459  jz      loc_18001F542
0x18001f45f  inc     ecx
0x18001f461  cmp     ecx, edx
0x18001f463  jb      short loc_18001F453
0x18001f465  mov     rcx, [rdi+70h]
0x18001f469  lea     rdx, [rcx+392h]
0x18001f470  mov     rax, [rsi+8]
0x18001f474  lea     r8, [rax+r8*4]; struct in_addr *
0x18001f478  mov     eax, [rcx+494h]
0x18001f47e  mov     [rsp+8F0h+var_8C8], eax; unsigned int
0x18001f482  mov     [rsp+8F0h+var_8D0], rdx; unsigned __int8 *
0x18001f487  xor     r9d, r9d; struct in6_addr *
0x18001f48a  mov     dl, 1; unsigned __int8
0x18001f48c  mov     rcx, [rdi+0D0h]; this
0x18001f493  call    ?PlumbPolicy@ClientBFEHandler@@QEAAKEPEAUin_addr@@PEAUin6_addr@@PEAEK@Z; ClientBFEHandler::PlumbPolicy(uchar,in_addr *,in6_addr *,uchar *,ulong)
0x18001f498  mov     [rsp+8F0h+var_8C0], eax
0x18001f49c  test    eax, eax
0x18001f49e  jz      loc_18001F542
0x18001f4a4  test    cs:byte_1800AA941, 4
0x18001f4ab  jz      loc_18001F542
0x18001f4b1  mov     word ptr [rbp+7F0h+var_840], r13w
0x18001f4b6  mov     word ptr [rbp+7F0h+var_870], r13w
0x18001f4bb  mov     rax, [rdi+70h]
0x18001f4bf  test    rax, rax
0x18001f4c2  jz      short loc_18001F4CF
0x18001f4c4  cmp     [rax+10h], r13
0x18001f4c8  jz      short loc_18001F4CF
0x18001f4ca  mov     edx, [rax+10h]
0x18001f4cd  jmp     short loc_18001F4D2
0x18001f4cf  mov     edx, r15d
0x18001f4d2  lea     rcx, [rbp+7F0h+var_870]
0x18001f4d6  call    ConvertPortNoToString
0x18001f4db  mov     r8d, [rsp+8F0h+var_8C0]
0x18001f4e0  lea     rdx, aPlumbpolicyFai; "PlumbPolicy failed: %d"
0x18001f4e7  lea     rcx, [rbp+7F0h+var_840]
0x18001f4eb  call    FormatRRASErrorString
0x18001f4f0  test    cs:byte_1800AA941, 4
0x18001f4f7  jz      short loc_18001F542
0x18001f4f9  mov     rdx, [rdi+70h]
0x18001f4fd  mov     rax, rdx
0x18001f500  lea     rcx, [rdx+0A7Eh]
0x18001f507  neg     rax
0x18001f50a  sbb     r8, r8
0x18001f50d  and     r8, rcx
0x18001f510  test    rdx, rdx
0x18001f513  lea     r9, [rdx+848h]
0x18001f51a  jnz     short loc_18001F521
0x18001f51c  lea     r9, [rsp+8F0h+var_880]
0x18001f521  lea     rax, [rbp+7F0h+var_870]
0x18001f525  mov     qword ptr [rsp+8F0h+var_8C8], rax
0x18001f52a  mov     [rsp+8F0h+var_8D0], r8
0x18001f52f  lea     r8, [rbp+7F0h+var_840]
0x18001f533  lea     rdx, RasVpnIkeParamTraceError
0x18001f53a  mov     rcx, r12
0x18001f53d  call    McTemplateU0zjzz_EventWriteTransfer
0x18001f542  inc     ebx
0x18001f544  cmp     ebx, [rsi]
0x18001f546  jb      loc_18001F438
0x18001f54c  mov     ebx, r13d
0x18001f54f  cmp     [rdi+128h], r13d
0x18001f556  jbe     loc_18001F65A
0x18001f55c  mov     edx, ebx
0x18001f55e  cmp     [rsi], r13d
0x18001f561  jbe     short loc_18001F583
0x18001f563  mov     ecx, r13d
0x18001f566  mov     r8, [rsi+8]
0x18001f56a  mov     rax, [r14]
0x18001f56d  mov     r9d, [rax+rdx*4]
0x18001f571  mov     eax, ecx
0x18001f573  cmp     r9d, [r8+rax*4]
0x18001f577  jz      loc_18001F64C
0x18001f57d  inc     ecx
0x18001f57f  cmp     ecx, [rsi]
0x18001f581  jb      short loc_18001F571
0x18001f583  lea     r14, [rdi+130h]
0x18001f58a  mov     rax, [r14]
0x18001f58d  lea     r8, [rax+rdx*4]; struct in_addr *
0x18001f591  xor     r9d, r9d; struct in6_addr *
0x18001f594  mov     dl, 1; unsigned __int8
0x18001f596  mov     rcx, [rdi+0D0h]; this
0x18001f59d  call    ?DeletePolicy@ClientBFEHandler@@QEAAKEPEAUin_addr@@PEAUin6_addr@@@Z; ClientBFEHandler::DeletePolicy(uchar,in_addr *,in6_addr *)
0x18001f5a2  mov     [rsp+8F0h+var_8C0], eax
0x18001f5a6  test    eax, eax
0x18001f5a8  jz      loc_18001F64C
0x18001f5ae  test    cs:byte_1800AA941, 4
0x18001f5b5  jz      loc_18001F64C
0x18001f5bb  mov     word ptr [rbp+7F0h+var_840], r13w
0x18001f5c0  mov     word ptr [rbp+7F0h+var_870], r13w
0x18001f5c5  mov     rax, [rdi+70h]
0x18001f5c9  test    rax, rax
0x18001f5cc  jz      short loc_18001F5D9
0x18001f5ce  cmp     [rax+10h], r13
0x18001f5d2  jz      short loc_18001F5D9
0x18001f5d4  mov     edx, [rax+10h]
0x18001f5d7  jmp     short loc_18001F5DC
0x18001f5d9  mov     edx, r15d
0x18001f5dc  lea     rcx, [rbp+7F0h+var_870]
0x18001f5e0  call    ConvertPortNoToString
0x18001f5e5  mov     r8d, [rsp+8F0h+var_8C0]
0x18001f5ea  lea     rdx, aDeletepolicyFa; "DeletePolicy failed: %d"
0x18001f5f1  lea     rcx, [rbp+7F0h+var_840]
0x18001f5f5  call    FormatRRASErrorString
0x18001f5fa  test    cs:byte_1800AA941, 4
0x18001f601  jz      short loc_18001F64C
0x18001f603  mov     rdx, [rdi+70h]
0x18001f607  mov     rax, rdx
0x18001f60a  lea     rcx, [rdx+0A7Eh]
0x18001f611  neg     rax
0x18001f614  sbb     r8, r8
0x18001f617  and     r8, rcx
0x18001f61a  test    rdx, rdx
0x18001f61d  lea     r9, [rdx+848h]
0x18001f624  jnz     short loc_18001F62B
0x18001f626  lea     r9, [rsp+8F0h+var_880]
0x18001f62b  lea     rax, [rbp+7F0h+var_870]
0x18001f62f  mov     qword ptr [rsp+8F0h+var_8C8], rax
0x18001f634  mov     [rsp+8F0h+var_8D0], r8
0x18001f639  lea     r8, [rbp+7F0h+var_840]
0x18001f63d  lea     rdx, RasVpnIkeParamTraceError
0x18001f644  mov     rcx, r12
0x18001f647  call    McTemplateU0zjzz_EventWriteTransfer
0x18001f64c  inc     ebx
0x18001f64e  cmp     ebx, [rdi+128h]
0x18001f654  jb      loc_18001F55C
0x18001f65a  cmp     [rsi+4], r13d
0x18001f65e  jbe     loc_18001F797
0x18001f664  mov     ebx, r13d
0x18001f667  mov     r8d, [rdi+12Ch]
0x18001f66e  mov     r9d, ebx
0x18001f671  test    r8d, r8d
0x18001f674  jz      short loc_18001F6AF
0x18001f676  mov     edx, r13d
0x18001f679  mov     r10, [rdi+138h]
0x18001f680  mov     ecx, r9d
0x18001f683  shl     rcx, 4
0x18001f687  add     rcx, [rsi+10h]
0x18001f68b  mov     r11, [rcx+8]
0x18001f68f  mov     eax, edx
0x18001f691  add     rax, rax
0x18001f694  cmp     r11, [r10+rax*8+8]
0x18001f699  jnz     short loc_18001F6A8
0x18001f69b  mov     rax, [r10+rax*8]
0x18001f69f  cmp     [rcx], rax
0x18001f6a2  jz      loc_18001F78C
0x18001f6a8  inc     edx
0x18001f6aa  cmp     edx, r8d
0x18001f6ad  jb      short loc_18001F68F
0x18001f6af  mov     rax, [rdi+70h]
0x18001f6b3  lea     rcx, [rax+392h]
0x18001f6ba  shl     r9, 4
0x18001f6be  add     r9, [rsi+10h]; struct in6_addr *
0x18001f6c2  mov     eax, [rax+494h]
0x18001f6c8  mov     [rsp+8F0h+var_8C8], eax; unsigned int
0x18001f6cc  mov     [rsp+8F0h+var_8D0], rcx; unsigned __int8 *
0x18001f6d1  xor     r8d, r8d; struct in_addr *
0x18001f6d4  xor     edx, edx; unsigned __int8
0x18001f6d6  mov     rcx, [rdi+0D0h]; this
0x18001f6dd  call    ?PlumbPolicy@ClientBFEHandler@@QEAAKEPEAUin_addr@@PEAUin6_addr@@PEAEK@Z; ClientBFEHandler::PlumbPolicy(uchar,in_addr *,in6_addr *,uchar *,ulong)
0x18001f6e2  mov     [rsp+8F0h+var_8C0], eax
0x18001f6e6  test    eax, eax
0x18001f6e8  jz      loc_18001F78C
0x18001f6ee  test    cs:byte_1800AA941, 4
0x18001f6f5  jz      loc_18001F78C
0x18001f6fb  mov     word ptr [rbp+7F0h+var_840], r13w
0x18001f700  mov     word ptr [rbp+7F0h+var_870], r13w
0x18001f705  mov     rax, [rdi+70h]
0x18001f709  test    rax, rax
0x18001f70c  jz      short loc_18001F719
0x18001f70e  cmp     [rax+10h], r13
0x18001f712  jz      short loc_18001F719
0x18001f714  mov     edx, [rax+10h]
0x18001f717  jmp     short loc_18001F71C
0x18001f719  mov     edx, r15d
0x18001f71c  lea     rcx, [rbp+7F0h+var_870]
0x18001f720  call    ConvertPortNoToString
0x18001f725  mov     r8d, [rsp+8F0h+var_8C0]
0x18001f72a  lea     rdx, aPlumbpolicyFai; "PlumbPolicy failed: %d"
0x18001f731  lea     rcx, [rbp+7F0h+var_840]
  ... truncated ...
```
