# LsaAcceptSecurityContext(_SecHandle *,_SecHandle *,_SecBufferDesc *,ulong,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *)

- ea: `0x18001b700`
- end: `0x18001bb0e`
- name: `?LsaAcceptSecurityContext@@YAJPEAU_SecHandle@@0PEAU_SecBufferDesc@@KK01PEAKPEAT_LARGE_INTEGER@@@Z`
- size: `1038`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecHandle *, struct _SecBufferDesc *, unsigned int, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800011f0`
- `0x180002740`
- `0x180002780`
- `0x180003ee0`
- `0x180005370`
- `0x180005cc0`
- `0x18000c4f0`
- `0x18001b700`
- `0x18001c8e4`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001bad2`
- `ntdll!RtlNtStatusToDosError` at `0x18001bad2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bada`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001baa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001baa4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b88f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b88f`

## pseudocode

```c
__int64 __fastcall LsaAcceptSecurityContext(
        struct _SecHandle *a1,
        struct _SecHandle *a2,
        struct _SecBufferDesc *a3,
        int a4,
        unsigned int a5,
        struct _SecHandle *a6,
        struct _SecBufferDesc *a7,
        unsigned int *a8,
        union _LARGE_INTEGER *a9)
{
  struct _SecBufferDesc *v9; // rbx
  NTSTATUS v14; // edi
  ULONG_PTR dwLower; // rax
  int v16; // r12d
  unsigned int i; // edx
  PSecBuffer pBuffers; // rax
  bool v19; // zf
  unsigned int *v20; // rdi
  LPVOID Value; // rax
  NTSTATUS v22; // eax
  __int64 v23; // rdx
  ULONG_PTR v24; // rcx
  ULONG_PTR dwUpper; // rax
  struct _SecHandle *v26; // r14
  int v27; // eax
  __int64 v28; // r8
  __int64 *v29; // r15
  unsigned int j; // esi
  PSecBuffer v31; // r9
  unsigned int k; // r14d
  PSecBuffer v33; // rcx
  void *pvBuffer; // rcx
  ULONG v35; // eax
  bool v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v39; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v40; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h]
  __int128 v44; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v45[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v46; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v47; // [rsp+E0h] [rbp-20h] BYREF
  struct _SecHandle v48; // [rsp+F0h] [rbp-10h] BYREF

  v9 = a7;
  v41 = a8;
  v40 = (__int64 *)a9;
  v42 = 0;
  v43 = 0;
  v37 = 0;
  v44 = 0;
  v45[0] = 0;
  v45[1] = 0;
  v38 = 0;
  v47 = 0;
  v39 = 0;
  v46 = 0;
  v48.dwUpper = -1;
  v48.dwLower = -1;
  if ( !(unsigned int)SecpReserveVMSpots(19, &v39) )
  {
    v14 = -2146893056;
    goto LABEL_63;
  }
  if ( !a1 && !a2 )
  {
    v14 = -2146893055;
    goto LABEL_63;
  }
  if ( (a4 & 0x100000) != 0 )
  {
    v14 = -2146893054;
    goto LABEL_63;
  }
  if ( !a3 )
  {
    a3 = (struct _SecBufferDesc *)&v44;
    v44 = 0;
  }
  if ( !a7 )
  {
    v9 = (struct _SecBufferDesc *)&v44;
    v44 = 0;
  }
  if ( a2 )
  {
    *((_QWORD *)&v46 + 1) = a2->dwUpper;
    dwLower = a2->dwLower;
    *(_QWORD *)&v46 = a2->dwLower;
  }
  else
  {
    dwLower = v46;
    a2 = (struct _SecHandle *)v45;
  }
  if ( a1 )
  {
    *((_QWORD *)&v47 + 1) = a1->dwUpper;
    dwLower = a1->dwLower;
  }
  *(_QWORD *)&v47 = dwLower;
  v16 = a4 & 0x100;
  if ( (a4 & 0x100) != 0 )
  {
    if ( v9 )
    {
      for ( i = 0; i < v9->cBuffers; ++i )
      {
        pBuffers = v9->pBuffers;
        if ( pBuffers[i].BufferType == 2 )
        {
          pBuffers[i].pvBuffer = 0;
          v9->pBuffers[i].cbBuffer = 0;
        }
      }
    }
  }
  v19 = (DllState & 0x20000000) == 0;
  v20 = v41;
  v38 = 0;
  *v41 = 0;
  if ( v19 )
    Value = TlsGetValue(SecTlsIP);
  else
    Value = 0;
  v22 = SspipProcessSecurityContext(
          &v47,
          &v46,
          0,
          a3,
          a4,
          a5,
          &v48,
          (__int64)v9,
          v20,
          v40,
          &v37,
          (__int64)&v42,
          &v38,
          (__int64)Value,
          0);
  v24 = v48.dwLower;
  v14 = v22;
  dwUpper = v48.dwUpper;
  *a6 = v48;
  if ( v14 >= 0 && v37 )
  {
    v40 = 0;
    if ( a2 == (struct _SecHandle *)v45 || (v26 = a2, (v38 & 0x20) != 0) )
      v26 = a6;
    v26->dwUpper = dwUpper;
    v26->dwLower = v24;
    v27 = SecLocatePackageById(v24, &v40);
    v29 = v40;
    if ( v27 < 0 )
      goto LABEL_36;
    if ( !v40[23] )
    {
LABEL_35:
      v14 = -2146893055;
LABEL_37:
      if ( a2 == (struct _SecHandle *)v45 || (v38 & 0x20) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_PPD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v28, v26->dwUpper, v26->dwLower, v14);
        LsaDeleteSecurityContext(a6);
        a6->dwUpper = -2;
      }
      else
      {
        v26->dwLower = (ULONG_PTR)v29;
      }
      goto LABEL_44;
    }
    LOBYTE(v23) = 1;
    SecpAddVMEx(v43, v23, &v39);
    v27 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64 *))(v29[23] + 8))(v26->dwUpper, &v42);
    if ( v27 < 0 )
    {
LABEL_36:
      v14 = v27;
      goto LABEL_37;
    }
    if ( !v29[23] )
      goto LABEL_35;
  }
