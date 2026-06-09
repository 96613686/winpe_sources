# SddlpGetRootDomainSid

- ea: `0x1800231e8`
- end: `0x18002336c`
- name: `SddlpGetRootDomainSid`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180004f20`

## callees

- `0x18000cba0`
- `0x18000cd60`
- `0x18000dbb0`
- `0x18000dc40`
- `0x1800231e8`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800232e1`
- `ntdll!RtlCopySid` at `0x1800232e1`
- `ntdll!RtlNtStatusToDosError` at `0x18002334c`
- `ntdll!RtlNtStatusToDosError` at `0x18002334c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023354`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023354`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002332e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002333c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002332e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002333c`

## pseudocode

```c
_BOOL8 SddlpGetRootDomainSid()
{
  PLSA_TRANSLATED_SID2 v0; // rsi
  PVOID v1; // r14
  NTSTATUS v2; // eax
  PVOID v3; // rdi
  int v4; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  DWORD v7; // ecx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+90h] [rbp+30h] BYREF
  PVOID DomainInfo; // [rsp+98h] [rbp+38h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+A0h] [rbp+40h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+A8h] [rbp+48h] BYREF

  PolicyHandle = 0;
  v0 = 0;
  ReferencedDomains = 0;
  v1 = 0;
  Sids = 0;
  DomainInfo = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  v3 = PolicyHandle;
  v4 = v2;
  if ( v2 >= 0 )
  {
    v4 = LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, &DomainInfo);
    if ( v4 < 0 )
    {
      v1 = DomainInfo;
    }
    else
    {
      LsaLookupClose(v3);
      PolicyHandle = 0;
      v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x800u, &PolicyHandle);
      v1 = DomainInfo;
      v4 = v5;
      v3 = PolicyHandle;
      if ( v5 >= 0 )
      {
        v6 = LsaLookupTranslateNames(
               PolicyHandle,
               0,
               1u,
               (PLSA_UNICODE_STRING)DomainInfo + 2,
               &ReferencedDomains,
               &Sids);
        v0 = Sids;
        v4 = v6;
        if ( v6 >= 0 )
        {
          if ( Sids->Use == SidTypeDomain )
          {
            EnterCriticalSection(&SddlSidLookupCritical);
            v4 = RtlCopySid(SizeofRootDomSidBuf, RootDomSidBuf, v0->Sid);
            if ( v4 >= 0 )
              RootDomInited = 1;
            LeaveCriticalSection(&SddlSidLookupCritical);
          }
          else
          {
            v4 = -1073741603;
          }
        }
      }
    }
  }
  if ( v3 )
    LsaLookupClose(v3);
  if ( ReferencedDomains )
    LocalFree(ReferencedDomains);
  if ( v0 )
    LocalFree(v0);
  if ( v1 )
    LocalFree(v1);
  if ( v4 < 0 )
    v7 = RtlNtStatusToDosError(v4);
  else
    v7 = 0;
  SetLastError(v7);
  return v4 == 0;
}

```

## disassembly

