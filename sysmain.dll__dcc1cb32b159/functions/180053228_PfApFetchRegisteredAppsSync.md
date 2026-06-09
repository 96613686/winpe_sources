# PfApFetchRegisteredAppsSync

- ea: `0x180053228`
- end: `0x18005361f`
- name: `PfApFetchRegisteredAppsSync`
- size: `1015`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180058d80`

## callees

- `0x18003fc24`
- `0x180053228`
- `0x18006e3f8`
- `0x180072efc`
- `0x180073e28`
- `0x1800ab9e8`
- `0x1800b7010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180053543`
- `ntdll!RtlNtStatusToDosError` at `0x180053543`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005340c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800535ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800535e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005340c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800535ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800535e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053603`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053423`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800534ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053423`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800534ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005359d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005359d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x1800533c4`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x1800533c4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x1800533ea`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x1800533ea`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18005351e`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x1800535cd`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18005351e`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x1800535cd`

## pseudocode

```c
__int64 __fastcall PfApFetchRegisteredAppsSync(__int64 a1, void *a2)
{
  _QWORD *v2; // rdi
  int v3; // r12d
  void *v4; // r13
  _QWORD *v6; // rbx
  __int64 **v7; // rcx
  BYTE *v8; // r14
  int v9; // eax
  ULONG PrefetchableAppAdd; // edi
  UINT32 v11; // ebx
  unsigned int v12; // r15d
  __int64 (__fastcall *v13)(char *, int *, __int64 *); // rax
  NTSTATUS v14; // eax
  LONG PackageApplicationIds; // eax
  __int64 v16; // r13
  unsigned int AppNameHashFromAppUserModelId; // eax
  _QWORD *v18; // rdi
  _QWORD *v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdi
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 *v26; // rdx
  __int64 *v27; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v30; // [rsp+30h] [rbp-39h] BYREF
  __int64 v31; // [rsp+38h] [rbp-31h] BYREF
  __int64 *v32; // [rsp+40h] [rbp-29h] BYREF
  __int64 **v33; // [rsp+48h] [rbp-21h]
  LPVOID lpMem; // [rsp+50h] [rbp-19h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+58h] [rbp-11h] BYREF
  int v36; // [rsp+60h] [rbp-9h] BYREF
  _QWORD *v37; // [rsp+68h] [rbp-1h] BYREF
  PCWSTR v38; // [rsp+70h] [rbp+7h]
  __int64 v39; // [rsp+78h] [rbp+Fh]
  UINT32 bufferLength; // [rsp+D0h] [rbp+67h] BYREF
  void *v41; // [rsp+D8h] [rbp+6Fh]
  unsigned int v42; // [rsp+E0h] [rbp+77h] BYREF
  UINT32 count; // [rsp+E8h] [rbp+7Fh] BYREF

  v41 = a2;
  v2 = *(_QWORD **)(a1 + 8);
  v3 = 0;
  v33 = &v32;
  v37 = 0;
  v32 = (__int64 *)&v32;
  v4 = a2;
  bufferLength = 0;
  count = 0;
  v6 = v2;
  v36 = 0;
  v42 = 0;
  lpMem = 0;
  v31 = 0;
  packageInfoReference = 0;
  while ( 1 )
  {
    v30 = v6;
    if ( !v6 )
      break;
    if ( (*v6 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
    {
      PfsHashTableCorruptionCallback(a1, 30, &v30);
      v6 = v30;
    }
    if ( !v6 )
      break;
    v6 = (_QWORD *)*v6;
    if ( ((unsigned __int8)v6 & 1) != 0 )
      break;
LABEL_12:
    if ( !v6 )
      goto LABEL_15;
    v7 = v33;
    v37 = v6;
    if ( *v33 != (__int64 *)&v32 )
LABEL_51:
      __fastfail(3u);
    v6[3] = v33;
    v6[2] = &v32;
    *v7 = v6 + 2;
    v33 = (__int64 **)(v6 + 2);
    PfApFetchEntryEventsCleanup(v6);
    *(_OWORD *)(v6 + 7) = 0;
    v6[6] = v6 + 6;
  }
  for ( ++v2; (unsigned __int64)v2 < *(_QWORD *)(a1 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 4) >> 5); ++v2 )
  {
    v6 = (_QWORD *)*v2;
    if ( (*v2 & 1) == 0 )
    {
      v30 = (_QWORD *)*v2;
      goto LABEL_12;
    }
  }
LABEL_15:
  v8 = 0;
  v9 = (*(__int64 (__fastcall **)(unsigned int *, LPVOID *, const wchar_t *, _QWORD))(a1 + 48))(
         &v42,
         &lpMem,
         L"*.*",
         *(unsigned int *)(a1 + 100));
  if ( v9 < 0 )
  {
    PrefetchableAppAdd = (unsigned __int16)v9;
    goto LABEL_53;
  }
  v11 = 0;
  v12 = 0;
  LODWORD(v30) = 0;
  while ( v12 < v42 )
  {
    v13 = *(__int64 (__fastcall **)(char *, int *, __int64 *))(a1 + 24);
    v39 = 16LL * v12;
    v31 = 0;
    v14 = v13((char *)lpMem + v39, &v36, &v31);
    if ( v14 < 0 )
    {
      PrefetchableAppAdd = RtlNtStatusToDosError(v14);
      goto LABEL_53;
    }
    v38 = (PCWSTR)(v31 + *(unsigned int *)(v31 + 36));
    PrefetchableAppAdd = OpenPackageInfoByFullNameForUser(v4, v38, 0, &packageInfoReference);
    if ( PrefetchableAppAdd )
      goto LABEL_53;
    v3 = 1;
    while ( 1 )
    {
      bufferLength = v11;
      PackageApplicationIds = GetPackageApplicationIds(packageInfoReference, &bufferLength, v8, &count);
      PrefetchableAppAdd = PackageApplicationIds;
      if ( PackageApplicationIds != 122 )
        break;
      if ( v8 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
      v8 = (BYTE *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, bufferLength);
      if ( !v8 )
      {
        PrefetchableAppAdd = 8;
        goto LABEL_53;
      }
      v11 = bufferLength;
      LODWORD(v30) = bufferLength;
    }
    if ( PackageApplicationIds )
      goto LABEL_53;
    v16 = 0;
    while ( (unsigned int)v16 < count )
    {
      AppNameHashFromAppUserModelId = PfsGetAppNameHashFromAppUserModelId(*(_QWORD *)&v8[8 * v16]);
      PrefetchableAppAdd = PfApFetchPrefetchableAppAdd(a1, v38, AppNameHashFromAppUserModelId, &v37);
      if ( PrefetchableAppAdd )
        goto LABEL_53;
      v18 = v37;
      v19 = v37 + 2;
      v20 = v37[2];
      if ( (_QWORD *)v20 != v37 + 2 )
      {
        if ( *(_QWORD **)(v20 + 8) != v19 )
          goto LABEL_51;
        v21 = (_QWORD *)v37[3];
        if ( (_QWORD *)*v21 != v19 )
          goto LABEL_51;
        *v21 = v20;
        *(_QWORD *)(v20 + 8) = v21;
        v19[1] = v19;
        *v19 = v19;
      }
      v22 = v18 + 6;
      if ( (_QWORD *)*v22 == v22 )
      {
        v23 = v22;
        v24 = 0;
      }
      else
      {
        v24 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x18u);
        v23 = v24;
        if ( !v24 )
        {
          PrefetchableAppAdd = 8;
          goto LABEL_53;
        }
        *v24 = *v22;
      }
      v25 = v39;
      v16 = (unsigned int)(v16 + 1);
      *v22 = v24;
      *(_OWORD *)(v23 + 1) = *(_OWORD *)((char *)lpMem + v25);
    }
    v3 = 0;
    if ( v31 )
    {
      (*(void (**)(void))(a1 + 32))();
      v31 = 0;
    }
    ClosePackageInfo(packageInfoReference);
    v11 = (unsigned int)v30;
    ++v12;
    v4 = v41;
  }
  while ( 1 )
  {
    v26 = v32;
    if ( v32 == (__int64 *)&v32 )
      break;
    if ( (__int64 **)v32[1] != &v32 )
      goto LABEL_51;
    v27 = (__int64 *)*v32;
    if ( *(__int64 **)(*v32 + 8) != v32 )
      goto LABEL_51;
    v32 = (__int64 *)*v32;
    v27[1] = (__int64)&v32;
    PfApFetchPrefetchableAppRemove(a1, v26 - 2);
  }
  PrefetchableAppAdd = 0;
LABEL_53:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v31 )
    (*(void (**)(void))(a1 + 32))();
  if ( v3 )
    ClosePackageInfo(packageInfoReference);
  if ( v8 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
  return PrefetchableAppAdd;
}

```

## disassembly

```asm
0x180053228  mov     [rsp-8+arg_8], rdx
0x18005322d  push    rbp
0x18005322e  push    rbx
0x18005322f  push    rsi
0x180053230  push    rdi
0x180053231  push    r12
0x180053233  push    r13
0x180053235  push    r14
0x180053237  push    r15
0x180053239  lea     rbp, [rsp-1Fh]
0x18005323e  sub     rsp, 88h
0x180053245  mov     rdi, [rcx+8]
0x180053249  lea     rax, [rbp+57h+var_80]
0x18005324d  xor     r12d, r12d
0x180053250  mov     [rbp+57h+var_78], rax
0x180053254  lea     rax, [rbp+57h+var_80]
0x180053258  mov     [rbp+57h+var_58], r12
0x18005325c  mov     [rbp+57h+var_80], rax
0x180053260  mov     r13, rdx
0x180053263  mov     rsi, rcx
0x180053266  mov     [rbp+57h+bufferLength], r12d
0x18005326a  mov     [rbp+57h+count], r12d
0x18005326e  mov     rbx, rdi
0x180053271  mov     [rbp+57h+var_60], r12d
0x180053275  mov     r14, 8000000000000002h
0x18005327f  mov     [rbp+57h+arg_10], r12d
0x180053283  mov     [rbp+57h+lpMem], r12
0x180053287  mov     [rbp+57h+var_88], r12
0x18005328b  mov     [rbp+57h+packageInfoReference], r12
0x18005328f  mov     [rbp+57h+var_90], rbx
0x180053293  test    rbx, rbx
0x180053296  jz      short loc_1800532C5
0x180053298  mov     rax, [rbx]
0x18005329b  and     rax, r14
0x18005329e  cmp     rax, r14
0x1800532a1  jnz     short loc_1800532B8
0x1800532a3  lea     r8, [rbp+57h+var_90]
0x1800532a7  mov     edx, 1Eh
0x1800532ac  mov     rcx, rsi
0x1800532af  call    PfsHashTableCorruptionCallback
0x1800532b4  mov     rbx, [rbp+57h+var_90]
0x1800532b8  test    rbx, rbx
0x1800532bb  jz      short loc_1800532C5
0x1800532bd  mov     rbx, [rbx]
0x1800532c0  test    bl, 1
0x1800532c3  jz      short loc_1800532EF
0x1800532c5  mov     ecx, [rsi+4]
0x1800532c8  add     rdi, 8
0x1800532cc  mov     rax, [rsi+8]
0x1800532d0  shr     rcx, 5
0x1800532d4  lea     rdx, [rax+rcx*8]
0x1800532d8  cmp     rdi, rdx
0x1800532db  jnb     short loc_18005333D
0x1800532dd  mov     rbx, [rdi]
0x1800532e0  test    bl, 1
0x1800532e3  jz      short loc_1800532EB
0x1800532e5  add     rdi, 8
0x1800532e9  jmp     short loc_1800532D8
0x1800532eb  mov     [rbp+57h+var_90], rbx
0x1800532ef  mov     rax, rbx
0x1800532f2  test    rax, rax
0x1800532f5  jz      short loc_18005333D
0x1800532f7  mov     rcx, [rbp+57h+var_78]
0x1800532fb  lea     rax, [rbp+57h+var_80]
0x1800532ff  mov     [rbp+57h+var_58], rbx
0x180053303  cmp     [rcx], rax
0x180053306  jnz     loc_180053589
0x18005330c  lea     rax, [rbx+10h]
0x180053310  mov     [rax+8], rcx
0x180053314  lea     rdx, [rbp+57h+var_80]
0x180053318  mov     [rax], rdx
0x18005331b  mov     [rcx], rax
0x18005331e  mov     rcx, rbx
0x180053321  mov     [rbp+57h+var_78], rax
0x180053325  call    PfApFetchEntryEventsCleanup
0x18005332a  xorps   xmm0, xmm0
0x18005332d  lea     rax, [rbx+30h]
0x180053331  movups  xmmword ptr [rbx+38h], xmm0
0x180053335  mov     [rax], rax
0x180053338  jmp     loc_18005328F
0x18005333d  mov     r9d, [rsi+64h]
0x180053341  lea     r8, asc_1800BD050; "*.*"
0x180053348  mov     rax, [rsi+30h]
0x18005334c  lea     rdx, [rbp+57h+lpMem]
0x180053350  lea     rcx, [rbp+57h+arg_10]
0x180053354  mov     r14, r12
0x180053357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005335c  test    eax, eax
0x18005335e  jns     short loc_18005336A
0x180053360  xor     ebx, ebx
0x180053362  movzx   edi, ax
0x180053365  jmp     loc_180053596
0x18005336a  mov     ebx, r12d
0x18005336d  mov     r15d, r12d
0x180053370  mov     dword ptr [rbp+57h+var_90], ebx
0x180053373  cmp     r15d, [rbp+57h+arg_10]
0x180053377  jnb     loc_18005354F
0x18005337d  mov     rax, [rsi+18h]
0x180053381  lea     r8, [rbp+57h+var_88]
0x180053385  mov     ecx, r15d
0x180053388  lea     rdx, [rbp+57h+var_60]
0x18005338c  shl     rcx, 4
0x180053390  mov     [rbp+57h+var_48], rcx
0x180053394  add     rcx, [rbp+57h+lpMem]
0x180053398  mov     [rbp+57h+var_88], r12
0x18005339c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533a1  test    eax, eax
0x1800533a3  js      loc_180053541
0x1800533a9  mov     rax, [rbp+57h+var_88]
0x1800533ad  lea     r9, [rbp+57h+packageInfoReference]; packageInfoReference
0x1800533b1  xor     r8d, r8d; reserved
0x1800533b4  mov     ecx, [rax+24h]
0x1800533b7  add     rcx, rax
0x1800533ba  mov     [rbp+57h+var_50], rcx
0x1800533be  mov     rdx, rcx; packageFullName
0x1800533c1  mov     rcx, r13; userSid
0x1800533c4  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x1800533ca  mov     edi, eax
0x1800533cc  test    eax, eax
0x1800533ce  jnz     loc_18005354B
0x1800533d4  lea     r12d, [rax+1]
0x1800533d8  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x1800533dc  lea     r9, [rbp+57h+count]; count
0x1800533e0  mov     r8, r14; buffer
0x1800533e3  mov     [rbp+57h+bufferLength], ebx
0x1800533e6  lea     rdx, [rbp+57h+bufferLength]; bufferLength
0x1800533ea  call    cs:__imp_GetPackageApplicationIds
0x1800533f0  mov     edi, eax
0x1800533f2  cmp     eax, 7Ah ; 'z'
0x1800533f5  jnz     short loc_18005343D
0x1800533f7  test    r14, r14
0x1800533fa  jz      short loc_180053412
0x1800533fc  mov     rcx, cs:PfSvcGlobals
0x180053403  mov     r8, r14; lpMem
0x180053406  xor     edx, edx; dwFlags
0x180053408  mov     rcx, [rcx+58h]; hHeap
0x18005340c  call    cs:__imp_HeapFree
0x180053412  mov     rcx, cs:PfSvcGlobals
0x180053419  xor     edx, edx; dwFlags
0x18005341b  mov     r8d, [rbp+57h+bufferLength]; dwBytes
0x18005341f  mov     rcx, [rcx+58h]; hHeap
0x180053423  call    cs:__imp_HeapAlloc
0x180053429  mov     r14, rax
0x18005342c  test    rax, rax
0x18005342f  jz      loc_180053533
0x180053435  mov     ebx, [rbp+57h+bufferLength]
0x180053438  mov     dword ptr [rbp+57h+var_90], ebx
0x18005343b  jmp     short loc_1800533D8
0x18005343d  test    eax, eax
0x18005343f  jnz     loc_18005354B
0x180053445  xor     r13d, r13d
0x180053448  cmp     r13d, [rbp+57h+count]
0x18005344c  jnb     loc_180053501
0x180053452  mov     rcx, [r14+r13*8]
0x180053456  call    PfsGetAppNameHashFromAppUserModelId
0x18005345b  mov     rdx, [rbp+57h+var_50]
0x18005345f  lea     r9, [rbp+57h+var_58]
0x180053463  mov     r8d, eax
0x180053466  mov     rcx, rsi
0x180053469  call    PfApFetchPrefetchableAppAdd
0x18005346e  mov     edi, eax
0x180053470  test    eax, eax
0x180053472  jnz     loc_18005354B
0x180053478  mov     rdi, [rbp+57h+var_58]
0x18005347c  lea     rax, [rdi+10h]
0x180053480  mov     rcx, [rax]
0x180053483  cmp     rcx, rax
0x180053486  jz      short loc_1800534AD
0x180053488  cmp     [rcx+8], rax
0x18005348c  jnz     loc_180053589
0x180053492  mov     rdx, [rax+8]
0x180053496  cmp     [rdx], rax
0x180053499  jnz     loc_180053589
0x18005349f  mov     [rdx], rcx
0x1800534a2  mov     [rcx+8], rdx
0x1800534a6  mov     [rax+8], rax
0x1800534aa  mov     [rax], rax
0x1800534ad  add     rdi, 30h ; '0'
0x1800534b1  cmp     [rdi], rdi
0x1800534b4  jnz     short loc_1800534BD
0x1800534b6  mov     rbx, rdi
0x1800534b9  xor     eax, eax
0x1800534bb  jmp     short loc_1800534E5
0x1800534bd  mov     rcx, cs:PfSvcGlobals
0x1800534c4  xor     edx, edx; dwFlags
0x1800534c6  mov     rcx, [rcx+58h]; hHeap
0x1800534ca  lea     r8d, [rdx+18h]; dwBytes
0x1800534ce  call    cs:__imp_HeapAlloc
0x1800534d4  mov     rbx, rax
0x1800534d7  test    rax, rax
0x1800534da  jz      short loc_18005353A
0x1800534dc  mov     rax, [rdi]
0x1800534df  mov     [rbx], rax
0x1800534e2  mov     rax, rbx
0x1800534e5  mov     rcx, [rbp+57h+var_48]
0x1800534e9  inc     r13d
0x1800534ec  mov     [rdi], rax
0x1800534ef  mov     rax, [rbp+57h+lpMem]
0x1800534f3  movups  xmm0, xmmword ptr [rcx+rax]
0x1800534f7  movdqu  xmmword ptr [rbx+8], xmm0
0x1800534fc  jmp     loc_180053448
0x180053501  mov     rcx, [rbp+57h+var_88]
0x180053505  xor     r12d, r12d
0x180053508  test    rcx, rcx
0x18005350b  jz      short loc_18005351A
0x18005350d  mov     rax, [rsi+20h]
0x180053511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053516  mov     [rbp+57h+var_88], r12
0x18005351a  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x18005351e  call    cs:__imp_ClosePackageInfo
0x180053524  mov     ebx, dword ptr [rbp+57h+var_90]
0x180053527  inc     r15d
0x18005352a  mov     r13, [rbp+57h+arg_8]
0x18005352e  jmp     loc_180053373
0x180053533  mov     edi, 8
0x180053538  jmp     short loc_18005354B
0x18005353a  mov     edi, 8
0x18005353f  jmp     short loc_180053596
0x180053541  mov     ecx, eax; Status
0x180053543  call    cs:__imp_RtlNtStatusToDosError
0x180053549  mov     edi, eax
0x18005354b  xor     ebx, ebx
0x18005354d  jmp     short loc_180053596
0x18005354f  mov     rdx, [rbp+57h+var_80]
0x180053553  lea     rax, [rbp+57h+var_80]
0x180053557  cmp     rdx, rax
0x18005355a  jz      short loc_180053590
0x18005355c  lea     rax, [rbp+57h+var_80]
0x180053560  cmp     [rdx+8], rax
0x180053564  jnz     short loc_180053589
0x180053566  mov     rax, [rdx]
0x180053569  cmp     [rax+8], rdx
0x18005356d  jnz     short loc_180053589
0x18005356f  lea     rcx, [rbp+57h+var_80]
0x180053573  mov     [rbp+57h+var_80], rax
0x180053577  mov     [rax+8], rcx
0x18005357b  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18005357f  mov     rcx, rsi
0x180053582  call    PfApFetchPrefetchableAppRemove
0x180053587  jmp     short loc_18005354F
0x180053589  mov     ecx, 3
0x18005358e  int     29h; Win8: RtlFailFast(ecx)
0x180053590  mov     edi, r12d
0x180053593  mov     rbx, r12
0x180053596  cmp     [rbp+57h+lpMem], 0
0x18005359b  jz      short loc_1800535B2
0x18005359d  call    cs:__imp_GetProcessHeap
0x1800535a3  mov     r8, [rbp+57h+lpMem]; lpMem
0x1800535a7  xor     edx, edx; dwFlags
0x1800535a9  mov     rcx, rax; hHeap
0x1800535ac  call    cs:__imp_HeapFree
0x1800535b2  mov     rcx, [rbp+57h+var_88]
0x1800535b6  test    rcx, rcx
0x1800535b9  jz      short loc_1800535C4
0x1800535bb  mov     rax, [rsi+20h]
0x1800535bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535c4  test    r12d, r12d
0x1800535c7  jz      short loc_1800535D3
0x1800535c9  mov     rcx, [rbp+57h+packageInfoReference]; packageInfoReference
0x1800535cd  call    cs:__imp_ClosePackageInfo
0x1800535d3  test    r14, r14
0x1800535d6  jz      short loc_1800535EE
0x1800535d8  mov     rcx, cs:PfSvcGlobals
0x1800535df  mov     r8, r14; lpMem
0x1800535e2  xor     edx, edx; dwFlags
0x1800535e4  mov     rcx, [rcx+58h]; hHeap
0x1800535e8  call    cs:__imp_HeapFree
0x1800535ee  test    rbx, rbx
0x1800535f1  jz      short loc_180053609
0x1800535f3  mov     rcx, cs:PfSvcGlobals
0x1800535fa  mov     r8, rbx; lpMem
0x1800535fd  xor     edx, edx; dwFlags
0x1800535ff  mov     rcx, [rcx+58h]; hHeap
0x180053603  call    cs:__imp_HeapFree
0x180053609  mov     eax, edi
0x18005360b  add     rsp, 88h
0x180053612  pop     r15
0x180053614  pop     r14
0x180053616  pop     r13
0x180053618  pop     r12
0x18005361a  pop     rdi
0x18005361b  pop     rsi
0x18005361c  pop     rbx
0x18005361d  pop     rbp
0x18005361e  retn
```
