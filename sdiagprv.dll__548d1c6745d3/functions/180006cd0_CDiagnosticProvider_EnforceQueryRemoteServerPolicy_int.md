# CDiagnosticProvider::EnforceQueryRemoteServerPolicy(int *)

- ea: `0x180006cd0`
- end: `0x180006f97`
- name: `?EnforceQueryRemoteServerPolicy@CDiagnosticProvider@@AEAAJPEAH@Z`
- size: `711`
- prototype: `__int64 __fastcall(CDiagnosticProvider *this, int *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006fa0`

## callees

- `0x180001074`
- `0x18000247c`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180006cd0`
- `0x180007f68`
- `0x1800180f0`
- `0x180019010`

## string_xrefs

- `0x180006deb`: `QueryRemoteServerConfiguration::CreateInstance`
- `0x180006e02`: `QueryRemoteServerConfiguration::CreateInstance`
- `0x180006e2a`: `QueryRemoteServerConfiguration::CreateInstance`
- `0x180006e4f`: `QueryRemoteServerConfiguration::CreateInstance`
- `0x180006e76`: `QueryRemoteServerConfiguration::GetGroupPolicySetting`
- `0x180006eb3`: `QueryRemoteServerConfiguration::GetSystemWidePreference`

## pseudocode

```c
__int64 __fastcall CDiagnosticProvider::EnforceQueryRemoteServerPolicy(CDiagnosticProvider *this, int *a2, __int64 a3)
{
  unsigned int v5; // ebp
  QueryRemoteServerConfiguration *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rdx
  QueryRemoteServerConfiguration *v9; // rsi
  int v10; // edi
  __int64 v11; // r8
  int v12; // edi
  unsigned int v13; // eax
  __int64 *v14; // rdx
  int v15; // edi
  __int64 v17; // r9
  int v18; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-60h] BYREF
  int *v20; // [rsp+48h] [rbp-50h]
  __int64 v21; // [rsp+50h] [rbp-48h]

  if ( !a2 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CDiagnosticProvider::EnforceQueryRemoteServerPolicy",
        -2147024809,
        (__int64)"QueryRemoteServerAllowed");
    return v5;
  }
  v6 = 0;
  v5 = 0;
  v7 = 0xFFFFFFFFLL;
  *a2 = *((_WORD *)this + 44) == 0xFFFF;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 4) != 0 )
  {
    v18 = *((__int16 *)this + 44);
    v21 = 4;
    v20 = &v18;
    McGenEventWrite_EventWriteTransfer(
      0xFFFFFFFFLL,
      SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_QUERY_REMOTE_SERVER,
      a3,
      2,
      v19);
  }
  if ( !*((_WORD *)this + 44) )
    goto LABEL_35;
  v9 = (QueryRemoteServerConfiguration *)operator new(0x10u);
  if ( !v9 )
  {
    v10 = -2147024882;
    v9 = 0;
    goto LABEL_20;
  }
  *((_DWORD *)v9 + 2) = 1;
  *(_QWORD *)v9 = &QueryRemoteServerConfiguration::`vftable';
  *((_DWORD *)v9 + 3) = 1;
  v10 = QueryRemoteServerConfiguration::Initialize(v9);
  if ( v10 == -2147024882 )
  {
LABEL_20:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_40;
    McTemplateU0s_EventWriteTransfer(
      v7,
      SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
      "QueryRemoteServerConfiguration::CreateInstance");
LABEL_22:
    if ( v10 >= 0 )
      goto LABEL_23;
LABEL_40:
    if ( !v9 )
      goto LABEL_42;
    goto LABEL_41;
  }
  v6 = v9;
  if ( v10 < 0 )
    v6 = 0;
  if ( v10 != -2147024809 )
  {
    if ( !v10 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        McTemplateU0s_EventWriteTransfer(
          v7,
          SDIAGPRV_EVENT_DEBUG_SUCCESS,
          "QueryRemoteServerConfiguration::CreateInstance");
LABEL_23:
      v12 = *((_DWORD *)v6 + 2);
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        McTemplateU0s_EventWriteTransfer(
          v7,
          SDIAGPRV_EVENT_DEBUG_SUCCESS,
          "QueryRemoteServerConfiguration::GetGroupPolicySetting");
      v13 = QueryRemoteServerConfiguration::DISABLE_QUERY_REMOTE_SERVER;
      if ( QueryRemoteServerConfiguration::DISABLE_QUERY_REMOTE_SERVER == v12 )
      {
        v5 = 0;
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 1) != 0 )
        {
          v14 = SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_GROUP_POLICY_OVERRIDE;
LABEL_33:
          McGenEventWrite_EventWriteTransfer(v7, v14, v11, 1, v19);
        }
      }
      else
      {
        v15 = *((_DWORD *)v6 + 3);
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        {
          McTemplateU0s_EventWriteTransfer(
            v7,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "QueryRemoteServerConfiguration::GetSystemWidePreference");
          v13 = QueryRemoteServerConfiguration::DISABLE_QUERY_REMOTE_SERVER;
        }
        v5 = 0;
        if ( v13 != v15 )
          goto LABEL_35;
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 1) != 0 )
        {
          v14 = SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_SYSTEM_WIDE_PREFERENCE_OVERRIDE;
          goto LABEL_33;
        }
      }
      *a2 = 0;
LABEL_35:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
        McTemplateU0s_EventWriteTransfer(
          v7,
          SDIAGPRV_EVENT_DEBUG_SUCCESS,
          "CDiagnosticProvider::EnforceQueryRemoteServerPolicy");
      goto LABEL_37;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v7, v8, "QueryRemoteServerConfiguration::CreateInstance", (unsigned int)v10);
    goto LABEL_22;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v7, v8, "QueryRemoteServerConfiguration::CreateInstance", 2147942487LL);
LABEL_41:
  (**(void (__fastcall ***)(QueryRemoteServerConfiguration *, __int64))v9)(v9, 1);
LABEL_42:
  if ( v10 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_46;
    v17 = 2147942487LL;
    goto LABEL_45;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v17 = (unsigned int)v10;
LABEL_45:
    McTemplateU0sq_EventWriteTransfer(v7, v8, "CDiagnosticProvider::EnforceQueryRemoteServerPolicy", v17);
  }
LABEL_46:
  v5 = v10;
LABEL_37:
  if ( v6 )
    (**(void (__fastcall ***)(QueryRemoteServerConfiguration *, __int64))v6)(v6, 1);
  return v5;
}

```

