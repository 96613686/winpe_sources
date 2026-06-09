# ServiceInit(ulong,ushort * *)

- ea: `0x180001fec`
- end: `0x1800022ee`
- name: `?ServiceInit@@YAXKPEAPEAG@Z`
- size: `770`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x180001008`
- `0x18000123c`
- `0x180001bb8`
- `0x180001f3c`
- `0x180001fec`
- `0x180002460`
- `0x180002866`
- `0x180002890`
- `0x180003010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000219a`
- `msvcrt!_wtoi` at `0x18000219a`
- `msvcrt!_wcsicmp` at `0x1800021d1`
- `msvcrt!_wcsicmp` at `0x1800021f4`
- `msvcrt!_wcsicmp` at `0x1800021d1`
- `msvcrt!_wcsicmp` at `0x1800021f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002189`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002189`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000203b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000203b`
- `ntdll!RtlGetVersion` at `0x1800021ab`
- `ntdll!RtlGetVersion` at `0x1800021ab`
- `mi!MI_Application_InitializeV1` at `0x180002143`
- `mi!MI_Application_InitializeV1` at `0x180002143`

## string_xrefs

- `0x1800020cd`: `ServiceInit`
- `0x1800022a7`: `ServiceInit`

## pseudocode

```c
void __fastcall ServiceInit(__int64 a1, unsigned __int16 **a2)
{
  unsigned int v2; // edx
  int Provider; // ebx
  DWORD v4; // esi
  NTSTATUS Version; // r14d
  struct _WSP_HOSTED_PROVIDER near **v6; // rdi
  unsigned int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  const char *v12; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[32]; // [rsp+170h] [rbp+70h] BYREF
  const char *v15; // [rsp+190h] [rbp+90h]
  __int64 v16; // [rsp+198h] [rbp+98h]
  const char **v17; // [rsp+1A0h] [rbp+A0h]
  __int64 v18; // [rsp+1A8h] [rbp+A8h]
  int *v19; // [rsp+1B0h] [rbp+B0h]
  __int64 v20; // [rsp+1B8h] [rbp+B8h]
  wchar_t String[32]; // [rsp+1C0h] [rbp+C0h] BYREF

  pcbData = 64;
  memset_0(&VersionInformation, 0, 0x11Cu);
  g_ServiceStopEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_ServiceStopEvent )
  {
    Provider = 27;
LABEL_3:
    ReportServiceStatus(1u, v2, 0);
    if ( (unsigned int)dword_180006048 > 5
      && (qword_180006058 & 0x400000000000LL) != 0
      && (qword_180006060 & 0x400000000000LL) == qword_180006060 )
    {
      v10 = Provider;
      v19 = &v10;
      LODWORD(v12) = 205;
      v17 = &v12;
      v20 = 4;
      v15 = "ServiceInit";
      v18 = 4;
      v16 = 12;
      tlgWriteTransfer_EventWriteTransfer(&dword_180006048, byte_180004969, 0, 0, 5, v14);
    }
    return;
  }
  Provider = MI_Application_InitializeV1(0, 0, 0, &g_Application);
  if ( Provider )
    goto LABEL_3;
  v4 = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
          L"CurrentBuild",
          2u,
          0,
          String,
          &pcbData) )
    v4 = _wtoi(String);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  v6 = &g_HostedProviders;
  do
  {
    if ( Version < 0 || VersionInformation.dwBuildNumber <= v4 || !_wcsicmp((const wchar_t *)v6[1], L"MISpace") )
    {
      Provider = LoadProvider((struct _WSP_HOSTED_PROVIDER *)v6);
      if ( Provider )
      {
        if ( !_wcsicmp((const wchar_t *)v6[1], L"MISpace") )
        {
          ServiceStopCallback(0, 0);
          goto LABEL_3;
        }
      }
    }
    v6 += 8;
  }
  while ( v6 != (struct _WSP_HOSTED_PROVIDER near **)&_native_dllmain_reason );
  ReportServiceStatus(4u, v7, 0);
  (*((void (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned int), _QWORD, int))g_SvchostGlobals
   + 24))(
    &g_WaitHandle,
    L"SMPHost",
    g_ServiceStopEvent,
    ServiceStopCallback,
    0,
    24);
  if ( (unsigned int)dword_180006048 > 5
    && (qword_180006058 & 0x400000000000LL) != 0
    && (qword_180006060 & 0x400000000000LL) == qword_180006060 )
  {
    v10 = 211;
    v12 = "ServiceInit";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      0,
      (unsigned int)qword_1800049A0,
      v8,
      v9,
      (__int64)&v12,
      (__int64)&v10);
  }
}

