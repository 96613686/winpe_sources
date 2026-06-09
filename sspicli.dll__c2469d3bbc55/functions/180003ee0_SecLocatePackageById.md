# SecLocatePackageById

- ea: `0x180003ee0`
- end: `0x18000427e`
- name: `SecLocatePackageById`
- size: `926`
- prototype: ``
- caller_count: `21`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002130`
- `0x180003670`
- `0x180004290`
- `0x180009360`
- `0x18000c570`
- `0x1800104e0`
- `0x180012570`
- `0x1800135e0`
- `0x180013bf0`
- `0x1800145d0`
- `0x180014d00`
- `0x180017760`
- `0x180018430`
- `0x1800197b0`
- `0x18001a8e0`
- `0x18001b700`
- `0x18001c010`
- `0x18001c130`
- `0x18001c5f0`
- `0x18001c7b0`
- `0x18001c830`

## callees

- `0x180003ee0`
- `0x1800069d8`
- `0x180006eac`
- `0x1800070d0`
- `0x180008fc4`
- `0x18001d478`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000419d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004234`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000419d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004234`
- `ntdll!RtlReleaseResource` at `0x180003f7a`
- `ntdll!RtlReleaseResource` at `0x180004010`
- `ntdll!RtlReleaseResource` at `0x18000405e`
- `ntdll!RtlReleaseResource` at `0x1800040fc`
- `ntdll!RtlReleaseResource` at `0x1800041c5`
- `ntdll!RtlReleaseResource` at `0x1800041f2`
- `ntdll!RtlReleaseResource` at `0x180004212`
- `ntdll!RtlReleaseResource` at `0x180004256`
- `ntdll!RtlReleaseResource` at `0x180003f7a`
- `ntdll!RtlReleaseResource` at `0x180004010`
- `ntdll!RtlReleaseResource` at `0x18000405e`
- `ntdll!RtlReleaseResource` at `0x1800040fc`
- `ntdll!RtlReleaseResource` at `0x1800041c5`
- `ntdll!RtlReleaseResource` at `0x1800041f2`
- `ntdll!RtlReleaseResource` at `0x180004212`
- `ntdll!RtlReleaseResource` at `0x180004256`
- `ntdll!RtlAcquireResourceShared` at `0x180003f2c`
- `ntdll!RtlAcquireResourceShared` at `0x180003fd1`
- `ntdll!RtlAcquireResourceShared` at `0x180003f2c`
- `ntdll!RtlAcquireResourceShared` at `0x180003fd1`

## pseudocode

```c
__int64 __fastcall SecLocatePackageById(HLOCAL a1, HLOCAL **a2)
{
  struct _RTL_RESOURCE *v4; // rbp
  __int64 v5; // r8
  HLOCAL *v6; // rbx
  HLOCAL *v7; // rdi
  PVOID *v8; // rcx
  __int64 v9; // rdx
  int v10; // r8d
  struct _RTL_RESOURCE *v11; // rbx
  __int64 v12; // r8
  HLOCAL *v13; // r14
  PVOID *v14; // rcx
  int v16; // eax
  __int64 i; // rbx
  int SaslProfiles; // ebx
  __int64 v19; // rdi
  int v20; // eax
  __int64 j; // rbx
  __int64 v22; // rbx
  __int64 v23; // rsi
  unsigned int k; // ebx
  __int64 v25; // rbx

  v4 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                 * (unsigned __int8)((SecPackageListLockCount - 1)
                                                                   & NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v4, 1u);
  v6 = (HLOCAL *)SecPackageControlList;
  v7 = 0;
  if ( SecPackageControlList != &SecPackageControlList )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      {
        WPP_SF_S(v8[2], 11, v5, v6[13]);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6[3] == a1 )
        break;
      v6 = (HLOCAL *)*v6;
      v7 = 0;
      if ( v6 == &SecPackageControlList )
        goto LABEL_6;
    }
    v7 = v6;
  }
