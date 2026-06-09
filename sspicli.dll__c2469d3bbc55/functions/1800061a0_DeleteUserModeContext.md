# DeleteUserModeContext

- ea: `0x1800061a0`
- end: `0x180006542`
- name: `DeleteUserModeContext`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005370`

## callees

- `0x1800061a0`
- `0x1800069d8`
- `0x180006eac`
- `0x1800070d0`
- `0x180008fc4`
- `0x18001d478`
- `0x180023010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000646d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180006506`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000646d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180006506`
- `ntdll!RtlReleaseResource` at `0x180006238`
- `ntdll!RtlReleaseResource` at `0x1800062d0`
- `ntdll!RtlReleaseResource` at `0x180006336`
- `ntdll!RtlReleaseResource` at `0x1800063ce`
- `ntdll!RtlReleaseResource` at `0x180006495`
- `ntdll!RtlReleaseResource` at `0x1800064c4`
- `ntdll!RtlReleaseResource` at `0x1800064e4`
- `ntdll!RtlReleaseResource` at `0x180006528`
- `ntdll!RtlReleaseResource` at `0x180006238`
- `ntdll!RtlReleaseResource` at `0x1800062d0`
- `ntdll!RtlReleaseResource` at `0x180006336`
- `ntdll!RtlReleaseResource` at `0x1800063ce`
- `ntdll!RtlReleaseResource` at `0x180006495`
- `ntdll!RtlReleaseResource` at `0x1800064c4`
- `ntdll!RtlReleaseResource` at `0x1800064e4`
- `ntdll!RtlReleaseResource` at `0x180006528`
- `ntdll!RtlAcquireResourceShared` at `0x1800061ea`
- `ntdll!RtlAcquireResourceShared` at `0x18000628f`
- `ntdll!RtlAcquireResourceShared` at `0x1800061ea`
- `ntdll!RtlAcquireResourceShared` at `0x18000628f`

## pseudocode

```c
__int64 __fastcall DeleteUserModeContext(void **a1)
{
  HLOCAL v2; // rsi
  struct _RTL_RESOURCE *v3; // rbp
  __int64 v4; // r8
  HLOCAL *v5; // rbx
  HLOCAL *v6; // rdi
  PVOID *v7; // rcx
  __int64 v8; // rdx
  int v9; // r8d
  struct _RTL_RESOURCE *v10; // rbx
  __int64 v11; // r8
  HLOCAL *v12; // r14
  PVOID *v13; // rcx
  __int64 result; // rax
  int v15; // eax
  __int64 i; // rbx
  int SaslProfiles; // ebx
  __int64 v18; // rdi
  unsigned int k; // ebx
  int v20; // eax
  __int64 j; // rbx
  __int64 v22; // rbx
  __int64 v23; // rsi
  __int64 v24; // rbx

  v2 = *a1;
  v3 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                 * (unsigned __int8)((SecPackageListLockCount - 1)
                                                                   & NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v3, 1u);
  v5 = (HLOCAL *)SecPackageControlList;
  v6 = 0;
  if ( SecPackageControlList != &SecPackageControlList )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
      {
        WPP_SF_S(v7[2], 11, v4, v5[13]);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5[3] == v2 )
        break;
      v5 = (HLOCAL *)*v5;
      v6 = 0;
      if ( v5 == &SecPackageControlList )
        goto LABEL_6;
    }
    v6 = v5;
  }
LABEL_6:
  if ( v6 )
  {
    RtlReleaseResource(v3);
    goto LABEL_16;
  }
  if ( SecPackageLsaLoaded && SecPackageSspiLoaded )
  {
    RtlReleaseResource(v3);
    return 2148074241LL;
  }
  RtlReleaseResource(v3);
  v15 = SecPackageListLockCount;
  for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
    v15 = SecPackageListLockCount;
  }
  if ( SecPackageLoadInProgress )
  {
    v24 = 0;
    if ( v15 )
    {
      do
      {
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v24]);
        v24 = (unsigned int)(v24 + 1);
      }
      while ( (unsigned int)v24 < SecPackageListLockCount );
    }
    return (unsigned int)-2146893055;
  }
  SecPackageLoadInProgress = 1;
  if ( SecPackageLsaLoaded || (SaslProfiles = SecpLoadLsaPackages(), SaslProfiles >= 0) )
  {
    if ( SecPackageSspiLoaded || (SaslProfiles = SecpLoadSspiPackages(), SaslProfiles >= 0) )
      SaslProfiles = SecpLoadSaslProfiles();
  }
  v18 = 0;
  for ( SecPackageLoadInProgress = 0; (unsigned int)v18 < SecPackageListLockCount; v18 = (unsigned int)(v18 + 1) )
    RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v18]);
  if ( SaslProfiles < 0 )
    return (unsigned int)-2146893055;
  v10 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                  * ((unsigned int)(SecPackageListLockCount - 1)
                                                   & (unsigned __int64)NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v10, 1u);
  v12 = (HLOCAL *)SecPackageControlList;
  v6 = 0;
  if ( SecPackageControlList != &SecPackageControlList )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        WPP_SF_S(v13[2], 11, v11, v12[13]);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12[3] == v2 )
        break;
      v12 = (HLOCAL *)*v12;
      v6 = 0;
      if ( v12 == &SecPackageControlList )
        goto LABEL_15;
    }
    v6 = v12;
  }
LABEL_15:
  RtlReleaseResource(v10);
  if ( !v6 )
    return (unsigned int)-2146893055;
LABEL_16:
  if ( (*((_BYTE *)v6 + 36) & 4) != 0 )
  {
    v20 = SecPackageListLockCount;
    for ( j = 0; (unsigned int)j < SecPackageListLockCount; j = (unsigned int)(j + 1) )
    {
      RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * j], 1u);
      v20 = SecPackageListLockCount;
    }
    if ( (*((_BYTE *)v6 + 36) & 4) == 0 )
    {
      v22 = 0;
      if ( v20 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v22]);
          v22 = (unsigned int)(v22 + 1);
        }
        while ( (unsigned int)v22 < SecPackageListLockCount );
      }
      goto LABEL_17;
    }
    v23 = 0;
    for ( k = SecpSnapPackage((struct _DLL_SECURITY_PACKAGE *)v6, v8, v9);
          (unsigned int)v23 < SecPackageListLockCount;
          v23 = (unsigned int)(v23 + 1) )
    {
      RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v23]);
    }
    if ( !k )
      goto LABEL_17;
    if ( k != -2146893056 )
      return (unsigned int)-2146893055;
    return k;
  }
LABEL_17:
  result = (__int64)v6[23];
  if ( result )
    return (*(__int64 (__fastcall **)(void *))(result + 72))(a1[1]);
  return result;
}

```

