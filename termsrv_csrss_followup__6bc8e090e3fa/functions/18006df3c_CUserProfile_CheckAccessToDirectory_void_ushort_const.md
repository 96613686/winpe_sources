# CUserProfile::CheckAccessToDirectory(void *,ushort const *)

- ea: `0x18006df3c`
- end: `0x18006e03c`
- name: `?CheckAccessToDirectory@CUserProfile@@CAJPEAXPEBG@Z`
- size: `256`
- prototype: `__int64 __fastcall(PSID pSid2, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006ea88`

## callees

- `0x180009940`
- `0x18003440c`
- `0x18006df3c`
- `0x18006e400`
- `0x18006e910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dfc1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18006dfb1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18006dfb1`

## string_xrefs

- `0x18006df8a`: `CUserProfile::CheckAccessToDirectory`
- `0x18006df80`: `GetFileSecurity failed: 0x%x in %s`
- `0x18006dfe3`: `GetSecurityDescriptorDacl failed: 0x%x in %s`
- `0x18006e00b`: `UserHasExplicitAccess failed: 0x%x in %s`

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
0x18006df3c  mov     r11, rsp
0x18006df3f  mov     [r11+8], rbx
0x18006df43  push    rsi
0x18006df44  sub     rsp, 30h
0x18006df48  mov     rax, rdx
0x18006df4b  mov     qword ptr [r11-18h], 0
0x18006df53  mov     rsi, rcx
0x18006df56  mov     qword ptr [r11-10h], 0
0x18006df5e  mov     rcx, rax; lpFileName
0x18006df61  mov     [rsp+38h+bDaclDefaulted], 0
0x18006df69  lea     rdx, [r11-18h]; void **
0x18006df6d  mov     [rsp+38h+bDaclPresent], 0
0x18006df75  call    ?GetFileSecurityW@CUserProfile@@CAJPEBGPEAPEAX@Z; CUserProfile::GetFileSecurityW(ushort const *,void * *)
0x18006df7a  mov     ebx, eax
0x18006df7c  test    eax, eax
0x18006df7e  jns     short loc_18006DF9D
0x18006df80  lea     rdx, aGetfilesecurit; "GetFileSecurity failed: 0x%x in %s"
0x18006df87  mov     r8d, eax
0x18006df8a  lea     r9, aCuserprofileCh; "CUserProfile::CheckAccessToDirectory"
0x18006df91  mov     ecx, 8; int
0x18006df96  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006df9b  jmp     short loc_18006E01C
0x18006df9d  mov     rcx, [rsp+38h+pSecurityDescriptor]; pSecurityDescriptor
0x18006dfa2  lea     r9, [rsp+38h+bDaclDefaulted]; lpbDaclDefaulted
0x18006dfa7  lea     r8, [rsp+38h+pDacl]; pDacl
0x18006dfac  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x18006dfb1  call    cs:__imp_GetSecurityDescriptorDacl
0x18006dfb8  nop     dword ptr [rax+rax+00h]
0x18006dfbd  test    eax, eax
0x18006dfbf  jnz     short loc_18006DFEC
0x18006dfc1  call    cs:__imp_GetLastError
0x18006dfc8  nop     dword ptr [rax+rax+00h]
0x18006dfcd  mov     ebx, eax
0x18006dfcf  test    eax, eax
0x18006dfd1  jle     short loc_18006DFDC
0x18006dfd3  movzx   ebx, ax
0x18006dfd6  or      ebx, 80070000h
0x18006dfdc  test    ebx, ebx
0x18006dfde  jns     short loc_18006DFEC
0x18006dfe0  mov     r8d, ebx
0x18006dfe3  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorDacl failed: 0x%x "...
0x18006dfea  jmp     short loc_18006DF8A
0x18006dfec  cmp     [rsp+38h+bDaclPresent], 0
0x18006dff1  jz      short loc_18006E017
0x18006dff3  mov     rdx, [rsp+38h+pDacl]; pAcl
0x18006dff8  test    rdx, rdx
0x18006dffb  jz      short loc_18006E017
0x18006dffd  mov     rcx, rsi; pSid2
0x18006e000  call    ?UserHasExplicitAccess@CUserProfile@@CAJPEAXPEAU_ACL@@@Z; CUserProfile::UserHasExplicitAccess(void *,_ACL *)
0x18006e005  mov     ebx, eax
0x18006e007  test    eax, eax
0x18006e009  jns     short loc_18006E01C
0x18006e00b  lea     rdx, aUserhasexplici; "UserHasExplicitAccess failed: 0x%x in %"...
0x18006e012  jmp     loc_18006DF87
0x18006e017  mov     ebx, 1
0x18006e01c  cmp     [rsp+38h+pSecurityDescriptor], 0
0x18006e022  jz      short loc_18006E02E
0x18006e024  mov     rcx, [rsp+38h+pSecurityDescriptor]; Block
0x18006e029  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e02e  mov     eax, ebx
0x18006e030  mov     rbx, [rsp+38h+arg_0]
0x18006e035  add     rsp, 30h
0x18006e039  pop     rsi
0x18006e03a  retn
```
