# CHangrepServer::IsCrashReportingInProgress(ulong,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180024784`
- end: `0x1800248ec`
- name: `?IsCrashReportingInProgress@CHangrepServer@@CAHKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(DWORD dwProcessId, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800248f4`

## callees

- `0x1800029d0`
- `0x180006134`
- `0x180006aa8`
- `0x180007cf8`
- `0x180013df4`
- `0x180024784`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800247f1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800247f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800247e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800247e4`
- `ntdll!RtlInitUnicodeString` at `0x180024860`
- `ntdll!RtlInitUnicodeString` at `0x180024860`
- `ntdll!NtOpenEvent` at `0x1800248a7`
- `ntdll!NtOpenEvent` at `0x1800248a7`

## string_xrefs

- `0x180024804`: `\Sessions\BNOLINKS\%ld\WERReportingForProcessComplete%u`

## pseudocode

```c
__int64 __fastcall CHangrepServer::IsCrashReportingInProgress(DWORD dwProcessId, void **a2)
{
  void *v3; // rcx
  void **v5; // rax
  __int64 v6; // rcx
  DWORD pSessionId; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SourceString[72]; // [rsp+80h] [rbp-80h] BYREF

  pSessionId = 0;
  v3 = *a2;
  DestinationString = 0;
  *a2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  if ( !ProcessIdToSessionId(dwProcessId, &pSessionId)
    || (int)StringCchPrintfW(
              SourceString,
              0x48u,
              L"\\Sessions\\BNOLINKS\\%ld\\WERReportingForProcessComplete%u",
              pSessionId,
              dwProcessId) < 0 )
  {
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, SourceString);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 0;
  v5 = tlx::replace<tlx::file_handle_traits>(a2);
  if ( NtOpenEvent(v5, 0x100000u, &ObjectAttributes) < 0 )
    return 0;
  v6 = (__int64)*a2 + 1;
  if ( *a2 == (void *)-1LL || v6 == 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  return 1;
}

```

## disassembly

```asm
0x180024784  mov     [rsp-8+arg_10], rbx
0x180024789  mov     [rsp-8+arg_18], rdi
0x18002478e  push    rbp
0x18002478f  lea     rbp, [rsp-20h]
0x180024794  sub     rsp, 120h
0x18002479b  mov     rax, cs:__security_cookie
0x1800247a2  xor     rax, rsp
0x1800247a5  mov     [rbp+20h+var_10], rax
0x1800247a9  xorps   xmm1, xmm1
0x1800247ac  mov     [rsp+120h+pSessionId], 0
0x1800247b4  mov     edi, ecx
0x1800247b6  xorps   xmm0, xmm0
0x1800247b9  mov     rcx, [rdx]; hObject
0x1800247bc  mov     rbx, rdx
0x1800247bf  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1800247c4  mov     qword ptr [rdx], 0
0x1800247cb  movups  xmmword ptr [rsp+120h+ObjectAttributes.Length], xmm1
0x1800247d0  lea     rax, [rcx+1]
0x1800247d4  movups  xmmword ptr [rsp+120h+ObjectAttributes.ObjectName], xmm1
0x1800247d9  movups  xmmword ptr [rsp+120h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800247de  cmp     rax, 1
0x1800247e2  jbe     short loc_1800247EA
0x1800247e4  call    cs:__imp_CloseHandle
0x1800247ea  lea     rdx, [rsp+120h+pSessionId]; pSessionId
0x1800247ef  mov     ecx, edi; dwProcessId
0x1800247f1  call    cs:__imp_ProcessIdToSessionId
0x1800247f7  test    eax, eax
0x1800247f9  jz      loc_1800248C9
0x1800247ff  mov     r9d, [rsp+120h+pSessionId]
0x180024804  lea     r8, aSessionsBnolin; "\\Sessions\\BNOLINKS\\%ld\\WERReporting"...
0x18002480b  mov     edx, 48h ; 'H'; unsigned __int64
0x180024810  mov     [rsp+120h+var_100], edi
0x180024814  lea     rcx, [rbp+20h+SourceString]; wchar_t *
0x180024818  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002481d  test    eax, eax
0x18002481f  js      loc_1800248C9
0x180024825  mov     rcx, cs:WPP_GLOBAL_Control
0x18002482c  lea     rax, WPP_GLOBAL_Control
0x180024833  cmp     rcx, rax
0x180024836  jz      short loc_180024857
0x180024838  test    byte ptr [rcx+1Ch], 8
0x18002483c  jz      short loc_180024857
0x18002483e  mov     rcx, [rcx+10h]
0x180024842  lea     r9, [rbp+20h+SourceString]
0x180024846  mov     edx, 2Bh ; '+'
0x18002484b  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180024852  call    WPP_SF_S
0x180024857  lea     rdx, [rbp+20h+SourceString]; SourceString
0x18002485b  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180024860  call    cs:__imp_RtlInitUnicodeString
0x180024866  lea     rax, [rsp+120h+DestinationString]
0x18002486b  mov     [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x180024873  xorps   xmm0, xmm0
0x180024876  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x18002487b  mov     rcx, rbx
0x18002487e  mov     [rsp+120h+ObjectAttributes.RootDirectory], 0
0x180024887  movdqu  xmmword ptr [rsp+120h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002488d  mov     [rsp+120h+ObjectAttributes.Attributes], 0
0x180024895  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002489a  mov     rcx, rax; EventHandle
0x18002489d  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x1800248a2  mov     edx, 100000h; DesiredAccess
0x1800248a7  call    cs:__imp_NtOpenEvent
0x1800248ad  test    eax, eax
0x1800248af  js      short loc_1800248C9
0x1800248b1  mov     rcx, [rbx]
0x1800248b4  inc     rcx
0x1800248b7  cmp     rcx, 1
0x1800248bb  ja      short loc_1800248C2
0x1800248bd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800248c2  mov     eax, 1
0x1800248c7  jmp     short loc_1800248CB
0x1800248c9  xor     eax, eax
0x1800248cb  mov     rcx, [rbp+20h+var_10]
0x1800248cf  xor     rcx, rsp; StackCookie
0x1800248d2  call    __security_check_cookie
0x1800248d7  lea     r11, [rsp+120h+var_s0]
0x1800248df  mov     rbx, [r11+20h]
0x1800248e3  mov     rdi, [r11+28h]
0x1800248e7  mov     rsp, r11
0x1800248ea  pop     rbp
0x1800248eb  retn
```
