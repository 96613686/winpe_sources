# SampMakeLowBoxRpcSD(void * *)

- ea: `0x18008e1a4`
- end: `0x18008e47a`
- name: `?SampMakeLowBoxRpcSD@@YAJPEAPEAX@Z`
- size: `726`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008e830`
- `0x18008e998`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18008e1a4`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e2b6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e2f5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e334`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e376`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e3b0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e2b6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e2f5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e334`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e376`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18008e3b0`
- `ntdll!RtlFreeSid` at `0x18008e3ef`
- `ntdll!RtlFreeSid` at `0x18008e3ff`
- `ntdll!RtlFreeSid` at `0x18008e40f`
- `ntdll!RtlFreeSid` at `0x18008e41f`
- `ntdll!RtlFreeSid` at `0x18008e42e`
- `ntdll!RtlFreeSid` at `0x18008e3ef`
- `ntdll!RtlFreeSid` at `0x18008e3ff`
- `ntdll!RtlFreeSid` at `0x18008e40f`
- `ntdll!RtlFreeSid` at `0x18008e41f`
- `ntdll!RtlFreeSid` at `0x18008e42e`
- `ntdll!RtlCreateAndSetSD` at `0x18008e3d2`
- `ntdll!RtlCreateAndSetSD` at `0x18008e3d2`

## pseudocode

```c
__int64 __fastcall SampMakeLowBoxRpcSD(void **a1)
{
  NTSTATUS v2; // ebx
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v5; // [rsp+68h] [rbp-98h] BYREF
  PSID v6; // [rsp+70h] [rbp-90h] BYREF
  PSID v7; // [rsp+78h] [rbp-88h] BYREF
  PSID v8; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+88h] [rbp-78h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v10; // [rsp+90h] [rbp-70h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v12; // [rsp+A0h] [rbp-60h] BYREF
  __int16 AceData; // [rsp+B0h] [rbp-50h] BYREF
  char v14; // [rsp+B2h] [rbp-4Eh]
  int v15; // [rsp+B4h] [rbp-4Ch]
  PSID *p_Sid; // [rsp+B8h] [rbp-48h]
  __int16 v17; // [rsp+C0h] [rbp-40h]
  char v18; // [rsp+C2h] [rbp-3Eh]
  int v19; // [rsp+C4h] [rbp-3Ch]
  PSID *v20; // [rsp+C8h] [rbp-38h]
  __int16 v21; // [rsp+D0h] [rbp-30h]
  char v22; // [rsp+D2h] [rbp-2Eh]
  unsigned int v23; // [rsp+D4h] [rbp-2Ch]
  PSID *v24; // [rsp+D8h] [rbp-28h]
  __int16 v25; // [rsp+E0h] [rbp-20h]
  char v26; // [rsp+E2h] [rbp-1Eh]
  int v27; // [rsp+E4h] [rbp-1Ch]
  PSID *v28; // [rsp+E8h] [rbp-18h]
  __int16 v29; // [rsp+F0h] [rbp-10h]
  char v30; // [rsp+F2h] [rbp-Eh]
  int v31; // [rsp+F4h] [rbp-Ch]
  PSID *v32; // [rsp+F8h] [rbp-8h]
  __int16 v33; // [rsp+100h] [rbp+0h]
  char v34; // [rsp+102h] [rbp+2h]
  int v35; // [rsp+104h] [rbp+4h]
  PSID *v36; // [rsp+108h] [rbp+8h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  Sid = 0;
  v15 = -536870912;
  v19 = -536870912;
  v27 = 0x10000000;
  p_Sid = &Sid;
  v31 = 0x10000000;
  v20 = &v5;
  v35 = -536870912;
  v24 = &v6;
  v5 = 0;
  v28 = &v7;
  v7 = 0;
  v32 = &v8;
  v36 = &SampUserSigninSupportCapabilitySid;
  v8 = 0;
  v6 = 0;
  NewDescriptor = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v10.Value = 0;
  *(_WORD *)&v10.Value[4] = 1280;
  *(_DWORD *)v12.Value = 0;
  *(_WORD *)&v12.Value[4] = 768;
  AceData = 0;
  v14 = 0;
  v17 = 1;
  v18 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0x80000000;
  v25 = 0;
  v26 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v2 >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(&v10, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v5);
    if ( v2 >= 0 )
    {
      v2 = RtlAllocateAndInitializeSid(&v10, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, &v6);
      if ( v2 >= 0 )
      {
        v2 = RtlAllocateAndInitializeSid(&v10, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7);
        if ( v2 >= 0 )
        {
          v2 = RtlAllocateAndInitializeSid(&v12, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v8);
          if ( v2 >= 0 )
          {
            v2 = RtlCreateAndSetSD(&AceData, 6u, 0, 0, &NewDescriptor);
            if ( v2 >= 0 )
              *a1 = NewDescriptor;
          }
        }
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v5 )
    RtlFreeSid(v5);
  if ( v6 )
    RtlFreeSid(v6);
  if ( v7 )
    RtlFreeSid(v7);
  if ( v8 )
    RtlFreeSid(v8);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 29, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v2, v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008e1a4  push    rbp
0x18008e1a6  push    rbx
0x18008e1a7  push    rsi
0x18008e1a8  push    rdi
0x18008e1a9  lea     rbp, [rsp-28h]
0x18008e1ae  sub     rsp, 128h
0x18008e1b5  mov     rax, cs:__security_cookie
0x18008e1bc  xor     rax, rsp
0x18008e1bf  mov     [rbp+40h+var_30], rax
0x18008e1c3  xor     esi, esi
0x18008e1c5  mov     word ptr [rbp+40h+IdentifierAuthority.Value+4], 100h
0x18008e1cb  mov     edx, 0E0000000h
0x18008e1d0  mov     [rsp+140h+var_E0], rsi
0x18008e1d5  mov     rdi, rcx
0x18008e1d8  mov     [rbp+40h+var_8C], edx
0x18008e1db  mov     ecx, 10000000h
0x18008e1e0  mov     [rbp+40h+var_7C], edx
0x18008e1e3  lea     rax, [rsp+140h+var_E0]
0x18008e1e8  mov     [rbp+40h+var_5C], ecx
0x18008e1eb  mov     [rbp+40h+var_88], rax
0x18008e1ef  xor     r9d, r9d; SubAuthority1
0x18008e1f2  lea     rax, [rsp+140h+var_D8]
0x18008e1f7  mov     [rbp+40h+var_4C], ecx
0x18008e1fa  mov     [rbp+40h+var_78], rax
0x18008e1fe  lea     rcx, [rbp+40h+IdentifierAuthority]; IdentifierAuthority
0x18008e202  lea     rax, [rsp+140h+var_D0]
0x18008e207  mov     [rbp+40h+var_3C], edx
0x18008e20a  mov     [rbp+40h+var_68], rax
0x18008e20e  xor     r8d, r8d; SubAuthority0
0x18008e211  lea     rax, [rsp+140h+var_C8]
0x18008e216  mov     [rsp+140h+var_D8], rsi
0x18008e21b  mov     [rbp+40h+var_58], rax
0x18008e21f  mov     dl, 1; SubAuthorityCount
0x18008e221  lea     rax, [rbp+40h+var_C0]
0x18008e225  mov     [rsp+140h+var_C8], rsi
0x18008e22a  mov     [rbp+40h+var_48], rax
0x18008e22e  lea     rax, SampUserSigninSupportCapabilitySid
0x18008e235  mov     [rbp+40h+var_38], rax
0x18008e239  lea     rax, [rsp+140h+var_E0]
0x18008e23e  mov     [rsp+140h+Sid], rax; Sid
0x18008e243  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x18008e247  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x18008e24b  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x18008e24f  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x18008e253  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18008e257  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x18008e25b  mov     [rbp+40h+var_C0], rsi
0x18008e25f  mov     [rsp+140h+var_D0], rsi
0x18008e264  mov     [rbp+40h+NewDescriptor], rsi
0x18008e268  mov     dword ptr [rbp+40h+IdentifierAuthority.Value], esi
0x18008e26b  mov     dword ptr [rbp+40h+var_B0.Value], esi
0x18008e26e  mov     word ptr [rbp+40h+var_B0.Value+4], 500h
0x18008e274  mov     dword ptr [rbp+40h+var_A0.Value], esi
0x18008e277  mov     word ptr [rbp+40h+var_A0.Value+4], 300h
0x18008e27d  mov     [rbp+40h+AceData], si
0x18008e281  mov     [rbp+40h+var_8E], sil
0x18008e285  mov     [rbp+40h+var_80], 1
0x18008e28b  mov     [rbp+40h+var_7E], sil
0x18008e28f  mov     [rbp+40h+var_70], si
0x18008e293  mov     [rbp+40h+var_6E], sil
0x18008e297  mov     [rbp+40h+var_6C], 80000000h
0x18008e29e  mov     [rbp+40h+var_60], si
0x18008e2a2  mov     [rbp+40h+var_5E], sil
0x18008e2a6  mov     [rbp+40h+var_50], si
0x18008e2aa  mov     [rbp+40h+var_4E], sil
0x18008e2ae  mov     [rbp+40h+var_40], si
0x18008e2b2  mov     [rbp+40h+var_3E], sil
0x18008e2b6  call    cs:__imp_RtlAllocateAndInitializeSid
0x18008e2bc  mov     ebx, eax
0x18008e2be  test    eax, eax
0x18008e2c0  js      loc_18008E3E5
0x18008e2c6  lea     rax, [rsp+140h+var_D8]
0x18008e2cb  xor     r9d, r9d; SubAuthority1
0x18008e2ce  mov     [rsp+140h+Sid], rax; Sid
0x18008e2d3  lea     r8d, [rsi+0Ch]; SubAuthority0
0x18008e2d7  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x18008e2db  lea     rcx, [rbp+40h+var_B0]; IdentifierAuthority
0x18008e2df  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x18008e2e3  mov     dl, 1; SubAuthorityCount
0x18008e2e5  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x18008e2e9  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x18008e2ed  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18008e2f1  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x18008e2f5  call    cs:__imp_RtlAllocateAndInitializeSid
0x18008e2fb  mov     ebx, eax
0x18008e2fd  test    eax, eax
0x18008e2ff  js      loc_18008E3E5
0x18008e305  lea     rax, [rsp+140h+var_D0]
0x18008e30a  xor     r9d, r9d; SubAuthority1
0x18008e30d  mov     [rsp+140h+Sid], rax; Sid
0x18008e312  lea     r8d, [rsi+7]; SubAuthority0
0x18008e316  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x18008e31a  lea     rcx, [rbp+40h+var_B0]; IdentifierAuthority
0x18008e31e  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x18008e322  mov     dl, 1; SubAuthorityCount
0x18008e324  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x18008e328  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x18008e32c  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18008e330  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x18008e334  call    cs:__imp_RtlAllocateAndInitializeSid
0x18008e33a  mov     ebx, eax
0x18008e33c  test    eax, eax
0x18008e33e  js      loc_18008E3E5
0x18008e344  lea     rax, [rsp+140h+var_C8]
0x18008e349  mov     r9d, 220h; SubAuthority1
0x18008e34f  mov     [rsp+140h+Sid], rax; Sid
0x18008e354  lea     r8d, [rsi+20h]; SubAuthority0
0x18008e358  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x18008e35c  lea     rcx, [rbp+40h+var_B0]; IdentifierAuthority
0x18008e360  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x18008e364  mov     dl, 2; SubAuthorityCount
0x18008e366  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x18008e36a  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x18008e36e  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18008e372  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x18008e376  call    cs:__imp_RtlAllocateAndInitializeSid
0x18008e37c  mov     ebx, eax
0x18008e37e  test    eax, eax
0x18008e380  js      short loc_18008E3E5
0x18008e382  lea     rax, [rbp+40h+var_C0]
0x18008e386  xor     r9d, r9d; SubAuthority1
0x18008e389  mov     [rsp+140h+Sid], rax; Sid
0x18008e38e  lea     r8d, [rsi+4]; SubAuthority0
0x18008e392  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x18008e396  lea     rcx, [rbp+40h+var_A0]; IdentifierAuthority
0x18008e39a  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x18008e39e  mov     dl, 1; SubAuthorityCount
0x18008e3a0  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x18008e3a4  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x18008e3a8  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18008e3ac  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x18008e3b0  call    cs:__imp_RtlAllocateAndInitializeSid
0x18008e3b6  mov     ebx, eax
0x18008e3b8  test    eax, eax
0x18008e3ba  js      short loc_18008E3E5
0x18008e3bc  lea     rax, [rbp+40h+NewDescriptor]
0x18008e3c0  xor     r9d, r9d; GroupSid
0x18008e3c3  xor     r8d, r8d; OwnerSid
0x18008e3c6  mov     qword ptr [rsp+140h+SubAuthority2], rax; NewDescriptor
0x18008e3cb  lea     edx, [rsi+6]; AceCount
0x18008e3ce  lea     rcx, [rbp+40h+AceData]; AceData
0x18008e3d2  call    cs:__imp_RtlCreateAndSetSD
0x18008e3d8  mov     ebx, eax
0x18008e3da  test    eax, eax
0x18008e3dc  js      short loc_18008E3E5
0x18008e3de  mov     rax, [rbp+40h+NewDescriptor]
0x18008e3e2  mov     [rdi], rax
0x18008e3e5  mov     rcx, [rsp+140h+var_E0]; Sid
0x18008e3ea  test    rcx, rcx
0x18008e3ed  jz      short loc_18008E3F5
0x18008e3ef  call    cs:__imp_RtlFreeSid
0x18008e3f5  mov     rcx, [rsp+140h+var_D8]; Sid
0x18008e3fa  test    rcx, rcx
0x18008e3fd  jz      short loc_18008E405
0x18008e3ff  call    cs:__imp_RtlFreeSid
0x18008e405  mov     rcx, [rsp+140h+var_D0]; Sid
0x18008e40a  test    rcx, rcx
0x18008e40d  jz      short loc_18008E415
0x18008e40f  call    cs:__imp_RtlFreeSid
0x18008e415  mov     rcx, [rsp+140h+var_C8]; Sid
0x18008e41a  test    rcx, rcx
0x18008e41d  jz      short loc_18008E425
0x18008e41f  call    cs:__imp_RtlFreeSid
0x18008e425  mov     rcx, [rbp+40h+var_C0]; Sid
0x18008e429  test    rcx, rcx
0x18008e42c  jz      short loc_18008E434
0x18008e42e  call    cs:__imp_RtlFreeSid
0x18008e434  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e43b  test    dword ptr [rcx+44h], 20000h
0x18008e442  jz      short loc_18008E460
0x18008e444  mov     rcx, [rcx+38h]
0x18008e448  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008e44f  mov     edx, 1Dh
0x18008e454  mov     [rsp+140h+SubAuthority2], ebx
0x18008e458  mov     r9d, ebx
0x18008e45b  call    WPP_SF_Dd
0x18008e460  mov     eax, ebx
0x18008e462  mov     rcx, [rbp+40h+var_30]
0x18008e466  xor     rcx, rsp; StackCookie
0x18008e469  call    __security_check_cookie
0x18008e46e  add     rsp, 128h
0x18008e475  pop     rdi
0x18008e476  pop     rsi
0x18008e477  pop     rbx
0x18008e478  pop     rbp
0x18008e479  retn
```
