# ConfigureMachineAlias

- ea: `0x18003b728`
- end: `0x18003b85a`
- name: `ConfigureMachineAlias`
- size: `306`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009470`
- `0x180009a20`
- `0x180015500`
- `0x18002f0fc`
- `0x18002f8b8`

## callees

- `0x18000ae90`
- `0x18001e80c`
- `0x18003b728`
- `0x18003b860`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b787`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b787`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b83a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b83a`
- `ntdll!RtlInitUnicodeString` at `0x18003b770`
- `ntdll!RtlInitUnicodeString` at `0x18003b770`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18003b80f`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18003b80f`
- `SspiCli!LsaFreeReturnBuffer` at `0x18003b827`
- `SspiCli!LsaFreeReturnBuffer` at `0x18003b827`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003b831`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003b831`

## pseudocode

```c
__int64 __fastcall ConfigureMachineAlias(PCWSTR SourceString, char a2)
{
  int v2; // ebx
  ULONG v3; // esi
  char *v4; // rax
  char *v5; // rdi
  __int64 v7; // rcx
  int LsaHandleAndPackageId; // ebx
  HANDLE LsaHandle; // [rsp+40h] [rbp-20h] BYREF
  PVOID Buffer; // [rsp+48h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  ULONG AuthenticationPackage; // [rsp+98h] [rbp+38h] BYREF
  int ProtocolStatus; // [rsp+A0h] [rbp+40h] BYREF
  ULONG ReturnBufferLength; // [rsp+A8h] [rbp+48h] BYREF

  Buffer = 0;
  LsaHandle = 0;
  AuthenticationPackage = 0;
  ProtocolStatus = 0;
  ReturnBufferLength = 0;
  v2 = 2 - (a2 != 0);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v3 = DestinationString.Length + 24;
  v4 = (char *)LocalAlloc(0x40u, v3);
  v5 = v4;
  if ( !v4 )
    return 1450;
  memset_0(v4, 0, v3);
  *(_DWORD *)v5 = 13;
  *((_DWORD *)v5 + 1) = v2;
  *(struct _UNICODE_STRING *)(v5 + 8) = DestinationString;
  *((_QWORD *)v5 + 2) = v5 + 24;
  memcpy_0(v5 + 24, DestinationString.Buffer, DestinationString.Length);
  LsaHandleAndPackageId = GetLsaHandleAndPackageId(v7, &LsaHandle, &AuthenticationPackage);
  if ( LsaHandleAndPackageId >= 0 )
  {
    LsaHandleAndPackageId = LsaCallAuthenticationPackage(
                              LsaHandle,
                              AuthenticationPackage,
                              v5,
                              v3,
                              &Buffer,
                              &ReturnBufferLength,
                              &ProtocolStatus);
    if ( LsaHandleAndPackageId >= 0 )
    {
      LsaHandleAndPackageId = ProtocolStatus;
      if ( Buffer )
        LsaFreeReturnBuffer(Buffer);
    }
    LsaDeregisterLogonProcess(LsaHandle);
  }
  LocalFree(v5);
  if ( LsaHandleAndPackageId < 0 )
    return NetpNtStatusToApiStatus(LsaHandleAndPackageId);
  else
    return 0;
}

```

## disassembly

