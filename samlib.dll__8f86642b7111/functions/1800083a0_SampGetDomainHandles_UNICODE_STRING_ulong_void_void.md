# SampGetDomainHandles(_UNICODE_STRING *,ulong,void * *,void * *)

- ea: `0x1800083a0`
- end: `0x180008587`
- name: `?SampGetDomainHandles@@YAJPEAU_UNICODE_STRING@@KPEAPEAX1@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, void **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008104`

## callees

- `0x180001800`
- `0x180002a80`
- `0x180004dd0`
- `0x180006620`
- `0x1800083a0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180008477`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180008477`
- `ntdll!RtlFreeHeap` at `0x180008554`
- `ntdll!RtlFreeHeap` at `0x180008554`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000852d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000852d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000851e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000851e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800084ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800084ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180008495`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180008495`

## pseudocode

```c
__int64 __fastcall SampGetDomainHandles(struct _UNICODE_STRING *a1, __int64 a2, void **a3, void **a4)
{
  int v6; // ebx
  void *v8; // [rsp+60h] [rbp-29h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp-21h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp-19h] BYREF
  PSID P; // [rsp+78h] [rbp-11h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF
  _DWORD v14[2]; // [rsp+B8h] [rbp+2Fh] BYREF
  __int16 v15; // [rsp+C0h] [rbp+37h]
  __int16 v16; // [rsp+C2h] [rbp+39h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v8 = 0;
  PolicyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  P = 0;
  Buffer = 0;
  v16 = 0;
  if ( !a4 || !a3 )
    return 3221225473LL;
  *a4 = 0;
  ObjectAttributes.SecurityQualityOfService = v14;
  *a3 = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v14[0] = 12;
  v14[1] = 2;
  v15 = 1;
  v6 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x20u, 0, 0, 0, 0, 0, 0, 0, &P);
  if ( v6 >= 0 )
  {
    v6 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
    if ( v6 >= 0 )
    {
      v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
      if ( v6 >= 0 )
      {
        v6 = SamConnect(0, &v8, 32, &ObjectAttributes);
        if ( v6 >= 0 )
        {
          v6 = SamOpenDomain(v8, 516, *((PSID *)Buffer + 2), (__int64 *)a4);
          if ( v6 >= 0 )
          {
            v6 = SamOpenDomain(v8, 516, P, (__int64 *)a3);
            if ( v6 < 0 )
            {
              SamCloseHandle(*a4);
              *a4 = 0;
              *a3 = 0;
            }
          }
        }
      }
    }
  }
  LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v8 )
    SamCloseHandle(v8);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800083a0  mov     [rsp-8+arg_0], rbx
