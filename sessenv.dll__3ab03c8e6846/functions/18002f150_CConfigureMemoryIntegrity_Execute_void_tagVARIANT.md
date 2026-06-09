# CConfigureMemoryIntegrity::Execute(void *,tagVARIANT *)

- ea: `0x18002f150`
- end: `0x18002f4ff`
- name: `?Execute@CConfigureMemoryIntegrity@@UEAAJPEAXPEAUtagVARIANT@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(CConfigureMemoryIntegrity *__hidden this, HANDLE hHandle, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001090`
- `0x180001134`
- `0x1800013a4`
- `0x18001a280`
- `0x18001ad5c`
- `0x180025a7c`
- `0x18002edd8`
- `0x18002f150`
- `0x18002f5c4`
- `0x18004325c`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x18002f318`
- `ntdll!VerSetConditionMask` at `0x18002f318`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f380`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f380`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18002f328`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18002f328`

## string_xrefs

- `0x18002f1ea`: `IsAutomatedAppServerInstallation`
- `0x18002f25b`: `IsAutomatedAppServerInstallation returned false, skipping.`
- `0x18002f435`: `ConfigureMemoryIntegrity`
- `0x18002f47a`: `Configured Memory Integrity`
- `0x18002f498`: `Skipping configuring Memory Integrity`

## pseudocode

```c
__int64 __fastcall CConfigureMemoryIntegrity::Execute(
        CConfigureMemoryIntegrity *this,
        HANDLE hHandle,
        struct tagVARIANT *a3)
{
  int IsAutomatedAppServerInstallation; // eax
  CConfigureMemoryIntegrity *v6; // rcx
  unsigned int IsMemoryIntegrityOverrideApplied; // ebx
  __int16 *v8; // rdx
  int *v9; // rax
  const char *v10; // rax
  char *v11; // rdx
  ULONGLONG v12; // rax
  BOOL v13; // eax
  int v14; // edi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int *v19; // [rsp+38h] [rbp-C8h]
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  const char *v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v23; // [rsp+58h] [rbp-A8h] BYREF
  struct _OSVERSIONINFOEXW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF

  v20 = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  v22[0] = 0;
  IsAutomatedAppServerInstallation = CSLQuery::IsAutomatedAppServerInstallation(v22);
  IsMemoryIntegrityOverrideApplied = IsAutomatedAppServerInstallation;
  if ( IsAutomatedAppServerInstallation >= 0 )
  {
    if ( v22[0] )
    {
      IsMemoryIntegrityOverrideApplied = CConfigureMemoryIntegrity::IsMemoryIntegrityOverrideApplied(v6, &v20);
      if ( (IsMemoryIntegrityOverrideApplied & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_180084170 <= 3 )
          return IsMemoryIntegrityOverrideApplied;
        v21 = "Execute";
        v8 = &word_18007A0CE;
        v23 = "IsMemoryIntegrityOverrideApplied";
        *(_QWORD *)v22 = "Warning HResult failed";
        v19 = (int *)&v21;
        v9 = v22;
        goto LABEL_4;
      }
      VersionInformation.dwOSVersionInfoSize = 284;
      VersionInformation.wSuiteMask = 16;
      v12 = VerSetConditionMask(0, 0x40u, 7u);
      v13 = VerifyVersionInfoW(&VersionInformation, 0x40u, v12);
      v14 = v13;
      if ( (unsigned int)dword_180084170 > 4 )
      {
        v22[0] = v13;
        v21 = "VER_SUITE_TERMINAL check for multi-session SKU";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180084170,
          (unsigned int)&dword_18007A08C,
          0,
          0,
          (__int64)&v21,
          (__int64)v22);
      }
      if ( !WaitForSingleObject(hHandle, 1u) )
      {
        IsMemoryIntegrityOverrideApplied = -2147467260;
        if ( (unsigned int)dword_180084170 <= 3 )
          return IsMemoryIntegrityOverrideApplied;
        v21 = "Execute";
        v8 = (__int16 *)byte_18007A043;
        v23 = "Abort was signalled";
        *(_QWORD *)v22 = "Warning HResult failed";
        v19 = (int *)&v21;
        v9 = v22;
        goto LABEL_4;
      }
      if ( !v14 || v20 )
      {
        if ( (unsigned int)dword_180084170 > 4 )
        {
          v21 = "Skipping configuring Memory Integrity";
          v22[0] = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v15,
            (unsigned int)&unk_180079F68,
            v16,
            v17,
            (__int64)&v21,
            (__int64)v22,
            (__int64)&v20);
        }
        return IsMemoryIntegrityOverrideApplied;
      }
      IsMemoryIntegrityOverrideApplied = CConfigureMemoryIntegrity::ConfigureMemoryIntegrity(this);
      if ( (IsMemoryIntegrityOverrideApplied & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_180084170 <= 3 )
          return IsMemoryIntegrityOverrideApplied;
        v21 = "Execute";
        v8 = word_180079FFA;
        v23 = "ConfigureMemoryIntegrity";
        *(_QWORD *)v22 = "Warning HResult failed";
        v19 = (int *)&v21;
        v9 = v22;
        goto LABEL_4;
      }
      if ( (unsigned int)dword_180084170 <= 4 )
        return IsMemoryIntegrityOverrideApplied;
      v10 = "Configured Memory Integrity";
      v11 = byte_180079FCB;
    }
    else
    {
      if ( (unsigned int)dword_180084170 <= 4 )
        return IsMemoryIntegrityOverrideApplied;
      v10 = "IsAutomatedAppServerInstallation returned false, skipping.";
      v11 = &byte_18007A117;
    }
    v21 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_180084170,
      (_DWORD)v11,
      0,
      0,
      (__int64)&v21);
    return IsMemoryIntegrityOverrideApplied;
  }
  MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)IsAutomatedAppServerInstallation, 0);
  if ( (unsigned int)dword_180084170 > 3 )
  {
    *(_QWORD *)v22 = "Execute";
    v8 = &word_18007A146;
    v23 = "IsAutomatedAppServerInstallation";
    v21 = "Warning HResult failed";
    v19 = v22;
    v9 = (int *)&v21;
LABEL_4:
    v20 = IsMemoryIntegrityOverrideApplied;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)&dword_180084170,
      (_DWORD)v8,
      0,
      0,
      (__int64)v9,
      (__int64)&v23,
      (__int64)&v20,
      (__int64)v19);
  }
  return IsMemoryIntegrityOverrideApplied;
}

