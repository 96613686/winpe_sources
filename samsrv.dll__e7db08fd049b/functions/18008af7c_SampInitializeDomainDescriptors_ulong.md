# SampInitializeDomainDescriptors(ulong)

- ea: `0x18008af7c`
- end: `0x18008b457`
- name: `?SampInitializeDomainDescriptors@@YAJK@Z`
- size: `1243`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800539f4`
- `0x18005afd0`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x18008af7c`
- `0x18008c120`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18008b10a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008b10a`
- `ntdll!RtlSubAuthoritySid` at `0x18008b03a`
- `ntdll!RtlSubAuthoritySid` at `0x18008b04e`
- `ntdll!RtlSubAuthoritySid` at `0x18008b072`
- `ntdll!RtlSubAuthoritySid` at `0x18008b081`
- `ntdll!RtlSubAuthoritySid` at `0x18008b03a`
- `ntdll!RtlSubAuthoritySid` at `0x18008b04e`
- `ntdll!RtlSubAuthoritySid` at `0x18008b072`
- `ntdll!RtlSubAuthoritySid` at `0x18008b081`
- `ntdll!RtlInitializeSid` at `0x18008b02e`
- `ntdll!RtlInitializeSid` at `0x18008b066`
- `ntdll!RtlInitializeSid` at `0x18008b02e`
- `ntdll!RtlInitializeSid` at `0x18008b066`
- `ntdll!RtlFreeHeap` at `0x18008b3ff`
- `ntdll!RtlFreeHeap` at `0x18008b3ff`
- `ntdll!RtlAllocateHeap` at `0x18008b0bb`
- `ntdll!RtlAllocateHeap` at `0x18008b0bb`
- `ntdll!RtlCopySid` at `0x18008b101`
- `ntdll!RtlCopySid` at `0x18008b101`
- `ntdll!RtlLengthSid` at `0x18008b0a0`
- `ntdll!RtlLengthSid` at `0x18008b0a0`

## pseudocode

```c
__int64 __fastcall SampInitializeDomainDescriptors(unsigned int a1)
{
  __int64 v1; // rbx
  PULONG v2; // rax
  struct _PSAMP_DEFINED_DOMAINS *v3; // rcx
  __int64 v4; // rdi
  ULONG v5; // ebx
  PVOID Heap; // rax
  void *v7; // rsi
  PUNICODE_STRING v8; // rcx
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  PUCHAR v12; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-B0h] BYREF
  struct _GENERIC_MAPPING v15; // [rsp+58h] [rbp-A8h] BYREF
  struct _GENERIC_MAPPING v16; // [rsp+68h] [rbp-98h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  int v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+94h] [rbp-6Ch]
  int v21; // [rsp+98h] [rbp-68h]
  _BYTE Sid[32]; // [rsp+B0h] [rbp-50h] BYREF
  PSID v23; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v24; // [rsp+D8h] [rbp-28h]
  _BYTE *v25; // [rsp+E0h] [rbp-20h]
  PSID v26; // [rsp+E8h] [rbp-18h]
  void *v27; // [rsp+F0h] [rbp-10h]
  _BYTE v28[32]; // [rsp+120h] [rbp+20h] BYREF

  v1 = a1;
  memset_0(&v23, 0, 0x50u);
  GenericMapping.GenericRead = 131076;
  GenericMapping.GenericAll = 983071;
  v15.GenericAll = 983071;
  GenericMapping.GenericWrite = 131091;
  GenericMapping.GenericExecute = 131080;
  v15.GenericRead = 131088;
  v15.GenericWrite = 131086;
  v15.GenericExecute = 131073;
  v16.GenericRead = 131866;
  v16.GenericWrite = 131140;
  v16.GenericExecute = 131137;
  v16.GenericAll = 985087;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  RtlInitializeSid(v28, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v28, 0) = 32;
  v2 = RtlSubAuthoritySid(v28, 1u);
  v3 = SampDefinedDomains;
  v4 = 1360 * v1;
  *v2 = 548;
  v5 = RtlLengthSid(*((PSID *)v3 + 170 * v1 + 1)) + 4;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  v7 = Heap;
  if ( Heap )
  {
    RtlCopySid(v5, Heap, *(PSID *)((char *)SampDefinedDomains + v4 + 8));
    v12 = RtlSubAuthorityCountSid(v7);
    ++*v12;
    v24 = Sid;
    v25 = v28;
    v26 = SampUserSigninSupportCapabilitySid;
    v18 = 0xF001F0002000CLL;
    v20 = 131084;
    v23 = SampWorldSid;
    v19 = 983071;
    v9 = SampBuildSamProtection(
           SampWorldSid,
           Sid,
           4u,
           (__int64)&v23,
           (__int64)&v18,
           &GenericMapping,
           0,
           (ULONG *)((char *)SampDefinedDomains + v4 + 120),
           (struct _PSAMP_DEFINED_DOMAINS *)((char *)SampDefinedDomains + v4 + 80),
           0);
    if ( v9 >= 0 )
    {
      v24 = Sid;
      v23 = SampWorldSid;
      v18 = 0xF001F00020011LL;
      v9 = SampBuildSamProtection(
             SampWorldSid,
             Sid,
             2u,
             (__int64)&v23,
             (__int64)&v18,
             &v15,
             0,
             (ULONG *)((char *)SampDefinedDomains + v4 + 108),
             (struct _PSAMP_DEFINED_DOMAINS *)((char *)SampDefinedDomains + v4 + 56),
             0);
      if ( v9 >= 0 )
      {
        v24 = Sid;
        v25 = v28;
        v23 = SampWorldSid;
        v18 = 0xF001F00020011LL;
        v19 = 983071;
        v9 = SampBuildSamProtection(
               SampWorldSid,
               Sid,
               3u,
               (__int64)&v23,
               (__int64)&v18,
               &v15,
               0,
               (ULONG *)((char *)SampDefinedDomains + v4 + 116),
               (struct _PSAMP_DEFINED_DOMAINS *)((char *)SampDefinedDomains + v4 + 72),
               0);
        if ( v9 >= 0 )
        {
          v24 = Sid;
          v25 = SampUserSigninSupportCapabilitySid;
          v23 = SampWorldSid;
          v18 = 0xF07FF0002035BLL;
          v19 = 131867;
          v26 = v7;
          v20 = 131140;
          v9 = SampBuildSamProtection(
                 SampWorldSid,
                 Sid,
                 4u,
                 (__int64)&v23,
                 (__int64)&v18,
                 &v16,
                 1,
                 (ULONG *)((char *)SampDefinedDomains + v4 + 104),
                 (struct _PSAMP_DEFINED_DOMAINS *)((char *)SampDefinedDomains + v4 + 48),
                 (PULONG *)((char *)SampDefinedDomains + v4 + 88));
          if ( v9 >= 0 )
          {
            v24 = Sid;
            v25 = v28;
            v26 = SampUserSigninSupportCapabilitySid;
            v23 = SampWorldSid;
            v18 = 0xF07FF0002035BLL;
            v19 = 985087;
            v20 = 131867;
            v27 = v7;
            v21 = 131140;
            v9 = SampBuildSamProtection(
                   SampWorldSid,
                   Sid,
                   5u,
                   (__int64)&v23,
                   (__int64)&v18,
                   &v16,
                   1,
                   (ULONG *)((char *)SampDefinedDomains + v4 + 112),
                   (struct _PSAMP_DEFINED_DOMAINS *)((char *)SampDefinedDomains + v4 + 64),
                   (PULONG *)((char *)SampDefinedDomains + v4 + 96));
          }
        }
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v8 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 11;
      v11 = (unsigned int)v9;
      goto LABEL_11;
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    v9 = -1073741670;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 10;
      v11 = 3221225626LL;
LABEL_11:
      WPP_SF_Dd(v8[3].Buffer, v10, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, v11, v9);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008af7c  mov     [rsp-8+arg_8], rbx
0x18008af81  mov     [rsp-8+arg_10], rsi
0x18008af86  push    rbp
0x18008af87  push    rdi
0x18008af88  push    r15
0x18008af8a  lea     rbp, [rsp-50h]
0x18008af8f  sub     rsp, 150h
0x18008af96  mov     rax, cs:__security_cookie
0x18008af9d  xor     rax, rsp
0x18008afa0  mov     [rbp+60h+var_20], rax
0x18008afa4  xor     edx, edx; Val
0x18008afa6  mov     ebx, ecx
0x18008afa8  lea     rcx, [rbp+60h+var_90]; void *
0x18008afac  lea     r8d, [rdx+50h]; Size
0x18008afb0  call    memset_0
0x18008afb5  mov     r15d, 0F001Fh
0x18008afbb  mov     [rsp+160h+var_E8.GenericRead], 20004h
0x18008afc3  mov     r8b, 2; SubAuthorityCount
0x18008afc6  mov     [rbp+60h+var_E8.GenericAll], r15d
0x18008afca  lea     rdx, [rsp+160h+IdentifierAuthority]; IdentifierAuthority
0x18008afcf  mov     [rsp+160h+var_108.GenericAll], r15d
0x18008afd4  lea     rcx, [rbp+60h+Sid]; Sid
0x18008afd8  mov     [rsp+160h+var_E8.GenericWrite], 20013h
0x18008afe0  mov     [rbp+60h+var_E8.GenericExecute], 20008h
0x18008afe7  mov     [rsp+160h+var_108.GenericRead], 20010h
0x18008afef  mov     [rsp+160h+var_108.GenericWrite], 2000Eh
0x18008aff7  mov     [rsp+160h+var_108.GenericExecute], 20001h
0x18008afff  mov     [rsp+160h+var_F8.GenericRead], 2031Ah
0x18008b007  mov     [rsp+160h+var_F8.GenericWrite], 20044h
0x18008b00f  mov     [rsp+160h+var_F8.GenericExecute], 20041h
0x18008b017  mov     [rsp+160h+var_F8.GenericAll], 0F07FFh
0x18008b01f  mov     dword ptr [rsp+160h+IdentifierAuthority.Value], 0
0x18008b027  mov     word ptr [rsp+160h+IdentifierAuthority.Value+4], 500h
0x18008b02e  call    cs:__imp_RtlInitializeSid
0x18008b034  xor     edx, edx; SubAuthority
0x18008b036  lea     rcx, [rbp+60h+Sid]; Sid
0x18008b03a  call    cs:__imp_RtlSubAuthoritySid
0x18008b040  mov     edi, 20h ; ' '
0x18008b045  lea     rcx, [rbp+60h+Sid]; Sid
0x18008b049  mov     [rax], edi
0x18008b04b  lea     edx, [rdi-1Fh]; SubAuthority
0x18008b04e  call    cs:__imp_RtlSubAuthoritySid
0x18008b054  mov     r8b, 2; SubAuthorityCount
0x18008b057  lea     rdx, [rsp+160h+IdentifierAuthority]; IdentifierAuthority
0x18008b05c  lea     rcx, [rbp+60h+var_40]; Sid
0x18008b060  mov     dword ptr [rax], 220h
0x18008b066  call    cs:__imp_RtlInitializeSid
0x18008b06c  xor     edx, edx; SubAuthority
0x18008b06e  lea     rcx, [rbp+60h+var_40]; Sid
0x18008b072  call    cs:__imp_RtlSubAuthoritySid
0x18008b078  lea     edx, [rdi-1Fh]; SubAuthority
0x18008b07b  lea     rcx, [rbp+60h+var_40]; Sid
0x18008b07f  mov     [rax], edi
0x18008b081  call    cs:__imp_RtlSubAuthoritySid
0x18008b087  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b08e  imul    rdi, rbx, 550h
0x18008b095  mov     dword ptr [rax], 224h
0x18008b09b  mov     rcx, [rdi+rcx+8]; Sid
0x18008b0a0  call    cs:__imp_RtlLengthSid
0x18008b0a6  mov     rcx, gs:60h
0x18008b0af  xor     edx, edx; Flags
0x18008b0b1  lea     ebx, [rax+4]
0x18008b0b4  mov     rcx, [rcx+30h]; HeapHandle
0x18008b0b8  mov     r8d, ebx; Size
0x18008b0bb  call    cs:__imp_RtlAllocateHeap
0x18008b0c1  mov     rsi, rax
0x18008b0c4  test    rax, rax
0x18008b0c7  jnz     short loc_18008B0F0
0x18008b0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b0d0  mov     ebx, 0C000009Ah
0x18008b0d5  test    dword ptr [rcx+44h], 20000h
0x18008b0dc  jz      loc_18008B431
0x18008b0e2  lea     edx, [rax+0Ah]
0x18008b0e5  mov     r9d, 0C000009Ah
0x18008b0eb  jmp     loc_18008B41D
0x18008b0f0  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b0f7  mov     rdx, rsi; DestinationSid
0x18008b0fa  mov     ecx, ebx; DestinationSidLength
0x18008b0fc  mov     r8, [rdi+r8+8]; SourceSid
0x18008b101  call    cs:__imp_RtlCopySid
0x18008b107  mov     rcx, rsi; Sid
0x18008b10a  call    cs:__imp_RtlSubAuthorityCountSid
0x18008b110  mov     [rsp+160h+var_118], 0; __int64
0x18008b119  lea     r9, [rbp+60h+var_90]
0x18008b11d  mov     edx, 2000Ch
0x18008b122  inc     byte ptr [rax]
0x18008b124  lea     rax, [rbp+60h+Sid]
0x18008b128  mov     rcx, cs:SampWorldSid; Sid
0x18008b12f  mov     [rbp+60h+var_88], rax
0x18008b133  lea     rax, [rbp+60h+var_40]
0x18008b137  mov     [rbp+60h+var_80], rax
0x18008b13b  mov     rax, cs:SampUserSigninSupportCapabilitySid
0x18008b142  mov     [rbp+60h+var_78], rax
0x18008b146  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b14d  mov     dword ptr [rbp+60h+var_D8], edx
0x18008b150  mov     [rbp+60h+var_CC], edx
0x18008b153  mov     [rbp+60h+var_90], rcx
0x18008b157  lea     rdx, [rax+50h]
0x18008b15b  mov     dword ptr [rbp+60h+var_D8+4], r15d
0x18008b15f  lea     r8, [rax+78h]
0x18008b163  mov     [rbp+60h+var_D0], r15d
0x18008b167  add     rdx, rdi
0x18008b16a  lea     rax, [rsp+160h+var_E8]
0x18008b16f  mov     [rsp+160h+var_120], rdx; __int64
0x18008b174  add     r8, rdi
0x18008b177  mov     [rsp+160h+var_128], r8; __int64
0x18008b17c  lea     rdx, [rbp+60h+Sid]; Group
0x18008b180  mov     [rsp+160h+var_130], 0; char
0x18008b185  mov     r8d, 4
0x18008b18b  mov     [rsp+160h+GenericMapping], rax; GenericMapping
0x18008b190  lea     rax, [rbp+60h+var_D8]
0x18008b194  mov     [rsp+160h+var_140], rax; __int64
0x18008b199  call    SampBuildSamProtection
0x18008b19e  mov     ebx, eax
0x18008b1a0  test    eax, eax
0x18008b1a2  js      loc_18008B3ED
0x18008b1a8  mov     rcx, cs:SampWorldSid; Sid
0x18008b1af  lea     rax, [rbp+60h+Sid]
0x18008b1b3  mov     [rsp+160h+var_118], 0; __int64
0x18008b1bc  lea     r9, [rbp+60h+var_90]
0x18008b1c0  mov     [rbp+60h+var_88], rax
0x18008b1c4  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b1cb  mov     [rbp+60h+var_90], rcx
0x18008b1cf  mov     dword ptr [rbp+60h+var_D8], 20011h
0x18008b1d6  mov     dword ptr [rbp+60h+var_D8+4], r15d
0x18008b1da  lea     rdx, [rax+38h]
0x18008b1de  lea     r8, [rax+6Ch]
0x18008b1e2  add     rdx, rdi
0x18008b1e5  mov     [rsp+160h+var_120], rdx; __int64
0x18008b1ea  lea     rax, [rsp+160h+var_108]
0x18008b1ef  add     r8, rdi
0x18008b1f2  lea     rdx, [rbp+60h+Sid]; Group
0x18008b1f6  mov     [rsp+160h+var_128], r8; __int64
0x18008b1fb  mov     r8d, 2
0x18008b201  mov     [rsp+160h+var_130], 0; char
0x18008b206  mov     [rsp+160h+GenericMapping], rax; GenericMapping
0x18008b20b  lea     rax, [rbp+60h+var_D8]
0x18008b20f  mov     [rsp+160h+var_140], rax; __int64
0x18008b214  call    SampBuildSamProtection
0x18008b219  mov     ebx, eax
0x18008b21b  test    eax, eax
0x18008b21d  js      loc_18008B3ED
0x18008b223  mov     rcx, cs:SampWorldSid; Sid
0x18008b22a  lea     rax, [rbp+60h+Sid]
0x18008b22e  mov     [rbp+60h+var_88], rax
0x18008b232  lea     r9, [rbp+60h+var_90]
0x18008b236  mov     [rsp+160h+var_118], 0; __int64
0x18008b23f  lea     rax, [rbp+60h+var_40]
0x18008b243  mov     [rbp+60h+var_80], rax
0x18008b247  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b24e  mov     [rbp+60h+var_90], rcx
0x18008b252  mov     dword ptr [rbp+60h+var_D8], 20011h
0x18008b259  mov     dword ptr [rbp+60h+var_D8+4], r15d
0x18008b25d  lea     rdx, [rax+48h]
0x18008b261  mov     [rbp+60h+var_D0], r15d
0x18008b265  lea     r8, [rax+74h]
0x18008b269  add     rdx, rdi
0x18008b26c  mov     [rsp+160h+var_120], rdx; __int64
0x18008b271  lea     rax, [rsp+160h+var_108]
0x18008b276  add     r8, rdi
0x18008b279  lea     rdx, [rbp+60h+Sid]; Group
0x18008b27d  mov     [rsp+160h+var_128], r8; __int64
0x18008b282  mov     r8d, 3
0x18008b288  mov     [rsp+160h+var_130], 0; char
0x18008b28d  mov     [rsp+160h+GenericMapping], rax; GenericMapping
0x18008b292  lea     rax, [rbp+60h+var_D8]
0x18008b296  mov     [rsp+160h+var_140], rax; __int64
0x18008b29b  call    SampBuildSamProtection
0x18008b2a0  mov     ebx, eax
0x18008b2a2  test    eax, eax
0x18008b2a4  js      loc_18008B3ED
0x18008b2aa  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b2b1  lea     rax, [rbp+60h+Sid]
0x18008b2b5  mov     rcx, cs:SampWorldSid; Sid
0x18008b2bc  lea     r9, [rbp+60h+var_90]
0x18008b2c0  mov     [rbp+60h+var_88], rax
0x18008b2c4  mov     r15d, 2035Bh
0x18008b2ca  mov     rax, cs:SampUserSigninSupportCapabilitySid
0x18008b2d1  mov     [rbp+60h+var_80], rax
0x18008b2d5  lea     rdx, [r8+30h]
0x18008b2d9  lea     rax, [r8+58h]
0x18008b2dd  mov     [rbp+60h+var_90], rcx
0x18008b2e1  add     rax, rdi
0x18008b2e4  mov     dword ptr [rbp+60h+var_D8], r15d
0x18008b2e8  mov     [rsp+160h+var_118], rax; __int64
0x18008b2ed  add     r8, 68h ; 'h'
0x18008b2f1  add     rdx, rdi
0x18008b2f4  mov     dword ptr [rbp+60h+var_D8+4], 0F07FFh
0x18008b2fb  mov     [rsp+160h+var_120], rdx; __int64
0x18008b300  lea     rax, [rsp+160h+var_F8]
0x18008b305  add     r8, rdi
0x18008b308  mov     [rbp+60h+var_D0], 2031Bh
0x18008b30f  mov     [rsp+160h+var_128], r8; __int64
0x18008b314  lea     rdx, [rbp+60h+Sid]; Group
0x18008b318  mov     [rsp+160h+var_130], 1; char
0x18008b31d  mov     r8d, 4
0x18008b323  mov     [rsp+160h+GenericMapping], rax; GenericMapping
0x18008b328  lea     rax, [rbp+60h+var_D8]
0x18008b32c  mov     [rsp+160h+var_140], rax; __int64
0x18008b331  mov     [rbp+60h+var_78], rsi
0x18008b335  mov     [rbp+60h+var_CC], 20044h
0x18008b33c  call    SampBuildSamProtection
0x18008b341  mov     ebx, eax
0x18008b343  test    eax, eax
0x18008b345  js      loc_18008B3ED
0x18008b34b  mov     r9, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008b352  lea     rax, [rbp+60h+Sid]
0x18008b356  mov     rcx, cs:SampWorldSid; Sid
0x18008b35d  mov     r8d, 5
0x18008b363  mov     [rbp+60h+var_88], rax
0x18008b367  lea     rax, [rbp+60h+var_40]
0x18008b36b  mov     [rbp+60h+var_80], rax
0x18008b36f  mov     rax, cs:SampUserSigninSupportCapabilitySid
0x18008b376  lea     rdx, [r9+40h]
0x18008b37a  mov     [rbp+60h+var_78], rax
0x18008b37e  add     rdx, rdi
0x18008b381  lea     rax, [r9+60h]
0x18008b385  mov     [rbp+60h+var_90], rcx
0x18008b389  add     rax, rdi
0x18008b38c  mov     dword ptr [rbp+60h+var_D8], r15d
0x18008b390  mov     [rsp+160h+var_118], rax; __int64
0x18008b395  add     r9, 70h ; 'p'
0x18008b399  mov     [rsp+160h+var_120], rdx; __int64
0x18008b39e  lea     rax, [rsp+160h+var_F8]
0x18008b3a3  add     r9, rdi
0x18008b3a6  mov     dword ptr [rbp+60h+var_D8+4], 0F07FFh
0x18008b3ad  mov     [rsp+160h+var_128], r9; __int64
0x18008b3b2  lea     rdx, [rbp+60h+Sid]; Group
0x18008b3b6  mov     [rsp+160h+var_130], 1; char
0x18008b3bb  lea     r9, [rbp+60h+var_90]
0x18008b3bf  mov     [rsp+160h+GenericMapping], rax; GenericMapping
0x18008b3c4  lea     rax, [rbp+60h+var_D8]
0x18008b3c8  mov     [rsp+160h+var_140], rax; __int64
0x18008b3cd  mov     [rbp+60h+var_D0], 0F07FFh
0x18008b3d4  mov     [rbp+60h+var_CC], 2031Bh
0x18008b3db  mov     [rbp+60h+var_70], rsi
0x18008b3df  mov     [rbp+60h+var_C8], 20044h
0x18008b3e6  call    SampBuildSamProtection
0x18008b3eb  mov     ebx, eax
0x18008b3ed  mov     rcx, gs:60h
0x18008b3f6  mov     r8, rsi; P
0x18008b3f9  xor     edx, edx; Flags
0x18008b3fb  mov     rcx, [rcx+30h]; HeapHandle
0x18008b3ff  call    cs:__imp_RtlFreeHeap
0x18008b405  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b40c  test    dword ptr [rcx+44h], 20000h
0x18008b413  jz      short loc_18008B431
0x18008b415  mov     edx, 0Bh
0x18008b41a  mov     r9d, ebx
0x18008b41d  mov     rcx, [rcx+38h]
0x18008b421  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008b428  mov     dword ptr [rsp+160h+var_140], ebx
0x18008b42c  call    WPP_SF_Dd
0x18008b431  mov     eax, ebx
0x18008b433  mov     rcx, [rbp+60h+var_20]
0x18008b437  xor     rcx, rsp; StackCookie
0x18008b43a  call    __security_check_cookie
0x18008b43f  lea     r11, [rsp+160h+var_10]
0x18008b447  mov     rbx, [r11+28h]
0x18008b44b  mov     rsi, [r11+30h]
0x18008b44f  mov     rsp, r11
0x18008b452  pop     r15
0x18008b454  pop     rdi
0x18008b455  pop     rbp
0x18008b456  retn
```
