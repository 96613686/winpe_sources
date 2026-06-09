# SampRevertToSelfIfAnonymous(void * *)

- ea: `0x18000b260`
- end: `0x18000b3ab`
- name: `?SampRevertToSelfIfAnonymous@@YAJPEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013490`

## callees

- `0x1800078c0`
- `0x18000b260`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b383`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b2e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b2e0`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000b31e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000b31e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b328`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b35c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b37a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b35c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b37a`
- `ntdll!NtOpenThreadToken` at `0x18000b290`
- `ntdll!NtOpenThreadToken` at `0x18000b290`
- `ntdll!NtQueryInformationToken` at `0x18000b2c5`
- `ntdll!NtQueryInformationToken` at `0x18000b30a`
- `ntdll!NtQueryInformationToken` at `0x18000b2c5`
- `ntdll!NtQueryInformationToken` at `0x18000b30a`

## pseudocode

```c
__int64 __fastcall SampRevertToSelfIfAnonymous(void **a1)
{
  PSID *v1; // rdi
  NTSTATUS v3; // eax
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  void *v6; // rcx
  ULONG TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF

  v1 = 0;
  TokenInformationLength = 0;
  *a1 = 0;
  TokenHandle = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &TokenHandle);
  v4 = v3;
  if ( v3 != -1073741700 )
  {
    if ( v3 >= 0 )
    {
      v5 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, 0, 0, &TokenInformationLength);
      v4 = v5;
      if ( v5 == -1073741789 )
      {
        v1 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
        if ( v1 )
        {
          v4 = NtQueryInformationToken(
                 (HANDLE)0xFFFFFFFFFFFFFFFBLL,
                 TokenUser,
                 v1,
                 TokenInformationLength,
                 &TokenInformationLength);
          if ( v4 >= 0 )
          {
            if ( IsWellKnownSid(*v1, WinAnonymousSid) )
            {
              RevertToSelf();
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 371, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
            }
            else
            {
              CloseHandle(TokenHandle);
              TokenHandle = 0;
            }
            goto LABEL_18;
          }
        }
        else
        {
          v4 = -1073741801;
        }
      }
      else if ( v5 >= 0 )
      {
        goto LABEL_18;
      }
    }
    v6 = TokenHandle;
    goto LABEL_14;
  }
  v4 = 0;
LABEL_18:
  v6 = 0;
  *a1 = TokenHandle;
  TokenHandle = 0;
LABEL_14:
  if ( v6 )
    CloseHandle(v6);
  LocalFree(v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b260  mov     [rsp-18h+arg_10], rbx
0x18000b265  push    rbp
0x18000b266  push    rsi
0x18000b267  push    rdi
0x18000b268  mov     rbp, rsp
0x18000b26b  sub     rsp, 30h
0x18000b26f  xor     edi, edi
0x18000b271  mov     [rbp+TokenInformationLength], 0
0x18000b278  mov     rsi, rcx
0x18000b27b  mov     [rcx], rdi
0x18000b27e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000b282  mov     [rbp+TokenHandle], rdi
0x18000b286  mov     r8b, 1; OpenAsSelf
0x18000b289  lea     edx, [rdi+4]; DesiredAccess
0x18000b28c  lea     rcx, [rdi-2]; ThreadHandle
0x18000b290  call    cs:__imp_NtOpenThreadToken
0x18000b296  mov     ebx, eax
0x18000b298  cmp     eax, 0C000007Ch
0x18000b29d  jnz     short loc_18000B2A6
0x18000b29f  xor     ebx, ebx
0x18000b2a1  jmp     loc_18000B39C
0x18000b2a6  test    eax, eax
0x18000b2a8  js      loc_18000B371
0x18000b2ae  xor     r9d, r9d; TokenInformationLength
0x18000b2b1  lea     rax, [rbp+TokenInformationLength]
0x18000b2b5  xor     r8d, r8d; TokenInformation
0x18000b2b8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000b2bd  lea     edx, [r9+1]; TokenInformationClass
0x18000b2c1  lea     rcx, [r9-5]; TokenHandle
0x18000b2c5  call    cs:__imp_NtQueryInformationToken
0x18000b2cb  mov     ebx, eax
0x18000b2cd  cmp     eax, 0C0000023h
0x18000b2d2  jnz     loc_18000B398
0x18000b2d8  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18000b2db  mov     ecx, 40h ; '@'; uFlags
0x18000b2e0  call    cs:__imp_LocalAlloc
0x18000b2e6  mov     rdi, rax
0x18000b2e9  test    rax, rax
0x18000b2ec  jz      short loc_18000B36C
0x18000b2ee  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000b2f2  lea     rax, [rbp+TokenInformationLength]
0x18000b2f6  mov     r8, rdi; TokenInformation
0x18000b2f9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000b2fe  mov     edx, 1; TokenInformationClass
0x18000b303  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18000b30a  call    cs:__imp_NtQueryInformationToken
0x18000b310  mov     ebx, eax
0x18000b312  test    eax, eax
0x18000b314  js      short loc_18000B371
0x18000b316  mov     rcx, [rdi]; pSid
0x18000b319  mov     edx, 0Dh; WellKnownSidType
0x18000b31e  call    cs:__imp_IsWellKnownSid
0x18000b324  test    eax, eax
0x18000b326  jz      short loc_18000B358
0x18000b328  call    cs:__imp_RevertToSelf
0x18000b32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b335  test    byte ptr [rcx+1Ch], 2
0x18000b339  jz      short loc_18000B39C
0x18000b33b  cmp     byte ptr [rcx+19h], 4
0x18000b33f  jb      short loc_18000B39C
0x18000b341  mov     rcx, [rcx+10h]
0x18000b345  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000b34c  mov     edx, 173h
0x18000b351  call    WPP_SF_
0x18000b356  jmp     short loc_18000B39C
0x18000b358  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b35c  call    cs:__imp_CloseHandle
0x18000b362  mov     [rbp+TokenHandle], 0
0x18000b36a  jmp     short loc_18000B39C
0x18000b36c  mov     ebx, 0C0000017h
0x18000b371  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b375  test    rcx, rcx
0x18000b378  jz      short loc_18000B380
0x18000b37a  call    cs:__imp_CloseHandle
0x18000b380  mov     rcx, rdi; hMem
0x18000b383  call    cs:__imp_LocalFree
0x18000b389  mov     eax, ebx
0x18000b38b  mov     rbx, [rsp+30h+arg_10]
0x18000b390  add     rsp, 30h
0x18000b394  pop     rdi
0x18000b395  pop     rsi
0x18000b396  pop     rbp
0x18000b397  retn
0x18000b398  test    eax, eax
0x18000b39a  js      short loc_18000B371
0x18000b39c  mov     rax, [rbp+TokenHandle]
0x18000b3a0  xor     ecx, ecx
0x18000b3a2  mov     [rsi], rax
0x18000b3a5  mov     [rbp+TokenHandle], rcx
0x18000b3a9  jmp     short loc_18000B375
```
