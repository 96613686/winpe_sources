# DiagnosticProviderWorkerThread(void *)

- ea: `0x180008220`
- end: `0x1800083e5`
- name: `?DiagnosticProviderWorkerThread@@YAKPEAX@Z`
- size: `453`
- prototype: `__int64 __fastcall(char *Parameter, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180008220`
- `0x180019010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800082b4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800082b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082d1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000829f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000829f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000830a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000830a`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x1800082c7`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x1800082c7`

## string_xrefs

- `0x180008342`: `DiagnosticProviderWorkerThread`
- `0x1800083aa`: `DiagnosticProviderWorkerThread`
- `0x1800083c7`: `DiagnosticProviderWorkerThread`

## pseudocode

```c
__int64 __fastcall DiagnosticProviderWorkerThread(char *Parameter, __int64 a2)
{
  unsigned int v3; // ebx
  const char *v4; // rax
  _QWORD *v5; // rsi
  signed int LastError; // eax
  __int64 v7; // r9

  if ( !Parameter )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v4 = "Parameter";
LABEL_36:
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)Parameter,
        a2,
        (unsigned int)"DiagnosticProviderWorkerThread",
        -2147024809,
        (__int64)v4);
      return v3;
    }
    return v3;
  }
  v5 = Parameter + 8;
  if ( *(_QWORD *)Parameter && *v5 && *((_QWORD *)Parameter + 4) && *((_QWORD *)Parameter + 6) )
  {
    v3 = CoInitializeEx(0, 0);
    if ( (v3 & 0x80000000) == 0 )
    {
      EventActivityIdControl(2u, (LPGUID)Parameter + 1);
      if ( SetThreadPreferredUILanguages(8u, *((PCZZWSTR *)Parameter + 4), (PULONG)Parameter + 10) )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)Parameter + 16LL))(
               *(_QWORD *)Parameter,
               *v5,
               *((_QWORD *)Parameter + 6));
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( (v3 & 0x80000000) == 0 )
          v3 = -2147467259;
      }
      CoUninitialize();
    }
    if ( v3 != -2147024809 )
    {
      if ( !v3 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(Parameter, SDIAGPRV_EVENT_DEBUG_SUCCESS, "DiagnosticProviderWorkerThread");
        return v3;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v3;
      v7 = v3;
      goto LABEL_39;
    }
  }
  else
  {
    v3 = -2147024809;
  }
  if ( *(_QWORD *)Parameter )
  {
    if ( !*v5 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v4 = "QueryParameter";
        goto LABEL_36;
      }
      return v3;
    }
    if ( !*((_QWORD *)Parameter + 4) )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v4 = "Languages";
        goto LABEL_36;
      }
      return v3;
    }
    if ( !*((_QWORD *)Parameter + 6) )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v4 = "DiagnosticCollection";
        goto LABEL_36;
      }
      return v3;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v3;
    v7 = 2147942487LL;
LABEL_39:
    McTemplateU0sq_EventWriteTransfer(Parameter, a2, "DiagnosticProviderWorkerThread", v7);
    return v3;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v4 = "DiagnosticProviderImpl";
    goto LABEL_36;
  }
  return v3;
}

```

## disassembly

