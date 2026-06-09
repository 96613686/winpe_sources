# GetTokenUserInfo(void *,_TOKEN_USER * *)

- ea: `0x18000c800`
- end: `0x18000ca5a`
- name: `?GetTokenUserInfo@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `602`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bfa0`
- `0x18000c5e0`
- `0x18001a618`
- `0x180036214`
- `0x18012423c`
- `0x180130ba0`
- `0x1801c875c`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x18000c800`
- `0x180011530`
- `0x1800c6774`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c884`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c89a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c89a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c994`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c99a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c99a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c851`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c8cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c851`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c8cf`

## pseudocode

```c
DWORD __fastcall GetTokenUserInfo(HANDLE TokenHandle, struct _TOKEN_USER **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  DWORD result; // eax
  DWORD LastError; // edi
  DWORD v9; // edi
  struct _TOKEN_USER *v10; // rbx
  HANDLE ProcessHeap; // rax
  PVOID *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids);
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v6);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    LastError = 1003;
  }
  else
  {
    result = GetLastError();
    LastError = result;
    if ( result == 122 )
    {
      v9 = TokenInformationLength;
      if ( TokenInformationLength )
      {
        v10 = 0;
        ProcessHeap = GetProcessHeap();
        if ( ProcessHeap && (v10 = (struct _TOKEN_USER *)HeapAlloc(ProcessHeap, 8u, v9)) == 0 )
        {
          SetLastError(8u);
        }
        else if ( v10 )
        {
          if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
          {
            LastError = 0;
            *a2 = v10;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError == 122 )
              MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v16);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                20,
                WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids,
                LastError);
            }
            FreeWLMem(v10);
          }
          v12 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_12;
        }
      }
      else
      {
        SetLastError(0x57u);
      }
      v13 = GetLastError();
      LastError = v13;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, v13);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_12;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return result;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, result);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_12:
  if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 105) >= 4u && (*((_BYTE *)v12 + 108) & 1) != 0 )
    WPP_SF_d(v12[12], 21, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000c800  push    rbp
0x18000c802  push    rsi
0x18000c803  push    r14
0x18000c805  sub     rsp, 30h
0x18000c809  mov     r14, rdx
0x18000c80c  mov     [rsp+48h+TokenInformationLength], 0
0x18000c814  mov     rsi, rcx
0x18000c817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c81e  lea     rbp, WPP_GLOBAL_Control
0x18000c825  cmp     rcx, rbp
0x18000c828  jz      short loc_18000C834
0x18000c82a  cmp     byte ptr [rcx+69h], 4
0x18000c82e  jnb     loc_18000C946
0x18000c834  lea     rax, [rsp+48h+TokenInformationLength]
0x18000c839  mov     [rsp+48h+arg_8], rdi
0x18000c83e  xor     r9d, r9d; TokenInformationLength
0x18000c841  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c846  xor     r8d, r8d; TokenInformation
0x18000c849  mov     edx, 1; TokenInformationClass
0x18000c84e  mov     rcx, rsi; TokenHandle
0x18000c851  call    cs:__imp_GetTokenInformation
0x18000c857  test    eax, eax
0x18000c859  jnz     loc_18000C96A
0x18000c85f  call    cs:__imp_GetLastError
0x18000c865  mov     edi, eax
0x18000c867  cmp     eax, 7Ah ; 'z'
0x18000c86a  jnz     loc_18000C90D
0x18000c870  mov     edi, [rsp+48h+TokenInformationLength]
0x18000c874  mov     [rsp+48h+arg_0], rbx
0x18000c879  test    rdi, rdi
0x18000c87c  jz      loc_18000C980
0x18000c882  xor     ebx, ebx
0x18000c884  call    cs:__imp_GetProcessHeap
0x18000c88a  test    rax, rax
0x18000c88d  jz      short loc_18000C8AC
0x18000c88f  mov     r8d, edi; dwBytes
0x18000c892  mov     edx, 8; dwFlags
0x18000c897  mov     rcx, rax; hHeap
0x18000c89a  call    cs:__imp_HeapAlloc
0x18000c8a0  mov     rbx, rax
0x18000c8a3  test    rax, rax
0x18000c8a6  jz      loc_18000C98F
0x18000c8ac  test    rbx, rbx
0x18000c8af  jz      loc_18000C99A
0x18000c8b5  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000c8ba  lea     rax, [rsp+48h+TokenInformationLength]
0x18000c8bf  mov     r8, rbx; TokenInformation
0x18000c8c2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c8c7  mov     edx, 1; TokenInformationClass
0x18000c8cc  mov     rcx, rsi; TokenHandle
0x18000c8cf  call    cs:__imp_GetTokenInformation
0x18000c8d5  test    eax, eax
0x18000c8d7  jz      loc_18000C9E4
0x18000c8dd  xor     edi, edi
0x18000c8df  mov     [r14], rbx
0x18000c8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8e9  mov     rbx, [rsp+48h+arg_0]
0x18000c8ee  cmp     rcx, rbp
0x18000c8f1  jz      short loc_18000C8FD
0x18000c8f3  cmp     byte ptr [rcx+69h], 4
0x18000c8f7  jnb     loc_18000CA33
0x18000c8fd  mov     eax, edi
0x18000c8ff  mov     rdi, [rsp+48h+arg_8]
0x18000c904  add     rsp, 30h
0x18000c908  pop     r14
0x18000c90a  pop     rsi
0x18000c90b  pop     rbp
0x18000c90c  retn
0x18000c90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c914  cmp     rcx, rbp
0x18000c917  jz      short loc_18000C8FF
0x18000c919  cmp     byte ptr [rcx+69h], 1
0x18000c91d  jb      short loc_18000C8EE
0x18000c91f  test    byte ptr [rcx+6Ch], 1
0x18000c923  jz      short loc_18000C8EE
0x18000c925  mov     rcx, [rcx+60h]
0x18000c929  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c930  mov     edx, 12h
0x18000c935  mov     r9d, eax
0x18000c938  call    WPP_SF_d
0x18000c93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c944  jmp     short loc_18000C8EE
0x18000c946  test    byte ptr [rcx+6Ch], 1
0x18000c94a  jz      loc_18000C834
0x18000c950  mov     rcx, [rcx+60h]
0x18000c954  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c95b  mov     edx, 11h
0x18000c960  call    WPP_SF_
0x18000c965  jmp     loc_18000C834
0x18000c96a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0")
0x18000c96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c976  mov     edi, 3EBh
0x18000c97b  jmp     loc_18000C8EE
0x18000c980  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c985  call    cs:__imp_SetLastError
0x18000c98b  xor     ebx, ebx
0x18000c98d  jmp     short loc_18000C99A
0x18000c98f  mov     ecx, 8; dwErrCode
0x18000c994  call    cs:__imp_SetLastError
0x18000c99a  call    cs:__imp_GetLastError
0x18000c9a0  mov     edi, eax
0x18000c9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9a9  cmp     rcx, rbp
0x18000c9ac  jz      short loc_18000C9D9
0x18000c9ae  cmp     byte ptr [rcx+69h], 1
0x18000c9b2  jb      short loc_18000C9D9
0x18000c9b4  test    byte ptr [rcx+6Ch], 1
0x18000c9b8  jz      short loc_18000C9D9
0x18000c9ba  mov     rcx, [rcx+60h]
0x18000c9be  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000c9c5  mov     edx, 13h
0x18000c9ca  mov     r9d, eax
0x18000c9cd  call    WPP_SF_d
0x18000c9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9d9  test    rbx, rbx
0x18000c9dc  jz      loc_18000C8E9
0x18000c9e2  jmp     short loc_18000CA26
0x18000c9e4  call    cs:__imp_GetLastError
0x18000c9ea  mov     edi, eax
0x18000c9ec  cmp     eax, 7Ah ; 'z'
0x18000c9ef  jnz     short loc_18000C9F6
0x18000c9f1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwRetCode != 122L")
0x18000c9f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9fd  cmp     rcx, rbp
0x18000ca00  jz      short loc_18000CA26
0x18000ca02  cmp     byte ptr [rcx+69h], 1
0x18000ca06  jb      short loc_18000CA26
0x18000ca08  test    byte ptr [rcx+6Ch], 1
0x18000ca0c  jz      short loc_18000CA26
0x18000ca0e  mov     rcx, [rcx+60h]
0x18000ca12  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000ca19  mov     edx, 14h
0x18000ca1e  mov     r9d, edi
0x18000ca21  call    WPP_SF_d
0x18000ca26  mov     rcx, rbx
0x18000ca29  call    FreeWLMem
0x18000ca2e  jmp     loc_18000C8E2
0x18000ca33  test    byte ptr [rcx+6Ch], 1
0x18000ca37  jz      loc_18000C8FD
0x18000ca3d  mov     rcx, [rcx+60h]
0x18000ca41  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18000ca48  mov     edx, 15h
0x18000ca4d  mov     r9d, edi
0x18000ca50  call    WPP_SF_d
0x18000ca55  jmp     loc_18000C8FD
```
