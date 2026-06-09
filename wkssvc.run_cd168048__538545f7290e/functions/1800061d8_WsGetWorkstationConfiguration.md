# WsGetWorkstationConfiguration

- ea: `0x1800061d8`
- end: `0x1800067dd`
- name: `WsGetWorkstationConfiguration`
- size: `1541`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006e0c`

## callees

- `0x180005df0`
- `0x180006068`
- `0x1800061d8`
- `0x1800067e4`
- `0x18000776c`
- `0x180007958`
- `0x180007a90`
- `0x18000b190`
- `0x180011bbc`
- `0x180011ccc`
- `0x18001fbd0`
- `0x1800204f6`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006651`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006685`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006651`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006685`
- `ntdll!RtlGetNtProductType` at `0x180006560`
- `ntdll!RtlGetNtProductType` at `0x180006560`
- `ntdll!DbgPrint` at `0x180006242`
- `ntdll!DbgPrint` at `0x1800062bb`
- `ntdll!DbgPrint` at `0x1800063c1`
- `ntdll!DbgPrint` at `0x180006450`
- `ntdll!DbgPrint` at `0x180006242`
- `ntdll!DbgPrint` at `0x1800062bb`
- `ntdll!DbgPrint` at `0x1800063c1`
- `ntdll!DbgPrint` at `0x180006450`
- `ntdll!NtDeviceIoControlFile` at `0x1800065c7`
- `ntdll!NtDeviceIoControlFile` at `0x1800065c7`
- `ntdll!NtFsControlFile` at `0x1800066e9`
- `ntdll!NtFsControlFile` at `0x1800066e9`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000622b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000622b`
- `ntdll!RtlReleaseResource` at `0x1800062a6`
- `ntdll!RtlReleaseResource` at `0x1800063ac`
- `ntdll!RtlReleaseResource` at `0x180006410`
- `ntdll!RtlReleaseResource` at `0x1800067ad`
- `ntdll!RtlReleaseResource` at `0x1800062a6`
- `ntdll!RtlReleaseResource` at `0x1800063ac`
- `ntdll!RtlReleaseResource` at `0x180006410`
- `ntdll!RtlReleaseResource` at `0x1800067ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180006266`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180006266`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180006763`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180006763`
- `netutils!NetApiBufferFree` at `0x18000639d`
- `netutils!NetApiBufferFree` at `0x1800063d7`
- `netutils!NetApiBufferFree` at `0x1800064d0`
- `netutils!NetApiBufferFree` at `0x1800064f9`
- `netutils!NetApiBufferFree` at `0x18000639d`
- `netutils!NetApiBufferFree` at `0x1800063d7`
- `netutils!NetApiBufferFree` at `0x1800064d0`
- `netutils!NetApiBufferFree` at `0x1800064f9`
- `netutils!NetpwNameCanonicalize` at `0x1800062ef`
- `netutils!NetpwNameCanonicalize` at `0x180006498`
- `netutils!NetpwNameCanonicalize` at `0x1800062ef`
- `netutils!NetpwNameCanonicalize` at `0x180006498`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180006318`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180006318`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000637f`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000637f`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000638e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000638e`

## string_xrefs

- `0x1800063ba`: `WKSSVC Invalid computer name failed %lx\n`
- `0x18000623b`: `WKSSVC Acquire ConfigResource failed\n`
- `0x1800062b2`: `WKSSVC Get computer name failed %lx\n`
- `0x18000641c`: `WKSSVC Open config file failed %lx\n`

## pseudocode

