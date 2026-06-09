# CWcnWfdGoTransport::ProcessWfdPeer(_WFD_WCN_CONFIG_PARAMS *,_WFD_DEVICE_DESCRIPTOR *)

- ea: `0x18004e048`
- end: `0x18004e5e7`
- name: `?ProcessWfdPeer@CWcnWfdGoTransport@@QEAAXPEAU_WFD_WCN_CONFIG_PARAMS@@PEAU_WFD_DEVICE_DESCRIPTOR@@@Z`
- size: `1439`
- prototype: `void __fastcall(CWcnWfdGoTransport *__hidden this, struct _WFD_WCN_CONFIG_PARAMS *, struct _WFD_DEVICE_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004da90`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000c58c`
- `0x18000c6e8`
- `0x18000ebe0`
- `0x18001a57c`
- `0x18001b548`
- `0x18001de78`
- `0x180044dd8`
- `0x18004d838`
- `0x18004e048`
- `0x180052da0`
- `0x180053004`
- `0x180056dcf`
- `0x180056de6`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e102`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e1b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e1b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWcnWfdGoTransport::ProcessWfdPeer(
        CWcnWfdGoTransport *this,
        struct _WFD_WCN_CONFIG_PARAMS *a2,
        struct _WFD_DEVICE_DESCRIPTOR *a3)
{
  char v5; // r12
  const char *Indent; // rax
  __int64 v7; // r10
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  int *v9; // rdi
  int v10; // ecx
  int v11; // eax
  int v12; // ebx
  CWcnPeer *v13; // r14
  unsigned int v14; // eax
  __int64 v15; // r10
  int v16; // eax
  _QWORD *v17; // r10
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r10
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rax
  struct IWcnTransportPeer *v25; // rdi
  char *v26; // rax
  int v27; // eax
  const char *v28; // rax
  __int64 v29; // r10
  _DWORD Buf1[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-C8h] BYREF
  CWcnPeer *v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-B0h]
  struct _WFD_DEVICE_DESCRIPTOR *v35; // [rsp+58h] [rbp-A8h]
  struct _GUID v36; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[32]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v38; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v39[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v40[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[40]; // [rsp+D8h] [rbp-28h] BYREF

  v35 = a3;
  v32 = 0;
  v38 = 0;
  v33 = 0;
  v31 = 0;
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v39);
  memset(Buf1, 0, 6);
  v5 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 25, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, Indent);
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)g_pWcnService + 7) + 192LL);
  lpCriticalSection = v8;
  EnterCriticalSection(v8);
  v9 = (int *)((char *)a2 + 6);
  if ( !memcmp_0(Buf1, (char *)a2 + 6, 6u) )
  {
    LOBYTE(v10) = 10;
  }
  else
  {
    v10 = *v9;
    Buf1[0] = *v9;
    LOWORD(Buf1[1]) = *((_WORD *)a2 + 5);
  }
  v38 = 0;
  LOBYTE(v38.Data1) = v10;
  *(unsigned int *)((char *)&v38.Data1 + 1) = *(_DWORD *)((char *)Buf1 + 1);
  HIBYTE(v38.Data2) = BYTE1(Buf1[1]);
  v36 = v38;
  v11 = CWcnPeerCache::GetOrCreatePeer((__int64)v8, &v38, &v32);
  v12 = v11;
  v13 = v32;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids,
        (unsigned int)v11);
    goto LABEL_11;
  }
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v40);
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v37);
  v16 = CSbSafeBuffer::CopyFromBuffer<unsigned char *>((__int64)v37, (__int64)a2, (__int64)a2 + 6);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_34;
    v18 = 33;
    goto LABEL_32;
  }
  v16 = CWcnAttribute::SetValueFromBlob((CWcnAttribute *)v40, WCN_TYPE_MAC_ADDRESS, (const struct CSbSafeBuffer *)v37);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_34;
    v18 = 34;
    goto LABEL_32;
  }
  v16 = CWcnIdentity::SetAttribute((CWcnPeer *)((char *)v13 + 136), (const struct CWcnAttribute *)v40);
  v12 = v16;
  if ( v16 >= 0 )
  {
LABEL_33:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_38;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 35;
LABEL_32:
    WPP_SF_d(v17[2], v18, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, (unsigned int)v16);
    goto LABEL_33;
  }
