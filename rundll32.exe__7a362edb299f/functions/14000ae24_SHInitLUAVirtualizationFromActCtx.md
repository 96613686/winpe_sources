# SHInitLUAVirtualizationFromActCtx

- ea: `0x14000ae24`
- end: `0x14000afdb`
- name: `SHInitLUAVirtualizationFromActCtx`
- size: `439`
- prototype: `__int64 __fastcall(char *hActCtx)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140007798`

## callees

- `0x1400015a0`
- `0x14000ae24`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x14000af63`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x14000af63`
- `ntdll!RtlNtStatusToDosError` at `0x14000ae62`
- `ntdll!RtlNtStatusToDosError` at `0x14000aef7`
- `ntdll!RtlNtStatusToDosError` at `0x14000ae62`
- `ntdll!RtlNtStatusToDosError` at `0x14000aef7`
- `ntdll!NtSetInformationToken` at `0x14000afc9`
- `ntdll!NtSetInformationToken` at `0x14000afc9`
- `ntdll!NtClose` at `0x14000af1b`
- `ntdll!NtClose` at `0x14000afd3`
- `ntdll!NtClose` at `0x14000af1b`
- `ntdll!NtClose` at `0x14000afd3`
- `ntdll!NtQueryInformationToken` at `0x14000aeac`
- `ntdll!NtQueryInformationToken` at `0x14000aee0`
- `ntdll!NtQueryInformationToken` at `0x14000aeac`
- `ntdll!NtQueryInformationToken` at `0x14000aee0`
- `ntdll!NtOpenProcessToken` at `0x14000ae5a`
- `ntdll!NtOpenProcessToken` at `0x14000afaa`
- `ntdll!NtOpenProcessToken` at `0x14000ae5a`
- `ntdll!NtOpenProcessToken` at `0x14000afaa`

## pseudocode