LABEL_44:
  if ( (v14 & 0xC0000000) != 0xC0000000 && (*v41 & 0x100) != 0 && v9 )
  {
    for ( j = 0; j < v9->cBuffers; ++j )
    {
      v31 = v9->pBuffers;
      if ( v31[j].BufferType - 2 <= 1 && v31[j].cbBuffer )
      {
        LOBYTE(v23) = 1;
        SecpAddVMEx(v31[j].pvBuffer, v23, &v39);
      }
    }
  }
  else if ( v16 )
  {
    if ( v9 )
    {
      for ( k = 0; k < v9->cBuffers; ++k )
      {
        v33 = v9->pBuffers;
        if ( v33[k].BufferType - 2 <= 1 )
        {
          pvBuffer = v33[k].pvBuffer;
          if ( pvBuffer )
          {
            if ( SecpLsaInprocDispatch )
              (*(void (**)(void))SecpLsaInprocDispatch)();
            else
              LocalFree(pvBuffer);
            v9->pBuffers[k].cbBuffer = 0;
            v9->pBuffers[k].pvBuffer = 0;
          }
        }
      }
    }
  }
LABEL_63:
  SecpReleaseVMSpots(v39);
  if ( v14 < 0 )
  {
    v35 = RtlNtStatusToDosError(v14);
    SetLastError(v35);
  }
  return SspNtStatusToSecStatus((unsigned int)v14);
}

