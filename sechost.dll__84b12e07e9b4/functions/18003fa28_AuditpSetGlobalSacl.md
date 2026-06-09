# AuditpSetGlobalSacl

- ea: `0x18003fa28`
- end: `0x18003fb41`
- name: `AuditpSetGlobalSacl`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003f760`

## callees

- `0x18003fa28`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003fafa`
- `ntdll!RtlNtStatusToDosError` at `0x18003fafa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fb14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fb14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa7e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003fa74`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003fa74`
- `RPCRT4!NdrClientCall3` at `0x18003fae9`
- `RPCRT4!NdrClientCall3` at `0x18003fae9`

## pseudocode

```c
bool __fastcall AuditpSetGlobalSacl(__int64 a1, struct _ACL *a2)
{
  DWORD LastError; // ebx
  NTSTATUS Pointer; // eax
  bool v4; // zf
  __int64 v6; // [rsp+60h] [rbp-28h] BYREF
  int v7; // [rsp+68h] [rbp-20h]

  LastError = 0;
  v6 = 0;
  v7 = 0;
  if ( !a2 || GetAclInformation(a2, &v6, 0xCu, AclSizeInformation) )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0, 0x67u, 0).Pointer;
    if ( Pointer < 0 )
      LastError = RtlNtStatusToDosError(Pointer);
  }
  else
  {
    LastError = GetLastError();
  }
  v4 = LastError == 0;
  if ( LastError )
  {
    SetLastError(LastError);
    return LastError == 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18003fa28  mov     r11, rsp
0x18003fa2b  mov     [r11+18h], rbx
0x18003fa2f  mov     [r11+20h], rsi
0x18003fa33  push    rdi
0x18003fa34  sub     rsp, 80h
0x18003fa3b  mov     rax, cs:__security_cookie
0x18003fa42  xor     rax, rsp
0x18003fa45  mov     [rsp+88h+var_18], rax
0x18003fa4a  mov     rdi, rdx
0x18003fa4d  mov     rsi, rcx
0x18003fa50  xor     ebx, ebx
0x18003fa52  xor     eax, eax
0x18003fa54  mov     [r11-28h], rax
0x18003fa58  mov     [rsp+88h+var_20], eax
0x18003fa5c  mov     dword ptr [rsp+88h+var_58+4], eax
0x18003fa60  test    rdx, rdx
0x18003fa63  jz      short loc_18003FA9E
0x18003fa65  lea     r9d, [rbx+2]; dwAclInformationClass
0x18003fa69  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x18003fa6d  lea     rdx, [r11-28h]; pAclInformation
0x18003fa71  mov     rcx, rdi; pAcl
0x18003fa74  call    cs:__imp_GetAclInformation
0x18003fa7a  test    eax, eax
0x18003fa7c  jnz     short loc_18003FA8B
0x18003fa7e  call    cs:__imp_GetLastError
0x18003fa84  mov     ebx, eax
0x18003fa86  jmp     loc_18003FB0E
0x18003fa8b  mov     ecx, [rsp+88h+var_20]
0x18003fa8f  add     ecx, [rsp+88h+var_24]
0x18003fa93  mov     dword ptr [rsp+88h+var_58], ecx
0x18003fa97  mov     qword ptr [rsp+88h+var_58+8], rdi
0x18003fa9c  jmp     short loc_18003FAA7
0x18003fa9e  mov     dword ptr [rsp+88h+var_58], eax
0x18003faa2  mov     qword ptr [rsp+88h+var_58+8], rax
0x18003faa7  mov     [rsp+88h+var_40], 0
0x18003fab0  movaps  xmm0, [rsp+88h+var_58]
0x18003fab5  movdqa  [rsp+88h+var_58], xmm0
0x18003fabb  movups  xmm1, xmmword ptr [rsi]
0x18003fabe  movdqu  [rsp+88h+var_38], xmm1
0x18003fac4  lea     rax, [rsp+88h+var_58]
0x18003fac9  mov     [rsp+88h+var_60], rax
0x18003face  lea     rax, [rsp+88h+var_38]
0x18003fad3  mov     [rsp+88h+var_68], rax
0x18003fad8  xor     r9d, r9d
0x18003fadb  xor     r8d, r8d; pReturnValue
0x18003fade  lea     edx, [r9+67h]; nProcNum
0x18003fae2  lea     rcx, stru_1800524F0; pProxyInfo
0x18003fae9  call    cs:__imp_NdrClientCall3
0x18003faef  mov     [rsp+88h+var_40], rax
0x18003faf4  test    eax, eax
0x18003faf6  jns     short loc_18003FB06
0x18003faf8  mov     ecx, eax; Status
0x18003fafa  call    cs:__imp_RtlNtStatusToDosError
0x18003fb00  mov     ebx, eax
0x18003fb02  mov     [rsp+88h+var_48], eax
0x18003fb06  jmp     short loc_18003FB0E
0x18003fb08  mov     ebx, eax
0x18003fb0a  mov     [rsp+88h+var_48], eax
0x18003fb0e  test    ebx, ebx
0x18003fb10  jz      short loc_18003FB1C
0x18003fb12  mov     ecx, ebx; dwErrCode
0x18003fb14  call    cs:__imp_SetLastError
0x18003fb1a  test    ebx, ebx
0x18003fb1c  setz    al
0x18003fb1f  mov     rcx, [rsp+88h+var_18]
0x18003fb24  xor     rcx, rsp; StackCookie
0x18003fb27  call    __security_check_cookie
0x18003fb2c  lea     r11, [rsp+88h+var_8]
0x18003fb34  mov     rbx, [r11+20h]
0x18003fb38  mov     rsi, [r11+28h]
0x18003fb3c  mov     rsp, r11
0x18003fb3f  pop     rdi
0x18003fb40  retn
0x18005048a  push    rbp
0x18005048c  sub     rsp, 30h
0x180050490  mov     rbp, rdx
0x180050493  mov     rcx, [rcx]
0x180050496  mov     ecx, [rcx]; ExceptionCode
0x180050498  call    cs:__imp_I_RpcExceptionFilter
0x18005049e  nop
0x18005049f  add     rsp, 30h
0x1800504a3  pop     rbp
0x1800504a4  retn
```
