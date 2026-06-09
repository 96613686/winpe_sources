# SecpAddDll(_SECP_DLL_BINDING *)

- ea: `0x180013e40`
- end: `0x180013ffb`
- name: `?SecpAddDll@@YAHPEAU_SECP_DLL_BINDING@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800069d8`
- `0x1800070d0`

## callees

- `0x180013e40`
- `0x18001d478`
- `0x180022047`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180013e9a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180013e9a`
- `ntdll!RtlReleaseResource` at `0x180013edc`
- `ntdll!RtlReleaseResource` at `0x180013f30`
- `ntdll!RtlReleaseResource` at `0x180013f9a`
- `ntdll!RtlReleaseResource` at `0x180013fda`
- `ntdll!RtlReleaseResource` at `0x180013edc`
- `ntdll!RtlReleaseResource` at `0x180013f30`
- `ntdll!RtlReleaseResource` at `0x180013f9a`
- `ntdll!RtlReleaseResource` at `0x180013fda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013f09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013f09`

## pseudocode

```c
__int64 __fastcall SecpAddDll(struct _SECP_DLL_BINDING *a1, __int64 a2, __int64 a3)
{
  int v4; // ecx
  __int64 i; // rbx
  unsigned int v6; // edx
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  HLOCAL v9; // rax
  HLOCAL v10; // r14
  __int64 j; // rbx
  unsigned int v12; // edi
  __int64 v13; // rbx
  __int64 v15; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, *((_QWORD *)a1 + 3));
  v4 = SecPackageListLockCount;
  for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
    v4 = SecPackageListLockCount;
  }
  v6 = SecPackageDllCount;
  if ( SecPackageDllCount == SecPackageDllTotal )
  {
    if ( SecPackageDllTotal + 4 < SecPackageDllTotal )
    {
      v7 = 0;
      if ( v4 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v7]);
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < SecPackageListLockCount );
      }
      return 0;
    }
    v8 = 8LL * (SecPackageDllTotal + 4);
    if ( v8 > 0xFFFFFFFF )
    {
      v13 = 0;
      if ( v4 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v13]);
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < SecPackageListLockCount );
      }
      return 0;
    }
    v9 = LocalAlloc(0, (unsigned int)v8);
    v10 = v9;
    if ( !v9 )
    {
      for ( j = 0; (unsigned int)j < SecPackageListLockCount; j = (unsigned int)(j + 1) )
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * j]);
      return 0;
    }
    v12 = SecPackageDllTotal;
    memcpy_0(v9, SecPackageDllList, 8LL * SecPackageDllTotal);
    SecPackageDllTotal = v12 + 4;
    LocalFree(SecPackageDllList);
    v4 = SecPackageListLockCount;
    v6 = SecPackageDllCount;
    SecPackageDllList = v10;
  }
  else
  {
    v10 = SecPackageDllList;
  }
  ++*((_DWORD *)a1 + 8);
  v15 = 0;
  *((_DWORD *)a1 + 10) = v6;
  SecPackageDllCount = v6 + 1;
  *((_QWORD *)v10 + v6) = a1;
  if ( v4 )
  {
    do
    {
      RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v15]);
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < SecPackageListLockCount );
  }
  return 1;
}

