# WcpFilterLoadWithPrivilege

- ea: `0x14024d890`
- end: `0x14024d9ef`
- name: `WcpFilterLoadWithPrivilege`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14024d534`

## callees

- `0x14024d058`
- `0x14024d890`
- `0x14024d9f8`
- `0x14024da6c`

## import_xrefs

- `ntdll!RtlImpersonateSelf` at `0x14024d919`
- `ntdll!RtlImpersonateSelf` at `0x14024d919`
- `ntdll!NtOpenThreadToken` at `0x14024d8ed`
- `ntdll!NtOpenThreadToken` at `0x14024d93a`
- `ntdll!NtOpenThreadToken` at `0x14024d8ed`
- `ntdll!NtOpenThreadToken` at `0x14024d93a`
- `ntdll!NtSetInformationThread` at `0x14024d9c4`
- `ntdll!NtSetInformationThread` at `0x14024d9c4`
- `ntdll!NtClose` at `0x14024d999`
- `ntdll!NtClose` at `0x14024d999`

## pseudocode

```c
__int64 __fastcall WcpFilterLoadWithPrivilege(__int64 a1)
{
  int v1; // edi
  int v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 ThreadInformation; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(ThreadInformation) = HIDWORD(a1);
  v1 = 0;
  TokenHandle = (void *)-1LL;
  LODWORD(ThreadInformation) = 0;
  v2 = NtFilterLoad();
  v3 = v2;
  if ( v2 < 0 && (v2 == -2147023582 || v2 == (unsigned int)FilterHResultFromNtStatus(3221225569LL)) )
  {
    v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle);
    if ( v4
      && (v4 != -1073741700
       || (v4 = RtlImpersonateSelf(SecurityImpersonation), v4 < 0)
       || (v1 = 1, (v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle)) != 0)) )
    {
      v3 = FilterHResultFromNtStatus((unsigned int)v4);
    }
    else
    {
      v6 = WcpSetPrivilege(TokenHandle, v5, 1, &ThreadInformation);
      if ( v6 )
        v7 = FilterHResultFromNtStatus(v6);
      else
        v7 = NtFilterLoad();
      v3 = v7;
      if ( !v1 && (_DWORD)ThreadInformation && (unsigned int)WcpSetPrivilege(TokenHandle, v8, 0, 0) )
        goto LABEL_19;
    }
  }
  if ( TokenHandle != (void *)-1LL )
    NtClose(TokenHandle);
  if ( v1 )
  {
    ThreadInformation = 0;
    if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) )
LABEL_19:
      __fastfail(7u);
  }
  return v3;
}

```

## disassembly

```asm
0x14024d890  mov     rax, rsp
0x14024d893  mov     [rax+18h], rbx
0x14024d897  mov     [rax+20h], rdi
0x14024d89b  mov     [rax+8], rcx
0x14024d89f  push    r14
0x14024d8a1  sub     rsp, 20h
0x14024d8a5  xor     edi, edi
0x14024d8a7  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x14024d8af  mov     [rax+8], edi
0x14024d8b2  call    NtFilterLoad
0x14024d8b7  lea     r14, [rdi-2]
0x14024d8bb  mov     ebx, eax
0x14024d8bd  test    eax, eax
0x14024d8bf  jns     loc_14024D98E
0x14024d8c5  cmp     eax, 80070522h
0x14024d8ca  jz      short loc_14024D8DE
0x14024d8cc  mov     ecx, 0C0000061h
0x14024d8d1  call    FilterHResultFromNtStatus
0x14024d8d6  cmp     ebx, eax
0x14024d8d8  jnz     loc_14024D98E
0x14024d8de  xor     r8d, r8d; OpenAsSelf
0x14024d8e1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x14024d8e6  mov     rcx, r14; ThreadHandle
0x14024d8e9  lea     edx, [r8+28h]; DesiredAccess
0x14024d8ed  call    cs:__imp_NtOpenThreadToken
0x14024d8f4  nop     dword ptr [rax+rax+00h]
0x14024d8f9  mov     ebx, 1
0x14024d8fe  test    eax, eax
0x14024d900  jz      short loc_14024D94A
0x14024d902  cmp     eax, 0C000007Ch
0x14024d907  jz      short loc_14024D914
0x14024d909  mov     ecx, eax
0x14024d90b  call    FilterHResultFromNtStatus
0x14024d910  mov     ebx, eax
0x14024d912  jmp     short loc_14024D98E
0x14024d914  mov     ecx, 2; ImpersonationLevel
0x14024d919  call    cs:__imp_RtlImpersonateSelf
0x14024d920  nop     dword ptr [rax+rax+00h]
0x14024d925  test    eax, eax
0x14024d927  js      short loc_14024D909
0x14024d929  xor     r8d, r8d; OpenAsSelf
0x14024d92c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x14024d931  mov     rcx, r14; ThreadHandle
0x14024d934  mov     edi, ebx
0x14024d936  lea     edx, [r8+28h]; DesiredAccess
0x14024d93a  call    cs:__imp_NtOpenThreadToken
0x14024d941  nop     dword ptr [rax+rax+00h]
0x14024d946  test    eax, eax
0x14024d948  jnz     short loc_14024D909
0x14024d94a  mov     rcx, [rsp+28h+TokenHandle]
0x14024d94f  lea     r9, [rsp+28h+ThreadInformation]
0x14024d954  mov     r8d, ebx
0x14024d957  call    WcpSetPrivilege
0x14024d95c  test    eax, eax
0x14024d95e  jz      short loc_14024D969
0x14024d960  mov     ecx, eax
0x14024d962  call    FilterHResultFromNtStatus
0x14024d967  jmp     short loc_14024D96E
0x14024d969  call    NtFilterLoad
0x14024d96e  mov     ebx, eax
0x14024d970  test    edi, edi
0x14024d972  jnz     short loc_14024D98E
0x14024d974  cmp     dword ptr [rsp+28h+ThreadInformation], edi
0x14024d978  jz      short loc_14024D98E
0x14024d97a  mov     rcx, [rsp+28h+TokenHandle]
0x14024d97f  xor     r9d, r9d
0x14024d982  xor     r8d, r8d
0x14024d985  call    WcpSetPrivilege
0x14024d98a  test    eax, eax
0x14024d98c  jnz     short loc_14024D9D4
0x14024d98e  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x14024d993  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14024d997  jz      short loc_14024D9A5
0x14024d999  call    cs:__imp_NtClose
0x14024d9a0  nop     dword ptr [rax+rax+00h]
0x14024d9a5  test    edi, edi
0x14024d9a7  jz      short loc_14024D9DB
0x14024d9a9  mov     r9d, 8; ThreadInformationLength
0x14024d9af  mov     [rsp+28h+ThreadInformation], 0
0x14024d9b8  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x14024d9bd  mov     rcx, r14; ThreadHandle
0x14024d9c0  lea     edx, [r9-3]; ThreadInformationClass
0x14024d9c4  call    cs:__imp_NtSetInformationThread
0x14024d9cb  nop     dword ptr [rax+rax+00h]
0x14024d9d0  test    eax, eax
0x14024d9d2  jz      short loc_14024D9DB
0x14024d9d4  mov     ecx, 7
0x14024d9d9  int     29h; Win8: RtlFailFast(ecx)
0x14024d9db  mov     rdi, [rsp+28h+arg_18]
0x14024d9e0  mov     eax, ebx
0x14024d9e2  mov     rbx, [rsp+28h+arg_10]
0x14024d9e7  add     rsp, 20h
0x14024d9eb  pop     r14
0x14024d9ed  retn
```
