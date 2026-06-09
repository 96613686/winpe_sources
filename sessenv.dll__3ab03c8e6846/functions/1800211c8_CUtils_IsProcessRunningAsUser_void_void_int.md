# CUtils::IsProcessRunningAsUser(void *,void *,int *)

- ea: `0x1800211c8`
- end: `0x180021333`
- name: `?IsProcessRunningAsUser@CUtils@@SAJPEAX0PEAH@Z`
- size: `363`
- prototype: `static int(void *, void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015924`

## callees

- `0x180003f30`
- `0x1800211c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002125e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002125e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002130a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002130a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800211fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800211fa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800212f8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800212f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021254`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800212cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021254`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800212cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021294`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021294`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021318`

## string_xrefs

- `0x180021282`: `GetTokenInformation failed: 0x%x in %s`
- `0x18002121d`: `OpenProcessToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::IsProcessRunningAsUser(void *a1, void *a2, int *a3)
{
  signed int v3; // ebx
  PSID *v6; // rdi
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-28h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  TokenInformationLength = 0;
  ReturnLength = 0;
  v6 = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(a1, 8u, &TokenHandle) )
    goto LABEL_18;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_18:
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      if ( v3 < 0 )
        goto LABEL_12;
    }
    v6 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v6 )
    {
      v3 = -2147024882;
      _DbgPrintMessage(8, "LocalAlloc failed: 0x%x in %s", 2147942414LL, "CUtils::IsProcessRunningAsUser");
      goto LABEL_20;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &ReturnLength) )
    {
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 < 0 )
      {
LABEL_12:
        _DbgPrintMessage(
          8,
          "GetTokenInformation failed: 0x%x in %s",
          (unsigned int)v3,
          "CUtils::IsProcessRunningAsUser");
        goto LABEL_20;
      }
    }
    *a3 = EqualSid(*v6, a2);
  }
  else
  {
    _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x in %s", (unsigned int)v3, "CUtils::IsProcessRunningAsUser");
  }
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800211c8  mov     rax, rsp
0x1800211cb  mov     [rax+8], rbx
0x1800211cf  mov     [rax+10h], rbp
0x1800211d3  push    rsi
0x1800211d4  push    rdi
0x1800211d5  push    r15
0x1800211d7  sub     rsp, 40h
0x1800211db  xor     ebx, ebx
0x1800211dd  mov     rsi, r8
0x1800211e0  mov     rbp, rdx
0x1800211e3  mov     [rax+20h], ebx
0x1800211e6  lea     r8, [rax-20h]; TokenHandle
0x1800211ea  mov     [rax-28h], ebx
0x1800211ed  xor     edi, edi
0x1800211ef  mov     [rax-20h], rbx
0x1800211f3  lea     r15d, [rbx+8]
0x1800211f7  mov     edx, r15d; DesiredAccess
0x1800211fa  call    cs:__imp_OpenProcessToken
0x180021200  test    eax, eax
0x180021202  jnz     short loc_18002123B
0x180021204  call    cs:__imp_GetLastError
0x18002120a  mov     ebx, eax
0x18002120c  test    eax, eax
0x18002120e  jle     short loc_180021219
0x180021210  movzx   ebx, ax
0x180021213  or      ebx, 80070000h
0x180021219  test    ebx, ebx
0x18002121b  jns     short loc_18002123B
0x18002121d  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: 0x%x in %s"
0x180021224  lea     r9, aCutilsIsproces; "CUtils::IsProcessRunningAsUser"
0x18002122b  mov     r8d, ebx
0x18002122e  mov     ecx, r15d; int
0x180021231  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021236  jmp     loc_180021300
0x18002123b  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180021240  lea     rax, [rsp+58h+TokenInformationLength]
0x180021245  xor     r9d, r9d; TokenInformationLength
0x180021248  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18002124d  xor     r8d, r8d; TokenInformation
0x180021250  lea     edx, [r9+1]; TokenInformationClass
0x180021254  call    cs:__imp_GetTokenInformation
0x18002125a  test    eax, eax
0x18002125c  jnz     short loc_18002128B
0x18002125e  call    cs:__imp_GetLastError
0x180021264  cmp     eax, 7Ah ; 'z'
0x180021267  jz      short loc_18002128B
0x180021269  call    cs:__imp_GetLastError
0x18002126f  mov     ebx, eax
0x180021271  test    eax, eax
0x180021273  jle     short loc_18002127E
0x180021275  movzx   ebx, ax
0x180021278  or      ebx, 80070000h
0x18002127e  test    ebx, ebx
0x180021280  jns     short loc_18002128B
0x180021282  lea     rdx, aGettokeninform_1; "GetTokenInformation failed: 0x%x in %s"
0x180021289  jmp     short loc_180021224
0x18002128b  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18002128f  mov     ecx, 40h ; '@'; uFlags
0x180021294  call    cs:__imp_LocalAlloc
0x18002129a  mov     rdi, rax
0x18002129d  test    rax, rax
0x1800212a0  jnz     short loc_1800212B3
0x1800212a2  mov     ebx, 8007000Eh
0x1800212a7  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x1800212ae  jmp     loc_180021224
0x1800212b3  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800212b8  lea     rax, [rsp+58h+var_28]
0x1800212bd  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800212c2  mov     r8, rdi; TokenInformation
0x1800212c5  mov     edx, 1; TokenInformationClass
0x1800212ca  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800212cf  call    cs:__imp_GetTokenInformation
0x1800212d5  test    eax, eax
0x1800212d7  jnz     short loc_1800212F2
0x1800212d9  call    cs:__imp_GetLastError
0x1800212df  mov     ebx, eax
0x1800212e1  test    eax, eax
0x1800212e3  jle     short loc_1800212EE
0x1800212e5  movzx   ebx, ax
0x1800212e8  or      ebx, 80070000h
0x1800212ee  test    ebx, ebx
0x1800212f0  js      short loc_180021282
0x1800212f2  mov     rcx, [rdi]; pSid1
0x1800212f5  mov     rdx, rbp; pSid2
0x1800212f8  call    cs:__imp_EqualSid
0x1800212fe  mov     [rsi], eax
0x180021300  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180021305  test    rcx, rcx
0x180021308  jz      short loc_180021310
0x18002130a  call    cs:__imp_CloseHandle
0x180021310  test    rdi, rdi
0x180021313  jz      short loc_18002131E
0x180021315  mov     rcx, rdi; hMem
0x180021318  call    cs:__imp_LocalFree
0x18002131e  mov     rbp, [rsp+58h+arg_8]
0x180021323  mov     eax, ebx
0x180021325  mov     rbx, [rsp+58h+arg_0]
0x18002132a  add     rsp, 40h
0x18002132e  pop     r15
0x180021330  pop     rdi
0x180021331  pop     rsi
0x180021332  retn
```
