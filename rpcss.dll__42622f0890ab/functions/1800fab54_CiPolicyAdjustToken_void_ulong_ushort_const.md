# CiPolicyAdjustToken(void *,ulong,ushort const *)

- ea: `0x1800fab54`
- end: `0x1800fae3b`
- name: `?CiPolicyAdjustToken@@YAJPEAXKPEBG@Z`
- size: `743`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008b018`

## callees

- `0x1800b27e0`
- `0x1800fab54`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800facfe`
- `ntdll!RtlAcquirePrivilege` at `0x1800fadec`
- `ntdll!RtlAcquirePrivilege` at `0x1800facfe`
- `ntdll!RtlAcquirePrivilege` at `0x1800fadec`
- `ntdll!NtSetInformationToken` at `0x1800fad22`
- `ntdll!NtSetInformationToken` at `0x1800fae07`
- `ntdll!NtSetInformationToken` at `0x1800fad22`
- `ntdll!NtSetInformationToken` at `0x1800fae07`
- `ntdll!RtlReleasePrivilege` at `0x1800fad2f`
- `ntdll!RtlReleasePrivilege` at `0x1800fae14`
- `ntdll!RtlReleasePrivilege` at `0x1800fad2f`
- `ntdll!RtlReleasePrivilege` at `0x1800fae14`
- `ntdll!RtlQueryPackageClaims` at `0x1800fac6d`
- `ntdll!RtlQueryPackageClaims` at `0x1800fac6d`
- `ntdll!RtlInitUnicodeString` at `0x1800fabf1`
- `ntdll!RtlInitUnicodeString` at `0x1800fac85`
- `ntdll!RtlInitUnicodeString` at `0x1800fabf1`
- `ntdll!RtlInitUnicodeString` at `0x1800fac85`
- `ntdll!RtlEqualUnicodeString` at `0x1800fac12`
- `ntdll!RtlEqualUnicodeString` at `0x1800fac12`

## pseudocode