```asm
0x180008220  mov     [rsp+arg_0], rbx
0x180008225  mov     [rsp+arg_8], rsi
0x18000822a  push    rdi
0x18000822b  sub     rsp, 30h
0x18000822f  mov     rdi, rcx
0x180008232  test    rcx, rcx
0x180008235  jnz     short loc_180008255
0x180008237  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000823e  mov     ebx, 80070057h
0x180008243  jz      loc_1800083D3
0x180008249  lea     rax, aParameter; "Parameter"
0x180008250  jmp     loc_18000839F
0x180008255  cmp     qword ptr [rcx], 0
0x180008259  lea     rsi, [rcx+8]
0x18000825d  jnz     short loc_180008287
0x18000825f  mov     ebx, 80070057h
0x180008264  cmp     qword ptr [rdi], 0
0x180008268  jnz     loc_180008357
0x18000826e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008275  jz      loc_1800083D3
0x18000827b  lea     rax, aDiagnosticprov; "DiagnosticProviderImpl"
0x180008282  jmp     loc_18000839F
0x180008287  cmp     qword ptr [rsi], 0
0x18000828b  jz      short loc_18000825F
0x18000828d  cmp     qword ptr [rcx+20h], 0
0x180008292  jz      short loc_18000825F
0x180008294  cmp     qword ptr [rcx+30h], 0
0x180008299  jz      short loc_18000825F
0x18000829b  xor     edx, edx; dwCoInit
0x18000829d  xor     ecx, ecx; pvReserved
0x18000829f  call    cs:__imp_CoInitializeEx
0x1800082a5  mov     ebx, eax
0x1800082a7  test    eax, eax
0x1800082a9  js      short loc_180008310
0x1800082ab  lea     rdx, [rdi+10h]; ActivityId
0x1800082af  mov     ecx, 2; ControlCode
0x1800082b4  call    cs:__imp_EventActivityIdControl
0x1800082ba  mov     rdx, [rdi+20h]; pwszLanguagesBuffer
0x1800082be  lea     r8, [rdi+28h]; pulNumLanguages
0x1800082c2  mov     ecx, 8; dwFlags
0x1800082c7  call    cs:__imp_SetThreadPreferredUILanguages
0x1800082cd  test    eax, eax
0x1800082cf  jnz     short loc_1800082F2
0x1800082d1  call    cs:__imp_GetLastError
0x1800082d7  mov     ebx, eax
0x1800082d9  test    eax, eax
0x1800082db  jle     short loc_1800082E6
0x1800082dd  movzx   ebx, ax
0x1800082e0  or      ebx, 80070000h
0x1800082e6  test    ebx, ebx
0x1800082e8  mov     eax, 80004005h
0x1800082ed  cmovns  ebx, eax
0x1800082f0  jmp     short loc_18000830A
0x1800082f2  mov     rcx, [rdi]
0x1800082f5  mov     r8, [rdi+30h]
0x1800082f9  mov     rdx, [rsi]
0x1800082fc  mov     rax, [rcx]
0x1800082ff  mov     rax, [rax+10h]
0x180008303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008308  mov     ebx, eax
0x18000830a  call    cs:__imp_CoUninitialize
0x180008310  cmp     ebx, 80070057h
0x180008316  jz      loc_180008264
0x18000831c  test    ebx, ebx
0x18000831e  jz      short loc_180008335
0x180008320  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008327  jz      loc_1800083D3
0x18000832d  mov     r9d, ebx
0x180008330  jmp     loc_1800083C7
0x180008335  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000833c  jz      loc_1800083D3
0x180008342  lea     r8, aDiagnosticprov_0; "DiagnosticProviderWorkerThread"
0x180008349  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180008350  call    McTemplateU0s_EventWriteTransfer
0x180008355  jmp     short loc_1800083D3
0x180008357  cmp     qword ptr [rsi], 0
0x18000835b  jnz     short loc_18000836F
0x18000835d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008364  jz      short loc_1800083D3
0x180008366  lea     rax, aQueryparameter; "QueryParameter"
0x18000836d  jmp     short loc_18000839F
0x18000836f  cmp     qword ptr [rdi+20h], 0
0x180008374  jnz     short loc_180008388
0x180008376  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000837d  jz      short loc_1800083D3
0x18000837f  lea     rax, aLanguages; "Languages"
0x180008386  jmp     short loc_18000839F
0x180008388  cmp     qword ptr [rdi+30h], 0
0x18000838d  jnz     short loc_1800083B8
0x18000838f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008396  jz      short loc_1800083D3
0x180008398  lea     rax, aDiagnosticcoll; "DiagnosticCollection"
0x18000839f  mov     r9d, 80070057h
0x1800083a5  mov     [rsp+38h+var_18], rax
0x1800083aa  lea     r8, aDiagnosticprov_0; "DiagnosticProviderWorkerThread"
0x1800083b1  call    McTemplateU0sqs_EventWriteTransfer
0x1800083b6  jmp     short loc_1800083D3
0x1800083b8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800083bf  jz      short loc_1800083D3
0x1800083c1  mov     r9d, 80070057h
0x1800083c7  lea     r8, aDiagnosticprov_0; "DiagnosticProviderWorkerThread"
0x1800083ce  call    McTemplateU0sq_EventWriteTransfer
0x1800083d3  mov     rsi, [rsp+38h+arg_8]
0x1800083d8  mov     eax, ebx
0x1800083da  mov     rbx, [rsp+38h+arg_0]
0x1800083df  add     rsp, 30h
0x1800083e3  pop     rdi
0x1800083e4  retn
```
