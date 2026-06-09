# CreateLowPrivilegedTokenForScreenSaver(_WLSM_GLOBAL_CONTEXT *,void * *)

- ea: `0x140078b0c`
- end: `0x140078df6`
- name: `?CreateLowPrivilegedTokenForScreenSaver@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEAPEAX@Z`
- size: `746`
- prototype: `unsigned int __fastcall(struct _WLSM_GLOBAL_CONTEXT *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x140006c3c`

## callees

- `0x1400057f4`
- `0x14000fb98`
- `0x1400198e0`
- `0x14001a200`
- `0x140078b0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140078b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140078b85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140078c0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140078c0c`
- `ntdll!NtFilterToken` at `0x140078bff`
- `ntdll!NtFilterToken` at `0x140078bff`
- `ntdll!NtQueryInformationToken` at `0x140078c7b`
- `ntdll!NtQueryInformationToken` at `0x140078d14`
- `ntdll!NtQueryInformationToken` at `0x140078c7b`
- `ntdll!NtQueryInformationToken` at `0x140078d14`
- `ntdll!RtlNtStatusToDosError` at `0x140078c18`
- `ntdll!RtlNtStatusToDosError` at `0x140078c8a`
- `ntdll!RtlNtStatusToDosError` at `0x140078d20`
- `ntdll!RtlNtStatusToDosError` at `0x140078c18`
- `ntdll!RtlNtStatusToDosError` at `0x140078c8a`
- `ntdll!RtlNtStatusToDosError` at `0x140078d20`
- `ntdll!NtClose` at `0x140078dda`
- `ntdll!NtClose` at `0x14009fc3d`
- `ntdll!NtClose` at `0x140078dda`
- `ntdll!NtClose` at `0x14009fc3d`
- `SspiCli!LogonUserExExW` at `0x140078b7b`
- `SspiCli!LogonUserExExW` at `0x140078b7b`

## string_xrefs

- `0x140078b74`: `LocalService`

## pseudocode

