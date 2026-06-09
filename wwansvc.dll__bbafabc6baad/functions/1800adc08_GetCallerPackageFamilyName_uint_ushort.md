# GetCallerPackageFamilyName(uint *,ushort *)

- ea: `0x1800adc08`
- end: `0x1800add74`
- name: `?GetCallerPackageFamilyName@@YAKPEAIPEAG@Z`
- size: `364`
- prototype: `unsigned int __fastcall(UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800ae368`

## callees

- `0x180012300`
- `0x180016c50`
- `0x1800adc08`
- `0x1800adea8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800add00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800add00`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800adca5`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800adca5`
- `RPCRT4!RpcImpersonateClient` at `0x1800adc62`
- `RPCRT4!RpcImpersonateClient` at `0x1800adc62`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800add0c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800add0c`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800adcdb`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800adcdb`

## string_xrefs

- `0x1800adc76`: `RpcImpersonateClient failed, dwErr = 0x%8x`
- `0x1800adcb9`: `I_RpcOpenClientProcess failed, dwErr = 0x%8x`
- `0x1800add1f`: `Revert Impersonation failed, dwErr = 0x%8x`

## pseudocode

```c
__int64 __fastcall GetCallerPackageFamilyName(UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)
{
  RPC_STATUS v4; // eax
  __int64 v5; // rbx
  int v6; // ebp
  RPC_STATUS v7; // eax
  unsigned int v8; // eax
  RPC_STATUS v9; // eax
  void *ClientProcess; // [rsp+40h] [rbp+8h] BYREF

  ClientProcess = 0;
  if ( packageFamilyNameLength && (!*packageFamilyNameLength || packageFamilyName) )
  {
    *packageFamilyName = 0;
    WwanLog::Verbose("GetCallerPackageFamilyName", 0, L"PackageFamilyName length = %d", *packageFamilyNameLength);
    v4 = RpcImpersonateClient(0);
    if ( v4 )
    {
      v5 = WIN32_FROM_NTSTATUS(v4);
      WwanLog::Error("GetCallerPackageFamilyName", 0, L"RpcImpersonateClient failed, dwErr = 0x%8x", v5);
      v6 = 0;
      if ( (_DWORD)v5 )
        goto LABEL_17;
    }
    else
    {
      v6 = 1;
    }
    v7 = I_RpcOpenClientProcess(0, 0x400u, &ClientProcess);
    if ( !v7
      || (v5 = WIN32_FROM_NTSTATUS(v7),
          WwanLog::Error("GetCallerPackageFamilyName", 0, L"I_RpcOpenClientProcess failed, dwErr = 0x%8x", v5),
          !(_DWORD)v5) )
    {
      v8 = GetPackageFamilyName(ClientProcess, packageFamilyNameLength, packageFamilyName);
      LODWORD(v5) = v8;
      if ( v8 )
        WwanLog::Error("GetCallerPackageFamilyName", 0, L"GetPackageFamilyName failed, dwErr = 0x%8x", v8);
      CloseHandle(ClientProcess);
    }
    if ( v6 )
    {
      v9 = RpcRevertToSelfEx(0);
      if ( v9 )
      {
        v5 = WIN32_FROM_NTSTATUS(v9);
        WwanLog::Error("GetCallerPackageFamilyName", 0, L"Revert Impersonation failed, dwErr = 0x%8x", v5);
      }
    }
  }
  else
  {
    LODWORD(v5) = 87;
    WwanLog::Error("GetCallerPackageFamilyName", 0, L"Invalid parameters, dwErr = 0x%8x", 87);
  }
LABEL_17:
  WwanLog::Verbose("GetCallerPackageFamilyName", 0, L"dwErr = 0x%8x", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800adc08  mov     [rsp+arg_8], rbx
0x1800adc0d  mov     [rsp+arg_10], rbp
0x1800adc12  push    rsi
0x1800adc13  push    rdi
0x1800adc14  push    r14
0x1800adc16  sub     rsp, 20h
0x1800adc1a  mov     [rsp+38h+ClientProcess], 0
0x1800adc23  mov     r14, rdx
0x1800adc26  mov     rsi, rcx
0x1800adc29  test    rcx, rcx
0x1800adc2c  jz      loc_1800ADD2B
0x1800adc32  cmp     dword ptr [rcx], 0
0x1800adc35  jbe     short loc_1800ADC40
0x1800adc37  test    rdx, rdx
0x1800adc3a  jz      loc_1800ADD2B
0x1800adc40  xor     eax, eax
0x1800adc42  lea     rdi, aGetcallerpacka; "GetCallerPackageFamilyName"
0x1800adc49  mov     [rdx], ax
0x1800adc4c  lea     r8, aPackagefamilyn; "PackageFamilyName length = %d"
0x1800adc53  mov     r9d, [rcx]
0x1800adc56  xor     edx, edx; struct _GUID *
0x1800adc58  mov     rcx, rdi; char *
0x1800adc5b  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800adc60  xor     ecx, ecx; BindingHandle
0x1800adc62  call    cs:__imp_RpcImpersonateClient
0x1800adc68  test    eax, eax
0x1800adc6a  jz      short loc_1800ADC94
0x1800adc6c  mov     ecx, eax; int
0x1800adc6e  call    ?WIN32_FROM_NTSTATUS@@YAKJ@Z; WIN32_FROM_NTSTATUS(long)
0x1800adc73  mov     r9d, eax
0x1800adc76  lea     r8, aRpcimpersonate; "RpcImpersonateClient failed, dwErr = 0x"...
0x1800adc7d  xor     edx, edx; struct _GUID *
0x1800adc7f  mov     rcx, rdi; char *
0x1800adc82  mov     ebx, eax
0x1800adc84  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800adc89  xor     ebp, ebp
0x1800adc8b  test    ebx, ebx
0x1800adc8d  jz      short loc_1800ADC99
0x1800adc8f  jmp     loc_1800ADD4B
0x1800adc94  mov     ebp, 1
0x1800adc99  lea     r8, [rsp+38h+ClientProcess]; ClientProcess
0x1800adc9e  mov     edx, 400h; DesiredAccess
0x1800adca3  xor     ecx, ecx; Binding
0x1800adca5  call    cs:__imp_I_RpcOpenClientProcess
0x1800adcab  test    eax, eax
0x1800adcad  jz      short loc_1800ADCD0
0x1800adcaf  mov     ecx, eax; int
0x1800adcb1  call    ?WIN32_FROM_NTSTATUS@@YAKJ@Z; WIN32_FROM_NTSTATUS(long)
0x1800adcb6  mov     r9d, eax
0x1800adcb9  lea     r8, aIRpcopenclient; "I_RpcOpenClientProcess failed, dwErr = "...
0x1800adcc0  xor     edx, edx; struct _GUID *
0x1800adcc2  mov     rcx, rdi; char *
0x1800adcc5  mov     ebx, eax
0x1800adcc7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800adccc  test    ebx, ebx
0x1800adcce  jnz     short loc_1800ADD06
0x1800adcd0  mov     rcx, [rsp+38h+ClientProcess]; hProcess
0x1800adcd5  mov     r8, r14; packageFamilyName
0x1800adcd8  mov     rdx, rsi; packageFamilyNameLength
0x1800adcdb  call    cs:__imp_GetPackageFamilyName
0x1800adce1  mov     ebx, eax
0x1800adce3  test    eax, eax
0x1800adce5  jz      short loc_1800ADCFB
0x1800adce7  mov     r9d, eax
0x1800adcea  lea     r8, aGetpackagefami_0; "GetPackageFamilyName failed, dwErr = 0x"...
0x1800adcf1  xor     edx, edx; struct _GUID *
0x1800adcf3  mov     rcx, rdi; char *
0x1800adcf6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800adcfb  mov     rcx, [rsp+38h+ClientProcess]; hObject
0x1800add00  call    cs:__imp_CloseHandle
0x1800add06  test    ebp, ebp
0x1800add08  jz      short loc_1800ADD4B
0x1800add0a  xor     ecx, ecx; BindingHandle
0x1800add0c  call    cs:__imp_RpcRevertToSelfEx
0x1800add12  test    eax, eax
0x1800add14  jz      short loc_1800ADD4B
0x1800add16  mov     ecx, eax; int
0x1800add18  call    ?WIN32_FROM_NTSTATUS@@YAKJ@Z; WIN32_FROM_NTSTATUS(long)
0x1800add1d  mov     ebx, eax
0x1800add1f  lea     r8, aRevertImperson; "Revert Impersonation failed, dwErr = 0x"...
0x1800add26  mov     r9d, eax
0x1800add29  jmp     short loc_1800ADD41
0x1800add2b  mov     ebx, 57h ; 'W'
0x1800add30  lea     r8, aInvalidParamet_17; "Invalid parameters, dwErr = 0x%8x"
0x1800add37  mov     r9d, ebx
0x1800add3a  lea     rdi, aGetcallerpacka; "GetCallerPackageFamilyName"
0x1800add41  xor     edx, edx; struct _GUID *
0x1800add43  mov     rcx, rdi; char *
0x1800add46  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800add4b  mov     r9d, ebx
0x1800add4e  lea     r8, aDwerr0x8x_0; "dwErr = 0x%8x"
0x1800add55  xor     edx, edx; struct _GUID *
0x1800add57  mov     rcx, rdi; char *
0x1800add5a  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800add5f  mov     rbp, [rsp+38h+arg_10]
0x1800add64  mov     eax, ebx
0x1800add66  mov     rbx, [rsp+38h+arg_8]
0x1800add6b  add     rsp, 20h
0x1800add6f  pop     r14
0x1800add71  pop     rdi
0x1800add72  pop     rsi
0x1800add73  retn
```
