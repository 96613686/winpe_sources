# WriteACLToSetupLog

- ea: `0x18028ae68`
- end: `0x18028aebd`
- name: `WriteACLToSetupLog`
- size: `85`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800edf90`
- `0x18028acd0`
- `0x180383870`

## callees

- `0x18028ae68`
- `0x18028aec4`
- `0x18028b0e8`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18067721e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18067721e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180677349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180677349`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180677239`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180677239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180677311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067733a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180677311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18067733a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1806771d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1806771d5`
- `api-ms-win-security-base-l1-1-0!QuerySecurityAccessMask` at `0x1806771a4`
- `api-ms-win-security-base-l1-1-0!QuerySecurityAccessMask` at `0x1806771a4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18067720a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180677267`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18067720a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180677267`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1806772a0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1806772a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1806772ea`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1806772ea`

## string_xrefs

- `0x18067731f`: `%s: Failed to convert Dacl to Sddl\n`
- `0x180677328`: `%s: Null Dacl\n`
- `0x18067735e`: `%s: Unable to open to get Dacl\n`
- `0x1806772ba`: `%s: No Dacl\n`
- `0x180677301`: `%s: Dacl: %s\n`

## pseudocode

```c
int __fastcall WriteACLToSetupLog(LPCWSTR lpFileName)
{
  int result; // eax
  HANDLE FileW; // rsi
  HLOCAL v4; // rdi
  const wchar_t *v5; // rcx
  DWORD nLengthNeeded; // [rsp+40h] [rbp-30h] BYREF
  DWORD DesiredAccess; // [rsp+44h] [rbp-2Ch] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-20h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp-18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+5Ch] [rbp-14h] BYREF

  result = IsGuimodeSetupRunning();
  if ( result )
  {
    DesiredAccess = 0;
    QuerySecurityAccessMask(7u, &DesiredAccess);
    FileW = CreateFileW(lpFileName, DesiredAccess, 7u, 0, 3u, 0, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      nLengthNeeded = 0;
      if ( GetKernelObjectSecurity(FileW, 7u, 0, 0, &nLengthNeeded) )
        return CloseHandle(FileW);
      if ( GetLastError() != 122 )
        return CloseHandle(FileW);
      v4 = LocalAlloc(0x40u, nLengthNeeded);
      if ( !v4 )
        return CloseHandle(FileW);
      if ( GetKernelObjectSecurity(FileW, 7u, v4, nLengthNeeded, &nLengthNeeded) )
      {
        bDaclPresent = 0;
        bDaclDefaulted = 0;
        pDacl = 0;
        if ( GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          if ( bDaclPresent )
          {
            if ( pDacl )
            {
              StringSecurityDescriptor = 0;
              if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v4, 1u, 7u, &StringSecurityDescriptor, 0) )
              {
                WriteSetupErrorLogEntry(L"%s: Dacl: %s\n", lpFileName, StringSecurityDescriptor);
                LocalFree(StringSecurityDescriptor);
              }
              else
              {
                WriteSetupErrorLogEntry(L"%s: Failed to convert Dacl to Sddl\n", lpFileName);
              }
              goto LABEL_16;
            }
            v5 = L"%s: Null Dacl\n";
          }
          else
          {
            v5 = L"%s: No Dacl\n";
          }
          WriteSetupErrorLogEntry(v5, lpFileName);
        }
      }
LABEL_16:
      LocalFree(v4);
      return CloseHandle(FileW);
    }
    return WriteSetupErrorLogEntry(L"%s: Unable to open to get Dacl\n", lpFileName);
  }
  return result;
}

