# MarkEdpDatabaseDirectoryForEncryption(ushort const *)

- ea: `0x1800b3a3c`
- end: `0x1800b3b80`
- name: `?MarkEdpDatabaseDirectoryForEncryption@@YAJPEBG@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a094`

## callees

- `0x180080f94`
- `0x1800814bc`
- `0x1800b3a3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3a7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3a7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b3a90`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b3a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3b38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3b38`
- `RPCRT4!RpcRevertToSelf` at `0x1800b3af9`
- `RPCRT4!RpcRevertToSelf` at `0x1800b3b57`
- `RPCRT4!RpcRevertToSelf` at `0x1800b3af9`
- `RPCRT4!RpcRevertToSelf` at `0x1800b3b57`
- `RPCRT4!RpcImpersonateClient` at `0x1800b3a54`
- `RPCRT4!RpcImpersonateClient` at `0x1800b3a54`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x1800b3b18`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x1800b3b18`
- `srpapi!SrpGetEnterpriseIds` at `0x1800b3abe`
- `srpapi!SrpGetEnterpriseIds` at `0x1800b3ae7`
- `srpapi!SrpGetEnterpriseIds` at `0x1800b3abe`
- `srpapi!SrpGetEnterpriseIds` at `0x1800b3ae7`

## pseudocode

```c
__int64 __fastcall MarkEdpDatabaseDirectoryForEncryption(const unsigned __int16 *a1)
{
  RPC_STATUS v2; // eax
  signed int EnterpriseIds; // ebx
  HANDLE CurrentThread; // rax
  char v5; // si
  _QWORD *v6; // rdi
  RPC_STATUS v7; // eax
  signed int LastError; // eax
  int v9; // eax
  size_t Size; // [rsp+58h] [rbp+38h] BYREF
  int v12; // [rsp+60h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+48h] BYREF

  v2 = RpcImpersonateClient(0);
  EnterpriseIds = v2;
  if ( v2 > 0 )
    EnterpriseIds = (unsigned __int16)v2 | 0x80070000;
  if ( EnterpriseIds >= 0 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      LastError = GetLastError();
      EnterpriseIds = LastError;
      if ( LastError > 0 )
        EnterpriseIds = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_19;
    }
    v12 = 0;
    LODWORD(Size) = 0;
    v5 = 0;
    EnterpriseIds = SrpGetEnterpriseIds(TokenHandle, &Size, 0, &v12);
    if ( EnterpriseIds == -2147024774 )
    {
      v6 = operator new((unsigned int)Size);
      EnterpriseIds = SrpGetEnterpriseIds(TokenHandle, &Size, v6, &v12);
      if ( EnterpriseIds >= 0 && v12 )
      {
        v7 = RpcRevertToSelf();
        EnterpriseIds = v7;
        if ( v7 > 0 )
          EnterpriseIds = (unsigned __int16)v7 | 0x80070000;
        if ( EnterpriseIds >= 0 )
        {
          v5 = 1;
          EnterpriseIds = ProtectFileToEnterpriseIdentity(a1, *v6);
        }
      }
      operator delete(v6);
    }
    else if ( EnterpriseIds >= 0 )
    {
      EnterpriseIds = -2147418113;
    }
    CloseHandle(TokenHandle);
    if ( !v5 )
    {
LABEL_19:
      v9 = RpcRevertToSelf();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      if ( EnterpriseIds >= 0 )
        return (unsigned int)v9;
    }
  }
  return (unsigned int)EnterpriseIds;
}

