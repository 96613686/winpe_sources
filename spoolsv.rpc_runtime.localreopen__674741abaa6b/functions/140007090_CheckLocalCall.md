# CheckLocalCall

- ea: `0x140007090`
- end: `0x140007358`
- name: `CheckLocalCall`
- size: `712`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003590`
- `0x140004fc0`
- `0x140005630`
- `0x1400065e0`
- `0x140007d80`
- `0x140013360`
- `0x1400625a0`

## callees

- `0x140007090`
- `0x1400087c8`
- `0x140015378`
- `0x140016314`
- `0x14002d0a0`
- `0x14005d4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007115`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007130`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007317`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007115`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007130`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007317`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400070d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400070d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007247`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007247`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000715e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000715e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400072f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400072f5`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1400070e4`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1400070e4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400071cf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000729b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400071cf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000729b`
- `ADVAPI32!CheckTokenMembership` at `0x1400071ef`
- `ADVAPI32!CheckTokenMembership` at `0x1400072b7`
- `ADVAPI32!CheckTokenMembership` at `0x1400071ef`
- `ADVAPI32!CheckTokenMembership` at `0x1400072b7`
- `ADVAPI32!FreeSid` at `0x1400072dc`
- `ADVAPI32!FreeSid` at `0x1400072dc`

## pseudocode

```c
__int64 CheckLocalCall()
{
  DWORD LastError; // edi
  void *Value; // rax
  RPC_STATUS v2; // eax
  int LastErrorAsHResult; // ebx
  HANDLE CurrentThread; // rax
  void **v6; // r9
  int v7; // eax
  bool v8; // sf
  HANDLE v9; // rax
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+Fh] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+17h] BYREF
  unsigned int Type; // [rsp+78h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+7Ch] [rbp+23h] BYREF

  Type = 0;
  LastError = GetLastError();
  if ( gdwTlsBindingHandle == -1 )
    Value = 0;
  else
    Value = TlsGetValue(gdwTlsBindingHandle);
  v2 = I_RpcBindingInqTransportType(Value, &Type);
  LastErrorAsHResult = v2;
  if ( v2 )
  {
    if ( v2 != 1725 )
    {
      if ( v2 > 0 )
        LastErrorAsHResult = (unsigned __int16)v2 | 0x80070000;
      goto LABEL_29;
    }
LABEL_8:
    SetLastError(LastError);
    return 0;
  }
  if ( Type != 4 )
  {
    SetLastError(LastError);
    return 1;
  }
  TokenHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    v7 = SecurityHelper::OpenThreadToken(CurrentThread, 8u, &TokenHandle, v6);
    v8 = v7 < 0;
    if ( v7 > 0 )
      v8 = 1;
    if ( v8 )
    {
      LastErrorAsHResult = GetLastErrorAsHResult();
      if ( LastErrorAsHResult == -2147023888 )
        LastErrorAsHResult = 0;
      goto LABEL_29;
    }
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    SidToCheck = 0;
    IsMember = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        LastErrorAsHResult = IsMember != 0;
LABEL_25:
        FreeSid(SidToCheck);
LABEL_27:
        CloseHandle(TokenHandle);
        goto LABEL_29;
      }
      goto LABEL_24;
    }
    goto LABEL_26;
  }
  v9 = GetCurrentThread();
  if ( OpenThreadToken(v9, 8u, 1, &TokenHandle) )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    SidToCheck = 0;
    IsMember = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        LastErrorAsHResult = IsMember != 0;
        goto LABEL_25;
      }
LABEL_24:
      LastErrorAsHResult = GetLastErrorAsHResult();
      goto LABEL_25;
    }
LABEL_26:
    LastErrorAsHResult = GetLastErrorAsHResult();
    goto LABEL_27;
  }
  LastErrorAsHResult = GetLastErrorAsHResult();
  if ( LastErrorAsHResult == -2147023888 )
    goto LABEL_8;
