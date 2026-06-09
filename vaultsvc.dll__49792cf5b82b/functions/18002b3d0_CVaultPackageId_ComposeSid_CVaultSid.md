# CVaultPackageId::ComposeSid(CVaultSid * *)

- ea: `0x18002b3d0`
- end: `0x18002b5d6`
- name: `?ComposeSid@CVaultPackageId@@QEAAKPEAPEAVCVaultSid@@@Z`
- size: `518`
- prototype: `unsigned int __fastcall(PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, struct CVaultSid **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003ca4`
- `0x180006680`

## callees

- `0x18002b3d0`
- `0x18002b5dc`
- `0x18002b6f0`
- `0x18003a580`
- `0x18003b7d8`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b4dd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b4dd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b50f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b524`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b50f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b553`

## pseudocode

```c
__int64 __fastcall CVaultPackageId::ComposeSid(PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, struct CVaultSid **a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  unsigned int v6; // esi
  unsigned int v7; // eax
  PSID v8; // rcx
  unsigned int v9; // ebx
  unsigned int VaultSid; // eax
  _QWORD *v11; // rcx
  DWORD LastError; // eax
  DWORD v13; // ebx
  __int64 v14; // rdx
  PSID pSourceSid; // [rsp+60h] [rbp-38h] BYREF
  DWORD nSubAuthority0[4]; // [rsp+68h] [rbp-30h] BYREF
  DWORD nSubAuthority4[4]; // [rsp+78h] [rbp-20h]

  result = *(unsigned int *)&pIdentifierAuthority[6].Value[4];
  if ( !(_DWORD)result )
  {
    *a2 = 0;
    return result;
  }
  if ( (unsigned int)result < 7 || (v5 = (unsigned int)(result - 7), (v5 & 3) != 0) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 87;
    v14 = 45;
    goto LABEL_26;
  }
  v6 = pIdentifierAuthority[1].Value[0];
  if ( v5 < 4 * (unsigned __int64)pIdentifierAuthority[1].Value[0] || (unsigned __int8)v6 > 8u )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 87;
    v14 = 46;
LABEL_26:
    WPP_SF_d(v11[2], v14, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 87);
    return 87;
  }
  *(_OWORD *)nSubAuthority0 = 0;
  *(_OWORD *)nSubAuthority4 = 0;
  if ( v6 )
    memcpy_0(nSubAuthority0, &pIdentifierAuthority[1].Value[1], 4LL * v6);
  pSourceSid = 0;
  if ( AllocateAndInitializeSid(
         pIdentifierAuthority,
         v6,
         nSubAuthority0[0],
         nSubAuthority0[1],
         nSubAuthority0[2],
         nSubAuthority0[3],
         nSubAuthority4[0],
         nSubAuthority4[1],
         nSubAuthority4[2],
         nSubAuthority4[3],
         &pSourceSid) )
  {
    v7 = VaultValidatePackageSid(pSourceSid);
    v8 = pSourceSid;
    v9 = v7;
    if ( v7 || (VaultSid = CVaultSid::CreateVaultSid(pSourceSid, a2), v8 = pSourceSid, (v9 = VaultSid) != 0) )
    {
      FreeSid(v8);
      return v9;
    }
    else
    {
      FreeSid(pSourceSid);
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, LastError);
    return v13;
  }
}

```

## disassembly

