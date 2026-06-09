# SecpLocatePackageEx(int,ulong,_UNICODE_STRING *,unsigned __int64,_DLL_SECURITY_PACKAGE * *)

- ea: `0x180007200`
- end: `0x180007516`
- name: `?SecpLocatePackageEx@@YAJHKPEAU_UNICODE_STRING@@_KPEAPEAU_DLL_SECURITY_PACKAGE@@@Z`
- size: `790`
- prototype: `__int64 __fastcall(int, unsigned int, struct _UNICODE_STRING *, unsigned __int64, struct _DLL_SECURITY_PACKAGE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007b58`

## callees

- `0x1800069d8`
- `0x180006eac`
- `0x1800070d0`
- `0x180007200`
- `0x180007520`
- `0x18001d478`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000745d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000745d`
- `ntdll!RtlReleaseResource` at `0x1800072be`
- `ntdll!RtlReleaseResource` at `0x18000738c`
- `ntdll!RtlReleaseResource` at `0x1800073db`
- `ntdll!RtlReleaseResource` at `0x180007485`
- `ntdll!RtlReleaseResource` at `0x1800074e1`
- `ntdll!RtlReleaseResource` at `0x180007501`
- `ntdll!RtlReleaseResource` at `0x1800072be`
- `ntdll!RtlReleaseResource` at `0x18000738c`
- `ntdll!RtlReleaseResource` at `0x1800073db`
- `ntdll!RtlReleaseResource` at `0x180007485`
- `ntdll!RtlReleaseResource` at `0x1800074e1`
- `ntdll!RtlReleaseResource` at `0x180007501`
- `ntdll!RtlEqualUnicodeString` at `0x180007412`
- `ntdll!RtlEqualUnicodeString` at `0x180007412`
- `ntdll!RtlAcquireResourceShared` at `0x180007251`
- `ntdll!RtlAcquireResourceShared` at `0x1800073bf`
- `ntdll!RtlAcquireResourceShared` at `0x180007251`
- `ntdll!RtlAcquireResourceShared` at `0x1800073bf`

## pseudocode

```c
__int64 __fastcall SecpLocatePackageEx(
        int a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        unsigned __int64 a4,
        struct _DLL_SECURITY_PACKAGE **a5)
{
  struct _RTL_RESOURCE *v9; // r15
  __int64 v10; // r8
  HLOCAL *v11; // rbx
  struct _DLL_SECURITY_PACKAGE *v12; // rsi
  int v13; // eax
  __int64 i; // rbx
  int SaslProfiles; // ebx
  __int64 v16; // rsi
  __int64 result; // rax
  struct _RTL_RESOURCE *v18; // rbx
  __int64 v19; // rbx

  v9 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                 * (unsigned __int8)((SecPackageListLockCount - 1)
                                                                   & NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v9, 1u);
  v11 = (HLOCAL *)SecPackageControlList;
  v12 = 0;
  if ( SecPackageControlList == &SecPackageControlList )
    goto LABEL_20;
  while ( 1 )
  {
    v12 = (struct _DLL_SECURITY_PACKAGE *)v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v10, v11[13]);
    if ( a3 )
      break;
    if ( v11[3] == (HLOCAL)a4 && (a2 == 8 || (a2 & (_DWORD)v11[2]) == a2) )
      goto LABEL_18;
LABEL_5:
    v11 = (HLOCAL *)*v11;
    if ( v11 == &SecPackageControlList )
      goto LABEL_6;
  }
  if ( !RtlEqualUnicodeString((PCUNICODE_STRING)v11 + 6, a3, 1u) || a2 != 8 && (a2 & (_DWORD)v11[2]) != a2 )
    goto LABEL_5;
LABEL_18:
  if ( v11 && ((_DWORD)v11[10] & 0x200000) != 0 && a1 && SecGlobalExtenderPackage )
    v12 = SecGlobalExtenderPackage;
LABEL_20:
  if ( v12 )
  {
    RtlReleaseResource(v9);
    goto LABEL_23;
  }
LABEL_6:
  if ( !SecPackageLsaLoaded || !SecPackageSspiLoaded )
  {
    RtlReleaseResource(v9);
    v13 = SecPackageListLockCount;
    for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
    {
      RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
      v13 = SecPackageListLockCount;
    }
    if ( SecPackageLoadInProgress )
    {
      v19 = 0;
      if ( v13 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v19]);
          v19 = (unsigned int)(v19 + 1);
        }
        while ( (unsigned int)v19 < SecPackageListLockCount );
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
      v16 = 0;
      for ( SecPackageLoadInProgress = 0; (unsigned int)v16 < SecPackageListLockCount; v16 = (unsigned int)(v16 + 1) )
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v16]);
      if ( SaslProfiles >= 0 )
      {
        v18 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                        * ((unsigned int)(SecPackageListLockCount - 1)
                                                         & (unsigned __int64)NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
        RtlAcquireResourceShared(v18, 1u);
        v12 = SecpScanPackageListEx(a1, a2, a3, a4);
        RtlReleaseResource(v18);
        if ( v12 )
        {
LABEL_23:
          result = 0;
          *a5 = v12;
          return result;
        }
      }
    }
    return 2148074245LL;
  }
  RtlReleaseResource(v9);
  return 2148074245LL;
}

