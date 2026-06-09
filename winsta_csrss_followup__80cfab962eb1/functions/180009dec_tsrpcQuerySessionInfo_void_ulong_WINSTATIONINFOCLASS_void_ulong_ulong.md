# _tsrpcQuerySessionInfo(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)

- ea: `0x180009dec`
- end: `0x18000a286`
- name: `?_tsrpcQuerySessionInfo@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z`
- size: `1178`
- prototype: `unsigned __int8 __usercall@<al>(CPublicBinding *this@<rcx>, unsigned int@<edx>, enum _WINSTATIONINFOCLASS@<r8d>, void *@<r9>, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting`

## callers

- `0x1800096c0`
- `0x18000aac4`

## callees

- `0x1800016c8`
- `0x180001a10`
- `0x180002014`
- `0x180003480`
- `0x1800041a0`
- `0x180004558`
- `0x1800049a0`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180009dec`
- `0x180010bbc`
- `0x18001369c`
- `0x1800141c4`
- `0x1800216f8`
- `0x180023e6c`
- `0x1800315a0`
- `0x180031668`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000a1e6`
- `ntdll!RtlNtStatusToDosError` at `0x18000a1e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f56`

## string_xrefs

- `0x180009e9e`: `Failed to open binding`
- `0x18000a217`: `Session::Open failed: 0x%x in %s`
- `0x18000a05c`: `GetConfigData failed: 0x%x in %s`

## pseudocode

