# LsapMakeLowBoxRpcSD

- ea: `0x18000235c`
- end: `0x18000270c`
- name: `LsapMakeLowBoxRpcSD`
- size: `944`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002840`

## callees

- `0x18000235c`
- `0x1800033f0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x1800024a9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800024ee`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002533`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000257b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800025bf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002605`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800024a9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800024ee`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002533`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000257b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800025bf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002605`
- `ntdll!RtlCreateAndSetSD` at `0x180002653`
- `ntdll!RtlCreateAndSetSD` at `0x180002653`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180002623`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180002623`
- `ntdll!RtlFreeSid` at `0x180002676`
- `ntdll!RtlFreeSid` at `0x18000268c`
- `ntdll!RtlFreeSid` at `0x1800026a2`
- `ntdll!RtlFreeSid` at `0x1800026b8`
- `ntdll!RtlFreeSid` at `0x1800026cd`
- `ntdll!RtlFreeSid` at `0x1800026e2`
- `ntdll!RtlFreeSid` at `0x180002676`
- `ntdll!RtlFreeSid` at `0x18000268c`
- `ntdll!RtlFreeSid` at `0x1800026a2`
- `ntdll!RtlFreeSid` at `0x1800026b8`
- `ntdll!RtlFreeSid` at `0x1800026cd`
- `ntdll!RtlFreeSid` at `0x1800026e2`

## string_xrefs

- `0x1800023a4`: `lpacIdentityServices`

## pseudocode

