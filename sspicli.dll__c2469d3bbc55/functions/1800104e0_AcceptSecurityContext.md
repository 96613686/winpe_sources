# AcceptSecurityContext

- ea: `0x1800104e0`
- end: `0x1800108fe`
- name: `AcceptSecurityContext`
- size: `1054`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800199c0`

## callees

- `0x180001f90`
- `0x180003ee0`
- `0x1800104e0`
- `0x18001584c`
- `0x18001b088`
- `0x18001b0ec`
- `0x18001b14c`
- `0x18001b1d8`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180010763`
- `ntdll!RtlAcquireResourceExclusive` at `0x180010763`
- `ntdll!RtlReleaseResource` at `0x18001078d`
- `ntdll!RtlReleaseResource` at `0x1800107bd`
- `ntdll!RtlReleaseResource` at `0x18001078d`
- `ntdll!RtlReleaseResource` at `0x1800107bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180010632`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180010632`

## pseudocode

```c
SECURITY_STATUS __stdcall AcceptSecurityContext(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSecBufferDesc pInput,
        unsigned int fContextReq,
        unsigned int TargetDataRep,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  PCredHandle v11; // r14
  ULONG_PTR v12; // rbx
  struct _SecHandle *v13; // rsi
  struct _DLL_SECURITY_PACKAGE *v14; // rax
  ULONG_PTR dwUpper; // r9
  ULONG_PTR dwLower; // rax
  ULONG_PTR v18; // rdx
  ULONG_PTR v19; // r8
  __int64 v20; // rcx
  ULONG_PTR v21; // r8
  SECURITY_STATUS v22; // r14d
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  __int64 v26; // rsi
  __int64 v27; // rsi
  PVOID *v28; // rcx
  struct _DLL_SECURITY_PACKAGE *v29; // [rsp+50h] [rbp-61h] BYREF
  ULONG_PTR v30; // [rsp+58h] [rbp-59h] BYREF
  PTimeStamp v31; // [rsp+60h] [rbp-51h]
  unsigned int *v32; // [rsp+68h] [rbp-49h]
  __int128 v33; // [rsp+70h] [rbp-41h] BYREF
  struct _SecHandle v34; // [rsp+80h] [rbp-31h] BYREF
  struct _SecHandle v35; // [rsp+90h] [rbp-21h] BYREF

  v32 = pfContextAttr;
  v11 = phCredential;
  v31 = ptsExpiry;
  v30 = 0;
  *((_QWORD *)&v33 + 1) = 0;
  v35 = 0;
  v34 = 0;
  if ( __PAIR128__((unsigned __int64)phCredential, (unsigned __int64)phContext) == 0 )
    return -2146893055;
  v12 = 0;
  *(_QWORD *)&v33 = -1;
  v29 = 0;
  if ( phNewContext )
    *((_QWORD *)&v33 + 1) = phNewContext->dwUpper;
  if ( phContext )
  {
    v29 = SecpValidateHandle(1, phContext, &v34);
    v12 = (ULONG_PTR)v29;
    if ( !v29 )
      return -2146893055;
    v13 = &v34;
  }
  else
  {
    v13 = 0;
  }
  if ( v11 )
  {
    v14 = SecpValidateHandle(0, v11, &v35);
    if ( !v14 )
      return -2146893055;
    v11 = &v35;
    if ( !v12 )
      v12 = (ULONG_PTR)v14;
    v29 = (struct _DLL_SECURITY_PACKAGE *)v12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( v13 )
    {
      dwUpper = v13->dwUpper;
      dwLower = v13->dwLower;
    }
    else
    {
      LOBYTE(dwUpper) = 0;
      LOBYTE(dwLower) = 0;
    }
    if ( v11 )
    {
      v18 = v11->dwUpper;
      v19 = v11->dwLower;
    }
    else
    {
      LODWORD(v18) = 0;
      LODWORD(v19) = 0;
    }
    WPP_SF_SPPPP(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, *(_QWORD *)(v12 + 104), v18, v19, dwUpper, dwLower);
  }
  TlsSetValue(SecTlsPackage, (LPVOID)v12);
  v22 = (*(__int64 (__fastcall **)(PCredHandle, struct _SecHandle *, PSecBufferDesc, _QWORD, unsigned int, __int128 *, PSecBufferDesc, unsigned int *, PTimeStamp))(*(_QWORD *)(v12 + 176) + 56LL))(
          v11,
          v13,
          pInput,
          fContextReq,
          TargetDataRep,
          &v33,
          pOutput,
          v32,
          v31);
  if ( v22 < 0 )
  {
LABEL_31:
    if ( phNewContext )
    {
      if ( v12
        && (*(_BYTE *)(v12 + 16) & 2) != 0
        && (_QWORD)v33 != -1
        && (*(_BYTE *)(v12 + 36) & 1) != 0
        && *(_QWORD *)(v12 + 40) != (_QWORD)v33 )
      {
        v24 = SecLocatePackageById(v33, &v29);
        v21 = (ULONG_PTR)v29;
        if ( v24 >= 0 )
        {
          if ( (*((_BYTE *)v29 + 16) & 2) != 0 && (*((_BYTE *)v29 + 36) & 1) != 0 )
          {
            phNewContext->dwUpper = *((_QWORD *)&v33 + 1);
            phNewContext->dwLower = v21;
          }
        }
        else if ( v24 == -2146893055 )
        {
          *phNewContext = (struct _SecHandle)v33;
        }
        else
        {
          phNewContext->dwUpper = -1;
          phNewContext->dwLower = -1;
        }
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v22;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_65;
        WPP_SF_PPI(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          v21,
          phNewContext->dwUpper,
          phNewContext->dwLower,
          *(_QWORD *)(v21 + 24));
      }
LABEL_64:
      v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_65:
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 )
        WPP_SF_DPP(v28[2], 29, v21, (unsigned int)v22, phNewContext->dwUpper, phNewContext->dwLower);
      return v22;
    }
    return v22;
  }
  v21 = v33;
  if ( (_QWORD)v33 != -1 )
  {
    if ( (*(_BYTE *)(v12 + 16) & 2) != 0 )
      v23 = SecLocatePackageById(v33, &v30);
    else
      v23 = SecLocatePackageByOriginalLower(v20, v12, v33, &v30);
    if ( v23 >= 0 )
    {
      v12 = v30;
    }
    else if ( *(_QWORD *)(v12 + 40) )
    {
      v22 = v23;
      goto LABEL_31;
    }
    v25 = SecPackageListLockCount;
    while ( (*(_BYTE *)(v12 + 36) & 1) == 0 )
    {
      v26 = 0;
      if ( v25 )
      {
        do
        {
          RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * v26], 1u);
          v25 = SecPackageListLockCount;
          v26 = (unsigned int)(v26 + 1);
        }
        while ( (unsigned int)v26 < SecPackageListLockCount );
      }
      v27 = 0;
      if ( (*(_BYTE *)(v12 + 36) & 1) == 0 )
      {
        *(_QWORD *)(v12 + 40) = v33;
        *(_DWORD *)(v12 + 36) |= 1u;
        if ( v25 )
        {
          do
          {
            RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v27]);
            v27 = (unsigned int)(v27 + 1);
          }
          while ( (unsigned int)v27 < SecPackageListLockCount );
        }
        goto LABEL_51;
      }
      if ( v25 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v27]);
          v25 = SecPackageListLockCount;
          v27 = (unsigned int)(v27 + 1);
        }
        while ( (unsigned int)v27 < SecPackageListLockCount );
      }
    }
    v21 = v33;
    if ( *(_QWORD *)(v12 + 40) != (_QWORD)v33
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SPP(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids,
        *(_QWORD *)(v12 + 104),
        v33,
        *(_QWORD *)(v12 + 40));
    }
  }
