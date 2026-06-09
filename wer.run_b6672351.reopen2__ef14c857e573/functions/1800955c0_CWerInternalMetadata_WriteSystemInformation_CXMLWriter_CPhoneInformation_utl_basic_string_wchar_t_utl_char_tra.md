# CWerInternalMetadata::WriteSystemInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800955c0`
- end: `0x180095e04`
- name: `?WriteSystemInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `2116`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180093a2c`

## callees

- `0x180004c64`
- `0x18000a3ac`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000db80`
- `0x18000e31c`
- `0x180010280`
- `0x18001be50`
- `0x18002a0f4`
- `0x18003a7f0`
- `0x180043324`
- `0x180043468`
- `0x180049fb0`
- `0x180053300`
- `0x180053d3c`
- `0x1800955c0`
- `0x180098870`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180095bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180095bc3`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180095c5e`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180095c5e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180095af7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180095af7`

## string_xrefs

- `0x180095d6f`: `WriteSystemInformation found XmlWriter == NULL || !XmlWriter->IsInitialized() || PhoneInformation == NULL\n`
- `0x18009597b`: `SystemProductName`
- `0x180095a26`: `InstallDate`
- `0x180095a8d`: `OSInstallDate`
- `0x180095b7e`: `OSInstallTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWerInternalMetadata::WriteSystemInformation(_QWORD *a1, _DWORD *a2, void *a3)
{
  int MachineId; // ebx
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int DWORD; // eax
  int v13; // r9d
  int v14; // r9d
  int v15; // r9d
  unsigned int Bias; // r9d
  __int64 v17; // r8
  __int64 v18; // r9
  const wchar_t *v19; // rdx
  int v20; // r9d
  bool *v22; // [rsp+20h] [rbp-E0h]
  bool v23; // [rsp+28h] [rbp-D8h]
  bool v24[8]; // [rsp+28h] [rbp-D8h]
  bool v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  _OWORD v29[2]; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v36; // [rsp+E0h] [rbp-20h]
  _QWORD v37[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v38[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v39[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v40[4]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v41[4]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v42[4]; // [rsp+198h] [rbp+98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1B8h] [rbp+B8h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+1D0h] [rbp+D0h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+210h] [rbp+110h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v42);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v33);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v35);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v39);
  v25 = 0;
  FileTime = 0;
  SystemTime = 0;
  memset_0(&Buffer, 0, sizeof(Buffer));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v37);
  if ( !a1 || (unsigned __int64)(*a1 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL || !a2 )
  {
    MachineId = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      a3,
      L"WriteSystemInformation found XmlWriter == NULL || !XmlWriter->IsInitialized() || PhoneInformation == NULL\r\n");
    goto LABEL_56;
  }
  v26 = 0;
  v29[0] = 0;
  v27 = L"SystemInformation";
  v28 = 17;
  MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)v29, 0, (__int64)&v26);
  if ( MachineId < 0 )
    goto LABEL_56;
  MachineId = MachineId::GetMachineId((__int64)v42);
  if ( MachineId < 0 )
    goto LABEL_56;
  v29[0] = 0;
  v27 = (const wchar_t *)v42[0];
  v28 = (v42[1] - v42[0]) >> 1;
  *(_QWORD *)&v26 = L"MID";
  *((_QWORD *)&v26 + 1) = 3;
  LOBYTE(v7) = 1;
  MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v26, (unsigned int)&v27, v7, (__int64)v29);
  if ( MachineId < 0 )
    goto LABEL_56;
  if ( (int)UtilGetMarkerFileData(v41) >= 0 )
  {
    v29[0] = 0;
    *(_QWORD *)&v26 = v41[0];
    *((_QWORD *)&v26 + 1) = (__int64)(v41[1] - v41[0]) >> 1;
    v27 = L"MarkerFile";
    v28 = 10;
    LOBYTE(v8) = 1;
    MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v8, (__int64)v29);
    if ( MachineId < 0 )
      goto LABEL_56;
  }
  if ( (int)UtilGetManufacturerInformation((__int64)&v33, (__int64)&v31, (__int64)&v35) < 0 )
  {
    v34 = v33;
    *(_WORD *)v33 = 0;
    v32 = v31;
    *(_WORD *)v31 = 0;
    v36 = v35;
    *(_WORD *)v35 = 0;
  }
  v10 = v33;
  if ( *a2 )
  {
    if ( v33 == v34 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
      if ( (int)CPhoneInformation::QueryPhoneInfo(a2, 0, v29) < 0
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               &v33,
                               *(void **)&v29[0]) )
      {
        v34 = v33;
        *(_WORD *)v33 = 0;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
      v10 = v33;
    }
    v11 = v31;
    if ( v31 != v32 )
      goto LABEL_23;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
    if ( (int)CPhoneInformation::QueryPhoneInfo(a2, 15, v29) < 0
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v31,
                             *(void **)&v29[0]) )
    {
      v32 = v31;
      *(_WORD *)v31 = 0;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
    v10 = v33;
  }
  v11 = v31;
LABEL_23:
  if ( v10 != v34 )
  {
    v29[0] = 0;
    *(_QWORD *)&v26 = v10;
    *((_QWORD *)&v26 + 1) = (v34 - v10) >> 1;
    v27 = L"SystemManufacturer";
    v28 = 18;
    LOBYTE(v9) = 1;
    MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v9, (__int64)v29);
    if ( MachineId < 0 )
      goto LABEL_56;
    v11 = v31;
  }
  if ( v11 == v32
    || (v29[0] = 0,
        *(_QWORD *)&v26 = v11,
        *((_QWORD *)&v26 + 1) = (v32 - v11) >> 1,
        v27 = L"SystemProductName",
        v28 = 17,
        LOBYTE(v9) = 1,
        MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v9, (__int64)v29),
        MachineId >= 0) )
  {
    if ( v35 == v36
      || (v29[0] = 0,
          *(_QWORD *)&v26 = v35,
          *((_QWORD *)&v26 + 1) = (v36 - v35) >> 1,
          v27 = L"BIOSVersion",
          v28 = 11,
          LOBYTE(v9) = 1,
          MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v9, (__int64)v29),
          MachineId >= 0) )
    {
      DWORD = UtilRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                L"InstallDate",
                0,
                &v25,
                v23);
      if ( !DWORD )
        goto LABEL_59;
      if ( v25 )
        goto LABEL_59;
      MachineId = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40, L"%u", DWORD);
      if ( MachineId >= 0 )
      {
        v29[0] = 0;
        *(_QWORD *)&v26 = v40[0];
        *((_QWORD *)&v26 + 1) = (__int64)(v40[1] - v40[0]) >> 1;
        v27 = L"OSInstallDate";
        v28 = 13;
        LOBYTE(v13) = 1;
        MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v13, (__int64)v29);
        if ( MachineId >= 0 )
        {
LABEL_59:
          if ( (int)UtilGetInstallTime(&FileTime) < 0 || !FileTime.dwLowDateTime && !FileTime.dwHighDateTime )
            goto LABEL_60;
          if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
            goto LABEL_60;
          *(_DWORD *)v24 = SystemTime.wHour;
          LODWORD(v22) = SystemTime.wDay;
          if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      v39,
                      L"%04hu-%02hu-%02huT%02hu:%02hu:%02huZ",
                      SystemTime.wYear,
                      SystemTime.wMonth,
                      v22,
                      *(_QWORD *)v24,
                      SystemTime.wMinute,
                      SystemTime.wSecond) < 0
            || (v29[0] = 0,
                *(_QWORD *)&v26 = v39[0],
                *((_QWORD *)&v26 + 1) = (__int64)(v39[1] - v39[0]) >> 1,
                v27 = L"OSInstallTime",
                v28 = 13,
                LOBYTE(v14) = 1,
                MachineId = CXMLWriter::BeginElement(
                              (_DWORD)a1,
                              (unsigned int)&v27,
                              (unsigned int)&v26,
                              v14,
                              (__int64)v29),
                MachineId >= 0) )
          {
LABEL_60:
            if ( !GlobalMemoryStatusEx(&Buffer) )
              goto LABEL_43;
            MachineId = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                          v38,
                          L"%I64u",
                          Buffer.ullTotalPhys);
            if ( MachineId >= 0 )
            {
              v29[0] = 0;
              *(_QWORD *)&v26 = v38[0];
              *((_QWORD *)&v26 + 1) = (__int64)(v38[1] - v38[0]) >> 1;
              v27 = L"Ram";
              v28 = 3;
              LOBYTE(v15) = 1;
              MachineId = CXMLWriter::BeginElement(
                            (_DWORD)a1,
                            (unsigned int)&v27,
                            (unsigned int)&v26,
                            v15,
                            (__int64)v29);
              if ( MachineId >= 0 )
              {
LABEL_43:
                if ( GetTimeZoneInformation(&TimeZoneInformation) == -1 )
                  goto LABEL_50;
                Bias = -TimeZoneInformation.Bias;
                if ( TimeZoneInformation.Bias > 0 )
                  Bias = TimeZoneInformation.Bias;
                v17 = Bias / 0x3C;
                v18 = Bias % 0x3C;
                v19 = L"-%02u:%02u";
                if ( TimeZoneInformation.Bias >= 0 )
                  v19 = L"%02u:%02u";
                MachineId = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                              v37,
                              v19,
                              v17,
                              v18);
                if ( MachineId >= 0 )
                {
                  v29[0] = 0;
                  *(_QWORD *)&v26 = v37[0];
                  *((_QWORD *)&v26 + 1) = (__int64)(v37[1] - v37[0]) >> 1;
                  v27 = L"TimeZoneBias";
                  v28 = 12;
                  LOBYTE(v20) = 1;
                  MachineId = CXMLWriter::BeginElement(
                                (_DWORD)a1,
                                (unsigned int)&v27,
                                (unsigned int)&v26,
                                v20,
                                (__int64)v29);
                  if ( MachineId >= 0 )
                  {
LABEL_50:
                    *(_QWORD *)&v26 = L"SystemInformation";
                    *((_QWORD *)&v26 + 1) = 17;
                    MachineId = CXMLWriter::EndElement(a1, &v26);
                    if ( MachineId >= 0 )
                      MachineId = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_56:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v37);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v39);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v40);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v31);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v33);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v41);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
  return (unsigned int)MachineId;
}

```

