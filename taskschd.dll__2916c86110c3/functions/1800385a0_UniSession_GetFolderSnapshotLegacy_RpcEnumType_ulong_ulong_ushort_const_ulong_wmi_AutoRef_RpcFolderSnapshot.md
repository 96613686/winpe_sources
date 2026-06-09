# UniSession::GetFolderSnapshotLegacy(RpcEnumType,ulong *,ulong,ushort const *,ulong,wmi::AutoRef<RpcFolderSnapshot> &)

- ea: `0x1800385a0`
- end: `0x180038982`
- name: `?GetFolderSnapshotLegacy@UniSession@@IEBAJW4RpcEnumType@@PEAKKPEBGKAEAV?$AutoRef@VRpcFolderSnapshot@@@wmi@@@Z`
- size: `994`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bb00`
- `0x180028bd0`

## callees

- `0x1800017f0`
- `0x180007aa0`
- `0x180009a30`
- `0x18000c750`
- `0x18000c77c`
- `0x18000ca30`
- `0x180026870`
- `0x180036290`
- `0x1800385a0`
- `0x18003b51c`
- `0x180048b4c`
- `0x180049ad8`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003869f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003893b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003894e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003869f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003893b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003894e`

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
        v48 = &qword_180077320;
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
      v48 = &qword_180077320;
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
0x1800385a0  mov     rax, rsp
0x1800385a3  mov     [rax+8], rbx
0x1800385a7  mov     [rax+20h], r9d
0x1800385ab  mov     [rax+18h], r8
0x1800385af  push    rbp
0x1800385b0  push    rsi
0x1800385b1  push    rdi
0x1800385b2  push    r12
0x1800385b4  push    r13
0x1800385b6  push    r14
0x1800385b8  push    r15
0x1800385ba  lea     rbp, [rax-47h]
0x1800385be  sub     rsp, 0C0h
0x1800385c5  mov     r12, r8
0x1800385c8  mov     rax, [rbp+3Fh+arg_20]
0x1800385cc  xor     esi, esi
0x1800385ce  test    rax, rax
0x1800385d1  jz      short loc_1800385EE
0x1800385d3  cmp     word ptr [rax], 5Ch ; '\'
0x1800385d7  jnz     short loc_1800385DF
0x1800385d9  add     rax, 2
0x1800385dd  jz      short loc_1800385EE
0x1800385df  cmp     [rax], si
0x1800385e2  jz      short loc_1800385EE
0x1800385e4  mov     eax, 80070003h
0x1800385e9  jmp     loc_180038967
0x1800385ee  test    r12, r12
0x1800385f1  jnz     short loc_1800385FD
0x1800385f3  mov     eax, 80070057h
0x1800385f8  jmp     loc_180038967
0x1800385fd  mov     [rbp+3Fh+var_A0], rsi
0x180038601  mov     rcx, [rcx+10h]
0x180038605  mov     rax, [rcx]
0x180038608  lea     rdx, [rbp+3Fh+var_A0]
0x18003860c  mov     rax, [rax+28h]
0x180038610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038615  mov     ebx, eax
0x180038617  test    eax, eax
0x180038619  jns     short loc_18003862B
0x18003861b  lea     rcx, [rbp+3Fh+var_A0]
0x18003861f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038624  mov     eax, ebx
0x180038626  jmp     loc_180038967
0x18003862b  mov     edx, [r12]
0x18003862f  test    edx, edx
0x180038631  jz      short loc_180038649
0x180038633  mov     rcx, [rbp+3Fh+var_A0]
0x180038637  mov     rax, [rcx]
0x18003863a  mov     rax, [rax+20h]
0x18003863e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038643  mov     ebx, eax
0x180038645  test    eax, eax
0x180038647  jnz     short loc_18003861B
0x180038649  mov     [rbp+3Fh+pv], rsi
0x18003864d  mov     [rbp+3Fh+var_A8], esi
0x180038650  mov     rcx, [rbp+3Fh+var_A0]
0x180038654  mov     rax, [rcx]
0x180038657  lea     r9, [rbp+3Fh+var_A8]
0x18003865b  lea     r8, [rbp+3Fh+pv]
0x18003865f  mov     edx, 1
0x180038664  mov     rax, [rax+18h]
0x180038668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003866d  mov     r15d, eax
0x180038670  mov     [rbp+3Fh+arg_18], eax
0x180038673  test    eax, eax
0x180038675  jns     short loc_1800386B7
0x180038677  mov     rcx, [rbp+3Fh+pv]
0x18003867b  test    rcx, rcx
0x18003867e  jz      loc_180038954
0x180038684  mov     ebx, esi
0x180038686  mov     edx, [rbp+3Fh+var_A8]
0x180038689  test    edx, edx
0x18003868b  jz      loc_18003894E
0x180038691  mov     eax, ebx
0x180038693  mov     r8, [rcx+rax*8]
0x180038697  test    r8, r8
0x18003869a  jz      short loc_1800386AC
0x18003869c  mov     rcx, r8; pv
0x18003869f  call    cs:__imp_CoTaskMemFree
0x1800386a5  mov     edx, [rbp+3Fh+var_A8]
0x1800386a8  mov     rcx, [rbp+3Fh+pv]
0x1800386ac  inc     ebx
0x1800386ae  cmp     ebx, edx
0x1800386b0  jb      short loc_180038691
0x1800386b2  jmp     loc_18003894E
0x1800386b7  mov     r14d, 30h ; '0'
0x1800386bd  mov     eax, [rbp+3Fh+var_A8]
0x1800386c0  test    eax, eax
0x1800386c2  jnz     short loc_1800386F1
0x1800386c4  mov     ecx, r14d; unsigned __int64
0x1800386c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800386cc  mov     [rbp+3Fh+var_90], rax
0x1800386d0  test    rax, rax
0x1800386d3  jz      short loc_1800386DF
0x1800386d5  mov     rcx, rax; this
0x1800386d8  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x1800386dd  jmp     short loc_1800386E2
0x1800386df  mov     rax, rsi
0x1800386e2  mov     rdx, rax
0x1800386e5  mov     rcx, [rbp+3Fh+arg_30]
0x1800386e9  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x1800386ee  mov     eax, [rbp+3Fh+var_A8]
0x1800386f1  mov     ebx, eax
0x1800386f3  shl     rbx, 3
0x1800386f7  mov     edi, esi
0x1800386f9  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800386fd  cmp     edi, eax
0x1800386ff  jnb     loc_180038786
0x180038705  mov     edx, edi
0x180038707  lea     rcx, [rbp+3Fh+pv]
0x18003870b  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x180038710  mov     rcx, r13
0x180038713  inc     rcx
0x180038716  cmp     [rax+rcx*2], si
0x18003871a  jnz     short loc_180038713
0x18003871c  lea     rcx, ds:0FFFFFFFFFFFFFFFAh[rcx*2]
0x180038724  lea     rax, [rcx+3]
0x180038728  and     rax, 0FFFFFFFFFFFFFFFCh
0x18003872c  add     rcx, rax
0x18003872f  add     rcx, rbx
0x180038732  cmp     rcx, rbx
0x180038735  jb      short loc_180038741
0x180038737  mov     rbx, rcx
0x18003873a  inc     edi
0x18003873c  mov     eax, [rbp+3Fh+var_A8]
0x18003873f  jmp     short loc_1800386FD
0x180038741  mov     [rbp+3Fh+var_70], sil
0x180038745  lea     rax, qword_180077320
0x18003874c  mov     [rbp+3Fh+var_68], rax
0x180038750  mov     [rbp+3Fh+var_60], rsi
0x180038754  mov     [rbp+3Fh+var_58], rsi
0x180038758  mov     [rbp+3Fh+var_50], 0Eh
0x18003875f  mov     [rbp+3Fh+var_4C], 0FFFFFFFFh
0x180038766  mov     [rbp+3Fh+var_48], r13d
0x18003876a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180038771  mov     [rbp+3Fh+pExceptionObject], rax
0x180038775  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003877c  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180038780  call    _CxxThrowException_0
0x180038786  mov     rcx, r14; unsigned __int64
0x180038789  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003878e  mov     [rbp+3Fh+var_90], rax
0x180038792  test    rax, rax
0x180038795  jz      short loc_1800387A4
0x180038797  mov     rcx, rax; this
0x18003879a  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18003879f  mov     rdi, rax
0x1800387a2  jmp     short loc_1800387A7
0x1800387a4  mov     rdi, rsi
0x1800387a7  mov     [rbp+3Fh+var_80], rdi
0x1800387ab  mov     [rbp+3Fh+var_90], rdi
0x1800387af  test    rdi, rdi
0x1800387b2  jz      short loc_1800387B8
0x1800387b4  lock inc dword ptr [rdi+8]
0x1800387b8  mov     [rbp+3Fh+var_38], esi
0x1800387bb  mov     rcx, rbx; size
0x1800387be  call    MIDL_user_allocate
0x1800387c3  mov     r14, rax
0x1800387c6  mov     [rbp+3Fh+var_40], rax
0x1800387ca  test    rax, rax
0x1800387cd  jnz     short loc_180038814
0x1800387cf  mov     [rbp+3Fh+var_70], sil
0x1800387d3  lea     rax, qword_180077320
0x1800387da  mov     [rbp+3Fh+var_68], rax
0x1800387de  mov     [rbp+3Fh+var_60], rsi
0x1800387e2  mov     [rbp+3Fh+var_58], rsi
0x1800387e6  mov     [rbp+3Fh+var_50], 0Eh
0x1800387ed  mov     [rbp+3Fh+var_4C], 0FFFFFFFFh
0x1800387f4  mov     [rbp+3Fh+var_48], r13d
0x1800387f8  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800387ff  mov     [rbp+3Fh+pExceptionObject], rax
0x180038803  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003880a  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18003880e  call    _CxxThrowException_0
0x180038814  mov     r13d, [rbp+3Fh+var_A8]
0x180038818  mov     [rbp+3Fh+var_38], r13d
0x18003881c  lea     eax, ds:0[r13*8]
0x180038824  mov     ecx, eax
0x180038826  add     rax, r14
0x180038829  sub     rbx, rcx
0x18003882c  shr     rbx, 1
0x18003882f  test    r13d, r13d
0x180038832  jz      loc_1800388E6
0x180038838  mov     r12, rax
0x18003883b  xor     edi, edi
0x18003883d  mov     [rbp+3Fh+var_88], rdi
0x180038841  mov     [rbp+3Fh+var_98], rdi
0x180038845  mov     edx, esi
0x180038847  lea     rcx, [rbp+3Fh+pv]
0x18003884b  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x180038850  or      r15, 0FFFFFFFFFFFFFFFFh
0x180038854  inc     r15
0x180038857  cmp     [rax+r15*2], di
0x18003885c  jnz     short loc_180038854
0x18003885e  mov     edx, esi
0x180038860  lea     rcx, [rbp+3Fh+pv]
0x180038864  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x180038869  lea     r9, [r15-4]; unsigned __int64
0x18003886d  lea     rcx, [rbp+3Fh+var_98]
0x180038871  mov     [rsp+28h], rcx; unsigned __int64 *
0x180038876  lea     rcx, [rbp+3Fh+var_88]
0x18003887a  mov     [rsp+0F0h+var_D0], rcx; unsigned __int16 **
0x18003887f  mov     r8, rax; unsigned __int16 *
0x180038882  mov     rdx, rbx; unsigned __int64
0x180038885  mov     rcx, r12; unsigned __int16 *
0x180038888  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003888d  test    eax, eax
0x18003888f  js      short loc_1800388DA
0x180038891  mov     eax, esi
0x180038893  mov     [r14+rax*8], r12
0x180038897  mov     rdx, [rbp+3Fh+var_88]
0x18003889b  add     rdx, 2
0x18003889f  mov     rbx, [rbp+3Fh+var_98]
0x1800388a3  test    rbx, rbx
0x1800388a6  jz      short loc_1800388AB
0x1800388a8  dec     rbx
0x1800388ab  mov     rcx, rdx
0x1800388ae  sub     rcx, r12
0x1800388b1  sar     rcx, 1
0x1800388b4  lea     eax, [rcx+3]
0x1800388b7  and     eax, 0FFFFFFFCh
0x1800388ba  sub     eax, ecx
0x1800388bc  mov     ecx, eax
0x1800388be  lea     r12, [rdx+rax*2]
0x1800388c2  cmp     rbx, rcx
0x1800388c5  jbe     short loc_1800388CC
0x1800388c7  sub     rbx, rcx
0x1800388ca  jmp     short loc_1800388CF
0x1800388cc  mov     rbx, rdi
0x1800388cf  inc     esi
0x1800388d1  cmp     esi, r13d
0x1800388d4  jb      loc_18003883D
0x1800388da  mov     rdi, [rbp+3Fh+var_80]
0x1800388de  mov     r12, [rbp+3Fh+arg_10]
0x1800388e2  mov     r15d, [rbp+3Fh+arg_18]
0x1800388e6  lea     rdx, [rbp+3Fh+var_40]
0x1800388ea  mov     rcx, rdi
0x1800388ed  call    ?AddBatch@RpcFolderSnapshot@@AEAAXAEAV?$RpcArray@PEBG@@@Z; RpcFolderSnapshot::AddBatch(RpcArray<ushort const *> &)
0x1800388f2  mov     rdx, rdi
0x1800388f5  mov     rcx, [rbp+3Fh+arg_30]
0x1800388f9  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x1800388fe  mov     eax, [rbp+3Fh+var_A8]
0x180038901  add     [r12], eax
0x180038905  mov     rcx, [rbp+3Fh+var_40]; void *
0x180038909  call    MIDL_user_free
0x18003890e  nop
0x18003890f  lea     rcx, [rbp+3Fh+var_90]
0x180038913  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x180038918  nop
0x180038919  mov     rcx, [rbp+3Fh+pv]
0x18003891d  xor     esi, esi
0x18003891f  test    rcx, rcx
0x180038922  jz      short loc_180038954
0x180038924  mov     ebx, esi
0x180038926  mov     edx, [rbp+3Fh+var_A8]
0x180038929  test    edx, edx
0x18003892b  jz      short loc_18003894E
0x18003892d  mov     eax, ebx
0x18003892f  mov     r8, [rcx+rax*8]
0x180038933  test    r8, r8
0x180038936  jz      short loc_180038948
0x180038938  mov     rcx, r8; pv
0x18003893b  call    cs:__imp_CoTaskMemFree
0x180038941  mov     edx, [rbp+3Fh+var_A8]
0x180038944  mov     rcx, [rbp+3Fh+pv]; pv
0x180038948  inc     ebx
0x18003894a  cmp     ebx, edx
0x18003894c  jb      short loc_18003892D
0x18003894e  call    cs:__imp_CoTaskMemFree
0x180038954  mov     [rbp+3Fh+pv], rsi
0x180038958  mov     [rbp+3Fh+var_A8], esi
0x18003895b  lea     rcx, [rbp+3Fh+var_A0]
0x18003895f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038964  mov     eax, r15d
0x180038967  mov     rbx, [rsp+0F0h+arg_0]
0x18003896f  add     rsp, 0C0h
0x180038976  pop     r15
0x180038978  pop     r14
0x18003897a  pop     r13
0x18003897c  pop     r12
0x18003897e  pop     rdi
0x18003897f  pop     rsi
0x180038980  pop     rbp
0x180038981  retn
```
