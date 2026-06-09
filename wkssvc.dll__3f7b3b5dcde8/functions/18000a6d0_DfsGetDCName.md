# DfsGetDCName

- ea: `0x18000a6d0`
- end: `0x18000a987`
- name: `DfsGetDCName`
- size: `695`
- prototype: `__int64 __fastcall(int, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d080`

## callees

- `0x18000a6d0`
- `0x18000a990`
- `0x18000b798`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x18000a726`
- `ntdll!RtlGetNtProductType` at `0x18000a726`
- `ntdll!NtOpenFile` at `0x18000a87d`
- `ntdll!NtOpenFile` at `0x18000a87d`
- `ntdll!RtlNtStatusToDosError` at `0x18000a894`
- `ntdll!RtlNtStatusToDosError` at `0x18000a894`
- `ntdll!NtClose` at `0x18000a97c`
- `ntdll!NtClose` at `0x18000a97c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a908`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a908`
- `logoncli!DsGetDcNameW` at `0x18000a7ec`
- `logoncli!DsGetDcNameW` at `0x18000a7ec`
- `netutils!NetApiBufferFree` at `0x18000a971`
- `netutils!NetApiBufferFree` at `0x18000a971`
- `DSROLE!DsRoleFreeMemory` at `0x18000a8e8`
- `DSROLE!DsRoleFreeMemory` at `0x18000a8e8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000a75e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000a75e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000a799`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000a799`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000a778`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000a778`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000a78f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000a78f`

## pseudocode

```c
__int64 __fastcall DfsGetDCName(int a1, _BYTE *a2)
{
  __int64 v3; // rbx
  int v5; // edi
  DWORD DomainNameInfo; // esi
  LPWSTR i; // rdi
  int v8; // eax
  __int64 v10; // rcx
  void *FileHandle; // [rsp+30h] [rbp-29h] BYREF
  PVOID DomainInfo[2]; // [rsp+38h] [rbp-21h] BYREF
  PVOID Buffer; // [rsp+48h] [rbp-11h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+C8h] [rbp+6Fh] BYREF
  PVOID PolicyHandle; // [rsp+D0h] [rbp+77h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+D8h] [rbp+7Fh] BYREF

  *a2 = 1;
  DomainControllerInfo = 0;
  Buffer = 0;
  v3 = -1;
  ProductType = 0;
  FileHandle = (void *)-1LL;
  PolicyHandle = 0;
  DomainInfo[0] = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( RtlGetNtProductType(&ProductType) )
  {
    if ( ProductType != NtProductLanManNt )
    {
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle) >= 0 )
      {
        v5 = 0;
        if ( LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, DomainInfo) >= 0 )
          LOBYTE(v5) = *((_QWORD *)DomainInfo[0] + 8) == 0;
        if ( DomainInfo[0] )
          LsaLookupFreeMemory(DomainInfo[0]);
        LsaLookupClose(PolicyHandle);
        if ( v5 == 1 )
          return 1355;
      }
    }
  }
  if ( !hMupEvent )
    hMupEvent = CreateEventW(0, 1, 0, L"wkssvc:  MUP finished initializing event");
  DomainNameInfo = DfsGetDomainNameInfo((PBYTE *)&Buffer);
  if ( !DomainNameInfo )
  {
    DomainNameInfo = DsGetDcNameW(0, 0, 0, 0, a1 | 0x10, &DomainControllerInfo);
    if ( !DomainNameInfo )
    {
      for ( i = DomainControllerInfo->DomainControllerName; *i == 92; ++i )
        ;
      do
        ++v3;
      while ( i[v3] );
      if ( (_DWORD)v3 )
      {
        v10 = (unsigned int)(v3 - 1);
        if ( i[v10] != 46 )
          goto LABEL_18;
        i[v10] = 0;
        LODWORD(v3) = v3 - 1;
      }
      if ( (_DWORD)v3 )
      {
LABEL_18:
        *a2 = 0;
        ObjectAttributes.ObjectName = (PLSA_UNICODE_STRING)LocalDfsName;
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 64;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)DomainInfo = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v8 = NtOpenFile(
               &FileHandle,
               0x100002u,
               (POBJECT_ATTRIBUTES)&ObjectAttributes,
               (PIO_STATUS_BLOCK)DomainInfo,
               7u,
               0x20u);
        if ( v8 < 0
          || (v8 = (int)DomainInfo[0], SLODWORD(DomainInfo[0]) < 0)
          || (v8 = DfsFsctl(FileHandle, 0x680A4u, i, 2 * v3 + 2, 0, 0), v8 < 0) )
        {
          DomainNameInfo = RtlNtStatusToDosError(v8);
        }
        goto LABEL_21;
      }
      DomainNameInfo = 59;
    }
  }
LABEL_21:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( Buffer )
    DsRoleFreeMemory(Buffer);
  return DomainNameInfo;
}

```

