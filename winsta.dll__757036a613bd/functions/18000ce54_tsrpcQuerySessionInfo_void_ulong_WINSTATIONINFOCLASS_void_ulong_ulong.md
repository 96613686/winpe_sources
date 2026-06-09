# _tsrpcQuerySessionInfo(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)

- ea: `0x18000ce54`
- end: `0x18000d2e1`
- name: `?_tsrpcQuerySessionInfo@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z`
- size: `1165`
- prototype: `unsigned __int8 __usercall@<al>(void *@<rcx>, unsigned int@<edx>, enum _WINSTATIONINFOCLASS@<r8d>, void *@<r9>, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting`

## callers

- `0x180003ba8`
- `0x18000c820`

## callees

- `0x1800039e8`
- `0x180004114`
- `0x180005c30`
- `0x180005fcc`
- `0x1800067b0`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000aa20`
- `0x18000ad50`
- `0x18000ce54`
- `0x18000dcc4`
- `0x180012828`
- `0x1800132c8`
- `0x18001ffbc`
- `0x18002256c`
- `0x18002eb08`
- `0x18002ebbc`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d247`
- `ntdll!RtlNtStatusToDosError` at `0x18000d247`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfbe`

## string_xrefs

- `0x18000cf06`: `Failed to open binding`
- `0x18000d272`: `Session::Open failed: 0x%x in %s`
- `0x18000d0bd`: `GetConfigData failed: 0x%x in %s`

## pseudocode

```c
char __fastcall _tsrpcQuerySessionInfo(
        void *a1,
        unsigned int a2,
        int a3,
        struct _WINSTATIONINFORMATIONW *a4,
        unsigned int a5,
        unsigned int *a6)
{
  char v9; // si
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int WinStationInformation; // ebx
  ULONG v17; // eax
  DWORD v18; // ecx
  unsigned int v19; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  void *v26; // rax
  unsigned int v27; // eax
  void *v28; // rax
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v30[12]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  __int128 v33; // [rsp+60h] [rbp-A0h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  char v37[208]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+168h] [rbp+68h]

  v31 = 0;
  v38 = 0;
  v36 = 0;
  v32 = -1;
  v9 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  memset_0(v37, 0, sizeof(v37));
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v30, a1, 0);
  if ( a2 == -1 )
  {
    _DbgPrintMessage(8, "_tsrpcQuerySessionInfo - SessionId is LOGONID_CURRENT - UNEXPECTED!!");
    goto LABEL_25;
  }
  if ( CSmartPublicBinding::operator void *(v30) )
  {
    if ( a3 <= 8 )
    {
      if ( a3 == 8 )
      {
        WinStationInformation = GetWinStationInformation((CPublicBinding *)a1, a2, a4, a5, a6);
        if ( WinStationInformation < 0 )
        {
          _DbgPrintMessage(
            8,
            "GetWinStationInfromation failed: 0x%x in %s",
            (unsigned int)WinStationInformation,
            "_tsrpcQuerySessionInfo");
          goto LABEL_18;
        }
        goto LABEL_24;
      }
      v11 = a3 - 1;
      if ( !v11 )
      {
        WinStationInformation = GetConfigData(a1, a2, (struct _WINSTATIONCONFIGW *)a4, a5, a6);
        if ( WinStationInformation < 0 )
        {
          _DbgPrintMessage(
            8,
            "GetConfigData failed: 0x%x in %s",
            (unsigned int)WinStationInformation,
            "_tsrpcQuerySessionInfo");
          goto LABEL_18;
        }
        goto LABEL_24;
      }
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( !v13 )
        {
          WinStationInformation = GetWinStationWd(a1, a2, (struct _WDCONFIGW *)a4, a5, a6);
          if ( WinStationInformation < 0 )
          {
            _DbgPrintMessage(
              8,
              "GetWinStationWd failed: 0x%x in %s",
              (unsigned int)WinStationInformation,
              "_tsrpcQuerySessionInfo");
            goto LABEL_18;
          }
          goto LABEL_24;
        }
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 2;
          if ( !v15 )
          {
            WinStationInformation = GetClientData(a1, a2, (struct _WINSTATIONCLIENTW *)a4, a5, a6);
            if ( WinStationInformation < 0 )
            {
              _DbgPrintMessage(
                8,
                "GetClientData failed: 0x%x in %s",
                (unsigned int)WinStationInformation,
                "_tsrpcQuerySessionInfo");
              goto LABEL_18;
            }
LABEL_24:
            v9 = 1;
            goto LABEL_25;
          }
          if ( v15 == 1 )
          {
            WinStationInformation = GetWinStationModules(a1, a2, a4->Reserved2, a5, a6);
            if ( WinStationInformation < 0 )
            {
              _DbgPrintMessage(
                8,
                "GetWinStationModule failed: 0x%x in %s",
                (unsigned int)WinStationInformation,
                "_tsrpcQuerySessionInfo");
LABEL_18:
              v17 = ConvertHRESULT2WIN32(WinStationInformation);
LABEL_19:
              v18 = v17;
LABEL_20:
              SetLastError(v18);
              goto LABEL_25;
            }
            goto LABEL_24;
          }
LABEL_42:
          v18 = 1;
          goto LABEL_20;
        }
        v19 = 736;
        if ( a5 < 0x2E0 )
        {
          WinStationInformation = -2147024809;
          _DbgPrintMessage(8, "GetWinStationPd failed: 0x%x in %s", 2147942487LL, "_tsrpcQuerySessionInfo");
          goto LABEL_18;
        }
        memset_0(a4, 0, 0x2E0u);
        *(_DWORD *)&a4->Reserved2[68] = 2;
      }
      else
      {
        v19 = 568;
        if ( a5 < 0x238 )
        {
          WinStationInformation = -2147024809;
          _DbgPrintMessage(8, "GetWinStationPdParams failed: 0x%x in %s", 2147942487LL, "_tsrpcQuerySessionInfo");
          goto LABEL_18;
        }
        memset_0(a4, 0, 0x238u);
      }
      *a6 = v19;
      goto LABEL_24;
    }
    v21 = a3 - 20;
    if ( !v21 )
    {
      WinStationInformation = GetWinStationVirtualData(a1, a2, a4->Reserved2, a5, a6);
      if ( WinStationInformation < 0 )
      {
        _DbgPrintMessage(
          8,
          "GetWinStationVirtualData failed: 0x%x in %s",
          (unsigned int)WinStationInformation,
          "_tsrpcQuerySessionInfo");
        goto LABEL_18;
      }
      goto LABEL_24;
    }
    v22 = v21 - 8;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
      {
        WinStationInformation = GetWinStationAddress(a1, a2, (struct WINSTATIONREMOTEADDRESS *)a4, a5, a6);
        if ( WinStationInformation < 0 )
        {
          _DbgPrintMessage(
            8,
            "GetWinStationAddress failed: 0x%x in %s",
            (unsigned int)WinStationInformation,
            "_tsrpcQuerySessionInfo");
          goto LABEL_18;
        }
        goto LABEL_24;
      }
      v24 = v23 - 10;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( !v25 )
        {
          WinStationInformation = GetWinStationInformationEx(a1, a2, (struct _WINSTATIONINFORMATIONEX *)a4, a5, a6);
          if ( WinStationInformation < 0 )
          {
            _DbgPrintMessage(
              8,
              "GetWinStationInformationEx failed: 0x%x in %s",
              (unsigned int)WinStationInformation,
              "_tsrpcQuerySessionInfo");
            goto LABEL_18;
          }
          goto LABEL_24;
        }
        if ( v25 != 2 )
          goto LABEL_42;
        if ( a5 >= 0x10 )
        {
          v26 = (void *)CSmartPublicBinding::operator void *(v30);
          WinStationInformation = CSmartSession::Open((CSmartSession *)&v31, a2, v26);
          if ( WinStationInformation >= 0 )
          {
            WinStationInformation = CSmartSession::GetActivityId((CSmartSession *)&v31, (struct _GUID *)a4);
            if ( WinStationInformation < 0 )
            {
              _DbgPrintMessage(
                8,
                "Session::GetActivityId failed: 0x%x in %s",
                (unsigned int)WinStationInformation,
                "_tsrpcQuerySessionInfo");
              goto LABEL_18;
            }
            *a6 = 16;
            goto LABEL_24;
          }
LABEL_60:
          _DbgPrintMessage(
            8,
            "Session::Open failed: 0x%x in %s",
            (unsigned int)WinStationInformation,
            "_tsrpcQuerySessionInfo");
          goto LABEL_18;
        }