```

## disassembly

```asm
0x18001b700  mov     [rsp-8+arg_0], rbx
0x18001b705  push    rbp
0x18001b706  push    rsi
0x18001b707  push    rdi
0x18001b708  push    r12
0x18001b70a  push    r13
0x18001b70c  push    r14
0x18001b70e  push    r15
0x18001b710  lea     rbp, [rsp-10h]
0x18001b715  sub     rsp, 110h
0x18001b71c  mov     rax, cs:__security_cookie
0x18001b723  xor     rax, rsp
0x18001b726  mov     [rbp+40h+var_40], rax
0x18001b72a  mov     rax, [rbp+40h+arg_38]
0x18001b731  xor     r12d, r12d
0x18001b734  mov     r13, [rbp+40h+arg_28]
0x18001b738  xorps   xmm0, xmm0
0x18001b73b  mov     rbx, [rbp+40h+arg_30]
0x18001b742  mov     rsi, rdx
0x18001b745  mov     [rbp+40h+var_A8], rax
0x18001b749  lea     rdx, [rbp+40h+var_B8]
0x18001b74d  mov     rax, [rbp+40h+arg_40]
0x18001b754  mov     rdi, rcx
0x18001b757  mov     [rbp+40h+var_B0], rax
0x18001b75b  xorps   xmm1, xmm1
0x18001b75e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b762  mov     [rbp+40h+var_A0], r12
0x18001b766  mov     r15d, r9d
0x18001b769  mov     [rbp+40h+var_98], r12
0x18001b76d  mov     r14, r8
0x18001b770  mov     [rbp+40h+var_C0], r12b
0x18001b774  movups  [rbp+40h+var_90], xmm0
0x18001b778  lea     ecx, [rax+14h]
0x18001b77b  mov     [rbp+40h+var_80], r12
0x18001b77f  mov     [rbp+40h+var_78], r12
0x18001b783  mov     [rbp+40h+var_BC], r12d
0x18001b787  movups  [rbp+40h+var_60], xmm0
0x18001b78b  mov     [rbp+40h+var_B8], r12d
0x18001b78f  movups  [rbp+40h+var_70], xmm1
0x18001b793  mov     [rbp+40h+var_48], rax
0x18001b797  mov     [rbp+40h+var_50], rax
0x18001b79b  call    SecpReserveVMSpots
0x18001b7a0  test    eax, eax
0x18001b7a2  jnz     short loc_18001B7AE
0x18001b7a4  mov     edi, 80090300h
0x18001b7a9  jmp     loc_18001BAC4
0x18001b7ae  test    rdi, rdi
0x18001b7b1  jnz     short loc_18001B7C2
0x18001b7b3  test    rsi, rsi
0x18001b7b6  jnz     short loc_18001B7C2
0x18001b7b8  mov     edi, 80090301h
0x18001b7bd  jmp     loc_18001BAC4
0x18001b7c2  bt      r15d, 14h
0x18001b7c7  jnb     short loc_18001B7D3
0x18001b7c9  mov     edi, 80090302h
0x18001b7ce  jmp     loc_18001BAC4
0x18001b7d3  test    r14, r14
0x18001b7d6  jnz     short loc_18001B7E3
0x18001b7d8  xorps   xmm0, xmm0
0x18001b7db  lea     r14, [rbp+40h+var_90]
0x18001b7df  movups  [rbp+40h+var_90], xmm0
0x18001b7e3  test    rbx, rbx
0x18001b7e6  jnz     short loc_18001B7F3
0x18001b7e8  xorps   xmm0, xmm0
0x18001b7eb  lea     rbx, [rbp+40h+var_90]
0x18001b7ef  movups  [rbp+40h+var_90], xmm0
0x18001b7f3  test    rsi, rsi
0x18001b7f6  jnz     short loc_18001B802
0x18001b7f8  mov     rax, qword ptr [rbp+40h+var_70]
0x18001b7fc  lea     rsi, [rbp+40h+var_80]
0x18001b800  jmp     short loc_18001B811
0x18001b802  mov     rax, [rsi+8]
0x18001b806  mov     qword ptr [rbp+40h+var_70+8], rax
0x18001b80a  mov     rax, [rsi]
0x18001b80d  mov     qword ptr [rbp+40h+var_70], rax
0x18001b811  test    rdi, rdi
0x18001b814  jz      short loc_18001B821
0x18001b816  mov     rax, [rdi+8]
0x18001b81a  mov     qword ptr [rbp+40h+var_60+8], rax
0x18001b81e  mov     rax, [rdi]
0x18001b821  mov     r12d, r15d
0x18001b824  mov     qword ptr [rbp+40h+var_60], rax
0x18001b828  and     r12d, 100h
0x18001b82f  jz      short loc_18001B868
0x18001b831  test    rbx, rbx
0x18001b834  jz      short loc_18001B868
0x18001b836  xor     edx, edx
0x18001b838  cmp     [rbx+4], edx
0x18001b83b  jbe     short loc_18001B868
0x18001b83d  mov     rax, [rbx+8]
0x18001b841  mov     ecx, edx
0x18001b843  add     rcx, rcx
0x18001b846  cmp     dword ptr [rax+rcx*8+4], 2
0x18001b84b  jnz     short loc_18001B861
0x18001b84d  mov     qword ptr [rax+rcx*8+8], 0
0x18001b856  mov     rax, [rbx+8]
0x18001b85a  mov     dword ptr [rax+rcx*8], 0
0x18001b861  inc     edx
0x18001b863  cmp     edx, [rbx+4]
0x18001b866  jb      short loc_18001B83D
0x18001b868  test    cs:DllState, 20000000h
0x18001b872  mov     rdi, [rbp+40h+var_A8]
0x18001b876  mov     [rbp+40h+var_BC], 0
0x18001b87d  mov     dword ptr [rdi], 0
0x18001b883  jz      short loc_18001B889
0x18001b885  xor     eax, eax
0x18001b887  jmp     short loc_18001B895
0x18001b889  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x18001b88f  call    cs:__imp_TlsGetValue
0x18001b895  mov     [rsp+140h+var_D0], 0
0x18001b89e  lea     rdx, [rbp+40h+var_70]
0x18001b8a2  mov     [rsp+140h+var_D8], rax
0x18001b8a7  lea     rcx, [rbp+40h+var_60]
0x18001b8ab  lea     rax, [rbp+40h+var_BC]
0x18001b8af  mov     r9, r14
0x18001b8b2  mov     [rsp+140h+var_E0], rax
0x18001b8b7  xor     r8d, r8d
0x18001b8ba  lea     rax, [rbp+40h+var_A0]
0x18001b8be  mov     [rsp+140h+var_E8], rax
0x18001b8c3  lea     rax, [rbp+40h+var_C0]
0x18001b8c7  mov     [rsp+140h+var_F0], rax
0x18001b8cc  mov     rax, [rbp+40h+var_B0]
0x18001b8d0  mov     [rsp+140h+var_F8], rax
0x18001b8d5  lea     rax, [rbp+40h+var_50]
0x18001b8d9  mov     [rsp+140h+var_100], rdi
0x18001b8de  mov     [rsp+140h+var_108], rbx
0x18001b8e3  mov     [rsp+140h+var_110], rax
0x18001b8e8  mov     eax, [rbp+40h+arg_20]
0x18001b8eb  mov     [rsp+140h+var_118], eax
0x18001b8ef  mov     dword ptr [rsp+140h+var_120], r15d
0x18001b8f4  call    SspipProcessSecurityContext
0x18001b8f9  mov     rcx, [rbp+40h+var_50]
0x18001b8fd  mov     edi, eax
0x18001b8ff  mov     rax, [rbp+40h+var_48]
0x18001b903  mov     [r13+8], rax
0x18001b907  mov     [r13+0], rcx
0x18001b90b  test    edi, edi
0x18001b90d  js      loc_18001B9F5
0x18001b913  cmp     [rbp+40h+var_C0], 0
0x18001b917  jz      loc_18001B9F5
0x18001b91d  lea     rdx, [rbp+40h+var_80]
0x18001b921  mov     [rbp+40h+var_B0], 0
0x18001b929  cmp     rsi, rdx
0x18001b92c  jz      short loc_18001B937
0x18001b92e  test    byte ptr [rbp+40h+var_BC], 20h
0x18001b932  mov     r14, rsi
0x18001b935  jz      short loc_18001B93A
0x18001b937  mov     r14, r13
0x18001b93a  lea     rdx, [rbp+40h+var_B0]
0x18001b93e  mov     [r14+8], rax
0x18001b942  mov     [r14], rcx
0x18001b945  call    SecLocatePackageById
0x18001b94a  mov     r15, [rbp+40h+var_B0]
0x18001b94e  test    eax, eax
0x18001b950  js      short loc_18001B998
0x18001b952  cmp     qword ptr [r15+0B8h], 0
0x18001b95a  jz      short loc_18001B991
0x18001b95c  mov     rcx, [rbp+40h+var_98]
0x18001b960  lea     r8, [rbp+40h+var_B8]
0x18001b964  mov     dl, 1
0x18001b966  call    SecpAddVMEx
0x18001b96b  mov     rax, [r15+0B8h]
0x18001b972  lea     rdx, [rbp+40h+var_A0]
0x18001b976  mov     rcx, [r14+8]
0x18001b97a  mov     rax, [rax+8]
0x18001b97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b983  test    eax, eax
0x18001b985  js      short loc_18001B998
0x18001b987  cmp     qword ptr [r15+0B8h], 0
0x18001b98f  jnz     short loc_18001B9F5
0x18001b991  mov     edi, 80090301h
0x18001b996  jmp     short loc_18001B99A
0x18001b998  mov     edi, eax
0x18001b99a  lea     rax, [rbp+40h+var_80]
0x18001b99e  cmp     rsi, rax
0x18001b9a1  jz      short loc_18001B9AE
0x18001b9a3  test    byte ptr [rbp+40h+var_BC], 20h
0x18001b9a7  jnz     short loc_18001B9AE
0x18001b9a9  mov     [r14], r15
0x18001b9ac  jmp     short loc_18001B9F5
0x18001b9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9b5  lea     rax, WPP_GLOBAL_Control
0x18001b9bc  cmp     rcx, rax
0x18001b9bf  jz      short loc_18001B9E5
0x18001b9c1  test    byte ptr [rcx+1Ch], 1
0x18001b9c5  jz      short loc_18001B9E5
0x18001b9c7  mov     rax, [r14]
0x18001b9ca  mov     edx, 0Dh
0x18001b9cf  mov     r9, [r14+8]
0x18001b9d3  mov     rcx, [rcx+10h]
0x18001b9d7  mov     [rsp+140h+var_118], edi
0x18001b9db  mov     [rsp+140h+var_120], rax
0x18001b9e0  call    WPP_SF_PPD
0x18001b9e5  mov     rcx, r13; struct _SecHandle *
0x18001b9e8  call    ?LsaDeleteSecurityContext@@YAJPEAU_SecHandle@@@Z; LsaDeleteSecurityContext(_SecHandle *)
0x18001b9ed  mov     qword ptr [r13+8], 0FFFFFFFFFFFFFFFEh
0x18001b9f5  mov     ecx, 0C0000000h
0x18001b9fa  mov     eax, edi
0x18001b9fc  and     eax, ecx
0x18001b9fe  cmp     eax, ecx
0x18001ba00  jz      short loc_18001BA58
0x18001ba02  mov     rax, [rbp+40h+var_A8]
0x18001ba06  test    dword ptr [rax], 100h
0x18001ba0c  jz      short loc_18001BA58
0x18001ba0e  test    rbx, rbx
0x18001ba11  jz      short loc_18001BA58
0x18001ba13  xor     r12d, r12d
0x18001ba16  mov     esi, r12d
0x18001ba19  cmp     [rbx+4], r12d
0x18001ba1d  jbe     loc_18001BAC4
0x18001ba23  mov     r9, [rbx+8]
0x18001ba27  mov     ecx, esi
0x18001ba29  add     rcx, rcx
0x18001ba2c  mov     eax, [r9+rcx*8+4]
0x18001ba31  sub     eax, 2
0x18001ba34  cmp     eax, 1
0x18001ba37  ja      short loc_18001BA4F
0x18001ba39  cmp     [r9+rcx*8], r12d
0x18001ba3d  jz      short loc_18001BA4F
0x18001ba3f  mov     rcx, [r9+rcx*8+8]
0x18001ba44  lea     r8, [rbp+40h+var_B8]
0x18001ba48  mov     dl, 1
0x18001ba4a  call    SecpAddVMEx
0x18001ba4f  inc     esi
0x18001ba51  cmp     esi, [rbx+4]
0x18001ba54  jb      short loc_18001BA23
0x18001ba56  jmp     short loc_18001BAC4
0x18001ba58  test    r12d, r12d
0x18001ba5b  jz      short loc_18001BAC4
0x18001ba5d  xor     r12d, r12d
0x18001ba60  test    rbx, rbx
0x18001ba63  jz      short loc_18001BAC4
0x18001ba65  mov     r14d, r12d
0x18001ba68  cmp     [rbx+4], r12d
0x18001ba6c  jbe     short loc_18001BAC4
0x18001ba6e  mov     rcx, [rbx+8]
0x18001ba72  mov     esi, r14d
0x18001ba75  add     rsi, rsi
0x18001ba78  mov     eax, [rcx+rsi*8+4]
0x18001ba7c  sub     eax, 2
0x18001ba7f  cmp     eax, 1
0x18001ba82  ja      short loc_18001BABB
0x18001ba84  mov     rcx, [rcx+rsi*8+8]; hMem
0x18001ba89  test    rcx, rcx
0x18001ba8c  jz      short loc_18001BABB
0x18001ba8e  mov     rax, cs:SecpLsaInprocDispatch
0x18001ba95  test    rax, rax
0x18001ba98  jz      short loc_18001BAA4
0x18001ba9a  mov     rax, [rax]
0x18001ba9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa2  jmp     short loc_18001BAAA
0x18001baa4  call    cs:__imp_LocalFree
0x18001baaa  mov     rax, [rbx+8]
0x18001baae  mov     [rax+rsi*8], r12d
0x18001bab2  mov     rax, [rbx+8]
0x18001bab6  mov     [rax+rsi*8+8], r12
0x18001babb  inc     r14d
0x18001babe  cmp     r14d, [rbx+4]
0x18001bac2  jb      short loc_18001BA6E
0x18001bac4  mov     ecx, [rbp+40h+var_B8]
0x18001bac7  call    SecpReleaseVMSpots
0x18001bacc  test    edi, edi
0x18001bace  jns     short loc_18001BAE0
0x18001bad0  mov     ecx, edi; Status
0x18001bad2  call    cs:__imp_RtlNtStatusToDosError
0x18001bad8  mov     ecx, eax; dwErrCode
0x18001bada  call    cs:__imp_SetLastError
0x18001bae0  mov     ecx, edi
0x18001bae2  call    SspNtStatusToSecStatus
0x18001bae7  mov     rcx, [rbp+40h+var_40]
0x18001baeb  xor     rcx, rsp; StackCookie
0x18001baee  call    __security_check_cookie
0x18001baf3  mov     rbx, [rsp+140h+arg_0]
0x18001bafb  add     rsp, 110h
0x18001bb02  pop     r15
0x18001bb04  pop     r14
0x18001bb06  pop     r13
0x18001bb08  pop     r12
0x18001bb0a  pop     rdi
0x18001bb0b  pop     rsi
0x18001bb0c  pop     rbp
0x18001bb0d  retn
```
