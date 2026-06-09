# GetSystemConfigInfo(mlib::XmlStream &)

- ea: `0x14002ac4c`
- end: `0x14002b888`
- name: `?GetSystemConfigInfo@@YAXAEAVXmlStream@mlib@@@Z`
- size: `3132`
- prototype: `void __fastcall(struct mlib::XmlStream *this)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d91c`
- `0x14002b890`

## callees

- `0x140003611`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140004650`
- `0x140005d78`
- `0x140005e5c`
- `0x140005f10`
- `0x140008178`
- `0x1400085b4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016480`
- `0x140016524`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x140019bd8`
- `0x140021b58`
- `0x140021da8`
- `0x14002ac4c`
- `0x14004c884`
- `0x140053590`
- `0x140053900`
- `0x140056d9c`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14002b16b`
- `KERNEL32!GetProcAddress` at `0x14002b16b`
- `KERNEL32!LoadLibraryW` at `0x14002b156`
- `KERNEL32!LoadLibraryW` at `0x14002b156`
- `KERNEL32!GetLastError` at `0x14002b176`
- `KERNEL32!GetLastError` at `0x14002b176`
- `KERNEL32!SetLastError` at `0x14002b187`
- `KERNEL32!SetLastError` at `0x14002b187`
- `ntdll!RtlGetVersion` at `0x14002ae0e`
- `ntdll!RtlGetVersion` at `0x14002ae0e`

## string_xrefs

- `0x14002acec`: `ComputerName`
- `0x14002ad63`: `ComputerName`
- `0x14002b14f`: `ntdll.dll`
- `0x14002b766`: `HistoryVersionWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall GetSystemConfigInfo(__int64 **this)
{
  __int64 v2; // rax
  __int64 *v3; // rax
  __int64 *v4; // rax
  mlib::XmlStream *v5; // rbx
  const wchar_t *v6; // rdx
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *v9; // rax
  __int64 *v10; // rax
  DWORD dwMajorVersion; // ebx
  const wchar_t *v12; // rdx
  __int64 *v13; // rcx
  __int64 *v14; // rax
  __int64 *v15; // rax
  DWORD dwMinorVersion; // ebx
  const wchar_t *v17; // rdx
  __int64 *v18; // rcx
  __int64 *v19; // rax
  __int64 *v20; // rax
  DWORD dwBuildNumber; // ebx
  const wchar_t *v22; // rdx
  __int64 *v23; // rcx
  __int64 *v24; // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int64 *v27; // rax
  int v28; // ebx
  const wchar_t *v29; // rdx
  __int64 *v30; // rcx
  __int64 *v31; // rax
  __int64 *v32; // rax
  mlib::XmlStream *v33; // rbx
  const wchar_t *v34; // rdx
  __int64 *v35; // rcx
  __int64 *v36; // rax
  __int64 *v37; // rax
  mlib::XmlStream *v38; // rbx
  mlib::XmlStream *v39; // rax
  __int64 v40; // rbx
  const wchar_t *v41; // rdx
  __int64 *v42; // rcx
  __int64 *v43; // rax
  __int64 *v44; // rax
  mlib::XmlStream *v45; // rbx
  const wchar_t *v46; // rdx
  __int64 *v47; // rcx
  __int64 *v48; // rax
  const wchar_t *v49; // rdx
  __int64 *v50; // rcx
  __int64 *v51; // rax
  __int64 *v52; // rax
  const wchar_t *v53; // rdx
  __int64 *v54; // rcx
  __int64 *v55; // rax
  unsigned __int64 *v56; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 *v57; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v58; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 *v59; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 *v60; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 *v61; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 *v62; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+80h] [rbp-80h]
  __int64 v66; // [rsp+88h] [rbp-78h]
  _QWORD v67[9]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v68; // [rsp+D8h] [rbp-28h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF

  if ( App::s_Verbose )
  {
    v2 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
    v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           (__int64 *)(v2 + 240),
           (__int64)L"> Gathering System Information");
    std::endl(v3);
  }
  if ( App::s_IsPrivateBld || App::s_DumpComputerName )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      (__int64)&v61,
      3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v60,
      L"ComputerName");
    if ( *((_DWORD *)this + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
    *((_DWORD *)this + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)this);
    v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v4, &v60);
    ++*((_DWORD *)this + 3);
    *((_BYTE *)this + 17) = 0;
    v59 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v59,
      (__int64)v61);
    v5 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
           (mlib::XmlStream *)this,
           &v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v57,
      L"ComputerName");
    --*((_DWORD *)v5 + 3);
    if ( *((_DWORD *)v5 + 2) == 1 )
    {
      if ( !*((_BYTE *)v5 + 17) )
        mlib::XmlStream::Indent(v5);
      *((_BYTE *)v5 + 17) = 0;
      v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v5, (__int64)L"</");
      v7 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v8, &v57);
      v6 = L">";
    }
    else
    {
      if ( *((_DWORD *)v5 + 2) != 2 )
      {
LABEL_14:
        *((_DWORD *)v5 + 2) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v57);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
        std::basic_ostream<unsigned short>::flush(*this);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v61);
        goto LABEL_15;
      }
      v6 = L"/>";
      v7 = *(__int64 **)v5;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, (__int64)v6);
    goto LABEL_14;
  }