LABEL_58:
        v17 = RtlNtStatusToDosError(-1073741789);
        goto LABEL_19;
      }
      v29 = 0;
      if ( a5 < 4 )
      {
        WinStationInformation = -2147024809;
        _DbgPrintMessage(8, "WinStationType failed: 0x%x in %s", 2147942487LL, "_tsrpcQuerySessionInfo");
        goto LABEL_18;
      }
      WinStationInformation = GetWinStationType(a1, a2, &v29);
      if ( WinStationInformation < 0 )
      {
        _DbgPrintMessage(
          8,
          "GetWinStationType failed: 0x%x in %s",
          (unsigned int)WinStationInformation,
          "_tsrpcQuerySessionInfo");
        goto LABEL_18;
      }
      v27 = v29;
    }
    else
    {
      if ( a5 < 4 )
        goto LABEL_58;
      v28 = (void *)CSmartPublicBinding::operator void *(v30);
      WinStationInformation = CSmartSession::Open((CSmartSession *)&v31, a2, v28);
      if ( WinStationInformation < 0 )
        goto LABEL_60;
      WinStationInformation = CSmartSession::IsDesktopLocked((CSmartSession *)&v31);
      if ( WinStationInformation < 0 )
      {
        _DbgPrintMessage(
          8,
          "IsDesktopLocked failed: 0x%x in %s",
          (unsigned int)WinStationInformation,
          "_tsrpcQuerySessionInfo");
        goto LABEL_18;
      }
      v27 = WinStationInformation != 1;
    }
    *(_DWORD *)a4->Reserved2 = v27;
    *a6 = 4;
    goto LABEL_24;
  }
  _DbgPrintMessage(8, "Failed to open binding");
