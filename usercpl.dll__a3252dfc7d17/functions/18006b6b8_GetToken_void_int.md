# _GetToken(void * *,int *)

- ea: `0x18006b6b8`
- end: `0x18006b91a`
- name: `?_GetToken@@YAJPEAPEAXPEAH@Z`
- size: `610`
- prototype: `__int64 __fastcall(void **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b46c`

## callees

- `0x18006a608`
- `0x18006b6b8`
- `0x1800772c0`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x18006b7c9`
- `ntdll!NtDuplicateToken` at `0x18006b7c9`
- `ntdll!NtOpenProcessToken` at `0x18006b73a`
- `ntdll!NtOpenProcessToken` at `0x18006b73a`
- `ntdll!NtOpenThreadToken` at `0x18006b71b`
- `ntdll!NtOpenThreadToken` at `0x18006b71b`
- `ntdll!NtQueryInformationToken` at `0x18006b835`
- `ntdll!NtQueryInformationToken` at `0x18006b835`
- `ntdll!NtClose` at `0x18006b7fe`
- `ntdll!NtClose` at `0x18006b8ea`
- `ntdll!NtClose` at `0x18006b8f9`
- `ntdll!NtClose` at `0x18006b7fe`
- `ntdll!NtClose` at `0x18006b8ea`
- `ntdll!NtClose` at `0x18006b8f9`

## string_xrefs

- `0x18006b8c8`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006b87f`: `Not an impersonation level token`
- `0x18006b8b4`: `NtOpenThreadToken`
- `0x18006b752`: `NtOpenProcessToken`
- `0x18006b7e1`: `NtDuplicateToken`
- `0x18006b84d`: `NtQueryInformationToken`

## pseudocode

```c
__int64 __fastcall _GetToken(void **a1, int *a2)
{
  unsigned int v3; // ebx
  HANDLE v4; // rax
  TOKEN_TYPE TokenType[2]; // [rsp+20h] [rbp-49h]
  TOKEN_TYPE TokenTypea[2]; // [rsp+20h] [rbp-49h]
  void *TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-21h] BYREF
  int TokenInformation; // [rsp+4Ch] [rbp-1Dh] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  __int64 v13; // [rsp+88h] [rbp+1Fh] BYREF
  int v14; // [rsp+90h] [rbp+27h]

  TokenInformation = 0;
  ReturnLength = 4;
  v13 = 0;
  v14 = 0;
  TokenHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v3 == -1073741700 )
  {
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xAu, &TokenHandle);
    if ( v3 )
    {
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        934,
        L"NtOpenProcessToken",
        &Class);
      goto LABEL_15;
    }
    v13 = 0x20000000CLL;
    ObjectAttributes.SecurityQualityOfService = &v13;
    LOWORD(v14) = 0;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = 0;
    v3 = NtDuplicateToken(TokenHandle, 8u, &ObjectAttributes, 0, TokenImpersonation, &Handle);
    if ( v3 )
    {
      TokenType[0] = 958;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        *(_QWORD *)TokenType,
        L"NtDuplicateToken",
        &Class);
      goto LABEL_15;
    }
    NtClose(TokenHandle);
    v4 = Handle;
    Handle = 0;
LABEL_13:
    *a1 = v4;
    v3 = 0;
    TokenHandle = 0;
    goto LABEL_15;
  }
  if ( !v3 )
  {
    v3 = NtQueryInformationToken(TokenHandle, TokenImpersonationLevel, &TokenInformation, ReturnLength, &ReturnLength);
    if ( v3 )
    {
      TokenTypea[0] = 973;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        *(_QWORD *)TokenTypea,
        L"NtQueryInformationToken",
        &Class);
      goto LABEL_15;
    }
    if ( (unsigned int)(TokenInformation - 2) > 1 )
    {
      v3 = -1073741790;
      TokenTypea[0] = 979;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221225506LL,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        *(_QWORD *)TokenTypea,
        L"Not an impersonation level token",
        &Class);
      goto LABEL_15;
    }
    v4 = TokenHandle;
    goto LABEL_13;
  }
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v3,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    989,
    L"NtOpenThreadToken",
    &Class);
LABEL_15:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  return v3;
}

```

