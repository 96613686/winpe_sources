# CWcnWfdClientTransport::ProcessWfdClientPeer(_WFD_WCN_CONFIG_PARAMS *,_WFD_DEVICE_DESCRIPTOR *,_DOT11_SSID *,_GUID *)

- ea: `0x18004b644`
- end: `0x18004baf3`
- name: `?ProcessWfdClientPeer@CWcnWfdClientTransport@@AEAAXPEAU_WFD_WCN_CONFIG_PARAMS@@PEAU_WFD_DEVICE_DESCRIPTOR@@PEAU_DOT11_SSID@@PEAU_GUID@@@Z`
- size: `1199`
- prototype: `void __usercall(CWcnWfdClientTransport *__hidden this@<rcx>, struct _WFD_WCN_CONFIG_PARAMS *@<rdx>, struct _WFD_DEVICE_DESCRIPTOR *@<r8>, struct _DOT11_SSID *@<r9>, struct _GUID *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004ad30`

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
- `0x180044dd8`
- `0x18004b36c`
- `0x18004b644`
- `0x180052da0`
- `0x180053004`
- `0x180056dcf`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b6ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b6ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWcnWfdClientTransport::ProcessWfdClientPeer(
        CWcnWfdClientTransport *this,
        struct _WFD_WCN_CONFIG_PARAMS *a2,
        struct _WFD_DEVICE_DESCRIPTOR *a3,
        struct _DOT11_SSID *a4,
        struct _GUID *a5)
{
  const char *Indent; // rax
  __int64 v10; // r10
  int v11; // eax
  int v12; // ebx
  struct CWcnPeer *v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  _QWORD *v17; // r10
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r10
  __int64 v21; // r9
  struct CWcnWfdClientPeer *v22; // rdx
  struct CWcnWfdClientPeer *v23; // rax
  const char *v24; // rax
  __int64 v25; // r10
  unsigned int v26; // eax
  __int64 v27; // r10
  unsigned int v28; // [rsp+30h] [rbp-B1h] BYREF
  unsigned __int8 v29[6]; // [rsp+34h] [rbp-ADh] BYREF
  struct CWcnPeer *v30; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v31; // [rsp+48h] [rbp-99h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-91h]
  _BYTE v33[32]; // [rsp+58h] [rbp-89h] BYREF
  __int128 v34; // [rsp+78h] [rbp-69h] BYREF
  _BYTE v35[32]; // [rsp+88h] [rbp-59h] BYREF
  _BYTE v36[24]; // [rsp+A8h] [rbp-39h] BYREF
  _BYTE v37[40]; // [rsp+C0h] [rbp-21h] BYREF

  v30 = 0;
  v34 = 0;
  v31 = 0;
  v28 = 0;
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v35);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 20, WPP_de419415f993330b2119000481c3437b_Traceguids, Indent);
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(*((_QWORD *)g_pWcnService + 7) + 192LL);
  EnterCriticalSection(lpCriticalSection);
  *(_DWORD *)v29 = *(_DWORD *)((char *)a2 + 6);
  *(_WORD *)&v29[4] = *((_WORD *)a2 + 5);
  v34 = 0;
  LODWORD(v34) = *(_DWORD *)((char *)a2 + 6);
  WORD2(v34) = *((_WORD *)a2 + 5);
  v11 = CWcnPeerCache::GetOrCreatePeer((__int64)lpCriticalSection, &v34, &v30);
  v12 = v11;
  v13 = v30;
  if ( v11 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 21;
LABEL_41:
      v21 = (unsigned int)v11;
      goto LABEL_42;
    }
    goto LABEL_49;
  }
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v36);
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v33);
  v16 = CSbSafeBuffer::CopyFromBuffer<unsigned char *>((__int64)v33, (__int64)a2, (__int64)a2 + 6);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_22;
    v18 = 27;
    goto LABEL_20;
  }
  v16 = CWcnAttribute::SetValueFromBlob((CWcnAttribute *)v36, WCN_TYPE_MAC_ADDRESS, (const struct CSbSafeBuffer *)v33);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_22;
    v18 = 28;
    goto LABEL_20;
  }
  v16 = CWcnIdentity::SetAttribute((struct CWcnPeer *)((char *)v13 + 136), (const struct CWcnAttribute *)v36);
  v12 = v16;
  if ( v16 >= 0 )
  {
LABEL_21:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_26;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 29;
LABEL_20:
    WPP_SF_d(v17[2], v18, WPP_de419415f993330b2119000481c3437b_Traceguids, (unsigned int)v16);
    goto LABEL_21;
  }
