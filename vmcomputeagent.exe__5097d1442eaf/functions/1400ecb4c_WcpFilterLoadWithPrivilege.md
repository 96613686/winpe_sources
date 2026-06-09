# WcpFilterLoadWithPrivilege

- ea: `0x1400ecb4c`
- end: `0x1400ecc8c`
- name: `WcpFilterLoadWithPrivilege`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400ec840`

## callees

- `0x1400ec3b4`
- `0x1400ecb4c`
- `0x1400ecc94`
- `0x1400ecd04`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1400ecc68`
- `ntdll!NtSetInformationThread` at `0x1400ecc68`
- `ntdll!NtOpenThreadToken` at `0x1400ecba9`
- `ntdll!NtOpenThreadToken` at `0x1400ecbea`
- `ntdll!NtOpenThreadToken` at `0x1400ecba9`
- `ntdll!NtOpenThreadToken` at `0x1400ecbea`
- `ntdll!RtlImpersonateSelf` at `0x1400ecbcf`
- `ntdll!RtlImpersonateSelf` at `0x1400ecbcf`
- `ntdll!NtClose` at `0x1400ecc43`
- `ntdll!NtClose` at `0x1400ecc43`

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
0x1400ecb4c  mov     rax, rsp
0x1400ecb4f  mov     [rax+18h], rbx
0x1400ecb53  mov     [rax+20h], rdi
0x1400ecb57  mov     [rax+8], rcx
0x1400ecb5b  push    r14
0x1400ecb5d  sub     rsp, 20h
0x1400ecb61  xor     edi, edi
0x1400ecb63  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1400ecb6b  mov     [rax+8], edi
0x1400ecb6e  call    NtFilterLoad
0x1400ecb73  lea     r14, [rdi-2]
0x1400ecb77  mov     ebx, eax
0x1400ecb79  test    eax, eax
0x1400ecb7b  jns     loc_1400ECC38
0x1400ecb81  cmp     eax, 80070522h
0x1400ecb86  jz      short loc_1400ECB9A
0x1400ecb88  mov     ecx, 0C0000061h
0x1400ecb8d  call    FilterHResultFromNtStatus
0x1400ecb92  cmp     ebx, eax
0x1400ecb94  jnz     loc_1400ECC38
0x1400ecb9a  xor     r8d, r8d; OpenAsSelf
0x1400ecb9d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1400ecba2  mov     rcx, r14; ThreadHandle
0x1400ecba5  lea     edx, [r8+28h]; DesiredAccess
0x1400ecba9  call    cs:__imp_NtOpenThreadToken
0x1400ecbaf  mov     ebx, 1
0x1400ecbb4  test    eax, eax
0x1400ecbb6  jz      short loc_1400ECBF4
0x1400ecbb8  cmp     eax, 0C000007Ch
0x1400ecbbd  jz      short loc_1400ECBCA
0x1400ecbbf  mov     ecx, eax
0x1400ecbc1  call    FilterHResultFromNtStatus
0x1400ecbc6  mov     ebx, eax
0x1400ecbc8  jmp     short loc_1400ECC38
0x1400ecbca  mov     ecx, 2; ImpersonationLevel
0x1400ecbcf  call    cs:__imp_RtlImpersonateSelf
0x1400ecbd5  test    eax, eax
0x1400ecbd7  js      short loc_1400ECBBF
0x1400ecbd9  xor     r8d, r8d; OpenAsSelf
0x1400ecbdc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1400ecbe1  mov     rcx, r14; ThreadHandle
0x1400ecbe4  mov     edi, ebx
0x1400ecbe6  lea     edx, [r8+28h]; DesiredAccess
0x1400ecbea  call    cs:__imp_NtOpenThreadToken
0x1400ecbf0  test    eax, eax
0x1400ecbf2  jnz     short loc_1400ECBBF
0x1400ecbf4  mov     rcx, [rsp+28h+TokenHandle]
0x1400ecbf9  lea     r9, [rsp+28h+ThreadInformation]
0x1400ecbfe  mov     r8d, ebx
0x1400ecc01  call    WcpSetPrivilege
0x1400ecc06  test    eax, eax
0x1400ecc08  jz      short loc_1400ECC13
0x1400ecc0a  mov     ecx, eax
0x1400ecc0c  call    FilterHResultFromNtStatus
0x1400ecc11  jmp     short loc_1400ECC18
0x1400ecc13  call    NtFilterLoad
0x1400ecc18  mov     ebx, eax
0x1400ecc1a  test    edi, edi
0x1400ecc1c  jnz     short loc_1400ECC38
0x1400ecc1e  cmp     dword ptr [rsp+28h+ThreadInformation], edi
0x1400ecc22  jz      short loc_1400ECC38
0x1400ecc24  mov     rcx, [rsp+28h+TokenHandle]
0x1400ecc29  xor     r9d, r9d
0x1400ecc2c  xor     r8d, r8d
0x1400ecc2f  call    WcpSetPrivilege
0x1400ecc34  test    eax, eax
0x1400ecc36  jnz     short loc_1400ECC72
0x1400ecc38  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x1400ecc3d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400ecc41  jz      short loc_1400ECC49
0x1400ecc43  call    cs:__imp_NtClose
0x1400ecc49  test    edi, edi
0x1400ecc4b  jz      short loc_1400ECC79
0x1400ecc4d  mov     r9d, 8; ThreadInformationLength
0x1400ecc53  mov     [rsp+28h+ThreadInformation], 0
0x1400ecc5c  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1400ecc61  mov     rcx, r14; ThreadHandle
0x1400ecc64  lea     edx, [r9-3]; ThreadInformationClass
0x1400ecc68  call    cs:__imp_NtSetInformationThread
0x1400ecc6e  test    eax, eax
0x1400ecc70  jz      short loc_1400ECC79
0x1400ecc72  mov     ecx, 7
0x1400ecc77  int     29h; Win8: RtlFailFast(ecx)
0x1400ecc79  mov     rdi, [rsp+28h+arg_18]
0x1400ecc7e  mov     eax, ebx
0x1400ecc80  mov     rbx, [rsp+28h+arg_10]
0x1400ecc85  add     rsp, 20h
0x1400ecc89  pop     r14
0x1400ecc8b  retn
```
