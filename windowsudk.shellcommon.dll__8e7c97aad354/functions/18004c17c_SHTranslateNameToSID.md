# SHTranslateNameToSID

- ea: `0x18004c17c`
- end: `0x18004c2d0`
- name: `SHTranslateNameToSID`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c0e8`

## callees

- `0x18004c17c`
- `0x18033b018`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004c272`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004c272`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004c297`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004c297`
- `ntdll!RtlInitUnicodeString` at `0x18004c206`
- `ntdll!RtlInitUnicodeString` at `0x18004c206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c2b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c2b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c27c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004c1c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004c1c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004c241`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004c24b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004c241`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004c24b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004c255`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004c255`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18004c231`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18004c231`

## pseudocode

```c
__int64 __fastcall SHTranslateNameToSID(struct _LSA_TRANSLATED_SID2 *a1, _QWORD *a2)
{
  NTSTATUS v3; // eax
  unsigned int Error; // ebx
  NTSTATUS v6; // eax
  DWORD LengthSid; // ebx
  void *v8; // rax
  void *v9; // rdi
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+90h] [rbp+20h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+28h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+A0h] [rbp+30h] BYREF

  Sids = a1;
  *a2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  Error = v3 | 0x10000000;
  if ( v3 >= 0 )
  {
    ReferencedDomains = 0;
    Sids = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"CDFAccount");
    v6 = LsaLookupNames2(
           PolicyHandle,
           0x80000000,
           1u,
           (PLSA_UNICODE_STRING)&DestinationString,
           &ReferencedDomains,
           &Sids);
    Error = v6 | 0x10000000;
    if ( v6 >= 0 )
    {
      if ( (unsigned int)(Sids->Use - 7) <= 1 )
      {
        Error = -2147467259;
      }
      else
      {
        LengthSid = GetLengthSid(Sids->Sid);
        v8 = CoTaskMemAlloc(LengthSid);
        v9 = v8;
        if ( v8 )
        {
          if ( CopySid(LengthSid, v8, Sids->Sid) )
          {
            *a2 = v9;
            v9 = 0;
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
          CoTaskMemFree(v9);
        }
        else
        {
          Error = -2147024882;
        }
      }
    }
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Sids);
    LsaClose(PolicyHandle);
  }
  return Error;
}

```

## disassembly

```asm
0x18004c17c  mov     [rsp-18h+arg_18], rbx
0x18004c181  mov     [rsp-18h+arg_0], rcx
0x18004c186  push    rbp
0x18004c187  push    rsi
0x18004c188  push    rdi
0x18004c189  mov     rbp, rsp
0x18004c18c  sub     rsp, 70h
0x18004c190  xorps   xmm0, xmm0
0x18004c193  mov     qword ptr [rdx], 0
0x18004c19a  mov     rsi, rdx
0x18004c19d  mov     [rbp+PolicyHandle], 0
0x18004c1a5  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18004c1a9  mov     r8d, 800h; DesiredAccess
0x18004c1af  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18004c1b3  xor     ecx, ecx; SystemName
0x18004c1b5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004c1b9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004c1bd  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004c1c1  call    cs:__imp_LsaOpenPolicy
0x18004c1c7  mov     ebx, eax
0x18004c1c9  mov     edi, 10000000h
0x18004c1ce  or      ebx, edi
0x18004c1d0  jge     short loc_18004C1E4
0x18004c1d2  mov     eax, ebx
0x18004c1d4  mov     rbx, [rsp+70h+arg_18]
0x18004c1dc  add     rsp, 70h
0x18004c1e0  pop     rdi
0x18004c1e1  pop     rsi
0x18004c1e2  pop     rbp
0x18004c1e3  retn
0x18004c1e4  xorps   xmm0, xmm0
0x18004c1e7  mov     [rbp+arg_10], 0
0x18004c1ef  lea     rdx, SourceString; "CDFAccount"
0x18004c1f6  mov     [rbp+arg_0], 0
0x18004c1fe  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004c202  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004c206  call    cs:__imp_RtlInitUnicodeString
0x18004c20c  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18004c210  lea     rax, [rbp+arg_0]
0x18004c214  mov     [rsp+70h+Sids], rax; Sids
0x18004c219  lea     r9, [rbp+DestinationString]; Names
0x18004c21d  lea     rax, [rbp+arg_10]
0x18004c221  mov     edx, 80000000h; Flags
0x18004c226  mov     r8d, 1; Count
0x18004c22c  mov     [rsp+70h+ReferencedDomains], rax; ReferencedDomains
0x18004c231  call    cs:__imp_LsaLookupNames2
0x18004c237  mov     ebx, eax
0x18004c239  or      ebx, edi
0x18004c23b  jge     short loc_18004C260
0x18004c23d  mov     rcx, [rbp+arg_10]; Buffer
0x18004c241  call    cs:__imp_LsaFreeMemory
0x18004c247  mov     rcx, [rbp+arg_0]; Buffer
0x18004c24b  call    cs:__imp_LsaFreeMemory
0x18004c251  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18004c255  call    cs:__imp_LsaClose
0x18004c25b  jmp     loc_18004C1D2
0x18004c260  mov     rcx, [rbp+arg_0]
0x18004c264  mov     eax, [rcx]
0x18004c266  sub     eax, 7
0x18004c269  cmp     eax, 1
0x18004c26c  jbe     short loc_18004C2C6
0x18004c26e  mov     rcx, [rcx+8]; pSid
0x18004c272  call    cs:__imp_GetLengthSid
0x18004c278  mov     ecx, eax; cb
0x18004c27a  mov     ebx, eax
0x18004c27c  call    cs:__imp_CoTaskMemAlloc
0x18004c282  mov     rdi, rax
0x18004c285  test    rax, rax
0x18004c288  jz      short loc_18004C2BC
0x18004c28a  mov     r8, [rbp+arg_0]
0x18004c28e  mov     rdx, rax; pDestinationSid
0x18004c291  mov     ecx, ebx; nDestinationSidLength
0x18004c293  mov     r8, [r8+8]; pSourceSid
0x18004c297  call    cs:__imp_CopySid
0x18004c29d  test    eax, eax
0x18004c29f  jz      short loc_18004C2AA
0x18004c2a1  mov     [rsi], rdi
0x18004c2a4  xor     edi, edi
0x18004c2a6  xor     ebx, ebx
0x18004c2a8  jmp     short loc_18004C2B1
0x18004c2aa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004c2af  mov     ebx, eax
0x18004c2b1  mov     rcx, rdi; pv
0x18004c2b4  call    cs:__imp_CoTaskMemFree
0x18004c2ba  jmp     short loc_18004C23D
0x18004c2bc  mov     ebx, 8007000Eh
0x18004c2c1  jmp     loc_18004C23D
0x18004c2c6  mov     ebx, 80004005h
0x18004c2cb  jmp     loc_18004C23D
```
