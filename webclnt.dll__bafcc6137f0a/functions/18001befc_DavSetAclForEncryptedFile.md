# DavSetAclForEncryptedFile

- ea: `0x18001befc`
- end: `0x18001bfcd`
- name: `DavSetAclForEncryptedFile`
- size: `209`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001507c`
- `0x180016d24`
- `0x18001832c`
- `0x18001f190`
- `0x180024190`

## callees

- `0x18000b7dc`
- `0x18001befc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf77`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18001bf6d`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18001bf6d`
- `KERNEL32!LocalFree` at `0x18001bfba`
- `KERNEL32!LocalFree` at `0x18001bfba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001bf2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001bf2e`

## pseudocode

```c
__int64 __fastcall DavSetAclForEncryptedFile(LPCWSTR lpFileName)
{
  DWORD LastError; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  ULONG v6; // [rsp+38h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  pSecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GAGRGWGX;;;WD)", 1u, &pSecurityDescriptor, &v6) )
  {
    LastError = 0;
    if ( !SetFileSecurityW(lpFileName, 4u, pSecurityDescriptor) )
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 241;
        goto LABEL_9;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 240;
LABEL_9:
      WPP_SF_d(v3[2], v4, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
    }
  }
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18001befc  mov     rax, rsp
0x18001beff  mov     [rax+8], rbx
0x18001bf03  push    rdi
0x18001bf04  sub     rsp, 20h
0x18001bf08  mov     rdi, rcx
0x18001bf0b  mov     dword ptr [rax+10h], 0
0x18001bf12  lea     rcx, StringSecurityDescriptor; "D:(A;;GAGRGWGX;;;WD)"
0x18001bf19  mov     qword ptr [rax+18h], 0
0x18001bf21  lea     r9, [rax+10h]; SecurityDescriptorSize
0x18001bf25  mov     edx, 1; StringSDRevision
0x18001bf2a  lea     r8, [rax+18h]; SecurityDescriptor
0x18001bf2e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001bf34  test    eax, eax
0x18001bf36  jnz     short loc_18001BF60
0x18001bf38  call    cs:__imp_GetLastError
0x18001bf3e  mov     ebx, eax
0x18001bf40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf47  lea     rax, WPP_GLOBAL_Control
0x18001bf4e  cmp     rcx, rax
0x18001bf51  jz      short loc_18001BFB0
0x18001bf53  test    byte ptr [rcx+1Ch], 1
0x18001bf57  jz      short loc_18001BFB0
0x18001bf59  mov     edx, 0F0h
0x18001bf5e  jmp     short loc_18001BF9D
0x18001bf60  mov     r8, [rsp+28h+pSecurityDescriptor]; pSecurityDescriptor
0x18001bf65  xor     ebx, ebx
0x18001bf67  mov     rcx, rdi; lpFileName
0x18001bf6a  lea     edx, [rbx+4]; SecurityInformation
0x18001bf6d  call    cs:__imp_SetFileSecurityW
0x18001bf73  test    eax, eax
0x18001bf75  jnz     short loc_18001BFB0
0x18001bf77  call    cs:__imp_GetLastError
0x18001bf7d  mov     ebx, eax
0x18001bf7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf86  lea     rax, WPP_GLOBAL_Control
0x18001bf8d  cmp     rcx, rax
0x18001bf90  jz      short loc_18001BFB0
0x18001bf92  test    byte ptr [rcx+1Ch], 1
0x18001bf96  jz      short loc_18001BFB0
0x18001bf98  mov     edx, 0F1h
0x18001bf9d  mov     rcx, [rcx+10h]
0x18001bfa1  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001bfa8  mov     r9d, ebx
0x18001bfab  call    WPP_SF_d
0x18001bfb0  mov     rcx, [rsp+28h+pSecurityDescriptor]; hMem
0x18001bfb5  test    rcx, rcx
0x18001bfb8  jz      short loc_18001BFC0
0x18001bfba  call    cs:__imp_LocalFree
0x18001bfc0  mov     eax, ebx
0x18001bfc2  mov     rbx, [rsp+28h+arg_0]
0x18001bfc7  add     rsp, 20h
0x18001bfcb  pop     rdi
0x18001bfcc  retn
```
