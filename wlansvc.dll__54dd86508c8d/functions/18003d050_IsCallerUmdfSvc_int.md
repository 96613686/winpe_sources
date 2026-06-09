# IsCallerUmdfSvc(int *)

- ea: `0x18003d050`
- end: `0x18003d20d`
- name: `?IsCallerUmdfSvc@@YAKPEAH@Z`
- size: `445`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d214`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003d050`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0f9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d0de`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d0de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d109`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d109`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d0c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d0c3`

## pseudocode

```c
__int64 __fastcall IsCallerUmdfSvc(PBOOL IsMember)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 57, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  Sid = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_(v2[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  *IsMember = 0;
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  if ( !LastError
    && (ConvertStringSidToSidW(L"S-1-5-84-0-0-0-0-0", &Sid) || (LastError = GetLastError()) == 0)
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
      WPP_SF_d(v4[12], 58, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003d050  mov     [rsp+arg_10], rbx
0x18003d055  mov     [rsp+arg_18], rsi
0x18003d05a  push    r12
0x18003d05c  sub     rsp, 20h
0x18003d060  mov     rsi, rcx
0x18003d063  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d06a  lea     r12, WPP_GLOBAL_Control
0x18003d071  cmp     rcx, r12
0x18003d074  jz      short loc_18003D080
0x18003d076  cmp     byte ptr [rcx+69h], 4
0x18003d07a  jnb     loc_18003D147
0x18003d080  mov     [rsp+28h+TokenHandle], 0
0x18003d089  mov     [rsp+28h+Sid], 0
0x18003d092  cmp     rcx, r12
0x18003d095  jz      short loc_18003D0A1
0x18003d097  cmp     byte ptr [rcx+69h], 4
0x18003d09b  jnb     loc_18003D172
0x18003d0a1  lea     rcx, [rsp+28h+TokenHandle]; void **
0x18003d0a6  mov     dword ptr [rsi], 0
0x18003d0ac  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003d0b1  mov     ebx, eax
0x18003d0b3  test    eax, eax
0x18003d0b5  jnz     short loc_18003D0EC
0x18003d0b7  lea     rdx, [rsp+28h+Sid]; Sid
0x18003d0bc  lea     rcx, aS158400000; "S-1-5-84-0-0-0-0-0"
0x18003d0c3  call    cs:__imp_ConvertStringSidToSidW
0x18003d0c9  test    eax, eax
0x18003d0cb  jz      loc_18003D196
0x18003d0d1  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18003d0d6  mov     r8, rsi; IsMember
0x18003d0d9  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18003d0de  call    cs:__imp_CheckTokenMembership
0x18003d0e4  test    eax, eax
0x18003d0e6  jz      loc_18003D1AB
0x18003d0ec  cmp     [rsp+28h+TokenHandle], 0
0x18003d0f2  jz      short loc_18003D0FF
0x18003d0f4  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003d0f9  call    cs:__imp_CloseHandle
0x18003d0ff  mov     rcx, [rsp+28h+Sid]; hMem
0x18003d104  test    rcx, rcx
0x18003d107  jz      short loc_18003D10F
0x18003d109  call    cs:__imp_LocalFree
0x18003d10f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d116  cmp     rcx, r12
0x18003d119  jz      short loc_18003D134
0x18003d11b  cmp     byte ptr [rcx+69h], 4
0x18003d11f  jnb     loc_18003D1B8
0x18003d125  cmp     rcx, r12
0x18003d128  jz      short loc_18003D134
0x18003d12a  cmp     byte ptr [rcx+69h], 4
0x18003d12e  jnb     loc_18003D1E6
0x18003d134  mov     rsi, [rsp+28h+arg_18]
0x18003d139  mov     eax, ebx
0x18003d13b  mov     rbx, [rsp+28h+arg_10]
0x18003d140  add     rsp, 20h
0x18003d144  pop     r12
0x18003d146  retn
0x18003d147  test    byte ptr [rcx+6Ch], 1
0x18003d14b  jz      loc_18003D080
0x18003d151  mov     rcx, [rcx+60h]
0x18003d155  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d15c  mov     edx, 39h ; '9'
0x18003d161  call    WPP_SF_
0x18003d166  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d16d  jmp     loc_18003D080
0x18003d172  test    byte ptr [rcx+6Ch], 1
0x18003d176  jz      loc_18003D0A1
0x18003d17c  mov     rcx, [rcx+60h]
0x18003d180  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d187  mov     edx, 2Fh ; '/'
0x18003d18c  call    WPP_SF_
0x18003d191  jmp     loc_18003D0A1
0x18003d196  call    cs:__imp_GetLastError
0x18003d19c  mov     ebx, eax
0x18003d19e  test    eax, eax
0x18003d1a0  jnz     loc_18003D0EC
0x18003d1a6  jmp     loc_18003D0D1
0x18003d1ab  call    cs:__imp_GetLastError
0x18003d1b1  mov     ebx, eax
0x18003d1b3  jmp     loc_18003D0EC
0x18003d1b8  test    byte ptr [rcx+6Ch], 1
0x18003d1bc  jz      loc_18003D125
0x18003d1c2  mov     rcx, [rcx+60h]
0x18003d1c6  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d1cd  mov     edx, 30h ; '0'
0x18003d1d2  mov     r9d, ebx
0x18003d1d5  call    WPP_SF_d
0x18003d1da  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1e1  jmp     loc_18003D125
0x18003d1e6  test    byte ptr [rcx+6Ch], 1
0x18003d1ea  jz      loc_18003D134
0x18003d1f0  mov     rcx, [rcx+60h]
0x18003d1f4  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d1fb  mov     edx, 3Ah ; ':'
0x18003d200  mov     r9d, ebx
0x18003d203  call    WPP_SF_d
0x18003d208  jmp     loc_18003D134
```
