# Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(Microsoft::Diagnostics::XmlWriterFacade &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,unsigned __int64,unsigned __int64,ulong,Microsoft::Diagnostics::GetFileInfoActionDef::FileInfoQueryState const &)

- ea: `0x180088304`
- end: `0x180088da0`
- name: `?WriteSingleFileInfoToXML@GetFileInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N_K3KAEBUFileInfoQueryState@123@@Z`
- size: `2716`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800872f0`
- `0x180308b68`

## callees

- `0x18001d160`
- `0x18001e638`
- `0x18001ee94`
- `0x180027be0`
- `0x18004a750`
- `0x18004cf5c`
- `0x1800566b0`
- `0x180088304`
- `0x1800e2d20`
- `0x1800e2fd8`
- `0x18012de40`
- `0x1802e4fc0`
- `0x1802e50d0`
- `0x1802e5670`
- `0x1802f52a8`
- `0x1803079fc`
- `0x180308028`
- `0x18030827c`

## import_xrefs

- `ext-ms-win-appcompat-aepic-l1-1-0!PicFreeFileInfo` at `0x180088d62`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicFreeFileInfo` at `0x180088d62`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x180088a06`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x180088a2f`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x180088a06`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x180088a2f`

## string_xrefs

- `0x180088452`: `Compressed`
- `0x180088779`: `ReparsePointTag`
- `0x180088749`: `ReparsePointQueryInfoError`
- `0x18008880f`: `ReparsePointPrintName`
- `0x1800887bb`: `ReparsePointSubstituteName`
- `0x1800886b2`: `ReparsePoint`
- `0x180088663`: `ReadOnly`
- `0x180088b88`: `CompanyName`
- `0x1800888b4`: `SecurityDescriptor`
- `0x180088861`: `ReparsePointSecurityDescriptor`
- `0x18008897f`: `Temporary`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(
        __int64 a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        _BYTE *a7)
{
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // r9d
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  int v15; // r9d
  const wchar_t *v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rax
  void *v20; // rax
  _QWORD *v21; // rcx
  _BYTE v22[16]; // [rsp+30h] [rbp-C1h] BYREF
  __int128 v23; // [rsp+40h] [rbp-B1h] BYREF
  __int128 v24; // [rsp+50h] [rbp-A1h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-91h] BYREF
  _QWORD *v26; // [rsp+70h] [rbp-81h] BYREF
  __int64 v27; // [rsp+78h] [rbp-79h]
  int v28; // [rsp+80h] [rbp-71h] BYREF
  _QWORD v29[3]; // [rsp+88h] [rbp-69h] BYREF
  unsigned __int64 v30; // [rsp+A0h] [rbp-51h]
  _QWORD Src[6]; // [rsp+A8h] [rbp-49h] BYREF
  _QWORD v32[4]; // [rsp+D8h] [rbp-19h] BYREF

  v26 = a4;
  std::wstring::wstring(v29, *a2, a2[1]);
  *(_QWORD *)&v24 = L"FileSize";
  *((_QWORD *)&v24 + 1) = 8;
  *(_QWORD *)&v23 = L"info";
  *((_QWORD *)&v23 + 1) = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v23,
    (unsigned int)&v24,
    (unsigned int)&v26,
    0);
  v10 = Microsoft::Diagnostics::Utils::Time::FileTimeToPrecise8601((STRSAFE_LPWSTR)Src);
  *(_QWORD *)&v23 = L"LastModifiedTime";
  *((_QWORD *)&v23 + 1) = 16;
  *(_QWORD *)&v24 = L"info";
  *((_QWORD *)&v24 + 1) = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a1, &v24, &v23, v10);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  *((_QWORD *)&v24 + 1) = 4;
  v11 = a1;
  if ( a6 == -1 )
  {
    v22[0] = 1;
    v16 = L"InvalidFileAttributes";
    *((_QWORD *)&v23 + 1) = 21;
  }
  else
  {
    v22[0] = (a6 & 0x20) != 0;
    *(_QWORD *)&v23 = L"Archive";
    *((_QWORD *)&v23 + 1) = 7;
    *(_QWORD *)&v24 = L"info";
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 0x800) != 0;
    *(_QWORD *)&v23 = L"Compressed";
    *((_QWORD *)&v23 + 1) = 10;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 0x40) != 0;
    *(_QWORD *)&v23 = L"Device";
    *((_QWORD *)&v23 + 1) = 6;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 0x4000) != 0;
    *(_QWORD *)&v23 = L"Encrypted";
    *((_QWORD *)&v23 + 1) = 9;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 2) != 0;
    *(_QWORD *)&v23 = L"Hidden";
    *((_QWORD *)&v23 + 1) = 6;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 0x80) != 0;
    *(_QWORD *)&v23 = L"Normal";
    *((_QWORD *)&v23 + 1) = 6;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 0x2000) != 0;
    *(_QWORD *)&v23 = L"NotContentIndexed";
    *((_QWORD *)&v23 + 1) = 17;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 0x1000) != 0;
    *(_QWORD *)&v23 = L"Offline";
    *((_QWORD *)&v23 + 1) = 7;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = a6 & 1;
    *(_QWORD *)&v23 = L"ReadOnly";
    *((_QWORD *)&v23 + 1) = 8;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    if ( (a6 & 0x400) != 0 )
    {
      v22[0] = 1;
      *(_QWORD *)&v23 = L"ReparsePoint";
      *((_QWORD *)&v23 + 1) = 12;
      *(_QWORD *)&v24 = L"info";
      *((_QWORD *)&v24 + 1) = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
      v28 = 0;
      std::wstring::wstring(Src);
      std::wstring::wstring(v32);
      v23 = *(_OWORD *)a2;
      LODWORD(v26) = Microsoft::Diagnostics::Utils::FileSystem::GetReparsePointInfo(&v23, &v28, Src, v32);
      *((_QWORD *)&v24 + 1) = 4;
      if ( (int)v26 >= 0 )
      {
        *(_QWORD *)&v23 = L"ReparsePointTag";
        *((_QWORD *)&v23 + 1) = 15;
        *(_QWORD *)&v24 = L"info";
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
          a1,
          (unsigned int)&v24,
          (unsigned int)&v23,
          (unsigned int)&v28,
          0);
        v13 = Src;
        if ( Src[3] > 7u )
          v13 = (_QWORD *)Src[0];
        v26 = v13;
        *(_QWORD *)&v23 = L"ReparsePointSubstituteName";
        *((_QWORD *)&v23 + 1) = 26;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v14 = v32;
        if ( v32[3] > 7u )
          v14 = (_QWORD *)v32[0];
        v26 = v14;
        *(_QWORD *)&v23 = L"ReparsePointPrintName";
        *((_QWORD *)&v23 + 1) = 21;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        if ( a7[2] )
        {
          v24 = *(_OWORD *)a2;
          *(_QWORD *)&v23 = L"ReparsePointSecurityDescriptor";
          *((_QWORD *)&v23 + 1) = 30;
          LOBYTE(v15) = a3;
          Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(
            a1,
            (unsigned int)&v23,
            (unsigned int)&v24,
            v15,
            1);
        }
      }
      else
      {
        *(_QWORD *)&v23 = L"ReparsePointQueryInfoError";
        *((_QWORD *)&v23 + 1) = 26;
        *(_QWORD *)&v24 = L"info";
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(a1, &v24, &v23, &v26);
      }
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v32);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    }
    if ( a7[2] )
    {
      v24 = *(_OWORD *)a2;
      *(_QWORD *)&v23 = L"SecurityDescriptor";
      *((_QWORD *)&v23 + 1) = 18;
      LOBYTE(v12) = a3;
      Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(a1, (unsigned int)&v23, (unsigned int)&v24, v12, 0);
    }
    v22[0] = (a6 & 0x200) != 0;
    *(_QWORD *)&v23 = L"SparseFile";
    *((_QWORD *)&v23 + 1) = 10;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = (a6 & 4) != 0;
    *(_QWORD *)&v23 = L"System";
    *((_QWORD *)&v23 + 1) = 6;
    *(_QWORD *)&v24 = L"info";
    *((_QWORD *)&v24 + 1) = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v24, &v23, v22);
    v22[0] = BYTE1(a6) & 1;
    v16 = L"Temporary";
    *((_QWORD *)&v23 + 1) = 9;
    *((_QWORD *)&v24 + 1) = 4;
    v11 = a1;
  }
  *(_QWORD *)&v23 = v16;
  *(_QWORD *)&v24 = L"info";
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(v11, &v24, &v23, v22);
  if ( !a3 && !*a7 )
  {
    v25[0] = 0;
    v17 = v29;
    if ( v30 > 7 )
      v17 = (_QWORD *)v29[0];
    if ( (int)PicRetrieveFileInfo(v17, 16, v25) >= 0 )
      goto LABEL_25;
    v18 = v29;
    if ( v30 > 7 )
      v18 = (_QWORD *)v29[0];
    if ( (int)PicRetrieveFileInfo(v18, 0, v25) >= 0 )
    {
LABEL_25:
      v26 = v25;
      LOBYTE(v27) = 1;
      v21 = (_QWORD *)v25[0];
      if ( *(_QWORD *)(v25[0] + 72LL) )
      {
        *(_QWORD *)&v23 = L"Architecture";
        *((_QWORD *)&v23 + 1) = 12;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[4] )
      {
        *(_QWORD *)&v23 = L"BinFileVersion";
        *((_QWORD *)&v23 + 1) = 14;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[7] )
      {
        *(_QWORD *)&v23 = L"CompanyName";
        *((_QWORD *)&v23 + 1) = 11;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[2] )
      {
        *(_QWORD *)&v23 = L"FileDescription";
        *((_QWORD *)&v23 + 1) = 15;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( *v21 )
      {
        *(_QWORD *)&v23 = L"FileID";
        *((_QWORD *)&v23 + 1) = 6;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[3] )
      {
        *(_QWORD *)&v23 = L"FileVersion";
        *((_QWORD *)&v23 + 1) = 11;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[6] )
      {
        *(_QWORD *)&v23 = L"ProductName";
        *((_QWORD *)&v23 + 1) = 11;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[8] )
      {
        *(_QWORD *)&v23 = L"ProductVersion";
        *((_QWORD *)&v23 + 1) = 14;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[1] )
      {
        *(_QWORD *)&v23 = L"ProgramID";
        *((_QWORD *)&v23 + 1) = 9;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      if ( v21[5] )
      {
        *(_QWORD *)&v23 = L"VerLanguage";
        *((_QWORD *)&v23 + 1) = 11;
        *(_QWORD *)&v24 = L"info";
        *((_QWORD *)&v24 + 1) = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v24, &v23);
        v21 = (_QWORD *)v25[0];
      }
      PicFreeFileInfo(v21);
    }
    else
    {
      Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)Src);
      v19 = Microsoft::Diagnostics::WideStringStream::operator<<(Src);
      WORD1(v23) = 0;
      LOBYTE(v26) = 1;
      *(_WORD *)((char *)&v26 + 1) = BYTE1(v23);
      BYTE3(v26) = 0;
      HIDWORD(v26) = 2097153;
      v27 = 0;
      v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v19, &v26);
      Microsoft::Diagnostics::WideStringStream::operator<<(v20);
      *(_QWORD *)&v23 = L"Error";
      *((_QWORD *)&v23 + 1) = 5;
      *(_QWORD *)&v24 = L"info";
      *((_QWORD *)&v24 + 1) = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a1, &v24, &v23, Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    }
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v29);
}