## disassembly

```asm
0x1800061a0  push    rbx
0x1800061a2  push    rbp
0x1800061a3  push    rsi
0x1800061a4  push    rdi
0x1800061a5  push    r12
0x1800061a7  push    r13
0x1800061a9  push    r14
0x1800061ab  push    r15
0x1800061ad  sub     rsp, 28h
0x1800061b1  mov     rax, gs:30h
0x1800061ba  lea     r14, SecPackageListLock
0x1800061c1  mov     edx, cs:SecPackageListLockCount
0x1800061c7  mov     r15, rcx
0x1800061ca  mov     rsi, [rcx]
0x1800061cd  dec     edx
0x1800061cf  movzx   r8d, byte ptr [rax+1747h]
0x1800061d7  and     r8, rdx
0x1800061da  mov     dl, 1; Wait
0x1800061dc  lea     rbp, [r8+r8*2]
0x1800061e0  shl     rbp, 5
0x1800061e4  add     rbp, r14
0x1800061e7  mov     rcx, rbp; Resource
0x1800061ea  call    cs:__imp_RtlAcquireResourceShared
0x1800061f0  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x1800061f7  lea     r13, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x1800061fe  xor     edi, edi
0x180006200  lea     r12, WPP_GLOBAL_Control
0x180006207  cmp     rbx, r13
0x18000620a  jz      short loc_18000622C
0x18000620c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006213  cmp     rcx, r12
0x180006216  jnz     short loc_180006243
0x180006218  cmp     [rbx+18h], rsi
0x18000621c  jz      loc_18000631E
0x180006222  mov     rbx, [rbx]
0x180006225  xor     edi, edi
0x180006227  cmp     rbx, r13
0x18000622a  jnz     short loc_180006213
0x18000622c  test    rdi, rdi
0x18000622f  jz      loc_180006326
0x180006235  mov     rcx, rbp; Resource
0x180006238  call    cs:__imp_RtlReleaseResource
0x18000623e  jmp     loc_1800062E6
0x180006243  test    byte ptr [rcx+1Ch], 4
0x180006247  jz      short loc_180006218
0x180006249  mov     r9, [rbx+68h]
0x18000624d  mov     edx, 0Bh
0x180006252  mov     rcx, [rcx+10h]
0x180006256  call    WPP_SF_S
0x18000625b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006262  jmp     short loc_180006218
0x180006264  mov     rax, gs:30h
0x18000626d  mov     ecx, cs:SecPackageListLockCount
0x180006273  dec     ecx
0x180006275  movzx   edx, byte ptr [rax+1747h]
0x18000627c  and     rdx, rcx
0x18000627f  lea     rbx, [rdx+rdx*2]
0x180006283  mov     dl, 1; Wait
0x180006285  shl     rbx, 5
0x180006289  add     rbx, r14
0x18000628c  mov     rcx, rbx; Resource
0x18000628f  call    cs:__imp_RtlAcquireResourceShared
0x180006295  mov     r14, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000629c  xor     edi, edi
0x18000629e  cmp     r14, r13
0x1800062a1  jz      short loc_1800062CD
0x1800062a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062aa  nop     word ptr [rax+rax+00h]
0x1800062b0  cmp     rcx, r12
0x1800062b3  jnz     loc_180006403
0x1800062b9  cmp     [r14+18h], rsi
0x1800062bd  jz      loc_1800064A7
0x1800062c3  mov     r14, [r14]
0x1800062c6  xor     edi, edi
0x1800062c8  cmp     r14, r13
0x1800062cb  jnz     short loc_1800062B0
0x1800062cd  mov     rcx, rbx; Resource
0x1800062d0  call    cs:__imp_RtlReleaseResource
0x1800062d6  test    rdi, rdi
0x1800062d9  jz      loc_180006397
0x1800062df  lea     r14, SecPackageListLock
0x1800062e6  test    byte ptr [rdi+24h], 4
0x1800062ea  jnz     loc_1800063A3
0x1800062f0  mov     rax, [rdi+0B8h]
0x1800062f7  test    rax, rax
0x1800062fa  jz      loc_18000653D
0x180006300  mov     rcx, [r15+8]
0x180006304  mov     rax, [rax+48h]
0x180006308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630d  add     rsp, 28h
0x180006311  pop     r15
0x180006313  pop     r14
0x180006315  pop     r13
0x180006317  pop     r12
0x180006319  pop     rdi
0x18000631a  pop     rsi
0x18000631b  pop     rbp
0x18000631c  pop     rbx
0x18000631d  retn
0x18000631e  mov     rdi, rbx
0x180006321  jmp     loc_18000622C
0x180006326  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x18000632d  jnz     loc_180006485
0x180006333  mov     rcx, rbp; Resource
0x180006336  call    cs:__imp_RtlReleaseResource
0x18000633c  mov     eax, cs:SecPackageListLockCount
0x180006342  xor     ebx, ebx
0x180006344  test    eax, eax
0x180006346  jnz     loc_180006460
0x18000634c  cmp     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x180006353  jnz     loc_1800064AF
0x180006359  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x180006360  mov     cs:?SecPackageLoadInProgress@@3HA, 1; int SecPackageLoadInProgress
0x18000636a  jnz     short loc_1800063E3
0x18000636c  call    ?SecpLoadLsaPackages@@YAJXZ; SecpLoadLsaPackages(void)
0x180006371  mov     ebx, eax
0x180006373  test    eax, eax
0x180006375  jns     short loc_1800063E3
0x180006377  xor     edi, edi
0x180006379  mov     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x180006383  cmp     cs:SecPackageListLockCount, edi
0x180006389  ja      loc_1800064D9
0x18000638f  test    ebx, ebx
0x180006391  jns     loc_180006264
0x180006397  mov     ebx, 80090301h
0x18000639c  mov     eax, ebx
0x18000639e  jmp     loc_18000630D
0x1800063a3  mov     eax, cs:SecPackageListLockCount
0x1800063a9  xor     ebx, ebx
0x1800063ab  test    eax, eax
0x1800063ad  jnz     loc_1800064F9
0x1800063b3  test    byte ptr [rdi+24h], 4
0x1800063b7  jnz     short loc_18000642B
0x1800063b9  xor     ebx, ebx
0x1800063bb  test    eax, eax
0x1800063bd  jz      loc_1800062F0
0x1800063c3  lea     rcx, [rbx+rbx*2]
0x1800063c7  shl     rcx, 5
0x1800063cb  add     rcx, r14; Resource
0x1800063ce  call    cs:__imp_RtlReleaseResource
0x1800063d4  inc     ebx
0x1800063d6  cmp     ebx, cs:SecPackageListLockCount
0x1800063dc  jb      short loc_1800063C3
0x1800063de  jmp     loc_1800062F0
0x1800063e3  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x1800063ea  jnz     short loc_1800063F7
0x1800063ec  call    ?SecpLoadSspiPackages@@YAJXZ; SecpLoadSspiPackages(void)
0x1800063f1  mov     ebx, eax
0x1800063f3  test    eax, eax
0x1800063f5  js      short loc_180006377
0x1800063f7  call    ?SecpLoadSaslProfiles@@YAJXZ; SecpLoadSaslProfiles(void)
0x1800063fc  mov     ebx, eax
0x1800063fe  jmp     loc_180006377
0x180006403  test    byte ptr [rcx+1Ch], 4
0x180006407  jz      loc_1800062B9
0x18000640d  mov     r9, [r14+68h]
0x180006411  mov     edx, 0Bh
0x180006416  mov     rcx, [rcx+10h]
0x18000641a  call    WPP_SF_S
0x18000641f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006426  jmp     loc_1800062B9
0x18000642b  mov     rcx, rdi; struct _DLL_SECURITY_PACKAGE *
0x18000642e  call    ?SecpSnapPackage@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpSnapPackage(_DLL_SECURITY_PACKAGE *)
0x180006433  xor     esi, esi
0x180006435  mov     ebx, eax
0x180006437  cmp     cs:SecPackageListLockCount, esi
0x18000643d  ja      loc_18000651D
0x180006443  test    ebx, ebx
0x180006445  jz      loc_1800062F0
0x18000644b  cmp     ebx, 80090300h
0x180006451  mov     eax, 80090301h
0x180006456  cmovnz  ebx, eax
0x180006459  jmp     loc_18000639C
0x180006460  lea     rcx, [rbx+rbx*2]
0x180006464  mov     dl, 1; Wait
0x180006466  shl     rcx, 5
0x18000646a  add     rcx, r14; Resource
0x18000646d  call    cs:__imp_RtlAcquireResourceExclusive
0x180006473  mov     eax, cs:SecPackageListLockCount
0x180006479  inc     ebx
0x18000647b  cmp     ebx, eax
0x18000647d  jnb     loc_18000634C
0x180006483  jmp     short loc_180006460
0x180006485  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x18000648c  jz      loc_180006333
0x180006492  mov     rcx, rbp; Resource
0x180006495  call    cs:__imp_RtlReleaseResource
0x18000649b  mov     ebx, 80090301h
0x1800064a0  mov     eax, ebx
0x1800064a2  jmp     loc_18000630D
0x1800064a7  mov     rdi, r14
0x1800064aa  jmp     loc_1800062CD
0x1800064af  xor     ebx, ebx
0x1800064b1  test    eax, eax
0x1800064b3  jz      loc_180006397
0x1800064b9  lea     rcx, [rbx+rbx*2]
0x1800064bd  shl     rcx, 5
0x1800064c1  add     rcx, r14; Resource
0x1800064c4  call    cs:__imp_RtlReleaseResource
0x1800064ca  inc     ebx
0x1800064cc  cmp     ebx, cs:SecPackageListLockCount
0x1800064d2  jb      short loc_1800064B9
0x1800064d4  jmp     loc_180006397
0x1800064d9  lea     rcx, [rdi+rdi*2]
0x1800064dd  shl     rcx, 5
0x1800064e1  add     rcx, r14; Resource
0x1800064e4  call    cs:__imp_RtlReleaseResource
0x1800064ea  inc     edi
0x1800064ec  cmp     edi, cs:SecPackageListLockCount
0x1800064f2  jb      short loc_1800064D9
0x1800064f4  jmp     loc_18000638F
0x1800064f9  lea     rcx, [rbx+rbx*2]
0x1800064fd  mov     dl, 1; Wait
0x1800064ff  shl     rcx, 5
0x180006503  add     rcx, r14; Resource
0x180006506  call    cs:__imp_RtlAcquireResourceExclusive
0x18000650c  mov     eax, cs:SecPackageListLockCount
0x180006512  inc     ebx
0x180006514  cmp     ebx, eax
0x180006516  jb      short loc_1800064F9
0x180006518  jmp     loc_1800063B3
0x18000651d  lea     rcx, [rsi+rsi*2]
0x180006521  shl     rcx, 5
0x180006525  add     rcx, r14; Resource
0x180006528  call    cs:__imp_RtlReleaseResource
0x18000652e  inc     esi
0x180006530  cmp     esi, cs:SecPackageListLockCount
0x180006536  jb      short loc_18000651D
0x180006538  jmp     loc_180006443
0x18000653d  jmp     loc_18000630D
```
