# _lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()

- ea: `0x140071c5c`
- end: `0x140072136`
- name: `_lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()`
- size: `1242`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x14006fd90`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14001c804`
- `0x140060498`
- `0x140060e60`
- `0x140060f58`
- `0x140071c5c`
- `0x1400723b8`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071cba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071ef1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071f96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071cba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071ef1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140071f96`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rbx
  _WORD *v6; // rax
  char v7; // bl
  unsigned __int64 v8; // r8
  void *v9; // rcx
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rax
  int v16; // ebx
  _BYTE *v17; // rdx
  _WORD *v18; // rax
  void *v19; // rcx
  int v20; // ebx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, _WORD *, __int64); // rbx
  __int64 v23; // rax
  int v24; // ebx
  _BYTE *v25; // rcx
  bool v26; // bl
  _BYTE *v27; // rdx
  _WORD *v28; // rax
  void *v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // r8
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v33; // rcx
  int v35; // eax
  __int64 v36; // r10
  int v37; // eax
  __int64 v38; // r10
  int v39; // eax
  __int64 v40; // r10
  int v41; // eax
  __int64 v42; // r10
  _WORD *pv; // [rsp+30h] [rbp-D0h]
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v48[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp-90h] BYREF
  void *v50; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v52; // [rsp+E0h] [rbp-20h]
  void *v53; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v54[56]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE *v55; // [rsp+130h] [rbp+30h]

  v48[0] = a2;
  v5 = lambda_d40de2733d855246ee074aa8c091e9f3_::operator()(*(_QWORD *)a1, v48, a3);
  v6 = *(_WORD **)v5;
  *(_QWORD *)v5 = 0;
  pv = v6;
  v7 = *(_BYTE *)(v5 + 8);
  if ( v48[0] )
    CoTaskMemFree(v48[0]);
  if ( !v7 )
  {
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 0;
    v8 = -1;
    do
      ++v8;
    while ( pv[v8] );
    std::wstring::_Construct<1,unsigned short const *>((char **)a2, pv, v8);
    v9 = pv;
LABEL_36:
    if ( v9 )
      CoTaskMemFree(v9);
    return a2;
  }
  v45 = 0;
  v47 = 0;
  v10 = (****(__int64 (__fastcall *****)(_QWORD, GUID *, __int64 *))(a1 + 8))(
          **(_QWORD **)(a1 + 8),
          &GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20,
          &v47);
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v37 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
      WPP_SF_Sd(*(_QWORD *)(v38 + 16), 44, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v37, v10);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v10);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v46 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD))(*(_QWORD *)v47 + 40LL))(v47, pv, &v46);
  v44 = 0;
  if ( v11 < 0 )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(***(_QWORD ***)(a1 + 24) + 72LL))(
            **(_QWORD **)(a1 + 24),
            &GUID_e3c22b30_8502_4b2f_9133_559674587e51,
            &v44);
    if ( v20 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v35 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
        WPP_SF_Sd(*(_QWORD *)(v36 + 16), 47, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v35, v20);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v20);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v21 = **(_QWORD **)(a1 + 8);
    v22 = *(__int64 (__fastcall **)(__int64, __int64, _WORD *, __int64))(*(_QWORD *)v21 + 48LL);
    v23 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v53, (__int64)&v45);
    v24 = v22(v21, v44, pv, v23);
    v25 = v55;
    if ( v55 )
    {
      v48[0] = v53;
      (*(void (__fastcall **)(_BYTE *, LPVOID *))(*(_QWORD *)v55 + 16LL))(v55, v48);
      v25 = v55;
    }
    v26 = v24 >= 0;
    if ( v25 )
    {
      v27 = v54;
      LOBYTE(v27) = v25 != v54;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v27);
    }
    if ( v26 )
    {
      v28 = v45;
      v45 = 0;
      v29 = pv;
      pv = v28;
      if ( v29 )
        CoTaskMemFree(v29);
    }
  }
  else
  {
    v12 = (**v46)(v46, &GUID_f98ce1cb_901b_41f4_bf42_83d51895e1e2, &v44);
    if ( v12 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v39 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
        WPP_SF_Sd(*(_QWORD *)(v40 + 16), 45, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v39, v12);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v13 = v44;
    v14 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 24LL);
    v15 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v50, (__int64)&v45);
    v16 = v14(v13, v15);
    if ( v52 )
    {
      v48[0] = v50;
      (*(void (__fastcall **)(_BYTE *, LPVOID *))(*(_QWORD *)v52 + 16LL))(v52, v48);
      if ( v52 )
      {
        v17 = v51;
        LOBYTE(v17) = v52 != v51;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v52 + 32LL))(v52, v17);
      }
    }
    if ( v16 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v41 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
        WPP_SF_Sd(*(_QWORD *)(v42 + 16), 46, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v41, v16);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v18 = v45;
    v45 = 0;
    v19 = pv;
    pv = v18;
    if ( v19 )
      CoTaskMemFree(v19);
  }
  v30 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 0;
  v31 = -1;
  do
    ++v31;
  while ( pv[v31] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, pv, v31);
  v32 = v46;
  if ( v46 )
  {
    v46 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
  }
  v33 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  if ( v45 )
    CoTaskMemFree(v45);
  v9 = pv;
  if ( pv )
    goto LABEL_36;
  return a2;
}

```