## disassembly

```asm
0x180006cd0  push    rbx
0x180006cd2  push    rbp
0x180006cd3  push    rsi
0x180006cd4  push    rdi
0x180006cd5  push    r12
0x180006cd7  push    r14
0x180006cd9  sub     rsp, 68h
0x180006cdd  mov     rax, cs:__security_cookie
0x180006ce4  xor     rax, rsp
0x180006ce7  mov     [rsp+98h+var_40], rax
0x180006cec  mov     r14, rdx
0x180006cef  mov     rdi, rcx
0x180006cf2  test    rdx, rdx
0x180006cf5  jnz     short loc_180006D2C
0x180006cf7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006cfe  mov     ebp, 80070057h
0x180006d03  jz      loc_180006F29
0x180006d09  lea     rax, aQueryremoteser_4; "QueryRemoteServerAllowed"
0x180006d10  mov     r9d, 80070057h
0x180006d16  lea     r8, aCdiagnosticpro_4; "CDiagnosticProvider::EnforceQueryRemote"...
0x180006d1d  mov     [rsp+98h+var_78], rax
0x180006d22  call    McTemplateU0sqs_EventWriteTransfer
0x180006d27  jmp     loc_180006F29
0x180006d2c  xor     eax, eax
0x180006d2e  xor     ebx, ebx
0x180006d30  xor     ebp, ebp
0x180006d32  or      ecx, 0FFFFFFFFh
0x180006d35  cmp     cx, [rdi+58h]
0x180006d39  setz    al
0x180006d3c  mov     [rdx], eax
0x180006d3e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 4
0x180006d45  jz      short loc_180006D7C
0x180006d47  movsx   eax, word ptr [rdi+58h]
0x180006d4b  lea     r9d, [rbx+2]
0x180006d4f  mov     [rsp+98h+var_68], eax
0x180006d53  lea     rdx, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_QUERY_REMOTE_SERVER
0x180006d5a  lea     rax, [rsp+98h+var_68]
0x180006d5f  mov     [rsp+98h+var_48], 4
0x180006d68  mov     [rsp+98h+var_50], rax
0x180006d6d  lea     rax, [rsp+98h+var_60]
0x180006d72  mov     [rsp+98h+var_78], rax
0x180006d77  call    McGenEventWrite_EventWriteTransfer
0x180006d7c  xor     eax, eax
0x180006d7e  lea     r12d, [rax+1]
0x180006d82  cmp     ax, [rdi+58h]
0x180006d86  jz      loc_180006EF7
0x180006d8c  lea     ecx, [rax+10h]; Size
0x180006d8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d94  mov     rsi, rax
0x180006d97  mov     ebp, 80070057h
0x180006d9c  test    rax, rax
0x180006d9f  jz      loc_180006E3B
0x180006da5  lea     rax, ??_7QueryRemoteServerConfiguration@@6B@; const QueryRemoteServerConfiguration::`vftable'
0x180006dac  mov     [rsi+8], r12d
0x180006db0  mov     rcx, rsi; this
0x180006db3  mov     [rsi], rax
0x180006db6  mov     [rsi+0Ch], r12d
0x180006dba  call    ?Initialize@QueryRemoteServerConfiguration@@AEAAJXZ; QueryRemoteServerConfiguration::Initialize(void)
0x180006dbf  mov     edi, eax
0x180006dc1  test    eax, eax
0x180006dc3  jns     short loc_180006DCC
0x180006dc5  cmp     eax, 8007000Eh
0x180006dca  jz      short loc_180006E42
0x180006dcc  xor     eax, eax
0x180006dce  mov     rbx, rsi
0x180006dd1  test    edi, edi
0x180006dd3  cmovs   rbx, rax
0x180006dd7  cmp     edi, ebp
0x180006dd9  jz      short loc_180006E17
0x180006ddb  test    edi, edi
0x180006ddd  jz      short loc_180006DF9
0x180006ddf  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006de6  jz      short loc_180006E62
0x180006de8  mov     r9d, edi
0x180006deb  lea     r8, aQueryremoteser_5; "QueryRemoteServerConfiguration::CreateI"...
0x180006df2  call    McTemplateU0sq_EventWriteTransfer
0x180006df7  jmp     short loc_180006E62
0x180006df9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, r12b
0x180006e00  jz      short loc_180006E6A
0x180006e02  lea     r8, aQueryremoteser_5; "QueryRemoteServerConfiguration::CreateI"...
0x180006e09  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180006e10  call    McTemplateU0s_EventWriteTransfer
0x180006e15  jmp     short loc_180006E6A
0x180006e17  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006e1e  jz      loc_180006F4A
0x180006e24  mov     r9d, 80070057h
0x180006e2a  lea     r8, aQueryremoteser_5; "QueryRemoteServerConfiguration::CreateI"...
0x180006e31  call    McTemplateU0sq_EventWriteTransfer
0x180006e36  jmp     loc_180006F4A
0x180006e3b  mov     edi, 8007000Eh
0x180006e40  xor     esi, esi
0x180006e42  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006e49  jz      loc_180006F45
0x180006e4f  lea     r8, aQueryremoteser_5; "QueryRemoteServerConfiguration::CreateI"...
0x180006e56  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180006e5d  call    McTemplateU0s_EventWriteTransfer
0x180006e62  test    edi, edi
0x180006e64  js      loc_180006F45
0x180006e6a  mov     edi, [rbx+8]
0x180006e6d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, r12b
0x180006e74  jz      short loc_180006E89
0x180006e76  lea     r8, aQueryremoteser; "QueryRemoteServerConfiguration::GetGrou"...
0x180006e7d  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180006e84  call    McTemplateU0s_EventWriteTransfer
0x180006e89  mov     eax, cs:?DISABLE_QUERY_REMOTE_SERVER@QueryRemoteServerConfiguration@@2KA; ulong QueryRemoteServerConfiguration::DISABLE_QUERY_REMOTE_SERVER
0x180006e8f  cmp     eax, edi
0x180006e91  jnz     short loc_180006EA7
0x180006e93  xor     ebp, ebp
0x180006e95  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, r12b
0x180006e9c  jz      short loc_180006EF4
0x180006e9e  lea     rdx, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_GROUP_POLICY_OVERRIDE
0x180006ea5  jmp     short loc_180006EE2
0x180006ea7  mov     edi, [rbx+0Ch]
0x180006eaa  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, r12b
0x180006eb1  jz      short loc_180006ECC
0x180006eb3  lea     r8, aQueryremoteser_1; "QueryRemoteServerConfiguration::GetSyst"...
0x180006eba  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180006ec1  call    McTemplateU0s_EventWriteTransfer
0x180006ec6  mov     eax, cs:?DISABLE_QUERY_REMOTE_SERVER@QueryRemoteServerConfiguration@@2KA; ulong QueryRemoteServerConfiguration::DISABLE_QUERY_REMOTE_SERVER
0x180006ecc  xor     ebp, ebp
0x180006ece  cmp     eax, edi
0x180006ed0  jnz     short loc_180006EF7
0x180006ed2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, r12b
0x180006ed9  jz      short loc_180006EF4
0x180006edb  lea     rdx, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_SYSTEM_WIDE_PREFERENCE_OVERRIDE
0x180006ee2  lea     rax, [rsp+98h+var_60]
0x180006ee7  mov     r9d, r12d
0x180006eea  mov     [rsp+98h+var_78], rax
0x180006eef  call    McGenEventWrite_EventWriteTransfer
0x180006ef4  mov     [r14], ebp
0x180006ef7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, r12b
0x180006efe  jz      short loc_180006F13
0x180006f00  lea     r8, aCdiagnosticpro_4; "CDiagnosticProvider::EnforceQueryRemote"...
0x180006f07  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180006f0e  call    McTemplateU0s_EventWriteTransfer
0x180006f13  test    rbx, rbx
0x180006f16  jz      short loc_180006F29
0x180006f18  mov     r8, [rbx]
0x180006f1b  mov     edx, r12d
0x180006f1e  mov     rcx, rbx
0x180006f21  mov     rax, [r8]
0x180006f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f29  mov     eax, ebp
0x180006f2b  mov     rcx, [rsp+98h+var_40]
0x180006f30  xor     rcx, rsp; StackCookie
0x180006f33  call    __security_check_cookie
0x180006f38  add     rsp, 68h
0x180006f3c  pop     r14
0x180006f3e  pop     r12
0x180006f40  pop     rdi
0x180006f41  pop     rsi
0x180006f42  pop     rbp
0x180006f43  pop     rbx
0x180006f44  retn
0x180006f45  test    rsi, rsi
0x180006f48  jz      short loc_180006F5B
0x180006f4a  mov     rax, [rsi]
0x180006f4d  mov     edx, r12d
0x180006f50  mov     rcx, rsi
0x180006f53  mov     rax, [rax]
0x180006f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f5b  cmp     edi, ebp
0x180006f5d  jz      short loc_180006F86
0x180006f5f  test    edi, edi
0x180006f61  jz      short loc_180006F7F
0x180006f63  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006f6a  jz      short loc_180006F7B
0x180006f6c  mov     r9d, edi
0x180006f6f  lea     r8, aCdiagnosticpro_4; "CDiagnosticProvider::EnforceQueryRemote"...
0x180006f76  call    McTemplateU0sq_EventWriteTransfer
0x180006f7b  mov     ebp, edi
0x180006f7d  jmp     short loc_180006F13
0x180006f7f  mov     ebp, edi
0x180006f81  jmp     loc_180006EF7
0x180006f86  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006f8d  jz      short loc_180006F7B
0x180006f8f  mov     r9d, 80070057h
0x180006f95  jmp     short loc_180006F6F
```
