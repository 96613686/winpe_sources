# AllowSAS(void)

- ea: `0x14008cd28`
- end: `0x14008d01c`
- name: `?AllowSAS@@YAHXZ`
- size: `756`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14008e0f0`

## callees

- `0x1400057f4`
- `0x140014370`
- `0x140041c34`
- `0x14008cd28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008cd6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008cd6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008cf56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008cf56`
- `RPCRT4!RpcRevertToSelf` at `0x14008cf94`
- `RPCRT4!RpcRevertToSelf` at `0x14008cf94`
- `RPCRT4!RpcImpersonateClient` at `0x14008cd9b`
- `RPCRT4!RpcImpersonateClient` at `0x14008cd9b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14008cd5c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14008cd5c`
- `ntdll!NtOpenThreadToken` at `0x14008cdbe`
- `ntdll!NtOpenThreadToken` at `0x14008cdbe`
- `ntdll!RtlGetActiveConsoleId` at `0x14008cd43`
- `ntdll!RtlGetActiveConsoleId` at `0x14008cd43`
- `ntdll!NtQueryInformationToken` at `0x14008cde6`
- `ntdll!NtQueryInformationToken` at `0x14008ce87`
- `ntdll!NtQueryInformationToken` at `0x14008cde6`
- `ntdll!NtQueryInformationToken` at `0x14008ce87`

## pseudocode

```c
__int64 AllowSAS(void)
{
  ULONG SessionId; // ebx
  unsigned int v1; // esi
  unsigned int v2; // eax
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  __int64 v5; // r9
  CUser *v6; // rcx
  __int64 v7; // rdx
  unsigned int TokenInformation; // [rsp+60h] [rbp+28h] BYREF
  unsigned int Pid; // [rsp+68h] [rbp+30h] BYREF
  ULONG ReturnLength; // [rsp+70h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+40h] BYREF

  SessionId = NtCurrentPeb()->SessionId;
  if ( (unsigned int)RtlGetActiveConsoleId() != SessionId )
    return 1;
  v1 = 0;
  Pid = 0;
  v2 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v2);
    }
    return v1;
  }
  if ( Pid == GetCurrentProcessId() )
    return 1;
  ReturnLength = 4;
  Pid = CMachine::GetMachinePolicy(qword_1400D2548, L"SoftwareSASGeneration", 2u);
  if ( !RpcImpersonateClient(0) )
  {
    TokenHandle = 0;
    TokenInformation = 0;
    v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_9372b429430230a2303f99774b8cd740_Traceguids,
          (unsigned int)v3);
      }
      goto LABEL_41;
    }
    ReturnLength = 4;
    v4 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_9372b429430230a2303f99774b8cd740_Traceguids,
          (unsigned int)v4);
      }
      goto LABEL_36;
    }
    v5 = Pid;
    if ( (Pid & 1) != 0 )
    {
      if ( !TokenInformation )
        goto LABEL_18;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_14:
        if ( (v5 & 2) != 0 )
        {
          v5 = TokenInformation;
          if ( TokenInformation == NtCurrentPeb()->SessionId )
          {
            TokenInformation = 0;
            ReturnLength = 4;
            if ( NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength) < 0 )
            {
LABEL_36:
              CloseHandle(TokenHandle);
LABEL_41:
              RpcRevertToSelf();
              return v1;
            }
            if ( !TokenInformation )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9372b429430230a2303f99774b8cd740_Traceguids);
              }
              goto LABEL_36;
            }
LABEL_18:
            v1 = 1;
            goto LABEL_36;
          }
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_36;
          }
          v7 = 12;
        }
        else
        {
          if ( v6 == (CUser *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 4u )
            goto LABEL_36;
          v7 = 13;
        }
        WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v5);
        goto LABEL_36;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_9372b429430230a2303f99774b8cd740_Traceguids,
        TokenInformation);
      v5 = Pid;
    }
    v6 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9372b429430230a2303f99774b8cd740_Traceguids);
  }
  return v1;
}

