# CSpObjectTokenCategory::SetId(ushort const *,int)

- ea: `0x18000c840`
- end: `0x18000cd9f`
- name: `?SetId@CSpObjectTokenCategory@@UEAAJPEBGH@Z`
- size: `1375`
- prototype: `int(CSpObjectTokenCategory *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a420`
- `0x18000bee8`
- `0x18000c840`
- `0x18000e518`
- `0x180018d10`
- `0x180026508`
- `0x18007d7b1`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000cb18`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000cb18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c87d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c87d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c8c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c8c2`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000c92b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000c92b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c91d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c91d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cbf5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c9b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c9b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000cbc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ccdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000cd23`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000cbc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ccdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000cd23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cb44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cb44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd93`

## string_xrefs

- `0x18000cca4`: `onecoreuap\enduser\NUI\OneCore\sapi\sapi\SharedLib\RegistryIsolator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSpObjectTokenCategory::SetId(CSpObjectTokenCategory *this, const unsigned __int16 *a2, int a3)
{
  char *v5; // r9
  struct _RTL_CRITICAL_SECTION *v6; // r15
  unsigned __int16 *v7; // rdx
  int InitializedSingleton; // esi
  __int64 v9; // rdi
  __int64 v10; // rax
  void **v12; // r14
  const unsigned __int16 *v13; // r12
  HANDLE ProcessHeap; // rax
  SIZE_T v15; // rax
  SIZE_T v16; // rax
  unsigned __int64 v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // r8
  SIZE_T v20; // rcx
  LPVOID v21; // rax
  DWORD v22; // ecx
  HKEY v23; // r12
  HKEY v24; // r13
  unsigned __int16 *v25; // rdx
  HKEY v26; // r11
  HKEY v27; // r8
  unsigned __int64 i; // rdx
  __int64 v29; // r10
  int v30; // esi
  const WCHAR *v31; // r13
  LSTATUS v32; // eax
  struct IUnknown **v33; // r13
  LSTATUS v34; // eax
  const WCHAR *v35; // rdx
  HKEY v36; // rcx
  int phkResult; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  HKEY v39; // [rsp+58h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-20h] BYREF
  HKEY v41; // [rsp+68h] [rbp-18h] BYREF
  HKEY v42; // [rsp+70h] [rbp-10h]
  char *v43; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  struct CSpRegistryIsolator *v45; // [rsp+C0h] [rbp+40h] BYREF
  int v46; // [rsp+D0h] [rbp+50h]
  HKEY v47; // [rsp+D8h] [rbp+58h] BYREF

  v46 = a3;
  v5 = (char *)this + 8;
  if ( !this )
    v5 = 0;
  v43 = v5;
  v6 = (struct _RTL_CRITICAL_SECTION *)(v5 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  if ( *((_QWORD *)this + 9) )
  {
    InitializedSingleton = -2147201022;
    goto LABEL_10;
  }
  if ( !a2 )
    goto LABEL_9;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( (unsigned __int64)(v10 + 1) > 0xFFFFF )
  {
LABEL_9:
    InitializedSingleton = -2147024809;
    goto LABEL_10;
  }
  v41 = 0;
  v45 = 0;
  if ( (int)CSpRegistryIsolator::GetInitializedSingleton(&v45, v7) >= 0
    && v45
    && CSpRegistryIsolator::ReplaceWithIsolatedKeyIfAvailable(v45, 0, &v41) >= 0 )
  {
    v23 = v41;
  }
  else
  {
    v23 = 0;
    v41 = 0;
  }
  v24 = 0;
  v42 = 0;
  LODWORD(v45) = 0;
  hKey = 0;
  SpGetRootFromRegPath(a2, &hKey);
  if ( !hKey )
  {
    InitializedSingleton = -2147200960;
    goto LABEL_57;
  }
  if ( v23 )
  {
    RegCloseKey(hKey);
    hKey = v23;
  }
  v47 = 0;
  InitializedSingleton = CSpRegistryIsolator::GetInitializedSingleton((struct CSpRegistryIsolator **)&v47, v25);
  if ( InitializedSingleton >= 0 )
  {
    v26 = v47;
    if ( !v47 )
    {
      InitializedSingleton = -2147024882;
      goto LABEL_57;
    }
    v27 = hKey;
    v47 = hKey;
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_QWORD *)v26 + 1) )
        goto LABEL_52;
      v29 = *(_QWORD *)v26 + 16 * i;
      if ( hKey == *(HKEY *)(v29 + 8) )
        break;
    }
    v34 = RegCreateKeyExW(*((HKEY *)v26 + 3), *(LPCWSTR *)v29, 0, 0, 1u, 0xF003Fu, 0, &v47, 0);
    InitializedSingleton = v34;
    if ( v34 > 0 )
      InitializedSingleton = (unsigned __int16)v34 | 0x80070000;
    if ( InitializedSingleton < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\sapi\\sapi\\SharedLib\\RegistryIsolator.h",
        (const char *)(unsigned int)InitializedSingleton,
        phkResult);
      goto LABEL_57;
    }
    v27 = v47;
LABEL_52:
    hKey = v27;
    v39 = 0;
    v30 = 0;
    v31 = wcschr(a2, 0x5Cu) + 1;
    if ( v46 )
      v32 = RegCreateKeyExW(hKey, v31, 0, 0, 1u, 0x2001Fu, 0, &v39, 0);
    else
      v32 = RegOpenKeyExW(hKey, v31, 0, 0x2001Fu, &v39);
    if ( !v32 )
    {
LABEL_55:
      v24 = v39;
      LODWORD(v45) = v30;
      InitializedSingleton = 0;
      goto LABEL_57;
    }
    LODWORD(v47) = 1;
    v35 = v31;
    v36 = hKey;
    if ( v46 )
    {
      InitializedSingleton = RegCreateKeyExW(hKey, v31, 0, 0, 1u, 0x20019u, 0, &v39, 0);
      if ( InitializedSingleton != 5 )
      {
LABEL_80:
        if ( !InitializedSingleton )
        {
          v30 = (int)v47;
          goto LABEL_55;
        }
        if ( InitializedSingleton == 2 || InitializedSingleton == 259 )
        {
          InitializedSingleton = -2147200966;
          v24 = v42;
        }
        else
        {
          if ( InitializedSingleton > 0 )
            InitializedSingleton = (unsigned __int16)InitializedSingleton | 0x80070000;
          v24 = v42;
        }
        goto LABEL_57;
      }
      v35 = v31;
      v36 = hKey;
    }
    InitializedSingleton = RegOpenKeyExW(v36, v35, 0, 0x20019u, &v39);
    goto LABEL_80;
  }
LABEL_57:
  if ( hKey != v23 && hKey )
    RegCloseKey(hKey);
  ppv = 0;
  if ( InitializedSingleton < 0
    || (InitializedSingleton = CoCreateInstance(
                                 &CLSID_SpDataKey,
                                 0,
                                 0x17u,
                                 &GUID_92a66e2b_c830_4149_83df_6fc2ba1e7a5b,
                                 &ppv),
        InitializedSingleton < 0)
    || (InitializedSingleton = (*(__int64 (__fastcall **)(LPVOID, HKEY, _QWORD))(*(_QWORD *)ppv + 120LL))(
                                 ppv,
                                 v24,
                                 (unsigned int)v45),
        InitializedSingleton < 0) )
  {
    if ( v24 )
      RegCloseKey(v24);
    v33 = (struct IUnknown **)((char *)this + 72);
  }
  else
  {
    v33 = (struct IUnknown **)((char *)this + 72);
    InitializedSingleton = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(
                             ppv,
                             &GUID_14056581_e16c_11d2_bb90_00c04f8ee6c0,
                             (char *)this + 72);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v23 )
    RegCloseKey(v23);
  if ( InitializedSingleton >= 0 )
  {
    v12 = (void **)((char *)this + 64);
    v13 = (const unsigned __int16 *)*v12;
    if ( a2 == *v12 )
    {
LABEL_29:
      if ( !*v12 )
      {
        InitializedSingleton = -2147024882;
        if ( *v33 )
          ATL::AtlComPtrAssign(v33, 0);
      }
      goto LABEL_10;
    }
    if ( !v13 )
    {
      do
LABEL_24:
        ++v9;
      while ( a2[v9] );
      if ( (unsigned int)v9 >= 0x4FFFFFFF || (v20 = 2LL * (unsigned int)(v9 + 1), v20 <= (unsigned int)v9) )
      {
        v22 = 534;
      }
      else
      {
        v21 = CoTaskMemAlloc(v20);
        *v12 = v21;
        if ( v21 )
        {
          *((_WORD *)v21 + (unsigned int)v9) = 0;
          memcpy_0(*v12, a2, 2 * v9);
          goto LABEL_29;
        }
        v22 = 14;
      }
      SetLastError(v22);
      goto LABEL_29;
    }
    ProcessHeap = GetProcessHeap();
    v15 = HeapSize(ProcessHeap, 0, v13);
    if ( v15 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v16 = v15 >> 1;
      v17 = v16 - 1;
      if ( v16 - 1 < 8 )
      {
        if ( v16 == 1 )
          goto LABEL_23;
        v19 = 0;
      }
      else
      {
        v18 = *v12;
        if ( *v12 > v12 || (v19 = 0, v17 = 8, (void **)((char *)v18 + 14) < v12) )
        {
          *v18 = -559030611;
          v18[1] = -559030611;
          v18[2] = -559030611;
          v18[3] = -559030611;
          goto LABEL_23;
        }
      }
      do
        *((_WORD *)*v12 + v19++) = -8531;
      while ( v19 < v17 );
    }
LABEL_23:
    CoTaskMemFree(*v12);
    *v12 = 0;
    goto LABEL_24;
  }
LABEL_10:
  LeaveCriticalSection(v6);
  return (unsigned int)InitializedSingleton;
}

```

