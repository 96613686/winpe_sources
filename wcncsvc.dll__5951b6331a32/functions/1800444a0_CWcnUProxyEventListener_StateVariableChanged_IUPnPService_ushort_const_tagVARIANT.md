# CWcnUProxyEventListener::StateVariableChanged(IUPnPService *,ushort const *,tagVARIANT)

- ea: `0x1800444a0`
- end: `0x1800448a7`
- name: `?StateVariableChanged@CWcnUProxyEventListener@@UEAAJPEAUIUPnPService@@PEBGUtagVARIANT@@@Z`
- size: `1031`
- prototype: `int(CWcnUProxyEventListener *__hidden this, struct IUPnPService *, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x1800076ac`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a6d4`
- `0x180026ab4`
- `0x18003e180`
- `0x1800441f4`
- `0x1800444a0`
- `0x180053004`
- `0x180056dfe`
- `0x180056e30`

## import_xrefs

- `msvcrt!sscanf_s` at `0x180044735`
- `msvcrt!sscanf_s` at `0x180044735`
- `RPCRT4!UuidCreate` at `0x180044562`
- `RPCRT4!UuidCreate` at `0x180044562`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004466b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004466b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180044806`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180044806`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWcnUProxyEventListener::StateVariableChanged(
        CWcnUProxyEventListener *this,
        struct IUPnPService *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4)
{
  _QWORD *v7; // r10
  const char *Indent; // rax
  __int64 v9; // r10
  int v10; // ebx
  LONGLONG llVal; // rcx
  _BYTE *v12; // r10
  unsigned int v13; // eax
  __int64 v14; // r10
  const char *v15; // rax
  __int64 v16; // r10
  SAFEARRAY *parray; // rsi
  __int64 cElements; // rdi
  HRESULT v19; // eax
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  const char *v23; // rax
  __int64 v24; // r10
  __int64 i; // rcx
  unsigned int v26; // eax
  __int64 v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  void *ppvData; // [rsp+40h] [rbp-49h] BYREF
  int v32; // [rsp+48h] [rbp-41h]
  __int16 v33; // [rsp+4Ch] [rbp-3Dh]
  __int128 v34; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v35[32]; // [rsp+60h] [rbp-29h] BYREF
  UUID Uuid; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v37[24]; // [rsp+90h] [rbp+7h] BYREF

  ppvData = 0;
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v35);
  v34 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 17, WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, Indent);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_s(v7[2], 18, WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, "pcwszStateVarName");
    v10 = -2147467261;
    goto LABEL_54;
  }
  UuidCreate(&Uuid);
  if ( a4->vt == 8209 )
  {
    llVal = a4->llVal;
    if ( !*(_DWORD *)(llVal + 28) && (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 1) != 0 )
      McTemplateU0zzjhbr3_EtwEventWriteTransfer(
        llVal,
        (unsigned int)RawReceive,
        (unsigned int)L"UPROXY",
        (_DWORD)a3,
        (__int64)&Uuid,
        *(_WORD *)(llVal + 24),
        *(_QWORD *)(llVal + 16));
  }
  if ( wcscmp_0(a3, L"WLANEvent") )
  {
    v10 = 0;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_54;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_50;
    v13 = (unsigned int)GetIndent(0);
    WPP_SF_sS(
      *(_QWORD *)(v14 + 16),
      19,
      (unsigned int)WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids,
      v13,
      (__int64)a3);
    goto LABEL_49;
  }
  if ( a4->vt != 8209 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v15 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v16 + 16), 20, WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, v15);
      v12 = WPP_GLOBAL_Control;
    }
    v10 = -2147418113;
    goto LABEL_50;
  }
  parray = a4->parray;
  cElements = parray->rgsabound[0].cElements;
  if ( (unsigned __int64)(cElements - 19) > 0x27ED )
  {
    v10 = -2147024809;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_54;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_50;
    v26 = (unsigned int)GetIndent(0);
    WPP_SF_sP(*(_QWORD *)(v27 + 16), 21, (unsigned int)WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, v26, cElements);
    goto LABEL_49;
  }
  v19 = SafeArrayAccessData(parray, &ppvData);
  v10 = v19;
  if ( v19 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_54;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_50;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids,
      (unsigned int)v19);
    goto LABEL_49;
  }
  if ( *(_BYTE *)ppvData == 1 || *(_BYTE *)ppvData == 2 )
  {
    v20 = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v35, (const unsigned __int8 *)ppvData + 18, cElements - 18);
    v10 = v20;
    if ( v20 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_45;
      v22 = 23;
      goto LABEL_44;
    }
    if ( sscanf_s(
           (const char *const)ppvData + 1,
           "%02x:%02x:%02x:%02x:%02x:%02x",
           v37,
           &v37[4],
           &v37[8],
           &v37[12],
           &v37[16],
           &v37[20]) != 6 )
    {
      v10 = -2147024809;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v23 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v24 + 16), 24, WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, v23);
      }
      goto LABEL_45;
    }
    for ( i = 0; i != 6; ++i )
      *((_BYTE *)&v32 + i) = v37[4 * i];
    v34 = 0;
    LODWORD(v34) = v32;
    WORD2(v34) = v33;
    if ( g_pUProxyTransport )
    {
      v20 = CWcnUProxyTransport::NotifyMessageArrival(
              6,
              &v34,
              (char *)ppvData + 1,
              *(unsigned __int8 *)ppvData,
              (struct CSbMessageBuffer *)v35,
              *((_DWORD *)this + 22));
      v10 = v20;
      if ( v20 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = 25;
LABEL_44:
          WPP_SF_d(v21[2], v22, WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, (unsigned int)v20);
        }
      }
    }
  }
LABEL_45:
  SafeArrayUnaccessData(parray);
LABEL_49:
  v12 = WPP_GLOBAL_Control;
LABEL_50:
  if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v10 < 0 || v12[25] >= 6u) )
  {
    v28 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v29 + 16), 26, (unsigned int)WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids, v28, v10);
  }
LABEL_54:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v35);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800444a0  push    rbp
0x1800444a2  push    rbx
0x1800444a3  push    rsi
0x1800444a4  push    rdi
0x1800444a5  push    r12
0x1800444a7  push    r13
0x1800444a9  push    r14
0x1800444ab  lea     rbp, [rsp-27h]
0x1800444b0  sub     rsp, 0B0h
0x1800444b7  mov     rax, cs:__security_cookie
0x1800444be  xor     rax, rsp
0x1800444c1  mov     [rbp+57h+var_38], rax
0x1800444c5  mov     rsi, r9
0x1800444c8  mov     rdi, r8
0x1800444cb  mov     r14, rcx
0x1800444ce  mov     [rbp+57h+ppvData], 0
0x1800444d6  lea     rcx, [rbp+57h+var_80]; this
0x1800444da  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x1800444df  nop
0x1800444e0  xorps   xmm0, xmm0
0x1800444e3  movups  [rbp+57h+var_90], xmm0
0x1800444e7  lea     r12, WPP_GLOBAL_Control
0x1800444ee  lea     r13, WPP_2b1f6476da833ce9f57ec3a1e8f59cb5_Traceguids
0x1800444f5  mov     r10, cs:WPP_GLOBAL_Control
0x1800444fc  cmp     r10, r12
0x1800444ff  jz      short loc_18004452D
0x180044501  cmp     byte ptr [r10+19h], 6
0x180044506  jb      short loc_18004452D
0x180044508  mov     ecx, 1; int
0x18004450d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180044512  mov     edx, 11h
0x180044517  mov     r9, rax
0x18004451a  mov     r8, r13
0x18004451d  mov     rcx, [r10+10h]
0x180044521  call    WPP_SF_s
0x180044526  mov     r10, cs:WPP_GLOBAL_Control
0x18004452d  test    rdi, rdi
0x180044530  jnz     short loc_18004455E
0x180044532  cmp     r10, r12
0x180044535  jz      short loc_180044554
0x180044537  cmp     byte ptr [r10+19h], 2
0x18004453c  jb      short loc_180044554
0x18004453e  lea     edx, [rdi+12h]
0x180044541  lea     r9, aPcwszstatevarn; "pcwszStateVarName"
0x180044548  mov     r8, r13
0x18004454b  mov     rcx, [r10+10h]
0x18004454f  call    WPP_SF_s
0x180044554  mov     ebx, 80004003h
0x180044559  jmp     loc_18004487E
0x18004455e  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180044562  call    cs:__imp_UuidCreate
0x180044568  mov     ebx, 2011h
0x18004456d  cmp     [rsi], bx
0x180044570  jnz     short loc_1800445B6
0x180044572  mov     rcx, [rsi+8]
0x180044576  cmp     dword ptr [rcx+1Ch], 0
0x18004457a  jnz     short loc_1800445B6
0x18004457c  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, 1
0x180044583  jz      short loc_1800445B6
0x180044585  mov     rax, [rcx+10h]
0x180044589  mov     [rsp+0E0h+var_B0], rax
0x18004458e  movzx   eax, word ptr [rcx+18h]
0x180044592  mov     word ptr [rsp+0E0h+var_B8], ax
0x180044597  lea     rax, [rbp+57h+Uuid]
0x18004459b  mov     [rsp+0E0h+var_C0], rax
0x1800445a0  mov     r9, rdi
0x1800445a3  lea     r8, aUproxy; "UPROXY"
0x1800445aa  lea     rdx, RawReceive
0x1800445b1  call    McTemplateU0zzjhbr3_EtwEventWriteTransfer
0x1800445b6  lea     rdx, aWlanevent; "WLANEvent"
0x1800445bd  mov     rcx, rdi; String1
0x1800445c0  call    wcscmp_0
0x1800445c5  test    eax, eax
0x1800445c7  jz      short loc_180044609
0x1800445c9  xor     ebx, ebx
0x1800445cb  mov     r10, cs:WPP_GLOBAL_Control
0x1800445d2  cmp     r10, r12
0x1800445d5  jz      loc_18004487E
0x1800445db  cmp     byte ptr [r10+19h], 5
0x1800445e0  jb      loc_18004484D
0x1800445e6  xor     ecx, ecx; int
0x1800445e8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800445ed  lea     edx, [rbx+13h]
0x1800445f0  mov     [rsp+0E0h+var_C0], rdi
0x1800445f5  mov     r9, rax
0x1800445f8  mov     r8, r13
0x1800445fb  mov     rcx, [r10+10h]
0x1800445ff  call    WPP_SF_sS
0x180044604  jmp     loc_180044846
0x180044609  cmp     [rsi], bx
0x18004460c  jz      short loc_18004464D
0x18004460e  mov     r10, cs:WPP_GLOBAL_Control
0x180044615  cmp     r10, r12
0x180044618  jz      short loc_180044643
0x18004461a  cmp     byte ptr [r10+19h], 3
0x18004461f  jb      short loc_180044643
0x180044621  xor     ecx, ecx; int
0x180044623  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180044628  mov     edx, 14h
0x18004462d  mov     r9, rax
0x180044630  mov     r8, r13
0x180044633  mov     rcx, [r10+10h]
0x180044637  call    WPP_SF_s
0x18004463c  mov     r10, cs:WPP_GLOBAL_Control
0x180044643  mov     ebx, 8000FFFFh
0x180044648  jmp     loc_18004484D
0x18004464d  mov     rsi, [rsi+8]
0x180044651  mov     edi, [rsi+18h]
0x180044654  lea     rax, [rdi-13h]
0x180044658  cmp     rax, 27EDh
0x18004465e  ja      loc_18004480E
0x180044664  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180044668  mov     rcx, rsi; psa
0x18004466b  call    cs:__imp_SafeArrayAccessData
0x180044671  mov     ebx, eax
0x180044673  test    eax, eax
0x180044675  jns     short loc_1800446AB
0x180044677  mov     r10, cs:WPP_GLOBAL_Control
0x18004467e  cmp     r10, r12
0x180044681  jz      loc_18004487E
0x180044687  cmp     byte ptr [r10+19h], 2
0x18004468c  jb      loc_18004484D
0x180044692  mov     edx, 16h
0x180044697  mov     r9d, eax
0x18004469a  mov     r8, r13
0x18004469d  mov     rcx, [r10+10h]
0x1800446a1  call    WPP_SF_d
0x1800446a6  jmp     loc_180044846
0x1800446ab  mov     rdx, [rbp+57h+ppvData]
0x1800446af  movzx   ecx, byte ptr [rdx]
0x1800446b2  sub     ecx, 1
0x1800446b5  jz      short loc_1800446C0
0x1800446b7  cmp     ecx, 1
0x1800446ba  jnz     loc_180044803
0x1800446c0  lea     r8, [rdi-12h]; unsigned __int64
0x1800446c4  add     rdx, 12h; unsigned __int8 *
0x1800446c8  lea     rcx, [rbp+57h+var_80]; this
0x1800446cc  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x1800446d1  mov     ebx, eax
0x1800446d3  test    eax, eax
0x1800446d5  jns     short loc_1800446FB
0x1800446d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446de  cmp     rcx, r12
0x1800446e1  jz      loc_180044803
0x1800446e7  cmp     byte ptr [rcx+19h], 2
0x1800446eb  jb      loc_180044803
0x1800446f1  mov     edx, 17h
0x1800446f6  jmp     loc_1800447F4
0x1800446fb  mov     rcx, [rbp+57h+ppvData]
0x1800446ff  inc     rcx; Buffer
0x180044702  lea     rax, [rbp+57h+var_3C]
0x180044706  mov     [rsp+0E0h+var_A8], rax
0x18004470b  lea     rax, [rbp+57h+var_40]
0x18004470f  mov     [rsp+0E0h+var_B0], rax
0x180044714  lea     rax, [rbp+57h+var_44]
0x180044718  mov     [rsp+0E0h+var_B8], rax
0x18004471d  lea     rax, [rbp+57h+var_48]
0x180044721  mov     [rsp+0E0h+var_C0], rax
0x180044726  lea     r9, [rbp+57h+var_4C]
0x18004472a  lea     r8, [rbp+57h+var_50]
0x18004472e  lea     rdx, a02x02x02x02x02; "%02x:%02x:%02x:%02x:%02x:%02x"
0x180044735  call    cs:__imp_sscanf_s
0x18004473b  cmp     eax, 6
0x18004473e  jz      short loc_180044780
0x180044740  mov     ebx, 80070057h
0x180044745  mov     r10, cs:WPP_GLOBAL_Control
0x18004474c  cmp     r10, r12
0x18004474f  jz      loc_180044803
0x180044755  cmp     byte ptr [r10+19h], 3
0x18004475a  jb      loc_180044803
0x180044760  xor     ecx, ecx; int
0x180044762  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180044767  mov     edx, 18h
0x18004476c  mov     r9, rax
0x18004476f  mov     r8, r13
0x180044772  mov     rcx, [r10+10h]
0x180044776  call    WPP_SF_s
0x18004477b  jmp     loc_180044803
0x180044780  xor     ecx, ecx
0x180044782  mov     al, [rbp+rcx*4+57h+var_50]
0x180044786  mov     byte ptr [rbp+rcx+57h+var_98], al
0x18004478a  inc     rcx
0x18004478d  cmp     rcx, 6
0x180044791  jnz     short loc_180044782
0x180044793  xorps   xmm0, xmm0
0x180044796  movups  [rbp+57h+var_90], xmm0
0x18004479a  mov     eax, [rbp+57h+var_98]
0x18004479d  mov     dword ptr [rbp+57h+var_90], eax
0x1800447a0  movzx   eax, [rbp+57h+var_94]
0x1800447a4  mov     word ptr [rbp+57h+var_90+4], ax
0x1800447a8  cmp     cs:?g_pUProxyTransport@@3PEAVCWcnUProxyTransport@@EA, 0; CWcnUProxyTransport * g_pUProxyTransport
0x1800447b0  jz      short loc_180044803
0x1800447b2  mov     r8, [rbp+57h+ppvData]
0x1800447b6  movzx   r9d, byte ptr [r8]
0x1800447ba  inc     r8
0x1800447bd  mov     eax, [r14+58h]
0x1800447c1  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800447c5  lea     rax, [rbp+57h+var_80]
0x1800447c9  mov     [rsp+0E0h+var_C0], rax
0x1800447ce  lea     rdx, [rbp+57h+var_90]
0x1800447d2  call    ?NotifyMessageArrival@CWcnUProxyTransport@@QEAAJPEBU_GUID@@PEAEW4tagWcnUPnP_WLANEventType@@PEBVCSbMessageBuffer@@K@Z; CWcnUProxyTransport::NotifyMessageArrival(_GUID const *,uchar *,tagWcnUPnP_WLANEventType,CSbMessageBuffer const *,ulong)
0x1800447d7  mov     ebx, eax
0x1800447d9  test    eax, eax
0x1800447db  jns     short loc_180044803
0x1800447dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447e4  cmp     rcx, r12
0x1800447e7  jz      short loc_180044803
0x1800447e9  cmp     byte ptr [rcx+19h], 2
0x1800447ed  jb      short loc_180044803
0x1800447ef  mov     edx, 19h
0x1800447f4  mov     r9d, eax
0x1800447f7  mov     r8, r13
0x1800447fa  mov     rcx, [rcx+10h]
0x1800447fe  call    WPP_SF_d
0x180044803  mov     rcx, rsi; psa
0x180044806  call    cs:__imp_SafeArrayUnaccessData
0x18004480c  jmp     short loc_180044846
0x18004480e  mov     ebx, 80070057h
0x180044813  mov     r10, cs:WPP_GLOBAL_Control
0x18004481a  cmp     r10, r12
0x18004481d  jz      short loc_18004487E
0x18004481f  cmp     byte ptr [r10+19h], 3
0x180044824  jb      short loc_18004484D
0x180044826  xor     ecx, ecx; int
0x180044828  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004482d  mov     edx, 15h
0x180044832  mov     [rsp+0E0h+var_C0], rdi
0x180044837  mov     r9, rax
0x18004483a  mov     r8, r13
0x18004483d  mov     rcx, [r10+10h]
0x180044841  call    WPP_SF_sP
0x180044846  mov     r10, cs:WPP_GLOBAL_Control
0x18004484d  cmp     r10, r12
0x180044850  jz      short loc_18004487E
0x180044852  test    ebx, ebx
0x180044854  js      short loc_18004485D
0x180044856  cmp     byte ptr [r10+19h], 6
0x18004485b  jb      short loc_18004487E
0x18004485d  or      ecx, 0FFFFFFFFh; int
0x180044860  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180044865  mov     edx, 1Ah
0x18004486a  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18004486e  mov     r9, rax
0x180044871  mov     r8, r13
0x180044874  mov     rcx, [r10+10h]
0x180044878  call    WPP_SF_sd
0x18004487d  nop
0x18004487e  lea     rcx, [rbp+57h+var_80]; this
0x180044882  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180044887  mov     eax, ebx
0x180044889  mov     rcx, [rbp+57h+var_38]
0x18004488d  xor     rcx, rsp; StackCookie
0x180044890  call    __security_check_cookie
0x180044895  add     rsp, 0B0h
0x18004489c  pop     r14
0x18004489e  pop     r13
0x1800448a0  pop     r12
0x1800448a2  pop     rdi
0x1800448a3  pop     rsi
0x1800448a4  pop     rbx
0x1800448a5  pop     rbp
0x1800448a6  retn
```