## disassembly

```asm
0x140071c5c  mov     [rsp-8+arg_18], rbx
0x140071c61  push    rbp
0x140071c62  push    rsi
0x140071c63  push    rdi
0x140071c64  push    r14
0x140071c66  push    r15
0x140071c68  lea     rbp, [rsp-50h]
0x140071c6d  sub     rsp, 150h
0x140071c74  mov     rax, cs:__security_cookie
0x140071c7b  xor     rax, rsp
0x140071c7e  mov     [rbp+70h+var_30], rax
0x140071c82  mov     rsi, rdx
0x140071c85  mov     r14, rcx
0x140071c88  mov     [rsp+170h+var_118], rdx
0x140071c8d  xor     r15d, r15d
0x140071c90  mov     [rsp+170h+pv], r15
0x140071c95  lea     rdx, [rsp+170h+var_118]
0x140071c9a  mov     rcx, [rcx]
0x140071c9d  call    _lambda_d40de2733d855246ee074aa8c091e9f3___operator__
0x140071ca2  mov     rbx, rax
0x140071ca5  mov     rax, [rax]
0x140071ca8  mov     [rbx], r15
0x140071cab  mov     rcx, [rsp+170h+pv]; pv
0x140071cb0  mov     [rsp+170h+pv], rax
0x140071cb5  test    rcx, rcx
0x140071cb8  jz      short loc_140071CC0
0x140071cba  call    cs:__imp_CoTaskMemFree
0x140071cc0  mov     bl, [rbx+8]
0x140071cc3  mov     rcx, [rsp+170h+var_118]; pv
0x140071cc8  test    rcx, rcx
0x140071ccb  jz      short loc_140071CD3
0x140071ccd  call    cs:__imp_CoTaskMemFree
0x140071cd3  test    bl, bl
0x140071cd5  jnz     short loc_140071D0B
0x140071cd7  mov     rdx, [rsp+170h+pv]
0x140071cdc  xorps   xmm0, xmm0
0x140071cdf  movups  xmmword ptr [rsi], xmm0
0x140071ce2  mov     [rsi+10h], r15
0x140071ce6  mov     [rsi+18h], r15
0x140071cea  or      r8, 0FFFFFFFFFFFFFFFFh
0x140071cee  inc     r8
0x140071cf1  cmp     [rdx+r8*2], r15w
0x140071cf6  jnz     short loc_140071CEE
0x140071cf8  mov     rcx, rsi
0x140071cfb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140071d00  nop
0x140071d01  mov     rcx, [rsp+170h+pv]
0x140071d06  jmp     loc_140071F91
0x140071d0b  mov     [rsp+170h+var_130], r15
0x140071d10  mov     [rsp+170h+var_120], r15
0x140071d15  mov     rax, [r14+8]
0x140071d19  mov     rcx, [rax]
0x140071d1c  mov     rax, [rcx]
0x140071d1f  lea     r8, [rsp+170h+var_120]
0x140071d24  lea     rdx, _GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20
0x140071d2b  mov     rax, [rax]
0x140071d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071d33  mov     ebx, eax
0x140071d35  test    eax, eax
0x140071d37  js      loc_14007201F
0x140071d3d  mov     [rsp+170h+var_128], r15
0x140071d42  mov     rcx, [rsp+170h+var_120]
0x140071d47  mov     rax, [rcx]
0x140071d4a  lea     r8, [rsp+170h+var_128]
0x140071d4f  mov     rdx, [rsp+170h+pv]
0x140071d54  mov     rax, [rax+28h]
0x140071d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071d5d  mov     [rsp+170h+var_138], r15
0x140071d62  test    eax, eax
0x140071d64  js      loc_140071E2B
0x140071d6a  mov     rcx, [rsp+170h+var_128]
0x140071d6f  mov     rax, [rcx]
0x140071d72  lea     r8, [rsp+170h+var_138]
0x140071d77  lea     rdx, _GUID_f98ce1cb_901b_41f4_bf42_83d51895e1e2
0x140071d7e  mov     rax, [rax]
0x140071d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071d86  mov     ebx, eax
0x140071d88  test    eax, eax
0x140071d8a  js      loc_14007207C
0x140071d90  mov     rdi, [rsp+170h+var_138]
0x140071d95  mov     rax, [rdi]
0x140071d98  mov     rbx, [rax+18h]
0x140071d9c  lea     rdx, [rsp+170h+var_130]
0x140071da1  lea     rcx, [rbp+70h+var_D0]
0x140071da5  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x140071daa  nop
0x140071dab  mov     rdx, rax
0x140071dae  mov     rcx, rdi
0x140071db1  mov     rax, rbx
0x140071db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071db9  mov     ebx, eax
0x140071dbb  mov     rcx, [rbp+70h+var_90]
0x140071dbf  test    rcx, rcx
0x140071dc2  jz      short loc_140071DFE
0x140071dc4  mov     rax, [rbp+70h+var_D0]
0x140071dc8  mov     [rsp+170h+var_118], rax
0x140071dcd  mov     rax, [rcx]
0x140071dd0  lea     rdx, [rsp+170h+var_118]
0x140071dd5  mov     rax, [rax+10h]
0x140071dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071dde  mov     rcx, [rbp+70h+var_90]
0x140071de2  test    rcx, rcx
0x140071de5  jz      short loc_140071DFE
0x140071de7  mov     rax, [rcx]
0x140071dea  lea     rdx, [rbp+70h+var_C8]
0x140071dee  cmp     rcx, rdx
0x140071df1  setnz   dl
0x140071df4  mov     rax, [rax+20h]
0x140071df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071dfd  nop
0x140071dfe  test    ebx, ebx
0x140071e00  js      loc_1400720D9
0x140071e06  mov     rax, [rsp+170h+var_130]
0x140071e0b  mov     [rsp+170h+var_130], r15
0x140071e10  mov     rcx, [rsp+170h+pv]; pv
0x140071e15  mov     [rsp+170h+pv], rax
0x140071e1a  test    rcx, rcx
0x140071e1d  jz      short loc_140071E26
0x140071e1f  call    cs:__imp_CoTaskMemFree
0x140071e25  nop
0x140071e26  jmp     loc_140071EF8
0x140071e2b  mov     rax, [r14+18h]
0x140071e2f  mov     rcx, [rax]
0x140071e32  mov     rax, [rcx]
0x140071e35  lea     r8, [rsp+170h+var_138]
0x140071e3a  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x140071e41  mov     rax, [rax+48h]
0x140071e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071e4a  mov     ebx, eax
0x140071e4c  test    eax, eax
0x140071e4e  js      loc_140071FC2
0x140071e54  mov     rax, [r14+8]
0x140071e58  mov     rdi, [rax]
0x140071e5b  mov     rax, [rdi]
0x140071e5e  mov     rbx, [rax+30h]
0x140071e62  lea     rdx, [rsp+170h+var_130]
0x140071e67  lea     rcx, [rbp+70h+var_80]
0x140071e6b  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x140071e70  nop
0x140071e71  mov     r9, rax
0x140071e74  mov     r8, [rsp+170h+pv]
0x140071e79  mov     rdx, [rsp+170h+var_138]
0x140071e7e  mov     rcx, rdi
0x140071e81  mov     rax, rbx
0x140071e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071e89  mov     ebx, eax
0x140071e8b  mov     rcx, [rbp+70h+var_40]
0x140071e8f  test    rcx, rcx
0x140071e92  jz      short loc_140071EB2
0x140071e94  mov     rax, [rbp+70h+var_80]
0x140071e98  mov     [rsp+170h+var_118], rax
0x140071e9d  mov     rax, [rcx]
0x140071ea0  lea     rdx, [rsp+170h+var_118]
0x140071ea5  mov     rax, [rax+10h]
0x140071ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071eae  mov     rcx, [rbp+70h+var_40]
0x140071eb2  shr     ebx, 1Fh
0x140071eb5  xor     bl, 1
0x140071eb8  test    rcx, rcx
0x140071ebb  jz      short loc_140071ED4
0x140071ebd  mov     rax, [rcx]
0x140071ec0  lea     rdx, [rbp+70h+var_78]
0x140071ec4  cmp     rcx, rdx
0x140071ec7  setnz   dl
0x140071eca  mov     rax, [rax+20h]
0x140071ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071ed3  nop
0x140071ed4  test    bl, bl
0x140071ed6  jz      short loc_140071EF8
0x140071ed8  mov     rax, [rsp+170h+var_130]
0x140071edd  mov     [rsp+170h+var_130], r15
0x140071ee2  mov     rcx, [rsp+170h+pv]; pv
0x140071ee7  mov     [rsp+170h+pv], rax
0x140071eec  test    rcx, rcx
0x140071eef  jz      short loc_140071EF8
0x140071ef1  call    cs:__imp_CoTaskMemFree
0x140071ef7  nop
0x140071ef8  mov     rcx, [rsp+170h+var_138]
0x140071efd  test    rcx, rcx
0x140071f00  jz      short loc_140071F14
0x140071f02  mov     [rsp+170h+var_138], r15
0x140071f07  mov     rax, [rcx]
0x140071f0a  mov     rax, [rax+10h]
0x140071f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071f13  nop
0x140071f14  mov     rdx, [rsp+170h+pv]
0x140071f19  xorps   xmm0, xmm0
0x140071f1c  movups  xmmword ptr [rsi], xmm0
0x140071f1f  mov     [rsi+10h], r15
0x140071f23  mov     [rsi+18h], r15
0x140071f27  or      r8, 0FFFFFFFFFFFFFFFFh
0x140071f2b  inc     r8
0x140071f2e  cmp     [rdx+r8*2], r15w
0x140071f33  jnz     short loc_140071F2B
0x140071f35  mov     rcx, rsi
0x140071f38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140071f3d  nop
0x140071f3e  mov     rcx, [rsp+170h+var_128]
0x140071f43  test    rcx, rcx
0x140071f46  jz      short loc_140071F5A
0x140071f48  mov     [rsp+170h+var_128], r15
0x140071f4d  mov     rax, [rcx]
0x140071f50  mov     rax, [rax+10h]
0x140071f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071f59  nop
0x140071f5a  mov     rcx, [rsp+170h+var_120]
0x140071f5f  test    rcx, rcx
0x140071f62  jz      short loc_140071F76
0x140071f64  mov     [rsp+170h+var_120], r15
0x140071f69  mov     rax, [rcx]
0x140071f6c  mov     rax, [rax+10h]
0x140071f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071f75  nop
0x140071f76  mov     rcx, [rsp+170h+var_130]; pv
0x140071f7b  test    rcx, rcx
0x140071f7e  jz      short loc_140071F87
0x140071f80  call    cs:__imp_CoTaskMemFree
0x140071f86  nop
0x140071f87  mov     rcx, [rsp+170h+pv]; pv
0x140071f8c  test    rcx, rcx
0x140071f8f  jz      short loc_140071F9C
0x140071f91  test    rcx, rcx
0x140071f94  jz      short loc_140071F9C
0x140071f96  call    cs:__imp_CoTaskMemFree
0x140071f9c  mov     rax, rsi
0x140071f9f  mov     rcx, [rbp+70h+var_30]
0x140071fa3  xor     rcx, rsp; StackCookie
0x140071fa6  call    __security_check_cookie
0x140071fab  mov     rbx, [rsp+170h+arg_18]
0x140071fb3  add     rsp, 150h
0x140071fba  pop     r15
0x140071fbc  pop     r14
0x140071fbe  pop     rdi
0x140071fbf  pop     rsi
0x140071fc0  pop     rbp
0x140071fc1  retn
0x140071fc2  lea     rax, WPP_GLOBAL_Control
0x140071fc9  mov     r10, cs:WPP_GLOBAL_Control
0x140071fd0  cmp     r10, rax
0x140071fd3  jz      short loc_140072001
0x140071fd5  test    byte ptr [r10+1Ch], 1
0x140071fda  jz      short loc_140072001
0x140071fdc  mov     rcx, [r14+10h]
0x140071fe0  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140071fe5  mov     edx, 2Fh ; '/'
0x140071fea  mov     [rsp+170h+var_150], ebx
0x140071fee  mov     r9, rax
0x140071ff1  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140071ff8  mov     rcx, [r10+10h]
0x140071ffc  call    WPP_SF_Sd
0x140072001  mov     edx, ebx; int
0x140072003  lea     rcx, [rsp+170h+pExceptionObject]; this
0x140072008  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007200d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140072014  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x140072019  call    _CxxThrowException_0
0x14007201f  lea     rax, WPP_GLOBAL_Control
0x140072026  mov     r10, cs:WPP_GLOBAL_Control
0x14007202d  cmp     r10, rax
0x140072030  jz      short loc_14007205E
0x140072032  test    byte ptr [r10+1Ch], 1
0x140072037  jz      short loc_14007205E
0x140072039  mov     rcx, [r14+10h]
0x14007203d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140072042  mov     edx, 2Ch ; ','
0x140072047  mov     [rsp+170h+var_150], ebx
0x14007204b  mov     r9, rax
0x14007204e  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140072055  mov     rcx, [r10+10h]
0x140072059  call    WPP_SF_Sd
0x14007205e  mov     edx, ebx; int
0x140072060  lea     rcx, [rsp+170h+pExceptionObject]; this
0x140072065  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007206a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140072071  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x140072076  call    _CxxThrowException_0
0x14007207c  lea     rax, WPP_GLOBAL_Control
0x140072083  mov     r10, cs:WPP_GLOBAL_Control
0x14007208a  cmp     r10, rax
0x14007208d  jz      short loc_1400720BB
0x14007208f  test    byte ptr [r10+1Ch], 1
0x140072094  jz      short loc_1400720BB
0x140072096  mov     rcx, [r14+10h]
0x14007209a  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14007209f  mov     edx, 2Dh ; '-'
0x1400720a4  mov     [rsp+170h+var_150], ebx
0x1400720a8  mov     r9, rax
0x1400720ab  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x1400720b2  mov     rcx, [r10+10h]
0x1400720b6  call    WPP_SF_Sd
0x1400720bb  mov     edx, ebx; int
0x1400720bd  lea     rcx, [rsp+170h+pExceptionObject]; this
0x1400720c2  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400720c7  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400720ce  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1400720d3  call    _CxxThrowException_0
0x1400720d9  lea     rax, WPP_GLOBAL_Control
0x1400720e0  mov     r10, cs:WPP_GLOBAL_Control
0x1400720e7  cmp     r10, rax
0x1400720ea  jz      short loc_140072118
  ... truncated ...
```
