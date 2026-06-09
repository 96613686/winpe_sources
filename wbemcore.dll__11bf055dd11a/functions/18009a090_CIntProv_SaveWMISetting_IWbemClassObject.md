# CIntProv::SaveWMISetting(IWbemClassObject *)

- ea: `0x18009a090`
- end: `0x18009a42f`
- name: `?SaveWMISetting@CIntProv@@QEAAJPEAUIWbemClassObject@@@Z`
- size: `927`
- prototype: `int(CIntProv *__hidden this, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099520`

## callees

- `0x18000b140`
- `0x180099780`
- `0x180099904`
- `0x18009a090`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetDWORD@CVar@@QEAAKXZ` at `0x18009a11a`
- `wbemcomn!?GetDWORD@CVar@@QEAAKXZ` at `0x18009a129`
- `wbemcomn!?GetDWORD@CVar@@QEAAKXZ` at `0x18009a13a`
- `wbemcomn!?GetDWORD@CVar@@QEAAKXZ` at `0x18009a11a`
- `wbemcomn!?GetDWORD@CVar@@QEAAKXZ` at `0x18009a129`
- `wbemcomn!?GetDWORD@CVar@@QEAAKXZ` at `0x18009a13a`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18009a256`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18009a2c9`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18009a3d9`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18009a256`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18009a2c9`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18009a3d9`
- `wbemcomn!?SetDWORDStr@Registry@@QEAAHPEBGK@Z` at `0x18009a2e4`
- `wbemcomn!?SetDWORDStr@Registry@@QEAAHPEBGK@Z` at `0x18009a2e4`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18009a0bb`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18009a0d0`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18009a0bb`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18009a0d0`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18009a271`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18009a3f4`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18009a271`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x18009a3f4`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18009a40c`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18009a417`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18009a40c`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18009a417`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18009a0db`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18009a0db`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18009a401`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18009a401`
- `wbemcomn!GetMemLogObject` at `0x18009a144`
- `wbemcomn!GetMemLogObject` at `0x18009a144`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009a154`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009a154`

## string_xrefs

- `0x18009a208`: `LoggingDirectory`
- `0x18009a20f`: `Logging Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIntProv::SaveWMISetting(CIntProv *this, struct IWbemClassObject *a2)
{
  unsigned int v3; // ebx
  CIntProv *v4; // rcx
  CMemoryLog *MemLogObject; // rax
  int v6; // ebx
  CIntProv *v7; // rcx
  int v8; // edi
  CIntProv *v9; // rcx
  int v10; // ebx
  CIntProv *v11; // rcx
  int v12; // edi
  CIntProv *v13; // rcx
  int v14; // r14d
  __int16 Bool; // ax
  int v16; // ebx
  CIntProv *v17; // rcx
  int v18; // edi
  __int16 v19; // ax
  int v20; // ebx
  CIntProv *v21; // rcx
  int v22; // edi
  CIntProv *v23; // rcx
  int v24; // ebx
  CIntProv *v25; // rcx
  int v26; // edi
  CIntProv *v27; // rcx
  int v28; // ebx
  CIntProv *v29; // rcx
  int v30; // edi
  __int16 v31; // ax
  _BYTE v33[24]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v34[24]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v35[80]; // [rsp+70h] [rbp+7h] BYREF

  Registry::Registry((Registry *)v33, L"Software\\Microsoft\\WBEM\\CIMOM", 2u);
  Registry::Registry((Registry *)v34, L"Software\\Microsoft\\WBEM\\scripting", 2u);
  CVar::CVar((CVar *)v35);
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, _BYTE *, _QWORD, _QWORD))a2->lpVtbl->Get)(
         a2,
         L"BackupInterval",
         0,
         v35,
         0,
         0);
  if ( !v3 )
  {
    if ( (CVar::GetDWORD((CVar *)v35) < 5 || CVar::GetDWORD((CVar *)v35) > 0x5A0) && CVar::GetDWORD((CVar *)v35) )
    {
      MemLogObject = GetMemLogObject();
      v3 = -2147217400;
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_74d77713876d364524dd83337d5790f1_Traceguids, 2147749896LL);
      }
    }
    else
    {
      v6 = CIntProv::PutRegUINTProp(
             v4,
             (struct Registry *)v33,
             L"Backup interval threshold",
             L"BackupInterval",
             (struct CWbemObject *)a2);
      v8 = v6
         | CIntProv::PutRegUINTProp(
             v7,
             (struct Registry *)v33,
             L"Log File Max Size",
             L"MaxLogFileSize",
             (struct CWbemObject *)a2);
      v10 = v8
          | CIntProv::PutRegUINTProp(v9, (struct Registry *)v33, L"Logging", L"LoggingLevel", (struct CWbemObject *)a2);
      v12 = v10
          | CIntProv::PutRegStrProp(
              v11,
              (struct Registry *)v33,
              L"Logging Directory",
              L"LoggingDirectory",
              (struct CWbemObject *)a2);
      v14 = v12
          | ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, _BYTE *, _QWORD, _QWORD))a2->lpVtbl->Get)(
              a2,
              L"ASPScriptEnabled",
              0,
              v35,
              0,
              0);
      if ( !v14 )
      {
        Bool = CVar::GetBool((CVar *)v35);
        Registry::SetDWORD((Registry *)v34, L"Enable for ASP", Bool != 0);
      }
      v16 = v14
          | CIntProv::PutRegStrProp(
              v13,
              (struct Registry *)v34,
              L"Default Namespace",
              L"ASPScriptDefaultNamespace",
              (struct CWbemObject *)a2);
      v18 = v16
          | ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, _BYTE *, _QWORD, _QWORD))a2->lpVtbl->Get)(
              a2,
              L"EnableEvents",
              0,
              v35,
              0,
              0);
      if ( !v18 )
      {
        v19 = CVar::GetBool((CVar *)v35);
        Registry::SetDWORDStr((Registry *)v33, L"EnableEvents", v19 != 0);
      }
      v20 = v18
          | CIntProv::PutRegUINTProp(
              v17,
              (struct Registry *)v33,
              L"High Threshold On Client Objects (b)",
              L"HighThresholdOnClientObjects",
              (struct CWbemObject *)a2);
      v22 = v20
          | CIntProv::PutRegUINTProp(
              v21,
              (struct Registry *)v33,
              L"Low Threshold On Client Objects (b)",
              L"LowThresholdOnClientObjects",
              (struct CWbemObject *)a2);
      v24 = v22
          | CIntProv::PutRegUINTProp(
              v23,
              (struct Registry *)v33,
              L"Max Wait On Client Objects (ms)",
              L"MaxWaitOnClientObjects",
              (struct CWbemObject *)a2);
      v26 = v24
          | CIntProv::PutRegUINTProp(
              v25,
              (struct Registry *)v33,
              L"High Threshold On Events (b)",
              L"HighThresholdOnEvents",
              (struct CWbemObject *)a2);
      v28 = v26
          | CIntProv::PutRegUINTProp(
              v27,
              (struct Registry *)v33,
              L"Low Threshold On Events (b)",
              L"LowThresholdOnEvents",
              (struct CWbemObject *)a2);
      v30 = v28
          | CIntProv::PutRegUINTProp(
              v29,
              (struct Registry *)v33,
              L"Max Wait On Events (ms)",
              L"MaxWaitOnEvents",
              (struct CWbemObject *)a2);
      if ( !(v30
           | ((unsigned int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, _BYTE *, _QWORD, _QWORD))a2->lpVtbl->Get)(
               a2,
               L"EnableStartupHeapPreallocation",
               0,
               v35,
               0,
               0)) )
      {
        v31 = CVar::GetBool((CVar *)v35);
        Registry::SetDWORD((Registry *)v33, L"EnableStartupHeapPreallocation", v31 != 0);
      }
      v3 = 0;
    }
  }
  CVar::~CVar((CVar *)v35);
  Registry::~Registry((Registry *)v34);
  Registry::~Registry((Registry *)v33);
  return v3;
}