LABEL_34:
  if ( v17 != &WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)v17 + 25) >= 6u) )
  {
    v19 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v20 + 16), 36, (unsigned int)WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v19, v12);
  }
LABEL_38:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v37);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v41);
  if ( v12 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_11;
    v22 = 27;
    v23 = (unsigned int)v12;
    goto LABEL_42;
  }
  v24 = _RTDynamicCast_0(
          *((_QWORD *)v13 + *((unsigned int *)this + 2) + 7),
          0,
          &IWcnTransportPeer `RTTI Type Descriptor',
          &CWcnWfdGoPeer `RTTI Type Descriptor',
          0);
  v25 = (struct IWcnTransportPeer *)v24;
  if ( v24 )
  {
    *(_QWORD *)(v24 + 72) = this;
    if ( a2 )
    {
      *(_OWORD *)(v24 + 40) = *(_OWORD *)a2;
      *(_OWORD *)(v24 + 56) = *((_OWORD *)a2 + 1);
    }
    *(_BYTE *)(v24 + 8) = 1;
  }
  else
  {
    v26 = (char *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v25 = (struct IWcnTransportPeer *)v26;
    v32 = (CWcnPeer *)v26;
    if ( !v26 )
    {
      v12 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, "pNewGOPeer");
      goto LABEL_11;
    }
    v26[8] = 0;
    *(_QWORD *)v26 = &CWcnWfdGoPeer::`vftable';
    *((_QWORD *)v26 + 9) = 0;
    *(_OWORD *)(v26 + 40) = 0;
    *(_OWORD *)(v26 + 56) = 0;
    *((_QWORD *)v26 + 9) = this;
    if ( a2 )
    {
      *(_OWORD *)(v26 + 40) = *(_OWORD *)a2;
      *(_OWORD *)(v26 + 56) = *((_OWORD *)a2 + 1);
    }
    v26[8] = 1;
  }
  CWcnPeer::SetTransportData(v13, *((_DWORD *)this + 2), v25);
  if ( (unsigned __int8)GetWpsIe((char *)v35 + *((unsigned int *)v35 + 52), *((unsigned int *)v35 + 53), &v33, &v31) )
  {
    v27 = CSbSafeBuffer::CopyFromBuffer<unsigned char *>((__int64)v39, v33, v33 + v31);
    v12 = v27;
    if ( v27 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_11;
      v22 = 29;
      goto LABEL_59;
    }
    if ( (*(int (__fastcall **)(_QWORD, char *, CWcnPeer *, _BYTE *, _QWORD))(**((_QWORD **)v13 + 15) + 16LL))(
           *((_QWORD *)v13 + 15),
           (char *)this + 136,
           v13,
           v39,
           0) < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v28 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v29 + 16), 30, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v28);
      }
      if ( !*((_BYTE *)v13 + 233) )
      {
        *((_BYTE *)v13 + 233) = 1;
        CWcnIdentity::NotifyListenerInternal((char *)v13 + 136, 2);
      }
    }
  }
  v27 = CWcnWfdGoTransport::AddWfdGoPeerToLocalCache(this, &v36, v25);
  v12 = v27;
  if ( v27 >= 0 )
    goto LABEL_12;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = 31;
LABEL_59:
    v23 = (unsigned int)v27;
LABEL_42:
    WPP_SF_d(v21[2], v22, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v23);
  }
LABEL_11:
  v5 = 0;
LABEL_12:
  LeaveCriticalSection(lpCriticalSection);
  if ( v13 && !v5 )
    _InterlockedDecrement((volatile signed __int32 *)v13 + 66);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v14 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v15 + 16), 32, (unsigned int)WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v14, v12);
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v39);
}

```

## disassembly

```asm
0x18004e048  mov     [rsp-8+arg_18], rbx
0x18004e04d  push    rbp
0x18004e04e  push    rsi
0x18004e04f  push    rdi
0x18004e050  push    r12
0x18004e052  push    r13
0x18004e054  push    r14
0x18004e056  push    r15
0x18004e058  lea     rbp, [rsp-10h]
0x18004e05d  sub     rsp, 110h
0x18004e064  mov     rax, cs:__security_cookie
0x18004e06b  xor     rax, rsp
0x18004e06e  mov     [rbp+40h+var_40], rax
0x18004e072  mov     [rsp+140h+var_E8], r8
0x18004e077  mov     r15, rdx
0x18004e07a  mov     r13, rcx
0x18004e07d  xor     r14d, r14d
0x18004e080  mov     [rsp+140h+var_100], r14
0x18004e085  xorps   xmm0, xmm0
0x18004e088  movups  [rbp+40h+var_B0], xmm0
0x18004e08c  mov     [rsp+140h+var_F8], r14
0x18004e091  mov     [rsp+140h+var_108], r14d
0x18004e096  lea     rcx, [rbp+40h+var_A0]; this
0x18004e09a  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004e09f  nop
0x18004e0a0  xor     eax, eax
0x18004e0a2  mov     [rsp+140h+Buf1], eax
0x18004e0a6  mov     [rsp+140h+var_10C], ax
0x18004e0ab  lea     rsi, WPP_GLOBAL_Control
0x18004e0b2  lea     r12d, [r14+1]
0x18004e0b6  mov     r10, cs:WPP_GLOBAL_Control
0x18004e0bd  cmp     r10, rsi
0x18004e0c0  jz      short loc_18004E0E8
0x18004e0c2  cmp     byte ptr [r10+19h], 6
0x18004e0c7  jb      short loc_18004E0E8
0x18004e0c9  mov     ecx, r12d; int
0x18004e0cc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004e0d1  lea     edx, [r14+19h]
0x18004e0d5  mov     r9, rax
0x18004e0d8  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e0df  mov     rcx, [r10+10h]
0x18004e0e3  call    WPP_SF_s
0x18004e0e8  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18004e0ef  mov     rbx, [rax+38h]
0x18004e0f3  add     rbx, 0C0h
0x18004e0fa  mov     [rsp+140h+lpCriticalSection], rbx
0x18004e0ff  mov     rcx, rbx; lpCriticalSection
0x18004e102  call    cs:__imp_EnterCriticalSection
0x18004e108  lea     rdi, [r15+6]
0x18004e10c  mov     r8d, 6; Size
0x18004e112  mov     rdx, rdi; Buf2
0x18004e115  lea     rcx, [rsp+140h+Buf1]; Buf1
0x18004e11a  call    memcmp_0
0x18004e11f  test    eax, eax
0x18004e121  jnz     short loc_18004E127
0x18004e123  mov     cl, 0Ah
0x18004e125  jmp     short loc_18004E136
0x18004e127  mov     ecx, [rdi]
0x18004e129  mov     [rsp+140h+Buf1], ecx
0x18004e12d  movzx   eax, word ptr [rdi+4]
0x18004e131  mov     [rsp+140h+var_10C], ax
0x18004e136  xorps   xmm0, xmm0
0x18004e139  movups  [rbp+40h+var_B0], xmm0
0x18004e13d  mov     byte ptr [rbp+40h+var_B0], cl
0x18004e140  mov     eax, [rsp+140h+Buf1+1]
0x18004e144  mov     dword ptr [rbp+40h+var_B0+1], eax
0x18004e147  mov     al, byte ptr [rsp+140h+var_10C+1]
0x18004e14b  mov     byte ptr [rbp+40h+var_B0+5], al
0x18004e14e  movaps  xmm0, [rbp+40h+var_B0]
0x18004e152  movdqa  xmmword ptr [rsp+140h+var_E0.Data1], xmm0
0x18004e158  lea     r8, [rsp+140h+var_100]
0x18004e15d  lea     rdx, [rbp+40h+var_B0]
0x18004e161  mov     rcx, rbx
0x18004e164  call    ?GetOrCreatePeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z; CWcnPeerCache::GetOrCreatePeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)
0x18004e169  mov     ebx, eax
0x18004e16b  mov     r14, [rsp+140h+var_100]
0x18004e170  test    eax, eax
0x18004e172  jns     loc_18004E238
0x18004e178  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e17f  cmp     rcx, rsi
0x18004e182  jz      short loc_18004E1A5
0x18004e184  mov     esi, 2
0x18004e189  cmp     [rcx+19h], sil
0x18004e18d  jb      short loc_18004E1A5
0x18004e18f  lea     edx, [rsi+18h]
0x18004e192  mov     r9d, eax
0x18004e195  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e19c  mov     rcx, [rcx+10h]
0x18004e1a0  call    WPP_SF_d
0x18004e1a5  lea     r15, WPP_GLOBAL_Control
0x18004e1ac  xor     r12b, r12b
0x18004e1af  mov     rcx, [rsp+140h+lpCriticalSection]; lpCriticalSection
0x18004e1b4  call    cs:__imp_LeaveCriticalSection
0x18004e1ba  test    r14, r14
0x18004e1bd  jz      short loc_18004E1CC
0x18004e1bf  test    r12b, r12b
0x18004e1c2  jnz     short loc_18004E1CC
0x18004e1c4  lock dec dword ptr [r14+108h]
0x18004e1cc  mov     r10, cs:WPP_GLOBAL_Control
0x18004e1d3  cmp     r10, r15
0x18004e1d6  jz      short loc_18004E208
0x18004e1d8  test    ebx, ebx
0x18004e1da  js      short loc_18004E1E3
0x18004e1dc  cmp     byte ptr [r10+19h], 6
0x18004e1e1  jb      short loc_18004E208
0x18004e1e3  or      ecx, 0FFFFFFFFh; int
0x18004e1e6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004e1eb  mov     edx, 20h ; ' '
0x18004e1f0  mov     dword ptr [rsp+140h+var_120], ebx
0x18004e1f4  mov     r9, rax
0x18004e1f7  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e1fe  mov     rcx, [r10+10h]
0x18004e202  call    WPP_SF_sd
0x18004e207  nop
0x18004e208  lea     rcx, [rbp+40h+var_A0]; this
0x18004e20c  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004e211  mov     rcx, [rbp+40h+var_40]
0x18004e215  xor     rcx, rsp; StackCookie
0x18004e218  call    __security_check_cookie
0x18004e21d  mov     rbx, [rsp+140h+arg_18]
0x18004e225  add     rsp, 110h
0x18004e22c  pop     r15
0x18004e22e  pop     r14
0x18004e230  pop     r13
0x18004e232  pop     r12
0x18004e234  pop     rdi
0x18004e235  pop     rsi
0x18004e236  pop     rbp
0x18004e237  retn
0x18004e238  lea     rcx, [rbp+40h+var_80]; this
0x18004e23c  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18004e241  nop
0x18004e242  lea     rcx, [rsp+140h+var_D0]; this
0x18004e247  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004e24c  nop
0x18004e24d  mov     r8, rdi
0x18004e250  mov     rdx, r15
0x18004e253  lea     rcx, [rsp+140h+var_D0]
0x18004e258  call    ??$CopyFromBuffer@PEAE@CSbSafeBuffer@@QEAAJPEAE0@Z; CSbSafeBuffer::CopyFromBuffer<uchar *>(uchar *,uchar *)
0x18004e25d  mov     ebx, eax
0x18004e25f  mov     esi, 2
0x18004e264  test    eax, eax
0x18004e266  jns     short loc_18004E28E
0x18004e268  mov     r10, cs:WPP_GLOBAL_Control
0x18004e26f  lea     rdi, WPP_GLOBAL_Control
0x18004e276  cmp     r10, rdi
0x18004e279  jz      loc_18004E357
0x18004e27f  cmp     [r10+19h], sil
0x18004e283  jb      loc_18004E322
0x18004e289  lea     edx, [rsi+1Fh]
0x18004e28c  jmp     short loc_18004E2FF
0x18004e28e  lea     r8, [rsp+140h+var_D0]; struct CSbSafeBuffer *
0x18004e293  mov     edx, 1Bh; enum tagWCN_ATTRIBUTE_TYPE
0x18004e298  lea     rcx, [rbp+40h+var_80]; this
0x18004e29c  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x18004e2a1  mov     ebx, eax
0x18004e2a3  test    eax, eax
0x18004e2a5  jns     short loc_18004E2CB
0x18004e2a7  mov     r10, cs:WPP_GLOBAL_Control
0x18004e2ae  lea     rdi, WPP_GLOBAL_Control
0x18004e2b5  cmp     r10, rdi
0x18004e2b8  jz      loc_18004E357
0x18004e2be  cmp     [r10+19h], sil
0x18004e2c2  jb      short loc_18004E322
0x18004e2c4  mov     edx, 22h ; '"'
0x18004e2c9  jmp     short loc_18004E2FF
0x18004e2cb  lea     rcx, [r14+88h]; this
0x18004e2d2  lea     rdx, [rbp+40h+var_80]; struct CWcnAttribute *
0x18004e2d6  call    ?SetAttribute@CWcnIdentity@@QEAAJPEBVCWcnAttribute@@@Z; CWcnIdentity::SetAttribute(CWcnAttribute const *)
0x18004e2db  mov     ebx, eax
0x18004e2dd  test    eax, eax
0x18004e2df  jns     short loc_18004E314
0x18004e2e1  mov     r10, cs:WPP_GLOBAL_Control
0x18004e2e8  lea     rdi, WPP_GLOBAL_Control
0x18004e2ef  cmp     r10, rdi
0x18004e2f2  jz      short loc_18004E357
0x18004e2f4  cmp     [r10+19h], sil
0x18004e2f8  jb      short loc_18004E322
0x18004e2fa  mov     edx, 23h ; '#'
0x18004e2ff  mov     r9d, eax
0x18004e302  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e309  mov     rcx, [r10+10h]
0x18004e30d  call    WPP_SF_d
0x18004e312  jmp     short loc_18004E31B
0x18004e314  lea     rdi, WPP_GLOBAL_Control
0x18004e31b  mov     r10, cs:WPP_GLOBAL_Control
0x18004e322  cmp     r10, rdi
0x18004e325  jz      short loc_18004E357
0x18004e327  test    ebx, ebx
0x18004e329  js      short loc_18004E332
0x18004e32b  cmp     byte ptr [r10+19h], 6
0x18004e330  jb      short loc_18004E357
0x18004e332  or      ecx, 0FFFFFFFFh; int
0x18004e335  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004e33a  mov     edx, 24h ; '$'
0x18004e33f  mov     dword ptr [rsp+140h+var_120], ebx
0x18004e343  mov     r9, rax
0x18004e346  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e34d  mov     rcx, [r10+10h]
0x18004e351  call    WPP_SF_sd
0x18004e356  nop
0x18004e357  lea     rcx, [rsp+140h+var_D0]; this
0x18004e35c  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004e361  nop
0x18004e362  lea     rcx, [rbp+40h+var_68]; this
0x18004e366  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004e36b  test    ebx, ebx
0x18004e36d  jns     short loc_18004E3AD
0x18004e36f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e376  lea     r15, WPP_GLOBAL_Control
0x18004e37d  cmp     rcx, r15
0x18004e380  jz      loc_18004E1AC
0x18004e386  cmp     [rcx+19h], sil
0x18004e38a  jb      loc_18004E1AC
0x18004e390  mov     edx, 1Bh
0x18004e395  mov     r9d, ebx
0x18004e398  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e39f  mov     rcx, [rcx+10h]
0x18004e3a3  call    WPP_SF_d
0x18004e3a8  jmp     loc_18004E1AC
0x18004e3ad  mov     ecx, [r13+8]
0x18004e3b1  xor     ebx, ebx
0x18004e3b3  mov     dword ptr [rsp+140h+var_120], ebx
0x18004e3b7  lea     r9, ??_R0?AVCWcnWfdGoPeer@@@8; CWcnWfdGoPeer `RTTI Type Descriptor'
0x18004e3be  lea     r8, ??_R0?AVIWcnTransportPeer@@@8; IWcnTransportPeer `RTTI Type Descriptor'
0x18004e3c5  xor     edx, edx
0x18004e3c7  mov     rcx, [r14+rcx*8+38h]
0x18004e3cc  call    __RTDynamicCast_0
0x18004e3d1  mov     rdi, rax
0x18004e3d4  test    rax, rax
0x18004e3d7  jnz     loc_18004E481
0x18004e3dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004e3e4  lea     ecx, [rbx+50h]; unsigned __int64
0x18004e3e7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004e3ec  mov     rdi, rax
0x18004e3ef  mov     [rsp+140h+var_100], rax
0x18004e3f4  test    rax, rax
0x18004e3f7  jz      short loc_18004E43A
0x18004e3f9  mov     [rax+8], bl
0x18004e3fc  lea     rax, ??_7CWcnWfdGoPeer@@6B@; const CWcnWfdGoPeer::`vftable'
0x18004e403  mov     [rdi], rax
0x18004e406  mov     [rdi+48h], rbx
0x18004e40a  xorps   xmm0, xmm0
0x18004e40d  movups  xmmword ptr [rdi+28h], xmm0
0x18004e411  movups  xmmword ptr [rdi+38h], xmm0
0x18004e415  test    rdi, rdi
0x18004e418  jz      short loc_18004E43A
0x18004e41a  mov     [rdi+48h], r13
0x18004e41e  test    r15, r15
0x18004e421  jz      short loc_18004E434
0x18004e423  movups  xmm0, xmmword ptr [r15]
0x18004e427  movups  xmmword ptr [rdi+28h], xmm0
0x18004e42b  movups  xmm1, xmmword ptr [r15+10h]
0x18004e430  movups  xmmword ptr [rdi+38h], xmm1
0x18004e434  mov     [rdi+8], r12b
0x18004e438  jmp     short loc_18004E49F
0x18004e43a  mov     ebx, 8007000Eh
0x18004e43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e446  lea     r15, WPP_GLOBAL_Control
0x18004e44d  cmp     rcx, r15
0x18004e450  jz      loc_18004E1AC
0x18004e456  cmp     [rcx+19h], sil
0x18004e45a  jb      loc_18004E1AC
0x18004e460  mov     edx, 1Ch
0x18004e465  lea     r9, aPnewgopeer; "pNewGOPeer"
0x18004e46c  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004e473  mov     rcx, [rcx+10h]
0x18004e477  call    WPP_SF_s
0x18004e47c  jmp     loc_18004E1AC
0x18004e481  mov     [rax+48h], r13
0x18004e485  test    r15, r15
0x18004e488  jz      short loc_18004E49B
0x18004e48a  movups  xmm0, xmmword ptr [r15]
0x18004e48e  movups  xmmword ptr [rax+28h], xmm0
0x18004e492  movups  xmm1, xmmword ptr [r15+10h]
0x18004e497  movups  xmmword ptr [rax+38h], xmm1
0x18004e49b  mov     [rax+8], r12b
0x18004e49f  mov     rcx, r14; this
0x18004e4a2  mov     r8, rdi; struct IWcnTransportPeer *
0x18004e4a5  mov     edx, [r13+8]; unsigned int
0x18004e4a9  call    ?SetTransportData@CWcnPeer@@QEAAXKPEAVIWcnTransportPeer@@@Z; CWcnPeer::SetTransportData(ulong,IWcnTransportPeer *)
0x18004e4ae  mov     rax, [rsp+140h+var_E8]
0x18004e4b3  mov     ecx, [rax+0D0h]
0x18004e4b9  add     rcx, rax
0x18004e4bc  lea     r9, [rsp+140h+var_108]
0x18004e4c1  lea     r8, [rsp+140h+var_F8]
0x18004e4c6  mov     edx, [rax+0D4h]
0x18004e4cc  call    GetWpsIe
0x18004e4d1  test    al, al
0x18004e4d3  jz      loc_18004E5A1
0x18004e4d9  mov     r8d, [rsp+140h+var_108]
0x18004e4de  mov     rdx, [rsp+140h+var_F8]
0x18004e4e3  add     r8, rdx
0x18004e4e6  lea     rcx, [rbp+40h+var_A0]
0x18004e4ea  call    ??$CopyFromBuffer@PEAE@CSbSafeBuffer@@QEAAJPEAE0@Z; CSbSafeBuffer::CopyFromBuffer<uchar *>(uchar *,uchar *)
0x18004e4ef  mov     ebx, eax
0x18004e4f1  test    eax, eax
0x18004e4f3  jns     short loc_18004E523
0x18004e4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e4fc  lea     r15, WPP_GLOBAL_Control
  ... truncated ...
```
