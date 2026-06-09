# CWcnUProxyTransport::NotifyMessageArrival(_GUID const *,uchar *,tagWcnUPnP_WLANEventType,CSbMessageBuffer const *,ulong)

- ea: `0x18003e180`
- end: `0x18003e68b`
- name: `?NotifyMessageArrival@CWcnUProxyTransport@@QEAAJPEBU_GUID@@PEAEW4tagWcnUPnP_WLANEventType@@PEBVCSbMessageBuffer@@K@Z`
- size: `1291`
- prototype: `__int64 __fastcall(__int64, void *, char *, int, struct CSbMessageBuffer *, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800444a0`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a6d4`
- `0x18000c6e8`
- `0x18000ebe0`
- `0x18001a57c`
- `0x18001b548`
- `0x18001de78`
- `0x18003e180`
- `0x180040770`
- `0x1800408dc`
- `0x180040c98`
- `0x180053004`
- `0x180056dcf`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `msvcrt!sscanf_s` at `0x18003e364`
- `msvcrt!sscanf_s` at `0x18003e364`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003e53c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003e53c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e2cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e2cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e621`

## string_xrefs

- `0x18003e26c`: `pIncomingMessage`

## pseudocode

```c
__int64 __fastcall CWcnUProxyTransport::NotifyMessageArrival(
        __int64 a1,
        void *a2,
        char *a3,
        int a4,
        struct CSbMessageBuffer *a5,
        unsigned int a6)
{
  struct CWcnUProxyTransport *v9; // r13
  _BYTE *v10; // r10
  const char *Indent; // rax
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // rdx
  const char *v15; // r9
  CWcnUProxyPeer *v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // r10
  int v20; // r11d
  int v21; // eax
  int v22; // ebx
  volatile signed __int32 *v23; // rsi
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  const char *v26; // rax
  __int64 v27; // rdx
  const char *v28; // r9
  __int64 v29; // r10
  __int64 v30; // rcx
  __int64 i; // rcx
  int v32; // eax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  char *v35; // rax
  unsigned int v36; // eax
  __int64 v37; // r10
  CWcnPeer *v38; // [rsp+40h] [rbp-89h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-81h]
  _BYTE v40[32]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v41[24]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v42[40]; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int8 v43[24]; // [rsp+B0h] [rbp-19h] BYREF
  unsigned __int8 v44[8]; // [rsp+C8h] [rbp-1h] BYREF

  v9 = g_pUProxyTransport;
  v38 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 27, v13, Indent);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 28;
    v15 = "pPeerGuid";
LABEL_16:
    WPP_SF_s(*((_QWORD *)v10 + 2), v14, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids, v15);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 29;
    v15 = "MacString";
    goto LABEL_16;
  }
  if ( !a5 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 30;
    v15 = "pIncomingMessage";
    goto LABEL_16;
  }
  v17 = 0;
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 5u )
  {
    v18 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 31, v20, v18, a4);
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(*((_QWORD *)g_pWcnService + 7) + 192LL);
  EnterCriticalSection(lpCriticalSection);
  v21 = CWcnPeerCache::GetOrCreatePeer((__int64)lpCriticalSection, a2, &v38);
  v22 = v21;
  v23 = (volatile signed __int32 *)v38;
  if ( v21 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_62;
    v25 = 32;
    goto LABEL_25;
  }
  if ( sscanf_s(a3, "%02x:%02x:%02x:%02x:%02x:%02x", v43, &v43[4], &v43[8], &v43[12], &v43[16], &v43[20]) != 6 )
  {
    v22 = -2147024809;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_62;
    v26 = GetIndent(0);
    v27 = 33;
    v28 = v26;
    v30 = *(_QWORD *)(v29 + 16);
    goto LABEL_30;
  }
  for ( i = 0; i != 6; ++i )
    v44[i] = v43[4 * i];
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v41);
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v40);
  v32 = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v40, v44, 6u);
  v22 = v32;
  if ( v32 < 0 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    v34 = 34;
LABEL_37:
    WPP_SF_d(v33[2], v34, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids, (unsigned int)v32);
LABEL_38:
    CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v40);
    CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v42);
    goto LABEL_62;
  }
  v32 = CWcnAttribute::SetValueFromBlob(
          (CWcnAttribute *)v41,
          WCN_TYPE_DOT11_MAC_ADDRESS,
          (const struct CSbSafeBuffer *)v40);
  v22 = v32;
  if ( v32 < 0 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    v34 = 35;
    goto LABEL_37;
  }
  v32 = CWcnIdentity::SetAttribute((CWcnIdentity *)(v23 + 34), (const struct CWcnAttribute *)v41);
  v22 = v32;
  if ( v32 < 0 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    v34 = 36;
    goto LABEL_37;
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v40);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v42);
  v17 = (CWcnUProxyPeer *)_RTDynamicCast_0(
                            *(_QWORD *)&v23[2 * *((unsigned int *)v9 + 2) + 14],
                            0,
                            &IWcnTransportPeer `RTTI Type Descriptor',
                            &CWcnUProxyPeer `RTTI Type Descriptor',
                            0);
  if ( v17 )
  {
LABEL_54:
    if ( a4 == 2 )
    {
      CWcnUProxyPeer::NotifyMessageArrival(v17, a5);
    }
    else if ( a4 == 1 )
    {
      CWcnUProxyPeer::NotifyProbeRequestArrival(v17, a5);
    }
    v17 = 0;
    goto LABEL_62;
  }
  v35 = (char *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v17 = (CWcnUProxyPeer *)v35;
  v38 = (CWcnPeer *)v35;
  if ( !v35 )
  {
    v17 = 0;
    v22 = -2147024882;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_62;
    v27 = 37;
    v28 = "pUProxyPeer";
    v30 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_30:
    WPP_SF_s(v30, v27, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids, v28);
    goto LABEL_62;
  }
  v35[8] = 0;
  *(_QWORD *)v35 = &CWcnUProxyPeer::`vftable';
  *((_QWORD *)v35 + 5) = 0;
  *((_WORD *)v35 + 46) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v35 + 48));
  v21 = CWcnUProxyPeer::Init(v17, (unsigned __int8 *)a3, a6);
  v22 = v21;
  if ( v21 >= 0 )
  {
    CWcnPeer::SetTransportData((CWcnPeer *)v23, *((_DWORD *)v9 + 2), v17);
    *((_BYTE *)v17 + 8) = 1;
    goto LABEL_54;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_62;
  v25 = 38;
LABEL_25:
  WPP_SF_d(v24[2], v25, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids, (unsigned int)v21);
LABEL_62:
  if ( v23 )
    _InterlockedDecrement(v23 + 66);
  if ( v17 )
    (**(void (__fastcall ***)(CWcnUProxyPeer *, __int64))v17)(v17, 1);
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v22 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v36 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v37 + 16), 39, (unsigned int)WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids, v36, v22);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18003e180  mov     [rsp-8+arg_0], rbx
0x18003e185  push    rbp
0x18003e186  push    rsi
0x18003e187  push    rdi
0x18003e188  push    r12
0x18003e18a  push    r13
0x18003e18c  push    r14
0x18003e18e  push    r15
0x18003e190  lea     rbp, [rsp-17h]
0x18003e195  sub     rsp, 0E0h
0x18003e19c  mov     rax, cs:__security_cookie
0x18003e1a3  xor     rax, rsp
0x18003e1a6  mov     [rbp+47h+var_40], rax
0x18003e1aa  mov     r15d, r9d
0x18003e1ad  mov     r12, r8
0x18003e1b0  mov     rbx, rdx
0x18003e1b3  mov     r14, [rbp+47h+arg_20]
0x18003e1b7  mov     r13, cs:?g_pUProxyTransport@@3PEAVCWcnUProxyTransport@@EA; CWcnUProxyTransport * g_pUProxyTransport
0x18003e1be  mov     [rsp+110h+var_D0], 0
0x18003e1c7  lea     rax, WPP_GLOBAL_Control
0x18003e1ce  lea     r11, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids
0x18003e1d5  mov     r10, cs:WPP_GLOBAL_Control
0x18003e1dc  cmp     r10, rax
0x18003e1df  jz      short loc_18003E21B
0x18003e1e1  cmp     byte ptr [r10+19h], 6
0x18003e1e6  jb      short loc_18003E21B
0x18003e1e8  mov     ecx, 1; int
0x18003e1ed  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003e1f2  mov     edx, 1Bh
0x18003e1f7  mov     r9, rax
0x18003e1fa  mov     r8, r11
0x18003e1fd  mov     rcx, [r10+10h]
0x18003e201  call    WPP_SF_s
0x18003e206  mov     r10, cs:WPP_GLOBAL_Control
0x18003e20d  lea     rax, WPP_GLOBAL_Control
0x18003e214  lea     r11, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids
0x18003e21b  test    rbx, rbx
0x18003e21e  jnz     short loc_18003E238
0x18003e220  cmp     r10, rax
0x18003e223  jz      short loc_18003E27F
0x18003e225  cmp     byte ptr [r10+19h], 2
0x18003e22a  jb      short loc_18003E27F
0x18003e22c  lea     edx, [rbx+1Ch]
0x18003e22f  lea     r9, aPpeerguid; "pPeerGuid"
0x18003e236  jmp     short loc_18003E273
0x18003e238  test    r12, r12
0x18003e23b  jnz     short loc_18003E257
0x18003e23d  cmp     r10, rax
0x18003e240  jz      short loc_18003E27F
0x18003e242  cmp     byte ptr [r10+19h], 2
0x18003e247  jb      short loc_18003E27F
0x18003e249  lea     edx, [r12+1Dh]
0x18003e24e  lea     r9, aMacstring; "MacString"
0x18003e255  jmp     short loc_18003E273
0x18003e257  test    r14, r14
0x18003e25a  jnz     short loc_18003E289
0x18003e25c  cmp     r10, rax
0x18003e25f  jz      short loc_18003E27F
0x18003e261  cmp     byte ptr [r10+19h], 2
0x18003e266  jb      short loc_18003E27F
0x18003e268  lea     edx, [r14+1Eh]
0x18003e26c  lea     r9, aPincomingmessa; "pIncomingMessage"
0x18003e273  mov     r8, r11
0x18003e276  mov     rcx, [r10+10h]
0x18003e27a  call    WPP_SF_s
0x18003e27f  mov     eax, 80004003h
0x18003e284  jmp     loc_18003E664
0x18003e289  xor     edi, edi
0x18003e28b  cmp     r10, rax
0x18003e28e  jz      short loc_18003E2B5
0x18003e290  cmp     byte ptr [r10+19h], 5
0x18003e295  jb      short loc_18003E2B5
0x18003e297  xor     ecx, ecx; int
0x18003e299  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003e29e  lea     edx, [rdi+1Fh]
0x18003e2a1  mov     dword ptr [rsp+110h+var_F0], r15d
0x18003e2a6  mov     r9, rax
0x18003e2a9  mov     r8, r11
0x18003e2ac  mov     rcx, [r10+10h]
0x18003e2b0  call    WPP_SF_sd
0x18003e2b5  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18003e2bc  mov     rsi, [rax+38h]
0x18003e2c0  add     rsi, 0C0h
0x18003e2c7  mov     [rsp+110h+lpCriticalSection], rsi
0x18003e2cc  mov     rcx, rsi; lpCriticalSection
0x18003e2cf  call    cs:__imp_EnterCriticalSection
0x18003e2d5  lea     r8, [rsp+110h+var_D0]
0x18003e2da  mov     rdx, rbx
0x18003e2dd  mov     rcx, rsi
0x18003e2e0  call    ?GetOrCreatePeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z; CWcnPeerCache::GetOrCreatePeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)
0x18003e2e5  mov     ebx, eax
0x18003e2e7  mov     rsi, [rsp+110h+var_D0]
0x18003e2ec  test    eax, eax
0x18003e2ee  jns     short loc_18003E32E
0x18003e2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2f7  lea     r14, WPP_GLOBAL_Control
0x18003e2fe  cmp     rcx, r14
0x18003e301  jz      loc_18003E5F8
0x18003e307  cmp     byte ptr [rcx+19h], 2
0x18003e30b  jb      loc_18003E5F8
0x18003e311  mov     edx, 20h ; ' '
0x18003e316  mov     r9d, eax
0x18003e319  lea     r8, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids
0x18003e320  mov     rcx, [rcx+10h]
0x18003e324  call    WPP_SF_d
0x18003e329  jmp     loc_18003E5F8
0x18003e32e  lea     rax, [rbp+47h+var_4C]
0x18003e332  mov     [rsp+110h+var_D8], rax
0x18003e337  lea     rax, [rbp+47h+var_50]
0x18003e33b  mov     [rsp+110h+var_E0], rax
0x18003e340  lea     rax, [rbp+47h+var_54]
0x18003e344  mov     [rsp+110h+var_E8], rax
0x18003e349  lea     rax, [rbp+47h+var_58]
0x18003e34d  mov     [rsp+110h+var_F0], rax
0x18003e352  lea     r9, [rbp+47h+var_5C]
0x18003e356  lea     r8, [rbp+47h+var_60]
0x18003e35a  lea     rdx, a02x02x02x02x02; "%02x:%02x:%02x:%02x:%02x:%02x"
0x18003e361  mov     rcx, r12; Buffer
0x18003e364  call    cs:__imp_sscanf_s
0x18003e36a  cmp     eax, 6
0x18003e36d  jz      short loc_18003E3BA
0x18003e36f  mov     ebx, 80070057h
0x18003e374  mov     r10, cs:WPP_GLOBAL_Control
0x18003e37b  lea     r14, WPP_GLOBAL_Control
0x18003e382  cmp     r10, r14
0x18003e385  jz      loc_18003E5F8
0x18003e38b  cmp     byte ptr [r10+19h], 3
0x18003e390  jb      loc_18003E5F8
0x18003e396  xor     ecx, ecx; int
0x18003e398  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003e39d  mov     edx, 21h ; '!'
0x18003e3a2  mov     r9, rax
0x18003e3a5  mov     rcx, [r10+10h]
0x18003e3a9  lea     r8, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids
0x18003e3b0  call    WPP_SF_s
0x18003e3b5  jmp     loc_18003E5F8
0x18003e3ba  xor     ecx, ecx
0x18003e3bc  mov     al, [rbp+rcx*4+47h+var_60]
0x18003e3c0  mov     [rbp+rcx+47h+var_48], al
0x18003e3c4  inc     rcx
0x18003e3c7  cmp     rcx, 6
0x18003e3cb  jnz     short loc_18003E3BC
0x18003e3cd  lea     rcx, [rbp+47h+var_A0]; this
0x18003e3d1  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18003e3d6  nop
0x18003e3d7  lea     rcx, [rbp+47h+var_C0]; this
0x18003e3db  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18003e3e0  nop
0x18003e3e1  mov     r8d, 6; unsigned __int64
0x18003e3e7  lea     rdx, [rbp+47h+var_48]; unsigned __int8 *
0x18003e3eb  lea     rcx, [rbp+47h+var_C0]; this
0x18003e3ef  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x18003e3f4  mov     ebx, eax
0x18003e3f6  test    eax, eax
0x18003e3f8  jns     short loc_18003E444
0x18003e3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e401  lea     r14, WPP_GLOBAL_Control
0x18003e408  cmp     rcx, r14
0x18003e40b  jz      short loc_18003E42C
0x18003e40d  cmp     byte ptr [rcx+19h], 2
0x18003e411  jb      short loc_18003E42C
0x18003e413  mov     edx, 22h ; '"'
0x18003e418  mov     r9d, eax
0x18003e41b  lea     r8, WPP_c1644ed7f6fb3a028db320535ea4e979_Traceguids
0x18003e422  mov     rcx, [rcx+10h]
0x18003e426  call    WPP_SF_d
0x18003e42b  nop
0x18003e42c  lea     rcx, [rbp+47h+var_C0]; this
0x18003e430  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18003e435  nop
0x18003e436  lea     rcx, [rbp+47h+var_88]; this
0x18003e43a  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18003e43f  jmp     loc_18003E5F8
0x18003e444  lea     r8, [rbp+47h+var_C0]; struct CSbSafeBuffer *
0x18003e448  mov     edx, 5Ch ; '\'; enum tagWCN_ATTRIBUTE_TYPE
0x18003e44d  lea     rcx, [rbp+47h+var_A0]; this
0x18003e451  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x18003e456  mov     ebx, eax
0x18003e458  test    eax, eax
0x18003e45a  jns     short loc_18003E47C
0x18003e45c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e463  lea     r14, WPP_GLOBAL_Control
0x18003e46a  cmp     rcx, r14
0x18003e46d  jz      short loc_18003E42C
0x18003e46f  cmp     byte ptr [rcx+19h], 2
0x18003e473  jb      short loc_18003E42C
0x18003e475  mov     edx, 23h ; '#'
0x18003e47a  jmp     short loc_18003E418
0x18003e47c  lea     rcx, [rsi+88h]; this
0x18003e483  lea     rdx, [rbp+47h+var_A0]; struct CWcnAttribute *
0x18003e487  call    ?SetAttribute@CWcnIdentity@@QEAAJPEBVCWcnAttribute@@@Z; CWcnIdentity::SetAttribute(CWcnAttribute const *)
0x18003e48c  mov     ebx, eax
0x18003e48e  test    eax, eax
0x18003e490  jns     short loc_18003E4B5
0x18003e492  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e499  lea     r14, WPP_GLOBAL_Control
0x18003e4a0  cmp     rcx, r14
0x18003e4a3  jz      short loc_18003E42C
0x18003e4a5  cmp     byte ptr [rcx+19h], 2
0x18003e4a9  jb      short loc_18003E42C
0x18003e4ab  mov     edx, 24h ; '$'
0x18003e4b0  jmp     loc_18003E418
0x18003e4b5  lea     rcx, [rbp+47h+var_C0]; this
0x18003e4b9  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18003e4be  nop
0x18003e4bf  lea     rcx, [rbp+47h+var_88]; this
0x18003e4c3  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18003e4c8  mov     ecx, [r13+8]
0x18003e4cc  mov     dword ptr [rsp+110h+var_F0], 0
0x18003e4d4  lea     r9, ??_R0?AVCWcnUProxyPeer@@@8; CWcnUProxyPeer `RTTI Type Descriptor'
0x18003e4db  lea     r8, ??_R0?AVIWcnTransportPeer@@@8; IWcnTransportPeer `RTTI Type Descriptor'
0x18003e4e2  xor     edx, edx
0x18003e4e4  mov     rcx, [rsi+rcx*8+38h]
0x18003e4e9  call    __RTDynamicCast_0
0x18003e4ee  mov     rdi, rax
0x18003e4f1  test    rax, rax
0x18003e4f4  jnz     loc_18003E596
0x18003e4fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e501  mov     ecx, 80h; unsigned __int64
0x18003e506  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e50b  mov     rdi, rax
0x18003e50e  mov     [rsp+110h+var_D0], rax
0x18003e513  test    rax, rax
0x18003e516  jz      loc_18003E5A9
0x18003e51c  mov     byte ptr [rax+8], 0
0x18003e520  lea     rax, ??_7CWcnUProxyPeer@@6B@; const CWcnUProxyPeer::`vftable'
0x18003e527  mov     [rdi], rax
0x18003e52a  mov     qword ptr [rdi+28h], 0
0x18003e532  xor     eax, eax
0x18003e534  mov     [rdi+5Ch], ax
0x18003e538  lea     rcx, [rdi+30h]; lpCriticalSection
0x18003e53c  call    cs:__imp_InitializeCriticalSection
0x18003e542  test    rdi, rdi
0x18003e545  jz      short loc_18003E5AB
0x18003e547  mov     r8d, [rbp+47h+arg_28]; unsigned int
0x18003e54b  mov     rdx, r12; unsigned __int8 *
0x18003e54e  mov     rcx, rdi; this
0x18003e551  call    ?Init@CWcnUProxyPeer@@QEAAJPEAEK@Z; CWcnUProxyPeer::Init(uchar *,ulong)
0x18003e556  mov     ebx, eax
0x18003e558  test    eax, eax
0x18003e55a  jns     short loc_18003E583
0x18003e55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e563  lea     r14, WPP_GLOBAL_Control
0x18003e56a  cmp     rcx, r14
0x18003e56d  jz      loc_18003E5F8
0x18003e573  cmp     byte ptr [rcx+19h], 2
0x18003e577  jb      short loc_18003E5F8
0x18003e579  mov     edx, 26h ; '&'
0x18003e57e  jmp     loc_18003E316
0x18003e583  mov     r8, rdi; struct IWcnTransportPeer *
0x18003e586  mov     edx, [r13+8]; unsigned int
0x18003e58a  mov     rcx, rsi; this
0x18003e58d  call    ?SetTransportData@CWcnPeer@@QEAAXKPEAVIWcnTransportPeer@@@Z; CWcnPeer::SetTransportData(ulong,IWcnTransportPeer *)
0x18003e592  mov     byte ptr [rdi+8], 1
0x18003e596  cmp     r15d, 2
0x18003e59a  jnz     short loc_18003E5DE
0x18003e59c  mov     rdx, r14; struct CSbMessageBuffer *
0x18003e59f  mov     rcx, rdi; this
0x18003e5a2  call    ?NotifyMessageArrival@CWcnUProxyPeer@@QEAAXPEBVCSbMessageBuffer@@@Z; CWcnUProxyPeer::NotifyMessageArrival(CSbMessageBuffer const *)
0x18003e5a7  jmp     short loc_18003E5EF
0x18003e5a9  xor     edi, edi
0x18003e5ab  mov     ebx, 8007000Eh
0x18003e5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5b7  lea     r14, WPP_GLOBAL_Control
0x18003e5be  cmp     rcx, r14
0x18003e5c1  jz      short loc_18003E5F8
0x18003e5c3  cmp     byte ptr [rcx+19h], 2
0x18003e5c7  jb      short loc_18003E5F8
0x18003e5c9  mov     edx, 25h ; '%'
0x18003e5ce  lea     r9, aPuproxypeer; "pUProxyPeer"
0x18003e5d5  mov     rcx, [rcx+10h]
0x18003e5d9  jmp     loc_18003E3A9
0x18003e5de  cmp     r15d, 1
0x18003e5e2  jnz     short loc_18003E5EF
0x18003e5e4  mov     rdx, r14; struct CSbMessageBuffer *
0x18003e5e7  mov     rcx, rdi; this
0x18003e5ea  call    ?NotifyProbeRequestArrival@CWcnUProxyPeer@@QEAAXPEBVCSbMessageBuffer@@@Z; CWcnUProxyPeer::NotifyProbeRequestArrival(CSbMessageBuffer const *)
0x18003e5ef  xor     edi, edi
0x18003e5f1  lea     r14, WPP_GLOBAL_Control
0x18003e5f8  test    rsi, rsi
0x18003e5fb  jz      short loc_18003E604
0x18003e5fd  lock dec dword ptr [rsi+108h]
0x18003e604  test    rdi, rdi
0x18003e607  jz      short loc_18003E61C
0x18003e609  mov     rax, [rdi]
0x18003e60c  mov     edx, 1
0x18003e611  mov     rcx, rdi
0x18003e614  mov     rax, [rax]
0x18003e617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e61c  mov     rcx, [rsp+110h+lpCriticalSection]; lpCriticalSection
0x18003e621  call    cs:__imp_LeaveCriticalSection
0x18003e627  mov     r10, cs:WPP_GLOBAL_Control
0x18003e62e  cmp     r10, r14
0x18003e631  jz      short loc_18003E662
0x18003e633  test    ebx, ebx
0x18003e635  js      short loc_18003E63E
0x18003e637  cmp     byte ptr [r10+19h], 6
0x18003e63c  jb      short loc_18003E662
0x18003e63e  or      ecx, 0FFFFFFFFh; int
0x18003e641  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
  ... truncated ...
```