```

## disassembly

```asm
0x180088304  mov     [rsp-8+arg_10], rbx
0x180088309  push    rbp
0x18008830a  push    rsi
0x18008830b  push    rdi
0x18008830c  push    r12
0x18008830e  push    r13
0x180088310  push    r14
0x180088312  push    r15
0x180088314  lea     rbp, [rsp-0Fh]
0x180088319  sub     rsp, 100h
0x180088320  mov     rax, cs:__security_cookie
0x180088327  xor     rax, rsp
0x18008832a  mov     [rbp+3Fh+var_38], rax
0x18008832e  mov     r15b, r8b
0x180088331  mov     r14, rdx
0x180088334  mov     rdi, rcx
0x180088337  mov     [rsp+130h+var_C0], r9
0x18008833c  mov     rbx, [rbp+3Fh+arg_20]
0x180088340  mov     r8, [rdx+8]
0x180088344  mov     rdx, [rdx]
0x180088347  lea     rcx, [rbp+3Fh+var_A8]
0x18008834b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x180088350  nop
0x180088351  lea     rax, aFilesize; "FileSize"
0x180088358  mov     qword ptr [rsp+130h+var_E0], rax
0x18008835d  mov     qword ptr [rsp+130h+var_E0+8], 8
0x180088366  lea     rsi, aInfo_0; "info"
0x18008836d  mov     qword ptr [rsp+130h+var_F0], rsi
0x180088372  mov     r12d, 4
0x180088378  mov     qword ptr [rsp+130h+var_F0+8], r12
0x18008837d  xor     r13d, r13d
0x180088380  mov     [rsp+130h+var_110], r13b
0x180088385  lea     r9, [rsp+130h+var_C0]
0x18008838a  lea     r8, [rsp+130h+var_E0]
0x18008838f  lea     rdx, [rsp+130h+var_F0]
0x180088394  mov     rcx, rdi
0x180088397  call    ??$WriteInfoElement@_K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_K_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(std::wstring_view,std::wstring_view,unsigned __int64 const &,bool)
0x18008839c  mov     rdx, rbx
0x18008839f  lea     rcx, [rbp+3Fh+Src]; pszDest
0x1800883a3  call    ?FileTimeToPrecise8601@Time@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; Microsoft::Diagnostics::Utils::Time::FileTimeToPrecise8601(unsigned __int64)
0x1800883a8  nop
0x1800883a9  lea     rcx, aLastmodifiedti; "LastModifiedTime"
0x1800883b0  mov     qword ptr [rsp+130h+var_F0], rcx
0x1800883b5  mov     qword ptr [rsp+130h+var_F0+8], 10h
0x1800883be  mov     qword ptr [rsp+130h+var_E0], rsi
0x1800883c3  mov     qword ptr [rsp+130h+var_E0+8], r12
0x1800883c8  mov     r9, rax
0x1800883cb  lea     r8, [rsp+130h+var_F0]
0x1800883d0  lea     rdx, [rsp+130h+var_E0]
0x1800883d5  mov     rcx, rdi
0x1800883d8  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x1800883dd  nop
0x1800883de  lea     rcx, [rbp+3Fh+Src]; this
0x1800883e2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800883e7  mov     r12, [rbp+3Fh+arg_30]
0x1800883eb  mov     esi, [rbp+3Fh+arg_28]
0x1800883ee  lea     ebx, [r13+1]
0x1800883f2  mov     qword ptr [rsp+130h+var_E0+8], 4
0x1800883fb  lea     r9, [rsp+130h+var_100]
0x180088400  lea     r8, [rsp+130h+var_F0]
0x180088405  lea     rdx, [rsp+130h+var_E0]
0x18008840a  mov     rcx, rdi
0x18008840d  cmp     esi, 0FFFFFFFFh
0x180088410  jz      loc_1800889AC
0x180088416  mov     eax, esi
0x180088418  shr     eax, 5
0x18008841b  and     al, bl
0x18008841d  mov     [rsp+130h+var_100], al
0x180088421  lea     rax, aArchive; "Archive"
0x180088428  mov     qword ptr [rsp+130h+var_F0], rax
0x18008842d  mov     qword ptr [rsp+130h+var_F0+8], 7
0x180088436  lea     rax, aInfo_0; "info"
0x18008843d  mov     qword ptr [rsp+130h+var_E0], rax
0x180088442  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x180088447  mov     eax, esi
0x180088449  shr     eax, 0Bh
0x18008844c  and     al, bl
0x18008844e  mov     [rsp+130h+var_100], al
0x180088452  lea     rax, aCompressed; "Compressed"
0x180088459  mov     qword ptr [rsp+130h+var_F0], rax
0x18008845e  mov     qword ptr [rsp+130h+var_F0+8], 0Ah
0x180088467  lea     rax, aInfo_0; "info"
0x18008846e  mov     qword ptr [rsp+130h+var_E0], rax
0x180088473  mov     qword ptr [rsp+130h+var_E0+8], 4
0x18008847c  lea     r9, [rsp+130h+var_100]
0x180088481  lea     r8, [rsp+130h+var_F0]
0x180088486  lea     rdx, [rsp+130h+var_E0]
0x18008848b  mov     rcx, rdi
0x18008848e  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x180088493  mov     eax, esi
0x180088495  shr     eax, 6
0x180088498  and     al, bl
0x18008849a  mov     [rsp+130h+var_100], al
0x18008849e  lea     rax, aDevice_0; "Device"
0x1800884a5  mov     qword ptr [rsp+130h+var_F0], rax
0x1800884aa  mov     qword ptr [rsp+130h+var_F0+8], 6
0x1800884b3  lea     rax, aInfo_0; "info"
0x1800884ba  mov     qword ptr [rsp+130h+var_E0], rax
0x1800884bf  mov     qword ptr [rsp+130h+var_E0+8], 4
0x1800884c8  lea     r9, [rsp+130h+var_100]
0x1800884cd  lea     r8, [rsp+130h+var_F0]
0x1800884d2  lea     rdx, [rsp+130h+var_E0]
0x1800884d7  mov     rcx, rdi
0x1800884da  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1800884df  mov     eax, esi
0x1800884e1  shr     eax, 0Eh
0x1800884e4  and     al, bl
0x1800884e6  mov     [rsp+130h+var_100], al
0x1800884ea  lea     rax, aEncrypted; "Encrypted"
0x1800884f1  mov     qword ptr [rsp+130h+var_F0], rax
0x1800884f6  mov     qword ptr [rsp+130h+var_F0+8], 9
0x1800884ff  lea     rax, aInfo_0; "info"
0x180088506  mov     qword ptr [rsp+130h+var_E0], rax
0x18008850b  mov     qword ptr [rsp+130h+var_E0+8], 4
0x180088514  lea     r9, [rsp+130h+var_100]
0x180088519  lea     r8, [rsp+130h+var_F0]
0x18008851e  lea     rdx, [rsp+130h+var_E0]
0x180088523  mov     rcx, rdi
0x180088526  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x18008852b  mov     eax, esi
0x18008852d  shr     eax, 1
0x18008852f  and     al, bl
0x180088531  mov     [rsp+130h+var_100], al
0x180088535  lea     rax, aHidden; "Hidden"
0x18008853c  mov     qword ptr [rsp+130h+var_F0], rax
0x180088541  mov     qword ptr [rsp+130h+var_F0+8], 6
0x18008854a  lea     rax, aInfo_0; "info"
0x180088551  mov     qword ptr [rsp+130h+var_E0], rax
0x180088556  mov     qword ptr [rsp+130h+var_E0+8], 4
0x18008855f  lea     r9, [rsp+130h+var_100]
0x180088564  lea     r8, [rsp+130h+var_F0]
0x180088569  lea     rdx, [rsp+130h+var_E0]
0x18008856e  mov     rcx, rdi
0x180088571  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x180088576  mov     eax, esi
0x180088578  shr     eax, 7
0x18008857b  and     al, bl
0x18008857d  mov     [rsp+130h+var_100], al
0x180088581  lea     rax, aNormal; "Normal"
0x180088588  mov     qword ptr [rsp+130h+var_F0], rax
0x18008858d  mov     qword ptr [rsp+130h+var_F0+8], 6
0x180088596  lea     rax, aInfo_0; "info"
0x18008859d  mov     qword ptr [rsp+130h+var_E0], rax
0x1800885a2  mov     qword ptr [rsp+130h+var_E0+8], 4
0x1800885ab  lea     r9, [rsp+130h+var_100]
0x1800885b0  lea     r8, [rsp+130h+var_F0]
0x1800885b5  lea     rdx, [rsp+130h+var_E0]
0x1800885ba  mov     rcx, rdi
0x1800885bd  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1800885c2  mov     eax, esi
0x1800885c4  shr     eax, 0Dh
0x1800885c7  and     al, bl
0x1800885c9  mov     [rsp+130h+var_100], al
0x1800885cd  lea     rax, aNotcontentinde; "NotContentIndexed"
0x1800885d4  mov     qword ptr [rsp+130h+var_F0], rax
0x1800885d9  mov     qword ptr [rsp+130h+var_F0+8], 11h
0x1800885e2  lea     rax, aInfo_0; "info"
0x1800885e9  mov     qword ptr [rsp+130h+var_E0], rax
0x1800885ee  mov     qword ptr [rsp+130h+var_E0+8], 4
0x1800885f7  lea     r9, [rsp+130h+var_100]
0x1800885fc  lea     r8, [rsp+130h+var_F0]
0x180088601  lea     rdx, [rsp+130h+var_E0]
0x180088606  mov     rcx, rdi
0x180088609  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x18008860e  mov     eax, esi
0x180088610  shr     eax, 0Ch
0x180088613  and     al, bl
0x180088615  mov     [rsp+130h+var_100], al
0x180088619  lea     rax, aOffline; "Offline"
0x180088620  mov     qword ptr [rsp+130h+var_F0], rax
0x180088625  mov     qword ptr [rsp+130h+var_F0+8], 7
0x18008862e  lea     rax, aInfo_0; "info"
0x180088635  mov     qword ptr [rsp+130h+var_E0], rax
0x18008863a  mov     qword ptr [rsp+130h+var_E0+8], 4
0x180088643  lea     r9, [rsp+130h+var_100]
0x180088648  lea     r8, [rsp+130h+var_F0]
0x18008864d  lea     rdx, [rsp+130h+var_E0]
0x180088652  mov     rcx, rdi
0x180088655  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x18008865a  mov     al, sil
0x18008865d  and     al, bl
0x18008865f  mov     [rsp+130h+var_100], al
0x180088663  lea     rax, aReadonly; "ReadOnly"
0x18008866a  mov     qword ptr [rsp+130h+var_F0], rax
0x18008866f  mov     qword ptr [rsp+130h+var_F0+8], 8
0x180088678  lea     rax, aInfo_0; "info"
0x18008867f  mov     qword ptr [rsp+130h+var_E0], rax
0x180088684  mov     qword ptr [rsp+130h+var_E0+8], 4
0x18008868d  lea     r9, [rsp+130h+var_100]
0x180088692  lea     r8, [rsp+130h+var_F0]
0x180088697  lea     rdx, [rsp+130h+var_E0]
0x18008869c  mov     rcx, rdi
0x18008869f  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1800886a4  bt      esi, 0Ah
0x1800886a8  jnb     loc_1800888A3
0x1800886ae  mov     [rsp+130h+var_100], bl
0x1800886b2  lea     rax, aReparsepoint; "ReparsePoint"
0x1800886b9  mov     qword ptr [rsp+130h+var_F0], rax
0x1800886be  mov     qword ptr [rsp+130h+var_F0+8], 0Ch
0x1800886c7  lea     rax, aInfo_0; "info"
0x1800886ce  mov     qword ptr [rsp+130h+var_E0], rax
0x1800886d3  mov     qword ptr [rsp+130h+var_E0+8], 4
0x1800886dc  lea     r9, [rsp+130h+var_100]
0x1800886e1  lea     r8, [rsp+130h+var_F0]
0x1800886e6  lea     rdx, [rsp+130h+var_E0]
0x1800886eb  mov     rcx, rdi
0x1800886ee  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1800886f3  mov     [rbp+3Fh+var_B0], r13d
0x1800886f7  lea     rcx, [rbp+3Fh+Src]; void *
0x1800886fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180088700  nop
0x180088701  lea     rcx, [rbp+3Fh+var_58]; void *
0x180088705  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008870a  nop
0x18008870b  movaps  xmm0, xmmword ptr [r14]
0x18008870f  movdqa  [rsp+130h+var_F0], xmm0
0x180088715  lea     r9, [rbp+3Fh+var_58]
0x180088719  lea     r8, [rbp+3Fh+Src]
0x18008871d  lea     rdx, [rbp+3Fh+var_B0]
0x180088721  lea     rcx, [rsp+130h+var_F0]
0x180088726  call    ?GetReparsePointInfo@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@2@Z; Microsoft::Diagnostics::Utils::FileSystem::GetReparsePointInfo(std::wstring_view,ulong &,std::wstring &,std::wstring &)
0x18008872b  mov     dword ptr [rsp+130h+var_C0], eax
0x18008872f  mov     qword ptr [rsp+130h+var_E0+8], 4
0x180088738  lea     r8, [rsp+130h+var_F0]
0x18008873d  lea     rdx, [rsp+130h+var_E0]
0x180088742  mov     rcx, rdi
0x180088745  test    eax, eax
0x180088747  jns     short loc_180088779
0x180088749  lea     rax, aReparsepointqu; "ReparsePointQueryInfoError"
0x180088750  mov     qword ptr [rsp+130h+var_F0], rax
0x180088755  mov     qword ptr [rsp+130h+var_F0+8], 1Ah
0x18008875e  lea     rax, aInfo_0; "info"
0x180088765  mov     qword ptr [rsp+130h+var_E0], rax
0x18008876a  lea     r9, [rsp+130h+var_C0]
0x18008876f  call    ??$WriteInfoElement@J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBJ_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(std::wstring_view,std::wstring_view,long const &,bool)
0x180088774  jmp     loc_180088890
0x180088779  lea     rax, aReparsepointta; "ReparsePointTag"
0x180088780  mov     qword ptr [rsp+130h+var_F0], rax
0x180088785  mov     qword ptr [rsp+130h+var_F0+8], 0Fh
0x18008878e  lea     rax, aInfo_0; "info"
0x180088795  mov     qword ptr [rsp+130h+var_E0], rax
0x18008879a  mov     [rsp+130h+var_110], r13b
0x18008879f  lea     r9, [rbp+3Fh+var_B0]
0x1800887a3  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1800887a8  lea     rax, [rbp+3Fh+Src]
0x1800887ac  cmp     [rbp+3Fh+var_70], 7
0x1800887b1  cmova   rax, [rbp+3Fh+Src]
0x1800887b6  mov     [rsp+130h+var_C0], rax
0x1800887bb  lea     rax, aReparsepointsu; "ReparsePointSubstituteName"
0x1800887c2  mov     qword ptr [rsp+130h+var_F0], rax
0x1800887c7  mov     qword ptr [rsp+130h+var_F0+8], 1Ah
0x1800887d0  lea     rax, aInfo_0; "info"
0x1800887d7  mov     qword ptr [rsp+130h+var_E0], rax
0x1800887dc  mov     qword ptr [rsp+130h+var_E0+8], 4
0x1800887e5  lea     r9, [rsp+130h+var_C0]
0x1800887ea  lea     r8, [rsp+130h+var_F0]
0x1800887ef  lea     rdx, [rsp+130h+var_E0]
0x1800887f4  mov     rcx, rdi
0x1800887f7  call    ??$WriteInfoElement@PEA_W@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBQEA_W_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(std::wstring_view,std::wstring_view,wchar_t * const &,bool)
0x1800887fc  lea     rax, [rbp+3Fh+var_58]
0x180088800  cmp     [rbp+3Fh+var_40], 7
0x180088805  cmova   rax, [rbp+3Fh+var_58]
0x18008880a  mov     [rsp+130h+var_C0], rax
0x18008880f  lea     rax, aReparsepointpr; "ReparsePointPrintName"
0x180088816  mov     qword ptr [rsp+130h+var_F0], rax
0x18008881b  mov     qword ptr [rsp+130h+var_F0+8], 15h
0x180088824  lea     rax, aInfo_0; "info"
0x18008882b  mov     qword ptr [rsp+130h+var_E0], rax
0x180088830  mov     qword ptr [rsp+130h+var_E0+8], 4
0x180088839  lea     r9, [rsp+130h+var_C0]
0x18008883e  lea     r8, [rsp+130h+var_F0]
0x180088843  lea     rdx, [rsp+130h+var_E0]
0x180088848  mov     rcx, rdi
0x18008884b  call    ??$WriteInfoElement@PEA_W@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBQEA_W_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(std::wstring_view,std::wstring_view,wchar_t * const &,bool)
0x180088850  cmp     [r12+2], r13b
0x180088855  jz      short loc_180088890
0x180088857  movaps  xmm0, xmmword ptr [r14]
0x18008885b  movdqa  [rsp+130h+var_E0], xmm0
0x180088861  lea     rax, aReparsepointse; "ReparsePointSecurityDescriptor"
0x180088868  mov     qword ptr [rsp+130h+var_F0], rax
0x18008886d  mov     qword ptr [rsp+130h+var_F0+8], 1Eh
0x180088876  mov     [rsp+130h+var_110], bl
0x18008887a  mov     r9b, r15b
0x18008887d  lea     r8, [rsp+130h+var_E0]
0x180088882  lea     rdx, [rsp+130h+var_F0]
0x180088887  mov     rcx, rdi
0x18008888a  call    ?QuerySecurity@GetFileInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_N2@Z; Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(Microsoft::Diagnostics::XmlWriterFacade &,std::wstring_view,std::wstring_view,bool,bool)
0x18008888f  nop
0x180088890  lea     rcx, [rbp+3Fh+var_58]; this
0x180088894  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180088899  nop
0x18008889a  lea     rcx, [rbp+3Fh+Src]; this
0x18008889e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800888a3  cmp     [r12+2], r13b
0x1800888a8  jz      short loc_1800888E3
0x1800888aa  movaps  xmm0, xmmword ptr [r14]
0x1800888ae  movdqa  [rsp+130h+var_E0], xmm0
0x1800888b4  lea     rax, aSecuritydescri; "SecurityDescriptor"
0x1800888bb  mov     qword ptr [rsp+130h+var_F0], rax
0x1800888c0  mov     qword ptr [rsp+130h+var_F0+8], 12h
  ... truncated ...
```