## disassembly

```asm
0x18000c840  mov     [rsp-38h+arg_8], rbx
0x18000c845  mov     [rsp-38h+arg_10], r8d
0x18000c84a  push    rbp
0x18000c84b  push    rsi
0x18000c84c  push    rdi
0x18000c84d  push    r12
0x18000c84f  push    r13
0x18000c851  push    r14
0x18000c853  push    r15
0x18000c855  mov     rbp, rsp
0x18000c858  sub     rsp, 80h
0x18000c85f  mov     rbx, rdx
0x18000c862  mov     r14, rcx
0x18000c865  lea     r9, [rcx+8]
0x18000c869  xor     eax, eax
0x18000c86b  test    rcx, rcx
0x18000c86e  cmovz   r9, rax
0x18000c872  mov     [rbp+var_8], r9
0x18000c876  lea     r15, [r9+8]
0x18000c87a  mov     rcx, r15; lpCriticalSection
0x18000c87d  call    cs:__imp_EnterCriticalSection
0x18000c883  nop
0x18000c884  cmp     qword ptr [r14+48h], 0
0x18000c889  jz      short loc_18000C892
0x18000c88b  mov     esi, 80045002h
0x18000c890  jmp     short loc_18000C8BF
0x18000c892  test    rbx, rbx
0x18000c895  jz      short loc_18000C8BA
0x18000c897  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c89e  mov     rax, rdi
0x18000c8a1  inc     rax
0x18000c8a4  cmp     word ptr [rbx+rax*2], 0
0x18000c8a9  jnz     short loc_18000C8A1
0x18000c8ab  inc     rax
0x18000c8ae  cmp     rax, 0FFFFFh
0x18000c8b4  jbe     loc_18000CA3A
0x18000c8ba  mov     esi, 80070057h
0x18000c8bf  mov     rcx, r15; lpCriticalSection
0x18000c8c2  call    cs:__imp_LeaveCriticalSection
0x18000c8c8  mov     eax, esi
0x18000c8ca  mov     rbx, [rsp+80h+arg_8]
0x18000c8d2  add     rsp, 80h
0x18000c8d9  pop     r15
0x18000c8db  pop     r14
0x18000c8dd  pop     r13
0x18000c8df  pop     r12
0x18000c8e1  pop     rdi
0x18000c8e2  pop     rsi
0x18000c8e3  pop     rbp
0x18000c8e4  retn
0x18000c8e5  mov     rcx, [rbp+ppv]
0x18000c8e9  test    rcx, rcx
0x18000c8ec  jz      short loc_18000C8FB
0x18000c8ee  mov     rax, [rcx]
0x18000c8f1  mov     rax, [rax+10h]
0x18000c8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8fa  nop
0x18000c8fb  test    r12, r12
0x18000c8fe  jnz     loc_18000CD90
0x18000c904  test    esi, esi
0x18000c906  js      short loc_18000C8BF
0x18000c908  add     r14, 40h ; '@'
0x18000c90c  mov     r12, [r14]
0x18000c90f  cmp     rbx, r12
0x18000c912  jz      loc_18000C9D9
0x18000c918  test    r12, r12
0x18000c91b  jz      short loc_18000C995
0x18000c91d  call    cs:__imp_GetProcessHeap
0x18000c923  mov     r8, r12; lpMem
0x18000c926  xor     edx, edx; dwFlags
0x18000c928  mov     rcx, rax; hHeap
0x18000c92b  call    cs:__imp_HeapSize
0x18000c931  lea     rcx, [rax-3]
0x18000c935  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18000c939  ja      short loc_18000C985
0x18000c93b  shr     rax, 1
0x18000c93e  lea     r9, [rax-1]
0x18000c942  cmp     r9, 8
0x18000c946  jb      loc_18000CA16
0x18000c94c  mov     rcx, [r14]
0x18000c94f  cmp     rcx, r14
0x18000c952  ja      short loc_18000C96A
0x18000c954  xor     r8d, r8d
0x18000c957  mov     r9d, 8
0x18000c95d  lea     rax, [rcx+0Eh]
0x18000c961  cmp     rax, r14
0x18000c964  jnb     loc_18000CA22
0x18000c96a  mov     dword ptr [rcx], 0DEADDEADh
0x18000c970  mov     dword ptr [rcx+4], 0DEADDEADh
0x18000c977  mov     dword ptr [rcx+8], 0DEADDEADh
0x18000c97e  mov     dword ptr [rcx+0Ch], 0DEADDEADh
0x18000c985  mov     rcx, [r14]; pv
0x18000c988  call    cs:__imp_CoTaskMemFree
0x18000c98e  mov     qword ptr [r14], 0
0x18000c995  inc     rdi
0x18000c998  cmp     word ptr [rbx+rdi*2], 0
0x18000c99d  jnz     short loc_18000C995
0x18000c99f  cmp     edi, 4FFFFFFFh
0x18000c9a5  jnb     short loc_18000CA0F
0x18000c9a7  lea     ecx, [rdi+1]
0x18000c9aa  add     rcx, rcx; cb
0x18000c9ad  mov     r12d, edi
0x18000c9b0  cmp     rcx, r12
0x18000c9b3  jbe     short loc_18000CA0F
0x18000c9b5  call    cs:__imp_CoTaskMemAlloc
0x18000c9bb  mov     [r14], rax
0x18000c9be  test    rax, rax
0x18000c9c1  jz      short loc_18000CA02
0x18000c9c3  xor     ecx, ecx
0x18000c9c5  mov     [rax+r12*2], cx
0x18000c9ca  lea     r8, [rdi+rdi]; Size
0x18000c9ce  mov     rdx, rbx; Src
0x18000c9d1  mov     rcx, [r14]; void *
0x18000c9d4  call    memcpy_0
0x18000c9d9  cmp     qword ptr [r14], 0
0x18000c9dd  jnz     loc_18000C8BF
0x18000c9e3  mov     esi, 8007000Eh
0x18000c9e8  cmp     qword ptr [r13+0], 0
0x18000c9ed  jz      loc_18000C8BF
0x18000c9f3  xor     edx, edx; struct IUnknown *
0x18000c9f5  mov     rcx, r13; struct IUnknown **
0x18000c9f8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000c9fd  jmp     loc_18000C8BF
0x18000ca02  mov     ecx, 0Eh; dwErrCode
0x18000ca07  call    cs:__imp_SetLastError
0x18000ca0d  jmp     short loc_18000C9D9
0x18000ca0f  mov     ecx, 216h
0x18000ca14  jmp     short loc_18000CA07
0x18000ca16  test    r9, r9
0x18000ca19  jz      loc_18000C985
0x18000ca1f  xor     r8d, r8d
0x18000ca22  mov     rax, [r14]
0x18000ca25  mov     word ptr [rax+r8*2], 0DEADh
0x18000ca2c  inc     r8
0x18000ca2f  cmp     r8, r9
0x18000ca32  jnb     loc_18000C985
0x18000ca38  jmp     short loc_18000CA22
0x18000ca3a  mov     [rbp+var_18], 0
0x18000ca42  mov     [rbp+arg_0], 0
0x18000ca4a  lea     rcx, [rbp+arg_0]; struct CSpRegistryIsolator **
0x18000ca4e  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x18000ca53  test    eax, eax
0x18000ca55  jns     loc_18000CC60
0x18000ca5b  xor     r12d, r12d
0x18000ca5e  mov     [rbp+var_18], r12
0x18000ca62  xor     r13d, r13d
0x18000ca65  mov     [rbp+var_10], r13
0x18000ca69  mov     dword ptr [rbp+arg_0], r13d
0x18000ca6d  mov     [rbp+hKey], r13
0x18000ca71  lea     rdx, [rbp+hKey]; HKEY *
0x18000ca75  mov     rcx, rbx; unsigned __int16 *
0x18000ca78  call    ?SpGetRootFromRegPath@@YAXPEBGPEAPEAUHKEY__@@@Z; SpGetRootFromRegPath(ushort const *,HKEY__ * *)
0x18000ca7d  cmp     [rbp+hKey], r13
0x18000ca81  jz      loc_18000CC89
0x18000ca87  test    r12, r12
0x18000ca8a  jnz     short loc_18000CADC
0x18000ca8c  mov     [rbp+arg_18], r13
0x18000ca90  lea     rcx, [rbp+arg_18]; struct CSpRegistryIsolator **
0x18000ca94  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x18000ca99  mov     esi, eax
0x18000ca9b  test    eax, eax
0x18000ca9d  js      loc_18000CB61
0x18000caa3  mov     r11, [rbp+arg_18]
0x18000caa7  test    r11, r11
0x18000caaa  jz      loc_18000CC93
0x18000cab0  mov     r8, [rbp+hKey]
0x18000cab4  mov     [rbp+arg_18], r8
0x18000cab8  xor     edx, edx
0x18000caba  mov     r9, [r11+8]
0x18000cabe  cmp     rdx, r9
0x18000cac1  jnb     short loc_18000CB06
0x18000cac3  mov     r10, rdx
0x18000cac6  shl     r10, 4
0x18000caca  add     r10, [r11]
0x18000cacd  cmp     r8, [r10+8]
0x18000cad1  jz      loc_18000CB91
0x18000cad7  inc     rdx
0x18000cada  jmp     short loc_18000CABE
0x18000cadc  mov     rcx, [rbp+hKey]; hKey
0x18000cae0  test    rcx, rcx
0x18000cae3  jz      short loc_18000CAEB
0x18000cae5  call    cs:__imp_RegCloseKey
0x18000caeb  mov     [rbp+hKey], r12
0x18000caef  jmp     short loc_18000CA8C
0x18000caf1  movzx   esi, ax
0x18000caf4  or      esi, 80070000h
0x18000cafa  test    esi, esi
0x18000cafc  js      loc_18000CC9D
0x18000cb02  mov     r8, [rbp+arg_18]
0x18000cb06  mov     [rbp+hKey], r8
0x18000cb0a  mov     [rbp+var_28], r13
0x18000cb0e  xor     esi, esi
0x18000cb10  mov     edx, 5Ch ; '\'; Ch
0x18000cb15  mov     rcx, rbx; Str
0x18000cb18  call    cs:__imp_wcschr
0x18000cb1e  lea     r13, [rax+2]
0x18000cb22  lea     rax, [rbp+var_28]
0x18000cb26  xor     r8d, r8d; Reserved
0x18000cb29  mov     rdx, r13; lpSubKey
0x18000cb2c  mov     rcx, [rbp+hKey]; hKey
0x18000cb30  cmp     [rbp+arg_10], esi
0x18000cb33  jnz     loc_18000CCBA
0x18000cb39  mov     [rsp+80h+phkResult], rax; phkResult
0x18000cb3e  mov     r9d, 2001Fh; samDesired
0x18000cb44  call    cs:__imp_RegOpenKeyExW
0x18000cb4a  test    eax, eax
0x18000cb4c  jnz     loc_18000CCE7
0x18000cb52  mov     r13, [rbp+var_28]
0x18000cb56  mov     dword ptr [rbp+arg_0], esi
0x18000cb59  xor     esi, esi
0x18000cb5b  jmp     short loc_18000CB61
0x18000cb5d  mov     r13, [rbp+var_10]
0x18000cb61  mov     rcx, [rbp+hKey]; hKey
0x18000cb65  cmp     rcx, r12
0x18000cb68  jnz     loc_18000CD7C
0x18000cb6e  mov     [rbp+ppv], 0
0x18000cb76  test    esi, esi
0x18000cb78  jns     short loc_18000CBD6
0x18000cb7a  test    r13, r13
0x18000cb7d  jz      short loc_18000CB88
0x18000cb7f  mov     rcx, r13; hKey
0x18000cb82  call    cs:__imp_RegCloseKey
0x18000cb88  lea     r13, [r14+48h]
0x18000cb8c  jmp     loc_18000C8E5
0x18000cb91  mov     [rsp+80h+lpdwDisposition], r13; lpdwDisposition
0x18000cb96  lea     rax, [rbp+arg_18]
0x18000cb9a  mov     [rsp+80h+var_48], rax; phkResult
0x18000cb9f  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18000cba4  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18000cbac  mov     dword ptr [rsp+80h+phkResult], 1; int
0x18000cbb4  xor     r9d, r9d; lpClass
0x18000cbb7  xor     r8d, r8d; Reserved
0x18000cbba  mov     rdx, [r10]; lpSubKey
0x18000cbbd  mov     rcx, [r11+18h]; hKey
0x18000cbc1  call    cs:__imp_RegCreateKeyExW
0x18000cbc7  mov     esi, eax
0x18000cbc9  test    eax, eax
0x18000cbcb  jle     loc_18000CAFA
0x18000cbd1  jmp     loc_18000CAF1
0x18000cbd6  lea     rax, [rbp+ppv]
0x18000cbda  mov     [rsp+80h+phkResult], rax; ppv
0x18000cbdf  lea     r9, _GUID_92a66e2b_c830_4149_83df_6fc2ba1e7a5b; riid
0x18000cbe6  xor     edx, edx; pUnkOuter
0x18000cbe8  mov     r8d, 17h; dwClsContext
0x18000cbee  lea     rcx, CLSID_SpDataKey; rclsid
0x18000cbf5  call    cs:__imp_CoCreateInstance
0x18000cbfb  mov     esi, eax
0x18000cbfd  test    eax, eax
0x18000cbff  js      loc_18000CB7A
0x18000cc05  mov     rcx, [rbp+ppv]
0x18000cc09  mov     rax, [rcx]
0x18000cc0c  mov     r8d, dword ptr [rbp+arg_0]
0x18000cc10  mov     rdx, r13
0x18000cc13  mov     rax, [rax+78h]
0x18000cc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1c  mov     esi, eax
0x18000cc1e  test    eax, eax
0x18000cc20  js      loc_18000CB7A
0x18000cc26  mov     rcx, [rbp+ppv]
0x18000cc2a  mov     rax, [rcx]
0x18000cc2d  lea     r13, [r14+48h]
0x18000cc31  mov     r8, r13
0x18000cc34  lea     rdx, _GUID_14056581_e16c_11d2_bb90_00c04f8ee6c0
0x18000cc3b  mov     rax, [rax]
0x18000cc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc43  mov     esi, eax
0x18000cc45  jmp     loc_18000C8E5
0x18000cc4a  test    esi, esi
0x18000cc4c  jle     loc_18000CB5D
0x18000cc52  movzx   esi, si
0x18000cc55  or      esi, 80070000h
0x18000cc5b  jmp     loc_18000CB5D
0x18000cc60  mov     rcx, [rbp+arg_0]; this
0x18000cc64  test    rcx, rcx
0x18000cc67  jz      loc_18000CA5B
0x18000cc6d  lea     r8, [rbp+var_18]; HKEY *
0x18000cc71  xor     edx, edx; HKEY
0x18000cc73  call    ?ReplaceWithIsolatedKeyIfAvailable@CSpRegistryIsolator@@QEAAJPEAUHKEY__@@PEAPEAU2@@Z; CSpRegistryIsolator::ReplaceWithIsolatedKeyIfAvailable(HKEY__ *,HKEY__ * *)
0x18000cc78  test    eax, eax
0x18000cc7a  js      loc_18000CA5B
0x18000cc80  mov     r12, [rbp+var_18]
0x18000cc84  jmp     loc_18000CA62
0x18000cc89  mov     esi, 80045040h
0x18000cc8e  jmp     loc_18000CB61
0x18000cc93  mov     esi, 8007000Eh
0x18000cc98  jmp     loc_18000CB61
0x18000cc9d  mov     rcx, [rbp+38h]; this
0x18000cca1  mov     r9d, esi; char *
0x18000cca4  lea     r8, aOnecoreuapEndu_348; "onecoreuap\\enduser\\NUI\\OneCore\\sapi"...
0x18000ccab  mov     edx, 5Fh ; '_'; void *
0x18000ccb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccb5  jmp     loc_18000CB61
0x18000ccba  mov     [rsp+80h+lpdwDisposition], rsi; lpdwDisposition
0x18000ccbf  mov     [rsp+80h+var_48], rax; phkResult
0x18000ccc4  mov     [rsp+80h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000ccc9  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x18000ccd1  mov     dword ptr [rsp+80h+phkResult], 1; dwOptions
0x18000ccd9  xor     r9d, r9d; lpClass
0x18000ccdc  call    cs:__imp_RegCreateKeyExW
0x18000cce2  jmp     loc_18000CB4A
  ... truncated ...
```
