# BfspDeleteBootmgfwForceSha1Variable

- ea: `0x1800345e8`
- end: `0x1800347bd`
- name: `BfspDeleteBootmgfwForceSha1Variable`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180032518`

## callees

- `0x1800345e8`
- `0x1800366b8`
- `0x18003682c`
- `0x1800369e0`
- `0x18007ed40`

## import_xrefs

- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x1800346f5`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x1800346f5`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x180034741`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x180034741`
- `ntdll!NtQuerySystemInformation` at `0x180034655`
- `ntdll!NtQuerySystemInformation` at `0x180034655`
- `ntdll!RtlInitUnicodeString` at `0x1800346d7`
- `ntdll!RtlInitUnicodeString` at `0x1800346d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034777`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034793`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034777`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034793`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034786`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800347a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034786`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800347a2`

## string_xrefs

- `0x180034672`: `SeSystemEnvironmentPrivilege`
- `0x180034691`: `Failed to create privilege info for BootmgfwForceSHA1 cleanup.`
- `0x1800346b6`: `Failed to acquire SE_SYSTEM_ENVIRONMENT_PRIVILEGE for BootmgfwForceSHA1 cleanup.`
- `0x18003474b`: `Failed to delete BootmgfwForceSHA1 variable. Status: %#x`
- `0x180034754`: `Deleted BootmgfwForceSHA1 UEFI variable.`

## pseudocode

