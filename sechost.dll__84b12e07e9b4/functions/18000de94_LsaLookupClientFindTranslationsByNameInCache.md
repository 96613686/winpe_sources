# LsaLookupClientFindTranslationsByNameInCache

- ea: `0x18000de94`
- end: `0x18000e0fb`
- name: `LsaLookupClientFindTranslationsByNameInCache`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ce20`

## callees

- `0x18000de94`
- `0x18001fdb4`
- `0x18001fde0`
- `0x18001fea0`
- `0x180020234`
- `0x180020314`
- `0x180020400`
- `0x180020480`
- `0x1800204c8`
- `0x1800208c0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000df23`
- `ntdll!RtlInitUnicodeString` at `0x18000df23`
- `ntdll!RtlCopySid` at `0x18000e057`
- `ntdll!RtlCopySid` at `0x18000e057`
- `ntdll!RtlValidSid` at `0x18000e013`
- `ntdll!RtlValidSid` at `0x18000e013`
- `ntdll!RtlLengthSid` at `0x18000e02c`
- `ntdll!RtlLengthSid` at `0x18000e02c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000df4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000df4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e093`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e093`

## pseudocode

```c
__int64 __fastcall LsaLookupClientFindTranslationsByNameInCache(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _DWORD *a6,
        _BYTE *a7)
{
  _QWORD *v8; // rdi
  __int64 v10; // r12
  int v11; // ebx
  int v12; // edx
  int i; // esi
  __int64 CacheEntryByName; // rax
  __int64 v15; // rdi
  __int64 v16; // r13
  __int64 v17; // r12
  void *Memory; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-68h] BYREF
  __int128 v21; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v22[4]; // [rsp+50h] [rbp-48h] BYREF
  ULONG DestinationSidLength; // [rsp+A0h] [rbp+8h]
  _QWORD *v26; // [rsp+C8h] [rbp+30h]

  DestinationString = 0;
  *a3 = 0;
  v8 = a4;
  v22[0] = 0;
  v10 = a2;
  v21 = 0;
  *a4 = 0;
  *a6 = 0;
  *a7 = 0;
  *a5 = 0;
  v11 = LsaLookupClientInitializeSidCache();
  if ( v11 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\");
    LsaLookupClientRtlSplitNames(v10, v12, (unsigned int)&DestinationString, (unsigned int)v22, (__int64)&v21);
    AcquireSRWLockShared(&LsaLookupClientSidCacheLock);
    for ( i = 0; !i; i = 1 )
    {
      if ( *(_QWORD *)(v10 + 8) )
      {
        CacheEntryByName = LsaLookupClientFindCacheEntryByName(v22, &v21);
        v15 = CacheEntryByName;
        if ( CacheEntryByName )
        {
          if ( *(_BYTE *)(CacheEntryByName + 88) )
          {
            v16 = (unsigned int)*a6;
            v11 = LsaLookupClientInitializeReferencedDomains(a3);
            if ( v11 < 0 )
              break;
            v26 = (_QWORD *)(*a3 + 8LL);
            v11 = LsaLookupClientGrowTranslatedSidsList(v26, (unsigned int)(v16 + 1));
            if ( v11 < 0 )
              break;
            v11 = LsaLookupClientGrowTranslatedSidsList(a4, (unsigned int)(v16 + 1));
            if ( v11 < 0 )
              break;
            v11 = LsaLookupClientFillDomainInfoFromCacheEntry(v15, *v26 + 24 * v16);
            if ( v11 < 0 )
              break;
            if ( !RtlValidSid(*(PSID *)v15) )
            {
              v11 = -1073741811;
              break;
            }
            v17 = a4[v16];
            DestinationSidLength = RtlLengthSid(*(PSID *)v15);
            Memory = (void *)LsaLookupClientAllocateMemory(DestinationSidLength);
            *(_QWORD *)(v17 + 8) = Memory;
            if ( !Memory )
            {
              v11 = -1073741801;
              break;
            }
            RtlCopySid(DestinationSidLength, Memory, *(PSID *)v15);
            ++*a6;
            *(_DWORD *)(v17 + 16) = v16;
            *(_DWORD *)v17 = *(_DWORD *)(v15 + 16);
            v10 = a2;
            ++*(_DWORD *)*a3;
          }
        }
      }
    }
    ReleaseSRWLockShared(&LsaLookupClientSidCacheLock);
    v8 = a4;
    if ( *a6 == 1 )
      *a7 = 1;
  }
  if ( *a7 )
  {
    if ( v11 >= 0 )
      return (unsigned int)v11;
  }
  else
  {
    v11 = -1073741823;
  }
  if ( *a3 )
  {
    LsaLookupClientFreeTranslatedSids(*(unsigned int *)*a3, v8);
    LsaLookupClientFreeReferencedDomains(a3);
  }
  *a6 = 0;
  *a7 = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000de94  mov     rax, rsp
0x18000de97  mov     [rax+18h], rbx
0x18000de9b  mov     [rax+20h], r9
0x18000de9f  mov     [rax+10h], rdx
0x18000dea3  mov     [rax+8], ecx
0x18000dea6  push    rbp
0x18000dea7  push    rsi
0x18000dea8  push    rdi
0x18000dea9  push    r12
0x18000deab  push    r13
0x18000dead  push    r14
0x18000deaf  push    r15
0x18000deb1  sub     rsp, 60h
0x18000deb5  mov     r15, [rsp+98h+arg_28]
0x18000debd  xorps   xmm0, xmm0
0x18000dec0  mov     rbp, [rsp+98h+arg_30]
0x18000dec8  xorps   xmm1, xmm1
0x18000decb  movups  xmmword ptr [rax-68h], xmm0
0x18000decf  mov     qword ptr [r8], 0
0x18000ded6  mov     rdi, r9
0x18000ded9  movups  xmmword ptr [rax-48h], xmm1
0x18000dedd  mov     r14, r8
0x18000dee0  mov     r12, rdx
0x18000dee3  movups  xmmword ptr [rax-58h], xmm0
0x18000dee7  mov     rax, [rsp+98h+arg_20]
0x18000deef  mov     qword ptr [r9], 0
0x18000def6  mov     dword ptr [r15], 0
0x18000defd  mov     byte ptr [rbp+0], 0
0x18000df01  mov     qword ptr [rax], 0
0x18000df08  call    LsaLookupClientInitializeSidCache
0x18000df0d  mov     ebx, eax
0x18000df0f  test    eax, eax
0x18000df11  js      loc_18000E0AB
0x18000df17  lea     rdx, SourceString; "\\"
0x18000df1e  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x18000df23  call    cs:__imp_RtlInitUnicodeString
0x18000df29  lea     rax, [rsp+98h+var_58]
0x18000df2e  mov     rcx, r12
0x18000df31  lea     r9, [rsp+98h+var_48]
0x18000df36  mov     [rsp+98h+var_78], rax
0x18000df3b  lea     r8, [rsp+98h+DestinationString]
0x18000df40  call    LsaLookupClientRtlSplitNames
0x18000df45  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x18000df4c  call    cs:__imp_AcquireSRWLockShared
0x18000df52  xor     esi, esi
0x18000df54  cmp     esi, 1
0x18000df57  jnb     loc_18000E08C
0x18000df5d  mov     eax, esi
0x18000df5f  add     rax, rax
0x18000df62  cmp     qword ptr [r12+rax*8+8], 0
0x18000df68  jz      loc_18000E079
0x18000df6e  lea     rdx, [rsp+98h+var_58]
0x18000df73  lea     rcx, [rsp+98h+var_48]
0x18000df78  call    LsaLookupClientFindCacheEntryByName
0x18000df7d  mov     rdi, rax
0x18000df80  test    rax, rax
0x18000df83  jz      loc_18000E079
0x18000df89  cmp     byte ptr [rax+58h], 0
0x18000df8d  jz      loc_18000E079
0x18000df93  mov     r13d, [r15]
0x18000df96  mov     rcx, r14
0x18000df99  call    LsaLookupClientInitializeReferencedDomains
0x18000df9e  mov     ebx, eax
0x18000dfa0  test    eax, eax
0x18000dfa2  js      loc_18000E08C
0x18000dfa8  mov     rax, [r14]
0x18000dfab  lea     edx, [r13+1]
0x18000dfaf  add     rax, 8
0x18000dfb3  mov     rcx, rax
0x18000dfb6  mov     [rsp+98h+arg_28], rax
0x18000dfbe  call    LsaLookupClientGrowTranslatedSidsList
0x18000dfc3  mov     ebx, eax
0x18000dfc5  test    eax, eax
0x18000dfc7  js      loc_18000E08C
0x18000dfcd  mov     rcx, [rsp+98h+arg_18]
0x18000dfd5  lea     edx, [r13+1]
0x18000dfd9  call    LsaLookupClientGrowTranslatedSidsList
0x18000dfde  mov     ebx, eax
0x18000dfe0  test    eax, eax
0x18000dfe2  js      loc_18000E08C
0x18000dfe8  mov     rax, [rsp+98h+arg_28]
0x18000dff0  lea     rcx, ds:0[r13*2]
0x18000dff8  add     rcx, r13
0x18000dffb  mov     rax, [rax]
0x18000dffe  lea     rdx, [rax+rcx*8]
0x18000e002  mov     rcx, rdi
0x18000e005  call    LsaLookupClientFillDomainInfoFromCacheEntry
0x18000e00a  mov     ebx, eax
0x18000e00c  test    eax, eax
0x18000e00e  js      short loc_18000E08C
0x18000e010  mov     rcx, [rdi]; Sid
0x18000e013  call    cs:__imp_RtlValidSid
0x18000e019  test    al, al
0x18000e01b  jz      short loc_18000E087
0x18000e01d  mov     rax, [rsp+98h+arg_18]
0x18000e025  mov     rcx, [rdi]; Sid
0x18000e028  mov     r12, [rax+r13*8]
0x18000e02c  call    cs:__imp_RtlLengthSid
0x18000e032  mov     ecx, eax
0x18000e034  mov     [rsp+98h+DestinationSidLength], eax
0x18000e03b  call    LsaLookupClientAllocateMemory
0x18000e040  mov     [r12+8], rax
0x18000e045  test    rax, rax
0x18000e048  jz      short loc_18000E080
0x18000e04a  mov     r8, [rdi]; SourceSid
0x18000e04d  mov     rdx, rax; DestinationSid
0x18000e050  mov     ecx, [rsp+98h+DestinationSidLength]; DestinationSidLength
0x18000e057  call    cs:__imp_RtlCopySid
0x18000e05d  inc     dword ptr [r15]
0x18000e060  mov     [r12+10h], r13d
0x18000e065  mov     eax, [rdi+10h]
0x18000e068  mov     [r12], eax
0x18000e06c  mov     rax, [r14]
0x18000e06f  mov     r12, [rsp+98h+arg_8]
0x18000e077  inc     dword ptr [rax]
0x18000e079  inc     esi
0x18000e07b  jmp     loc_18000DF54
0x18000e080  mov     ebx, 0C0000017h
0x18000e085  jmp     short loc_18000E08C
0x18000e087  mov     ebx, 0C000000Dh
0x18000e08c  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x18000e093  call    cs:__imp_ReleaseSRWLockShared
0x18000e099  cmp     dword ptr [r15], 1
0x18000e09d  mov     rdi, [rsp+98h+arg_18]
0x18000e0a5  jnz     short loc_18000E0AB
0x18000e0a7  mov     byte ptr [rbp+0], 1
0x18000e0ab  cmp     byte ptr [rbp+0], 0
0x18000e0af  jnz     short loc_18000E0B8
0x18000e0b1  mov     ebx, 0C0000001h
0x18000e0b6  jmp     short loc_18000E0BC
0x18000e0b8  test    ebx, ebx
0x18000e0ba  jns     short loc_18000E0E1
0x18000e0bc  mov     rcx, [r14]
0x18000e0bf  test    rcx, rcx
0x18000e0c2  jz      short loc_18000E0D6
0x18000e0c4  mov     ecx, [rcx]
0x18000e0c6  mov     rdx, rdi
0x18000e0c9  call    LsaLookupClientFreeTranslatedSids
0x18000e0ce  mov     rcx, r14
0x18000e0d1  call    LsaLookupClientFreeReferencedDomains
0x18000e0d6  mov     dword ptr [r15], 0
0x18000e0dd  mov     byte ptr [rbp+0], 0
0x18000e0e1  mov     eax, ebx
0x18000e0e3  mov     rbx, [rsp+98h+arg_10]
0x18000e0eb  add     rsp, 60h
0x18000e0ef  pop     r15
0x18000e0f1  pop     r14
0x18000e0f3  pop     r13
0x18000e0f5  pop     r12
0x18000e0f7  pop     rdi
0x18000e0f8  pop     rsi
0x18000e0f9  pop     rbp
0x18000e0fa  retn
```
