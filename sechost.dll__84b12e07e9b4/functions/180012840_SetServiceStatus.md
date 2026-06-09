# SetServiceStatus

- ea: `0x180012840`
- end: `0x180012b00`
- name: `SetServiceStatus`
- size: `704`
- prototype: `BOOL __stdcall(SERVICE_STATUS_HANDLE hServiceStatus, LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b460`
- `0x180012840`
- `0x180015350`
- `0x180017584`
- `0x180018dd8`
- `0x18004abac`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180012a02`
- `ntdll!RtlNtStatusToDosError` at `0x180012a2a`
- `ntdll!RtlNtStatusToDosError` at `0x180012a02`
- `ntdll!RtlNtStatusToDosError` at `0x180012a2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800129c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ae6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800129c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012aa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012aa4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenGroups` at `0x180012a77`
- `api-ms-win-security-base-l1-1-0!AdjustTokenGroups` at `0x180012a77`
- `RPCRT4!NdrClientCall2` at `0x1800128d0`
- `RPCRT4!NdrClientCall2` at `0x1800128d0`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004ffae`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004ffae`

## pseudocode

```c
BOOL __stdcall SetServiceStatus(SERVICE_STATUS_HANDLE hServiceStatus, LPSERVICE_STATUS lpServiceStatus)
{
  int v4; // esi
  char *v5; // r12
  __int64 v6; // r13
  DWORD dwCurrentState; // r14d
  CLIENT_CALL_RETURN v8; // rax
  DWORD Pointer; // ebx
  char *i; // rax
  void *v12; // rcx
  DWORD v13; // r15d
  __int64 j; // r12
  NTSTATUS ServiceSidFromString; // eax
  const WCHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  HLOCAL v19; // rcx
  char *v20; // [rsp+38h] [rbp-90h]
  HLOCAL hMem[2]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v22; // [rsp+58h] [rbp-70h]
  SERVICE_STATUS_HANDLE v23; // [rsp+60h] [rbp-68h]
  _TOKEN_GROUPS NewState; // [rsp+68h] [rbp-60h] BYREF
  __int128 v25; // [rsp+80h] [rbp-48h]

  v23 = hServiceStatus;
  v4 = 0;
  if ( !hServiceStatus )
  {
    SetLastError(6u);
    return 0;
  }
  v5 = 0;
  v20 = 0;
  v6 = 0;
  v22 = 0;
  dwCurrentState = lpServiceStatus->dwCurrentState;
  if ( dwCurrentState == 1 )
  {
    for ( i = (char *)::hMem + 8; *((_QWORD *)i + 1); i += 96 )
    {
      if ( *((SERVICE_STATUS_HANDLE *)i + 6) == hServiceStatus )
      {
        *((_QWORD *)i + 6) = 0;
        v5 = i;
        v20 = i;
        v6 = _InterlockedExchange64((volatile __int64 *)i + 5, 0);
        v22 = v6;
        v12 = (void *)_InterlockedExchange64((volatile __int64 *)i + 10, 0);
        if ( v12 )
          CloseHandle(v12);
        break;
      }
    }
    *(_OWORD *)hMem = 0;
    v13 = 0;
    memset(&NewState, 0, sizeof(NewState));
    v25 = 0;
    if ( !TokenHandle || !v5 || (v5[56] & 8) == 0 )
      goto LABEL_15;
    ServiceSidFromString = ScCreateServiceSidFromString(*((PCWSTR *)v5 + 2), hMem);
    if ( ServiceSidFromString < 0 )
      goto LABEL_22;
    v13 = 1;
    v16 = (const WCHAR *)*((_QWORD *)v5 + 3);
    if ( v16 )
    {
      ServiceSidFromString = ScCreateServiceSidFromString(v16, &hMem[1]);
      if ( ServiceSidFromString < 0 )
      {
LABEL_22:
        RtlNtStatusToDosError(ServiceSidFromString);
LABEL_15:
        for ( j = 0; (unsigned int)j < v13; j = (unsigned int)(j + 1) )
        {
          v19 = hMem[j];
          if ( v19 )
            LocalFree(v19);
        }
        v5 = v20;
        goto LABEL_5;
      }
      v13 = 2;
    }
    NewState.GroupCount = v13;
    v17 = 0;
    do
    {
      v18 = (unsigned int)v17;
      NewState.Groups[v18].Sid = hMem[v17];
      NewState.Groups[v18].Attributes = 0;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < v13 );
    if ( AdjustTokenGroups(TokenHandle, 0, &NewState, 0, 0, 0) )
      v4 = 1;
    else
      GetLastError();
    goto LABEL_15;
  }
  if ( dwCurrentState == 4 )
    ScAdjustServiceMainThreadPriority((struct SC_HANDLE__ *)hServiceStatus);
LABEL_5:
  hMem[0] = 0;
  v8.Pointer = NdrClientCall2(&pStubDescriptor, &byte_180060118, hServiceStatus, lpServiceStatus).Pointer;
  Pointer = (DWORD)v8.Pointer;
  hMem[0] = v8.Pointer;
  if ( LODWORD(v8.Pointer) )
  {
    if ( v5 )
    {
      *((_QWORD *)v5 + 6) = hServiceStatus;
      _InterlockedExchange64((volatile __int64 *)v5 + 5, v6);
    }
    if ( v4 )
      ScAdjustSidState((struct _INTERNAL_DISPATCH_ENTRY *)v5, 1, 0);
    SetLastError(Pointer);
    return 0;
  }
  else
  {
    if ( dwCurrentState == 1 )
      CloseServiceHandle((SC_HANDLE)hServiceStatus);
    return 1;
  }
}

