# CIntProv::CreateWMISetting(IWbemClassObject * *,IWbemContext *)

- ea: `0x180098ab4`
- end: `0x180098e57`
- name: `?CreateWMISetting@CIntProv@@QEAAJPEAPEAUIWbemClassObject@@PEAUIWbemContext@@@Z`
- size: `931`
- prototype: `int(CIntProv *__hidden this, struct IWbemClassObject **, struct IWbemContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800987b0`
- `0x180099030`

## callees

- `0x1800986e0`
- `0x180098ab4`
- `0x180099280`
- `0x1800993e4`
- `0x180099ac0`
- `0x180099d30`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?SetBool@CVar@@QEAAXF@Z` at `0x180098c8d`
- `wbemcomn!?SetBool@CVar@@QEAAXF@Z` at `0x180098deb`
- `wbemcomn!?SetBool@CVar@@QEAAXF@Z` at `0x180098c8d`
- `wbemcomn!?SetBool@CVar@@QEAAXF@Z` at `0x180098deb`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180098b0b`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180098b2e`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180098b51`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180098b0b`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180098b2e`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180098b51`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180098e24`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180098e2f`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180098e3a`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180098e24`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180098e2f`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180098e3a`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180098c65`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180098dcb`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180098c65`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180098dcb`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180098c76`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180098dd5`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180098c76`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180098dd5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180098cbb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180098e19`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180098cbb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180098e19`

## string_xrefs

