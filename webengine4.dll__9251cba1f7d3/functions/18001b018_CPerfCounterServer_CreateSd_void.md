# CPerfCounterServer::CreateSd(void * *)

- ea: `0x18001b018`
- end: `0x18001b226`
- name: `?CreateSd@CPerfCounterServer@@AEAAJPEAPEAX@Z`
- size: `526`
- prototype: `__int64 __fastcall(CPerfCounterServer *this, struct _ACL **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001be18`

## callees

- `0x18001b018`
- `0x18001b380`
- `0x18001c550`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004eaa8`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x18001b193`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001b193`
- `ADVAPI32!GetLengthSid` at `0x18001b11c`
- `ADVAPI32!GetLengthSid` at `0x18001b11c`
- `ADVAPI32!InitializeAcl` at `0x18001b162`
- `ADVAPI32!InitializeAcl` at `0x18001b162`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001b1ac`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001b1ac`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001b1c3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001b1c3`

## string_xrefs

- `0x18001b0a9`: `NT SERVICE\RemoteRegistry`
- `0x18001b0b4`: `ProcessIdentity`

## pseudocode

```c
__int64 __fastcall CPerfCounterServer::CreateSd(CPerfCounterServer *this, struct _ACL **a2)
{
  struct _ACL *v3; // rdi
  signed int v4; // r15d
  unsigned __int8 v5; // si
  __int64 v6; // r12
  void **v7; // r14
  int PrincipalSID; // eax
  unsigned int LastWin32Error; // ebx
  struct _ACL *v10; // rax
  struct _ACL *v11; // rsi
  unsigned __int8 v12; // bl
  PSID v13; // r9
  void **v14; // rsi
  unsigned __int16 *v16; // [rsp+28h] [rbp-69h]
  DWORD AccessMask; // [rsp+30h] [rbp-61h]
  PSID pSid[2]; // [rsp+38h] [rbp-59h] BYREF
  int v19; // [rsp+48h] [rbp-49h]
  __int64 v20; // [rsp+50h] [rbp-41h]
  const unsigned __int16 *v21; // [rsp+58h] [rbp-39h]
  int v22; // [rsp+60h] [rbp-31h]
  __int64 v23; // [rsp+68h] [rbp-29h]
  const wchar_t *v24; // [rsp+70h] [rbp-21h]
  int v25; // [rsp+78h] [rbp-19h]
  __int64 v26; // [rsp+80h] [rbp-11h]
  const wchar_t *v27; // [rsp+88h] [rbp-9h]
  int v28; // [rsp+90h] [rbp-1h]
  __int64 v29; // [rsp+98h] [rbp+7h]
  const wchar_t *v30; // [rsp+A0h] [rbp+Fh]
  int v31; // [rsp+A8h] [rbp+17h]
  __int64 v32; // [rsp+B0h] [rbp+1Fh]

  pSid[0] = 0;
  v20 = 0;
  v23 = 0;
  v26 = 0;
  v29 = 0;
  v3 = 0;
  v32 = 0;
  v16 = L"system";
  pSid[1] = (PSID)L"administrators";
  v21 = L"Performance Log Users";
  v4 = 8;
  AccessMask = 0x10000000;
  v24 = L"Performance Monitor Users";
  v27 = L"NT SERVICE\\RemoteRegistry";
  v30 = L"ProcessIdentity";
  v19 = 0x10000000;
  v22 = 1245631;
  v25 = 1245631;
  v28 = 1245631;
  v31 = 0x10000000;
  IsVista();
  v5 = 0;
  v6 = 6;
  do
  {
    v7 = &pSid[3 * v5];
    if ( v5 == 5 )
    {
      GetSidForProcessIdentity(v7);
    }
    else
    {
      PrincipalSID = GetPrincipalSID((&v16)[3 * v5], &pSid[3 * v5]);
      LastWin32Error = PrincipalSID;
      if ( v5 != 4 && PrincipalSID )
        goto LABEL_21;
    }
    if ( *v7 )
      v4 += GetLengthSid(*v7) + 8;
    ++v5;
  }
  while ( v5 < 6u );
  v10 = (struct _ACL *)MemAlloc(v4 + 40LL);
  v3 = v10;
  if ( v10 )
  {
    v11 = v10 + 5;
    if ( InitializeAcl(v10 + 5, v4, 2u) )
    {
      v12 = 0;
      while ( 1 )
      {
        v13 = pSid[3 * v12];
        if ( v13 )
        {
          if ( !AddAccessAllowedAce(v11, 2u, (DWORD)pSid[3 * v12], v13) )
            break;
        }
        if ( ++v12 >= 6u )
        {
          if ( InitializeSecurityDescriptor(v3, 1u) && SetSecurityDescriptorDacl(v3, 1, v11, 0) )
          {
            *a2 = v3;
            v3 = 0;
            LastWin32Error = 0;
            goto LABEL_21;
          }
          break;
        }
      }
    }
    LastWin32Error = GetLastWin32Error();
  }
  else
  {
    LastWin32Error = -2147024882;
  }
LABEL_21:
  v14 = pSid;
  do
  {
    MemFree(*v14);
    *v14 = 0;
    v14 += 3;
    --v6;
  }
  while ( v6 );
  MemFree(v3);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18001b018  mov     rax, rsp
0x18001b01b  mov     [rax+8], rbx
0x18001b01f  mov     [rax+18h], rsi
0x18001b023  mov     [rax+20h], rdi
0x18001b027  push    rbp
0x18001b028  push    r12
0x18001b02a  push    r13
0x18001b02c  push    r14
0x18001b02e  push    r15
0x18001b030  lea     rbp, [rax-5Fh]
0x18001b034  sub     rsp, 0C0h
0x18001b03b  mov     rax, cs:__security_cookie
0x18001b042  xor     rax, rsp
0x18001b045  mov     [rbp+57h+var_30], rax
0x18001b049  and     [rbp+57h+pSid], 0
0x18001b04e  lea     rax, aSystem_0; "system"
0x18001b055  and     [rbp+57h+var_98], 0
0x18001b05a  mov     ecx, 1301BFh
0x18001b05f  and     [rbp+57h+var_80], 0
0x18001b064  mov     r13, rdx
0x18001b067  and     [rbp+57h+var_68], 0
0x18001b06c  mov     edx, 10000000h
0x18001b071  and     [rbp+57h+var_50], 0
0x18001b076  xor     edi, edi
0x18001b078  and     [rbp+57h+var_38], 0
0x18001b07d  mov     [rbp+57h+var_C0], rax
0x18001b081  lea     rax, aAdministrators; "administrators"
0x18001b088  mov     [rbp+57h+var_A8], rax
0x18001b08c  lea     rax, aPerformanceLog; "Performance Log Users"
0x18001b093  mov     [rbp+57h+var_90], rax
0x18001b097  lea     r15d, [rdi+8]
0x18001b09b  lea     rax, aPerformanceMon; "Performance Monitor Users"
0x18001b0a2  mov     [rbp+57h+AccessMask], edx
0x18001b0a5  mov     [rbp+57h+var_78], rax
0x18001b0a9  lea     rax, aNtServiceRemot; "NT SERVICE\\RemoteRegistry"
0x18001b0b0  mov     [rbp+57h+var_60], rax
0x18001b0b4  lea     rax, aProcessidentit; "ProcessIdentity"
0x18001b0bb  mov     [rbp+57h+var_48], rax
0x18001b0bf  mov     [rbp+57h+var_A0], edx
0x18001b0c2  mov     [rbp+57h+var_88], ecx
0x18001b0c5  mov     [rbp+57h+var_70], ecx
0x18001b0c8  mov     [rbp+57h+var_58], ecx
0x18001b0cb  mov     [rbp+57h+var_40], edx
0x18001b0ce  call    ?IsVista@@YAHXZ; IsVista(void)
0x18001b0d3  xor     sil, sil
0x18001b0d6  lea     r12d, [rdi+6]
0x18001b0da  movzx   eax, sil
0x18001b0de  lea     rcx, [rax+rax*2]
0x18001b0e2  lea     r14, [rbp+rcx*8+57h+pSid]
0x18001b0e7  cmp     sil, 5
0x18001b0eb  jz      short loc_18001B10C
0x18001b0ed  mov     rcx, [rbp+rcx*8+57h+var_C0]; unsigned __int16 *
0x18001b0f2  mov     rdx, r14; void **
0x18001b0f5  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x18001b0fa  mov     ebx, eax
0x18001b0fc  cmp     sil, 4
0x18001b100  jz      short loc_18001B114
0x18001b102  test    eax, eax
0x18001b104  jnz     loc_18001B1D5
0x18001b10a  jmp     short loc_18001B114
0x18001b10c  mov     rcx, r14; void **
0x18001b10f  call    ?GetSidForProcessIdentity@@YAJPEAPEAX@Z; GetSidForProcessIdentity(void * *)
0x18001b114  mov     rcx, [r14]; pSid
0x18001b117  test    rcx, rcx
0x18001b11a  jz      short loc_18001B129
0x18001b11c  call    cs:__imp_GetLengthSid
0x18001b122  add     r15d, 8
0x18001b126  add     r15d, eax
0x18001b129  inc     sil
0x18001b12c  cmp     sil, r12b
0x18001b12f  jb      short loc_18001B0DA
0x18001b131  movsxd  rcx, r15d
0x18001b134  add     rcx, 28h ; '('; unsigned __int64
0x18001b138  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001b13d  mov     rdi, rax
0x18001b140  test    rax, rax
0x18001b143  jnz     short loc_18001B14F
0x18001b145  mov     ebx, 8007000Eh
0x18001b14a  jmp     loc_18001B1D5
0x18001b14f  lea     rsi, [rax+28h]
0x18001b153  mov     r14d, 2
0x18001b159  mov     r8d, r14d; dwAclRevision
0x18001b15c  mov     rcx, rsi; pAcl
0x18001b15f  mov     edx, r15d; nAclLength
0x18001b162  call    cs:__imp_InitializeAcl
0x18001b168  test    eax, eax
0x18001b16a  jnz     short loc_18001B175
0x18001b16c  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001b171  mov     ebx, eax
0x18001b173  jmp     short loc_18001B1D5
0x18001b175  xor     bl, bl
0x18001b177  movzx   eax, bl
0x18001b17a  lea     rcx, [rax+rax*2]
0x18001b17e  mov     r9, [rbp+rcx*8+57h+pSid]; pSid
0x18001b183  test    r9, r9
0x18001b186  jz      short loc_18001B19D
0x18001b188  mov     r8d, [rbp+rcx*8+57h+AccessMask]; AccessMask
0x18001b18d  mov     edx, r14d; dwAceRevision
0x18001b190  mov     rcx, rsi; pAcl
0x18001b193  call    cs:__imp_AddAccessAllowedAce
0x18001b199  test    eax, eax
0x18001b19b  jz      short loc_18001B16C
0x18001b19d  inc     bl
0x18001b19f  cmp     bl, r12b
0x18001b1a2  jb      short loc_18001B177
0x18001b1a4  mov     edx, 1; dwRevision
0x18001b1a9  mov     rcx, rdi; pSecurityDescriptor
0x18001b1ac  call    cs:__imp_InitializeSecurityDescriptor
0x18001b1b2  test    eax, eax
0x18001b1b4  jz      short loc_18001B16C
0x18001b1b6  xor     r9d, r9d; bDaclDefaulted
0x18001b1b9  mov     r8, rsi; pDacl
0x18001b1bc  mov     rcx, rdi; pSecurityDescriptor
0x18001b1bf  lea     edx, [r9+1]; bDaclPresent
0x18001b1c3  call    cs:__imp_SetSecurityDescriptorDacl
0x18001b1c9  test    eax, eax
0x18001b1cb  jz      short loc_18001B16C
0x18001b1cd  mov     [r13+0], rdi
0x18001b1d1  xor     edi, edi
0x18001b1d3  xor     ebx, ebx
0x18001b1d5  lea     rsi, [rbp+57h+pSid]
0x18001b1d9  mov     rcx, [rsi]; lpMem
0x18001b1dc  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b1e1  and     qword ptr [rsi], 0
0x18001b1e5  lea     rsi, [rsi+18h]
0x18001b1e9  sub     r12, 1
0x18001b1ed  jnz     short loc_18001B1D9
0x18001b1ef  mov     rcx, rdi; lpMem
0x18001b1f2  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b1f7  mov     eax, ebx
0x18001b1f9  mov     rcx, [rbp+57h+var_30]
0x18001b1fd  xor     rcx, rsp; StackCookie
0x18001b200  call    __security_check_cookie
0x18001b205  lea     r11, [rsp+0E0h+var_20]
0x18001b20d  mov     rbx, [r11+30h]
0x18001b211  mov     rsi, [r11+40h]
0x18001b215  mov     rdi, [r11+48h]
0x18001b219  mov     rsp, r11
0x18001b21c  pop     r15
0x18001b21e  pop     r14
0x18001b220  pop     r13
0x18001b222  pop     r12
0x18001b224  pop     rbp
0x18001b225  retn
```
