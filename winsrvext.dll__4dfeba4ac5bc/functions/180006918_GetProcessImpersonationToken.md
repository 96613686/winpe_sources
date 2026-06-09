# GetProcessImpersonationToken

- ea: `0x180006918`
- end: `0x180006a1c`
- name: `GetProcessImpersonationToken`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007374`

## callees

- `0x180006918`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800069d1`
- `ntdll!NtDuplicateToken` at `0x1800069d1`
- `ntdll!NtOpenProcessToken` at `0x18000695b`
- `ntdll!NtOpenProcessToken` at `0x18000695b`
- `ntdll!NtClose` at `0x1800069e5`
- `ntdll!NtClose` at `0x1800069f6`
- `ntdll!NtClose` at `0x1800069e5`
- `ntdll!NtClose` at `0x1800069f6`

## pseudocode

```c
void *__fastcall GetProcessImpersonationToken(void *a1)
{
  void *TokenHandle; // [rsp+30h] [rbp-9h] BYREF
  void *NewTokenHandle; // [rsp+38h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp+7h] BYREF
  __int64 v5; // [rsp+70h] [rbp+37h] BYREF
  int v6; // [rsp+78h] [rbp+3Fh]

  v5 = 0;
  v6 = 0;
  TokenHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  NewTokenHandle = 0;
  if ( NtOpenProcessToken(a1, 2u, &TokenHandle) < 0 )
    return 0;
  ObjectAttributes.SecurityQualityOfService = &v5;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v5 = 0x20000000CLL;
  LOWORD(v6) = 1;
  if ( NtDuplicateToken(TokenHandle, 0xCu, &ObjectAttributes, 0, TokenImpersonation, &NewTokenHandle) < 0 )
  {
    NtClose(TokenHandle);
    return 0;
  }
  NtClose(TokenHandle);
  return NewTokenHandle;
}

```

## disassembly

```asm
0x180006918  push    rbp
0x18000691a  lea     rbp, [rsp-57h]
0x18000691f  sub     rsp, 90h
0x180006926  mov     rax, cs:__security_cookie
0x18000692d  xor     rax, rsp
0x180006930  mov     [rbp+57h+var_10], rax
0x180006934  xor     eax, eax
0x180006936  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000693a  xorps   xmm0, xmm0
0x18000693d  mov     [rbp+57h+var_20], rax
0x180006941  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006945  mov     [rbp+57h+var_18], eax
0x180006948  lea     edx, [rax+2]; DesiredAccess
0x18000694b  mov     [rbp+57h+TokenHandle], rax
0x18000694f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006953  mov     [rbp+57h+var_58], rax
0x180006957  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000695b  call    cs:__imp_NtOpenProcessToken
0x180006962  nop     dword ptr [rax+rax+00h]
0x180006967  test    eax, eax
0x180006969  jns     short loc_180006972
0x18000696b  xor     eax, eax
0x18000696d  jmp     loc_180006A06
0x180006972  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180006976  lea     rax, [rbp+57h+var_20]
0x18000697a  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18000697e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006982  lea     rax, [rbp+57h+var_58]
0x180006986  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000698d  mov     edx, 0Ch; DesiredAccess
0x180006992  mov     [rsp+90h+NewTokenHandle], rax; NewTokenHandle
0x180006997  xor     r9d, r9d; EffectiveOnly
0x18000699a  mov     [rsp+90h+TokenType], 2; TokenType
0x1800069a2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800069aa  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800069b1  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800069b9  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x1800069c1  mov     dword ptr [rbp+57h+var_20], edx
0x1800069c4  mov     dword ptr [rbp+57h+var_20+4], 2
0x1800069cb  mov     word ptr [rbp+57h+var_18], 1
0x1800069d1  call    cs:__imp_NtDuplicateToken
0x1800069d8  nop     dword ptr [rax+rax+00h]
0x1800069dd  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800069e1  test    eax, eax
0x1800069e3  jns     short loc_1800069F6
0x1800069e5  call    cs:__imp_NtClose
0x1800069ec  nop     dword ptr [rax+rax+00h]
0x1800069f1  jmp     loc_18000696B
0x1800069f6  call    cs:__imp_NtClose
0x1800069fd  nop     dword ptr [rax+rax+00h]
0x180006a02  mov     rax, [rbp+57h+var_58]
0x180006a06  mov     rcx, [rbp+57h+var_10]
0x180006a0a  xor     rcx, rsp; StackCookie
0x180006a0d  call    __security_check_cookie
0x180006a12  add     rsp, 90h
0x180006a19  pop     rbp
0x180006a1a  retn
```
