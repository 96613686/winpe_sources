# ScGetLockOwner(void *,ushort * *)

- ea: `0x140073e2c`
- end: `0x1400742ac`
- name: `?ScGetLockOwner@@YAKPEAXPEAPEAG@Z`
- size: `1152`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400743b0`

## callees

- `0x140004c58`
- `0x14000cee0`
- `0x14001f99c`
- `0x14002e420`
- `0x1400428b8`
- `0x140073e2c`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400740e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400740e4`
- `ntdll!RtlNtStatusToDosError` at `0x140073f3b`
- `ntdll!RtlNtStatusToDosError` at `0x140073f9f`
- `ntdll!RtlNtStatusToDosError` at `0x140073f3b`
- `ntdll!RtlNtStatusToDosError` at `0x140073f9f`
- `ntdll!RtlFreeHeap` at `0x14007412f`
- `ntdll!RtlFreeHeap` at `0x14007412f`
- `ntdll!RtlEqualUnicodeString` at `0x140074170`
- `ntdll!RtlEqualUnicodeString` at `0x14007419c`
- `ntdll!RtlEqualUnicodeString` at `0x140074170`
- `ntdll!RtlEqualUnicodeString` at `0x14007419c`
- `ntdll!RtlGetNtProductType` at `0x1400740da`
- `ntdll!RtlGetNtProductType` at `0x1400740da`
- `ntdll!RtlAllocateHeap` at `0x140073e77`
- `ntdll!RtlAllocateHeap` at `0x14007408f`
- `ntdll!RtlAllocateHeap` at `0x140073e77`
- `ntdll!RtlAllocateHeap` at `0x14007408f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateSids` at `0x140073f60`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateSids` at `0x140073f60`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x140074280`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14007428f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x140074280`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14007428f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x140074299`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x140074299`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x140073efc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x140073efc`

## string_xrefs

- `0x140073ebb`: `.\NT Service Control Manager`

## pseudocode

```c
ULONG __fastcall ScGetLockOwner(void *a1, unsigned __int16 **a2)
{
  unsigned __int16 *Heap; // rax
  int v5; // ebx
  int v6; // ebx
  ULONG LastError; // ebx
  __int64 DomainIndex; // r8
  PRPC_ASYNC_STATE v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  PLSA_TRANSLATED_NAME Names; // [rsp+30h] [rbp-40h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PSID Sids; // [rsp+A0h] [rbp+30h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+B0h] [rbp+40h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+B8h] [rbp+48h] BYREF

  Sids = a1;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  PolicyHandle = 0;
  ReferencedDomains = 0;
  Names = 0;
  ProductType = 0;
  if ( !a1 )
  {
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x3Au);
    *a2 = Heap;
    if ( Heap )
    {
      StringCbCopyW(Heap, 0x3Au, L".\\NT Service Control Manager");
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 20, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids);
      return 8;
    }
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 21, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids, (unsigned int)v5);
    return RtlNtStatusToDosError(v5);
  }
  v6 = LsaLookupTranslateSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 22, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids, (unsigned int)v6);
    LastError = RtlNtStatusToDosError(v6);
    goto LABEL_55;
  }
  if ( !ReferencedDomains || !Names )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->StubInfo,
        23,
        WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids,
        ReferencedDomains,
        Names);
    goto LABEL_54;
  }
  if ( (unsigned int)(Names->Use - 7) <= 1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_54;
    v10 = 24;
    goto LABEL_29;
  }
  DomainIndex = Names->DomainIndex;
  if ( (int)DomainIndex < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->StubInfo,
        25,
        WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids,
        (unsigned int)DomainIndex);
    goto LABEL_54;
  }
  if ( !ReferencedDomains->Entries )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_54;
    v10 = 26;
LABEL_29:
    WPP_SF_(v9->StubInfo, v10, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids);
LABEL_54:
    LastError = 31;
    goto LABEL_55;
  }
  LastError = 8;
  v11 = Names->Name.Length + (unsigned __int64)ReferencedDomains->Domains[DomainIndex].Name.Length;
  v12 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11 + 4);
  *a2 = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 27, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids);
    goto LABEL_55;
  }
  if ( !RtlGetNtProductType(&ProductType) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 28, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids, LastError);
    goto LABEL_38;
  }
  LastError = 0;
  if ( ProductType == NtProductLanManNt )
    goto LABEL_44;
  LastError = ScGetAccountDomainInfo();
  if ( !LastError )
  {
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)&ReferencedDomains->Domains[Names->DomainIndex], &ScAccountDomain, 1u)
      || RtlEqualUnicodeString((PCUNICODE_STRING)&ReferencedDomains->Domains[Names->DomainIndex], &ScComputerName, 1u) )
    {
      StringCbCopyW(*a2, v11 + 4, L".");
      goto LABEL_45;
    }
LABEL_44:
    memmove(
      *a2,
      ReferencedDomains->Domains[Names->DomainIndex].Name.Buffer,
      ReferencedDomains->Domains[Names->DomainIndex].Name.Length);
LABEL_45:
    v13 = *a2;
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v13[v14] = 92;
    memmove(&v13[v14 + 1], Names->Name.Buffer, Names->Name.Length);
    goto LABEL_55;
  }
LABEL_38:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a2);
LABEL_55:
  if ( ReferencedDomains )
    LsaLookupFreeMemory(ReferencedDomains);
  if ( Names )
    LsaLookupFreeMemory(Names);
  LsaLookupClose(PolicyHandle);
  return LastError;
}

```

