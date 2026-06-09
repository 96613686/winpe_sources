# CReport::WriteReportAsXML(XML_EXPORT_TYPE,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180077234`
- end: `0x180077565`
- name: `?WriteReportAsXML@CReport@@QEAAJW4XML_EXPORT_TYPE@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(CReport *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x180097120`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180008298`
- `0x18000da00`
- `0x18001c368`
- `0x180020680`
- `0x180043324`
- `0x180043468`
- `0x18004ff20`
- `0x180050440`
- `0x180053300`
- `0x18007546c`
- `0x180077234`
- `0x180077870`
- `0x1800779f8`
- `0x180077c20`
- `0x180077e3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077412`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800773e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800773e6`

## string_xrefs

- `0x1800772e3`: `.report.xml`
- `0x180077465`: `xmlns:xsi`
- `0x180077470`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CReport::WriteReportAsXML(CReport *this, __int64 a2, LPCWSTR *a3)
{
  int TempFile; // ebx
  wchar_t *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  void *v9; // rdx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  CReport *v12; // rcx
  CReport *v13; // rcx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+50h] [rbp-B0h]
  const wchar_t *v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h]
  _QWORD v21[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v24[264]; // [rsp+B0h] [rbp-50h] BYREF

  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 244, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
    TempFile = -2147024809;
    goto LABEL_27;
  }
  if ( *a3 == a3[1] )
  {
    TempFile = UtilGetTempFile((__int64)&v16, 0, (const size_t *)L".report.xml", v24, dwCreationDisposition, 0, 1u, 0);
    if ( TempFile < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_27;
      v7 = 245;
      goto LABEL_11;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a3, v24) )
    {
      TempFile = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_27;
      v7 = 246;
      v8 = 2147942414LL;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v8);
      goto LABEL_27;
    }
    v9 = v16;
  }
  else
  {
    FileW = CreateFileW(*a3, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(&v16, FileW);
    v9 = v16;
    if ( (unsigned __int64)v16 + 1 <= 1 )
    {
      LastError = GetLastError();
      TempFile = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          247,
          WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
          (unsigned int)TempFile);
      goto LABEL_27;
    }
  }
  TempFile = CXMLWriter::Initialize((CXMLWriter *)&v17, v9);
  if ( TempFile >= 0 )
  {
    v22[0] = L"xmlns:xsi";
    v22[1] = L"http://www.w3.org/2001/XMLSchema-instance";
    v22[2] = 0;
    v21[0] = v22;
    v21[1] = 1;
    v23 = 0;
    v19 = L"WERREPORT";
    v20 = 9;
    CXMLWriter::BeginElement((unsigned int)&v17, (unsigned int)&v19, (unsigned int)&v23, 0, (__int64)v21);
    CReport::XMLWriteMachineInfo(v12, (struct CXMLWriter *)&v17);
    CReport::XMLWriteUserInfo(v13, (struct CXMLWriter *)&v17);
    CReport::XMLWriteApplicationInfo(this, (struct CXMLWriter *)&v17);
    CReport::XMLWriteEventInfo(this, (struct CXMLWriter *)&v17);
    CReport::XMLWriteSignatureInfo(this, (struct CXMLWriter *)&v17);
    CReport::XMLWriteFileInfo(this, (struct CXMLWriter *)&v17);
    v19 = L"WERREPORT";
    v20 = 9;
    CXMLWriter::EndElement(&v17, &v19);
    TempFile = 0;
    goto LABEL_27;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v7 = 248;
LABEL_11:
    v8 = (unsigned int)TempFile;
    goto LABEL_12;
  }
