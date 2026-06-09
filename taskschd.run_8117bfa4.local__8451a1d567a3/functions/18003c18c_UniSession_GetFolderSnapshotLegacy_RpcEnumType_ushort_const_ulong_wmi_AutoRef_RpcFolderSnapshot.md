# UniSession::GetFolderSnapshotLegacy(RpcEnumType,ushort const *,ulong,wmi::AutoRef<RpcFolderSnapshot> &)

- ea: `0x18003c18c`
- end: `0x18003c589`
- name: `?GetFolderSnapshotLegacy@UniSession@@IEBAJW4RpcEnumType@@PEBGKAEAV?$AutoRef@VRpcFolderSnapshot@@@wmi@@@Z`
- size: `1021`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c950`
- `0x1800201b0`
- `0x1800203d0`

## callees

- `0x180001880`
- `0x180007e90`
- `0x18000a100`
- `0x18000cd10`
- `0x18000cd44`
- `0x18000cff8`
- `0x180028670`
- `0x1800391c0`
- `0x18003c18c`
- `0x18003e88c`
- `0x18004c66c`
- `0x18004d660`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c53c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c555`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c53c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c555`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UniSession::GetFolderSnapshotLegacy(__int64 a1, int a2, _WORD *a3, __int64 a4, __int64 a5)
{
  int v6; // ebx
  int v7; // edi
  LPVOID *v8; // rcx
  unsigned int v9; // ebx
  unsigned int n; // edx
  unsigned int v11; // eax
  RpcFolderSnapshot *v12; // rax
  RpcFolderSnapshot *v13; // rax
  LPVOID *v14; // rcx
  unsigned int v15; // ebx
  unsigned int m; // edx
  size_t v17; // rbx
  unsigned int i; // edi
  __int64 v19; // rax
  __int64 v20; // rcx
  size_t v21; // rcx
  RpcFolderSnapshot *v22; // rax
  RpcFolderSnapshot *v23; // rdi
  char *v24; // r14
  unsigned int v25; // r12d
  unsigned __int16 *v26; // r13
  unsigned __int64 v27; // rbx
  unsigned int j; // esi
  __int64 v29; // rax
  __int64 v30; // r15
  const unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rdx
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // rcx
  unsigned int v35; // ebx
  unsigned int k; // edx
  unsigned int v37; // [rsp+30h] [rbp-81h]
  LPVOID pv; // [rsp+40h] [rbp-71h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-69h] BYREF
  __int64 v40; // [rsp+50h] [rbp-61h] BYREF
  RpcFolderSnapshot *v41; // [rsp+58h] [rbp-59h] BYREF
  unsigned __int16 *v42; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-41h] BYREF
  char v45; // [rsp+78h] [rbp-39h]
  __int64 *v46; // [rsp+80h] [rbp-31h]
  __int64 v47; // [rsp+88h] [rbp-29h]
  __int64 v48; // [rsp+90h] [rbp-21h]
  int v49; // [rsp+98h] [rbp-19h]
  int v50; // [rsp+9Ch] [rbp-15h]
  int v51; // [rsp+A0h] [rbp-11h]
  void *v52; // [rsp+A8h] [rbp-9h] BYREF
  unsigned int v53; // [rsp+B0h] [rbp-1h]

  if ( a2 != 1 )
    return 2147942450LL;
  if ( a3 )
  {
    if ( *a3 != 92 || ++a3 != 0 )
    {
      if ( *a3 )
        return 2147942403LL;
    }
  }
  v40 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 16) + 40LL))(*(_QWORD *)(a1 + 16), &v40);
  if ( v6 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    return (unsigned int)v6;
  }
  pv = 0;
  v39 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v40 + 24LL))(
         v40,
         0xFFFFFFFFLL,
         &pv,
         &v39);
  if ( v7 >= 0 )
  {
    v11 = v39;
    if ( v39 )
    {
      v17 = 8LL * v39;
      for ( i = 0; i < v11; ++i )
      {
        v19 = tsched::CoTaskMemAutoArrayPtr<unsigned short *>::operator[](&pv, i);
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(v19 + 2 * v20) );
        v21 = v17 + ((2 * v20 - 6 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 * v20 - 6;
        if ( v21 < v17 )
        {
          v45 = 0;
          v46 = &qword_18007B2F0;
          v47 = 0;
          v48 = 0;
          v49 = 14;
          v50 = -1;
          v51 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        v17 = v21;
        v11 = v39;
      }
      v22 = (RpcFolderSnapshot *)operator new(0x30u);
      v41 = v22;
      if ( v22 )
        v23 = RpcFolderSnapshot::RpcFolderSnapshot(v22);
      else
        v23 = 0;
      v41 = v23;
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)v23 + 2);
      v53 = 0;
      v24 = (char *)MIDL_user_allocate(v17);
      v52 = v24;
      if ( !v24 )
      {
        v45 = 0;
        v46 = &qword_18007B2F0;
        v47 = 0;
        v48 = 0;
        v49 = 14;
        v50 = -1;
        v51 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v25 = v39;
      v53 = v39;
      v26 = (unsigned __int16 *)&v24[8 * v39];
      v27 = (v17 - 8 * v39) >> 1;
      for ( j = 0; j < v25; ++j )
      {
        v42 = 0;
        v43 = 0;
        v29 = tsched::CoTaskMemAutoArrayPtr<unsigned short *>::operator[](&pv, j);
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)(v29 + 2 * v30) );
        v31 = (const unsigned __int16 *)tsched::CoTaskMemAutoArrayPtr<unsigned short *>::operator[](&pv, j);
        if ( StringCchCopyNExW(v26, v27, v31, v30 - 4, &v42, &v43, v37) < 0 )
          break;
        *(_QWORD *)&v24[8 * j] = v26;
        v32 = v42 + 1;
        v33 = v43;
        if ( v43 )
          v33 = v43 - 1;
        v34 = (((unsigned int)(v32 - v26) + 3) & 0xFFFFFFFC) - (unsigned int)(v32 - v26);
        v26 = &v32[v34];
        v27 = v33 <= v34 ? 0LL : v33 - v34;
      }
      RpcFolderSnapshot::AddBatch(v23, &v52);
      wmi::AutoRef<RpcFolderSnapshot>::operator=(a5, v23);
      MIDL_user_free(v52);
      wmi::AutoRef<RpcFolderSnapshot>::Release(&v41);
      v14 = (LPVOID *)pv;
      if ( !pv )
        goto LABEL_58;
      v35 = 0;
      for ( k = v39; v35 < k; ++v35 )
      {
        if ( v14[v35] )
        {
          CoTaskMemFree(v14[v35]);
          k = v39;
          v14 = (LPVOID *)pv;
        }
      }
    }
    else
    {
      v12 = (RpcFolderSnapshot *)operator new(0x30u);
      v41 = v12;
      if ( v12 )
        v13 = RpcFolderSnapshot::RpcFolderSnapshot(v12);
      else
        v13 = 0;
      wmi::AutoRef<RpcFolderSnapshot>::operator=(a5, v13);
      v14 = (LPVOID *)pv;
      if ( !pv )
        goto LABEL_58;
      v15 = 0;
      for ( m = v39; v15 < m; ++v15 )
      {
        if ( v14[v15] )
        {
          CoTaskMemFree(v14[v15]);
          m = v39;
          v14 = (LPVOID *)pv;
        }
      }
    }
    CoTaskMemFree(v14);
LABEL_58:
    pv = 0;
    v39 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    return 0;
  }
  v8 = (LPVOID *)pv;
  if ( pv )
  {
    v9 = 0;
    for ( n = v39; v9 < n; ++v9 )
    {
      if ( v8[v9] )
      {
        CoTaskMemFree(v8[v9]);
        n = v39;
        v8 = (LPVOID *)pv;
      }
    }
    CoTaskMemFree(v8);
  }
  pv = 0;
  v39 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003c18c  push    rbp
0x18003c18e  push    rbx
0x18003c18f  push    rsi
0x18003c190  push    rdi
0x18003c191  push    r12
0x18003c193  push    r13
0x18003c195  push    r14
0x18003c197  push    r15
0x18003c199  lea     rbp, [rsp-17h]
0x18003c19e  sub     rsp, 0C8h
0x18003c1a5  cmp     edx, 1
0x18003c1a8  jz      short loc_18003C1B4
0x18003c1aa  mov     eax, 80070032h
0x18003c1af  jmp     loc_18003C574
0x18003c1b4  xor     r15d, r15d
0x18003c1b7  test    r8, r8
0x18003c1ba  jz      short loc_18003C1D9
0x18003c1bc  cmp     word ptr [r8], 5Ch ; '\'
0x18003c1c1  jnz     short loc_18003C1C9
0x18003c1c3  add     r8, 2
0x18003c1c7  jz      short loc_18003C1D9
0x18003c1c9  cmp     [r8], r15w
0x18003c1cd  jz      short loc_18003C1D9
0x18003c1cf  mov     eax, 80070003h
0x18003c1d4  jmp     loc_18003C574
0x18003c1d9  mov     [rbp+4Fh+var_B0], r15
0x18003c1dd  mov     rcx, [rcx+10h]
0x18003c1e1  mov     rax, [rcx]
0x18003c1e4  lea     rdx, [rbp+4Fh+var_B0]
0x18003c1e8  mov     rax, [rax+28h]
0x18003c1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1f1  mov     ebx, eax
0x18003c1f3  test    eax, eax
0x18003c1f5  jns     short loc_18003C207
0x18003c1f7  lea     rcx, [rbp+4Fh+var_B0]
0x18003c1fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c200  mov     eax, ebx
0x18003c202  jmp     loc_18003C574
0x18003c207  mov     [rbp+4Fh+pv], r15
0x18003c20b  mov     [rbp+4Fh+var_B8], r15d
0x18003c20f  mov     rcx, [rbp+4Fh+var_B0]
0x18003c213  mov     rax, [rcx]
0x18003c216  lea     r9, [rbp+4Fh+var_B8]
0x18003c21a  lea     r8, [rbp+4Fh+pv]
0x18003c21e  or      r12d, 0FFFFFFFFh
0x18003c222  mov     edx, r12d
0x18003c225  mov     rax, [rax+18h]
0x18003c229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c22e  mov     edi, eax
0x18003c230  test    eax, eax
0x18003c232  jns     short loc_18003C292
0x18003c234  mov     rcx, [rbp+4Fh+pv]
0x18003c238  test    rcx, rcx
0x18003c23b  jz      short loc_18003C27A
0x18003c23d  mov     ebx, r15d
0x18003c240  mov     edx, [rbp+4Fh+var_B8]
0x18003c243  test    edx, edx
0x18003c245  jz      short loc_18003C26E
0x18003c247  mov     eax, ebx
0x18003c249  mov     r8, [rcx+rax*8]
0x18003c24d  test    r8, r8
0x18003c250  jz      short loc_18003C268
0x18003c252  mov     rcx, r8; pv
0x18003c255  call    cs:__imp_CoTaskMemFree
0x18003c25c  nop     dword ptr [rax+rax+00h]
0x18003c261  mov     edx, [rbp+4Fh+var_B8]
0x18003c264  mov     rcx, [rbp+4Fh+pv]; pv
0x18003c268  inc     ebx
0x18003c26a  cmp     ebx, edx
0x18003c26c  jb      short loc_18003C247
0x18003c26e  call    cs:__imp_CoTaskMemFree
0x18003c275  nop     dword ptr [rax+rax+00h]
0x18003c27a  mov     [rbp+4Fh+pv], r15
0x18003c27e  mov     [rbp+4Fh+var_B8], r15d
0x18003c282  lea     rcx, [rbp+4Fh+var_B0]
0x18003c286  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c28b  mov     eax, edi
0x18003c28d  jmp     loc_18003C574
0x18003c292  mov     eax, [rbp+4Fh+var_B8]
0x18003c295  test    eax, eax
0x18003c297  jnz     short loc_18003C30B
0x18003c299  lea     ecx, [rax+30h]; unsigned __int64
0x18003c29c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c2a1  mov     [rbp+4Fh+var_A8], rax
0x18003c2a5  test    rax, rax
0x18003c2a8  jz      short loc_18003C2B4
0x18003c2aa  mov     rcx, rax; this
0x18003c2ad  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18003c2b2  jmp     short loc_18003C2B7
0x18003c2b4  mov     rax, r15
0x18003c2b7  mov     rdx, rax
0x18003c2ba  mov     rcx, [rbp+4Fh+arg_20]
0x18003c2be  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x18003c2c3  nop
0x18003c2c4  mov     rcx, [rbp+4Fh+pv]
0x18003c2c8  test    rcx, rcx
0x18003c2cb  jz      loc_18003C561
0x18003c2d1  mov     ebx, r15d
0x18003c2d4  mov     edx, [rbp+4Fh+var_B8]
0x18003c2d7  test    edx, edx
0x18003c2d9  jz      loc_18003C555
0x18003c2df  mov     eax, ebx
0x18003c2e1  mov     r8, [rcx+rax*8]
0x18003c2e5  test    r8, r8
0x18003c2e8  jz      short loc_18003C300
0x18003c2ea  mov     rcx, r8; pv
0x18003c2ed  call    cs:__imp_CoTaskMemFree
0x18003c2f4  nop     dword ptr [rax+rax+00h]
0x18003c2f9  mov     edx, [rbp+4Fh+var_B8]
0x18003c2fc  mov     rcx, [rbp+4Fh+pv]
0x18003c300  inc     ebx
0x18003c302  cmp     ebx, edx
0x18003c304  jb      short loc_18003C2DF
0x18003c306  jmp     loc_18003C555
0x18003c30b  mov     rbx, rax
0x18003c30e  shl     rbx, 3
0x18003c312  mov     edi, r15d
0x18003c315  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003c319  cmp     edi, eax
0x18003c31b  jnb     short loc_18003C39B
0x18003c31d  mov     edx, edi
0x18003c31f  lea     rcx, [rbp+4Fh+pv]
0x18003c323  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x18003c328  mov     rcx, rsi
0x18003c32b  inc     rcx
0x18003c32e  cmp     [rax+rcx*2], r15w
0x18003c333  jnz     short loc_18003C32B
0x18003c335  lea     rcx, ds:0FFFFFFFFFFFFFFFAh[rcx*2]
0x18003c33d  lea     rax, [rcx+3]
0x18003c341  and     rax, 0FFFFFFFFFFFFFFFCh
0x18003c345  add     rcx, rax
0x18003c348  add     rcx, rbx
0x18003c34b  cmp     rcx, rbx
0x18003c34e  jb      short loc_18003C35A
0x18003c350  mov     rbx, rcx
0x18003c353  inc     edi
0x18003c355  mov     eax, [rbp+4Fh+var_B8]
0x18003c358  jmp     short loc_18003C319
0x18003c35a  mov     [rbp+4Fh+var_88], r15b
0x18003c35e  lea     rax, qword_18007B2F0
0x18003c365  mov     [rbp+4Fh+var_80], rax
0x18003c369  mov     [rbp+4Fh+var_78], r15
0x18003c36d  mov     [rbp+4Fh+var_70], r15
0x18003c371  mov     [rbp+4Fh+var_68], 0Eh
0x18003c378  mov     [rbp+4Fh+var_64], r12d
0x18003c37c  mov     [rbp+4Fh+var_60], esi
0x18003c37f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003c386  mov     [rbp+4Fh+pExceptionObject], rax
0x18003c38a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003c391  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003c395  call    _CxxThrowException_0
0x18003c39b  mov     ecx, 30h ; '0'; unsigned __int64
0x18003c3a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c3a5  mov     [rbp+4Fh+var_A8], rax
0x18003c3a9  test    rax, rax
0x18003c3ac  jz      short loc_18003C3BB
0x18003c3ae  mov     rcx, rax; this
0x18003c3b1  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18003c3b6  mov     rdi, rax
0x18003c3b9  jmp     short loc_18003C3BE
0x18003c3bb  mov     rdi, r15
0x18003c3be  mov     [rbp+4Fh+var_A8], rdi
0x18003c3c2  test    rdi, rdi
0x18003c3c5  jz      short loc_18003C3CB
0x18003c3c7  lock inc dword ptr [rdi+8]
0x18003c3cb  mov     [rbp+4Fh+var_50], r15d
0x18003c3cf  mov     rcx, rbx; size
0x18003c3d2  call    MIDL_user_allocate
0x18003c3d7  mov     r14, rax
0x18003c3da  mov     [rbp+4Fh+var_58], rax
0x18003c3de  test    rax, rax
0x18003c3e1  jnz     short loc_18003C424
0x18003c3e3  mov     [rbp+4Fh+var_88], r15b
0x18003c3e7  lea     rax, qword_18007B2F0
0x18003c3ee  mov     [rbp+4Fh+var_80], rax
0x18003c3f2  mov     [rbp+4Fh+var_78], r15
0x18003c3f6  mov     [rbp+4Fh+var_70], r15
0x18003c3fa  mov     [rbp+4Fh+var_68], 0Eh
0x18003c401  mov     [rbp+4Fh+var_64], r12d
0x18003c405  mov     [rbp+4Fh+var_60], esi
0x18003c408  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003c40f  mov     [rbp+4Fh+pExceptionObject], rax
0x18003c413  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003c41a  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003c41e  call    _CxxThrowException_0
0x18003c424  mov     r12d, [rbp+4Fh+var_B8]
0x18003c428  mov     [rbp+4Fh+var_50], r12d
0x18003c42c  lea     eax, ds:0[r12*8]
0x18003c434  mov     ecx, eax
0x18003c436  lea     r13, [rax+r14]
0x18003c43a  sub     rbx, rcx
0x18003c43d  shr     rbx, 1
0x18003c440  mov     esi, r15d
0x18003c443  test    r12d, r12d
0x18003c446  jz      loc_18003C4EE
0x18003c44c  mov     [rbp+4Fh+var_A0], r15
0x18003c450  mov     [rbp+4Fh+var_98], r15
0x18003c454  mov     edx, esi
0x18003c456  lea     rcx, [rbp+4Fh+pv]
0x18003c45a  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x18003c45f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003c463  xor     ecx, ecx
0x18003c465  inc     r15
0x18003c468  cmp     [rax+r15*2], cx
0x18003c46d  jnz     short loc_18003C465
0x18003c46f  mov     edx, esi
0x18003c471  lea     rcx, [rbp+4Fh+pv]
0x18003c475  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x18003c47a  lea     r9, [r15-4]; unsigned __int64
0x18003c47e  lea     rcx, [rbp+4Fh+var_98]
0x18003c482  mov     [rsp+100h+var_D8], rcx; unsigned __int64 *
0x18003c487  lea     rcx, [rbp+4Fh+var_A0]
0x18003c48b  mov     [rsp+100h+var_E0], rcx; unsigned __int16 **
0x18003c490  mov     r8, rax; unsigned __int16 *
0x18003c493  mov     rdx, rbx; unsigned __int64
0x18003c496  mov     rcx, r13; unsigned __int16 *
0x18003c499  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003c49e  xor     r15d, r15d
0x18003c4a1  test    eax, eax
0x18003c4a3  js      short loc_18003C4EE
0x18003c4a5  mov     eax, esi
0x18003c4a7  mov     [r14+rax*8], r13
0x18003c4ab  mov     rdx, [rbp+4Fh+var_A0]
0x18003c4af  add     rdx, 2
0x18003c4b3  mov     rbx, [rbp+4Fh+var_98]
0x18003c4b7  test    rbx, rbx
0x18003c4ba  jz      short loc_18003C4BF
0x18003c4bc  dec     rbx
0x18003c4bf  mov     rcx, rdx
0x18003c4c2  sub     rcx, r13
0x18003c4c5  sar     rcx, 1
0x18003c4c8  lea     eax, [rcx+3]
0x18003c4cb  and     eax, 0FFFFFFFCh
0x18003c4ce  sub     eax, ecx
0x18003c4d0  mov     ecx, eax
0x18003c4d2  lea     r13, [rdx+rax*2]
0x18003c4d6  cmp     rbx, rcx
0x18003c4d9  jbe     short loc_18003C4E0
0x18003c4db  sub     rbx, rcx
0x18003c4de  jmp     short loc_18003C4E3
0x18003c4e0  mov     rbx, r15
0x18003c4e3  inc     esi
0x18003c4e5  cmp     esi, r12d
0x18003c4e8  jb      loc_18003C44C
0x18003c4ee  lea     rdx, [rbp+4Fh+var_58]
0x18003c4f2  mov     rcx, rdi
0x18003c4f5  call    ?AddBatch@RpcFolderSnapshot@@AEAAXAEAV?$RpcArray@PEBG@@@Z; RpcFolderSnapshot::AddBatch(RpcArray<ushort const *> &)
0x18003c4fa  mov     rdx, rdi
0x18003c4fd  mov     rcx, [rbp+4Fh+arg_20]
0x18003c501  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x18003c506  nop
0x18003c507  mov     rcx, [rbp+4Fh+var_58]; void *
0x18003c50b  call    MIDL_user_free
0x18003c510  nop
0x18003c511  lea     rcx, [rbp+4Fh+var_A8]
0x18003c515  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18003c51a  nop
0x18003c51b  mov     rcx, [rbp+4Fh+pv]
0x18003c51f  test    rcx, rcx
0x18003c522  jz      short loc_18003C561
0x18003c524  mov     ebx, r15d
0x18003c527  mov     edx, [rbp+4Fh+var_B8]
0x18003c52a  test    edx, edx
0x18003c52c  jz      short loc_18003C555
0x18003c52e  mov     eax, ebx
0x18003c530  mov     r8, [rcx+rax*8]
0x18003c534  test    r8, r8
0x18003c537  jz      short loc_18003C54F
0x18003c539  mov     rcx, r8; pv
0x18003c53c  call    cs:__imp_CoTaskMemFree
0x18003c543  nop     dword ptr [rax+rax+00h]
0x18003c548  mov     edx, [rbp+4Fh+var_B8]
0x18003c54b  mov     rcx, [rbp+4Fh+pv]; pv
0x18003c54f  inc     ebx
0x18003c551  cmp     ebx, edx
0x18003c553  jb      short loc_18003C52E
0x18003c555  call    cs:__imp_CoTaskMemFree
0x18003c55c  nop     dword ptr [rax+rax+00h]
0x18003c561  mov     [rbp+4Fh+pv], r15
0x18003c565  mov     [rbp+4Fh+var_B8], r15d
0x18003c569  lea     rcx, [rbp+4Fh+var_B0]
0x18003c56d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c572  xor     eax, eax
0x18003c574  add     rsp, 0C8h
0x18003c57b  pop     r15
0x18003c57d  pop     r14
0x18003c57f  pop     r13
0x18003c581  pop     r12
0x18003c583  pop     rdi
0x18003c584  pop     rsi
0x18003c585  pop     rbx
0x18003c586  pop     rbp
0x18003c587  retn
```
