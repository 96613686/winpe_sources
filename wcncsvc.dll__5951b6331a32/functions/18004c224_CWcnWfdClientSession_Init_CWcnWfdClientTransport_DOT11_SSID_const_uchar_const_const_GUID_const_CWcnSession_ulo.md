# CWcnWfdClientSession::Init(CWcnWfdClientTransport *,_DOT11_SSID const *,uchar const * const,_GUID const *,CWcnSession *,ulong)

- ea: `0x18004c224`
- end: `0x18004c7df`
- name: `?Init@CWcnWfdClientSession@@QEAAJPEAVCWcnWfdClientTransport@@PEBU_DOT11_SSID@@QEBEPEBU_GUID@@PEAVCWcnSession@@K@Z`
- size: `1467`
- prototype: `__int64 __fastcall(CWcnWfdClientSession *this, struct CWcnWfdClientTransport *, const struct _DOT11_SSID *, const unsigned __int8 *, struct _GUID *rguid, struct CWcnSession *, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18004d120`

## callees

- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000b1f8`
- `0x180018c6c`
- `0x18003cfa4`
- `0x18004af24`
- `0x18004b440`
- `0x18004c224`
- `0x180050118`
- `0x1800505fc`
- `0x180050934`
- `0x180050b38`
- `0x1800510b8`
- `0x1800511f8`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18004c3a4`
- `RPCRT4!UuidCreate` at `0x18004c3a4`
- `wlanapi!WlanConnectEx` at `0x18004c702`
- `wlanapi!WlanConnectEx` at `0x18004c702`
- `wlanapi!WlanRegisterNotification` at `0x18004c665`
- `wlanapi!WlanRegisterNotification` at `0x18004c665`

## string_xrefs

- `0x18004c303`: `pSsid`

## pseudocode