```c
__int64 WsGetWorkstationConfiguration()
{
  __int16 Version; // ax
  unsigned int ComputerNameEx2; // ebx
  WCHAR *v3; // rdi
  unsigned int v4; // esi
  HANDLE v5; // rax
  void *v6; // rbx
  __int64 v7; // rdx
  HKEY v8; // r8
  DWORDLONG ullTotalPhys; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int DomainName; // eax
  void *v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  NTSTATUS v20; // eax
  int v21; // eax
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR Strings[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 RawData; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Buffer; // [rsp+70h] [rbp-90h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+78h] [rbp-88h] BYREF
  _MEMORYSTATUSEX v27; // [rsp+80h] [rbp-80h] BYREF
  int InputBuffer; // [rsp+C0h] [rbp-40h] BYREF
  int v29; // [rsp+C4h] [rbp-3Ch]
  int v30; // [rsp+D4h] [rbp-2Ch]
  int v31; // [rsp+D8h] [rbp-28h]
  _WORD v32[14]; // [rsp+DCh] [rbp-24h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-8h]
  bool v34; // [rsp+108h] [rbp+8h]
  bool v35; // [rsp+109h] [rbp+9h]

  RawData = 0;
  Strings[0] = 0;
  Buffer = 0;
  ProductType = 0;
  if ( !RtlAcquireResourceExclusive(&WsInfo, 1u) )
  {
    DbgPrint("WKSSVC Acquire ConfigResource failed\n");
    return 2140;
  }
  qword_180052010 = (__int64)&off_180050190;
  Version = GetVersion();
  dword_180051F74 = 500;
  dword_180051F78 = (unsigned __int8)Version;
  dword_180051F7C = HIBYTE(Version);
  ComputerNameEx2 = NetpGetComputerNameEx2((LPVOID *)Strings, ComputerNameNetBIOS);
  if ( ComputerNameEx2 )
  {
    RtlReleaseResource(&WsInfo);
    DbgPrint("WKSSVC Get computer name failed %lx\n", ComputerNameEx2);
    return ComputerNameEx2;
  }
  v3 = (WCHAR *)Strings[0];
  v4 = NetpwNameCanonicalize(Strings[0], qword_180051D40, 522, 4, 0);
  if ( !v4 )
  {
    NetApiBufferFree(v3);
    ullTotalPhys = -1;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)qword_180051D40 + v10) );
    dword_180051F4C = v10;
    ComputerNameEx2 = NetpOpenConfigDataEx(&RawData, v7, v8, 1);
    if ( ComputerNameEx2 )
    {
      RtlReleaseResource(&WsInfo);
      DbgPrint("WKSSVC Open config file failed %lx\n", ComputerNameEx2);
      return ComputerNameEx2;
    }
    LOBYTE(v22) = 0;
    DomainName = NetpGetDomainNameExExEx(&Buffer, v11, v12, v13, (bool *)&v22);
    ComputerNameEx2 = DomainName;
    if ( DomainName )
    {
      DbgPrint("WKSSVC Get the primary domain name failed %lx\n", DomainName);
      goto LABEL_46;
    }
    v15 = Buffer;
    if ( *(_WORD *)Buffer )
    {
      v16 = WsInAWorkgroup();
      ComputerNameEx2 = NetpwNameCanonicalize(Buffer, word_180051F50, 32, v16 != 0 ? 13 : 6, 0);
      if ( ComputerNameEx2 )
      {
        Strings[0] = (LPCWSTR)Buffer;
        WsLogEvent(0xF5Cu, 0);
        NetApiBufferFree(Buffer);
        DbgPrint("WKSSVC Invalid domain name failed %lx\n", ComputerNameEx2);
LABEL_46:
        NetpCloseConfigData(RawData);
        RtlReleaseResource(&WsInfo);
        return ComputerNameEx2;
      }
      v15 = Buffer;
    }
    else
    {
      word_180051F50[0] = 0;
    }
    NetApiBufferFree(v15);
    v17 = -1;
    do
      ++v17;
    while ( word_180051F50[v17] );
    dword_180051F70 = v17;
    WsUpdateWkstaToMatchRegistry(RawData, 1);
    v33 = xmmword_180051FC0;
    v34 = (_DWORD)xmmword_180051FD0 != 0;
    v29 = 6;
    RtlGetNtProductType(&ProductType);
    v35 = ProductType == NtProductLanManNt;
    *(_OWORD *)Strings = 0;
    if ( WsDgReceiverDeviceHandle )
    {
      LOWORD(v31) = 0;
      v18 = NtDeviceIoControlFile(
              WsDgReceiverDeviceHandle,
              0,
              0,
              0,
              (PIO_STATUS_BLOCK)Strings,
              0x130007u,
              &InputBuffer,
              0x60u,
              0,
              0);
      if ( v18 == 259 )
        v18 = (unsigned int)Strings[0];
      if ( v18 == 258 )
      {
        ComputerNameEx2 = 1460;
LABEL_35:
        Strings[0] = L"datagram receiver";
        WsLogEvent(0xC29u, ComputerNameEx2);
        DbgPrint("WKSSVC Start Datagram recevier failed %lx\n", ComputerNameEx2);
        goto LABEL_46;
      }
      v19 = WsMapStatus(v18);
      ComputerNameEx2 = v19;
      if ( v19 && v19 != 1056 && v19 != 50 )
        goto LABEL_35;
    }
    InputBuffer = 0;
    v29 = 6;
    _o_wcscpy_s(v32, 277, qword_180051D40);
    v30 = 2 * dword_180051F4C;
    v31 = 2 * dword_180051F70;
    _o_wcscpy_s(&v32[dword_180051F4C], (unsigned int)(277 - dword_180051F4C), word_180051F50);
    *(_OWORD *)Strings = 0;
    v20 = NtFsControlFile(
            WsRedirDeviceHandle,
            0,
            0,
            0,
            (PIO_STATUS_BLOCK)Strings,
            0x140191u,
            &InputBuffer,
            v31 + 36 + v30,
            &xmmword_180051F80,
            0x8Cu);
    if ( v20 >= 0 )
      v20 = (NTSTATUS)Strings[0];
    v21 = WsMapStatus((unsigned int)v20);
    ComputerNameEx2 = v21;
    if ( !v21 || v21 == 1056 )
    {
      if ( (_DWORD)xmmword_180051FC0 == -1 )
      {
        memset_0(&v27, 0, sizeof(v27));
        v27.dwLength = 64;
        GlobalMemoryStatusEx(&v27);
        if ( v27.ullTotalPhys != -1 )
          ullTotalPhys = v27.ullTotalPhys;
        LODWORD(xmmword_180051FC0) = ullTotalPhys / 0x1F4000;
      }
      WsCSCReportStartRedir();
      ComputerNameEx2 = 0;
    }
    else
    {
      Strings[0] = L"redirector";
      WsLogEvent(0xC29u, v21);
      DbgPrint("WKSSVC Start redirector failed %lx\n", ComputerNameEx2);
    }
    goto LABEL_46;
  }
  Strings[0] = v3;
  LODWORD(RawData) = 0;
  v5 = RegisterEventSourceW(0, L"Workstation");
  v6 = v5;
  if ( v5 )
  {
    if ( (_DWORD)RawData )
      ReportEventW(v5, 1u, 0, 0xF1Eu, 0, 1u, 4u, Strings, &RawData);
    else
      ReportEventW(v5, 1u, 0, 0xF1Eu, 0, 1u, 0, Strings, 0);
    DeregisterEventSource(v6);
  }
  NetApiBufferFree(v3);
  RtlReleaseResource(&WsInfo);
  DbgPrint("WKSSVC Invalid computer name failed %lx\n", v4);
  return v4;
}

```

