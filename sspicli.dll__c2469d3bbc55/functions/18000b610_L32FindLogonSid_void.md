# L32FindLogonSid(void *)

- ea: `0x18000b610`
- end: `0x18000b79b`
- name: `?L32FindLogonSid@@YAPEAXPEAX@Z`
- size: `395`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ab30`

## callees

- `0x18000b610`
- `0x18002205f`
- `0x180022190`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000b6e5`
- `ntdll!RtlCopySid` at `0x18000b6e5`
- `ntdll!RtlLengthSid` at `0x18000b6bd`
- `ntdll!RtlLengthSid` at `0x18000b6bd`
- `ntdll!RtlValidSid` at `0x18000b6aa`
- `ntdll!RtlValidSid` at `0x18000b6aa`
- `ntdll!NtQueryInformationToken` at `0x18000b66c`
- `ntdll!NtQueryInformationToken` at `0x18000b756`
- `ntdll!NtQueryInformationToken` at `0x18000b66c`
- `ntdll!NtQueryInformationToken` at `0x18000b756`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b766`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b78e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b766`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b78e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b6c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b72b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b6c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b72b`

## pseudocode

```c
void *__fastcall L32FindLogonSid(HANDLE TokenHandle)
{
  void *v2; // rbx
  NTSTATUS InformationToken; // edi
  void *v4; // rsi
  unsigned int *v5; // r14
  unsigned int i; // eax
  __int64 v7; // rbp
  ULONG v8; // edi
  HLOCAL v9; // rax
  HLOCAL v11; // rax
  ULONG TokenInformationLength[4]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE TokenInformation[512]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  TokenInformationLength[0] = 512;
  v2 = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenGroups, TokenInformation, 0x200u, TokenInformationLength);
  if ( InformationToken == -1073741789 )
  {
    v11 = LocalAlloc(0, TokenInformationLength[0]);
    v4 = v11;
    if ( !v11 )
      return v2;
    v5 = (unsigned int *)v11;
    InformationToken = NtQueryInformationToken(
                         TokenHandle,
                         TokenGroups,
                         v11,
                         TokenInformationLength[0],
                         TokenInformationLength);
  }
  else
  {
    v4 = 0;
    v5 = (unsigned int *)TokenInformation;
  }
  if ( InformationToken >= 0 )
  {
    for ( i = 0; i < *v5; ++i )
    {
      v7 = 2LL * i;
      if ( (v5[4 * i + 4] & 0xC0000000) != 0 )
      {
        if ( RtlValidSid(*(PSID *)&v5[4 * i + 2]) )
        {
          v8 = RtlLengthSid(*(PSID *)&v5[2 * v7 + 2]);
          v9 = LocalAlloc(0, v8);
          v2 = v9;
          if ( v9 )
            InformationToken = RtlCopySid(v8, v9, *(PSID *)&v5[2 * v7 + 2]);
          else
            InformationToken = -1073741670;
        }
        else
        {
          InformationToken = -1073741704;
        }
        break;
      }
    }
  }
  if ( v4 )
    LocalFree(v4);
  if ( InformationToken < 0 && v2 )
  {
    LocalFree(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18000b610  mov     [rsp+arg_8], rbx
0x18000b615  mov     [rsp+arg_10], rbp
0x18000b61a  push    rsi
0x18000b61b  push    rdi
0x18000b61c  push    r14
0x18000b61e  sub     rsp, 250h
0x18000b625  mov     rax, cs:__security_cookie
0x18000b62c  xor     rax, rsp
0x18000b62f  mov     [rsp+268h+var_28], rax
0x18000b637  mov     rbp, rcx
0x18000b63a  mov     edi, 200h
0x18000b63f  mov     r8d, edi; Size
0x18000b642  lea     rcx, [rsp+268h+TokenInformation]; void *
0x18000b647  xor     edx, edx; Val
0x18000b649  call    memset_0
0x18000b64e  lea     rax, [rsp+268h+TokenInformationLength]
0x18000b653  mov     [rsp+268h+TokenInformationLength], edi
0x18000b657  xor     ebx, ebx
0x18000b659  mov     [rsp+268h+ReturnLength], rax; ReturnLength
0x18000b65e  mov     r9d, edi; TokenInformationLength
0x18000b661  lea     r8, [rsp+268h+TokenInformation]; TokenInformation
0x18000b666  mov     rcx, rbp; TokenHandle
0x18000b669  lea     edx, [rbx+2]; TokenInformationClass
0x18000b66c  call    cs:__imp_NtQueryInformationToken
0x18000b672  mov     edi, eax
0x18000b674  cmp     eax, 0C0000023h
0x18000b679  jz      loc_18000B725
0x18000b67f  xor     esi, esi
0x18000b681  lea     r14, [rsp+268h+TokenInformation]
0x18000b686  test    edi, edi
0x18000b688  js      short loc_18000B6ED
0x18000b68a  xor     eax, eax
0x18000b68c  cmp     eax, [r14]
0x18000b68f  jnb     short loc_18000B6ED
0x18000b691  mov     ebp, eax
0x18000b693  add     rbp, rbp
0x18000b696  test    dword ptr [r14+rbp*8+10h], 0C0000000h
0x18000b69f  jnz     short loc_18000B6A5
0x18000b6a1  inc     eax
0x18000b6a3  jmp     short loc_18000B68C
0x18000b6a5  mov     rcx, [r14+rbp*8+8]; Sid
0x18000b6aa  call    cs:__imp_RtlValidSid
0x18000b6b0  test    al, al
0x18000b6b2  jz      loc_18000B76E
0x18000b6b8  mov     rcx, [r14+rbp*8+8]; Sid
0x18000b6bd  call    cs:__imp_RtlLengthSid
0x18000b6c3  mov     edx, eax; uBytes
0x18000b6c5  xor     ecx, ecx; uFlags
0x18000b6c7  mov     edi, eax
0x18000b6c9  call    cs:__imp_LocalAlloc
0x18000b6cf  mov     rbx, rax
0x18000b6d2  test    rax, rax
0x18000b6d5  jz      loc_18000B778
0x18000b6db  mov     r8, [r14+rbp*8+8]; SourceSid
0x18000b6e0  mov     rdx, rax; DestinationSid
0x18000b6e3  mov     ecx, edi; DestinationSidLength
0x18000b6e5  call    cs:__imp_RtlCopySid
0x18000b6eb  mov     edi, eax
0x18000b6ed  test    rsi, rsi
0x18000b6f0  jnz     short loc_18000B763
0x18000b6f2  test    edi, edi
0x18000b6f4  js      loc_18000B782
0x18000b6fa  mov     rax, rbx
0x18000b6fd  mov     rcx, [rsp+268h+var_28]
0x18000b705  xor     rcx, rsp; StackCookie
0x18000b708  call    __security_check_cookie
0x18000b70d  lea     r11, [rsp+268h+var_18]
0x18000b715  mov     rbx, [r11+28h]
0x18000b719  mov     rbp, [r11+30h]
0x18000b71d  mov     rsp, r11
0x18000b720  pop     r14
0x18000b722  pop     rdi
0x18000b723  pop     rsi
0x18000b724  retn
0x18000b725  mov     edx, [rsp+268h+TokenInformationLength]; uBytes
0x18000b729  xor     ecx, ecx; uFlags
0x18000b72b  call    cs:__imp_LocalAlloc
0x18000b731  mov     rsi, rax
0x18000b734  test    rax, rax
0x18000b737  jz      short loc_18000B6FA
0x18000b739  mov     r9d, [rsp+268h+TokenInformationLength]; TokenInformationLength
0x18000b73e  mov     r14, rax
0x18000b741  lea     rax, [rsp+268h+TokenInformationLength]
0x18000b746  mov     r8, r14; TokenInformation
0x18000b749  mov     edx, 2; TokenInformationClass
0x18000b74e  mov     [rsp+268h+ReturnLength], rax; ReturnLength
0x18000b753  mov     rcx, rbp; TokenHandle
0x18000b756  call    cs:__imp_NtQueryInformationToken
0x18000b75c  mov     edi, eax
0x18000b75e  jmp     loc_18000B686
0x18000b763  mov     rcx, rsi; hMem
0x18000b766  call    cs:__imp_LocalFree
0x18000b76c  jmp     short loc_18000B6F2
0x18000b76e  mov     edi, 0C0000078h
0x18000b773  jmp     loc_18000B6ED
0x18000b778  mov     edi, 0C000009Ah
0x18000b77d  jmp     loc_18000B6ED
0x18000b782  test    rbx, rbx
0x18000b785  jz      loc_18000B6FA
0x18000b78b  mov     rcx, rbx; hMem
0x18000b78e  call    cs:__imp_LocalFree
0x18000b794  xor     ebx, ebx
0x18000b796  jmp     loc_18000B6FA
```
