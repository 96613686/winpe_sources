# CDiagnosticProvider::Cancel(void)

- ea: `0x1800067c0`
- end: `0x180006948`
- name: `?Cancel@CDiagnosticProvider@@UEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(CDiagnosticProvider *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000247c`
- `0x1800067c0`
- `0x1800077bc`
- `0x180007c88`
- `0x1800180f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800067f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000687a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006921`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800067f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000687a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006921`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006818`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006818`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006887`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006891`
- `RPCRT4!UuidCreate` at `0x18000685d`
- `RPCRT4!UuidCreate` at `0x18000685d`

## pseudocode

```c
__int64 __fastcall CDiagnosticProvider::Cancel(CDiagnosticProvider *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  UUID *v6; // rcx
  __int64 v7; // rcx
  signed int LastError; // eax
  __int64 v9; // r8
  GUID ActivityId; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-28h] BYREF

  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( !*((_DWORD *)this + 23) )
  {
    v3 = -2147467259;
LABEL_19:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v2, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_CANCEL_FAIL, v3);
    goto LABEL_23;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CANCEL_START, v5, 1, v12);
  if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)((char *)this + 184), &GUID_NULL) )
    UuidCreate(v6);
  if ( !(unsigned int)InlineIsEqualGUID((const struct _GUID *)((char *)this + 184), &ActivityId) )
    EventActivityIdControl(2u, (LPGUID)((char *)this + 184));
  if ( SetEvent(*((HANDLE *)this + 22)) )
  {
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v3 = LastError;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x40) != 0 )
    McTemplateU0q_EventWriteTransfer(v7, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CANCEL_END, v3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( v3 )
    goto LABEL_19;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_CANCEL_SUCCESS, v9, 1, v12);
LABEL_23:
  EventActivityIdControl(2u, &ActivityId);
  return v3;
}

```

## disassembly

```asm
0x1800067c0  mov     [rsp+arg_8], rbx
0x1800067c5  mov     [rsp+arg_10], rsi
0x1800067ca  push    rdi
0x1800067cb  sub     rsp, 60h
0x1800067cf  mov     rax, cs:__security_cookie
0x1800067d6  xor     rax, rsp
0x1800067d9  mov     [rsp+68h+var_18], rax
0x1800067de  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800067e5  mov     rdi, rcx
0x1800067e8  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x1800067ed  mov     ecx, 1; ControlCode
0x1800067f2  movdqu  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x1800067f8  call    cs:__imp_EventActivityIdControl
0x1800067fe  cmp     dword ptr [rdi+5Ch], 0
0x180006802  jnz     short loc_18000680E
0x180006804  mov     ebx, 80004005h
0x180006809  jmp     loc_1800068D8
0x18000680e  lea     rsi, [rdi+88h]
0x180006815  mov     rcx, rsi; lpCriticalSection
0x180006818  call    cs:__imp_EnterCriticalSection
0x18000681e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 40h
0x180006825  jz      short loc_180006843
0x180006827  lea     rax, [rsp+68h+var_28]
0x18000682c  mov     r9d, 1
0x180006832  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CANCEL_START
0x180006839  mov     [rsp+68h+var_48], rax
0x18000683e  call    McGenEventWrite_EventWriteTransfer
0x180006843  lea     rbx, [rdi+0B8h]
0x18000684a  mov     rcx, rbx; struct _GUID *
0x18000684d  lea     rdx, GUID_NULL; struct _GUID *
0x180006854  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180006859  test    eax, eax
0x18000685b  jz      short loc_180006863
0x18000685d  call    cs:__imp_UuidCreate
0x180006863  lea     rdx, [rsp+68h+ActivityId]; struct _GUID *
0x180006868  mov     rcx, rbx; struct _GUID *
0x18000686b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180006870  test    eax, eax
0x180006872  jnz     short loc_180006880
0x180006874  mov     rdx, rbx; ActivityId
0x180006877  lea     ecx, [rax+2]; ControlCode
0x18000687a  call    cs:__imp_EventActivityIdControl
0x180006880  mov     rcx, [rdi+0B0h]; hEvent
0x180006887  call    cs:__imp_SetEvent
0x18000688d  test    eax, eax
0x18000688f  jnz     short loc_1800068B1
0x180006891  call    cs:__imp_GetLastError
0x180006897  test    eax, eax
0x180006899  jle     short loc_1800068A3
0x18000689b  movzx   eax, ax
0x18000689e  or      eax, 80070000h
0x1800068a3  mov     ebx, 80004005h
0x1800068a8  test    eax, eax
0x1800068aa  cmovns  eax, ebx
0x1800068ad  mov     ebx, eax
0x1800068af  jmp     short loc_1800068B3
0x1800068b1  xor     ebx, ebx
0x1800068b3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 40h
0x1800068ba  jz      short loc_1800068CB
0x1800068bc  mov     r8d, ebx
0x1800068bf  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_CANCEL_END
0x1800068c6  call    McTemplateU0q_EventWriteTransfer
0x1800068cb  mov     rcx, rsi; lpCriticalSection
0x1800068ce  call    cs:__imp_LeaveCriticalSection
0x1800068d4  test    ebx, ebx
0x1800068d6  jz      short loc_1800068F2
0x1800068d8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 2
0x1800068df  jz      short loc_180006917
0x1800068e1  mov     r8d, ebx
0x1800068e4  lea     rdx, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_CANCEL_FAIL
0x1800068eb  call    McTemplateU0q_EventWriteTransfer
0x1800068f0  jmp     short loc_180006917
0x1800068f2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 1
0x1800068f9  jz      short loc_180006917
0x1800068fb  lea     rax, [rsp+68h+var_28]
0x180006900  mov     r9d, 1
0x180006906  lea     rdx, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_CANCEL_SUCCESS
0x18000690d  mov     [rsp+68h+var_48], rax
0x180006912  call    McGenEventWrite_EventWriteTransfer
0x180006917  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x18000691c  mov     ecx, 2; ControlCode
0x180006921  call    cs:__imp_EventActivityIdControl
0x180006927  mov     eax, ebx
0x180006929  mov     rcx, [rsp+68h+var_18]
0x18000692e  xor     rcx, rsp; StackCookie
0x180006931  call    __security_check_cookie
0x180006936  lea     r11, [rsp+68h+var_8]
0x18000693b  mov     rbx, [r11+18h]
0x18000693f  mov     rsi, [r11+20h]
0x180006943  mov     rsp, r11
0x180006946  pop     rdi
0x180006947  retn
```
