# DuplicateAndSetTokenClaim(void *,ushort const *,_TOKEN_SECURITY_ATTRIBUTE_V1 *,void * *)

- ea: `0x1800cce58`
- end: `0x1800cd053`
- name: `?DuplicateAndSetTokenClaim@@YAJPEAXPEBGPEAU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEAPEAX@Z`
- size: `507`
- prototype: `int(void *, const unsigned __int16 *, struct _TOKEN_SECURITY_ATTRIBUTE_V1 *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cce08`
- `0x1800cd05c`

## callees

- `0x180034260`
- `0x18008172c`
- `0x1800cce58`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800ccf80`
- `ntdll!RtlAcquirePrivilege` at `0x1800ccf80`
- `ntdll!NtSetInformationToken` at `0x1800ccfe5`
- `ntdll!NtSetInformationToken` at `0x1800ccfe5`
- `ntdll!RtlReleasePrivilege` at `0x1800ccff7`
- `ntdll!RtlReleasePrivilege` at `0x1800ccff7`
- `ntdll!NtDuplicateToken` at `0x1800ccec0`
- `ntdll!NtDuplicateToken` at `0x1800ccec0`
- `ntdll!RtlNtStatusToDosError` at `0x1800ccf1b`
- `ntdll!RtlNtStatusToDosError` at `0x1800ccf1b`
- `ntdll!RtlInitUnicodeString` at `0x1800ccf42`
- `ntdll!RtlInitUnicodeString` at `0x1800ccf42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ccf96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ccf96`

## string_xrefs

- `0x1800ccf0d`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x1800ccefe`: `DuplicateAndSetTokenClaim`
- `0x1800cceed`: `NtDuplicateToken failed: %!STATUS!`
- `0x1800cd02a`: `NtSetInformationToken failed: %!STATUS!`
- `0x1800ccfc5`: `RtlAcquirePrivilege failed: %!STATUS!`

## pseudocode

