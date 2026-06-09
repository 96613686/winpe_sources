# IsClientPrivilegeWcmSvc(void)

- ea: `0x18000c3e4`
- end: `0x18000c4ed`
- name: `?IsClientPrivilegeWcmSvc@@YAHXZ`
- size: `265`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ce60`
- `0x18000cf90`

## callees

- `0x18000bf74`
- `0x18000c3e4`
- `0x18000c4f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c48e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c48e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c444`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c444`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c484`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c4de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c4de`

## pseudocode

```c
__int64 IsClientPrivilegeWcmSvc(void)
{
  unsigned int LastError; // eax
  TetheringServiceTelemetry *v1; // r10
  __int64 v2; // rdx
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  IsMember = 0;
  TokenHandle = 0;
  Sid = 0;
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 13;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids, LastError);
    }
  }
  else if ( ConvertStringSidToSidW(L"S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888", &Sid) )
  {
    if ( !CheckTokenMembership(TokenHandle, Sid, &IsMember) )
    {
      LastError = GetLastError();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v2 = 15;
        goto LABEL_13;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 14;
      goto LABEL_13;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  LocalFree(Sid);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18000c3e4  mov     rax, rsp
0x18000c3e7  sub     rsp, 28h
0x18000c3eb  lea     rcx, [rax+10h]; void **
0x18000c3ef  mov     dword ptr [rax+8], 0
0x18000c3f6  mov     qword ptr [rax+10h], 0
0x18000c3fe  mov     qword ptr [rax+18h], 0
0x18000c406  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18000c40b  test    eax, eax
0x18000c40d  jz      short loc_18000C438
0x18000c40f  mov     r10, cs:WPP_GLOBAL_Control
0x18000c416  lea     rcx, WPP_GLOBAL_Control
0x18000c41d  cmp     r10, rcx
0x18000c420  jz      loc_18000C4C6
0x18000c426  test    byte ptr [r10+1Ch], 1
0x18000c42b  jz      loc_18000C4C6
0x18000c431  mov     edx, 0Dh
0x18000c436  jmp     short loc_18000C4B3
0x18000c438  lea     rdx, [rsp+28h+Sid]; Sid
0x18000c43d  lea     rcx, StringSid; "S-1-5-80-4155767994-3874329934-38008851"...
0x18000c444  call    cs:__imp_ConvertStringSidToSidW
0x18000c44a  test    eax, eax
0x18000c44c  jnz     short loc_18000C475
0x18000c44e  call    cs:__imp_GetLastError
0x18000c454  mov     r10, cs:WPP_GLOBAL_Control
0x18000c45b  lea     rcx, WPP_GLOBAL_Control
0x18000c462  cmp     r10, rcx
0x18000c465  jz      short loc_18000C4C6
0x18000c467  test    byte ptr [r10+1Ch], 1
0x18000c46c  jz      short loc_18000C4C6
0x18000c46e  mov     edx, 0Eh
0x18000c473  jmp     short loc_18000C4B3
0x18000c475  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18000c47a  lea     r8, [rsp+28h+IsMember]; IsMember
0x18000c47f  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18000c484  call    cs:__imp_CheckTokenMembership
0x18000c48a  test    eax, eax
0x18000c48c  jnz     short loc_18000C4C6
0x18000c48e  call    cs:__imp_GetLastError
0x18000c494  mov     r10, cs:WPP_GLOBAL_Control
0x18000c49b  lea     rcx, WPP_GLOBAL_Control
0x18000c4a2  cmp     r10, rcx
0x18000c4a5  jz      short loc_18000C4C6
0x18000c4a7  test    byte ptr [r10+1Ch], 1
0x18000c4ac  jz      short loc_18000C4C6
0x18000c4ae  mov     edx, 0Fh
0x18000c4b3  mov     rcx, [r10+10h]
0x18000c4b7  lea     r8, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids
0x18000c4be  mov     r9d, eax
0x18000c4c1  call    WPP_SF_d
0x18000c4c6  cmp     [rsp+28h+TokenHandle], 0
0x18000c4cc  jz      short loc_18000C4D9
0x18000c4ce  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18000c4d3  call    cs:__imp_CloseHandle
0x18000c4d9  mov     rcx, [rsp+28h+Sid]; hMem
0x18000c4de  call    cs:__imp_LocalFree
0x18000c4e4  mov     eax, [rsp+28h+IsMember]
0x18000c4e8  add     rsp, 28h
0x18000c4ec  retn
```
