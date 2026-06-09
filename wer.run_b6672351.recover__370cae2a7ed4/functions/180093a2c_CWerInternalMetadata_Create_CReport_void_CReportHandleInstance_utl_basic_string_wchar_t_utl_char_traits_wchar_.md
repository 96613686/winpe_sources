# CWerInternalMetadata::Create(CReport *,void *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180093a2c`
- end: `0x180094073`
- name: `?Create@CWerInternalMetadata@@SAJPEAVCReport@@PEAXPEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1607`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009074`

## callees

- `0x180004c64`
- `0x180010280`
- `0x180020680`
- `0x18003970c`
- `0x180043210`
- `0x180043324`
- `0x180043468`
- `0x180049e1c`
- `0x18004ac74`
- `0x18004c428`
- `0x18007546c`
- `0x180093a2c`
- `0x18009407c`
- `0x1800942c0`
- `0x180094454`
- `0x180094670`
- `0x1800946fc`
- `0x180094c74`
- `0x180094e8c`
- `0x180094fac`
- `0x1800952e4`
- `0x1800955c0`
- `0x180095e0c`

## string_xrefs

- `0x180093aa4`: `CWerInternalMetadata::Create Report == NULL\n`
- `0x180093af8`: `xmlWriter.Initialize failed with hr=0x%x\n`
- `0x180093b86`: `xmlWriter.BeginElement failed with hr=0x%x\n`
- `0x180093bd5`: `WriteOsVersionInformation failed with hr=0x%x\n`
- `0x180093c34`: `WriteProcessInformation failed with hr=0x%x\n`
- `0x180093c83`: `WriteProcessMetadata failed with hr=0x%x\n`
- `0x180093cd2`: `WriteProblemSignatures failed with hr=0x%x\n`
- `0x180093d21`: `WriteDynamicSignatures failed with hr=0x%x\n`
- `0x180093d70`: `WriteServiceInformation failed with hr=0x%x\n`
- `0x180093dee`: `WriteSystemInformation failed with hr=0x%x\n`
- `0x180093e7e`: `WriteSecureBootState failed with hr=0x%x\n`
- `0x180093ed2`: `WriteIntegrator failed with hr=0x%x\n`
- `0x180093f2b`: `WritePhoneInformation failed with hr=0x%x\n`
- `0x180093f77`: `WriteContainerInformation failed with hr=0x%x\n`
- `0x180093fc6`: `WriteTimelineInformation failed with hr=0x%x\n`
- `0x180094015`: `WriteReportInformation failed with hr=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerInternalMetadata::Create(__int64 a1, void *a2, __int64 a3, void *a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+38h] [rbp-21h]
  const wchar_t *v12; // [rsp+40h] [rbp-19h] BYREF
  __int64 v13; // [rsp+48h] [rbp-11h]
  __int128 v14; // [rsp+50h] [rbp-9h] BYREF
  __int128 v15; // [rsp+60h] [rbp+7h] BYREF
  int v16; // [rsp+70h] [rbp+17h] BYREF
  __int64 v17; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v18[6]; // [rsp+80h] [rbp+27h] BYREF

  v10 = -1;
  v11 = 0;
  v16 = 0;
  v17 = 0;
  v18[0] = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      a4,
      L"CWerInternalMetadata::Create Report == NULL\r\n");
    goto LABEL_95;
  }
  v7 = CXMLWriter::Initialize((CXMLWriter *)&v10, a2);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"xmlWriter.Initialize failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v14 = 0;
  v15 = 0;
  v12 = L"WERReportMetadata";
  v13 = 17;
  v7 = CXMLWriter::BeginElement((unsigned int)&v10, (unsigned int)&v12, (unsigned int)&v15, 0, (__int64)&v14);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"xmlWriter.BeginElement failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteOsVersionInformation(&v10, a4);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteOsVersionInformation failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  if ( *(_DWORD *)(a1 + 5872) != 4 )
  {
    v7 = CWerInternalMetadata::WriteProcessInformation((struct CXMLWriter *)&v10);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteProcessInformation failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
    v7 = CWerInternalMetadata::WriteProcessMetadata(&v10, a1);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteProcessMetadata failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
  }
  v7 = CWerInternalMetadata::WriteProblemSignatures(&v10, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteProblemSignatures failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteDynamicSignatures(&v10, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteDynamicSignatures failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  v7 = CWerInternalMetadata::WriteServiceInformation(&v10, a1);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteServiceInformation failed with hr=0x%x\r\n",
      v7);
    goto LABEL_95;
  }
  if ( v16 )
  {
    v7 = -2147024809;
    goto LABEL_58;
  }
  v8 = CPhoneInformation::LoadPhoneInfoDll(&v17, v18);
  v7 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147024770 )
    {
LABEL_58:
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"phoneInformation.Initialize failed with hr=0x%x\r\n",
        v7);
      goto LABEL_95;
    }
  }
  else
  {
    v16 = 1;
  }
  v7 = CWerInternalMetadata::WriteSystemInformation(&v10, &v16, a4);
  if ( (v7 & 0x80000000) == 0 )
  {
    v7 = CWerInternalMetadata::WriteSecureBootState(&v10);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( a3 && (v7 = CWerInternalMetadata::WriteIntegrator(&v10, a3), (v7 & 0x80000000) != 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a4,
          L"WriteIntegrator failed with hr=0x%x\r\n",
          v7);
      }
      else if ( v16 && (v7 = CWerInternalMetadata::WritePhoneInformation(&v10, &v16, a4), (v7 & 0x80000000) != 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a4,
          L"WritePhoneInformation failed with hr=0x%x\r\n",
          v7);
      }
      else
      {
        v7 = CWerInternalMetadata::WriteContainerInformation(&v10);
        if ( (v7 & 0x80000000) == 0 )
        {
          v7 = CWerInternalMetadata::WriteTimelineInformation((struct CXMLWriter *)&v10);
          if ( (v7 & 0x80000000) == 0 )
          {
            v7 = CWerInternalMetadata::WriteReportInformation(&v10, a1);
            if ( (v7 & 0x80000000) == 0 )
            {
              v7 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
              tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                a4,
                L"WriteReportInformation failed with hr=0x%x\r\n",
                v7);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              a4,
              L"WriteTimelineInformation failed with hr=0x%x\r\n",
              v7);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
      tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        a4,
        L"WriteSecureBootState failed with hr=0x%x\r\n",
        v7);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids, v7);
    tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      a4,
      L"WriteSystemInformation failed with hr=0x%x\r\n",
      v7);
  }