```

## disassembly

```asm
0x180012840  mov     [rsp+arg_10], rbx
0x180012845  mov     [rsp+arg_18], rsi
0x18001284a  push    rdi
0x18001284b  push    r12
0x18001284d  push    r13
0x18001284f  push    r14
0x180012851  push    r15
0x180012853  sub     rsp, 0A0h
0x18001285a  mov     rax, cs:__security_cookie
0x180012861  xor     rax, rsp
0x180012864  mov     [rsp+0C8h+var_38], rax
0x18001286c  mov     rbx, rdx
0x18001286f  mov     rdi, rcx
0x180012872  mov     [rsp+0C8h+var_68], rcx
0x180012877  xor     esi, esi
0x180012879  mov     [rsp+0C8h+var_98], esi
0x18001287d  test    rcx, rcx
0x180012880  jz      loc_1800129C0
0x180012886  xor     r12d, r12d
0x180012889  mov     [rsp+0C8h+var_90], r12
0x18001288e  xor     r13d, r13d
0x180012891  mov     [rsp+0C8h+var_70], r13
0x180012896  mov     r14d, [rdx+4]
0x18001289a  mov     [rsp+0C8h+var_84], r14d
0x18001289f  cmp     r14d, 1
0x1800128a3  jz      loc_18001294D
0x1800128a9  cmp     r14d, 4
0x1800128ad  jz      loc_180012AB7
0x1800128b3  mov     [rsp+0C8h+hMem], 0
0x1800128bc  mov     r9, rbx
0x1800128bf  mov     r8, rdi
0x1800128c2  lea     rdx, byte_180060118; pFormat
0x1800128c9  lea     rcx, pStubDescriptor; pStubDescriptor
0x1800128d0  call    cs:__imp_NdrClientCall2
0x1800128d6  mov     rbx, rax
0x1800128d9  mov     [rsp+0C8h+hMem], rax
0x1800128de  mov     [rsp+0C8h+var_88], eax
0x1800128e2  jmp     short loc_180012909
0x1800128e4  mov     ecx, eax; unsigned int
0x1800128e6  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800128eb  mov     ebx, eax
0x1800128ed  mov     [rsp+0C8h+var_88], eax
0x1800128f1  mov     r13, [rsp+0C8h+var_70]
0x1800128f6  mov     esi, [rsp+0C8h+var_98]
0x1800128fa  mov     r14d, [rsp+0C8h+var_84]
0x1800128ff  mov     rdi, [rsp+0C8h+var_68]
0x180012904  mov     r12, [rsp+0C8h+var_90]
0x180012909  test    ebx, ebx
0x18001290b  jnz     loc_180012AC1
0x180012911  cmp     r14d, 1
0x180012915  jz      loc_180012AF3
0x18001291b  mov     eax, 1
0x180012920  mov     rcx, [rsp+0C8h+var_38]
0x180012928  xor     rcx, rsp; StackCookie
0x18001292b  call    __security_check_cookie
0x180012930  lea     r11, [rsp+0C8h+var_28]
0x180012938  mov     rbx, [r11+40h]
0x18001293c  mov     rsi, [r11+48h]
0x180012940  mov     rsp, r11
0x180012943  pop     r15
0x180012945  pop     r14
0x180012947  pop     r13
0x180012949  pop     r12
0x18001294b  pop     rdi
0x18001294c  retn
0x18001294d  mov     rax, cs:hMem
0x180012954  add     rax, 8
0x180012958  cmp     [rax+8], rsi
0x18001295c  jz      short loc_180012984
0x18001295e  cmp     [rax+30h], rdi
0x180012962  jnz     short loc_1800129D2
0x180012964  mov     [rax+30h], rsi
0x180012968  mov     r12, rax
0x18001296b  mov     [rsp+0C8h+var_90], rax
0x180012970  xchg    r13, [rax+28h]
0x180012974  mov     [rsp+0C8h+var_70], r13
0x180012979  xor     ecx, ecx
0x18001297b  xchg    rcx, [rax+50h]; hObject
0x18001297f  test    rcx, rcx
0x180012982  jnz     short loc_1800129D8
0x180012984  xorps   xmm0, xmm0
0x180012987  movups  xmmword ptr [rsp+0C8h+hMem], xmm0
0x18001298c  xor     r15d, r15d
0x18001298f  mov     qword ptr [rsp+0C8h+NewState.GroupCount], rsi
0x180012994  movups  xmmword ptr [rsp+0C8h+NewState.Groups.Sid], xmm0
0x180012999  movups  [rsp+0C8h+var_48], xmm0
0x1800129a1  cmp     cs:TokenHandle, rsi
0x1800129a8  jnz     short loc_1800129E0
0x1800129aa  xor     r12d, r12d
0x1800129ad  test    r15d, r15d
0x1800129b0  jnz     loc_180012A9A
0x1800129b6  mov     r12, [rsp+0C8h+var_90]
0x1800129bb  jmp     loc_1800128B3
0x1800129c0  mov     ecx, 6; dwErrCode
0x1800129c5  call    cs:__imp_SetLastError
0x1800129cb  xor     eax, eax
0x1800129cd  jmp     loc_180012920
0x1800129d2  add     rax, 60h ; '`'
0x1800129d6  jmp     short loc_180012958
0x1800129d8  call    cs:__imp_CloseHandle
0x1800129de  jmp     short loc_180012984
0x1800129e0  test    r12, r12
0x1800129e3  jz      short loc_1800129AA
0x1800129e5  test    byte ptr [r12+38h], 8
0x1800129eb  jz      short loc_1800129AA
0x1800129ed  lea     rdx, [rsp+0C8h+hMem]
0x1800129f2  mov     rcx, [r12+10h]; SourceString
0x1800129f7  call    ScCreateServiceSidFromString
0x1800129fc  test    eax, eax
0x1800129fe  jns     short loc_180012A0A
0x180012a00  mov     ecx, eax; Status
0x180012a02  call    cs:__imp_RtlNtStatusToDosError
0x180012a08  jmp     short loc_1800129AA
0x180012a0a  mov     r15d, 1
0x180012a10  mov     rcx, [r12+18h]; SourceString
0x180012a15  test    rcx, rcx
0x180012a18  jz      short loc_180012A3B
0x180012a1a  lea     rdx, [rsp+0C8h+hMem+8]
0x180012a1f  call    ScCreateServiceSidFromString
0x180012a24  test    eax, eax
0x180012a26  jns     short loc_180012A35
0x180012a28  mov     ecx, eax; Status
0x180012a2a  call    cs:__imp_RtlNtStatusToDosError
0x180012a30  jmp     loc_1800129AA
0x180012a35  mov     r15d, 2
0x180012a3b  mov     [rsp+0C8h+NewState.GroupCount], r15d
0x180012a40  xor     edx, edx
0x180012a42  mov     ecx, edx
0x180012a44  add     rcx, rcx
0x180012a47  mov     rax, [rsp+rdx*8+0C8h+hMem]
0x180012a4c  mov     [rsp+rcx*8+0C8h+NewState.Groups.Sid], rax
0x180012a51  mov     [rsp+rcx*8+0C8h+NewState.Groups.Attributes], esi
0x180012a55  inc     edx
0x180012a57  cmp     edx, r15d
0x180012a5a  jb      short loc_180012A42
0x180012a5c  mov     [rsp+0C8h+ReturnLength], rsi; ReturnLength
0x180012a61  mov     [rsp+0C8h+PreviousState], rsi; PreviousState
0x180012a66  xor     r9d, r9d; BufferLength
0x180012a69  lea     r8, [rsp+0C8h+NewState]; NewState
0x180012a6e  xor     edx, edx; ResetToDefault
0x180012a70  mov     rcx, cs:TokenHandle; TokenHandle
0x180012a77  call    cs:__imp_AdjustTokenGroups
0x180012a7d  test    eax, eax
0x180012a7f  jnz     short loc_180012A8C
0x180012a81  call    cs:__imp_GetLastError
0x180012a87  jmp     loc_1800129AA
0x180012a8c  mov     esi, 1
0x180012a91  mov     [rsp+0C8h+var_98], esi
0x180012a95  jmp     loc_1800129AA
0x180012a9a  mov     rcx, [rsp+r12*8+0C8h+hMem]; hMem
0x180012a9f  test    rcx, rcx
0x180012aa2  jz      short loc_180012AAA
0x180012aa4  call    cs:__imp_LocalFree
0x180012aaa  inc     r12d
0x180012aad  cmp     r12d, r15d
0x180012ab0  jb      short loc_180012A9A
0x180012ab2  jmp     loc_1800129B6
0x180012ab7  call    ?ScAdjustServiceMainThreadPriority@@YAKPEAUSC_HANDLE__@@@Z; ScAdjustServiceMainThreadPriority(SC_HANDLE__ *)
0x180012abc  jmp     loc_1800128B3
0x180012ac1  test    r12, r12
0x180012ac4  jz      short loc_180012AD0
0x180012ac6  mov     [r12+30h], rdi
0x180012acb  xchg    r13, [r12+28h]
0x180012ad0  test    esi, esi
0x180012ad2  jz      short loc_180012AE4
0x180012ad4  xor     r8d, r8d; int *
0x180012ad7  mov     edx, 1; int
0x180012adc  mov     rcx, r12; struct _INTERNAL_DISPATCH_ENTRY *
0x180012adf  call    ?ScAdjustSidState@@YAKPEAU_INTERNAL_DISPATCH_ENTRY@@HPEAH@Z; ScAdjustSidState(_INTERNAL_DISPATCH_ENTRY *,int,int *)
0x180012ae4  mov     ecx, ebx; dwErrCode
0x180012ae6  call    cs:__imp_SetLastError
0x180012aec  xor     eax, eax
0x180012aee  jmp     loc_180012920
0x180012af3  mov     rcx, rdi; hSCObject
0x180012af6  call    CloseServiceHandle
0x180012afb  jmp     loc_18001291B
0x18004ffa0  push    rbp
0x18004ffa2  sub     rsp, 30h
0x18004ffa6  mov     rbp, rdx
0x18004ffa9  mov     rcx, [rcx]
0x18004ffac  mov     ecx, [rcx]; ExceptionCode
0x18004ffae  call    cs:__imp_I_RpcExceptionFilter
0x18004ffb4  nop
0x18004ffb5  add     rsp, 30h
0x18004ffb9  pop     rbp
0x18004ffba  retn
```
