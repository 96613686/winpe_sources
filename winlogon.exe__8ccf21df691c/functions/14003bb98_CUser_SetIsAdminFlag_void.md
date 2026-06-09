# CUser::SetIsAdminFlag(void)

- ea: `0x14003bb98`
- end: `0x14003bce2`
- name: `?SetIsAdminFlag@CUser@@AEAAKXZ`
- size: `330`
- prototype: `unsigned int __fastcall(CUser *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140081d40`

## callees

- `0x1400057f4`
- `0x14003bb98`
- `0x1400993e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bc04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003bcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009e6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003bcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009e6ce`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14003bbd0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14003bbd0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14003bbfa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14003bbfa`
- `ntdll!RtlNtStatusToDosError` at `0x14003bc7c`
- `ntdll!RtlNtStatusToDosError` at `0x14003bc7c`

## pseudocode

```c
__int64 __fastcall CUser::SetIsAdminFlag(CUser *this)
{
  DWORD LastError; // ebx
  CUser *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  NTSTATUS v6; // eax
  unsigned int v7; // esi
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  LastError = 0;
  TokenHandle = 0;
  if ( !DuplicateTokenEx(*((HANDLE *)this + 17), 0x2000Cu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
    LastError = GetLastError();
    goto LABEL_16;
  }
  if ( CheckTokenMembership(TokenHandle, g_pSidAdmin, (PBOOL)this + 38) )
  {
    if ( !*((_DWORD *)this + 38) )
    {
      v9 = 0;
      v6 = LUAGetUserType(TokenHandle, (int *)&v9);
      v7 = v6;
      if ( v6 >= 0 )
      {
        *((_DWORD *)this + 38) = v9 <= 1;
      }
      else
      {
        LastError = RtlNtStatusToDosError(v6);
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v4 = 68;
          v5 = v7;
          goto LABEL_8;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v4 = 67;
      v5 = LastError;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v5);
    }
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x14003bb98  mov     r11, rsp
0x14003bb9b  mov     [r11+8], rbx
0x14003bb9f  mov     [r11+20h], rsi
0x14003bba3  push    rdi
0x14003bba4  sub     rsp, 30h
0x14003bba8  mov     rdi, rcx
0x14003bbab  xor     ebx, ebx
0x14003bbad  mov     [r11+18h], rbx
0x14003bbb1  lea     rax, [r11+18h]
0x14003bbb5  mov     [r11-10h], rax
0x14003bbb9  lea     r9d, [rbx+2]; ImpersonationLevel
0x14003bbbd  mov     [r11-18h], r9d
0x14003bbc1  xor     r8d, r8d; lpTokenAttributes
0x14003bbc4  mov     edx, 2000Ch; dwDesiredAccess
0x14003bbc9  mov     rcx, [rcx+88h]; hExistingToken
0x14003bbd0  call    cs:__imp_DuplicateTokenEx
0x14003bbd6  test    eax, eax
0x14003bbd8  jnz     short loc_14003BBE7
0x14003bbda  call    cs:__imp_GetLastError
0x14003bbe0  mov     ebx, eax
0x14003bbe2  jmp     loc_14003BCC0
0x14003bbe7  lea     r8, [rdi+98h]; IsMember
0x14003bbee  mov     rdx, cs:g_pSidAdmin; SidToCheck
0x14003bbf5  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x14003bbfa  call    cs:__imp_CheckTokenMembership
0x14003bc00  test    eax, eax
0x14003bc02  jnz     short loc_14003BC54
0x14003bc04  call    cs:__imp_GetLastError
0x14003bc0a  mov     ebx, eax
0x14003bc0c  lea     rax, WPP_GLOBAL_Control
0x14003bc13  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bc1a  cmp     rcx, rax
0x14003bc1d  jz      loc_14003BCC0
0x14003bc23  test    dword ptr [rcx+1Ch], 1000h
0x14003bc2a  jz      loc_14003BCC0
0x14003bc30  cmp     byte ptr [rcx+19h], 4
0x14003bc34  jb      loc_14003BCC0
0x14003bc3a  mov     edx, 43h ; 'C'
0x14003bc3f  mov     r9d, ebx
0x14003bc42  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003bc49  mov     rcx, [rcx+10h]
0x14003bc4d  call    WPP_SF_d
0x14003bc52  jmp     short loc_14003BCC0
0x14003bc54  cmp     dword ptr [rdi+98h], 0
0x14003bc5b  jnz     short loc_14003BCC0
0x14003bc5d  mov     [rsp+38h+arg_8], 0
0x14003bc65  lea     rdx, [rsp+38h+arg_8]
0x14003bc6a  mov     rcx, [rsp+38h+TokenHandle]
0x14003bc6f  call    LUAGetUserType
0x14003bc74  mov     esi, eax
0x14003bc76  test    eax, eax
0x14003bc78  jns     short loc_14003BCB0
0x14003bc7a  mov     ecx, eax; Status
0x14003bc7c  call    cs:__imp_RtlNtStatusToDosError
0x14003bc82  mov     ebx, eax
0x14003bc84  lea     rax, WPP_GLOBAL_Control
0x14003bc8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bc92  cmp     rcx, rax
0x14003bc95  jz      short loc_14003BCC0
0x14003bc97  test    dword ptr [rcx+1Ch], 1000h
0x14003bc9e  jz      short loc_14003BCC0
0x14003bca0  cmp     byte ptr [rcx+19h], 4
0x14003bca4  jb      short loc_14003BCC0
0x14003bca6  mov     edx, 44h ; 'D'
0x14003bcab  mov     r9d, esi
0x14003bcae  jmp     short loc_14003BC42
0x14003bcb0  xor     eax, eax
0x14003bcb2  cmp     [rsp+38h+arg_8], 1
0x14003bcb7  setbe   al
0x14003bcba  mov     [rdi+98h], eax
0x14003bcc0  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x14003bcc5  test    rcx, rcx
0x14003bcc8  jz      short loc_14003BCD0
0x14003bcca  call    cs:__imp_CloseHandle
0x14003bcd0  mov     eax, ebx
0x14003bcd2  mov     rbx, [rsp+38h+arg_0]
0x14003bcd7  mov     rsi, [rsp+38h+arg_18]
0x14003bcdc  add     rsp, 30h
0x14003bce0  pop     rdi
0x14003bce1  retn
0x14009e6bc  push    rbp
0x14009e6be  sub     rsp, 30h
0x14009e6c2  mov     rbp, rdx
0x14009e6c5  mov     rcx, [rbp+50h]; hObject
0x14009e6c9  test    rcx, rcx
0x14009e6cc  jz      short loc_14009E6D5
0x14009e6ce  call    cs:__imp_CloseHandle
0x14009e6d4  nop
0x14009e6d5  add     rsp, 30h
0x14009e6d9  pop     rbp
0x14009e6da  retn
```