```c
__int64 __fastcall CWcnWfdClientSession::Init(
        CWcnWfdClientSession *this,
        struct CWcnWfdClientTransport *a2,
        const struct _DOT11_SSID *a3,
        const unsigned __int8 *a4,
        struct _GUID *rguid,
        struct CWcnSession *a6,
        unsigned int a7)
{
  _BYTE *v10; // r10
  const char *Indent; // rax
  __int64 v12; // r10
  __int64 v13; // rdx
  const char *v14; // r9
  int TemporaryProfile; // ebx
  unsigned int v16; // ebx
  signed int v17; // eax
  unsigned int v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  HANDLE *v21; // r14
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int IsSecure; // eax
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // r10
  bool v30; // [rsp+40h] [rbp-91h] BYREF
  bool v31; // [rsp+41h] [rbp-90h] BYREF
  struct _WLAN_CONNECT_EXTENSION_PARAMETERS_V1 *v32; // [rsp+48h] [rbp-89h] BYREF
  __int128 v33; // [rsp+50h] [rbp-81h] BYREF
  __int128 v34; // [rsp+60h] [rbp-71h]
  __int64 v35; // [rsp+70h] [rbp-61h]
  const unsigned __int8 *v36; // [rsp+78h] [rbp-59h]
  _BYTE v37[32]; // [rsp+80h] [rbp-51h] BYREF
  _BYTE v38[24]; // [rsp+A0h] [rbp-31h] BYREF
  _QWORD *v39; // [rsp+B8h] [rbp-19h]
  __int128 v40; // [rsp+C0h] [rbp-11h] BYREF
  int v41; // [rsp+D0h] [rbp-1h]

  v36 = a4;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v38);
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v37);
  v31 = 1;
  v30 = 0;
  v40 = 0;
  v41 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 10, WPP_16f86085a523394303ca33111ba71bc3_Traceguids, Indent);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      goto LABEL_13;
    v13 = 11;
    v14 = "pSsid";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v10 + 2), v13, WPP_16f86085a523394303ca33111ba71bc3_Traceguids, v14);
LABEL_13:
    TemporaryProfile = -2147467261;
    goto LABEL_77;
  }
  if ( !rguid )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      goto LABEL_13;
    v13 = 12;
    v14 = "pWlanInterface";
    goto LABEL_12;
  }
  *((_DWORD *)a6 + 38) = 288;
  v16 = a7;
  if ( (a7 & 0x2000) == 0 )
  {
    v16 = -1;
    CWcnSession::UpdateSelfIdentity(a6, 0xFFFFFFFF);
  }
  *((_QWORD *)this + 18) = a2;
  *((struct _GUID *)this + 4) = *rguid;
  *((_OWORD *)this + 5) = *(_OWORD *)&a3->uSSIDLength;
  *((_OWORD *)this + 6) = *(_OWORD *)&a3->ucSSID[12];
  *((_DWORD *)this + 28) = *(_DWORD *)&a3->ucSSID[28];
  *((_QWORD *)this + 2) = a6;
  *((_BYTE *)this + 336) = 0;
  *((_DWORD *)this + 6) = v16;
  *((_DWORD *)this + 33) = v16;
  v17 = UuidCreate((UUID *)((char *)this + 116));
  if ( v17 )
  {
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    else
      v18 = v17;
    TemporaryProfile = v18 | 0x80000000;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_73;
    v20 = 13;
    goto LABEL_72;
  }
  v21 = (HANDLE *)((char *)this + 56);
  TemporaryProfile = WcnWlanOpenHandle((PHANDLE)this + 7);
  if ( TemporaryProfile >= 0 )
  {
    IsSecure = WcnWlanDetermineIfNetworksIsSecure(*v21, a3, rguid, &v31, &v30);
    if ( IsSecure < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_16f86085a523394303ca33111ba71bc3_Traceguids,
        (unsigned int)IsSecure);
    }
    TemporaryProfile = WcnWlanGenerateTemporaryProfile(
                         a3,
                         v30,
                         (CWcnWfdClientSession *)((char *)this + 116),
                         (struct CSbSafeBuffer *)v38);
    if ( TemporaryProfile >= 0 )
    {
      TemporaryProfile = WcnWlanGetMacAddressOfInterface(rguid, (unsigned __int8 (*)[6])((char *)this + 8));
      if ( TemporaryProfile < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF__guid_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_16f86085a523394303ca33111ba71bc3_Traceguids,
            rguid,
            TemporaryProfile);
        goto LABEL_73;
      }
      TemporaryProfile = CWcnScheduler::CreateWorkItem(
                           (CWcnScheduler *)(*((_QWORD *)g_pWcnService + 7) + 320LL),
                           (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))CWcnWfdClientSession::RealDisconnectThunk,
                           this,
                           (struct _TP_WORK **)this + 19);
      if ( TemporaryProfile >= 0 )
      {
        HIDWORD(v40) = *(_DWORD *)v36;
        LOWORD(v41) = *((_WORD *)v36 + 2);
        *(_QWORD *)((char *)&v40 + 4) = 0x100000001LL;
        LODWORD(v33) = 1;
        *((_QWORD *)&v33 + 1) = *v39;
        *(_QWORD *)&v34 = a3;
        *((_QWORD *)&v34 + 1) = &v40;
        v35 = 1;
        TemporaryProfile = CWcnWfdClientTransport::GenerateAssociationRequestWpsIe(
                             *((CWcnWfdClientTransport **)this + 18),
                             (struct CWcnIdentity *)(*((_QWORD *)this + 2) + 40LL),
                             (struct CSbSafeBuffer *)v37);
        if ( TemporaryProfile >= 0 )
        {
          TemporaryProfile = WcnWlanBuildIeListStructure((struct CSbSafeBuffer *)v37, &v32);
          if ( TemporaryProfile >= 0 )
          {
            v17 = WlanRegisterNotification(*v21, 8u, 0, CWcnWfdClientSession::WlanNotificationCallbackThunk, this, 0, 0);
            if ( v17 )
            {
              if ( v17 > 0 )
                v25 = (unsigned __int16)v17 | 0x80070000;
              else
                v25 = v17;
              TemporaryProfile = v25 | 0x80000000;
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_73;
              v20 = 21;
            }
            else
            {
              if ( !v31 )
                HIDWORD(v35) |= 4u;
              TemporaryProfile = CWcnWfdClientTransport::NotifySessionCreated(
                                   *((CWcnWfdClientTransport **)this + 18),
                                   this);
              if ( TemporaryProfile < 0 )
              {
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v23 = 22;
                  goto LABEL_27;
                }
                goto LABEL_73;
              }
              v17 = WlanConnectEx(*v21, rguid, &v33, v32);
              if ( !v17 )
                goto LABEL_73;
              v26 = v17 > 0 ? (unsigned __int16)v17 | 0x80070000 : v17;
              TemporaryProfile = v26 | 0x80000000;
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_73;
              v20 = 23;
            }
LABEL_72:
            WPP_SF_Dd(v19[2], v20, WPP_16f86085a523394303ca33111ba71bc3_Traceguids, (unsigned int)v17, TemporaryProfile);
            goto LABEL_73;
          }
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = 20;
            goto LABEL_27;
          }
        }
        else
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = 19;
            goto LABEL_27;
          }
        }
      }
      else
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = 18;
          goto LABEL_27;
        }
      }
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = 16;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = 14;
LABEL_27:
      WPP_SF_d(v22[2], v23, WPP_16f86085a523394303ca33111ba71bc3_Traceguids, (unsigned int)TemporaryProfile);
    }
  }
LABEL_73:
  WcnWlanSafeFree((void **)&v32);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (TemporaryProfile < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v27 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(
      *(_QWORD *)(v28 + 16),
      24,
      (unsigned int)WPP_16f86085a523394303ca33111ba71bc3_Traceguids,
      v27,
      TemporaryProfile);
  }
LABEL_77:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v37);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v38);
  return (unsigned int)TemporaryProfile;
}

```

