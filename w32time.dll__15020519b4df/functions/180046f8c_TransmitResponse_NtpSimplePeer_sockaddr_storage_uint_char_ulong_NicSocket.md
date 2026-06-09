# TransmitResponse(NtpSimplePeer *,sockaddr_storage *,uint,char *,ulong,NicSocket *)

- ea: `0x180046f8c`
- end: `0x180048068`
- name: `?TransmitResponse@@YA_NPEAUNtpSimplePeer@@PEAUsockaddr_storage@@IPEADKPEAUNicSocket@@@Z`
- size: `4316`
- prototype: `bool(struct NtpSimplePeer *, struct sockaddr_storage *, unsigned int, char *, unsigned int, struct NicSocket *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bdb0`
- `0x180035560`

## callees

- `0x18000a7e0`
- `0x180018138`
- `0x180018dfc`
- `0x18001a780`
- `0x18001d9a0`
- `0x18002bbf8`
- `0x18002c918`
- `0x18002cbe0`
- `0x18002d108`
- `0x18002d8f4`
- `0x18002db44`
- `0x18002fbdc`
- `0x18002fc0c`
- `0x180030c48`
- `0x180033f38`
- `0x18003a830`
- `0x18003d270`
- `0x18003dd2c`
- `0x18003f491`
- `0x180042658`
- `0x180043b7c`
- `0x180046f8c`
- `0x180063f50`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800478ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800478cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047dfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800478ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800478cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047dfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047e0f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180047e6d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180047e6d`
- `logoncli!I_NetlogonComputeServerDigest` at `0x18004773d`
- `logoncli!I_NetlogonComputeServerDigest` at `0x18004773d`
- `logoncli!I_NetlogonComputeServerSignature` at `0x180047c1d`
- `logoncli!I_NetlogonComputeServerSignature` at `0x180047c1d`
- `ntdll!RtlInitUnicodeString` at `0x180047841`
- `ntdll!RtlInitUnicodeString` at `0x18004785a`
- `ntdll!RtlInitUnicodeString` at `0x180047ced`
- `ntdll!RtlInitUnicodeString` at `0x180047d06`
- `ntdll!RtlInitUnicodeString` at `0x180047841`
- `ntdll!RtlInitUnicodeString` at `0x18004785a`
- `ntdll!RtlInitUnicodeString` at `0x180047ced`
- `ntdll!RtlInitUnicodeString` at `0x180047d06`
- `WS2_32!__imp_WSAGetLastError` at `0x180047f3b`
- `WS2_32!__imp_WSAGetLastError` at `0x180047f3b`

## string_xrefs

- `0x180047701`: `Computing server digest: OLD:%s, RID:%08X\n`
- `0x18004787c`: `Logging warning: NtpServer encountered an error while validating the computer account for client %s. NtpServer cannot provide secure (signed) time to the client and will ignore the request. The error was: %s\n`
- `0x180047d28`: `Logging warning: NtpServer encountered an error while validating the computer account for client %s. NtpServer cannot provide secure (signed) time to the client and will ignore the request. The error was: %s\n`
- `0x180047afb`: `Warning: NtpServer does not have a common hash format with client %s.NtpServer cannot provide secure (signed) time to the client and will ignore the request. SupportedFormats: 0x%x.  ClientFormats: 0x%x\n`
- `0x180047b97`: `Computing server signature: OLD:%s, RID:%08X, format:0x%x\n`

## pseudocode

```c
char __fastcall TransmitResponse(
        struct NtpSimplePeer *a1,
        struct sockaddr *a2,
        DWORD a3,
        char *a4,
        unsigned int a5,
        struct NicSocket *a6)
{
  char v8; // r14
  unsigned int v9; // r12d
  unsigned __int32 v10; // r13d
  unsigned int v11; // r15d
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned __int64 v16; // rbx
  char *v17; // rbx
  unsigned int v18; // ecx
  unsigned int v19; // ebx
  char *v20; // rcx
  int v21; // eax
  struct sockaddr_storage *v22; // rsi
  unsigned int v23; // eax
  unsigned int v24; // r15d
  const wchar_t *v25; // rdx
  signed int v26; // ecx
  int SystemErrorString; // eax
  struct sockaddr *v29; // r15
  void *v30; // rsi
  bool v31; // zf
  __int128 v32; // xmm0
  __int64 v33; // r8
  __int64 v34; // rdx
  struct sockaddr *v35; // r15
  wchar_t *v36; // r14
  __int64 v37; // rbx
  const wchar_t *v38; // rdx
  signed int v39; // ecx
  int v40; // eax
  HLOCAL v41; // rbx
  HLOCAL v42; // rsi
  int Error; // eax
  unsigned int v44; // r15d
  __int64 ActualTxDelay; // rax
  bool v46; // cl
  __int64 v47; // [rsp+0h] [rbp-358h] BYREF
  unsigned int v48[2]; // [rsp+20h] [rbp-338h]
  unsigned __int64 *v49; // [rsp+48h] [rbp-310h]
  char v50; // [rsp+50h] [rbp-308h]
  _BYTE v51[3]; // [rsp+51h] [rbp-307h] BYREF
  unsigned int v52; // [rsp+54h] [rbp-304h] BYREF
  char v53[4]; // [rsp+58h] [rbp-300h] BYREF
  DWORD dwAddressLength; // [rsp+5Ch] [rbp-2FCh]
  unsigned int v55; // [rsp+60h] [rbp-2F8h] BYREF
  LPSOCKADDR lpsaAddress; // [rsp+68h] [rbp-2F0h]
  unsigned int valid; // [rsp+70h] [rbp-2E8h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-2E0h] BYREF
  __int64 v59; // [rsp+80h] [rbp-2D8h] BYREF
  size_t Size; // [rsp+88h] [rbp-2D0h] BYREF
  unsigned __int32 v61; // [rsp+90h] [rbp-2C8h]
  struct sockaddr_storage *v62; // [rsp+98h] [rbp-2C0h]
  void *Src; // [rsp+A0h] [rbp-2B8h] BYREF
  HLOCAL TxDelay; // [rsp+A8h] [rbp-2B0h] BYREF
  int v65; // [rsp+B0h] [rbp-2A8h] BYREF
  int v66; // [rsp+B4h] [rbp-2A4h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-2A0h] BYREF
  unsigned __int64 v68; // [rsp+C0h] [rbp-298h] BYREF
  char *v69; // [rsp+C8h] [rbp-290h]
  __int64 ClockPeriodInFileTimeIncrements; // [rsp+D0h] [rbp-288h] BYREF
  __int64 v71; // [rsp+D8h] [rbp-280h] BYREF
  _QWORD *v72; // [rsp+E0h] [rbp-278h]
  HLOCAL v73; // [rsp+E8h] [rbp-270h] BYREF
  int v74; // [rsp+F0h] [rbp-268h] BYREF
  int v75; // [rsp+F4h] [rbp-264h] BYREF
  unsigned int v76; // [rsp+F8h] [rbp-260h]
  __int64 v77; // [rsp+100h] [rbp-258h] BYREF
  __int64 v78; // [rsp+108h] [rbp-250h] BYREF
  __int64 v79; // [rsp+110h] [rbp-248h] BYREF
  __int64 v80; // [rsp+118h] [rbp-240h]
  __int64 *v81; // [rsp+120h] [rbp-238h]
  struct _UNICODE_STRING v82; // [rsp+128h] [rbp-230h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+138h] [rbp-220h] BYREF
  struct _UNICODE_STRING v84; // [rsp+148h] [rbp-210h] BYREF
  struct _UNICODE_STRING v85; // [rsp+158h] [rbp-200h] BYREF
  HLOCAL v86; // [rsp+168h] [rbp-1F0h]
  __int64 v87; // [rsp+170h] [rbp-1E8h]
  int v88; // [rsp+198h] [rbp-1C0h]
  _QWORD *v89; // [rsp+1A0h] [rbp-1B8h]
  char v90[16]; // [rsp+1B0h] [rbp-1A8h] BYREF
  __int128 v91; // [rsp+1C0h] [rbp-198h]
  __int128 v92; // [rsp+1D0h] [rbp-188h]
  char v93[4]; // [rsp+1E0h] [rbp-178h] BYREF
  __int64 v94; // [rsp+1E4h] [rbp-174h]
  int v95; // [rsp+1ECh] [rbp-16Ch]
  __int128 v96; // [rsp+1F0h] [rbp-168h]
  __int128 v97; // [rsp+200h] [rbp-158h]
  _OWORD v98[2]; // [rsp+210h] [rbp-148h] BYREF
  char v99[4]; // [rsp+230h] [rbp-128h] BYREF
  __int64 v100; // [rsp+234h] [rbp-124h]
  int v101; // [rsp+23Ch] [rbp-11Ch]
  __int128 v102; // [rsp+240h] [rbp-118h]
  __int128 v103; // [rsp+250h] [rbp-108h]
  unsigned __int8 v105; // [rsp+264h] [rbp-F4h]
  _BYTE v106[72]; // [rsp+268h] [rbp-F0h] BYREF
  _QWORD v107[8]; // [rsp+2B0h] [rbp-A8h] BYREF
  __int128 v108; // [rsp+2F0h] [rbp-68h] BYREF
  __int128 v109; // [rsp+300h] [rbp-58h] BYREF