```

## disassembly

```asm
0x18002f150  mov     [rsp-8+arg_10], rbx
0x18002f155  mov     [rsp-8+arg_18], rsi
0x18002f15a  push    rbp
0x18002f15b  push    rdi
0x18002f15c  push    r14
0x18002f15e  lea     rbp, [rsp-90h]
0x18002f166  sub     rsp, 190h
0x18002f16d  mov     rax, cs:__security_cookie
0x18002f174  xor     rax, rsp
0x18002f177  mov     [rbp+0A0h+var_20], rax
0x18002f17e  mov     r14, rdx
0x18002f181  mov     [rsp+1A0h+var_160], 0
0x18002f189  mov     rsi, rcx
0x18002f18c  mov     edi, 11Ch
0x18002f191  mov     r8d, edi; Size
0x18002f194  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x18002f199  xor     edx, edx; Val
0x18002f19b  call    memset_0
0x18002f1a0  lea     rcx, [rsp+1A0h+var_150]; int *
0x18002f1a5  mov     [rsp+1A0h+var_150], 0
0x18002f1ad  call    ?IsAutomatedAppServerInstallation@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAutomatedAppServerInstallation(int *)
0x18002f1b2  mov     ebx, eax
0x18002f1b4  test    eax, eax
0x18002f1b6  jns     loc_18002F245
0x18002f1bc  xor     r8d, r8d
0x18002f1bf  mov     edx, eax
0x18002f1c1  xor     ecx, ecx
0x18002f1c3  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002f1c8  mov     ecx, cs:dword_180084170
0x18002f1ce  cmp     ecx, 3
0x18002f1d1  jbe     loc_18002F4D6
0x18002f1d7  lea     rax, aExecute; "Execute"
0x18002f1de  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002f1e3  lea     rdx, word_18007A146
0x18002f1ea  lea     rax, aIsautomatedapp_0; "IsAutomatedAppServerInstallation"
0x18002f1f1  mov     [rsp+1A0h+var_148], rax
0x18002f1f6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f1fd  mov     [rsp+1A0h+var_158], rax
0x18002f202  lea     rax, [rsp+1A0h+var_150]
0x18002f207  mov     [rsp+1A0h+var_168], rax
0x18002f20c  lea     rax, [rsp+1A0h+var_160]
0x18002f211  mov     [rsp+1A0h+var_170], rax
0x18002f216  lea     rax, [rsp+1A0h+var_148]
0x18002f21b  mov     [rsp+1A0h+var_178], rax
0x18002f220  lea     rax, [rsp+1A0h+var_158]
0x18002f225  xor     r9d, r9d
0x18002f228  mov     [rsp+1A0h+var_180], rax
0x18002f22d  xor     r8d, r8d
0x18002f230  mov     [rsp+1A0h+var_160], ebx
0x18002f234  lea     rcx, dword_180084170
0x18002f23b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002f240  jmp     loc_18002F4D6
0x18002f245  cmp     [rsp+1A0h+var_150], 0
0x18002f24a  jnz     short loc_18002F28F
0x18002f24c  mov     eax, cs:dword_180084170
0x18002f252  cmp     eax, 4
0x18002f255  jbe     loc_18002F4D6
0x18002f25b  lea     rax, aIsautomatedapp_1; "IsAutomatedAppServerInstallation return"...
0x18002f262  lea     rdx, byte_18007A117
0x18002f269  mov     [rsp+1A0h+var_158], rax
0x18002f26e  lea     rcx, dword_180084170
0x18002f275  lea     rax, [rsp+1A0h+var_158]
0x18002f27a  xor     r9d, r9d
0x18002f27d  xor     r8d, r8d
0x18002f280  mov     [rsp+1A0h+var_180], rax
0x18002f285  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002f28a  jmp     loc_18002F4D6
0x18002f28f  lea     rdx, [rsp+1A0h+var_160]; int *
0x18002f294  call    ?IsMemoryIntegrityOverrideApplied@CConfigureMemoryIntegrity@@AEAAJPEAH@Z; CConfigureMemoryIntegrity::IsMemoryIntegrityOverrideApplied(int *)
0x18002f299  mov     ebx, eax
0x18002f29b  test    eax, eax
0x18002f29d  jns     short loc_18002F301
0x18002f29f  mov     eax, cs:dword_180084170
0x18002f2a5  cmp     eax, 3
0x18002f2a8  jbe     loc_18002F4D6
0x18002f2ae  lea     rax, aExecute; "Execute"
0x18002f2b5  mov     [rsp+1A0h+var_158], rax
0x18002f2ba  lea     rdx, word_18007A0CE
0x18002f2c1  lea     rax, aIsmemoryintegr; "IsMemoryIntegrityOverrideApplied"
0x18002f2c8  mov     [rsp+1A0h+var_148], rax
0x18002f2cd  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f2d4  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002f2d9  lea     rax, [rsp+1A0h+var_158]
0x18002f2de  mov     [rsp+1A0h+var_168], rax
0x18002f2e3  lea     rax, [rsp+1A0h+var_160]
0x18002f2e8  mov     [rsp+1A0h+var_170], rax
0x18002f2ed  lea     rax, [rsp+1A0h+var_148]
0x18002f2f2  mov     [rsp+1A0h+var_178], rax
0x18002f2f7  lea     rax, [rsp+1A0h+var_150]
0x18002f2fc  jmp     loc_18002F225
0x18002f301  mov     eax, 10h
0x18002f306  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], edi
0x18002f30a  mov     r8b, 7; Condition
0x18002f30d  mov     [rbp+0A0h+VersionInformation.wSuiteMask], ax
0x18002f311  xor     ecx, ecx; ConditionMask
0x18002f313  lea     edi, [rax+30h]
0x18002f316  mov     edx, edi; TypeMask
0x18002f318  call    cs:__imp_VerSetConditionMask
0x18002f31e  mov     edx, edi; dwTypeMask
0x18002f320  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x18002f325  mov     r8, rax; dwlConditionMask
0x18002f328  call    cs:__imp_VerifyVersionInfoW
0x18002f32e  mov     ecx, cs:dword_180084170
0x18002f334  mov     edi, eax
0x18002f336  cmp     ecx, 4
0x18002f339  jbe     short loc_18002F378
0x18002f33b  mov     [rsp+1A0h+var_150], eax
0x18002f33f  lea     rdx, dword_18007A08C
0x18002f346  lea     rax, aVerSuiteTermin; "VER_SUITE_TERMINAL check for multi-sess"...
0x18002f34d  xor     r9d, r9d
0x18002f350  mov     [rsp+1A0h+var_158], rax
0x18002f355  lea     rcx, dword_180084170
0x18002f35c  lea     rax, [rsp+1A0h+var_150]
0x18002f361  xor     r8d, r8d
0x18002f364  mov     [rsp+1A0h+var_178], rax
0x18002f369  lea     rax, [rsp+1A0h+var_158]
0x18002f36e  mov     [rsp+1A0h+var_180], rax
0x18002f373  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002f378  mov     edx, 1; dwMilliseconds
0x18002f37d  mov     rcx, r14; hHandle
0x18002f380  call    cs:__imp_WaitForSingleObject
0x18002f386  test    eax, eax
0x18002f388  jnz     short loc_18002F3F1
0x18002f38a  mov     eax, cs:dword_180084170
0x18002f390  mov     ebx, 80004004h
0x18002f395  cmp     eax, 3
0x18002f398  jbe     loc_18002F4D6
0x18002f39e  lea     rax, aExecute; "Execute"
0x18002f3a5  mov     [rsp+1A0h+var_158], rax
0x18002f3aa  lea     rdx, byte_18007A043
0x18002f3b1  lea     rax, aAbortWasSignal_0; "Abort was signalled"
0x18002f3b8  mov     [rsp+1A0h+var_148], rax
0x18002f3bd  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f3c4  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002f3c9  lea     rax, [rsp+1A0h+var_158]
0x18002f3ce  mov     [rsp+1A0h+var_168], rax
0x18002f3d3  lea     rax, [rsp+1A0h+var_160]
0x18002f3d8  mov     [rsp+1A0h+var_170], rax
0x18002f3dd  lea     rax, [rsp+1A0h+var_148]
0x18002f3e2  mov     [rsp+1A0h+var_178], rax
0x18002f3e7  lea     rax, [rsp+1A0h+var_150]
0x18002f3ec  jmp     loc_18002F225
0x18002f3f1  mov     edx, [rsp+1A0h+var_160]
0x18002f3f5  test    edi, edi
0x18002f3f7  jz      loc_18002F48D
0x18002f3fd  test    edx, edx
0x18002f3ff  jnz     loc_18002F48D
0x18002f405  mov     rcx, rsi; this
0x18002f408  call    ?ConfigureMemoryIntegrity@CConfigureMemoryIntegrity@@AEAAJXZ; CConfigureMemoryIntegrity::ConfigureMemoryIntegrity(void)
0x18002f40d  mov     ebx, eax
0x18002f40f  test    eax, eax
0x18002f411  mov     eax, cs:dword_180084170
0x18002f417  jns     short loc_18002F475
0x18002f419  cmp     eax, 3
0x18002f41c  jbe     loc_18002F4D6
0x18002f422  lea     rax, aExecute; "Execute"
0x18002f429  mov     [rsp+1A0h+var_158], rax
0x18002f42e  lea     rdx, word_180079FFA
0x18002f435  lea     rax, aConfigurememor; "ConfigureMemoryIntegrity"
0x18002f43c  mov     [rsp+1A0h+var_148], rax
0x18002f441  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f448  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002f44d  lea     rax, [rsp+1A0h+var_158]
0x18002f452  mov     [rsp+1A0h+var_168], rax
0x18002f457  lea     rax, [rsp+1A0h+var_160]
0x18002f45c  mov     [rsp+1A0h+var_170], rax
0x18002f461  lea     rax, [rsp+1A0h+var_148]
0x18002f466  mov     [rsp+1A0h+var_178], rax
0x18002f46b  lea     rax, [rsp+1A0h+var_150]
0x18002f470  jmp     loc_18002F225
0x18002f475  cmp     eax, 4
0x18002f478  jbe     short loc_18002F4D6
0x18002f47a  lea     rax, aConfiguredMemo; "Configured Memory Integrity"
0x18002f481  lea     rdx, byte_180079FCB
0x18002f488  jmp     loc_18002F269
0x18002f48d  mov     eax, cs:dword_180084170
0x18002f493  cmp     eax, 4
0x18002f496  jbe     short loc_18002F4D6
0x18002f498  lea     rax, aSkippingConfig; "Skipping configuring Memory Integrity"
0x18002f49f  mov     [rsp+1A0h+var_160], edx
0x18002f4a3  mov     [rsp+1A0h+var_158], rax
0x18002f4a8  lea     rdx, unk_180079F68
0x18002f4af  lea     rax, [rsp+1A0h+var_160]
0x18002f4b4  mov     [rsp+1A0h+var_150], edi
0x18002f4b8  mov     [rsp+1A0h+var_170], rax
0x18002f4bd  lea     rax, [rsp+1A0h+var_150]
0x18002f4c2  mov     [rsp+1A0h+var_178], rax
0x18002f4c7  lea     rax, [rsp+1A0h+var_158]
0x18002f4cc  mov     [rsp+1A0h+var_180], rax
0x18002f4d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002f4d6  mov     eax, ebx
0x18002f4d8  mov     rcx, [rbp+0A0h+var_20]
0x18002f4df  xor     rcx, rsp; StackCookie
0x18002f4e2  call    __security_check_cookie
0x18002f4e7  lea     r11, [rsp+1A0h+var_10]
0x18002f4ef  mov     rbx, [r11+30h]
0x18002f4f3  mov     rsi, [r11+38h]
0x18002f4f7  mov     rsp, r11
0x18002f4fa  pop     r14
0x18002f4fc  pop     rdi
0x18002f4fd  pop     rbp
0x18002f4fe  retn
```
