# UniSession::GetFolderSnapshotLegacy(RpcEnumType,ulong *,ulong,ushort const *,ulong,wmi::AutoRef<RpcFolderSnapshot> &)

- ea: `0x18003b784`
- end: `0x18003bb79`
- name: `?GetFolderSnapshotLegacy@UniSession@@IEBAJW4RpcEnumType@@PEAKKPEBGKAEAV?$AutoRef@VRpcFolderSnapshot@@@wmi@@@Z`
- size: `1013`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c020`
- `0x1800211f0`

## callees

- `0x180001880`
- `0x180007e90`
- `0x18000a100`
- `0x18000cd10`
- `0x18000cd44`
- `0x18000cff8`
- `0x180028670`
- `0x1800391c0`
- `0x18003b784`
- `0x18003e88c`
- `0x18004c66c`
- `0x18004d660`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b883`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b883`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UniSession::GetFolderSnapshotLegacy(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        _WORD *a5,
        int a6,
        __int64 a7)
{
  _DWORD *v7; // r12
  _WORD *v8; // rax
  unsigned int v9; // esi
  int v11; // ebx
  int v12; // r15d
  LPVOID *v13; // rcx
  unsigned int v14; // ebx
  unsigned int k; // edx
  unsigned int v16; // eax
  RpcFolderSnapshot *v17; // rax
  RpcFolderSnapshot *v18; // rax
  size_t v19; // rbx
  unsigned int i; // edi
  __int64 v21; // rax
  __int64 v22; // rcx
  size_t v23; // rcx
  RpcFolderSnapshot *v24; // rax
  RpcFolderSnapshot *v25; // rdi
  char *v26; // r14
  unsigned int v27; // r13d
  unsigned __int64 v28; // rbx
  unsigned __int16 *v29; // r12
  __int64 v30; // rax
  __int64 v31; // r15
  const unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rdx
  unsigned __int64 v34; // rbx
  unsigned __int64 v35; // rcx
  unsigned int v36; // ebx
  unsigned int j; // edx
  unsigned int v38; // [rsp+38h] [rbp-81h]
  LPVOID pv; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v40; // [rsp+50h] [rbp-69h] BYREF
  __int64 v41; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 v42; // [rsp+60h] [rbp-59h] BYREF
  RpcFolderSnapshot *v43; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v44; // [rsp+70h] [rbp-49h] BYREF
  RpcFolderSnapshot *v45; // [rsp+78h] [rbp-41h]
  void **pExceptionObject; // [rsp+80h] [rbp-39h] BYREF
  char v47; // [rsp+88h] [rbp-31h]
  __int64 *v48; // [rsp+90h] [rbp-29h]
  __int64 v49; // [rsp+98h] [rbp-21h]
  __int64 v50; // [rsp+A0h] [rbp-19h]
  int v51; // [rsp+A8h] [rbp-11h]
  int v52; // [rsp+ACh] [rbp-Dh]
  int v53; // [rsp+B0h] [rbp-9h]
  void *v54; // [rsp+B8h] [rbp-1h] BYREF
  unsigned int v55; // [rsp+C0h] [rbp+7h]
  int v57; // [rsp+120h] [rbp+67h]

  v7 = a3;
  v8 = a5;
  v9 = 0;
  if ( a5 )
  {
    if ( *a5 != 92 || (v8 = a5 + 1, a5 != (_WORD *)-2LL) )
    {
      if ( *v8 )
        return 2147942403LL;
    }
  }
  if ( !a3 )
    return 2147942487LL;
  v41 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 16) + 40LL))(*(_QWORD *)(a1 + 16), &v41);
  if ( v11 < 0 || *v7 && (v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 32LL))(v41)) != 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    return (unsigned int)v11;
  }
  pv = 0;
  v40 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v41 + 24LL))(
          v41,
          1,
          &pv,
          &v40);
  v57 = v12;
  if ( v12 >= 0 )
  {
    v16 = v40;
    if ( !v40 )
    {
      v17 = (RpcFolderSnapshot *)operator new(0x30u);
      v43 = v17;
      if ( v17 )
        v18 = RpcFolderSnapshot::RpcFolderSnapshot(v17);
      else
        v18 = 0;
      wmi::AutoRef<RpcFolderSnapshot>::operator=(a7, v18);
      v16 = v40;
    }
    v19 = 8LL * v16;
    for ( i = 0; i < v16; ++i )
    {
      v21 = tsched::CoTaskMemAutoArrayPtr<unsigned short *>::operator[](&pv, i);
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
      v23 = v19 + ((2 * v22 - 6 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 * v22 - 6;
      if ( v23 < v19 )
      {
        v47 = 0;
        v48 = &qword_18007B2F0;
        v49 = 0;
        v50 = 0;
        v51 = 14;
        v52 = -1;
        v53 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v19 = v23;
      v16 = v40;
    }
    v24 = (RpcFolderSnapshot *)operator new(0x30u);
    v43 = v24;
    if ( v24 )
      v25 = RpcFolderSnapshot::RpcFolderSnapshot(v24);
    else
      v25 = 0;
    v45 = v25;
    v43 = v25;
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)v25 + 2);
    v55 = 0;
    v26 = (char *)MIDL_user_allocate(v19);
    v54 = v26;
    if ( !v26 )
    {
      v47 = 0;
      v48 = &qword_18007B2F0;
      v49 = 0;
      v50 = 0;
      v51 = 14;
      v52 = -1;
      v53 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v27 = v40;
    v55 = v40;
    v28 = (v19 - 8 * v40) >> 1;
    if ( v40 )
    {
      v29 = (unsigned __int16 *)&v26[8 * v40];
      do
      {
        v44 = 0;
        v42 = 0;
        v30 = tsched::CoTaskMemAutoArrayPtr<unsigned short *>::operator[](&pv, v9);
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)(v30 + 2 * v31) );
        v32 = (const unsigned __int16 *)tsched::CoTaskMemAutoArrayPtr<unsigned short *>::operator[](&pv, v9);
        if ( StringCchCopyNExW(v29, v28, v32, v31 - 4, &v44, &v42, v38) < 0 )
          break;
        *(_QWORD *)&v26[8 * v9] = v29;
        v33 = v44 + 1;
        v34 = v42;
        if ( v42 )
          v34 = v42 - 1;
        v35 = (((unsigned int)(v33 - v29) + 3) & 0xFFFFFFFC) - (unsigned int)(v33 - v29);
        v29 = &v33[v35];
        v28 = v34 <= v35 ? 0LL : v34 - v35;
        ++v9;
      }
      while ( v9 < v27 );
      v25 = v45;
      v7 = a3;
      v12 = v57;
    }
    RpcFolderSnapshot::AddBatch(v25, &v54);
    wmi::AutoRef<RpcFolderSnapshot>::operator=(a7, v25);
    *v7 += v40;
    MIDL_user_free(v54);
    wmi::AutoRef<RpcFolderSnapshot>::Release(&v43);
    v13 = (LPVOID *)pv;
    if ( !pv )
      goto LABEL_56;
    v36 = 0;
    for ( j = v40; v36 < j; ++v36 )
    {
      if ( v13[v36] )
      {
        CoTaskMemFree(v13[v36]);
        j = v40;
        v13 = (LPVOID *)pv;
      }
    }
    goto LABEL_55;
  }
  v13 = (LPVOID *)pv;
  if ( pv )
  {
    v14 = 0;
    for ( k = v40; v14 < k; ++v14 )
    {
      if ( v13[v14] )
      {
        CoTaskMemFree(v13[v14]);
        k = v40;
        v13 = (LPVOID *)pv;
      }
    }
LABEL_55:
    CoTaskMemFree(v13);
  }
LABEL_56:
  pv = 0;
  v40 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003b784  mov     rax, rsp
0x18003b787  mov     [rax+8], rbx
0x18003b78b  mov     [rax+20h], r9d
0x18003b78f  mov     [rax+18h], r8
0x18003b793  push    rbp
0x18003b794  push    rsi
0x18003b795  push    rdi
0x18003b796  push    r12
0x18003b798  push    r13
0x18003b79a  push    r14
0x18003b79c  push    r15
0x18003b79e  lea     rbp, [rax-47h]
0x18003b7a2  sub     rsp, 0C0h
0x18003b7a9  mov     r12, r8
0x18003b7ac  mov     rax, [rbp+3Fh+arg_20]
0x18003b7b0  xor     esi, esi
0x18003b7b2  test    rax, rax
0x18003b7b5  jz      short loc_18003B7D2
0x18003b7b7  cmp     word ptr [rax], 5Ch ; '\'
0x18003b7bb  jnz     short loc_18003B7C3
0x18003b7bd  add     rax, 2
0x18003b7c1  jz      short loc_18003B7D2
0x18003b7c3  cmp     [rax], si
0x18003b7c6  jz      short loc_18003B7D2
0x18003b7c8  mov     eax, 80070003h
0x18003b7cd  jmp     loc_18003BB5D
0x18003b7d2  test    r12, r12
0x18003b7d5  jnz     short loc_18003B7E1
0x18003b7d7  mov     eax, 80070057h
0x18003b7dc  jmp     loc_18003BB5D
0x18003b7e1  mov     [rbp+3Fh+var_A0], rsi
0x18003b7e5  mov     rcx, [rcx+10h]
0x18003b7e9  mov     rax, [rcx]
0x18003b7ec  lea     rdx, [rbp+3Fh+var_A0]
0x18003b7f0  mov     rax, [rax+28h]
0x18003b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7f9  mov     ebx, eax
0x18003b7fb  test    eax, eax
0x18003b7fd  jns     short loc_18003B80F
0x18003b7ff  lea     rcx, [rbp+3Fh+var_A0]
0x18003b803  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b808  mov     eax, ebx
0x18003b80a  jmp     loc_18003BB5D
0x18003b80f  mov     edx, [r12]
0x18003b813  test    edx, edx
0x18003b815  jz      short loc_18003B82D
0x18003b817  mov     rcx, [rbp+3Fh+var_A0]
0x18003b81b  mov     rax, [rcx]
0x18003b81e  mov     rax, [rax+20h]
0x18003b822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b827  mov     ebx, eax
0x18003b829  test    eax, eax
0x18003b82b  jnz     short loc_18003B7FF
0x18003b82d  mov     [rbp+3Fh+pv], rsi
0x18003b831  mov     [rbp+3Fh+var_A8], esi
0x18003b834  mov     rcx, [rbp+3Fh+var_A0]
0x18003b838  mov     rax, [rcx]
0x18003b83b  lea     r9, [rbp+3Fh+var_A8]
0x18003b83f  lea     r8, [rbp+3Fh+pv]
0x18003b843  mov     edx, 1
0x18003b848  mov     rax, [rax+18h]
0x18003b84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b851  mov     r15d, eax
0x18003b854  mov     [rbp+3Fh+arg_18], eax
0x18003b857  test    eax, eax
0x18003b859  jns     short loc_18003B8A1
0x18003b85b  mov     rcx, [rbp+3Fh+pv]
0x18003b85f  test    rcx, rcx
0x18003b862  jz      loc_18003BB4A
0x18003b868  mov     ebx, esi
0x18003b86a  mov     edx, [rbp+3Fh+var_A8]
0x18003b86d  test    edx, edx
0x18003b86f  jz      loc_18003BB3E
0x18003b875  mov     eax, ebx
0x18003b877  mov     r8, [rcx+rax*8]
0x18003b87b  test    r8, r8
0x18003b87e  jz      short loc_18003B896
0x18003b880  mov     rcx, r8; pv
0x18003b883  call    cs:__imp_CoTaskMemFree
0x18003b88a  nop     dword ptr [rax+rax+00h]
0x18003b88f  mov     edx, [rbp+3Fh+var_A8]
0x18003b892  mov     rcx, [rbp+3Fh+pv]
0x18003b896  inc     ebx
0x18003b898  cmp     ebx, edx
0x18003b89a  jb      short loc_18003B875
0x18003b89c  jmp     loc_18003BB3E
0x18003b8a1  mov     r14d, 30h ; '0'
0x18003b8a7  mov     eax, [rbp+3Fh+var_A8]
0x18003b8aa  test    eax, eax
0x18003b8ac  jnz     short loc_18003B8DB
0x18003b8ae  mov     ecx, r14d; unsigned __int64
0x18003b8b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b8b6  mov     [rbp+3Fh+var_90], rax
0x18003b8ba  test    rax, rax
0x18003b8bd  jz      short loc_18003B8C9
0x18003b8bf  mov     rcx, rax; this
0x18003b8c2  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18003b8c7  jmp     short loc_18003B8CC
0x18003b8c9  mov     rax, rsi
0x18003b8cc  mov     rdx, rax
0x18003b8cf  mov     rcx, [rbp+3Fh+arg_30]
0x18003b8d3  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x18003b8d8  mov     eax, [rbp+3Fh+var_A8]
0x18003b8db  mov     ebx, eax
0x18003b8dd  shl     rbx, 3
0x18003b8e1  mov     edi, esi
0x18003b8e3  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003b8e7  cmp     edi, eax
0x18003b8e9  jnb     loc_18003B970
0x18003b8ef  mov     edx, edi
0x18003b8f1  lea     rcx, [rbp+3Fh+pv]
0x18003b8f5  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x18003b8fa  mov     rcx, r13
0x18003b8fd  inc     rcx
0x18003b900  cmp     [rax+rcx*2], si
0x18003b904  jnz     short loc_18003B8FD
0x18003b906  lea     rcx, ds:0FFFFFFFFFFFFFFFAh[rcx*2]
0x18003b90e  lea     rax, [rcx+3]
0x18003b912  and     rax, 0FFFFFFFFFFFFFFFCh
0x18003b916  add     rcx, rax
0x18003b919  add     rcx, rbx
0x18003b91c  cmp     rcx, rbx
0x18003b91f  jb      short loc_18003B92B
0x18003b921  mov     rbx, rcx
0x18003b924  inc     edi
0x18003b926  mov     eax, [rbp+3Fh+var_A8]
0x18003b929  jmp     short loc_18003B8E7
0x18003b92b  mov     [rbp+3Fh+var_70], sil
0x18003b92f  lea     rax, qword_18007B2F0
0x18003b936  mov     [rbp+3Fh+var_68], rax
0x18003b93a  mov     [rbp+3Fh+var_60], rsi
0x18003b93e  mov     [rbp+3Fh+var_58], rsi
0x18003b942  mov     [rbp+3Fh+var_50], 0Eh
0x18003b949  mov     [rbp+3Fh+var_4C], 0FFFFFFFFh
0x18003b950  mov     [rbp+3Fh+var_48], r13d
0x18003b954  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003b95b  mov     [rbp+3Fh+pExceptionObject], rax
0x18003b95f  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003b966  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18003b96a  call    _CxxThrowException_0
0x18003b970  mov     rcx, r14; unsigned __int64
0x18003b973  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b978  mov     [rbp+3Fh+var_90], rax
0x18003b97c  test    rax, rax
0x18003b97f  jz      short loc_18003B98E
0x18003b981  mov     rcx, rax; this
0x18003b984  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18003b989  mov     rdi, rax
0x18003b98c  jmp     short loc_18003B991
0x18003b98e  mov     rdi, rsi
0x18003b991  mov     [rbp+3Fh+var_80], rdi
0x18003b995  mov     [rbp+3Fh+var_90], rdi
0x18003b999  test    rdi, rdi
0x18003b99c  jz      short loc_18003B9A2
0x18003b99e  lock inc dword ptr [rdi+8]
0x18003b9a2  mov     [rbp+3Fh+var_38], esi
0x18003b9a5  mov     rcx, rbx; size
0x18003b9a8  call    MIDL_user_allocate
0x18003b9ad  mov     r14, rax
0x18003b9b0  mov     [rbp+3Fh+var_40], rax
0x18003b9b4  test    rax, rax
0x18003b9b7  jnz     short loc_18003B9FE
0x18003b9b9  mov     [rbp+3Fh+var_70], sil
0x18003b9bd  lea     rax, qword_18007B2F0
0x18003b9c4  mov     [rbp+3Fh+var_68], rax
0x18003b9c8  mov     [rbp+3Fh+var_60], rsi
0x18003b9cc  mov     [rbp+3Fh+var_58], rsi
0x18003b9d0  mov     [rbp+3Fh+var_50], 0Eh
0x18003b9d7  mov     [rbp+3Fh+var_4C], 0FFFFFFFFh
0x18003b9de  mov     [rbp+3Fh+var_48], r13d
0x18003b9e2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003b9e9  mov     [rbp+3Fh+pExceptionObject], rax
0x18003b9ed  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003b9f4  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18003b9f8  call    _CxxThrowException_0
0x18003b9fe  mov     r13d, [rbp+3Fh+var_A8]
0x18003ba02  mov     [rbp+3Fh+var_38], r13d
0x18003ba06  lea     eax, ds:0[r13*8]
0x18003ba0e  mov     ecx, eax
0x18003ba10  add     rax, r14
0x18003ba13  sub     rbx, rcx
0x18003ba16  shr     rbx, 1
0x18003ba19  test    r13d, r13d
0x18003ba1c  jz      loc_18003BAD0
0x18003ba22  mov     r12, rax
0x18003ba25  xor     edi, edi
0x18003ba27  mov     [rbp+3Fh+var_88], rdi
0x18003ba2b  mov     [rbp+3Fh+var_98], rdi
0x18003ba2f  mov     edx, esi
0x18003ba31  lea     rcx, [rbp+3Fh+pv]
0x18003ba35  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x18003ba3a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003ba3e  inc     r15
0x18003ba41  cmp     [rax+r15*2], di
0x18003ba46  jnz     short loc_18003BA3E
0x18003ba48  mov     edx, esi
0x18003ba4a  lea     rcx, [rbp+3Fh+pv]
0x18003ba4e  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x18003ba53  lea     r9, [r15-4]; unsigned __int64
0x18003ba57  lea     rcx, [rbp+3Fh+var_98]
0x18003ba5b  mov     [rsp+28h], rcx; unsigned __int64 *
0x18003ba60  lea     rcx, [rbp+3Fh+var_88]
0x18003ba64  mov     [rsp+0F0h+var_D0], rcx; unsigned __int16 **
0x18003ba69  mov     r8, rax; unsigned __int16 *
0x18003ba6c  mov     rdx, rbx; unsigned __int64
0x18003ba6f  mov     rcx, r12; unsigned __int16 *
0x18003ba72  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003ba77  test    eax, eax
0x18003ba79  js      short loc_18003BAC4
0x18003ba7b  mov     eax, esi
0x18003ba7d  mov     [r14+rax*8], r12
0x18003ba81  mov     rdx, [rbp+3Fh+var_88]
0x18003ba85  add     rdx, 2
0x18003ba89  mov     rbx, [rbp+3Fh+var_98]
0x18003ba8d  test    rbx, rbx
0x18003ba90  jz      short loc_18003BA95
0x18003ba92  dec     rbx
0x18003ba95  mov     rcx, rdx
0x18003ba98  sub     rcx, r12
0x18003ba9b  sar     rcx, 1
0x18003ba9e  lea     eax, [rcx+3]
0x18003baa1  and     eax, 0FFFFFFFCh
0x18003baa4  sub     eax, ecx
0x18003baa6  mov     ecx, eax
0x18003baa8  lea     r12, [rdx+rax*2]
0x18003baac  cmp     rbx, rcx
0x18003baaf  jbe     short loc_18003BAB6
0x18003bab1  sub     rbx, rcx
0x18003bab4  jmp     short loc_18003BAB9
0x18003bab6  mov     rbx, rdi
0x18003bab9  inc     esi
0x18003babb  cmp     esi, r13d
0x18003babe  jb      loc_18003BA27
0x18003bac4  mov     rdi, [rbp+3Fh+var_80]
0x18003bac8  mov     r12, [rbp+3Fh+arg_10]
0x18003bacc  mov     r15d, [rbp+3Fh+arg_18]
0x18003bad0  lea     rdx, [rbp+3Fh+var_40]
0x18003bad4  mov     rcx, rdi
0x18003bad7  call    ?AddBatch@RpcFolderSnapshot@@AEAAXAEAV?$RpcArray@PEBG@@@Z; RpcFolderSnapshot::AddBatch(RpcArray<ushort const *> &)
0x18003badc  mov     rdx, rdi
0x18003badf  mov     rcx, [rbp+3Fh+arg_30]
0x18003bae3  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x18003bae8  mov     eax, [rbp+3Fh+var_A8]
0x18003baeb  add     [r12], eax
0x18003baef  mov     rcx, [rbp+3Fh+var_40]; void *
0x18003baf3  call    MIDL_user_free
0x18003baf8  nop
0x18003baf9  lea     rcx, [rbp+3Fh+var_90]
0x18003bafd  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18003bb02  nop
0x18003bb03  mov     rcx, [rbp+3Fh+pv]
0x18003bb07  xor     esi, esi
0x18003bb09  test    rcx, rcx
0x18003bb0c  jz      short loc_18003BB4A
0x18003bb0e  mov     ebx, esi
0x18003bb10  mov     edx, [rbp+3Fh+var_A8]
0x18003bb13  test    edx, edx
0x18003bb15  jz      short loc_18003BB3E
0x18003bb17  mov     eax, ebx
0x18003bb19  mov     r8, [rcx+rax*8]
0x18003bb1d  test    r8, r8
0x18003bb20  jz      short loc_18003BB38
0x18003bb22  mov     rcx, r8; pv
0x18003bb25  call    cs:__imp_CoTaskMemFree
0x18003bb2c  nop     dword ptr [rax+rax+00h]
0x18003bb31  mov     edx, [rbp+3Fh+var_A8]
0x18003bb34  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bb38  inc     ebx
0x18003bb3a  cmp     ebx, edx
0x18003bb3c  jb      short loc_18003BB17
0x18003bb3e  call    cs:__imp_CoTaskMemFree
0x18003bb45  nop     dword ptr [rax+rax+00h]
0x18003bb4a  mov     [rbp+3Fh+pv], rsi
0x18003bb4e  mov     [rbp+3Fh+var_A8], esi
0x18003bb51  lea     rcx, [rbp+3Fh+var_A0]
0x18003bb55  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bb5a  mov     eax, r15d
0x18003bb5d  mov     rbx, [rsp+0F0h+arg_0]
0x18003bb65  add     rsp, 0C0h
0x18003bb6c  pop     r15
0x18003bb6e  pop     r14
0x18003bb70  pop     r13
0x18003bb72  pop     r12
0x18003bb74  pop     rdi
0x18003bb75  pop     rsi
0x18003bb76  pop     rbp
0x18003bb77  retn
```
