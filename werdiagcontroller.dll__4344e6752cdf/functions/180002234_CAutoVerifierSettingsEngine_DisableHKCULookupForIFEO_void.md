# CAutoVerifierSettingsEngine::DisableHKCULookupForIFEO(void)

- ea: `0x180002234`
- end: `0x18000278a`
- name: `?DisableHKCULookupForIFEO@CAutoVerifierSettingsEngine@@AEAAJXZ`
- size: `1366`
- prototype: `__int64 __fastcall(CAutoVerifierSettingsEngine *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180002cc8`

## callees

- `0x180001400`
- `0x180001cc6`
- `0x180001cd4`
- `0x180002234`
- `0x180005a9c`
- `0x180005d24`
- `0x1800061b4`
- `0x180006360`
- `0x1800063b4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800024d9`
- `ntdll!RtlInitUnicodeString` at `0x1800024d9`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800023b4`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800023b4`
- `ntdll!ZwUpdateWnfStateData` at `0x18000238b`
- `ntdll!ZwUpdateWnfStateData` at `0x18000238b`
- `ntdll!NtClose` at `0x1800024a6`
- `ntdll!NtClose` at `0x18000272f`
- `ntdll!NtClose` at `0x180002754`
- `ntdll!NtClose` at `0x1800024a6`
- `ntdll!NtClose` at `0x18000272f`
- `ntdll!NtClose` at `0x180002754`
- `ntdll!DbgPrintEx` at `0x1800026da`
- `ntdll!DbgPrintEx` at `0x18000270a`
- `ntdll!DbgPrintEx` at `0x1800026da`
- `ntdll!DbgPrintEx` at `0x18000270a`
- `ntdll!NtWaitForSingleObject` at `0x180002499`
- `ntdll!NtWaitForSingleObject` at `0x180002499`
- `ntdll!NtOpenEvent` at `0x180002460`
- `ntdll!NtOpenEvent` at `0x180002460`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000252d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000252d`
- `ntdll!NtAlpcConnectPort` at `0x1800025c0`
- `ntdll!NtAlpcConnectPort` at `0x1800025c0`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800026ad`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800026ad`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000235c`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000235c`
- `ntdll!RtlFreeSid` at `0x1800024ee`
- `ntdll!RtlFreeSid` at `0x18000271f`
- `ntdll!RtlFreeSid` at `0x180002744`
- `ntdll!RtlFreeSid` at `0x1800024ee`
- `ntdll!RtlFreeSid` at `0x18000271f`
- `ntdll!RtlFreeSid` at `0x180002744`
- `ntdll!NtQuerySystemInformation` at `0x1800023e7`
- `ntdll!NtQuerySystemInformation` at `0x1800023e7`

## string_xrefs

- `0x1800022e1`: `\Registry\Machine\Software\Microsoft\Windows\Windows Error Reporting`
- `0x1800022fc`: `WERDIAG: Failed opening registry key. NTSTATUS: %08X\n`
- `0x180002325`: `WERDIAG: PluginsNtGetRegStringValue failed. NTSTATUS: %08X\n`
- `0x18000253c`: `WERDIAG: RtlAllocateAndInitializeSid failed. NTSTATUS: %08X\n`
- `0x1800026cc`: `WERDIAG: Service returned failure status. NTSTATUS: %08X\n`
- `0x180002412`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
__int64 __fastcall CAutoVerifierSettingsEngine::DisableHKCULookupForIFEO(CAutoVerifierSettingsEngine *this)
{
  char v1; // di
  int v2; // eax
  NTSTATUS v3; // ebx
  int RegStringValue; // eax
  BOOL v5; // ebx
  int v6; // eax
  int v7; // ecx
  NTSTATUS v8; // eax
  __int64 v9; // rsi
  char v10; // dl
  union _LARGE_INTEGER *v11; // r8
  NTSTATUS v12; // eax
  __int64 *v13; // rsi
  int v14; // eax
  HANDLE v15; // rbx
  int v16; // eax
  PSID v17; // rcx
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  void *EventHandle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  __int64 SystemInformation; // [rsp+78h] [rbp-88h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h] BYREF
  HANDLE KeyHandle; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR SourceString; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-38h]
  __int128 v31; // [rsp+D8h] [rbp-28h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE Src[1408]; // [rsp+120h] [rbp+20h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int128 v35; // [rsp+6A8h] [rbp+5A8h] BYREF
  _DWORD v36[352]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _DWORD v37[11]; // [rsp+C40h] [rbp+B40h] BYREF
  int v38; // [rsp+C6Ch] [rbp+B6Ch]

  SourceString = 0;
  Handle = 0;
  KeyHandle = 0;
  memset_0(v36, 0, 0x578u);
  memset_0(v37, 0, 0x578u);
  v27 = 0;
  DestinationString = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v23 = 0;
  SystemInformation = 0;
  v1 = 1;
  v2 = PluginsNtOpenKey(
         1u,
         L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\Windows Error Reporting",
         0,
         0,
         &KeyHandle);
  v3 = v2;
  if ( v2 >= 0 )
  {
    RegStringValue = PluginsNtGetRegStringValue(KeyHandle, L"ErrorPort", (void **)&SourceString);
    v3 = RegStringValue;
    if ( RegStringValue >= 0 )
    {
      v35 = 0;
      LODWORD(EventHandle) = 0;
      v5 = 0;
      if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0
        && (_DWORD)EventHandle )
      {
        v5 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
      }
      v35 = 0;
      v6 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v35, 0, 0);
      v7 = v5 + 1;
      if ( v6 )
        v7 = v5;
      if ( v7 )
      {
        v8 = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
        v3 = v8;
        if ( v8 >= 0 )
        {
          v9 = (int)SystemInformation;
          *(_QWORD *)&v35 = 4718662;
          *((_QWORD *)&v35 + 1) = L"\\KernelObjects\\SystemErrorPortReady";
          *(_QWORD *)&ObjectAttributes.Length = 48;
          memset(&ObjectAttributes.Attributes, 0, 24);
          EventHandle = 0;
          v26 = 0;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v35;
          v3 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
          if ( v3 < 0 )
            goto LABEL_41;
          if ( (_DWORD)v9 == -1 )
          {
            v10 = 1;
          }
          else
          {
            v10 = 0;
            v26 = -10000 * v9;
          }
          v11 = (union _LARGE_INTEGER *)&v26;
          if ( v10 )
            v11 = 0;
          v3 = NtWaitForSingleObject(EventHandle, 0, v11);
          NtClose(EventHandle);
          if ( v3 < 0 )
          {
LABEL_41:
            DbgPrintEx(0x96u, 0, "WERDIAG: WaitForWerSvc failed. NTSTATUS: %08X\n", (unsigned int)v3);
          }
          else if ( v3 == 258 )
          {
            v3 = -1073740973;
            DbgPrintEx(
              0x96u,
              0,
              "WERDIAG: WaitForWerSvc timed out, failing the call with NTSTATUS: %08X\n",
              3221226323LL);
          }
          else
          {
            RtlInitUnicodeString(&DestinationString, SourceString);
            Sid = 0;
            v12 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
            v3 = v12;
            if ( v12 >= 0 )
            {
              LODWORD(v29) = 48;
              *((_QWORD *)&v29 + 1) = 0;
              DWORD2(v30) = 0;
              *(_QWORD *)&v30 = 0;
              v31 = 0;
              if ( HIDWORD(SystemInformation) != -1 )
              {
                v1 = 0;
                v23 = -10000LL * SHIDWORD(SystemInformation);
              }
              v13 = &v23;
              if ( v1 )
                v13 = 0;
              v14 = NtAlpcConnectPort(&Handle, &DestinationString, &v29, 0, 0x20000, Sid, 0, 0, 0, 0, v13);
              v3 = v14;
              if ( v14 >= 0 )
              {
                if ( v14 == 258 )
                {
                  v3 = -1073740973;
                  DbgPrintEx(
                    0x96u,
                    0,
                    "WERDIAG: NtAlpcConnectPort timed out, failing the call with NTSTATUS %08X\n",
                    3221226323LL);
                }
                else
                {
                  v15 = Handle;
                  if ( !Handle )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs();
                    v15 = Handle;
                  }
                  memset_0(Src, 0, 0x578u);
                  memcpy_0(v36, Src, 0x578u);
                  v36[0] = 91751760;
                  v36[10] = 0x80000000;
                  v36[12] = 0;
                  memset_0(Src, 0, 0x578u);
                  memcpy_0(v37, Src, 0x578u);
                  v37[0] = 91751760;
                  v27 = 1400;
                  v16 = NtAlpcSendWaitReceivePort(v15, 0x20000, v36, 0, v37, &v27, 0, v13);
                  v3 = v16;
                  if ( v16 < 0 || v16 == 258 )
                  {
                    DbgPrintEx(
                      0x96u,
                      0,
                      "WERDIAG: NtAlpcSendWaitReceivePort failed. NTSTATUS: %08X\n",
                      (unsigned int)v16);
                  }
                  else if ( v38 >= 0 )
                  {
                    v3 = 0;
                  }
                  else
                  {
                    DbgPrintEx(0x96u, 0, "WERDIAG: Service returned failure status. NTSTATUS: %08X\n", v38);
                    v3 = v38;
                  }
                }
              }
              else
              {
                DbgPrintEx(0x96u, 0, "WERDIAG: NtAlpcConnectPort failed. NTSTATUS: %08X\n", (unsigned int)v14);
              }
            }
            else
            {
              DbgPrintEx(0x96u, 0, "WERDIAG: RtlAllocateAndInitializeSid failed. NTSTATUS: %08X\n", (unsigned int)v12);
            }
          }
        }
        else
        {
          DbgPrintEx(0x96u, 0, "WERDIAG: NtQuerySysInfo(ErrorPortTimeouts) failed. NTSTATUS: %08X\n", (unsigned int)v8);
        }
      }
      else
      {
        v3 = -1073741696;
        DbgPrintEx(0x96u, 0, "WERDIAG: SignalStartWerSvc failed NTSTATUS: %08X\n", 3221225600LL);
      }
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: PluginsNtGetRegStringValue failed. NTSTATUS: %08X\n", (unsigned int)RegStringValue);
    }
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening registry key. NTSTATUS: %08X\n", (unsigned int)v2);
  }
  v17 = Sid;
  Sid = 0;
  if ( v17 )
    RtlFreeSid(v17);
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( SourceString )
    operator delete[]((void *)SourceString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002234  push    rbp
0x180002236  push    rbx
0x180002237  push    rsi
0x180002238  push    rdi
0x180002239  push    r13
0x18000223b  push    r15
0x18000223d  lea     rbp, [rsp-10D8h]
0x180002245  mov     eax, 11D8h
0x18000224a  call    _alloca_probe
0x18000224f  sub     rsp, rax
0x180002252  mov     rax, cs:__security_cookie
0x180002259  xor     rax, rsp
0x18000225c  mov     [rbp+1100h+var_40], rax
0x180002263  xor     r15d, r15d
0x180002266  mov     [rbp+1100h+SourceString], r15
0x18000226a  mov     [rsp+1200h+Handle], r15
0x18000226f  mov     [rbp+1100h+KeyHandle], r15
0x180002273  mov     ebx, 578h
0x180002278  mov     r8d, ebx; Size
0x18000227b  xor     edx, edx; Val
0x18000227d  lea     rcx, [rbp+1100h+var_B40]; void *
0x180002284  call    memset_0
0x180002289  mov     r8d, ebx; Size
0x18000228c  xor     edx, edx; Val
0x18000228e  lea     rcx, [rbp+1100h+var_5C0]; void *
0x180002295  call    memset_0
0x18000229a  mov     [rbp+1100h+var_1160], r15
0x18000229e  xorps   xmm0, xmm0
0x1800022a1  movups  xmmword ptr [rbp+1100h+DestinationString.Length], xmm0
0x1800022a5  xorps   xmm1, xmm1
0x1800022a8  movups  [rbp+1100h+var_1148], xmm1
0x1800022ac  movups  [rbp+1100h+var_1138], xmm1
0x1800022b0  movups  [rbp+1100h+var_1128], xmm1
0x1800022b4  mov     [rsp+1200h+Sid], r15
0x1800022b9  mov     dword ptr [rbp+1100h+IdentifierAuthority.Value], r15d
0x1800022c0  mov     word ptr [rbp+1100h+IdentifierAuthority.Value+4], 500h
0x1800022c9  mov     [rbp+1100h+var_1180], r15
0x1800022cd  mov     [rsp+1200h+SystemInformation], r15
0x1800022d2  lea     rax, [rbp+1100h+KeyHandle]
0x1800022d6  mov     qword ptr [rsp+1200h+SubAuthority2], rax; KeyHandle
0x1800022db  xor     r9d, r9d
0x1800022de  xor     r8d, r8d
0x1800022e1  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x1800022e8  lea     edi, [r15+1]
0x1800022ec  mov     ecx, edi; DesiredAccess
0x1800022ee  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x1800022f3  mov     ebx, eax
0x1800022f5  test    eax, eax
0x1800022f7  jns     short loc_180002308
0x1800022f9  mov     r9d, eax
0x1800022fc  lea     r8, aWerdiagFailedO_5; "WERDIAG: Failed opening registry key. N"...
0x180002303  jmp     loc_180002703
0x180002308  lea     r8, [rbp+1100h+SourceString]
0x18000230c  lea     rdx, aErrorport; "ErrorPort"
0x180002313  mov     rcx, [rbp+1100h+KeyHandle]; KeyHandle
0x180002317  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x18000231c  mov     ebx, eax
0x18000231e  test    eax, eax
0x180002320  jns     short loc_180002331
0x180002322  mov     r9d, eax
0x180002325  lea     r8, aWerdiagPlugins; "WERDIAG: PluginsNtGetRegStringValue fai"...
0x18000232c  jmp     loc_180002703
0x180002331  xorps   xmm0, xmm0
0x180002334  movups  [rbp+1100h+var_B58], xmm0
0x18000233b  mov     dword ptr [rsp+1200h+EventHandle], r15d
0x180002340  mov     ebx, r15d
0x180002343  mov     [rsp+1200h+SubAuthority2], 4
0x18000234b  lea     r9, [rsp+1200h+EventHandle]
0x180002350  xor     r8d, r8d
0x180002353  mov     edx, edi
0x180002355  lea     rcx, WNF_WER_SERVICE_START
0x18000235c  call    cs:__imp_ZwQueryWnfStateNameInformation
0x180002362  test    eax, eax
0x180002364  js      short loc_180002396
0x180002366  cmp     dword ptr [rsp+1200h+EventHandle], r15d
0x18000236b  jz      short loc_180002396
0x18000236d  mov     [rsp+1200h+SubAuthority4], r15d
0x180002372  mov     [rsp+1200h+SubAuthority3], r15d
0x180002377  mov     qword ptr [rsp+1200h+SubAuthority2], r15
0x18000237c  xor     r9d, r9d
0x18000237f  xor     r8d, r8d
0x180002382  xor     edx, edx
0x180002384  lea     rcx, WNF_WER_SERVICE_START
0x18000238b  call    cs:__imp_ZwUpdateWnfStateData
0x180002391  test    eax, eax
0x180002393  cmovns  ebx, edi
0x180002396  xorps   xmm0, xmm0
0x180002399  movups  [rbp+1100h+var_B58], xmm0
0x1800023a0  xor     r9d, r9d
0x1800023a3  xor     r8d, r8d
0x1800023a6  lea     rdx, [rbp+1100h+var_B58]
0x1800023ad  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x1800023b4  call    cs:__imp_EtwEventWriteNoRegistration
0x1800023ba  lea     ecx, [rbx+1]
0x1800023bd  test    eax, eax
0x1800023bf  cmovnz  ecx, ebx
0x1800023c2  test    ecx, ecx
0x1800023c4  jnz     short loc_1800023D7
0x1800023c6  mov     ebx, 0C0000080h
0x1800023cb  lea     r8, aWerdiagSignals; "WERDIAG: SignalStartWerSvc failed NTSTA"...
0x1800023d2  jmp     loc_180002700
0x1800023d7  xor     r9d, r9d; ReturnLength
0x1800023da  lea     r8d, [r9+8]; SystemInformationLength
0x1800023de  lea     rdx, [rsp+1200h+SystemInformation]; SystemInformation
0x1800023e3  lea     ecx, [r9+73h]; SystemInformationClass
0x1800023e7  call    cs:__imp_NtQuerySystemInformation
0x1800023ed  mov     ebx, eax
0x1800023ef  test    eax, eax
0x1800023f1  jns     short loc_180002402
0x1800023f3  mov     r9d, eax
0x1800023f6  lea     r8, aWerdiagNtquery; "WERDIAG: NtQuerySysInfo(ErrorPortTimeou"...
0x1800023fd  jmp     loc_180002703
0x180002402  movsxd  rsi, dword ptr [rsp+1200h+SystemInformation]
0x180002407  mov     qword ptr [rbp+1100h+var_B58], 480046h
0x180002412  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x180002419  mov     qword ptr [rbp+1100h+var_B58+8], rax
0x180002420  mov     qword ptr [rbp+1100h+ObjectAttributes.Length], 30h ; '0'
0x180002428  mov     qword ptr [rbp+1100h+ObjectAttributes.Attributes], r15
0x18000242c  mov     [rsp+1200h+EventHandle], r15
0x180002431  mov     [rbp+1100h+var_1168], r15
0x180002435  mov     r13d, 30h ; '0'
0x18000243b  mov     [rbp+1100h+ObjectAttributes.RootDirectory], r15
0x18000243f  lea     rax, [rbp+1100h+var_B58]
0x180002446  mov     [rbp+1100h+ObjectAttributes.ObjectName], rax
0x18000244a  xorps   xmm0, xmm0
0x18000244d  movdqu  xmmword ptr [rbp+1100h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002452  lea     r8, [rbp+1100h+ObjectAttributes]; ObjectAttributes
0x180002456  mov     edx, 100001h; DesiredAccess
0x18000245b  lea     rcx, [rsp+1200h+EventHandle]; EventHandle
0x180002460  call    cs:__imp_NtOpenEvent
0x180002466  mov     ebx, eax
0x180002468  test    eax, eax
0x18000246a  js      loc_1800026F9
0x180002470  cmp     esi, 0FFFFFFFFh
0x180002473  jnz     short loc_18000247A
0x180002475  mov     dl, dil
0x180002478  jmp     short loc_180002488
0x18000247a  mov     dl, r15b
0x18000247d  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x180002484  mov     [rbp+1100h+var_1168], rcx
0x180002488  lea     r8, [rbp+1100h+var_1168]
0x18000248c  test    dl, dl
0x18000248e  cmovnz  r8, r15; Timeout
0x180002492  xor     edx, edx; Alertable
0x180002494  mov     rcx, [rsp+1200h+EventHandle]; Handle
0x180002499  call    cs:__imp_NtWaitForSingleObject
0x18000249f  mov     ebx, eax
0x1800024a1  mov     rcx, [rsp+1200h+EventHandle]; Handle
0x1800024a6  call    cs:__imp_NtClose
0x1800024ac  test    ebx, ebx
0x1800024ae  js      loc_1800026F9
0x1800024b4  cmp     ebx, 102h
0x1800024ba  jnz     short loc_1800024D1
0x1800024bc  mov     r9d, 0C0000353h
0x1800024c2  mov     ebx, r9d
0x1800024c5  lea     r8, aWerdiagWaitfor_0; "WERDIAG: WaitForWerSvc timed out, faili"...
0x1800024cc  jmp     loc_180002703
0x1800024d1  mov     rdx, [rbp+1100h+SourceString]; SourceString
0x1800024d5  lea     rcx, [rbp+1100h+DestinationString]; DestinationString
0x1800024d9  call    cs:__imp_RtlInitUnicodeString
0x1800024df  mov     rcx, [rsp+1200h+Sid]; Sid
0x1800024e4  mov     [rsp+1200h+Sid], r15
0x1800024e9  test    rcx, rcx
0x1800024ec  jz      short loc_1800024F4
0x1800024ee  call    cs:__imp_RtlFreeSid
0x1800024f4  lea     rax, [rsp+1200h+Sid]
0x1800024f9  mov     [rsp+1200h+var_11B0], rax; Sid
0x1800024fe  mov     [rsp+1200h+SubAuthority7], r15d; SubAuthority7
0x180002503  mov     [rsp+1200h+SubAuthority6], r15d; SubAuthority6
0x180002508  mov     [rsp+1200h+SubAuthority5], r15d; SubAuthority5
0x18000250d  mov     [rsp+1200h+SubAuthority4], r15d; SubAuthority4
0x180002512  mov     [rsp+1200h+SubAuthority3], r15d; SubAuthority3
0x180002517  mov     [rsp+1200h+SubAuthority2], r15d; SubAuthority2
0x18000251c  xor     r9d, r9d; SubAuthority1
0x18000251f  lea     r8d, [r9+12h]; SubAuthority0
0x180002523  mov     dl, dil; SubAuthorityCount
0x180002526  lea     rcx, [rbp+1100h+IdentifierAuthority]; IdentifierAuthority
0x18000252d  call    cs:__imp_RtlAllocateAndInitializeSid
0x180002533  mov     ebx, eax
0x180002535  test    eax, eax
0x180002537  jns     short loc_180002548
0x180002539  mov     r9d, eax
0x18000253c  lea     r8, aWerdiagRtlallo; "WERDIAG: RtlAllocateAndInitializeSid fa"...
0x180002543  jmp     loc_180002703
0x180002548  mov     dword ptr [rbp+1100h+var_1148], r13d
0x18000254c  mov     qword ptr [rbp+1100h+var_1148+8], r15
0x180002550  mov     dword ptr [rbp+1100h+var_1138+8], r15d
0x180002554  mov     qword ptr [rbp+1100h+var_1138], r15
0x180002558  xorps   xmm0, xmm0
0x18000255b  movdqu  [rbp+1100h+var_1128], xmm0
0x180002560  cmp     dword ptr [rsp+1200h+SystemInformation+4], 0FFFFFFFFh
0x180002565  jz      short loc_18000257A
0x180002567  mov     dil, r15b
0x18000256a  movsxd  rax, dword ptr [rsp+1200h+SystemInformation+4]
0x18000256f  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x180002576  mov     [rbp+1100h+var_1180], rcx
0x18000257a  lea     rsi, [rbp+1100h+var_1180]
0x18000257e  test    dil, dil
0x180002581  cmovnz  rsi, r15
0x180002585  mov     [rsp+1200h+var_11B0], rsi
0x18000258a  mov     qword ptr [rsp+1200h+SubAuthority7], r15
0x18000258f  mov     qword ptr [rsp+1200h+SubAuthority6], r15
0x180002594  mov     qword ptr [rsp+1200h+SubAuthority5], r15
0x180002599  mov     qword ptr [rsp+1200h+SubAuthority4], r15
0x18000259e  mov     rax, [rsp+1200h+Sid]
0x1800025a3  mov     qword ptr [rsp+1200h+SubAuthority3], rax
0x1800025a8  mov     [rsp+1200h+SubAuthority2], 20000h
0x1800025b0  xor     r9d, r9d
0x1800025b3  lea     r8, [rbp+1100h+var_1148]
0x1800025b7  lea     rdx, [rbp+1100h+DestinationString]
0x1800025bb  lea     rcx, [rsp+1200h+Handle]
0x1800025c0  call    cs:__imp_NtAlpcConnectPort
0x1800025c6  mov     ebx, eax
0x1800025c8  test    eax, eax
0x1800025ca  jns     short loc_1800025DB
0x1800025cc  mov     r9d, eax
0x1800025cf  lea     r8, aWerdiagNtalpcc_0; "WERDIAG: NtAlpcConnectPort failed. NTST"...
0x1800025d6  jmp     loc_180002703
0x1800025db  cmp     eax, 102h
0x1800025e0  jnz     short loc_1800025F7
0x1800025e2  mov     r9d, 0C0000353h
0x1800025e8  mov     ebx, r9d
0x1800025eb  lea     r8, aWerdiagNtalpcc; "WERDIAG: NtAlpcConnectPort timed out, f"...
0x1800025f2  jmp     loc_180002703
0x1800025f7  mov     rbx, [rsp+1200h+Handle]
0x1800025fc  test    rbx, rbx
0x1800025ff  jnz     short loc_18000260B
0x180002601  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002606  mov     rbx, [rsp+1200h+Handle]
0x18000260b  mov     r13d, 578h
0x180002611  mov     r8d, r13d; Size
0x180002614  xor     edx, edx; Val
0x180002616  lea     rcx, [rbp+1100h+Src]; void *
0x18000261a  call    memset_0
0x18000261f  lea     rcx, [rbp+1100h+var_B40]; void *
0x180002626  lea     rdx, [rbp+1100h+Src]; Src
0x18000262a  mov     r8d, r13d; Size
0x18000262d  call    memcpy_0
0x180002632  mov     [rbp+1100h+var_B40], 5780550h
0x18000263c  mov     [rbp+1100h+var_B18], 80000000h
0x180002646  mov     [rbp+1100h+var_B10], r15d
0x18000264d  mov     r8d, r13d; Size
0x180002650  xor     edx, edx; Val
0x180002652  lea     rcx, [rbp+1100h+Src]; void *
0x180002656  call    memset_0
0x18000265b  lea     rcx, [rbp+1100h+var_5C0]; void *
0x180002662  lea     rdx, [rbp+1100h+Src]; Src
0x180002666  mov     r8d, r13d; Size
0x180002669  call    memcpy_0
0x18000266e  mov     [rbp+1100h+var_5C0], 5780550h
0x180002678  mov     [rbp+1100h+var_1160], r13
0x18000267c  mov     qword ptr [rsp+1200h+SubAuthority5], rsi
0x180002681  mov     qword ptr [rsp+1200h+SubAuthority4], r15
0x180002686  lea     rax, [rbp+1100h+var_1160]
0x18000268a  mov     qword ptr [rsp+1200h+SubAuthority3], rax
0x18000268f  lea     rax, [rbp+1100h+var_5C0]
0x180002696  mov     qword ptr [rsp+1200h+SubAuthority2], rax
0x18000269b  xor     r9d, r9d
0x18000269e  lea     r8, [rbp+1100h+var_B40]
0x1800026a5  mov     edx, 20000h
0x1800026aa  mov     rcx, rbx
0x1800026ad  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800026b3  mov     ebx, eax
0x1800026b5  test    eax, eax
0x1800026b7  js      short loc_1800026ED
0x1800026b9  cmp     eax, 102h
0x1800026be  jz      short loc_1800026ED
0x1800026c0  mov     r9d, [rbp+1100h+var_594]
0x1800026c7  test    r9d, r9d
0x1800026ca  jns     short loc_1800026E8
0x1800026cc  lea     r8, aWerdiagService; "WERDIAG: Service returned failure statu"...
0x1800026d3  xor     edx, edx; Level
0x1800026d5  mov     ecx, 96h; ComponentId
0x1800026da  call    cs:__imp_DbgPrintEx
0x1800026e0  mov     ebx, [rbp+1100h+var_594]
0x1800026e6  jmp     short loc_180002710
0x1800026e8  mov     ebx, r15d
0x1800026eb  jmp     short loc_180002710
0x1800026ed  mov     r9d, eax
0x1800026f0  lea     r8, aWerdiagNtalpcs; "WERDIAG: NtAlpcSendWaitReceivePort fail"...
0x1800026f7  jmp     short loc_180002703
0x1800026f9  lea     r8, aWerdiagWaitfor; "WERDIAG: WaitForWerSvc failed. NTSTATUS"...
0x180002700  mov     r9d, ebx
0x180002703  xor     edx, edx; Level
0x180002705  mov     ecx, 96h; ComponentId
0x18000270a  call    cs:__imp_DbgPrintEx
0x180002710  mov     rcx, [rsp+1200h+Sid]; Sid
0x180002715  mov     [rsp+1200h+Sid], r15
0x18000271a  test    rcx, rcx
0x18000271d  jz      short loc_180002725
0x18000271f  call    cs:__imp_RtlFreeSid
0x180002725  mov     rcx, [rsp+1200h+Handle]; Handle
0x18000272a  test    rcx, rcx
0x18000272d  jz      short loc_18000273A
0x18000272f  call    cs:__imp_NtClose
0x180002735  mov     [rsp+1200h+Handle], r15
0x18000273a  mov     rcx, [rsp+1200h+Sid]; Sid
0x18000273f  test    rcx, rcx
0x180002742  jz      short loc_18000274B
0x180002744  call    cs:__imp_RtlFreeSid
  ... truncated ...
```