LABEL_6:
  if ( !v7 )
  {
    if ( SecPackageLsaLoaded && SecPackageSspiLoaded )
    {
      RtlReleaseResource(v4);
      return 2148074241LL;
    }
    RtlReleaseResource(v4);
    v16 = SecPackageListLockCount;
    for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
    {
      RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
      v16 = SecPackageListLockCount;
    }
    if ( SecPackageLoadInProgress )
    {
      v25 = 0;
      if ( v16 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v25]);
          v25 = (unsigned int)(v25 + 1);
        }
        while ( (unsigned int)v25 < SecPackageListLockCount );
      }
    }
    else
    {
      SecPackageLoadInProgress = 1;
      if ( SecPackageLsaLoaded || (SaslProfiles = SecpLoadLsaPackages(), SaslProfiles >= 0) )
      {
        if ( SecPackageSspiLoaded || (SaslProfiles = SecpLoadSspiPackages(), SaslProfiles >= 0) )
          SaslProfiles = SecpLoadSaslProfiles();
      }
      v19 = 0;
      for ( SecPackageLoadInProgress = 0; (unsigned int)v19 < SecPackageListLockCount; v19 = (unsigned int)(v19 + 1) )
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v19]);
      if ( SaslProfiles >= 0 )
      {
        v11 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                        * ((unsigned int)(SecPackageListLockCount - 1)
                                                         & (unsigned __int64)NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
        RtlAcquireResourceShared(v11, 1u);
        v13 = (HLOCAL *)SecPackageControlList;
        v7 = 0;
        if ( SecPackageControlList != &SecPackageControlList )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          while ( 1 )
          {
            if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
            {
              WPP_SF_S(v14[2], 11, v12, v13[13]);
              v14 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v13[3] == a1 )
              break;
            v13 = (HLOCAL *)*v13;
            v7 = 0;
            if ( v13 == &SecPackageControlList )
              goto LABEL_15;
          }
          v7 = v13;
        }
LABEL_15:
        RtlReleaseResource(v11);
        if ( v7 )
          goto LABEL_16;
      }
    }
    return 2148074241LL;
  }
  RtlReleaseResource(v4);
LABEL_16:
  if ( (*((_BYTE *)v7 + 36) & 4) == 0 )
  {
LABEL_17:
    *a2 = v7;
    return 0;
  }
  v20 = SecPackageListLockCount;
  for ( j = 0; (unsigned int)j < SecPackageListLockCount; j = (unsigned int)(j + 1) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * j], 1u);
    v20 = SecPackageListLockCount;
  }
  if ( (*((_BYTE *)v7 + 36) & 4) == 0 )
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
  for ( k = SecpSnapPackage((struct _DLL_SECURITY_PACKAGE *)v7, v9, v10);
        (unsigned int)v23 < SecPackageListLockCount;
        v23 = (unsigned int)(v23 + 1) )
  {
    RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v23]);
  }
  if ( k )
  {
    if ( k != -2146893056 )
      return (unsigned int)-2146893055;
  }
  else
  {
    *a2 = v7;
  }
  return k;
}