LABEL_15:
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  RtlGetVersion(&VersionInformation);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"OSVersion");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v9, &v56);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v58,
    L"Major");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v10, &v58);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  dwMajorVersion = VersionInformation.dwMajorVersion;
  mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
  std::basic_ostream<unsigned short>::operator<<((__int64)*this, dwMajorVersion);
  mlib::XmlStream::AfterText((mlib::XmlStream *)this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v62,
    L"Major");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)this);
    *((_BYTE *)this + 17) = 0;
    v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
    v13 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v14, &v62);
    v12 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_26;
    v12 = L"/>";
    v13 = *this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, (__int64)v12);
LABEL_26:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &si128,
    L"Minor");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v15,
    (unsigned __int64 **)&si128);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  dwMinorVersion = VersionInformation.dwMinorVersion;
  mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
  std::basic_ostream<unsigned short>::operator<<((__int64)*this, dwMinorVersion);
  mlib::XmlStream::AfterText((mlib::XmlStream *)this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v59,
    L"Minor");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)this);
    *((_BYTE *)this + 17) = 0;
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
    v18 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v19, &v59);
    v17 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_35;
    v17 = L"/>";
    v18 = *this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, (__int64)v17);
LABEL_35:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v57,
    L"Build");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v20, &v57);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  dwBuildNumber = VersionInformation.dwBuildNumber;
  mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
  std::basic_ostream<unsigned short>::operator<<((__int64)*this, dwBuildNumber);
  mlib::XmlStream::AfterText((mlib::XmlStream *)this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v61,
    L"Build");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)this);
    *((_BYTE *)this + 17) = 0;
    v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
    v23 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v24, &v61);
    v22 = L">";
    goto LABEL_43;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    v22 = L"/>";
    v23 = *this;
LABEL_43:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, (__int64)v22);
  }
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v61);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v57);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&si128);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v62);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v58);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  v64 = 0;
  v65 = 0;
  v66 = 0;
  mlib::WinBrand::LoadLibraryW((mlib::WinBrand *)&v64);
  LibraryW = LoadLibraryW(L"ntdll.dll");
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "RtlGetProductInfo")) != 0 )
  {
    LODWORD(v60) = 0;
    if ( ((unsigned __int8 (__fastcall *)(__int64, __int64, __int64, __int64, unsigned __int64 **))ProcAddress)(
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           &v60) )
    {
      goto LABEL_49;
    }
  }
  else
  {
    GetLastError();
    LODWORD(v60) = 0;
    SetLastError(0x32u);
  }
  LODWORD(v60) = 0;
