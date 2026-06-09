# _UserTestForWinStaAccess

- ea: `0x1401d6b1c`
- end: `0x1401d6e39`
- name: `_UserTestForWinStaAccess`
- size: `797`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401d5de0`

## callees

- `0x140033b58`
- `0x1401d6b1c`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1401d6cab`
- `ntoskrnl!ObCloseHandle` at `0x1401d6cab`
- `ntoskrnl!ExWindowStationObjectType` at `0x1401d6c0f`
- `ntoskrnl!ExWindowStationObjectType` at `0x1401d6c5b`
- `ntoskrnl!ObReferenceObjectByName` at `0x1401d6c36`
- `ntoskrnl!ObReferenceObjectByName` at `0x1401d6c36`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401d6bc7`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401d6cd8`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401d6d2a`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401d6bc7`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401d6cd8`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401d6d2a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401d6b8a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401d6b8a`
- `ntoskrnl!ZwClose` at `0x1401d6bf4`
- `ntoskrnl!ZwClose` at `0x1401d6d84`
- `ntoskrnl!ZwClose` at `0x1401d6e0b`
- `ntoskrnl!ZwClose` at `0x1401d6bf4`
- `ntoskrnl!ZwClose` at `0x1401d6d84`
- `ntoskrnl!ZwClose` at `0x1401d6e0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6b74`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6b74`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401d6c76`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401d6c76`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6c88`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6c88`
- `win32kbase!WinStaMapping` at `0x1401d6de4`
- `win32kbase!AccessCheckObject` at `0x1401d6df0`
- `win32kbase!AccessCheckObject` at `0x1401d6df0`
- `win32kbase!luidSystem` at `0x1401d6dcb`
- `win32kbase!OpenEffectiveToken` at `0x1401d6b9c`
- `win32kbase!OpenEffectiveToken` at `0x1401d6b9c`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401d6cf9`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401d6cf9`
- `win32kbase!Win32FreePool` at `0x1401d6d93`
- `win32kbase!Win32FreePool` at `0x1401d6d93`
- `WIN32K!W32GetUserSessionState` at `0x1401d6d41`
- `WIN32K!W32GetUserSessionState` at `0x1401d6d57`
- `WIN32K!W32GetUserSessionState` at `0x1401d6d41`
- `WIN32K!W32GetUserSessionState` at `0x1401d6d57`

## pseudocode

```c
int __fastcall UserTestForWinStaAccess(PCUNICODE_STRING String1, int a2)
{
  ACCESS_MASK v4; // esi
  BOOLEAN v5; // bl
  int result; // eax
  int v7; // eax
  NTSTATUS v8; // ebx
  NTSTATUS v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  _DWORD *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 UserSessionState; // rax
  __int64 v16; // r8
  int v17; // edx
  __int64 v18; // rcx
  int v19; // eax
  HANDLE TokenHandle; // [rsp+40h] [rbp-30h] BYREF
  PVOID Object; // [rsp+48h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  ULONG TokenInformationLength; // [rsp+A0h] [rbp+30h] BYREF
  int TokenInformation; // [rsp+A8h] [rbp+38h] BYREF

  TokenInformationLength = 0;
  Handle = 0;
  TokenHandle = 0;
  Object = 0;
  TokenInformation = 0;
  DestinationString = 0;
  v4 = 0x20000000;
  RtlInitUnicodeString(&DestinationString, L"\\Windows\\WindowStations\\WinSta0");
  v5 = RtlEqualUnicodeString(String1, &DestinationString, 1u);
  result = OpenEffectiveToken(&TokenHandle);
  if ( result >= 0 )
  {
    result = ZwQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength);
    if ( result >= 0 )
    {
      if ( TokenInformation )
        v4 = 131104;
    }
  }
  if ( v5 )
  {
    if ( !TokenHandle )
      return result;
    v8 = ZwQueryInformationToken(TokenHandle, TokenStatistics, 0, 0, &TokenInformationLength);
    if ( v8 == -1073741789 )
    {
      v12 = (_DWORD *)Win32AllocPoolWithQuotaZInit(TokenInformationLength, 1702064981, v10, v11);
      if ( v12 )
      {
        v8 = ZwQueryInformationToken(TokenHandle, TokenStatistics, v12, TokenInformationLength, &TokenInformationLength);
        if ( v8 >= 0 )
        {
          v8 = -1073741790;
          if ( *(_QWORD *)(W32GetUserSessionState(v13) + 63288) )
          {
            UserSessionState = W32GetUserSessionState(v14);
            v17 = v12[2];
            v18 = *(_QWORD *)(UserSessionState + 63288);
            v19 = *(_DWORD *)(v18 + 152);
            if ( a2 )
            {
              if ( v17 == v19 && v12[3] == *(_DWORD *)(v18 + 156)
                || v17 == luidSystem[0] && v12[3] == luidSystem[1]
                || (LOBYTE(v16) = 1, (unsigned int)AccessCheckObject(v18, v4, v16, WinStaMapping)) )
              {
                v8 = 0;
              }
            }
            else if ( v17 == v19 && v12[3] == *(_DWORD *)(v18 + 156) )
            {
              v8 = 0;
            }
          }
        }
        ZwClose(TokenHandle);
        Win32FreePool(v12);
        return v8;
      }
      v8 = -1073741801;
    }
    ZwClose(TokenHandle);
    return v8;
  }
  if ( TokenHandle )
    ZwClose(TokenHandle);
  v7 = ObReferenceObjectByName(String1, 64, 0, v4, ExWindowStationObjectType, 0, 0, &Object);
  v8 = v7;
  if ( v7 < 0 )
  {
    SetLastNtError((unsigned int)v7);
    return v8;
  }
  v9 = ObOpenObjectByPointer(Object, 0x40u, 0, v4, ExWindowStationObjectType, 1, &Handle);
  ObfDereferenceObject(Object);
  if ( v9 >= 0 && Handle )
    return ObCloseHandle(Handle, 1);
  else
    return -1073741790;
}