```

## disassembly

```asm
0x14008cd28  push    rbp
0x14008cd2a  push    rbx
0x14008cd2b  push    rsi
0x14008cd2c  push    rdi
0x14008cd2d  mov     rbp, rsp
0x14008cd30  sub     rsp, 38h
0x14008cd34  mov     rax, gs:60h
0x14008cd3d  mov     ebx, [rax+2C0h]
0x14008cd43  call    cs:__imp_RtlGetActiveConsoleId
0x14008cd49  cmp     eax, ebx
0x14008cd4b  jnz     loc_14008D00C
0x14008cd51  xor     esi, esi
0x14008cd53  lea     rdx, [rbp+Pid]; Pid
0x14008cd57  xor     ecx, ecx; Binding
0x14008cd59  mov     [rbp+Pid], esi
0x14008cd5c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14008cd62  test    eax, eax
0x14008cd64  jnz     loc_14008CFD1
0x14008cd6a  call    cs:__imp_GetCurrentProcessId
0x14008cd70  cmp     [rbp+Pid], eax
0x14008cd73  jz      loc_14008D00C
0x14008cd79  mov     rcx, cs:qword_1400D2548; this
0x14008cd80  lea     ebx, [rsi+4]
0x14008cd83  lea     r8d, [rsi+2]; unsigned int
0x14008cd87  mov     [rbp+arg_10], ebx
0x14008cd8a  lea     rdx, aSoftwaresasgen_0; "SoftwareSASGeneration"
0x14008cd91  call    ?GetMachinePolicy@CMachine@@QEAAKPEBGK@Z; CMachine::GetMachinePolicy(ushort const *,ulong)
0x14008cd96  xor     ecx, ecx; BindingHandle
0x14008cd98  mov     [rbp+Pid], eax
0x14008cd9b  call    cs:__imp_RpcImpersonateClient
0x14008cda1  test    eax, eax
0x14008cda3  jnz     loc_14008CF9C
0x14008cda9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14008cdad  mov     [rbp+TokenHandle], rsi
0x14008cdb1  mov     r8b, 1; OpenAsSelf
0x14008cdb4  mov     [rbp+TokenInformation], esi
0x14008cdb7  lea     edx, [rsi+8]; DesiredAccess
0x14008cdba  lea     rcx, [rsi-2]; ThreadHandle
0x14008cdbe  call    cs:__imp_NtOpenThreadToken
0x14008cdc4  test    eax, eax
0x14008cdc6  js      loc_14008CF5E
0x14008cdcc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14008cdd0  lea     rax, [rbp+arg_10]
0x14008cdd4  mov     r9d, ebx; TokenInformationLength
0x14008cdd7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14008cddc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14008cde0  mov     [rbp+arg_10], ebx
0x14008cde3  lea     edx, [rsi+0Ch]; TokenInformationClass
0x14008cde6  call    cs:__imp_NtQueryInformationToken
0x14008cdec  lea     rdi, WPP_GLOBAL_Control
0x14008cdf3  test    eax, eax
0x14008cdf5  js      loc_14008CF23
0x14008cdfb  mov     r9d, [rbp+Pid]
0x14008cdff  test    r9b, 1
0x14008ce03  jz      short loc_14008CE41
0x14008ce05  mov     eax, [rbp+TokenInformation]
0x14008ce08  test    eax, eax
0x14008ce0a  jz      loc_14008CE9A
0x14008ce10  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce17  cmp     rcx, rdi
0x14008ce1a  jz      short loc_14008CE48
0x14008ce1c  test    byte ptr [rcx+1Ch], 1
0x14008ce20  jz      short loc_14008CE48
0x14008ce22  cmp     [rcx+19h], bl
0x14008ce25  jb      short loc_14008CE48
0x14008ce27  mov     rcx, [rcx+10h]
0x14008ce2b  lea     edx, [rsi+0Ah]
0x14008ce2e  mov     r9d, eax
0x14008ce31  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008ce38  call    WPP_SF_d
0x14008ce3d  mov     r9d, [rbp+Pid]
0x14008ce41  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce48  test    r9b, 2
0x14008ce4c  jz      loc_14008CEFC
0x14008ce52  mov     rax, gs:60h
0x14008ce5b  mov     r9d, [rbp+TokenInformation]
0x14008ce5f  cmp     r9d, [rax+2C0h]
0x14008ce66  jnz     short loc_14008CEDE
0x14008ce68  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14008ce6c  lea     rax, [rbp+arg_10]
0x14008ce70  mov     r9d, ebx; TokenInformationLength
0x14008ce73  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14008ce78  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14008ce7c  mov     [rbp+TokenInformation], esi
0x14008ce7f  mov     edx, 1Ah; TokenInformationClass
0x14008ce84  mov     [rbp+arg_10], ebx
0x14008ce87  call    cs:__imp_NtQueryInformationToken
0x14008ce8d  test    eax, eax
0x14008ce8f  js      loc_14008CF52
0x14008ce95  cmp     [rbp+TokenInformation], esi
0x14008ce98  jz      short loc_14008CEA4
0x14008ce9a  mov     esi, 1
0x14008ce9f  jmp     loc_14008CF52
0x14008cea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ceab  cmp     rcx, rdi
0x14008ceae  jz      loc_14008CF52
0x14008ceb4  test    byte ptr [rcx+1Ch], 1
0x14008ceb8  jz      loc_14008CF52
0x14008cebe  cmp     [rcx+19h], bl
0x14008cec1  jb      loc_14008CF52
0x14008cec7  mov     rcx, [rcx+10h]
0x14008cecb  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008ced2  mov     edx, 0Bh
0x14008ced7  call    WPP_SF_
0x14008cedc  jmp     short loc_14008CF52
0x14008cede  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cee5  cmp     rcx, rdi
0x14008cee8  jz      short loc_14008CF52
0x14008ceea  test    byte ptr [rcx+1Ch], 1
0x14008ceee  jz      short loc_14008CF52
0x14008cef0  cmp     [rcx+19h], bl
0x14008cef3  jb      short loc_14008CF52
0x14008cef5  mov     edx, 0Ch
0x14008cefa  jmp     short loc_14008CF11
0x14008cefc  cmp     rcx, rdi
0x14008ceff  jz      short loc_14008CF52
0x14008cf01  test    byte ptr [rcx+1Ch], 1
0x14008cf05  jz      short loc_14008CF52
0x14008cf07  cmp     [rcx+19h], bl
0x14008cf0a  jb      short loc_14008CF52
0x14008cf0c  mov     edx, 0Dh
0x14008cf11  mov     rcx, [rcx+10h]
0x14008cf15  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008cf1c  call    WPP_SF_d
0x14008cf21  jmp     short loc_14008CF52
0x14008cf23  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cf2a  cmp     rcx, rdi
0x14008cf2d  jz      short loc_14008CF52
0x14008cf2f  test    byte ptr [rcx+1Ch], 1
0x14008cf33  jz      short loc_14008CF52
0x14008cf35  cmp     [rcx+19h], bl
0x14008cf38  jb      short loc_14008CF52
0x14008cf3a  mov     rcx, [rcx+10h]
0x14008cf3e  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008cf45  mov     edx, 0Eh
0x14008cf4a  mov     r9d, eax
0x14008cf4d  call    WPP_SF_d
0x14008cf52  mov     rcx, [rbp+TokenHandle]; hObject
0x14008cf56  call    cs:__imp_CloseHandle
0x14008cf5c  jmp     short loc_14008CF94
0x14008cf5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cf65  lea     rdi, WPP_GLOBAL_Control
0x14008cf6c  cmp     rcx, rdi
0x14008cf6f  jz      short loc_14008CF94
0x14008cf71  test    byte ptr [rcx+1Ch], 1
0x14008cf75  jz      short loc_14008CF94
0x14008cf77  cmp     [rcx+19h], bl
0x14008cf7a  jb      short loc_14008CF94
0x14008cf7c  mov     rcx, [rcx+10h]
0x14008cf80  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008cf87  mov     edx, 0Fh
0x14008cf8c  mov     r9d, eax
0x14008cf8f  call    WPP_SF_d
0x14008cf94  call    cs:__imp_RpcRevertToSelf
0x14008cf9a  jmp     short loc_14008D011
0x14008cf9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cfa3  lea     rdi, WPP_GLOBAL_Control
0x14008cfaa  cmp     rcx, rdi
0x14008cfad  jz      short loc_14008D011
0x14008cfaf  test    byte ptr [rcx+1Ch], 1
0x14008cfb3  jz      short loc_14008D011
0x14008cfb5  cmp     [rcx+19h], bl
0x14008cfb8  jb      short loc_14008D011
0x14008cfba  mov     rcx, [rcx+10h]
0x14008cfbe  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008cfc5  mov     edx, 10h
0x14008cfca  call    WPP_SF_
0x14008cfcf  jmp     short loc_14008D011
0x14008cfd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cfd8  lea     rdi, WPP_GLOBAL_Control
0x14008cfdf  cmp     rcx, rdi
0x14008cfe2  jz      short loc_14008D011
0x14008cfe4  test    byte ptr [rcx+1Ch], 1
0x14008cfe8  jz      short loc_14008D011
0x14008cfea  mov     ebx, 4
0x14008cfef  cmp     [rcx+19h], bl
0x14008cff2  jb      short loc_14008D011
0x14008cff4  mov     rcx, [rcx+10h]
0x14008cff8  lea     edx, [rbx+0Dh]
0x14008cffb  mov     r9d, eax
0x14008cffe  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d005  call    WPP_SF_d
0x14008d00a  jmp     short loc_14008D011
0x14008d00c  mov     esi, 1
0x14008d011  mov     eax, esi
0x14008d013  add     rsp, 38h
0x14008d017  pop     rdi
0x14008d018  pop     rsi
0x14008d019  pop     rbx
0x14008d01a  pop     rbp
0x14008d01b  retn
```
