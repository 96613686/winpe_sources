# GetSID(_WINBIO_IDENTITY *)

- ea: `0x1801e9c28`
- end: `0x1801e9d82`
- name: `?GetSID@@YAJPEAU_WINBIO_IDENTITY@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(struct _WINBIO_IDENTITY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801e354c`
- `0x1801e48d8`

## callees

- `0x18007a2dc`
- `0x18007a31c`
- `0x1801e9c28`
- `0x1801e9d88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e9d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801e9c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801e9c44`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801e9c55`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801e9c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e9d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e9d45`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801e9d0c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801e9d0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801e9c9d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801e9cea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801e9c9d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801e9cea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801e9d19`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801e9d19`

## pseudocode

```c
__int64 __fastcall GetSID(struct _WINBIO_IDENTITY *a1)
{
  signed int v1; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v5; // eax
  PSID *v6; // rsi
  signed int v7; // eax
  ULONG LengthSid; // ebx
  rsize_t v9; // rdx
  signed int v10; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  TokenInformationLength = 0;
  if ( v1 >= 0 && !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v5 = GetLastError();
    if ( v5 != 122 )
    {
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
      else
        v1 = v5;
    }
  }
  v6 = 0;
  if ( v1 >= 0 )
  {
    v6 = (PSID *)operator new[](TokenInformationLength);
    if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_26;
    v7 = GetLastError();
    v1 = v7;
    if ( v7 > 0 )
      v1 = (unsigned __int16)v7 | 0x80070000;
    if ( v1 >= 0 )
    {
LABEL_26:
      if ( IsValidSid(*v6) )
      {
        LengthSid = GetLengthSid(*v6);
        memcpy_s_3(a1->Value.AccountSid.Data, v9, *v6, LengthSid);
        a1->Value.Null = LengthSid;
        a1->Type = 3;
      }
    }
  }
  if ( TokenHandle )
  {
    if ( !CloseHandle(TokenHandle) )
    {
      v10 = GetLastError();
      v1 = v10;
      if ( v10 > 0 )
        v1 = (unsigned __int16)v10 | 0x80070000;
    }
  }
  if ( v6 )
    operator delete(v6);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801e9c28  mov     [rsp+arg_0], rbx
0x1801e9c2d  mov     [rsp+arg_18], rbp
0x1801e9c32  push    rsi
0x1801e9c33  push    rdi
0x1801e9c34  push    r14
0x1801e9c36  sub     rsp, 30h
0x1801e9c3a  xor     edi, edi
0x1801e9c3c  mov     r14, rcx
0x1801e9c3f  mov     [rsp+48h+TokenHandle], rdi
0x1801e9c44  call    cs:__imp_GetCurrentProcess
0x1801e9c4a  mov     rcx, rax; ProcessHandle
0x1801e9c4d  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1801e9c52  lea     edx, [rdi+8]; DesiredAccess
0x1801e9c55  call    cs:__imp_OpenProcessToken
0x1801e9c5b  mov     ebp, 80070000h
0x1801e9c60  test    eax, eax
0x1801e9c62  jnz     short loc_1801E9C75
0x1801e9c64  call    cs:__imp_GetLastError
0x1801e9c6a  mov     edi, eax
0x1801e9c6c  test    eax, eax
0x1801e9c6e  jle     short loc_1801E9C75
0x1801e9c70  movzx   edi, ax
0x1801e9c73  or      edi, ebp
0x1801e9c75  mov     [rsp+48h+TokenInformationLength], 0
0x1801e9c7d  mov     ebx, 1
0x1801e9c82  test    edi, edi
0x1801e9c84  js      short loc_1801E9CBF
0x1801e9c86  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1801e9c8b  lea     rax, [rsp+48h+TokenInformationLength]
0x1801e9c90  xor     r9d, r9d; TokenInformationLength
0x1801e9c93  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1801e9c98  xor     r8d, r8d; TokenInformation
0x1801e9c9b  mov     edx, ebx; TokenInformationClass
0x1801e9c9d  call    cs:__imp_GetTokenInformation
0x1801e9ca3  test    eax, eax
0x1801e9ca5  jnz     short loc_1801E9CBF
0x1801e9ca7  call    cs:__imp_GetLastError
0x1801e9cad  cmp     eax, 7Ah ; 'z'
0x1801e9cb0  jz      short loc_1801E9CBF
0x1801e9cb2  test    eax, eax
0x1801e9cb4  jg      short loc_1801E9CBA
0x1801e9cb6  mov     edi, eax
0x1801e9cb8  jmp     short loc_1801E9CBF
0x1801e9cba  movzx   edi, ax
0x1801e9cbd  or      edi, ebp
0x1801e9cbf  xor     esi, esi
0x1801e9cc1  test    edi, edi
0x1801e9cc3  js      short loc_1801E9D3B
0x1801e9cc5  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x1801e9cc9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801e9cce  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1801e9cd3  mov     rsi, rax
0x1801e9cd6  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1801e9cdb  lea     rax, [rsp+48h+TokenInformationLength]
0x1801e9ce0  mov     r8, rsi; TokenInformation
0x1801e9ce3  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1801e9ce8  mov     edx, ebx; TokenInformationClass
0x1801e9cea  call    cs:__imp_GetTokenInformation
0x1801e9cf0  test    eax, eax
0x1801e9cf2  jnz     short loc_1801E9D09
0x1801e9cf4  call    cs:__imp_GetLastError
0x1801e9cfa  mov     edi, eax
0x1801e9cfc  test    eax, eax
0x1801e9cfe  jle     short loc_1801E9D05
0x1801e9d00  movzx   edi, ax
0x1801e9d03  or      edi, ebp
0x1801e9d05  test    edi, edi
0x1801e9d07  js      short loc_1801E9D3B
0x1801e9d09  mov     rcx, [rsi]; pSid
0x1801e9d0c  call    cs:__imp_IsValidSid
0x1801e9d12  test    eax, eax
0x1801e9d14  jz      short loc_1801E9D3B
0x1801e9d16  mov     rcx, [rsi]; pSid
0x1801e9d19  call    cs:__imp_GetLengthSid
0x1801e9d1f  mov     r8, [rsi]; Source
0x1801e9d22  lea     rcx, [r14+8]; Destination
0x1801e9d26  mov     r9d, eax; SourceSize
0x1801e9d29  mov     ebx, eax
0x1801e9d2b  call    memcpy_s_3
0x1801e9d30  mov     [r14+4], ebx
0x1801e9d34  mov     dword ptr [r14], 3
0x1801e9d3b  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1801e9d40  test    rcx, rcx
0x1801e9d43  jz      short loc_1801E9D60
0x1801e9d45  call    cs:__imp_CloseHandle
0x1801e9d4b  test    eax, eax
0x1801e9d4d  jnz     short loc_1801E9D60
0x1801e9d4f  call    cs:__imp_GetLastError
0x1801e9d55  mov     edi, eax
0x1801e9d57  test    eax, eax
0x1801e9d59  jle     short loc_1801E9D60
0x1801e9d5b  movzx   edi, ax
0x1801e9d5e  or      edi, ebp
0x1801e9d60  test    rsi, rsi
0x1801e9d63  jz      short loc_1801E9D6D
0x1801e9d65  mov     rcx, rsi; Block
0x1801e9d68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e9d6d  mov     rbx, [rsp+48h+arg_0]
0x1801e9d72  mov     eax, edi
0x1801e9d74  mov     rbp, [rsp+48h+arg_18]
0x1801e9d79  add     rsp, 30h
0x1801e9d7d  pop     r14
0x1801e9d7f  pop     rdi
0x1801e9d80  pop     rsi
0x1801e9d81  retn
```