```

## disassembly

```asm
0x180001fec  push    rbp
0x180001fee  push    rbx
0x180001fef  push    rsi
0x180001ff0  push    rdi
0x180001ff1  push    r14
0x180001ff3  lea     rbp, [rsp-110h]
0x180001ffb  sub     rsp, 210h
0x180002002  mov     rax, cs:__security_cookie
0x180002009  xor     rax, rsp
0x18000200c  mov     [rbp+130h+var_30], rax
0x180002013  mov     edi, 11Ch
0x180002018  mov     [rsp+230h+var_1EC], 40h ; '@'
0x180002020  mov     r8d, edi; Size
0x180002023  lea     rcx, [rsp+230h+VersionInformation]; void *
0x180002028  xor     edx, edx; Val
0x18000202a  call    memset_0
0x18000202f  xor     r9d, r9d; lpName
0x180002032  xor     r8d, r8d; bInitialState
0x180002035  xor     ecx, ecx; lpEventAttributes
0x180002037  lea     edx, [r9+1]; bManualReset
0x18000203b  call    cs:__imp_CreateEventW
0x180002041  mov     cs:?g_ServiceStopEvent@@3PEAXEA, rax; void * g_ServiceStopEvent
0x180002048  test    rax, rax
0x18000204b  jnz     loc_180002135
0x180002051  lea     ebx, [rax+1Bh]
0x180002054  xor     r8d, r8d; unsigned int
0x180002057  lea     ecx, [r8+1]; unsigned int
0x18000205b  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180002060  mov     eax, cs:dword_180006048
0x180002066  cmp     eax, 5
0x180002069  jbe     loc_180002118
0x18000206f  mov     rdx, cs:qword_180006060
0x180002076  mov     rcx, 400000000000h
0x180002080  mov     rax, cs:qword_180006058
0x180002087  test    rcx, rax
0x18000208a  jz      loc_180002118
0x180002090  mov     rax, rdx
0x180002093  and     rax, rcx
0x180002096  cmp     rax, rdx
0x180002099  jnz     short loc_180002118
0x18000209b  lea     rax, [rsp+230h+var_1F0]
0x1800020a0  mov     [rsp+230h+var_1F0], ebx
0x1800020a4  mov     [rbp+130h+var_80], rax
0x1800020ab  lea     rdx, byte_180004969
0x1800020b2  lea     rax, [rsp+230h+var_1E8]
0x1800020b7  mov     dword ptr [rsp+230h+var_1E8], 0CDh
0x1800020bf  mov     [rbp+130h+var_90], rax
0x1800020c6  lea     rcx, dword_180006048
0x1800020cd  lea     rax, aServiceinit; "ServiceInit"
0x1800020d4  mov     [rbp+130h+var_78], 4
0x1800020df  mov     [rbp+130h+var_A0], rax
0x1800020e6  xor     r9d, r9d
0x1800020e9  lea     rax, [rbp+130h+var_C0]
0x1800020ed  mov     [rbp+130h+var_88], 4
0x1800020f8  mov     [rsp+230h+pvData], rax
0x1800020fd  xor     r8d, r8d
0x180002100  mov     dword ptr [rsp+230h+pdwType], 5
0x180002108  mov     [rbp+130h+var_98], 0Ch
0x180002113  call    _tlgWriteTransfer_EventWriteTransfer
0x180002118  mov     rcx, [rbp+130h+var_30]
0x18000211f  xor     rcx, rsp; StackCookie
0x180002122  call    __security_check_cookie
0x180002127  add     rsp, 210h
0x18000212e  pop     r14
0x180002130  pop     rdi
0x180002131  pop     rsi
0x180002132  pop     rbx
0x180002133  pop     rbp
0x180002134  retn
0x180002135  lea     r9, ?g_Application@@3U_MI_Application@@A; application
0x18000213c  xor     r8d, r8d; extendedError
0x18000213f  xor     edx, edx; applicationID
0x180002141  xor     ecx, ecx; flags
0x180002143  call    cs:__imp_MI_Application_InitializeV1
0x180002149  mov     ebx, eax
0x18000214b  test    eax, eax
0x18000214d  jnz     loc_180002054
0x180002153  lea     rax, [rsp+230h+var_1EC]
0x180002158  xor     esi, esi
0x18000215a  mov     [rsp+230h+pcbData], rax; pcbData
0x18000215f  lea     r9d, [rbx+2]; dwFlags
0x180002163  lea     rax, [rbp+130h+String]
0x18000216a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002171  mov     [rsp+230h+pvData], rax; pvData
0x180002176  lea     r8, Value; "CurrentBuild"
0x18000217d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180002184  mov     [rsp+230h+pdwType], rsi; pdwType
0x180002189  call    cs:__imp_RegGetValueW
0x18000218f  test    eax, eax
0x180002191  jnz     short loc_1800021A2
0x180002193  lea     rcx, [rbp+130h+String]; String
0x18000219a  call    cs:__imp__wtoi
0x1800021a0  mov     esi, eax
0x1800021a2  lea     rcx, [rsp+230h+VersionInformation]; lpVersionInformation
0x1800021a7  mov     [rsp+230h+VersionInformation.dwOSVersionInfoSize], edi
0x1800021ab  call    cs:__imp_RtlGetVersion
0x1800021b1  mov     r14d, eax
0x1800021b4  lea     rdi, ?g_HostedProviders@@3PAU_WSP_HOSTED_PROVIDER@@A; _WSP_HOSTED_PROVIDER near * g_HostedProviders
0x1800021bb  test    r14d, r14d
0x1800021be  js      short loc_1800021DB
0x1800021c0  cmp     [rsp+230h+VersionInformation.dwBuildNumber], esi
0x1800021c4  jbe     short loc_1800021DB
0x1800021c6  mov     rcx, [rdi+8]; String1
0x1800021ca  lea     rdx, aMispace; "MISpace"
0x1800021d1  call    cs:__imp__wcsicmp
0x1800021d7  test    eax, eax
0x1800021d9  jnz     short loc_180002204
0x1800021db  mov     rcx, rdi; struct _WSP_HOSTED_PROVIDER *
0x1800021de  call    ?LoadProvider@@YA?AW4_MI_Result@@PEAU_WSP_HOSTED_PROVIDER@@@Z; LoadProvider(_WSP_HOSTED_PROVIDER *)
0x1800021e3  mov     ebx, eax
0x1800021e5  test    eax, eax
0x1800021e7  jz      short loc_180002204
0x1800021e9  mov     rcx, [rdi+8]; String1
0x1800021ed  lea     rdx, aMispace; "MISpace"
0x1800021f4  call    cs:__imp__wcsicmp
0x1800021fa  test    eax, eax
0x1800021fc  jz      loc_1800022E0
0x180002202  xor     ebx, ebx
0x180002204  add     rdi, 40h ; '@'
0x180002208  lea     rax, __native_dllmain_reason
0x18000220f  cmp     rdi, rax
0x180002212  jnz     short loc_1800021BB
0x180002214  xor     r8d, r8d; unsigned int
0x180002217  lea     ecx, [r8+4]; unsigned int
0x18000221b  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180002220  mov     rax, cs:?g_SvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_SvchostGlobals
0x180002227  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x18000222e  mov     r8, cs:?g_ServiceStopEvent@@3PEAXEA; void * g_ServiceStopEvent
0x180002235  lea     rdx, ServiceName; "SMPHost"
0x18000223c  mov     dword ptr [rsp+230h+pvData], 18h
0x180002244  lea     rcx, ?g_WaitHandle@@3PEAXEA; void * g_WaitHandle
0x18000224b  mov     [rsp+230h+pdwType], 0
0x180002254  mov     rax, [rax+0C0h]
0x18000225b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002260  test    ebx, ebx
0x180002262  jnz     loc_180002054
0x180002268  mov     eax, cs:dword_180006048
0x18000226e  cmp     eax, 5
0x180002271  jbe     loc_180002118
0x180002277  mov     rdx, cs:qword_180006060
0x18000227e  mov     rcx, 400000000000h
0x180002288  mov     rax, cs:qword_180006058
0x18000228f  test    rcx, rax
0x180002292  jz      loc_180002118
0x180002298  mov     rax, rdx
0x18000229b  and     rax, rcx
0x18000229e  cmp     rax, rdx
0x1800022a1  jnz     loc_180002118
0x1800022a7  lea     rax, aServiceinit; "ServiceInit"
0x1800022ae  mov     [rsp+230h+var_1F0], 0D3h
0x1800022b6  mov     [rsp+230h+var_1E8], rax
0x1800022bb  lea     rdx, qword_1800049A0
0x1800022c2  lea     rax, [rsp+230h+var_1F0]
0x1800022c7  mov     [rsp+230h+pvData], rax
0x1800022cc  lea     rax, [rsp+230h+var_1E8]
0x1800022d1  mov     [rsp+230h+pdwType], rax
0x1800022d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800022db  jmp     loc_180002118
0x1800022e0  xor     edx, edx; unsigned __int8
0x1800022e2  xor     ecx, ecx; void *
0x1800022e4  call    ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x1800022e9  jmp     loc_180002054
```