```

## disassembly

```asm
0x18028ae68  mov     [rsp-18h+arg_8], rbx
0x18028ae6d  mov     [rsp-18h+arg_10], rsi
0x18028ae72  push    rbp
0x18028ae73  push    rdi
0x18028ae74  push    r15
0x18028ae76  mov     rbp, rsp
0x18028ae79  sub     rsp, 70h
0x18028ae7d  mov     rax, cs:__security_cookie
0x18028ae84  xor     rax, rsp
0x18028ae87  mov     [rbp+var_10], rax
0x18028ae8b  mov     rbx, rcx
0x18028ae8e  call    IsGuimodeSetupRunning
0x18028ae93  test    eax, eax
0x18028ae95  jnz     loc_180677190
0x18028ae9b  mov     rcx, [rbp+var_10]
0x18028ae9f  xor     rcx, rsp; StackCookie
0x18028aea2  call    __security_check_cookie
0x18028aea7  lea     r11, [rsp+70h+var_s0]
0x18028aeac  mov     rbx, [r11+28h]
0x18028aeb0  mov     rsi, [r11+30h]
0x18028aeb4  mov     rsp, r11
0x18028aeb7  pop     r15
0x18028aeb9  pop     rdi
0x18028aeba  pop     rbp
0x18028aebb  retn
0x180677190  mov     r15d, 7
0x180677196  mov     [rbp+DesiredAccess], 0
0x18067719d  mov     ecx, r15d; SecurityInformation
0x1806771a0  lea     rdx, [rbp+DesiredAccess]; DesiredAccess
0x1806771a4  call    cs:__imp_QuerySecurityAccessMask
0x1806771ab  nop     dword ptr [rax+rax+00h]
0x1806771b0  mov     edx, [rbp+DesiredAccess]; dwDesiredAccess
0x1806771b3  xor     r9d, r9d; lpSecurityAttributes
0x1806771b6  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1806771bf  mov     r8d, r15d; dwShareMode
0x1806771c2  mov     [rsp+70h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1806771ca  mov     rcx, rbx; lpFileName
0x1806771cd  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x1806771d5  call    cs:__imp_CreateFileW
0x1806771dc  nop     dword ptr [rax+rax+00h]
0x1806771e1  mov     rsi, rax
0x1806771e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1806771e8  jz      loc_18067735B
0x1806771ee  lea     rax, [rbp+nLengthNeeded]
0x1806771f2  mov     [rbp+nLengthNeeded], 0
0x1806771f9  xor     r9d, r9d; nLength
0x1806771fc  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpnLengthNeeded
0x180677201  xor     r8d, r8d; pSecurityDescriptor
0x180677204  mov     edx, r15d; RequestedInformation
0x180677207  mov     rcx, rsi; Handle
0x18067720a  call    cs:__imp_GetKernelObjectSecurity
0x180677211  nop     dword ptr [rax+rax+00h]
0x180677216  test    eax, eax
0x180677218  jnz     loc_180677346
0x18067721e  call    cs:__imp_GetLastError
0x180677225  nop     dword ptr [rax+rax+00h]
0x18067722a  cmp     eax, 7Ah ; 'z'
0x18067722d  jnz     loc_180677346
0x180677233  mov     edx, [rbp+nLengthNeeded]; uBytes
0x180677236  lea     ecx, [rax-3Ah]; uFlags
0x180677239  call    cs:__imp_LocalAlloc
0x180677240  nop     dword ptr [rax+rax+00h]
0x180677245  mov     rdi, rax
0x180677248  test    rax, rax
0x18067724b  jz      loc_180677346
0x180677251  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180677255  lea     rax, [rbp+nLengthNeeded]
0x180677259  mov     r8, rdi; pSecurityDescriptor
0x18067725c  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpnLengthNeeded
0x180677261  mov     edx, r15d; RequestedInformation
0x180677264  mov     rcx, rsi; Handle
0x180677267  call    cs:__imp_GetKernelObjectSecurity
0x18067726e  nop     dword ptr [rax+rax+00h]
0x180677273  test    eax, eax
0x180677275  jz      loc_180677337
0x18067727b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18067727f  mov     [rbp+bDaclPresent], 0
0x180677286  lea     r8, [rbp+pDacl]; pDacl
0x18067728a  mov     [rbp+bDaclDefaulted], 0
0x180677291  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180677295  mov     [rbp+pDacl], 0
0x18067729d  mov     rcx, rdi; pSecurityDescriptor
0x1806772a0  call    cs:__imp_GetSecurityDescriptorDacl
0x1806772a7  nop     dword ptr [rax+rax+00h]
0x1806772ac  test    eax, eax
0x1806772ae  jz      loc_180677337
0x1806772b4  cmp     [rbp+bDaclPresent], 0
0x1806772b8  jnz     short loc_1806772C3
0x1806772ba  lea     rcx, aSNoDacl; "%s: No Dacl\n"
0x1806772c1  jmp     short loc_18067732F
0x1806772c3  cmp     [rbp+pDacl], 0
0x1806772c8  jz      short loc_180677328
0x1806772ca  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1806772ce  mov     [rbp+StringSecurityDescriptor], 0
0x1806772d6  mov     r8d, r15d; SecurityInformation
0x1806772d9  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; StringSecurityDescriptorLen
0x1806772e2  mov     edx, 1; RequestedStringSDRevision
0x1806772e7  mov     rcx, rdi; SecurityDescriptor
0x1806772ea  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1806772f1  nop     dword ptr [rax+rax+00h]
0x1806772f6  mov     rdx, rbx
0x1806772f9  test    eax, eax
0x1806772fb  jz      short loc_18067731F
0x1806772fd  mov     r8, [rbp+StringSecurityDescriptor]
0x180677301  lea     rcx, aSDaclS; "%s: Dacl: %s\n"
0x180677308  call    WriteSetupErrorLogEntry
0x18067730d  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180677311  call    cs:__imp_LocalFree
0x180677318  nop     dword ptr [rax+rax+00h]
0x18067731d  jmp     short loc_180677337
0x18067731f  lea     rcx, aSFailedToConve; "%s: Failed to convert Dacl to Sddl\n"
0x180677326  jmp     short loc_180677332
0x180677328  lea     rcx, aSNullDacl; "%s: Null Dacl\n"
0x18067732f  mov     rdx, rbx
0x180677332  call    WriteSetupErrorLogEntry
0x180677337  mov     rcx, rdi; hMem
0x18067733a  call    cs:__imp_LocalFree
0x180677341  nop     dword ptr [rax+rax+00h]
0x180677346  mov     rcx, rsi; hObject
0x180677349  call    cs:__imp_CloseHandle
0x180677350  nop     dword ptr [rax+rax+00h]
0x180677355  nop
0x180677356  jmp     loc_18028AE9B
0x18067735b  mov     rdx, rbx
0x18067735e  lea     rcx, aSUnableToOpenT; "%s: Unable to open to get Dacl\n"
0x180677365  call    WriteSetupErrorLogEntry
0x18067736a  nop
0x18067736b  jmp     loc_18028AE9B
```