## disassembly

```asm
0x1800955c0  mov     [rsp-8+arg_8], rbx
0x1800955c5  push    rbp
0x1800955c6  push    rsi
0x1800955c7  push    rdi
0x1800955c8  push    r12
0x1800955ca  push    r14
0x1800955cc  lea     rbp, [rsp-1D0h]
0x1800955d4  sub     rsp, 2D0h
0x1800955db  mov     rax, cs:__security_cookie
0x1800955e2  xor     rax, rsp
0x1800955e5  mov     [rbp+1F0h+var_30], rax
0x1800955ec  mov     r14, r8
0x1800955ef  mov     rsi, rdx
0x1800955f2  mov     rdi, rcx
0x1800955f5  lea     rcx, [rbp+1F0h+var_158]; void *
0x1800955fc  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180095601  nop
0x180095602  lea     rcx, [rbp+1F0h+var_178]; void *
0x180095606  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009560b  nop
0x18009560c  lea     rcx, [rbp+1F0h+var_238]; void *
0x180095610  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180095615  nop
0x180095616  lea     rcx, [rbp+1F0h+var_258]; void *
0x18009561a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009561f  nop
0x180095620  lea     rcx, [rbp+1F0h+var_218]; void *
0x180095624  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180095629  nop
0x18009562a  lea     rcx, [rbp+1F0h+var_198]; void *
0x18009562e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180095633  nop
0x180095634  lea     rcx, [rbp+1F0h+var_1B8]; void *
0x180095638  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009563d  nop
0x18009563e  mov     [rsp+2F0h+var_2B0], 0
0x180095643  mov     qword ptr [rbp+1F0h+FileTime.dwLowDateTime], 0
0x18009564b  xorps   xmm0, xmm0
0x18009564e  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x180095655  xor     edx, edx; Val
0x180095657  lea     r8d, [rdx+40h]; Size
0x18009565b  lea     rcx, [rbp+1F0h+Buffer]; void *
0x180095662  call    memset_0
0x180095667  lea     rcx, [rbp+1F0h+var_1D8]; void *
0x18009566b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180095670  nop
0x180095671  xor     edx, edx; Val
0x180095673  mov     r8d, 0ACh; Size
0x180095679  lea     rcx, [rbp+1F0h+TimeZoneInformation]; void *
0x180095680  call    memset_0
0x180095685  lea     rcx, [rbp+1F0h+var_1F8]; void *
0x180095689  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009568e  nop
0x18009568f  test    rdi, rdi
0x180095692  jz      loc_180095D3C
0x180095698  mov     rax, [rdi]
0x18009569b  dec     rax
0x18009569e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800956a2  ja      loc_180095D3C
0x1800956a8  test    rsi, rsi
0x1800956ab  jz      loc_180095D3C
0x1800956b1  xorps   xmm0, xmm0
0x1800956b4  movdqa  [rsp+2F0h+var_2A0], xmm0
0x1800956ba  xorps   xmm1, xmm1
0x1800956bd  movdqa  [rsp+2F0h+var_280], xmm1
0x1800956c3  lea     r12, aSysteminformat; "SystemInformation"
0x1800956ca  mov     [rsp+2F0h+var_290], r12
0x1800956cf  mov     r14d, 11h
0x1800956d5  mov     [rsp+2F0h+var_288], r14
0x1800956da  lea     rax, [rsp+2F0h+var_2A0]
0x1800956df  mov     [rsp+2F0h+var_2D0], rax
0x1800956e4  xor     r9d, r9d
0x1800956e7  lea     r8, [rsp+2F0h+var_280]
0x1800956ec  lea     rdx, [rsp+2F0h+var_290]
0x1800956f1  mov     rcx, rdi
0x1800956f4  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800956f9  mov     ebx, eax
0x1800956fb  test    eax, eax
0x1800956fd  js      loc_180095D7F
0x180095703  lea     rcx, [rbp+1F0h+var_158]; __int64
0x18009570a  call    ?GetMachineId@MachineId@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; MachineId::GetMachineId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009570f  mov     ebx, eax
0x180095711  test    eax, eax
0x180095713  js      loc_180095D7F
0x180095719  xorps   xmm0, xmm0
0x18009571c  movdqa  [rsp+2F0h+var_280], xmm0
0x180095722  mov     rax, [rbp+1F0h+var_158]
0x180095729  mov     [rsp+2F0h+var_290], rax
0x18009572e  mov     rcx, [rbp+1F0h+var_150]
0x180095735  sub     rcx, rax
0x180095738  sar     rcx, 1
0x18009573b  mov     [rsp+2F0h+var_288], rcx
0x180095740  lea     rax, aMid; "MID"
0x180095747  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x18009574c  mov     qword ptr [rsp+2F0h+var_2A0+8], 3
0x180095755  lea     rax, [rsp+2F0h+var_280]
0x18009575a  mov     [rsp+2F0h+var_2D0], rax
0x18009575f  mov     r9b, 1
0x180095762  lea     r8, [rsp+2F0h+var_290]
0x180095767  lea     rdx, [rsp+2F0h+var_2A0]
0x18009576c  mov     rcx, rdi
0x18009576f  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180095774  mov     ebx, eax
0x180095776  test    eax, eax
0x180095778  js      loc_180095D7F
0x18009577e  lea     rcx, [rbp+1F0h+var_178]
0x180095782  call    ?UtilGetMarkerFileData@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetMarkerFileData(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180095787  test    eax, eax
0x180095789  js      short loc_1800957ED
0x18009578b  xorps   xmm0, xmm0
0x18009578e  movdqa  [rsp+2F0h+var_280], xmm0
0x180095794  mov     rax, [rbp+1F0h+var_178]
0x180095798  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x18009579d  mov     rcx, [rbp+1F0h+var_170]
0x1800957a4  sub     rcx, rax
0x1800957a7  sar     rcx, 1
0x1800957aa  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x1800957af  lea     rax, aMarkerfile; "MarkerFile"
0x1800957b6  mov     [rsp+2F0h+var_290], rax
0x1800957bb  mov     [rsp+2F0h+var_288], 0Ah
0x1800957c4  lea     rax, [rsp+2F0h+var_280]
0x1800957c9  mov     [rsp+2F0h+var_2D0], rax
0x1800957ce  mov     r9b, 1
0x1800957d1  lea     r8, [rsp+2F0h+var_2A0]
0x1800957d6  lea     rdx, [rsp+2F0h+var_290]
0x1800957db  mov     rcx, rdi
0x1800957de  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800957e3  mov     ebx, eax
0x1800957e5  test    eax, eax
0x1800957e7  js      loc_180095D7F
0x1800957ed  lea     r8, [rbp+1F0h+var_218]; __int64
0x1800957f1  lea     rdx, [rbp+1F0h+var_258]; __int64
0x1800957f5  lea     rcx, [rbp+1F0h+var_238]; __int64
0x1800957f9  call    ?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z; UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800957fe  test    eax, eax
0x180095800  jns     short loc_180095825
0x180095802  mov     rcx, [rbp+1F0h+var_238]
0x180095806  mov     [rbp+1F0h+var_230], rcx
0x18009580a  xor     eax, eax
0x18009580c  mov     [rcx], ax
0x18009580f  mov     rcx, [rbp+1F0h+var_258]
0x180095813  mov     [rbp+1F0h+var_250], rcx
0x180095817  mov     [rcx], ax
0x18009581a  mov     rcx, [rbp+1F0h+var_218]
0x18009581e  mov     [rbp+1F0h+var_210], rcx
0x180095822  mov     [rcx], ax
0x180095825  mov     rcx, [rbp+1F0h+var_238]
0x180095829  cmp     dword ptr [rsi], 0
0x18009582c  jz      loc_1800958F1
0x180095832  cmp     rcx, [rbp+1F0h+var_230]
0x180095836  jnz     short loc_18009588E
0x180095838  lea     rcx, [rsp+2F0h+var_280]; void *
0x18009583d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180095842  nop
0x180095843  lea     r8, [rsp+2F0h+var_280]
0x180095848  xor     edx, edx
0x18009584a  mov     rcx, rsi
0x18009584d  call    ?QueryPhoneInfo@CPhoneInformation@@QEAAJW4_PHONE_INFORMATION_KEY@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPhoneInformation::QueryPhoneInfo(_PHONE_INFORMATION_KEY,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180095852  test    eax, eax
0x180095854  js      short loc_180095873
0x180095856  mov     r8, qword ptr [rsp+2F0h+var_280+8]
0x18009585b  mov     rdx, qword ptr [rsp+2F0h+var_280]
0x180095860  sub     r8, rdx
0x180095863  sar     r8, 1
0x180095866  lea     rcx, [rbp+1F0h+var_238]
0x18009586a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18009586f  test    al, al
0x180095871  jnz     short loc_180095880
0x180095873  mov     rcx, [rbp+1F0h+var_238]
0x180095877  mov     [rbp+1F0h+var_230], rcx
0x18009587b  xor     eax, eax
0x18009587d  mov     [rcx], ax
0x180095880  lea     rcx, [rsp+2F0h+var_280]; void *
0x180095885  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009588a  mov     rcx, [rbp+1F0h+var_238]
0x18009588e  mov     rax, [rbp+1F0h+var_258]
0x180095892  cmp     rax, [rbp+1F0h+var_250]
0x180095896  jnz     short loc_1800958F5
0x180095898  lea     rcx, [rsp+2F0h+var_280]; void *
0x18009589d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800958a2  nop
0x1800958a3  lea     r8, [rsp+2F0h+var_280]
0x1800958a8  mov     edx, 0Fh
0x1800958ad  mov     rcx, rsi
0x1800958b0  call    ?QueryPhoneInfo@CPhoneInformation@@QEAAJW4_PHONE_INFORMATION_KEY@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPhoneInformation::QueryPhoneInfo(_PHONE_INFORMATION_KEY,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800958b5  test    eax, eax
0x1800958b7  js      short loc_1800958D6
0x1800958b9  mov     r8, qword ptr [rsp+2F0h+var_280+8]
0x1800958be  mov     rdx, qword ptr [rsp+2F0h+var_280]
0x1800958c3  sub     r8, rdx
0x1800958c6  sar     r8, 1
0x1800958c9  lea     rcx, [rbp+1F0h+var_258]
0x1800958cd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800958d2  test    al, al
0x1800958d4  jnz     short loc_1800958E3
0x1800958d6  mov     rcx, [rbp+1F0h+var_258]
0x1800958da  mov     [rbp+1F0h+var_250], rcx
0x1800958de  xor     eax, eax
0x1800958e0  mov     [rcx], ax
0x1800958e3  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800958e8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800958ed  mov     rcx, [rbp+1F0h+var_238]
0x1800958f1  mov     rax, [rbp+1F0h+var_258]
0x1800958f5  mov     rdx, [rbp+1F0h+var_230]
0x1800958f9  cmp     rcx, rdx
0x1800958fc  jz      short loc_180095959
0x1800958fe  xorps   xmm0, xmm0
0x180095901  movdqa  [rsp+2F0h+var_280], xmm0
0x180095907  mov     qword ptr [rsp+2F0h+var_2A0], rcx
0x18009590c  sub     rdx, rcx
0x18009590f  sar     rdx, 1
0x180095912  mov     qword ptr [rsp+2F0h+var_2A0+8], rdx
0x180095917  lea     rax, aSystemmanufact; "SystemManufacturer"
0x18009591e  mov     [rsp+2F0h+var_290], rax
0x180095923  mov     [rsp+2F0h+var_288], 12h
0x18009592c  lea     rax, [rsp+2F0h+var_280]
0x180095931  mov     [rsp+2F0h+var_2D0], rax
0x180095936  mov     r9b, 1
0x180095939  lea     r8, [rsp+2F0h+var_2A0]
0x18009593e  lea     rdx, [rsp+2F0h+var_290]
0x180095943  mov     rcx, rdi
0x180095946  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x18009594b  mov     ebx, eax
0x18009594d  test    eax, eax
0x18009594f  js      loc_180095D7F
0x180095955  mov     rax, [rbp+1F0h+var_258]
0x180095959  mov     rcx, [rbp+1F0h+var_250]
0x18009595d  cmp     rax, rcx
0x180095960  jz      short loc_1800959B5
0x180095962  xorps   xmm0, xmm0
0x180095965  movdqa  [rsp+2F0h+var_280], xmm0
0x18009596b  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180095970  sub     rcx, rax
0x180095973  sar     rcx, 1
0x180095976  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x18009597b  lea     rax, aSystemproductn; "SystemProductName"
0x180095982  mov     [rsp+2F0h+var_290], rax
0x180095987  mov     [rsp+2F0h+var_288], r14
0x18009598c  lea     rax, [rsp+2F0h+var_280]
0x180095991  mov     [rsp+2F0h+var_2D0], rax
0x180095996  mov     r9b, 1
0x180095999  lea     r8, [rsp+2F0h+var_2A0]
0x18009599e  lea     rdx, [rsp+2F0h+var_290]
0x1800959a3  mov     rcx, rdi
0x1800959a6  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800959ab  mov     ebx, eax
0x1800959ad  test    eax, eax
0x1800959af  js      loc_180095D7F
0x1800959b5  mov     rcx, [rbp+1F0h+var_218]
0x1800959b9  mov     rax, [rbp+1F0h+var_210]
0x1800959bd  cmp     rcx, rax
0x1800959c0  jz      short loc_180095A19
0x1800959c2  xorps   xmm0, xmm0
0x1800959c5  movdqa  [rsp+2F0h+var_280], xmm0
0x1800959cb  mov     qword ptr [rsp+2F0h+var_2A0], rcx
0x1800959d0  sub     rax, rcx
0x1800959d3  sar     rax, 1
0x1800959d6  mov     qword ptr [rsp+2F0h+var_2A0+8], rax
0x1800959db  lea     rax, aBiosversion; "BIOSVersion"
0x1800959e2  mov     [rsp+2F0h+var_290], rax
0x1800959e7  mov     [rsp+2F0h+var_288], 0Bh
0x1800959f0  lea     rax, [rsp+2F0h+var_280]
0x1800959f5  mov     [rsp+2F0h+var_2D0], rax
0x1800959fa  mov     r9b, 1
0x1800959fd  lea     r8, [rsp+2F0h+var_2A0]
0x180095a02  lea     rdx, [rsp+2F0h+var_290]
0x180095a07  mov     rcx, rdi
0x180095a0a  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180095a0f  mov     ebx, eax
0x180095a11  test    eax, eax
0x180095a13  js      loc_180095D7F
0x180095a19  lea     rax, [rsp+2F0h+var_2B0]
0x180095a1e  mov     [rsp+2F0h+var_2D0], rax; bool *
0x180095a23  xor     r9d, r9d; unsigned int
0x180095a26  lea     r8, aInstalldate; "InstallDate"
0x180095a2d  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180095a34  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180095a3b  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180095a40  test    eax, eax
0x180095a42  jz      loc_180095ACB
0x180095a48  cmp     [rsp+2F0h+var_2B0], 0
0x180095a4d  jnz     short loc_180095ACB
0x180095a4f  mov     r8d, eax
0x180095a52  lea     rdx, aU_0; "%u"
0x180095a59  lea     rcx, [rbp+1F0h+var_198]
0x180095a5d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180095a62  mov     ebx, eax
0x180095a64  test    eax, eax
0x180095a66  js      loc_180095D7F
0x180095a6c  xorps   xmm0, xmm0
0x180095a6f  movdqa  [rsp+2F0h+var_280], xmm0
0x180095a75  mov     rax, [rbp+1F0h+var_198]
0x180095a79  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180095a7e  mov     rcx, [rbp+1F0h+var_190]
0x180095a82  sub     rcx, rax
0x180095a85  sar     rcx, 1
0x180095a88  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x180095a8d  lea     rax, aOsinstalldate; "OSInstallDate"
0x180095a94  mov     [rsp+2F0h+var_290], rax
0x180095a99  mov     [rsp+2F0h+var_288], 0Dh
  ... truncated ...
```