```c
__int64 __fastcall SHInitLUAVirtualizationFromActCtx(char *hActCtx)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  bool v4; // sf
  void *v5; // rdi
  int v6; // r14d
  bool v7; // si
  unsigned int v8; // ebx
  int v9; // eax
  signed int v10; // eax
  signed int v11; // edi
  int v13; // [rsp+40h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+44h] [rbp-34h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]

  TokenHandle = 0;
  v2 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  v3 = RtlNtStatusToDosError(v2);
  v4 = v3 < 0;
  if ( v3 > 0 )
    v4 = 1;
  if ( v4 )
    return 0;
  v5 = TokenHandle;
  v6 = 0;
  ReturnLength = 0;
  v13 = 0;
  v7 = 0;
  v8 = 1;
  TokenInformation = 1;
  v9 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v9 >= 0 )
  {
    if ( TokenInformation == 2 )
    {
      v7 = 1;
    }
    else if ( TokenInformation == 1 )
    {
      v9 = NtQueryInformationToken(v5, TokenElevation, &v13, 4u, &ReturnLength);
      if ( v9 >= 0 )
        v7 = v13 != 0;
    }
  }
  v10 = RtlNtStatusToDosError(v9);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
    LOBYTE(v6) = v7;
  NtClose(TokenHandle);
  if ( v11 < 0 )
    return 0;
  if ( !v6 )
  {
    if ( (unsigned __int64)(hActCtx - 1) <= 0xFFFFFFFFFFFFFFFDuLL
      && (TokenHandle = 0, v17 = 0, QueryActCtxW(0x80000000, hActCtx, 0, 5u, &TokenHandle, 0xCu, 0))
      && HIDWORD(TokenHandle) )
    {
      if ( HIDWORD(TokenHandle) != 1 )
        return 0;
    }
    else
    {
      TokenHandle = 0;
      if ( NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x80u, &TokenHandle) >= 0 )
      {
        v13 = 1;
        NtSetInformationToken(TokenHandle, TokenVirtualizationEnabled, &v13, 4u);
        NtClose(TokenHandle);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14000ae24  push    rbp
0x14000ae26  push    rbx
0x14000ae27  push    rsi
0x14000ae28  push    rdi
0x14000ae29  push    r14
0x14000ae2b  push    r15
0x14000ae2d  mov     rbp, rsp
0x14000ae30  sub     rsp, 78h
0x14000ae34  mov     rax, cs:__security_cookie
0x14000ae3b  xor     rax, rsp
0x14000ae3e  mov     [rbp+var_18], rax
0x14000ae42  mov     r15, rcx
0x14000ae45  mov     [rbp+TokenHandle], 0
0x14000ae4d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000ae51  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000ae55  mov     edx, 8; DesiredAccess
0x14000ae5a  call    cs:__imp_NtOpenProcessToken
0x14000ae60  mov     ecx, eax; Status
0x14000ae62  call    cs:__imp_RtlNtStatusToDosError
0x14000ae68  test    eax, eax
0x14000ae6a  jle     short loc_14000AE76
0x14000ae6c  movzx   eax, ax
0x14000ae6f  or      eax, 80070000h
0x14000ae74  test    eax, eax
0x14000ae76  js      loc_14000AF78
0x14000ae7c  mov     rdi, [rbp+TokenHandle]
0x14000ae80  lea     rax, [rbp+var_30]
0x14000ae84  xor     r14d, r14d
0x14000ae87  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x14000ae8c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14000ae90  mov     [rbp+var_30], r14d
0x14000ae94  mov     rcx, rdi; TokenHandle
0x14000ae97  mov     [rbp+var_38], r14d
0x14000ae9b  xor     sil, sil
0x14000ae9e  lea     ebx, [r14+1]
0x14000aea2  lea     edx, [rbx+11h]; TokenInformationClass
0x14000aea5  mov     [rbp+TokenInformation], ebx
0x14000aea8  lea     r9d, [r14+4]; TokenInformationLength
0x14000aeac  call    cs:__imp_NtQueryInformationToken
0x14000aeb2  test    eax, eax
0x14000aeb4  js      short loc_14000AEF5
0x14000aeb6  cmp     [rbp+TokenInformation], 2
0x14000aeba  jnz     short loc_14000AEC1
0x14000aebc  mov     sil, bl
0x14000aebf  jmp     short loc_14000AEF5
0x14000aec1  cmp     [rbp+TokenInformation], ebx
0x14000aec4  jnz     short loc_14000AEF5
0x14000aec6  mov     r9d, 4; TokenInformationLength
0x14000aecc  lea     rax, [rbp+var_30]
0x14000aed0  lea     r8, [rbp+var_38]; TokenInformation
0x14000aed4  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x14000aed9  mov     rcx, rdi; TokenHandle
0x14000aedc  lea     edx, [r9+10h]; TokenInformationClass
0x14000aee0  call    cs:__imp_NtQueryInformationToken
0x14000aee6  test    eax, eax
0x14000aee8  js      short loc_14000AEF5
0x14000aeea  cmp     [rbp+var_38], r14d
0x14000aeee  movzx   esi, sil
0x14000aef2  cmovnz  esi, ebx
0x14000aef5  mov     ecx, eax; Status
0x14000aef7  call    cs:__imp_RtlNtStatusToDosError
0x14000aefd  mov     edi, eax
0x14000aeff  test    eax, eax
0x14000af01  jle     short loc_14000AF0C
0x14000af03  movzx   edi, ax
0x14000af06  or      edi, 80070000h
0x14000af0c  test    edi, edi
0x14000af0e  js      short loc_14000AF17
0x14000af10  test    sil, sil
0x14000af13  setnz   r14b
0x14000af17  mov     rcx, [rbp+TokenHandle]; Handle
0x14000af1b  call    cs:__imp_NtClose
0x14000af21  test    edi, edi
0x14000af23  js      short loc_14000AF78
0x14000af25  test    r14d, r14d
0x14000af28  jnz     short loc_14000AF7A
0x14000af2a  lea     rax, [r15-1]
0x14000af2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000af32  ja      short loc_14000AF95
0x14000af34  xor     eax, eax
0x14000af36  lea     r9d, [r14+5]; ulInfoClass
0x14000af3a  mov     [rsp+78h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x14000af3f  xor     r8d, r8d; pvSubInstance
0x14000af42  mov     [rbp+TokenHandle], rax
0x14000af46  mov     rdx, r15; hActCtx
0x14000af49  mov     [rbp+var_20], eax
0x14000af4c  mov     ecx, 80000000h; dwFlags
0x14000af51  lea     rax, [rbp+TokenHandle]
0x14000af55  mov     [rsp+78h+cbBuffer], 0Ch; cbBuffer
0x14000af5e  mov     [rsp+78h+ReturnLength], rax; pvBuffer
0x14000af63  call    cs:__imp_QueryActCtxW
0x14000af69  test    eax, eax
0x14000af6b  jz      short loc_14000AF95
0x14000af6d  mov     ecx, dword ptr [rbp+TokenHandle+4]
0x14000af70  test    ecx, ecx
0x14000af72  jz      short loc_14000AF95
0x14000af74  cmp     ecx, ebx
0x14000af76  jz      short loc_14000AF7A
0x14000af78  xor     ebx, ebx
0x14000af7a  mov     eax, ebx
0x14000af7c  mov     rcx, [rbp+var_18]
0x14000af80  xor     rcx, rsp; StackCookie
0x14000af83  call    __security_check_cookie
0x14000af88  add     rsp, 78h
0x14000af8c  pop     r15
0x14000af8e  pop     r14
0x14000af90  pop     rdi
0x14000af91  pop     rsi
0x14000af92  pop     rbx
0x14000af93  pop     rbp
0x14000af94  retn
0x14000af95  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000af99  mov     [rbp+TokenHandle], 0
0x14000afa1  mov     edx, 80h; DesiredAccess
0x14000afa6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000afaa  call    cs:__imp_NtOpenProcessToken
0x14000afb0  test    eax, eax
0x14000afb2  js      short loc_14000AF7A
0x14000afb4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000afb8  lea     r8, [rbp+var_38]; TokenInformation
0x14000afbc  mov     r9d, 4; TokenInformationLength
0x14000afc2  mov     [rbp+var_38], ebx
0x14000afc5  lea     edx, [r9+14h]; TokenInformationClass
0x14000afc9  call    cs:__imp_NtSetInformationToken
0x14000afcf  mov     rcx, [rbp+TokenHandle]; Handle
0x14000afd3  call    cs:__imp_NtClose
0x14000afd9  jmp     short loc_14000AF7A
```
