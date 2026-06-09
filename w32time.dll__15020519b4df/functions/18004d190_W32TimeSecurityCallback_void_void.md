# W32TimeSecurityCallback(void *,void *)

- ea: `0x18004d190`
- end: `0x18004d371`
- name: `?W32TimeSecurityCallback@@YAJPEAX0@Z`
- size: `481`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`
- `0x18004c0ec`
- `0x18004d190`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18004d33e`
- `RPCRT4!RpcRevertToSelf` at `0x18004d33e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004d281`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004d281`
- `RPCRT4!RpcImpersonateClient` at `0x18004d1db`
- `RPCRT4!RpcImpersonateClient` at `0x18004d1db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d233`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d20a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d20a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d223`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d32e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d32e`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18004d302`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18004d302`

## string_xrefs

- `0x18004d2b3`: `RPC Call Attribute is local=%d, kernel=%d, session=%d, authentication=%d, protocol=%d, OpNum=%d\n`

## pseudocode

```c
__int64 __fastcall W32TimeSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  int v5; // edi
  bool v6; // cc
  HANDLE CurrentThread; // rax
  WINBOOL pfResult; // [rsp+40h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-41h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-31h] BYREF
  int v13; // [rsp+78h] [rbp-11h]
  unsigned int v14; // [rsp+80h] [rbp-9h]
  unsigned int v15; // [rsp+84h] [rbp-5h]
  int v16; // [rsp+88h] [rbp-1h]
  unsigned int v17; // [rsp+8Ch] [rbp+3h]
  unsigned __int16 v18; // [rsp+A8h] [rbp+1Fh]

  pfResult = 0;
  TokenHandle = 0;
  memset_0(RpcCallAttributes, 0, 0x70u);
  LastError = RpcImpersonateClient(0);
  v4 = LastError;
  if ( !LastError )
  {
    v5 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
LABEL_7:
      LastError = GetLastError();
      v4 = LastError;
      goto LABEL_3;
    }
    if ( (unsigned __int8)FileLogAllowEntry(69) )
      DumpRpcCaller(TokenHandle);
    memset_0(v12, 0, 0x68u);
    RpcCallAttributes[1] = 32;
    RpcCallAttributes[0] = 2;
    LastError = RpcServerInqCallAttributesW(Context, RpcCallAttributes);
    v4 = LastError;
    v6 = LastError <= 0;
    if ( LastError )
      goto LABEL_4;
    if ( (unsigned __int8)FileLogAllowEntry(69) && (unsigned __int8)FileLogAllowEntry(v4 + 69) )
      FileLogAdd(
        L"RPC Call Attribute is local=%d, kernel=%d, session=%d, authentication=%d, protocol=%d, OpNum=%d\n",
        v17,
        v15,
        v14,
        v13,
        v16,
        v18);
    if ( ((v18 - 2) & 0xFFFB) != 0 || v17 != 1 )
    {
      if ( !PrivilegeCheck(TokenHandle, RequiredPrivileges, &pfResult) )
        goto LABEL_7;
      if ( !pfResult )
      {
        v4 = -2147024891;
        goto LABEL_20;
      }
    }
    v4 = 0;
    goto LABEL_20;
  }
  v5 = 0;
LABEL_3:
  v6 = LastError <= 0;
LABEL_4:
  if ( !v6 )
    v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 )
    RpcRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x18004d190  mov     [rsp-8+arg_0], rbx