LABEL_49:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v58,
    L"ProductType");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v27, &v58);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v28 = (int)v60;
  mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
  std::basic_ostream<unsigned short>::operator<<((__int64)*this, v28);
  mlib::XmlStream::AfterText((mlib::XmlStream *)this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"ProductType");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)this);
    *((_BYTE *)this + 17) = 0;
    v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
    v30 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v31, &v56);
    v29 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_58;
    v29 = L"/>";
    v30 = *this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, (__int64)v29);
LABEL_58:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v58);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>((__int64 *)&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion");
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &si128.m128i_i64[1],
    (__int64)v56);
  mlib::RegistryBaseKey::cleanup((_QWORD **)&si128.m128i_i64[1]);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"ProductName");
  mlib::RstringReg::RstringReg(v67);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  if ( (unsigned int)mlib::MRegistryRWBase::read((mlib::MRegistryRWBase *)v67) )
    mlib::WinBrand::BrandingLoadStringZ(&v64, 13, &v59);
  else
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v59,
      v68);
  mlib::RstringReg::~RstringReg((mlib::RstringReg *)v67);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v58,
    L"ProductName");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v32, &v58);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v57 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v57,
    (__int64)v59);
  v33 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
          (mlib::XmlStream *)this,
          &v57);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"ProductName");
  --*((_DWORD *)v33 + 3);
  if ( *((_DWORD *)v33 + 2) == 1 )
  {
    if ( !*((_BYTE *)v33 + 17) )
      mlib::XmlStream::Indent(v33);
    *((_BYTE *)v33 + 17) = 0;
    v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v33, (__int64)L"</");
    v35 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v36, &v56);
    v34 = L">";
  }
  else
  {
    if ( *((_DWORD *)v33 + 2) != 2 )
      goto LABEL_70;
    v34 = L"/>";
    v35 = *(__int64 **)v33;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, (__int64)v34);
LABEL_70:
  *((_DWORD *)v33 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v58);
  v64 = 0;
  v65 = 0;
  v66 = 0;
  mlib::WinBrand::LoadLibraryW((mlib::WinBrand *)&v64);
  mlib::WinBrand::BrandingLoadStringZ(&v64, 12, &v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v58,
    L"OSName");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v37, &v58);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v38 = (mlib::XmlStream *)mlib::XmlStream::operator<<<void>((__int64)this, (void (*)(void))mlib::BeginCData);
  v57 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v57,
    (__int64)v59);
  v39 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
          v38,
          &v57);
  v40 = mlib::XmlStream::operator<<<void>((__int64)v39, (void (*)(void))mlib::EndCData);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"OSName");
  --*(_DWORD *)(v40 + 12);
  if ( *(_DWORD *)(v40 + 8) == 1 )
  {
    if ( !*(_BYTE *)(v40 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)v40);
    *(_BYTE *)(v40 + 17) = 0;
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v40, (__int64)L"</");
    v42 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43, &v56);
    v41 = L">";
  }
  else
  {
    if ( *(_DWORD *)(v40 + 8) != 2 )
      goto LABEL_79;
    v41 = L"/>";
    v42 = *(__int64 **)v40;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, (__int64)v41);
LABEL_79:
  *(_DWORD *)(v40 + 8) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v58);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"BuildLab");
  mlib::RstringReg::RstringReg(v67);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  if ( (unsigned int)mlib::MRegistryRWBase::read((mlib::MRegistryRWBase *)v67) )
    goto LABEL_90;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v58,
    L"BuildLab");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v44, &v58);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v57 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v57,
    v68);
  v45 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(
          (mlib::XmlStream *)this,
          &v57);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"BuildLab");
  --*((_DWORD *)v45 + 3);
  if ( *((_DWORD *)v45 + 2) == 1 )
  {
    if ( !*((_BYTE *)v45 + 17) )
      mlib::XmlStream::Indent(v45);
    *((_BYTE *)v45 + 17) = 0;
    v48 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(__int64 **)v45, (__int64)L"</");
    v47 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v48, &v56);
    v46 = L">";
    goto LABEL_88;
  }
  if ( *((_DWORD *)v45 + 2) == 2 )
  {
    v46 = L"/>";
    v47 = *(__int64 **)v45;
LABEL_88:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, (__int64)v46);
  }
  *((_DWORD *)v45 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v58);