```

## disassembly

```asm
0x18009a090  push    rbp
0x18009a092  push    rbx
0x18009a093  push    rsi
0x18009a094  push    rdi
0x18009a095  push    r14
0x18009a097  push    r15
0x18009a099  lea     rbp, [rsp-2Fh]
0x18009a09e  sub     rsp, 98h
0x18009a0a5  mov     rsi, rdx
0x18009a0a8  mov     edi, 2
0x18009a0ad  mov     r8d, edi
0x18009a0b0  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x18009a0b7  lea     rcx, [rbp+57h+var_80]
0x18009a0bb  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18009a0c1  nop
0x18009a0c2  mov     r8d, edi
0x18009a0c5  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\WBEM\\scripting"
0x18009a0cc  lea     rcx, [rbp+57h+var_68]
0x18009a0d0  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18009a0d6  nop
0x18009a0d7  lea     rcx, [rbp+57h+var_50]
0x18009a0db  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18009a0e1  nop
0x18009a0e2  mov     rax, [rsi]
0x18009a0e5  xor     r15d, r15d
0x18009a0e8  mov     [rsp+0C0h+var_98], r15
0x18009a0ed  mov     [rsp+0C0h+var_A0], r15
0x18009a0f2  lea     r9, [rbp+57h+var_50]
0x18009a0f6  xor     r8d, r8d
0x18009a0f9  lea     rdx, aBackupinterval; "BackupInterval"
0x18009a100  mov     rcx, rsi
0x18009a103  mov     rax, [rax+20h]
0x18009a107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a10c  mov     ebx, eax
0x18009a10e  test    eax, eax
0x18009a110  jnz     loc_18009A3FD
0x18009a116  lea     rcx, [rbp+57h+var_50]
0x18009a11a  call    cs:__imp_?GetDWORD@CVar@@QEAAKXZ; CVar::GetDWORD(void)
0x18009a120  cmp     eax, 5
0x18009a123  jb      short loc_18009A136
0x18009a125  lea     rcx, [rbp+57h+var_50]
0x18009a129  call    cs:__imp_?GetDWORD@CVar@@QEAAKXZ; CVar::GetDWORD(void)
0x18009a12f  cmp     eax, 5A0h
0x18009a134  jbe     short loc_18009A1A5
0x18009a136  lea     rcx, [rbp+57h+var_50]
0x18009a13a  call    cs:__imp_?GetDWORD@CVar@@QEAAKXZ; CVar::GetDWORD(void)
0x18009a140  test    eax, eax
0x18009a142  jz      short loc_18009A1A5
0x18009a144  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009a14a  mov     ebx, 80041008h
0x18009a14f  mov     edx, ebx
0x18009a151  mov     rcx, rax
0x18009a154  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009a15a  lea     rax, WPP_GLOBAL_Control
0x18009a161  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a168  cmp     rcx, rax
0x18009a16b  jz      loc_18009A3FD
0x18009a171  test    byte ptr [rcx+1Ch], 1
0x18009a175  jz      loc_18009A3FD
0x18009a17b  cmp     [rcx+19h], dil
0x18009a17f  jb      loc_18009A3FD
0x18009a185  mov     edx, 22h ; '"'
0x18009a18a  mov     r9d, 80041008h
0x18009a190  lea     r8, WPP_74d77713876d364524dd83337d5790f1_Traceguids
0x18009a197  mov     rcx, [rcx+10h]
0x18009a19b  call    WPP_SF_d
0x18009a1a0  jmp     loc_18009A3FD
0x18009a1a5  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a1aa  lea     r9, aBackupinterval; "BackupInterval"
0x18009a1b1  lea     r8, aBackupInterval_0; "Backup interval threshold"
0x18009a1b8  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a1bc  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a1c1  mov     ebx, eax
0x18009a1c3  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a1c8  lea     r9, aMaxlogfilesize; "MaxLogFileSize"
0x18009a1cf  lea     r8, aLogFileMaxSize; "Log File Max Size"
0x18009a1d6  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a1da  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a1df  mov     edi, eax
0x18009a1e1  or      edi, ebx
0x18009a1e3  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a1e8  lea     r9, aLogginglevel; "LoggingLevel"
0x18009a1ef  lea     r8, aLogging; "Logging"
0x18009a1f6  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a1fa  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a1ff  mov     ebx, eax
0x18009a201  or      ebx, edi
0x18009a203  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a208  lea     r9, aLoggingdirecto; "LoggingDirectory"
0x18009a20f  lea     r8, aLoggingDirecto; "Logging Directory"
0x18009a216  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a21a  call    ?PutRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a21f  mov     edi, eax
0x18009a221  or      edi, ebx
0x18009a223  mov     rcx, [rsi]
0x18009a226  mov     rax, [rcx+20h]
0x18009a22a  mov     [rsp+0C0h+var_98], r15
0x18009a22f  mov     [rsp+0C0h+var_A0], r15
0x18009a234  lea     r9, [rbp+57h+var_50]
0x18009a238  xor     r8d, r8d
0x18009a23b  lea     rdx, aAspscriptenabl; "ASPScriptEnabled"
0x18009a242  mov     rcx, rsi
0x18009a245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a24a  mov     r14d, eax
0x18009a24d  or      r14d, edi
0x18009a250  jnz     short loc_18009A277
0x18009a252  lea     rcx, [rbp+57h+var_50]
0x18009a256  call    cs:__imp_?GetBool@CVar@@QEAAFXZ; CVar::GetBool(void)
0x18009a25c  mov     r8d, r15d
0x18009a25f  test    ax, ax
0x18009a262  setnz   r8b
0x18009a266  lea     rdx, aEnableForAsp; "Enable for ASP"
0x18009a26d  lea     rcx, [rbp+57h+var_68]
0x18009a271  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18009a277  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a27c  lea     r9, aAspscriptdefau; "ASPScriptDefaultNamespace"
0x18009a283  lea     r8, aDefaultNamespa; "Default Namespace"
0x18009a28a  lea     rdx, [rbp+57h+var_68]; struct Registry *
0x18009a28e  call    ?PutRegStrProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegStrProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a293  mov     ebx, eax
0x18009a295  or      ebx, r14d
0x18009a298  mov     rcx, [rsi]
0x18009a29b  mov     rax, [rcx+20h]
0x18009a29f  mov     [rsp+0C0h+var_98], r15
0x18009a2a4  mov     [rsp+0C0h+var_A0], r15
0x18009a2a9  lea     r9, [rbp+57h+var_50]
0x18009a2ad  xor     r8d, r8d
0x18009a2b0  lea     rdx, aEnableevents; "EnableEvents"
0x18009a2b7  mov     rcx, rsi
0x18009a2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a2bf  mov     edi, eax
0x18009a2c1  or      edi, ebx
0x18009a2c3  jnz     short loc_18009A2EA
0x18009a2c5  lea     rcx, [rbp+57h+var_50]
0x18009a2c9  call    cs:__imp_?GetBool@CVar@@QEAAFXZ; CVar::GetBool(void)
0x18009a2cf  mov     r8d, r15d
0x18009a2d2  test    ax, ax
0x18009a2d5  setnz   r8b
0x18009a2d9  lea     rdx, aEnableevents; "EnableEvents"
0x18009a2e0  lea     rcx, [rbp+57h+var_80]
0x18009a2e4  call    cs:__imp_?SetDWORDStr@Registry@@QEAAHPEBGK@Z; Registry::SetDWORDStr(ushort const *,ulong)
0x18009a2ea  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a2ef  lea     r9, aHighthresholdo_0; "HighThresholdOnClientObjects"
0x18009a2f6  lea     r8, aHighThresholdO; "High Threshold On Client Objects (b)"
0x18009a2fd  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a301  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a306  mov     ebx, eax
0x18009a308  or      ebx, edi
0x18009a30a  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a30f  lea     r9, aLowthresholdon_0; "LowThresholdOnClientObjects"
0x18009a316  lea     r8, aLowThresholdOn_0; "Low Threshold On Client Objects (b)"
0x18009a31d  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a321  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a326  mov     edi, eax
0x18009a328  or      edi, ebx
0x18009a32a  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a32f  lea     r9, aMaxwaitonclien; "MaxWaitOnClientObjects"
0x18009a336  lea     r8, aMaxWaitOnClien; "Max Wait On Client Objects (ms)"
0x18009a33d  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a341  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a346  mov     ebx, eax
0x18009a348  or      ebx, edi
0x18009a34a  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a34f  lea     r9, aHighthresholdo; "HighThresholdOnEvents"
0x18009a356  lea     r8, aHighThresholdO_0; "High Threshold On Events (b)"
0x18009a35d  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a361  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a366  mov     edi, eax
0x18009a368  or      edi, ebx
0x18009a36a  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a36f  lea     r9, aLowthresholdon; "LowThresholdOnEvents"
0x18009a376  lea     r8, aLowThresholdOn; "Low Threshold On Events (b)"
0x18009a37d  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a381  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a386  mov     ebx, eax
0x18009a388  or      ebx, edi
0x18009a38a  mov     [rsp+0C0h+var_A0], rsi; struct CWbemObject *
0x18009a38f  lea     r9, aMaxwaitonevent; "MaxWaitOnEvents"
0x18009a396  lea     r8, aMaxWaitOnEvent; "Max Wait On Events (ms)"
0x18009a39d  lea     rdx, [rbp+57h+var_80]; struct Registry *
0x18009a3a1  call    ?PutRegUINTProp@CIntProv@@QEAAJAEAVRegistry@@PEAG1PEAVCWbemObject@@@Z; CIntProv::PutRegUINTProp(Registry &,ushort *,ushort *,CWbemObject *)
0x18009a3a6  mov     edi, eax
0x18009a3a8  or      edi, ebx
0x18009a3aa  mov     rcx, [rsi]
0x18009a3ad  mov     rax, [rcx+20h]
0x18009a3b1  mov     [rsp+0C0h+var_98], r15
0x18009a3b6  mov     [rsp+0C0h+var_A0], r15
0x18009a3bb  lea     r9, [rbp+57h+var_50]
0x18009a3bf  xor     r8d, r8d
0x18009a3c2  lea     rdx, aEnablestartuph; "EnableStartupHeapPreallocation"
0x18009a3c9  mov     rcx, rsi
0x18009a3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a3d1  or      eax, edi
0x18009a3d3  jnz     short loc_18009A3FA
0x18009a3d5  lea     rcx, [rbp+57h+var_50]
0x18009a3d9  call    cs:__imp_?GetBool@CVar@@QEAAFXZ; CVar::GetBool(void)
0x18009a3df  mov     r8d, r15d
0x18009a3e2  test    ax, ax
0x18009a3e5  setnz   r8b
0x18009a3e9  lea     rdx, aEnablestartuph; "EnableStartupHeapPreallocation"
0x18009a3f0  lea     rcx, [rbp+57h+var_80]
0x18009a3f4  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x18009a3fa  mov     ebx, r15d
0x18009a3fd  lea     rcx, [rbp+57h+var_50]
0x18009a401  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18009a407  nop
0x18009a408  lea     rcx, [rbp+57h+var_68]
0x18009a40c  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18009a412  nop
0x18009a413  lea     rcx, [rbp+57h+var_80]
0x18009a417  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18009a41d  mov     eax, ebx
0x18009a41f  add     rsp, 98h
0x18009a426  pop     r15
0x18009a428  pop     r14
0x18009a42a  pop     rdi
0x18009a42b  pop     rsi
0x18009a42c  pop     rbx
0x18009a42d  pop     rbp
0x18009a42e  retn
```