LABEL_25:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v30);
  CSmartSession::~CSmartSession((CSmartSession *)&v31);
  return v9;
}

```

## disassembly

```asm
0x18000ce54  mov     [rsp-8+arg_10], rbx
0x18000ce59  push    rbp
0x18000ce5a  push    rsi
0x18000ce5b  push    rdi
0x18000ce5c  push    r12
0x18000ce5e  push    r13
0x18000ce60  push    r14
0x18000ce62  push    r15
0x18000ce64  lea     rbp, [rsp-80h]
0x18000ce69  sub     rsp, 180h
0x18000ce70  mov     rax, cs:__security_cookie
0x18000ce77  xor     rax, rsp
0x18000ce7a  mov     [rbp+0B0h+var_40], rax
0x18000ce7e  mov     r15, [rbp+0B0h+arg_28]
0x18000ce85  xor     eax, eax
0x18000ce87  xorps   xmm0, xmm0
0x18000ce8a  mov     [rsp+1B0h+var_160], rax
0x18000ce8f  mov     ebx, r8d
0x18000ce92  mov     [rbp+0B0h+var_48], rax
0x18000ce96  mov     r12d, edx
0x18000ce99  mov     [rbp+0B0h+var_120], rax
0x18000ce9d  mov     r13, rcx
0x18000cea0  or      edi, 0FFFFFFFFh
0x18000cea3  xor     edx, edx; Val
0x18000cea5  mov     [rsp+1B0h+var_158], edi
0x18000cea9  mov     r8d, 0D0h; Size
0x18000ceaf  lea     rcx, [rbp+0B0h+var_118]; void *
0x18000ceb3  mov     sil, al
0x18000ceb6  mov     r14, r9
0x18000ceb9  movups  [rsp+1B0h+var_150], xmm0
0x18000cebe  movups  [rsp+1B0h+var_140], xmm0
0x18000cec3  movups  [rbp+0B0h+var_130], xmm0
0x18000cec7  call    memset_0
0x18000cecc  xor     r8d, r8d; int
0x18000cecf  lea     rcx, [rsp+1B0h+var_178]; this
0x18000ced4  mov     rdx, r13; void *
0x18000ced7  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000cedc  cmp     r12d, edi
0x18000cedf  jnz     short loc_18000CEF7
0x18000cee1  lea     rdx, aTsrpcquerysess_0; "_tsrpcQuerySessionInfo - SessionId is L"...
0x18000cee8  mov     ecx, 8; int
0x18000ceed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cef2  jmp     loc_18000CFEE
0x18000cef7  lea     rcx, [rsp+1B0h+var_178]; unsigned __int16 *
0x18000cefc  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000cf01  test    rax, rax
0x18000cf04  jnz     short loc_18000CF0F
0x18000cf06  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000cf0d  jmp     short loc_18000CEE8
0x18000cf0f  mov     edi, 8
0x18000cf14  cmp     ebx, edi
0x18000cf16  jg      loc_18000D0F9
0x18000cf1c  jz      loc_18000D0C9
0x18000cf22  sub     ebx, 1
0x18000cf25  jz      loc_18000D099
0x18000cf2b  sub     ebx, 1
0x18000cf2e  jz      loc_18000D069
0x18000cf34  sub     ebx, 1
0x18000cf37  jz      loc_18000D03D
0x18000cf3d  sub     ebx, 1
0x18000cf40  jz      loc_18000CFC6
0x18000cf46  sub     ebx, 2
0x18000cf49  jz      short loc_18000CF7D
0x18000cf4b  cmp     ebx, 1
0x18000cf4e  jnz     loc_18000D126
0x18000cf54  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000cf5b  mov     r8, r14; unsigned __int8 *
0x18000cf5e  mov     edx, r12d; unsigned int
0x18000cf61  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000cf66  mov     rcx, r13; void *
0x18000cf69  call    ?GetWinStationModules@@YAJPEAXKPEAEKPEAK@Z; GetWinStationModules(void *,ulong,uchar *,ulong,ulong *)
0x18000cf6e  mov     ebx, eax
0x18000cf70  test    eax, eax
0x18000cf72  jns     short loc_18000CFEB
0x18000cf74  lea     rdx, aGetwinstationm; "GetWinStationModule failed: 0x%x in %s"
0x18000cf7b  jmp     short loc_18000CFA4
0x18000cf7d  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000cf84  mov     r8, r14; struct _WINSTATIONCLIENTW *
0x18000cf87  mov     edx, r12d; unsigned int
0x18000cf8a  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000cf8f  mov     rcx, r13; void *
0x18000cf92  call    ?GetClientData@@YAJPEAXKPEAU_WINSTATIONCLIENTW@@KPEAK@Z; GetClientData(void *,ulong,_WINSTATIONCLIENTW *,ulong,ulong *)
0x18000cf97  mov     ebx, eax
0x18000cf99  test    eax, eax
0x18000cf9b  jns     short loc_18000CFEB
0x18000cf9d  lea     rdx, aGetclientdataF; "GetClientData failed: 0x%x in %s"
0x18000cfa4  lea     r9, aTsrpcquerysess; "_tsrpcQuerySessionInfo"
0x18000cfab  mov     r8d, ebx
0x18000cfae  mov     ecx, edi; int
0x18000cfb0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cfb5  mov     ecx, ebx; int
0x18000cfb7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000cfbc  mov     ecx, eax; dwErrCode
0x18000cfbe  call    cs:__imp_SetLastError
0x18000cfc4  jmp     short loc_18000CFEE
0x18000cfc6  mov     ebx, 2E0h
0x18000cfcb  cmp     [rbp+0B0h+arg_20], ebx
0x18000cfd1  jb      short loc_18000D02C
0x18000cfd3  mov     r8d, ebx; Size
0x18000cfd6  xor     edx, edx; Val
0x18000cfd8  mov     rcx, r14; void *
0x18000cfdb  call    memset_0
0x18000cfe0  mov     dword ptr [r14+44h], 2
0x18000cfe8  mov     [r15], ebx
0x18000cfeb  mov     sil, 1
0x18000cfee  lea     rcx, [rsp+1B0h+var_178]; this
0x18000cff3  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000cff8  lea     rcx, [rsp+1B0h+var_160]; this
0x18000cffd  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x18000d002  mov     al, sil
0x18000d005  mov     rcx, [rbp+0B0h+var_40]
0x18000d009  xor     rcx, rsp; StackCookie
0x18000d00c  call    __security_check_cookie
0x18000d011  mov     rbx, [rsp+1B0h+arg_10]
0x18000d019  add     rsp, 180h
0x18000d020  pop     r15
0x18000d022  pop     r14
0x18000d024  pop     r13
0x18000d026  pop     r12
0x18000d028  pop     rdi
0x18000d029  pop     rsi
0x18000d02a  pop     rbp
0x18000d02b  retn
0x18000d02c  mov     ebx, 80070057h
0x18000d031  lea     rdx, aGetwinstationp_0; "GetWinStationPd failed: 0x%x in %s"
0x18000d038  jmp     loc_18000CFA4
0x18000d03d  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000d044  mov     r8, r14; struct _WDCONFIGW *
0x18000d047  mov     edx, r12d; unsigned int
0x18000d04a  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000d04f  mov     rcx, r13; void *
0x18000d052  call    ?GetWinStationWd@@YAJPEAXKPEAU_WDCONFIGW@@KPEAK@Z; GetWinStationWd(void *,ulong,_WDCONFIGW *,ulong,ulong *)
0x18000d057  mov     ebx, eax
0x18000d059  test    eax, eax
0x18000d05b  jns     short loc_18000CFEB
0x18000d05d  lea     rdx, aGetwinstationw; "GetWinStationWd failed: 0x%x in %s"
0x18000d064  jmp     loc_18000CFA4
0x18000d069  mov     ebx, 238h
0x18000d06e  cmp     [rbp+0B0h+arg_20], ebx
0x18000d074  jb      short loc_18000D088
0x18000d076  mov     r8d, ebx; Size
0x18000d079  xor     edx, edx; Val
0x18000d07b  mov     rcx, r14; void *
0x18000d07e  call    memset_0
0x18000d083  jmp     loc_18000CFE8
0x18000d088  mov     ebx, 80070057h
0x18000d08d  lea     rdx, aGetwinstationp; "GetWinStationPdParams failed: 0x%x in %"...
0x18000d094  jmp     loc_18000CFA4
0x18000d099  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000d0a0  mov     r8, r14; struct _WINSTATIONCONFIGW *
0x18000d0a3  mov     edx, r12d; unsigned int
0x18000d0a6  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000d0ab  mov     rcx, r13; void *
0x18000d0ae  call    ?GetConfigData@@YAJPEAXKPEAU_WINSTATIONCONFIGW@@KPEAK@Z; GetConfigData(void *,ulong,_WINSTATIONCONFIGW *,ulong,ulong *)
0x18000d0b3  mov     ebx, eax
0x18000d0b5  test    eax, eax
0x18000d0b7  jns     loc_18000CFEB
0x18000d0bd  lea     rdx, aGetconfigdataF; "GetConfigData failed: 0x%x in %s"
0x18000d0c4  jmp     loc_18000CFA4
0x18000d0c9  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000d0d0  mov     r8, r14; struct _WINSTATIONINFORMATIONW *
0x18000d0d3  mov     edx, r12d; unsigned int
0x18000d0d6  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000d0db  mov     rcx, r13; this
0x18000d0de  call    ?GetWinStationInformation@@YAJPEAXKPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z; GetWinStationInformation(void *,ulong,_WINSTATIONINFORMATIONW *,ulong,ulong *)
0x18000d0e3  mov     ebx, eax
0x18000d0e5  test    eax, eax
0x18000d0e7  jns     loc_18000CFEB
0x18000d0ed  lea     rdx, aGetwinstationi_2; "GetWinStationInfromation failed: 0x%x i"...
0x18000d0f4  jmp     loc_18000CFA4
0x18000d0f9  sub     ebx, 14h
0x18000d0fc  jz      loc_18000D2B1
0x18000d102  sub     ebx, edi
0x18000d104  jz      loc_18000D239
0x18000d10a  sub     ebx, 1
0x18000d10d  jz      loc_18000D209
0x18000d113  sub     ebx, 0Ah
0x18000d116  jz      loc_18000D1BC
0x18000d11c  sub     ebx, 1
0x18000d11f  jz      short loc_18000D18C
0x18000d121  cmp     ebx, 2
0x18000d124  jz      short loc_18000D130
0x18000d126  mov     ecx, 1
0x18000d12b  jmp     loc_18000CFBE
0x18000d130  cmp     [rbp+0B0h+arg_20], 10h
0x18000d137  jb      loc_18000D242
0x18000d13d  lea     rcx, [rsp+1B0h+var_178]; unsigned __int16 *
0x18000d142  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000d147  mov     r8, rax; void *
0x18000d14a  lea     rcx, [rsp+1B0h+var_160]; this
0x18000d14f  mov     edx, r12d; unsigned int
0x18000d152  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x18000d157  mov     ebx, eax
0x18000d159  test    eax, eax
0x18000d15b  js      loc_18000D272
0x18000d161  mov     rdx, r14; struct _GUID *
0x18000d164  lea     rcx, [rsp+1B0h+var_160]; this
0x18000d169  call    ?GetActivityId@CSmartSession@@QEAAJPEAU_GUID@@@Z; CSmartSession::GetActivityId(_GUID *)
0x18000d16e  mov     ebx, eax
0x18000d170  test    eax, eax
0x18000d172  jns     short loc_18000D180
0x18000d174  lea     rdx, aSessionGetacti; "Session::GetActivityId failed: 0x%x in "...
0x18000d17b  jmp     loc_18000CFA4
0x18000d180  mov     dword ptr [r15], 10h
0x18000d187  jmp     loc_18000CFEB
0x18000d18c  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000d193  mov     r8, r14; struct _WINSTATIONINFORMATIONEX *
0x18000d196  mov     edx, r12d; unsigned int
0x18000d199  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000d19e  mov     rcx, r13; void *
0x18000d1a1  call    ?GetWinStationInformationEx@@YAJPEAXKPEAU_WINSTATIONINFORMATIONEX@@KPEAK@Z; GetWinStationInformationEx(void *,ulong,_WINSTATIONINFORMATIONEX *,ulong,ulong *)
0x18000d1a6  mov     ebx, eax
0x18000d1a8  test    eax, eax
0x18000d1aa  jns     loc_18000CFEB
0x18000d1b0  lea     rdx, aGetwinstationi_0; "GetWinStationInformationEx failed: 0x%x"...
0x18000d1b7  jmp     loc_18000CFA4
0x18000d1bc  cmp     [rbp+0B0h+arg_20], 4
0x18000d1c3  mov     [rsp+1B0h+var_180], 0
0x18000d1cb  jnb     short loc_18000D1DE
0x18000d1cd  mov     ebx, 80070057h
0x18000d1d2  lea     rdx, aWinstationtype; "WinStationType failed: 0x%x in %s"
0x18000d1d9  jmp     loc_18000CFA4
0x18000d1de  lea     r8, [rsp+1B0h+var_180]; unsigned int *
0x18000d1e3  mov     edx, r12d; unsigned int
0x18000d1e6  mov     rcx, r13; void *
0x18000d1e9  call    ?GetWinStationType@@YAJPEAXKPEAK@Z; GetWinStationType(void *,ulong,ulong *)
0x18000d1ee  mov     ebx, eax
0x18000d1f0  test    eax, eax
0x18000d1f2  jns     short loc_18000D200
0x18000d1f4  lea     rdx, aGetwinstationt; "GetWinStationType failed: 0x%x in %s"
0x18000d1fb  jmp     loc_18000CFA4
0x18000d200  mov     eax, [rsp+1B0h+var_180]
0x18000d204  jmp     loc_18000D2A2
0x18000d209  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000d210  mov     r8, r14; struct WINSTATIONREMOTEADDRESS *
0x18000d213  mov     edx, r12d; unsigned int
0x18000d216  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000d21b  mov     rcx, r13; void *
0x18000d21e  call    ?GetWinStationAddress@@YAJPEAXKPEAUWINSTATIONREMOTEADDRESS@@KPEAK@Z; GetWinStationAddress(void *,ulong,WINSTATIONREMOTEADDRESS *,ulong,ulong *)
0x18000d223  mov     ebx, eax
0x18000d225  test    eax, eax
0x18000d227  jns     loc_18000CFEB
0x18000d22d  lea     rdx, aGetwinstationa; "GetWinStationAddress failed: 0x%x in %s"
0x18000d234  jmp     loc_18000CFA4
0x18000d239  cmp     [rbp+0B0h+arg_20], 4
0x18000d240  jnb     short loc_18000D252
0x18000d242  mov     ecx, 0C0000023h; Status
0x18000d247  call    cs:__imp_RtlNtStatusToDosError
0x18000d24d  jmp     loc_18000CFBC
0x18000d252  lea     rcx, [rsp+1B0h+var_178]; unsigned __int16 *
0x18000d257  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000d25c  mov     r8, rax; void *
0x18000d25f  lea     rcx, [rsp+1B0h+var_160]; this
0x18000d264  mov     edx, r12d; unsigned int
0x18000d267  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x18000d26c  mov     ebx, eax
0x18000d26e  test    eax, eax
0x18000d270  jns     short loc_18000D27E
0x18000d272  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x18000d279  jmp     loc_18000CFA4
0x18000d27e  lea     rcx, [rsp+1B0h+var_160]; this
0x18000d283  call    ?IsDesktopLocked@CSmartSession@@QEAAJXZ; CSmartSession::IsDesktopLocked(void)
0x18000d288  mov     ebx, eax
0x18000d28a  test    eax, eax
0x18000d28c  jns     short loc_18000D29A
0x18000d28e  lea     rdx, aIsdesktoplocke; "IsDesktopLocked failed: 0x%x in %s"
0x18000d295  jmp     loc_18000CFA4
0x18000d29a  xor     eax, eax
0x18000d29c  cmp     ebx, 1
0x18000d29f  setnz   al
0x18000d2a2  mov     [r14], eax
0x18000d2a5  mov     dword ptr [r15], 4
0x18000d2ac  jmp     loc_18000CFEB
0x18000d2b1  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000d2b8  mov     r8, r14; unsigned __int8 *
0x18000d2bb  mov     edx, r12d; unsigned int
0x18000d2be  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000d2c3  mov     rcx, r13; void *
0x18000d2c6  call    ?GetWinStationVirtualData@@YAJPEAXKPEAEKPEAK@Z; GetWinStationVirtualData(void *,ulong,uchar *,ulong,ulong *)
0x18000d2cb  mov     ebx, eax
0x18000d2cd  test    eax, eax
0x18000d2cf  jns     loc_18000CFEB
0x18000d2d5  lea     rdx, aGetwinstationv; "GetWinStationVirtualData failed: 0x%x i"...
0x18000d2dc  jmp     loc_18000CFA4
```
