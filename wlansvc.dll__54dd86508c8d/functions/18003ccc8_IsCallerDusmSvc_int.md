# IsCallerDusmSvc(int *)

- ea: `0x18003ccc8`
- end: `0x18003ce85`
- name: `?IsCallerDusmSvc@@YAKPEAH@Z`
- size: `445`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d214`
- `0x180097c70`
- `0x18012ae50`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003ccc8`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cd71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cd71`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003cd56`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003cd56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cd81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cd81`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003cd3b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003cd3b`

## pseudocode

```c
__int64 __fastcall IsCallerDusmSvc(PBOOL IsMember)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  Sid = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_(v2[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  *IsMember = 0;
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  if ( !LastError
    && (ConvertStringSidToSidW(L"S-1-5-80-4071458001-3563271761-1846288968-3700919931-3809667977", &Sid)
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
      WPP_SF_d(v4[12], 54, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003ccc8  mov     [rsp+arg_10], rbx
0x18003cccd  mov     [rsp+arg_18], rsi
0x18003ccd2  push    r12
0x18003ccd4  sub     rsp, 20h
0x18003ccd8  mov     rsi, rcx
0x18003ccdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cce2  lea     r12, WPP_GLOBAL_Control
0x18003cce9  cmp     rcx, r12
0x18003ccec  jz      short loc_18003CCF8
0x18003ccee  cmp     byte ptr [rcx+69h], 4
0x18003ccf2  jnb     loc_18003CDBF
0x18003ccf8  mov     [rsp+28h+TokenHandle], 0
0x18003cd01  mov     [rsp+28h+Sid], 0
0x18003cd0a  cmp     rcx, r12
0x18003cd0d  jz      short loc_18003CD19
0x18003cd0f  cmp     byte ptr [rcx+69h], 4
0x18003cd13  jnb     loc_18003CDEA
0x18003cd19  lea     rcx, [rsp+28h+TokenHandle]; void **
0x18003cd1e  mov     dword ptr [rsi], 0
0x18003cd24  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003cd29  mov     ebx, eax
0x18003cd2b  test    eax, eax
0x18003cd2d  jnz     short loc_18003CD64
0x18003cd2f  lea     rdx, [rsp+28h+Sid]; Sid
0x18003cd34  lea     rcx, StringSid; "S-1-5-80-4071458001-3563271761-18462889"...
0x18003cd3b  call    cs:__imp_ConvertStringSidToSidW
0x18003cd41  test    eax, eax
0x18003cd43  jz      loc_18003CE0E
0x18003cd49  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18003cd4e  mov     r8, rsi; IsMember
0x18003cd51  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18003cd56  call    cs:__imp_CheckTokenMembership
0x18003cd5c  test    eax, eax
0x18003cd5e  jz      loc_18003CE23
0x18003cd64  cmp     [rsp+28h+TokenHandle], 0
0x18003cd6a  jz      short loc_18003CD77
0x18003cd6c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003cd71  call    cs:__imp_CloseHandle
0x18003cd77  mov     rcx, [rsp+28h+Sid]; hMem
0x18003cd7c  test    rcx, rcx
0x18003cd7f  jz      short loc_18003CD87
0x18003cd81  call    cs:__imp_LocalFree
0x18003cd87  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd8e  cmp     rcx, r12
0x18003cd91  jz      short loc_18003CDAC
0x18003cd93  cmp     byte ptr [rcx+69h], 4
0x18003cd97  jnb     loc_18003CE30
0x18003cd9d  cmp     rcx, r12
0x18003cda0  jz      short loc_18003CDAC
0x18003cda2  cmp     byte ptr [rcx+69h], 4
0x18003cda6  jnb     loc_18003CE5E
0x18003cdac  mov     rsi, [rsp+28h+arg_18]
0x18003cdb1  mov     eax, ebx
0x18003cdb3  mov     rbx, [rsp+28h+arg_10]
0x18003cdb8  add     rsp, 20h
0x18003cdbc  pop     r12
0x18003cdbe  retn
0x18003cdbf  test    byte ptr [rcx+6Ch], 1
0x18003cdc3  jz      loc_18003CCF8
0x18003cdc9  mov     rcx, [rcx+60h]
0x18003cdcd  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003cdd4  mov     edx, 35h ; '5'
0x18003cdd9  call    WPP_SF_
0x18003cdde  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cde5  jmp     loc_18003CCF8
0x18003cdea  test    byte ptr [rcx+6Ch], 1
0x18003cdee  jz      loc_18003CD19
0x18003cdf4  mov     rcx, [rcx+60h]
0x18003cdf8  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003cdff  mov     edx, 2Fh ; '/'
0x18003ce04  call    WPP_SF_
0x18003ce09  jmp     loc_18003CD19
0x18003ce0e  call    cs:__imp_GetLastError
0x18003ce14  mov     ebx, eax
0x18003ce16  test    eax, eax
0x18003ce18  jnz     loc_18003CD64
0x18003ce1e  jmp     loc_18003CD49
0x18003ce23  call    cs:__imp_GetLastError
0x18003ce29  mov     ebx, eax
0x18003ce2b  jmp     loc_18003CD64
0x18003ce30  test    byte ptr [rcx+6Ch], 1
0x18003ce34  jz      loc_18003CD9D
0x18003ce3a  mov     rcx, [rcx+60h]
0x18003ce3e  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003ce45  mov     edx, 30h ; '0'
0x18003ce4a  mov     r9d, ebx
0x18003ce4d  call    WPP_SF_d
0x18003ce52  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce59  jmp     loc_18003CD9D
0x18003ce5e  test    byte ptr [rcx+6Ch], 1
0x18003ce62  jz      loc_18003CDAC
0x18003ce68  mov     rcx, [rcx+60h]
0x18003ce6c  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003ce73  mov     edx, 36h ; '6'
0x18003ce78  mov     r9d, ebx
0x18003ce7b  call    WPP_SF_d
0x18003ce80  jmp     loc_18003CDAC
```