```

## disassembly

```asm
0x180003ee0  push    rbx
0x180003ee2  push    rbp
0x180003ee3  push    rsi
0x180003ee4  push    rdi
0x180003ee5  push    r12
0x180003ee7  push    r13
0x180003ee9  push    r14
0x180003eeb  push    r15
0x180003eed  sub     rsp, 28h
0x180003ef1  mov     rax, gs:30h
0x180003efa  lea     r14, SecPackageListLock
0x180003f01  mov     r8d, cs:SecPackageListLockCount
0x180003f08  mov     r15, rdx
0x180003f0b  dec     r8d
0x180003f0e  mov     rsi, rcx
0x180003f11  mov     dl, 1; Wait
0x180003f13  movzx   r9d, byte ptr [rax+1747h]
0x180003f1b  and     r9, r8
0x180003f1e  lea     rbp, [r9+r9*2]
0x180003f22  shl     rbp, 5
0x180003f26  add     rbp, r14
0x180003f29  mov     rcx, rbp; Resource
0x180003f2c  call    cs:__imp_RtlAcquireResourceShared
0x180003f32  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180003f39  lea     r13, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180003f40  xor     edi, edi
0x180003f42  lea     r12, WPP_GLOBAL_Control
0x180003f49  cmp     rbx, r13
0x180003f4c  jz      short loc_180003F6E
0x180003f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f55  cmp     rcx, r12
0x180003f58  jnz     short loc_180003F85
0x180003f5a  cmp     [rbx+18h], rsi
0x180003f5e  jz      loc_180004046
0x180003f64  mov     rbx, [rbx]
0x180003f67  xor     edi, edi
0x180003f69  cmp     rbx, r13
0x180003f6c  jnz     short loc_180003F55
0x180003f6e  test    rdi, rdi
0x180003f71  jz      loc_18000404E
0x180003f77  mov     rcx, rbp; Resource
0x180003f7a  call    cs:__imp_RtlReleaseResource
0x180003f80  jmp     loc_180004026
0x180003f85  test    byte ptr [rcx+1Ch], 4
0x180003f89  jz      short loc_180003F5A
0x180003f8b  mov     r9, [rbx+68h]
0x180003f8f  mov     edx, 0Bh
0x180003f94  mov     rcx, [rcx+10h]
0x180003f98  call    WPP_SF_S
0x180003f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fa4  jmp     short loc_180003F5A
0x180003fa6  mov     rax, gs:30h
0x180003faf  mov     ecx, cs:SecPackageListLockCount
0x180003fb5  dec     ecx
0x180003fb7  movzx   edx, byte ptr [rax+1747h]
0x180003fbe  and     rdx, rcx
0x180003fc1  lea     rbx, [rdx+rdx*2]
0x180003fc5  mov     dl, 1; Wait
0x180003fc7  shl     rbx, 5
0x180003fcb  add     rbx, r14
0x180003fce  mov     rcx, rbx; Resource
0x180003fd1  call    cs:__imp_RtlAcquireResourceShared
0x180003fd7  mov     r14, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180003fde  xor     edi, edi
0x180003fe0  cmp     r14, r13
0x180003fe3  jz      short loc_18000400D
0x180003fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fec  nop     dword ptr [rax+00h]
0x180003ff0  cmp     rcx, r12
0x180003ff3  jnz     loc_180004111
0x180003ff9  cmp     [r14+18h], rsi
0x180003ffd  jz      loc_1800041D5
0x180004003  mov     r14, [r14]
0x180004006  xor     edi, edi
0x180004008  cmp     r14, r13
0x18000400b  jnz     short loc_180003FF0
0x18000400d  mov     rcx, rbx; Resource
0x180004010  call    cs:__imp_RtlReleaseResource
0x180004016  test    rdi, rdi
0x180004019  jz      loc_1800040C7
0x18000401f  lea     r14, SecPackageListLock
0x180004026  test    byte ptr [rdi+24h], 4
0x18000402a  jnz     loc_1800040D1
0x180004030  mov     [r15], rdi
0x180004033  xor     eax, eax
0x180004035  add     rsp, 28h
0x180004039  pop     r15
0x18000403b  pop     r14
0x18000403d  pop     r13
0x18000403f  pop     r12
0x180004041  pop     rdi
0x180004042  pop     rsi
0x180004043  pop     rbp
0x180004044  pop     rbx
0x180004045  retn
0x180004046  mov     rdi, rbx
0x180004049  jmp     loc_180003F6E
0x18000404e  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x180004055  jnz     loc_1800041B5
0x18000405b  mov     rcx, rbp; Resource
0x18000405e  call    cs:__imp_RtlReleaseResource
0x180004064  mov     eax, cs:SecPackageListLockCount
0x18000406a  xor     ebx, ebx
0x18000406c  test    eax, eax
0x18000406e  jnz     loc_180004190
0x180004074  cmp     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x18000407b  jnz     loc_1800041DD
0x180004081  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x180004088  mov     cs:?SecPackageLoadInProgress@@3HA, 1; int SecPackageLoadInProgress
0x180004092  jnz     loc_180004139
0x180004098  call    ?SecpLoadLsaPackages@@YAJXZ; SecpLoadLsaPackages(void)
0x18000409d  mov     ebx, eax
0x18000409f  test    eax, eax
0x1800040a1  jns     loc_180004139
0x1800040a7  xor     edi, edi
0x1800040a9  mov     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x1800040b3  cmp     cs:SecPackageListLockCount, edi
0x1800040b9  ja      loc_180004207
0x1800040bf  test    ebx, ebx
0x1800040c1  jns     loc_180003FA6
0x1800040c7  mov     eax, 80090301h
0x1800040cc  jmp     loc_180004035
0x1800040d1  mov     eax, cs:SecPackageListLockCount
0x1800040d7  xor     ebx, ebx
0x1800040d9  test    eax, eax
0x1800040db  jnz     loc_180004227
0x1800040e1  test    byte ptr [rdi+24h], 4
0x1800040e5  jnz     short loc_18000415D
0x1800040e7  xor     ebx, ebx
0x1800040e9  test    eax, eax
0x1800040eb  jz      loc_180004030
0x1800040f1  lea     rcx, [rbx+rbx*2]
0x1800040f5  shl     rcx, 5
0x1800040f9  add     rcx, r14; Resource
0x1800040fc  call    cs:__imp_RtlReleaseResource
0x180004102  inc     ebx
0x180004104  cmp     ebx, cs:SecPackageListLockCount
0x18000410a  jb      short loc_1800040F1
0x18000410c  jmp     loc_180004030
0x180004111  test    byte ptr [rcx+1Ch], 4
0x180004115  jz      loc_180003FF9
0x18000411b  mov     r9, [r14+68h]
0x18000411f  mov     edx, 0Bh
0x180004124  mov     rcx, [rcx+10h]
0x180004128  call    WPP_SF_S
0x18000412d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004134  jmp     loc_180003FF9
0x180004139  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x180004140  jnz     short loc_180004151
0x180004142  call    ?SecpLoadSspiPackages@@YAJXZ; SecpLoadSspiPackages(void)
0x180004147  mov     ebx, eax
0x180004149  test    eax, eax
0x18000414b  js      loc_1800040A7
0x180004151  call    ?SecpLoadSaslProfiles@@YAJXZ; SecpLoadSaslProfiles(void)
0x180004156  mov     ebx, eax
0x180004158  jmp     loc_1800040A7
0x18000415d  mov     rcx, rdi; struct _DLL_SECURITY_PACKAGE *
0x180004160  call    ?SecpSnapPackage@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpSnapPackage(_DLL_SECURITY_PACKAGE *)
0x180004165  xor     esi, esi
0x180004167  mov     ebx, eax
0x180004169  cmp     cs:SecPackageListLockCount, esi
0x18000416f  ja      loc_18000424B
0x180004175  test    ebx, ebx
0x180004177  jnz     loc_18000426B
0x18000417d  mov     [r15], rdi
0x180004180  mov     eax, ebx
0x180004182  jmp     loc_180004035
0x180004190  lea     rcx, [rbx+rbx*2]
0x180004194  mov     dl, 1; Wait
0x180004196  shl     rcx, 5
0x18000419a  add     rcx, r14; Resource
0x18000419d  call    cs:__imp_RtlAcquireResourceExclusive
0x1800041a3  mov     eax, cs:SecPackageListLockCount
0x1800041a9  inc     ebx
0x1800041ab  cmp     ebx, eax
0x1800041ad  jnb     loc_180004074
0x1800041b3  jmp     short loc_180004190
0x1800041b5  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x1800041bc  jz      loc_18000405B
0x1800041c2  mov     rcx, rbp; Resource
0x1800041c5  call    cs:__imp_RtlReleaseResource
0x1800041cb  mov     eax, 80090301h
0x1800041d0  jmp     loc_180004035
0x1800041d5  mov     rdi, r14
0x1800041d8  jmp     loc_18000400D
0x1800041dd  xor     ebx, ebx
0x1800041df  test    eax, eax
0x1800041e1  jz      loc_1800040C7
0x1800041e7  lea     rcx, [rbx+rbx*2]
0x1800041eb  shl     rcx, 5
0x1800041ef  add     rcx, r14; Resource
0x1800041f2  call    cs:__imp_RtlReleaseResource
0x1800041f8  inc     ebx
0x1800041fa  cmp     ebx, cs:SecPackageListLockCount
0x180004200  jb      short loc_1800041E7
0x180004202  jmp     loc_1800040C7
0x180004207  lea     rcx, [rdi+rdi*2]
0x18000420b  shl     rcx, 5
0x18000420f  add     rcx, r14; Resource
0x180004212  call    cs:__imp_RtlReleaseResource
0x180004218  inc     edi
0x18000421a  cmp     edi, cs:SecPackageListLockCount
0x180004220  jb      short loc_180004207
0x180004222  jmp     loc_1800040BF
0x180004227  lea     rcx, [rbx+rbx*2]
0x18000422b  mov     dl, 1; Wait
0x18000422d  shl     rcx, 5
0x180004231  add     rcx, r14; Resource
0x180004234  call    cs:__imp_RtlAcquireResourceExclusive
0x18000423a  mov     eax, cs:SecPackageListLockCount
0x180004240  inc     ebx
0x180004242  cmp     ebx, eax
0x180004244  jb      short loc_180004227
0x180004246  jmp     loc_1800040E1
0x18000424b  lea     rcx, [rsi+rsi*2]
0x18000424f  shl     rcx, 5
0x180004253  add     rcx, r14; Resource
0x180004256  call    cs:__imp_RtlReleaseResource
0x18000425c  inc     esi
0x18000425e  cmp     esi, cs:SecPackageListLockCount
0x180004264  jb      short loc_18000424B
0x180004266  jmp     loc_180004175
0x18000426b  cmp     ebx, 80090300h
0x180004271  mov     eax, 80090301h
0x180004276  cmovnz  ebx, eax
0x180004279  jmp     loc_180004180
```
