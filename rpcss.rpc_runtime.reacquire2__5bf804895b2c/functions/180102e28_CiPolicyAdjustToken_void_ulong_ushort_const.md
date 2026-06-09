# CiPolicyAdjustToken(void *,ulong,ushort const *)

- ea: `0x180102e28`
- end: `0x18010314c`
- name: `?CiPolicyAdjustToken@@YAJPEAXKPEBG@Z`
- size: `804`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008fbec`

## callees

- `0x1800b7ac0`
- `0x180102e28`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180102fea`
- `ntdll!RtlAcquirePrivilege` at `0x1801030ea`
- `ntdll!RtlAcquirePrivilege` at `0x180102fea`
- `ntdll!RtlAcquirePrivilege` at `0x1801030ea`
- `ntdll!NtSetInformationToken` at `0x180103014`
- `ntdll!NtSetInformationToken` at `0x18010310b`
- `ntdll!NtSetInformationToken` at `0x180103014`
- `ntdll!NtSetInformationToken` at `0x18010310b`
- `ntdll!RtlReleasePrivilege` at `0x180103027`
- `ntdll!RtlReleasePrivilege` at `0x18010311e`
- `ntdll!RtlReleasePrivilege` at `0x180103027`
- `ntdll!RtlReleasePrivilege` at `0x18010311e`
- `ntdll!RtlQueryPackageClaims` at `0x180102f4d`
- `ntdll!RtlQueryPackageClaims` at `0x180102f4d`
- `ntdll!RtlInitUnicodeString` at `0x180102ec5`
- `ntdll!RtlInitUnicodeString` at `0x180102f6b`
- `ntdll!RtlInitUnicodeString` at `0x180102ec5`
- `ntdll!RtlInitUnicodeString` at `0x180102f6b`
- `ntdll!RtlEqualUnicodeString` at `0x180102eec`
- `ntdll!RtlEqualUnicodeString` at `0x180102eec`

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
0x180102e28  push    rbp
0x180102e2a  push    rbx
0x180102e2b  push    rsi
0x180102e2c  push    rdi
0x180102e2d  push    r13
0x180102e2f  push    r15
0x180102e31  lea     rbp, [rsp-108h]
0x180102e39  sub     rsp, 208h
0x180102e40  mov     rax, cs:__security_cookie
0x180102e47  xor     rax, rsp
0x180102e4a  mov     [rbp+130h+var_40], rax
0x180102e51  xorps   xmm0, xmm0
0x180102e54  mov     [rbp+130h+var_188], 1C001Ah
0x180102e5b  xor     eax, eax
0x180102e5d  mov     [rbp+130h+var_178], 0A0008h
0x180102e64  mov     [rbp+130h+var_198], rax
0x180102e68  mov     edi, edx
0x180102e6a  lea     rax, aMcpb; "MCPB"
0x180102e71  mov     [rsp+230h+Privilege], 7
0x180102e79  mov     [rbp+130h+var_170], rax
0x180102e7d  lea     rdx, aTrustedlaunch; "TRUSTEDLAUNCH"
0x180102e84  xor     eax, eax
0x180102e86  mov     [rbp+130h+var_180], rdx
0x180102e8a  mov     rsi, rcx
0x180102e8d  mov     [rbp+130h+DestinationString.Length], ax
0x180102e91  xorps   xmm1, xmm1
0x180102e94  mov     [rsp+230h+var_1F0], eax
0x180102e98  movups  xmmword ptr [rbp+130h+DestinationString.MaximumLength], xmm0
0x180102e9c  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x180102ea0  mov     word ptr [rsp+230h+var_1D0], ax
0x180102ea5  movups  xmmword ptr [rsp+230h+var_1BE], xmm0
0x180102eaa  mov     qword ptr [rbp+130h+var_1BE+0Eh], rax
0x180102eae  mov     [rsp+230h+ReturnedState], rax
0x180102eb3  movups  xmmword ptr [rbp+130h+var_158.Length], xmm0
0x180102eb7  movups  xmmword ptr [rsp+230h+var_1D0+2], xmm0
0x180102ebc  movups  [rsp+230h+var_1E8], xmm0
0x180102ec1  movups  [rbp+130h+TokenInformation], xmm1
0x180102ec5  call    cs:__imp_RtlInitUnicodeString
0x180102ecc  nop     dword ptr [rax+rax+00h]
0x180102ed1  xor     ebx, ebx
0x180102ed3  lea     r15d, [rbx+1]
0x180102ed7  movsxd  rax, ebx
0x180102eda  lea     rdx, [rbp+130h+var_188]
0x180102ede  shl     rax, 4
0x180102ee2  lea     rcx, [rbp+130h+DestinationString]; String1
0x180102ee6  add     rdx, rax; String2
0x180102ee9  xor     r8d, r8d; CaseInsensitive
0x180102eec  call    cs:__imp_RtlEqualUnicodeString
0x180102ef3  nop     dword ptr [rax+rax+00h]
0x180102ef8  test    al, al
0x180102efa  jnz     short loc_180102F04
0x180102efc  add     ebx, r15d
0x180102eff  cmp     ebx, 2
0x180102f02  jb      short loc_180102ED7
0x180102f04  cmp     ebx, 2
0x180102f07  jnz     short loc_180102F13
0x180102f09  mov     ebx, 0C00000F1h
0x180102f0e  jmp     loc_18010312A
0x180102f13  mov     [rsp+230h+var_1F8], 0
0x180102f1c  lea     r8, [rbp+130h+var_190]
0x180102f20  mov     [rsp+230h+var_200], 0
0x180102f29  lea     rdx, [rbp+130h+SourceString]
0x180102f2d  mov     [rsp+230h+var_208], 0
0x180102f36  xor     r9d, r9d
0x180102f39  mov     rcx, rsi
0x180102f3c  mov     [rsp+230h+var_210], 0
0x180102f45  mov     [rbp+130h+var_190], 100h
0x180102f4d  call    cs:__imp_RtlQueryPackageClaims
0x180102f54  nop     dword ptr [rax+rax+00h]
0x180102f59  mov     ebx, eax
0x180102f5b  test    eax, eax
0x180102f5d  js      loc_18010312A
0x180102f63  lea     rdx, [rbp+130h+SourceString]; SourceString
0x180102f67  lea     rcx, [rbp+130h+var_158]; DestinationString
0x180102f6b  call    cs:__imp_RtlInitUnicodeString
0x180102f72  nop     dword ptr [rax+rax+00h]
0x180102f77  mov     rcx, [rbp+130h+var_198]
0x180102f7b  lea     r9, [rsp+230h+ReturnedState]; ReturnedState
0x180102f80  mov     eax, 3
0x180102f85  mov     [rsp+230h+var_1CC], ecx
0x180102f89  mov     [rsp+230h+var_1F0], eax
0x180102f8d  lea     rcx, aWinCipolicy; "WIN://CIPOLICY"
0x180102f94  mov     [rsp+230h+var_1C0], ax
0x180102f99  mov     r8d, 2; Flags
0x180102f9f  lea     rax, [rsp+230h+var_1D0]
0x180102fa4  mov     [rsp+230h+var_1C8], rcx
0x180102fa9  mov     qword ptr [rsp+230h+var_1E8+8], rax
0x180102fae  lea     rcx, [rsp+230h+Privilege]; Privilege
0x180102fb3  lea     rax, [rsp+230h+var_1E8]
0x180102fb8  mov     [rsp+230h+var_1D0], 1E001Ch
0x180102fc0  mov     qword ptr [rbp+130h+TokenInformation], rax
0x180102fc4  mov     edx, r15d; NumPriv
0x180102fc7  lea     rax, [rsp+230h+var_1F0]
0x180102fcc  mov     qword ptr [rbp+130h+var_1BE+0Eh], 0
0x180102fd4  mov     qword ptr [rbp+130h+TokenInformation+8], rax
0x180102fd8  mov     dword ptr [rsp+230h+var_1BE+6], 0
0x180102fe0  mov     dword ptr [rsp+230h+var_1E8], r15d
0x180102fe5  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x180102fea  call    cs:__imp_RtlAcquirePrivilege
0x180102ff1  nop     dword ptr [rax+rax+00h]
0x180102ff6  mov     ebx, eax
0x180102ff8  test    eax, eax
0x180102ffa  js      loc_18010312A
0x180103000  mov     r13d, 10h
0x180103006  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x18010300a  mov     r9d, r13d; TokenInformationLength
0x18010300d  mov     rcx, rsi; TokenHandle
0x180103010  lea     edx, [r13+17h]; TokenInformationClass
0x180103014  call    cs:__imp_NtSetInformationToken
0x18010301b  nop     dword ptr [rax+rax+00h]
0x180103020  mov     rcx, [rsp+230h+ReturnedState]; ReturnedState
0x180103025  mov     ebx, eax
0x180103027  call    cs:__imp_RtlReleasePrivilege
0x18010302e  nop     dword ptr [rax+rax+00h]
0x180103033  mov     ecx, 80000000h
0x180103038  lea     eax, [rbx+rcx]
0x18010303b  test    ecx, eax
0x18010303d  jnz     short loc_18010304B
0x18010303f  cmp     ebx, 0C0000225h
0x180103045  jnz     loc_18010312A
0x18010304b  xor     eax, eax
0x18010304d  test    edi, edi
0x18010304f  jz      short loc_18010306F
0x180103051  sub     edi, r15d
0x180103054  jz      short loc_18010306A
0x180103056  cmp     edi, r15d
0x180103059  jz      short loc_180103065
0x18010305b  mov     ebx, 0C000000Dh
0x180103060  jmp     loc_18010312A
0x180103065  mov     eax, r15d
0x180103068  jmp     short loc_18010306F
0x18010306a  mov     eax, 80h
0x18010306f  mov     rcx, [rbp+130h+var_198]
0x180103073  lea     r9, [rsp+230h+ReturnedState]; ReturnedState
0x180103078  mov     [rsp+230h+var_1CC], ecx
0x18010307c  mov     r8d, 2; Flags
0x180103082  mov     dword ptr [rsp+230h+var_1BE+2], eax
0x180103086  lea     rcx, aWinCipolicy; "WIN://CIPOLICY"
0x18010308d  mov     [rsp+230h+var_1C8], rcx
0x180103092  lea     rax, [rsp+230h+var_1D0]
0x180103097  mov     qword ptr [rsp+230h+var_1E8+8], rax
0x18010309c  mov     ecx, 3
0x1801030a1  mov     [rsp+230h+var_1C0], cx
0x1801030a6  lea     rax, [rsp+230h+var_1E8]
0x1801030ab  lea     rcx, [rbp+130h+DestinationString]
0x1801030af  mov     qword ptr [rbp+130h+TokenInformation], rax
0x1801030b3  mov     qword ptr [rbp+130h+var_1BE+0Eh], rcx
0x1801030b7  lea     rax, [rsp+230h+var_1F0]
0x1801030bc  lea     rcx, [rsp+230h+Privilege]; Privilege
0x1801030c1  mov     [rsp+230h+var_1F0], 2
0x1801030c9  mov     edx, r15d; NumPriv
0x1801030cc  mov     [rsp+230h+var_1D0], 1E001Ch
0x1801030d4  mov     dword ptr [rsp+230h+var_1BE+6], 2
0x1801030dc  mov     dword ptr [rsp+230h+var_1E8], r15d
0x1801030e1  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1801030e6  mov     qword ptr [rbp+130h+TokenInformation+8], rax
0x1801030ea  call    cs:__imp_RtlAcquirePrivilege
0x1801030f1  nop     dword ptr [rax+rax+00h]
0x1801030f6  mov     ebx, eax
0x1801030f8  test    eax, eax
0x1801030fa  js      short loc_18010312A
0x1801030fc  mov     r9d, r13d; TokenInformationLength
0x1801030ff  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x180103103  mov     edx, 27h ; '''; TokenInformationClass
0x180103108  mov     rcx, rsi; TokenHandle
0x18010310b  call    cs:__imp_NtSetInformationToken
0x180103112  nop     dword ptr [rax+rax+00h]
0x180103117  mov     rcx, [rsp+230h+ReturnedState]; ReturnedState
0x18010311c  mov     ebx, eax
0x18010311e  call    cs:__imp_RtlReleasePrivilege
0x180103125  nop     dword ptr [rax+rax+00h]
0x18010312a  mov     eax, ebx
0x18010312c  mov     rcx, [rbp+130h+var_40]
0x180103133  xor     rcx, rsp; StackCookie
0x180103136  call    __security_check_cookie
0x18010313b  add     rsp, 208h
0x180103142  pop     r15
0x180103144  pop     r13
0x180103146  pop     rdi
0x180103147  pop     rsi
0x180103148  pop     rbx
0x180103149  pop     rbp
0x18010314a  retn
```
