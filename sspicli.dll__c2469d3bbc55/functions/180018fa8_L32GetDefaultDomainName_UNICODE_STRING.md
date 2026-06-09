# L32GetDefaultDomainName(_UNICODE_STRING *)

- ea: `0x180018fa8`
- end: `0x1800190af`
- name: `?L32GetDefaultDomainName@@YAHPEAU_UNICODE_STRING@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ab30`

## callees

- `0x1800171dc`
- `0x180018918`
- `0x180018fa8`
- `0x180022047`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018fe4`
- `ntdll!RtlInitUnicodeString` at `0x180018fe4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180019098`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180019098`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18001904e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18001904e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18001905a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18001905a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18001902c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18001902c`

## pseudocode

```c
__int64 __fastcall L32GetDefaultDomainName(struct _UNICODE_STRING *a1)
{
  struct _UNICODE_STRING *v1; // rsi
  NTSTATUS v3; // eax
  int v4; // ecx
  NTSTATUS v5; // ebx
  _WORD *v6; // rdi
  unsigned __int64 v7; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp+28h] BYREF
  PVOID DomainInfo; // [rsp+80h] [rbp+30h] BYREF

  v1 = a1;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  PolicyHandle = 0;
  DomainInfo = 0;
  if ( Logon32DomainName )
  {
LABEL_2:
    RtlInitUnicodeString(a1, &Logon32DomainName);
    return 1;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v3 >= 0 )
  {
    v5 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
    LsaLookupClose(PolicyHandle);
    if ( v5 >= 0 )
    {
      v6 = DomainInfo;
      memcpy_0(&Logon32DomainName, *((const void **)DomainInfo + 1), *(unsigned __int16 *)DomainInfo);
      v7 = *v6 & 0xFFFE;
      if ( v7 >= 0x20 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)&Logon32DomainName + v7) = 0;
      LsaLookupFreeMemory(v6);
      a1 = v1;
      goto LABEL_2;
    }
    v4 = v5;
  }
  else
  {
    v4 = v3;
  }
  BaseSetLastNTError(v4);
  return 0;
}

```

## disassembly

```asm
0x180018fa8  mov     [rsp-18h+arg_0], rbx
0x180018fad  mov     [rsp-18h+arg_18], rsi
0x180018fb2  push    rbp
0x180018fb3  push    rdi
0x180018fb4  push    r14
0x180018fb6  mov     rbp, rsp
0x180018fb9  sub     rsp, 50h
0x180018fbd  xor     r14d, r14d
0x180018fc0  mov     rsi, rcx
0x180018fc3  cmp     cs:?Logon32DomainName@@3PAGA, r14w; ushort near * Logon32DomainName
0x180018fcb  mov     dword ptr [rbp+ObjectAttributes+4], r14d
0x180018fcf  mov     dword ptr [rbp+ObjectAttributes+1Ch], r14d
0x180018fd3  mov     [rbp+PolicyHandle], r14
0x180018fd7  mov     [rbp+DomainInfo], r14
0x180018fdb  jz      short loc_180019004
0x180018fdd  lea     rdx, ?Logon32DomainName@@3PAGA; SourceString
0x180018fe4  call    cs:__imp_RtlInitUnicodeString
0x180018fea  mov     eax, 1
0x180018fef  lea     r11, [rsp+50h+var_s0]
0x180018ff4  mov     rbx, [r11+20h]
0x180018ff8  mov     rsi, [r11+38h]
0x180018ffc  mov     rsp, r11
0x180018fff  pop     r14
0x180019001  pop     rdi
0x180019002  pop     rbp
0x180019003  retn
0x180019004  xorps   xmm0, xmm0
0x180019007  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001900e  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x180019012  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x180019016  mov     edx, 1; AccessMask
0x18001901b  mov     [rbp+ObjectAttributes.Attributes], r14d
0x18001901f  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180019023  mov     [rbp+ObjectAttributes.ObjectName], r14
0x180019027  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001902c  call    cs:__imp_LsaLookupOpenLocalPolicy
0x180019032  test    eax, eax
0x180019034  jns     short loc_180019041
0x180019036  mov     ecx, eax; int
0x180019038  call    ?BaseSetLastNTError@@YAKJ@Z; BaseSetLastNTError(long)
0x18001903d  xor     eax, eax
0x18001903f  jmp     short loc_180018FEF
0x180019041  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180019045  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180019049  mov     edx, 5; DomainInfoClass
0x18001904e  call    cs:__imp_LsaLookupGetDomainInfo
0x180019054  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180019058  mov     ebx, eax
0x18001905a  call    cs:__imp_LsaLookupClose
0x180019060  test    ebx, ebx
0x180019062  jns     short loc_180019068
0x180019064  mov     ecx, ebx
0x180019066  jmp     short loc_180019038
0x180019068  mov     rdi, [rbp+DomainInfo]
0x18001906c  lea     rbx, ?Logon32DomainName@@3PAGA; ushort near * Logon32DomainName
0x180019073  mov     rcx, rbx; void *
0x180019076  movzx   r8d, word ptr [rdi]; Size
0x18001907a  mov     rdx, [rdi+8]; Src
0x18001907e  call    memcpy_0
0x180019083  movzx   ecx, word ptr [rdi]
0x180019086  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18001908a  cmp     rcx, 20h ; ' '
0x18001908e  jnb     short loc_1800190A9
0x180019090  mov     [rcx+rbx], r14w
0x180019095  mov     rcx, rdi; Buffer
0x180019098  call    cs:__imp_LsaLookupFreeMemory
0x18001909e  mov     rdx, rbx
0x1800190a1  mov     rcx, rsi
0x1800190a4  jmp     loc_180018FE4
0x1800190a9  call    __report_rangecheckfailure
```
