# ValidateSessionIdOnTokenAndLinkedToken(void *,ulong,int *)

- ea: `0x14008c76c`
- end: `0x14008c9c9`
- name: `?ValidateSessionIdOnTokenAndLinkedToken@@YAKPEAXKPEAH@Z`
- size: `605`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140051d40`

## callees

- `0x1400057f4`
- `0x14004df08`
- `0x14008c76c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008c8e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008c8e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008c7c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008c887`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008c94c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008c7c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008c887`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008c94c`

## pseudocode

```c
__int64 __fastcall ValidateSessionIdOnTokenAndLinkedToken(HANDLE TokenHandle, int a2, int *a3)
{
  DWORD LastError; // eax
  DWORD v7; // ebx
  CUser *v8; // r10
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  DWORD v12; // eax
  HANDLE hObject[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int TokenInformation; // [rsp+80h] [rbp+40h] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  TokenInformation = -1;
  hObject[0] = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 155;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, LastError);
LABEL_19:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  v10 = TokenInformation;
  v7 = 0;
  if ( TokenInformation != a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_20;
    }
    v11 = 156;
    goto LABEL_12;
  }
  if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, hObject, 8u, &ReturnLength) )
  {
    v12 = GetLastError();
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v12);
    }
    goto LABEL_18;
  }
  if ( GetTokenInformation(hObject[0], TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    v10 = TokenInformation;
    if ( TokenInformation != a2 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_20;
      }
      v11 = 159;
LABEL_12:
      WPP_SF_DD(*((_QWORD *)v8 + 2), v11, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v10, a2);
      goto LABEL_19;
    }
LABEL_18:
    *a3 = 1;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v7 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 158;
    goto LABEL_6;
  }
