# CUserProfile::CheckAccessToDirectory(void *,ushort const *)

- ea: `0x18006ac5c`
- end: `0x18006ad4f`
- name: `?CheckAccessToDirectory@CUserProfile@@CAJPEAXPEBG@Z`
- size: `243`
- prototype: `__int64 __fastcall(PSID pSid2, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006b704`

## callees

- `0x18000a210`
- `0x18003269c`
- `0x18006ac5c`
- `0x18006b0cc`
- `0x18006b5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006acdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006acdb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18006acd1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18006acd1`

## string_xrefs

- `0x18006acaa`: `CUserProfile::CheckAccessToDirectory`
- `0x18006aca0`: `GetFileSecurity failed: 0x%x in %s`
- `0x18006acf7`: `GetSecurityDescriptorDacl failed: 0x%x in %s`
- `0x18006ad1f`: `UserHasExplicitAccess failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserProfile::CheckAccessToDirectory(PSID pSid2, LPCWSTR lpFileName)
{
  int FileSecurityW; // eax
  unsigned int v4; // ebx
  const char *v5; // rdx
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-10h] BYREF
  WINBOOL bDaclPresent; // [rsp+50h] [rbp+18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+58h] [rbp+20h] BYREF

  pSecurityDescriptor = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  bDaclPresent = 0;
  FileSecurityW = CUserProfile::GetFileSecurityW(lpFileName, &pSecurityDescriptor);
  v4 = FileSecurityW;
  if ( FileSecurityW >= 0 )
  {
    if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (v4 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "GetSecurityDescriptorDacl failed: 0x%x in %s", v4, "CUserProfile::CheckAccessToDirectory");
        goto LABEL_15;
      }
    }
    if ( !bDaclPresent || !pDacl )
    {
      v4 = 1;
      goto LABEL_15;
    }
    FileSecurityW = CUserProfile::UserHasExplicitAccess(pSid2, pDacl);
    v4 = FileSecurityW;
    if ( FileSecurityW >= 0 )
      goto LABEL_15;
    v5 = "UserHasExplicitAccess failed: 0x%x in %s";
  }
  else
  {
    v5 = "GetFileSecurity failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v5, (unsigned int)FileSecurityW, "CUserProfile::CheckAccessToDirectory");
LABEL_15:
  if ( pSecurityDescriptor )
    operator delete(pSecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x18006ac5c  mov     r11, rsp
0x18006ac5f  mov     [r11+8], rbx
0x18006ac63  push    rsi
0x18006ac64  sub     rsp, 30h
0x18006ac68  mov     rax, rdx
0x18006ac6b  mov     qword ptr [r11-18h], 0
0x18006ac73  mov     rsi, rcx
0x18006ac76  mov     qword ptr [r11-10h], 0
0x18006ac7e  mov     rcx, rax; lpFileName
0x18006ac81  mov     [rsp+38h+bDaclDefaulted], 0
0x18006ac89  lea     rdx, [r11-18h]; void **
0x18006ac8d  mov     [rsp+38h+bDaclPresent], 0
0x18006ac95  call    ?GetFileSecurityW@CUserProfile@@CAJPEBGPEAPEAX@Z; CUserProfile::GetFileSecurityW(ushort const *,void * *)
0x18006ac9a  mov     ebx, eax
0x18006ac9c  test    eax, eax
0x18006ac9e  jns     short loc_18006ACBD
0x18006aca0  lea     rdx, aGetfilesecurit; "GetFileSecurity failed: 0x%x in %s"
0x18006aca7  mov     r8d, eax
0x18006acaa  lea     r9, aCuserprofileCh; "CUserProfile::CheckAccessToDirectory"
0x18006acb1  mov     ecx, 8; int
0x18006acb6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006acbb  jmp     short loc_18006AD30
0x18006acbd  mov     rcx, [rsp+38h+pSecurityDescriptor]; pSecurityDescriptor
0x18006acc2  lea     r9, [rsp+38h+bDaclDefaulted]; lpbDaclDefaulted
0x18006acc7  lea     r8, [rsp+38h+pDacl]; pDacl
0x18006accc  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x18006acd1  call    cs:__imp_GetSecurityDescriptorDacl
0x18006acd7  test    eax, eax
0x18006acd9  jnz     short loc_18006AD00
0x18006acdb  call    cs:__imp_GetLastError
0x18006ace1  mov     ebx, eax
0x18006ace3  test    eax, eax
0x18006ace5  jle     short loc_18006ACF0
0x18006ace7  movzx   ebx, ax
0x18006acea  or      ebx, 80070000h
0x18006acf0  test    ebx, ebx
0x18006acf2  jns     short loc_18006AD00
0x18006acf4  mov     r8d, ebx
0x18006acf7  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorDacl failed: 0x%x "...
0x18006acfe  jmp     short loc_18006ACAA
0x18006ad00  cmp     [rsp+38h+bDaclPresent], 0
0x18006ad05  jz      short loc_18006AD2B
0x18006ad07  mov     rdx, [rsp+38h+pDacl]; pAcl
0x18006ad0c  test    rdx, rdx
0x18006ad0f  jz      short loc_18006AD2B
0x18006ad11  mov     rcx, rsi; pSid2
0x18006ad14  call    ?UserHasExplicitAccess@CUserProfile@@CAJPEAXPEAU_ACL@@@Z; CUserProfile::UserHasExplicitAccess(void *,_ACL *)
0x18006ad19  mov     ebx, eax
0x18006ad1b  test    eax, eax
0x18006ad1d  jns     short loc_18006AD30
0x18006ad1f  lea     rdx, aUserhasexplici; "UserHasExplicitAccess failed: 0x%x in %"...
0x18006ad26  jmp     loc_18006ACA7
0x18006ad2b  mov     ebx, 1
0x18006ad30  cmp     [rsp+38h+pSecurityDescriptor], 0
0x18006ad36  jz      short loc_18006AD42
0x18006ad38  mov     rcx, [rsp+38h+pSecurityDescriptor]; Block
0x18006ad3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006ad42  mov     eax, ebx
0x18006ad44  mov     rbx, [rsp+38h+arg_0]
0x18006ad49  add     rsp, 30h
0x18006ad4d  pop     rsi
0x18006ad4e  retn
```