```c
__int64 __fastcall LsapMakeLowBoxRpcSD(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS v2; // ebx
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v5; // [rsp+68h] [rbp-98h] BYREF
  PSID v6; // [rsp+70h] [rbp-90h] BYREF
  PSID v7; // [rsp+78h] [rbp-88h] BYREF
  PSID v8; // [rsp+80h] [rbp-80h] BYREF
  PSID v9; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v10; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v12[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v13; // [rsp+B0h] [rbp-50h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v16; // [rsp+C8h] [rbp-38h] BYREF
  __int16 AceData; // [rsp+D0h] [rbp-30h] BYREF
  char v18; // [rsp+D2h] [rbp-2Eh]
  int v19; // [rsp+D4h] [rbp-2Ch]
  PSID *p_Sid; // [rsp+D8h] [rbp-28h]
  __int16 v21; // [rsp+E0h] [rbp-20h]
  char v22; // [rsp+E2h] [rbp-1Eh]
  int v23; // [rsp+E4h] [rbp-1Ch]
  PSID *v24; // [rsp+E8h] [rbp-18h]
  __int16 v25; // [rsp+F0h] [rbp-10h]
  char v26; // [rsp+F2h] [rbp-Eh]
  unsigned int v27; // [rsp+F4h] [rbp-Ch]
  PSID *v28; // [rsp+F8h] [rbp-8h]
  __int16 v29; // [rsp+100h] [rbp+0h]
  char v30; // [rsp+102h] [rbp+2h]
  int v31; // [rsp+104h] [rbp+4h]
  PSID *v32; // [rsp+108h] [rbp+8h]
  __int16 v33; // [rsp+110h] [rbp+10h]
  char v34; // [rsp+112h] [rbp+12h]
  int v35; // [rsp+114h] [rbp+14h]
  PSID *v36; // [rsp+118h] [rbp+18h]
  __int16 v37; // [rsp+120h] [rbp+20h]
  char v38; // [rsp+122h] [rbp+22h]
  unsigned int v39; // [rsp+124h] [rbp+24h]
  PSID *v40; // [rsp+128h] [rbp+28h]
  __int16 v41; // [rsp+130h] [rbp+30h]
  char v42; // [rsp+132h] [rbp+32h]
  unsigned int v43; // [rsp+134h] [rbp+34h]
  _QWORD *v44; // [rsp+138h] [rbp+38h]
  _BYTE v45[48]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v46[48]; // [rsp+170h] [rbp+70h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  Sid = 0;
  v27 = 0x80000000;
  v39 = 0x80000000;
  v19 = -536870912;
  v12[1] = L"lpacIdentityServices";
  v23 = -536870912;
  p_Sid = &Sid;
  v31 = 0x10000000;
  v24 = &v5;
  v35 = 0x10000000;
  v28 = &v6;
  v43 = 0x80000000;
  v32 = &v7;
  v5 = 0;
  v36 = &v8;
  v40 = &v9;
  v44 = &v10;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v6 = 0;
  v10 = 0;
  NewDescriptor = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v13.Value = 0;
  *(_WORD *)&v13.Value[4] = 1280;
  *(_DWORD *)v15.Value = 0;
  *(_WORD *)&v15.Value[4] = 768;
  *(_DWORD *)v16.Value = 0;
  *(_WORD *)&v16.Value[4] = 3840;
  v12[0] = 2752552;
  AceData = 0;
  v18 = 0;
  v21 = 1;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  v38 = 0;
  v41 = 0;
  v42 = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v2 >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(&v13, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v5);
    if ( v2 >= 0 )
    {
      v2 = RtlAllocateAndInitializeSid(&v13, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, &v6);
      if ( v2 >= 0 )
      {
        v2 = RtlAllocateAndInitializeSid(&v13, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7);
        if ( v2 >= 0 )
        {
          v2 = RtlAllocateAndInitializeSid(&v15, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v8);
          if ( v2 >= 0 )
          {
            v2 = RtlAllocateAndInitializeSid(&v16, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v9);
            if ( v2 >= 0 )
            {
              v2 = RtlDeriveCapabilitySidsFromName(v12, v46, v45);
              if ( v2 >= 0 )
              {
                v10 = v45;
                v2 = RtlCreateAndSetSD(&AceData, 7u, 0, 0, &NewDescriptor);
                if ( v2 >= 0 )
                  *a1 = NewDescriptor;
              }
            }
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
  if ( v9 )
    RtlFreeSid(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000235c  push    rbp
0x18000235e  push    rbx
0x18000235f  push    rsi
0x180002360  push    rdi
0x180002361  lea     rbp, [rsp-0B8h]
0x180002369  sub     rsp, 1B8h
0x180002370  mov     rax, cs:__security_cookie
0x180002377  xor     rax, rsp
0x18000237a  mov     [rbp+0D0h+var_30], rax
0x180002381  xor     esi, esi
0x180002383  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 100h
0x180002389  mov     edx, 80000000h
0x18000238e  mov     [rsp+1D0h+var_170], rsi
0x180002393  mov     rdi, rcx
0x180002396  mov     [rbp+0D0h+var_DC], edx
0x180002399  mov     ecx, 0E0000000h
0x18000239e  mov     [rbp+0D0h+var_AC], edx
0x1800023a1  mov     [rbp+0D0h+var_FC], ecx
0x1800023a4  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x1800023ab  mov     [rbp+0D0h+var_128], rax
0x1800023af  xor     r9d, r9d; SubAuthority1
0x1800023b2  mov     [rbp+0D0h+var_EC], ecx
0x1800023b5  lea     rax, [rsp+1D0h+var_170]
0x1800023ba  mov     [rbp+0D0h+var_F8], rax
0x1800023be  mov     ecx, 10000000h
0x1800023c3  lea     rax, [rsp+1D0h+var_168]
0x1800023c8  mov     [rbp+0D0h+var_CC], ecx
0x1800023cb  mov     [rbp+0D0h+var_E8], rax
0x1800023cf  xor     r8d, r8d; SubAuthority0
0x1800023d2  lea     rax, [rsp+1D0h+var_160]
0x1800023d7  mov     [rbp+0D0h+var_BC], ecx
0x1800023da  mov     [rbp+0D0h+var_D8], rax
0x1800023de  lea     rcx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x1800023e2  lea     rax, [rsp+1D0h+var_158]
0x1800023e7  mov     [rbp+0D0h+var_9C], edx
0x1800023ea  mov     [rbp+0D0h+var_C8], rax
0x1800023ee  mov     dl, 1; SubAuthorityCount
0x1800023f0  lea     rax, [rbp+0D0h+var_150]
0x1800023f4  mov     [rsp+1D0h+var_168], rsi
0x1800023f9  mov     [rbp+0D0h+var_B8], rax
0x1800023fd  lea     rax, [rbp+0D0h+var_148]
0x180002401  mov     [rbp+0D0h+var_A8], rax
0x180002405  lea     rax, [rbp+0D0h+var_140]
0x180002409  mov     [rbp+0D0h+var_98], rax
0x18000240d  lea     rax, [rsp+1D0h+var_170]
0x180002412  mov     [rsp+1D0h+Sid], rax; Sid
0x180002417  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x18000241b  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x18000241f  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x180002423  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x180002427  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x18000242b  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x18000242f  mov     [rsp+1D0h+var_158], rsi
0x180002434  mov     [rbp+0D0h+var_150], rsi
0x180002438  mov     [rbp+0D0h+var_148], rsi
0x18000243c  mov     [rsp+1D0h+var_160], rsi
0x180002441  mov     [rbp+0D0h+var_140], rsi
0x180002445  mov     [rbp+0D0h+NewDescriptor], rsi
0x180002449  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], esi
0x18000244c  mov     dword ptr [rbp+0D0h+var_120.Value], esi
0x18000244f  mov     word ptr [rbp+0D0h+var_120.Value+4], 500h
0x180002455  mov     dword ptr [rbp+0D0h+var_110.Value], esi
0x180002458  mov     word ptr [rbp+0D0h+var_110.Value+4], 300h
0x18000245e  mov     dword ptr [rbp+0D0h+var_108.Value], esi
0x180002461  mov     word ptr [rbp+0D0h+var_108.Value+4], 0F00h
0x180002467  mov     [rbp+0D0h+var_130], 2A0028h
0x18000246f  mov     [rbp+0D0h+AceData], si
0x180002473  mov     [rbp+0D0h+var_FE], sil
0x180002477  mov     [rbp+0D0h+var_F0], 1
0x18000247d  mov     [rbp+0D0h+var_EE], sil
0x180002481  mov     [rbp+0D0h+var_E0], si
0x180002485  mov     [rbp+0D0h+var_DE], sil
0x180002489  mov     [rbp+0D0h+var_D0], si
0x18000248d  mov     [rbp+0D0h+var_CE], sil
0x180002491  mov     [rbp+0D0h+var_C0], si
0x180002495  mov     [rbp+0D0h+var_BE], sil
0x180002499  mov     [rbp+0D0h+var_B0], si
0x18000249d  mov     [rbp+0D0h+var_AE], sil
0x1800024a1  mov     [rbp+0D0h+var_A0], si
0x1800024a5  mov     [rbp+0D0h+var_9E], sil
0x1800024a9  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800024b0  nop     dword ptr [rax+rax+00h]
0x1800024b5  mov     ebx, eax
0x1800024b7  test    eax, eax
0x1800024b9  js      loc_18000266C
0x1800024bf  lea     rax, [rsp+1D0h+var_168]
0x1800024c4  xor     r9d, r9d; SubAuthority1
0x1800024c7  mov     [rsp+1D0h+Sid], rax; Sid
0x1800024cc  lea     r8d, [rsi+0Ch]; SubAuthority0
0x1800024d0  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800024d4  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x1800024d8  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800024dc  mov     dl, 1; SubAuthorityCount
0x1800024de  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x1800024e2  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x1800024e6  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x1800024ea  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x1800024ee  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800024f5  nop     dword ptr [rax+rax+00h]
0x1800024fa  mov     ebx, eax
0x1800024fc  test    eax, eax
0x1800024fe  js      loc_18000266C
0x180002504  lea     rax, [rsp+1D0h+var_160]
0x180002509  xor     r9d, r9d; SubAuthority1
0x18000250c  mov     [rsp+1D0h+Sid], rax; Sid
0x180002511  lea     r8d, [rsi+7]; SubAuthority0
0x180002515  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x180002519  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x18000251d  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x180002521  mov     dl, 1; SubAuthorityCount
0x180002523  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x180002527  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x18000252b  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x18000252f  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x180002533  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000253a  nop     dword ptr [rax+rax+00h]
0x18000253f  mov     ebx, eax
0x180002541  test    eax, eax
0x180002543  js      loc_18000266C
0x180002549  lea     rax, [rsp+1D0h+var_158]
0x18000254e  mov     r9d, 220h; SubAuthority1
0x180002554  mov     [rsp+1D0h+Sid], rax; Sid
0x180002559  lea     r8d, [rsi+20h]; SubAuthority0
0x18000255d  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x180002561  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x180002565  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x180002569  mov     dl, 2; SubAuthorityCount
0x18000256b  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x18000256f  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x180002573  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x180002577  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x18000257b  call    cs:__imp_RtlAllocateAndInitializeSid
0x180002582  nop     dword ptr [rax+rax+00h]
0x180002587  mov     ebx, eax
0x180002589  test    eax, eax
0x18000258b  js      loc_18000266C
0x180002591  lea     rax, [rbp+0D0h+var_150]
0x180002595  xor     r9d, r9d; SubAuthority1
0x180002598  mov     [rsp+1D0h+Sid], rax; Sid
0x18000259d  lea     r8d, [rsi+4]; SubAuthority0
0x1800025a1  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800025a5  lea     rcx, [rbp+0D0h+var_110]; IdentifierAuthority
0x1800025a9  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800025ad  mov     dl, 1; SubAuthorityCount
0x1800025af  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x1800025b3  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x1800025b7  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x1800025bb  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x1800025bf  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800025c6  nop     dword ptr [rax+rax+00h]
0x1800025cb  mov     ebx, eax
0x1800025cd  test    eax, eax
0x1800025cf  js      loc_18000266C
0x1800025d5  lea     rax, [rbp+0D0h+var_148]
0x1800025d9  mov     [rsp+1D0h+Sid], rax; Sid
0x1800025de  lea     r8d, [rsi+2]; SubAuthority0
0x1800025e2  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800025e6  lea     r9d, [rsi+1]; SubAuthority1
0x1800025ea  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800025ee  lea     rcx, [rbp+0D0h+var_108]; IdentifierAuthority
0x1800025f2  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x1800025f6  mov     dl, r8b; SubAuthorityCount
0x1800025f9  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x1800025fd  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x180002601  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x180002605  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000260c  nop     dword ptr [rax+rax+00h]
0x180002611  mov     ebx, eax
0x180002613  test    eax, eax
0x180002615  js      short loc_18000266C
0x180002617  lea     r8, [rbp+0D0h+var_90]
0x18000261b  lea     rdx, [rbp+0D0h+var_60]
0x18000261f  lea     rcx, [rbp+0D0h+var_130]
0x180002623  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18000262a  nop     dword ptr [rax+rax+00h]
0x18000262f  mov     ebx, eax
0x180002631  test    eax, eax
0x180002633  js      short loc_18000266C
0x180002635  lea     rax, [rbp+0D0h+var_90]
0x180002639  xor     r9d, r9d; GroupSid
0x18000263c  mov     [rbp+0D0h+var_140], rax
0x180002640  lea     edx, [rsi+7]; AceCount
0x180002643  lea     rax, [rbp+0D0h+NewDescriptor]
0x180002647  xor     r8d, r8d; OwnerSid
0x18000264a  lea     rcx, [rbp+0D0h+AceData]; AceData
0x18000264e  mov     qword ptr [rsp+1D0h+SubAuthority2], rax; NewDescriptor
0x180002653  call    cs:__imp_RtlCreateAndSetSD
0x18000265a  nop     dword ptr [rax+rax+00h]
0x18000265f  mov     ebx, eax
0x180002661  test    eax, eax
0x180002663  js      short loc_18000266C
0x180002665  mov     rax, [rbp+0D0h+NewDescriptor]
0x180002669  mov     [rdi], rax
0x18000266c  mov     rcx, [rsp+1D0h+var_170]; Sid
0x180002671  test    rcx, rcx
0x180002674  jz      short loc_180002682
0x180002676  call    cs:__imp_RtlFreeSid
0x18000267d  nop     dword ptr [rax+rax+00h]
0x180002682  mov     rcx, [rsp+1D0h+var_168]; Sid
0x180002687  test    rcx, rcx
0x18000268a  jz      short loc_180002698
0x18000268c  call    cs:__imp_RtlFreeSid
0x180002693  nop     dword ptr [rax+rax+00h]
0x180002698  mov     rcx, [rsp+1D0h+var_160]; Sid
0x18000269d  test    rcx, rcx
0x1800026a0  jz      short loc_1800026AE
0x1800026a2  call    cs:__imp_RtlFreeSid
0x1800026a9  nop     dword ptr [rax+rax+00h]
0x1800026ae  mov     rcx, [rsp+1D0h+var_158]; Sid
0x1800026b3  test    rcx, rcx
0x1800026b6  jz      short loc_1800026C4
0x1800026b8  call    cs:__imp_RtlFreeSid
0x1800026bf  nop     dword ptr [rax+rax+00h]
0x1800026c4  mov     rcx, [rbp+0D0h+var_150]; Sid
0x1800026c8  test    rcx, rcx
0x1800026cb  jz      short loc_1800026D9
0x1800026cd  call    cs:__imp_RtlFreeSid
0x1800026d4  nop     dword ptr [rax+rax+00h]
0x1800026d9  mov     rcx, [rbp+0D0h+var_148]; Sid
0x1800026dd  test    rcx, rcx
0x1800026e0  jz      short loc_1800026EE
0x1800026e2  call    cs:__imp_RtlFreeSid
0x1800026e9  nop     dword ptr [rax+rax+00h]
0x1800026ee  mov     eax, ebx
0x1800026f0  mov     rcx, [rbp+0D0h+var_30]
0x1800026f7  xor     rcx, rsp; StackCookie
0x1800026fa  call    __security_check_cookie
0x1800026ff  add     rsp, 1B8h
0x180002706  pop     rdi
0x180002707  pop     rsi
0x180002708  pop     rbx
0x180002709  pop     rbp
0x18000270a  retn
```