```c
int __fastcall DuplicateAndSetTokenClaim(void *a1, const unsigned __int16 *a2, struct _UNICODE_STRING *a3, void **a4)
{
  int v7; // ebx
  const wchar_t *v8; // rax
  int v9; // r8d
  int result; // eax
  PHANDLE NewTokenHandle; // [rsp+28h] [rbp-50h]
  __int64 Privilege; // [rsp+30h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-40h] BYREF
  PVOID ReturnedState; // [rsp+40h] [rbp-38h] BYREF
  __int128 v15; // [rsp+48h] [rbp-30h] BYREF
  __int128 TokenInformation; // [rsp+58h] [rbp-20h] BYREF
  int v17; // [rsp+C8h] [rbp+50h] BYREF

  *a4 = 0;
  v17 = 4;
  hObject = 0;
  LODWORD(Privilege) = 7;
  ReturnedState = 0;
  v15 = 0;
  TokenInformation = 0;
  v7 = NtDuplicateToken(a1, 0, 0, 0, TokenPrimary, &hObject);
  if ( v7 < 0 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      goto LABEL_7;
    v8 = L"NtDuplicateToken failed: %!STATUS!";
    v9 = 433;
    goto LABEL_6;
  }
  RtlInitUnicodeString(a3, a2);
  LODWORD(a3[1].Buffer) = 1;
  *(_QWORD *)&TokenInformation = &v15;
  LOWORD(v15) = 1;
  *((_QWORD *)&TokenInformation + 1) = &v17;
  DWORD1(v15) = 1;
  *((_QWORD *)&v15 + 1) = a3;
  v7 = RtlAcquirePrivilege((PULONG)&Privilege, 1u, 2u, &ReturnedState);
  if ( v7 < 0 )
  {
    CloseHandle(hObject);
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
      goto LABEL_7;
    v8 = L"RtlAcquirePrivilege failed: %!STATUS!";
    v9 = 461;
    goto LABEL_6;
  }
  v7 = NtSetInformationToken(hObject, TokenSecurityAttributes, &TokenInformation, 0x10u);
  RtlReleasePrivilege(ReturnedState);
  if ( v7 >= 0 )
  {
    *a4 = hObject;
    return 0;
  }
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
  {
    v8 = L"NtSetInformationToken failed: %!STATUS!";
    v9 = 472;
LABEL_6:
    LODWORD(NewTokenHandle) = v7;
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
      (unsigned int)"DuplicateAndSetTokenClaim",
      v9,
      0,
      (__int64)v8,
      NewTokenHandle,
      Privilege);
  }
LABEL_7:
  result = RtlNtStatusToDosError(v7);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800cce58  push    rbp
0x1800cce5a  push    rbx
0x1800cce5b  push    rsi
0x1800cce5c  push    rdi
0x1800cce5d  push    r12
0x1800cce5f  push    r14
0x1800cce61  mov     rbp, rsp
0x1800cce64  sub     rsp, 78h
0x1800cce68  lea     rax, [rbp+hObject]
0x1800cce6c  mov     qword ptr [r9], 0
0x1800cce73  mov     rdi, r9
0x1800cce76  mov     [rsp+78h+NewTokenHandle], rax; NewTokenHandle
0x1800cce7b  mov     rsi, r8
0x1800cce7e  mov     [rbp+arg_18], 4
0x1800cce85  mov     r14, rdx
0x1800cce88  mov     [rbp+hObject], 0
0x1800cce90  xorps   xmm0, xmm0
0x1800cce93  mov     dword ptr [rbp+Privilege], 7
0x1800cce9a  xorps   xmm1, xmm1
0x1800cce9d  mov     [rbp+ReturnedState], 0
0x1800ccea5  mov     r12d, 1
0x1800cceab  xor     r9d, r9d; EffectiveOnly
0x1800cceae  xor     r8d, r8d; ObjectAttributes
0x1800cceb1  mov     [rsp+78h+TokenType], r12d; TokenType
0x1800cceb6  xor     edx, edx; DesiredAccess
0x1800cceb8  movups  [rbp+var_30], xmm0
0x1800ccebc  movups  [rbp+TokenInformation], xmm1
0x1800ccec0  call    cs:__imp_NtDuplicateToken
0x1800ccec7  nop     dword ptr [rax+rax+00h]
0x1800ccecc  mov     ebx, eax
0x1800ccece  test    eax, eax
0x1800cced0  jns     short loc_1800CCF3C
0x1800cced2  mov     ecx, cs:dword_1801574B8
0x1800cced8  test    ecx, ecx
0x1800cceda  jnz     short loc_1800CCEED
0x1800ccedc  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800ccee2  jz      short loc_1800CCF19
0x1800ccee4  call    IsWppLevelEnabled
0x1800ccee9  test    al, al
0x1800cceeb  jz      short loc_1800CCF19
0x1800cceed  lea     rax, aNtduplicatetok; "NtDuplicateToken failed: %!STATUS!"
0x1800ccef4  mov     r8d, 1B1h
0x1800ccefa  mov     dword ptr [rsp+78h+NewTokenHandle], ebx
0x1800ccefe  lea     rdx, aDuplicateandse; "DuplicateAndSetTokenClaim"
0x1800ccf05  xor     r9d, r9d
0x1800ccf08  mov     qword ptr [rsp+78h+TokenType], rax
0x1800ccf0d  lea     rcx, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x1800ccf14  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800ccf19  mov     ecx, ebx; Status
0x1800ccf1b  call    cs:__imp_RtlNtStatusToDosError
0x1800ccf22  nop     dword ptr [rax+rax+00h]
0x1800ccf27  test    eax, eax
0x1800ccf29  jle     loc_1800CD045
0x1800ccf2f  movzx   eax, ax
0x1800ccf32  or      eax, 80070000h
0x1800ccf37  jmp     loc_1800CD045
0x1800ccf3c  mov     rdx, r14; SourceString
0x1800ccf3f  mov     rcx, rsi; DestinationString
0x1800ccf42  call    cs:__imp_RtlInitUnicodeString
0x1800ccf49  nop     dword ptr [rax+rax+00h]
0x1800ccf4e  lea     rax, [rbp+var_30]
0x1800ccf52  mov     [rsi+18h], r12d
0x1800ccf56  mov     qword ptr [rbp+TokenInformation], rax
0x1800ccf5a  lea     r9, [rbp+ReturnedState]; ReturnedState
0x1800ccf5e  lea     rax, [rbp+arg_18]
0x1800ccf62  mov     word ptr [rbp+var_30], r12w
0x1800ccf67  mov     r8d, 2; Flags
0x1800ccf6d  mov     qword ptr [rbp+TokenInformation+8], rax
0x1800ccf71  mov     edx, r12d; NumPriv
0x1800ccf74  mov     dword ptr [rbp+var_30+4], r12d
0x1800ccf78  lea     rcx, [rbp+Privilege]; Privilege
0x1800ccf7c  mov     qword ptr [rbp+var_30+8], rsi
0x1800ccf80  call    cs:__imp_RtlAcquirePrivilege
0x1800ccf87  nop     dword ptr [rax+rax+00h]
0x1800ccf8c  mov     rcx, [rbp+hObject]; TokenHandle
0x1800ccf90  mov     ebx, eax
0x1800ccf92  test    eax, eax
0x1800ccf94  jns     short loc_1800CCFD7
0x1800ccf96  call    cs:__imp_CloseHandle
0x1800ccf9d  nop     dword ptr [rax+rax+00h]
0x1800ccfa2  mov     ecx, cs:dword_1801574B8
0x1800ccfa8  test    ecx, ecx
0x1800ccfaa  jnz     short loc_1800CCFC5
0x1800ccfac  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800ccfb2  jz      loc_1800CCF19
0x1800ccfb8  call    IsWppLevelEnabled
0x1800ccfbd  test    al, al
0x1800ccfbf  jz      loc_1800CCF19
0x1800ccfc5  lea     rax, aRtlacquirepriv; "RtlAcquirePrivilege failed: %!STATUS!"
0x1800ccfcc  mov     r8d, 1CDh
0x1800ccfd2  jmp     loc_1800CCEFA
0x1800ccfd7  mov     r9d, 10h; TokenInformationLength
0x1800ccfdd  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800ccfe1  lea     edx, [r9+17h]; TokenInformationClass
0x1800ccfe5  call    cs:__imp_NtSetInformationToken
0x1800ccfec  nop     dword ptr [rax+rax+00h]
0x1800ccff1  mov     rcx, [rbp+ReturnedState]; ReturnedState
0x1800ccff5  mov     ebx, eax
0x1800ccff7  call    cs:__imp_RtlReleasePrivilege
0x1800ccffe  nop     dword ptr [rax+rax+00h]
0x1800cd003  test    ebx, ebx
0x1800cd005  jns     short loc_1800CD03C
0x1800cd007  mov     ecx, cs:dword_1801574B8
0x1800cd00d  test    ecx, ecx
0x1800cd00f  jnz     short loc_1800CD02A
0x1800cd011  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800cd017  jz      loc_1800CCF19
0x1800cd01d  call    IsWppLevelEnabled
0x1800cd022  test    al, al
0x1800cd024  jz      loc_1800CCF19
0x1800cd02a  lea     rax, aNtsetinformati; "NtSetInformationToken failed: %!STATUS!"
0x1800cd031  mov     r8d, 1D8h
0x1800cd037  jmp     loc_1800CCEFA
0x1800cd03c  mov     rax, [rbp+hObject]
0x1800cd040  mov     [rdi], rax
0x1800cd043  xor     eax, eax
0x1800cd045  add     rsp, 78h
0x1800cd049  pop     r14
0x1800cd04b  pop     r12
0x1800cd04d  pop     rdi
0x1800cd04e  pop     rsi
0x1800cd04f  pop     rbx
0x1800cd050  pop     rbp
0x1800cd051  retn
```