```c
NTSTATUS BfspDeleteBootmgfwForceSha1Variable()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  ULONG *Attributes; // [rsp+20h] [rbp-29h]
  ULONG ReturnLength; // [rsp+30h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-11h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-9h] BYREF
  const WCHAR *v8; // [rsp+48h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  GUID VendorGuid; // [rsp+60h] [rbp+17h] BYREF
  __int128 SystemInformation; // [rsp+70h] [rbp+27h] BYREF
  __int128 v12; // [rsp+80h] [rbp+37h]

  VendorGuid.Data1 = 2012912317;
  *(_DWORD *)&VendorGuid.Data2 = 1295123289;
  *(_DWORD *)VendorGuid.Data4 = -198680387;
  SystemInformation = 0;
  *(_DWORD *)&VendorGuid.Data4[4] = 1266192359;
  ReturnLength = 0;
  NewState = 0;
  v12 = 0;
  lpMem = 0;
  DestinationString = 0;
  result = NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  if ( result >= 0 && (_DWORD)v12 == 2 )
  {
    v8 = L"SeSystemEnvironmentPrivilege";
    if ( (unsigned int)BfspCreateTokenPrivilegesInformation(&v8, 1, 1, &NewState) )
    {
      if ( (unsigned int)BfspAdjustTokenPrivileges(NewState, (struct _TOKEN_PRIVILEGES **)&lpMem) )
      {
        ReturnLength = 0;
        RtlInitUnicodeString(&DestinationString, L"BootmgfwForceSHA1");
        result = NtQuerySystemEnvironmentValueEx(&DestinationString, &VendorGuid, 0, &ReturnLength, 0);
        if ( result != -1073741568 )
        {
          if ( (int)(result + 0x80000000) < 0 || result == -1073741789 )
          {
            LODWORD(Attributes) = 1;
            v1 = NtSetSystemEnvironmentValueEx(&DestinationString, &VendorGuid, 0, 0, Attributes);
            if ( v1 >= 0 )
              result = BfspLogMessage(2, L"Deleted BootmgfwForceSHA1 UEFI variable.");
            else
              result = BfspLogMessage(3, L"Failed to delete BootmgfwForceSHA1 variable. Status: %#x", (unsigned int)v1);
          }
          else
          {
            result = BfspLogMessage(3, L"Failed to query BootmgfwForceSHA1 variable. Status: %#x", (unsigned int)result);
          }
        }
      }
      else
      {
        result = BfspLogMessage(3, L"Failed to acquire SE_SYSTEM_ENVIRONMENT_PRIVILEGE for BootmgfwForceSHA1 cleanup.");
      }
      if ( lpMem )
      {
        BfspAdjustTokenPrivileges((PTOKEN_PRIVILEGES)lpMem, 0);
        ProcessHeap = GetProcessHeap();
        result = HeapFree(ProcessHeap, 0, lpMem);
      }
    }
    else
    {
      result = BfspLogMessage(3, L"Failed to create privilege info for BootmgfwForceSHA1 cleanup.");
    }
    if ( NewState )
    {
      v3 = GetProcessHeap();
      return HeapFree(v3, 0, NewState);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800345e8  push    rbp
0x1800345ea  lea     rbp, [rsp-57h]
0x1800345ef  sub     rsp, 0A0h
0x1800345f6  mov     rax, cs:__security_cookie
0x1800345fd  xor     rax, rsp
0x180034600  mov     [rbp+57h+var_10], rax
0x180034604  xorps   xmm0, xmm0
0x180034607  mov     [rbp+57h+VendorGuid.Data1], 77FA9ABDh
0x18003460e  xor     r9d, r9d; ReturnLength
0x180034611  mov     dword ptr [rbp+57h+VendorGuid.Data2], 4D320359h
0x180034618  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18003461c  mov     dword ptr [rbp+57h+VendorGuid.Data4], 0F42860BDh
0x180034623  movups  [rbp+57h+SystemInformation], xmm0
0x180034627  mov     dword ptr [rbp+57h+VendorGuid.Data4+4], 4B788FE7h
0x18003462e  lea     r8d, [r9+20h]; SystemInformationLength
0x180034632  mov     [rbp+57h+ReturnLength], 0
0x180034639  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18003463d  mov     [rbp+57h+NewState], 0
0x180034645  movups  [rbp+57h+var_20], xmm0
0x180034649  mov     [rbp+57h+lpMem], 0
0x180034651  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180034655  call    cs:__imp_NtQuerySystemInformation
0x18003465b  test    eax, eax
0x18003465d  js      loc_1800347A8
0x180034663  cmp     dword ptr [rbp+57h+var_20], 2
0x180034667  jnz     loc_1800347A8
0x18003466d  mov     edx, 1
0x180034672  lea     rax, Name; "SeSystemEnvironmentPrivilege"
0x180034679  mov     r8d, edx
0x18003467c  mov     [rbp+57h+var_58], rax
0x180034680  lea     r9, [rbp+57h+NewState]
0x180034684  lea     rcx, [rbp+57h+var_58]
0x180034688  call    BfspCreateTokenPrivilegesInformation
0x18003468d  test    eax, eax
0x18003468f  jnz     short loc_1800346A5
0x180034691  lea     rdx, aFailedToCreate_2; "Failed to create privilege info for Boo"...
0x180034698  lea     ecx, [rax+3]
0x18003469b  call    BfspLogMessage
0x1800346a0  jmp     loc_18003478C
0x1800346a5  mov     rcx, [rbp+57h+NewState]; NewState
0x1800346a9  lea     rdx, [rbp+57h+lpMem]
0x1800346ad  call    BfspAdjustTokenPrivileges
0x1800346b2  test    eax, eax
0x1800346b4  jnz     short loc_1800346C5
0x1800346b6  lea     rdx, aFailedToAcquir; "Failed to acquire SE_SYSTEM_ENVIRONMENT"...
0x1800346bd  lea     ecx, [rax+3]
0x1800346c0  jmp     loc_180034760
0x1800346c5  lea     rdx, SourceString; "BootmgfwForceSHA1"
0x1800346cc  mov     [rbp+57h+ReturnLength], 0
0x1800346d3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800346d7  call    cs:__imp_RtlInitUnicodeString
0x1800346dd  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1800346e1  mov     [rsp+0A0h+Attributes], 0; Attributes
0x1800346ea  xor     r8d, r8d; Value
0x1800346ed  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x1800346f1  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x1800346f5  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x1800346fb  cmp     eax, 0C0000100h
0x180034700  jz      short loc_180034765
0x180034702  mov     edx, 80000000h
0x180034707  lea     ecx, [rax+rdx]
0x18003470a  test    edx, ecx
0x18003470c  jnz     short loc_18003472B
0x18003470e  cmp     eax, 0C0000023h
0x180034713  jz      short loc_18003472B
0x180034715  lea     rdx, aFailedToQueryB; "Failed to query BootmgfwForceSHA1 varia"...
0x18003471c  mov     r8d, eax
0x18003471f  mov     ecx, 3
0x180034724  call    BfspLogMessage
0x180034729  jmp     short loc_180034765
0x18003472b  xor     r9d, r9d; ReturnLength
0x18003472e  mov     dword ptr [rsp+0A0h+Attributes], 1; Attributes
0x180034736  xor     r8d, r8d; Value
0x180034739  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x18003473d  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x180034741  call    cs:__imp_NtSetSystemEnvironmentValueEx
0x180034747  test    eax, eax
0x180034749  jns     short loc_180034754
0x18003474b  lea     rdx, aFailedToDelete; "Failed to delete BootmgfwForceSHA1 vari"...
0x180034752  jmp     short loc_18003471C
0x180034754  lea     rdx, aDeletedBootmgf; "Deleted BootmgfwForceSHA1 UEFI variable"...
0x18003475b  mov     ecx, 2
0x180034760  call    BfspLogMessage
0x180034765  cmp     [rbp+57h+lpMem], 0
0x18003476a  jz      short loc_18003478C
0x18003476c  mov     rcx, [rbp+57h+lpMem]; NewState
0x180034770  xor     edx, edx
0x180034772  call    BfspAdjustTokenPrivileges
0x180034777  call    cs:__imp_GetProcessHeap
0x18003477d  mov     r8, [rbp+57h+lpMem]; lpMem
0x180034781  xor     edx, edx; dwFlags
0x180034783  mov     rcx, rax; hHeap
0x180034786  call    cs:__imp_HeapFree
0x18003478c  cmp     [rbp+57h+NewState], 0
0x180034791  jz      short loc_1800347A8
0x180034793  call    cs:__imp_GetProcessHeap
0x180034799  mov     r8, [rbp+57h+NewState]; lpMem
0x18003479d  xor     edx, edx; dwFlags
0x18003479f  mov     rcx, rax; hHeap
0x1800347a2  call    cs:__imp_HeapFree
0x1800347a8  mov     rcx, [rbp+57h+var_10]
0x1800347ac  xor     rcx, rsp; StackCookie
0x1800347af  call    __security_check_cookie
0x1800347b4  add     rsp, 0A0h
0x1800347bb  pop     rbp
0x1800347bc  retn
```
