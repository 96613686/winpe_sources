# IsCallerMember(ushort const *,int *)

- ea: `0x18003dff0`
- end: `0x18003e116`
- name: `?IsCallerMember@@YAKPEBGPEAH@Z`
- size: `294`
- prototype: `unsigned int __fastcall(LPCWSTR StringSid, PBOOL IsMember)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801241a4`
- `0x180124344`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003dff0`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e077`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e065`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e065`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e087`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003e050`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003e050`

## pseudocode

```c
__int64 __fastcall IsCallerMember(LPCWSTR StringSid, PBOOL IsMember)
{
  RPC_STATUS v4; // eax
  HANDLE v5; // rbx
  DWORD LastError; // edi
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  Sid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  }
  *IsMember = 0;
  v4 = LocalQueryRpcClientToken(&TokenHandle);
  v5 = TokenHandle;
  LastError = v4;
  if ( !v4
    && (ConvertStringSidToSidW(StringSid, &Sid) || (LastError = GetLastError()) == 0)
    && !CheckTokenMembership(v5, Sid, IsMember) )
  {
    LastError = GetLastError();
  }
  if ( v5 )
    CloseHandle(v5);
  if ( Sid )
    LocalFree(Sid);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 48, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003dff0  mov     [rsp+arg_0], rbx
0x18003dff5  mov     [rsp+arg_18], rbp
0x18003dffa  push    rsi
0x18003dffb  push    rdi
0x18003dffc  push    r14
0x18003dffe  sub     rsp, 20h
0x18003e002  xor     ebx, ebx
0x18003e004  mov     rsi, rdx
0x18003e007  mov     [rsp+38h+TokenHandle], rbx
0x18003e00c  mov     rbp, rcx
0x18003e00f  mov     [rsp+38h+Sid], rbx
0x18003e014  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e01b  lea     r14, WPP_GLOBAL_Control
0x18003e022  cmp     rcx, r14
0x18003e025  jz      short loc_18003E031
0x18003e027  cmp     byte ptr [rcx+69h], 4
0x18003e02b  jnb     loc_18003E0B4
0x18003e031  lea     rcx, [rsp+38h+TokenHandle]; void **
0x18003e036  mov     [rsi], ebx
0x18003e038  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003e03d  mov     rbx, [rsp+38h+TokenHandle]
0x18003e042  mov     edi, eax
0x18003e044  test    eax, eax
0x18003e046  jnz     short loc_18003E06F
0x18003e048  lea     rdx, [rsp+38h+Sid]; Sid
0x18003e04d  mov     rcx, rbp; StringSid
0x18003e050  call    cs:__imp_ConvertStringSidToSidW
0x18003e056  test    eax, eax
0x18003e058  jz      short loc_18003E0D8
0x18003e05a  mov     rdx, [rsp+38h+Sid]; SidToCheck
0x18003e05f  mov     r8, rsi; IsMember
0x18003e062  mov     rcx, rbx; TokenHandle
0x18003e065  call    cs:__imp_CheckTokenMembership
0x18003e06b  test    eax, eax
0x18003e06d  jz      short loc_18003E0E9
0x18003e06f  test    rbx, rbx
0x18003e072  jz      short loc_18003E07D
0x18003e074  mov     rcx, rbx; hObject
0x18003e077  call    cs:__imp_CloseHandle
0x18003e07d  mov     rcx, [rsp+38h+Sid]; hMem
0x18003e082  test    rcx, rcx
0x18003e085  jz      short loc_18003E08D
0x18003e087  call    cs:__imp_LocalFree
0x18003e08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e094  cmp     rcx, r14
0x18003e097  jz      short loc_18003E09F
0x18003e099  cmp     byte ptr [rcx+69h], 4
0x18003e09d  jnb     short loc_18003E0F6
0x18003e09f  mov     rbx, [rsp+38h+arg_0]
0x18003e0a4  mov     eax, edi
0x18003e0a6  mov     rbp, [rsp+38h+arg_18]
0x18003e0ab  add     rsp, 20h
0x18003e0af  pop     r14
0x18003e0b1  pop     rdi
0x18003e0b2  pop     rsi
0x18003e0b3  retn
0x18003e0b4  test    byte ptr [rcx+6Ch], 1
0x18003e0b8  jz      loc_18003E031
0x18003e0be  mov     rcx, [rcx+60h]
0x18003e0c2  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e0c9  mov     edx, 2Fh ; '/'
0x18003e0ce  call    WPP_SF_
0x18003e0d3  jmp     loc_18003E031
0x18003e0d8  call    cs:__imp_GetLastError
0x18003e0de  mov     edi, eax
0x18003e0e0  test    eax, eax
0x18003e0e2  jnz     short loc_18003E06F
0x18003e0e4  jmp     loc_18003E05A
0x18003e0e9  call    cs:__imp_GetLastError
0x18003e0ef  mov     edi, eax
0x18003e0f1  jmp     loc_18003E06F
0x18003e0f6  test    byte ptr [rcx+6Ch], 1
0x18003e0fa  jz      short loc_18003E09F
0x18003e0fc  mov     rcx, [rcx+60h]
0x18003e100  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e107  mov     edx, 30h ; '0'
0x18003e10c  mov     r9d, edi
0x18003e10f  call    WPP_SF_d
0x18003e114  jmp     short loc_18003E09F
```
