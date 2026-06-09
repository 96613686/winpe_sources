# WxGetRpcImpersonationTokenAndSid(void *,void * *,_SID *)

- ea: `0x18006a9a8`
- end: `0x18006ab9d`
- name: `?WxGetRpcImpersonationTokenAndSid@@YAJPEAXPEAPEAXPEAU_SID@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, void **, struct _SID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006a0f0`

## callees

- `0x18006a9a8`
- `0x18006aba4`
- `0x1800a1d10`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006aa84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006aa84`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006aa99`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006aa99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006aac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006aac3`
- `RPCRT4!RpcImpersonateClient` at `0x18006aa09`
- `RPCRT4!RpcImpersonateClient` at `0x18006aa09`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006aab5`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006aab5`

## pseudocode

```c
__int64 __fastcall WxGetRpcImpersonationTokenAndSid(RPC_BINDING_HANDLE BindingHandle, void **a2, struct _SID *a3)
{
  RPC_STATUS v6; // eax
  int v7; // ecx
  signed int v8; // ebx
  int UserToken; // eax
  HANDLE v10; // rdi
  signed int v12; // eax
  signed int LastError; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-A8h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-A0h] BYREF
  int v16; // [rsp+3Ch] [rbp-9Ch]
  PSID TokenInformation[12]; // [rsp+40h] [rbp-98h] BYREF

  v16 = 0;
  TokenHandle = 0;
  if ( a2 )
    *a2 = 0;
  if ( !BindingHandle )
  {
    v16 = 148;
    return (unsigned int)-2147024809;
  }
  if ( !a2 )
  {
    v16 = 149;
    return (unsigned int)-2147024809;
  }
  if ( !a3 )
  {
    v16 = 150;
    return (unsigned int)-2147024809;
  }
  v6 = RpcImpersonateClient(BindingHandle);
  v8 = v6;
  if ( v6 > 0 )
    v8 = (unsigned __int16)v6 | 0x80070000;
  if ( v8 < 0 )
  {
    v16 = 152;
  }
  else
  {
    UserToken = WxGetUserToken(v7, &TokenHandle);
    v10 = TokenHandle;
    v8 = UserToken;
    if ( UserToken < 0 )
    {
      v16 = 156;
    }
    else
    {
      HIDWORD(TokenHandle) = 0;
      memset_0(TokenInformation, 0, 0x58u);
      ReturnLength = 0;
      if ( v10 )
      {
        if ( GetTokenInformation(v10, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
        {
          if ( CopySid(0x44u, a3, TokenInformation[0]) )
          {
            v8 = 0;
          }
          else
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
            HIDWORD(TokenHandle) = 32;
            if ( v8 >= 0 )
              v8 = -2147418113;
          }
        }
        else
        {
          v12 = GetLastError();
          v8 = v12;
          if ( v12 > 0 )
            v8 = (unsigned __int16)v12 | 0x80070000;
          HIDWORD(TokenHandle) = 31;
          if ( v8 >= 0 )
            v8 = -2147418113;
        }
      }
      else
      {
        v8 = -2147024809;
        HIDWORD(TokenHandle) = 27;
      }
      if ( v8 < 0 )
      {
        v16 = 160;
      }
      else
      {
        *a2 = v10;
        v10 = 0;
      }
    }
    RpcRevertToSelfEx(BindingHandle);
    if ( v10 )
      CloseHandle(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006a9a8  push    rbx
0x18006a9aa  push    rbp
0x18006a9ab  push    rsi
0x18006a9ac  push    rdi
0x18006a9ad  push    r14
0x18006a9af  sub     rsp, 0B0h
0x18006a9b6  mov     rax, cs:__security_cookie
0x18006a9bd  xor     rax, rsp
0x18006a9c0  mov     [rsp+0D8h+var_38], rax
0x18006a9c8  mov     [rsp+0D8h+var_9C], 0
0x18006a9d0  mov     r14, r8
0x18006a9d3  mov     [rsp+0D8h+TokenHandle], 0
0x18006a9dc  mov     rsi, rdx
0x18006a9df  mov     rbp, rcx
0x18006a9e2  test    rdx, rdx
0x18006a9e5  jz      short loc_18006A9EE
0x18006a9e7  mov     qword ptr [rdx], 0
0x18006a9ee  test    rbp, rbp
0x18006a9f1  jz      loc_18006AB3E
0x18006a9f7  test    rsi, rsi
0x18006a9fa  jz      loc_18006AB5A
0x18006aa00  test    r14, r14
0x18006aa03  jz      loc_18006AB48
0x18006aa09  call    cs:__imp_RpcImpersonateClient
0x18006aa0f  mov     ebx, eax
0x18006aa11  test    eax, eax
0x18006aa13  jle     short loc_18006AA1E
0x18006aa15  movzx   ebx, ax
0x18006aa18  or      ebx, 80070000h
0x18006aa1e  test    ebx, ebx
0x18006aa20  js      loc_18006AB64
0x18006aa26  lea     rdx, [rsp+0D8h+TokenHandle]; void **
0x18006aa2b  call    ?WxGetUserToken@@YAJHPEAPEAX@Z; WxGetUserToken(int,void * *)
0x18006aa30  mov     rdi, [rsp+0D8h+TokenHandle]
0x18006aa35  mov     ebx, eax
0x18006aa37  test    eax, eax
0x18006aa39  js      loc_18006AB71
0x18006aa3f  mov     ebx, 58h ; 'X'
0x18006aa44  mov     dword ptr [rsp+0D8h+TokenHandle+4], 0
0x18006aa4c  mov     r8d, ebx; Size
0x18006aa4f  lea     rcx, [rsp+0D8h+TokenInformation]; void *
0x18006aa54  xor     edx, edx; Val
0x18006aa56  call    memset_0
0x18006aa5b  mov     [rsp+0D8h+var_A0], 0
0x18006aa63  test    rdi, rdi
0x18006aa66  jz      loc_18006AB7E
0x18006aa6c  lea     rax, [rsp+0D8h+var_A0]
0x18006aa71  mov     r9d, ebx; TokenInformationLength
0x18006aa74  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x18006aa79  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x18006aa7e  lea     edx, [rbx-57h]; TokenInformationClass
0x18006aa81  mov     rcx, rdi; TokenHandle
0x18006aa84  call    cs:__imp_GetTokenInformation
0x18006aa8a  test    eax, eax
0x18006aa8c  jz      short loc_18006AAE9
0x18006aa8e  mov     r8, [rsp+0D8h+TokenInformation]; pSourceSid
0x18006aa93  lea     ecx, [rbx-14h]; nDestinationSidLength
0x18006aa96  mov     rdx, r14; pDestinationSid
0x18006aa99  call    cs:__imp_CopySid
0x18006aa9f  test    eax, eax
0x18006aaa1  jz      short loc_18006AB12
0x18006aaa3  xor     ebx, ebx
0x18006aaa5  test    ebx, ebx
0x18006aaa7  js      loc_18006AB90
0x18006aaad  mov     [rsi], rdi
0x18006aab0  xor     edi, edi
0x18006aab2  mov     rcx, rbp; BindingHandle
0x18006aab5  call    cs:__imp_RpcRevertToSelfEx
0x18006aabb  test    rdi, rdi
0x18006aabe  jz      short loc_18006AAC9
0x18006aac0  mov     rcx, rdi; hObject
0x18006aac3  call    cs:__imp_CloseHandle
0x18006aac9  mov     eax, ebx
0x18006aacb  mov     rcx, [rsp+0D8h+var_38]
0x18006aad3  xor     rcx, rsp; StackCookie
0x18006aad6  call    __security_check_cookie
0x18006aadb  add     rsp, 0B0h
0x18006aae2  pop     r14
0x18006aae4  pop     rdi
0x18006aae5  pop     rsi
0x18006aae6  pop     rbp
0x18006aae7  pop     rbx
0x18006aae8  retn
0x18006aae9  call    cs:__imp_GetLastError
0x18006aaef  mov     ebx, eax
0x18006aaf1  test    eax, eax
0x18006aaf3  jle     short loc_18006AAFE
0x18006aaf5  movzx   ebx, ax
0x18006aaf8  or      ebx, 80070000h
0x18006aafe  test    ebx, ebx
0x18006ab00  mov     dword ptr [rsp+0D8h+TokenHandle+4], 1Fh
0x18006ab08  mov     eax, 8000FFFFh
0x18006ab0d  cmovns  ebx, eax
0x18006ab10  jmp     short loc_18006AAA5
0x18006ab12  call    cs:__imp_GetLastError
0x18006ab18  mov     ebx, eax
0x18006ab1a  test    eax, eax
0x18006ab1c  jle     short loc_18006AB27
0x18006ab1e  movzx   ebx, ax
0x18006ab21  or      ebx, 80070000h
0x18006ab27  test    ebx, ebx
0x18006ab29  mov     dword ptr [rsp+0D8h+TokenHandle+4], 20h ; ' '
0x18006ab31  mov     eax, 8000FFFFh
0x18006ab36  cmovns  ebx, eax
0x18006ab39  jmp     loc_18006AAA5
0x18006ab3e  mov     [rsp+0D8h+var_9C], 94h
0x18006ab46  jmp     short loc_18006AB50
0x18006ab48  mov     [rsp+0D8h+var_9C], 96h
0x18006ab50  mov     ebx, 80070057h
0x18006ab55  jmp     loc_18006AAC9
0x18006ab5a  mov     [rsp+0D8h+var_9C], 95h
0x18006ab62  jmp     short loc_18006AB50
0x18006ab64  mov     [rsp+0D8h+var_9C], 98h
0x18006ab6c  jmp     loc_18006AAC9
0x18006ab71  mov     [rsp+0D8h+var_9C], 9Ch
0x18006ab79  jmp     loc_18006AAB2
0x18006ab7e  mov     ebx, 80070057h
0x18006ab83  mov     dword ptr [rsp+0D8h+TokenHandle+4], 1Bh
0x18006ab8b  jmp     loc_18006AAA5
0x18006ab90  mov     [rsp+0D8h+var_9C], 0A0h
0x18006ab98  jmp     loc_18006AAB2
```
