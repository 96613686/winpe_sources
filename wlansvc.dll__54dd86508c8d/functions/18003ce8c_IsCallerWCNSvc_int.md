# IsCallerWCNSvc(int *)

- ea: `0x18003ce8c`
- end: `0x18003d049`
- name: `?IsCallerWCNSvc@@YAKPEAH@Z`
- size: `445`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d214`
- `0x1800a6d20`
- `0x1801496fc`
- `0x18015cd70`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003ce8c`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cf35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cf35`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003cf1a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003cf1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cf45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cf45`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003ceff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003ceff`

## pseudocode

```c
__int64 __fastcall IsCallerWCNSvc(PBOOL IsMember)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 63, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  Sid = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_(v2[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  *IsMember = 0;
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  if ( !LastError
    && (ConvertStringSidToSidW(L"S-1-5-80-1555863574-1012459212-3842453055-37978308-1142448422", &Sid)
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
      WPP_SF_d(v4[12], 64, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003ce8c  mov     [rsp+arg_10], rbx
0x18003ce91  mov     [rsp+arg_18], rsi
0x18003ce96  push    r12
0x18003ce98  sub     rsp, 20h
0x18003ce9c  mov     rsi, rcx
0x18003ce9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cea6  lea     r12, WPP_GLOBAL_Control
0x18003cead  cmp     rcx, r12
0x18003ceb0  jz      short loc_18003CEBC
0x18003ceb2  cmp     byte ptr [rcx+69h], 4
0x18003ceb6  jnb     loc_18003CF83
0x18003cebc  mov     [rsp+28h+TokenHandle], 0
0x18003cec5  mov     [rsp+28h+Sid], 0
0x18003cece  cmp     rcx, r12
0x18003ced1  jz      short loc_18003CEDD
0x18003ced3  cmp     byte ptr [rcx+69h], 4
0x18003ced7  jnb     loc_18003CFAE
0x18003cedd  lea     rcx, [rsp+28h+TokenHandle]; void **
0x18003cee2  mov     dword ptr [rsi], 0
0x18003cee8  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003ceed  mov     ebx, eax
0x18003ceef  test    eax, eax
0x18003cef1  jnz     short loc_18003CF28
0x18003cef3  lea     rdx, [rsp+28h+Sid]; Sid
0x18003cef8  lea     rcx, aS1580155586357; "S-1-5-80-1555863574-1012459212-38424530"...
0x18003ceff  call    cs:__imp_ConvertStringSidToSidW
0x18003cf05  test    eax, eax
0x18003cf07  jz      loc_18003CFD2
0x18003cf0d  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18003cf12  mov     r8, rsi; IsMember
0x18003cf15  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18003cf1a  call    cs:__imp_CheckTokenMembership
0x18003cf20  test    eax, eax
0x18003cf22  jz      loc_18003CFE7
0x18003cf28  cmp     [rsp+28h+TokenHandle], 0
0x18003cf2e  jz      short loc_18003CF3B
0x18003cf30  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003cf35  call    cs:__imp_CloseHandle
0x18003cf3b  mov     rcx, [rsp+28h+Sid]; hMem
0x18003cf40  test    rcx, rcx
0x18003cf43  jz      short loc_18003CF4B
0x18003cf45  call    cs:__imp_LocalFree
0x18003cf4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf52  cmp     rcx, r12
0x18003cf55  jz      short loc_18003CF70
0x18003cf57  cmp     byte ptr [rcx+69h], 4
0x18003cf5b  jnb     loc_18003CFF4
0x18003cf61  cmp     rcx, r12
0x18003cf64  jz      short loc_18003CF70
0x18003cf66  cmp     byte ptr [rcx+69h], 4
0x18003cf6a  jnb     loc_18003D022
0x18003cf70  mov     rsi, [rsp+28h+arg_18]
0x18003cf75  mov     eax, ebx
0x18003cf77  mov     rbx, [rsp+28h+arg_10]
0x18003cf7c  add     rsp, 20h
0x18003cf80  pop     r12
0x18003cf82  retn
0x18003cf83  test    byte ptr [rcx+6Ch], 1
0x18003cf87  jz      loc_18003CEBC
0x18003cf8d  mov     rcx, [rcx+60h]
0x18003cf91  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003cf98  mov     edx, 3Fh ; '?'
0x18003cf9d  call    WPP_SF_
0x18003cfa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfa9  jmp     loc_18003CEBC
0x18003cfae  test    byte ptr [rcx+6Ch], 1
0x18003cfb2  jz      loc_18003CEDD
0x18003cfb8  mov     rcx, [rcx+60h]
0x18003cfbc  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003cfc3  mov     edx, 2Fh ; '/'
0x18003cfc8  call    WPP_SF_
0x18003cfcd  jmp     loc_18003CEDD
0x18003cfd2  call    cs:__imp_GetLastError
0x18003cfd8  mov     ebx, eax
0x18003cfda  test    eax, eax
0x18003cfdc  jnz     loc_18003CF28
0x18003cfe2  jmp     loc_18003CF0D
0x18003cfe7  call    cs:__imp_GetLastError
0x18003cfed  mov     ebx, eax
0x18003cfef  jmp     loc_18003CF28
0x18003cff4  test    byte ptr [rcx+6Ch], 1
0x18003cff8  jz      loc_18003CF61
0x18003cffe  mov     rcx, [rcx+60h]
0x18003d002  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d009  mov     edx, 30h ; '0'
0x18003d00e  mov     r9d, ebx
0x18003d011  call    WPP_SF_d
0x18003d016  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d01d  jmp     loc_18003CF61
0x18003d022  test    byte ptr [rcx+6Ch], 1
0x18003d026  jz      loc_18003CF70
0x18003d02c  mov     rcx, [rcx+60h]
0x18003d030  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d037  mov     edx, 40h ; '@'
0x18003d03c  mov     r9d, ebx
0x18003d03f  call    WPP_SF_d
0x18003d044  jmp     loc_18003CF70
```
