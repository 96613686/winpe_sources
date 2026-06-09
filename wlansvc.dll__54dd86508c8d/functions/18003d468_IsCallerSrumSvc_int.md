# IsCallerSrumSvc(int *)

- ea: `0x18003d468`
- end: `0x18003d625`
- name: `?IsCallerSrumSvc@@YAKPEAH@Z`
- size: `445`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008c8e0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003d468`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d511`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d4f6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d4f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d521`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d521`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d4db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d4db`

## pseudocode

```c
__int64 __fastcall IsCallerSrumSvc(PBOOL IsMember)
{
  PVOID *v2; // rcx
  DWORD LastError; // ebx
  PVOID *v4; // rcx
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  Sid = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_(v2[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  *IsMember = 0;
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  if ( !LastError
    && (ConvertStringSidToSidW(L"S-1-5-80-2970612574-78537857-698502321-558674196-1451644582", &Sid)
     || (LastError = GetLastError()) == 0)
    && !CheckTokenMembership(TokenHandle, Sid, IsMember) )
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Sid )
    LocalFree(Sid);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 48, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 105) >= 4u && (*((_BYTE *)v4 + 108) & 1) != 0 )
      WPP_SF_d(v4[12], 56, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003d468  mov     [rsp+arg_10], rbx
0x18003d46d  mov     [rsp+arg_18], rsi
0x18003d472  push    r12
0x18003d474  sub     rsp, 20h
0x18003d478  mov     rsi, rcx
0x18003d47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d482  lea     r12, WPP_GLOBAL_Control
0x18003d489  cmp     rcx, r12
0x18003d48c  jz      short loc_18003D498
0x18003d48e  cmp     byte ptr [rcx+69h], 4
0x18003d492  jnb     loc_18003D55F
0x18003d498  mov     [rsp+28h+TokenHandle], 0
0x18003d4a1  mov     [rsp+28h+Sid], 0
0x18003d4aa  cmp     rcx, r12
0x18003d4ad  jz      short loc_18003D4B9
0x18003d4af  cmp     byte ptr [rcx+69h], 4
0x18003d4b3  jnb     loc_18003D58A
0x18003d4b9  lea     rcx, [rsp+28h+TokenHandle]; void **
0x18003d4be  mov     dword ptr [rsi], 0
0x18003d4c4  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003d4c9  mov     ebx, eax
0x18003d4cb  test    eax, eax
0x18003d4cd  jnz     short loc_18003D504
0x18003d4cf  lea     rdx, [rsp+28h+Sid]; Sid
0x18003d4d4  lea     rcx, aS1580297061257; "S-1-5-80-2970612574-78537857-698502321-"...
0x18003d4db  call    cs:__imp_ConvertStringSidToSidW
0x18003d4e1  test    eax, eax
0x18003d4e3  jz      loc_18003D5AE
0x18003d4e9  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18003d4ee  mov     r8, rsi; IsMember
0x18003d4f1  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18003d4f6  call    cs:__imp_CheckTokenMembership
0x18003d4fc  test    eax, eax
0x18003d4fe  jz      loc_18003D5C3
0x18003d504  cmp     [rsp+28h+TokenHandle], 0
0x18003d50a  jz      short loc_18003D517
0x18003d50c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003d511  call    cs:__imp_CloseHandle
0x18003d517  mov     rcx, [rsp+28h+Sid]; hMem
0x18003d51c  test    rcx, rcx
0x18003d51f  jz      short loc_18003D527
0x18003d521  call    cs:__imp_LocalFree
0x18003d527  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d52e  cmp     rcx, r12
0x18003d531  jz      short loc_18003D54C
0x18003d533  cmp     byte ptr [rcx+69h], 4
0x18003d537  jnb     loc_18003D5D0
0x18003d53d  cmp     rcx, r12
0x18003d540  jz      short loc_18003D54C
0x18003d542  cmp     byte ptr [rcx+69h], 4
0x18003d546  jnb     loc_18003D5FE
0x18003d54c  mov     rsi, [rsp+28h+arg_18]
0x18003d551  mov     eax, ebx
0x18003d553  mov     rbx, [rsp+28h+arg_10]
0x18003d558  add     rsp, 20h
0x18003d55c  pop     r12
0x18003d55e  retn
0x18003d55f  test    byte ptr [rcx+6Ch], 1
0x18003d563  jz      loc_18003D498
0x18003d569  mov     rcx, [rcx+60h]
0x18003d56d  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d574  mov     edx, 37h ; '7'
0x18003d579  call    WPP_SF_
0x18003d57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d585  jmp     loc_18003D498
0x18003d58a  test    byte ptr [rcx+6Ch], 1
0x18003d58e  jz      loc_18003D4B9
0x18003d594  mov     rcx, [rcx+60h]
0x18003d598  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d59f  mov     edx, 2Fh ; '/'
0x18003d5a4  call    WPP_SF_
0x18003d5a9  jmp     loc_18003D4B9
0x18003d5ae  call    cs:__imp_GetLastError
0x18003d5b4  mov     ebx, eax
0x18003d5b6  test    eax, eax
0x18003d5b8  jnz     loc_18003D504
0x18003d5be  jmp     loc_18003D4E9
0x18003d5c3  call    cs:__imp_GetLastError
0x18003d5c9  mov     ebx, eax
0x18003d5cb  jmp     loc_18003D504
0x18003d5d0  test    byte ptr [rcx+6Ch], 1
0x18003d5d4  jz      loc_18003D53D
0x18003d5da  mov     rcx, [rcx+60h]
0x18003d5de  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d5e5  mov     edx, 30h ; '0'
0x18003d5ea  mov     r9d, ebx
0x18003d5ed  call    WPP_SF_d
0x18003d5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d5f9  jmp     loc_18003D53D
0x18003d5fe  test    byte ptr [rcx+6Ch], 1
0x18003d602  jz      loc_18003D54C
0x18003d608  mov     rcx, [rcx+60h]
0x18003d60c  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d613  mov     edx, 38h ; '8'
0x18003d618  mov     r9d, ebx
0x18003d61b  call    WPP_SF_d
0x18003d620  jmp     loc_18003D54C
```
