# LUAIsUserUACAdminEx

- ea: `0x180026c68`
- end: `0x180026d30`
- name: `LUAIsUserUACAdminEx`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026b58`

## callees

- `0x1800269cc`
- `0x180026a70`
- `0x180026aac`
- `0x180026c68`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026cef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026cef`

## pseudocode

```c
__int64 __fastcall LUAIsUserUACAdminEx(HANDLE TokenHandle, _DWORD *a2)
{
  NTSTATUS v5; // esi
  int v6; // eax
  void *v7; // rcx
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenInformation; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 3221225474LL;
  ReturnLength = 0;
  LODWORD(TokenInformation) = 0;
  v5 = LUAIsElevatedToken(TokenHandle, &ReturnLength, &TokenInformation);
  if ( v5 >= 0 )
  {
    if ( ReturnLength )
    {
      *a2 = _LUAIsTokenAdmin(TokenHandle);
    }
    else
    {
      TokenInformation = 0;
      ReturnLength = 8;
      if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
      {
        if ( TokenInformation )
        {
          v6 = _LUAIsTokenAdmin(TokenInformation);
          v7 = TokenInformation;
          *a2 = v6;
          CloseHandle(v7);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026c68  mov     [rsp+arg_0], rbx
0x180026c6d  mov     [rsp+arg_18], rsi
0x180026c72  push    rdi
0x180026c73  sub     rsp, 30h
0x180026c77  mov     rbx, rdx
0x180026c7a  mov     dword ptr [rdx], 0
0x180026c80  mov     rdi, rcx
0x180026c83  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180026c88  test    eax, eax
0x180026c8a  jnz     short loc_180026C96
0x180026c8c  mov     eax, 0C0000002h
0x180026c91  jmp     loc_180026D20
0x180026c96  lea     r8, [rsp+38h+TokenInformation]
0x180026c9b  mov     [rsp+38h+arg_8], 0
0x180026ca3  lea     rdx, [rsp+38h+arg_8]
0x180026ca8  mov     dword ptr [rsp+38h+TokenInformation], 0
0x180026cb0  mov     rcx, rdi; TokenHandle
0x180026cb3  call    LUAIsElevatedToken
0x180026cb8  mov     esi, eax
0x180026cba  test    eax, eax
0x180026cbc  js      short loc_180026D1E
0x180026cbe  cmp     [rsp+38h+arg_8], 0
0x180026cc3  mov     rcx, rdi; void *
0x180026cc6  jnz     short loc_180026D17
0x180026cc8  mov     r9d, 8; TokenInformationLength
0x180026cce  mov     [rsp+38h+TokenInformation], 0
0x180026cd7  lea     rax, [rsp+38h+arg_8]
0x180026cdc  mov     [rsp+38h+arg_8], r9d
0x180026ce1  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180026ce6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180026ceb  lea     edx, [r9+0Bh]; TokenInformationClass
0x180026cef  call    cs:__imp_GetTokenInformation
0x180026cf5  test    eax, eax
0x180026cf7  jz      short loc_180026D1E
0x180026cf9  mov     rcx, [rsp+38h+TokenInformation]; void *
0x180026cfe  test    rcx, rcx
0x180026d01  jz      short loc_180026D1E
0x180026d03  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180026d08  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x180026d0d  mov     [rbx], eax
0x180026d0f  call    cs:__imp_CloseHandle
0x180026d15  jmp     short loc_180026D1E
0x180026d17  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180026d1c  mov     [rbx], eax
0x180026d1e  mov     eax, esi
0x180026d20  mov     rbx, [rsp+38h+arg_0]
0x180026d25  mov     rsi, [rsp+38h+arg_18]
0x180026d2a  add     rsp, 30h
0x180026d2e  pop     rdi
0x180026d2f  retn
```
