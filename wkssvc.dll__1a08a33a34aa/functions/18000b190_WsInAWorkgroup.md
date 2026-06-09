# WsInAWorkgroup

- ea: `0x18000b190`
- end: `0x18000b284`
- name: `WsInAWorkgroup`
- size: `244`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005e54`
- `0x1800061d8`
- `0x180006ea0`
- `0x18000abb0`
- `0x18000ace0`
- `0x18002f910`

## callees

- `0x18000b190`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x18000b1bf`
- `ntdll!RtlGetNtProductType` at `0x18000b1bf`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000b20c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000b20c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000b25d`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000b25d`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000b232`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000b232`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000b24c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000b24c`

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
0x18000b190  push    rdi
0x18000b192  sub     rsp, 50h
0x18000b196  xorps   xmm0, xmm0
0x18000b199  lea     rcx, [rsp+58h+ProductType]; ProductType
0x18000b19e  xor     edi, edi
0x18000b1a0  xor     eax, eax
0x18000b1a2  movups  xmmword ptr [rsp+58h+ObjectAttributes.ObjectName], xmm0
0x18000b1a7  mov     [rsp+58h+ProductType], edi
0x18000b1ab  movups  xmmword ptr [rsp+58h+ObjectAttributes+1Ch], xmm0
0x18000b1b0  mov     [rsp+58h+PolicyHandle], rdi
0x18000b1b5  movups  xmmword ptr [rsp+58h+ObjectAttributes.Length], xmm0
0x18000b1ba  mov     [rsp+58h+DomainInfo], rdi
0x18000b1bf  call    cs:__imp_RtlGetNtProductType
0x18000b1c6  nop     dword ptr [rax+rax+00h]
0x18000b1cb  test    al, al
0x18000b1cd  jz      loc_18000B280
0x18000b1d3  cmp     [rsp+58h+ProductType], 2
0x18000b1d8  jz      loc_18000B280
0x18000b1de  xorps   xmm0, xmm0
0x18000b1e1  mov     [rsp+58h+ObjectAttributes.Length], 30h ; '0'
0x18000b1e9  lea     r8, [rsp+58h+PolicyHandle]; PolicyHandle
0x18000b1ee  mov     [rsp+58h+ObjectAttributes.RootDirectory], rdi
0x18000b1f3  mov     edx, 1; AccessMask
0x18000b1f8  mov     [rsp+58h+ObjectAttributes.Attributes], edi
0x18000b1fc  lea     rcx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x18000b201  mov     [rsp+58h+ObjectAttributes.ObjectName], rdi
0x18000b206  movdqu  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b20c  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000b213  nop     dword ptr [rax+rax+00h]
0x18000b218  test    eax, eax
0x18000b21a  js      short loc_18000B280
0x18000b21c  mov     rcx, [rsp+58h+PolicyHandle]; PolicyHandle
0x18000b221  lea     r8, [rsp+58h+DomainInfo]; DomainInfo
0x18000b226  mov     [rsp+58h+arg_18], rbx
0x18000b22b  mov     edx, 0Ch; DomainInfoClass
0x18000b230  mov     ebx, edi
0x18000b232  call    cs:__imp_LsaLookupGetDomainInfo
0x18000b239  nop     dword ptr [rax+rax+00h]
0x18000b23e  mov     rcx, [rsp+58h+DomainInfo]; Buffer
0x18000b243  test    eax, eax
0x18000b245  jns     short loc_18000B277
0x18000b247  test    rcx, rcx
0x18000b24a  jz      short loc_18000B258
0x18000b24c  call    cs:__imp_LsaLookupFreeMemory
0x18000b253  nop     dword ptr [rax+rax+00h]
0x18000b258  mov     rcx, [rsp+58h+PolicyHandle]; ObjectHandle
0x18000b25d  call    cs:__imp_LsaLookupClose
0x18000b264  nop     dword ptr [rax+rax+00h]
0x18000b269  mov     eax, ebx
0x18000b26b  mov     rbx, [rsp+58h+arg_18]
0x18000b270  add     rsp, 50h
0x18000b274  pop     rdi
0x18000b275  retn
0x18000b277  cmp     [rcx+40h], rbx
0x18000b27b  setz    bl
0x18000b27e  jmp     short loc_18000B247
0x18000b280  xor     eax, eax
0x18000b282  jmp     short loc_18000B270
```
