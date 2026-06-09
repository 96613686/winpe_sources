# IsCallerWCMSvc(int *)

- ea: `0x18003d2a4`
- end: `0x18003d461`
- name: `?IsCallerWCMSvc@@YAKPEAH@Z`
- size: `445`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d214`
- `0x1800954a0`
- `0x180097c70`
- `0x18012a2a0`
- `0x18012ae50`
- `0x180130880`
- `0x180130a20`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003d2a4`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d34d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d34d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d332`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d332`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d35d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d35d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d317`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d317`

## pseudocode

```c
__int64 __fastcall IsCallerWCMSvc(PBOOL IsMember)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 49, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  Sid = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_(v2[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  *IsMember = 0;
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  if ( !LastError
    && (ConvertStringSidToSidW(L"S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888", &Sid)
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
      WPP_SF_d(v4[12], 50, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003d2a4  mov     [rsp+arg_10], rbx
0x18003d2a9  mov     [rsp+arg_18], rsi
0x18003d2ae  push    r12
0x18003d2b0  sub     rsp, 20h
0x18003d2b4  mov     rsi, rcx
0x18003d2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d2be  lea     r12, WPP_GLOBAL_Control
0x18003d2c5  cmp     rcx, r12
0x18003d2c8  jz      short loc_18003D2D4
0x18003d2ca  cmp     byte ptr [rcx+69h], 4
0x18003d2ce  jnb     loc_18003D39B
0x18003d2d4  mov     [rsp+28h+TokenHandle], 0
0x18003d2dd  mov     [rsp+28h+Sid], 0
0x18003d2e6  cmp     rcx, r12
0x18003d2e9  jz      short loc_18003D2F5
0x18003d2eb  cmp     byte ptr [rcx+69h], 4
0x18003d2ef  jnb     loc_18003D3C6
0x18003d2f5  lea     rcx, [rsp+28h+TokenHandle]; void **
0x18003d2fa  mov     dword ptr [rsi], 0
0x18003d300  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003d305  mov     ebx, eax
0x18003d307  test    eax, eax
0x18003d309  jnz     short loc_18003D340
0x18003d30b  lea     rdx, [rsp+28h+Sid]; Sid
0x18003d310  lea     rcx, aS1580415576799; "S-1-5-80-4155767994-3874329934-38008851"...
0x18003d317  call    cs:__imp_ConvertStringSidToSidW
0x18003d31d  test    eax, eax
0x18003d31f  jz      loc_18003D3EA
0x18003d325  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18003d32a  mov     r8, rsi; IsMember
0x18003d32d  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18003d332  call    cs:__imp_CheckTokenMembership
0x18003d338  test    eax, eax
0x18003d33a  jz      loc_18003D3FF
0x18003d340  cmp     [rsp+28h+TokenHandle], 0
0x18003d346  jz      short loc_18003D353
0x18003d348  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003d34d  call    cs:__imp_CloseHandle
0x18003d353  mov     rcx, [rsp+28h+Sid]; hMem
0x18003d358  test    rcx, rcx
0x18003d35b  jz      short loc_18003D363
0x18003d35d  call    cs:__imp_LocalFree
0x18003d363  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d36a  cmp     rcx, r12
0x18003d36d  jz      short loc_18003D388
0x18003d36f  cmp     byte ptr [rcx+69h], 4
0x18003d373  jnb     loc_18003D40C
0x18003d379  cmp     rcx, r12
0x18003d37c  jz      short loc_18003D388
0x18003d37e  cmp     byte ptr [rcx+69h], 4
0x18003d382  jnb     loc_18003D43A
0x18003d388  mov     rsi, [rsp+28h+arg_18]
0x18003d38d  mov     eax, ebx
0x18003d38f  mov     rbx, [rsp+28h+arg_10]
0x18003d394  add     rsp, 20h
0x18003d398  pop     r12
0x18003d39a  retn
0x18003d39b  test    byte ptr [rcx+6Ch], 1
0x18003d39f  jz      loc_18003D2D4
0x18003d3a5  mov     rcx, [rcx+60h]
0x18003d3a9  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d3b0  mov     edx, 31h ; '1'
0x18003d3b5  call    WPP_SF_
0x18003d3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3c1  jmp     loc_18003D2D4
0x18003d3c6  test    byte ptr [rcx+6Ch], 1
0x18003d3ca  jz      loc_18003D2F5
0x18003d3d0  mov     rcx, [rcx+60h]
0x18003d3d4  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d3db  mov     edx, 2Fh ; '/'
0x18003d3e0  call    WPP_SF_
0x18003d3e5  jmp     loc_18003D2F5
0x18003d3ea  call    cs:__imp_GetLastError
0x18003d3f0  mov     ebx, eax
0x18003d3f2  test    eax, eax
0x18003d3f4  jnz     loc_18003D340
0x18003d3fa  jmp     loc_18003D325
0x18003d3ff  call    cs:__imp_GetLastError
0x18003d405  mov     ebx, eax
0x18003d407  jmp     loc_18003D340
0x18003d40c  test    byte ptr [rcx+6Ch], 1
0x18003d410  jz      loc_18003D379
0x18003d416  mov     rcx, [rcx+60h]
0x18003d41a  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d421  mov     edx, 30h ; '0'
0x18003d426  mov     r9d, ebx
0x18003d429  call    WPP_SF_d
0x18003d42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d435  jmp     loc_18003D379
0x18003d43a  test    byte ptr [rcx+6Ch], 1
0x18003d43e  jz      loc_18003D388
0x18003d444  mov     rcx, [rcx+60h]
0x18003d448  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d44f  mov     edx, 32h ; '2'
0x18003d454  mov     r9d, ebx
0x18003d457  call    WPP_SF_d
0x18003d45c  jmp     loc_18003D388
```
