# CApplySecurityTemplate::Execute(void *,tagVARIANT *)

- ea: `0x18002e410`
- end: `0x18002e7f7`
- name: `?Execute@CApplySecurityTemplate@@UEAAJPEAXPEAUtagVARIANT@@@Z`
- size: `999`
- prototype: `__int64 __fastcall(CApplySecurityTemplate *this, void *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001090`
- `0x1800013a4`
- `0x18001a280`
- `0x18001ad5c`
- `0x180025a7c`
- `0x18002ddd8`
- `0x18002e410`
- `0x18002e8b4`
- `0x18004325c`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x18002e59a`
- `ntdll!VerSetConditionMask` at `0x18002e59a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e606`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e606`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18002e5ad`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18002e5ad`

## string_xrefs

- `0x18002e541`: `IsAppServerInstalled`
- `0x18002e4a9`: `IsAutomatedAppServerInstallation`
- `0x18002e6c0`: `ApplySecurityTemplate`
- `0x18002e759`: `ApplySecurityTemplate`
- `0x18002e709`: `Applied server security template`
- `0x18002e79e`: `Applied default server security template`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApplySecurityTemplate::Execute(CApplySecurityTemplate *this, void *a2, struct tagVARIANT *a3)
{
  int IsAutomatedAppServerInstallation; // eax
  CApplySecurityTemplate *v6; // rcx
  unsigned int IsRdshTemplateApplied; // ebx
  char *v8; // rdx
  int *v9; // rax
  ULONGLONG v10; // rax
  BOOL v11; // eax
  BOOL v12; // r14d
  const char *v13; // rax
  char *v14; // rdx
  int *v16; // [rsp+38h] [rbp-C8h]
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  const char *v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v20; // [rsp+58h] [rbp-A8h] BYREF
  struct _OSVERSIONINFOEXW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF

  v19[0] = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  v17 = 0;
  IsAutomatedAppServerInstallation = CSLQuery::IsAutomatedAppServerInstallation(&v17);
  IsRdshTemplateApplied = IsAutomatedAppServerInstallation;
  if ( IsAutomatedAppServerInstallation >= 0 )
  {
    if ( !v17 )
      return IsRdshTemplateApplied;
    IsRdshTemplateApplied = CApplySecurityTemplate::IsRdshTemplateApplied(v6, v19);
    if ( (IsRdshTemplateApplied & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180084170 <= 3 )
        return IsRdshTemplateApplied;
      v18 = "Execute";
      v8 = (char *)&word_180079B5E;
      v20 = "IsAppServerInstalled";
      *(_QWORD *)v19 = "Warning HResult failed";
      v16 = (int *)&v18;
      v9 = v19;
      goto LABEL_4;
    }
    VersionInformation.dwOSVersionInfoSize = 284;
    VersionInformation.wSuiteMask = 16;
    v10 = VerSetConditionMask(0, 0x40u, 7u);
    v11 = VerifyVersionInfoW(&VersionInformation, 0x40u, v10);
    v12 = v11;
    if ( (unsigned int)dword_180084170 > 4 )
    {
      v17 = v11;
      v18 = "VER_SUITE_TERMINAL check for multi-session SKU";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180084170,
        (unsigned int)byte_180079B25,
        0,
        0,
        (__int64)&v18,
        (__int64)&v17);
    }
    if ( !WaitForSingleObject(a2, 1u) )
    {
      IsRdshTemplateApplied = -2147467260;
      if ( (unsigned int)dword_180084170 <= 3 )
        return IsRdshTemplateApplied;
      v18 = "Execute";
      v8 = byte_180079AE5;
      v20 = "Abort was signalled";
      *(_QWORD *)v19 = "Warning HResult failed";
      v16 = (int *)&v18;
      v9 = v19;
      goto LABEL_4;
    }
    if ( v12 )
    {
      if ( v19[0] )
        return IsRdshTemplateApplied;
      IsRdshTemplateApplied = CApplySecurityTemplate::ApplySecurityTemplate(this, 1);
      if ( (IsRdshTemplateApplied & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_180084170 <= 3 )
          return IsRdshTemplateApplied;
        v18 = "Execute";
        v8 = byte_180079AA5;
        v20 = "ApplySecurityTemplate";
        *(_QWORD *)v19 = "Warning HResult failed";
        v16 = (int *)&v18;
        v9 = v19;
        goto LABEL_4;
      }
      if ( (unsigned int)dword_180084170 <= 4 )
        return IsRdshTemplateApplied;
      v13 = "Applied server security template";
      v14 = &byte_180079A7F;
    }
    else
    {
      if ( !v19[0] )
        return IsRdshTemplateApplied;
      IsRdshTemplateApplied = CApplySecurityTemplate::ApplySecurityTemplate(this, 0);
      if ( (IsRdshTemplateApplied & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_180084170 <= 3 )
          return IsRdshTemplateApplied;
        v18 = "Execute";
        v8 = &byte_180079A3F;
        v20 = "ApplySecurityTemplate";
        *(_QWORD *)v19 = "Warning HResult failed";
        v16 = (int *)&v18;
        v9 = v19;
        goto LABEL_4;
      }
      if ( (unsigned int)dword_180084170 <= 4 )
        return IsRdshTemplateApplied;
      v13 = "Applied default server security template";
      v14 = byte_180079A19;
    }
    v18 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_180084170,
      (_DWORD)v14,
      0,
      0,
      (__int64)&v18);
    return IsRdshTemplateApplied;
  }
  MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)IsAutomatedAppServerInstallation, 0);
  if ( (unsigned int)dword_180084170 > 3 )
  {
    *(_QWORD *)v19 = "Execute";
    v8 = (char *)&word_180079B9E;
    v20 = "IsAutomatedAppServerInstallation";
    v18 = "Warning HResult failed";
    v16 = v19;
    v9 = (int *)&v18;
LABEL_4:
    v17 = IsRdshTemplateApplied;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)&dword_180084170,
      (_DWORD)v8,
      0,
      0,
      (__int64)v9,
      (__int64)&v20,
      (__int64)&v17,
      (__int64)v16);
  }
  return IsRdshTemplateApplied;
}