```c
char __fastcall _tsrpcQuerySessionInfo(
        CPublicBinding *this,
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
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v30, this, 0);
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
        WinStationInformation = GetWinStationInformation(this, a2, a4, a5, a6);
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
        WinStationInformation = GetConfigData(this, a2, (struct _WINSTATIONCONFIGW *)a4, a5, a6);
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
          WinStationInformation = GetWinStationWd(this, a2, (struct _WDCONFIGW *)a4, a5, a6);
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
            WinStationInformation = GetClientData(this, a2, (struct _WINSTATIONCLIENTW *)a4, a5, a6);
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
            WinStationInformation = GetWinStationModules(this, a2, a4->Reserved2, a5, a6);
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
      WinStationInformation = GetWinStationVirtualData(this, a2, a4->Reserved2, a5, a6);
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
        WinStationInformation = GetWinStationAddress(this, a2, (struct WINSTATIONREMOTEADDRESS *)a4, a5, a6);
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
          WinStationInformation = GetWinStationInformationEx(this, a2, (struct _WINSTATIONINFORMATIONEX *)a4, a5, a6);
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
      WinStationInformation = GetWinStationType(this, a2, &v29);
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
0x180009dec  mov     [rsp-8+arg_10], rbx
0x180009df1  push    rbp
0x180009df2  push    rsi
0x180009df3  push    rdi
0x180009df4  push    r12
0x180009df6  push    r13
0x180009df8  push    r14
0x180009dfa  push    r15
0x180009dfc  lea     rbp, [rsp-80h]
0x180009e01  sub     rsp, 180h
0x180009e08  mov     rax, cs:__security_cookie
0x180009e0f  xor     rax, rsp
0x180009e12  mov     [rbp+0B0h+var_40], rax
0x180009e16  mov     r15, [rbp+0B0h+arg_28]
0x180009e1d  xor     eax, eax
0x180009e1f  xorps   xmm0, xmm0
0x180009e22  mov     [rsp+1B0h+var_160], rax
0x180009e27  mov     ebx, r8d
0x180009e2a  mov     [rbp+0B0h+var_48], rax
0x180009e2e  mov     r12d, edx
0x180009e31  mov     [rbp+0B0h+var_120], rax
0x180009e35  mov     r13, rcx
0x180009e38  or      edi, 0FFFFFFFFh
0x180009e3b  xor     edx, edx; Val
0x180009e3d  mov     [rsp+1B0h+var_158], edi
0x180009e41  mov     r8d, 0D0h; Size
0x180009e47  lea     rcx, [rbp+0B0h+var_118]; void *
0x180009e4b  mov     sil, al
0x180009e4e  mov     r14, r9
0x180009e51  movups  [rsp+1B0h+var_150], xmm0
0x180009e56  movups  [rsp+1B0h+var_140], xmm0
0x180009e5b  movups  [rbp+0B0h+var_130], xmm0
0x180009e5f  call    memset_0
0x180009e64  xor     r8d, r8d; int
0x180009e67  lea     rcx, [rsp+1B0h+var_178]; this
0x180009e6c  mov     rdx, r13; void *
0x180009e6f  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180009e74  cmp     r12d, edi
0x180009e77  jnz     short loc_180009E8F
0x180009e79  lea     rdx, aTsrpcquerysess_0; "_tsrpcQuerySessionInfo - SessionId is L"...
0x180009e80  mov     ecx, 8; int
0x180009e85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009e8a  jmp     loc_180009F8C
0x180009e8f  lea     rcx, [rsp+1B0h+var_178]; unsigned __int16 *
0x180009e94  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180009e99  test    rax, rax
0x180009e9c  jnz     short loc_180009EA7
0x180009e9e  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180009ea5  jmp     short loc_180009E80
0x180009ea7  mov     edi, 8
0x180009eac  cmp     ebx, edi
0x180009eae  jg      loc_18000A098
0x180009eb4  jz      loc_18000A068
0x180009eba  sub     ebx, 1
0x180009ebd  jz      loc_18000A038
0x180009ec3  sub     ebx, 1
0x180009ec6  jz      loc_18000A008
0x180009ecc  sub     ebx, 1
0x180009ecf  jz      loc_180009FDC
0x180009ed5  sub     ebx, 1
0x180009ed8  jz      loc_180009F64
0x180009ede  sub     ebx, 2
0x180009ee1  jz      short loc_180009F15
0x180009ee3  cmp     ebx, 1
0x180009ee6  jnz     loc_18000A0C5
0x180009eec  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x180009ef3  mov     r8, r14; unsigned __int8 *
0x180009ef6  mov     edx, r12d; unsigned int
0x180009ef9  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x180009efe  mov     rcx, r13; void *
0x180009f01  call    ?GetWinStationModules@@YAJPEAXKPEAEKPEAK@Z; GetWinStationModules(void *,ulong,uchar *,ulong,ulong *)
0x180009f06  mov     ebx, eax
0x180009f08  test    eax, eax
0x180009f0a  jns     short loc_180009F89
0x180009f0c  lea     rdx, aGetwinstationm; "GetWinStationModule failed: 0x%x in %s"
0x180009f13  jmp     short loc_180009F3C
0x180009f15  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x180009f1c  mov     r8, r14; struct _WINSTATIONCLIENTW *
0x180009f1f  mov     edx, r12d; unsigned int
0x180009f22  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x180009f27  mov     rcx, r13; void *
0x180009f2a  call    ?GetClientData@@YAJPEAXKPEAU_WINSTATIONCLIENTW@@KPEAK@Z; GetClientData(void *,ulong,_WINSTATIONCLIENTW *,ulong,ulong *)
0x180009f2f  mov     ebx, eax
0x180009f31  test    eax, eax
0x180009f33  jns     short loc_180009F89
0x180009f35  lea     rdx, aGetclientdataF; "GetClientData failed: 0x%x in %s"
0x180009f3c  lea     r9, aTsrpcquerysess; "_tsrpcQuerySessionInfo"
0x180009f43  mov     r8d, ebx
0x180009f46  mov     ecx, edi; int
0x180009f48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009f4d  mov     ecx, ebx; int
0x180009f4f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180009f54  mov     ecx, eax; dwErrCode
0x180009f56  call    cs:__imp_SetLastError
0x180009f5d  nop     dword ptr [rax+rax+00h]
0x180009f62  jmp     short loc_180009F8C
0x180009f64  mov     ebx, 2E0h
0x180009f69  cmp     [rbp+0B0h+arg_20], ebx
0x180009f6f  jb      short loc_180009FCB
0x180009f71  mov     r8d, ebx; Size
0x180009f74  xor     edx, edx; Val
0x180009f76  mov     rcx, r14; void *
0x180009f79  call    memset_0
0x180009f7e  mov     dword ptr [r14+44h], 2
0x180009f86  mov     [r15], ebx
0x180009f89  mov     sil, 1
0x180009f8c  lea     rcx, [rsp+1B0h+var_178]; this
0x180009f91  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180009f96  lea     rcx, [rsp+1B0h+var_160]; this
0x180009f9b  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180009fa0  mov     al, sil
0x180009fa3  mov     rcx, [rbp+0B0h+var_40]
0x180009fa7  xor     rcx, rsp; StackCookie
0x180009faa  call    __security_check_cookie
0x180009faf  mov     rbx, [rsp+1B0h+arg_10]
0x180009fb7  add     rsp, 180h
0x180009fbe  pop     r15
0x180009fc0  pop     r14
0x180009fc2  pop     r13
0x180009fc4  pop     r12
0x180009fc6  pop     rdi
0x180009fc7  pop     rsi
0x180009fc8  pop     rbp
0x180009fc9  retn
0x180009fcb  mov     ebx, 80070057h
0x180009fd0  lea     rdx, aGetwinstationp_0; "GetWinStationPd failed: 0x%x in %s"
0x180009fd7  jmp     loc_180009F3C
0x180009fdc  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x180009fe3  mov     r8, r14; struct _WDCONFIGW *
0x180009fe6  mov     edx, r12d; unsigned int
0x180009fe9  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x180009fee  mov     rcx, r13; void *
0x180009ff1  call    ?GetWinStationWd@@YAJPEAXKPEAU_WDCONFIGW@@KPEAK@Z; GetWinStationWd(void *,ulong,_WDCONFIGW *,ulong,ulong *)
0x180009ff6  mov     ebx, eax
0x180009ff8  test    eax, eax
0x180009ffa  jns     short loc_180009F89
0x180009ffc  lea     rdx, aGetwinstationw; "GetWinStationWd failed: 0x%x in %s"
0x18000a003  jmp     loc_180009F3C
0x18000a008  mov     ebx, 238h
0x18000a00d  cmp     [rbp+0B0h+arg_20], ebx
0x18000a013  jb      short loc_18000A027
0x18000a015  mov     r8d, ebx; Size
0x18000a018  xor     edx, edx; Val
0x18000a01a  mov     rcx, r14; void *
0x18000a01d  call    memset_0
0x18000a022  jmp     loc_180009F86
0x18000a027  mov     ebx, 80070057h
0x18000a02c  lea     rdx, aGetwinstationp; "GetWinStationPdParams failed: 0x%x in %"...
0x18000a033  jmp     loc_180009F3C
0x18000a038  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000a03f  mov     r8, r14; struct _WINSTATIONCONFIGW *
0x18000a042  mov     edx, r12d; unsigned int
0x18000a045  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000a04a  mov     rcx, r13; void *
0x18000a04d  call    ?GetConfigData@@YAJPEAXKPEAU_WINSTATIONCONFIGW@@KPEAK@Z; GetConfigData(void *,ulong,_WINSTATIONCONFIGW *,ulong,ulong *)
0x18000a052  mov     ebx, eax
0x18000a054  test    eax, eax
0x18000a056  jns     loc_180009F89
0x18000a05c  lea     rdx, aGetconfigdataF; "GetConfigData failed: 0x%x in %s"
0x18000a063  jmp     loc_180009F3C
0x18000a068  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000a06f  mov     r8, r14; struct _WINSTATIONINFORMATIONW *
0x18000a072  mov     edx, r12d; unsigned int
0x18000a075  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000a07a  mov     rcx, r13; this
0x18000a07d  call    ?GetWinStationInformation@@YAJPEAXKPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z; GetWinStationInformation(void *,ulong,_WINSTATIONINFORMATIONW *,ulong,ulong *)
0x18000a082  mov     ebx, eax
0x18000a084  test    eax, eax
0x18000a086  jns     loc_180009F89
0x18000a08c  lea     rdx, aGetwinstationi_2; "GetWinStationInfromation failed: 0x%x i"...
0x18000a093  jmp     loc_180009F3C
0x18000a098  sub     ebx, 14h
0x18000a09b  jz      loc_18000A256
0x18000a0a1  sub     ebx, edi
0x18000a0a3  jz      loc_18000A1D8
0x18000a0a9  sub     ebx, 1
0x18000a0ac  jz      loc_18000A1A8
0x18000a0b2  sub     ebx, 0Ah
0x18000a0b5  jz      loc_18000A15B
0x18000a0bb  sub     ebx, 1
0x18000a0be  jz      short loc_18000A12B
0x18000a0c0  cmp     ebx, 2
0x18000a0c3  jz      short loc_18000A0CF
0x18000a0c5  mov     ecx, 1
0x18000a0ca  jmp     loc_180009F56
0x18000a0cf  cmp     [rbp+0B0h+arg_20], 10h
0x18000a0d6  jb      loc_18000A1E1
0x18000a0dc  lea     rcx, [rsp+1B0h+var_178]; unsigned __int16 *
0x18000a0e1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a0e6  mov     r8, rax; void *
0x18000a0e9  lea     rcx, [rsp+1B0h+var_160]; this
0x18000a0ee  mov     edx, r12d; unsigned int
0x18000a0f1  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x18000a0f6  mov     ebx, eax
0x18000a0f8  test    eax, eax
0x18000a0fa  js      loc_18000A217
0x18000a100  mov     rdx, r14; struct _GUID *
0x18000a103  lea     rcx, [rsp+1B0h+var_160]; this
0x18000a108  call    ?GetActivityId@CSmartSession@@QEAAJPEAU_GUID@@@Z; CSmartSession::GetActivityId(_GUID *)
0x18000a10d  mov     ebx, eax
0x18000a10f  test    eax, eax
0x18000a111  jns     short loc_18000A11F
0x18000a113  lea     rdx, aSessionGetacti; "Session::GetActivityId failed: 0x%x in "...
0x18000a11a  jmp     loc_180009F3C
0x18000a11f  mov     dword ptr [r15], 10h
0x18000a126  jmp     loc_180009F89
0x18000a12b  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000a132  mov     r8, r14; struct _WINSTATIONINFORMATIONEX *
0x18000a135  mov     edx, r12d; unsigned int
0x18000a138  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000a13d  mov     rcx, r13; void *
0x18000a140  call    ?GetWinStationInformationEx@@YAJPEAXKPEAU_WINSTATIONINFORMATIONEX@@KPEAK@Z; GetWinStationInformationEx(void *,ulong,_WINSTATIONINFORMATIONEX *,ulong,ulong *)
0x18000a145  mov     ebx, eax
0x18000a147  test    eax, eax
0x18000a149  jns     loc_180009F89
0x18000a14f  lea     rdx, aGetwinstationi_0; "GetWinStationInformationEx failed: 0x%x"...
0x18000a156  jmp     loc_180009F3C
0x18000a15b  cmp     [rbp+0B0h+arg_20], 4
0x18000a162  mov     [rsp+1B0h+var_180], 0
0x18000a16a  jnb     short loc_18000A17D
0x18000a16c  mov     ebx, 80070057h
0x18000a171  lea     rdx, aWinstationtype; "WinStationType failed: 0x%x in %s"
0x18000a178  jmp     loc_180009F3C
0x18000a17d  lea     r8, [rsp+1B0h+var_180]; unsigned int *
0x18000a182  mov     edx, r12d; unsigned int
0x18000a185  mov     rcx, r13; void *
0x18000a188  call    ?GetWinStationType@@YAJPEAXKPEAK@Z; GetWinStationType(void *,ulong,ulong *)
0x18000a18d  mov     ebx, eax
0x18000a18f  test    eax, eax
0x18000a191  jns     short loc_18000A19F
0x18000a193  lea     rdx, aGetwinstationt; "GetWinStationType failed: 0x%x in %s"
0x18000a19a  jmp     loc_180009F3C
0x18000a19f  mov     eax, [rsp+1B0h+var_180]
0x18000a1a3  jmp     loc_18000A247
0x18000a1a8  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000a1af  mov     r8, r14; struct WINSTATIONREMOTEADDRESS *
0x18000a1b2  mov     edx, r12d; unsigned int
0x18000a1b5  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000a1ba  mov     rcx, r13; void *
0x18000a1bd  call    ?GetWinStationAddress@@YAJPEAXKPEAUWINSTATIONREMOTEADDRESS@@KPEAK@Z; GetWinStationAddress(void *,ulong,WINSTATIONREMOTEADDRESS *,ulong,ulong *)
0x18000a1c2  mov     ebx, eax
0x18000a1c4  test    eax, eax
0x18000a1c6  jns     loc_180009F89
0x18000a1cc  lea     rdx, aGetwinstationa; "GetWinStationAddress failed: 0x%x in %s"
0x18000a1d3  jmp     loc_180009F3C
0x18000a1d8  cmp     [rbp+0B0h+arg_20], 4
0x18000a1df  jnb     short loc_18000A1F7
0x18000a1e1  mov     ecx, 0C0000023h; Status
0x18000a1e6  call    cs:__imp_RtlNtStatusToDosError
0x18000a1ed  nop     dword ptr [rax+rax+00h]
0x18000a1f2  jmp     loc_180009F54
0x18000a1f7  lea     rcx, [rsp+1B0h+var_178]; unsigned __int16 *
0x18000a1fc  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a201  mov     r8, rax; void *
0x18000a204  lea     rcx, [rsp+1B0h+var_160]; this
0x18000a209  mov     edx, r12d; unsigned int
0x18000a20c  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x18000a211  mov     ebx, eax
0x18000a213  test    eax, eax
0x18000a215  jns     short loc_18000A223
0x18000a217  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x18000a21e  jmp     loc_180009F3C
0x18000a223  lea     rcx, [rsp+1B0h+var_160]; this
0x18000a228  call    ?IsDesktopLocked@CSmartSession@@QEAAJXZ; CSmartSession::IsDesktopLocked(void)
0x18000a22d  mov     ebx, eax
0x18000a22f  test    eax, eax
0x18000a231  jns     short loc_18000A23F
0x18000a233  lea     rdx, aIsdesktoplocke; "IsDesktopLocked failed: 0x%x in %s"
0x18000a23a  jmp     loc_180009F3C
0x18000a23f  xor     eax, eax
0x18000a241  cmp     ebx, 1
0x18000a244  setnz   al
0x18000a247  mov     [r14], eax
0x18000a24a  mov     dword ptr [r15], 4
0x18000a251  jmp     loc_180009F89
0x18000a256  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18000a25d  mov     r8, r14; unsigned __int8 *
0x18000a260  mov     edx, r12d; unsigned int
0x18000a263  mov     [rsp+1B0h+var_190], r15; unsigned int *
0x18000a268  mov     rcx, r13; void *
0x18000a26b  call    ?GetWinStationVirtualData@@YAJPEAXKPEAEKPEAK@Z; GetWinStationVirtualData(void *,ulong,uchar *,ulong,ulong *)
0x18000a270  mov     ebx, eax
0x18000a272  test    eax, eax
0x18000a274  jns     loc_180009F89
0x18000a27a  lea     rdx, aGetwinstationv; "GetWinStationVirtualData failed: 0x%x i"...
0x18000a281  jmp     loc_180009F3C
```