```c
__int64 __fastcall CiPolicyAdjustToken(HANDLE TokenHandle, int a2, const unsigned __int16 *a3)
{
  unsigned int i; // ebx
  NTSTATUS v6; // ebx
  int v7; // eax
  int v8; // edi
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Privilege; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v12; // [rsp+48h] [rbp-B8h] BYREF
  PVOID ReturnedState; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v14[5]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 TokenInformation; // [rsp+88h] [rbp-78h] BYREF
  __int64 v16; // [rsp+98h] [rbp-68h]
  __int64 v17; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v18[2]; // [rsp+A8h] [rbp-58h] BYREF
  const WCHAR *v19; // [rsp+B0h] [rbp-50h]
  int v20; // [rsp+B8h] [rbp-48h]
  const wchar_t *v21; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING DestinationString[2]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SourceString[128]; // [rsp+F0h] [rbp-10h] BYREF

  v18[0] = 1835034;
  v20 = 655368;
  v16 = 0;
  Privilege = 7;
  v21 = L"MCPB";
  v19 = L"TRUSTEDLAUNCH";
  memset(DestinationString, 0, sizeof(DestinationString));
  v10 = 0;
  memset(v14, 0, sizeof(v14));
  ReturnedState = 0;
  v12 = 0;
  TokenInformation = 0;
  RtlInitUnicodeString(DestinationString, L"TRUSTEDLAUNCH");
  for ( i = 0; i < 2; ++i )
  {
    if ( RtlEqualUnicodeString(DestinationString, (PCUNICODE_STRING)&v18[4 * i], 0) )
      break;
  }
  if ( i == 2 )
  {
    return (unsigned int)-1073741583;
  }
  else
  {
    v17 = 256;
    v6 = RtlQueryPackageClaims(TokenHandle, SourceString, &v17, 0);
    if ( v6 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString[1], SourceString);
      HIDWORD(v14[0]) = v16;
      v10 = 3;
      LOWORD(v14[2]) = 3;
      v14[1] = L"WIN://CIPOLICY";
      *((_QWORD *)&v12 + 1) = v14;
      LODWORD(v14[0]) = 1966108;
      *(_QWORD *)&TokenInformation = &v12;
      v14[4] = 0;
      *((_QWORD *)&TokenInformation + 1) = &v10;
      LODWORD(v14[3]) = 0;
      *(_QWORD *)&v12 = 0x100000001LL;
      v6 = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
      if ( v6 >= 0 )
      {
        v6 = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
        RtlReleasePrivilege(ReturnedState);
        if ( (int)(v6 + 0x80000000) < 0 || v6 == -1073741275 )
        {
          v7 = 0;
          if ( a2 )
          {
            v8 = a2 - 1;
            if ( v8 )
            {
              if ( v8 != 1 )
                return (unsigned int)-1073741811;
              v7 = 1;
            }
            else
            {
              v7 = 128;
            }
          }
          HIDWORD(v14[0]) = v16;
          HIDWORD(v14[2]) = v7;
          v14[1] = L"WIN://CIPOLICY";
          *((_QWORD *)&v12 + 1) = v14;
          LOWORD(v14[2]) = 3;
          *(_QWORD *)&TokenInformation = &v12;
          v14[4] = DestinationString;
          v10 = 2;
          LODWORD(v14[0]) = 1966108;
          LODWORD(v14[3]) = 2;
          *(_QWORD *)&v12 = 0x100000001LL;
          *((_QWORD *)&TokenInformation + 1) = &v10;
          v6 = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
          if ( v6 >= 0 )
          {
            v6 = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
            RtlReleasePrivilege(ReturnedState);
          }
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800fab54  push    rbp
0x1800fab56  push    rbx
0x1800fab57  push    rsi
0x1800fab58  push    rdi
0x1800fab59  push    r13
0x1800fab5b  push    r15
0x1800fab5d  lea     rbp, [rsp-108h]
0x1800fab65  sub     rsp, 208h
0x1800fab6c  mov     rax, cs:__security_cookie
0x1800fab73  xor     rax, rsp
0x1800fab76  mov     [rbp+130h+var_40], rax
0x1800fab7d  xorps   xmm0, xmm0
0x1800fab80  mov     [rbp+130h+var_188], 1C001Ah
0x1800fab87  xor     eax, eax
0x1800fab89  mov     [rbp+130h+var_178], 0A0008h
0x1800fab90  mov     [rbp+130h+var_198], rax
0x1800fab94  mov     edi, edx
0x1800fab96  lea     rax, aMcpb; "MCPB"
0x1800fab9d  mov     [rsp+230h+Privilege], 7
0x1800faba5  mov     [rbp+130h+var_170], rax
0x1800faba9  lea     rdx, aTrustedlaunch; "TRUSTEDLAUNCH"
0x1800fabb0  xor     eax, eax
0x1800fabb2  mov     [rbp+130h+var_180], rdx
0x1800fabb6  mov     rsi, rcx
0x1800fabb9  mov     [rbp+130h+DestinationString.Length], ax
0x1800fabbd  xorps   xmm1, xmm1
0x1800fabc0  mov     [rsp+230h+var_1F0], eax
0x1800fabc4  movups  xmmword ptr [rbp+130h+DestinationString.MaximumLength], xmm0
0x1800fabc8  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x1800fabcc  mov     word ptr [rsp+230h+var_1D0], ax
0x1800fabd1  movups  xmmword ptr [rsp+230h+var_1BE], xmm0
0x1800fabd6  mov     qword ptr [rbp+130h+var_1BE+0Eh], rax
0x1800fabda  mov     [rsp+230h+ReturnedState], rax
0x1800fabdf  movups  xmmword ptr [rbp+130h+var_158.Length], xmm0
0x1800fabe3  movups  xmmword ptr [rsp+230h+var_1D0+2], xmm0
0x1800fabe8  movups  [rsp+230h+var_1E8], xmm0
0x1800fabed  movups  [rbp+130h+TokenInformation], xmm1
0x1800fabf1  call    cs:__imp_RtlInitUnicodeString
0x1800fabf7  xor     ebx, ebx
0x1800fabf9  lea     r15d, [rbx+1]
0x1800fabfd  movsxd  rax, ebx
0x1800fac00  lea     rdx, [rbp+130h+var_188]
0x1800fac04  shl     rax, 4
0x1800fac08  lea     rcx, [rbp+130h+DestinationString]; String1
0x1800fac0c  add     rdx, rax; String2
0x1800fac0f  xor     r8d, r8d; CaseInsensitive
0x1800fac12  call    cs:__imp_RtlEqualUnicodeString
0x1800fac18  test    al, al
0x1800fac1a  jnz     short loc_1800FAC24
0x1800fac1c  add     ebx, r15d
0x1800fac1f  cmp     ebx, 2
0x1800fac22  jb      short loc_1800FABFD
0x1800fac24  cmp     ebx, 2
0x1800fac27  jnz     short loc_1800FAC33
0x1800fac29  mov     ebx, 0C00000F1h
0x1800fac2e  jmp     loc_1800FAE1A
0x1800fac33  mov     [rsp+230h+var_1F8], 0
0x1800fac3c  lea     r8, [rbp+130h+var_190]
0x1800fac40  mov     [rsp+230h+var_200], 0
0x1800fac49  lea     rdx, [rbp+130h+SourceString]
0x1800fac4d  mov     [rsp+230h+var_208], 0
0x1800fac56  xor     r9d, r9d
0x1800fac59  mov     rcx, rsi
0x1800fac5c  mov     [rsp+230h+var_210], 0
0x1800fac65  mov     [rbp+130h+var_190], 100h
0x1800fac6d  call    cs:__imp_RtlQueryPackageClaims
0x1800fac73  mov     ebx, eax
0x1800fac75  test    eax, eax
0x1800fac77  js      loc_1800FAE1A
0x1800fac7d  lea     rdx, [rbp+130h+SourceString]; SourceString
0x1800fac81  lea     rcx, [rbp+130h+var_158]; DestinationString
0x1800fac85  call    cs:__imp_RtlInitUnicodeString
0x1800fac8b  mov     rcx, [rbp+130h+var_198]
0x1800fac8f  lea     r9, [rsp+230h+ReturnedState]; ReturnedState
0x1800fac94  mov     eax, 3
0x1800fac99  mov     [rsp+230h+var_1CC], ecx
0x1800fac9d  mov     [rsp+230h+var_1F0], eax
0x1800faca1  lea     rcx, aWinCipolicy; "WIN://CIPOLICY"
0x1800faca8  mov     [rsp+230h+var_1C0], ax
0x1800facad  mov     r8d, 2; Flags
0x1800facb3  lea     rax, [rsp+230h+var_1D0]
0x1800facb8  mov     [rsp+230h+var_1C8], rcx
0x1800facbd  mov     qword ptr [rsp+230h+var_1E8+8], rax
0x1800facc2  lea     rcx, [rsp+230h+Privilege]; Privilege
0x1800facc7  lea     rax, [rsp+230h+var_1E8]
0x1800faccc  mov     [rsp+230h+var_1D0], 1E001Ch
0x1800facd4  mov     qword ptr [rbp+130h+TokenInformation], rax
0x1800facd8  mov     edx, r15d; NumPriv
0x1800facdb  lea     rax, [rsp+230h+var_1F0]
0x1800face0  mov     qword ptr [rbp+130h+var_1BE+0Eh], 0
0x1800face8  mov     qword ptr [rbp+130h+TokenInformation+8], rax
0x1800facec  mov     dword ptr [rsp+230h+var_1BE+6], 0
0x1800facf4  mov     dword ptr [rsp+230h+var_1E8], r15d
0x1800facf9  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1800facfe  call    cs:__imp_RtlAcquirePrivilege
0x1800fad04  mov     ebx, eax
0x1800fad06  test    eax, eax
0x1800fad08  js      loc_1800FAE1A
0x1800fad0e  mov     r13d, 10h
0x1800fad14  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x1800fad18  mov     r9d, r13d; TokenInformationLength
0x1800fad1b  mov     rcx, rsi; TokenHandle
0x1800fad1e  lea     edx, [r13+17h]; TokenInformationClass
0x1800fad22  call    cs:__imp_NtSetInformationToken
0x1800fad28  mov     rcx, [rsp+230h+ReturnedState]; ReturnedState
0x1800fad2d  mov     ebx, eax
0x1800fad2f  call    cs:__imp_RtlReleasePrivilege
0x1800fad35  mov     ecx, 80000000h
0x1800fad3a  lea     eax, [rbx+rcx]
0x1800fad3d  test    ecx, eax
0x1800fad3f  jnz     short loc_1800FAD4D
0x1800fad41  cmp     ebx, 0C0000225h
0x1800fad47  jnz     loc_1800FAE1A
0x1800fad4d  xor     eax, eax
0x1800fad4f  test    edi, edi
0x1800fad51  jz      short loc_1800FAD71
0x1800fad53  sub     edi, r15d
0x1800fad56  jz      short loc_1800FAD6C
0x1800fad58  cmp     edi, r15d
0x1800fad5b  jz      short loc_1800FAD67
0x1800fad5d  mov     ebx, 0C000000Dh
0x1800fad62  jmp     loc_1800FAE1A
0x1800fad67  mov     eax, r15d
0x1800fad6a  jmp     short loc_1800FAD71
0x1800fad6c  mov     eax, 80h
0x1800fad71  mov     rcx, [rbp+130h+var_198]
0x1800fad75  lea     r9, [rsp+230h+ReturnedState]; ReturnedState
0x1800fad7a  mov     [rsp+230h+var_1CC], ecx
0x1800fad7e  mov     r8d, 2; Flags
0x1800fad84  mov     dword ptr [rsp+230h+var_1BE+2], eax
0x1800fad88  lea     rcx, aWinCipolicy; "WIN://CIPOLICY"
0x1800fad8f  mov     [rsp+230h+var_1C8], rcx
0x1800fad94  lea     rax, [rsp+230h+var_1D0]
0x1800fad99  mov     qword ptr [rsp+230h+var_1E8+8], rax
0x1800fad9e  mov     ecx, 3
0x1800fada3  mov     [rsp+230h+var_1C0], cx
0x1800fada8  lea     rax, [rsp+230h+var_1E8]
0x1800fadad  lea     rcx, [rbp+130h+DestinationString]
0x1800fadb1  mov     qword ptr [rbp+130h+TokenInformation], rax
0x1800fadb5  mov     qword ptr [rbp+130h+var_1BE+0Eh], rcx
0x1800fadb9  lea     rax, [rsp+230h+var_1F0]
0x1800fadbe  lea     rcx, [rsp+230h+Privilege]; Privilege
0x1800fadc3  mov     [rsp+230h+var_1F0], 2
0x1800fadcb  mov     edx, r15d; NumPriv
0x1800fadce  mov     [rsp+230h+var_1D0], 1E001Ch
0x1800fadd6  mov     dword ptr [rsp+230h+var_1BE+6], 2
0x1800fadde  mov     dword ptr [rsp+230h+var_1E8], r15d
0x1800fade3  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1800fade8  mov     qword ptr [rbp+130h+TokenInformation+8], rax
0x1800fadec  call    cs:__imp_RtlAcquirePrivilege
0x1800fadf2  mov     ebx, eax
0x1800fadf4  test    eax, eax
0x1800fadf6  js      short loc_1800FAE1A
0x1800fadf8  mov     r9d, r13d; TokenInformationLength
0x1800fadfb  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x1800fadff  mov     edx, 27h ; '''; TokenInformationClass
0x1800fae04  mov     rcx, rsi; TokenHandle
0x1800fae07  call    cs:__imp_NtSetInformationToken
0x1800fae0d  mov     rcx, [rsp+230h+ReturnedState]; ReturnedState
0x1800fae12  mov     ebx, eax
0x1800fae14  call    cs:__imp_RtlReleasePrivilege
0x1800fae1a  mov     eax, ebx
0x1800fae1c  mov     rcx, [rbp+130h+var_40]
0x1800fae23  xor     rcx, rsp; StackCookie
0x1800fae26  call    __security_check_cookie
0x1800fae2b  add     rsp, 208h
0x1800fae32  pop     r15
0x1800fae34  pop     r13
0x1800fae36  pop     rdi
0x1800fae37  pop     rsi
0x1800fae38  pop     rbx
0x1800fae39  pop     rbp
0x1800fae3a  retn
```