LABEL_20:
  if ( hObject[0] )
  {
    CloseHandle(hObject[0]);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_d(*((_QWORD *)v8 + 2), 160, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x14008c76c  mov     [rsp-28h+arg_0], rbx
0x14008c771  mov     [rsp-28h+arg_8], rsi
0x14008c776  push    rbp
0x14008c777  push    rdi
0x14008c778  push    r12
0x14008c77a  push    r14
0x14008c77c  push    r15
0x14008c77e  mov     rbp, rsp
0x14008c781  sub     rsp, 40h
0x14008c785  mov     r9d, 4; TokenInformationLength
0x14008c78b  mov     dword ptr [r8], 0
0x14008c792  mov     rsi, r8
0x14008c795  mov     [rbp+TokenInformation], 0FFFFFFFFh
0x14008c79c  mov     edi, edx
0x14008c79e  mov     [rbp+hObject], 0
0x14008c7a6  lea     rax, [rbp+arg_18]
0x14008c7aa  mov     [rbp+arg_18], 0
0x14008c7b1  lea     edx, [r9+8]; TokenInformationClass
0x14008c7b5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x14008c7ba  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14008c7be  mov     r14, rcx
0x14008c7c1  call    cs:__imp_GetTokenInformation
0x14008c7c7  mov     r15d, 1000h
0x14008c7cd  lea     r12, WPP_GLOBAL_Control
0x14008c7d4  test    eax, eax
0x14008c7d6  jnz     short loc_14008C822
0x14008c7d8  call    cs:__imp_GetLastError
0x14008c7de  mov     ebx, eax
0x14008c7e0  mov     r10, cs:WPP_GLOBAL_Control
0x14008c7e7  cmp     r10, r12
0x14008c7ea  jz      loc_14008C8D8
0x14008c7f0  test    [r10+1Ch], r15d
0x14008c7f4  jz      loc_14008C8D8
0x14008c7fa  cmp     byte ptr [r10+19h], 2
0x14008c7ff  jb      loc_14008C8D8
0x14008c805  mov     edx, 9Bh
0x14008c80a  mov     rcx, [r10+10h]
0x14008c80e  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c815  mov     r9d, eax
0x14008c818  call    WPP_SF_d
0x14008c81d  jmp     loc_14008C8D1
0x14008c822  mov     r9d, [rbp+TokenInformation]
0x14008c826  xor     ebx, ebx
0x14008c828  cmp     r9d, edi
0x14008c82b  jz      short loc_14008C86D
0x14008c82d  mov     r10, cs:WPP_GLOBAL_Control
0x14008c834  cmp     r10, r12
0x14008c837  jz      loc_14008C8D8
0x14008c83d  test    [r10+1Ch], r15d
0x14008c841  jz      loc_14008C8D8
0x14008c847  cmp     byte ptr [r10+19h], 4
0x14008c84c  jb      loc_14008C8D8
0x14008c852  mov     edx, 9Ch
0x14008c857  mov     rcx, [r10+10h]
0x14008c85b  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c862  mov     dword ptr [rsp+40h+ReturnLength], edi
0x14008c866  call    WPP_SF_DD
0x14008c86b  jmp     short loc_14008C8D1
0x14008c86d  mov     r9d, 8; TokenInformationLength
0x14008c873  lea     rax, [rbp+arg_18]
0x14008c877  lea     r8, [rbp+hObject]; TokenInformation
0x14008c87b  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x14008c880  mov     rcx, r14; TokenHandle
0x14008c883  lea     edx, [r9+0Bh]; TokenInformationClass
0x14008c887  call    cs:__imp_GetTokenInformation
0x14008c88d  test    eax, eax
0x14008c88f  jnz     loc_14008C931
0x14008c895  call    cs:__imp_GetLastError
0x14008c89b  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c8a2  cmp     rcx, r12
0x14008c8a5  jz      short loc_14008C8CB
0x14008c8a7  test    [rcx+1Ch], r15d
0x14008c8ab  jz      short loc_14008C8CB
0x14008c8ad  cmp     byte ptr [rcx+19h], 5
0x14008c8b1  jb      short loc_14008C8CB
0x14008c8b3  mov     rcx, [rcx+10h]
0x14008c8b7  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c8be  mov     edx, 9Dh
0x14008c8c3  mov     r9d, eax
0x14008c8c6  call    WPP_SF_d
0x14008c8cb  mov     dword ptr [rsi], 1
0x14008c8d1  mov     r10, cs:WPP_GLOBAL_Control
0x14008c8d8  mov     rcx, [rbp+hObject]; hObject
0x14008c8dc  test    rcx, rcx
0x14008c8df  jz      short loc_14008C8EE
0x14008c8e1  call    cs:__imp_CloseHandle
0x14008c8e7  mov     r10, cs:WPP_GLOBAL_Control
0x14008c8ee  cmp     r10, r12
0x14008c8f1  jz      short loc_14008C918
0x14008c8f3  test    [r10+1Ch], r15d
0x14008c8f7  jz      short loc_14008C918
0x14008c8f9  cmp     byte ptr [r10+19h], 5
0x14008c8fe  jb      short loc_14008C918
0x14008c900  mov     rcx, [r10+10h]
0x14008c904  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c90b  mov     edx, 0A0h
0x14008c910  mov     r9d, ebx
0x14008c913  call    WPP_SF_d
0x14008c918  mov     rsi, [rsp+40h+arg_8]
0x14008c91d  mov     eax, ebx
0x14008c91f  mov     rbx, [rsp+40h+arg_0]
0x14008c924  add     rsp, 40h
0x14008c928  pop     r15
0x14008c92a  pop     r14
0x14008c92c  pop     r12
0x14008c92e  pop     rdi
0x14008c92f  pop     rbp
0x14008c930  retn
0x14008c931  mov     rcx, [rbp+hObject]; TokenHandle
0x14008c935  lea     rax, [rbp+arg_18]
0x14008c939  mov     r9d, 4; TokenInformationLength
0x14008c93f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x14008c944  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14008c948  lea     edx, [r9+8]; TokenInformationClass
0x14008c94c  call    cs:__imp_GetTokenInformation
0x14008c952  test    eax, eax
0x14008c954  jnz     short loc_14008C98D
0x14008c956  call    cs:__imp_GetLastError
0x14008c95c  mov     ebx, eax
0x14008c95e  mov     r10, cs:WPP_GLOBAL_Control
0x14008c965  cmp     r10, r12
0x14008c968  jz      loc_14008C8D8
0x14008c96e  test    [r10+1Ch], r15d
0x14008c972  jz      loc_14008C8D8
0x14008c978  cmp     byte ptr [r10+19h], 2
0x14008c97d  jb      loc_14008C8D8
0x14008c983  mov     edx, 9Eh
0x14008c988  jmp     loc_14008C80A
0x14008c98d  mov     r9d, [rbp+TokenInformation]
0x14008c991  cmp     r9d, edi
0x14008c994  jz      loc_14008C8CB
0x14008c99a  mov     r10, cs:WPP_GLOBAL_Control
0x14008c9a1  cmp     r10, r12
0x14008c9a4  jz      loc_14008C8D8
0x14008c9aa  test    [r10+1Ch], r15d
0x14008c9ae  jz      loc_14008C8D8
0x14008c9b4  cmp     byte ptr [r10+19h], 4
0x14008c9b9  jb      loc_14008C8D8
0x14008c9bf  mov     edx, 9Fh
0x14008c9c4  jmp     loc_14008C857
```