## disassembly

```asm
0x18006b6b8  push    rbp
0x18006b6ba  push    rbx
0x18006b6bb  push    rdi
0x18006b6bc  push    r14
0x18006b6be  lea     rbp, [rsp-3Fh]
0x18006b6c3  sub     rsp, 0A8h
0x18006b6ca  mov     rax, cs:__security_cookie
0x18006b6d1  xor     rax, rsp
0x18006b6d4  mov     [rbp+57h+var_28], rax
0x18006b6d8  xor     eax, eax
0x18006b6da  mov     [rbp+57h+TokenInformation], 0
0x18006b6e1  xorps   xmm0, xmm0
0x18006b6e4  mov     [rbp+57h+ReturnLength], 4
0x18006b6eb  mov     rdi, rcx
0x18006b6ee  mov     [rbp+57h+var_38], rax
0x18006b6f2  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18006b6f6  mov     [rbp+57h+var_30], eax
0x18006b6f9  lea     r14d, [rax+1]
0x18006b6fd  mov     [rbp+57h+TokenHandle], rax
0x18006b701  mov     r8b, r14b; OpenAsSelf
0x18006b704  mov     [rbp+57h+Handle], rax
0x18006b708  lea     edx, [rax+8]; DesiredAccess
0x18006b70b  lea     rcx, [rax-2]; ThreadHandle
0x18006b70f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006b713  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006b717  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b71b  call    cs:__imp_NtOpenThreadToken
0x18006b721  mov     ebx, eax
0x18006b723  cmp     eax, 0C000007Ch
0x18006b728  jnz     loc_18006B815
0x18006b72e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18006b732  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006b736  lea     edx, [r14+9]; DesiredAccess
0x18006b73a  call    cs:__imp_NtOpenProcessToken
0x18006b740  mov     ebx, eax
0x18006b742  test    eax, eax
0x18006b744  jz      short loc_18006B76B
0x18006b746  lea     rax, Class
0x18006b74d  mov     [rsp+0C0h+var_90], rax
0x18006b752  lea     rax, aNtopenprocesst; "NtOpenProcessToken"
0x18006b759  mov     [rsp+0C0h+NewTokenHandle], rax
0x18006b75e  mov     [rsp+0C0h+TokenType], 3A6h
0x18006b766  jmp     loc_18006B8C8
0x18006b76b  mov     ecx, 2
0x18006b770  mov     dword ptr [rbp+57h+var_38], 0Ch
0x18006b777  lea     rax, [rbp+57h+var_38]
0x18006b77b  mov     dword ptr [rbp+57h+var_38+4], ecx
0x18006b77e  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18006b782  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006b786  lea     rax, [rbp+57h+Handle]
0x18006b78a  mov     word ptr [rbp+57h+var_30], 0
0x18006b790  mov     [rsp+0C0h+NewTokenHandle], rax; NewTokenHandle
0x18006b795  lea     edx, [rcx+6]; DesiredAccess
0x18006b798  mov     [rsp+0C0h+TokenType], ecx; TokenType
0x18006b79c  xor     r9d, r9d; EffectiveOnly
0x18006b79f  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18006b7a3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006b7aa  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18006b7b2  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18006b7b9  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18006b7c1  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x18006b7c9  call    cs:__imp_NtDuplicateToken
0x18006b7cf  mov     ebx, eax
0x18006b7d1  test    eax, eax
0x18006b7d3  jz      short loc_18006B7FA
0x18006b7d5  lea     rax, Class
0x18006b7dc  mov     [rsp+0C0h+var_90], rax
0x18006b7e1  lea     rax, aNtduplicatetok; "NtDuplicateToken"
0x18006b7e8  mov     [rsp+0C0h+NewTokenHandle], rax
0x18006b7ed  mov     [rsp+0C0h+TokenType], 3BEh
0x18006b7f5  jmp     loc_18006B8C8
0x18006b7fa  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18006b7fe  call    cs:__imp_NtClose
0x18006b804  mov     rax, [rbp+57h+Handle]
0x18006b808  mov     [rbp+57h+Handle], 0
0x18006b810  jmp     loc_18006B899
0x18006b815  test    ebx, ebx
0x18006b817  jnz     loc_18006B8A8
0x18006b81d  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x18006b821  lea     rax, [rbp+57h+ReturnLength]
0x18006b825  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006b829  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006b82d  lea     edx, [rbx+9]; TokenInformationClass
0x18006b830  mov     qword ptr [rsp+0C0h+TokenType], rax; ReturnLength
0x18006b835  call    cs:__imp_NtQueryInformationToken
0x18006b83b  mov     ebx, eax
0x18006b83d  test    eax, eax
0x18006b83f  jz      short loc_18006B863
0x18006b841  lea     rax, Class
0x18006b848  mov     [rsp+0C0h+var_90], rax
0x18006b84d  lea     rax, aNtqueryinforma; "NtQueryInformationToken"
0x18006b854  mov     [rsp+0C0h+NewTokenHandle], rax
0x18006b859  mov     [rsp+0C0h+TokenType], 3CDh
0x18006b861  jmp     short loc_18006B8C8
0x18006b863  mov     eax, [rbp+57h+TokenInformation]
0x18006b866  add     eax, 0FFFFFFFEh
0x18006b869  cmp     eax, r14d
0x18006b86c  jbe     short loc_18006B895
0x18006b86e  lea     rax, Class
0x18006b875  mov     ebx, 0C0000022h
0x18006b87a  mov     [rsp+0C0h+var_90], rax
0x18006b87f  lea     rax, aNotAnImpersona; "Not an impersonation level token"
0x18006b886  mov     [rsp+0C0h+NewTokenHandle], rax
0x18006b88b  mov     [rsp+0C0h+TokenType], 3D3h
0x18006b893  jmp     short loc_18006B8C8
0x18006b895  mov     rax, [rbp+57h+TokenHandle]
0x18006b899  mov     [rdi], rax
0x18006b89c  xor     ebx, ebx
0x18006b89e  mov     [rbp+57h+TokenHandle], 0
0x18006b8a6  jmp     short loc_18006B8E1
0x18006b8a8  lea     rax, Class
0x18006b8af  mov     [rsp+0C0h+var_90], rax
0x18006b8b4  lea     rax, aNtopenthreadto; "NtOpenThreadToken"
0x18006b8bb  mov     [rsp+0C0h+NewTokenHandle], rax
0x18006b8c0  mov     [rsp+0C0h+TokenType], 3DDh
0x18006b8c8  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006b8cf  mov     r8d, ebx
0x18006b8d2  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006b8d9  mov     ecx, r14d; unsigned int
0x18006b8dc  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006b8e1  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18006b8e5  test    rcx, rcx
0x18006b8e8  jz      short loc_18006B8F0
0x18006b8ea  call    cs:__imp_NtClose
0x18006b8f0  mov     rcx, [rbp+57h+Handle]; Handle
0x18006b8f4  test    rcx, rcx
0x18006b8f7  jz      short loc_18006B8FF
0x18006b8f9  call    cs:__imp_NtClose
0x18006b8ff  mov     eax, ebx
0x18006b901  mov     rcx, [rbp+57h+var_28]
0x18006b905  xor     rcx, rsp; StackCookie
0x18006b908  call    __security_check_cookie
0x18006b90d  add     rsp, 0A8h
0x18006b914  pop     r14
0x18006b916  pop     rdi
0x18006b917  pop     rbx
0x18006b918  pop     rbp
0x18006b919  retn
```