## disassembly

```asm
0x140073e2c  mov     [rsp-28h+Sids], rcx
0x140073e31  push    rbp
0x140073e32  push    rbx
0x140073e33  push    rsi
0x140073e34  push    rdi
0x140073e35  push    r14
0x140073e37  mov     rbp, rsp
0x140073e3a  sub     rsp, 70h
0x140073e3e  xor     r14d, r14d
0x140073e41  mov     rdi, rdx
0x140073e44  mov     dword ptr [rbp+ObjectAttributes+4], r14d
0x140073e48  mov     dword ptr [rbp+ObjectAttributes+1Ch], r14d
0x140073e4c  mov     [rbp+PolicyHandle], r14
0x140073e50  mov     [rbp+ReferencedDomains], r14
0x140073e54  mov     [rbp+var_40], r14
0x140073e58  mov     [rbp+ProductType], r14d
0x140073e5c  test    rcx, rcx
0x140073e5f  jnz     short loc_140073ED4
0x140073e61  mov     rcx, gs:60h
0x140073e6a  lea     ebx, [r14+3Ah]
0x140073e6e  mov     r8d, ebx; Size
0x140073e71  xor     edx, edx; Flags
0x140073e73  mov     rcx, [rcx+30h]; HeapHandle
0x140073e77  call    cs:__imp_RtlAllocateHeap
0x140073e7d  mov     [rdi], rax
0x140073e80  test    rax, rax
0x140073e83  jnz     short loc_140073EBB
0x140073e85  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e8c  lea     rax, WPP_GLOBAL_Control
0x140073e93  cmp     rcx, rax
0x140073e96  jz      short loc_140073EB1
0x140073e98  test    byte ptr [rcx+1Ch], 1
0x140073e9c  jz      short loc_140073EB1
0x140073e9e  mov     rcx, [rcx+10h]
0x140073ea2  lea     edx, [rbx-26h]
0x140073ea5  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140073eac  call    WPP_SF_
0x140073eb1  mov     eax, 8
0x140073eb6  jmp     loc_1400742A1
0x140073ebb  lea     r8, aNtServiceContr; ".\\NT Service Control Manager"
0x140073ec2  mov     rdx, rbx; unsigned __int64
0x140073ec5  mov     rcx, rax; unsigned __int16 *
0x140073ec8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140073ecd  xor     eax, eax
0x140073ecf  jmp     loc_1400742A1
0x140073ed4  xorps   xmm0, xmm0
0x140073ed7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140073ede  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x140073ee2  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x140073ee6  mov     edx, 800h; AccessMask
0x140073eeb  mov     [rbp+ObjectAttributes.Attributes], r14d
0x140073eef  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x140073ef3  mov     [rbp+ObjectAttributes.ObjectName], r14
0x140073ef7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140073efc  call    cs:__imp_LsaLookupOpenLocalPolicy
0x140073f02  mov     ebx, eax
0x140073f04  test    eax, eax
0x140073f06  jns     short loc_140073F46
0x140073f08  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f0f  lea     rax, WPP_GLOBAL_Control
0x140073f16  cmp     rcx, rax
0x140073f19  jz      short loc_140073F39
0x140073f1b  test    byte ptr [rcx+1Ch], 1
0x140073f1f  jz      short loc_140073F39
0x140073f21  mov     rcx, [rcx+10h]
0x140073f25  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140073f2c  mov     edx, 15h
0x140073f31  mov     r9d, ebx
0x140073f34  call    WPP_SF_d
0x140073f39  mov     ecx, ebx; Status
0x140073f3b  call    cs:__imp_RtlNtStatusToDosError
0x140073f41  jmp     loc_1400742A1
0x140073f46  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x140073f4a  lea     rax, [rbp+var_40]
0x140073f4e  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x140073f52  mov     [rsp+70h+Names], rax; Names
0x140073f57  lea     r8, [rbp+Sids]; Sids
0x140073f5b  mov     edx, 1; Count
0x140073f60  call    cs:__imp_LsaLookupTranslateSids
0x140073f66  mov     ebx, eax
0x140073f68  test    eax, eax
0x140073f6a  jns     short loc_140073FAC
0x140073f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f73  lea     rax, WPP_GLOBAL_Control
0x140073f7a  cmp     rcx, rax
0x140073f7d  jz      short loc_140073F9D
0x140073f7f  test    byte ptr [rcx+1Ch], 1
0x140073f83  jz      short loc_140073F9D
0x140073f85  mov     rcx, [rcx+10h]
0x140073f89  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140073f90  mov     edx, 16h
0x140073f95  mov     r9d, ebx
0x140073f98  call    WPP_SF_d
0x140073f9d  mov     ecx, ebx; Status
0x140073f9f  call    cs:__imp_RtlNtStatusToDosError
0x140073fa5  mov     ebx, eax
0x140073fa7  jmp     loc_140074277
0x140073fac  cmp     [rbp+ReferencedDomains], r14
0x140073fb0  jz      loc_140074237
0x140073fb6  mov     rcx, [rbp+var_40]
0x140073fba  test    rcx, rcx
0x140073fbd  jz      loc_140074237
0x140073fc3  mov     eax, [rcx]
0x140073fc5  sub     eax, 7
0x140073fc8  cmp     eax, 1
0x140073fcb  jbe     loc_140074214
0x140073fd1  movsxd  r8, dword ptr [rcx+18h]
0x140073fd5  test    r8d, r8d
0x140073fd8  jns     short loc_140074018
0x140073fda  mov     rcx, cs:WPP_GLOBAL_Control
0x140073fe1  lea     rax, WPP_GLOBAL_Control
0x140073fe8  cmp     rcx, rax
0x140073feb  jz      loc_140074272
0x140073ff1  test    byte ptr [rcx+1Ch], 1
0x140073ff5  jz      loc_140074272
0x140073ffb  mov     rcx, [rcx+10h]
0x140073fff  mov     r9d, r8d
0x140074002  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140074009  mov     edx, 19h
0x14007400e  call    WPP_SF_d
0x140074013  jmp     loc_140074272
0x140074018  mov     rax, [rbp+ReferencedDomains]
0x14007401c  cmp     [rax], r14d
0x14007401f  jnz     short loc_14007405C
0x140074021  mov     rcx, cs:WPP_GLOBAL_Control
0x140074028  lea     rax, WPP_GLOBAL_Control
0x14007402f  cmp     rcx, rax
0x140074032  jz      loc_140074272
0x140074038  test    byte ptr [rcx+1Ch], 1
0x14007403c  jz      loc_140074272
0x140074042  mov     edx, 1Ah
0x140074047  mov     rcx, [rcx+10h]
0x14007404b  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140074052  call    WPP_SF_
0x140074057  jmp     loc_140074272
0x14007405c  mov     rax, [rbp+ReferencedDomains]
0x140074060  lea     rdx, [r8+r8*2]
0x140074064  mov     ebx, 8
0x140074069  mov     rcx, [rax+8]
0x14007406d  mov     rax, [rbp+var_40]
0x140074071  movzx   esi, word ptr [rcx+rdx*8]
0x140074075  mov     edx, ebx; Flags
0x140074077  movzx   ecx, word ptr [rax+8]
0x14007407b  add     rsi, rcx
0x14007407e  mov     rcx, gs:60h
0x140074087  mov     rcx, [rcx+30h]; HeapHandle
0x14007408b  lea     r8, [rsi+4]; Size
0x14007408f  call    cs:__imp_RtlAllocateHeap
0x140074095  mov     [rdi], rax
0x140074098  test    rax, rax
0x14007409b  jnz     short loc_1400740D6
0x14007409d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740a4  lea     rax, WPP_GLOBAL_Control
0x1400740ab  cmp     rcx, rax
0x1400740ae  jz      loc_140074277
0x1400740b4  test    byte ptr [rcx+1Ch], 1
0x1400740b8  jz      loc_140074277
0x1400740be  mov     rcx, [rcx+10h]
0x1400740c2  lea     edx, [rbx+13h]
0x1400740c5  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x1400740cc  call    WPP_SF_
0x1400740d1  jmp     loc_140074277
0x1400740d6  lea     rcx, [rbp+ProductType]; ProductType
0x1400740da  call    cs:__imp_RtlGetNtProductType
0x1400740e0  test    al, al
0x1400740e2  jnz     short loc_14007413A
0x1400740e4  call    cs:__imp_GetLastError
0x1400740ea  mov     ebx, eax
0x1400740ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740f3  lea     rax, WPP_GLOBAL_Control
0x1400740fa  cmp     rcx, rax
0x1400740fd  jz      short loc_14007411D
0x1400740ff  test    byte ptr [rcx+1Ch], 1
0x140074103  jz      short loc_14007411D
0x140074105  mov     rcx, [rcx+10h]
0x140074109  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140074110  mov     edx, 1Ch
0x140074115  mov     r9d, ebx
0x140074118  call    WPP_SF_d
0x14007411d  mov     rcx, gs:60h
0x140074126  xor     edx, edx; Flags
0x140074128  mov     r8, [rdi]; P
0x14007412b  mov     rcx, [rcx+30h]; HeapHandle
0x14007412f  call    cs:__imp_RtlFreeHeap
0x140074135  jmp     loc_140074277
0x14007413a  cmp     [rbp+ProductType], 2
0x14007413e  mov     ebx, r14d
0x140074141  jz      short loc_1400741BB
0x140074143  call    ?ScGetAccountDomainInfo@@YAKXZ; ScGetAccountDomainInfo(void)
0x140074148  mov     ebx, eax
0x14007414a  test    eax, eax
0x14007414c  jnz     short loc_14007411D
0x14007414e  mov     rax, [rbp+var_40]
0x140074152  mov     r8b, 1; CaseInsensitive
0x140074155  movsxd  rcx, dword ptr [rax+18h]
0x140074159  mov     rax, [rbp+ReferencedDomains]
0x14007415d  lea     rdx, [rcx+rcx*2]
0x140074161  mov     rcx, [rax+8]
0x140074165  lea     rcx, [rcx+rdx*8]; String1
0x140074169  lea     rdx, ?ScAccountDomain@@3U_UNICODE_STRING@@A; String2
0x140074170  call    cs:__imp_RtlEqualUnicodeString
0x140074176  test    al, al
0x140074178  jnz     short loc_1400741A6
0x14007417a  mov     rax, [rbp+var_40]
0x14007417e  lea     rdx, ?ScComputerName@@3U_UNICODE_STRING@@A; String2
0x140074185  mov     r8b, 1; CaseInsensitive
0x140074188  movsxd  rcx, dword ptr [rax+18h]
0x14007418c  mov     rax, [rbp+ReferencedDomains]
0x140074190  lea     r9, [rcx+rcx*2]
0x140074194  mov     rcx, [rax+8]
0x140074198  lea     rcx, [rcx+r9*8]; String1
0x14007419c  call    cs:__imp_RtlEqualUnicodeString
0x1400741a2  test    al, al
0x1400741a4  jz      short loc_1400741BB
0x1400741a6  mov     rcx, [rdi]; unsigned __int16 *
0x1400741a9  lea     r8, asc_1400A65F4; "."
0x1400741b0  lea     rdx, [rsi+4]; unsigned __int64
0x1400741b4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400741b9  jmp     short loc_1400741E1
0x1400741bb  mov     rax, [rbp+var_40]
0x1400741bf  movsxd  rcx, dword ptr [rax+18h]
0x1400741c3  mov     rax, [rbp+ReferencedDomains]
0x1400741c7  lea     r9, [rcx+rcx*2]
0x1400741cb  mov     rcx, [rdi]; void *
0x1400741ce  mov     rdx, [rax+8]
0x1400741d2  movzx   r8d, word ptr [rdx+r9*8]; Size
0x1400741d7  mov     rdx, [rdx+r9*8+8]; Src
0x1400741dc  call    memmove
0x1400741e1  mov     rcx, [rdi]
0x1400741e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400741e8  inc     rax
0x1400741eb  cmp     [rcx+rax*2], r14w
0x1400741f0  jnz     short loc_1400741E8
0x1400741f2  mov     word ptr [rcx+rax*2], 5Ch ; '\'
0x1400741f8  lea     rcx, [rcx+rax*2]
0x1400741fc  mov     rdx, [rbp+var_40]
0x140074200  add     rcx, 2; void *
0x140074204  movzx   r8d, word ptr [rdx+8]; Size
0x140074209  mov     rdx, [rdx+10h]; Src
0x14007420d  call    memmove
0x140074212  jmp     short loc_140074277
0x140074214  mov     rcx, cs:WPP_GLOBAL_Control
0x14007421b  lea     rax, WPP_GLOBAL_Control
0x140074222  cmp     rcx, rax
0x140074225  jz      short loc_140074272
0x140074227  test    byte ptr [rcx+1Ch], 1
0x14007422b  jz      short loc_140074272
0x14007422d  mov     edx, 18h
0x140074232  jmp     loc_140074047
0x140074237  mov     rcx, cs:WPP_GLOBAL_Control
0x14007423e  lea     rax, WPP_GLOBAL_Control
0x140074245  cmp     rcx, rax
0x140074248  jz      short loc_140074272
0x14007424a  test    byte ptr [rcx+1Ch], 1
0x14007424e  jz      short loc_140074272
0x140074250  mov     rax, [rbp+var_40]
0x140074254  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x14007425b  mov     r9, [rbp+ReferencedDomains]
0x14007425f  mov     edx, 17h
0x140074264  mov     rcx, [rcx+10h]
0x140074268  mov     [rsp+70h+Names], rax
0x14007426d  call    WPP_SF_qq
0x140074272  mov     ebx, 1Fh
0x140074277  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x14007427b  test    rcx, rcx
0x14007427e  jz      short loc_140074286
0x140074280  call    cs:__imp_LsaLookupFreeMemory
0x140074286  mov     rcx, [rbp+var_40]; Buffer
0x14007428a  test    rcx, rcx
0x14007428d  jz      short loc_140074295
0x14007428f  call    cs:__imp_LsaLookupFreeMemory
0x140074295  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x140074299  call    cs:__imp_LsaLookupClose
0x14007429f  mov     eax, ebx
0x1400742a1  add     rsp, 70h
0x1400742a5  pop     r14
0x1400742a7  pop     rdi
0x1400742a8  pop     rsi
0x1400742a9  pop     rbx
0x1400742aa  pop     rbp
0x1400742ab  retn
```
