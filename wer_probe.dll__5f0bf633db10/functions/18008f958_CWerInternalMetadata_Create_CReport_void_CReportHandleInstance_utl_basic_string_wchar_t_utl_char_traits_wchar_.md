# CWerInternalMetadata::Create(CReport *,void *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18008f958`
- end: `0x18008ff9e`
- name: `?Create@CWerInternalMetadata@@SAJPEAVCReport@@PEAXPEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1606`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b280`

## callees

- `0x180004bb4`
- `0x18000e7fc`
- `0x18001fe24`
- `0x18003765c`
- `0x180041338`
- `0x18004144c`
- `0x180041588`
- `0x180047c10`
- `0x180048a24`
- `0x18004a12c`
- `0x18007211c`
- `0x18008f958`
- `0x18008ffa4`
- `0x1800901e4`
- `0x180090374`
- `0x180090590`
- `0x18009061c`
- `0x180090b94`
- `0x180090dac`
- `0x180090ecc`
- `0x1800911fc`
- `0x1800914d8`
- `0x180091d10`

## string_xrefs

- `0x18008f9d0`: `CWerInternalMetadata::Create Report == NULL\n`
- `0x18008fa24`: `xmlWriter.Initialize failed with hr=0x%x\n`
- `0x18008fab2`: `xmlWriter.BeginElement failed with hr=0x%x\n`
- `0x18008fb01`: `WriteOsVersionInformation failed with hr=0x%x\n`
- `0x18008fb60`: `WriteProcessInformation failed with hr=0x%x\n`
- `0x18008fbaf`: `WriteProcessMetadata failed with hr=0x%x\n`
- `0x18008fbfe`: `WriteProblemSignatures failed with hr=0x%x\n`
- `0x18008fc4d`: `WriteDynamicSignatures failed with hr=0x%x\n`
- `0x18008fc9c`: `WriteServiceInformation failed with hr=0x%x\n`
- `0x18008fd1a`: `WriteSystemInformation failed with hr=0x%x\n`
- `0x18008fdaa`: `WriteSecureBootState failed with hr=0x%x\n`
- `0x18008fdfe`: `WriteIntegrator failed with hr=0x%x\n`
- `0x18008fe57`: `WritePhoneInformation failed with hr=0x%x\n`
- `0x18008fea3`: `WriteContainerInformation failed with hr=0x%x\n`
- `0x18008fef2`: `WriteTimelineInformation failed with hr=0x%x\n`
- `0x18008ff41`: `WriteReportInformation failed with hr=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerInternalMetadata::Create(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  int v13; // [rsp+38h] [rbp-21h]
  const wchar_t *v14; // [rsp+40h] [rbp-19h] BYREF
  __int64 v15; // [rsp+48h] [rbp-11h]
  __int128 v16; // [rsp+50h] [rbp-9h] BYREF
  __int128 v17; // [rsp+60h] [rbp+7h] BYREF
  int v18; // [rsp+70h] [rbp+17h] BYREF
  __int64 v19; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v20[6]; // [rsp+80h] [rbp+27h] BYREF

  v12 = -1;
  v13 = 0;
  v18 = 0;
  v19 = 0;
  v20[0] = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      a4,
      L"CWerInternalMetadata::Create Report == NULL\r\n");
    goto LABEL_95;
  }
  v7 = CXMLWriter::Initialize((CXMLWriter *)&v12, a2);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"xmlWriter.Initialize failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v16 = 0;
  v17 = 0;
  v14 = L"WERReportMetadata";
  v15 = 17;
  v7 = CXMLWriter::BeginElement((unsigned int)&v12, (unsigned int)&v14, (unsigned int)&v17, 0, (__int64)&v16);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"xmlWriter.BeginElement failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteOsVersionInformation(&v12, a4);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteOsVersionInformation failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  if ( *(_DWORD *)(a1 + 5872) != 4 )
  {
    v7 = CWerInternalMetadata::WriteProcessInformation((struct CXMLWriter *)&v12);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteProcessInformation failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
    v7 = CWerInternalMetadata::WriteProcessMetadata(&v12, a1);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteProcessMetadata failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
  }
  v7 = CWerInternalMetadata::WriteProblemSignatures(&v12, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteProblemSignatures failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteDynamicSignatures(&v12, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteDynamicSignatures failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteServiceInformation(&v12, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteServiceInformation failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  if ( v18 )
  {
    v7 = -2147024809;
    goto LABEL_58;
  }
  v10 = CPhoneInformation::LoadPhoneInfoDll(&v19, v20);
  v7 = v10;
  if ( v10 < 0 )
  {
    if ( v10 != -2147024770 )
    {
LABEL_58:
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"phoneInformation.Initialize failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
  }
  else
  {
    v18 = 1;
  }
  v7 = CWerInternalMetadata::WriteSystemInformation(&v12, &v18, a4);
  if ( (v7 & 0x80000000) == 0 )
  {
    v7 = CWerInternalMetadata::WriteSecureBootState(&v12);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( a3 && (v7 = CWerInternalMetadata::WriteIntegrator(&v12, a3), (v7 & 0x80000000) != 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a4,
          L"WriteIntegrator failed with hr=0x%x\r\n",
          v7);
      }
      else if ( v18 && (v7 = CWerInternalMetadata::WritePhoneInformation(&v12, &v18, a4), (v7 & 0x80000000) != 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a4,
          L"WritePhoneInformation failed with hr=0x%x\r\n",
          v7);
      }
      else
      {
        v7 = CWerInternalMetadata::WriteContainerInformation(&v12);
        if ( (v7 & 0x80000000) == 0 )
        {
          v7 = CWerInternalMetadata::WriteTimelineInformation((struct CXMLWriter *)&v12, a1);
          if ( (v7 & 0x80000000) == 0 )
          {
            v7 = CWerInternalMetadata::WriteReportInformation(&v12, a1);
            if ( (v7 & 0x80000000) == 0 )
            {
              v7 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
              tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                a4,
                L"WriteReportInformation failed with hr=0x%x\r\n",
                v7);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              a4,
              L"WriteTimelineInformation failed with hr=0x%x\r\n",
              v7);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            a4,
            L"WriteContainerInformation failed with hr=0x%x\r\n",
            v7);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteSecureBootState failed with hr=0x%x\r\n",
        v7);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteSystemInformation failed with hr=0x%x\r\n",
      v7);
  }
LABEL_95:
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v14 = L"WERReportMetadata";
    v15 = 17;
    CXMLWriter::EndElement(&v12, &v14, v8, v9);
    v12 = -1;
  }
  CPhoneInformation::~CPhoneInformation((CPhoneInformation *)&v18);
  return v7;
}

```

## disassembly

```asm
0x18008f958  push    rbp
0x18008f95a  push    rbx
0x18008f95b  push    rsi
0x18008f95c  push    rdi
0x18008f95d  push    r14
0x18008f95f  lea     rbp, [rsp-37h]
0x18008f964  sub     rsp, 90h
0x18008f96b  mov     rdi, r9
0x18008f96e  mov     r14, r8
0x18008f971  mov     rsi, rcx
0x18008f974  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x18008f97c  mov     [rbp+57h+var_78], 0
0x18008f983  mov     [rbp+57h+var_40], 0
0x18008f98a  mov     [rbp+57h+var_38], 0
0x18008f992  mov     [rbp+57h+var_30], 0
0x18008f99a  test    rcx, rcx
0x18008f99d  jnz     short loc_18008F9E4
0x18008f99f  mov     ebx, 80070057h
0x18008f9a4  lea     rax, WPP_GLOBAL_Control
0x18008f9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f9b2  cmp     rcx, rax
0x18008f9b5  jz      short loc_18008F9D0
0x18008f9b7  test    byte ptr [rcx+1Ch], 1
0x18008f9bb  jz      short loc_18008F9D0
0x18008f9bd  lea     edx, [rsi+0Fh]
0x18008f9c0  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008f9c7  mov     rcx, [rcx+10h]
0x18008f9cb  call    WPP_SF_
0x18008f9d0  lea     rdx, aCwerinternalme; "CWerInternalMetadata::Create Report == "...
0x18008f9d7  mov     rcx, rdi
0x18008f9da  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x18008f9df  jmp     loc_18008FF4F
0x18008f9e4  lea     rcx, [rbp+57h+var_80]; this
0x18008f9e8  call    ?Initialize@CXMLWriter@@QEAAJPEAX@Z; CXMLWriter::Initialize(void *)
0x18008f9ed  mov     ebx, eax
0x18008f9ef  test    eax, eax
0x18008f9f1  jns     short loc_18008FA3B
0x18008f9f3  lea     rax, WPP_GLOBAL_Control
0x18008f9fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa01  cmp     rcx, rax
0x18008fa04  jz      short loc_18008FA24
0x18008fa06  test    byte ptr [rcx+1Ch], 1
0x18008fa0a  jz      short loc_18008FA24
0x18008fa0c  mov     edx, 10h
0x18008fa11  mov     r9d, ebx
0x18008fa14  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fa1b  mov     rcx, [rcx+10h]
0x18008fa1f  call    WPP_SF_d
0x18008fa24  lea     rdx, aXmlwriterIniti; "xmlWriter.Initialize failed with hr=0x%"...
0x18008fa2b  mov     r8d, ebx
0x18008fa2e  mov     rcx, rdi
0x18008fa31  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008fa36  jmp     loc_18008FF4F
0x18008fa3b  xorps   xmm0, xmm0
0x18008fa3e  movdqa  [rbp+57h+var_60], xmm0
0x18008fa43  xorps   xmm1, xmm1
0x18008fa46  movdqa  [rbp+57h+var_50], xmm1
0x18008fa4b  lea     rax, aWerreportmetad; "WERReportMetadata"
0x18008fa52  mov     [rbp+57h+var_70], rax
0x18008fa56  mov     [rbp+57h+var_68], 11h
0x18008fa5e  lea     rax, [rbp+57h+var_60]
0x18008fa62  mov     [rsp+0B0h+var_90], rax
0x18008fa67  xor     r9d, r9d
0x18008fa6a  lea     r8, [rbp+57h+var_50]
0x18008fa6e  lea     rdx, [rbp+57h+var_70]
0x18008fa72  lea     rcx, [rbp+57h+var_80]
0x18008fa76  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x18008fa7b  mov     ebx, eax
0x18008fa7d  test    eax, eax
0x18008fa7f  jns     short loc_18008FABE
0x18008fa81  lea     rax, WPP_GLOBAL_Control
0x18008fa88  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa8f  cmp     rcx, rax
0x18008fa92  jz      short loc_18008FAB2
0x18008fa94  test    byte ptr [rcx+1Ch], 1
0x18008fa98  jz      short loc_18008FAB2
0x18008fa9a  mov     edx, 11h
0x18008fa9f  mov     r9d, ebx
0x18008faa2  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008faa9  mov     rcx, [rcx+10h]
0x18008faad  call    WPP_SF_d
0x18008fab2  lea     rdx, aXmlwriterBegin; "xmlWriter.BeginElement failed with hr=0"...
0x18008fab9  jmp     loc_18008FA2B
0x18008fabe  mov     rdx, rdi
0x18008fac1  lea     rcx, [rbp+57h+var_80]
0x18008fac5  call    ?WriteOsVersionInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteOsVersionInformation(CXMLWriter *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008faca  mov     ebx, eax
0x18008facc  test    eax, eax
0x18008face  jns     short loc_18008FB0D
0x18008fad0  lea     rax, WPP_GLOBAL_Control
0x18008fad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fade  cmp     rcx, rax
0x18008fae1  jz      short loc_18008FB01
0x18008fae3  test    byte ptr [rcx+1Ch], 1
0x18008fae7  jz      short loc_18008FB01
0x18008fae9  mov     edx, 12h
0x18008faee  mov     r9d, ebx
0x18008faf1  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008faf8  mov     rcx, [rcx+10h]
0x18008fafc  call    WPP_SF_d
0x18008fb01  lea     rdx, aWriteosversion; "WriteOsVersionInformation failed with h"...
0x18008fb08  jmp     loc_18008FA2B
0x18008fb0d  cmp     dword ptr [rsi+16F0h], 4
0x18008fb14  jz      loc_18008FBBB
0x18008fb1a  mov     r8, rdi
0x18008fb1d  mov     rdx, rsi
0x18008fb20  lea     rcx, [rbp+57h+var_80]; struct CXMLWriter *
0x18008fb24  call    ?WriteProcessInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProcessInformation(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fb29  mov     ebx, eax
0x18008fb2b  test    eax, eax
0x18008fb2d  jns     short loc_18008FB6C
0x18008fb2f  lea     rax, WPP_GLOBAL_Control
0x18008fb36  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fb3d  cmp     rcx, rax
0x18008fb40  jz      short loc_18008FB60
0x18008fb42  test    byte ptr [rcx+1Ch], 1
0x18008fb46  jz      short loc_18008FB60
0x18008fb48  mov     edx, 13h
0x18008fb4d  mov     r9d, ebx
0x18008fb50  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fb57  mov     rcx, [rcx+10h]
0x18008fb5b  call    WPP_SF_d
0x18008fb60  lea     rdx, aWriteprocessin; "WriteProcessInformation failed with hr="...
0x18008fb67  jmp     loc_18008FA2B
0x18008fb6c  mov     rdx, rsi
0x18008fb6f  lea     rcx, [rbp+57h+var_80]
0x18008fb73  call    ?WriteProcessMetadata@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProcessMetadata(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fb78  mov     ebx, eax
0x18008fb7a  test    eax, eax
0x18008fb7c  jns     short loc_18008FBBB
0x18008fb7e  lea     rax, WPP_GLOBAL_Control
0x18008fb85  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fb8c  cmp     rcx, rax
0x18008fb8f  jz      short loc_18008FBAF
0x18008fb91  test    byte ptr [rcx+1Ch], 1
0x18008fb95  jz      short loc_18008FBAF
0x18008fb97  mov     edx, 14h
0x18008fb9c  mov     r9d, ebx
0x18008fb9f  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fba6  mov     rcx, [rcx+10h]
0x18008fbaa  call    WPP_SF_d
0x18008fbaf  lea     rdx, aWriteprocessme; "WriteProcessMetadata failed with hr=0x%"...
0x18008fbb6  jmp     loc_18008FA2B
0x18008fbbb  mov     rdx, rsi
0x18008fbbe  lea     rcx, [rbp+57h+var_80]
0x18008fbc2  call    ?WriteProblemSignatures@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProblemSignatures(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fbc7  mov     ebx, eax
0x18008fbc9  test    eax, eax
0x18008fbcb  jns     short loc_18008FC0A
0x18008fbcd  lea     rax, WPP_GLOBAL_Control
0x18008fbd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fbdb  cmp     rcx, rax
0x18008fbde  jz      short loc_18008FBFE
0x18008fbe0  test    byte ptr [rcx+1Ch], 1
0x18008fbe4  jz      short loc_18008FBFE
0x18008fbe6  mov     edx, 15h
0x18008fbeb  mov     r9d, ebx
0x18008fbee  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fbf5  mov     rcx, [rcx+10h]
0x18008fbf9  call    WPP_SF_d
0x18008fbfe  lea     rdx, aWriteproblemsi; "WriteProblemSignatures failed with hr=0"...
0x18008fc05  jmp     loc_18008FA2B
0x18008fc0a  mov     rdx, rsi
0x18008fc0d  lea     rcx, [rbp+57h+var_80]
0x18008fc11  call    ?WriteDynamicSignatures@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteDynamicSignatures(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fc16  mov     ebx, eax
0x18008fc18  test    eax, eax
0x18008fc1a  jns     short loc_18008FC59
0x18008fc1c  lea     rax, WPP_GLOBAL_Control
0x18008fc23  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fc2a  cmp     rcx, rax
0x18008fc2d  jz      short loc_18008FC4D
0x18008fc2f  test    byte ptr [rcx+1Ch], 1
0x18008fc33  jz      short loc_18008FC4D
0x18008fc35  mov     edx, 16h
0x18008fc3a  mov     r9d, ebx
0x18008fc3d  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fc44  mov     rcx, [rcx+10h]
0x18008fc48  call    WPP_SF_d
0x18008fc4d  lea     rdx, aWritedynamicsi; "WriteDynamicSignatures failed with hr=0"...
0x18008fc54  jmp     loc_18008FA2B
0x18008fc59  mov     rdx, rsi
0x18008fc5c  lea     rcx, [rbp+57h+var_80]
0x18008fc60  call    ?WriteServiceInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteServiceInformation(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fc65  mov     ebx, eax
0x18008fc67  test    eax, eax
0x18008fc69  jns     short loc_18008FCA8
0x18008fc6b  lea     rax, WPP_GLOBAL_Control
0x18008fc72  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fc79  cmp     rcx, rax
0x18008fc7c  jz      short loc_18008FC9C
0x18008fc7e  test    byte ptr [rcx+1Ch], 1
0x18008fc82  jz      short loc_18008FC9C
0x18008fc84  mov     edx, 17h
0x18008fc89  mov     r9d, ebx
0x18008fc8c  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fc93  mov     rcx, [rcx+10h]
0x18008fc97  call    WPP_SF_d
0x18008fc9c  lea     rdx, aWriteservicein; "WriteServiceInformation failed with hr="...
0x18008fca3  jmp     loc_18008FA2B
0x18008fca8  cmp     [rbp+57h+var_40], 0
0x18008fcac  jz      short loc_18008FCB5
0x18008fcae  mov     ebx, 80070057h
0x18008fcb3  jmp     short loc_18008FD2D
0x18008fcb5  lea     rdx, [rbp+57h+var_30]
0x18008fcb9  lea     rcx, [rbp+57h+var_38]
0x18008fcbd  call    ?LoadPhoneInfoDll@CPhoneInformation@@CAJPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6AHW4_PHONE_INFORMATION_KEY@@PEA_W_KPEA_K@Z@Z; CPhoneInformation::LoadPhoneInfoDll(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,int (**)(_PHONE_INFORMATION_KEY,wchar_t *,unsigned __int64,unsigned __int64 *))
0x18008fcc2  mov     ebx, eax
0x18008fcc4  test    eax, eax
0x18008fcc6  js      short loc_18008FD26
0x18008fcc8  mov     [rbp+57h+var_40], 1
0x18008fccf  mov     r8, rdi
0x18008fcd2  lea     rdx, [rbp+57h+var_40]
0x18008fcd6  lea     rcx, [rbp+57h+var_80]
0x18008fcda  call    ?WriteSystemInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteSystemInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fcdf  mov     ebx, eax
0x18008fce1  test    eax, eax
0x18008fce3  jns     loc_18008FD6A
0x18008fce9  lea     rax, WPP_GLOBAL_Control
0x18008fcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fcf7  cmp     rcx, rax
0x18008fcfa  jz      short loc_18008FD1A
0x18008fcfc  test    byte ptr [rcx+1Ch], 1
0x18008fd00  jz      short loc_18008FD1A
0x18008fd02  mov     edx, 19h
0x18008fd07  mov     r9d, ebx
0x18008fd0a  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fd11  mov     rcx, [rcx+10h]
0x18008fd15  call    WPP_SF_d
0x18008fd1a  lea     rdx, aWritesysteminf_0; "WriteSystemInformation failed with hr=0"...
0x18008fd21  jmp     loc_18008FA2B
0x18008fd26  cmp     eax, 8007007Eh
0x18008fd2b  jz      short loc_18008FCCF
0x18008fd2d  lea     rax, WPP_GLOBAL_Control
0x18008fd34  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fd3b  cmp     rcx, rax
0x18008fd3e  jz      short loc_18008FD5E
0x18008fd40  test    byte ptr [rcx+1Ch], 1
0x18008fd44  jz      short loc_18008FD5E
0x18008fd46  mov     edx, 18h
0x18008fd4b  mov     r9d, ebx
0x18008fd4e  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fd55  mov     rcx, [rcx+10h]
0x18008fd59  call    WPP_SF_d
0x18008fd5e  lea     rdx, aPhoneinformati_0; "phoneInformation.Initialize failed with"...
0x18008fd65  jmp     loc_18008FA2B
0x18008fd6a  lea     rcx, [rbp+57h+var_80]
0x18008fd6e  call    ?WriteSecureBootState@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteSecureBootState(CXMLWriter *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fd73  mov     ebx, eax
0x18008fd75  test    eax, eax
0x18008fd77  jns     short loc_18008FDB6
0x18008fd79  lea     rax, WPP_GLOBAL_Control
0x18008fd80  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fd87  cmp     rcx, rax
0x18008fd8a  jz      short loc_18008FDAA
0x18008fd8c  test    byte ptr [rcx+1Ch], 1
0x18008fd90  jz      short loc_18008FDAA
0x18008fd92  mov     edx, 1Ah
0x18008fd97  mov     r9d, ebx
0x18008fd9a  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fda1  mov     rcx, [rcx+10h]
0x18008fda5  call    WPP_SF_d
0x18008fdaa  lea     rdx, aWritesecureboo; "WriteSecureBootState failed with hr=0x%"...
0x18008fdb1  jmp     loc_18008FA2B
0x18008fdb6  test    r14, r14
0x18008fdb9  jz      short loc_18008FE0A
0x18008fdbb  mov     rdx, r14
0x18008fdbe  lea     rcx, [rbp+57h+var_80]
0x18008fdc2  call    ?WriteIntegrator@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteIntegrator(CXMLWriter *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fdc7  mov     ebx, eax
0x18008fdc9  test    eax, eax
0x18008fdcb  jns     short loc_18008FE0A
0x18008fdcd  lea     rax, WPP_GLOBAL_Control
0x18008fdd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fddb  cmp     rcx, rax
0x18008fdde  jz      short loc_18008FDFE
0x18008fde0  test    byte ptr [rcx+1Ch], 1
0x18008fde4  jz      short loc_18008FDFE
0x18008fde6  mov     edx, 1Bh
0x18008fdeb  mov     r9d, ebx
0x18008fdee  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x18008fdf5  mov     rcx, [rcx+10h]
0x18008fdf9  call    WPP_SF_d
0x18008fdfe  lea     rdx, aWriteintegrato; "WriteIntegrator failed with hr=0x%x\r\n"
0x18008fe05  jmp     loc_18008FA2B
0x18008fe0a  cmp     [rbp+57h+var_40], 0
0x18008fe0e  jz      short loc_18008FE63
0x18008fe10  mov     r8, rdi
0x18008fe13  lea     rdx, [rbp+57h+var_40]
0x18008fe17  lea     rcx, [rbp+57h+var_80]
0x18008fe1b  call    ?WritePhoneInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WritePhoneInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008fe20  mov     ebx, eax
0x18008fe22  test    eax, eax
0x18008fe24  jns     short loc_18008FE63
0x18008fe26  lea     rax, WPP_GLOBAL_Control
0x18008fe2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fe34  cmp     rcx, rax
0x18008fe37  jz      short loc_18008FE57
0x18008fe39  test    byte ptr [rcx+1Ch], 1
0x18008fe3d  jz      short loc_18008FE57
  ... truncated ...
```
