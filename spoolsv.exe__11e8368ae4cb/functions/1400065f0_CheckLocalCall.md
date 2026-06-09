# CheckLocalCall

- ea: `0x1400065f0`
- end: `0x140006859`
- name: `CheckLocalCall`
- size: `617`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400030d0`
- `0x140004890`
- `0x140004e90`
- `0x140005c30`
- `0x140007250`
- `0x140012140`
- `0x14005c9e0`

## callees

- `0x1400065f0`
- `0x140007bdc`
- `0x1400140cc`
- `0x140014fc4`
- `0x14002abc0`
- `0x140057e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000660f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000660f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006663`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006678`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000681f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006663`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006678`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000681f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14000662b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14000662b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000676d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000676d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400066a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400066a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006755`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006803`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x140006638`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x140006638`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140006707`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400067bb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140006707`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400067bb`
- `ADVAPI32!CheckTokenMembership` at `0x140006721`
- `ADVAPI32!CheckTokenMembership` at `0x1400067d1`
- `ADVAPI32!CheckTokenMembership` at `0x140006721`
- `ADVAPI32!CheckTokenMembership` at `0x1400067d1`
- `ADVAPI32!FreeSid` at `0x1400067f0`
- `ADVAPI32!FreeSid` at `0x1400067f0`

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
0x1400065f0  push    rbp
0x1400065f2  push    rbx
0x1400065f3  push    rsi
0x1400065f4  push    rdi
0x1400065f5  lea     rbp, [rsp-3Fh]
0x1400065fa  sub     rsp, 98h
0x140006601  mov     rax, cs:__security_cookie
0x140006608  xor     rax, rsp
0x14000660b  mov     [rbp+57h+var_28], rax
0x14000660f  call    cs:__imp_GetLastError
0x140006615  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000661b  xor     esi, esi
0x14000661d  mov     [rbp+57h+Type], esi
0x140006620  mov     edi, eax
0x140006622  cmp     ecx, 0FFFFFFFFh
0x140006625  jnz     short loc_14000662B
0x140006627  mov     eax, esi
0x140006629  jmp     short loc_140006631
0x14000662b  call    cs:__imp_TlsGetValue
0x140006631  lea     rdx, [rbp+57h+Type]; Type
0x140006635  mov     rcx, rax; Binding
0x140006638  call    cs:__imp_I_RpcBindingInqTransportType
0x14000663e  mov     ebx, eax
0x140006640  test    eax, eax
0x140006642  jz      short loc_140006670
0x140006644  cmp     eax, 6BDh
0x140006649  jz      short loc_140006661
0x14000664b  test    eax, eax
0x14000664d  jle     loc_14000681D
0x140006653  movzx   ebx, ax
0x140006656  or      ebx, 80070000h
0x14000665c  jmp     loc_14000681D
0x140006661  mov     ecx, edi; dwErrCode
0x140006663  call    cs:__imp_SetLastError
0x140006669  mov     eax, esi
0x14000666b  jmp     loc_140006841
0x140006670  cmp     [rbp+57h+Type], 4
0x140006674  jz      short loc_140006688
0x140006676  mov     ecx, edi; dwErrCode
0x140006678  call    cs:__imp_SetLastError
0x14000667e  mov     eax, 1
0x140006683  jmp     loc_140006841
0x140006688  mov     [rbp+57h+TokenHandle], rsi
0x14000668c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140006693  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140006698  test    al, al
0x14000669a  jz      loc_140006755
0x1400066a0  call    cs:__imp_GetCurrentThread
0x1400066a6  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1400066aa  mov     edx, 8; DesiredAccess
0x1400066af  mov     rcx, rax; ThreadHandle
0x1400066b2  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x1400066b7  test    eax, eax
0x1400066b9  jle     short loc_1400066C5
0x1400066bb  movzx   eax, ax
0x1400066be  or      eax, 80070000h
0x1400066c3  test    eax, eax
0x1400066c5  js      short loc_14000673C
0x1400066c7  lea     rax, [rbp+57h+SidToCheck]
0x1400066cb  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1400066ce  mov     [rsp+0B0h+pSid], rax; pSid
0x1400066d3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400066d7  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x1400066db  xor     r9d, r9d; nSubAuthority1
0x1400066de  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x1400066e2  mov     r8d, 2; nSubAuthority0
0x1400066e8  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x1400066ec  mov     dl, 1; nSubAuthorityCount
0x1400066ee  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x1400066f2  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x1400066f6  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x1400066fa  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140006700  mov     [rbp+57h+SidToCheck], rsi
0x140006704  mov     [rbp+57h+IsMember], esi
0x140006707  call    cs:__imp_AllocateAndInitializeSid
0x14000670d  test    eax, eax
0x14000670f  jz      loc_1400067F8
0x140006715  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140006719  lea     r8, [rbp+57h+IsMember]; IsMember
0x14000671d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140006721  call    cs:__imp_CheckTokenMembership
0x140006727  test    eax, eax
0x140006729  jz      loc_1400067E5
0x14000672f  cmp     [rbp+57h+IsMember], esi
0x140006732  mov     ebx, esi
0x140006734  setnz   bl
0x140006737  jmp     loc_1400067EC
0x14000673c  call    GetLastErrorAsHResult
0x140006741  mov     ebx, eax
0x140006743  cmp     eax, 800703F0h
0x140006748  jnz     loc_14000681D
0x14000674e  mov     ebx, esi
0x140006750  jmp     loc_14000681D
0x140006755  call    cs:__imp_GetCurrentThread
0x14000675b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14000675f  mov     edx, 8; DesiredAccess
0x140006764  mov     rcx, rax; ThreadHandle
0x140006767  mov     r8d, 1; OpenAsSelf
0x14000676d  call    cs:__imp_OpenThreadToken
0x140006773  test    eax, eax
0x140006775  jz      loc_14000680B
0x14000677b  lea     rax, [rbp+57h+SidToCheck]
0x14000677f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140006782  mov     [rsp+0B0h+pSid], rax; pSid
0x140006787  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000678b  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000678f  xor     r9d, r9d; nSubAuthority1
0x140006792  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x140006796  mov     r8d, 2; nSubAuthority0
0x14000679c  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x1400067a0  mov     dl, 1; nSubAuthorityCount
0x1400067a2  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x1400067a6  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x1400067aa  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x1400067ae  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400067b4  mov     [rbp+57h+SidToCheck], rsi
0x1400067b8  mov     [rbp+57h+IsMember], esi
0x1400067bb  call    cs:__imp_AllocateAndInitializeSid
0x1400067c1  test    eax, eax
0x1400067c3  jz      short loc_1400067F8
0x1400067c5  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1400067c9  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400067cd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400067d1  call    cs:__imp_CheckTokenMembership
0x1400067d7  test    eax, eax
0x1400067d9  jz      short loc_1400067E5
0x1400067db  cmp     [rbp+57h+IsMember], esi
0x1400067de  mov     ebx, esi
0x1400067e0  setnz   bl
0x1400067e3  jmp     short loc_1400067EC
0x1400067e5  call    GetLastErrorAsHResult
0x1400067ea  mov     ebx, eax
0x1400067ec  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1400067f0  call    cs:__imp_FreeSid
0x1400067f6  jmp     short loc_1400067FF
0x1400067f8  call    GetLastErrorAsHResult
0x1400067fd  mov     ebx, eax
0x1400067ff  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x140006803  call    cs:__imp_CloseHandle
0x140006809  jmp     short loc_14000681D
0x14000680b  call    GetLastErrorAsHResult
0x140006810  mov     ebx, eax
0x140006812  cmp     eax, 800703F0h
0x140006817  jz      loc_140006661
0x14000681d  mov     ecx, edi; dwErrCode
0x14000681f  call    cs:__imp_SetLastError
0x140006825  test    ebx, ebx
0x140006827  jns     short loc_14000683F
0x140006829  mov     r8d, ebx
0x14000682c  lea     rdx, aFailedErrorHr0_1; "Failed.  Error hr: 0x%x."
0x140006833  lea     rcx, aChecklocalcall; "CheckLocalCall"
0x14000683a  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000683f  mov     eax, ebx
0x140006841  mov     rcx, [rbp+57h+var_28]
0x140006845  xor     rcx, rsp; StackCookie
0x140006848  call    __security_check_cookie
0x14000684d  add     rsp, 98h
0x140006854  pop     rdi
0x140006855  pop     rsi
0x140006856  pop     rbx
0x140006857  pop     rbp
0x140006858  retn
```
