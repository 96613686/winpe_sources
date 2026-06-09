# CopySecurityInformation

- ea: `0x180019eb0`
- end: `0x18001a092`
- name: `CopySecurityInformation`
- size: `482`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, LPWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800193b8`

## callees

- `0x180019eb0`
- `0x18001a28c`
- `0x18001cc80`
- `0x18001ccd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019f8d`
- `KERNEL32!GetLastError` at `0x180019f8d`
- `KERNEL32!LocalFree` at `0x18001a057`
- `KERNEL32!LocalFree` at `0x18001a057`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001a01e`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001a01e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180019f7d`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180019f7d`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180019f4d`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180019f4d`

## pseudocode

```c
__int64 __fastcall CopySecurityInformation(LPCWSTR pObjectName, LPWSTR a2, int a3)
{
  signed int v6; // ebx
  int NamedSecurityInfoW; // eax
  int v8; // ebx
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  SECURITY_INFORMATION v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD dwRevision; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-18h] BYREF
  PSID psidGroup; // [rsp+60h] [rbp-10h] BYREF
  PSID ppsidOwner; // [rsp+68h] [rbp-8h] BYREF
  WORD pControl; // [rsp+A8h] [rbp+38h] BYREF

  dwRevision = 0;
  psidGroup = 0;
  ppsidOwner = 0;
  pDacl = 0;
  pSacl = 0;
  pSecurityDescriptor = 0;
  pControl = 0;
  v6 = WdsModifySecurityPrivilege(1);
  if ( v6 >= 0 )
  {
    v6 = WdsModifyRestorePrivilege(1);
    if ( v6 >= 0 )
    {
      NamedSecurityInfoW = GetNamedSecurityInfoW(
                             pObjectName,
                             SE_FILE_OBJECT,
                             0xFu,
                             &ppsidOwner,
                             &psidGroup,
                             &pDacl,
                             &pSacl,
                             &pSecurityDescriptor);
      dwRevision = NamedSecurityInfoW;
      if ( NamedSecurityInfoW )
      {
        if ( NamedSecurityInfoW <= 0 )
        {
          v6 = NamedSecurityInfoW;
          goto LABEL_20;
        }
        v8 = (unsigned __int16)NamedSecurityInfoW;
        goto LABEL_19;
      }
      if ( GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
      {
        if ( a3 )
        {
          v13 = ((pControl & 0xF000) << 19) | 0xF;
          if ( (pControl & 0x2000) != 0 )
            v13 = ((pControl & 0xF000) << 19) | 0x4000000F;
        }
        else
        {
          v13 = -1073741809;
        }
        dwRevision = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, v13, ppsidOwner, psidGroup, pDacl, pSacl);
        if ( (unsigned int)ElValidateWin32_8(dwRevision, v14, v15, 2299) )
        {
          v6 = dwRevision;
          if ( (int)dwRevision > 0 )
          {
            v8 = (unsigned __int16)dwRevision;
LABEL_19:
            v6 = v8 | 0x80070000;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v12 = ElValidateWin32_8(LastError, v10, v11, 2263);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
      }
    }
  }
LABEL_20:
  if ( pSecurityDescriptor )
  {
    LocalFree(pSecurityDescriptor);
    pSecurityDescriptor = 0;
  }
  WdsModifyRestorePrivilege(0);
  WdsModifySecurityPrivilege(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019eb0  mov     [rsp-18h+arg_0], rbx
0x180019eb5  mov     [rsp-18h+arg_8], rsi
0x180019eba  mov     [rsp-18h+arg_10], rdi
0x180019ebf  push    rbp
0x180019ec0  push    r14
0x180019ec2  push    r15
0x180019ec4  mov     rbp, rsp
0x180019ec7  sub     rsp, 70h
0x180019ecb  xor     r15d, r15d
0x180019ece  mov     rsi, rcx
0x180019ed1  mov     edi, r8d
0x180019ed4  mov     [rbp+dwRevision], r15d
0x180019ed8  mov     r14, rdx
0x180019edb  mov     [rbp+psidGroup], r15
0x180019edf  mov     [rbp+ppsidOwner], r15
0x180019ee3  lea     ecx, [r15+1]
0x180019ee7  mov     [rbp+pDacl], r15
0x180019eeb  mov     [rbp+pSacl], r15
0x180019eef  mov     [rbp+pSecurityDescriptor], r15
0x180019ef3  mov     [rbp+pControl], r15w
0x180019ef8  call    WdsModifySecurityPrivilege
0x180019efd  mov     ebx, eax
0x180019eff  test    eax, eax
0x180019f01  js      loc_18001A04E
0x180019f07  lea     ecx, [r15+1]
0x180019f0b  call    WdsModifyRestorePrivilege
0x180019f10  mov     ebx, eax
0x180019f12  test    eax, eax
0x180019f14  js      loc_18001A04E
0x180019f1a  lea     rax, [rbp+pSecurityDescriptor]
0x180019f1e  mov     rcx, rsi; pObjectName
0x180019f21  mov     [rsp+70h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180019f26  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x180019f2a  lea     rax, [rbp+pSacl]
0x180019f2e  mov     [rsp+70h+ppSacl], rax; ppSacl
0x180019f33  lea     edx, [r15+1]; ObjectType
0x180019f37  lea     rax, [rbp+pDacl]
0x180019f3b  mov     [rsp+70h+ppDacl], rax; ppDacl
0x180019f40  lea     r8d, [r15+0Fh]; SecurityInfo
0x180019f44  lea     rax, [rbp+psidGroup]
0x180019f48  mov     [rsp+70h+ppsidGroup], rax; ppsidGroup
0x180019f4d  call    cs:__imp_GetNamedSecurityInfoW
0x180019f54  nop     dword ptr [rax+rax+00h]
0x180019f59  mov     [rbp+dwRevision], eax
0x180019f5c  test    eax, eax
0x180019f5e  jz      short loc_180019F71
0x180019f60  jg      short loc_180019F69
0x180019f62  mov     ebx, eax
0x180019f64  jmp     loc_18001A04E
0x180019f69  movzx   ebx, ax
0x180019f6c  jmp     loc_18001A048
0x180019f71  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180019f75  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180019f79  lea     rdx, [rbp+pControl]; pControl
0x180019f7d  call    cs:__imp_GetSecurityDescriptorControl
0x180019f84  nop     dword ptr [rax+rax+00h]
0x180019f89  test    eax, eax
0x180019f8b  jnz     short loc_180019FC7
0x180019f8d  call    cs:__imp_GetLastError
0x180019f94  nop     dword ptr [rax+rax+00h]
0x180019f99  mov     ecx, eax
0x180019f9b  mov     r9d, 8D7h
0x180019fa1  call    ElValidateWin32_8
0x180019fa6  mov     ebx, eax
0x180019fa8  test    eax, eax
0x180019faa  jle     short loc_180019FB5
0x180019fac  movzx   ebx, ax
0x180019faf  or      ebx, 80070000h
0x180019fb5  test    ebx, ebx
0x180019fb7  js      loc_18001A04E
0x180019fbd  mov     ebx, 80004005h
0x180019fc2  jmp     loc_18001A04E
0x180019fc7  test    edi, edi
0x180019fc9  jnz     short loc_180019FD3
0x180019fcb  mov     r8d, 0C000000Fh
0x180019fd1  jmp     short loc_180019FF7
0x180019fd3  movzx   r8d, [rbp+pControl]
0x180019fd8  mov     eax, 2000h
0x180019fdd  and     r8d, 0FFFFF000h
0x180019fe4  shl     r8d, 13h
0x180019fe8  or      r8d, 0Fh
0x180019fec  test    [rbp+pControl], ax
0x180019ff0  jz      short loc_180019FF7
0x180019ff2  bts     r8d, 1Eh; SecurityInfo
0x180019ff7  mov     rax, [rbp+pSacl]
0x180019ffb  mov     edx, 1; ObjectType
0x18001a000  mov     r9, [rbp+ppsidOwner]; psidOwner
0x18001a004  mov     rcx, r14; pObjectName
0x18001a007  mov     [rsp+70h+ppSacl], rax; pSacl
0x18001a00c  mov     rax, [rbp+pDacl]
0x18001a010  mov     [rsp+70h+ppDacl], rax; pDacl
0x18001a015  mov     rax, [rbp+psidGroup]
0x18001a019  mov     [rsp+70h+ppsidGroup], rax; psidGroup
0x18001a01e  call    cs:__imp_SetNamedSecurityInfoW
0x18001a025  nop     dword ptr [rax+rax+00h]
0x18001a02a  mov     ecx, eax
0x18001a02c  mov     [rbp+dwRevision], eax
0x18001a02f  mov     r9d, 8FBh
0x18001a035  call    ElValidateWin32_8
0x18001a03a  test    eax, eax
0x18001a03c  jz      short loc_18001A04E
0x18001a03e  mov     ebx, [rbp+dwRevision]
0x18001a041  test    ebx, ebx
0x18001a043  jle     short loc_18001A04E
0x18001a045  movzx   ebx, bx
0x18001a048  or      ebx, 80070000h
0x18001a04e  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x18001a052  test    rcx, rcx
0x18001a055  jz      short loc_18001A067
0x18001a057  call    cs:__imp_LocalFree
0x18001a05e  nop     dword ptr [rax+rax+00h]
0x18001a063  mov     [rbp+pSecurityDescriptor], r15
0x18001a067  xor     ecx, ecx
0x18001a069  call    WdsModifyRestorePrivilege
0x18001a06e  xor     ecx, ecx
0x18001a070  call    WdsModifySecurityPrivilege
0x18001a075  lea     r11, [rsp+70h+var_s0]
0x18001a07a  mov     eax, ebx
0x18001a07c  mov     rbx, [r11+20h]
0x18001a080  mov     rsi, [r11+28h]
0x18001a084  mov     rdi, [r11+30h]
0x18001a088  mov     rsp, r11
0x18001a08b  pop     r15
0x18001a08d  pop     r14
0x18001a08f  pop     rbp
0x18001a090  retn
```
