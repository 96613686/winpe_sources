# SecUnloadPackages

- ea: `0x18000d0f0`
- end: `0x18000d2a8`
- name: `SecUnloadPackages`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c904`

## callees

- `0x18000d0f0`
- `0x18000d2b0`
- `0x18000d30c`
- `0x18000d358`
- `0x180023010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000d264`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000d264`
- `ntdll!RtlReleaseResource` at `0x18000d291`
- `ntdll!RtlReleaseResource` at `0x18000d291`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d225`
- `ntdll!RtlDeleteResource` at `0x18000d237`
- `ntdll!RtlDeleteResource` at `0x18000d237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d17d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d19e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d17d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d19e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1ff`

## pseudocode

```c
NTSTATUS __fastcall SecUnloadPackages(char a1)
{
  HLOCAL v2; // rbx
  __int64 v3; // rax
  void (*v4)(void); // rax
  void *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // edx
  struct _SECP_DLL_BINDING **v11; // rcx
  int v12; // eax
  __int64 v13; // rbx
  __int64 i; // rbx
  __int64 j; // rbx

  if ( !a1 )
  {
    for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
      RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
  }
  while ( 1 )
  {
    v2 = SecPackageControlList;
    if ( SecPackageControlList == &SecPackageControlList )
      break;
    if ( *((HLOCAL **)SecPackageControlList + 1) != &SecPackageControlList
      || (v3 = *(_QWORD *)SecPackageControlList,
          *(HLOCAL *)(*(_QWORD *)SecPackageControlList + 8LL) != SecPackageControlList) )
    {
LABEL_24:
      __fastfail(3u);
    }
    SecPackageControlList = *(HLOCAL *)SecPackageControlList;
    *(_QWORD *)(v3 + 8) = &SecPackageControlList;
    v4 = (void (*)(void))*((_QWORD *)v2 + 25);
    if ( v4 )
      v4();
    LocalFree(*((HLOCAL *)v2 + 13));
    LocalFree(*((HLOCAL *)v2 + 15));
    LocalFree(*((HLOCAL *)v2 + 16));
    LocalFree(*((HLOCAL *)v2 + 18));
    if ( *((_QWORD *)v2 + 26) )
    {
      while ( 1 )
      {
        v6 = *((_QWORD *)v2 + 26);
        v7 = (_QWORD *)(v6 + 16);
        v8 = *(_QWORD **)(v6 + 16);
        if ( v8 == (_QWORD *)(v6 + 16) )
          break;
        if ( (_QWORD *)v8[1] != v7 )
          goto LABEL_24;
        v9 = *v8;
        if ( *(_QWORD **)(*v8 + 8LL) != v8 )
          goto LABEL_24;
        *v7 = v9;
        *(_QWORD *)(v9 + 8) = v7;
        LocalFree(v8);
      }
      LocalFree(*(HLOCAL *)(v6 + 8));
    }
    v5 = (void *)*((_QWORD *)v2 + 7);
    if ( v5 )
      SecpDerefDll(v5);
    LocalFree(v2);
  }
  SecpFreeSaslProfiles();
  SecpFreeBindings(v11, v10);
  LocalFree(SecPackageDllList);
  v12 = SecPackageListLockCount;
  if ( !a1 )
  {
    for ( j = 0; (unsigned int)j < SecPackageListLockCount; j = (unsigned int)(j + 1) )
    {
      RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * j]);
      v12 = SecPackageListLockCount;
    }
  }
  v13 = 0;
  if ( v12 )
  {
    do
    {
      RtlDeleteResource((PRTL_RESOURCE)&SecPackageListLock[12 * v13]);
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < SecPackageListLockCount );
  }
  return RtlDeleteCriticalSection(&SaslLock);
}