```asm
0x1800231e8  push    rbp
0x1800231ea  push    rbx
0x1800231eb  push    rsi
0x1800231ec  push    rdi
0x1800231ed  push    r14
0x1800231ef  mov     rbp, rsp
0x1800231f2  sub     rsp, 60h
0x1800231f6  xorps   xmm0, xmm0
0x1800231f9  mov     [rbp+PolicyHandle], 0
0x180023201  xor     esi, esi
0x180023203  mov     [rbp+arg_18], 0
0x18002320b  xor     r14d, r14d
0x18002320e  mov     [rbp+arg_10], rsi
0x180023212  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x180023216  mov     [rbp+DomainInfo], r14
0x18002321a  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002321e  lea     edx, [rsi+1]; AccessMask
0x180023221  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180023225  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180023229  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002322d  call    LsaLookupOpenLocalPolicy
0x180023232  mov     rdi, [rbp+PolicyHandle]
0x180023236  mov     ebx, eax
0x180023238  test    eax, eax
0x18002323a  js      loc_18002330A
0x180023240  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180023244  mov     rcx, rdi; PolicyHandle
0x180023247  lea     edx, [rsi+0Ch]; DomainInfoClass
0x18002324a  call    LsaLookupGetDomainInfo
0x18002324f  mov     ebx, eax
0x180023251  test    eax, eax
0x180023253  js      loc_180023306
0x180023259  mov     rcx, rdi; ObjectHandle
0x18002325c  call    LsaLookupClose
0x180023261  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x180023265  mov     [rbp+PolicyHandle], rsi
0x180023269  mov     edx, 800h; AccessMask
0x18002326e  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180023272  call    LsaLookupOpenLocalPolicy
0x180023277  mov     r14, [rbp+DomainInfo]
0x18002327b  mov     ebx, eax
0x18002327d  mov     rdi, [rbp+PolicyHandle]
0x180023281  test    eax, eax
0x180023283  js      loc_18002330A
0x180023289  lea     rax, [rbp+arg_10]
0x18002328d  xor     edx, edx; Flags
0x18002328f  mov     [rsp+60h+Sids], rax; Sids
0x180023294  lea     r9, [r14+20h]; Names
0x180023298  lea     rax, [rbp+arg_18]
0x18002329c  mov     rcx, rdi; PolicyHandle
0x18002329f  lea     r8d, [rsi+1]; Count
0x1800232a3  mov     [rsp+60h+ReferencedDomains], rax; ReferencedDomains
0x1800232a8  call    LsaLookupTranslateNames
0x1800232ad  mov     rsi, [rbp+arg_10]
0x1800232b1  mov     ebx, eax
0x1800232b3  test    eax, eax
0x1800232b5  js      short loc_18002330A
0x1800232b7  cmp     dword ptr [rsi], 3
0x1800232ba  jz      short loc_1800232C3
0x1800232bc  mov     ebx, 0C00000DDh
0x1800232c1  jmp     short loc_18002330A
0x1800232c3  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x1800232ca  call    cs:__imp_EnterCriticalSection
0x1800232d0  mov     ecx, cs:SizeofRootDomSidBuf; DestinationSidLength
0x1800232d6  lea     rdx, RootDomSidBuf; DestinationSid
0x1800232dd  mov     r8, [rsi+8]; SourceSid
0x1800232e1  call    cs:__imp_RtlCopySid
0x1800232e7  mov     ebx, eax
0x1800232e9  test    eax, eax
0x1800232eb  js      short loc_1800232F7
0x1800232ed  mov     cs:RootDomInited, 1
0x1800232f7  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x1800232fe  call    cs:__imp_LeaveCriticalSection
0x180023304  jmp     short loc_18002330A
0x180023306  mov     r14, [rbp+DomainInfo]
0x18002330a  test    rdi, rdi
0x18002330d  jz      short loc_180023317
0x18002330f  mov     rcx, rdi; ObjectHandle
0x180023312  call    LsaLookupClose
0x180023317  mov     rcx, [rbp+arg_18]; hMem
0x18002331b  test    rcx, rcx
0x18002331e  jz      short loc_180023326
0x180023320  call    cs:__imp_LocalFree
0x180023326  test    rsi, rsi
0x180023329  jz      short loc_180023334
0x18002332b  mov     rcx, rsi; hMem
0x18002332e  call    cs:__imp_LocalFree
0x180023334  test    r14, r14
0x180023337  jz      short loc_180023342
0x180023339  mov     rcx, r14; hMem
0x18002333c  call    cs:__imp_LocalFree
0x180023342  test    ebx, ebx
0x180023344  js      short loc_18002334A
0x180023346  xor     ecx, ecx
0x180023348  jmp     short loc_180023354
0x18002334a  mov     ecx, ebx; Status
0x18002334c  call    cs:__imp_RtlNtStatusToDosError
0x180023352  mov     ecx, eax; dwErrCode
0x180023354  call    cs:__imp_SetLastError
0x18002335a  xor     eax, eax
0x18002335c  test    ebx, ebx
0x18002335e  setz    al
0x180023361  add     rsp, 60h
0x180023365  pop     r14
0x180023367  pop     rdi
0x180023368  pop     rsi
0x180023369  pop     rbx
0x18002336a  pop     rbp
0x18002336b  retn
```