```

## disassembly

```asm
0x1800b3a3c  mov     [rsp-28h+arg_0], rbx
0x1800b3a41  push    rbp
0x1800b3a42  push    rsi
0x1800b3a43  push    rdi
0x1800b3a44  push    r12
0x1800b3a46  push    r14
0x1800b3a48  mov     rbp, rsp
0x1800b3a4b  sub     rsp, 20h
0x1800b3a4f  mov     r14, rcx
0x1800b3a52  xor     ecx, ecx; BindingHandle
0x1800b3a54  call    cs:__imp_RpcImpersonateClient
0x1800b3a5a  mov     ebx, eax
0x1800b3a5c  mov     r12d, 80070000h
0x1800b3a62  test    eax, eax
0x1800b3a64  jle     short loc_1800B3A6C
0x1800b3a66  movzx   ebx, ax
0x1800b3a69  or      ebx, r12d
0x1800b3a6c  test    ebx, ebx
0x1800b3a6e  js      loc_1800B3B6D
0x1800b3a74  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800b3a7c  call    cs:__imp_GetCurrentThread
0x1800b3a82  xor     r8d, r8d; OpenAsSelf
0x1800b3a85  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800b3a89  mov     rcx, rax; ThreadHandle
0x1800b3a8c  lea     edx, [r8+8]; DesiredAccess
0x1800b3a90  call    cs:__imp_OpenThreadToken
0x1800b3a96  test    eax, eax
0x1800b3a98  jz      loc_1800B3B45
0x1800b3a9e  mov     rcx, [rbp+TokenHandle]
0x1800b3aa2  lea     r9, [rbp+arg_10]
0x1800b3aa6  xor     r8d, r8d
0x1800b3aa9  mov     [rbp+arg_10], 0
0x1800b3ab0  lea     rdx, [rbp+Size]
0x1800b3ab4  mov     dword ptr [rbp+Size], 0
0x1800b3abb  xor     sil, sil
0x1800b3abe  call    cs:__imp_SrpGetEnterpriseIds
0x1800b3ac4  mov     ebx, eax
0x1800b3ac6  cmp     eax, 8007007Ah
0x1800b3acb  jnz     short loc_1800B3B2A
0x1800b3acd  mov     ecx, dword ptr [rbp+Size]; Size
0x1800b3ad0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3ad5  mov     rcx, [rbp+TokenHandle]
0x1800b3ad9  lea     r9, [rbp+arg_10]
0x1800b3add  mov     r8, rax
0x1800b3ae0  lea     rdx, [rbp+Size]
0x1800b3ae4  mov     rdi, rax
0x1800b3ae7  call    cs:__imp_SrpGetEnterpriseIds
0x1800b3aed  mov     ebx, eax
0x1800b3aef  test    eax, eax
0x1800b3af1  js      short loc_1800B3B20
0x1800b3af3  cmp     [rbp+arg_10], 0
0x1800b3af7  jbe     short loc_1800B3B20
0x1800b3af9  call    cs:__imp_RpcRevertToSelf
0x1800b3aff  mov     ebx, eax
0x1800b3b01  test    eax, eax
0x1800b3b03  jle     short loc_1800B3B0B
0x1800b3b05  movzx   ebx, ax
0x1800b3b08  or      ebx, r12d
0x1800b3b0b  test    ebx, ebx
0x1800b3b0d  js      short loc_1800B3B20
0x1800b3b0f  mov     rdx, [rdi]
0x1800b3b12  mov     rcx, r14
0x1800b3b15  mov     sil, 1
0x1800b3b18  call    cs:__imp_ProtectFileToEnterpriseIdentity
0x1800b3b1e  mov     ebx, eax
0x1800b3b20  mov     rcx, rdi; Block
0x1800b3b23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b3b28  jmp     short loc_1800B3B34
0x1800b3b2a  test    ebx, ebx
0x1800b3b2c  mov     eax, 8000FFFFh
0x1800b3b31  cmovns  ebx, eax
0x1800b3b34  mov     rcx, [rbp+TokenHandle]; hObject
0x1800b3b38  call    cs:__imp_CloseHandle
0x1800b3b3e  test    sil, sil
0x1800b3b41  jnz     short loc_1800B3B6D
0x1800b3b43  jmp     short loc_1800B3B57
0x1800b3b45  call    cs:__imp_GetLastError
0x1800b3b4b  mov     ebx, eax
0x1800b3b4d  test    eax, eax
0x1800b3b4f  jle     short loc_1800B3B57
0x1800b3b51  movzx   ebx, ax
0x1800b3b54  or      ebx, r12d
0x1800b3b57  call    cs:__imp_RpcRevertToSelf
0x1800b3b5d  test    eax, eax
0x1800b3b5f  jle     short loc_1800B3B67
0x1800b3b61  movzx   eax, ax
0x1800b3b64  or      eax, r12d
0x1800b3b67  test    ebx, ebx
0x1800b3b69  js      short loc_1800B3B6D
0x1800b3b6b  mov     ebx, eax
0x1800b3b6d  mov     eax, ebx
0x1800b3b6f  mov     rbx, [rsp+20h+arg_0]
0x1800b3b74  add     rsp, 20h
0x1800b3b78  pop     r14
0x1800b3b7a  pop     r12
0x1800b3b7c  pop     rdi
0x1800b3b7d  pop     rsi
0x1800b3b7e  pop     rbp
0x1800b3b7f  retn
```
