# LsaLookupClientInitializeSidCache

- ea: `0x1800204c8`
- end: `0x18002061c`
- name: `LsaLookupClientInitializeSidCache`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000de94`
- `0x18001ffd4`

## callees

- `0x180008010`
- `0x18000cd60`
- `0x18000dbb0`
- `0x18000dc40`
- `0x180013ea8`
- `0x18001fdb4`
- `0x1800204c8`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180020573`
- `ntdll!RtlCopySid` at `0x180020573`
- `ntdll!RtlLengthSid` at `0x180020543`
- `ntdll!RtlLengthSid` at `0x180020543`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800205eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800205eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020589`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020589`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002057c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002057c`

## pseudocode

```c
__int64 LsaLookupClientInitializeSidCache()
{
  NTSTATUS v0; // edi
  void *v1; // rbx
  PSID *v2; // rsi
  void *v3; // rcx
  ULONG v4; // r15d
  void *Memory; // rax
  __int64 i; // rsi
  const WCHAR *v7; // rcx
  BOOL v8; // eax
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+80h] [rbp+30h] BYREF
  void *v12; // [rsp+88h] [rbp+38h] BYREF
  PVOID DomainInfo; // [rsp+90h] [rbp+40h] BYREF

  v0 = 0;
  v1 = 0;
  PolicyHandle = 0;
  DomainInfo = 0;
  v12 = 0;
  if ( LsaLookupClientSidCacheInitialized )
    return (unsigned int)v0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v0 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v0 >= 0 )
  {
    v0 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
    if ( v0 >= 0 )
    {
      v2 = (PSID *)DomainInfo;
      if ( DomainInfo )
      {
        v3 = (void *)*((_QWORD *)DomainInfo + 2);
        if ( v3 )
        {
          v4 = RtlLengthSid(v3);
          Memory = (void *)LsaLookupClientAllocateMemory(v4);
          v12 = Memory;
          v1 = Memory;
          if ( !Memory )
          {
            v0 = -1073741801;
            goto LABEL_14;
          }
          RtlCopySid(v4, Memory, v2[2]);
          LocalFree(v2);
        }
      }
    }
    AcquireSRWLockExclusive(&LsaLookupClientSidCacheLock);
    if ( !LsaLookupClientSidCacheInitialized )
    {
      AccountDomainSid = v1;
      v1 = 0;
      v12 = 0;
      for ( i = 0; i != 8; ++i )
      {
        v7 = WellKnownSidStringPrefixes[i];
        DomainInfo = 0;
        v8 = ConvertStringSidToSidW(v7, &DomainInfo);
        *(&WellKnownSidPrefixes + i) = (HLOCAL)((unsigned __int64)DomainInfo & -(__int64)v8);
      }
      LsaLookupClientSidCacheInitialized = 1;
    }
    ReleaseSRWLockExclusive(&LsaLookupClientSidCacheLock);
  }
LABEL_14:
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  if ( v1 )
    LsaLookupClientFreeMemory(&v12);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800204c8  push    rbp
0x1800204ca  push    rbx
0x1800204cb  push    rsi
0x1800204cc  push    rdi
0x1800204cd  push    r15
0x1800204cf  mov     rbp, rsp
0x1800204d2  sub     rsp, 50h
0x1800204d6  xor     edi, edi
0x1800204d8  xor     ebx, ebx
0x1800204da  cmp     cs:LsaLookupClientSidCacheInitialized, bl
0x1800204e0  mov     [rbp+PolicyHandle], rdi
0x1800204e4  mov     [rbp+DomainInfo], rdi
0x1800204e8  mov     [rbp+arg_8], rbx
0x1800204ec  jnz     loc_18002060F
0x1800204f2  xorps   xmm0, xmm0
0x1800204f5  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x1800204f9  lea     edx, [rdi+1]; AccessMask
0x1800204fc  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180020500  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180020504  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180020508  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002050c  call    LsaLookupOpenLocalPolicy
0x180020511  mov     edi, eax
0x180020513  test    eax, eax
0x180020515  js      loc_1800205F1
0x18002051b  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002051f  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180020523  lea     edx, [rbx+5]; DomainInfoClass
0x180020526  call    LsaLookupGetDomainInfo
0x18002052b  mov     edi, eax
0x18002052d  test    eax, eax
0x18002052f  js      short loc_180020582
0x180020531  mov     rsi, [rbp+DomainInfo]
0x180020535  test    rsi, rsi
0x180020538  jz      short loc_180020582
0x18002053a  mov     rcx, [rsi+10h]; Sid
0x18002053e  test    rcx, rcx
0x180020541  jz      short loc_180020582
0x180020543  call    cs:__imp_RtlLengthSid
0x180020549  mov     ecx, eax
0x18002054b  mov     r15d, eax
0x18002054e  call    LsaLookupClientAllocateMemory
0x180020553  mov     [rbp+arg_8], rax
0x180020557  mov     rbx, rax
0x18002055a  test    rax, rax
0x18002055d  jnz     short loc_180020569
0x18002055f  mov     edi, 0C0000017h
0x180020564  jmp     loc_1800205F1
0x180020569  mov     r8, [rsi+10h]; SourceSid
0x18002056d  mov     rdx, rax; DestinationSid
0x180020570  mov     ecx, r15d; DestinationSidLength
0x180020573  call    cs:__imp_RtlCopySid
0x180020579  mov     rcx, rsi; hMem
0x18002057c  call    cs:__imp_LocalFree
0x180020582  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020589  call    cs:__imp_AcquireSRWLockExclusive
0x18002058f  cmp     cs:LsaLookupClientSidCacheInitialized, 0
0x180020596  jnz     short loc_1800205E4
0x180020598  mov     cs:AccountDomainSid, rbx
0x18002059f  lea     r15, __ImageBase
0x1800205a6  xor     ebx, ebx
0x1800205a8  mov     [rbp+arg_8], rbx
0x1800205ac  xor     esi, esi
0x1800205ae  mov     rcx, ds:rva WellKnownSidStringPrefixes[r15+rsi*8]; StringSid
0x1800205b6  lea     rdx, [rbp+DomainInfo]; Sid
0x1800205ba  mov     [rbp+DomainInfo], rbx
0x1800205be  call    ConvertStringSidToSidW
0x1800205c3  neg     eax
0x1800205c5  sbb     rcx, rcx
0x1800205c8  and     rcx, [rbp+DomainInfo]
0x1800205cc  mov     rva WellKnownSidPrefixes[r15+rsi*8], rcx
0x1800205d4  inc     rsi
0x1800205d7  cmp     rsi, 8
0x1800205db  jnz     short loc_1800205AE
0x1800205dd  mov     cs:LsaLookupClientSidCacheInitialized, 1
0x1800205e4  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x1800205eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800205f1  cmp     [rbp+PolicyHandle], 0
0x1800205f6  jz      short loc_180020601
0x1800205f8  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800205fc  call    LsaLookupClose
0x180020601  test    rbx, rbx
0x180020604  jz      short loc_18002060F
0x180020606  lea     rcx, [rbp+arg_8]
0x18002060a  call    LsaLookupClientFreeMemory
0x18002060f  mov     eax, edi
0x180020611  add     rsp, 50h
0x180020615  pop     r15
0x180020617  pop     rdi
0x180020618  pop     rsi
0x180020619  pop     rbx
0x18002061a  pop     rbp
0x18002061b  retn
```