LABEL_29:
  SetLastError(LastError);
  if ( LastErrorAsHResult < 0 )
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CheckLocalCall",
      L"Failed.  Error hr: 0x%x.",
      (unsigned int)LastErrorAsHResult);
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140007090  push    rbp
0x140007092  push    rbx
0x140007093  push    rsi
0x140007094  push    rdi
0x140007095  lea     rbp, [rsp-3Fh]
0x14000709a  sub     rsp, 98h
0x1400070a1  mov     rax, cs:__security_cookie
0x1400070a8  xor     rax, rsp
0x1400070ab  mov     [rbp+57h+var_28], rax
0x1400070af  call    cs:__imp_GetLastError
0x1400070b6  nop     dword ptr [rax+rax+00h]
0x1400070bb  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400070c1  xor     esi, esi
0x1400070c3  mov     [rbp+57h+Type], esi
0x1400070c6  mov     edi, eax
0x1400070c8  cmp     ecx, 0FFFFFFFFh
0x1400070cb  jnz     short loc_1400070D1
0x1400070cd  mov     eax, esi
0x1400070cf  jmp     short loc_1400070DD
0x1400070d1  call    cs:__imp_TlsGetValue
0x1400070d8  nop     dword ptr [rax+rax+00h]
0x1400070dd  lea     rdx, [rbp+57h+Type]; Type
0x1400070e1  mov     rcx, rax; Binding
0x1400070e4  call    cs:__imp_I_RpcBindingInqTransportType
0x1400070eb  nop     dword ptr [rax+rax+00h]
0x1400070f0  mov     ebx, eax
0x1400070f2  test    eax, eax
0x1400070f4  jz      short loc_140007128
0x1400070f6  cmp     eax, 6BDh
0x1400070fb  jz      short loc_140007113
0x1400070fd  test    eax, eax
0x1400070ff  jle     loc_140007315
0x140007105  movzx   ebx, ax
0x140007108  or      ebx, 80070000h
0x14000710e  jmp     loc_140007315
0x140007113  mov     ecx, edi; dwErrCode
0x140007115  call    cs:__imp_SetLastError
0x14000711c  nop     dword ptr [rax+rax+00h]
0x140007121  mov     eax, esi
0x140007123  jmp     loc_14000733F
0x140007128  cmp     [rbp+57h+Type], 4
0x14000712c  jz      short loc_140007146
0x14000712e  mov     ecx, edi; dwErrCode
0x140007130  call    cs:__imp_SetLastError
0x140007137  nop     dword ptr [rax+rax+00h]
0x14000713c  mov     eax, 1
0x140007141  jmp     loc_14000733F
0x140007146  mov     [rbp+57h+TokenHandle], rsi
0x14000714a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140007151  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140007156  test    al, al
0x140007158  jz      loc_140007229
0x14000715e  call    cs:__imp_GetCurrentThread
0x140007165  nop     dword ptr [rax+rax+00h]
0x14000716a  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14000716e  mov     edx, 8; DesiredAccess
0x140007173  mov     rcx, rax; ThreadHandle
0x140007176  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14000717b  test    eax, eax
0x14000717d  jle     short loc_140007189
0x14000717f  movzx   eax, ax
0x140007182  or      eax, 80070000h
0x140007187  test    eax, eax
0x140007189  js      loc_140007210
0x14000718f  lea     rax, [rbp+57h+SidToCheck]
0x140007193  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140007196  mov     [rsp+0B0h+pSid], rax; pSid
0x14000719b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000719f  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x1400071a3  xor     r9d, r9d; nSubAuthority1
0x1400071a6  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x1400071aa  mov     r8d, 2; nSubAuthority0
0x1400071b0  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x1400071b4  mov     dl, 1; nSubAuthorityCount
0x1400071b6  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x1400071ba  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x1400071be  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x1400071c2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400071c8  mov     [rbp+57h+SidToCheck], rsi
0x1400071cc  mov     [rbp+57h+IsMember], esi
0x1400071cf  call    cs:__imp_AllocateAndInitializeSid
0x1400071d6  nop     dword ptr [rax+rax+00h]
0x1400071db  test    eax, eax
0x1400071dd  jz      loc_1400072EA
0x1400071e3  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1400071e7  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400071eb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400071ef  call    cs:__imp_CheckTokenMembership
0x1400071f6  nop     dword ptr [rax+rax+00h]
0x1400071fb  test    eax, eax
0x1400071fd  jz      loc_1400072D1
0x140007203  cmp     [rbp+57h+IsMember], esi
0x140007206  mov     ebx, esi
0x140007208  setnz   bl
0x14000720b  jmp     loc_1400072D8
0x140007210  call    GetLastErrorAsHResult
0x140007215  mov     ebx, eax
0x140007217  cmp     eax, 800703F0h
0x14000721c  jnz     loc_140007315
0x140007222  mov     ebx, esi
0x140007224  jmp     loc_140007315
0x140007229  call    cs:__imp_GetCurrentThread
0x140007230  nop     dword ptr [rax+rax+00h]
0x140007235  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140007239  mov     edx, 8; DesiredAccess
0x14000723e  mov     rcx, rax; ThreadHandle
0x140007241  mov     r8d, 1; OpenAsSelf
0x140007247  call    cs:__imp_OpenThreadToken
0x14000724e  nop     dword ptr [rax+rax+00h]
0x140007253  test    eax, eax
0x140007255  jz      loc_140007303
0x14000725b  lea     rax, [rbp+57h+SidToCheck]
0x14000725f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140007262  mov     [rsp+0B0h+pSid], rax; pSid
0x140007267  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000726b  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000726f  xor     r9d, r9d; nSubAuthority1
0x140007272  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x140007276  mov     r8d, 2; nSubAuthority0
0x14000727c  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x140007280  mov     dl, 1; nSubAuthorityCount
0x140007282  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x140007286  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x14000728a  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x14000728e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140007294  mov     [rbp+57h+SidToCheck], rsi
0x140007298  mov     [rbp+57h+IsMember], esi
0x14000729b  call    cs:__imp_AllocateAndInitializeSid
0x1400072a2  nop     dword ptr [rax+rax+00h]
0x1400072a7  test    eax, eax
0x1400072a9  jz      short loc_1400072EA
0x1400072ab  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1400072af  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400072b3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400072b7  call    cs:__imp_CheckTokenMembership
0x1400072be  nop     dword ptr [rax+rax+00h]
0x1400072c3  test    eax, eax
0x1400072c5  jz      short loc_1400072D1
0x1400072c7  cmp     [rbp+57h+IsMember], esi
0x1400072ca  mov     ebx, esi
0x1400072cc  setnz   bl
0x1400072cf  jmp     short loc_1400072D8
0x1400072d1  call    GetLastErrorAsHResult
0x1400072d6  mov     ebx, eax
0x1400072d8  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1400072dc  call    cs:__imp_FreeSid
0x1400072e3  nop     dword ptr [rax+rax+00h]
0x1400072e8  jmp     short loc_1400072F1
0x1400072ea  call    GetLastErrorAsHResult
0x1400072ef  mov     ebx, eax
0x1400072f1  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1400072f5  call    cs:__imp_CloseHandle
0x1400072fc  nop     dword ptr [rax+rax+00h]
0x140007301  jmp     short loc_140007315
0x140007303  call    GetLastErrorAsHResult
0x140007308  mov     ebx, eax
0x14000730a  cmp     eax, 800703F0h
0x14000730f  jz      loc_140007113
0x140007315  mov     ecx, edi; dwErrCode
0x140007317  call    cs:__imp_SetLastError
0x14000731e  nop     dword ptr [rax+rax+00h]
0x140007323  test    ebx, ebx
0x140007325  jns     short loc_14000733D
0x140007327  mov     r8d, ebx
0x14000732a  lea     rdx, aFailedErrorHr0_1; "Failed.  Error hr: 0x%x."
0x140007331  lea     rcx, aChecklocalcall; "CheckLocalCall"
0x140007338  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000733d  mov     eax, ebx
0x14000733f  mov     rcx, [rbp+57h+var_28]
0x140007343  xor     rcx, rsp; StackCookie
0x140007346  call    __security_check_cookie
0x14000734b  add     rsp, 98h
0x140007352  pop     rdi
0x140007353  pop     rsi
0x140007354  pop     rbx
0x140007355  pop     rbp
0x140007356  retn
```