```

## disassembly

```asm
0x180013e40  push    rbx
0x180013e42  push    rsi
0x180013e43  push    rdi
0x180013e44  push    r14
0x180013e46  push    r15
0x180013e48  sub     rsp, 20h
0x180013e4c  mov     rsi, rcx
0x180013e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e56  lea     rax, WPP_GLOBAL_Control
0x180013e5d  cmp     rcx, rax
0x180013e60  jz      short loc_180013E7A
0x180013e62  test    byte ptr [rcx+1Ch], 4
0x180013e66  jz      short loc_180013E7A
0x180013e68  mov     r9, [rsi+18h]
0x180013e6c  mov     edx, 0Ah
0x180013e71  mov     rcx, [rcx+10h]
0x180013e75  call    WPP_SF_S
0x180013e7a  mov     ecx, cs:SecPackageListLockCount
0x180013e80  lea     r15, SecPackageListLock
0x180013e87  xor     ebx, ebx
0x180013e89  test    ecx, ecx
0x180013e8b  jz      short loc_180013EAC
0x180013e8d  lea     rcx, [rbx+rbx*2]
0x180013e91  mov     dl, 1; Wait
0x180013e93  shl     rcx, 5
0x180013e97  add     rcx, r15; Resource
0x180013e9a  call    cs:__imp_RtlAcquireResourceExclusive
0x180013ea0  mov     ecx, cs:SecPackageListLockCount
0x180013ea6  inc     ebx
0x180013ea8  cmp     ebx, ecx
0x180013eaa  jb      short loc_180013E8D
0x180013eac  mov     edx, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x180013eb2  mov     eax, cs:?SecPackageDllTotal@@3KA; ulong SecPackageDllTotal
0x180013eb8  cmp     edx, eax
0x180013eba  jnz     loc_180013FAE
0x180013ec0  lea     edx, [rax+4]
0x180013ec3  cmp     edx, eax
0x180013ec5  jnb     short loc_180013EF1
0x180013ec7  xor     ebx, ebx
0x180013ec9  test    ecx, ecx
0x180013ecb  jz      loc_180013FAA
0x180013ed1  lea     rcx, [rbx+rbx*2]
0x180013ed5  shl     rcx, 5
0x180013ed9  add     rcx, r15; Resource
0x180013edc  call    cs:__imp_RtlReleaseResource
0x180013ee2  inc     ebx
0x180013ee4  cmp     ebx, cs:SecPackageListLockCount
0x180013eea  jb      short loc_180013ED1
0x180013eec  jmp     loc_180013FAA
0x180013ef1  mov     eax, edx
0x180013ef3  mov     edx, 0FFFFFFFFh
0x180013ef8  shl     rax, 3
0x180013efc  cmp     rax, rdx
0x180013eff  ja      loc_180013F89
0x180013f05  mov     edx, eax; uBytes
0x180013f07  xor     ecx, ecx; uFlags
0x180013f09  call    cs:__imp_LocalAlloc
0x180013f0f  mov     r14, rax
0x180013f12  test    rax, rax
0x180013f15  jnz     short loc_180013F42
0x180013f17  xor     ebx, ebx
0x180013f19  cmp     cs:SecPackageListLockCount, ebx
0x180013f1f  jbe     loc_180013FAA
0x180013f25  lea     rcx, [rbx+rbx*2]
0x180013f29  shl     rcx, 5
0x180013f2d  add     rcx, r15; Resource
0x180013f30  call    cs:__imp_RtlReleaseResource
0x180013f36  inc     ebx
0x180013f38  cmp     ebx, cs:SecPackageListLockCount
0x180013f3e  jb      short loc_180013F25
0x180013f40  jmp     short loc_180013FAA
0x180013f42  mov     edi, cs:?SecPackageDllTotal@@3KA; ulong SecPackageDllTotal
0x180013f48  mov     rcx, r14; void *
0x180013f4b  mov     rdx, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; Src
0x180013f52  mov     r8d, edi
0x180013f55  shl     r8, 3; Size
0x180013f59  call    memcpy_0
0x180013f5e  mov     rcx, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; hMem
0x180013f65  add     edi, 4
0x180013f68  mov     cs:?SecPackageDllTotal@@3KA, edi; ulong SecPackageDllTotal
0x180013f6e  call    cs:__imp_LocalFree
0x180013f74  mov     ecx, cs:SecPackageListLockCount
0x180013f7a  mov     edx, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x180013f80  mov     cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA, r14; _SECP_DLL_BINDING * * SecPackageDllList
0x180013f87  jmp     short loc_180013FB5
0x180013f89  xor     ebx, ebx
0x180013f8b  test    ecx, ecx
0x180013f8d  jz      short loc_180013FAA
0x180013f8f  lea     rcx, [rbx+rbx*2]
0x180013f93  shl     rcx, 5
0x180013f97  add     rcx, r15; Resource
0x180013f9a  call    cs:__imp_RtlReleaseResource
0x180013fa0  inc     ebx
0x180013fa2  cmp     ebx, cs:SecPackageListLockCount
0x180013fa8  jb      short loc_180013F8F
0x180013faa  xor     eax, eax
0x180013fac  jmp     short loc_180013FEF
0x180013fae  mov     r14, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; _SECP_DLL_BINDING * * SecPackageDllList
0x180013fb5  inc     dword ptr [rsi+20h]
0x180013fb8  xor     ebx, ebx
0x180013fba  mov     eax, edx
0x180013fbc  mov     [rsi+28h], edx
0x180013fbf  inc     edx
0x180013fc1  mov     cs:?SecPackageDllCount@@3KA, edx; ulong SecPackageDllCount
0x180013fc7  mov     [r14+rax*8], rsi
0x180013fcb  test    ecx, ecx
0x180013fcd  jz      short loc_180013FEA
0x180013fcf  lea     rcx, [rbx+rbx*2]
0x180013fd3  shl     rcx, 5
0x180013fd7  add     rcx, r15; Resource
0x180013fda  call    cs:__imp_RtlReleaseResource
0x180013fe0  inc     ebx
0x180013fe2  cmp     ebx, cs:SecPackageListLockCount
0x180013fe8  jb      short loc_180013FCF
0x180013fea  mov     eax, 1
0x180013fef  add     rsp, 20h
0x180013ff3  pop     r15
0x180013ff5  pop     r14
0x180013ff7  pop     rdi
0x180013ff8  pop     rsi
0x180013ff9  pop     rbx
0x180013ffa  retn
```