```c
__int64 __fastcall CreateLowPrivilegedTokenForScreenSaver(struct _WLSM_GLOBAL_CONTEXT *a1, void **a2)
{
  PSID *v4; // rdi
  ULONG LastError; // ebx
  CUser *v6; // rcx
  __int64 v7; // rdx
  int v8; // ebx
  NTSTATUS v9; // eax
  int v10; // eax
  PSID *v12; // [rsp+68h] [rbp-30h] BYREF
  HANDLE ExistingTokenHandle[5]; // [rsp+70h] [rbp-28h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+B8h] [rbp+20h] BYREF

  ExistingTokenHandle[0] = 0;
  TokenHandle = 0;
  v4 = 0;
  v12 = 0;
  ReturnLength = 0;
  if ( (unsigned int)LogonUserExExW(L"LocalService", L"NT AUTHORITY", 0, 5, 0, 0, ExistingTokenHandle, 0, 0, 0, 0) )
  {
    v8 = NtFilterToken(ExistingTokenHandle[0], 1u, 0, 0, 0, &TokenHandle);
    CloseHandle(ExistingTokenHandle[0]);
    if ( v8 >= 0 )
    {
      v9 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &ReturnLength);
      if ( v9 == -1073741789 )
      {
        v4 = (PSID *)WLAlloc(ReturnLength);
        v12 = v4;
        if ( v4 )
        {
          v10 = NtQueryInformationToken(TokenHandle, TokenUser, v4, ReturnLength, &ReturnLength);
          if ( v10 >= 0 )
          {
            LastError = AddUserToWinsta(
                          *(HWINSTA *)(*((_QWORD *)a1 + 2) + 96LL),
                          *(void **)(*((_QWORD *)a1 + 2) + 104LL),
                          g_pSidLocalService,
                          *v4);
            if ( LastError )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = 16;
                goto LABEL_6;
              }
            }
            else
            {
              *a2 = TokenHandle;
              LastError = 0;
            }
          }
          else
          {
            LastError = RtlNtStatusToDosError(v10);
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v7 = 15;
              goto LABEL_6;
            }
          }
        }
        else
        {
          LastError = 14;
        }
      }
      else
      {
        LastError = RtlNtStatusToDosError(v9);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 14;
          goto LABEL_6;
        }
      }
    }
    else
    {
      LastError = RtlNtStatusToDosError(v8);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 13;
        goto LABEL_6;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 12;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_1371844a6ad3397c141e9ae77dbbce4b_Traceguids, LastError);
    }
  }
  if ( v4 )
    UHHeapFree(&v12);
  if ( TokenHandle && LastError )
    NtClose(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x140078b0c  mov     rax, rsp
0x140078b0f  mov     [rax+8], rbx
0x140078b13  push    rsi
0x140078b14  push    rdi
0x140078b15  push    r14
0x140078b17  sub     rsp, 80h
0x140078b1e  mov     rsi, rdx
0x140078b21  mov     r14, rcx
0x140078b24  mov     dword ptr [rax-38h], 57h ; 'W'
0x140078b2b  mov     qword ptr [rax-28h], 0
0x140078b33  mov     qword ptr [rax+20h], 0
0x140078b3b  xor     edi, edi
0x140078b3d  mov     [rax-30h], rdi
0x140078b41  mov     [rax+18h], edi
0x140078b44  mov     [rax-48h], rdi
0x140078b48  mov     [rax-50h], rdi
0x140078b4c  mov     [rax-58h], rdi
0x140078b50  mov     [rax-60h], rdi
0x140078b54  lea     rax, [rax-28h]
0x140078b58  mov     [rsp+98h+var_68], rax
0x140078b5d  mov     [rsp+98h+NewTokenHandle], rdi
0x140078b62  mov     dword ptr [rsp+98h+RestrictedSids], edi
0x140078b66  lea     r9d, [rdi+5]
0x140078b6a  xor     r8d, r8d
0x140078b6d  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x140078b74  lea     rcx, aLocalservice; "LocalService"
0x140078b7b  call    cs:__imp_LogonUserExExW
0x140078b81  test    eax, eax
0x140078b83  jnz     short loc_140078BDA
0x140078b85  call    cs:__imp_GetLastError
0x140078b8b  mov     ebx, eax
0x140078b8d  mov     [rsp+98h+var_38], eax
0x140078b91  lea     rax, WPP_GLOBAL_Control
0x140078b98  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b9f  cmp     rcx, rax
0x140078ba2  jz      loc_140078DBA
0x140078ba8  test    dword ptr [rcx+1Ch], 20000h
0x140078baf  jz      loc_140078DBA
0x140078bb5  cmp     byte ptr [rcx+19h], 2
0x140078bb9  jb      loc_140078DBA
0x140078bbf  lea     edx, [rdi+0Ch]
0x140078bc2  mov     r9d, ebx
0x140078bc5  lea     r8, WPP_1371844a6ad3397c141e9ae77dbbce4b_Traceguids
0x140078bcc  mov     rcx, [rcx+10h]
0x140078bd0  call    WPP_SF_d
0x140078bd5  jmp     loc_140078DBA
0x140078bda  lea     rax, [rsp+98h+TokenHandle]
0x140078be2  mov     [rsp+98h+NewTokenHandle], rax; NewTokenHandle
0x140078be7  mov     [rsp+98h+RestrictedSids], 0; RestrictedSids
0x140078bf0  xor     r9d, r9d; PrivilegesToDelete
0x140078bf3  xor     r8d, r8d; SidsToDisable
0x140078bf6  lea     edx, [r9+1]; Flags
0x140078bfa  mov     rcx, [rsp+98h+ExistingTokenHandle]; ExistingTokenHandle
0x140078bff  call    cs:__imp_NtFilterToken
0x140078c05  mov     ebx, eax
0x140078c07  mov     rcx, [rsp+98h+ExistingTokenHandle]; hObject
0x140078c0c  call    cs:__imp_CloseHandle
0x140078c12  test    ebx, ebx
0x140078c14  jns     short loc_140078C5C
0x140078c16  mov     ecx, ebx; Status
0x140078c18  call    cs:__imp_RtlNtStatusToDosError
0x140078c1e  mov     ebx, eax
0x140078c20  mov     [rsp+98h+var_38], eax
0x140078c24  lea     rax, WPP_GLOBAL_Control
0x140078c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140078c32  cmp     rcx, rax
0x140078c35  jz      loc_140078DBA
0x140078c3b  test    dword ptr [rcx+1Ch], 20000h
0x140078c42  jz      loc_140078DBA
0x140078c48  cmp     byte ptr [rcx+19h], 2
0x140078c4c  jb      loc_140078DBA
0x140078c52  mov     edx, 0Dh
0x140078c57  jmp     loc_140078BC2
0x140078c5c  lea     rax, [rsp+98h+ReturnLength]
0x140078c64  mov     [rsp+98h+RestrictedSids], rax; ReturnLength
0x140078c69  xor     r9d, r9d; TokenInformationLength
0x140078c6c  xor     r8d, r8d; TokenInformation
0x140078c6f  lea     edx, [r9+1]; TokenInformationClass
0x140078c73  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x140078c7b  call    cs:__imp_NtQueryInformationToken
0x140078c81  cmp     eax, 0C0000023h
0x140078c86  jz      short loc_140078CCE
0x140078c88  mov     ecx, eax; Status
0x140078c8a  call    cs:__imp_RtlNtStatusToDosError
0x140078c90  mov     ebx, eax
0x140078c92  mov     [rsp+98h+var_38], eax
0x140078c96  lea     rax, WPP_GLOBAL_Control
0x140078c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140078ca4  cmp     rcx, rax
0x140078ca7  jz      loc_140078DBA
0x140078cad  test    dword ptr [rcx+1Ch], 20000h
0x140078cb4  jz      loc_140078DBA
0x140078cba  cmp     byte ptr [rcx+19h], 2
0x140078cbe  jb      loc_140078DBA
0x140078cc4  mov     edx, 0Eh
0x140078cc9  jmp     loc_140078BC2
0x140078cce  mov     ecx, [rsp+98h+ReturnLength]; unsigned __int64
0x140078cd5  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x140078cda  mov     rdi, rax
0x140078cdd  mov     [rsp+98h+var_30], rax
0x140078ce2  test    rax, rax
0x140078ce5  jnz     short loc_140078CEF
0x140078ce7  lea     ebx, [rax+0Eh]
0x140078cea  jmp     loc_140078DB6
0x140078cef  lea     rax, [rsp+98h+ReturnLength]
0x140078cf7  mov     [rsp+98h+RestrictedSids], rax; ReturnLength
0x140078cfc  mov     r9d, [rsp+98h+ReturnLength]; TokenInformationLength
0x140078d04  mov     r8, rdi; TokenInformation
0x140078d07  mov     edx, 1; TokenInformationClass
0x140078d0c  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x140078d14  call    cs:__imp_NtQueryInformationToken
0x140078d1a  test    eax, eax
0x140078d1c  jns     short loc_140078D58
0x140078d1e  mov     ecx, eax; Status
0x140078d20  call    cs:__imp_RtlNtStatusToDosError
0x140078d26  mov     ebx, eax
0x140078d28  mov     [rsp+98h+var_38], eax
0x140078d2c  lea     rax, WPP_GLOBAL_Control
0x140078d33  mov     rcx, cs:WPP_GLOBAL_Control
0x140078d3a  cmp     rcx, rax
0x140078d3d  jz      short loc_140078DBA
0x140078d3f  test    dword ptr [rcx+1Ch], 20000h
0x140078d46  jz      short loc_140078DBA
0x140078d48  cmp     byte ptr [rcx+19h], 2
0x140078d4c  jb      short loc_140078DBA
0x140078d4e  mov     edx, 0Fh
0x140078d53  jmp     loc_140078BC2
0x140078d58  mov     rcx, [r14+10h]
0x140078d5c  mov     r9, [rdi]; PSID
0x140078d5f  mov     r8, cs:g_pSidLocalService; SourceSid
0x140078d66  mov     rdx, [rcx+68h]; void *
0x140078d6a  mov     rcx, [rcx+60h]; hObj
0x140078d6e  call    AddUserToWinsta
0x140078d73  mov     ebx, eax
0x140078d75  mov     [rsp+98h+var_38], eax
0x140078d79  test    eax, eax
0x140078d7b  jz      short loc_140078DA9
0x140078d7d  lea     rax, WPP_GLOBAL_Control
0x140078d84  mov     rcx, cs:WPP_GLOBAL_Control
0x140078d8b  cmp     rcx, rax
0x140078d8e  jz      short loc_140078DBA
0x140078d90  test    dword ptr [rcx+1Ch], 1000h
0x140078d97  jz      short loc_140078DBA
0x140078d99  cmp     byte ptr [rcx+19h], 2
0x140078d9d  jb      short loc_140078DBA
0x140078d9f  mov     edx, 10h
0x140078da4  jmp     loc_140078BC2
0x140078da9  mov     rax, [rsp+98h+TokenHandle]
0x140078db1  mov     [rsi], rax
0x140078db4  xor     ebx, ebx
0x140078db6  mov     [rsp+98h+var_38], ebx
0x140078dba  test    rdi, rdi
0x140078dbd  jz      short loc_140078DC9
0x140078dbf  lea     rcx, [rsp+98h+var_30]
0x140078dc4  call    UHHeapFree
0x140078dc9  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x140078dd1  test    rcx, rcx
0x140078dd4  jz      short loc_140078DE0
0x140078dd6  test    ebx, ebx
0x140078dd8  jz      short loc_140078DE0
0x140078dda  call    cs:__imp_NtClose
0x140078de0  mov     eax, ebx
0x140078de2  mov     rbx, [rsp+98h+arg_0]
0x140078dea  add     rsp, 80h
0x140078df1  pop     r14
0x140078df3  pop     rdi
0x140078df4  pop     rsi
0x140078df5  retn
0x14009fc11  push    rbp
0x14009fc13  sub     rsp, 60h
0x14009fc17  mov     rbp, rdx
0x14009fc1a  cmp     qword ptr [rbp+68h], 0
0x14009fc1f  jz      short loc_14009FC2B
0x14009fc21  lea     rcx, [rbp+68h]
0x14009fc25  call    UHHeapFree
0x14009fc2a  nop
0x14009fc2b  mov     rcx, [rbp+0B8h]; Handle
0x14009fc32  test    rcx, rcx
0x14009fc35  jz      short loc_14009FC44
0x14009fc37  cmp     dword ptr [rbp+60h], 0
0x14009fc3b  jz      short loc_14009FC44
0x14009fc3d  call    cs:__imp_NtClose
0x14009fc43  nop
0x14009fc44  add     rsp, 60h
0x14009fc48  pop     rbp
0x14009fc49  retn
```
