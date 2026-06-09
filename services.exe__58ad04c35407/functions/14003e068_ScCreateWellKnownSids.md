# ScCreateWellKnownSids

- ea: `0x14003e068`
- end: `0x14003e2ab`
- name: `ScCreateWellKnownSids`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400848e0`

## callees

- `0x14003e068`
- `0x140042a80`
- `0x1400575b0`
- `0x140086794`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14003e288`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14003e288`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14003e0a6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14003e0a6`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x14003e198`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x14003e198`
- `ntdll!RtlSubAuthoritySid` at `0x14003e0fb`
- `ntdll!RtlSubAuthoritySid` at `0x14003e165`
- `ntdll!RtlSubAuthoritySid` at `0x14003e177`
- `ntdll!RtlSubAuthoritySid` at `0x14003e1d6`
- `ntdll!RtlSubAuthoritySid` at `0x14003e1ec`
- `ntdll!RtlSubAuthoritySid` at `0x14003e1fe`
- `ntdll!RtlSubAuthoritySid` at `0x14003e211`
- `ntdll!RtlSubAuthoritySid` at `0x14003e224`
- `ntdll!RtlSubAuthoritySid` at `0x14003e237`
- `ntdll!RtlSubAuthoritySid` at `0x14003e262`
- `ntdll!RtlSubAuthoritySid` at `0x14003e278`
- `ntdll!RtlSubAuthoritySid` at `0x14003e0fb`
- `ntdll!RtlSubAuthoritySid` at `0x14003e165`
- `ntdll!RtlSubAuthoritySid` at `0x14003e177`
- `ntdll!RtlSubAuthoritySid` at `0x14003e1d6`
- `ntdll!RtlSubAuthoritySid` at `0x14003e1ec`
- `ntdll!RtlSubAuthoritySid` at `0x14003e1fe`
- `ntdll!RtlSubAuthoritySid` at `0x14003e211`
- `ntdll!RtlSubAuthoritySid` at `0x14003e224`
- `ntdll!RtlSubAuthoritySid` at `0x14003e237`
- `ntdll!RtlSubAuthoritySid` at `0x14003e262`
- `ntdll!RtlSubAuthoritySid` at `0x14003e278`

## pseudocode

