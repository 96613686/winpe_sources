# HrWriteManifestWrappedEntry(ushort * const,ushort * const,ushort * const,void * const)

- ea: `0x180010400`
- end: `0x18001050f`
- name: `?HrWriteManifestWrappedEntry@@YAJQEAG00QEAX@Z`
- size: `271`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, void *const)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007b28`
- `0x18000bac8`

## callees

- `0x180003b90`
- `0x180007820`
- `0x180010400`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001048e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001048e`

## string_xrefs

- `0x18001043f`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\XWizards\%S\%S\"\n        >\n      <registryValue\n          buildFilter=""\n          name="Wrapped CLSID"\n          value="%S"\n          valueType="REG_SZ"\n          />\n    </registryKey>\n`

## pseudocode

```c
__int64 __fastcall HrWriteManifestWrappedEntry(
        unsigned __int16 *const a1,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        void *const a4)
{
  unsigned int v4; // ebx
  __int64 v6; // r8
  unsigned int LastErrorHRESULT; // eax
  int v8; // r8d
  PVOID *v9; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1D8h] BYREF
  char Buffer[416]; // [rsp+40h] [rbp-1C8h] BYREF

  v4 = 0;
  if ( !a4 )
    goto LABEL_9;
  NumberOfBytesWritten = 0;
  sprintf_sfn(
    Buffer,
    0x196u,
    "    <registryKey\r\n"
    "        buildFilter=\"\"\r\n"
    "        keyName=\"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\XWizards\\%S\\%S\\\"\r\n"
    "        >\r\n"
    "      <registryValue\r\n"
    "          buildFilter=\"\"\r\n"
    "          name=\"Wrapped CLSID\"\r\n"
    "          value=\"%S\"\r\n"
    "          valueType=\"REG_SZ\"\r\n"
    "          />\r\n"
    "    </registryKey>\r\n",
    a1,
    a2,
    a3);
  if ( (unsigned int)IsDuplicateManifestFileEntry(a4, Buffer) )
    goto LABEL_9;
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( WriteFile(a4, Buffer, v6, &NumberOfBytesWritten, 0) )
    goto LABEL_9;
  LastErrorHRESULT = GetLastErrorHRESULT();
  v4 = LastErrorHRESULT;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v8, (unsigned int)Buffer, LastErrorHRESULT);
LABEL_9:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    WPP_SF_D(v9[2], 28, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180010400  push    rbx
0x180010402  push    rbp
0x180010403  push    rdi
0x180010404  sub     rsp, 1F0h
0x18001040b  mov     rax, cs:__security_cookie
0x180010412  xor     rax, rsp
0x180010415  mov     [rsp+208h+var_28], rax
0x18001041d  xor     ebx, ebx
0x18001041f  lea     rbp, WPP_GLOBAL_Control
0x180010426  mov     rdi, r9
0x180010429  test    r9, r9
0x18001042c  jz      loc_1800104C8
0x180010432  mov     [rsp+208h+var_1E0], r8
0x180010437  mov     r9, rcx
0x18001043a  mov     [rsp+208h+lpOverlapped], rdx
0x18001043f  lea     r8, aRegistrykeyBui_5; "    <registryKey\r\n        buildFilter"...
0x180010446  mov     edx, 196h; unsigned __int64
0x18001044b  mov     [rsp+208h+NumberOfBytesWritten], ebx
0x18001044f  lea     rcx, [rsp+208h+Buffer]; char *
0x180010454  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x180010459  lea     rdx, [rsp+208h+Buffer]; char *
0x18001045e  mov     rcx, rdi; hFile
0x180010461  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x180010466  test    eax, eax
0x180010468  jnz     short loc_1800104C8
0x18001046a  lea     rax, [rsp+208h+Buffer]
0x18001046f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010473  inc     r8; nNumberOfBytesToWrite
0x180010476  cmp     [rax+r8], bl
0x18001047a  jnz     short loc_180010473
0x18001047c  lea     r9, [rsp+208h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180010481  mov     [rsp+208h+lpOverlapped], rbx; lpOverlapped
0x180010486  lea     rdx, [rsp+208h+Buffer]; lpBuffer
0x18001048b  mov     rcx, rdi; hFile
0x18001048e  call    cs:__imp_WriteFile
0x180010494  test    eax, eax
0x180010496  jnz     short loc_1800104C8
0x180010498  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001049d  mov     ebx, eax
0x18001049f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104a6  cmp     rcx, rbp
0x1800104a9  jz      short loc_1800104F2
0x1800104ab  test    byte ptr [rcx+1Ch], 4
0x1800104af  jz      short loc_1800104CF
0x1800104b1  mov     rcx, [rcx+10h]
0x1800104b5  lea     r9, [rsp+208h+Buffer]
0x1800104ba  mov     edx, 1Bh
0x1800104bf  mov     dword ptr [rsp+208h+lpOverlapped], eax
0x1800104c3  call    WPP_SF_sD
0x1800104c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104cf  cmp     rcx, rbp
0x1800104d2  jz      short loc_1800104F2
0x1800104d4  test    byte ptr [rcx+1Ch], 10h
0x1800104d8  jz      short loc_1800104F2
0x1800104da  mov     rcx, [rcx+10h]
0x1800104de  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x1800104e5  mov     edx, 1Ch
0x1800104ea  mov     r9d, ebx
0x1800104ed  call    WPP_SF_D
0x1800104f2  mov     eax, ebx
0x1800104f4  mov     rcx, [rsp+208h+var_28]
0x1800104fc  xor     rcx, rsp; StackCookie
0x1800104ff  call    __security_check_cookie
0x180010504  add     rsp, 1F0h
0x18001050b  pop     rdi
0x18001050c  pop     rbp
0x18001050d  pop     rbx
0x18001050e  retn
```
