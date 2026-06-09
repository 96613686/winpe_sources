# SetSidOnAcl(void *,_ACL *,_ACL * *,ulong,uchar,int)

- ea: `0x18003b2a4`
- end: `0x18003b445`
- name: `?SetSidOnAcl@@YAJPEAXPEAU_ACL@@PEAPEAU1@KEH@Z`
- size: `417`
- prototype: `__int64 __fastcall(PSID pSid, PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180036994`

## callees

- `0x180001600`
- `0x18002c8d4`
- `0x18003b2a4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18003b348`
- `KERNEL32!HeapAlloc` at `0x18003b348`
- `KERNEL32!GetLastError` at `0x18003b3f0`
- `KERNEL32!GetLastError` at `0x18003b3f0`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003b385`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003b385`
- `ADVAPI32!GetLengthSid` at `0x18003b317`
- `ADVAPI32!GetLengthSid` at `0x18003b317`
- `ADVAPI32!InitializeAcl` at `0x18003b362`
- `ADVAPI32!InitializeAcl` at `0x18003b362`
- `ADVAPI32!AddAce` at `0x18003b3e2`
- `ADVAPI32!AddAce` at `0x18003b3e2`
- `ADVAPI32!IsValidSid` at `0x18003b2e3`
- `ADVAPI32!IsValidSid` at `0x18003b2e3`
- `ADVAPI32!GetAce` at `0x18003b399`
- `ADVAPI32!GetAce` at `0x18003b3c0`
- `ADVAPI32!GetAce` at `0x18003b399`
- `ADVAPI32!GetAce` at `0x18003b3c0`
- `ADVAPI32!GetAclInformation` at `0x18003b306`
- `ADVAPI32!GetAclInformation` at `0x18003b306`

## pseudocode

```c
__int64 __fastcall SetSidOnAcl(PSID pSid, PACL pAcl, struct _ACL **a3)
{
  DWORD LengthSid; // eax
  DWORD v7; // ebx
  ACL *v8; // rax
  ACL *v9; // rcx
  DWORD v10; // edi
  unsigned int v11; // ebx
  signed int LastError; // eax
  LPVOID pAce; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pAceList; // [rsp+38h] [rbp-50h] BYREF
  __int64 pAclInformation; // [rsp+40h] [rbp-48h] BYREF
  int v17; // [rsp+48h] [rbp-40h]

  pAclInformation = 0;
  v17 = 0;
  pAceList = 0;
  *a3 = 0;
  if ( pAcl && IsValidSid(pSid) )
  {
    if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
      goto LABEL_15;
    LengthSid = GetLengthSid(pSid);
    if ( LengthSid >= 0xFFFFFFF4 )
    {
      v11 = -2147024362;
    }
    else
    {
      v7 = LengthSid + 12 + HIDWORD(pAclInformation) - 4;
      if ( v7 >= HIDWORD(pAclInformation) )
      {
        v8 = (ACL *)HeapAlloc(ghTapisrvHeap, 8u, v7);
        *a3 = v8;
        if ( v8 )
        {
          if ( InitializeAcl(v8, v7, 2u) )
          {
            v9 = *a3;
            pAce = 0;
            if ( AddAccessAllowedAce(v9, 2u, 2u, pSid) )
            {
              if ( GetAce(*a3, 0, &pAce) )
              {
                v10 = 0;
                v11 = 0;
                *((_BYTE *)pAce + 1) = 0;
                while ( v10 < (unsigned int)pAclInformation )
                {
                  if ( !GetAce(pAcl, v10, &pAceList)
                    || !AddAce(*a3, 2u, 0xFFFFFFFF, pAceList, *((unsigned __int16 *)pAceList + 1)) )
                  {
                    goto LABEL_15;
                  }
                  ++v10;
                }
LABEL_17:
                if ( !v11 )
                  return v11;
                goto LABEL_22;
              }
            }
          }
LABEL_15:
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_17;
        }
      }
      v11 = -2147483580;
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_22:
  if ( *a3 )
    ServerFree(*a3);
  return v11;
}

```

## disassembly

