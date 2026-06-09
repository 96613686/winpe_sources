# MimeParseAddress(char const *,tagADDRESSLIST *)

- ea: `0x18005d7a0`
- end: `0x18005db9c`
- name: `?MimeParseAddress@@YAJPEBDPEAUtagADDRESSLIST@@@Z`
- size: `1020`
- prototype: `int(const char *, struct tagADDRESSLIST *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005d4c4`

## callees

- `0x180008ee8`
- `0x18005d7a0`
- `0x18005dba4`
- `0x18005e048`
- `0x18005f38c`
- `0x1800977ac`
- `0x1800977b8`
- `0x180098323`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d818`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d818`

## pseudocode

```c
__int64 __fastcall MimeParseAddress(const char *a1, struct tagADDRESSLIST *a2)
{
  int v4; // r15d
  HRESULT v5; // ebx
  __int64 v6; // rcx
  unsigned int v7; // r14d
  unsigned int v8; // r12d
  void *v9; // rax
  __int64 v10; // r13
  __int64 v11; // rbx
  char *v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rsi
  char *v15; // rax
  __int64 v16; // r10
  _BYTE *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rsi
  char *v20; // rax
  __int64 v21; // r10
  __int64 v22; // rdx
  __int64 v24; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  __int64 v26; // [rsp+40h] [rbp-20h] BYREF
  __int64 v27; // [rsp+48h] [rbp-18h] BYREF
  __int64 v28; // [rsp+50h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-8h] BYREF
  size_t Size; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v31; // [rsp+B0h] [rbp+50h] BYREF
  char *v32; // [rsp+B8h] [rbp+58h] BYREF

  ppv = 0;
  v26 = 0;
  v4 = 0;
  v28 = 0;
  v27 = 0;
  v31 = 0;
  v24 = 0;
  v32 = 0;
  pv = 0;
  if ( !a1 || !a2 )
  {
    v5 = -2147024809;
LABEL_40:
    MimeFreeAddressList(a2);
    v6 = v24;
    goto LABEL_41;
  }
  *(_OWORD *)a2 = 0;
  v5 = CoCreateInstance(&CLSID_MIMEEntity, 0, 0x17u, &GUID_b3c11a6c_7392_446f_9e46_a30689d04a1b, &ppv);
  if ( v5 < 0 )
    goto LABEL_40;
  v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
         ppv,
         &GUID_84f8551b_83c6_47fd_8bb1_41b7e12b9df9,
         &v28);
  if ( v5 < 0 )
    goto LABEL_40;
  v5 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, __int64 *))(*(_QWORD *)v28 + 32LL))(v28, "To", 0, &v26);
  if ( v5 < 0 )
    goto LABEL_40;
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v26)(
         v26,
         &GUID_67708261_6a1c_4689_b758_dcdbf6aa7dbf,
         &v27);
  if ( v5 < 0 )
    goto LABEL_40;
  v5 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v27 + 24LL))(v27, a1, 3);
  if ( v5 < 0 )
    goto LABEL_40;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, &v24);
  if ( v5 < 0 )
    goto LABEL_40;
  v6 = v24;
  v7 = 0;
  if ( v24 )
  {
    while ( 1 )
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IMIMEMailBox, &v31);
      if ( v5 < 0 )
        goto LABEL_40;
      v4 = 1;
      v5 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v31 + 136LL))(v31, &v32);
      if ( v5 < 0 )
        goto LABEL_40;
      v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v31 + 144LL))(v31, &pv);
      if ( v5 < 0 )
        goto LABEL_40;
      v8 = *(_DWORD *)a2 + 1;
      if ( v8 < *(_DWORD *)a2 )
        goto LABEL_38;
      if ( v8 > v7 )
      {
        LODWORD(Size) = 0;
        if ( v7 + 5 < v7 )
        {
LABEL_38:
          v5 = -2147024362;
          goto LABEL_40;
        }
        v5 = ULongLongToULong(16LL * (v7 + 5), (unsigned int *)&Size);
        if ( v5 < 0 )
          goto LABEL_40;
        v9 = realloc_0(*((void **)a2 + 1), (unsigned int)Size);
        if ( !v9 )
        {
          v5 = -2147024882;
          goto LABEL_40;
        }
        v7 += 5;
        *((_QWORD *)a2 + 1) = v9;
      }
      v10 = *((_QWORD *)a2 + 1);
      v11 = 2LL * *(unsigned int *)a2;
      *(_OWORD *)(v10 + 16LL * *(unsigned int *)a2) = 0;
      v12 = v32;
      if ( v32 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v32[v13] );
        v14 = v13 + 1;
        v15 = (char *)operator new[](v13 + 1);
        if ( !v15 )
        {
LABEL_37:
          v5 = -2147024882;
          goto LABEL_40;
        }
        StringCchCopyA(v15, v14, v32);
        *(_QWORD *)(v10 + 8 * v11 + 8) = v16;
        v12 = v32;
      }
      v17 = pv;
      if ( !*(_BYTE *)pv )
      {
        CoTaskMemFree(pv);
        v12 = v32;
        v4 = 0;
        v17 = v32;
        pv = v32;
      }
      if ( v17 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        v19 = v18 + 1;
        v20 = (char *)operator new[](v18 + 1);
        if ( !v20 )
          goto LABEL_37;
        StringCchCopyA(v20, v19, (const char *)pv);
        *(_QWORD *)(v10 + 8 * v11) = v21;
        v12 = v32;
      }
      CoTaskMemFree(v12);
      v32 = 0;
      if ( v4 )
      {
        CoTaskMemFree(pv);
        pv = 0;
        v4 = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, &v24);
      if ( v5 < 0 )
        goto LABEL_40;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v6 = v24;
      v22 = 0;
      v31 = 0;
      *(_DWORD *)a2 = v8;
      if ( !v6 )
        goto LABEL_42;
    }
  }
LABEL_41:
  v22 = v31;
LABEL_42:
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v22 = v31;
    v24 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v31 = 0;
  }
  CoTaskMemFree(v32);
  if ( v4 )
    CoTaskMemFree(pv);
  operator delete(0);
  operator delete(0);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v27);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v28);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v26);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005d7a0  mov     [rsp-38h+arg_8], rbx
0x18005d7a5  push    rbp
0x18005d7a6  push    rsi
0x18005d7a7  push    rdi
0x18005d7a8  push    r12
0x18005d7aa  push    r13
0x18005d7ac  push    r14
0x18005d7ae  push    r15
0x18005d7b0  mov     rbp, rsp
0x18005d7b3  sub     rsp, 60h
0x18005d7b7  xor     r13d, r13d
0x18005d7ba  mov     rdi, rdx
0x18005d7bd  mov     [rbp+var_8], r13
0x18005d7c1  mov     rsi, rcx
0x18005d7c4  mov     [rbp+var_20], r13
0x18005d7c8  mov     r15d, r13d
0x18005d7cb  mov     [rbp+var_10], r13
0x18005d7cf  mov     [rbp+var_18], r13
0x18005d7d3  mov     [rbp+arg_10], r13
0x18005d7d7  mov     [rbp+var_30], r13
0x18005d7db  mov     [rbp+arg_18], r13
0x18005d7df  mov     [rbp+pv], r13
0x18005d7e3  test    rcx, rcx
0x18005d7e6  jz      loc_18005DAF1
0x18005d7ec  test    rdx, rdx
0x18005d7ef  jz      loc_18005DAF1
0x18005d7f5  xorps   xmm0, xmm0
0x18005d7f8  lea     rax, [rbp+var_8]
0x18005d7fc  movups  xmmword ptr [rdx], xmm0
0x18005d7ff  xor     edx, edx; pUnkOuter
0x18005d801  mov     [rsp+60h+ppv], rax; ppv
0x18005d806  lea     r9, _GUID_b3c11a6c_7392_446f_9e46_a30689d04a1b; riid
0x18005d80d  lea     r8d, [r13+17h]; dwClsContext
0x18005d811  lea     rcx, CLSID_MIMEEntity; rclsid
0x18005d818  call    cs:__imp_CoCreateInstance
0x18005d81e  mov     ebx, eax
0x18005d820  test    eax, eax
0x18005d822  js      loc_18005DAF6
0x18005d828  mov     rcx, [rbp+var_8]
0x18005d82c  lea     r8, [rbp+var_10]
0x18005d830  lea     rdx, _GUID_84f8551b_83c6_47fd_8bb1_41b7e12b9df9
0x18005d837  mov     rax, [rcx]
0x18005d83a  mov     rax, [rax]
0x18005d83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d842  mov     ebx, eax
0x18005d844  test    eax, eax
0x18005d846  js      loc_18005DAF6
0x18005d84c  mov     rcx, [rbp+var_10]
0x18005d850  lea     r9, [rbp+var_20]
0x18005d854  xor     r8d, r8d
0x18005d857  lea     rdx, aTo; "To"
0x18005d85e  mov     rax, [rcx]
0x18005d861  mov     rax, [rax+20h]
0x18005d865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d86a  mov     ebx, eax
0x18005d86c  test    eax, eax
0x18005d86e  js      loc_18005DAF6
0x18005d874  mov     rcx, [rbp+var_20]
0x18005d878  lea     r8, [rbp+var_18]
0x18005d87c  lea     rdx, _GUID_67708261_6a1c_4689_b758_dcdbf6aa7dbf
0x18005d883  mov     rax, [rcx]
0x18005d886  mov     rax, [rax]
0x18005d889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d88e  mov     ebx, eax
0x18005d890  test    eax, eax
0x18005d892  js      loc_18005DAF6
0x18005d898  mov     rcx, [rbp+var_18]
0x18005d89c  lea     r8d, [r13+3]
0x18005d8a0  mov     rdx, rsi
0x18005d8a3  mov     rax, [rcx]
0x18005d8a6  mov     rax, [rax+18h]
0x18005d8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8af  mov     ebx, eax
0x18005d8b1  test    eax, eax
0x18005d8b3  js      loc_18005DAF6
0x18005d8b9  mov     rcx, [rbp+var_20]
0x18005d8bd  lea     rdx, [rbp+var_30]
0x18005d8c1  mov     rax, [rcx]
0x18005d8c4  mov     rax, [rax+20h]
0x18005d8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8cd  mov     ebx, eax
0x18005d8cf  test    eax, eax
0x18005d8d1  js      loc_18005DAF6
0x18005d8d7  mov     rcx, [rbp+var_30]
0x18005d8db  mov     r14d, r13d
0x18005d8de  test    rcx, rcx
0x18005d8e1  jz      loc_18005DB02
0x18005d8e7  mov     rax, [rcx]
0x18005d8ea  lea     r8, [rbp+arg_10]
0x18005d8ee  lea     rdx, IID_IMIMEMailBox
0x18005d8f5  mov     rax, [rax]
0x18005d8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8fd  mov     ebx, eax
0x18005d8ff  test    eax, eax
0x18005d901  js      loc_18005DAF6
0x18005d907  mov     rcx, [rbp+arg_10]
0x18005d90b  lea     rdx, [rbp+arg_18]
0x18005d90f  mov     r15d, 1
0x18005d915  mov     rax, [rcx]
0x18005d918  mov     rax, [rax+88h]
0x18005d91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d924  mov     ebx, eax
0x18005d926  test    eax, eax
0x18005d928  js      loc_18005DAF6
0x18005d92e  mov     rcx, [rbp+arg_10]
0x18005d932  lea     rdx, [rbp+pv]
0x18005d936  mov     rax, [rcx]
0x18005d939  mov     rax, [rax+90h]
0x18005d940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d945  mov     ebx, eax
0x18005d947  test    eax, eax
0x18005d949  js      loc_18005DAF6
0x18005d94f  mov     eax, [rdi]
0x18005d951  lea     r12d, [rax+1]
0x18005d955  cmp     r12d, eax
0x18005d958  jb      loc_18005DAEA
0x18005d95e  cmp     r12d, r14d
0x18005d961  jbe     short loc_18005D9A9
0x18005d963  lea     esi, [r14+5]
0x18005d967  mov     dword ptr [rbp+Size], r13d
0x18005d96b  cmp     esi, r14d
0x18005d96e  jb      loc_18005DAEA
0x18005d974  mov     ecx, esi
0x18005d976  lea     rdx, [rbp+Size]; unsigned int *
0x18005d97a  shl     rcx, 4; unsigned __int64
0x18005d97e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005d983  mov     ebx, eax
0x18005d985  test    eax, eax
0x18005d987  js      loc_18005DAF6
0x18005d98d  mov     edx, dword ptr [rbp+Size]; Size
0x18005d990  mov     rcx, [rdi+8]; Block
0x18005d994  call    realloc_0
0x18005d999  test    rax, rax
0x18005d99c  jz      loc_18005DAD9
0x18005d9a2  mov     r14d, esi
0x18005d9a5  mov     [rdi+8], rax
0x18005d9a9  mov     ebx, [rdi]
0x18005d9ab  xorps   xmm0, xmm0
0x18005d9ae  mov     r13, [rdi+8]
0x18005d9b2  add     rbx, rbx
0x18005d9b5  movups  xmmword ptr [r13+rbx*8+0], xmm0
0x18005d9bb  mov     rcx, [rbp+arg_18]
0x18005d9bf  test    rcx, rcx
0x18005d9c2  jz      short loc_18005DA01
0x18005d9c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005d9c8  inc     rax
0x18005d9cb  cmp     byte ptr [rcx+rax], 0
0x18005d9cf  jnz     short loc_18005D9C8
0x18005d9d1  lea     rsi, [rax+1]
0x18005d9d5  mov     rcx, rsi; unsigned __int64
0x18005d9d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005d9dd  mov     r10, rax
0x18005d9e0  test    rax, rax
0x18005d9e3  jz      loc_18005DAE0
0x18005d9e9  mov     r8, [rbp+arg_18]; char *
0x18005d9ed  mov     rdx, rsi; unsigned __int64
0x18005d9f0  mov     rcx, rax; char *
0x18005d9f3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005d9f8  mov     [r13+rbx*8+8], r10
0x18005d9fd  mov     rcx, [rbp+arg_18]
0x18005da01  mov     rax, [rbp+pv]
0x18005da05  cmp     byte ptr [rax], 0
0x18005da08  jnz     short loc_18005DA21
0x18005da0a  mov     rcx, rax; pv
0x18005da0d  call    cs:__imp_CoTaskMemFree
0x18005da13  mov     rcx, [rbp+arg_18]
0x18005da17  xor     r15d, r15d
0x18005da1a  mov     rax, rcx
0x18005da1d  mov     [rbp+pv], rcx
0x18005da21  test    rax, rax
0x18005da24  jz      short loc_18005DA63
0x18005da26  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005da2a  inc     rcx
0x18005da2d  cmp     byte ptr [rax+rcx], 0
0x18005da31  jnz     short loc_18005DA2A
0x18005da33  lea     rsi, [rcx+1]
0x18005da37  mov     rcx, rsi; unsigned __int64
0x18005da3a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005da3f  mov     r10, rax
0x18005da42  test    rax, rax
0x18005da45  jz      loc_18005DAE0
0x18005da4b  mov     r8, [rbp+pv]; char *
0x18005da4f  mov     rdx, rsi; unsigned __int64
0x18005da52  mov     rcx, rax; char *
0x18005da55  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005da5a  mov     [r13+rbx*8+0], r10
0x18005da5f  mov     rcx, [rbp+arg_18]; pv
0x18005da63  call    cs:__imp_CoTaskMemFree
0x18005da69  xor     r13d, r13d
0x18005da6c  mov     [rbp+arg_18], r13
0x18005da70  test    r15d, r15d
0x18005da73  jz      short loc_18005DA86
0x18005da75  mov     rcx, [rbp+pv]; pv
0x18005da79  call    cs:__imp_CoTaskMemFree
0x18005da7f  mov     [rbp+pv], r13
0x18005da83  mov     r15d, r13d
0x18005da86  mov     rcx, [rbp+var_30]
0x18005da8a  mov     rax, [rcx]
0x18005da8d  mov     rax, [rax+10h]
0x18005da91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da96  mov     rcx, [rbp+arg_10]
0x18005da9a  lea     rdx, [rbp+var_30]
0x18005da9e  mov     rax, [rcx]
0x18005daa1  mov     rax, [rax+30h]
0x18005daa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daaa  mov     ebx, eax
0x18005daac  test    eax, eax
0x18005daae  js      short loc_18005DAF6
0x18005dab0  mov     rcx, [rbp+arg_10]
0x18005dab4  mov     rax, [rcx]
0x18005dab7  mov     rax, [rax+10h]
0x18005dabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dac0  mov     rcx, [rbp+var_30]
0x18005dac4  mov     rdx, r13
0x18005dac7  mov     [rbp+arg_10], rdx
0x18005dacb  mov     [rdi], r12d
0x18005dace  test    rcx, rcx
0x18005dad1  jnz     loc_18005D8E7
0x18005dad7  jmp     short loc_18005DB06
0x18005dad9  mov     ebx, 8007000Eh
0x18005dade  jmp     short loc_18005DAF6
0x18005dae0  mov     ebx, 8007000Eh
0x18005dae5  xor     r13d, r13d
0x18005dae8  jmp     short loc_18005DAF6
0x18005daea  mov     ebx, 80070216h
0x18005daef  jmp     short loc_18005DAF6
0x18005daf1  mov     ebx, 80070057h
0x18005daf6  mov     rcx, rdi; struct tagADDRESSLIST *
0x18005daf9  call    ?MimeFreeAddressList@@YAJPEAUtagADDRESSLIST@@@Z; MimeFreeAddressList(tagADDRESSLIST *)
0x18005dafe  mov     rcx, [rbp+var_30]
0x18005db02  mov     rdx, [rbp+arg_10]
0x18005db06  test    rcx, rcx
0x18005db09  jz      short loc_18005DB1F
0x18005db0b  mov     rax, [rcx]
0x18005db0e  mov     rax, [rax+10h]
0x18005db12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db17  mov     rdx, [rbp+arg_10]
0x18005db1b  mov     [rbp+var_30], r13
0x18005db1f  test    rdx, rdx
0x18005db22  jz      short loc_18005DB37
0x18005db24  mov     rax, [rdx]
0x18005db27  mov     rcx, rdx
0x18005db2a  mov     rax, [rax+10h]
0x18005db2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db33  mov     [rbp+arg_10], r13
0x18005db37  mov     rcx, [rbp+arg_18]; pv
0x18005db3b  call    cs:__imp_CoTaskMemFree
0x18005db41  test    r15d, r15d
0x18005db44  jz      short loc_18005DB50
0x18005db46  mov     rcx, [rbp+pv]; pv
0x18005db4a  call    cs:__imp_CoTaskMemFree
0x18005db50  xor     ecx, ecx; Block
0x18005db52  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005db57  xor     ecx, ecx; Block
0x18005db59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005db5e  lea     rcx, [rbp+var_18]
0x18005db62  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005db67  lea     rcx, [rbp+var_10]
0x18005db6b  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005db70  lea     rcx, [rbp+var_20]
0x18005db74  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005db79  lea     rcx, [rbp+var_8]
0x18005db7d  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005db82  mov     eax, ebx
0x18005db84  mov     rbx, [rsp+60h+arg_8]
0x18005db8c  add     rsp, 60h
0x18005db90  pop     r15
0x18005db92  pop     r14
0x18005db94  pop     r13
0x18005db96  pop     r12
0x18005db98  pop     rdi
0x18005db99  pop     rsi
0x18005db9a  pop     rbp
0x18005db9b  retn
```