LABEL_95:
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v12 = L"WERReportMetadata";
    v13 = 17;
    CXMLWriter::EndElement(&v10, &v12);
    v10 = -1;
  }
  CPhoneInformation::~CPhoneInformation((CPhoneInformation *)&v16);
  return v7;
}

```

## disassembly

```asm
0x180093a2c  push    rbp
0x180093a2e  push    rbx
0x180093a2f  push    rsi
0x180093a30  push    rdi
0x180093a31  push    r14
0x180093a33  lea     rbp, [rsp-37h]
0x180093a38  sub     rsp, 90h
0x180093a3f  mov     rdi, r9
0x180093a42  mov     r14, r8
0x180093a45  mov     rsi, rcx
0x180093a48  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x180093a50  mov     [rbp+57h+var_78], 0
0x180093a57  mov     [rbp+57h+var_40], 0
0x180093a5e  mov     [rbp+57h+var_38], 0
0x180093a66  mov     [rbp+57h+var_30], 0
0x180093a6e  test    rcx, rcx
0x180093a71  jnz     short loc_180093AB8
0x180093a73  mov     ebx, 80070057h
0x180093a78  lea     rax, WPP_GLOBAL_Control
0x180093a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180093a86  cmp     rcx, rax
0x180093a89  jz      short loc_180093AA4
0x180093a8b  test    byte ptr [rcx+1Ch], 1
0x180093a8f  jz      short loc_180093AA4
0x180093a91  lea     edx, [rsi+0Fh]
0x180093a94  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093a9b  mov     rcx, [rcx+10h]
0x180093a9f  call    WPP_SF_
0x180093aa4  lea     rdx, aCwerinternalme; "CWerInternalMetadata::Create Report == "...
0x180093aab  mov     rcx, rdi
0x180093aae  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x180093ab3  jmp     loc_180094023
0x180093ab8  lea     rcx, [rbp+57h+var_80]; this
0x180093abc  call    ?Initialize@CXMLWriter@@QEAAJPEAX@Z; CXMLWriter::Initialize(void *)
0x180093ac1  mov     ebx, eax
0x180093ac3  test    eax, eax
0x180093ac5  jns     short loc_180093B0F
0x180093ac7  lea     rax, WPP_GLOBAL_Control
0x180093ace  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ad5  cmp     rcx, rax
0x180093ad8  jz      short loc_180093AF8
0x180093ada  test    byte ptr [rcx+1Ch], 1
0x180093ade  jz      short loc_180093AF8
0x180093ae0  mov     edx, 10h
0x180093ae5  mov     r9d, ebx
0x180093ae8  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093aef  mov     rcx, [rcx+10h]
0x180093af3  call    WPP_SF_d
0x180093af8  lea     rdx, aXmlwriterIniti; "xmlWriter.Initialize failed with hr=0x%"...
0x180093aff  mov     r8d, ebx
0x180093b02  mov     rcx, rdi
0x180093b05  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180093b0a  jmp     loc_180094023
0x180093b0f  xorps   xmm0, xmm0
0x180093b12  movdqa  [rbp+57h+var_60], xmm0
0x180093b17  xorps   xmm1, xmm1
0x180093b1a  movdqa  [rbp+57h+var_50], xmm1
0x180093b1f  lea     rax, aWerreportmetad; "WERReportMetadata"
0x180093b26  mov     [rbp+57h+var_70], rax
0x180093b2a  mov     [rbp+57h+var_68], 11h
0x180093b32  lea     rax, [rbp+57h+var_60]
0x180093b36  mov     [rsp+0B0h+var_90], rax
0x180093b3b  xor     r9d, r9d
0x180093b3e  lea     r8, [rbp+57h+var_50]
0x180093b42  lea     rdx, [rbp+57h+var_70]
0x180093b46  lea     rcx, [rbp+57h+var_80]
0x180093b4a  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180093b4f  mov     ebx, eax
0x180093b51  test    eax, eax
0x180093b53  jns     short loc_180093B92
0x180093b55  lea     rax, WPP_GLOBAL_Control
0x180093b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180093b63  cmp     rcx, rax
0x180093b66  jz      short loc_180093B86
0x180093b68  test    byte ptr [rcx+1Ch], 1
0x180093b6c  jz      short loc_180093B86
0x180093b6e  mov     edx, 11h
0x180093b73  mov     r9d, ebx
0x180093b76  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093b7d  mov     rcx, [rcx+10h]
0x180093b81  call    WPP_SF_d
0x180093b86  lea     rdx, aXmlwriterBegin; "xmlWriter.BeginElement failed with hr=0"...
0x180093b8d  jmp     loc_180093AFF
0x180093b92  mov     rdx, rdi
0x180093b95  lea     rcx, [rbp+57h+var_80]
0x180093b99  call    ?WriteOsVersionInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteOsVersionInformation(CXMLWriter *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093b9e  mov     ebx, eax
0x180093ba0  test    eax, eax
0x180093ba2  jns     short loc_180093BE1
0x180093ba4  lea     rax, WPP_GLOBAL_Control
0x180093bab  mov     rcx, cs:WPP_GLOBAL_Control
0x180093bb2  cmp     rcx, rax
0x180093bb5  jz      short loc_180093BD5
0x180093bb7  test    byte ptr [rcx+1Ch], 1
0x180093bbb  jz      short loc_180093BD5
0x180093bbd  mov     edx, 12h
0x180093bc2  mov     r9d, ebx
0x180093bc5  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093bcc  mov     rcx, [rcx+10h]
0x180093bd0  call    WPP_SF_d
0x180093bd5  lea     rdx, aWriteosversion; "WriteOsVersionInformation failed with h"...
0x180093bdc  jmp     loc_180093AFF
0x180093be1  cmp     dword ptr [rsi+16F0h], 4
0x180093be8  jz      loc_180093C8F
0x180093bee  mov     r8, rdi
0x180093bf1  mov     rdx, rsi
0x180093bf4  lea     rcx, [rbp+57h+var_80]; struct CXMLWriter *
0x180093bf8  call    ?WriteProcessInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProcessInformation(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093bfd  mov     ebx, eax
0x180093bff  test    eax, eax
0x180093c01  jns     short loc_180093C40
0x180093c03  lea     rax, WPP_GLOBAL_Control
0x180093c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180093c11  cmp     rcx, rax
0x180093c14  jz      short loc_180093C34
0x180093c16  test    byte ptr [rcx+1Ch], 1
0x180093c1a  jz      short loc_180093C34
0x180093c1c  mov     edx, 13h
0x180093c21  mov     r9d, ebx
0x180093c24  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093c2b  mov     rcx, [rcx+10h]
0x180093c2f  call    WPP_SF_d
0x180093c34  lea     rdx, aWriteprocessin; "WriteProcessInformation failed with hr="...
0x180093c3b  jmp     loc_180093AFF
0x180093c40  mov     rdx, rsi
0x180093c43  lea     rcx, [rbp+57h+var_80]
0x180093c47  call    ?WriteProcessMetadata@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProcessMetadata(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093c4c  mov     ebx, eax
0x180093c4e  test    eax, eax
0x180093c50  jns     short loc_180093C8F
0x180093c52  lea     rax, WPP_GLOBAL_Control
0x180093c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180093c60  cmp     rcx, rax
0x180093c63  jz      short loc_180093C83
0x180093c65  test    byte ptr [rcx+1Ch], 1
0x180093c69  jz      short loc_180093C83
0x180093c6b  mov     edx, 14h
0x180093c70  mov     r9d, ebx
0x180093c73  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093c7a  mov     rcx, [rcx+10h]
0x180093c7e  call    WPP_SF_d
0x180093c83  lea     rdx, aWriteprocessme; "WriteProcessMetadata failed with hr=0x%"...
0x180093c8a  jmp     loc_180093AFF
0x180093c8f  mov     rdx, rsi
0x180093c92  lea     rcx, [rbp+57h+var_80]
0x180093c96  call    ?WriteProblemSignatures@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteProblemSignatures(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093c9b  mov     ebx, eax
0x180093c9d  test    eax, eax
0x180093c9f  jns     short loc_180093CDE
0x180093ca1  lea     rax, WPP_GLOBAL_Control
0x180093ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180093caf  cmp     rcx, rax
0x180093cb2  jz      short loc_180093CD2
0x180093cb4  test    byte ptr [rcx+1Ch], 1
0x180093cb8  jz      short loc_180093CD2
0x180093cba  mov     edx, 15h
0x180093cbf  mov     r9d, ebx
0x180093cc2  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093cc9  mov     rcx, [rcx+10h]
0x180093ccd  call    WPP_SF_d
0x180093cd2  lea     rdx, aWriteproblemsi; "WriteProblemSignatures failed with hr=0"...
0x180093cd9  jmp     loc_180093AFF
0x180093cde  mov     rdx, rsi
0x180093ce1  lea     rcx, [rbp+57h+var_80]
0x180093ce5  call    ?WriteDynamicSignatures@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteDynamicSignatures(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093cea  mov     ebx, eax
0x180093cec  test    eax, eax
0x180093cee  jns     short loc_180093D2D
0x180093cf0  lea     rax, WPP_GLOBAL_Control
0x180093cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180093cfe  cmp     rcx, rax
0x180093d01  jz      short loc_180093D21
0x180093d03  test    byte ptr [rcx+1Ch], 1
0x180093d07  jz      short loc_180093D21
0x180093d09  mov     edx, 16h
0x180093d0e  mov     r9d, ebx
0x180093d11  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093d18  mov     rcx, [rcx+10h]
0x180093d1c  call    WPP_SF_d
0x180093d21  lea     rdx, aWritedynamicsi; "WriteDynamicSignatures failed with hr=0"...
0x180093d28  jmp     loc_180093AFF
0x180093d2d  mov     rdx, rsi
0x180093d30  lea     rcx, [rbp+57h+var_80]
0x180093d34  call    ?WriteServiceInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteServiceInformation(CXMLWriter *,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093d39  mov     ebx, eax
0x180093d3b  test    eax, eax
0x180093d3d  jns     short loc_180093D7C
0x180093d3f  lea     rax, WPP_GLOBAL_Control
0x180093d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d4d  cmp     rcx, rax
0x180093d50  jz      short loc_180093D70
0x180093d52  test    byte ptr [rcx+1Ch], 1
0x180093d56  jz      short loc_180093D70
0x180093d58  mov     edx, 17h
0x180093d5d  mov     r9d, ebx
0x180093d60  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093d67  mov     rcx, [rcx+10h]
0x180093d6b  call    WPP_SF_d
0x180093d70  lea     rdx, aWriteservicein; "WriteServiceInformation failed with hr="...
0x180093d77  jmp     loc_180093AFF
0x180093d7c  cmp     [rbp+57h+var_40], 0
0x180093d80  jz      short loc_180093D89
0x180093d82  mov     ebx, 80070057h
0x180093d87  jmp     short loc_180093E01
0x180093d89  lea     rdx, [rbp+57h+var_30]
0x180093d8d  lea     rcx, [rbp+57h+var_38]
0x180093d91  call    ?LoadPhoneInfoDll@CPhoneInformation@@CAJPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6AHW4_PHONE_INFORMATION_KEY@@PEA_W_KPEA_K@Z@Z; CPhoneInformation::LoadPhoneInfoDll(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,int (**)(_PHONE_INFORMATION_KEY,wchar_t *,unsigned __int64,unsigned __int64 *))
0x180093d96  mov     ebx, eax
0x180093d98  test    eax, eax
0x180093d9a  js      short loc_180093DFA
0x180093d9c  mov     [rbp+57h+var_40], 1
0x180093da3  mov     r8, rdi
0x180093da6  lea     rdx, [rbp+57h+var_40]
0x180093daa  lea     rcx, [rbp+57h+var_80]
0x180093dae  call    ?WriteSystemInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteSystemInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093db3  mov     ebx, eax
0x180093db5  test    eax, eax
0x180093db7  jns     loc_180093E3E
0x180093dbd  lea     rax, WPP_GLOBAL_Control
0x180093dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180093dcb  cmp     rcx, rax
0x180093dce  jz      short loc_180093DEE
0x180093dd0  test    byte ptr [rcx+1Ch], 1
0x180093dd4  jz      short loc_180093DEE
0x180093dd6  mov     edx, 19h
0x180093ddb  mov     r9d, ebx
0x180093dde  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093de5  mov     rcx, [rcx+10h]
0x180093de9  call    WPP_SF_d
0x180093dee  lea     rdx, aWritesysteminf_0; "WriteSystemInformation failed with hr=0"...
0x180093df5  jmp     loc_180093AFF
0x180093dfa  cmp     eax, 8007007Eh
0x180093dff  jz      short loc_180093DA3
0x180093e01  lea     rax, WPP_GLOBAL_Control
0x180093e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e0f  cmp     rcx, rax
0x180093e12  jz      short loc_180093E32
0x180093e14  test    byte ptr [rcx+1Ch], 1
0x180093e18  jz      short loc_180093E32
0x180093e1a  mov     edx, 18h
0x180093e1f  mov     r9d, ebx
0x180093e22  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093e29  mov     rcx, [rcx+10h]
0x180093e2d  call    WPP_SF_d
0x180093e32  lea     rdx, aPhoneinformati_0; "phoneInformation.Initialize failed with"...
0x180093e39  jmp     loc_180093AFF
0x180093e3e  lea     rcx, [rbp+57h+var_80]
0x180093e42  call    ?WriteSecureBootState@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteSecureBootState(CXMLWriter *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093e47  mov     ebx, eax
0x180093e49  test    eax, eax
0x180093e4b  jns     short loc_180093E8A
0x180093e4d  lea     rax, WPP_GLOBAL_Control
0x180093e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e5b  cmp     rcx, rax
0x180093e5e  jz      short loc_180093E7E
0x180093e60  test    byte ptr [rcx+1Ch], 1
0x180093e64  jz      short loc_180093E7E
0x180093e66  mov     edx, 1Ah
0x180093e6b  mov     r9d, ebx
0x180093e6e  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093e75  mov     rcx, [rcx+10h]
0x180093e79  call    WPP_SF_d
0x180093e7e  lea     rdx, aWritesecureboo; "WriteSecureBootState failed with hr=0x%"...
0x180093e85  jmp     loc_180093AFF
0x180093e8a  test    r14, r14
0x180093e8d  jz      short loc_180093EDE
0x180093e8f  mov     rdx, r14
0x180093e92  lea     rcx, [rbp+57h+var_80]
0x180093e96  call    ?WriteIntegrator@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WriteIntegrator(CXMLWriter *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093e9b  mov     ebx, eax
0x180093e9d  test    eax, eax
0x180093e9f  jns     short loc_180093EDE
0x180093ea1  lea     rax, WPP_GLOBAL_Control
0x180093ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180093eaf  cmp     rcx, rax
0x180093eb2  jz      short loc_180093ED2
0x180093eb4  test    byte ptr [rcx+1Ch], 1
0x180093eb8  jz      short loc_180093ED2
0x180093eba  mov     edx, 1Bh
0x180093ebf  mov     r9d, ebx
0x180093ec2  lea     r8, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids
0x180093ec9  mov     rcx, [rcx+10h]
0x180093ecd  call    WPP_SF_d
0x180093ed2  lea     rdx, aWriteintegrato; "WriteIntegrator failed with hr=0x%x\r\n"
0x180093ed9  jmp     loc_180093AFF
0x180093ede  cmp     [rbp+57h+var_40], 0
0x180093ee2  jz      short loc_180093F37
0x180093ee4  mov     r8, rdi
0x180093ee7  lea     rdx, [rbp+57h+var_40]
0x180093eeb  lea     rcx, [rbp+57h+var_80]
0x180093eef  call    ?WritePhoneInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::WritePhoneInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180093ef4  mov     ebx, eax
0x180093ef6  test    eax, eax
0x180093ef8  jns     short loc_180093F37
0x180093efa  lea     rax, WPP_GLOBAL_Control
0x180093f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180093f08  cmp     rcx, rax
0x180093f0b  jz      short loc_180093F2B
0x180093f0d  test    byte ptr [rcx+1Ch], 1
0x180093f11  jz      short loc_180093F2B
  ... truncated ...
```
