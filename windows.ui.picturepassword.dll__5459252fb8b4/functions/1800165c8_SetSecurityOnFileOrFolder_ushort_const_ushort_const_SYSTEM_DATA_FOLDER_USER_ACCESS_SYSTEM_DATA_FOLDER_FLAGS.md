# _SetSecurityOnFileOrFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS)

- ea: `0x1800165c8`
- end: `0x180016726`
- name: `?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(const WCHAR *, const wchar_t *, int, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180016314`
- `0x18001720c`

## callees

- `0x180002610`
- `0x1800092b8`
- `0x18000a1c8`
- `0x18000a254`
- `0x1800164b8`
- `0x1800165c8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016677`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016677`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800166d7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800166d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166fa`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180016699`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180016699`

## pseudocode

```c
__int64 __fastcall _SetSecurityOnFileOrFolder(const WCHAR *a1, const wchar_t *a2, int a3, char a4)
{
  int v5; // eax
  bool v6; // zf
  const wchar_t *v7; // r9
  int Error; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( a3 )
  {
    v6 = (a4 & 1) == 0;
    v7 = L"BU";
    if ( v6 )
      v7 = a2;
    v5 = StringCchPrintfW(StringSecurityDescriptor, 0x104u, (&off_180020CD0)[3 * a3], v7);
  }
  else
  {
    v5 = StringCchCopyW(
           StringSecurityDescriptor,
           0x104u,
           L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)");
  }
  Error = v5;
  if ( v5 >= 0 && !_IsSecurityOnFileOrFolderEqualToSDDL(a1, StringSecurityDescriptor) )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( SetFileSecurityW(a1, 7u, SecurityDescriptor) )
        goto LABEL_11;
      Error = ResultFromKnownLastError();
      if ( Error != -2147024894 )
      {
        if ( Error == -2147024891 )
          Error = 0;
        goto LABEL_17;
      }
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      if ( CreateDirectoryW(a1, &SecurityAttributes) )
LABEL_11:
        Error = 0;
      else
        Error = ResultFromKnownLastError();
LABEL_17:
      LocalFree(SecurityDescriptor);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800165c8  mov     [rsp-8+arg_10], rbx
0x1800165cd  mov     [rsp-8+arg_18], rdi
0x1800165d2  push    rbp
0x1800165d3  lea     rbp, [rsp-160h]
0x1800165db  sub     rsp, 260h
0x1800165e2  mov     rax, cs:__security_cookie
0x1800165e9  xor     rax, rsp
0x1800165ec  mov     [rbp+160h+var_10], rax
0x1800165f3  mov     rdi, rcx
0x1800165f6  lea     rcx, [rsp+260h+StringSecurityDescriptor]; unsigned __int16 *
0x1800165fb  test    r8d, r8d
0x1800165fe  jnz     short loc_180016613
0x180016600  mov     r8, cs:off_180020CD0; unsigned __int16 *
0x180016607  mov     edx, 104h; unsigned __int64
0x18001660c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016611  jmp     short loc_18001663E
0x180016613  movsxd  rax, r8d
0x180016616  test    r9b, 1
0x18001661a  lea     r9, aBu; "BU"
0x180016621  cmovz   r9, rdx
0x180016625  mov     edx, 104h; unsigned __int64
0x18001662a  lea     r8, [rax+rax*2]
0x18001662e  lea     rax, off_180020CD0; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x180016635  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180016639  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001663e  mov     ebx, eax
0x180016640  test    eax, eax
0x180016642  js      loc_180016700
0x180016648  lea     rdx, [rsp+260h+StringSecurityDescriptor]; lpString2
0x18001664d  mov     rcx, rdi; lpFileName
0x180016650  call    ?_IsSecurityOnFileOrFolderEqualToSDDL@@YA_NPEBG0@Z; _IsSecurityOnFileOrFolderEqualToSDDL(ushort const *,ushort const *)
0x180016655  test    al, al
0x180016657  jnz     loc_180016700
0x18001665d  xor     r9d, r9d; SecurityDescriptorSize
0x180016660  mov     [rsp+260h+SecurityDescriptor], 0
0x180016669  lea     r8, [rsp+260h+SecurityDescriptor]; SecurityDescriptor
0x18001666e  lea     rcx, [rsp+260h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180016673  lea     edx, [r9+1]; StringSDRevision
0x180016677  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001667d  test    eax, eax
0x18001667f  jnz     short loc_18001668C
0x180016681  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016686  mov     ebx, eax
0x180016688  test    eax, eax
0x18001668a  js      short loc_180016700
0x18001668c  mov     r8, [rsp+260h+SecurityDescriptor]; pSecurityDescriptor
0x180016691  mov     edx, 7; SecurityInformation
0x180016696  mov     rcx, rdi; lpFileName
0x180016699  call    cs:__imp_SetFileSecurityW
0x18001669f  test    eax, eax
0x1800166a1  jz      short loc_1800166A7
0x1800166a3  xor     ebx, ebx
0x1800166a5  jmp     short loc_1800166F5
0x1800166a7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800166ac  mov     ebx, eax
0x1800166ae  cmp     eax, 80070002h
0x1800166b3  jnz     short loc_1800166EA
0x1800166b5  mov     rax, [rsp+260h+SecurityDescriptor]
0x1800166ba  lea     rdx, [rsp+260h+SecurityAttributes]; lpSecurityAttributes
0x1800166bf  mov     [rsp+260h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800166c4  mov     rcx, rdi; lpPathName
0x1800166c7  xor     eax, eax
0x1800166c9  mov     qword ptr [rsp+260h+SecurityAttributes.nLength], 18h
0x1800166d2  mov     qword ptr [rsp+260h+SecurityAttributes.bInheritHandle], rax
0x1800166d7  call    cs:__imp_CreateDirectoryW
0x1800166dd  test    eax, eax
0x1800166df  jnz     short loc_1800166A3
0x1800166e1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800166e6  mov     ebx, eax
0x1800166e8  jmp     short loc_1800166F5
0x1800166ea  xor     ecx, ecx
0x1800166ec  cmp     ebx, 80070005h
0x1800166f2  cmovz   ebx, ecx
0x1800166f5  mov     rcx, [rsp+260h+SecurityDescriptor]; hMem
0x1800166fa  call    cs:__imp_LocalFree
0x180016700  mov     eax, ebx
0x180016702  mov     rcx, [rbp+160h+var_10]
0x180016709  xor     rcx, rsp; StackCookie
0x18001670c  call    __security_check_cookie
0x180016711  lea     r11, [rsp+260h+var_s0]
0x180016719  mov     rbx, [r11+20h]
0x18001671d  mov     rdi, [r11+28h]
0x180016721  mov     rsp, r11
0x180016724  pop     rbp
0x180016725  retn
```