0x18004d195  mov     [rsp-8+arg_10], rsi
0x18004d19a  push    rbp
0x18004d19b  push    rdi
0x18004d19c  push    r12
0x18004d19e  lea     rbp, [rsp-47h]
0x18004d1a3  sub     rsp, 0D0h
0x18004d1aa  mov     rax, cs:__security_cookie
0x18004d1b1  xor     rax, rsp
0x18004d1b4  mov     [rbp+57h+var_20], rax
0x18004d1b8  mov     rsi, rdx
0x18004d1bb  mov     [rbp+57h+pfResult], 0
0x18004d1c2  xor     edx, edx; Val
0x18004d1c4  mov     [rbp+57h+TokenHandle], 0
0x18004d1cc  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x18004d1d0  lea     r8d, [rdx+70h]; Size
0x18004d1d4  call    memset_0
0x18004d1d9  xor     ecx, ecx; BindingHandle
0x18004d1db  call    cs:__imp_RpcImpersonateClient
0x18004d1e2  nop     dword ptr [rax+rax+00h]
0x18004d1e7  mov     ebx, eax
0x18004d1e9  test    eax, eax
0x18004d1eb  jz      short loc_18004D205
0x18004d1ed  xor     edi, edi
0x18004d1ef  test    eax, eax
0x18004d1f1  jle     loc_18004D325
0x18004d1f7  movzx   ebx, ax
0x18004d1fa  or      ebx, 80070000h
0x18004d200  jmp     loc_18004D325
0x18004d205  mov     edi, 1
0x18004d20a  call    cs:__imp_GetCurrentThread
0x18004d211  nop     dword ptr [rax+rax+00h]
0x18004d216  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004d21a  xor     r8d, r8d; OpenAsSelf
0x18004d21d  mov     rcx, rax; ThreadHandle
0x18004d220  lea     edx, [rdi+7]; DesiredAccess
0x18004d223  call    cs:__imp_OpenThreadToken
0x18004d22a  nop     dword ptr [rax+rax+00h]
0x18004d22f  test    eax, eax
0x18004d231  jnz     short loc_18004D243
0x18004d233  call    cs:__imp_GetLastError
0x18004d23a  nop     dword ptr [rax+rax+00h]
0x18004d23f  mov     ebx, eax
0x18004d241  jmp     short loc_18004D1EF
0x18004d243  mov     ecx, 45h ; 'E'
0x18004d248  call    FileLogAllowEntry
0x18004d24d  test    al, al
0x18004d24f  jz      short loc_18004D25A
0x18004d251  mov     rcx, [rbp+57h+TokenHandle]; void *
0x18004d255  call    ?DumpRpcCaller@@YAJPEAX@Z; DumpRpcCaller(void *)
0x18004d25a  xor     edx, edx; Val
0x18004d25c  lea     rcx, [rbp+57h+var_88]; void *
0x18004d260  lea     r8d, [rdx+68h]; Size
0x18004d264  call    memset_0
0x18004d269  mov     r12d, 2
0x18004d26f  mov     [rbp+57h+var_8C], 20h ; ' '
0x18004d276  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18004d27a  mov     [rbp+57h+RpcCallAttributes], r12d
0x18004d27e  mov     rcx, rsi; ClientBinding
0x18004d281  call    cs:__imp_RpcServerInqCallAttributesW
0x18004d288  nop     dword ptr [rax+rax+00h]
0x18004d28d  mov     ebx, eax
0x18004d28f  test    eax, eax
0x18004d291  jnz     loc_18004D1F1
0x18004d297  lea     ecx, [rax+45h]
0x18004d29a  call    FileLogAllowEntry
0x18004d29f  test    al, al
0x18004d2a1  jz      short loc_18004D2DC
0x18004d2a3  lea     ecx, [rbx+45h]
0x18004d2a6  call    FileLogAllowEntry
0x18004d2ab  test    al, al
0x18004d2ad  jz      short loc_18004D2DC
0x18004d2af  movzx   eax, [rbp+57h+var_38]
0x18004d2b3  lea     rcx, aRpcCallAttribu; "RPC Call Attribute is local=%d, kernel="...
0x18004d2ba  mov     r9d, [rbp+57h+var_60]
0x18004d2be  mov     r8d, [rbp+57h+var_5C]
0x18004d2c2  mov     edx, [rbp+57h+var_54]
0x18004d2c5  mov     [rsp+0E0h+var_B0], eax
0x18004d2c9  mov     eax, [rbp+57h+var_58]
0x18004d2cc  mov     [rsp+0E0h+var_B8], eax
0x18004d2d0  mov     eax, [rbp+57h+var_68]
0x18004d2d3  mov     [rsp+0E0h+var_C0], eax
0x18004d2d7  call    FileLogAdd
0x18004d2dc  movzx   eax, [rbp+57h+var_38]
0x18004d2e0  mov     ecx, 0FFFBh
0x18004d2e5  sub     ax, r12w
0x18004d2e9  test    cx, ax
0x18004d2ec  jnz     short loc_18004D2F3
0x18004d2ee  cmp     [rbp+57h+var_54], edi
0x18004d2f1  jz      short loc_18004D323
0x18004d2f3  mov     rdx, cs:RequiredPrivileges; RequiredPrivileges
0x18004d2fa  lea     r8, [rbp+57h+pfResult]; pfResult
0x18004d2fe  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x18004d302  call    cs:__imp_PrivilegeCheck
0x18004d309  nop     dword ptr [rax+rax+00h]
0x18004d30e  test    eax, eax
0x18004d310  jz      loc_18004D233
0x18004d316  cmp     [rbp+57h+pfResult], 0
0x18004d31a  jnz     short loc_18004D323
0x18004d31c  mov     ebx, 80070005h
0x18004d321  jmp     short loc_18004D325
0x18004d323  xor     ebx, ebx
0x18004d325  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18004d329  test    rcx, rcx
0x18004d32c  jz      short loc_18004D33A
0x18004d32e  call    cs:__imp_CloseHandle
0x18004d335  nop     dword ptr [rax+rax+00h]
0x18004d33a  test    edi, edi
0x18004d33c  jz      short loc_18004D34A
0x18004d33e  call    cs:__imp_RpcRevertToSelf
0x18004d345  nop     dword ptr [rax+rax+00h]
0x18004d34a  mov     eax, ebx
0x18004d34c  mov     rcx, [rbp+57h+var_20]
0x18004d350  xor     rcx, rsp; StackCookie
0x18004d353  call    __security_check_cookie
0x18004d358  lea     r11, [rsp+0E0h+var_10]
0x18004d360  mov     rbx, [r11+20h]
0x18004d364  mov     rsi, [r11+30h]
0x18004d368  mov     rsp, r11
0x18004d36b  pop     r12
0x18004d36d  pop     rdi
0x18004d36e  pop     rbp
0x18004d36f  retn
```
