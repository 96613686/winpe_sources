# HrWriteManifestCOMEntry(ushort * const,void * const)

- ea: `0x18000fa80`
- end: `0x18000fb9b`
- name: `?HrWriteManifestCOMEntry@@YAJQEAGQEAX@Z`
- size: `283`
- prototype: `int(unsigned __int16 *const, void *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000daac`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000fa80`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fb10`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fb10`

## string_xrefs

- `0x18000fabe`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_CLASSES_ROOT\CLSID\%S\"\n        >\n      <registryValue\n          buildFilter=""\n          name=""\n          value="XWizard Factory Generated Class"\n          valueType="REG_SZ"\n          />\n      <securityDescriptor name="WRP_KEY_DEFAULT_SDDL"/>\n    </registryKey>\n    <registryKey\n        buildFilter=""\n        keyName="HKEY_CLASSES_ROOT\CLSID\%S\InProcServer32\"\n        >\n      <registryValue\n       `

## pseudocode

```c
__int64 __fastcall HrWriteManifestCOMEntry(unsigned __int16 *const a1, void *const a2)
{
  unsigned int v2; // ebx
  __int64 v4; // r8
  unsigned int LastErrorHRESULT; // eax
  int v6; // r8d
  PVOID *v7; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-3A8h] BYREF
  char Buffer[896]; // [rsp+40h] [rbp-398h] BYREF

  v2 = 0;
  if ( !a2 )
    goto LABEL_9;
  NumberOfBytesWritten = 0;
  sprintf_sfn(
    Buffer,
    0x372u,
    "    <registryKey\r\n"
    "        buildFilter=\"\"\r\n"
    "        keyName=\"HKEY_CLASSES_ROOT\\CLSID\\%S\\\"\r\n"
    "        >\r\n"
    "      <registryValue\r\n"
    "          buildFilter=\"\"\r\n"
    "          name=\"\"\r\n"
    "          value=\"XWizard Factory Generated Class\"\r\n"
    "          valueType=\"REG_SZ\"\r\n"
    "          />\r\n"
    "      <securityDescriptor name=\"WRP_KEY_DEFAULT_SDDL\"/>\r\n"
    "    </registryKey>\r\n"
    "    <registryKey\r\n"
    "        buildFilter=\"\"\r\n"
    "        keyName=\"HKEY_CLASSES_ROOT\\CLSID\\%S\\InProcServer32\\\"\r\n"
    "        >\r\n"
    "      <registryValue\r\n"
    "          buildFilter=\"\"\r\n"
    "          name=\"\"\r\n"
    "          value=\"%%SystemRoot%%\\system32\\xwizards.dll\"\r\n"
    "          valueType=\"REG_EXPAND_SZ\"\r\n"
    "          />\r\n"
    "      <registryValue\r\n"
    "          buildFilter=\"\"\r\n"
    "          name=\"ThreadingModel\"\r\n"
    "          value=\"Apartment\"\r\n"
    "          valueType=\"REG_SZ\"\r\n"
    "          />\r\n"
    "    </registryKey>\r\n",
    a1,
    a1);
  if ( (unsigned int)IsDuplicateManifestFileEntry(a2, Buffer) )
    goto LABEL_9;
  v4 = -1;
  do
    ++v4;
  while ( Buffer[v4] );
  if ( WriteFile(a2, Buffer, v4, &NumberOfBytesWritten, 0) )
    goto LABEL_9;
  LastErrorHRESULT = GetLastErrorHRESULT();
  v2 = LastErrorHRESULT;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v6, (unsigned int)Buffer, LastErrorHRESULT);
LABEL_9:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_D(v7[2], 22, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18000fa80  mov     [rsp+arg_10], rbx
0x18000fa85  mov     [rsp+arg_18], rbp
0x18000fa8a  push    rdi
0x18000fa8b  sub     rsp, 3D0h
0x18000fa92  mov     rax, cs:__security_cookie
0x18000fa99  xor     rax, rsp
0x18000fa9c  mov     [rsp+3D8h+var_18], rax
0x18000faa4  xor     ebx, ebx
0x18000faa6  lea     rbp, WPP_GLOBAL_Control
0x18000faad  mov     rdi, rdx
0x18000fab0  test    rdx, rdx
0x18000fab3  jz      loc_18000FB4A
0x18000fab9  mov     [rsp+3D8h+lpOverlapped], rcx
0x18000fabe  lea     r8, aRegistrykeyBui; "    <registryKey\r\n        buildFilter"...
0x18000fac5  mov     r9, rcx
0x18000fac8  mov     [rsp+3D8h+NumberOfBytesWritten], ebx
0x18000facc  lea     rcx, [rsp+3D8h+Buffer]; char *
0x18000fad1  mov     edx, 372h; unsigned __int64
0x18000fad6  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x18000fadb  lea     rdx, [rsp+3D8h+Buffer]; char *
0x18000fae0  mov     rcx, rdi; hFile
0x18000fae3  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x18000fae8  test    eax, eax
0x18000faea  jnz     short loc_18000FB4A
0x18000faec  lea     rax, [rsp+3D8h+Buffer]
0x18000faf1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000faf5  inc     r8; nNumberOfBytesToWrite
0x18000faf8  cmp     [rax+r8], bl
0x18000fafc  jnz     short loc_18000FAF5
0x18000fafe  lea     r9, [rsp+3D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fb03  mov     [rsp+3D8h+lpOverlapped], rbx; lpOverlapped
0x18000fb08  lea     rdx, [rsp+3D8h+Buffer]; lpBuffer
0x18000fb0d  mov     rcx, rdi; hFile
0x18000fb10  call    cs:__imp_WriteFile
0x18000fb16  test    eax, eax
0x18000fb18  jnz     short loc_18000FB4A
0x18000fb1a  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000fb1f  mov     ebx, eax
0x18000fb21  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb28  cmp     rcx, rbp
0x18000fb2b  jz      short loc_18000FB74
0x18000fb2d  test    byte ptr [rcx+1Ch], 4
0x18000fb31  jz      short loc_18000FB51
0x18000fb33  mov     rcx, [rcx+10h]
0x18000fb37  lea     r9, [rsp+3D8h+Buffer]
0x18000fb3c  mov     edx, 15h
0x18000fb41  mov     dword ptr [rsp+3D8h+lpOverlapped], eax
0x18000fb45  call    WPP_SF_sD
0x18000fb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb51  cmp     rcx, rbp
0x18000fb54  jz      short loc_18000FB74
0x18000fb56  test    byte ptr [rcx+1Ch], 10h
0x18000fb5a  jz      short loc_18000FB74
0x18000fb5c  mov     rcx, [rcx+10h]
0x18000fb60  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000fb67  mov     edx, 16h
0x18000fb6c  mov     r9d, ebx
0x18000fb6f  call    WPP_SF_D
0x18000fb74  mov     eax, ebx
0x18000fb76  mov     rcx, [rsp+3D8h+var_18]
0x18000fb7e  xor     rcx, rsp; StackCookie
0x18000fb81  call    __security_check_cookie
0x18000fb86  lea     r11, [rsp+3D8h+var_8]
0x18000fb8e  mov     rbx, [r11+20h]
0x18000fb92  mov     rbp, [r11+28h]
0x18000fb96  mov     rsp, r11
0x18000fb99  pop     rdi
0x18000fb9a  retn
```