LABEL_90:
  mlib::RstringReg::~RstringReg((mlib::RstringReg *)v67);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"OSVersion");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)this);
    *((_BYTE *)this + 17) = 0;
    v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
    v50 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, &v56);
    v49 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_97;
    v49 = L"/>";
    v50 = *this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, (__int64)v49);
LABEL_97:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&si128.m128i_u64[1]);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v59);
  LODWORD(v60) = 0;
  if ( (int)DataStoreReader::GetHistoryVersion(L"HistoryVersionWrite", (unsigned int *)&v60) < 0 )
    return;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v58,
    L"HistoryVersion");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)this);
  v52 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v52, &v58);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::XmlStream::BeforeText((mlib::XmlStream *)this);
  std::basic_ostream<unsigned short>::operator<<((__int64)*this, (int)v60);
  mlib::XmlStream::AfterText((mlib::XmlStream *)this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v56,
    L"HistoryVersion");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)this);
    *((_BYTE *)this + 17) = 0;
    v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*this, (__int64)L"</");
    v54 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, &v56);
    v53 = L">";
    goto LABEL_106;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    v53 = L"/>";
    v54 = *this;
LABEL_106:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, (__int64)v53);
  }
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v56);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v58);
}

```

## disassembly

```asm
0x14002ac4c  push    rbp
0x14002ac4e  push    rbx
0x14002ac4f  push    rsi
0x14002ac50  push    rdi
0x14002ac51  push    r12
0x14002ac53  push    r13
0x14002ac55  push    r14
0x14002ac57  push    r15
0x14002ac59  lea     rbp, [rsp-128h]
0x14002ac61  sub     rsp, 228h
0x14002ac68  mov     rax, cs:__security_cookie
0x14002ac6f  xor     rax, rsp
0x14002ac72  mov     [rbp+160h+var_50], rax
0x14002ac79  mov     rdi, rcx
0x14002ac7c  xor     esi, esi
0x14002ac7e  cmp     cs:?s_Verbose@App@@2_NA, sil; bool App::s_Verbose
0x14002ac85  jz      short loc_14002ACAE
0x14002ac87  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14002ac8e  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ac93  lea     rcx, [rax+0F0h]
0x14002ac9a  lea     rdx, aGatheringSyste; "> Gathering System Information"
0x14002aca1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002aca6  mov     rcx, rax
0x14002aca9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14002acae  mov     r15d, 2
0x14002acb4  lea     r14, asc_14012B480; ">"
0x14002acbb  lea     r12d, [r15-1]
0x14002acbf  lea     r13, asc_14012B488; "/>"
0x14002acc6  cmp     cs:?s_IsPrivateBld@App@@2_NA, sil; bool App::s_IsPrivateBld
0x14002accd  jnz     short loc_14002ACDC
0x14002accf  cmp     cs:?s_DumpComputerName@App@@2_NA, sil; bool App::s_DumpComputerName
0x14002acd6  jz      loc_14002ADF2
0x14002acdc  mov     edx, 3
0x14002ace1  lea     rcx, [rsp+260h+var_208]
0x14002ace6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@W4CreationID@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::CreationID)
0x14002aceb  nop
0x14002acec  lea     rdx, aComputername; "ComputerName"
0x14002acf3  lea     rcx, [rsp+260h+var_210]
0x14002acf8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002acfd  nop
0x14002acfe  cmp     [rdi+8], r15d
0x14002ad02  jnz     short loc_14002AD0F
0x14002ad04  mov     rdx, r14
0x14002ad07  mov     rcx, [rdi]
0x14002ad0a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ad0f  mov     [rdi+8], r15d
0x14002ad13  mov     rcx, rdi; this
0x14002ad16  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ad1b  lea     rdx, asc_14012B484; "<"
0x14002ad22  mov     rcx, [rdi]
0x14002ad25  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ad2a  mov     rcx, rax
0x14002ad2d  lea     rdx, [rsp+260h+var_210]
0x14002ad32  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002ad37  add     [rdi+0Ch], r12d
0x14002ad3b  mov     [rdi+11h], sil
0x14002ad3f  mov     [rsp+260h+var_218], rsi
0x14002ad44  mov     rdx, [rsp+260h+var_208]
0x14002ad49  lea     rcx, [rsp+260h+var_218]
0x14002ad4e  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002ad53  lea     rdx, [rsp+260h+var_218]
0x14002ad58  mov     rcx, rdi
0x14002ad5b  call    ??$?6V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@XmlStream@mlib@@QEAAAEAV01@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::XmlStream::operator<<<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x14002ad60  mov     rbx, rax
0x14002ad63  lea     rdx, aComputername; "ComputerName"
0x14002ad6a  lea     rcx, [rsp+260h+var_228]
0x14002ad6f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ad74  nop
0x14002ad75  dec     dword ptr [rbx+0Ch]
0x14002ad78  mov     eax, [rbx+8]
0x14002ad7b  sub     eax, 1
0x14002ad7e  jz      short loc_14002AD8D
0x14002ad80  cmp     eax, 1
0x14002ad83  jnz     short loc_14002ADC6
0x14002ad85  mov     rdx, r13
0x14002ad88  mov     rcx, [rbx]
0x14002ad8b  jmp     short loc_14002ADC1
0x14002ad8d  cmp     [rbx+11h], sil
0x14002ad91  jnz     short loc_14002AD9B
0x14002ad93  mov     rcx, rbx; this
0x14002ad96  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ad9b  mov     [rbx+11h], sil
0x14002ad9f  lea     rdx, asc_14012B490; "</"
0x14002ada6  mov     rcx, [rbx]
0x14002ada9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002adae  mov     rcx, rax
0x14002adb1  lea     rdx, [rsp+260h+var_228]
0x14002adb6  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002adbb  mov     rcx, rax
0x14002adbe  mov     rdx, r14
0x14002adc1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002adc6  mov     [rbx+8], r12d
0x14002adca  lea     rcx, [rsp+260h+var_228]
0x14002adcf  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002add4  nop
0x14002add5  lea     rcx, [rsp+260h+var_210]
0x14002adda  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002addf  mov     rcx, [rdi]
0x14002ade2  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x14002ade7  nop
0x14002ade8  lea     rcx, [rsp+260h+var_208]
0x14002aded  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002adf2  xor     edx, edx; Val
0x14002adf4  mov     r8d, 118h; Size
0x14002adfa  lea     rcx, [rbp+160h+VersionInformation.dwMajorVersion]; void *
0x14002adfe  call    memset_0
0x14002ae03  mov     [rbp+160h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14002ae0a  lea     rcx, [rbp+160h+VersionInformation]; lpVersionInformation
0x14002ae0e  call    cs:__imp_RtlGetVersion
0x14002ae14  lea     rdx, aOsversion; "OSVersion"
0x14002ae1b  lea     rcx, [rsp+260h+var_230]
0x14002ae20  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ae25  nop
0x14002ae26  cmp     [rdi+8], r15d
0x14002ae2a  jnz     short loc_14002AE37
0x14002ae2c  mov     rdx, r14
0x14002ae2f  mov     rcx, [rdi]
0x14002ae32  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ae37  mov     [rdi+8], r15d
0x14002ae3b  mov     rcx, rdi; this
0x14002ae3e  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ae43  lea     rdx, asc_14012B484; "<"
0x14002ae4a  mov     rcx, [rdi]
0x14002ae4d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ae52  mov     rcx, rax
0x14002ae55  lea     rdx, [rsp+260h+var_230]
0x14002ae5a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002ae5f  add     [rdi+0Ch], r12d
0x14002ae63  mov     [rdi+11h], sil
0x14002ae67  lea     rdx, aMajor; "Major"
0x14002ae6e  lea     rcx, [rsp+260h+var_220]
0x14002ae73  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ae78  nop
0x14002ae79  cmp     [rdi+8], r15d
0x14002ae7d  jnz     short loc_14002AE8A
0x14002ae7f  mov     rdx, r14
0x14002ae82  mov     rcx, [rdi]
0x14002ae85  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ae8a  mov     [rdi+8], r15d
0x14002ae8e  mov     rcx, rdi; this
0x14002ae91  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ae96  lea     rdx, asc_14012B484; "<"
0x14002ae9d  mov     rcx, [rdi]
0x14002aea0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002aea5  mov     rcx, rax
0x14002aea8  lea     rdx, [rsp+260h+var_220]
0x14002aead  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002aeb2  add     [rdi+0Ch], r12d
0x14002aeb6  mov     [rdi+11h], sil
0x14002aeba  mov     ebx, [rbp+160h+VersionInformation.dwMajorVersion]
0x14002aebd  mov     rcx, rdi; this
0x14002aec0  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14002aec5  mov     edx, ebx
0x14002aec7  mov     rcx, [rdi]
0x14002aeca  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14002aecf  mov     rcx, rdi; this
0x14002aed2  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14002aed7  lea     rdx, aMajor; "Major"
0x14002aede  lea     rcx, [rsp+260h+var_200]
0x14002aee3  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002aee8  nop
0x14002aee9  dec     dword ptr [rdi+0Ch]
0x14002aeec  mov     ecx, [rdi+8]
0x14002aeef  sub     ecx, 1
0x14002aef2  jz      short loc_14002AF01
0x14002aef4  cmp     ecx, 1
0x14002aef7  jnz     short loc_14002AF3A
0x14002aef9  mov     rdx, r13
0x14002aefc  mov     rcx, [rdi]
0x14002aeff  jmp     short loc_14002AF35
0x14002af01  cmp     [rdi+11h], sil
0x14002af05  jnz     short loc_14002AF0F
0x14002af07  mov     rcx, rdi; this
0x14002af0a  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002af0f  mov     [rdi+11h], sil
0x14002af13  lea     rdx, asc_14012B490; "</"
0x14002af1a  mov     rcx, [rdi]
0x14002af1d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af22  mov     rcx, rax
0x14002af25  lea     rdx, [rsp+260h+var_200]
0x14002af2a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002af2f  mov     rcx, rax
0x14002af32  mov     rdx, r14
0x14002af35  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af3a  mov     [rdi+8], r12d
0x14002af3e  lea     rdx, aMinor; "Minor"
0x14002af45  lea     rcx, [rsp+260h+var_1F8]
0x14002af4a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002af4f  nop
0x14002af50  cmp     [rdi+8], r15d
0x14002af54  jnz     short loc_14002AF61
0x14002af56  mov     rdx, r14
0x14002af59  mov     rcx, [rdi]
0x14002af5c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af61  mov     [rdi+8], r15d
0x14002af65  mov     rcx, rdi; this
0x14002af68  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002af6d  lea     rdx, asc_14012B484; "<"
0x14002af74  mov     rcx, [rdi]
0x14002af77  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af7c  mov     rcx, rax
0x14002af7f  lea     rdx, [rsp+260h+var_1F8]
0x14002af84  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002af89  add     [rdi+0Ch], r12d
0x14002af8d  mov     [rdi+11h], sil
0x14002af91  mov     ebx, [rbp+160h+VersionInformation.dwMinorVersion]
0x14002af94  mov     rcx, rdi; this
0x14002af97  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14002af9c  mov     edx, ebx
0x14002af9e  mov     rcx, [rdi]
0x14002afa1  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14002afa6  mov     rcx, rdi; this
0x14002afa9  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14002afae  lea     rdx, aMinor; "Minor"
0x14002afb5  lea     rcx, [rsp+260h+var_218]
0x14002afba  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002afbf  nop
0x14002afc0  dec     dword ptr [rdi+0Ch]
0x14002afc3  mov     ecx, [rdi+8]
0x14002afc6  sub     ecx, 1
0x14002afc9  jz      short loc_14002AFD8
0x14002afcb  cmp     ecx, 1
0x14002afce  jnz     short loc_14002B011
0x14002afd0  mov     rdx, r13
0x14002afd3  mov     rcx, [rdi]
0x14002afd6  jmp     short loc_14002B00C
0x14002afd8  cmp     [rdi+11h], sil
0x14002afdc  jnz     short loc_14002AFE6
0x14002afde  mov     rcx, rdi; this
0x14002afe1  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002afe6  mov     [rdi+11h], sil
0x14002afea  lea     rdx, asc_14012B490; "</"
0x14002aff1  mov     rcx, [rdi]
0x14002aff4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002aff9  mov     rcx, rax
0x14002affc  lea     rdx, [rsp+260h+var_218]
0x14002b001  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002b006  mov     rcx, rax
0x14002b009  mov     rdx, r14
0x14002b00c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b011  mov     [rdi+8], r12d
0x14002b015  lea     rdx, aBuild_0; "Build"
0x14002b01c  lea     rcx, [rsp+260h+var_228]
0x14002b021  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002b026  nop
0x14002b027  cmp     [rdi+8], r15d
0x14002b02b  jnz     short loc_14002B038
0x14002b02d  mov     rdx, r14
0x14002b030  mov     rcx, [rdi]
0x14002b033  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b038  mov     [rdi+8], r15d
0x14002b03c  mov     rcx, rdi; this
0x14002b03f  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002b044  lea     rdx, asc_14012B484; "<"
0x14002b04b  mov     rcx, [rdi]
0x14002b04e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b053  mov     rcx, rax
0x14002b056  lea     rdx, [rsp+260h+var_228]
0x14002b05b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002b060  add     [rdi+0Ch], r12d
0x14002b064  mov     [rdi+11h], sil
0x14002b068  mov     ebx, [rbp+160h+VersionInformation.dwBuildNumber]
0x14002b06b  mov     rcx, rdi; this
0x14002b06e  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14002b073  mov     edx, ebx
0x14002b075  mov     rcx, [rdi]
0x14002b078  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14002b07d  mov     rcx, rdi; this
0x14002b080  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14002b085  lea     rdx, aBuild_0; "Build"
0x14002b08c  lea     rcx, [rsp+260h+var_208]
0x14002b091  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002b096  nop
0x14002b097  dec     dword ptr [rdi+0Ch]
0x14002b09a  mov     ecx, [rdi+8]
0x14002b09d  sub     ecx, 1
0x14002b0a0  jz      short loc_14002B0AF
0x14002b0a2  cmp     ecx, 1
0x14002b0a5  jnz     short loc_14002B0E8
0x14002b0a7  mov     rdx, r13
0x14002b0aa  mov     rcx, [rdi]
0x14002b0ad  jmp     short loc_14002B0E3
0x14002b0af  cmp     [rdi+11h], sil
0x14002b0b3  jnz     short loc_14002B0BD
0x14002b0b5  mov     rcx, rdi; this
0x14002b0b8  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002b0bd  mov     [rdi+11h], sil
0x14002b0c1  lea     rdx, asc_14012B490; "</"
0x14002b0c8  mov     rcx, [rdi]
0x14002b0cb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b0d0  mov     rcx, rax
0x14002b0d3  lea     rdx, [rsp+260h+var_208]
0x14002b0d8  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002b0dd  mov     rcx, rax
0x14002b0e0  mov     rdx, r14
0x14002b0e3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b0e8  mov     [rdi+8], r12d
0x14002b0ec  lea     rcx, [rsp+260h+var_208]
0x14002b0f1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002b0f6  nop
  ... truncated ...
```
