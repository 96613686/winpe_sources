# UniSession::GetFolderSnapshotLegacy(RpcEnumType,ushort const *,ulong,wmi::AutoRef<RpcFolderSnapshot> &)

- ea: `0x180039078`
- end: `0x180039456`
- name: `?GetFolderSnapshotLegacy@UniSession@@IEBAJW4RpcEnumType@@PEBGKAEAV?$AutoRef@VRpcFolderSnapshot@@@wmi@@@Z`
- size: `990`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c3e0`
- `0x18001f130`
- `0x18001f350`

## callees

- `0x1800017f0`
- `0x180007aa0`
- `0x180009a30`
- `0x18000c750`
- `0x18000c77c`
- `0x18000ca30`
- `0x180026870`
- `0x180036290`
- `0x180039078`
- `0x18003b51c`
- `0x180048b4c`
- `0x180049ad8`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039429`

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
          v46 = &qword_180077320;
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
        v46 = &qword_180077320;
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
0x180039078  push    rbp
0x18003907a  push    rbx
0x18003907b  push    rsi
0x18003907c  push    rdi
0x18003907d  push    r12
0x18003907f  push    r13
0x180039081  push    r14
0x180039083  push    r15
0x180039085  lea     rbp, [rsp-17h]
0x18003908a  sub     rsp, 0C8h
0x180039091  cmp     edx, 1
0x180039094  jz      short loc_1800390A0
0x180039096  mov     eax, 80070032h
0x18003909b  jmp     loc_180039442
0x1800390a0  xor     r15d, r15d
0x1800390a3  test    r8, r8
0x1800390a6  jz      short loc_1800390C5
0x1800390a8  cmp     word ptr [r8], 5Ch ; '\'
0x1800390ad  jnz     short loc_1800390B5
0x1800390af  add     r8, 2
0x1800390b3  jz      short loc_1800390C5
0x1800390b5  cmp     [r8], r15w
0x1800390b9  jz      short loc_1800390C5
0x1800390bb  mov     eax, 80070003h
0x1800390c0  jmp     loc_180039442
0x1800390c5  mov     [rbp+4Fh+var_B0], r15
0x1800390c9  mov     rcx, [rcx+10h]
0x1800390cd  mov     rax, [rcx]
0x1800390d0  lea     rdx, [rbp+4Fh+var_B0]
0x1800390d4  mov     rax, [rax+28h]
0x1800390d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390dd  mov     ebx, eax
0x1800390df  test    eax, eax
0x1800390e1  jns     short loc_1800390F3
0x1800390e3  lea     rcx, [rbp+4Fh+var_B0]
0x1800390e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800390ec  mov     eax, ebx
0x1800390ee  jmp     loc_180039442
0x1800390f3  mov     [rbp+4Fh+pv], r15
0x1800390f7  mov     [rbp+4Fh+var_B8], r15d
0x1800390fb  mov     rcx, [rbp+4Fh+var_B0]
0x1800390ff  mov     rax, [rcx]
0x180039102  lea     r9, [rbp+4Fh+var_B8]
0x180039106  lea     r8, [rbp+4Fh+pv]
0x18003910a  or      r12d, 0FFFFFFFFh
0x18003910e  mov     edx, r12d
0x180039111  mov     rax, [rax+18h]
0x180039115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003911a  mov     edi, eax
0x18003911c  test    eax, eax
0x18003911e  jns     short loc_180039172
0x180039120  mov     rcx, [rbp+4Fh+pv]
0x180039124  test    rcx, rcx
0x180039127  jz      short loc_18003915A
0x180039129  mov     ebx, r15d
0x18003912c  mov     edx, [rbp+4Fh+var_B8]
0x18003912f  test    edx, edx
0x180039131  jz      short loc_180039154
0x180039133  mov     eax, ebx
0x180039135  mov     r8, [rcx+rax*8]
0x180039139  test    r8, r8
0x18003913c  jz      short loc_18003914E
0x18003913e  mov     rcx, r8; pv
0x180039141  call    cs:__imp_CoTaskMemFree
0x180039147  mov     edx, [rbp+4Fh+var_B8]
0x18003914a  mov     rcx, [rbp+4Fh+pv]; pv
0x18003914e  inc     ebx
0x180039150  cmp     ebx, edx
0x180039152  jb      short loc_180039133
0x180039154  call    cs:__imp_CoTaskMemFree
0x18003915a  mov     [rbp+4Fh+pv], r15
0x18003915e  mov     [rbp+4Fh+var_B8], r15d
0x180039162  lea     rcx, [rbp+4Fh+var_B0]
0x180039166  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003916b  mov     eax, edi
0x18003916d  jmp     loc_180039442
0x180039172  mov     eax, [rbp+4Fh+var_B8]
0x180039175  test    eax, eax
0x180039177  jnz     short loc_1800391E5
0x180039179  lea     ecx, [rax+30h]; unsigned __int64
0x18003917c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039181  mov     [rbp+4Fh+var_A8], rax
0x180039185  test    rax, rax
0x180039188  jz      short loc_180039194
0x18003918a  mov     rcx, rax; this
0x18003918d  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x180039192  jmp     short loc_180039197
0x180039194  mov     rax, r15
0x180039197  mov     rdx, rax
0x18003919a  mov     rcx, [rbp+4Fh+arg_20]
0x18003919e  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x1800391a3  nop
0x1800391a4  mov     rcx, [rbp+4Fh+pv]
0x1800391a8  test    rcx, rcx
0x1800391ab  jz      loc_18003942F
0x1800391b1  mov     ebx, r15d
0x1800391b4  mov     edx, [rbp+4Fh+var_B8]
0x1800391b7  test    edx, edx
0x1800391b9  jz      loc_180039429
0x1800391bf  mov     eax, ebx
0x1800391c1  mov     r8, [rcx+rax*8]
0x1800391c5  test    r8, r8
0x1800391c8  jz      short loc_1800391DA
0x1800391ca  mov     rcx, r8; pv
0x1800391cd  call    cs:__imp_CoTaskMemFree
0x1800391d3  mov     edx, [rbp+4Fh+var_B8]
0x1800391d6  mov     rcx, [rbp+4Fh+pv]
0x1800391da  inc     ebx
0x1800391dc  cmp     ebx, edx
0x1800391de  jb      short loc_1800391BF
0x1800391e0  jmp     loc_180039429
0x1800391e5  mov     rbx, rax
0x1800391e8  shl     rbx, 3
0x1800391ec  mov     edi, r15d
0x1800391ef  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800391f3  cmp     edi, eax
0x1800391f5  jnb     short loc_180039275
0x1800391f7  mov     edx, edi
0x1800391f9  lea     rcx, [rbp+4Fh+pv]
0x1800391fd  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x180039202  mov     rcx, rsi
0x180039205  inc     rcx
0x180039208  cmp     [rax+rcx*2], r15w
0x18003920d  jnz     short loc_180039205
0x18003920f  lea     rcx, ds:0FFFFFFFFFFFFFFFAh[rcx*2]
0x180039217  lea     rax, [rcx+3]
0x18003921b  and     rax, 0FFFFFFFFFFFFFFFCh
0x18003921f  add     rcx, rax
0x180039222  add     rcx, rbx
0x180039225  cmp     rcx, rbx
0x180039228  jb      short loc_180039234
0x18003922a  mov     rbx, rcx
0x18003922d  inc     edi
0x18003922f  mov     eax, [rbp+4Fh+var_B8]
0x180039232  jmp     short loc_1800391F3
0x180039234  mov     [rbp+4Fh+var_88], r15b
0x180039238  lea     rax, qword_180077320
0x18003923f  mov     [rbp+4Fh+var_80], rax
0x180039243  mov     [rbp+4Fh+var_78], r15
0x180039247  mov     [rbp+4Fh+var_70], r15
0x18003924b  mov     [rbp+4Fh+var_68], 0Eh
0x180039252  mov     [rbp+4Fh+var_64], r12d
0x180039256  mov     [rbp+4Fh+var_60], esi
0x180039259  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180039260  mov     [rbp+4Fh+pExceptionObject], rax
0x180039264  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003926b  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003926f  call    _CxxThrowException_0
0x180039275  mov     ecx, 30h ; '0'; unsigned __int64
0x18003927a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003927f  mov     [rbp+4Fh+var_A8], rax
0x180039283  test    rax, rax
0x180039286  jz      short loc_180039295
0x180039288  mov     rcx, rax; this
0x18003928b  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x180039290  mov     rdi, rax
0x180039293  jmp     short loc_180039298
0x180039295  mov     rdi, r15
0x180039298  mov     [rbp+4Fh+var_A8], rdi
0x18003929c  test    rdi, rdi
0x18003929f  jz      short loc_1800392A5
0x1800392a1  lock inc dword ptr [rdi+8]
0x1800392a5  mov     [rbp+4Fh+var_50], r15d
0x1800392a9  mov     rcx, rbx; size
0x1800392ac  call    MIDL_user_allocate
0x1800392b1  mov     r14, rax
0x1800392b4  mov     [rbp+4Fh+var_58], rax
0x1800392b8  test    rax, rax
0x1800392bb  jnz     short loc_1800392FE
0x1800392bd  mov     [rbp+4Fh+var_88], r15b
0x1800392c1  lea     rax, qword_180077320
0x1800392c8  mov     [rbp+4Fh+var_80], rax
0x1800392cc  mov     [rbp+4Fh+var_78], r15
0x1800392d0  mov     [rbp+4Fh+var_70], r15
0x1800392d4  mov     [rbp+4Fh+var_68], 0Eh
0x1800392db  mov     [rbp+4Fh+var_64], r12d
0x1800392df  mov     [rbp+4Fh+var_60], esi
0x1800392e2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800392e9  mov     [rbp+4Fh+pExceptionObject], rax
0x1800392ed  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800392f4  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800392f8  call    _CxxThrowException_0
0x1800392fe  mov     r12d, [rbp+4Fh+var_B8]
0x180039302  mov     [rbp+4Fh+var_50], r12d
0x180039306  lea     eax, ds:0[r12*8]
0x18003930e  mov     ecx, eax
0x180039310  lea     r13, [rax+r14]
0x180039314  sub     rbx, rcx
0x180039317  shr     rbx, 1
0x18003931a  mov     esi, r15d
0x18003931d  test    r12d, r12d
0x180039320  jz      loc_1800393C8
0x180039326  mov     [rbp+4Fh+var_A0], r15
0x18003932a  mov     [rbp+4Fh+var_98], r15
0x18003932e  mov     edx, esi
0x180039330  lea     rcx, [rbp+4Fh+pv]
0x180039334  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x180039339  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003933d  xor     ecx, ecx
0x18003933f  inc     r15
0x180039342  cmp     [rax+r15*2], cx
0x180039347  jnz     short loc_18003933F
0x180039349  mov     edx, esi
0x18003934b  lea     rcx, [rbp+4Fh+pv]
0x18003934f  call    ??A?$CoTaskMemAutoArrayPtr@PEAG@tsched@@QEAAPEAGK@Z; tsched::CoTaskMemAutoArrayPtr<ushort *>::operator[](ulong)
0x180039354  lea     r9, [r15-4]; unsigned __int64
0x180039358  lea     rcx, [rbp+4Fh+var_98]
0x18003935c  mov     [rsp+100h+var_D8], rcx; unsigned __int64 *
0x180039361  lea     rcx, [rbp+4Fh+var_A0]
0x180039365  mov     [rsp+100h+var_E0], rcx; unsigned __int16 **
0x18003936a  mov     r8, rax; unsigned __int16 *
0x18003936d  mov     rdx, rbx; unsigned __int64
0x180039370  mov     rcx, r13; unsigned __int16 *
0x180039373  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180039378  xor     r15d, r15d
0x18003937b  test    eax, eax
0x18003937d  js      short loc_1800393C8
0x18003937f  mov     eax, esi
0x180039381  mov     [r14+rax*8], r13
0x180039385  mov     rdx, [rbp+4Fh+var_A0]
0x180039389  add     rdx, 2
0x18003938d  mov     rbx, [rbp+4Fh+var_98]
0x180039391  test    rbx, rbx
0x180039394  jz      short loc_180039399
0x180039396  dec     rbx
0x180039399  mov     rcx, rdx
0x18003939c  sub     rcx, r13
0x18003939f  sar     rcx, 1
0x1800393a2  lea     eax, [rcx+3]
0x1800393a5  and     eax, 0FFFFFFFCh
0x1800393a8  sub     eax, ecx
0x1800393aa  mov     ecx, eax
0x1800393ac  lea     r13, [rdx+rax*2]
0x1800393b0  cmp     rbx, rcx
0x1800393b3  jbe     short loc_1800393BA
0x1800393b5  sub     rbx, rcx
0x1800393b8  jmp     short loc_1800393BD
0x1800393ba  mov     rbx, r15
0x1800393bd  inc     esi
0x1800393bf  cmp     esi, r12d
0x1800393c2  jb      loc_180039326
0x1800393c8  lea     rdx, [rbp+4Fh+var_58]
0x1800393cc  mov     rcx, rdi
0x1800393cf  call    ?AddBatch@RpcFolderSnapshot@@AEAAXAEAV?$RpcArray@PEBG@@@Z; RpcFolderSnapshot::AddBatch(RpcArray<ushort const *> &)
0x1800393d4  mov     rdx, rdi
0x1800393d7  mov     rcx, [rbp+4Fh+arg_20]
0x1800393db  call    ??4?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAAEAV01@PEAVRpcFolderSnapshot@@@Z; wmi::AutoRef<RpcFolderSnapshot>::operator=(RpcFolderSnapshot *)
0x1800393e0  nop
0x1800393e1  mov     rcx, [rbp+4Fh+var_58]; void *
0x1800393e5  call    MIDL_user_free
0x1800393ea  nop
0x1800393eb  lea     rcx, [rbp+4Fh+var_A8]
0x1800393ef  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x1800393f4  nop
0x1800393f5  mov     rcx, [rbp+4Fh+pv]
0x1800393f9  test    rcx, rcx
0x1800393fc  jz      short loc_18003942F
0x1800393fe  mov     ebx, r15d
0x180039401  mov     edx, [rbp+4Fh+var_B8]
0x180039404  test    edx, edx
0x180039406  jz      short loc_180039429
0x180039408  mov     eax, ebx
0x18003940a  mov     r8, [rcx+rax*8]
0x18003940e  test    r8, r8
0x180039411  jz      short loc_180039423
0x180039413  mov     rcx, r8; pv
0x180039416  call    cs:__imp_CoTaskMemFree
0x18003941c  mov     edx, [rbp+4Fh+var_B8]
0x18003941f  mov     rcx, [rbp+4Fh+pv]; pv
0x180039423  inc     ebx
0x180039425  cmp     ebx, edx
0x180039427  jb      short loc_180039408
0x180039429  call    cs:__imp_CoTaskMemFree
0x18003942f  mov     [rbp+4Fh+pv], r15
0x180039433  mov     [rbp+4Fh+var_B8], r15d
0x180039437  lea     rcx, [rbp+4Fh+var_B0]
0x18003943b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039440  xor     eax, eax
0x180039442  add     rsp, 0C8h
0x180039449  pop     r15
0x18003944b  pop     r14
0x18003944d  pop     r13
0x18003944f  pop     r12
0x180039451  pop     rdi
0x180039452  pop     rsi
0x180039453  pop     rbx
0x180039454  pop     rbp
0x180039455  retn
```
