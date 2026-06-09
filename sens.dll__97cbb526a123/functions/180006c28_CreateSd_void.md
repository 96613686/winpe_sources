# CreateSd(void)

- ea: `0x180006c28`
- end: `0x180006df3`
- name: `?CreateSd@@YAPEAXXZ`
- size: `459`
- prototype: `struct _ACL *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800080dc`

## callees

- `0x180006c28`
- `0x180006dfc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006db8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006db8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006cb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006cb6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c77`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c8f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c9b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c77`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c8f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c9b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180006cda`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180006cda`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006cf8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006d18`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006d33`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006d4d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006cf8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006d18`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006d33`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180006d4d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d83`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d8d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d97`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006da1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006dc2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006dcc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006dd6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006de0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d83`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d8d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d97`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006da1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006dc2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006dcc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006dd6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006de0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180006d60`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180006d60`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180006d75`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180006d75`

## pseudocode

```c
struct _ACL *CreateSd(void)
{
  DWORD LengthSid; // esi
  DWORD v1; // esi
  DWORD v2; // esi
  DWORD v3; // esi
  struct _ACL *v4; // rax
  struct _ACL *v5; // rdi
  struct _ACL *v6; // rbx
  PSID v8; // [rsp+50h] [rbp+30h] BYREF
  PSID v9; // [rsp+58h] [rbp+38h] BYREF
  PSID v10; // [rsp+60h] [rbp+40h] BYREF
  PSID pSid; // [rsp+68h] [rbp+48h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  pSid = 0;
  if ( CreateSids(&v9, &v10, &v8, &pSid) )
  {
    LengthSid = GetLengthSid(pSid);
    v1 = GetLengthSid(v10) + LengthSid;
    v2 = GetLengthSid(v9) + v1;
    v3 = GetLengthSid(v8) + 40 + v2;
    v4 = (struct _ACL *)HeapAlloc(ghSensHeap, 0, v3 + 40LL);
    v5 = v4;
    if ( v4 )
    {
      v6 = v4 + 5;
      if ( InitializeAcl(v4 + 5, v3, 2u)
        && AddAccessAllowedAce(v6, 2u, 0xE0100000, v8)
        && AddAccessAllowedAce(v6, 2u, 0x10000000u, v9)
        && AddAccessAllowedAce(v6, 2u, 0x10000000u, v10)
        && AddAccessAllowedAce(v6, 2u, 0x80000000, pSid)
        && InitializeSecurityDescriptor(v5, 1u)
        && SetSecurityDescriptorDacl(v5, 1, v6, 0) )
      {
        FreeSid(v8);
        FreeSid(v9);
        FreeSid(v10);
        FreeSid(pSid);
        return v5;
      }
      HeapFree(ghSensHeap, 0, v5);
    }
    FreeSid(v8);
    FreeSid(v9);
    FreeSid(v10);
    FreeSid(pSid);
  }
  return 0;
}