```

## disassembly

```asm
0x180007200  push    rbx
0x180007202  push    rbp
0x180007203  push    rsi
0x180007204  push    rdi
0x180007205  push    r12
0x180007207  push    r13
0x180007209  push    r14
0x18000720b  push    r15
0x18000720d  sub     rsp, 28h
0x180007211  mov     rax, gs:30h
0x18000721a  mov     r12d, ecx
0x18000721d  mov     r10d, cs:SecPackageListLockCount
0x180007224  lea     rcx, SecPackageListLock
0x18000722b  dec     r10d
0x18000722e  mov     edi, edx
0x180007230  mov     dl, 1; Wait
0x180007232  mov     r14, r9
0x180007235  movzx   r11d, byte ptr [rax+1747h]
0x18000723d  mov     rbp, r8
0x180007240  and     r11, r10
0x180007243  lea     r15, [r11+r11*2]
0x180007247  shl     r15, 5
0x18000724b  add     r15, rcx
0x18000724e  mov     rcx, r15; Resource
0x180007251  call    cs:__imp_RtlAcquireResourceShared
0x180007257  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000725e  lea     r13, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180007265  xor     esi, esi
0x180007267  cmp     rbx, r13
0x18000726a  jz      loc_180007380
0x180007270  lea     rax, WPP_GLOBAL_Control
0x180007277  nop     word ptr [rax+rax+00000000h]
0x180007280  mov     rsi, rbx
0x180007283  mov     rcx, cs:WPP_GLOBAL_Control
0x18000728a  cmp     rcx, rax
0x18000728d  jnz     loc_180007334
0x180007293  test    rbp, rbp
0x180007296  jnz     loc_180007408
0x18000729c  cmp     [rbx+18h], r14
0x1800072a0  jz      loc_18000735C
0x1800072a6  mov     rbx, [rbx]
0x1800072a9  cmp     rbx, r13
0x1800072ac  jnz     short loc_180007280
0x1800072ae  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x1800072b5  jnz     loc_180007475
0x1800072bb  mov     rcx, r15; Resource
0x1800072be  call    cs:__imp_RtlReleaseResource
0x1800072c4  mov     eax, cs:SecPackageListLockCount
0x1800072ca  lea     r15, SecPackageListLock
0x1800072d1  xor     ebx, ebx
0x1800072d3  test    eax, eax
0x1800072d5  jnz     loc_180007450
0x1800072db  cmp     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x1800072e2  jnz     loc_1800074CC
0x1800072e8  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x1800072ef  mov     cs:?SecPackageLoadInProgress@@3HA, 1; int SecPackageLoadInProgress
0x1800072f9  jnz     loc_180007428
0x1800072ff  call    ?SecpLoadLsaPackages@@YAJXZ; SecpLoadLsaPackages(void)
0x180007304  mov     ebx, eax
0x180007306  test    eax, eax
0x180007308  jns     loc_180007428
0x18000730e  xor     esi, esi
0x180007310  mov     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x18000731a  cmp     cs:SecPackageListLockCount, esi
0x180007320  ja      loc_1800074F6
0x180007326  test    ebx, ebx
0x180007328  jns     short loc_180007394
0x18000732a  mov     eax, 80090305h
0x18000732f  jmp     loc_1800073F7
0x180007334  test    byte ptr [rcx+1Ch], 4
0x180007338  jz      loc_180007293
0x18000733e  mov     r9, [rbx+68h]
0x180007342  mov     edx, 0Bh
0x180007347  mov     rcx, [rcx+10h]
0x18000734b  call    WPP_SF_S
0x180007350  lea     rax, WPP_GLOBAL_Control
0x180007357  jmp     loc_180007293
0x18000735c  cmp     edi, 8
0x18000735f  jz      short loc_18000736E
0x180007361  mov     eax, [rbx+10h]
0x180007364  and     eax, edi
0x180007366  cmp     eax, edi
0x180007368  jnz     loc_18000741C
0x18000736e  test    rbx, rbx
0x180007371  jz      short loc_180007380
0x180007373  test    dword ptr [rbx+50h], 200000h
0x18000737a  jnz     loc_1800074B0
0x180007380  test    rsi, rsi
0x180007383  jz      loc_1800072AE
0x180007389  mov     rcx, r15; Resource
0x18000738c  call    cs:__imp_RtlReleaseResource
0x180007392  jmp     short loc_1800073EA
0x180007394  mov     rax, gs:30h
0x18000739d  mov     ecx, cs:SecPackageListLockCount
0x1800073a3  dec     ecx
0x1800073a5  movzx   edx, byte ptr [rax+1747h]
0x1800073ac  and     rdx, rcx
0x1800073af  lea     rbx, [rdx+rdx*2]
0x1800073b3  mov     dl, 1; Wait
0x1800073b5  shl     rbx, 5
0x1800073b9  add     rbx, r15
0x1800073bc  mov     rcx, rbx; Resource
0x1800073bf  call    cs:__imp_RtlAcquireResourceShared
0x1800073c5  mov     r9, r14; unsigned __int64
0x1800073c8  mov     r8, rbp; struct _UNICODE_STRING *
0x1800073cb  mov     edx, edi; unsigned int
0x1800073cd  mov     ecx, r12d; int
0x1800073d0  call    ?SecpScanPackageListEx@@YAPEAU_DLL_SECURITY_PACKAGE@@HKPEAU_UNICODE_STRING@@_K@Z; SecpScanPackageListEx(int,ulong,_UNICODE_STRING *,unsigned __int64)
0x1800073d5  mov     rcx, rbx; Resource
0x1800073d8  mov     rsi, rax
0x1800073db  call    cs:__imp_RtlReleaseResource
0x1800073e1  test    rsi, rsi
0x1800073e4  jz      loc_18000732A
0x1800073ea  mov     rcx, [rsp+68h+arg_20]
0x1800073f2  xor     eax, eax
0x1800073f4  mov     [rcx], rsi
0x1800073f7  add     rsp, 28h
0x1800073fb  pop     r15
0x1800073fd  pop     r14
0x1800073ff  pop     r13
0x180007401  pop     r12
0x180007403  pop     rdi
0x180007404  pop     rsi
0x180007405  pop     rbp
0x180007406  pop     rbx
0x180007407  retn
0x180007408  lea     rcx, [rbx+60h]; String1
0x18000740c  mov     r8b, 1; CaseInsensitive
0x18000740f  mov     rdx, rbp; String2
0x180007412  call    cs:__imp_RtlEqualUnicodeString
0x180007418  test    al, al
0x18000741a  jnz     short loc_180007495
0x18000741c  lea     rax, WPP_GLOBAL_Control
0x180007423  jmp     loc_1800072A6
0x180007428  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x18000742f  jnz     short loc_180007440
0x180007431  call    ?SecpLoadSspiPackages@@YAJXZ; SecpLoadSspiPackages(void)
0x180007436  mov     ebx, eax
0x180007438  test    eax, eax
0x18000743a  js      loc_18000730E
0x180007440  call    ?SecpLoadSaslProfiles@@YAJXZ; SecpLoadSaslProfiles(void)
0x180007445  mov     ebx, eax
0x180007447  jmp     loc_18000730E
0x180007450  lea     rcx, [rbx+rbx*2]
0x180007454  mov     dl, 1; Wait
0x180007456  shl     rcx, 5
0x18000745a  add     rcx, r15; Resource
0x18000745d  call    cs:__imp_RtlAcquireResourceExclusive
0x180007463  mov     eax, cs:SecPackageListLockCount
0x180007469  inc     ebx
0x18000746b  cmp     ebx, eax
0x18000746d  jnb     loc_1800072DB
0x180007473  jmp     short loc_180007450
0x180007475  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x18000747c  jz      loc_1800072BB
0x180007482  mov     rcx, r15; Resource
0x180007485  call    cs:__imp_RtlReleaseResource
0x18000748b  mov     eax, 80090305h
0x180007490  jmp     loc_1800073F7
0x180007495  cmp     edi, 8
0x180007498  jz      loc_18000736E
0x18000749e  mov     eax, [rbx+10h]
0x1800074a1  and     eax, edi
0x1800074a3  cmp     eax, edi
0x1800074a5  jz      loc_18000736E
0x1800074ab  jmp     loc_18000741C
0x1800074b0  test    r12d, r12d
0x1800074b3  jz      loc_180007380
0x1800074b9  mov     rax, cs:?SecGlobalExtenderPackage@@3PEAU_DLL_SECURITY_PACKAGE@@EA; _DLL_SECURITY_PACKAGE * SecGlobalExtenderPackage
0x1800074c0  test    rax, rax
0x1800074c3  cmovnz  rsi, rax
0x1800074c7  jmp     loc_180007380
0x1800074cc  xor     ebx, ebx
0x1800074ce  test    eax, eax
0x1800074d0  jz      loc_18000732A
0x1800074d6  lea     rcx, [rbx+rbx*2]
0x1800074da  shl     rcx, 5
0x1800074de  add     rcx, r15; Resource
0x1800074e1  call    cs:__imp_RtlReleaseResource
0x1800074e7  inc     ebx
0x1800074e9  cmp     ebx, cs:SecPackageListLockCount
0x1800074ef  jb      short loc_1800074D6
0x1800074f1  jmp     loc_18000732A
0x1800074f6  lea     rcx, [rsi+rsi*2]
0x1800074fa  shl     rcx, 5
0x1800074fe  add     rcx, r15; Resource
0x180007501  call    cs:__imp_RtlReleaseResource
0x180007507  inc     esi
0x180007509  cmp     esi, cs:SecPackageListLockCount
0x18000750f  jb      short loc_1800074F6
0x180007511  jmp     loc_180007326
```