LABEL_27:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x180077234  mov     [rsp-8+arg_8], rbx
0x180077239  push    rbp
0x18007723a  push    rsi
0x18007723b  push    rdi
0x18007723c  lea     rbp, [rsp-1D0h]
0x180077244  sub     rsp, 2D0h
0x18007724b  mov     rax, cs:__security_cookie
0x180077252  xor     rax, rsp
0x180077255  mov     [rbp+1E0h+var_20], rax
0x18007725c  mov     rdi, r8
0x18007725f  mov     rsi, rcx
0x180077262  mov     [rsp+2E0h+var_2A0], 0
0x18007726b  mov     [rsp+2E0h+var_298], 0FFFFFFFFFFFFFFFFh
0x180077274  mov     [rsp+2E0h+var_290], 0
0x18007727c  test    r8, r8
0x18007727f  jnz     short loc_1800772B9
0x180077281  lea     rax, WPP_GLOBAL_Control
0x180077288  mov     rcx, cs:WPP_GLOBAL_Control
0x18007728f  cmp     rcx, rax
0x180077292  jz      short loc_1800772AF
0x180077294  test    byte ptr [rcx+1Ch], 1
0x180077298  jz      short loc_1800772AF
0x18007729a  mov     edx, 0F4h
0x18007729f  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x1800772a6  mov     rcx, [rcx+10h]
0x1800772aa  call    WPP_SF_
0x1800772af  mov     ebx, 80070057h
0x1800772b4  jmp     loc_180077536
0x1800772b9  mov     rcx, [r8]; lpFileName
0x1800772bc  cmp     rcx, [r8+8]
0x1800772c0  jnz     loc_1800773C1
0x1800772c6  mov     [rsp+2E0h+var_2A8], 0
0x1800772ce  mov     dword ptr [rsp+2E0h+hTemplateFile], 1
0x1800772d6  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], 0
0x1800772df  lea     r9, [rbp+1E0h+var_230]
0x1800772e3  lea     r8, aReportXml; ".report.xml"
0x1800772ea  xor     edx, edx
0x1800772ec  lea     rcx, [rsp+2E0h+var_2A0]
0x1800772f1  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1800772f6  mov     ebx, eax
0x1800772f8  test    eax, eax
0x1800772fa  jns     short loc_18007733A
0x1800772fc  lea     rax, WPP_GLOBAL_Control
0x180077303  mov     rcx, cs:WPP_GLOBAL_Control
0x18007730a  cmp     rcx, rax
0x18007730d  jz      loc_180077536
0x180077313  test    byte ptr [rcx+1Ch], 1
0x180077317  jz      loc_180077536
0x18007731d  mov     edx, 0F5h
0x180077322  mov     r9d, ebx
0x180077325  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18007732c  mov     rcx, [rcx+10h]
0x180077330  call    WPP_SF_d
0x180077335  jmp     loc_180077536
0x18007733a  lea     rdx, [rbp+1E0h+var_230]
0x18007733e  mov     rcx, rdi
0x180077341  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180077346  test    al, al
0x180077348  jnz     short loc_18007737D
0x18007734a  mov     ebx, 8007000Eh
0x18007734f  lea     rax, WPP_GLOBAL_Control
0x180077356  mov     rcx, cs:WPP_GLOBAL_Control
0x18007735d  cmp     rcx, rax
0x180077360  jz      loc_180077536
0x180077366  test    byte ptr [rcx+1Ch], 1
0x18007736a  jz      loc_180077536
0x180077370  mov     edx, 0F6h
0x180077375  mov     r9d, 8007000Eh
0x18007737b  jmp     short loc_180077325
0x18007737d  mov     rdx, [rsp+2E0h+var_2A0]; void *
0x180077382  lea     rcx, [rsp+2E0h+var_298]; this
0x180077387  call    ?Initialize@CXMLWriter@@QEAAJPEAX@Z; CXMLWriter::Initialize(void *)
0x18007738c  mov     ebx, eax
0x18007738e  test    eax, eax
0x180077390  jns     loc_180077465
0x180077396  lea     rax, WPP_GLOBAL_Control
0x18007739d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800773a4  cmp     rcx, rax
0x1800773a7  jz      loc_180077536
0x1800773ad  test    byte ptr [rcx+1Ch], 1
0x1800773b1  jz      loc_180077536
0x1800773b7  mov     edx, 0F8h
0x1800773bc  jmp     loc_180077322
0x1800773c1  mov     [rsp+2E0h+hTemplateFile], 0; hTemplateFile
0x1800773ca  mov     [rsp+2E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800773d2  mov     [rsp+2E0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800773da  xor     r9d, r9d; lpSecurityAttributes
0x1800773dd  mov     edx, 40000000h; dwDesiredAccess
0x1800773e2  lea     r8d, [r9+1]; dwShareMode
0x1800773e6  call    cs:__imp_CreateFileW
0x1800773ed  nop     dword ptr [rax+rax+00h]
0x1800773f2  mov     rdx, rax
0x1800773f5  lea     rcx, [rsp+2E0h+var_2A0]
0x1800773fa  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800773ff  mov     rdx, [rsp+2E0h+var_2A0]
0x180077404  lea     rax, [rdx+1]
0x180077408  cmp     rax, 1
0x18007740c  ja      loc_180077382
0x180077412  call    cs:__imp_GetLastError
0x180077419  nop     dword ptr [rax+rax+00h]
0x18007741e  mov     ecx, eax; unsigned int
0x180077420  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180077425  mov     ebx, eax
0x180077427  lea     rax, WPP_GLOBAL_Control
0x18007742e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077435  cmp     rcx, rax
0x180077438  jz      loc_180077536
0x18007743e  test    byte ptr [rcx+1Ch], 1
0x180077442  jz      loc_180077536
0x180077448  mov     edx, 0F7h
0x18007744d  mov     r9d, ebx
0x180077450  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180077457  mov     rcx, [rcx+10h]
0x18007745b  call    WPP_SF_d
0x180077460  jmp     loc_180077536
0x180077465  lea     rax, aXmlnsXsi; "xmlns:xsi"
0x18007746c  mov     [rbp+1E0h+var_260], rax
0x180077470  lea     rax, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema-instan"...
0x180077477  mov     [rbp+1E0h+var_258], rax
0x18007747b  mov     [rbp+1E0h+var_250], 0
0x180077483  lea     rax, [rbp+1E0h+var_260]
0x180077487  mov     [rsp+2E0h+var_270], rax
0x18007748c  mov     [rsp+2E0h+var_268], 1
0x180077495  xorps   xmm0, xmm0
0x180077498  movdqa  [rbp+1E0h+var_240], xmm0
0x18007749d  lea     rdi, aWerreport; "WERREPORT"
0x1800774a4  mov     [rsp+2E0h+var_280], rdi
0x1800774a9  mov     ebx, 9
0x1800774ae  mov     [rsp+2E0h+var_278], rbx
0x1800774b3  lea     rax, [rsp+2E0h+var_270]
0x1800774b8  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x1800774bd  xor     r9d, r9d
0x1800774c0  lea     r8, [rbp+1E0h+var_240]
0x1800774c4  lea     rdx, [rsp+2E0h+var_280]
0x1800774c9  lea     rcx, [rsp+2E0h+var_298]
0x1800774ce  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800774d3  lea     rdx, [rsp+2E0h+var_298]; struct CXMLWriter *
0x1800774d8  call    ?XMLWriteMachineInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z; CReport::XMLWriteMachineInfo(CXMLWriter *)
0x1800774dd  lea     rdx, [rsp+2E0h+var_298]; struct CXMLWriter *
0x1800774e2  call    ?XMLWriteUserInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z; CReport::XMLWriteUserInfo(CXMLWriter *)
0x1800774e7  lea     rdx, [rsp+2E0h+var_298]; struct CXMLWriter *
0x1800774ec  mov     rcx, rsi; this
0x1800774ef  call    ?XMLWriteApplicationInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z; CReport::XMLWriteApplicationInfo(CXMLWriter *)
0x1800774f4  lea     rdx, [rsp+2E0h+var_298]; struct CXMLWriter *
0x1800774f9  mov     rcx, rsi; this
0x1800774fc  call    ?XMLWriteEventInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z; CReport::XMLWriteEventInfo(CXMLWriter *)
0x180077501  lea     rdx, [rsp+2E0h+var_298]; struct CXMLWriter *
0x180077506  mov     rcx, rsi; this
0x180077509  call    ?XMLWriteSignatureInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z; CReport::XMLWriteSignatureInfo(CXMLWriter *)
0x18007750e  lea     rdx, [rsp+2E0h+var_298]; struct CXMLWriter *
0x180077513  mov     rcx, rsi; this
0x180077516  call    ?XMLWriteFileInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z; CReport::XMLWriteFileInfo(CXMLWriter *)
0x18007751b  mov     [rsp+2E0h+var_280], rdi
0x180077520  mov     [rsp+2E0h+var_278], rbx
0x180077525  lea     rdx, [rsp+2E0h+var_280]
0x18007752a  lea     rcx, [rsp+2E0h+var_298]
0x18007752f  call    ?EndElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; CXMLWriter::EndElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180077534  xor     ebx, ebx
0x180077536  lea     rcx, [rsp+2E0h+var_2A0]
0x18007753b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180077540  mov     eax, ebx
0x180077542  mov     rcx, [rbp+1E0h+var_20]
0x180077549  xor     rcx, rsp; StackCookie
0x18007754c  call    __security_check_cookie
0x180077551  mov     rbx, [rsp+2E0h+arg_8]
0x180077559  add     rsp, 2D0h
0x180077560  pop     rdi
0x180077561  pop     rsi
0x180077562  pop     rbp
0x180077563  retn
```
