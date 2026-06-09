# CtxtHandlerInit

- ea: `0x18001a8ec`
- end: `0x18001aa19`
- name: `CtxtHandlerInit`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180026ad0`

## callees

- `0x18001a8ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001a96f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001a96f`
- `ntdll!RtlInitializeResource` at `0x18001a9b1`
- `ntdll!RtlInitializeResource` at `0x18001a9b1`
- `ntdll!RtlGetNtProductType` at `0x18001a943`
- `ntdll!RtlGetNtProductType` at `0x18001a943`
- `ntdll!RtlDeleteResource` at `0x18001a9ea`
- `ntdll!RtlDeleteResource` at `0x18001a9ea`

## pseudocode

```c
__int64 CtxtHandlerInit()
{
  int v0; // edi
  __int64 v1; // rdx
  __int64 v2; // rcx
  DWORD dwNumberOfProcessors; // eax
  unsigned int i; // esi
  _SYSTEM_INFO SystemInfo; // [rsp+28h] [rbp-50h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+80h] [rbp+8h] BYREF

  ProductType = 0;
  v0 = 0;
  v1 = 0;
  v2 = 0;
  do
  {
    *(&DigestContextList + v2 + 1) = (struct _LIST_ENTRY near *)&(&DigestContextList)[v2];
    (&DigestContextList)[v2] = (struct _LIST_ENTRY near *)&(&DigestContextList)[v2];
    ++v1;
    v2 += 2;
  }
  while ( v1 != 16 );
  DigestContextLockCount = 1;
  RtlGetNtProductType(&ProductType);
  if ( (unsigned int)(ProductType - 2) <= 1 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    if ( (SystemInfo.dwNumberOfProcessors & 1) != 0 )
      dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors + 1;
    if ( dwNumberOfProcessors > 4 )
      dwNumberOfProcessors = 4;
    if ( dwNumberOfProcessors )
      DigestContextLockCount = dwNumberOfProcessors;
  }
  for ( i = 0; i < DigestContextLockCount; ++i )
  {
    RtlInitializeResource((PRTL_RESOURCE)&(&DigestContextLock)[12 * i]);
    ++v0;
  }
  g_bContextInitialized = 1;
  return 0;
}

```

## disassembly

```asm
0x18001a8ec  mov     rax, rsp
0x18001a8ef  mov     [rax+10h], rbx
0x18001a8f3  mov     [rax+18h], rsi
0x18001a8f7  push    rdi
0x18001a8f8  push    r14
0x18001a8fa  push    r15
0x18001a8fc  sub     rsp, 60h
0x18001a900  xor     ebx, ebx
0x18001a902  mov     r14d, ebx
0x18001a905  mov     [rax+8], ebx
0x18001a908  mov     edi, ebx
0x18001a90a  mov     [rax-58h], ebx
0x18001a90d  mov     edx, ebx
0x18001a90f  mov     ecx, ebx
0x18001a911  lea     r8, ?DigestContextList@@3PAU_LIST_ENTRY@@A; _LIST_ENTRY near * DigestContextList
0x18001a918  lea     rax, [rcx+r8]
0x18001a91c  mov     [rcx+r8+8], rax
0x18001a921  mov     [rax], rax
0x18001a924  inc     rdx
0x18001a927  lea     rcx, [rcx+10h]
0x18001a92b  cmp     rdx, 10h
0x18001a92f  jnz     short loc_18001A918
0x18001a931  mov     cs:?DigestContextLockCount@@3KA, 1; ulong DigestContextLockCount
0x18001a93b  lea     rcx, [rsp+78h+ProductType]; ProductType
0x18001a943  call    cs:__imp_RtlGetNtProductType
0x18001a949  mov     eax, [rsp+78h+ProductType]
0x18001a950  add     eax, 0FFFFFFFEh
0x18001a953  cmp     eax, 1
0x18001a956  ja      short loc_18001A993
0x18001a958  xorps   xmm0, xmm0
0x18001a95b  movups  xmmword ptr [rsp+78h+SystemInfo], xmm0
0x18001a960  movups  xmmword ptr [rsp+78h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18001a965  movups  xmmword ptr [rsp+78h+SystemInfo.dwNumberOfProcessors], xmm0
0x18001a96a  lea     rcx, [rsp+78h+SystemInfo]; lpSystemInfo
0x18001a96f  call    cs:__imp_GetSystemInfo
0x18001a975  mov     eax, [rsp+78h+SystemInfo.dwNumberOfProcessors]
0x18001a979  test    al, 1
0x18001a97b  jz      short loc_18001A97F
0x18001a97d  inc     eax
0x18001a97f  mov     ecx, 4
0x18001a984  cmp     eax, ecx
0x18001a986  cmova   eax, ecx
0x18001a989  test    eax, eax
0x18001a98b  jz      short loc_18001A993
0x18001a98d  mov     cs:?DigestContextLockCount@@3KA, eax; ulong DigestContextLockCount
0x18001a993  mov     esi, ebx
0x18001a995  lea     r15, ?DigestContextLock@@3PAU_RTL_RESOURCE@@A; _RTL_RESOURCE near * DigestContextLock
0x18001a99c  cmp     esi, cs:?DigestContextLockCount@@3KA; ulong DigestContextLockCount
0x18001a9a2  jnb     short loc_18001A9D4
0x18001a9a4  mov     eax, esi
0x18001a9a6  lea     rcx, [rax+rax*2]
0x18001a9aa  shl     rcx, 5
0x18001a9ae  add     rcx, r15; Resource
0x18001a9b1  call    cs:__imp_RtlInitializeResource
0x18001a9b7  inc     edi
0x18001a9b9  mov     [rsp+78h+var_58], edi
0x18001a9bd  inc     esi
0x18001a9bf  jmp     short loc_18001A99C
0x18001a9c1  xor     ebx, ebx
0x18001a9c3  mov     r14d, 0C000009Ah
0x18001a9c9  lea     r15, ?DigestContextLock@@3PAU_RTL_RESOURCE@@A; _RTL_RESOURCE near * DigestContextLock
0x18001a9d0  mov     edi, [rsp+78h+var_58]
0x18001a9d4  test    r14d, r14d
0x18001a9d7  jns     short loc_18001A9F6
0x18001a9d9  test    edi, edi
0x18001a9db  jz      short loc_18001A9F6
0x18001a9dd  mov     ecx, ebx
0x18001a9df  lea     rcx, [rcx+rcx*2]
0x18001a9e3  shl     rcx, 5
0x18001a9e7  add     rcx, r15; Resource
0x18001a9ea  call    cs:__imp_RtlDeleteResource
0x18001a9f0  inc     ebx
0x18001a9f2  cmp     ebx, edi
0x18001a9f4  jb      short loc_18001A9DD
0x18001a9f6  mov     cs:?g_bContextInitialized@@3HA, 1; int g_bContextInitialized
0x18001aa00  mov     eax, r14d
0x18001aa03  lea     r11, [rsp+78h+var_18]
0x18001aa08  mov     rbx, [r11+28h]
0x18001aa0c  mov     rsi, [r11+30h]
0x18001aa10  mov     rsp, r11
0x18001aa13  pop     r15
0x18001aa15  pop     r14
0x18001aa17  pop     rdi
0x18001aa18  retn
```
