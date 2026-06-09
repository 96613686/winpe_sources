# InitializeSecurityContextCommon(_SecHandle *,_SecHandle *,void *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)

- ea: `0x180003670`
- end: `0x180003c9e`
- name: `?InitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAXKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z`
- size: `1582`
- prototype: `__int64 __usercall@<rax>(struct _SecHandle *@<rcx>, struct _SecHandle *@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003570`
- `0x1800035f0`
- `0x180019eb0`
- `0x18001a060`

## callees

- `0x180001f90`
- `0x180003670`
- `0x180003ee0`
- `0x18001b048`
- `0x18001b0ec`
- `0x18001b14c`
- `0x18001b540`
- `0x18001b5e0`
- `0x18001d560`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180003b76`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003b76`
- `ntdll!RtlReleaseResource` at `0x18000394d`
- `ntdll!RtlReleaseResource` at `0x180003aa9`
- `ntdll!RtlReleaseResource` at `0x180003ba0`
- `ntdll!RtlReleaseResource` at `0x18000394d`
- `ntdll!RtlReleaseResource` at `0x180003aa9`
- `ntdll!RtlReleaseResource` at `0x180003ba0`
- `ntdll!RtlAcquireResourceShared` at `0x180003936`
- `ntdll!RtlAcquireResourceShared` at `0x180003936`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003764`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003764`

## pseudocode

