# CWcnWfdGoTransport::TryOpenSinkSession(_GUID const *,CWcnMessageSinkSession *,CSbSafeBuffer const *,IWcnSinkConsumer * *)

- ea: `0x18004eb80`
- end: `0x18004ef6e`
- name: `?TryOpenSinkSession@CWcnWfdGoTransport@@UEAAJPEBU_GUID@@PEAVCWcnMessageSinkSession@@PEBVCSbSafeBuffer@@PEAPEAVIWcnSinkConsumer@@@Z`
- size: `1006`
- prototype: `int(CWcnWfdGoTransport *__hidden this, const struct _GUID *, struct CWcnMessageSinkSession *, const struct CSbSafeBuffer *, struct IWcnSinkConsumer **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000862c`
- `0x18000a808`
- `0x180017424`
- `0x18004dc44`
- `0x18004e7c8`
- `0x18004eb80`
- `0x18004f8f8`
- `0x180053004`
- `0x180056dcf`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004edac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004edac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ede9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ede9`

## pseudocode

```c
__int64 __fastcall CWcnWfdGoTransport::TryOpenSinkSession(
        CWcnWfdGoTransport *this,
        const struct _GUID *a2,
        struct CWcnMessageSinkSession *a3,
        const struct CSbSafeBuffer *a4,
        struct IWcnSinkConsumer **a5)
{
  __int64 v5; // rsi
  _BYTE *v10; // r10
  const char *Indent; // rax
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // rdx
  const char *v15; // r9
  _QWORD *v17; // rcx
  int WfdGoPeerFromLocalCache; // eax
  int v19; // ebx
  _QWORD *v20; // r10
  __int64 v21; // rdx
  __int64 v22; // r14
  __int64 v23; // rdi
  const char *v24; // rax
  __int64 v25; // r10
  unsigned int v26; // eax
  __int64 v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  char v30; // r11
  struct _GUID v31; // [rsp+30h] [rbp-30h] BYREF
  struct CWcnWfdGoPeer *v32; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int8 v33[8]; // [rsp+48h] [rbp-18h] BYREF
  int v34; // [rsp+50h] [rbp-10h]

  v5 = 0;
  v32 = 0;
  *(_QWORD *)v33 = 0;
  v34 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 44, v13, Indent);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 45;
    v15 = "pSinkSessionGuid";
LABEL_20:
    WPP_SF_s(*((_QWORD *)v10 + 2), v14, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v15);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 46;
    v15 = "pSinkSession";
    goto LABEL_20;
  }
  if ( !a4 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 47;
    v15 = "pTransportExtra";
    goto LABEL_20;
  }
  if ( !a5 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v14 = 48;
    v15 = "ppSinkConsumer";
    goto LABEL_20;
  }
  *a5 = 0;
  v17 = (_QWORD *)*((_QWORD *)a4 + 3);
  if ( !v17 || v17[1] - *v17 != 12 )
  {
    v19 = -2147024809;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_51;
      v28 = (unsigned int)GetIndent(0);
      WPP_SF_sPP(*(_QWORD *)(v29 + 16), 49, (unsigned int)WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v28, v30, 12);
      goto LABEL_34;
    }
    return (unsigned int)v19;
  }
  WfdGoPeerFromLocalCache = CSbSafeBuffer::CopyToBuffer(a4, v33, 0xCu);
  v19 = WfdGoPeerFromLocalCache;
  if ( WfdGoPeerFromLocalCache < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 50;
LABEL_33:
        WPP_SF_d(v20[2], v21, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, (unsigned int)WfdGoPeerFromLocalCache);
LABEL_34:
        v20 = WPP_GLOBAL_Control;
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    return (unsigned int)v19;
  }
  v31 = 0;
  v31.Data1 = *(_DWORD *)&v33[4];
  v31.Data2 = v34;
  if ( (unsigned int)CWcnWfdGoTransport::GetWfdGoPeerFromLocalCache(
                       (CWcnWfdGoTransport *)((char *)this - 16),
                       &v31,
                       &v32) != -2147023728
    || (v31 = 0,
        v31.Data1 = 10,
        v31.Data2 = 0,
        WfdGoPeerFromLocalCache = CWcnWfdGoTransport::GetWfdGoPeerFromLocalCache(
                                    (CWcnWfdGoTransport *)((char *)this - 16),
                                    &v31,
                                    &v32),
        v19 = WfdGoPeerFromLocalCache,
        WfdGoPeerFromLocalCache >= 0) )
  {
    v22 = *((_QWORD *)v32 + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 16));
    v23 = *(_QWORD *)(v22 + 112);
    if ( v23 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v23 + 1592));
      v5 = _RTDynamicCast_0(
             *(_QWORD *)(v23 + 200),
             0,
             &IWcnTransportSession `RTTI Type Descriptor',
             &CWcnWfdGoSession `RTTI Type Descriptor',
             0);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v22 + 16));
    if ( v5 )
    {
      v19 = CWcnWfdGoSession::SetConfigurationAndFinishConnect(
              (CWcnWfdGoSession *)v5,
              a3,
              (const struct tagWcnEapAuthConfiguration *)v33);
      if ( v19 >= 0 )
      {
        *a5 = (struct IWcnSinkConsumer *)(v5 + 32);
      }
      else
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_47;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids,
          (unsigned int)v19);
      }
    }
    else
    {
      v19 = -2147022646;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_47;
      v24 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v25 + 16), 52, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v24);
    }
    v20 = WPP_GLOBAL_Control;