```asm
0x18003b2a4  push    rbx
0x18003b2a6  push    rbp
0x18003b2a7  push    rsi
0x18003b2a8  push    rdi
0x18003b2a9  push    r15
0x18003b2ab  sub     rsp, 60h
0x18003b2af  mov     rax, cs:__security_cookie
0x18003b2b6  xor     rax, rsp
0x18003b2b9  mov     [rsp+88h+var_38], rax
0x18003b2be  xor     eax, eax
0x18003b2c0  mov     rsi, r8
0x18003b2c3  mov     [rsp+88h+pAclInformation], rax
0x18003b2c8  mov     rbp, rdx
0x18003b2cb  mov     [rsp+88h+var_40], eax
0x18003b2cf  mov     rdi, rcx
0x18003b2d2  mov     [rsp+88h+pAceList], rax
0x18003b2d7  mov     [r8], rax
0x18003b2da  test    rdx, rdx
0x18003b2dd  jz      loc_18003B419
0x18003b2e3  call    cs:__imp_IsValidSid
0x18003b2e9  test    eax, eax
0x18003b2eb  jz      loc_18003B419
0x18003b2f1  mov     r15d, 2
0x18003b2f7  lea     rdx, [rsp+88h+pAclInformation]; pAclInformation
0x18003b2fc  mov     r9d, r15d; dwAclInformationClass
0x18003b2ff  mov     rcx, rbp; pAcl
0x18003b302  lea     r8d, [r15+0Ah]; nAclInformationLength
0x18003b306  call    cs:__imp_GetAclInformation
0x18003b30c  test    eax, eax
0x18003b30e  jz      loc_18003B3F0
0x18003b314  mov     rcx, rdi; pSid
0x18003b317  call    cs:__imp_GetLengthSid
0x18003b31d  lea     ecx, [rax+0Ch]
0x18003b320  cmp     ecx, 0Ch
0x18003b323  jb      loc_18003B412
0x18003b329  mov     eax, dword ptr [rsp+88h+pAclInformation+4]
0x18003b32d  lea     ebx, [rax-4]
0x18003b330  add     ebx, ecx
0x18003b332  cmp     ebx, eax
0x18003b334  jb      loc_18003B40B
0x18003b33a  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18003b341  lea     edx, [r15+6]; dwFlags
0x18003b345  mov     r8d, ebx; dwBytes
0x18003b348  call    cs:__imp_HeapAlloc
0x18003b34e  mov     [rsi], rax
0x18003b351  test    rax, rax
0x18003b354  jz      loc_18003B40B
0x18003b35a  mov     r8d, r15d; dwAclRevision
0x18003b35d  mov     edx, ebx; nAclLength
0x18003b35f  mov     rcx, rax; pAcl
0x18003b362  call    cs:__imp_InitializeAcl
0x18003b368  test    eax, eax
0x18003b36a  jz      loc_18003B3F0
0x18003b370  mov     rcx, [rsi]; pAcl
0x18003b373  mov     r9, rdi; pSid
0x18003b376  mov     r8d, r15d; AccessMask
0x18003b379  mov     [rsp+88h+pAce], 0
0x18003b382  mov     edx, r15d; dwAceRevision
0x18003b385  call    cs:__imp_AddAccessAllowedAce
0x18003b38b  test    eax, eax
0x18003b38d  jz      short loc_18003B3F0
0x18003b38f  mov     rcx, [rsi]; pAcl
0x18003b392  lea     r8, [rsp+88h+pAce]; pAce
0x18003b397  xor     edx, edx; dwAceIndex
0x18003b399  call    cs:__imp_GetAce
0x18003b39f  test    eax, eax
0x18003b3a1  jz      short loc_18003B3F0
0x18003b3a3  mov     rax, [rsp+88h+pAce]
0x18003b3a8  xor     edi, edi
0x18003b3aa  xor     ebx, ebx
0x18003b3ac  mov     byte ptr [rax+1], 0
0x18003b3b0  cmp     edi, dword ptr [rsp+88h+pAclInformation]
0x18003b3b4  jnb     short loc_18003B405
0x18003b3b6  lea     r8, [rsp+88h+pAceList]; pAce
0x18003b3bb  mov     edx, edi; dwAceIndex
0x18003b3bd  mov     rcx, rbp; pAcl
0x18003b3c0  call    cs:__imp_GetAce
0x18003b3c6  test    eax, eax
0x18003b3c8  jz      short loc_18003B3F0
0x18003b3ca  mov     r9, [rsp+88h+pAceList]; pAceList
0x18003b3cf  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18003b3d3  mov     rcx, [rsi]; pAcl
0x18003b3d6  mov     edx, r15d; dwAceRevision
0x18003b3d9  movzx   eax, word ptr [r9+2]
0x18003b3de  mov     [rsp+88h+nAceListLength], eax; nAceListLength
0x18003b3e2  call    cs:__imp_AddAce
0x18003b3e8  test    eax, eax
0x18003b3ea  jz      short loc_18003B3F0
0x18003b3ec  inc     edi
0x18003b3ee  jmp     short loc_18003B3B0
0x18003b3f0  call    cs:__imp_GetLastError
0x18003b3f6  mov     ebx, eax
0x18003b3f8  test    eax, eax
0x18003b3fa  jle     short loc_18003B405
0x18003b3fc  movzx   ebx, ax
0x18003b3ff  or      ebx, 80070000h
0x18003b405  test    ebx, ebx
0x18003b407  jz      short loc_18003B42B
0x18003b409  jmp     short loc_18003B41E
0x18003b40b  mov     ebx, 80000044h
0x18003b410  jmp     short loc_18003B41E
0x18003b412  mov     ebx, 80070216h
0x18003b417  jmp     short loc_18003B41E
0x18003b419  mov     ebx, 80070057h
0x18003b41e  mov     rcx, [rsi]; lpMem
0x18003b421  test    rcx, rcx
0x18003b424  jz      short loc_18003B42B
0x18003b426  call    ServerFree
0x18003b42b  mov     eax, ebx
0x18003b42d  mov     rcx, [rsp+88h+var_38]
0x18003b432  xor     rcx, rsp; StackCookie
0x18003b435  call    __security_check_cookie
0x18003b43a  add     rsp, 60h
0x18003b43e  pop     r15
0x18003b440  pop     rdi
0x18003b441  pop     rsi
0x18003b442  pop     rbp
0x18003b443  pop     rbx
0x18003b444  retn
```
