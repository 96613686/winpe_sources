# DumpRpcCaller(void *)

- ea: `0x18004c0ec`
- end: `0x18004c339`
- name: `?DumpRpcCaller@@YAJPEAX@Z`
- size: `589`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d190`

## callees

- `0x18000bde0`
- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18004c0ec`
- `0x180063ef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c2d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c2e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c2d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c2e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c1ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c25e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c25e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c155`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c1e5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c155`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c1e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004c28c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004c28c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18004c24e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18004c24e`

## pseudocode

```c
__int64 __fastcall DumpRpcCaller(void *a1)
{
  unsigned int v2; // ebx
  signed int v3; // eax
  PSID *v4; // rdi
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-CCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[1024]; // [rsp+850h] [rbp+750h] BYREF

  TokenInformationLength = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  StringSid = 0;
  if ( GetTokenInformation(a1, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v2 = -2147418113;
    goto LABEL_19;
  }
  if ( GetLastError() == 122 )
  {
    v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v4 )
    {
      v2 = -2147024882;
      goto LABEL_19;
    }
    if ( !GetTokenInformation(a1, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_9;
    TokenInformationLength = 1024;
    cchReferencedDomainName = 1024;
    if ( !LookupAccountSidLocalW(
            *v4,
            Name,
            &TokenInformationLength,
            ReferencedDomainName,
            &cchReferencedDomainName,
            &peUse) )
    {
      if ( GetLastError() != 1332 )
        goto LABEL_9;
      StringCchCopyW(Name, 0x400u, L"NONE_MAPPED");
    }
    if ( ConvertSidToStringSidW(*v4, &StringSid) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(69) )
        FileLogAdd(L"RPC Caller is %s\\%s (%s)\n", ReferencedDomainName, Name, StringSid);
      v2 = 0;
      goto LABEL_18;
    }
LABEL_9:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    LocalFree(v4);
    goto LABEL_19;
  }
  v3 = GetLastError();
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
LABEL_19:
  if ( StringSid )
    LocalFree(StringSid);
  if ( (v2 & 0x80000000) != 0 && (unsigned __int8)FileLogAllowEntry(69) )
    FileLogAdd(L"*** Couldn't dump RPC caller.  The error was: %d\n", v2);
  return v2;
}

```

## disassembly