LABEL_47:
    if ( v22 )
    {
      CWcnWfdGoTransport::RemoveWfdGoPeerFromLocalCache((CWcnWfdGoTransport *)((char *)this - 16), &v31);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v23 )
    {
      CWcnSession::Release((CWcnSession *)v23);
      v20 = WPP_GLOBAL_Control;
    }
    goto LABEL_51;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 51;
      goto LABEL_33;
    }
LABEL_51:
    if ( v20 != &WPP_GLOBAL_Control && (v19 < 0 || *((_BYTE *)v20 + 25) >= 6u) )
    {
      v26 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v27 + 16), 54, (unsigned int)WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v26, v19);
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18004eb80  mov     [rsp-38h+arg_8], rbx
0x18004eb85  push    rbp
0x18004eb86  push    rsi
0x18004eb87  push    rdi
0x18004eb88  push    r12
0x18004eb8a  push    r13
0x18004eb8c  push    r14
0x18004eb8e  push    r15
0x18004eb90  mov     rbp, rsp
0x18004eb93  sub     rsp, 60h
0x18004eb97  mov     rax, cs:__security_cookie
0x18004eb9e  xor     rax, rsp
0x18004eba1  mov     [rbp+var_8], rax
0x18004eba5  mov     r15, [rbp+arg_20]
0x18004eba9  xor     esi, esi
0x18004ebab  xor     eax, eax
0x18004ebad  mov     [rbp+var_20], rsi
0x18004ebb1  mov     qword ptr [rbp+var_18], rax
0x18004ebb5  mov     rbx, r9
0x18004ebb8  mov     [rbp+var_10], eax
0x18004ebbb  mov     r12, r8
0x18004ebbe  mov     rdi, rdx
0x18004ebc1  mov     r13, rcx
0x18004ebc4  mov     r10, cs:WPP_GLOBAL_Control
0x18004ebcb  lea     r14, WPP_GLOBAL_Control
0x18004ebd2  lea     r11, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ebd9  cmp     r10, r14
0x18004ebdc  jz      short loc_18004EC0D
0x18004ebde  cmp     byte ptr [r10+19h], 6
0x18004ebe3  jb      short loc_18004EC0D
0x18004ebe5  lea     ecx, [rsi+1]; int
0x18004ebe8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004ebed  mov     rcx, [r10+10h]
0x18004ebf1  lea     edx, [rsi+2Ch]
0x18004ebf4  mov     r9, rax
0x18004ebf7  mov     r8, r11
0x18004ebfa  call    WPP_SF_s
0x18004ebff  mov     r10, cs:WPP_GLOBAL_Control
0x18004ec06  lea     r11, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ec0d  test    rdi, rdi
0x18004ec10  jnz     short loc_18004EC2A
0x18004ec12  cmp     r10, r14
0x18004ec15  jz      short loc_18004EC8E
0x18004ec17  cmp     byte ptr [r10+19h], 2
0x18004ec1c  jb      short loc_18004EC8E
0x18004ec1e  lea     edx, [rdi+2Dh]
0x18004ec21  lea     r9, aPsinksessiongu; "pSinkSessionGuid"
0x18004ec28  jmp     short loc_18004EC82
0x18004ec2a  test    r12, r12
0x18004ec2d  jnz     short loc_18004EC49
0x18004ec2f  cmp     r10, r14
0x18004ec32  jz      short loc_18004EC8E
0x18004ec34  cmp     byte ptr [r10+19h], 2
0x18004ec39  jb      short loc_18004EC8E
0x18004ec3b  lea     edx, [r12+2Eh]
0x18004ec40  lea     r9, aPsinksession; "pSinkSession"
0x18004ec47  jmp     short loc_18004EC82
0x18004ec49  test    rbx, rbx
0x18004ec4c  jnz     short loc_18004EC66
0x18004ec4e  cmp     r10, r14
0x18004ec51  jz      short loc_18004EC8E
0x18004ec53  cmp     byte ptr [r10+19h], 2
0x18004ec58  jb      short loc_18004EC8E
0x18004ec5a  lea     edx, [rbx+2Fh]
0x18004ec5d  lea     r9, aPtransportextr; "pTransportExtra"
0x18004ec64  jmp     short loc_18004EC82
0x18004ec66  test    r15, r15
0x18004ec69  jnz     short loc_18004EC98
0x18004ec6b  cmp     r10, r14
0x18004ec6e  jz      short loc_18004EC8E
0x18004ec70  cmp     byte ptr [r10+19h], 2
0x18004ec75  jb      short loc_18004EC8E
0x18004ec77  lea     edx, [r15+30h]
0x18004ec7b  lea     r9, aPpsinkconsumer; "ppSinkConsumer"
0x18004ec82  mov     rcx, [r10+10h]
0x18004ec86  mov     r8, r11
0x18004ec89  call    WPP_SF_s
0x18004ec8e  mov     eax, 80004003h
0x18004ec93  jmp     loc_18004EEF3
0x18004ec98  mov     [r15], rsi
0x18004ec9b  mov     edi, 0Ch
0x18004eca0  mov     rcx, [rbx+18h]
0x18004eca4  test    rcx, rcx
0x18004eca7  jz      loc_18004EF17
0x18004ecad  mov     rax, [rcx+8]
0x18004ecb1  sub     rax, [rcx]
0x18004ecb4  cmp     rax, rdi
0x18004ecb7  jnz     loc_18004EF17
0x18004ecbd  mov     r8d, edi; unsigned __int64
0x18004ecc0  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x18004ecc4  mov     rcx, rbx; this
0x18004ecc7  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x18004eccc  mov     ebx, eax
0x18004ecce  test    eax, eax
0x18004ecd0  jns     short loc_18004ECF5
0x18004ecd2  mov     r10, cs:WPP_GLOBAL_Control
0x18004ecd9  cmp     r10, r14
0x18004ecdc  jz      loc_18004EEF1
0x18004ece2  cmp     byte ptr [r10+19h], 2
0x18004ece7  jb      loc_18004EEBD
0x18004eced  lea     edx, [rdi+26h]
0x18004ecf0  jmp     loc_18004ED81
0x18004ecf5  mov     al, [rbp+var_18+4]
0x18004ecf8  lea     r8, [rbp+var_20]; struct CWcnWfdGoPeer **
0x18004ecfc  xorps   xmm0, xmm0
0x18004ecff  lea     rdx, [rbp+var_30]; struct _GUID *
0x18004ed03  movups  xmmword ptr [rbp+var_30.Data1], xmm0
0x18004ed07  mov     byte ptr [rbp+var_30.Data1], al
0x18004ed0a  lea     rcx, [r13-10h]; this
0x18004ed0e  mov     al, [rbp+var_18+5]
0x18004ed11  mov     byte ptr [rbp+var_30.Data1+1], al
0x18004ed14  mov     al, [rbp+var_18+6]
0x18004ed17  mov     byte ptr [rbp+var_30.Data1+2], al
0x18004ed1a  mov     al, [rbp+var_18+7]
0x18004ed1d  mov     byte ptr [rbp+var_30.Data1+3], al
0x18004ed20  mov     al, byte ptr [rbp+var_10]
0x18004ed23  mov     byte ptr [rbp+var_30.Data2], al
0x18004ed26  mov     al, byte ptr [rbp+var_10+1]
0x18004ed29  mov     byte ptr [rbp+var_30.Data2+1], al
0x18004ed2c  call    ?GetWfdGoPeerFromLocalCache@CWcnWfdGoTransport@@AEAAJPEBU_GUID@@PEAPEAVCWcnWfdGoPeer@@@Z; CWcnWfdGoTransport::GetWfdGoPeerFromLocalCache(_GUID const *,CWcnWfdGoPeer * *)
0x18004ed31  cmp     eax, 80070490h
0x18004ed36  jnz     short loc_18004EDA0
0x18004ed38  xorps   xmm0, xmm0
0x18004ed3b  lea     r8, [rbp+var_20]; struct CWcnWfdGoPeer **
0x18004ed3f  movups  xmmword ptr [rbp+var_30.Data1], xmm0
0x18004ed43  lea     rdx, [rbp+var_30]; struct _GUID *
0x18004ed47  mov     [rbp+var_30.Data1], 0Ah
0x18004ed4e  lea     rcx, [r13-10h]; this
0x18004ed52  mov     [rbp+var_30.Data2], si
0x18004ed56  call    ?GetWfdGoPeerFromLocalCache@CWcnWfdGoTransport@@AEAAJPEBU_GUID@@PEAPEAVCWcnWfdGoPeer@@@Z; CWcnWfdGoTransport::GetWfdGoPeerFromLocalCache(_GUID const *,CWcnWfdGoPeer * *)
0x18004ed5b  mov     ebx, eax
0x18004ed5d  test    eax, eax
0x18004ed5f  jns     short loc_18004EDA0
0x18004ed61  mov     r10, cs:WPP_GLOBAL_Control
0x18004ed68  cmp     r10, r14
0x18004ed6b  jz      loc_18004EEF1
0x18004ed71  cmp     byte ptr [r10+19h], 2
0x18004ed76  jb      loc_18004EEBD
0x18004ed7c  mov     edx, 33h ; '3'
0x18004ed81  mov     rcx, [r10+10h]
0x18004ed85  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ed8c  mov     r9d, eax
0x18004ed8f  call    WPP_SF_d
0x18004ed94  mov     r10, cs:WPP_GLOBAL_Control
0x18004ed9b  jmp     loc_18004EEBD
0x18004eda0  mov     rax, [rbp+var_20]
0x18004eda4  mov     r14, [rax+10h]
0x18004eda8  lea     rcx, [r14+10h]; lpCriticalSection
0x18004edac  call    cs:__imp_EnterCriticalSection
0x18004edb2  mov     rdi, [r14+70h]
0x18004edb6  test    rdi, rdi
0x18004edb9  jz      short loc_18004EDE5
0x18004edbb  lock inc dword ptr [rdi+638h]
0x18004edc2  mov     rcx, [rdi+0C8h]
0x18004edc9  lea     r9, ??_R0?AVCWcnWfdGoSession@@@8; CWcnWfdGoSession `RTTI Type Descriptor'
0x18004edd0  lea     r8, ??_R0?AVIWcnTransportSession@@@8; IWcnTransportSession `RTTI Type Descriptor'
0x18004edd7  mov     dword ptr [rsp+60h+var_40], esi
0x18004eddb  xor     edx, edx
0x18004eddd  call    __RTDynamicCast_0
0x18004ede2  mov     rsi, rax
0x18004ede5  lea     rcx, [r14+10h]; lpCriticalSection
0x18004ede9  call    cs:__imp_LeaveCriticalSection
0x18004edef  test    rsi, rsi
0x18004edf2  jnz     short loc_18004EE32
0x18004edf4  mov     ebx, 800708CAh
0x18004edf9  mov     r10, cs:WPP_GLOBAL_Control
0x18004ee00  lea     rax, WPP_GLOBAL_Control
0x18004ee07  cmp     r10, rax
0x18004ee0a  jz      short loc_18004EE89
0x18004ee0c  cmp     byte ptr [r10+19h], 2
0x18004ee11  jb      short loc_18004EE89
0x18004ee13  xor     ecx, ecx; int
0x18004ee15  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004ee1a  mov     rcx, [r10+10h]
0x18004ee1e  lea     edx, [rsi+34h]
0x18004ee21  mov     r9, rax
0x18004ee24  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ee2b  call    WPP_SF_s
0x18004ee30  jmp     short loc_18004EE82
0x18004ee32  lea     r8, [rbp+var_18]; struct tagWcnEapAuthConfiguration *
0x18004ee36  mov     rdx, r12; struct CWcnMessageSinkSession *
0x18004ee39  mov     rcx, rsi; this
0x18004ee3c  call    ?SetConfigurationAndFinishConnect@CWcnWfdGoSession@@QEAAJPEAVCWcnMessageSinkSession@@PEBUtagWcnEapAuthConfiguration@@@Z; CWcnWfdGoSession::SetConfigurationAndFinishConnect(CWcnMessageSinkSession *,tagWcnEapAuthConfiguration const *)
0x18004ee41  mov     ebx, eax
0x18004ee43  test    eax, eax
0x18004ee45  jns     short loc_18004EE7B
0x18004ee47  mov     r10, cs:WPP_GLOBAL_Control
0x18004ee4e  lea     rax, WPP_GLOBAL_Control
0x18004ee55  cmp     r10, rax
0x18004ee58  jz      short loc_18004EE89
0x18004ee5a  cmp     byte ptr [r10+19h], 2
0x18004ee5f  jb      short loc_18004EE89
0x18004ee61  mov     rcx, [r10+10h]
0x18004ee65  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ee6c  mov     edx, 35h ; '5'
0x18004ee71  mov     r9d, ebx
0x18004ee74  call    WPP_SF_d
0x18004ee79  jmp     short loc_18004EE82
0x18004ee7b  lea     rax, [rsi+20h]
0x18004ee7f  mov     [r15], rax
0x18004ee82  mov     r10, cs:WPP_GLOBAL_Control
0x18004ee89  test    r14, r14
0x18004ee8c  jz      short loc_18004EEA2
0x18004ee8e  lea     rcx, [r13-10h]; this
0x18004ee92  lea     rdx, [rbp+var_30]; struct _GUID *
0x18004ee96  call    ?RemoveWfdGoPeerFromLocalCache@CWcnWfdGoTransport@@AEAAJPEBU_GUID@@@Z; CWcnWfdGoTransport::RemoveWfdGoPeerFromLocalCache(_GUID const *)
0x18004ee9b  mov     r10, cs:WPP_GLOBAL_Control
0x18004eea2  test    rdi, rdi
0x18004eea5  jz      short loc_18004EEB6
0x18004eea7  mov     rcx, rdi; this
0x18004eeaa  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x18004eeaf  mov     r10, cs:WPP_GLOBAL_Control
0x18004eeb6  lea     r14, WPP_GLOBAL_Control
0x18004eebd  cmp     r10, r14
0x18004eec0  jz      short loc_18004EEF1
0x18004eec2  test    ebx, ebx
0x18004eec4  js      short loc_18004EECD
0x18004eec6  cmp     byte ptr [r10+19h], 6
0x18004eecb  jb      short loc_18004EEF1
0x18004eecd  or      ecx, 0FFFFFFFFh; int
0x18004eed0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004eed5  mov     rcx, [r10+10h]
0x18004eed9  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004eee0  mov     edx, 36h ; '6'
0x18004eee5  mov     dword ptr [rsp+60h+var_40], ebx
0x18004eee9  mov     r9, rax
0x18004eeec  call    WPP_SF_sd
0x18004eef1  mov     eax, ebx
0x18004eef3  mov     rcx, [rbp+var_8]
0x18004eef7  xor     rcx, rsp; StackCookie
0x18004eefa  call    __security_check_cookie
0x18004eeff  mov     rbx, [rsp+60h+arg_8]
0x18004ef07  add     rsp, 60h
0x18004ef0b  pop     r15
0x18004ef0d  pop     r14
0x18004ef0f  pop     r13
0x18004ef11  pop     r12
0x18004ef13  pop     rdi
0x18004ef14  pop     rsi
0x18004ef15  pop     rbp
0x18004ef16  retn
0x18004ef17  mov     ebx, 80070057h
0x18004ef1c  mov     r10, cs:WPP_GLOBAL_Control
0x18004ef23  cmp     r10, r14
0x18004ef26  jz      short loc_18004EEF1
0x18004ef28  cmp     byte ptr [r10+19h], 2
0x18004ef2d  jb      short loc_18004EEBD
0x18004ef2f  test    rcx, rcx
0x18004ef32  jz      short loc_18004EF3D
0x18004ef34  mov     r11, [rcx+8]
0x18004ef38  sub     r11, [rcx]
0x18004ef3b  jmp     short loc_18004EF40
0x18004ef3d  mov     r11, rsi
0x18004ef40  xor     ecx, ecx; int
0x18004ef42  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004ef47  mov     rcx, [r10+10h]
0x18004ef4b  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004ef52  mov     edx, 31h ; '1'
0x18004ef57  mov     [rsp+60h+var_38], rdi
0x18004ef5c  mov     r9, rax
0x18004ef5f  mov     [rsp+60h+var_40], r11
0x18004ef64  call    WPP_SF_sPP
0x18004ef69  jmp     loc_18004ED94
```
