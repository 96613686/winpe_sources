# GetCustomSecurityDescriptor(ushort const *,void *)

- ea: `0x180070c20`
- end: `0x180070da5`
- name: `?GetCustomSecurityDescriptor@@YAJPEBGPEAX@Z`
- size: `389`
- prototype: `int(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800708a0`

## callees

- `0x18000dafc`
- `0x1800706d0`
- `0x1800707a0`
- `0x1800709b0`
- `0x180070c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d4f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180070d41`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180070d41`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180070d2c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180070d2c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180070d14`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180070d14`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180070ca0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180070ca0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070d95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070d95`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180070c4c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180070c4c`

## pseudocode

```c
__int64 __fastcall GetCustomSecurityDescriptor(const unsigned __int16 *a1, void *a2)
{
  signed int v3; // eax
  signed int Instance; // ebx
  int v5; // r9d
  signed int v6; // eax
  void *v7; // rdx
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-20h] BYREF
  PACL v11; // [rsp+28h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-10h] BYREF
  const unsigned __int16 *bDaclDefaulted; // [rsp+60h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+30h] BYREF
  void *lpMem; // [rsp+78h] [rbp+38h] BYREF

  bDaclDefaulted = a1;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CIOI;KR;;;WD)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    pDacl = 0;
    LODWORD(bDaclDefaulted) = 0;
    bDaclPresent = 0;
    if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, (LPBOOL)&bDaclDefaulted) )
    {
      lpMem = 0;
      Instance = CAceList::CreateInstance(pDacl, SecurityDescriptor, (struct CAceList **)&lpMem, v5);
      if ( Instance >= 0 )
      {
        v11 = 0;
        Instance = CAceList::GetAclForExplicitEntries((CAceList *)lpMem, v7, &v11);
        if ( Instance >= 0 )
        {
          if ( InitializeSecurityDescriptor(a2, 1u)
            && SetSecurityDescriptorDacl(a2, 1, v11, 0)
            && SetSecurityDescriptorControl(a2, 0x1000u, 0x1000u) )
          {
            Instance = 0;
          }
          else
          {
            LastError = GetLastError();
            Instance = LastError;
            if ( LastError > 0 )
              Instance = (unsigned __int16)LastError | 0x80070000;
            if ( Instance >= 0 )
              Instance = -2147467259;
            LocalFree(v11);
          }
        }
        if ( lpMem )
        {
          CAceList::~CAceList((CAceList *)lpMem);
          operator delete(lpMem);
        }
      }
    }
    else
    {
      v6 = GetLastError();
      Instance = v6;
      if ( v6 > 0 )
        Instance = (unsigned __int16)v6 | 0x80070000;
      if ( Instance >= 0 )
        Instance = -2147467259;
    }
    LocalFree(SecurityDescriptor);
  }
  else
  {
    v3 = GetLastError();
    Instance = v3;
    if ( v3 > 0 )
      Instance = (unsigned __int16)v3 | 0x80070000;
    if ( Instance >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180070c20  mov     [rsp-18h+bDaclDefaulted], rcx
0x180070c25  push    rbp
0x180070c26  push    rbx
0x180070c27  push    rsi
0x180070c28  mov     rbp, rsp
0x180070c2b  sub     rsp, 40h
0x180070c2f  xor     r9d, r9d; SecurityDescriptorSize
0x180070c32  mov     [rbp+SecurityDescriptor], 0
0x180070c3a  mov     rsi, rdx
0x180070c3d  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180070c41  lea     rcx, StringSecurityDescriptor; "D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CI"...
0x180070c48  lea     edx, [r9+1]; StringSDRevision
0x180070c4c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180070c52  test    eax, eax
0x180070c54  jnz     short loc_180070C7A
0x180070c56  call    cs:__imp_GetLastError
0x180070c5c  mov     ebx, eax
0x180070c5e  test    eax, eax
0x180070c60  jle     short loc_180070C6B
0x180070c62  movzx   ebx, ax
0x180070c65  or      ebx, 80070000h
0x180070c6b  test    ebx, ebx
0x180070c6d  mov     eax, 80004005h
0x180070c72  cmovns  ebx, eax
0x180070c75  jmp     loc_180070D9B
0x180070c7a  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180070c7e  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180070c82  lea     r8, [rbp+pDacl]; pDacl
0x180070c86  mov     [rbp+pDacl], 0
0x180070c8e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180070c92  mov     dword ptr [rbp+bDaclDefaulted], 0
0x180070c99  mov     [rbp+bDaclPresent], 0
0x180070ca0  call    cs:__imp_GetSecurityDescriptorDacl
0x180070ca6  test    eax, eax
0x180070ca8  jnz     short loc_180070CCE
0x180070caa  call    cs:__imp_GetLastError
0x180070cb0  mov     ebx, eax
0x180070cb2  test    eax, eax
0x180070cb4  jle     short loc_180070CBF
0x180070cb6  movzx   ebx, ax
0x180070cb9  or      ebx, 80070000h
0x180070cbf  test    ebx, ebx
0x180070cc1  mov     eax, 80004005h
0x180070cc6  cmovns  ebx, eax
0x180070cc9  jmp     loc_180070D91
0x180070cce  mov     rdx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180070cd2  lea     r8, [rbp+lpMem]; struct CAceList **
0x180070cd6  mov     rcx, [rbp+pDacl]; struct _ACL *
0x180070cda  mov     [rbp+lpMem], 0
0x180070ce2  call    ?CreateInstance@CAceList@@SAJPEAU_ACL@@PEAXPEAPEAV1@H@Z; CAceList::CreateInstance(_ACL *,void *,CAceList * *,int)
0x180070ce7  mov     ebx, eax
0x180070ce9  test    eax, eax
0x180070ceb  js      loc_180070D91
0x180070cf1  mov     rcx, [rbp+lpMem]; this
0x180070cf5  lea     r8, [rbp+var_18]; struct _ACL **
0x180070cf9  mov     [rbp+var_18], 0
0x180070d01  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x180070d06  mov     ebx, eax
0x180070d08  test    eax, eax
0x180070d0a  js      short loc_180070D78
0x180070d0c  mov     edx, 1; dwRevision
0x180070d11  mov     rcx, rsi; pSecurityDescriptor
0x180070d14  call    cs:__imp_InitializeSecurityDescriptor
0x180070d1a  test    eax, eax
0x180070d1c  jz      short loc_180070D4F
0x180070d1e  mov     r8, [rbp+var_18]; pDacl
0x180070d22  xor     r9d, r9d; bDaclDefaulted
0x180070d25  mov     rcx, rsi; pSecurityDescriptor
0x180070d28  lea     edx, [r9+1]; bDaclPresent
0x180070d2c  call    cs:__imp_SetSecurityDescriptorDacl
0x180070d32  test    eax, eax
0x180070d34  jz      short loc_180070D4F
0x180070d36  mov     edx, 1000h; ControlBitsOfInterest
0x180070d3b  mov     rcx, rsi; pSecurityDescriptor
0x180070d3e  mov     r8d, edx; ControlBitsToSet
0x180070d41  call    cs:__imp_SetSecurityDescriptorControl
0x180070d47  test    eax, eax
0x180070d49  jz      short loc_180070D4F
0x180070d4b  xor     ebx, ebx
0x180070d4d  jmp     short loc_180070D78
0x180070d4f  call    cs:__imp_GetLastError
0x180070d55  mov     ebx, eax
0x180070d57  test    eax, eax
0x180070d59  jle     short loc_180070D64
0x180070d5b  movzx   ebx, ax
0x180070d5e  or      ebx, 80070000h
0x180070d64  mov     rcx, [rbp+var_18]; hMem
0x180070d68  test    ebx, ebx
0x180070d6a  mov     eax, 80004005h
0x180070d6f  cmovns  ebx, eax
0x180070d72  call    cs:__imp_LocalFree
0x180070d78  cmp     [rbp+lpMem], 0
0x180070d7d  jz      short loc_180070D91
0x180070d7f  mov     rcx, [rbp+lpMem]; this
0x180070d83  call    ??1CAceList@@QEAA@XZ; CAceList::~CAceList(void)
0x180070d88  mov     rcx, [rbp+lpMem]; lpMem
0x180070d8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070d91  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180070d95  call    cs:__imp_LocalFree
0x180070d9b  mov     eax, ebx
0x180070d9d  add     rsp, 40h
0x180070da1  pop     rsi
0x180070da2  pop     rbx
0x180070da3  pop     rbp
0x180070da4  retn
```