```asm
0x18004c0ec  mov     [rsp-8+arg_8], rbx
0x18004c0f1  mov     [rsp-8+arg_10], rdi
0x18004c0f6  push    rbp
0x18004c0f7  lea     rbp, [rsp-0F60h]
0x18004c0ff  mov     eax, 1060h
0x18004c104  call    _alloca_probe
0x18004c109  sub     rsp, rax
0x18004c10c  mov     rax, cs:__security_cookie
0x18004c113  xor     rax, rsp
0x18004c116  mov     [rbp+0F60h+var_10], rax
0x18004c11d  xor     r9d, r9d; TokenInformationLength
0x18004c120  mov     [rsp+1060h+TokenInformationLength], 0
0x18004c128  lea     rax, [rsp+1060h+TokenInformationLength]
0x18004c12d  mov     [rsp+1060h+cchReferencedDomainName], 0
0x18004c135  xor     r8d, r8d; TokenInformation
0x18004c138  mov     [rsp+1060h+var_1028], 0
0x18004c140  mov     rbx, rcx
0x18004c143  mov     [rsp+1060h+StringSid], 0
0x18004c14c  lea     edx, [r9+1]; TokenInformationClass
0x18004c150  mov     [rsp+1060h+ReturnLength], rax; ReturnLength
0x18004c155  call    cs:__imp_GetTokenInformation
0x18004c15c  nop     dword ptr [rax+rax+00h]
0x18004c161  test    eax, eax
0x18004c163  jz      short loc_18004C16F
0x18004c165  mov     ebx, 8000FFFFh
0x18004c16a  jmp     loc_18004C2DC
0x18004c16f  call    cs:__imp_GetLastError
0x18004c176  nop     dword ptr [rax+rax+00h]
0x18004c17b  cmp     eax, 7Ah ; 'z'
0x18004c17e  jz      short loc_18004C1A4
0x18004c180  call    cs:__imp_GetLastError
0x18004c187  nop     dword ptr [rax+rax+00h]
0x18004c18c  mov     ebx, eax
0x18004c18e  test    eax, eax
0x18004c190  jle     loc_18004C2DC
0x18004c196  movzx   ebx, ax
0x18004c199  or      ebx, 80070000h
0x18004c19f  jmp     loc_18004C2DC
0x18004c1a4  mov     edx, [rsp+1060h+TokenInformationLength]; uBytes
0x18004c1a8  mov     ecx, 40h ; '@'; uFlags
0x18004c1ad  call    cs:__imp_LocalAlloc
0x18004c1b4  nop     dword ptr [rax+rax+00h]
0x18004c1b9  mov     rdi, rax
0x18004c1bc  test    rax, rax
0x18004c1bf  jnz     short loc_18004C1CB
0x18004c1c1  mov     ebx, 8007000Eh
0x18004c1c6  jmp     loc_18004C2DC
0x18004c1cb  mov     r9d, [rsp+1060h+TokenInformationLength]; TokenInformationLength
0x18004c1d0  lea     rax, [rsp+1060h+TokenInformationLength]
0x18004c1d5  mov     r8, rdi; TokenInformation
0x18004c1d8  mov     [rsp+1060h+ReturnLength], rax; ReturnLength
0x18004c1dd  mov     edx, 1; TokenInformationClass
0x18004c1e2  mov     rcx, rbx; TokenHandle
0x18004c1e5  call    cs:__imp_GetTokenInformation
0x18004c1ec  nop     dword ptr [rax+rax+00h]
0x18004c1f1  test    eax, eax
0x18004c1f3  jnz     short loc_18004C219
0x18004c1f5  call    cs:__imp_GetLastError
0x18004c1fc  nop     dword ptr [rax+rax+00h]
0x18004c201  mov     ebx, eax
0x18004c203  test    eax, eax
0x18004c205  jle     loc_18004C2CD
0x18004c20b  movzx   ebx, ax
0x18004c20e  or      ebx, 80070000h
0x18004c214  jmp     loc_18004C2CD
0x18004c219  lea     rax, [rsp+1060h+var_1028]
0x18004c21e  mov     ebx, 400h
0x18004c223  mov     [rsp+1060h+peUse], rax; peUse
0x18004c228  lea     r9, [rbp+0F60h+ReferencedDomainName]; ReferencedDomainName
0x18004c22f  lea     rax, [rsp+1060h+cchReferencedDomainName]
0x18004c234  mov     [rsp+1060h+TokenInformationLength], ebx
0x18004c238  mov     [rsp+1060h+cchReferencedDomainName], ebx
0x18004c23c  lea     r8, [rsp+1060h+TokenInformationLength]; cchName
0x18004c241  mov     rcx, [rdi]; Sid
0x18004c244  lea     rdx, [rsp+1060h+Name]; Name
0x18004c249  mov     [rsp+1060h+ReturnLength], rax; cchReferencedDomainName
0x18004c24e  call    cs:__imp_LookupAccountSidLocalW
0x18004c255  nop     dword ptr [rax+rax+00h]
0x18004c25a  test    eax, eax
0x18004c25c  jnz     short loc_18004C284
0x18004c25e  call    cs:__imp_GetLastError
0x18004c265  nop     dword ptr [rax+rax+00h]
0x18004c26a  cmp     eax, 534h
0x18004c26f  jnz     short loc_18004C1F5
0x18004c271  lea     r8, aNoneMapped; "NONE_MAPPED"
0x18004c278  mov     edx, ebx; unsigned __int64
0x18004c27a  lea     rcx, [rsp+1060h+Name]; unsigned __int16 *
0x18004c27f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c284  mov     rcx, [rdi]; Sid
0x18004c287  lea     rdx, [rsp+1060h+StringSid]; StringSid
0x18004c28c  call    cs:__imp_ConvertSidToStringSidW
0x18004c293  nop     dword ptr [rax+rax+00h]
0x18004c298  test    eax, eax
0x18004c29a  jz      loc_18004C1F5
0x18004c2a0  mov     ecx, 45h ; 'E'
0x18004c2a5  call    FileLogAllowEntry
0x18004c2aa  test    al, al
0x18004c2ac  jz      short loc_18004C2CB
0x18004c2ae  mov     r9, [rsp+1060h+StringSid]
0x18004c2b3  lea     r8, [rsp+1060h+Name]
0x18004c2b8  lea     rdx, [rbp+0F60h+ReferencedDomainName]
0x18004c2bf  lea     rcx, aRpcCallerIsSSS; "RPC Caller is %s\\%s (%s)\n"
0x18004c2c6  call    FileLogAdd
0x18004c2cb  xor     ebx, ebx
0x18004c2cd  mov     rcx, rdi; hMem
0x18004c2d0  call    cs:__imp_LocalFree
0x18004c2d7  nop     dword ptr [rax+rax+00h]
0x18004c2dc  mov     rcx, [rsp+1060h+StringSid]; hMem
0x18004c2e1  test    rcx, rcx
0x18004c2e4  jz      short loc_18004C2F2
0x18004c2e6  call    cs:__imp_LocalFree
0x18004c2ed  nop     dword ptr [rax+rax+00h]
0x18004c2f2  test    ebx, ebx
0x18004c2f4  jns     short loc_18004C312
0x18004c2f6  mov     ecx, 45h ; 'E'
0x18004c2fb  call    FileLogAllowEntry
0x18004c300  test    al, al
0x18004c302  jz      short loc_18004C312
0x18004c304  mov     edx, ebx
0x18004c306  lea     rcx, aCouldnTDumpRpc; "*** Couldn't dump RPC caller.  The erro"...
0x18004c30d  call    FileLogAdd
0x18004c312  mov     eax, ebx
0x18004c314  mov     rcx, [rbp+0F60h+var_10]
0x18004c31b  xor     rcx, rsp; StackCookie
0x18004c31e  call    __security_check_cookie
0x18004c323  lea     r11, [rsp+1060h+var_s0]
0x18004c32b  mov     rbx, [r11+18h]
0x18004c32f  mov     rdi, [r11+20h]
0x18004c333  mov     rsp, r11
0x18004c336  pop     rbp
0x18004c337  retn
```