- `0x180098bf3`: `Repository Directory`
- `0x180098b60`: `InstallationDirectory`
- `0x180098b67`: `Working Directory`
- `0x180098bd0`: `LoggingDirectory`
- `0x180098bd7`: `Logging Directory`
- `0x180098bec`: `DatabaseDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CIntProv::CreateWMISetting(CIntProv *this, struct IWbemClassObject **a2, struct IWbemContext *a3)
{
  __int64 result; // rax
  struct IWbemClassObject *v5; // rbx
  CIntProv *v6; // rcx
  CIntProv *v7; // rcx
  CIntProv *v8; // rcx
  CIntProv *v9; // rcx
  CIntProv *v10; // rcx
  CIntProv *v11; // rcx
  CIntProv *v12; // rcx
  CIntProv *v13; // rcx
  CIntProv *v14; // rcx
  CIntProv *v15; // rcx
  CIntProv *v16; // rcx
  __int16 v17; // di
  __int16 v18; // dx
  CIntProv *v19; // rcx
  CIntProv *v20; // rcx
  CIntProv *v21; // rcx
  CIntProv *v22; // rcx
  CIntProv *v23; // rcx
  CIntProv *v24; // rcx
  CIntProv *v25; // rcx
  CIntProv *v26; // rcx
  _BYTE v27[24]; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v29[24]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v30[24]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v31[32]; // [rsp+80h] [rbp+17h] BYREF
  _BYTE v32[32]; // [rsp+A0h] [rbp+37h] BYREF
  unsigned int v33; // [rsp+E8h] [rbp+7Fh] BYREF

  result = CIntProv::CreateInstance(this, L"Win32_WMISetting", a2, a3);
  if ( !(_DWORD)result )
  {
    Registry::Registry((Registry *)v30, HKEY_LOCAL_MACHINE, 0, 0x20019u, L"Software\\Microsoft\\WBEM");
    Registry::Registry((Registry *)v27, HKEY_LOCAL_MACHINE, 0, 0x20019u, L"Software\\Microsoft\\WBEM\\CIMOM");
    Registry::Registry((Registry *)v29, HKEY_LOCAL_MACHINE, 0, 0x20019u, L"Software\\Microsoft\\WBEM\\scripting");
    v5 = *a2;
    CIntProv::GetRegStrProp(
      v6,
      (struct Registry *)v27,
      L"Working Directory",
      L"InstallationDirectory",
      (struct CWbemObject *)v5);
    CIntProv::GetRegStrProp(v7, (struct Registry *)v30, L"Build", L"BuildVersion", (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v8,
      (struct Registry *)v27,
      L"Log File Max Size",
      L"MaxLogFileSize",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(v9, (struct Registry *)v27, L"Logging", L"LoggingLevel", (struct CWbemObject *)v5);
    CIntProv::GetRegStrProp(
      v10,
      (struct Registry *)v27,
      L"Logging Directory",
      L"LoggingDirectory",
      (struct CWbemObject *)v5);
    CIntProv::GetRegStrProp(
      v11,
      (struct Registry *)v27,
      L"Repository Directory",
      L"DatabaseDirectory",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(v12, (struct Registry *)v27, L"Max DB Size", L"DatabaseMaxSize", (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v13,
      (struct Registry *)v27,
      L"Backup interval threshold",
      L"BackupInterval",
      (struct CWbemObject *)v5);
    CIntProv::ReadAutoMofs(v14, (struct CWbemObject *)v5);
    CIntProv::ReadLastBackup(v15, (struct Registry *)v27, (struct CWbemObject *)v5);
    v33 = 0;
    v17 = -1;
    if ( !Registry::GetDWORD((Registry *)v29, L"Enable for ASP", &v33) )
    {
      CVar::CVar((CVar *)v31);
      if ( v33 )
        v18 = -1;
      else
        v18 = 0;
      CVar::SetBool((CVar *)v31, v18);
      ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _BYTE *, __int64))v5->lpVtbl[4].AddRef)(
        v5,
        L"ASPScriptEnabled",
        v31,
        11);
      CVar::~CVar((CVar *)v31);
    }
    CIntProv::GetRegStrProp(
      v16,
      (struct Registry *)v29,
      L"Default Namespace",
      L"ASPScriptDefaultNamespace",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(v19, (struct Registry *)v27, L"EnableEvents", L"EnableEvents", (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v20,
      (struct Registry *)v27,
      L"High Threshold On Client Objects (b)",
      L"HighThresholdOnClientObjects",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v21,
      (struct Registry *)v27,
      L"Low Threshold On Client Objects (b)",
      L"LowThresholdOnClientObjects",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v22,
      (struct Registry *)v27,
      L"Max Wait On Client Objects (ms)",
      L"MaxWaitOnClientObjects",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v23,
      (struct Registry *)v27,
      L"High Threshold On Events (b)",
      L"HighThresholdOnEvents",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v24,
      (struct Registry *)v27,
      L"Low Threshold On Events (b)",
      L"LowThresholdOnEvents",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v25,
      (struct Registry *)v27,
      L"Max Wait On Events (ms)",
      L"MaxWaitOnEvents",
      (struct CWbemObject *)v5);
    CIntProv::GetRegUINTProp(
      v26,
      (struct Registry *)v27,
      L"LastStartupHeapPreallocation",
      L"LastStartupHeapPreallocation",
      (struct CWbemObject *)v5);
    v28 = 0;
    Registry::GetDWORD((Registry *)v27, L"EnableStartupHeapPreallocation", &v28);
    CVar::CVar((CVar *)v32);
    if ( v28 != 1 )
      v17 = 0;
    CVar::SetBool((CVar *)v32, v17);
    ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _BYTE *, __int64))v5->lpVtbl[4].AddRef)(
      v5,
      L"EnableStartupHeapPreallocation",
      v32,
      11);
    CVar::~CVar((CVar *)v32);
    Registry::~Registry((Registry *)v29);
    Registry::~Registry((Registry *)v27);
    Registry::~Registry((Registry *)v30);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180098ab4  mov     [rsp-8+arg_0], rbx
0x180098ab9  mov     [rsp-8+arg_8], rdi
0x180098abe  push    rbp
0x180098abf  lea     rbp, [rsp-57h]
0x180098ac4  sub     rsp, 0C0h
0x180098acb  mov     rbx, rdx
0x180098ace  mov     r9, r8; struct IWbemContext *
0x180098ad1  mov     r8, rdx; struct IWbemClassObject **
0x180098ad4  lea     rdx, aWin32Wmisettin; "Win32_WMISetting"
0x180098adb  call    ?CreateInstance@CIntProv@@QEAAJPEAGPEAPEAUIWbemClassObject@@PEAUIWbemContext@@@Z; CIntProv::CreateInstance(ushort *,IWbemClassObject * *,IWbemContext *)
0x180098ae0  test    eax, eax
0x180098ae2  jnz     loc_180098E42
0x180098ae8  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\WBEM"
0x180098aef  mov     [rsp+0C0h+var_A0], rax
0x180098af4  mov     r9d, 20019h
0x180098afa  xor     r8d, r8d
0x180098afd  mov     rdi, 0FFFFFFFF80000002h
0x180098b04  mov     rdx, rdi
0x180098b07  lea     rcx, [rbp+57h+var_58]
0x180098b0b  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z; Registry::Registry(HKEY__ *,ulong,ulong,ushort const *)
0x180098b11  nop
0x180098b12  lea     rax, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x180098b19  mov     [rsp+0C0h+var_A0], rax
0x180098b1e  mov     r9d, 20019h
0x180098b24  xor     r8d, r8d
0x180098b27  mov     rdx, rdi
0x180098b2a  lea     rcx, [rbp+57h+var_90]
0x180098b2e  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z; Registry::Registry(HKEY__ *,ulong,ulong,ushort const *)
0x180098b34  nop
0x180098b35  lea     rax, aSoftwareMicros_4; "Software\\Microsoft\\WBEM\\scripting"
0x180098b3c  mov     [rsp+0C0h+var_A0], rax
0x180098b41  mov     r9d, 20019h
0x180098b47  xor     r8d, r8d
0x180098b4a  mov     rdx, rdi
0x180098b4d  lea     rcx, [rbp+57h+var_70]
0x180098b51  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z; Registry::Registry(HKEY__ *,ulong,ulong,ushort const *)
0x180098b57  nop
0x180098b58  mov     rbx, [rbx]
0x180098b5b  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098b60  lea     r9, aInstallationdi; "InstallationDirectory"
0x180098b67  lea     r8, aWorkingDirecto; "Working Directory"
0x180098b6e  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098b72  call    ?GetRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098b77  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098b7c  lea     r9, aBuildversion; "BuildVersion"
0x180098b83  lea     r8, aBuild; "Build"
0x180098b8a  lea     rdx, [rbp+57h+var_58]; struct Registry *
0x180098b8e  call    ?GetRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098b93  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098b98  lea     r9, aMaxlogfilesize; "MaxLogFileSize"
0x180098b9f  lea     r8, aLogFileMaxSize; "Log File Max Size"
0x180098ba6  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098baa  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098baf  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098bb4  lea     r9, aLogginglevel; "LoggingLevel"
0x180098bbb  lea     r8, aLogging; "Logging"
0x180098bc2  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098bc6  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098bcb  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098bd0  lea     r9, aLoggingdirecto; "LoggingDirectory"
0x180098bd7  lea     r8, aLoggingDirecto; "Logging Directory"
0x180098bde  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098be2  call    ?GetRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098be7  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098bec  lea     r9, aDatabasedirect; "DatabaseDirectory"
0x180098bf3  lea     r8, aRepositoryDire; "Repository Directory"
0x180098bfa  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098bfe  call    ?GetRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098c03  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098c08  lea     r9, aDatabasemaxsiz; "DatabaseMaxSize"
0x180098c0f  lea     r8, aMaxDbSize; "Max DB Size"
0x180098c16  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098c1a  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098c1f  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098c24  lea     r9, aBackupinterval; "BackupInterval"
0x180098c2b  lea     r8, aBackupInterval_0; "Backup interval threshold"
0x180098c32  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098c36  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098c3b  mov     rdx, rbx; struct CWbemObject *
0x180098c3e  call    ?ReadAutoMofs@CIntProv@@QEAAJPEAVCWbemObject@@@Z; CIntProv::ReadAutoMofs(CWbemObject *)
0x180098c43  mov     r8, rbx; struct CWbemObject *
0x180098c46  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098c4a  call    ?ReadLastBackup@CIntProv@@QEAAJAEAVRegistry@@PEAVCWbemObject@@@Z; CIntProv::ReadLastBackup(Registry &,CWbemObject *)
0x180098c4f  mov     [rbp+57h+arg_18], 0
0x180098c56  lea     r8, [rbp+57h+arg_18]
0x180098c5a  lea     rdx, aEnableForAsp; "Enable for ASP"
0x180098c61  lea     rcx, [rbp+57h+var_70]
0x180098c65  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x180098c6b  or      edi, 0FFFFFFFFh
0x180098c6e  test    eax, eax
0x180098c70  jnz     short loc_180098CC1
0x180098c72  lea     rcx, [rbp+57h+var_40]
0x180098c76  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180098c7c  nop
0x180098c7d  cmp     [rbp+57h+arg_18], 0
0x180098c81  jnz     short loc_180098C87
0x180098c83  xor     edx, edx
0x180098c85  jmp     short loc_180098C89
0x180098c87  mov     edx, edi
0x180098c89  lea     rcx, [rbp+57h+var_40]
0x180098c8d  call    cs:__imp_?SetBool@CVar@@QEAAXF@Z; CVar::SetBool(short)
0x180098c93  mov     rax, [rbx]
0x180098c96  mov     r9d, 0Bh
0x180098c9c  lea     r8, [rbp+57h+var_40]
0x180098ca0  lea     rdx, aAspscriptenabl; "ASPScriptEnabled"
0x180098ca7  mov     rcx, rbx
0x180098caa  mov     rax, [rax+368h]
0x180098cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cb6  nop
0x180098cb7  lea     rcx, [rbp+57h+var_40]
0x180098cbb  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180098cc1  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098cc6  lea     r9, aAspscriptdefau; "ASPScriptDefaultNamespace"
0x180098ccd  lea     r8, aDefaultNamespa; "Default Namespace"
0x180098cd4  lea     rdx, [rbp+57h+var_70]; struct Registry *
0x180098cd8  call    ?GetRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098cdd  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098ce2  lea     r8, aEnableevents; "EnableEvents"
0x180098ce9  mov     r9, r8; unsigned __int16 *
0x180098cec  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098cf0  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098cf5  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098cfa  lea     r9, aHighthresholdo_0; "HighThresholdOnClientObjects"
0x180098d01  lea     r8, aHighThresholdO; "High Threshold On Client Objects (b)"
0x180098d08  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098d0c  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098d11  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098d16  lea     r9, aLowthresholdon_0; "LowThresholdOnClientObjects"
0x180098d1d  lea     r8, aLowThresholdOn_0; "Low Threshold On Client Objects (b)"
0x180098d24  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098d28  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098d2d  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098d32  lea     r9, aMaxwaitonclien; "MaxWaitOnClientObjects"
0x180098d39  lea     r8, aMaxWaitOnClien; "Max Wait On Client Objects (ms)"
0x180098d40  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098d44  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098d49  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098d4e  lea     r9, aHighthresholdo; "HighThresholdOnEvents"
0x180098d55  lea     r8, aHighThresholdO_0; "High Threshold On Events (b)"
0x180098d5c  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098d60  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098d65  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098d6a  lea     r9, aLowthresholdon; "LowThresholdOnEvents"
0x180098d71  lea     r8, aLowThresholdOn; "Low Threshold On Events (b)"
0x180098d78  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098d7c  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098d81  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098d86  lea     r9, aMaxwaitonevent; "MaxWaitOnEvents"
0x180098d8d  lea     r8, aMaxWaitOnEvent; "Max Wait On Events (ms)"
0x180098d94  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098d98  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098d9d  mov     [rsp+0C0h+var_A0], rbx; struct CWbemObject *
0x180098da2  lea     r8, aLaststartuphea; "LastStartupHeapPreallocation"
0x180098da9  mov     r9, r8; unsigned __int16 *
0x180098dac  lea     rdx, [rbp+57h+var_90]; struct Registry *
0x180098db0  call    ?GetRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::GetRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x180098db5  mov     [rbp+57h+var_78], 0
0x180098dbc  lea     r8, [rbp+57h+var_78]
0x180098dc0  lea     rdx, aEnablestartuph; "EnableStartupHeapPreallocation"
0x180098dc7  lea     rcx, [rbp+57h+var_90]
0x180098dcb  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x180098dd1  lea     rcx, [rbp+57h+var_20]
0x180098dd5  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180098ddb  nop
0x180098ddc  cmp     [rbp+57h+var_78], 1
0x180098de0  jz      short loc_180098DE4
0x180098de2  xor     edi, edi
0x180098de4  movzx   edx, di
0x180098de7  lea     rcx, [rbp+57h+var_20]
0x180098deb  call    cs:__imp_?SetBool@CVar@@QEAAXF@Z; CVar::SetBool(short)
0x180098df1  mov     rax, [rbx]
0x180098df4  mov     r9d, 0Bh
0x180098dfa  lea     r8, [rbp+57h+var_20]
0x180098dfe  lea     rdx, aEnablestartuph; "EnableStartupHeapPreallocation"
0x180098e05  mov     rcx, rbx
0x180098e08  mov     rax, [rax+368h]
0x180098e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e14  nop
0x180098e15  lea     rcx, [rbp+57h+var_20]
0x180098e19  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180098e1f  nop
0x180098e20  lea     rcx, [rbp+57h+var_70]
0x180098e24  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180098e2a  nop
0x180098e2b  lea     rcx, [rbp+57h+var_90]
0x180098e2f  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180098e35  nop
0x180098e36  lea     rcx, [rbp+57h+var_58]
0x180098e3a  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180098e40  xor     eax, eax
0x180098e42  lea     r11, [rsp+0C0h+var_s0]
0x180098e4a  mov     rbx, [r11+10h]
0x180098e4e  mov     rdi, [r11+18h]
0x180098e52  mov     rsp, r11
0x180098e55  pop     rbp
0x180098e56  retn
```