## disassembly

```asm
0x18000a6d0  push    rbp
0x18000a6d2  push    rbx
0x18000a6d3  push    rdi
0x18000a6d4  push    r12
0x18000a6d6  push    r14
0x18000a6d8  push    r15
0x18000a6da  lea     rbp, [rsp-2Fh]
0x18000a6df  sub     rsp, 88h
0x18000a6e6  xor     r12d, r12d
0x18000a6e9  mov     byte ptr [rdx], 1
0x18000a6ec  xorps   xmm0, xmm0
0x18000a6ef  mov     [rbp+57h+arg_18], r12
0x18000a6f3  mov     r14d, ecx
0x18000a6f6  mov     [rbp+57h+Buffer], r12
0x18000a6fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000a6fe  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a705  mov     [rbp+57h+ProductType], r12d
0x18000a709  xor     eax, eax
0x18000a70b  mov     [rbp+57h+FileHandle], rbx
0x18000a70f  lea     rcx, [rbp+57h+ProductType]; ProductType
0x18000a713  mov     [rbp+57h+PolicyHandle], r12
0x18000a717  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000a71b  mov     r15, rdx
0x18000a71e  mov     [rbp+57h+DomainInfo], r12
0x18000a722  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000a726  call    cs:__imp_RtlGetNtProductType
0x18000a72c  test    al, al
0x18000a72e  jz      short loc_18000A7A8
0x18000a730  cmp     [rbp+57h+ProductType], 2
0x18000a734  jz      short loc_18000A7A8
0x18000a736  xorps   xmm0, xmm0
0x18000a739  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a740  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a744  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18000a748  mov     edx, 1; AccessMask
0x18000a74d  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x18000a751  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a755  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x18000a759  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a75e  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000a764  test    eax, eax
0x18000a766  js      short loc_18000A7A8
0x18000a768  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a76c  lea     r8, [rbp+57h+DomainInfo]; DomainInfo
0x18000a770  mov     edx, 0Ch; DomainInfoClass
0x18000a775  mov     edi, r12d
0x18000a778  call    cs:__imp_LsaLookupGetDomainInfo
0x18000a77e  mov     rcx, [rbp+57h+DomainInfo]; Buffer
0x18000a782  test    eax, eax
0x18000a784  jns     loc_18000A8DB
0x18000a78a  test    rcx, rcx
0x18000a78d  jz      short loc_18000A795
0x18000a78f  call    cs:__imp_LsaLookupFreeMemory
0x18000a795  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18000a799  call    cs:__imp_LsaLookupClose
0x18000a79f  cmp     edi, 1
0x18000a7a2  jz      loc_18000A8F0
0x18000a7a8  cmp     cs:hMupEvent, r12
0x18000a7af  mov     [rsp+0B0h+var_30], rsi
0x18000a7b7  jz      loc_18000A8F7
0x18000a7bd  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18000a7c1  call    DfsGetDomainNameInfo
0x18000a7c6  mov     esi, eax
0x18000a7c8  test    eax, eax
0x18000a7ca  jnz     loc_18000A89C
0x18000a7d0  lea     rax, [rbp+57h+arg_18]
0x18000a7d4  or      r14d, 10h
0x18000a7d8  mov     [rsp+0B0h+DomainControllerInfo], rax; DomainControllerInfo
0x18000a7dd  xor     r9d, r9d; SiteName
0x18000a7e0  xor     r8d, r8d; DomainGuid
0x18000a7e3  mov     [rsp+0B0h+Flags], r14d; Flags
0x18000a7e8  xor     edx, edx; DomainName
0x18000a7ea  xor     ecx, ecx; ComputerName
0x18000a7ec  call    cs:__imp_DsGetDcNameW
0x18000a7f2  mov     esi, eax
0x18000a7f4  test    eax, eax
0x18000a7f6  jnz     loc_18000A89C
0x18000a7fc  mov     rax, [rbp+57h+arg_18]
0x18000a800  mov     rdi, [rax]
0x18000a803  cmp     word ptr [rdi], 5Ch ; '\'
0x18000a807  jnz     short loc_18000A813
0x18000a809  add     rdi, 2
0x18000a80d  cmp     word ptr [rdi], 5Ch ; '\'
0x18000a811  jz      short loc_18000A809
0x18000a813  inc     rbx
0x18000a816  cmp     [rdi+rbx*2], r12w
0x18000a81b  jnz     short loc_18000A813
0x18000a81d  cmp     ebx, 1
0x18000a820  jnb     loc_18000A91A
0x18000a826  test    ebx, ebx
0x18000a828  jz      loc_18000A967
0x18000a82e  xorps   xmm0, xmm0
0x18000a831  mov     dword ptr [rsp+0B0h+DomainControllerInfo], 20h ; ' '; OpenOptions
0x18000a839  lea     rax, LocalDfsName; "\"\""
0x18000a840  mov     [r15], r12b
0x18000a843  lea     r9, [rbp+57h+DomainInfo]; IoStatusBlock
0x18000a847  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000a84b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a84f  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a857  mov     edx, 100002h; DesiredAccess
0x18000a85c  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a864  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000a868  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18000a86c  movups  xmmword ptr [rbp+57h+DomainInfo], xmm0
0x18000a870  mov     [rsp+0B0h+Flags], 7; ShareAccess
0x18000a878  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a87d  call    cs:__imp_NtOpenFile
0x18000a883  test    eax, eax
0x18000a885  js      short loc_18000A892
0x18000a887  mov     eax, dword ptr [rbp+57h+DomainInfo]
0x18000a88a  test    eax, eax
0x18000a88c  jns     loc_18000A937
0x18000a892  mov     ecx, eax; Status
0x18000a894  call    cs:__imp_RtlNtStatusToDosError
0x18000a89a  mov     esi, eax
0x18000a89c  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18000a8a0  test    rcx, rcx
0x18000a8a3  jnz     loc_18000A971
0x18000a8a9  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000a8ad  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a8b1  jnz     loc_18000A97C
0x18000a8b7  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000a8bb  test    rcx, rcx
0x18000a8be  jnz     short loc_18000A8E8
0x18000a8c0  mov     eax, esi
0x18000a8c2  mov     rsi, [rsp+0B0h+var_30]
0x18000a8ca  add     rsp, 88h
0x18000a8d1  pop     r15
0x18000a8d3  pop     r14
0x18000a8d5  pop     r12
0x18000a8d7  pop     rdi
0x18000a8d8  pop     rbx
0x18000a8d9  pop     rbp
0x18000a8da  retn
0x18000a8db  cmp     [rcx+40h], rdi
0x18000a8df  setz    dil
0x18000a8e3  jmp     loc_18000A78A
0x18000a8e8  call    cs:__imp_DsRoleFreeMemory
0x18000a8ee  jmp     short loc_18000A8C0
0x18000a8f0  mov     eax, 54Bh
0x18000a8f5  jmp     short loc_18000A8CA
0x18000a8f7  lea     r9, Name; "wkssvc:  MUP finished initializing even"...
0x18000a8fe  xor     r8d, r8d; bInitialState
0x18000a901  mov     edx, 1; bManualReset
0x18000a906  xor     ecx, ecx; lpEventAttributes
0x18000a908  call    cs:__imp_CreateEventW
0x18000a90e  mov     cs:hMupEvent, rax
0x18000a915  jmp     loc_18000A7BD
0x18000a91a  lea     ecx, [rbx-1]
0x18000a91d  cmp     word ptr [rdi+rcx*2], 2Eh ; '.'
0x18000a922  lea     rdx, [rdi+rcx*2]
0x18000a926  jnz     loc_18000A82E
0x18000a92c  mov     [rdx], r12w
0x18000a930  mov     ebx, ecx
0x18000a932  jmp     loc_18000A826
0x18000a937  mov     rcx, [rbp+57h+FileHandle]
0x18000a93b  lea     r9d, ds:2[rbx*2]
0x18000a943  mov     dword ptr [rsp+0B0h+DomainControllerInfo], r12d
0x18000a948  mov     r8, rdi
0x18000a94b  mov     edx, 680A4h
0x18000a950  mov     qword ptr [rsp+0B0h+Flags], r12
0x18000a955  call    DfsFsctl
0x18000a95a  test    eax, eax
0x18000a95c  jns     loc_18000A89C
0x18000a962  jmp     loc_18000A892
0x18000a967  mov     esi, 3Bh ; ';'
0x18000a96c  jmp     loc_18000A89C
0x18000a971  call    cs:__imp_NetApiBufferFree
0x18000a977  jmp     loc_18000A8A9
0x18000a97c  call    cs:__imp_NtClose
0x18000a982  jmp     loc_18000A8B7
```