```

## disassembly

```asm
0x180006c28  push    rbp
0x180006c2a  push    rbx
0x180006c2b  push    rsi
0x180006c2c  push    rdi
0x180006c2d  push    r15
0x180006c2f  mov     rbp, rsp
0x180006c32  sub     rsp, 20h
0x180006c36  lea     r9, [rbp+pSid]; void **
0x180006c3a  mov     [rbp+arg_0], 0
0x180006c42  lea     r8, [rbp+arg_0]; void **
0x180006c46  mov     [rbp+arg_8], 0
0x180006c4e  lea     rdx, [rbp+arg_10]; void **
0x180006c52  mov     [rbp+arg_10], 0
0x180006c5a  lea     rcx, [rbp+arg_8]; void **
0x180006c5e  mov     [rbp+pSid], 0
0x180006c66  call    ?CreateSids@@YAHPEAPEAX000@Z; CreateSids(void * *,void * *,void * *,void * *)
0x180006c6b  test    eax, eax
0x180006c6d  jz      loc_180006DE6
0x180006c73  mov     rcx, [rbp+pSid]; pSid
0x180006c77  call    cs:__imp_GetLengthSid
0x180006c7d  mov     rcx, [rbp+arg_10]; pSid
0x180006c81  mov     esi, eax
0x180006c83  call    cs:__imp_GetLengthSid
0x180006c89  mov     rcx, [rbp+arg_8]; pSid
0x180006c8d  add     esi, eax
0x180006c8f  call    cs:__imp_GetLengthSid
0x180006c95  mov     rcx, [rbp+arg_0]; pSid
0x180006c99  add     esi, eax
0x180006c9b  call    cs:__imp_GetLengthSid
0x180006ca1  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180006ca8  xor     edx, edx; dwFlags
0x180006caa  add     eax, 28h ; '('
0x180006cad  add     esi, eax
0x180006caf  mov     r8d, esi
0x180006cb2  add     r8, 28h ; '('; dwBytes
0x180006cb6  call    cs:__imp_HeapAlloc
0x180006cbc  mov     rdi, rax
0x180006cbf  test    rax, rax
0x180006cc2  jz      loc_180006DBE
0x180006cc8  lea     rbx, [rax+28h]
0x180006ccc  mov     r15d, 2
0x180006cd2  mov     r8d, r15d; dwAclRevision
0x180006cd5  mov     rcx, rbx; pAcl
0x180006cd8  mov     edx, esi; nAclLength
0x180006cda  call    cs:__imp_InitializeAcl
0x180006ce0  test    eax, eax
0x180006ce2  jz      loc_180006DAC
0x180006ce8  mov     r9, [rbp+arg_0]; pSid
0x180006cec  mov     r8d, 0E0100000h; AccessMask
0x180006cf2  mov     edx, r15d; dwAceRevision
0x180006cf5  mov     rcx, rbx; pAcl
0x180006cf8  call    cs:__imp_AddAccessAllowedAce
0x180006cfe  test    eax, eax
0x180006d00  jz      loc_180006DAC
0x180006d06  mov     r9, [rbp+arg_8]; pSid
0x180006d0a  mov     esi, 10000000h
0x180006d0f  mov     r8d, esi; AccessMask
0x180006d12  mov     edx, r15d; dwAceRevision
0x180006d15  mov     rcx, rbx; pAcl
0x180006d18  call    cs:__imp_AddAccessAllowedAce
0x180006d1e  test    eax, eax
0x180006d20  jz      loc_180006DAC
0x180006d26  mov     r9, [rbp+arg_10]; pSid
0x180006d2a  mov     r8d, esi; AccessMask
0x180006d2d  mov     edx, r15d; dwAceRevision
0x180006d30  mov     rcx, rbx; pAcl
0x180006d33  call    cs:__imp_AddAccessAllowedAce
0x180006d39  test    eax, eax
0x180006d3b  jz      short loc_180006DAC
0x180006d3d  mov     r9, [rbp+pSid]; pSid
0x180006d41  mov     r8d, 80000000h; AccessMask
0x180006d47  mov     edx, r15d; dwAceRevision
0x180006d4a  mov     rcx, rbx; pAcl
0x180006d4d  call    cs:__imp_AddAccessAllowedAce
0x180006d53  test    eax, eax
0x180006d55  jz      short loc_180006DAC
0x180006d57  lea     esi, [r15-1]
0x180006d5b  mov     rcx, rdi; pSecurityDescriptor
0x180006d5e  mov     edx, esi; dwRevision
0x180006d60  call    cs:__imp_InitializeSecurityDescriptor
0x180006d66  test    eax, eax
0x180006d68  jz      short loc_180006DAC
0x180006d6a  xor     r9d, r9d; bDaclDefaulted
0x180006d6d  mov     r8, rbx; pDacl
0x180006d70  mov     edx, esi; bDaclPresent
0x180006d72  mov     rcx, rdi; pSecurityDescriptor
0x180006d75  call    cs:__imp_SetSecurityDescriptorDacl
0x180006d7b  test    eax, eax
0x180006d7d  jz      short loc_180006DAC
0x180006d7f  mov     rcx, [rbp+arg_0]; pSid
0x180006d83  call    cs:__imp_FreeSid
0x180006d89  mov     rcx, [rbp+arg_8]; pSid
0x180006d8d  call    cs:__imp_FreeSid
0x180006d93  mov     rcx, [rbp+arg_10]; pSid
0x180006d97  call    cs:__imp_FreeSid
0x180006d9d  mov     rcx, [rbp+pSid]; pSid
0x180006da1  call    cs:__imp_FreeSid
0x180006da7  mov     rax, rdi
0x180006daa  jmp     short loc_180006DE8
0x180006dac  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180006db3  mov     r8, rdi; lpMem
0x180006db6  xor     edx, edx; dwFlags
0x180006db8  call    cs:__imp_HeapFree
0x180006dbe  mov     rcx, [rbp+arg_0]; pSid
0x180006dc2  call    cs:__imp_FreeSid
0x180006dc8  mov     rcx, [rbp+arg_8]; pSid
0x180006dcc  call    cs:__imp_FreeSid
0x180006dd2  mov     rcx, [rbp+arg_10]; pSid
0x180006dd6  call    cs:__imp_FreeSid
0x180006ddc  mov     rcx, [rbp+pSid]; pSid
0x180006de0  call    cs:__imp_FreeSid
0x180006de6  xor     eax, eax
0x180006de8  add     rsp, 20h
0x180006dec  pop     r15
0x180006dee  pop     rdi
0x180006def  pop     rsi
0x180006df0  pop     rbx
0x180006df1  pop     rbp
0x180006df2  retn
```