```c
__int64 ScCreateWellKnownSids()
{
  unsigned int v0; // edi
  int v1; // ebx
  int v2; // ebx
  PULONG v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // edi
  int v7; // [rsp+20h] [rbp-20h] BYREF
  __int16 v8; // [rsp+24h] [rbp-1Ch]
  int v9; // [rsp+28h] [rbp-18h] BYREF
  __int16 v10; // [rsp+2Ch] [rbp-14h]

  v10 = 3840;
  v9 = 0;
  v7 = 0;
  v8 = 1280;
  RtlAcquireSRWLockExclusive(&qword_1400BC960);
  v0 = 0;
  while ( 1 )
  {
    v1 = ScAllocateAndInitializeSid((&off_140098740)[3 * v0], &qword_140098748[3 * v0], 1);
    if ( v1 < 0 )
      break;
    v2 = dword_140098750[6 * v0];
    v3 = RtlSubAuthoritySid((PSID)*(&off_140098740)[3 * v0++], 0);
    *v3 = v2;
    if ( v0 >= 0x12 )
    {
      v5 = 0;
      while ( 1 )
      {
        v1 = ScDomainIdToSid(v4, (unsigned int)dword_140098908[4 * v5], (&off_140098900)[2 * v5]);
        if ( v1 < 0 )
          goto LABEL_12;
        if ( ++v5 >= 8 )
        {
          v1 = ScAllocateAndInitializeSid(&AnyPackageSid, &v9, 2);
          if ( v1 >= 0 )
          {
            *RtlSubAuthoritySid(AnyPackageSid, 0) = 2;
            *RtlSubAuthoritySid(AnyPackageSid, 1u) = 1;
            v1 = RtlDeriveCapabilitySidsFromName(
                   L",.",
                   &LpacServicesManagementCapabilityGroupSidBuffer,
                   &LpacServicesManagementCapabilitySidBuffer);
            if ( v1 >= 0 )
            {
              LpacServicesManagementCapabilitySid = (__int64)&LpacServicesManagementCapabilitySidBuffer;
              v1 = ScAllocateAndInitializeSid(&UserModeDriversSid, &v7, 6);
              if ( v1 >= 0 )
              {
                *RtlSubAuthoritySid(UserModeDriversSid, 0) = 84;
                *RtlSubAuthoritySid(UserModeDriversSid, 1u) = 0;
                *RtlSubAuthoritySid(UserModeDriversSid, 2u) = 0;
                *RtlSubAuthoritySid(UserModeDriversSid, 3u) = 0;
                *RtlSubAuthoritySid(UserModeDriversSid, 4u) = 0;
                *RtlSubAuthoritySid(UserModeDriversSid, 5u) = 0;
                v1 = ScAllocateAndInitializeSid(&AllRestrictedServicesSid, &v7, 2);
                if ( v1 >= 0 )
                {
                  *RtlSubAuthoritySid(AllRestrictedServicesSid, 0) = 99;
                  *RtlSubAuthoritySid(AllRestrictedServicesSid, 1u) = 0;
                }
              }
            }
          }
          goto LABEL_12;
        }
      }
    }
  }
LABEL_12:
  RtlReleaseSRWLockExclusive(&qword_1400BC960);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14003e068  push    rbp
0x14003e06a  push    rbx
0x14003e06b  push    rsi
0x14003e06c  push    rdi
0x14003e06d  push    r12
0x14003e06f  push    r14
0x14003e071  push    r15
0x14003e073  mov     rbp, rsp
0x14003e076  sub     rsp, 40h
0x14003e07a  mov     rax, cs:__security_cookie
0x14003e081  xor     rax, rsp
0x14003e084  mov     [rbp+var_10], rax
0x14003e088  xor     r14d, r14d
0x14003e08b  mov     [rbp+var_14], 0F00h
0x14003e091  lea     rcx, qword_1400BC960
0x14003e098  mov     [rbp+var_18], r14d
0x14003e09c  mov     [rbp+var_20], r14d
0x14003e0a0  mov     [rbp+var_1C], 500h
0x14003e0a6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14003e0ac  mov     edi, r14d
0x14003e0af  lea     r12, __ImageBase
0x14003e0b6  lea     r15d, [r14+1]
0x14003e0ba  mov     eax, edi
0x14003e0bc  lea     rdx, rva qword_140098748[r12]
0x14003e0c4  mov     r8d, r15d
0x14003e0c7  lea     rsi, [rax+rax*2]
0x14003e0cb  mov     rcx, ds:rva off_140098740[r12+rsi*8]
0x14003e0d3  lea     rdx, [rdx+rsi*8]
0x14003e0d7  call    ScAllocateAndInitializeSid
0x14003e0dc  mov     ebx, eax
0x14003e0de  test    eax, eax
0x14003e0e0  js      loc_14003E281
0x14003e0e6  mov     rcx, ds:rva off_140098740[r12+rsi*8]
0x14003e0ee  xor     edx, edx; SubAuthority
0x14003e0f0  mov     ebx, ds:rva dword_140098750[r12+rsi*8]
0x14003e0f8  mov     rcx, [rcx]; Sid
0x14003e0fb  call    cs:__imp_RtlSubAuthoritySid
0x14003e101  add     edi, r15d
0x14003e104  mov     [rax], ebx
0x14003e106  cmp     edi, 12h
0x14003e109  jb      short loc_14003E0BA
0x14003e10b  mov     edi, r14d
0x14003e10e  mov     edx, edi
0x14003e110  add     rdx, rdx
0x14003e113  mov     r8, ds:rva off_140098900[r12+rdx*8]
0x14003e11b  mov     edx, ds:rva dword_140098908[r12+rdx*8]
0x14003e123  call    ScDomainIdToSid
0x14003e128  mov     ebx, eax
0x14003e12a  test    eax, eax
0x14003e12c  js      loc_14003E281
0x14003e132  add     edi, r15d
0x14003e135  cmp     edi, 8
0x14003e138  jb      short loc_14003E10E
0x14003e13a  mov     edi, 2
0x14003e13f  lea     rdx, [rbp+var_18]
0x14003e143  mov     r8d, edi
0x14003e146  lea     rcx, AnyPackageSid
0x14003e14d  call    ScAllocateAndInitializeSid
0x14003e152  mov     ebx, eax
0x14003e154  test    eax, eax
0x14003e156  js      loc_14003E281
0x14003e15c  mov     rcx, cs:AnyPackageSid; Sid
0x14003e163  xor     edx, edx; SubAuthority
0x14003e165  call    cs:__imp_RtlSubAuthoritySid
0x14003e16b  mov     edx, r15d; SubAuthority
0x14003e16e  mov     [rax], edi
0x14003e170  mov     rcx, cs:AnyPackageSid; Sid
0x14003e177  call    cs:__imp_RtlSubAuthoritySid
0x14003e17d  lea     rsi, ?LpacServicesManagementCapabilitySidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilitySidBuffer
0x14003e184  mov     r8, rsi
0x14003e187  lea     rdx, ?LpacServicesManagementCapabilityGroupSidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilityGroupSidBuffer
0x14003e18e  lea     rcx, asc_1400988F0; ",."
0x14003e195  mov     [rax], r15d
0x14003e198  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x14003e19e  mov     ebx, eax
0x14003e1a0  test    eax, eax
0x14003e1a2  js      loc_14003E281
0x14003e1a8  lea     r8d, [rdi+4]
0x14003e1ac  mov     cs:LpacServicesManagementCapabilitySid, rsi
0x14003e1b3  lea     rdx, [rbp+var_20]
0x14003e1b7  lea     rcx, UserModeDriversSid
0x14003e1be  call    ScAllocateAndInitializeSid
0x14003e1c3  mov     ebx, eax
0x14003e1c5  test    eax, eax
0x14003e1c7  js      loc_14003E281
0x14003e1cd  mov     rcx, cs:UserModeDriversSid; Sid
0x14003e1d4  xor     edx, edx; SubAuthority
0x14003e1d6  call    cs:__imp_RtlSubAuthoritySid
0x14003e1dc  mov     edx, r15d; SubAuthority
0x14003e1df  mov     dword ptr [rax], 54h ; 'T'
0x14003e1e5  mov     rcx, cs:UserModeDriversSid; Sid
0x14003e1ec  call    cs:__imp_RtlSubAuthoritySid
0x14003e1f2  mov     edx, edi; SubAuthority
0x14003e1f4  mov     [rax], r14d
0x14003e1f7  mov     rcx, cs:UserModeDriversSid; Sid
0x14003e1fe  call    cs:__imp_RtlSubAuthoritySid
0x14003e204  lea     edx, [rdi+1]; SubAuthority
0x14003e207  mov     [rax], r14d
0x14003e20a  mov     rcx, cs:UserModeDriversSid; Sid
0x14003e211  call    cs:__imp_RtlSubAuthoritySid
0x14003e217  lea     edx, [rdi+2]; SubAuthority
0x14003e21a  mov     [rax], r14d
0x14003e21d  mov     rcx, cs:UserModeDriversSid; Sid
0x14003e224  call    cs:__imp_RtlSubAuthoritySid
0x14003e22a  lea     edx, [rdi+3]; SubAuthority
0x14003e22d  mov     [rax], r14d
0x14003e230  mov     rcx, cs:UserModeDriversSid; Sid
0x14003e237  call    cs:__imp_RtlSubAuthoritySid
0x14003e23d  mov     r8d, edi
0x14003e240  lea     rdx, [rbp+var_20]
0x14003e244  lea     rcx, AllRestrictedServicesSid
0x14003e24b  mov     [rax], r14d
0x14003e24e  call    ScAllocateAndInitializeSid
0x14003e253  mov     ebx, eax
0x14003e255  test    eax, eax
0x14003e257  js      short loc_14003E281
0x14003e259  mov     rcx, cs:AllRestrictedServicesSid; Sid
0x14003e260  xor     edx, edx; SubAuthority
0x14003e262  call    cs:__imp_RtlSubAuthoritySid
0x14003e268  mov     edx, r15d; SubAuthority
0x14003e26b  mov     dword ptr [rax], 63h ; 'c'
0x14003e271  mov     rcx, cs:AllRestrictedServicesSid; Sid
0x14003e278  call    cs:__imp_RtlSubAuthoritySid
0x14003e27e  mov     [rax], r14d
0x14003e281  lea     rcx, qword_1400BC960
0x14003e288  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14003e28e  mov     eax, ebx
0x14003e290  mov     rcx, [rbp+var_10]
0x14003e294  xor     rcx, rsp; StackCookie
0x14003e297  call    __security_check_cookie
0x14003e29c  add     rsp, 40h
0x14003e2a0  pop     r15
0x14003e2a2  pop     r14
0x14003e2a4  pop     r12
0x14003e2a6  pop     rdi
0x14003e2a7  pop     rsi
0x14003e2a8  pop     rbx
0x14003e2a9  pop     rbp
0x14003e2aa  retn
```