## disassembly

```asm
0x1800061d8  push    rbp
0x1800061da  push    rbx
0x1800061db  push    rsi
0x1800061dc  push    rdi
0x1800061dd  push    r12
0x1800061df  push    r14
0x1800061e1  push    r15
0x1800061e3  lea     rbp, [rsp-220h]
0x1800061eb  sub     rsp, 320h
0x1800061f2  mov     rax, cs:__security_cookie
0x1800061f9  xor     rax, rsp
0x1800061fc  mov     [rbp+250h+var_40], rax
0x180006203  xor     r14d, r14d
0x180006206  lea     r12, WsInfo
0x18000620d  mov     rcx, r12; Resource
0x180006210  mov     [rsp+350h+RawData], r14
0x180006215  mov     [rsp+350h+Strings], r14
0x18000621a  mov     [rsp+350h+Buffer], r14
0x18000621f  lea     r15d, [r14+1]
0x180006223  mov     [rsp+350h+ProductType], r14d
0x180006228  mov     dl, r15b; Wait
0x18000622b  call    cs:__imp_RtlAcquireResourceExclusive
0x180006232  nop     dword ptr [rax+rax+00h]
0x180006237  test    al, al
0x180006239  jnz     short loc_180006258
0x18000623b  lea     rcx, aWkssvcAcquireC; "WKSSVC Acquire ConfigResource failed\n"
0x180006242  call    cs:__imp_DbgPrint
0x180006249  nop     dword ptr [rax+rax+00h]
0x18000624e  mov     eax, 85Ch
0x180006253  jmp     loc_1800067BB
0x180006258  lea     rax, off_180050190; "CharWait"
0x18000625f  mov     cs:qword_180052010, rax
0x180006266  call    cs:__imp_GetVersion
0x18000626d  nop     dword ptr [rax+rax+00h]
0x180006272  lea     rcx, [rsp+350h+Strings]
0x180006277  mov     cs:dword_180051F74, 1F4h
0x180006281  movzx   edx, al
0x180006284  shr     eax, 8
0x180006287  movzx   eax, al
0x18000628a  mov     cs:dword_180051F78, edx
0x180006290  xor     edx, edx
0x180006292  mov     cs:dword_180051F7C, eax
0x180006298  call    NetpGetComputerNameEx2
0x18000629d  mov     ebx, eax
0x18000629f  test    eax, eax
0x1800062a1  jz      short loc_1800062CC
0x1800062a3  mov     rcx, r12; Resource
0x1800062a6  call    cs:__imp_RtlReleaseResource
0x1800062ad  nop     dword ptr [rax+rax+00h]
0x1800062b2  lea     rcx, aWkssvcGetCompu; "WKSSVC Get computer name failed %lx\n"
0x1800062b9  mov     edx, ebx
0x1800062bb  call    cs:__imp_DbgPrint
0x1800062c2  nop     dword ptr [rax+rax+00h]
0x1800062c7  jmp     loc_1800067B9
0x1800062cc  mov     rdi, [rsp+350h+Strings]
0x1800062d1  lea     rbx, qword_180051D40
0x1800062d8  mov     rdx, rbx
0x1800062db  mov     dword ptr [rsp+350h+lpUserSid], r14d
0x1800062e0  mov     rcx, rdi
0x1800062e3  mov     r9d, 4
0x1800062e9  mov     r8d, 20Ah
0x1800062ef  call    cs:__imp_NetpwNameCanonicalize
0x1800062f6  nop     dword ptr [rax+rax+00h]
0x1800062fb  mov     esi, eax
0x1800062fd  test    eax, eax
0x1800062ff  jz      loc_1800063D4
0x180006305  lea     rdx, SourceName; "Workstation"
0x18000630c  mov     [rsp+350h+Strings], rdi
0x180006311  xor     ecx, ecx; lpUNCServerName
0x180006313  mov     dword ptr [rsp+350h+RawData], r14d
0x180006318  call    cs:__imp_RegisterEventSourceW
0x18000631f  nop     dword ptr [rax+rax+00h]
0x180006324  mov     rbx, rax
0x180006327  test    rax, rax
0x18000632a  jz      short loc_18000639A
0x18000632c  xor     r8d, r8d; wCategory
0x18000632f  mov     edx, r15d; wType
0x180006332  mov     r9d, 0F1Eh; dwEventID
0x180006338  mov     rcx, rax; hEventLog
0x18000633b  cmp     dword ptr [rsp+350h+RawData], r14d
0x180006340  jnz     short loc_180006358
0x180006342  mov     [rsp+350h+lpRawData], r14
0x180006347  lea     rax, [rsp+350h+Strings]
0x18000634c  mov     [rsp+350h+lpStrings], rax
0x180006351  mov     [rsp+350h+dwDataSize], r14d
0x180006356  jmp     short loc_180006374
0x180006358  lea     rax, [rsp+350h+RawData]
0x18000635d  mov     [rsp+350h+lpRawData], rax; lpRawData
0x180006362  lea     rax, [rsp+350h+Strings]
0x180006367  mov     [rsp+350h+lpStrings], rax; lpStrings
0x18000636c  mov     [rsp+350h+dwDataSize], 4; dwDataSize
0x180006374  mov     [rsp+350h+wNumStrings], r15w; wNumStrings
0x18000637a  mov     [rsp+350h+lpUserSid], r14; lpUserSid
0x18000637f  call    cs:__imp_ReportEventW
0x180006386  nop     dword ptr [rax+rax+00h]
0x18000638b  mov     rcx, rbx; hEventLog
0x18000638e  call    cs:__imp_DeregisterEventSource
0x180006395  nop     dword ptr [rax+rax+00h]
0x18000639a  mov     rcx, rdi; Buffer
0x18000639d  call    cs:__imp_NetApiBufferFree
0x1800063a4  nop     dword ptr [rax+rax+00h]
0x1800063a9  mov     rcx, r12; Resource
0x1800063ac  call    cs:__imp_RtlReleaseResource
0x1800063b3  nop     dword ptr [rax+rax+00h]
0x1800063b8  mov     edx, esi
0x1800063ba  lea     rcx, aWkssvcInvalidC; "WKSSVC Invalid computer name failed %lx"...
0x1800063c1  call    cs:__imp_DbgPrint
0x1800063c8  nop     dword ptr [rax+rax+00h]
0x1800063cd  mov     eax, esi
0x1800063cf  jmp     loc_1800067BB
0x1800063d4  mov     rcx, rdi; Buffer
0x1800063d7  call    cs:__imp_NetApiBufferFree
0x1800063de  nop     dword ptr [rax+rax+00h]
0x1800063e3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800063e7  mov     rax, rdi
0x1800063ea  inc     rax
0x1800063ed  cmp     [rbx+rax*2], r14w
0x1800063f2  jnz     short loc_1800063EA
0x1800063f4  mov     r9d, r15d
0x1800063f7  mov     cs:dword_180051F4C, eax
0x1800063fd  lea     rcx, [rsp+350h+RawData]
0x180006402  call    NetpOpenConfigDataEx
0x180006407  mov     ebx, eax
0x180006409  test    eax, eax
0x18000640b  jz      short loc_180006428
0x18000640d  mov     rcx, r12; Resource
0x180006410  call    cs:__imp_RtlReleaseResource
0x180006417  nop     dword ptr [rax+rax+00h]
0x18000641c  lea     rcx, aWkssvcOpenConf; "WKSSVC Open config file failed %lx\n"
0x180006423  jmp     loc_1800062B9
0x180006428  lea     rax, [rsp+350h+var_300]
0x18000642d  mov     byte ptr [rsp+350h+var_300], r14b
0x180006432  lea     rcx, [rsp+350h+Buffer]; Buffer
0x180006437  mov     [rsp+350h+lpUserSid], rax; __int64
0x18000643c  call    NetpGetDomainNameExExEx
0x180006441  mov     ebx, eax
0x180006443  test    eax, eax
0x180006445  jz      short loc_180006461
0x180006447  mov     edx, eax
0x180006449  lea     rcx, aWkssvcGetThePr; "WKSSVC Get the primary domain name fail"...
0x180006450  call    cs:__imp_DbgPrint
0x180006457  nop     dword ptr [rax+rax+00h]
0x18000645c  jmp     loc_1800067A0
0x180006461  mov     rcx, [rsp+350h+Buffer]; Buffer
0x180006466  lea     rsi, word_180051F50
0x18000646d  cmp     [rcx], r14w
0x180006471  jz      short loc_1800064F1
0x180006473  call    WsInAWorkgroup
0x180006478  mov     rcx, [rsp+350h+Buffer]
0x18000647d  neg     eax
0x18000647f  mov     r8d, 20h ; ' '
0x180006485  mov     dword ptr [rsp+350h+lpUserSid], r14d
0x18000648a  sbb     r9d, r9d
0x18000648d  mov     rdx, rsi
0x180006490  and     r9d, 7
0x180006494  add     r9d, 6
0x180006498  call    cs:__imp_NetpwNameCanonicalize
0x18000649f  nop     dword ptr [rax+rax+00h]
0x1800064a4  mov     ebx, eax
0x1800064a6  test    eax, eax
0x1800064a8  jz      short loc_1800064EA
0x1800064aa  mov     rax, [rsp+350h+Buffer]
0x1800064af  lea     r9, [rsp+350h+Strings]
0x1800064b4  mov     edx, r15d
0x1800064b7  mov     [rsp+350h+Strings], rax
0x1800064bc  mov     ecx, 0F5Ch; dwEventID
0x1800064c1  mov     dword ptr [rsp+350h+lpUserSid], r14d; RawData
0x1800064c6  call    WsLogEvent
0x1800064cb  mov     rcx, [rsp+350h+Buffer]; Buffer
0x1800064d0  call    cs:__imp_NetApiBufferFree
0x1800064d7  nop     dword ptr [rax+rax+00h]
0x1800064dc  mov     edx, ebx
0x1800064de  lea     rcx, aWkssvcInvalidD; "WKSSVC Invalid domain name failed %lx\n"
0x1800064e5  jmp     loc_180006450
0x1800064ea  mov     rcx, [rsp+350h+Buffer]
0x1800064ef  jmp     short loc_1800064F9
0x1800064f1  mov     cs:word_180051F50, r14w
0x1800064f9  call    cs:__imp_NetApiBufferFree
0x180006500  nop     dword ptr [rax+rax+00h]
0x180006505  mov     rax, rdi
0x180006508  inc     rax
0x18000650b  cmp     [rsi+rax*2], r14w
0x180006510  jnz     short loc_180006508
0x180006512  mov     rcx, [rsp+350h+RawData]
0x180006517  mov     edx, r15d
0x18000651a  mov     cs:dword_180051F70, eax
0x180006520  call    WsUpdateWkstaToMatchRegistry
0x180006525  mov     eax, dword ptr cs:xmmword_180051FC0
0x18000652b  lea     rcx, [rsp+350h+ProductType]; ProductType
0x180006530  cmp     dword ptr cs:xmmword_180051FD0, r14d
0x180006537  mov     dword ptr [rbp+250h+var_258], eax
0x18000653a  mov     eax, dword ptr cs:xmmword_180051FC0+4
0x180006540  setnz   [rbp+250h+var_248]
0x180006544  mov     dword ptr [rbp+250h+var_258+4], eax
0x180006547  mov     eax, dword ptr cs:xmmword_180051FC0+8
0x18000654d  mov     dword ptr [rbp+250h+var_258+8], eax
0x180006550  mov     eax, dword ptr cs:xmmword_180051FC0+0Ch
0x180006556  mov     dword ptr [rbp+250h+var_258+0Ch], eax
0x180006559  mov     [rbp+250h+var_28C], 6
0x180006560  call    cs:__imp_RtlGetNtProductType
0x180006567  nop     dword ptr [rax+rax+00h]
0x18000656c  cmp     [rsp+350h+ProductType], 2
0x180006571  xorps   xmm0, xmm0
0x180006574  mov     rcx, cs:WsDgReceiverDeviceHandle; FileHandle
0x18000657b  setz    [rbp+250h+var_247]
0x18000657f  movups  xmmword ptr [rsp+350h+Strings], xmm0
0x180006584  test    rcx, rcx
0x180006587  jz      loc_180006634
0x18000658d  mov     [rsp+350h+OutputBufferLength], r14d; OutputBufferLength
0x180006592  lea     rax, [rbp+250h+InputBuffer]
0x180006596  mov     [rsp+350h+lpRawData], r14; OutputBuffer
0x18000659b  xor     r9d, r9d; ApcContext
0x18000659e  mov     dword ptr [rsp+350h+lpStrings], 60h ; '`'; InputBufferLength
0x1800065a6  xor     r8d, r8d; ApcRoutine
0x1800065a9  mov     qword ptr [rsp+350h+dwDataSize], rax; InputBuffer
0x1800065ae  xor     edx, edx; Event
0x1800065b0  lea     rax, [rsp+350h+Strings]
0x1800065b5  mov     dword ptr [rsp+350h+wNumStrings], 130007h; IoControlCode
0x1800065bd  mov     [rsp+350h+lpUserSid], rax; IoStatusBlock
0x1800065c2  mov     word ptr [rbp+250h+var_278], r14w
0x1800065c7  call    cs:__imp_NtDeviceIoControlFile
0x1800065ce  nop     dword ptr [rax+rax+00h]
0x1800065d3  cmp     eax, 103h
0x1800065d8  cmovz   eax, dword ptr [rsp+350h+Strings]
0x1800065dd  cmp     eax, 102h
0x1800065e2  jnz     short loc_1800065EB
0x1800065e4  mov     ebx, 5B4h
0x1800065e9  jmp     short loc_180006604
0x1800065eb  mov     ecx, eax
0x1800065ed  call    WsMapStatus
0x1800065f2  mov     ebx, eax
0x1800065f4  test    eax, eax
0x1800065f6  jz      short loc_180006634
0x1800065f8  cmp     eax, 420h
0x1800065fd  jz      short loc_180006634
0x1800065ff  cmp     eax, 32h ; '2'
0x180006602  jz      short loc_180006634
0x180006604  lea     rax, aDatagramReceiv; "datagram receiver"
0x18000660b  mov     dword ptr [rsp+350h+lpUserSid], ebx; RawData
0x18000660f  mov     edx, r15d
0x180006612  mov     [rsp+350h+Strings], rax
0x180006617  lea     r9, [rsp+350h+Strings]
0x18000661c  mov     ecx, 0C29h; dwEventID
0x180006621  call    WsLogEvent
0x180006626  mov     edx, ebx
0x180006628  lea     rcx, aWkssvcStartDat; "WKSSVC Start Datagram recevier failed %"...
0x18000662f  jmp     loc_180006450
0x180006634  mov     ebx, 115h
0x180006639  mov     [rbp+250h+InputBuffer], r14d
0x18000663d  mov     edx, ebx
0x18000663f  mov     [rbp+250h+var_28C], 6
0x180006646  lea     r8, qword_180051D40
0x18000664d  lea     rcx, [rbp+250h+var_274]
0x180006651  call    cs:__imp__o_wcscpy_s
0x180006658  nop     dword ptr [rax+rax+00h]
0x18000665d  mov     ecx, cs:dword_180051F4C
0x180006663  mov     r8, rsi
0x180006666  sub     ebx, ecx
0x180006668  mov     edx, ebx
0x18000666a  lea     eax, [rcx+rcx]
0x18000666d  mov     [rbp+250h+var_27C], eax
0x180006670  mov     eax, cs:dword_180051F70
0x180006676  add     eax, eax
0x180006678  mov     [rbp+250h+var_278], eax
0x18000667b  mov     eax, ecx
0x18000667d  lea     rcx, [rbp+250h+var_274]
0x180006681  lea     rcx, [rcx+rax*2]
0x180006685  call    cs:__imp__o_wcscpy_s
0x18000668c  nop     dword ptr [rax+rax+00h]
0x180006691  mov     eax, [rbp+250h+var_278]
0x180006694  xorps   xmm0, xmm0
0x180006697  mov     r8d, [rbp+250h+var_27C]
0x18000669b  add     eax, 24h ; '$'
0x18000669e  mov     rcx, cs:WsRedirDeviceHandle; FileHandle
0x1800066a5  add     r8d, eax
0x1800066a8  mov     [rsp+350h+OutputBufferLength], 8Ch; OutputBufferLength
0x1800066b0  lea     rax, xmmword_180051F80
0x1800066b7  mov     [rsp+350h+lpRawData], rax; OutputBuffer
0x1800066bc  xor     r9d, r9d; ApcContext
0x1800066bf  mov     dword ptr [rsp+350h+lpStrings], r8d; InputBufferLength
0x1800066c4  lea     rax, [rbp+250h+InputBuffer]
0x1800066c8  mov     qword ptr [rsp+350h+dwDataSize], rax; InputBuffer
0x1800066cd  xor     r8d, r8d; ApcRoutine
0x1800066d0  lea     rax, [rsp+350h+Strings]
0x1800066d5  mov     dword ptr [rsp+350h+wNumStrings], 140191h; FsControlCode
0x1800066dd  xor     edx, edx; Event
0x1800066df  mov     [rsp+350h+lpUserSid], rax; IoStatusBlock
0x1800066e4  movups  xmmword ptr [rsp+350h+Strings], xmm0
0x1800066e9  call    cs:__imp_NtFsControlFile
0x1800066f0  nop     dword ptr [rax+rax+00h]
0x1800066f5  test    eax, eax
0x1800066f7  cmovns  eax, dword ptr [rsp+350h+Strings]
0x1800066fc  mov     ecx, eax
0x1800066fe  call    WsMapStatus
0x180006703  mov     ebx, eax
0x180006705  test    eax, eax
0x180006707  jz      short loc_180006740
0x180006709  cmp     eax, 420h
0x18000670e  jz      short loc_180006740
0x180006710  lea     rax, aRedirector; "redirector"
  ... truncated ...
```