```asm
0x18002b3d0  mov     [rsp+arg_18], rbx
0x18002b3d5  push    rdi
0x18002b3d6  sub     rsp, 90h
0x18002b3dd  mov     rax, cs:__security_cookie
0x18002b3e4  xor     rax, rsp
0x18002b3e7  mov     [rsp+98h+var_10], rax
0x18002b3ef  mov     eax, [rcx+28h]
0x18002b3f2  mov     rdi, rdx
0x18002b3f5  mov     rbx, rcx
0x18002b3f8  test    eax, eax
0x18002b3fa  jnz     short loc_18002B424
0x18002b3fc  mov     qword ptr [rdx], 0
0x18002b403  mov     rcx, [rsp+98h+var_10]
0x18002b40b  xor     rcx, rsp; StackCookie
0x18002b40e  call    __security_check_cookie
0x18002b413  mov     rbx, [rsp+98h+arg_18]
0x18002b41b  add     rsp, 90h
0x18002b422  pop     rdi
0x18002b423  retn
0x18002b424  mov     [rsp+98h+arg_10], rsi
0x18002b42c  cmp     eax, 7
0x18002b42f  jb      loc_18002B539
0x18002b435  add     eax, 0FFFFFFF9h
0x18002b438  test    al, 3
0x18002b43a  jnz     loc_18002B539
0x18002b440  movzx   esi, byte ptr [rcx+6]
0x18002b444  mov     ecx, esi
0x18002b446  shl     rcx, 2
0x18002b44a  cmp     rax, rcx
0x18002b44d  jb      loc_18002B590
0x18002b453  cmp     sil, 8
0x18002b457  ja      loc_18002B590
0x18002b45d  xorps   xmm0, xmm0
0x18002b460  movups  xmmword ptr [rsp+98h+nSubAuthority0], xmm0
0x18002b465  movups  xmmword ptr [rsp+98h+var_20], xmm0
0x18002b46a  test    esi, esi
0x18002b46c  jz      short loc_18002B483
0x18002b46e  mov     r8d, esi
0x18002b471  lea     rdx, [rbx+7]; Src
0x18002b475  shl     r8, 2; Size
0x18002b479  lea     rcx, [rsp+98h+nSubAuthority0]; void *
0x18002b47e  call    memcpy_0
0x18002b483  mov     r9d, [rsp+98h+nSubAuthority0+4]; nSubAuthority1
0x18002b488  lea     rax, [rsp+98h+pSourceSid]
0x18002b48d  mov     r8d, [rsp+98h+nSubAuthority0]; nSubAuthority0
0x18002b492  movzx   edx, sil; nSubAuthorityCount
0x18002b496  mov     [rsp+98h+pSid], rax; pSid
0x18002b49b  mov     rcx, rbx; pIdentifierAuthority
0x18002b49e  mov     eax, [rsp+98h+var_20+0Ch]
0x18002b4a5  mov     [rsp+98h+nSubAuthority7], eax; nSubAuthority7
0x18002b4a9  mov     eax, [rsp+98h+var_20+8]
0x18002b4b0  mov     [rsp+98h+nSubAuthority6], eax; nSubAuthority6
0x18002b4b4  mov     eax, [rsp+98h+var_20+4]
0x18002b4b8  mov     [rsp+98h+nSubAuthority5], eax; nSubAuthority5
0x18002b4bc  mov     eax, [rsp+98h+var_20]
0x18002b4c0  mov     [rsp+98h+nSubAuthority4], eax; nSubAuthority4
0x18002b4c4  mov     eax, [rsp+98h+nSubAuthority0+0Ch]
0x18002b4c8  mov     [rsp+98h+nSubAuthority3], eax; nSubAuthority3
0x18002b4cc  mov     eax, [rsp+98h+nSubAuthority0+8]
0x18002b4d0  mov     [rsp+98h+nSubAuthority2], eax; nSubAuthority2
0x18002b4d4  mov     [rsp+98h+pSourceSid], 0
0x18002b4dd  call    cs:__imp_AllocateAndInitializeSid
0x18002b4e3  test    eax, eax
0x18002b4e5  jz      short loc_18002B553
0x18002b4e7  mov     rcx, [rsp+98h+pSourceSid]; pSid
0x18002b4ec  call    ?VaultValidatePackageSid@@YAKQEAX@Z; VaultValidatePackageSid(void * const)
0x18002b4f1  mov     rcx, [rsp+98h+pSourceSid]; pSourceSid
0x18002b4f6  mov     ebx, eax
0x18002b4f8  test    eax, eax
0x18002b4fa  jnz     short loc_18002B50F
0x18002b4fc  mov     rdx, rdi; struct CVaultSid **
0x18002b4ff  call    ?CreateVaultSid@CVaultSid@@SAKQEAXPEAPEAV1@@Z; CVaultSid::CreateVaultSid(void * const,CVaultSid * *)
0x18002b504  mov     rcx, [rsp+98h+pSourceSid]; pSid
0x18002b509  mov     ebx, eax
0x18002b50b  test    eax, eax
0x18002b50d  jz      short loc_18002B524
0x18002b50f  call    cs:__imp_FreeSid
0x18002b515  mov     eax, ebx
0x18002b517  mov     rsi, [rsp+98h+arg_10]
0x18002b51f  jmp     loc_18002B403
0x18002b524  call    cs:__imp_FreeSid
0x18002b52a  mov     rsi, [rsp+98h+arg_10]
0x18002b532  xor     eax, eax
0x18002b534  jmp     loc_18002B403
0x18002b539  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b540  lea     rdx, WPP_GLOBAL_Control
0x18002b547  cmp     rcx, rdx
0x18002b54a  jnz     short loc_18002B5B0
0x18002b54c  mov     eax, 57h ; 'W'
0x18002b551  jmp     short loc_18002B517
0x18002b553  call    cs:__imp_GetLastError
0x18002b559  mov     ebx, eax
0x18002b55b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b562  lea     rdx, WPP_GLOBAL_Control
0x18002b569  cmp     rcx, rdx
0x18002b56c  jz      short loc_18002B58C
0x18002b56e  test    byte ptr [rcx+1Ch], 2
0x18002b572  jz      short loc_18002B58C
0x18002b574  mov     rcx, [rcx+10h]
0x18002b578  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18002b57f  mov     edx, 2Fh ; '/'
0x18002b584  mov     r9d, eax
0x18002b587  call    WPP_SF_d
0x18002b58c  mov     eax, ebx
0x18002b58e  jmp     short loc_18002B517
0x18002b590  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b597  lea     rdx, WPP_GLOBAL_Control
0x18002b59e  cmp     rcx, rdx
0x18002b5a1  jz      short loc_18002B54C
0x18002b5a3  test    byte ptr [rcx+1Ch], 2
0x18002b5a7  jz      short loc_18002B54C
0x18002b5a9  mov     edx, 2Eh ; '.'
0x18002b5ae  jmp     short loc_18002B5BB
0x18002b5b0  test    byte ptr [rcx+1Ch], 2
0x18002b5b4  jz      short loc_18002B54C
0x18002b5b6  mov     edx, 2Dh ; '-'
0x18002b5bb  mov     rcx, [rcx+10h]
0x18002b5bf  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18002b5c6  mov     r9d, 57h ; 'W'
0x18002b5cc  call    WPP_SF_d
0x18002b5d1  jmp     loc_18002B54C
```