  v81 = &v47;
  Src = a4;
  dwAddressLength = a3;
  lpsaAddress = a2;
  v62 = (struct sockaddr_storage *)a6;
  v8 = 0;
  *(_OWORD *)v90 = 0;
  v91 = 0;
  v92 = 0;
  v79 = 0;
  v77 = 0;
  v78 = 0;
  v71 = 0;
  v59 = 0;
  v51[0] = 0;
  v53[0] = 0;
  v65 = 0;
  v66 = 0;
  v74 = 0;
  v75 = 0;
  SourceString = 0;
  hMem = 0;
  v9 = -1;
  v10 = 0;
  v61 = 0;
  v80 = 0;
  v68 = 0;
  TxDelay = 0;
  v11 = 64;
  memset_0(v107, 0, sizeof(v107));
  v52 = 0;
  (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(10, &v79);
  (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(11, &v77);
  (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(1, &v78);
  (*((void (__fastcall **)(_QWORD, __int64 *))g_pnpstate + 2))(0, &v71);
  (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(3, &v59);
  (*((void (__fastcall **)(__int64, _BYTE *))g_pnpstate + 2))(6, v51);
  (*((void (__fastcall **)(__int64, char *))g_pnpstate + 2))(7, v53);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(2, &v65);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(8, &v66);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(9, &v74);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(12, &v75);
  ClockPeriodInFileTimeIncrements = (unsigned int)GetClockPeriodInFileTimeIncrements(&v78);
  v90[0] = (v51[0] << 6) | v90[0] & 0x1F | 0x18;
  v90[0] ^= (*((_BYTE *)a1 + 136) ^ v90[0]) & 7;
  v90[1] = v53[0];
  v90[2] = *((_BYTE *)a1 + 13);
  v90[3] = v65;
  *(_DWORD *)&v90[4] = NtpTimeOffsetFromNtTimeOffset(v79);
  v12 = v71 - v59;
  if ( v71 - v59 < 0 )
    v12 = v59 - v71;
  if ( v51[0] == 3 || v12 > 0xC92A69C000LL )
    v13 = 10000000;
  else
    v13 = v12 / 0x15180;
  v14 = v77 + v13 + ClockPeriodInFileTimeIncrements;
  if ( v14 > 0x9896800 )
    v14 = 160000000;
  *(_DWORD *)&v90[8] = NtpTimePeriodFromNtTimePeriod(v14);
  *(_DWORD *)&v90[12] = v66;
  *(_QWORD *)&v91 = NtpTimeEpochFromNtTimeEpoch(v71);
  *((_QWORD *)&v91 + 1) = *((_QWORD *)a1 + 10);
  *(_QWORD *)&v92 = NtpTimeEpochFromNtTimeEpoch(*((_QWORD *)a1 + 11));
  valid = IsValidIPProtoControl(a4, a5);
  if ( valid )
  {
    v15 = *(_DWORD *)a4;
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(6) )
      FileLogAdd(L"No valid IPPROTO Control passed in. Can potentially cause issues on systems with multiple NICs.\n");
    v15 = 0;
  }
  v55 = v15;
  v16 = (v15 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v16 > 0x40 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(6) )
      FileLogAdd(L"Insufficient buffer for ip_proto info. MinRequiredSize:%d GivenSize:%d\n", v16, 64);
    v15 = 0;
    v55 = 0;
  }
  v17 = (char *)v107;
  v72 = v107;
  if ( valid && v15 )
  {
    memcpy_0(v107, Src, v15);
    v52 = (v55 + 7) & 0xFFFFFFF8;
    v76 = v52;
    v89 = v107;
    v88 = 64;
    v72 = v107;
    v17 = (char *)v107 + ((v107[0] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
    if ( v17 + 16 > (char *)&v108 )
      v17 = 0;
    v72 = v17;
  }
  if ( !v62[1].__ss_pad2[9] )
    goto LABEL_36;
  TxDelay = (HLOCAL)GetTxDelay();
  v86 = TxDelay;
  v10 = _InterlockedIncrement(&dword_1800A4998);
  v61 = v10;
  if ( v10 > 0xA )
  {
    _InterlockedDecrement(&dword_1800A4998);
    if ( (unsigned __int8)FileLogAllowEntry(106) )
      FileLogAdd(L" HA reqcount:%d skipping tx delay\n", v10);
    v10 = 0;
    v61 = 0;
LABEL_36:
    v19 = v52;
    goto LABEL_37;
  }
  v18 = v52 + 24;
  if ( v52 + 24 > 0x40 )
    v17 = 0;
  v72 = v17;
  if ( !v17 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Insufficient control msg buffer to request tx tstmp.");
    goto LABEL_36;
  }
  v9 = _InterlockedIncrement(&dword_1800A3318);
  if ( v9 == -1 )
    v9 = _InterlockedIncrement(&dword_1800A3318);
  *(_QWORD *)v17 = 20;
  *((_DWORD *)v17 + 2) = 0xFFFF;
  *((_DWORD *)v17 + 3) = 12299;
  *((_DWORD *)v17 + 4) = v9;
  v19 = v18;
  v52 = v18;
  v76 = v18;
LABEL_37:
  v20 = (char *)v107;
  if ( !v19 )
    v20 = 0;
  v69 = v20;
  (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(3, &v59);
  if ( TxDelay )
    v59 += (__int64)TxDelay;
  *((_QWORD *)&v92 + 1) = NtpTimeEpochFromNtTimeEpoch(v59);
  v21 = *((_DWORD *)a1 + 35);
  if ( !v21 )
  {
    valid = 0;
    v49 = &v68;
    v22 = v62;
    if ( (unsigned int)MyWSASendMsg(
                         v62[1].__ss_align,
                         lpsaAddress,
                         dwAddressLength,
                         v90,
                         0x30u,
                         v69,
                         v19,
                         &valid,
                         *(int (**)(unsigned __int64, struct _WSAMSG *, unsigned int, unsigned int *, struct _OVERLAPPED *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *, unsigned int)))&v62[1].__ss_pad2[24],
                         &v68) != -1 )
    {
      if ( valid < 0x30 && (unsigned __int8)FileLogAllowEntry(6) )
        FileLogAdd(L"TransmitResponse: Fewer bytes sent than requested. Ignoring error.\n");
      goto LABEL_136;
    }
LABEL_128:
    Error = WSAGetLastError();
    v44 = Error;
    if ( Error > 0 )
      v44 = (unsigned __int16)Error | 0x80070000;
    if ( (unsigned __int8)FileLogAllowEntry(6) )
      FileLogAdd(L"TransmitResponse: Failed to send a response. Error: 0x%08X\n", v44);
    goto LABEL_136;
  }
  if ( v21 == 1 )
  {
    memset(v98, 0, 24);
    v93[0] = v90[0];
    v93[1] = v90[1];
    v93[2] = v90[2];
    v93[3] = v90[3];
    v94 = *(_QWORD *)&v90[4];
    v95 = *(_DWORD *)&v90[12];
    v96 = v91;
    v97 = v92;
    v23 = *((_DWORD *)a1 + 36);
    LODWORD(v98[0]) = v23;
    if ( v23 )
    {
      v24 = v23 >> 31;
      *((_DWORD *)a1 + 36) = v23 & 0x7FFFFFFF;
      if ( (unsigned __int8)FileLogAllowEntry(56) )
      {
        v25 = L"TRUE";
        if ( !(_BYTE)v24 )
          v25 = L"FALSE";
        FileLogAdd(L"Computing server digest: OLD:%s, RID:%08X\n", v25, *((unsigned int *)a1 + 36));
      }
      v26 = I_NetlogonComputeServerDigest(0, *((unsigned int *)a1 + 36), v90, 48, &v109, &v108);
      if ( v26 == 8620 && *((_BYTE *)g_pnpstate + 508) && !*((_BYTE *)g_pnpstate + 548) )
      {
        local_unwind_0(v81, &loc_180047780);
        return 1;
      }
      if ( !v26 )
      {
        v31 = (_BYTE)v24 == 0;
        v29 = lpsaAddress;
        if ( v31 )
          v32 = v109;
        else
          v32 = v108;
        *(_OWORD *)((char *)v98 + 4) = v32;
        goto LABEL_74;
      }
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      if ( (*((_BYTE *)g_pnpstate + 200) & 8) != 0 )
      {
        SourceString = 0;
        Src = 0;
        SystemErrorString = GetSystemErrorString(v26, (unsigned __int16 **)&SourceString);
        v29 = lpsaAddress;
        if ( SystemErrorString >= 0 )
        {
          if ( (int)MyAddressToString(lpsaAddress, dwAddressLength, (unsigned __int16 **)&Src) >= 0 )
          {
            DestinationString = 0;
            v82 = 0;
            v30 = Src;
            RtlInitUnicodeString(&DestinationString, (PCWSTR)Src);
            RtlInitUnicodeString(&v82, SourceString);
            if ( (unsigned __int8)FileLogAllowEntry(6) )
              FileLogAdd(
                L"Logging warning: NtpServer encountered an error while validating the computer account for client %s. Ntp"
                 "Server cannot provide secure (signed) time to the client and will ignore the request. The error was: %s\n",
                v30,
                SourceString);
            *(_QWORD *)v48 = &v82;
            LogEvent(
              &_W32TimeRegistrationHandle,
              W32TIME_EVENT_CLIENT_COMPUTE_SERVER_DIGEST_FAILED,
              L"uu",
              &DestinationString);
            LocalFree(v30);
          }
          LocalFree((HLOCAL)SourceString);
        }
        goto LABEL_73;
      }
    }
    else if ( (unsigned __int8)FileLogAllowEntry(6) )
    {
      FileLogAdd(
        L"Warning: this request expects an authenticated response, but did not provide the client ID.  Sounds like we're r"
         "esponding to a server response, which is incorrect behavior.  However, this can also be caused by other applica"
         "tions broadcasting NTP packets, using an unrecognized authentication mechanism.");
    }
    v29 = lpsaAddress;
LABEL_73:
    v50 = 1;
    v8 = 1;
LABEL_74:
    v22 = v62;
    if ( !v8 )
    {
      v55 = 0;
      if ( (unsigned int)MyWSASendMsg(
                           v62[1].__ss_align,
                           v29,
                           dwAddressLength,
                           v93,
                           0x44u,
                           v69,
                           v19,
                           &v55,
                           *(int (**)(unsigned __int64, struct _WSAMSG *, unsigned int, unsigned int *, struct _OVERLAPPED *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *, unsigned int)))&v62[1].__ss_pad2[24],
                           &v68) == -1 )
        goto LABEL_128;
      if ( v55 < 0x44 && (unsigned __int8)FileLogAllowEntry(6) )
      {
        v33 = 68;
        v34 = v55;
LABEL_79:
        FileLogAdd(L"TransmitResponse: Fewer bytes (0x%x) sent than requested (0x%x. Ignoring error.\n", v34, v33);
        goto LABEL_136;
      }
    }
    goto LABEL_136;
  }
  if ( v21 != 2 )
  {
    v22 = v62;
    goto LABEL_136;
  }
  memset_0(v99, 0, 0x78u);
  v99[0] = v90[0];
  v99[1] = v90[1];
  v99[2] = v90[2];
  v99[3] = v90[3];
  v100 = *(_QWORD *)&v90[4];
  v101 = *(_DWORD *)&v90[12];
  v102 = v91;
  v103 = v92;
  if ( !*((_DWORD *)a1 + 36) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(6) )
      FileLogAdd(
        L"Warning: this request expects an authenticated response, but did not provide the client ID.  Sounds like we're r"
         "esponding to a server response, which is incorrect behavior.  However, this can also be caused by other applica"
         "tions broadcasting NTP packets, using an unrecognized authentication mechanism.");
    v35 = lpsaAddress;
    goto LABEL_124;
  }
  v73 = 0;
  TxDelay = 0;
  Size = 0;
  if ( (*((_BYTE *)a1 + 152) & 1) == 0 )
  {
    v35 = lpsaAddress;
    valid = MyAddressToString(lpsaAddress, dwAddressLength, (unsigned __int16 **)&hMem);
    v36 = L"<unknown>";
    if ( (valid & 0x80000000) == 0 )
      v36 = (wchar_t *)hMem;
    hMem = v36;
    if ( (unsigned __int8)FileLogAllowEntry(6) )
      FileLogAdd(
        L"Warning: NtpServer does not have a common hash format with client %s.NtpServer cannot provide secure (signed) ti"
         "me to the client and will ignore the request. SupportedFormats: 0x%x.  ClientFormats: 0x%x\n",
        v36,
        *((unsigned int *)a1 + 38),
        1);
    if ( (valid & 0x80000000) == 0 )
      LocalFree(v36);
LABEL_124:
    v50 = 1;
    goto LABEL_125;
  }
  v105 = 1;
  v37 = v59;
  ClockPeriodInFileTimeIncrements = 0;
  Src = (void *)GetComputedDelayActual(&qword_1800A3310, &qword_1800A4980, &qword_1800A3308);
  if ( (unsigned __int8)FileLogAllowEntry(56) )
  {
    v38 = L"TRUE";
    if ( !*((_DWORD *)a1 + 37) )
      v38 = L"FALSE";
    FileLogAdd(L"Computing server signature: OLD:%s, RID:%08X, format:0x%x\n", v38, *((unsigned int *)a1 + 36), v105);
  }
  v59 += (__int64)Src;
  *((_QWORD *)&v103 + 1) = NtpTimeEpochFromNtTimeEpoch(v59);
  v39 = I_NetlogonComputeServerSignature(
          0,
          *((unsigned int *)a1 + 36),
          v105,
          v99,
          48,
          &v73,
          (char *)&Size + 4,
          &TxDelay,
          &Size);
  if ( v39 == 8620 && *((_BYTE *)g_pnpstate + 508) && !*((_BYTE *)g_pnpstate + 548) )
  {
    local_unwind_0(v81, &loc_180047C60);
    return 1;
  }
  if ( !v39 )
  {
    if ( *((_DWORD *)a1 + 37) )
    {
      if ( (unsigned int)Size < 0x40 )
        v11 = Size;
      memcpy_0(v106, TxDelay, v11);
      v42 = v73;
    }
    else
    {
      if ( HIDWORD(Size) < 0x40 )
        v11 = HIDWORD(Size);
      v42 = v73;
      memcpy_0(v106, v73, v11);
    }
    LocalFree(v42);
    LocalFree(TxDelay);
    (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(3, &ClockPeriodInFileTimeIncrements);
    v80 = ClockPeriodInFileTimeIncrements - v37;
    v87 = ClockPeriodInFileTimeIncrements - v37;
    if ( (__int64)Src > ClockPeriodInFileTimeIncrements - v37
      && (__int64)Src - (ClockPeriodInFileTimeIncrements - v37) > 4000 )
    {
      Sleep(1u);
      if ( (unsigned __int8)FileLogAllowEntry(56) )
        FileLogAdd(L"--+--\n");
    }
    v19 = v52;
    v35 = lpsaAddress;
    goto LABEL_126;
  }
  if ( v39 > 0 )
    v39 = (unsigned __int16)v39 | 0x80070000;
  if ( (*((_BYTE *)g_pnpstate + 200) & 8) != 0 )
  {
    v40 = GetSystemErrorString(v39, (unsigned __int16 **)&SourceString);
    v35 = lpsaAddress;
    if ( v40 >= 0 )
    {
      if ( (int)MyAddressToString(lpsaAddress, dwAddressLength, (unsigned __int16 **)&hMem) >= 0 )
      {
        v85 = 0;
        v84 = 0;
        v41 = hMem;
        RtlInitUnicodeString(&v85, (PCWSTR)hMem);
        RtlInitUnicodeString(&v84, SourceString);
        if ( (unsigned __int8)FileLogAllowEntry(6) )
          FileLogAdd(
            L"Logging warning: NtpServer encountered an error while validating the computer account for client %s. NtpServ"
             "er cannot provide secure (signed) time to the client and will ignore the request. The error was: %s\n",
            v41,
            SourceString);
        *(_QWORD *)v48 = &v84;
        LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_CLIENT_COMPUTE_SERVER_DIGEST_FAILED, L"uu", &v85);
        LocalFree(v41);
      }
      LocalFree((HLOCAL)SourceString);
    }
  }
  else
  {
    v35 = lpsaAddress;
  }
  v50 = 1;
  v19 = v52;
LABEL_125:
  v8 = 1;
LABEL_126:
  v22 = v62;
  if ( !v8 )
  {
    v52 = 0;
    if ( (unsigned int)MyWSASendMsg(
                         v62[1].__ss_align,
                         v35,
                         dwAddressLength,
                         v99,
                         0x78u,
                         v69,
                         v19,
                         &v52,
                         *(int (**)(unsigned __int64, struct _WSAMSG *, unsigned int, unsigned int *, struct _OVERLAPPED *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *, unsigned int)))&v62[1].__ss_pad2[24],
                         &v68) == -1 )
      goto LABEL_128;
    if ( v52 < 0x78 && (unsigned __int8)FileLogAllowEntry(6) )
    {
      v33 = 120;
      v34 = v52;
      goto LABEL_79;
    }
  }
LABEL_136:
  if ( v9 != -1 )
  {
    ActualTxDelay = GetActualTxDelay(v22[1].__ss_align, v9, v68);
    SaveDelayInfo(v80, ActualTxDelay);
  }
  if ( !v8 && (unsigned __int8)FileLogAllowEntry(56) )
  {
    FileLogAdd(L"TransmitResponse: sent ");
    FileLogSockaddrInEx2(1, (struct sockaddr *)v22, *(_DWORD *)&v22[1].ss_family);
    FileLogAppend(L"(");
    FileLogMsgAncillaryDataEx2(v46, v69, v19);
    FileLogAppend(L")");
    FileLogAppend(L"->");
    FileLogSockaddrInEx2(1, lpsaAddress, dwAddressLength);
    FileLogAppend(L"\n");
  }
  if ( v10 )
    _InterlockedDecrement(&dword_1800A4998);
  return 0;
}

```

## disassembly

```asm
0x180046f8c  mov     r11, rsp
0x180046f8f  push    rbx
0x180046f90  push    rsi
0x180046f91  push    rdi
0x180046f92  push    r12
0x180046f94  push    r13
0x180046f96  push    r14
0x180046f98  push    r15
0x180046f9a  sub     rsp, 320h
0x180046fa1  mov     rax, cs:__security_cookie
0x180046fa8  xor     rax, rsp
0x180046fab  mov     [rsp+358h+var_48], rax
0x180046fb3  mov     [rsp+358h+var_238], rsp
0x180046fbb  mov     rbx, r9
0x180046fbe  mov     [rsp+358h+Src], rbx
0x180046fc6  mov     [rsp+358h+dwAddressLength], r8d
0x180046fcb  mov     [rsp+358h+lpsaAddress], rdx
0x180046fd0  mov     rsi, rcx
0x180046fd3  mov     rax, [rsp+358h+arg_28]
0x180046fdb  mov     [rsp+358h+var_2C0], rax
0x180046fe3  xor     edi, edi
0x180046fe5  mov     r14b, dil
0x180046fe8  xorps   xmm0, xmm0
0x180046feb  movups  xmmword ptr [rsp+358h+var_1A8], xmm0
0x180046ff3  movups  [rsp+358h+var_198], xmm0
0x180046ffb  movups  [rsp+358h+var_188], xmm0
0x180047003  mov     [r11-248h], rdi
0x18004700a  mov     [r11-258h], rdi
0x180047011  mov     [r11-250h], rdi
0x180047018  mov     [r11-280h], rdi
0x18004701f  mov     [r11-2D8h], rdi
0x180047026  mov     [rsp+358h+var_307], dil
0x18004702b  mov     [rsp+358h+var_300], dil
0x180047030  mov     [rsp+358h+var_2A8], edi
0x180047037  mov     [rsp+358h+var_2A4], edi
0x18004703e  mov     [rsp+358h+var_268], edi
0x180047045  mov     [rsp+358h+var_264], edi
0x18004704c  mov     [rsp+358h+SourceString], rdi
0x180047051  mov     [r11-2A0h], rdi
0x180047058  or      r12d, 0FFFFFFFFh
0x18004705c  mov     r13d, edi
0x18004705f  mov     [rsp+358h+var_2C8], edi
0x180047066  mov     [r11-240h], rdi
0x18004706d  mov     [r11-298h], rdi
0x180047074  mov     [r11-2B0h], rdi
0x18004707b  lea     r15d, [rdi+40h]
0x18004707f  mov     r8d, r15d; Size
0x180047082  xor     edx, edx; Val
0x180047084  lea     rcx, [r11-0A8h]; void *
0x18004708b  call    memset_0
0x180047090  mov     [rsp+358h+var_304], edi
0x180047094  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18004709b  lea     rdx, [rsp+358h+var_248]
0x1800470a3  lea     ecx, [rdi+0Ah]
0x1800470a6  mov     rax, [rax+10h]
0x1800470aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470af  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800470b6  lea     rdx, [rsp+358h+var_258]
0x1800470be  lea     ecx, [rdi+0Bh]
0x1800470c1  mov     rax, [rax+10h]
0x1800470c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470ca  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800470d1  lea     rdx, [rsp+358h+var_250]
0x1800470d9  lea     edi, [r15-3Fh]
0x1800470dd  mov     ecx, edi
0x1800470df  mov     rax, [rax+10h]
0x1800470e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470e8  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800470ef  lea     rdx, [rsp+358h+var_280]
0x1800470f7  xor     ecx, ecx
0x1800470f9  mov     rax, [rax+10h]
0x1800470fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047102  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180047109  lea     rdx, [rsp+358h+var_2D8]
0x180047111  lea     ecx, [rdi+2]
0x180047114  mov     rax, [rax+10h]
0x180047118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004711d  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180047124  lea     rdx, [rsp+358h+var_307]
0x180047129  lea     ecx, [rdi+5]
0x18004712c  mov     rax, [rax+10h]
0x180047130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047135  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18004713c  lea     rdx, [rsp+358h+var_300]
0x180047141  lea     ecx, [rdi+6]
0x180047144  mov     rax, [rax+10h]
0x180047148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004714d  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180047154  lea     rdx, [rsp+358h+var_2A8]
0x18004715c  lea     ecx, [rdi+1]
0x18004715f  mov     rax, [rax+10h]
0x180047163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047168  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18004716f  lea     rdx, [rsp+358h+var_2A4]
0x180047177  lea     ecx, [rdi+7]
0x18004717a  mov     rax, [rax+10h]
0x18004717e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047183  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18004718a  lea     rdx, [rsp+358h+var_268]
0x180047192  lea     ecx, [rdi+8]
0x180047195  mov     rax, [rax+10h]
0x180047199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004719e  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800471a5  lea     rdx, [rsp+358h+var_264]
0x1800471ad  lea     ecx, [rdi+0Bh]
0x1800471b0  mov     rax, [rax+10h]
0x1800471b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471b9  lea     rcx, [rsp+358h+var_250]
0x1800471c1  call    GetClockPeriodInFileTimeIncrements
0x1800471c6  mov     eax, eax
0x1800471c8  mov     [rsp+358h+var_288], rax
0x1800471d0  mov     cl, [rsp+358h+var_1A8]
0x1800471d7  and     cl, 3Fh
0x1800471da  mov     al, [rsp+358h+var_307]
0x1800471de  shl     al, 6
0x1800471e1  or      cl, al
0x1800471e3  mov     [rsp+358h+var_1A8], cl
0x1800471ea  and     cl, 0DFh
0x1800471ed  or      cl, 18h
0x1800471f0  mov     [rsp+358h+var_1A8], cl
0x1800471f7  mov     al, cl
0x1800471f9  xor     al, [rsi+88h]
0x1800471ff  and     al, 7
0x180047201  xor     al, cl
0x180047203  mov     [rsp+358h+var_1A8], al
0x18004720a  mov     al, [rsp+358h+var_300]
0x18004720e  mov     [rsp+358h+var_1A8+1], al
0x180047215  mov     al, [rsi+0Dh]
0x180047218  mov     [rsp+358h+var_1A8+2], al
0x18004721f  mov     eax, [rsp+358h+var_2A8]
0x180047226  mov     [rsp+358h+var_1A8+3], al
0x18004722d  mov     rcx, [rsp+358h+var_248]
0x180047235  call    ?NtpTimeOffsetFromNtTimeOffset@@YA?AUNtpTimeOffset@@UNtTimeOffset@@@Z; NtpTimeOffsetFromNtTimeOffset(NtTimeOffset)
0x18004723a  mov     dword ptr [rsp+358h+var_1A8+4], eax
0x180047241  mov     rax, [rsp+358h+var_2D8]
0x180047249  sub     rax, [rsp+358h+var_280]
0x180047251  mov     rcx, rax
0x180047254  neg     rcx
0x180047257  cmovs   rcx, rax
0x18004725b  cmp     [rsp+358h+var_307], 3
0x180047260  jz      short loc_180047284
0x180047262  mov     rax, 0C92A69C000h
0x18004726c  cmp     rcx, rax
0x18004726f  ja      short loc_180047284
0x180047271  mov     rax, 0C22E450672894AB7h
0x18004727b  mul     rcx
0x18004727e  shr     rdx, 10h
0x180047282  jmp     short loc_180047289
0x180047284  mov     edx, 989680h
0x180047289  mov     rcx, [rsp+358h+var_288]
0x180047291  add     rcx, rdx
0x180047294  add     rcx, [rsp+358h+var_258]
0x18004729c  mov     eax, 9896800h
0x1800472a1  cmp     rcx, rax
0x1800472a4  cmova   rcx, rax
0x1800472a8  call    ?NtpTimePeriodFromNtTimePeriod@@YA?AUNtpTimePeriod@@UNtTimePeriod@@@Z; NtpTimePeriodFromNtTimePeriod(NtTimePeriod)
0x1800472ad  mov     dword ptr [rsp+358h+var_1A8+8], eax
0x1800472b4  mov     eax, [rsp+358h+var_2A4]
0x1800472bb  mov     dword ptr [rsp+358h+var_1A8+0Ch], eax
0x1800472c2  mov     rcx, [rsp+358h+var_280]
0x1800472ca  call    ?NtpTimeEpochFromNtTimeEpoch@@YA?AUNtpTimeEpoch@@UNtTimeEpoch@@@Z; NtpTimeEpochFromNtTimeEpoch(NtTimeEpoch)
0x1800472cf  mov     qword ptr [rsp+358h+var_198], rax
0x1800472d7  mov     rax, [rsi+50h]
0x1800472db  mov     qword ptr [rsp+358h+var_198+8], rax
0x1800472e3  mov     rcx, [rsi+58h]
0x1800472e7  call    ?NtpTimeEpochFromNtTimeEpoch@@YA?AUNtpTimeEpoch@@UNtTimeEpoch@@@Z; NtpTimeEpochFromNtTimeEpoch(NtTimeEpoch)
0x1800472ec  mov     qword ptr [rsp+358h+var_188], rax
0x1800472f4  mov     edx, [rsp+358h+arg_20]; unsigned int
0x1800472fb  mov     rcx, rbx; char *
0x1800472fe  call    ?IsValidIPProtoControl@@YAHPEADK@Z; IsValidIPProtoControl(char *,ulong)
0x180047303  mov     [rsp+358h+var_2E8], eax
0x180047307  test    eax, eax
0x180047309  jnz     short loc_180047327
0x18004730b  lea     ecx, [rax+6]
0x18004730e  call    FileLogAllowEntry
0x180047313  test    al, al
0x180047315  jz      short loc_180047323
0x180047317  lea     rcx, aNoValidIpproto; "No valid IPPROTO Control passed in. Can"...
0x18004731e  call    FileLogAdd
0x180047323  xor     eax, eax
0x180047325  jmp     short loc_180047329
0x180047327  mov     eax, [rbx]
0x180047329  mov     [rsp+358h+var_2F8], eax
0x18004732d  mov     ebx, eax
0x18004732f  add     rbx, 7
0x180047333  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180047337  cmp     rbx, r15
0x18004733a  jbe     short loc_180047362
0x18004733c  mov     ecx, 6
0x180047341  call    FileLogAllowEntry
0x180047346  test    al, al
0x180047348  jz      short loc_18004735C
0x18004734a  mov     r8d, r15d
0x18004734d  mov     rdx, rbx
0x180047350  lea     rcx, aInsufficientBu; "Insufficient buffer for ip_proto info. "...
0x180047357  call    FileLogAdd
0x18004735c  xor     eax, eax
0x18004735e  mov     [rsp+358h+var_2F8], eax
0x180047362  lea     rbx, [rsp+358h+var_A8]
0x18004736a  mov     [rsp+358h+var_278], rbx
0x180047372  cmp     [rsp+358h+var_2E8], 0
0x180047377  jz      loc_180047412
0x18004737d  test    eax, eax
0x18004737f  jz      loc_180047412
0x180047385  mov     r8d, eax; Size
0x180047388  mov     rdx, [rsp+358h+Src]; Src
0x180047390  lea     rcx, [rsp+358h+var_A8]; void *
0x180047398  call    memcpy_0
0x18004739d  mov     eax, [rsp+358h+var_2F8]
0x1800473a1  add     eax, 7
0x1800473a4  and     eax, 0FFFFFFF8h
0x1800473a7  mov     [rsp+358h+var_304], eax
0x1800473ab  mov     [rsp+358h+var_260], eax
0x1800473b2  lea     rax, [rsp+358h+var_A8]
0x1800473ba  mov     [rsp+358h+var_1B8], rax
0x1800473c2  mov     [rsp+358h+var_1C0], r15d
0x1800473ca  lea     rax, [rsp+358h+var_A8]
0x1800473d2  mov     [rsp+358h+var_278], rax
0x1800473da  mov     rax, [rsp+358h+var_A8]
0x1800473e2  add     rax, 7
0x1800473e6  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800473ea  lea     rbx, [rsp+358h+var_A8]
0x1800473f2  add     rbx, rax
0x1800473f5  lea     rcx, [rbx+10h]
0x1800473f9  xor     eax, eax
0x1800473fb  lea     rdx, [rsp+358h+var_68]
0x180047403  cmp     rcx, rdx
0x180047406  cmova   rbx, rax
0x18004740a  mov     [rsp+358h+var_278], rbx
0x180047412  mov     rax, [rsp+358h+var_2C0]
0x18004741a  cmp     byte ptr [rax+99h], 0
0x180047421  jz      loc_18004750D
0x180047427  call    ?GetTxDelay@@YA_JXZ; GetTxDelay(void)
0x18004742c  mov     [rsp+358h+var_2B0], rax
0x180047434  mov     [rsp+358h+var_1F0], rax
0x18004743c  mov     r13d, edi
0x18004743f  lock xadd cs:dword_1800A4998, r13d
0x180047448  add     r13d, edi
0x18004744b  mov     [rsp+358h+var_2C8], r13d
0x180047453  cmp     r13d, 0Ah
0x180047457  jbe     short loc_18004748D
0x180047459  lock dec cs:dword_1800A4998
0x180047460  mov     ecx, 6Ah ; 'j'
0x180047465  call    FileLogAllowEntry
0x18004746a  test    al, al
0x18004746c  jz      short loc_18004747D
0x18004746e  mov     edx, r13d
0x180047471  lea     rcx, aHaReqcountDSki; " HA reqcount:%d skipping tx delay\n"
0x180047478  call    FileLogAdd
0x18004747d  xor     r13d, r13d
0x180047480  mov     [rsp+358h+var_2C8], r13d
0x180047488  jmp     loc_18004750D
0x18004748d  mov     ecx, [rsp+358h+var_304]
0x180047491  add     ecx, 18h
0x180047494  xor     eax, eax
0x180047496  cmp     ecx, r15d
0x180047499  cmova   rbx, rax
0x18004749d  mov     [rsp+358h+var_278], rbx
0x1800474a5  test    rbx, rbx
0x1800474a8  jz      short loc_1800474F6
0x1800474aa  mov     r12d, edi
0x1800474ad  lock xadd cs:dword_1800A3318, r12d
0x1800474b6  add     r12d, edi
0x1800474b9  cmp     r12d, 0FFFFFFFFh
0x1800474bd  jnz     short loc_1800474CE
0x1800474bf  mov     r12d, edi
0x1800474c2  lock xadd cs:dword_1800A3318, r12d
0x1800474cb  add     r12d, edi
0x1800474ce  mov     qword ptr [rbx], 14h
0x1800474d5  mov     dword ptr [rbx+8], 0FFFFh
0x1800474dc  mov     dword ptr [rbx+0Ch], 300Bh
0x1800474e3  mov     [rbx+10h], r12d
0x1800474e7  mov     ebx, ecx
0x1800474e9  mov     [rsp+358h+var_304], ecx
0x1800474ed  mov     [rsp+358h+var_260], ecx
0x1800474f4  jmp     short loc_180047511
0x1800474f6  xor     ecx, ecx
0x1800474f8  call    FileLogAllowEntry
0x1800474fd  test    al, al
0x1800474ff  jz      short loc_18004750D
0x180047501  lea     rcx, aInsufficientCo; "Insufficient control msg buffer to requ"...
0x180047508  call    FileLogAdd
0x18004750d  mov     ebx, [rsp+358h+var_304]
0x180047511  xor     eax, eax
0x180047513  test    ebx, ebx
0x180047515  lea     rcx, [rsp+358h+var_A8]
0x18004751d  cmovz   rcx, rax
0x180047521  mov     [rsp+358h+var_290], rcx
0x180047529  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180047530  lea     rdx, [rsp+358h+var_2D8]
0x180047538  mov     ecx, 3
0x18004753d  mov     rax, [rax+10h]
0x180047541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047546  mov     rax, [rsp+358h+var_2B0]
0x18004754e  test    rax, rax
0x180047551  jz      short loc_18004755B
0x180047553  add     [rsp+358h+var_2D8], rax
0x18004755b  mov     rcx, [rsp+358h+var_2D8]
0x180047563  call    ?NtpTimeEpochFromNtTimeEpoch@@YA?AUNtpTimeEpoch@@UNtTimeEpoch@@@Z; NtpTimeEpochFromNtTimeEpoch(NtTimeEpoch)
0x180047568  mov     qword ptr [rsp+358h+var_188+8], rax
  ... truncated ...
```