0x1800083a5  mov     [rsp-8+arg_8], rsi
0x1800083aa  push    rbp
0x1800083ab  push    rdi
0x1800083ac  push    r14
0x1800083ae  lea     rbp, [rsp-47h]
0x1800083b3  sub     rsp, 0D0h
0x1800083ba  mov     rax, cs:__security_cookie
0x1800083c1  xor     rax, rsp
0x1800083c4  mov     [rbp+57h+var_18], rax
0x1800083c8  xor     r14d, r14d
0x1800083cb  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800083d1  mov     [rbp+57h+var_80], r14
0x1800083d5  mov     rdi, r9
0x1800083d8  mov     [rbp+57h+PolicyHandle], r14
0x1800083dc  mov     rsi, r8
0x1800083df  mov     dword ptr [rbp+57h+ObjectAttributes+4], r14d
0x1800083e3  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r14d
0x1800083e7  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x1800083eb  mov     [rbp+57h+P], r14
0x1800083ef  mov     [rbp+57h+Buffer], r14
0x1800083f3  mov     [rbp+57h+var_1E], r14w
0x1800083f8  test    r9, r9
0x1800083fb  jz      loc_18000855E
0x180008401  test    r8, r8
0x180008404  jz      loc_18000855E
0x18000840a  mov     [r9], r14
0x18000840d  lea     rax, [rbp+57h+var_28]
0x180008411  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180008415  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180008419  lea     rax, [rbp+57h+P]
0x18000841d  mov     [r8], r14
0x180008420  mov     [rsp+0E0h+Sid], rax; Sid
0x180008425  lea     r8d, [r14+20h]; SubAuthority0
0x180008429  mov     [rsp+0E0h+SubAuthority7], r14d; SubAuthority7
0x18000842e  xor     r9d, r9d; SubAuthority1
0x180008431  mov     [rsp+0E0h+SubAuthority6], r14d; SubAuthority6
0x180008436  mov     dl, 1; SubAuthorityCount
0x180008438  mov     [rsp+0E0h+SubAuthority5], r14d; SubAuthority5
0x18000843d  mov     [rsp+0E0h+SubAuthority4], r14d; SubAuthority4
0x180008442  mov     [rsp+0E0h+SubAuthority3], r14d; SubAuthority3
0x180008447  mov     [rsp+0E0h+SubAuthority2], r14d; SubAuthority2
0x18000844c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180008453  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180008457  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x18000845b  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18000845f  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x180008463  mov     [rbp+57h+var_28], 0Ch
0x18000846a  mov     [rbp+57h+var_24], 2
0x180008471  mov     [rbp+57h+var_20], 1
0x180008477  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000847d  mov     ebx, eax
0x18000847f  test    eax, eax
0x180008481  js      loc_18000851A
0x180008487  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000848b  xor     ecx, ecx; SystemName
0x18000848d  lea     r8d, [r14+1]; DesiredAccess
0x180008491  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180008495  call    cs:__imp_LsaOpenPolicy
0x18000849b  mov     ebx, eax
0x18000849d  test    eax, eax
0x18000849f  js      short loc_18000851A
0x1800084a1  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800084a5  lea     r8, [rbp+57h+Buffer]; Buffer
0x1800084a9  lea     edx, [r14+5]; InformationClass
0x1800084ad  call    cs:__imp_LsaQueryInformationPolicy
0x1800084b3  mov     ebx, eax
0x1800084b5  test    eax, eax
0x1800084b7  js      short loc_18000851A
0x1800084b9  lea     r9, [rbp+57h+ObjectAttributes]
0x1800084bd  xor     ecx, ecx
0x1800084bf  lea     r8d, [r14+20h]
0x1800084c3  lea     rdx, [rbp+57h+var_80]
0x1800084c7  call    SamConnect
0x1800084cc  mov     ebx, eax
0x1800084ce  test    eax, eax
0x1800084d0  js      short loc_18000851A
0x1800084d2  mov     r8, [rbp+57h+Buffer]
0x1800084d6  mov     r9, rdi
0x1800084d9  mov     rcx, [rbp+57h+var_80]; void *
0x1800084dd  mov     edx, 204h; char
0x1800084e2  mov     r8, [r8+10h]; pSid
0x1800084e6  call    SamOpenDomain
0x1800084eb  mov     ebx, eax
0x1800084ed  test    eax, eax
0x1800084ef  js      short loc_18000851A
0x1800084f1  mov     r8, [rbp+57h+P]; pSid
0x1800084f5  mov     r9, rsi
0x1800084f8  mov     rcx, [rbp+57h+var_80]; void *
0x1800084fc  mov     edx, 204h; char
0x180008501  call    SamOpenDomain
0x180008506  mov     ebx, eax
0x180008508  test    eax, eax
0x18000850a  jns     short loc_18000851A
0x18000850c  mov     rcx, [rdi]; void *
0x18000850f  call    SamCloseHandle
0x180008514  mov     [rdi], r14
0x180008517  mov     [rsi], r14
0x18000851a  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000851e  call    cs:__imp_LsaFreeMemory
0x180008524  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180008528  test    rcx, rcx
0x18000852b  jz      short loc_180008533
0x18000852d  call    cs:__imp_LsaClose
0x180008533  mov     rcx, [rbp+57h+var_80]; void *
0x180008537  test    rcx, rcx
0x18000853a  jz      short loc_180008541
0x18000853c  call    SamCloseHandle
0x180008541  mov     rcx, gs:60h
0x18000854a  xor     edx, edx; Flags
0x18000854c  mov     r8, [rbp+57h+P]; P
0x180008550  mov     rcx, [rcx+30h]; HeapHandle
0x180008554  call    cs:__imp_RtlFreeHeap
0x18000855a  mov     eax, ebx
0x18000855c  jmp     short loc_180008563
0x18000855e  mov     eax, 0C0000001h
0x180008563  mov     rcx, [rbp+57h+var_18]
0x180008567  xor     rcx, rsp; StackCookie
0x18000856a  call    __security_check_cookie
0x18000856f  lea     r11, [rsp+0E0h+var_10]
0x180008577  mov     rbx, [r11+20h]
0x18000857b  mov     rsi, [r11+28h]
0x18000857f  mov     rsp, r11
0x180008582  pop     r14
0x180008584  pop     rdi
0x180008585  pop     rbp
0x180008586  retn
```