```

## disassembly

```asm
0x18000d0f0  push    rbx
0x18000d0f2  push    rbp
0x18000d0f3  push    rsi
0x18000d0f4  push    rdi
0x18000d0f5  sub     rsp, 28h
0x18000d0f9  lea     rbp, SecPackageListLock
0x18000d100  mov     dil, cl
0x18000d103  test    cl, cl
0x18000d105  jz      loc_18000D249
0x18000d10b  lea     rsi, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000d112  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000d119  cmp     rbx, rsi
0x18000d11c  jz      loc_18000D1EE
0x18000d122  cmp     [rbx+8], rsi
0x18000d126  jnz     loc_18000D279
0x18000d12c  mov     rax, [rbx]
0x18000d12f  cmp     [rax+8], rbx
0x18000d133  jnz     loc_18000D279
0x18000d139  mov     cs:?SecPackageControlList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY SecPackageControlList
0x18000d140  mov     [rax+8], rsi
0x18000d144  mov     rax, [rbx+0C8h]
0x18000d14b  test    rax, rax
0x18000d14e  jz      short loc_18000D155
0x18000d150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d155  mov     rcx, [rbx+68h]; hMem
0x18000d159  call    cs:__imp_LocalFree
0x18000d15f  mov     rcx, [rbx+78h]; hMem
0x18000d163  call    cs:__imp_LocalFree
0x18000d169  mov     rcx, [rbx+80h]; hMem
0x18000d170  call    cs:__imp_LocalFree
0x18000d176  mov     rcx, [rbx+90h]; hMem
0x18000d17d  call    cs:__imp_LocalFree
0x18000d183  cmp     qword ptr [rbx+0D0h], 0
0x18000d18b  jnz     short loc_18000D1A9
0x18000d18d  mov     rcx, [rbx+38h]; hMem
0x18000d191  test    rcx, rcx
0x18000d194  jz      short loc_18000D19B
0x18000d196  call    ?SecpDerefDll@@YAXPEAU_SECP_DLL_BINDING@@@Z; SecpDerefDll(_SECP_DLL_BINDING *)
0x18000d19b  mov     rcx, rbx; hMem
0x18000d19e  call    cs:__imp_LocalFree
0x18000d1a4  jmp     loc_18000D112
0x18000d1a9  mov     rdx, [rbx+0D0h]
0x18000d1b0  lea     rax, [rdx+10h]
0x18000d1b4  mov     rcx, [rax]; hMem
0x18000d1b7  cmp     rcx, rax
0x18000d1ba  jz      short loc_18000D1E2
0x18000d1bc  cmp     [rcx+8], rax
0x18000d1c0  jnz     loc_18000D279
0x18000d1c6  mov     rdx, [rcx]
0x18000d1c9  cmp     [rdx+8], rcx
0x18000d1cd  jnz     loc_18000D279
0x18000d1d3  mov     [rax], rdx
0x18000d1d6  mov     [rdx+8], rax
0x18000d1da  call    cs:__imp_LocalFree
0x18000d1e0  jmp     short loc_18000D1A9
0x18000d1e2  mov     rcx, [rdx+8]; hMem
0x18000d1e6  call    cs:__imp_LocalFree
0x18000d1ec  jmp     short loc_18000D18D
0x18000d1ee  call    SecpFreeSaslProfiles
0x18000d1f3  call    ?SecpFreeBindings@@YAXPEAPEAU_SECP_DLL_BINDING@@K@Z; SecpFreeBindings(_SECP_DLL_BINDING * *,ulong)
0x18000d1f8  mov     rcx, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; hMem
0x18000d1ff  call    cs:__imp_LocalFree
0x18000d205  mov     eax, cs:SecPackageListLockCount
0x18000d20b  test    dil, dil
0x18000d20e  jz      short loc_18000D280
0x18000d210  xor     ebx, ebx
0x18000d212  test    eax, eax
0x18000d214  jnz     short loc_18000D22C
0x18000d216  lea     rcx, SaslLock
0x18000d21d  add     rsp, 28h
0x18000d221  pop     rdi
0x18000d222  pop     rsi
0x18000d223  pop     rbp
0x18000d224  pop     rbx
0x18000d225  jmp     cs:__imp_RtlDeleteCriticalSection
0x18000d22c  lea     rcx, [rbx+rbx*2]
0x18000d230  shl     rcx, 5
0x18000d234  add     rcx, rbp; Resource
0x18000d237  call    cs:__imp_RtlDeleteResource
0x18000d23d  inc     ebx
0x18000d23f  cmp     ebx, cs:SecPackageListLockCount
0x18000d245  jnb     short loc_18000D216
0x18000d247  jmp     short loc_18000D22C
0x18000d249  xor     ebx, ebx
0x18000d24b  cmp     cs:SecPackageListLockCount, ebx
0x18000d251  jbe     loc_18000D10B
0x18000d257  lea     rcx, [rbx+rbx*2]
0x18000d25b  mov     dl, 1; Wait
0x18000d25d  shl     rcx, 5
0x18000d261  add     rcx, rbp; Resource
0x18000d264  call    cs:__imp_RtlAcquireResourceExclusive
0x18000d26a  inc     ebx
0x18000d26c  cmp     ebx, cs:SecPackageListLockCount
0x18000d272  jb      short loc_18000D257
0x18000d274  jmp     loc_18000D10B
0x18000d279  mov     ecx, 3
0x18000d27e  int     29h; Win8: RtlFailFast(ecx)
0x18000d280  xor     ebx, ebx
0x18000d282  test    eax, eax
0x18000d284  jz      short loc_18000D210
0x18000d286  lea     rcx, [rbx+rbx*2]
0x18000d28a  shl     rcx, 5
0x18000d28e  add     rcx, rbp; Resource
0x18000d291  call    cs:__imp_RtlReleaseResource
0x18000d297  mov     eax, cs:SecPackageListLockCount
0x18000d29d  inc     ebx
0x18000d29f  cmp     ebx, eax
0x18000d2a1  jb      short loc_18000D286
0x18000d2a3  jmp     loc_18000D210
```
