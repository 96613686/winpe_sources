# SampValidateDSRMPwdSet(void)

- ea: `0x18005c180`
- end: `0x18005c2d2`
- name: `?SampValidateDSRMPwdSet@@YAJXZ`
- size: `338`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005c690`
- `0x18005c7f0`

## callees

- `0x18001cfa0`
- `0x18001d0d0`
- `0x180027e24`
- `0x18002d720`
- `0x18005c180`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18005c1e6`
- `ntdll!NtQueryInformationToken` at `0x18005c245`
- `ntdll!NtQueryInformationToken` at `0x18005c1e6`
- `ntdll!NtQueryInformationToken` at `0x18005c245`
- `ntdll!RtlEqualSid` at `0x18005c26d`
- `ntdll!RtlEqualSid` at `0x18005c26d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c206`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c28e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c28e`

## pseudocode

```c
__int64 SampValidateDSRMPwdSet(void)
{
  NTSTATUS v0; // ebx
  PUNICODE_STRING v1; // rcx
  __int64 v2; // rdx
  unsigned int *v3; // rdi
  unsigned int *v4; // rax
  unsigned int i; // esi
  ULONG TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  v8 = 0;
  v0 = SampImpersonateClient(&v8);
  if ( v0 >= 0 )
  {
    v3 = 0;
    v0 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenGroups, 0, 0, &TokenInformationLength);
    if ( v0 == -1073741789 && TokenInformationLength )
    {
      v4 = (unsigned int *)LocalAlloc(0x40u, TokenInformationLength);
      v3 = v4;
      if ( v4 )
      {
        memset_0(v4, 0, TokenInformationLength);
        v0 = NtQueryInformationToken(
               (HANDLE)0xFFFFFFFFFFFFFFFBLL,
               TokenGroups,
               v3,
               TokenInformationLength,
               &TokenInformationLength);
        if ( v0 >= 0 )
        {
          v0 = -1073741790;
          for ( i = 0; i < *v3; ++i )
          {
            if ( RtlEqualSid(*(PSID *)&v3[4 * i + 2], SampAdministratorsAliasSid) )
            {
              v0 = 0;
              break;
            }
          }
        }
      }
      else
      {
        v0 = -1073741670;
      }
    }
    SampRevertToSelf(v8);
    if ( v3 )
      LocalFree(v3);
    v1 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v2 = 11;
      goto LABEL_18;
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v2 = 10;
LABEL_18:
      WPP_SF_Dd(v1[3].Buffer, v2, WPP_cbf2dcf21a9d3f9d96f9bb6fd4e12ae5_Traceguids, (unsigned int)v0, v0);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18005c180  mov     rax, rsp
0x18005c183  mov     [rax+18h], rbx
0x18005c187  mov     [rax+20h], rsi
0x18005c18b  push    rdi
0x18005c18c  sub     rsp, 30h
0x18005c190  lea     rcx, [rax+10h]
0x18005c194  mov     dword ptr [rax+8], 0
0x18005c19b  mov     dword ptr [rax+10h], 0
0x18005c1a2  call    SampImpersonateClient
0x18005c1a7  mov     ebx, eax
0x18005c1a9  test    eax, eax
0x18005c1ab  jns     short loc_18005C1CB
0x18005c1ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1b4  test    dword ptr [rcx+44h], 20000h
0x18005c1bb  jz      loc_18005C2C0
0x18005c1c1  mov     edx, 0Ah
0x18005c1c6  jmp     loc_18005C2A9
0x18005c1cb  xor     edi, edi
0x18005c1cd  lea     rax, [rsp+38h+TokenInformationLength]
0x18005c1d2  xor     r9d, r9d; TokenInformationLength
0x18005c1d5  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005c1da  xor     r8d, r8d; TokenInformation
0x18005c1dd  lea     esi, [rdi+2]
0x18005c1e0  mov     edx, esi; TokenInformationClass
0x18005c1e2  lea     rcx, [rdi-5]; TokenHandle
0x18005c1e6  call    cs:__imp_NtQueryInformationToken
0x18005c1ec  mov     ebx, eax
0x18005c1ee  cmp     eax, 0C0000023h
0x18005c1f3  jnz     loc_18005C27D
0x18005c1f9  mov     eax, [rsp+38h+TokenInformationLength]
0x18005c1fd  test    eax, eax
0x18005c1ff  jz      short loc_18005C27D
0x18005c201  mov     edx, eax; uBytes
0x18005c203  lea     ecx, [rdi+40h]; uFlags
0x18005c206  call    cs:__imp_LocalAlloc
0x18005c20c  mov     rdi, rax
0x18005c20f  test    rax, rax
0x18005c212  jnz     short loc_18005C21B
0x18005c214  mov     ebx, 0C000009Ah
0x18005c219  jmp     short loc_18005C27D
0x18005c21b  mov     r8d, [rsp+38h+TokenInformationLength]; Size
0x18005c220  xor     edx, edx; Val
0x18005c222  mov     rcx, rdi; void *
0x18005c225  call    memset_0
0x18005c22a  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18005c22f  lea     rax, [rsp+38h+TokenInformationLength]
0x18005c234  mov     r8, rdi; TokenInformation
0x18005c237  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005c23c  mov     edx, esi; TokenInformationClass
0x18005c23e  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18005c245  call    cs:__imp_NtQueryInformationToken
0x18005c24b  mov     ebx, eax
0x18005c24d  test    eax, eax
0x18005c24f  js      short loc_18005C27D
0x18005c251  mov     ebx, 0C0000022h
0x18005c256  xor     esi, esi
0x18005c258  cmp     esi, [rdi]
0x18005c25a  jnb     short loc_18005C27D
0x18005c25c  mov     rdx, cs:SampAdministratorsAliasSid; Sid2
0x18005c263  mov     ecx, esi
0x18005c265  add     rcx, rcx
0x18005c268  mov     rcx, [rdi+rcx*8+8]; Sid1
0x18005c26d  call    cs:__imp_RtlEqualSid
0x18005c273  test    al, al
0x18005c275  jnz     short loc_18005C27B
0x18005c277  inc     esi
0x18005c279  jmp     short loc_18005C258
0x18005c27b  xor     ebx, ebx
0x18005c27d  mov     ecx, [rsp+38h+arg_8]
0x18005c281  call    SampRevertToSelf
0x18005c286  test    rdi, rdi
0x18005c289  jz      short loc_18005C294
0x18005c28b  mov     rcx, rdi; hMem
0x18005c28e  call    cs:__imp_LocalFree
0x18005c294  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c29b  test    dword ptr [rcx+44h], 20000h
0x18005c2a2  jz      short loc_18005C2C0
0x18005c2a4  mov     edx, 0Bh
0x18005c2a9  mov     rcx, [rcx+38h]
0x18005c2ad  lea     r8, WPP_cbf2dcf21a9d3f9d96f9bb6fd4e12ae5_Traceguids
0x18005c2b4  mov     r9d, ebx
0x18005c2b7  mov     dword ptr [rsp+38h+ReturnLength], ebx
0x18005c2bb  call    WPP_SF_Dd
0x18005c2c0  mov     rsi, [rsp+38h+arg_18]
0x18005c2c5  mov     eax, ebx
0x18005c2c7  mov     rbx, [rsp+38h+arg_10]
0x18005c2cc  add     rsp, 30h
0x18005c2d0  pop     rdi
0x18005c2d1  retn
```
