# CreatePerfCounterSd(void * *)

- ea: `0x180037f54`
- end: `0x180038250`
- name: `?CreatePerfCounterSd@@YAJPEAPEAX@Z`
- size: `764`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800382f0`

## callees

- `0x180024468`
- `0x180037f54`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004eaa8`
- `0x18004ef84`
- `0x1800653c0`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x1800381a9`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800381a9`
- `ADVAPI32!GetLengthSid` at `0x180038125`
- `ADVAPI32!GetLengthSid` at `0x180038125`
- `ADVAPI32!InitializeAcl` at `0x180038178`
- `ADVAPI32!InitializeAcl` at `0x180038178`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800381ca`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800381ca`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800381e1`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800381e1`

## string_xrefs

- `0x180038005`: `NetworkService`
- `0x180037ffa`: `LocalService`

## pseudocode

```c
__int64 __fastcall CreatePerfCounterSd(void **a1)
{
  unsigned int PrincipalSID; // edi
  struct _ACL *v2; // r14
  signed int v3; // r13d
  int v4; // esi
  __int64 v5; // r15
  unsigned int LastWin32Error; // ebx
  struct _ACL *v7; // rax
  struct _ACL *v8; // r12
  int v9; // esi
  DWORD *v10; // r15
  PSID *v11; // rdi
  void **v12; // rdi
  __int64 v13; // rsi
  int v15[2]; // [rsp+38h] [rbp-D0h] BYREF
  void **v16; // [rsp+40h] [rbp-C8h]
  _DWORD v17[6]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 v18; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v19[8]; // [rsp+68h] [rbp-A0h]
  PSID pSid[3]; // [rsp+A8h] [rbp-60h] BYREF
  void *v21; // [rsp+C0h] [rbp-48h] BYREF
  void *v22; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 v23[256]; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int16 v24[256]; // [rsp+2E8h] [rbp+1E0h] BYREF

  v16 = a1;
  v19[0] = L"administrators";
  v17[2] = 0x80000000;
  v19[1] = L"system";
  PrincipalSID = 0;
  v17[3] = 0x80000000;
  v19[2] = L"power users";
  v18 = 0xC000000080000000uLL;
  v19[3] = L"authenticated users";
  v2 = 0;
  v19[4] = L"IIS_WPG";
  v19[5] = L"IIS_IUSRS";
  v3 = 8;
  v19[6] = L"LocalService";
  v19[7] = L"NetworkService";
  v17[0] = 0x10000000;
  v17[1] = 0x10000000;
  v17[4] = -1073741824;
  v17[5] = -1073741824;
  memset_0(pSid, 0, 0x40u);
  v4 = 0;
  v5 = 0;
  do
  {
    if ( v4 == 3 )
      PrincipalSID = GetPrincipalSID((char *)L"Performance Log Users", &v21);
    if ( !PrincipalSID && v4 == 3 )
    {
LABEL_15:
      v3 += GetLengthSid(pSid[v5]) + 8;
      goto LABEL_17;
    }
    PrincipalSID = GetPrincipalSID((char *)v19[v5], &pSid[v4]);
    if ( PrincipalSID && v4 == 6 )
    {
      v15[0] = 0;
      IsDomainController(v15);
      if ( !v15[0] )
        goto LABEL_16;
      memset_0(v23, 0, sizeof(v23));
      memset_0(v24, 0, sizeof(v24));
      v15[1] = 0;
      PrincipalSID = CRegAccount::GetMachineAccountCredentialsOnDC(v23, 0x100u, v24, 0x100u, &v15[1]);
      if ( PrincipalSID )
        goto LABEL_16;
      PrincipalSID = GetPrincipalSID((char *)v23, &v22);
    }
    else if ( v4 < 4 )
    {
      LastWin32Error = PrincipalSID;
      if ( v4 != 2 )
      {
        if ( PrincipalSID )
          goto LABEL_29;
      }
    }
    if ( !PrincipalSID )
      goto LABEL_15;
LABEL_16:
    pSid[v5] = 0;
LABEL_17:
    ++v4;
    ++v5;
  }
  while ( v4 < 8 );
  LastWin32Error = 0;
  v7 = (struct _ACL *)MemAlloc(v3 + 40LL);
  v2 = v7;
  if ( v7 )
  {
    v8 = v7 + 5;
    if ( InitializeAcl(v7 + 5, v3, 2u) )
    {
      v9 = 0;
      v10 = v17;
      v11 = pSid;
      while ( !*v11 || AddAccessAllowedAce(v8, 2u, *v10, *v11) )
      {
        ++v9;
        ++v11;
        ++v10;
        if ( v9 >= 8 )
        {
          if ( InitializeSecurityDescriptor(v2, 1u) && SetSecurityDescriptorDacl(v2, 1, v8, 0) )
          {
            *v16 = v2;
            v2 = 0;
            goto LABEL_29;
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
LABEL_29:
  v12 = pSid;
  v13 = 8;
  do
  {
    if ( *v12 )
      MemFree(*v12);
    ++v12;
    --v13;
  }
  while ( v13 );
  MemFree(v2);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180037f54  mov     rax, rsp
0x180037f57  mov     [rax+10h], rbx
0x180037f5b  mov     [rax+18h], rsi
0x180037f5f  mov     [rax+20h], rdi
0x180037f63  push    rbp
0x180037f64  push    r12
0x180037f66  push    r13
0x180037f68  push    r14
0x180037f6a  push    r15
0x180037f6c  lea     rbp, [rax-418h]
0x180037f73  sub     rsp, 4F0h
0x180037f7a  mov     rax, cs:__security_cookie
0x180037f81  xor     rax, rsp
0x180037f84  mov     [rbp+410h+var_30], rax
0x180037f8b  mov     [rsp+510h+var_4D8], rcx
0x180037f90  lea     rax, aAdministrators
0x180037f97  mov     [rsp+510h+var_4B0], rax
0x180037f9c  mov     ecx, 80000000h
0x180037fa1  lea     rax, aSystem_0
0x180037fa8  mov     [rsp+510h+var_4C8], ecx
0x180037fac  mov     [rsp+510h+var_4A8], rax
0x180037fb1  xor     edi, edi
0x180037fb3  lea     rax, aPowerUsers
0x180037fba  mov     [rsp+510h+var_4C4], ecx
0x180037fbe  mov     [rsp+510h+var_4A0], rax
0x180037fc3  xor     edx, edx; Val
0x180037fc5  lea     rax, aAuthenticatedU
0x180037fcc  mov     dword ptr [rsp+510h+var_4B8], ecx
0x180037fd0  mov     [rsp+510h+var_498], rax
0x180037fd5  lea     r8d, [rdi+40h]; Size
0x180037fd9  lea     rax, aIisWpg
0x180037fe0  xor     r14d, r14d
0x180037fe3  mov     [rbp+410h+var_490], rax
0x180037fe7  lea     rcx, [rbp+410h+pSid]; void *
0x180037feb  lea     rax, aIisIusrs_0
0x180037ff2  mov     [rbp+410h+var_488], rax
0x180037ff6  lea     r13d, [rdi+8]
0x180037ffa  lea     rax, aLocalservice
0x180038001  mov     [rbp+410h+var_480], rax
0x180038005  lea     rax, aNetworkservice
0x18003800c  mov     [rbp+410h+var_478], rax
0x180038010  mov     eax, 10000000h
0x180038015  mov     [rsp+510h+var_4D0], eax
0x180038019  mov     [rsp+510h+var_4CC], eax
0x18003801d  mov     eax, 0C0000000h
0x180038022  mov     [rsp+510h+var_4C0], eax
0x180038026  mov     [rsp+510h+var_4BC], eax
0x18003802a  mov     dword ptr [rsp+510h+var_4B8+4], eax
0x18003802e  call    memset_0
0x180038033  xor     esi, esi
0x180038035  xor     r15d, r15d
0x180038038  cmp     esi, 3
0x18003803b  jnz     short loc_18003804F
0x18003803d  lea     rdx, [rbp+410h+var_458]; void **
0x180038041  lea     rcx, aPerformanceLog
0x180038048  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z
0x18003804d  mov     edi, eax
0x18003804f  test    edi, edi
0x180038051  jnz     short loc_18003805C
0x180038053  cmp     esi, 3
0x180038056  jz      loc_180038120
0x18003805c  mov     rcx, [rsp+r15+510h+var_4B0]; unsigned __int16 *
0x180038061  lea     rdx, [rbp+410h+pSid]
0x180038065  movsxd  r12, esi
0x180038068  lea     rdx, [rdx+r12*8]; void **
0x18003806c  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z
0x180038071  mov     ebx, eax
0x180038073  mov     edi, eax
0x180038075  test    eax, eax
0x180038077  jz      loc_180038108
0x18003807d  cmp     esi, 6
0x180038080  jnz     loc_180038108
0x180038086  and     [rsp+510h+var_4E0], r14d
0x18003808b  lea     rcx, [rsp+510h+var_4E0]; int *
0x180038090  call    ?IsDomainController@@YAJPEAH@Z
0x180038095  cmp     [rsp+510h+var_4E0], r14d
0x18003809a  jz      loc_180038134
0x1800380a0  mov     ebx, 200h
0x1800380a5  lea     rcx, [rbp+410h+var_430]; void *
0x1800380a9  mov     r8d, ebx; Size
0x1800380ac  xor     edx, edx; Val
0x1800380ae  call    memset_0
0x1800380b3  mov     r8d, ebx; Size
0x1800380b6  lea     rcx, [rbp+410h+var_230]; void *
0x1800380bd  xor     edx, edx; Val
0x1800380bf  call    memset_0
0x1800380c4  and     [rsp+510h+var_4E0+4], r14d
0x1800380c9  lea     rax, [rsp+510h+var_4E0+4]
0x1800380ce  mov     ebx, 100h
0x1800380d3  mov     [rsp+510h+var_4F0], rax; int *
0x1800380d8  mov     r9d, ebx; unsigned int
0x1800380db  lea     r8, [rbp+410h+var_230]; unsigned __int16 *
0x1800380e2  mov     edx, ebx; unsigned int
0x1800380e4  lea     rcx, [rbp+410h+var_430]; unsigned __int16 *
0x1800380e8  call    ?GetMachineAccountCredentialsOnDC@CRegAccount@@SAJPEAGK0KPEAH@Z
0x1800380ed  mov     edi, eax
0x1800380ef  test    eax, eax
0x1800380f1  jnz     short loc_180038134
0x1800380f3  lea     rdx, [rbp+410h+pSid]
0x1800380f7  lea     rdx, [rdx+r12*8]; void **
0x1800380fb  lea     rcx, [rbp+410h+var_430]; unsigned __int16 *
0x1800380ff  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z
0x180038104  mov     edi, eax
0x180038106  jmp     short loc_18003811C
0x180038108  cmp     esi, 4
0x18003810b  jge     short loc_18003811C
0x18003810d  mov     ebx, edi
0x18003810f  cmp     esi, 2
0x180038112  jz      short loc_18003811C
0x180038114  test    ebx, ebx
0x180038116  jnz     loc_1800381F6
0x18003811c  test    edi, edi
0x18003811e  jnz     short loc_180038134
0x180038120  mov     rcx, [rbp+r15+410h+pSid]; pSid
0x180038125  call    cs:__imp_GetLengthSid
0x18003812b  add     r13d, 8
0x18003812f  add     r13d, eax
0x180038132  jmp     short loc_180038139
0x180038134  and     [rbp+r15+410h+pSid], r14
0x180038139  inc     esi
0x18003813b  add     r15, 8
0x18003813f  cmp     esi, 8
0x180038142  jl      loc_180038038
0x180038148  movsxd  rcx, r13d
0x18003814b  xor     ebx, ebx
0x18003814d  add     rcx, 28h ; '('; unsigned __int64
0x180038151  call    ?MemAlloc@@YAPEAX_K@Z
0x180038156  mov     r14, rax
0x180038159  test    rax, rax
0x18003815c  jnz     short loc_180038168
0x18003815e  mov     ebx, 8007000Eh
0x180038163  jmp     loc_1800381F6
0x180038168  lea     r12, [rax+28h]
0x18003816c  mov     r8d, 2; dwAclRevision
0x180038172  mov     rcx, r12; pAcl
0x180038175  mov     edx, r13d; nAclLength
0x180038178  call    cs:__imp_InitializeAcl
0x18003817e  test    eax, eax
0x180038180  jnz     short loc_18003818B
0x180038182  call    ?GetLastWin32Error@@YAJXZ
0x180038187  mov     ebx, eax
0x180038189  jmp     short loc_1800381F6
0x18003818b  xor     esi, esi
0x18003818d  lea     r15, [rsp+510h+var_4D0]
0x180038192  lea     rdi, [rbp+410h+pSid]
0x180038196  mov     r9, [rdi]; pSid
0x180038199  test    r9, r9
0x18003819c  jz      short loc_1800381B3
0x18003819e  mov     r8d, [r15]; AccessMask
0x1800381a1  mov     edx, 2; dwAceRevision
0x1800381a6  mov     rcx, r12; pAcl
0x1800381a9  call    cs:__imp_AddAccessAllowedAce
0x1800381af  test    eax, eax
0x1800381b1  jz      short loc_180038182
0x1800381b3  inc     esi
0x1800381b5  add     rdi, 8
0x1800381b9  add     r15, 4
0x1800381bd  cmp     esi, 8
0x1800381c0  jl      short loc_180038196
0x1800381c2  mov     edx, 1; dwRevision
0x1800381c7  mov     rcx, r14; pSecurityDescriptor
0x1800381ca  call    cs:__imp_InitializeSecurityDescriptor
0x1800381d0  test    eax, eax
0x1800381d2  jz      short loc_180038182
0x1800381d4  xor     r9d, r9d; bDaclDefaulted
0x1800381d7  mov     r8, r12; pDacl
0x1800381da  mov     rcx, r14; pSecurityDescriptor
0x1800381dd  lea     edx, [r9+1]; bDaclPresent
0x1800381e1  call    cs:__imp_SetSecurityDescriptorDacl
0x1800381e7  test    eax, eax
0x1800381e9  jz      short loc_180038182
0x1800381eb  mov     rax, [rsp+510h+var_4D8]
0x1800381f0  mov     [rax], r14
0x1800381f3  xor     r14d, r14d
0x1800381f6  lea     rdi, [rbp+410h+pSid]
0x1800381fa  mov     esi, 8
0x1800381ff  mov     rcx, [rdi]; lpMem
0x180038202  test    rcx, rcx
0x180038205  jz      short loc_18003820C
0x180038207  call    ?MemFree@@YAXPEAX@Z
0x18003820c  add     rdi, 8
0x180038210  sub     rsi, 1
0x180038214  jnz     short loc_1800381FF
0x180038216  mov     rcx, r14; lpMem
0x180038219  call    ?MemFree@@YAXPEAX@Z
0x18003821e  mov     eax, ebx
0x180038220  mov     rcx, [rbp+410h+var_30]
0x180038227  xor     rcx, rsp; StackCookie
0x18003822a  call    __security_check_cookie
0x18003822f  lea     r11, [rsp+510h+var_20]
0x180038237  mov     rbx, [r11+38h]
0x18003823b  mov     rsi, [r11+40h]
0x18003823f  mov     rdi, [r11+48h]
0x180038243  mov     rsp, r11
0x180038246  pop     r15
0x180038248  pop     r14
0x18003824a  pop     r13
0x18003824c  pop     r12
0x18003824e  pop     rbp
0x18003824f  retn
```