```c
__int64 __fastcall InitializeSecurityContextCommon(
        struct _SecHandle *a1,
        struct _SecHandle *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        struct _SecBufferDesc *a7,
        unsigned int a8,
        struct _SecHandle *a9,
        struct _SecBufferDesc *a10,
        unsigned int *a11,
        union _LARGE_INTEGER *a12,
        unsigned __int8 a13)
{
  PRTL_RESOURCE v13; // r15
  struct _SecHandle *v14; // r12
  struct _SecHandle *v15; // rdi
  ULONG_PTR v16; // rbx
  int v17; // eax
  unsigned int v18; // edi
  ULONG_PTR v19; // r12
  int v20; // eax
  int v21; // ecx
  PVOID *v22; // rcx
  const char *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r13
  ULONG_PTR dwLower; // rcx
  int v28; // eax
  ULONG_PTR v29; // r8
  struct _DLL_SECURITY_PACKAGE *v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rbx
  const wchar_t *v33; // rax
  PVOID *v34; // r8
  struct _DLL_SECURITY_PACKAGE *v36; // [rsp+78h] [rbp-81h] BYREF
  PRTL_RESOURCE Resource; // [rsp+80h] [rbp-79h] BYREF
  union _LARGE_INTEGER *v38; // [rsp+88h] [rbp-71h]
  unsigned int *v39; // [rsp+90h] [rbp-69h]
  struct _SecBufferDesc *v40; // [rsp+98h] [rbp-61h]
  struct _SecBufferDesc *v41; // [rsp+A0h] [rbp-59h]
  void *v42; // [rsp+A8h] [rbp-51h]
  struct _SecHandle v43; // [rsp+B0h] [rbp-49h] BYREF
  struct _SecHandle v44; // [rsp+C0h] [rbp-39h] BYREF
  struct _SecHandle v45; // [rsp+D0h] [rbp-29h] BYREF

  v13 = 0;
  v41 = a7;
  v14 = a2;
  v15 = a1;
  v40 = a10;
  v39 = a11;
  v38 = a12;
  v42 = a3;
  Resource = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  if ( a13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v33 = (const wchar_t *)a3;
      if ( !a3 )
        v33 = L"<null>";
      WPP_SF_qqS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)L"<null>",
        (_DWORD)a3,
        (_DWORD)a1,
        (char)a2,
        (__int64)v33);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v24 = (const char *)a3;
    if ( !a3 )
      v24 = "<null>";
    WPP_SF_qqs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)"<null>",
      (_DWORD)a3,
      (_DWORD)a1,
      (char)a2,
      (__int64)v24);
  }
  if ( !v15 && !v14 )
    return 2148074241LL;
  v16 = 0;
  v43.dwLower = -1;
  v36 = 0;
  if ( a9 )
    v43.dwUpper = a9->dwUpper;
  if ( v14 )
  {
    v36 = SecpValidateHandle(1, v14, &v44);
    v16 = (ULONG_PTR)v36;
    if ( !v36 )
      return 2148074241LL;
    v14 = &v44;
  }
  if ( !v15 )
    goto LABEL_9;
  v30 = SecpValidateHandle(0, v15, &v45);
  if ( v30 )
  {
    v15 = &v45;
    if ( !v16 )
      v16 = (ULONG_PTR)v30;
    v36 = (struct _DLL_SECURITY_PACKAGE *)v16;
LABEL_9:
    TlsSetValue(SecTlsPackage, (LPVOID)v16);
    if ( a13 )
      v17 = (*(__int64 (__fastcall **)(struct _SecHandle *, struct _SecHandle *, void *, _QWORD, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *))(*(_QWORD *)(v16 + 168) + 48LL))(
              v15,
              v14,
              v42,
              a4,
              a5,
              a6,
              v41,
              a8,
              &v43,
              v40,
              v39,
              v38);
    else
      v17 = (*(__int64 (__fastcall **)(struct _SecHandle *, struct _SecHandle *, void *, _QWORD, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *))(*(_QWORD *)(v16 + 160) + 48LL))(
              v15,
              v14,
              v42,
              a4,
              a5,
              a6,
              v41,
              a8,
              &v43,
              v40,
              v39,
              v38);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( (*(_BYTE *)(v16 + 16) & 1) != 0 )
      {
        if ( !a9 )
          goto LABEL_23;
        dwLower = v43.dwLower;
        *a9 = v43;
        if ( dwLower == -1 || dwLower == *(_QWORD *)(v16 + 40) )
          a9->dwLower = v16;
        goto LABEL_38;
      }
    }
    else
    {
      v19 = v43.dwLower;
      if ( v43.dwLower == -1 )
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
        if ( !a9 )
          goto LABEL_24;
        a9->dwUpper = v43.dwUpper;
        a9->dwLower = v16;
        goto LABEL_23;
      }
      if ( (*(_BYTE *)(v16 + 16) & 2) != 0 )
      {
        v20 = SecLocatePackageById(v43.dwLower, &Resource);
        v13 = Resource;
      }
      else
      {
        Resource = (PRTL_RESOURCE)&SecPackageListLock[12
                                                    * ((unsigned int)(SecPackageListLockCount - 1)
                                                     & (unsigned __int64)NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
        RtlAcquireResourceShared(Resource, 1u);
        v26 = *(_QWORD *)(v16 + 64);
        if ( v26 )
        {
          v34 = (PVOID *)WPP_GLOBAL_Control;
          do
          {
            if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 4) != 0 )
            {
              WPP_SF_SP((unsigned int)v34[2], v25, (_DWORD)v34, *(_QWORD *)(v26 + 104), *(_QWORD *)(v26 + 40));
              v34 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( *(_QWORD *)(v26 + 40) == v19 )
            {
              v25 = *(_QWORD *)(v26 + 56);
              if ( *(_DWORD *)(v25 + 40) == *(_DWORD *)(*(_QWORD *)(v16 + 56) + 40LL) && (*(_BYTE *)(v26 + 16) & 2) == 0 )
                break;
            }
            v26 = *(_QWORD *)(v26 + 72);
          }
          while ( v26 );
        }
        RtlReleaseResource(Resource);
        if ( v26 )
        {
          v13 = (PRTL_RESOURCE)v26;
          v20 = 0;
        }
        else
        {
          v20 = -2146893051;
        }
      }
      if ( v20 >= 0 )
      {
LABEL_16:
        v21 = SecPackageListLockCount;
        while ( (v13->Lock.SpinCount & 0x100000000LL) == 0 )
        {
          v31 = 0;
          if ( v21 )
          {
            do
            {
              RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * v31], 1u);
              v21 = SecPackageListLockCount;
              v31 = (unsigned int)(v31 + 1);
            }
            while ( (unsigned int)v31 < SecPackageListLockCount );
          }
          v32 = 0;
          if ( (v13->Lock.SpinCount & 0x100000000LL) == 0 )
          {
            v13->SharedSemaphore = (HANDLE)v43.dwLower;
            HIDWORD(v13->Lock.SpinCount) |= 1u;
            if ( v21 )
            {
              do
              {
                RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v32]);
                v32 = (unsigned int)(v32 + 1);
              }
              while ( (unsigned int)v32 < SecPackageListLockCount );
            }
            goto LABEL_19;
          }
          if ( v21 )
          {
            do
            {
              RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v32]);
              v21 = SecPackageListLockCount;
              v32 = (unsigned int)(v32 + 1);
            }
            while ( (unsigned int)v32 < SecPackageListLockCount );
          }
        }
        if ( v13->SharedSemaphore == (HANDLE)v43.dwLower )
        {
LABEL_19:
          v22 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_20;
        }
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SPP(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids,
            *(_QWORD *)&v13[1].Lock.LockCount,
            v43.dwLower,
            (char)v13->SharedSemaphore);
          goto LABEL_19;
        }
LABEL_20:
        v16 = (ULONG_PTR)v13;
        goto LABEL_21;
      }
      if ( !*(_QWORD *)(v16 + 40) )
      {
        v13 = (PRTL_RESOURCE)v16;
        goto LABEL_16;
      }
      v18 = v20;
    }
    if ( !a9 )
      goto LABEL_23;
    dwLower = v43.dwLower;
LABEL_38:
    if ( v16
      && (*(_BYTE *)(v16 + 16) & 2) != 0
      && dwLower != -1
      && (*(_BYTE *)(v16 + 36) & 1) != 0
      && dwLower != *(_QWORD *)(v16 + 40) )
    {
      v28 = SecLocatePackageById(dwLower, &v36);
      v29 = (ULONG_PTR)v36;
      if ( v28 >= 0 )
      {
        if ( (*((_BYTE *)v36 + 16) & 2) != 0 && (*((_BYTE *)v36 + 36) & 1) != 0 )
        {
          a9->dwUpper = v43.dwUpper;
          a9->dwLower = v29;
        }
      }
      else if ( v28 == -2146893055 )
      {
        *a9 = v43;
      }
      else
      {
        a9->dwUpper = -1;
        a9->dwLower = -1;
      }
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v18;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_24:
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 4) != 0 )
          WPP_SF_D(v22[2], 25, &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids, v18);
        return v18;
      }
      WPP_SF_PPI(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v29, a9->dwUpper, a9->dwLower, *(_QWORD *)(v29 + 24));
    }
LABEL_23:
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_24;
  }
  return 2148074241LL;
}

```

