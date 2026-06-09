# WsInAWorkgroup

- ea: `0x1800082f0`
- end: `0x1800083c5`
- name: `WsInAWorkgroup`
- size: `213`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005ac0`
- `0x180005dec`
- `0x180006948`
- `0x18002d080`

## callees

- `0x1800082f0`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x18000831f`
- `ntdll!RtlGetNtProductType` at `0x18000831f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180008366`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180008366`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800083a5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800083a5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180008386`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180008386`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000839a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000839a`

## pseudocode

```c
__int64 WsInAWorkgroup()
{
  unsigned int v0; // ebx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+60h] [rbp+8h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp+10h] BYREF
  PVOID DomainInfo; // [rsp+70h] [rbp+18h] BYREF

  ProductType = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DomainInfo = 0;
  if ( !RtlGetNtProductType(&ProductType) )
    return 0;
  if ( ProductType == NtProductLanManNt )
    return 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle) < 0 )
    return 0;
  v0 = 0;
  if ( LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, &DomainInfo) >= 0 )
    LOBYTE(v0) = *((_QWORD *)DomainInfo + 8) == 0;
  if ( DomainInfo )
    LsaLookupFreeMemory(DomainInfo);
  LsaLookupClose(PolicyHandle);
  return v0;
}

```

## disassembly

```asm
0x1800082f0  push    rdi
0x1800082f2  sub     rsp, 50h
0x1800082f6  xorps   xmm0, xmm0
0x1800082f9  lea     rcx, [rsp+58h+ProductType]; ProductType
0x1800082fe  xor     edi, edi
0x180008300  xor     eax, eax
0x180008302  movups  xmmword ptr [rsp+58h+ObjectAttributes.ObjectName], xmm0
0x180008307  mov     [rsp+58h+ProductType], edi
0x18000830b  movups  xmmword ptr [rsp+58h+ObjectAttributes+1Ch], xmm0
0x180008310  mov     [rsp+58h+PolicyHandle], rdi
0x180008315  movups  xmmword ptr [rsp+58h+ObjectAttributes.Length], xmm0
0x18000831a  mov     [rsp+58h+DomainInfo], rdi
0x18000831f  call    cs:__imp_RtlGetNtProductType
0x180008325  test    al, al
0x180008327  jz      loc_1800083C1
0x18000832d  cmp     [rsp+58h+ProductType], 2
0x180008332  jz      loc_1800083C1
0x180008338  xorps   xmm0, xmm0
0x18000833b  mov     [rsp+58h+ObjectAttributes.Length], 30h ; '0'
0x180008343  lea     r8, [rsp+58h+PolicyHandle]; PolicyHandle
0x180008348  mov     [rsp+58h+ObjectAttributes.RootDirectory], rdi
0x18000834d  mov     edx, 1; AccessMask
0x180008352  mov     [rsp+58h+ObjectAttributes.Attributes], edi
0x180008356  lea     rcx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x18000835b  mov     [rsp+58h+ObjectAttributes.ObjectName], rdi
0x180008360  movdqu  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008366  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000836c  test    eax, eax
0x18000836e  js      short loc_1800083C1
0x180008370  mov     rcx, [rsp+58h+PolicyHandle]; PolicyHandle
0x180008375  lea     r8, [rsp+58h+DomainInfo]; DomainInfo
0x18000837a  mov     [rsp+58h+arg_18], rbx
0x18000837f  mov     edx, 0Ch; DomainInfoClass
0x180008384  mov     ebx, edi
0x180008386  call    cs:__imp_LsaLookupGetDomainInfo
0x18000838c  mov     rcx, [rsp+58h+DomainInfo]; Buffer
0x180008391  test    eax, eax
0x180008393  jns     short loc_1800083B8
0x180008395  test    rcx, rcx
0x180008398  jz      short loc_1800083A0
0x18000839a  call    cs:__imp_LsaLookupFreeMemory
0x1800083a0  mov     rcx, [rsp+58h+PolicyHandle]; ObjectHandle
0x1800083a5  call    cs:__imp_LsaLookupClose
0x1800083ab  mov     eax, ebx
0x1800083ad  mov     rbx, [rsp+58h+arg_18]
0x1800083b2  add     rsp, 50h
0x1800083b6  pop     rdi
0x1800083b7  retn
0x1800083b8  cmp     [rcx+40h], rbx
0x1800083bc  setz    bl
0x1800083bf  jmp     short loc_180008395
0x1800083c1  xor     eax, eax
0x1800083c3  jmp     short loc_1800083B2
```