## disassembly

```asm
0x18004c224  mov     [rsp-8+arg_8], rbx
0x18004c229  push    rbp
0x18004c22a  push    rsi
0x18004c22b  push    rdi
0x18004c22c  push    r12
0x18004c22e  push    r13
0x18004c230  push    r14
0x18004c232  push    r15
0x18004c234  lea     rbp, [rsp-0Fh]
0x18004c239  sub     rsp, 0E0h
0x18004c240  mov     rax, cs:__security_cookie
0x18004c247  xor     rax, rsp
0x18004c24a  mov     [rbp+3Fh+var_38], rax
0x18004c24e  mov     [rbp+3Fh+var_98], r9
0x18004c252  mov     r15, r8
0x18004c255  mov     r12, rdx
0x18004c258  mov     rdi, rcx
0x18004c25b  mov     rsi, [rbp+3Fh+rguid]
0x18004c25f  mov     r14, [rbp+3Fh+arg_28]
0x18004c263  xorps   xmm0, xmm0
0x18004c266  xor     eax, eax
0x18004c268  movups  [rsp+110h+var_C0], xmm0
0x18004c26d  movups  [rbp+3Fh+var_B0], xmm0
0x18004c271  mov     [rbp+3Fh+var_A0], rax
0x18004c275  mov     [rsp+110h+var_C8], rax
0x18004c27a  lea     rcx, [rbp+3Fh+var_70]; this
0x18004c27e  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004c283  nop
0x18004c284  lea     rcx, [rbp+3Fh+var_90]; this
0x18004c288  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004c28d  nop
0x18004c28e  mov     [rsp+110h+var_CF], 1
0x18004c293  mov     [rsp+110h+var_D0], 0
0x18004c298  xorps   xmm0, xmm0
0x18004c29b  xor     eax, eax
0x18004c29d  movups  [rbp+3Fh+var_50], xmm0
0x18004c2a1  mov     [rbp+3Fh+var_40], eax
0x18004c2a4  lea     rax, WPP_GLOBAL_Control
0x18004c2ab  mov     r10, cs:WPP_GLOBAL_Control
0x18004c2b2  cmp     r10, rax
0x18004c2b5  jz      short loc_18004C2EE
0x18004c2b7  cmp     byte ptr [r10+19h], 6
0x18004c2bc  jb      short loc_18004C2EE
0x18004c2be  mov     ecx, 1; int
0x18004c2c3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004c2c8  mov     edx, 0Ah
0x18004c2cd  mov     r9, rax
0x18004c2d0  lea     r8, WPP_16f86085a523394303ca33111ba71bc3_Traceguids
0x18004c2d7  mov     rcx, [r10+10h]
0x18004c2db  call    WPP_SF_s
0x18004c2e0  mov     r10, cs:WPP_GLOBAL_Control
0x18004c2e7  lea     rax, WPP_GLOBAL_Control
0x18004c2ee  test    r15, r15
0x18004c2f1  jnz     short loc_18004C30C
0x18004c2f3  cmp     r10, rax
0x18004c2f6  jz      short loc_18004C337
0x18004c2f8  cmp     byte ptr [r10+19h], 2
0x18004c2fd  jb      short loc_18004C337
0x18004c2ff  lea     edx, [r15+0Bh]
0x18004c303  lea     r9, aPssid; "pSsid"
0x18004c30a  jmp     short loc_18004C327
0x18004c30c  test    rsi, rsi
0x18004c30f  jnz     short loc_18004C341
0x18004c311  cmp     r10, rax
0x18004c314  jz      short loc_18004C337
0x18004c316  cmp     byte ptr [r10+19h], 2
0x18004c31b  jb      short loc_18004C337
0x18004c31d  lea     edx, [rsi+0Ch]
0x18004c320  lea     r9, aPwlaninterface_0; "pWlanInterface"
0x18004c327  lea     r8, WPP_16f86085a523394303ca33111ba71bc3_Traceguids
0x18004c32e  mov     rcx, [r10+10h]
0x18004c332  call    WPP_SF_s
0x18004c337  mov     ebx, 80004003h
0x18004c33c  jmp     loc_18004C7A3
0x18004c341  mov     dword ptr [r14+98h], 120h
0x18004c34c  mov     ebx, [rbp+3Fh+arg_30]
0x18004c34f  bt      ebx, 0Dh
0x18004c353  jb      short loc_18004C362
0x18004c355  or      ebx, 0FFFFFFFFh
0x18004c358  mov     edx, ebx; unsigned int
0x18004c35a  mov     rcx, r14; this
0x18004c35d  call    ?UpdateSelfIdentity@CWcnSession@@QEAAJK@Z; CWcnSession::UpdateSelfIdentity(ulong)
0x18004c362  mov     [rdi+90h], r12
0x18004c369  movups  xmm0, xmmword ptr [rsi]
0x18004c36c  movdqu  xmmword ptr [rdi+40h], xmm0
0x18004c371  movups  xmm0, xmmword ptr [r15]
0x18004c375  movups  xmmword ptr [rdi+50h], xmm0
0x18004c379  movups  xmm1, xmmword ptr [r15+10h]
0x18004c37e  movups  xmmword ptr [rdi+60h], xmm1
0x18004c382  mov     eax, [r15+20h]
0x18004c386  mov     [rdi+70h], eax
0x18004c389  mov     [rdi+10h], r14
0x18004c38d  xor     r12d, r12d
0x18004c390  mov     [rdi+150h], r12b
0x18004c397  mov     [rdi+18h], ebx
0x18004c39a  mov     [rdi+84h], ebx
0x18004c3a0  lea     rcx, [rdi+74h]; Uuid
0x18004c3a4  call    cs:__imp_UuidCreate
0x18004c3aa  test    eax, eax
0x18004c3ac  jz      short loc_18004C3EE
0x18004c3ae  jg      short loc_18004C3B4
0x18004c3b0  mov     ebx, eax
0x18004c3b2  jmp     short loc_18004C3BD
0x18004c3b4  movzx   ebx, ax
0x18004c3b7  or      ebx, 80070000h
0x18004c3bd  or      ebx, 80000000h
0x18004c3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c3ca  lea     rdx, WPP_GLOBAL_Control
0x18004c3d1  cmp     rcx, rdx
0x18004c3d4  jz      loc_18004C756
0x18004c3da  cmp     byte ptr [rcx+19h], 2
0x18004c3de  jb      loc_18004C756
0x18004c3e4  mov     edx, 0Dh
0x18004c3e9  jmp     loc_18004C73F
0x18004c3ee  lea     r14, [rdi+38h]
0x18004c3f2  mov     rcx, r14; phClientHandle
0x18004c3f5  call    ?WcnWlanOpenHandle@@YAJPEAPEAX@Z; WcnWlanOpenHandle(void * *)
0x18004c3fa  mov     ebx, eax
0x18004c3fc  test    eax, eax
0x18004c3fe  jns     short loc_18004C43E
0x18004c400  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c407  lea     rax, WPP_GLOBAL_Control
0x18004c40e  cmp     rcx, rax
0x18004c411  jz      loc_18004C756
0x18004c417  cmp     byte ptr [rcx+19h], 2
0x18004c41b  jb      loc_18004C756
0x18004c421  mov     edx, 0Eh
0x18004c426  mov     r9d, ebx
0x18004c429  lea     r8, WPP_16f86085a523394303ca33111ba71bc3_Traceguids
0x18004c430  mov     rcx, [rcx+10h]
0x18004c434  call    WPP_SF_d
0x18004c439  jmp     loc_18004C756
0x18004c43e  lea     rax, [rsp+110h+var_D0]
0x18004c443  mov     [rsp+110h+pCallbackContext], rax; bool *
0x18004c448  lea     r9, [rsp+110h+var_CF]; bool *
0x18004c44d  mov     r8, rsi; struct _GUID *
0x18004c450  mov     rdx, r15; struct _DOT11_SSID *
0x18004c453  mov     rcx, [r14]; hClientHandle
0x18004c456  call    ?WcnWlanDetermineIfNetworksIsSecure@@YAJPEAXPEBU_DOT11_SSID@@PEBU_GUID@@PEA_N3@Z; WcnWlanDetermineIfNetworksIsSecure(void *,_DOT11_SSID const *,_GUID const *,bool *,bool *)
0x18004c45b  test    eax, eax
0x18004c45d  jns     short loc_18004C490
0x18004c45f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c466  lea     rdx, WPP_GLOBAL_Control
0x18004c46d  cmp     rcx, rdx
0x18004c470  jz      short loc_18004C490
0x18004c472  cmp     byte ptr [rcx+19h], 3
0x18004c476  jb      short loc_18004C490
0x18004c478  mov     edx, 0Fh
0x18004c47d  mov     r9d, eax
0x18004c480  lea     r8, WPP_16f86085a523394303ca33111ba71bc3_Traceguids
0x18004c487  mov     rcx, [rcx+10h]
0x18004c48b  call    WPP_SF_d
0x18004c490  lea     r9, [rbp+3Fh+var_70]; struct CSbSafeBuffer *
0x18004c494  lea     r8, [rdi+74h]; struct tagWcnEapSessionConfiguration *
0x18004c498  mov     dl, [rsp+110h+var_D0]; bool
0x18004c49c  mov     rcx, r15; struct _DOT11_SSID *
0x18004c49f  call    ?WcnWlanGenerateTemporaryProfile@@YAJPEBU_DOT11_SSID@@_NPEAUtagWcnEapSessionConfiguration@@PEAVCSbSafeBuffer@@@Z; WcnWlanGenerateTemporaryProfile(_DOT11_SSID const *,bool,tagWcnEapSessionConfiguration *,CSbSafeBuffer *)
0x18004c4a4  mov     ebx, eax
0x18004c4a6  test    eax, eax
0x18004c4a8  jns     short loc_18004C4D5
0x18004c4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c4b1  lea     rax, WPP_GLOBAL_Control
0x18004c4b8  cmp     rcx, rax
0x18004c4bb  jz      loc_18004C756
0x18004c4c1  cmp     byte ptr [rcx+19h], 2
0x18004c4c5  jb      loc_18004C756
0x18004c4cb  mov     edx, 10h
0x18004c4d0  jmp     loc_18004C426
0x18004c4d5  lea     rdx, [rdi+8]; unsigned __int8 (*)[6]
0x18004c4d9  mov     rcx, rsi; rguid
0x18004c4dc  call    ?WcnWlanGetMacAddressOfInterface@@YAJPEBU_GUID@@PEAY05E@Z; WcnWlanGetMacAddressOfInterface(_GUID const *,uchar (*)[6])
0x18004c4e1  mov     ebx, eax
0x18004c4e3  test    eax, eax
0x18004c4e5  jns     short loc_18004C529
0x18004c4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c4ee  lea     rax, WPP_GLOBAL_Control
0x18004c4f5  cmp     rcx, rax
0x18004c4f8  jz      loc_18004C756
0x18004c4fe  cmp     byte ptr [rcx+19h], 2
0x18004c502  jb      loc_18004C756
0x18004c508  mov     edx, 11h
0x18004c50d  mov     dword ptr [rsp+110h+pCallbackContext], ebx
0x18004c511  mov     r9, rsi
0x18004c514  lea     r8, WPP_16f86085a523394303ca33111ba71bc3_Traceguids
0x18004c51b  mov     rcx, [rcx+10h]
0x18004c51f  call    WPP_SF__guid_d
0x18004c524  jmp     loc_18004C756
0x18004c529  lea     r9, [rdi+98h]; struct _TP_WORK **
0x18004c530  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18004c537  mov     rcx, [rax+38h]
0x18004c53b  add     rcx, 140h; this
0x18004c542  mov     r8, rdi; void *
0x18004c545  lea     rdx, ?RealDisconnectThunk@CWcnWfdClientSession@@CAXPEAX00@Z; void (*)(void *, void *, void *)
0x18004c54c  call    ?CreateWorkItem@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_WORK@@@Z; CWcnScheduler::CreateWorkItem(void (*)(void *,void *,void *),void *,_TP_WORK * *)
0x18004c551  mov     ebx, eax
0x18004c553  test    eax, eax
0x18004c555  jns     short loc_18004C582
0x18004c557  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c55e  lea     rax, WPP_GLOBAL_Control
0x18004c565  cmp     rcx, rax
0x18004c568  jz      loc_18004C756
0x18004c56e  cmp     byte ptr [rcx+19h], 2
0x18004c572  jb      loc_18004C756
0x18004c578  mov     edx, 12h
0x18004c57d  jmp     loc_18004C426
0x18004c582  mov     rcx, [rbp+3Fh+var_98]
0x18004c586  mov     eax, [rcx]
0x18004c588  mov     dword ptr [rbp+3Fh+var_50+0Ch], eax
0x18004c58b  movzx   eax, word ptr [rcx+4]
0x18004c58f  mov     word ptr [rbp+3Fh+var_40], ax
0x18004c593  mov     edx, 1
0x18004c598  mov     dword ptr [rbp+3Fh+var_50+8], edx
0x18004c59b  mov     dword ptr [rbp+3Fh+var_50+4], edx
0x18004c59e  mov     dword ptr [rsp+110h+var_C0], edx
0x18004c5a2  mov     rax, [rbp+3Fh+var_58]
0x18004c5a6  mov     rcx, [rax]
0x18004c5a9  mov     qword ptr [rbp+3Fh+var_C0+8], rcx
0x18004c5ad  mov     qword ptr [rbp+3Fh+var_B0], r15
0x18004c5b1  lea     rax, [rbp+3Fh+var_50]
0x18004c5b5  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18004c5b9  mov     [rbp+3Fh+var_A0], rdx
0x18004c5bd  mov     rdx, [rdi+10h]
0x18004c5c1  add     rdx, 28h ; '('; struct CWcnIdentity *
0x18004c5c5  lea     r8, [rbp+3Fh+var_90]; struct CSbSafeBuffer *
0x18004c5c9  mov     rcx, [rdi+90h]; this
0x18004c5d0  call    ?GenerateAssociationRequestWpsIe@CWcnWfdClientTransport@@QEAAJPEAVCWcnIdentity@@PEAVCSbSafeBuffer@@@Z; CWcnWfdClientTransport::GenerateAssociationRequestWpsIe(CWcnIdentity *,CSbSafeBuffer *)
0x18004c5d5  mov     ebx, eax
0x18004c5d7  test    eax, eax
0x18004c5d9  jns     short loc_18004C606
0x18004c5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c5e2  lea     rax, WPP_GLOBAL_Control
0x18004c5e9  cmp     rcx, rax
0x18004c5ec  jz      loc_18004C756
0x18004c5f2  cmp     byte ptr [rcx+19h], 2
0x18004c5f6  jb      loc_18004C756
0x18004c5fc  mov     edx, 13h
0x18004c601  jmp     loc_18004C426
0x18004c606  lea     rdx, [rsp+110h+var_C8]; struct _WLAN_CONNECT_EXTENSION_PARAMETERS_V1 **
0x18004c60b  lea     rcx, [rbp+3Fh+var_90]; struct CSbSafeBuffer *
0x18004c60f  call    ?WcnWlanBuildIeListStructure@@YAJPEAVCSbSafeBuffer@@PEAPEAU_WLAN_CONNECT_EXTENSION_PARAMETERS_V1@@@Z; WcnWlanBuildIeListStructure(CSbSafeBuffer *,_WLAN_CONNECT_EXTENSION_PARAMETERS_V1 * *)
0x18004c614  mov     ebx, eax
0x18004c616  test    eax, eax
0x18004c618  jns     short loc_18004C645
0x18004c61a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c621  lea     rax, WPP_GLOBAL_Control
0x18004c628  cmp     rcx, rax
0x18004c62b  jz      loc_18004C756
0x18004c631  cmp     byte ptr [rcx+19h], 2
0x18004c635  jb      loc_18004C756
0x18004c63b  mov     edx, 14h
0x18004c640  jmp     loc_18004C426
0x18004c645  mov     [rsp+110h+pdwPrevNotifSource], r12; pdwPrevNotifSource
0x18004c64a  mov     [rsp+110h+pReserved], r12; pReserved
0x18004c64f  mov     [rsp+110h+pCallbackContext], rdi; pCallbackContext
0x18004c654  lea     r9, ?WlanNotificationCallbackThunk@CWcnWfdClientSession@@SAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18004c65b  xor     r8d, r8d; bIgnoreDuplicate
0x18004c65e  lea     edx, [r8+8]; dwNotifSource
0x18004c662  mov     rcx, [r14]; hClientHandle
0x18004c665  call    cs:__imp_WlanRegisterNotification
0x18004c66b  test    eax, eax
0x18004c66d  jz      short loc_18004C6AF
0x18004c66f  jg      short loc_18004C675
0x18004c671  mov     ebx, eax
0x18004c673  jmp     short loc_18004C67E
0x18004c675  movzx   ebx, ax
0x18004c678  or      ebx, 80070000h
0x18004c67e  or      ebx, 80000000h
0x18004c684  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c68b  lea     rdx, WPP_GLOBAL_Control
0x18004c692  cmp     rcx, rdx
0x18004c695  jz      loc_18004C756
0x18004c69b  cmp     byte ptr [rcx+19h], 2
0x18004c69f  jb      loc_18004C756
0x18004c6a5  mov     edx, 15h
0x18004c6aa  jmp     loc_18004C73F
0x18004c6af  cmp     [rsp+110h+var_CF], r12b
0x18004c6b4  jnz     short loc_18004C6BA
0x18004c6b6  or      dword ptr [rbp+3Fh+var_A0+4], 4
0x18004c6ba  mov     rdx, rdi; struct CWcnWfdClientSession *
0x18004c6bd  mov     rcx, [rdi+90h]; this
0x18004c6c4  call    ?NotifySessionCreated@CWcnWfdClientTransport@@QEAAJPEAVCWcnWfdClientSession@@@Z; CWcnWfdClientTransport::NotifySessionCreated(CWcnWfdClientSession *)
0x18004c6c9  mov     ebx, eax
0x18004c6cb  test    eax, eax
0x18004c6cd  jns     short loc_18004C6F2
0x18004c6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c6d6  lea     rax, WPP_GLOBAL_Control
0x18004c6dd  cmp     rcx, rax
0x18004c6e0  jz      short loc_18004C756
0x18004c6e2  cmp     byte ptr [rcx+19h], 2
0x18004c6e6  jb      short loc_18004C756
0x18004c6e8  mov     edx, 16h
0x18004c6ed  jmp     loc_18004C426
0x18004c6f2  mov     r9, [rsp+110h+var_C8]
0x18004c6f7  lea     r8, [rsp+110h+var_C0]
0x18004c6fc  mov     rdx, rsi
0x18004c6ff  mov     rcx, [r14]
0x18004c702  call    cs:__imp_WlanConnectEx
0x18004c708  test    eax, eax
0x18004c70a  jz      short loc_18004C756
0x18004c70c  jg      short loc_18004C712
  ... truncated ...
```