LABEL_22:
  if ( v17 != &WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)v17 + 25) >= 6u) )
  {
    v19 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v20 + 16), 30, (unsigned int)WPP_de419415f993330b2119000481c3437b_Traceguids, v19, v12);
  }
LABEL_26:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v33);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v37);
  if ( v12 >= 0 )
  {
    v22 = (struct CWcnWfdClientPeer *)_RTDynamicCast_0(
                                        *((_QWORD *)v13 + *((unsigned int *)this + 2) + 7),
                                        0,
                                        &IWcnTransportPeer `RTTI Type Descriptor',
                                        &CWcnWfdClientPeer `RTTI Type Descriptor',
                                        0);
    if ( !v22 )
    {
      v23 = (struct CWcnWfdClientPeer *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v23;
      v30 = v23;
      if ( !v23 )
      {
        v12 = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_de419415f993330b2119000481c3437b_Traceguids,
            "pNewClientPeer");
        goto LABEL_49;
      }
      *((_BYTE *)v23 + 8) = 0;
      *(_QWORD *)v23 = &CWcnWfdClientPeer::`vftable';
      *((_BYTE *)v23 + 68) = 0;
      *((_DWORD *)v23 + 8) = 0;
    }
    CWcnWfdClientTransport::InitializeWfdClientPeer(this, v22, v13, a4, (unsigned __int8 (*)[6])v29, a5);
    if ( !(unsigned __int8)GetWpsIe((char *)a3 + *((unsigned int *)a3 + 52), *((unsigned int *)a3 + 53), &v31, &v28) )
      goto LABEL_49;
    v11 = CSbSafeBuffer::CopyFromBuffer<unsigned char *>((__int64)v35, v31, v31 + v28);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, char *, struct CWcnPeer *, _BYTE *, _QWORD))(**((_QWORD **)v13 + 15)
                                                                                          + 16LL))(
              *((_QWORD *)v13 + 15),
              (char *)this + 48,
              v13,
              v35,
              0);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v24 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v25 + 16), 25, WPP_de419415f993330b2119000481c3437b_Traceguids, v24);
        }
        v12 = 0;
        if ( !*((_BYTE *)v13 + 233) )
        {
          *((_BYTE *)v13 + 233) = 1;
          CWcnIdentity::NotifyListenerInternal((char *)v13 + 136, 2);
        }
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 24;
        goto LABEL_41;
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 22;
      v21 = (unsigned int)v12;
LABEL_42:
      WPP_SF_d(v14[2], v15, WPP_de419415f993330b2119000481c3437b_Traceguids, v21);
    }
  }
LABEL_49:
  LeaveCriticalSection(lpCriticalSection);
  if ( v13 )
    _InterlockedDecrement((volatile signed __int32 *)v13 + 66);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v26 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v27 + 16), 26, (unsigned int)WPP_de419415f993330b2119000481c3437b_Traceguids, v26, v12);
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v35);
}

```

## disassembly

```asm
0x18004b644  push    rbp
0x18004b646  push    rbx
0x18004b647  push    rsi
0x18004b648  push    rdi
0x18004b649  push    r12
0x18004b64b  push    r13
0x18004b64d  push    r14
0x18004b64f  push    r15
0x18004b651  lea     rbp, [rsp-17h]
0x18004b656  sub     rsp, 0F8h
0x18004b65d  mov     rax, cs:__security_cookie
0x18004b664  xor     rax, rsp
0x18004b667  mov     [rbp+4Fh+var_48], rax
0x18004b66b  mov     r12, r9
0x18004b66e  mov     r13, r8
0x18004b671  mov     r14, rdx
0x18004b674  mov     r15, rcx
0x18004b677  xor     eax, eax
0x18004b679  mov     [rsp+130h+var_F0], rax
0x18004b67e  xorps   xmm0, xmm0
0x18004b681  movups  [rbp+4Fh+var_B8], xmm0
0x18004b685  mov     [rsp+130h+var_E8], rax
0x18004b68a  mov     [rsp+130h+var_100], eax
0x18004b68e  lea     rcx, [rbp+4Fh+var_A8]; this
0x18004b692  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004b697  nop
0x18004b698  lea     rax, WPP_GLOBAL_Control
0x18004b69f  mov     r10, cs:WPP_GLOBAL_Control
0x18004b6a6  cmp     r10, rax
0x18004b6a9  jz      short loc_18004B6D4
0x18004b6ab  cmp     byte ptr [r10+19h], 6
0x18004b6b0  jb      short loc_18004B6D4
0x18004b6b2  mov     ecx, 1; int
0x18004b6b7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004b6bc  mov     edx, 14h
0x18004b6c1  mov     r9, rax
0x18004b6c4  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004b6cb  mov     rcx, [r10+10h]
0x18004b6cf  call    WPP_SF_s
0x18004b6d4  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18004b6db  mov     rbx, [rax+38h]
0x18004b6df  add     rbx, 0C0h
0x18004b6e6  mov     [rsp+130h+lpCriticalSection], rbx
0x18004b6eb  mov     rcx, rbx; lpCriticalSection
0x18004b6ee  call    cs:__imp_EnterCriticalSection
0x18004b6f4  lea     rsi, [r14+6]
0x18004b6f8  mov     eax, [rsi]
0x18004b6fa  mov     dword ptr [rsp+130h+var_FC], eax
0x18004b6fe  movzx   eax, word ptr [rsi+4]
0x18004b702  mov     word ptr [rsp+130h+var_FC+4], ax
0x18004b707  xorps   xmm0, xmm0
0x18004b70a  movups  [rbp+4Fh+var_B8], xmm0
0x18004b70e  mov     eax, [rsi]
0x18004b710  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18004b713  movzx   eax, word ptr [rsi+4]
0x18004b717  mov     word ptr [rbp+4Fh+var_B8+4], ax
0x18004b71b  lea     r8, [rsp+130h+var_F0]
0x18004b720  lea     rdx, [rbp+4Fh+var_B8]
0x18004b724  mov     rcx, rbx
0x18004b727  call    ?GetOrCreatePeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z; CWcnPeerCache::GetOrCreatePeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)
0x18004b72c  mov     ebx, eax
0x18004b72e  mov     rdi, [rsp+130h+var_F0]
0x18004b733  test    eax, eax
0x18004b735  jns     short loc_18004B762
0x18004b737  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b73e  lea     rsi, WPP_GLOBAL_Control
0x18004b745  cmp     rcx, rsi
0x18004b748  jz      loc_18004BA77
0x18004b74e  cmp     byte ptr [rcx+19h], 2
0x18004b752  jb      loc_18004BA77
0x18004b758  mov     edx, 15h
0x18004b75d  jmp     loc_18004B9EC
0x18004b762  lea     rcx, [rbp+4Fh+var_88]; this
0x18004b766  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18004b76b  nop
0x18004b76c  lea     rcx, [rsp+130h+var_D8]; this
0x18004b771  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004b776  nop
0x18004b777  mov     r8, rsi
0x18004b77a  mov     rdx, r14
0x18004b77d  lea     rcx, [rsp+130h+var_D8]
0x18004b782  call    ??$CopyFromBuffer@PEAE@CSbSafeBuffer@@QEAAJPEAE0@Z; CSbSafeBuffer::CopyFromBuffer<uchar *>(uchar *,uchar *)
0x18004b787  mov     ebx, eax
0x18004b789  test    eax, eax
0x18004b78b  jns     short loc_18004B7B6
0x18004b78d  mov     r10, cs:WPP_GLOBAL_Control
0x18004b794  lea     rsi, WPP_GLOBAL_Control
0x18004b79b  cmp     r10, rsi
0x18004b79e  jz      loc_18004B881
0x18004b7a4  cmp     byte ptr [r10+19h], 2
0x18004b7a9  jb      loc_18004B84C
0x18004b7af  mov     edx, 1Bh
0x18004b7b4  jmp     short loc_18004B829
0x18004b7b6  lea     r8, [rsp+130h+var_D8]; struct CSbSafeBuffer *
0x18004b7bb  mov     edx, 1Bh; enum tagWCN_ATTRIBUTE_TYPE
0x18004b7c0  lea     rcx, [rbp+4Fh+var_88]; this
0x18004b7c4  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x18004b7c9  mov     ebx, eax
0x18004b7cb  test    eax, eax
0x18004b7cd  jns     short loc_18004B7F4
0x18004b7cf  mov     r10, cs:WPP_GLOBAL_Control
0x18004b7d6  lea     rsi, WPP_GLOBAL_Control
0x18004b7dd  cmp     r10, rsi
0x18004b7e0  jz      loc_18004B881
0x18004b7e6  cmp     byte ptr [r10+19h], 2
0x18004b7eb  jb      short loc_18004B84C
0x18004b7ed  mov     edx, 1Ch
0x18004b7f2  jmp     short loc_18004B829
0x18004b7f4  lea     rcx, [rdi+88h]; this
0x18004b7fb  lea     rdx, [rbp+4Fh+var_88]; struct CWcnAttribute *
0x18004b7ff  call    ?SetAttribute@CWcnIdentity@@QEAAJPEBVCWcnAttribute@@@Z; CWcnIdentity::SetAttribute(CWcnAttribute const *)
0x18004b804  mov     ebx, eax
0x18004b806  test    eax, eax
0x18004b808  jns     short loc_18004B83E
0x18004b80a  mov     r10, cs:WPP_GLOBAL_Control
0x18004b811  lea     rsi, WPP_GLOBAL_Control
0x18004b818  cmp     r10, rsi
0x18004b81b  jz      short loc_18004B881
0x18004b81d  cmp     byte ptr [r10+19h], 2
0x18004b822  jb      short loc_18004B84C
0x18004b824  mov     edx, 1Dh
0x18004b829  mov     r9d, eax
0x18004b82c  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004b833  mov     rcx, [r10+10h]
0x18004b837  call    WPP_SF_d
0x18004b83c  jmp     short loc_18004B845
0x18004b83e  lea     rsi, WPP_GLOBAL_Control
0x18004b845  mov     r10, cs:WPP_GLOBAL_Control
0x18004b84c  cmp     r10, rsi
0x18004b84f  jz      short loc_18004B881
0x18004b851  test    ebx, ebx
0x18004b853  js      short loc_18004B85C
0x18004b855  cmp     byte ptr [r10+19h], 6
0x18004b85a  jb      short loc_18004B881
0x18004b85c  or      ecx, 0FFFFFFFFh; int
0x18004b85f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004b864  mov     edx, 1Eh
0x18004b869  mov     dword ptr [rsp+130h+var_110], ebx
0x18004b86d  mov     r9, rax
0x18004b870  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004b877  mov     rcx, [r10+10h]
0x18004b87b  call    WPP_SF_sd
0x18004b880  nop
0x18004b881  lea     rcx, [rsp+130h+var_D8]; this
0x18004b886  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004b88b  nop
0x18004b88c  lea     rcx, [rbp+4Fh+var_70]; this
0x18004b890  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004b895  test    ebx, ebx
0x18004b897  jns     short loc_18004B8C0
0x18004b899  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8a0  cmp     rcx, rsi
0x18004b8a3  jz      loc_18004BA77
0x18004b8a9  cmp     byte ptr [rcx+19h], 2
0x18004b8ad  jb      loc_18004BA77
0x18004b8b3  mov     edx, 16h
0x18004b8b8  mov     r9d, ebx
0x18004b8bb  jmp     loc_18004B9EF
0x18004b8c0  mov     ecx, [r15+8]
0x18004b8c4  mov     dword ptr [rsp+130h+var_110], 0
0x18004b8cc  lea     r9, ??_R0?AVCWcnWfdClientPeer@@@8; CWcnWfdClientPeer `RTTI Type Descriptor'
0x18004b8d3  lea     r8, ??_R0?AVIWcnTransportPeer@@@8; IWcnTransportPeer `RTTI Type Descriptor'
0x18004b8da  xor     edx, edx
0x18004b8dc  mov     rcx, [rdi+rcx*8+38h]
0x18004b8e1  call    __RTDynamicCast_0
0x18004b8e6  mov     rdx, rax; struct CWcnWfdClientPeer *
0x18004b8e9  test    rax, rax
0x18004b8ec  jnz     short loc_18004B968
0x18004b8ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b8f5  lea     ecx, [rax+60h]; unsigned __int64
0x18004b8f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b8fd  mov     rdx, rax
0x18004b900  mov     [rsp+130h+var_F0], rax
0x18004b905  test    rax, rax
0x18004b908  jz      short loc_18004B928
0x18004b90a  mov     byte ptr [rax+8], 0
0x18004b90e  lea     rax, ??_7CWcnWfdClientPeer@@6B@; const CWcnWfdClientPeer::`vftable'
0x18004b915  mov     [rdx], rax
0x18004b918  mov     byte ptr [rdx+44h], 0
0x18004b91c  mov     dword ptr [rdx+20h], 0
0x18004b923  test    rdx, rdx
0x18004b926  jnz     short loc_18004B968
0x18004b928  mov     ebx, 8007000Eh
0x18004b92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b934  cmp     rcx, rsi
0x18004b937  jz      loc_18004BA77
0x18004b93d  cmp     byte ptr [rcx+19h], 2
0x18004b941  jb      loc_18004BA77
0x18004b947  mov     edx, 17h
0x18004b94c  lea     r9, aPnewclientpeer; "pNewClientPeer"
0x18004b953  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004b95a  mov     rcx, [rcx+10h]
0x18004b95e  call    WPP_SF_s
0x18004b963  jmp     loc_18004BA77
0x18004b968  mov     rax, [rbp+4Fh+arg_20]
0x18004b96c  mov     [rsp+130h+var_108], rax; struct _GUID *
0x18004b971  lea     rax, [rsp+130h+var_FC]
0x18004b976  mov     [rsp+130h+var_110], rax; unsigned __int8 (*)[6]
0x18004b97b  mov     r9, r12; struct _DOT11_SSID *
0x18004b97e  mov     r8, rdi; struct CWcnPeer *
0x18004b981  mov     rcx, r15; this
0x18004b984  call    ?InitializeWfdClientPeer@CWcnWfdClientTransport@@AEAAXPEAVCWcnWfdClientPeer@@PEAVCWcnPeer@@PEAU_DOT11_SSID@@PEAY05EPEAU_GUID@@@Z; CWcnWfdClientTransport::InitializeWfdClientPeer(CWcnWfdClientPeer *,CWcnPeer *,_DOT11_SSID *,uchar (*)[6],_GUID *)
0x18004b989  mov     ecx, [r13+0D0h]
0x18004b990  add     rcx, r13
0x18004b993  lea     r9, [rsp+130h+var_100]
0x18004b998  lea     r8, [rsp+130h+var_E8]
0x18004b99d  mov     edx, [r13+0D4h]
0x18004b9a4  call    GetWpsIe
0x18004b9a9  test    al, al
0x18004b9ab  jz      loc_18004BA77
0x18004b9b1  mov     r8d, [rsp+130h+var_100]
0x18004b9b6  mov     rdx, [rsp+130h+var_E8]
0x18004b9bb  add     r8, rdx
0x18004b9be  lea     rcx, [rbp+4Fh+var_A8]
0x18004b9c2  call    ??$CopyFromBuffer@PEAE@CSbSafeBuffer@@QEAAJPEAE0@Z; CSbSafeBuffer::CopyFromBuffer<uchar *>(uchar *,uchar *)
0x18004b9c7  mov     ebx, eax
0x18004b9c9  test    eax, eax
0x18004b9cb  jns     short loc_18004BA01
0x18004b9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9d4  cmp     rcx, rsi
0x18004b9d7  jz      loc_18004BA77
0x18004b9dd  cmp     byte ptr [rcx+19h], 2
0x18004b9e1  jb      loc_18004BA77
0x18004b9e7  mov     edx, 18h
0x18004b9ec  mov     r9d, eax
0x18004b9ef  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004b9f6  mov     rcx, [rcx+10h]
0x18004b9fa  call    WPP_SF_d
0x18004b9ff  jmp     short loc_18004BA77
0x18004ba01  mov     rcx, [rdi+78h]
0x18004ba05  mov     rax, [rcx]
0x18004ba08  lea     rdx, [r15+30h]
0x18004ba0c  mov     [rsp+130h+var_110], 0
0x18004ba15  lea     r9, [rbp+4Fh+var_A8]
0x18004ba19  mov     r8, rdi
0x18004ba1c  mov     rax, [rax+10h]
0x18004ba20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba25  mov     ebx, eax
0x18004ba27  test    eax, eax
0x18004ba29  jns     short loc_18004BA77
0x18004ba2b  mov     r10, cs:WPP_GLOBAL_Control
0x18004ba32  cmp     r10, rsi
0x18004ba35  jz      short loc_18004BA5D
0x18004ba37  cmp     byte ptr [r10+19h], 4
0x18004ba3c  jb      short loc_18004BA5D
0x18004ba3e  xor     ecx, ecx; int
0x18004ba40  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004ba45  mov     edx, 19h
0x18004ba4a  mov     r9, rax
0x18004ba4d  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004ba54  mov     rcx, [r10+10h]
0x18004ba58  call    WPP_SF_s
0x18004ba5d  xor     ebx, ebx
0x18004ba5f  lea     rcx, [rdi+88h]
0x18004ba66  cmp     [rcx+61h], bl
0x18004ba69  jnz     short loc_18004BA77
0x18004ba6b  mov     byte ptr [rcx+61h], 1
0x18004ba6f  lea     edx, [rbx+2]
0x18004ba72  call    ?NotifyListenerInternal@CWcnIdentity@@AEAAXW4tagWCN_PEER_EVENT_TYPE@@@Z; CWcnIdentity::NotifyListenerInternal(tagWCN_PEER_EVENT_TYPE)
0x18004ba77  mov     rcx, [rsp+130h+lpCriticalSection]; lpCriticalSection
0x18004ba7c  call    cs:__imp_LeaveCriticalSection
0x18004ba82  test    rdi, rdi
0x18004ba85  jz      short loc_18004BA8E
0x18004ba87  lock dec dword ptr [rdi+108h]
0x18004ba8e  mov     r10, cs:WPP_GLOBAL_Control
0x18004ba95  cmp     r10, rsi
0x18004ba98  jz      short loc_18004BACA
0x18004ba9a  test    ebx, ebx
0x18004ba9c  js      short loc_18004BAA5
0x18004ba9e  cmp     byte ptr [r10+19h], 6
0x18004baa3  jb      short loc_18004BACA
0x18004baa5  or      ecx, 0FFFFFFFFh; int
0x18004baa8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004baad  mov     edx, 1Ah
0x18004bab2  mov     dword ptr [rsp+130h+var_110], ebx
0x18004bab6  mov     r9, rax
0x18004bab9  lea     r8, WPP_de419415f993330b2119000481c3437b_Traceguids
0x18004bac0  mov     rcx, [r10+10h]
0x18004bac4  call    WPP_SF_sd
0x18004bac9  nop
0x18004baca  lea     rcx, [rbp+4Fh+var_A8]; this
0x18004bace  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004bad3  mov     rcx, [rbp+4Fh+var_48]
0x18004bad7  xor     rcx, rsp; StackCookie
0x18004bada  call    __security_check_cookie
0x18004badf  add     rsp, 0F8h
0x18004bae6  pop     r15
0x18004bae8  pop     r14
0x18004baea  pop     r13
0x18004baec  pop     r12
0x18004baee  pop     rdi
0x18004baef  pop     rsi
0x18004baf0  pop     rbx
0x18004baf1  pop     rbp
0x18004baf2  retn
```
