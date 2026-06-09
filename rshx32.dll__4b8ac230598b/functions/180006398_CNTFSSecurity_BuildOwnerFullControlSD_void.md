# CNTFSSecurity::BuildOwnerFullControlSD(void *)

- ea: `0x180006398`
- end: `0x1800064ca`
- name: `?BuildOwnerFullControlSD@CNTFSSecurity@@IEAAJPEAX@Z`
- size: `306`
- prototype: `__int64 __fastcall(CNTFSSecurity *this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000729c`

## callees

- `0x180006398`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006482`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063f6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180006478`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180006478`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006457`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006457`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000643a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000643a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000641a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000641a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800063e2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800063e2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800063c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800063c9`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::BuildOwnerFullControlSD(CNTFSSecurity *this, void *a2)
{
  DWORD v4; // ebx
  HLOCAL v5; // rax
  struct _ACL *v6; // rsi
  signed int v7; // ebx
  signed int LastError; // eax
  void *v9; // rcx
  WINBOOL v10; // [rsp+40h] [rbp+18h] BYREF
  PSID pSid; // [rsp+48h] [rbp+20h] BYREF

  pSid = 0;
  v10 = 0;
  if ( !GetSecurityDescriptorOwner(a2, &pSid, &v10) )
    return 2147942487LL;
  v4 = GetLengthSid(pSid) + 16;
  v5 = LocalAlloc(0x40u, v4 + 40LL);
  *((_QWORD *)this + 43) = v5;
  if ( !v5 )
    return 2147942414LL;
  if ( !InitializeSecurityDescriptor(v5, 1u)
    || (v6 = (struct _ACL *)(*((_QWORD *)this + 43) + 40LL), !InitializeAcl(v6, v4, 2u))
    || !AddAccessAllowedAce(v6, 2u, 0x1F01FFu, pSid)
    || (v6[1].Sbz1 = 3, v7 = 0, !SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 43), 1, v6, 1)) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      v9 = (void *)*((_QWORD *)this + 43);
      if ( v9 )
      {
        LocalFree(v9);
        *((_QWORD *)this + 43) = 0;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006398  mov     r11, rsp
0x18000639b  mov     [r11+8], rbx
0x18000639f  mov     [r11+10h], rsi
0x1800063a3  push    rdi
0x1800063a4  sub     rsp, 20h
0x1800063a8  mov     rax, rdx
0x1800063ab  mov     qword ptr [r11+20h], 0
0x1800063b3  mov     rdi, rcx
0x1800063b6  mov     [rsp+28h+arg_10], 0
0x1800063be  mov     rcx, rax; pSecurityDescriptor
0x1800063c1  lea     r8, [r11+18h]; lpbOwnerDefaulted
0x1800063c5  lea     rdx, [r11+20h]; pOwner
0x1800063c9  call    cs:__imp_GetSecurityDescriptorOwner
0x1800063cf  test    eax, eax
0x1800063d1  jnz     short loc_1800063DD
0x1800063d3  mov     eax, 80070057h
0x1800063d8  jmp     loc_1800064BA
0x1800063dd  mov     rcx, [rsp+28h+pSid]; pSid
0x1800063e2  call    cs:__imp_GetLengthSid
0x1800063e8  mov     ecx, 40h ; '@'; uFlags
0x1800063ed  lea     ebx, [rax+10h]
0x1800063f0  mov     edx, ebx
0x1800063f2  add     rdx, 28h ; '('; uBytes
0x1800063f6  call    cs:__imp_LocalAlloc
0x1800063fc  mov     [rdi+158h], rax
0x180006403  test    rax, rax
0x180006406  jnz     short loc_180006412
0x180006408  mov     eax, 8007000Eh
0x18000640d  jmp     loc_1800064BA
0x180006412  mov     edx, 1; dwRevision
0x180006417  mov     rcx, rax; pSecurityDescriptor
0x18000641a  call    cs:__imp_InitializeSecurityDescriptor
0x180006420  test    eax, eax
0x180006422  jz      short loc_180006482
0x180006424  mov     rsi, [rdi+158h]
0x18000642b  mov     r8d, 2; dwAclRevision
0x180006431  add     rsi, 28h ; '('
0x180006435  mov     edx, ebx; nAclLength
0x180006437  mov     rcx, rsi; pAcl
0x18000643a  call    cs:__imp_InitializeAcl
0x180006440  test    eax, eax
0x180006442  jz      short loc_180006482
0x180006444  mov     r9, [rsp+28h+pSid]; pSid
0x180006449  mov     edx, 2; dwAceRevision
0x18000644e  mov     r8d, 1F01FFh; AccessMask
0x180006454  mov     rcx, rsi; pAcl
0x180006457  call    cs:__imp_AddAccessAllowedAce
0x18000645d  test    eax, eax
0x18000645f  jz      short loc_180006482
0x180006461  mov     byte ptr [rsi+9], 3
0x180006465  xor     ebx, ebx
0x180006467  mov     rcx, [rdi+158h]; pSecurityDescriptor
0x18000646e  mov     r8, rsi; pDacl
0x180006471  lea     r9d, [rbx+1]; bDaclDefaulted
0x180006475  mov     edx, r9d; bDaclPresent
0x180006478  call    cs:__imp_SetSecurityDescriptorDacl
0x18000647e  test    eax, eax
0x180006480  jnz     short loc_1800064B8
0x180006482  call    cs:__imp_GetLastError
0x180006488  mov     ebx, eax
0x18000648a  test    eax, eax
0x18000648c  jle     short loc_180006497
0x18000648e  movzx   ebx, ax
0x180006491  or      ebx, 80070000h
0x180006497  test    ebx, ebx
0x180006499  jns     short loc_1800064B8
0x18000649b  mov     rcx, [rdi+158h]; hMem
0x1800064a2  test    rcx, rcx
0x1800064a5  jz      short loc_1800064B8
0x1800064a7  call    cs:__imp_LocalFree
0x1800064ad  mov     qword ptr [rdi+158h], 0
0x1800064b8  mov     eax, ebx
0x1800064ba  mov     rbx, [rsp+28h+arg_0]
0x1800064bf  mov     rsi, [rsp+28h+arg_8]
0x1800064c4  add     rsp, 20h
0x1800064c8  pop     rdi
0x1800064c9  retn
```