```

## disassembly

```asm
0x18002e410  mov     [rsp-8+arg_10], rbx
0x18002e415  mov     [rsp-8+arg_18], rsi
0x18002e41a  push    rbp
0x18002e41b  push    r14
0x18002e41d  push    r15
0x18002e41f  lea     rbp, [rsp-90h]
0x18002e427  sub     rsp, 190h
0x18002e42e  mov     rax, cs:__security_cookie
0x18002e435  xor     rax, rsp
0x18002e438  mov     [rbp+0A0h+var_20], rax
0x18002e43f  mov     r15, rdx
0x18002e442  mov     [rsp+1A0h+var_150], 0
0x18002e44a  mov     rsi, rcx
0x18002e44d  xor     edx, edx; Val
0x18002e44f  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x18002e454  mov     r8d, 11Ch; Size
0x18002e45a  call    memset_0
0x18002e45f  lea     rcx, [rsp+1A0h+var_160]; int *
0x18002e464  mov     [rsp+1A0h+var_160], 0
0x18002e46c  call    ?IsAutomatedAppServerInstallation@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAutomatedAppServerInstallation(int *)
0x18002e471  mov     ebx, eax
0x18002e473  test    eax, eax
0x18002e475  jns     loc_18002E504
0x18002e47b  xor     r8d, r8d
0x18002e47e  mov     edx, eax
0x18002e480  xor     ecx, ecx
0x18002e482  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e487  mov     ecx, cs:dword_180084170
0x18002e48d  cmp     ecx, 3
0x18002e490  jbe     loc_18002E7CD
0x18002e496  lea     rax, aExecute; "Execute"
0x18002e49d  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002e4a2  lea     rdx, word_180079B9E
0x18002e4a9  lea     rax, aIsautomatedapp_0; "IsAutomatedAppServerInstallation"
0x18002e4b0  mov     [rsp+1A0h+var_148], rax
0x18002e4b5  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e4bc  mov     [rsp+1A0h+var_158], rax
0x18002e4c1  lea     rax, [rsp+1A0h+var_150]
0x18002e4c6  mov     [rsp+1A0h+var_168], rax
0x18002e4cb  lea     rax, [rsp+1A0h+var_160]
0x18002e4d0  mov     [rsp+1A0h+var_170], rax
0x18002e4d5  lea     rax, [rsp+1A0h+var_148]
0x18002e4da  mov     [rsp+1A0h+var_178], rax
0x18002e4df  lea     rax, [rsp+1A0h+var_158]
0x18002e4e4  xor     r9d, r9d
0x18002e4e7  mov     [rsp+1A0h+var_160], ebx
0x18002e4eb  xor     r8d, r8d
0x18002e4ee  mov     [rsp+1A0h+var_180], rax
0x18002e4f3  lea     rcx, dword_180084170
0x18002e4fa  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002e4ff  jmp     loc_18002E7CD
0x18002e504  cmp     [rsp+1A0h+var_160], 0
0x18002e509  jz      loc_18002E7CD
0x18002e50f  lea     rdx, [rsp+1A0h+var_150]; int *
0x18002e514  call    ?IsRdshTemplateApplied@CApplySecurityTemplate@@AEAAJPEAH@Z; CApplySecurityTemplate::IsRdshTemplateApplied(int *)
0x18002e519  mov     ebx, eax
0x18002e51b  test    eax, eax
0x18002e51d  jns     short loc_18002E581
0x18002e51f  mov     eax, cs:dword_180084170
0x18002e525  cmp     eax, 3
0x18002e528  jbe     loc_18002E7CD
0x18002e52e  lea     rax, aExecute; "Execute"
0x18002e535  mov     [rsp+1A0h+var_158], rax
0x18002e53a  lea     rdx, word_180079B5E
0x18002e541  lea     rax, aIsappserverins; "IsAppServerInstalled"
0x18002e548  mov     [rsp+1A0h+var_148], rax
0x18002e54d  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e554  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002e559  lea     rax, [rsp+1A0h+var_158]
0x18002e55e  mov     [rsp+1A0h+var_168], rax
0x18002e563  lea     rax, [rsp+1A0h+var_160]
0x18002e568  mov     [rsp+1A0h+var_170], rax
0x18002e56d  lea     rax, [rsp+1A0h+var_148]
0x18002e572  mov     [rsp+1A0h+var_178], rax
0x18002e577  lea     rax, [rsp+1A0h+var_150]
0x18002e57c  jmp     loc_18002E4E4
0x18002e581  mov     eax, 10h
0x18002e586  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002e58e  mov     r8b, 7; Condition
0x18002e591  mov     [rbp+0A0h+VersionInformation.wSuiteMask], ax
0x18002e595  xor     ecx, ecx; ConditionMask
0x18002e597  lea     edx, [rax+30h]; TypeMask
0x18002e59a  call    cs:__imp_VerSetConditionMask
0x18002e5a0  mov     edx, 40h ; '@'; dwTypeMask
0x18002e5a5  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x18002e5aa  mov     r8, rax; dwlConditionMask
0x18002e5ad  call    cs:__imp_VerifyVersionInfoW
0x18002e5b3  mov     ecx, cs:dword_180084170
0x18002e5b9  mov     r14d, eax
0x18002e5bc  cmp     ecx, 4
0x18002e5bf  jbe     short loc_18002E5FE
0x18002e5c1  mov     [rsp+1A0h+var_160], eax
0x18002e5c5  lea     rdx, byte_180079B25
0x18002e5cc  lea     rax, aVerSuiteTermin; "VER_SUITE_TERMINAL check for multi-sess"...
0x18002e5d3  xor     r9d, r9d
0x18002e5d6  mov     [rsp+1A0h+var_158], rax
0x18002e5db  lea     rcx, dword_180084170
0x18002e5e2  lea     rax, [rsp+1A0h+var_160]
0x18002e5e7  xor     r8d, r8d
0x18002e5ea  mov     [rsp+1A0h+var_178], rax
0x18002e5ef  lea     rax, [rsp+1A0h+var_158]
0x18002e5f4  mov     [rsp+1A0h+var_180], rax
0x18002e5f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002e5fe  mov     edx, 1; dwMilliseconds
0x18002e603  mov     rcx, r15; hHandle
0x18002e606  call    cs:__imp_WaitForSingleObject
0x18002e60c  test    eax, eax
0x18002e60e  jnz     short loc_18002E677
0x18002e610  mov     eax, cs:dword_180084170
0x18002e616  mov     ebx, 80004004h
0x18002e61b  cmp     eax, 3
0x18002e61e  jbe     loc_18002E7CD
0x18002e624  lea     rax, aExecute; "Execute"
0x18002e62b  mov     [rsp+1A0h+var_158], rax
0x18002e630  lea     rdx, byte_180079AE5
0x18002e637  lea     rax, aAbortWasSignal_0; "Abort was signalled"
0x18002e63e  mov     [rsp+1A0h+var_148], rax
0x18002e643  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e64a  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002e64f  lea     rax, [rsp+1A0h+var_158]
0x18002e654  mov     [rsp+1A0h+var_168], rax
0x18002e659  lea     rax, [rsp+1A0h+var_160]
0x18002e65e  mov     [rsp+1A0h+var_170], rax
0x18002e663  lea     rax, [rsp+1A0h+var_148]
0x18002e668  mov     [rsp+1A0h+var_178], rax
0x18002e66d  lea     rax, [rsp+1A0h+var_150]
0x18002e672  jmp     loc_18002E4E4
0x18002e677  test    r14d, r14d
0x18002e67a  jz      loc_18002E71C
0x18002e680  cmp     [rsp+1A0h+var_150], 0
0x18002e685  jnz     loc_18002E7CD
0x18002e68b  mov     edx, 1
0x18002e690  mov     rcx, rsi
0x18002e693  call    ?ApplySecurityTemplate@CApplySecurityTemplate@@AEAAJW4ESSecurityTemplate@1@@Z; CApplySecurityTemplate::ApplySecurityTemplate(CApplySecurityTemplate::ESSecurityTemplate)
0x18002e698  mov     ebx, eax
0x18002e69a  test    eax, eax
0x18002e69c  mov     eax, cs:dword_180084170
0x18002e6a2  jns     short loc_18002E700
0x18002e6a4  cmp     eax, 3
0x18002e6a7  jbe     loc_18002E7CD
0x18002e6ad  lea     rax, aExecute; "Execute"
0x18002e6b4  mov     [rsp+1A0h+var_158], rax
0x18002e6b9  lea     rdx, byte_180079AA5
0x18002e6c0  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002e6c7  mov     [rsp+1A0h+var_148], rax
0x18002e6cc  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e6d3  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002e6d8  lea     rax, [rsp+1A0h+var_158]
0x18002e6dd  mov     [rsp+1A0h+var_168], rax
0x18002e6e2  lea     rax, [rsp+1A0h+var_160]
0x18002e6e7  mov     [rsp+1A0h+var_170], rax
0x18002e6ec  lea     rax, [rsp+1A0h+var_148]
0x18002e6f1  mov     [rsp+1A0h+var_178], rax
0x18002e6f6  lea     rax, [rsp+1A0h+var_150]
0x18002e6fb  jmp     loc_18002E4E4
0x18002e700  cmp     eax, 4
0x18002e703  jbe     loc_18002E7CD
0x18002e709  lea     rax, aAppliedServerS; "Applied server security template"
0x18002e710  lea     rdx, byte_180079A7F
0x18002e717  jmp     loc_18002E7AC
0x18002e71c  cmp     [rsp+1A0h+var_150], 0
0x18002e721  jz      loc_18002E7CD
0x18002e727  xor     edx, edx
0x18002e729  mov     rcx, rsi
0x18002e72c  call    ?ApplySecurityTemplate@CApplySecurityTemplate@@AEAAJW4ESSecurityTemplate@1@@Z; CApplySecurityTemplate::ApplySecurityTemplate(CApplySecurityTemplate::ESSecurityTemplate)
0x18002e731  mov     ebx, eax
0x18002e733  test    eax, eax
0x18002e735  mov     eax, cs:dword_180084170
0x18002e73b  jns     short loc_18002E799
0x18002e73d  cmp     eax, 3
0x18002e740  jbe     loc_18002E7CD
0x18002e746  lea     rax, aExecute; "Execute"
0x18002e74d  mov     [rsp+1A0h+var_158], rax
0x18002e752  lea     rdx, byte_180079A3F
0x18002e759  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002e760  mov     [rsp+1A0h+var_148], rax
0x18002e765  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e76c  mov     qword ptr [rsp+1A0h+var_150], rax
0x18002e771  lea     rax, [rsp+1A0h+var_158]
0x18002e776  mov     [rsp+1A0h+var_168], rax
0x18002e77b  lea     rax, [rsp+1A0h+var_160]
0x18002e780  mov     [rsp+1A0h+var_170], rax
0x18002e785  lea     rax, [rsp+1A0h+var_148]
0x18002e78a  mov     [rsp+1A0h+var_178], rax
0x18002e78f  lea     rax, [rsp+1A0h+var_150]
0x18002e794  jmp     loc_18002E4E4
0x18002e799  cmp     eax, 4
0x18002e79c  jbe     short loc_18002E7CD
0x18002e79e  lea     rax, aAppliedDefault; "Applied default server security templat"...
0x18002e7a5  lea     rdx, byte_180079A19
0x18002e7ac  mov     [rsp+1A0h+var_158], rax
0x18002e7b1  lea     rcx, dword_180084170
0x18002e7b8  lea     rax, [rsp+1A0h+var_158]
0x18002e7bd  xor     r9d, r9d
0x18002e7c0  xor     r8d, r8d
0x18002e7c3  mov     [rsp+1A0h+var_180], rax
0x18002e7c8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002e7cd  mov     eax, ebx
0x18002e7cf  mov     rcx, [rbp+0A0h+var_20]
0x18002e7d6  xor     rcx, rsp; StackCookie
0x18002e7d9  call    __security_check_cookie
0x18002e7de  lea     r11, [rsp+1A0h+var_10]
0x18002e7e6  mov     rbx, [r11+30h]
0x18002e7ea  mov     rsi, [r11+38h]
0x18002e7ee  mov     rsp, r11
0x18002e7f1  pop     r15
0x18002e7f3  pop     r14
0x18002e7f5  pop     rbp
0x18002e7f6  retn
```