## disassembly

```asm
0x180003670  push    rbp
0x180003672  push    rsi
0x180003673  push    rdi
0x180003674  push    r12
0x180003676  push    r13
0x180003678  push    r14
0x18000367a  push    r15
0x18000367c  lea     rbp, [rsp-7]
0x180003681  sub     rsp, 100h
0x180003688  mov     rax, cs:__security_cookie
0x18000368f  xor     rax, rsp
0x180003692  mov     [rbp+37h+var_50], rax
0x180003696  mov     rax, [rbp+37h+arg_30]
0x18000369a  xor     r15d, r15d
0x18000369d  movzx   r13d, [rbp+37h+arg_60]
0x1800036a5  xorps   xmm0, xmm0
0x1800036a8  mov     rsi, [rbp+37h+arg_40]
0x1800036af  xorps   xmm1, xmm1
0x1800036b2  mov     [rbp+37h+var_90], rax
0x1800036b6  mov     r12, rdx
0x1800036b9  mov     rax, [rbp+37h+arg_48]
0x1800036c0  mov     rdi, rcx
0x1800036c3  mov     [rbp+37h+var_98], rax
0x1800036c7  mov     rax, [rbp+37h+arg_50]
0x1800036ce  mov     [rbp+37h+var_A0], rax
0x1800036d2  mov     rax, [rbp+37h+arg_58]
0x1800036d9  mov     [rbp+37h+var_A8], rax
0x1800036dd  mov     [rsp+130h+var_C0], r9d
0x1800036e2  mov     [rbp+37h+var_88], r8
0x1800036e6  mov     [rbp+37h+Resource], r15
0x1800036ea  movups  xmmword ptr [rbp+37h+var_60.dwLower], xmm0
0x1800036ee  movups  xmmword ptr [rbp+37h+var_70.dwLower], xmm1
0x1800036f2  movups  [rbp+37h+var_80], xmm0
0x1800036f6  test    r13b, r13b
0x1800036f9  jz      loc_1800038BA
0x1800036ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180003706  lea     r14, WPP_GLOBAL_Control
0x18000370d  cmp     rcx, r14
0x180003710  jz      short loc_18000371C
0x180003712  test    byte ptr [rcx+1Ch], 4
0x180003716  jnz     loc_180003ABE
0x18000371c  mov     [rsp+130h+var_38], rbx
0x180003724  test    rdi, rdi
0x180003727  jz      loc_180003AEA
0x18000372d  xor     ebx, ebx
0x18000372f  mov     qword ptr [rbp+37h+var_80], 0FFFFFFFFFFFFFFFFh
0x180003737  mov     [rsp+130h+var_B8], rbx
0x18000373c  test    rsi, rsi
0x18000373f  jz      short loc_180003749
0x180003741  mov     rax, [rsi+8]
0x180003745  mov     qword ptr [rbp+37h+var_80+8], rax
0x180003749  test    r12, r12
0x18000374c  jnz     loc_180003A41
0x180003752  test    rdi, rdi
0x180003755  jnz     loc_180003A19
0x18000375b  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180003761  mov     rdx, rbx; lpTlsValue
0x180003764  call    cs:__imp_TlsSetValue
0x18000376a  mov     rcx, [rbp+37h+var_A8]
0x18000376e  mov     rdx, r12
0x180003771  mov     r9d, [rsp+130h+var_C0]
0x180003776  mov     r8, [rbp+37h+var_88]
0x18000377a  mov     [rsp+130h+var_D8], rcx
0x18000377f  mov     rcx, [rbp+37h+var_A0]
0x180003783  mov     [rsp+130h+var_E0], rcx
0x180003788  mov     rcx, [rbp+37h+var_98]
0x18000378c  mov     [rsp+130h+var_E8], rcx
0x180003791  lea     rcx, [rbp+37h+var_80]
0x180003795  mov     [rsp+130h+var_F0], rcx
0x18000379a  test    r13b, r13b
0x18000379d  jz      loc_180003890
0x1800037a3  mov     r10d, [rbp+37h+arg_38]
0x1800037a7  mov     rcx, [rbp+37h+var_90]
0x1800037ab  mov     rax, [rbx+0A8h]
0x1800037b2  mov     [rsp+130h+var_F8], r10d
0x1800037b7  mov     r10d, [rbp+37h+arg_28]
0x1800037bb  mov     [rsp+130h+var_100], rcx
0x1800037c0  mov     dword ptr [rsp+130h+var_108], r10d
0x1800037c5  mov     r10d, [rbp+37h+arg_20]
0x1800037c9  mov     dword ptr [rsp+130h+var_110], r10d
0x1800037ce  mov     rax, [rax+30h]
0x1800037d2  mov     rcx, rdi
0x1800037d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037da  mov     edi, eax
0x1800037dc  test    eax, eax
0x1800037de  js      loc_18000396D
0x1800037e4  mov     r12, qword ptr [rbp+37h+var_80]
0x1800037e8  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1800037ec  jz      loc_180003BF9
0x1800037f2  test    byte ptr [rbx+10h], 2
0x1800037f6  lea     r13, SecPackageListLock
0x1800037fd  jz      loc_180003907
0x180003803  lea     rdx, [rbp+37h+Resource]
0x180003807  mov     rcx, r12
0x18000380a  call    SecLocatePackageById
0x18000380f  mov     r15, [rbp+37h+Resource]
0x180003813  test    eax, eax
0x180003815  js      loc_1800039E3
0x18000381b  mov     ecx, cs:SecPackageListLockCount
0x180003821  test    byte ptr [r15+24h], 1
0x180003826  jz      loc_180003A72
0x18000382c  mov     rax, [r15+28h]
0x180003830  mov     r8, qword ptr [rbp+37h+var_80]
0x180003834  cmp     rax, r8
0x180003837  jnz     loc_180003BB7
0x18000383d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003844  mov     rbx, r15
0x180003847  test    rsi, rsi
0x18000384a  jz      short loc_18000385E
0x18000384c  mov     rax, qword ptr [rbp+37h+var_80+8]
0x180003850  mov     [rsi+8], rax
0x180003854  mov     [rsi], rbx
0x180003857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000385e  cmp     rcx, r14
0x180003861  jnz     loc_1800039F2
0x180003867  mov     eax, edi
0x180003869  mov     rbx, [rsp+130h+var_38]
0x180003871  mov     rcx, [rbp+37h+var_50]
0x180003875  xor     rcx, rsp; StackCookie
0x180003878  call    __security_check_cookie
0x18000387d  add     rsp, 100h
0x180003884  pop     r15
0x180003886  pop     r14
0x180003888  pop     r13
0x18000388a  pop     r12
0x18000388c  pop     rdi
0x18000388d  pop     rsi
0x18000388e  pop     rbp
0x18000388f  retn
0x180003890  mov     ecx, [rbp+37h+arg_38]
0x180003893  mov     rax, [rbx+0A0h]
0x18000389a  mov     [rsp+130h+var_F8], ecx
0x18000389e  mov     rcx, [rbp+37h+var_90]
0x1800038a2  mov     [rsp+130h+var_100], rcx
0x1800038a7  mov     ecx, [rbp+37h+arg_28]
0x1800038aa  mov     dword ptr [rsp+130h+var_108], ecx
0x1800038ae  mov     ecx, [rbp+37h+arg_20]
0x1800038b1  mov     dword ptr [rsp+130h+var_110], ecx
0x1800038b5  jmp     loc_1800037CE
0x1800038ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038c1  lea     r14, WPP_GLOBAL_Control
0x1800038c8  cmp     rcx, r14
0x1800038cb  jz      loc_18000371C
0x1800038d1  test    byte ptr [rcx+1Ch], 4
0x1800038d5  jz      loc_18000371C
0x1800038db  mov     rcx, [rcx+10h]
0x1800038df  lea     rdx, aNull_0; "<null>"
0x1800038e6  test    r8, r8
0x1800038e9  mov     rax, r8
0x1800038ec  mov     r9, rdi
0x1800038ef  cmovz   rax, rdx
0x1800038f3  mov     [rsp+130h+var_108], rax
0x1800038f8  mov     [rsp+130h+var_110], r12
0x1800038fd  call    WPP_SF_qqs
0x180003902  jmp     loc_18000371C
0x180003907  mov     rax, gs:30h
0x180003910  mov     ecx, cs:SecPackageListLockCount
0x180003916  dec     ecx
0x180003918  movzx   edx, byte ptr [rax+1747h]
0x18000391f  and     rdx, rcx
0x180003922  lea     rax, [rdx+rdx*2]
0x180003926  mov     dl, 1; Wait
0x180003928  shl     rax, 5
0x18000392c  add     rax, r13
0x18000392f  mov     rcx, rax; Resource
0x180003932  mov     [rbp+37h+Resource], rax
0x180003936  call    cs:__imp_RtlAcquireResourceShared
0x18000393c  mov     r13, [rbx+40h]
0x180003940  test    r13, r13
0x180003943  jnz     loc_180003AF8
0x180003949  mov     rcx, [rbp+37h+Resource]; Resource
0x18000394d  call    cs:__imp_RtlReleaseResource
0x180003953  test    r13, r13
0x180003956  jz      loc_180003B57
0x18000395c  mov     r15, r13
0x18000395f  xor     eax, eax
0x180003961  lea     r13, SecPackageListLock
0x180003968  jmp     loc_180003813
0x18000396d  test    byte ptr [rbx+10h], 1
0x180003971  jnz     loc_180003C05
0x180003977  test    rsi, rsi
0x18000397a  jz      loc_180003857
0x180003980  mov     rcx, qword ptr [rbp+37h+var_80]
0x180003984  test    rbx, rbx
0x180003987  jz      loc_180003857
0x18000398d  test    byte ptr [rbx+10h], 2
0x180003991  jz      loc_180003857
0x180003997  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000399b  jz      loc_180003857
0x1800039a1  test    byte ptr [rbx+24h], 1
0x1800039a5  jz      loc_180003857
0x1800039ab  cmp     rcx, [rbx+28h]
0x1800039af  jz      loc_180003857
0x1800039b5  lea     rdx, [rsp+130h+var_B8]
0x1800039ba  call    SecLocatePackageById
0x1800039bf  mov     r8, [rsp+130h+var_B8]
0x1800039c4  test    eax, eax
0x1800039c6  jns     loc_180003C43
0x1800039cc  cmp     eax, 80090301h
0x1800039d1  jnz     loc_180003C32
0x1800039d7  movups  xmm0, [rbp+37h+var_80]
0x1800039db  movups  xmmword ptr [rsi], xmm0
0x1800039de  jmp     loc_180003C5C
0x1800039e3  cmp     qword ptr [rbx+28h], 0
0x1800039e8  jz      loc_180003B61
0x1800039ee  mov     edi, eax
0x1800039f0  jmp     short loc_180003977
0x1800039f2  test    byte ptr [rcx+1Ch], 4
0x1800039f6  jz      loc_180003867
0x1800039fc  mov     rcx, [rcx+10h]
0x180003a00  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x180003a07  mov     edx, 19h
0x180003a0c  mov     r9d, edi
0x180003a0f  call    WPP_SF_D
0x180003a14  jmp     loc_180003867
0x180003a19  lea     r8, [rbp+37h+var_60]; struct _SecHandle *
0x180003a1d  mov     rdx, rdi; struct _SecHandle *
0x180003a20  xor     ecx, ecx; int
0x180003a22  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180003a27  test    rax, rax
0x180003a2a  jz      short loc_180003A68
0x180003a2c  test    rbx, rbx
0x180003a2f  lea     rdi, [rbp+37h+var_60]
0x180003a33  cmovz   rbx, rax
0x180003a37  mov     [rsp+130h+var_B8], rbx
0x180003a3c  jmp     loc_18000375B
0x180003a41  lea     r8, [rbp+37h+var_70]; struct _SecHandle *
0x180003a45  mov     rdx, r12; struct _SecHandle *
0x180003a48  mov     ecx, 1; int
0x180003a4d  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180003a52  mov     [rsp+130h+var_B8], rax
0x180003a57  mov     rbx, rax
0x180003a5a  test    rax, rax
0x180003a5d  jz      short loc_180003A68
0x180003a5f  lea     r12, [rbp+37h+var_70]
0x180003a63  jmp     loc_180003752
0x180003a68  mov     eax, 80090301h
0x180003a6d  jmp     loc_180003869
0x180003a72  xor     ebx, ebx
0x180003a74  test    ecx, ecx
0x180003a76  jnz     loc_180003B69
0x180003a7c  xor     ebx, ebx
0x180003a7e  test    byte ptr [r15+24h], 1
0x180003a83  jnz     loc_180003B8D
0x180003a89  mov     rax, qword ptr [rbp+37h+var_80]
0x180003a8d  mov     [r15+28h], rax
0x180003a91  or      dword ptr [r15+24h], 1
0x180003a96  test    ecx, ecx
0x180003a98  jz      loc_18000383D
0x180003a9e  lea     rcx, [rbx+rbx*2]
0x180003aa2  shl     rcx, 5
0x180003aa6  add     rcx, r13; Resource
0x180003aa9  call    cs:__imp_RtlReleaseResource
0x180003aaf  inc     ebx
0x180003ab1  cmp     ebx, cs:SecPackageListLockCount
0x180003ab7  jb      short loc_180003A9E
0x180003ab9  jmp     loc_18000383D
0x180003abe  mov     rcx, [rcx+10h]
0x180003ac2  lea     rdx, aNull; "<null>"
0x180003ac9  test    r8, r8
0x180003acc  mov     rax, r8
0x180003acf  mov     r9, rdi
0x180003ad2  cmovz   rax, rdx
0x180003ad6  mov     [rsp+130h+var_108], rax
0x180003adb  mov     [rsp+130h+var_110], r12
0x180003ae0  call    WPP_SF_qqS
0x180003ae5  jmp     loc_18000371C
0x180003aea  test    r12, r12
0x180003aed  jz      loc_180003A68
0x180003af3  jmp     loc_18000372D
0x180003af8  mov     r8, cs:WPP_GLOBAL_Control
0x180003aff  cmp     r8, r14
0x180003b02  jz      short loc_180003B28
0x180003b04  test    byte ptr [r8+1Ch], 4
0x180003b09  jz      short loc_180003B28
0x180003b0b  mov     rax, [r13+28h]
0x180003b0f  mov     r9, [r13+68h]
0x180003b13  mov     rcx, [r8+10h]
0x180003b17  mov     [rsp+130h+var_110], rax
0x180003b1c  call    WPP_SF_SP
0x180003b21  mov     r8, cs:WPP_GLOBAL_Control
0x180003b28  cmp     [r13+28h], r12
0x180003b2c  jnz     short loc_180003B49
0x180003b2e  mov     rax, [rbx+38h]
0x180003b32  mov     rdx, [r13+38h]
0x180003b36  mov     ecx, [rax+28h]
0x180003b39  cmp     [rdx+28h], ecx
0x180003b3c  jnz     short loc_180003B49
0x180003b3e  test    byte ptr [r13+10h], 2
0x180003b43  jz      loc_180003949
0x180003b49  mov     r13, [r13+48h]
0x180003b4d  test    r13, r13
0x180003b50  jnz     short loc_180003AFF
0x180003b52  jmp     loc_180003949
0x180003b57  mov     eax, 80090305h
0x180003b5c  jmp     loc_180003961
0x180003b61  mov     r15, rbx
0x180003b64  jmp     loc_18000381B
0x180003b69  lea     rcx, [rbx+rbx*2]
0x180003b6d  mov     dl, 1; Wait
  ... truncated ...
```