```

## disassembly

```asm
0x1401d6b1c  mov     [rsp-18h+arg_0], rbx
0x1401d6b21  mov     [rsp-18h+arg_8], rsi
0x1401d6b26  push    rbp
0x1401d6b27  push    rdi
0x1401d6b28  push    r14
0x1401d6b2a  mov     rbp, rsp
0x1401d6b2d  sub     rsp, 70h
0x1401d6b31  mov     r14d, edx
0x1401d6b34  mov     [rbp+TokenInformationLength], 0
0x1401d6b3b  mov     rdi, rcx
0x1401d6b3e  mov     [rbp+var_20], 0
0x1401d6b46  xorps   xmm0, xmm0
0x1401d6b49  mov     [rbp+TokenHandle], 0
0x1401d6b51  lea     rdx, aWindowsWindows; "\\Windows\\WindowStations\\WinSta0"
0x1401d6b58  mov     [rbp+Object], 0
0x1401d6b60  lea     rcx, [rbp+DestinationString]; DestinationString
0x1401d6b64  mov     [rbp+TokenInformation], 0
0x1401d6b6b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1401d6b6f  mov     esi, 20000000h
0x1401d6b74  call    cs:__imp_RtlInitUnicodeString
0x1401d6b7b  nop     dword ptr [rax+rax+00h]
0x1401d6b80  mov     r8b, 1; CaseInSensitive
0x1401d6b83  lea     rdx, [rbp+DestinationString]; String2
0x1401d6b87  mov     rcx, rdi; String1
0x1401d6b8a  call    cs:__imp_RtlEqualUnicodeString
0x1401d6b91  nop     dword ptr [rax+rax+00h]
0x1401d6b96  lea     rcx, [rbp+TokenHandle]
0x1401d6b9a  mov     bl, al
0x1401d6b9c  call    cs:__imp_OpenEffectiveToken
0x1401d6ba3  nop     dword ptr [rax+rax+00h]
0x1401d6ba8  test    eax, eax
0x1401d6baa  js      short loc_1401D6BE3
0x1401d6bac  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401d6bb0  lea     rax, [rbp+TokenInformationLength]
0x1401d6bb4  mov     r9d, 4; TokenInformationLength
0x1401d6bba  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1401d6bbf  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1401d6bc3  lea     edx, [r9+19h]; TokenInformationClass
0x1401d6bc7  call    cs:__imp_ZwQueryInformationToken
0x1401d6bce  nop     dword ptr [rax+rax+00h]
0x1401d6bd3  test    eax, eax
0x1401d6bd5  js      short loc_1401D6BE3
0x1401d6bd7  cmp     [rbp+TokenInformation], 0
0x1401d6bdb  mov     ecx, 20020h
0x1401d6be0  cmovnz  esi, ecx
0x1401d6be3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401d6be7  test    bl, bl
0x1401d6be9  jnz     loc_1401D6CBC
0x1401d6bef  test    rcx, rcx
0x1401d6bf2  jz      short loc_1401D6C00
0x1401d6bf4  call    cs:__imp_ZwClose
0x1401d6bfb  nop     dword ptr [rax+rax+00h]
0x1401d6c00  lea     rax, [rbp+Object]
0x1401d6c04  xor     r8d, r8d
0x1401d6c07  mov     [rsp+70h+var_38], rax
0x1401d6c0c  mov     r9d, esi
0x1401d6c0f  mov     rax, cs:__imp_ExWindowStationObjectType
0x1401d6c16  mov     [rsp+70h+Handle], 0
0x1401d6c1f  lea     r14d, [r8+40h]
0x1401d6c23  mov     [rsp+70h+AccessMode], 0
0x1401d6c28  mov     edx, r14d
0x1401d6c2b  mov     rcx, [rax]
0x1401d6c2e  mov     [rsp+70h+ReturnLength], rcx
0x1401d6c33  mov     rcx, rdi
0x1401d6c36  call    cs:__imp_ObReferenceObjectByName
0x1401d6c3d  nop     dword ptr [rax+rax+00h]
0x1401d6c42  mov     ebx, eax
0x1401d6c44  test    eax, eax
0x1401d6c46  js      loc_1401D6DBE
0x1401d6c4c  lea     rax, [rbp+var_20]
0x1401d6c50  mov     r9d, esi; DesiredAccess
0x1401d6c53  mov     [rsp+70h+Handle], rax; Handle
0x1401d6c58  xor     r8d, r8d; PassedAccessState
0x1401d6c5b  mov     rax, cs:__imp_ExWindowStationObjectType
0x1401d6c62  mov     edx, r14d; HandleAttributes
0x1401d6c65  mov     [rsp+70h+AccessMode], 1; AccessMode
0x1401d6c6a  mov     rcx, [rax]
0x1401d6c6d  mov     [rsp+70h+ReturnLength], rcx; ObjectType
0x1401d6c72  mov     rcx, [rbp+Object]; Object
0x1401d6c76  call    cs:__imp_ObOpenObjectByPointer
0x1401d6c7d  nop     dword ptr [rax+rax+00h]
0x1401d6c82  mov     rcx, [rbp+Object]; Object
0x1401d6c86  mov     ebx, eax
0x1401d6c88  call    cs:__imp_ObfDereferenceObject
0x1401d6c8f  nop     dword ptr [rax+rax+00h]
0x1401d6c94  test    ebx, ebx
0x1401d6c96  js      loc_1401D6DB7
0x1401d6c9c  mov     rcx, [rbp+var_20]; Handle
0x1401d6ca0  test    rcx, rcx
0x1401d6ca3  jz      loc_1401D6DB7
0x1401d6ca9  mov     dl, 1; PreviousMode
0x1401d6cab  call    cs:__imp_ObCloseHandle
0x1401d6cb2  nop     dword ptr [rax+rax+00h]
0x1401d6cb7  jmp     loc_1401D6DA1
0x1401d6cbc  test    rcx, rcx
0x1401d6cbf  jz      loc_1401D6DA1
0x1401d6cc5  xor     r9d, r9d; TokenInformationLength
0x1401d6cc8  lea     rax, [rbp+TokenInformationLength]
0x1401d6ccc  xor     r8d, r8d; TokenInformation
0x1401d6ccf  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1401d6cd4  lea     edx, [r9+0Ah]; TokenInformationClass
0x1401d6cd8  call    cs:__imp_ZwQueryInformationToken
0x1401d6cdf  nop     dword ptr [rax+rax+00h]
0x1401d6ce4  mov     ebx, eax
0x1401d6ce6  cmp     eax, 0C0000023h
0x1401d6ceb  jnz     loc_1401D6E07
0x1401d6cf1  mov     ecx, [rbp+TokenInformationLength]
0x1401d6cf4  mov     edx, 65737355h
0x1401d6cf9  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1401d6d00  nop     dword ptr [rax+rax+00h]
0x1401d6d05  mov     rdi, rax
0x1401d6d08  test    rax, rax
0x1401d6d0b  jz      loc_1401D6E02
0x1401d6d11  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1401d6d15  lea     rax, [rbp+TokenInformationLength]
0x1401d6d19  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401d6d1d  mov     r8, rdi; TokenInformation
0x1401d6d20  mov     edx, 0Ah; TokenInformationClass
0x1401d6d25  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1401d6d2a  call    cs:__imp_ZwQueryInformationToken
0x1401d6d31  nop     dword ptr [rax+rax+00h]
0x1401d6d36  mov     ebx, eax
0x1401d6d38  test    eax, eax
0x1401d6d3a  js      short loc_1401D6D80
0x1401d6d3c  mov     ebx, 0C0000022h
0x1401d6d41  call    cs:__imp_W32GetUserSessionState
0x1401d6d48  nop     dword ptr [rax+rax+00h]
0x1401d6d4d  cmp     qword ptr [rax+0F738h], 0
0x1401d6d55  jz      short loc_1401D6D80
0x1401d6d57  call    cs:__imp_W32GetUserSessionState
0x1401d6d5e  nop     dword ptr [rax+rax+00h]
0x1401d6d63  mov     edx, [rdi+8]
0x1401d6d66  mov     rcx, [rax+0F738h]
0x1401d6d6d  mov     eax, [rcx+98h]
0x1401d6d73  test    r14d, r14d
0x1401d6d76  jnz     short loc_1401D6DC7
0x1401d6d78  cmp     edx, eax
0x1401d6d7a  jz      loc_1401D6E26
0x1401d6d80  mov     rcx, [rbp+TokenHandle]; Handle
0x1401d6d84  call    cs:__imp_ZwClose
0x1401d6d8b  nop     dword ptr [rax+rax+00h]
0x1401d6d90  mov     rcx, rdi
0x1401d6d93  call    cs:__imp_Win32FreePool
0x1401d6d9a  nop     dword ptr [rax+rax+00h]
0x1401d6d9f  mov     eax, ebx
0x1401d6da1  lea     r11, [rsp+70h+var_s0]
0x1401d6da6  mov     rbx, [r11+20h]
0x1401d6daa  mov     rsi, [r11+28h]
0x1401d6dae  mov     rsp, r11
0x1401d6db1  pop     r14
0x1401d6db3  pop     rdi
0x1401d6db4  pop     rbp
0x1401d6db5  retn
0x1401d6db7  mov     eax, 0C0000022h
0x1401d6dbc  jmp     short loc_1401D6DA1
0x1401d6dbe  mov     ecx, ebx
0x1401d6dc0  call    SetLastNtError
0x1401d6dc5  jmp     short loc_1401D6D9F
0x1401d6dc7  cmp     edx, eax
0x1401d6dc9  jz      short loc_1401D6E19
0x1401d6dcb  mov     rax, cs:__imp_luidSystem
0x1401d6dd2  cmp     edx, [rax]
0x1401d6dd4  jnz     short loc_1401D6DE4
0x1401d6dd6  mov     r9d, [rax+4]
0x1401d6dda  cmp     [rdi+0Ch], r9d
0x1401d6dde  jnz     short loc_1401D6DE4
0x1401d6de0  xor     ebx, ebx
0x1401d6de2  jmp     short loc_1401D6D80
0x1401d6de4  mov     r9, cs:__imp_WinStaMapping
0x1401d6deb  mov     r8b, 1
0x1401d6dee  mov     edx, esi
0x1401d6df0  call    cs:__imp_AccessCheckObject
0x1401d6df7  nop     dword ptr [rax+rax+00h]
0x1401d6dfc  test    eax, eax
0x1401d6dfe  jz      short loc_1401D6D80
0x1401d6e00  jmp     short loc_1401D6DE0
0x1401d6e02  mov     ebx, 0C0000017h
0x1401d6e07  mov     rcx, [rbp+TokenHandle]; Handle
0x1401d6e0b  call    cs:__imp_ZwClose
0x1401d6e12  nop     dword ptr [rax+rax+00h]
0x1401d6e17  jmp     short loc_1401D6D9F
0x1401d6e19  mov     eax, [rcx+9Ch]
0x1401d6e1f  cmp     [rdi+0Ch], eax
0x1401d6e22  jz      short loc_1401D6DE0
0x1401d6e24  jmp     short loc_1401D6DCB
0x1401d6e26  mov     ecx, [rcx+9Ch]
0x1401d6e2c  xor     edx, edx
0x1401d6e2e  cmp     [rdi+0Ch], ecx
0x1401d6e31  cmovz   ebx, edx
0x1401d6e34  jmp     loc_1401D6D80
```