```asm
0x18003b728  push    rbp
0x18003b72a  push    rbx
0x18003b72b  push    rsi
0x18003b72c  push    rdi
0x18003b72d  push    r14
0x18003b72f  mov     rbp, rsp
0x18003b732  sub     rsp, 60h
0x18003b736  neg     dl
0x18003b738  mov     [rbp+Buffer], 0
0x18003b740  xorps   xmm0, xmm0
0x18003b743  mov     [rbp+LsaHandle], 0
0x18003b74b  sbb     ebx, ebx
0x18003b74d  mov     [rbp+AuthenticationPackage], 0
0x18003b754  mov     rdx, rcx; SourceString
0x18003b757  mov     [rbp+arg_10], 0
0x18003b75e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003b762  mov     [rbp+arg_18], 0
0x18003b769  add     ebx, 2
0x18003b76c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003b770  call    cs:__imp_RtlInitUnicodeString
0x18003b776  movzx   esi, [rbp+DestinationString.Length]
0x18003b77a  mov     ecx, 40h ; '@'; uFlags
0x18003b77f  add     esi, 18h
0x18003b782  mov     edx, esi; uBytes
0x18003b784  mov     r14d, esi
0x18003b787  call    cs:__imp_LocalAlloc
0x18003b78d  mov     rdi, rax
0x18003b790  test    rax, rax
0x18003b793  jnz     short loc_18003B79F
0x18003b795  mov     eax, 5AAh
0x18003b79a  jmp     loc_18003B84F
0x18003b79f  mov     r8, r14; Size
0x18003b7a2  xor     edx, edx; Val
0x18003b7a4  mov     rcx, rdi; void *
0x18003b7a7  call    memset_0
0x18003b7ac  mov     dword ptr [rdi], 0Dh
0x18003b7b2  lea     rcx, [rdi+18h]; void *
0x18003b7b6  mov     [rdi+4], ebx
0x18003b7b9  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x18003b7bd  movdqu  xmmword ptr [rdi+8], xmm0
0x18003b7c2  mov     [rdi+10h], rcx
0x18003b7c6  movzx   r8d, [rbp+DestinationString.Length]; Size
0x18003b7cb  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x18003b7cf  call    memcpy_0
0x18003b7d4  lea     r8, [rbp+AuthenticationPackage]
0x18003b7d8  lea     rdx, [rbp+LsaHandle]
0x18003b7dc  call    GetLsaHandleAndPackageId
0x18003b7e1  mov     ebx, eax
0x18003b7e3  test    eax, eax
0x18003b7e5  js      short loc_18003B837
0x18003b7e7  mov     edx, [rbp+AuthenticationPackage]; AuthenticationPackage
0x18003b7ea  lea     rax, [rbp+arg_10]
0x18003b7ee  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18003b7f2  mov     r9d, esi; SubmitBufferLength
0x18003b7f5  mov     [rsp+60h+ProtocolStatus], rax; ProtocolStatus
0x18003b7fa  mov     r8, rdi; ProtocolSubmitBuffer
0x18003b7fd  lea     rax, [rbp+arg_18]
0x18003b801  mov     [rsp+60h+ReturnBufferLength], rax; ReturnBufferLength
0x18003b806  lea     rax, [rbp+Buffer]
0x18003b80a  mov     [rsp+60h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x18003b80f  call    cs:__imp_LsaCallAuthenticationPackage
0x18003b815  mov     ebx, eax
0x18003b817  test    eax, eax
0x18003b819  js      short loc_18003B82D
0x18003b81b  mov     rcx, [rbp+Buffer]; Buffer
0x18003b81f  mov     ebx, [rbp+arg_10]
0x18003b822  test    rcx, rcx
0x18003b825  jz      short loc_18003B82D
0x18003b827  call    cs:__imp_LsaFreeReturnBuffer
0x18003b82d  mov     rcx, [rbp+LsaHandle]; LsaHandle
0x18003b831  call    cs:__imp_LsaDeregisterLogonProcess
0x18003b837  mov     rcx, rdi; hMem
0x18003b83a  call    cs:__imp_LocalFree
0x18003b840  test    ebx, ebx
0x18003b842  js      short loc_18003B848
0x18003b844  xor     eax, eax
0x18003b846  jmp     short loc_18003B84F
0x18003b848  mov     ecx, ebx; Status
0x18003b84a  call    NetpNtStatusToApiStatus
0x18003b84f  add     rsp, 60h
0x18003b853  pop     r14
0x18003b855  pop     rdi
0x18003b856  pop     rsi
0x18003b857  pop     rbx
0x18003b858  pop     rbp
0x18003b859  retn
```