LABEL_51:
  if ( phNewContext )
  {
    phNewContext->dwUpper = *((_QWORD *)&v33 + 1);
    phNewContext->dwLower = v12;
    goto LABEL_64;
  }
  return v22;
}

```

## disassembly

```asm
0x1800104e0  push    rbp
0x1800104e2  push    rbx
0x1800104e3  push    rsi
0x1800104e4  push    rdi
0x1800104e5  push    r12
0x1800104e7  push    r13
0x1800104e9  push    r14
0x1800104eb  push    r15
0x1800104ed  lea     rbp, [rsp-7]
0x1800104f2  sub     rsp, 0B8h
0x1800104f9  mov     rax, cs:__security_cookie
0x180010500  xor     rax, rsp
0x180010503  mov     [rbp+3Fh+var_50], rax
0x180010507  mov     rax, [rbp+3Fh+pfContextAttr]
0x18001050e  xorps   xmm0, xmm0
0x180010511  mov     rdi, [rbp+3Fh+phNewContext]
0x180010515  xorps   xmm1, xmm1
0x180010518  mov     r13, [rbp+3Fh+pOutput]
0x18001051c  mov     r12d, r9d
0x18001051f  mov     [rbp+3Fh+var_88], rax
0x180010523  mov     r15, r8
0x180010526  mov     rax, [rbp+3Fh+ptsExpiry]
0x18001052d  mov     r14, rcx
0x180010530  mov     [rbp+3Fh+var_90], rax
0x180010534  mov     [rbp+3Fh+var_98], 0
0x18001053c  mov     qword ptr [rbp+3Fh+var_80+8], 0
0x180010544  movups  xmmword ptr [rbp+3Fh+var_60.dwLower], xmm0
0x180010548  movups  xmmword ptr [rbp+3Fh+var_70.dwLower], xmm1
0x18001054c  test    rcx, rcx
0x18001054f  jnz     short loc_180010556
0x180010551  test    rdx, rdx
0x180010554  jz      short loc_1800105B0
0x180010556  xor     ebx, ebx
0x180010558  mov     qword ptr [rbp+3Fh+var_80], 0FFFFFFFFFFFFFFFFh
0x180010560  mov     [rbp+3Fh+var_A0], rbx
0x180010564  test    rdi, rdi
0x180010567  jz      short loc_180010571
0x180010569  mov     rax, [rdi+8]
0x18001056d  mov     qword ptr [rbp+3Fh+var_80+8], rax
0x180010571  test    rdx, rdx
0x180010574  jz      short loc_180010596
0x180010576  lea     r8, [rbp+3Fh+var_70]; struct _SecHandle *
0x18001057a  mov     ecx, 1; int
0x18001057f  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180010584  mov     [rbp+3Fh+var_A0], rax
0x180010588  mov     rbx, rax
0x18001058b  test    rax, rax
0x18001058e  jz      short loc_1800105B0
0x180010590  lea     rsi, [rbp+3Fh+var_70]
0x180010594  jmp     short loc_180010598
0x180010596  xor     esi, esi
0x180010598  test    r14, r14
0x18001059b  jz      short loc_1800105C9
0x18001059d  lea     r8, [rbp+3Fh+var_60]; struct _SecHandle *
0x1800105a1  mov     rdx, r14; struct _SecHandle *
0x1800105a4  xor     ecx, ecx; int
0x1800105a6  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x1800105ab  test    rax, rax
0x1800105ae  jnz     short loc_1800105BA
0x1800105b0  mov     eax, 80090301h
0x1800105b5  jmp     loc_1800108DE
0x1800105ba  test    rbx, rbx
0x1800105bd  lea     r14, [rbp+3Fh+var_60]
0x1800105c1  cmovz   rbx, rax
0x1800105c5  mov     [rbp+3Fh+var_A0], rbx
0x1800105c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105d0  lea     rax, WPP_GLOBAL_Control
0x1800105d7  cmp     rcx, rax
0x1800105da  jz      short loc_180010629
0x1800105dc  test    byte ptr [rcx+1Ch], 4
0x1800105e0  jz      short loc_180010629
0x1800105e2  test    rsi, rsi
0x1800105e5  jz      short loc_1800105F0
0x1800105e7  mov     r9, [rsi+8]
0x1800105eb  mov     rax, [rsi]
0x1800105ee  jmp     short loc_1800105F5
0x1800105f0  xor     r9d, r9d
0x1800105f3  xor     eax, eax
0x1800105f5  test    r14, r14
0x1800105f8  jz      short loc_180010603
0x1800105fa  mov     rdx, [r14+8]
0x1800105fe  mov     r8, [r14]
0x180010601  jmp     short loc_180010608
0x180010603  xor     edx, edx
0x180010605  xor     r8d, r8d
0x180010608  mov     rcx, [rcx+10h]
0x18001060c  mov     [rsp+0F0h+var_B8], rax
0x180010611  mov     [rsp+0F0h+var_C0], r9
0x180010616  mov     r9, [rbx+68h]
0x18001061a  mov     [rsp+0F0h+var_C8], r8
0x18001061f  mov     [rsp+0F0h+var_D0], rdx
0x180010624  call    WPP_SF_SPPPP
0x180010629  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001062f  mov     rdx, rbx; lpTlsValue
0x180010632  call    cs:__imp_TlsSetValue
0x180010638  mov     rcx, [rbp+3Fh+var_90]
0x18001063c  mov     r9d, r12d
0x18001063f  mov     rax, [rbx+0B0h]
0x180010646  mov     r8, r15
0x180010649  mov     r10d, [rbp+3Fh+TargetDataRep]
0x18001064d  mov     rdx, rsi
0x180010650  mov     [rsp+0F0h+var_B0], rcx
0x180010655  mov     rcx, [rbp+3Fh+var_88]
0x180010659  mov     rax, [rax+38h]
0x18001065d  mov     [rsp+0F0h+var_B8], rcx
0x180010662  lea     rcx, [rbp+3Fh+var_80]
0x180010666  mov     [rsp+0F0h+var_C0], r13
0x18001066b  mov     [rsp+0F0h+var_C8], rcx
0x180010670  mov     rcx, r14
0x180010673  mov     dword ptr [rsp+0F0h+var_D0], r10d
0x180010678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001067d  mov     r14d, eax
0x180010680  mov     sil, 2
0x180010683  test    eax, eax
0x180010685  js      short loc_1800106C3
0x180010687  mov     r8, qword ptr [rbp+3Fh+var_80]
0x18001068b  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001068f  jz      loc_1800107CE
0x180010695  test    [rbx+10h], sil
0x180010699  jz      short loc_1800106A9
0x18001069b  lea     rdx, [rbp+3Fh+var_98]
0x18001069f  mov     rcx, r8
0x1800106a2  call    SecLocatePackageById
0x1800106a7  jmp     short loc_1800106B5
0x1800106a9  lea     r9, [rbp+3Fh+var_98]
0x1800106ad  mov     rdx, rbx
0x1800106b0  call    SecLocatePackageByOriginalLower
0x1800106b5  test    eax, eax
0x1800106b7  jns     short loc_18001072E
0x1800106b9  cmp     qword ptr [rbx+28h], 0
0x1800106be  jz      short loc_180010732
0x1800106c0  mov     r14d, eax
0x1800106c3  test    rdi, rdi
0x1800106c6  jz      loc_1800108DB
0x1800106cc  test    rbx, rbx
0x1800106cf  jz      loc_1800108A0
0x1800106d5  test    [rbx+10h], sil
0x1800106d9  jz      loc_1800108A0
0x1800106df  mov     rcx, qword ptr [rbp+3Fh+var_80]
0x1800106e3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800106e7  jz      loc_1800108A0
0x1800106ed  test    byte ptr [rbx+24h], 1
0x1800106f1  jz      loc_1800108A0
0x1800106f7  cmp     [rbx+28h], rcx
0x1800106fb  jz      loc_1800108A0
0x180010701  lea     rdx, [rbp+3Fh+var_A0]
0x180010705  call    SecLocatePackageById
0x18001070a  mov     r8, [rbp+3Fh+var_A0]
0x18001070e  test    eax, eax
0x180010710  jns     loc_18001084A
0x180010716  cmp     eax, 80090301h
0x18001071b  jnz     loc_180010839
0x180010721  movups  xmm0, [rbp+3Fh+var_80]
0x180010725  movdqu  xmmword ptr [rdi], xmm0
0x180010729  jmp     loc_180010862
0x18001072e  mov     rbx, [rbp+3Fh+var_98]
0x180010732  mov     ecx, cs:SecPackageListLockCount
0x180010738  lea     r12, SecPackageListLock
0x18001073f  mov     r15d, 1
0x180010745  test    [rbx+24h], r15b
0x180010749  jnz     loc_1800107EE
0x18001074f  xor     esi, esi
0x180010751  test    ecx, ecx
0x180010753  jz      short loc_180010776
0x180010755  lea     rcx, [rsi+rsi*2]
0x180010759  mov     dl, r15b; Wait
0x18001075c  shl     rcx, 5
0x180010760  add     rcx, r12; Resource
0x180010763  call    cs:__imp_RtlAcquireResourceExclusive
0x180010769  mov     ecx, cs:SecPackageListLockCount
0x18001076f  add     esi, r15d
0x180010772  cmp     esi, ecx
0x180010774  jb      short loc_180010755
0x180010776  xor     esi, esi
0x180010778  test    [rbx+24h], r15b
0x18001077c  jz      short loc_1800107A2
0x18001077e  test    ecx, ecx
0x180010780  jz      short loc_180010745
0x180010782  lea     rcx, [rsi+rsi*2]
0x180010786  shl     rcx, 5
0x18001078a  add     rcx, r12; Resource
0x18001078d  call    cs:__imp_RtlReleaseResource
0x180010793  mov     ecx, cs:SecPackageListLockCount
0x180010799  add     esi, r15d
0x18001079c  cmp     esi, ecx
0x18001079e  jb      short loc_180010782
0x1800107a0  jmp     short loc_180010745
0x1800107a2  mov     rax, qword ptr [rbp+3Fh+var_80]
0x1800107a6  mov     [rbx+28h], rax
0x1800107aa  or      [rbx+24h], r15d
0x1800107ae  test    ecx, ecx
0x1800107b0  jz      short loc_1800107CE
0x1800107b2  lea     rcx, [rsi+rsi*2]
0x1800107b6  shl     rcx, 5
0x1800107ba  add     rcx, r12; Resource
0x1800107bd  call    cs:__imp_RtlReleaseResource
0x1800107c3  add     esi, r15d
0x1800107c6  cmp     esi, cs:SecPackageListLockCount
0x1800107cc  jb      short loc_1800107B2
0x1800107ce  lea     rsi, WPP_GLOBAL_Control
0x1800107d5  test    rdi, rdi
0x1800107d8  jz      loc_1800108DB
0x1800107de  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x1800107e2  mov     [rdi+8], rax
0x1800107e6  mov     [rdi], rbx
0x1800107e9  jmp     loc_1800108A7
0x1800107ee  mov     rax, [rbx+28h]
0x1800107f2  mov     r8, qword ptr [rbp+3Fh+var_80]
0x1800107f6  cmp     rax, r8
0x1800107f9  jz      short loc_1800107CE
0x1800107fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010802  lea     rsi, WPP_GLOBAL_Control
0x180010809  cmp     rcx, rsi
0x18001080c  jz      short loc_1800107D5
0x18001080e  test    [rcx+1Ch], r15b
0x180010812  jz      short loc_1800107D5
0x180010814  mov     r9, [rbx+68h]
0x180010818  mov     edx, 1Bh
0x18001081d  mov     rcx, [rcx+10h]
0x180010821  mov     [rsp+0F0h+var_C8], rax
0x180010826  mov     [rsp+0F0h+var_D0], r8
0x18001082b  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x180010832  call    WPP_SF_SPP
0x180010837  jmp     short loc_1800107D5
0x180010839  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180010841  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180010848  jmp     short loc_180010862
0x18001084a  test    [r8+10h], sil
0x18001084e  jz      short loc_180010862
0x180010850  test    byte ptr [r8+24h], 1
0x180010855  jz      short loc_180010862
0x180010857  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x18001085b  mov     [rdi+8], rax
0x18001085f  mov     [rdi], r8
0x180010862  mov     rcx, cs:WPP_GLOBAL_Control
0x180010869  lea     rsi, WPP_GLOBAL_Control
0x180010870  cmp     rcx, rsi
0x180010873  jz      short loc_1800108DB
0x180010875  test    byte ptr [rcx+1Ch], 1
0x180010879  jz      short loc_1800108AE
0x18001087b  mov     rax, [r8+18h]
0x18001087f  mov     edx, 1Ch
0x180010884  mov     r9, [rdi+8]
0x180010888  mov     rcx, [rcx+10h]
0x18001088c  mov     [rsp+0F0h+var_C8], rax
0x180010891  mov     rax, [rdi]
0x180010894  mov     [rsp+0F0h+var_D0], rax
0x180010899  call    WPP_SF_PPI
0x18001089e  jmp     short loc_1800108A7
0x1800108a0  lea     rsi, WPP_GLOBAL_Control
0x1800108a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108ae  cmp     rcx, rsi
0x1800108b1  jz      short loc_1800108DB
0x1800108b3  test    byte ptr [rcx+1Ch], 4
0x1800108b7  jz      short loc_1800108DB
0x1800108b9  mov     rax, [rdi]
0x1800108bc  mov     edx, 1Dh
0x1800108c1  mov     rcx, [rcx+10h]
0x1800108c5  mov     r9d, r14d
0x1800108c8  mov     [rsp+0F0h+var_C8], rax
0x1800108cd  mov     rax, [rdi+8]
0x1800108d1  mov     [rsp+0F0h+var_D0], rax
0x1800108d6  call    WPP_SF_DPP
0x1800108db  mov     eax, r14d
0x1800108de  mov     rcx, [rbp+3Fh+var_50]
0x1800108e2  xor     rcx, rsp; StackCookie
0x1800108e5  call    __security_check_cookie
0x1800108ea  add     rsp, 0B8h
0x1800108f1  pop     r15
0x1800108f3  pop     r14
0x1800108f5  pop     r13
0x1800108f7  pop     r12
0x1800108f9  pop     rdi
0x1800108fa  pop     rsi
0x1800108fb  pop     rbx
0x1800108fc  pop     rbp
0x1800108fd  retn
```
