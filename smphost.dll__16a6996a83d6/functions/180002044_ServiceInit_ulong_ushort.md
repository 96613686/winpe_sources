# ServiceInit(ulong,ushort * *)

- ea: `0x180002044`
- end: `0x180002371`
- name: `?ServiceInit@@YAXKPEAPEAG@Z`
- size: `813`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002380`

## callees

- `0x180001008`
- `0x180001240`
- `0x180001bc8`
- `0x180001f80`
- `0x180002044`
- `0x1800024f0`
- `0x180002926`
- `0x180002950`
- `0x180003010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180002205`
- `msvcrt!_wtoi` at `0x180002205`
- `msvcrt!_wcsicmp` at `0x180002248`
- `msvcrt!_wcsicmp` at `0x180002271`
- `msvcrt!_wcsicmp` at `0x180002248`
- `msvcrt!_wcsicmp` at `0x180002271`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800021ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800021ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002093`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002093`
- `ntdll!RtlGetVersion` at `0x18000221c`
- `ntdll!RtlGetVersion` at `0x18000221c`
- `mi!MI_Application_InitializeV1` at `0x1800021a2`
- `mi!MI_Application_InitializeV1` at `0x1800021a2`

## string_xrefs

- `0x18000212b`: `ServiceInit`
- `0x18000232a`: `ServiceInit`

## pseudocode

```c
void __fastcall ServiceInit(__int64 a1, unsigned __int16 **a2)
{
  unsigned int v2; // edx
  enum _MI_Result Provider; // ebx
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
    Provider = MI_RESULT_SERVER_LIMITS_EXCEEDED;
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
  (*((void (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_SvchostGlobals
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
0x180002044  push    rbp
0x180002046  push    rbx
0x180002047  push    rsi
0x180002048  push    rdi
0x180002049  push    r14
0x18000204b  lea     rbp, [rsp-110h]
0x180002053  sub     rsp, 210h
0x18000205a  mov     rax, cs:__security_cookie
0x180002061  xor     rax, rsp
0x180002064  mov     [rbp+130h+var_30], rax
0x18000206b  mov     edi, 11Ch
0x180002070  mov     [rsp+230h+var_1EC], 40h ; '@'
0x180002078  mov     r8d, edi; Size
0x18000207b  lea     rcx, [rsp+230h+VersionInformation]; void *
0x180002080  xor     edx, edx; Val
0x180002082  call    memset_0
0x180002087  xor     r9d, r9d; lpName
0x18000208a  xor     r8d, r8d; bInitialState
0x18000208d  xor     ecx, ecx; lpEventAttributes
0x18000208f  lea     edx, [r9+1]; bManualReset
0x180002093  call    cs:__imp_CreateEventW
0x18000209a  nop     dword ptr [rax+rax+00h]
0x18000209f  mov     cs:?g_ServiceStopEvent@@3PEAXEA, rax; void * g_ServiceStopEvent
0x1800020a6  test    rax, rax
0x1800020a9  jnz     loc_180002194
0x1800020af  lea     ebx, [rax+1Bh]
0x1800020b2  xor     r8d, r8d; unsigned int
0x1800020b5  lea     ecx, [r8+1]; unsigned int
0x1800020b9  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x1800020be  mov     eax, cs:dword_180006048
0x1800020c4  cmp     eax, 5
0x1800020c7  jbe     loc_180002176
0x1800020cd  mov     rdx, cs:qword_180006060
0x1800020d4  mov     rcx, 400000000000h
0x1800020de  mov     rax, cs:qword_180006058
0x1800020e5  test    rcx, rax
0x1800020e8  jz      loc_180002176
0x1800020ee  mov     rax, rdx
0x1800020f1  and     rax, rcx
0x1800020f4  cmp     rax, rdx
0x1800020f7  jnz     short loc_180002176
0x1800020f9  lea     rax, [rsp+230h+var_1F0]
0x1800020fe  mov     [rsp+230h+var_1F0], ebx
0x180002102  mov     [rbp+130h+var_80], rax
0x180002109  lea     rdx, byte_180004969
0x180002110  lea     rax, [rsp+230h+var_1E8]
0x180002115  mov     dword ptr [rsp+230h+var_1E8], 0CDh
0x18000211d  mov     [rbp+130h+var_90], rax
0x180002124  lea     rcx, dword_180006048
0x18000212b  lea     rax, aServiceinit; "ServiceInit"
0x180002132  mov     [rbp+130h+var_78], 4
0x18000213d  mov     [rbp+130h+var_A0], rax
0x180002144  xor     r9d, r9d
0x180002147  lea     rax, [rbp+130h+var_C0]
0x18000214b  mov     [rbp+130h+var_88], 4
0x180002156  mov     [rsp+230h+pvData], rax
0x18000215b  xor     r8d, r8d
0x18000215e  mov     dword ptr [rsp+230h+pdwType], 5
0x180002166  mov     [rbp+130h+var_98], 0Ch
0x180002171  call    _tlgWriteTransfer_EventWriteTransfer
0x180002176  mov     rcx, [rbp+130h+var_30]
0x18000217d  xor     rcx, rsp; StackCookie
0x180002180  call    __security_check_cookie
0x180002185  add     rsp, 210h
0x18000218c  pop     r14
0x18000218e  pop     rdi
0x18000218f  pop     rsi
0x180002190  pop     rbx
0x180002191  pop     rbp
0x180002192  retn
0x180002194  lea     r9, ?g_Application@@3U_MI_Application@@A; application
0x18000219b  xor     r8d, r8d; extendedError
0x18000219e  xor     edx, edx; applicationID
0x1800021a0  xor     ecx, ecx; flags
0x1800021a2  call    cs:__imp_MI_Application_InitializeV1
0x1800021a9  nop     dword ptr [rax+rax+00h]
0x1800021ae  mov     ebx, eax
0x1800021b0  test    eax, eax
0x1800021b2  jnz     loc_1800020B2
0x1800021b8  lea     rax, [rsp+230h+var_1EC]
0x1800021bd  xor     esi, esi
0x1800021bf  mov     [rsp+230h+pcbData], rax; pcbData
0x1800021c4  lea     r9d, [rbx+2]; dwFlags
0x1800021c8  lea     rax, [rbp+130h+String]
0x1800021cf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800021d6  mov     [rsp+230h+pvData], rax; pvData
0x1800021db  lea     r8, Value; "CurrentBuild"
0x1800021e2  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800021e9  mov     [rsp+230h+pdwType], rsi; pdwType
0x1800021ee  call    cs:__imp_RegGetValueW
0x1800021f5  nop     dword ptr [rax+rax+00h]
0x1800021fa  test    eax, eax
0x1800021fc  jnz     short loc_180002213
0x1800021fe  lea     rcx, [rbp+130h+String]; String
0x180002205  call    cs:__imp__wtoi
0x18000220c  nop     dword ptr [rax+rax+00h]
0x180002211  mov     esi, eax
0x180002213  lea     rcx, [rsp+230h+VersionInformation]; lpVersionInformation
0x180002218  mov     [rsp+230h+VersionInformation.dwOSVersionInfoSize], edi
0x18000221c  call    cs:__imp_RtlGetVersion
0x180002223  nop     dword ptr [rax+rax+00h]
0x180002228  mov     r14d, eax
0x18000222b  lea     rdi, ?g_HostedProviders@@3PAU_WSP_HOSTED_PROVIDER@@A; _WSP_HOSTED_PROVIDER near * g_HostedProviders
0x180002232  test    r14d, r14d
0x180002235  js      short loc_180002258
0x180002237  cmp     [rsp+230h+VersionInformation.dwBuildNumber], esi
0x18000223b  jbe     short loc_180002258
0x18000223d  mov     rcx, [rdi+8]; String1
0x180002241  lea     rdx, aMispace; "MISpace"
0x180002248  call    cs:__imp__wcsicmp
0x18000224f  nop     dword ptr [rax+rax+00h]
0x180002254  test    eax, eax
0x180002256  jnz     short loc_180002287
0x180002258  mov     rcx, rdi; struct _WSP_HOSTED_PROVIDER *
0x18000225b  call    ?LoadProvider@@YA?AW4_MI_Result@@PEAU_WSP_HOSTED_PROVIDER@@@Z; LoadProvider(_WSP_HOSTED_PROVIDER *)
0x180002260  mov     ebx, eax
0x180002262  test    eax, eax
0x180002264  jz      short loc_180002287
0x180002266  mov     rcx, [rdi+8]; String1
0x18000226a  lea     rdx, aMispace; "MISpace"
0x180002271  call    cs:__imp__wcsicmp
0x180002278  nop     dword ptr [rax+rax+00h]
0x18000227d  test    eax, eax
0x18000227f  jz      loc_180002363
0x180002285  xor     ebx, ebx
0x180002287  add     rdi, 40h ; '@'
0x18000228b  lea     rax, __native_dllmain_reason
0x180002292  cmp     rdi, rax
0x180002295  jnz     short loc_180002232
0x180002297  xor     r8d, r8d; unsigned int
0x18000229a  lea     ecx, [r8+4]; unsigned int
0x18000229e  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x1800022a3  mov     rax, cs:?g_SvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_SvchostGlobals
0x1800022aa  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x1800022b1  mov     r8, cs:?g_ServiceStopEvent@@3PEAXEA; void * g_ServiceStopEvent
0x1800022b8  lea     rdx, ServiceName; "SMPHost"
0x1800022bf  mov     dword ptr [rsp+230h+pvData], 18h
0x1800022c7  lea     rcx, ?g_WaitHandle@@3PEAXEA; void * g_WaitHandle
0x1800022ce  mov     [rsp+230h+pdwType], 0
0x1800022d7  mov     rax, [rax+0C0h]
0x1800022de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e3  test    ebx, ebx
0x1800022e5  jnz     loc_1800020B2
0x1800022eb  mov     eax, cs:dword_180006048
0x1800022f1  cmp     eax, 5
0x1800022f4  jbe     loc_180002176
0x1800022fa  mov     rdx, cs:qword_180006060
0x180002301  mov     rcx, 400000000000h
0x18000230b  mov     rax, cs:qword_180006058
0x180002312  test    rcx, rax
0x180002315  jz      loc_180002176
0x18000231b  mov     rax, rdx
0x18000231e  and     rax, rcx
0x180002321  cmp     rax, rdx
0x180002324  jnz     loc_180002176
0x18000232a  lea     rax, aServiceinit; "ServiceInit"
0x180002331  mov     [rsp+230h+var_1F0], 0D3h
0x180002339  mov     [rsp+230h+var_1E8], rax
0x18000233e  lea     rdx, qword_1800049A0
0x180002345  lea     rax, [rsp+230h+var_1F0]
0x18000234a  mov     [rsp+230h+pvData], rax
0x18000234f  lea     rax, [rsp+230h+var_1E8]
0x180002354  mov     [rsp+230h+pdwType], rax
0x180002359  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000235e  jmp     loc_180002176
0x180002363  xor     edx, edx; unsigned __int8
0x180002365  xor     ecx, ecx; void *
0x180002367  call    ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x18000236c  jmp     loc_1800020B2
```
