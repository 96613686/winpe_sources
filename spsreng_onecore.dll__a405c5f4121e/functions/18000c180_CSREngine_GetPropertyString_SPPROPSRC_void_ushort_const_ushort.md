# CSREngine::GetPropertyString(SPPROPSRC,void *,ushort const *,ushort * *)

- ea: `0x18000c180`
- end: `0x18000c572`
- name: `?GetPropertyString@CSREngine@@UEAAJW4SPPROPSRC@@PEAXPEBGPEAPEAG@Z`
- size: `1010`
- prototype: `int(CSREngine *__hidden this, enum SPPROPSRC, void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002db8`
- `0x180004306`
- `0x180006abc`
- `0x18000c180`
- `0x1800140fc`
- `0x18004c4d8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c455`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c455`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSREngine::GetPropertyString(
        CSREngine *this,
        enum SPPROPSRC a2,
        void *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  unsigned int v7; // r12d
  struct CHeap *v9; // r15
  _QWORD *v10; // rsi
  unsigned __int64 v11; // rdi
  int v12; // ebx
  unsigned int v13; // r14d
  int v14; // eax
  void *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rax
  unsigned int i; // edi
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rcx
  unsigned int v23; // r15d
  const unsigned __int16 *v24; // r8
  unsigned int v26; // [rsp+28h] [rbp-59h]
  LPVOID pv; // [rsp+48h] [rbp-39h] BYREF
  __int64 v28; // [rsp+50h] [rbp-31h] BYREF
  __int64 v29; // [rsp+58h] [rbp-29h] BYREF
  __int64 v30; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-19h] BYREF
  HANDLE *v32; // [rsp+70h] [rbp-11h] BYREF
  void *v33; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v34[20]; // [rsp+80h] [rbp-1h] BYREF
  unsigned int v35; // [rsp+100h] [rbp+7Fh]

  v7 = 0;
  *a5 = 0;
  if ( !wcscmp_0(a4, L"LMList") )
  {
    v28 = 0;
    v30 = 0;
    v29 = 0;
    v9 = (struct CHeap *)&g_heap;
    v32 = &g_heap;
    v10 = 0;
    v33 = 0;
    *(_QWORD *)v34 = 0;
    pv = 0;
    v11 = 1;
    v31 = 1;
    v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(**((_QWORD **)this + 33) + 72LL))(
            *((_QWORD *)this + 33),
            L"LMs",
            &v28);
    v13 = 0;
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 72LL))(
                  v28,
                  L"Main",
                  &v30),
          v12 < 0)
      || (v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 72LL))(
                  v28,
                  L"AddOn",
                  &v29),
          v12 < 0) )
    {
      CGrowableArrayVoid::~CGrowableArrayVoid((CGrowableArrayVoid *)&v32);
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v29);
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v30);
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v28);
LABEL_48:
      CoTaskMemFree(*a5);
      *a5 = 0;
      return (unsigned int)v12;
    }
    while ( 1 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v30 + 112LL))(v30, v13, &pv);
      v12 = v14;
      if ( v14 == -2147200967 )
        break;
      if ( v14 < 0 )
        goto LABEL_28;
      v12 = EnsureArrayVoid(&v33, 8u, v13 + 1, v34, v7, v9);
      v15 = pv;
      if ( v12 < 0 )
      {
LABEL_15:
        CoTaskMemFree(v15);
        v10 = v33;
        goto LABEL_28;
      }
      if ( *(_WORD *)pv )
      {
        v10 = v33;
        *((_QWORD *)v33 + v13) = pv;
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)pv + v16) );
        v11 += v16 + 1;
        v31 = v11;
      }
      else
      {
        CoTaskMemFree(pv);
        v10 = v33;
        *((_QWORD *)v33 + v13) = 0;
      }
      ++v13;
      v7 = v34[1];
      v9 = (struct CHeap *)v32;
    }
    v17 = 0;
    v35 = 0;
    while ( 1 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v29 + 112LL))(v29, v17, &pv);
      v12 = v18;
      if ( v18 == -2147200967 )
        break;
      if ( v18 < 0 )
        goto LABEL_28;
      v12 = EnsureArrayVoid(&v33, 8u, v13 + 1, v34, v7, v9);
      v15 = pv;
      if ( v12 < 0 )
        goto LABEL_15;
      v17 = ++v35;
      if ( *(_WORD *)pv )
      {
        v10 = v33;
        *((_QWORD *)v33 + v13) = pv;
        v19 = -1;
        do
          ++v19;
        while ( *((_WORD *)pv + v19) );
        v11 += v19 + 1;
        v31 = v11;
      }
      else
      {
        CoTaskMemFree(pv);
        v10 = v33;
        *((_QWORD *)v33 + v13) = 0;
        v17 = v35;
      }
      ++v13;
      v7 = v34[1];
      v9 = (struct CHeap *)v32;
    }
    if ( v11 == (unsigned int)v11 )
    {
      v21 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)v11);
      v22 = v21;
      *a5 = v21;
      if ( v21 )
      {
        pv = v21;
        v23 = 0;
        v12 = 0;
        while ( v23 < v13 )
        {
          v24 = (const unsigned __int16 *)v10[v23];
          if ( v24 )
          {
            v12 = StringCchCopyExW(v22, v11, v24, (unsigned __int16 **)&pv, &v31, v26);
            if ( v12 < 0 )
              goto LABEL_28;
            *(_WORD *)pv = 10;
            v22 = (unsigned __int16 *)((char *)pv + 2);
            pv = (char *)pv + 2;
            v11 = --v31;
          }
          ++v23;
        }
        if ( v11 == 1 )
          *v22 = 0;
        else
          v12 = -2147467259;
      }
      else
      {
        v12 = -2147024882;
      }
    }
    else
    {
      v12 = -2147024882;
    }
LABEL_28:
    for ( i = 0; i < v13; ++i )
      CoTaskMemFree((LPVOID)v10[i]);
    CGrowableArrayVoid::~CGrowableArrayVoid((CGrowableArrayVoid *)&v32);
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v29);
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v30);
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v28);
  }
  else
  {
    if ( !wcscmp_0(a4, L"ETWActivityID") )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 **))(**((_QWORD **)this + 12)
                                                                                             + 24LL))(
              *((_QWORD *)this + 12),
              a4,
              a5);
      if ( v12 >= 0 )
        return (unsigned int)v12;
      goto LABEL_48;
    }
    v12 = 1;
    if ( wcscmp_0(a4, L"ETWProviderGUID") )
      return (unsigned int)v12;
    v12 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 **))(**((_QWORD **)this + 12)
                                                                                           + 24LL))(
            *((_QWORD *)this + 12),
            a4,
            a5);
  }
  if ( v12 < 0 )
    goto LABEL_48;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c180  push    rbp
0x18000c182  push    rbx
0x18000c183  push    rsi
0x18000c184  push    rdi
0x18000c185  push    r12
0x18000c187  push    r13
0x18000c189  push    r14
0x18000c18b  push    r15
0x18000c18d  lea     rbp, [rsp-17h]
0x18000c192  sub     rsp, 98h
0x18000c199  mov     rdi, r9
0x18000c19c  mov     r14, rcx
0x18000c19f  xor     r12d, r12d
0x18000c1a2  mov     r13, [rbp+4Fh+arg_20]
0x18000c1a6  mov     [r13+0], r12
0x18000c1aa  lea     rdx, aLmlist; "LMList"
0x18000c1b1  mov     rcx, r9; String1
0x18000c1b4  call    wcscmp_0
0x18000c1b9  test    eax, eax
0x18000c1bb  jnz     loc_18000C4E9
0x18000c1c1  mov     [rbp+4Fh+var_80], r12
0x18000c1c5  mov     [rbp+4Fh+var_70], r12
0x18000c1c9  mov     [rbp+4Fh+var_78], r12
0x18000c1cd  lea     r15, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18000c1d4  mov     [rbp+4Fh+var_60], r15
0x18000c1d8  mov     esi, r12d
0x18000c1db  mov     [rbp+4Fh+var_58], r12
0x18000c1df  mov     qword ptr [rbp+4Fh+var_50], r12
0x18000c1e3  mov     [rbp+4Fh+pv], r12
0x18000c1e7  lea     edi, [rax+1]
0x18000c1ea  mov     [rbp+4Fh+var_68], rdi
0x18000c1ee  mov     rcx, [r14+108h]
0x18000c1f5  mov     rax, [rcx]
0x18000c1f8  lea     r8, [rbp+4Fh+var_80]
0x18000c1fc  lea     rdx, aLms; "LMs"
0x18000c203  mov     rax, [rax+48h]
0x18000c207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20c  mov     ebx, eax
0x18000c20e  xor     r14d, r14d
0x18000c211  test    eax, eax
0x18000c213  jns     short loc_18000C244
0x18000c215  lea     rcx, [rbp+4Fh+var_60]; this
0x18000c219  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18000c21e  nop
0x18000c21f  lea     rcx, [rbp+4Fh+var_78]
0x18000c223  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000c228  nop
0x18000c229  lea     rcx, [rbp+4Fh+var_70]
0x18000c22d  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000c232  nop
0x18000c233  lea     rcx, [rbp+4Fh+var_80]
0x18000c237  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000c23c  xor     r12d, r12d
0x18000c23f  jmp     loc_18000C54E
0x18000c244  mov     rcx, [rbp+4Fh+var_80]
0x18000c248  mov     rax, [rcx]
0x18000c24b  lea     r8, [rbp+4Fh+var_70]
0x18000c24f  lea     rdx, aMain; "Main"
0x18000c256  mov     rax, [rax+48h]
0x18000c25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c25f  mov     ebx, eax
0x18000c261  test    eax, eax
0x18000c263  js      short loc_18000C215
0x18000c265  mov     rcx, [rbp+4Fh+var_80]
0x18000c269  mov     rax, [rcx]
0x18000c26c  lea     r8, [rbp+4Fh+var_78]
0x18000c270  lea     rdx, aAddon; "AddOn"
0x18000c277  mov     rax, [rax+48h]
0x18000c27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c280  mov     ebx, eax
0x18000c282  test    eax, eax
0x18000c284  js      short loc_18000C215
0x18000c286  mov     rcx, [rbp+4Fh+var_70]
0x18000c28a  mov     rax, [rcx]
0x18000c28d  lea     r8, [rbp+4Fh+pv]
0x18000c291  mov     edx, r14d
0x18000c294  mov     rax, [rax+70h]
0x18000c298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29d  mov     ebx, eax
0x18000c29f  cmp     eax, 80045039h
0x18000c2a4  jz      loc_18000C342
0x18000c2aa  test    eax, eax
0x18000c2ac  js      loc_18000C408
0x18000c2b2  lea     eax, [r14+1]
0x18000c2b6  mov     dword ptr [rbp+4Fh+arg_20], eax
0x18000c2b9  mov     qword ptr [rsp+0D0h+var_A8], r15; struct CHeap *
0x18000c2be  mov     dword ptr [rsp+0D0h+var_B0], r12d; unsigned int
0x18000c2c3  lea     r9, [rbp+4Fh+var_50]; unsigned int *
0x18000c2c7  mov     r8d, eax; unsigned int
0x18000c2ca  mov     edx, 8; unsigned __int64
0x18000c2cf  lea     rcx, [rbp+4Fh+var_58]; void **
0x18000c2d3  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x18000c2d8  mov     ebx, eax
0x18000c2da  xor     r12d, r12d
0x18000c2dd  mov     rcx, [rbp+4Fh+pv]; pv
0x18000c2e1  test    eax, eax
0x18000c2e3  js      short loc_18000C333
0x18000c2e5  mov     ebx, r14d
0x18000c2e8  cmp     r12w, [rcx]
0x18000c2ec  jnz     short loc_18000C2FE
0x18000c2ee  call    cs:__imp_CoTaskMemFree
0x18000c2f4  mov     rsi, [rbp+4Fh+var_58]
0x18000c2f8  mov     [rsi+rbx*8], r12
0x18000c2fc  jmp     short loc_18000C322
0x18000c2fe  mov     rsi, [rbp+4Fh+var_58]
0x18000c302  mov     [rsi+rbx*8], rcx
0x18000c306  mov     rcx, [rbp+4Fh+pv]
0x18000c30a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c30e  inc     rax
0x18000c311  cmp     [rcx+rax*2], r12w
0x18000c316  jnz     short loc_18000C30E
0x18000c318  inc     rdi
0x18000c31b  add     rdi, rax
0x18000c31e  mov     [rbp+4Fh+var_68], rdi
0x18000c322  mov     r14d, dword ptr [rbp+4Fh+arg_20]
0x18000c326  mov     r12d, [rbp+4Fh+var_50+4]
0x18000c32a  mov     r15, [rbp+4Fh+var_60]
0x18000c32e  jmp     loc_18000C286
0x18000c333  call    cs:__imp_CoTaskMemFree
0x18000c339  mov     rsi, [rbp+4Fh+var_58]
0x18000c33d  jmp     loc_18000C40B
0x18000c342  xor     edx, edx
0x18000c344  mov     dword ptr [rbp+4Fh+arg_20], edx
0x18000c347  mov     rcx, [rbp+4Fh+var_78]
0x18000c34b  mov     rax, [rcx]
0x18000c34e  lea     r8, [rbp+4Fh+pv]
0x18000c352  mov     rax, [rax+70h]
0x18000c356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c35b  mov     ebx, eax
0x18000c35d  cmp     eax, 80045039h
0x18000c362  jz      loc_18000C3FC
0x18000c368  test    eax, eax
0x18000c36a  js      loc_18000C408
0x18000c370  lea     eax, [r14+1]
0x18000c374  mov     [rbp+4Fh+var_90], eax
0x18000c377  mov     qword ptr [rsp+0D0h+var_A8], r15; struct CHeap *
0x18000c37c  mov     dword ptr [rsp+0D0h+var_B0], r12d; unsigned int
0x18000c381  lea     r9, [rbp+4Fh+var_50]; unsigned int *
0x18000c385  mov     r8d, eax; unsigned int
0x18000c388  mov     edx, 8; unsigned __int64
0x18000c38d  lea     rcx, [rbp+4Fh+var_58]; void **
0x18000c391  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x18000c396  mov     ebx, eax
0x18000c398  xor     r12d, r12d
0x18000c39b  mov     rcx, [rbp+4Fh+pv]; pv
0x18000c39f  test    eax, eax
0x18000c3a1  js      short loc_18000C333
0x18000c3a3  mov     edx, dword ptr [rbp+4Fh+arg_20]
0x18000c3a6  inc     edx
0x18000c3a8  mov     dword ptr [rbp+4Fh+arg_20], edx
0x18000c3ab  mov     ebx, r14d
0x18000c3ae  cmp     r12w, [rcx]
0x18000c3b2  jnz     short loc_18000C3C7
0x18000c3b4  call    cs:__imp_CoTaskMemFree
0x18000c3ba  mov     rsi, [rbp+4Fh+var_58]
0x18000c3be  mov     [rsi+rbx*8], r12
0x18000c3c2  mov     edx, dword ptr [rbp+4Fh+arg_20]
0x18000c3c5  jmp     short loc_18000C3EB
0x18000c3c7  mov     rsi, [rbp+4Fh+var_58]
0x18000c3cb  mov     [rsi+rbx*8], rcx
0x18000c3cf  mov     rcx, [rbp+4Fh+pv]
0x18000c3d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c3d7  inc     rax
0x18000c3da  cmp     [rcx+rax*2], r12w
0x18000c3df  jnz     short loc_18000C3D7
0x18000c3e1  inc     rdi
0x18000c3e4  add     rdi, rax
0x18000c3e7  mov     [rbp+4Fh+var_68], rdi
0x18000c3eb  mov     r14d, [rbp+4Fh+var_90]
0x18000c3ef  mov     r12d, [rbp+4Fh+var_50+4]
0x18000c3f3  mov     r15, [rbp+4Fh+var_60]
0x18000c3f7  jmp     loc_18000C347
0x18000c3fc  mov     ecx, edi
0x18000c3fe  cmp     rdi, rcx
0x18000c401  jz      short loc_18000C452
0x18000c403  mov     ebx, 8007000Eh
0x18000c408  xor     r12d, r12d
0x18000c40b  mov     edi, r12d
0x18000c40e  test    r14d, r14d
0x18000c411  jz      short loc_18000C426
0x18000c413  mov     ecx, edi
0x18000c415  mov     rcx, [rsi+rcx*8]; pv
0x18000c419  call    cs:__imp_CoTaskMemFree
0x18000c41f  inc     edi
0x18000c421  cmp     edi, r14d
0x18000c424  jb      short loc_18000C413
0x18000c426  lea     rcx, [rbp+4Fh+var_60]; this
0x18000c42a  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18000c42f  nop
0x18000c430  lea     rcx, [rbp+4Fh+var_78]
0x18000c434  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000c439  nop
0x18000c43a  lea     rcx, [rbp+4Fh+var_70]
0x18000c43e  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000c443  nop
0x18000c444  lea     rcx, [rbp+4Fh+var_80]
0x18000c448  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18000c44d  jmp     loc_18000C54A
0x18000c452  add     rcx, rcx; cb
0x18000c455  call    cs:__imp_CoTaskMemAlloc
0x18000c45b  mov     rcx, rax; unsigned __int16 *
0x18000c45e  mov     [r13+0], rax
0x18000c462  xor     r12d, r12d
0x18000c465  test    rax, rax
0x18000c468  jnz     short loc_18000C471
0x18000c46a  mov     ebx, 8007000Eh
0x18000c46f  jmp     short loc_18000C40B
0x18000c471  mov     [rbp+4Fh+pv], rax
0x18000c475  mov     r15d, r12d
0x18000c478  mov     ebx, r12d
0x18000c47b  cmp     r15d, r14d
0x18000c47e  jnb     short loc_18000C4D0
0x18000c480  mov     eax, r15d
0x18000c483  mov     r8, [rsi+rax*8]; unsigned __int16 *
0x18000c487  test    r8, r8
0x18000c48a  jz      short loc_18000C4CB
0x18000c48c  lea     rax, [rbp+4Fh+var_68]
0x18000c490  mov     [rsp+0D0h+var_B0], rax; unsigned __int64 *
0x18000c495  lea     r9, [rbp+4Fh+pv]; unsigned __int16 **
0x18000c499  mov     rdx, rdi; unsigned __int64
0x18000c49c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000c4a1  mov     ebx, eax
0x18000c4a3  test    eax, eax
0x18000c4a5  js      loc_18000C40B
0x18000c4ab  mov     rax, [rbp+4Fh+pv]
0x18000c4af  mov     word ptr [rax], 0Ah
0x18000c4b4  mov     rcx, [rbp+4Fh+pv]
0x18000c4b8  add     rcx, 2
0x18000c4bc  mov     [rbp+4Fh+pv], rcx
0x18000c4c0  mov     rdi, [rbp+4Fh+var_68]
0x18000c4c4  dec     rdi
0x18000c4c7  mov     [rbp+4Fh+var_68], rdi
0x18000c4cb  inc     r15d
0x18000c4ce  jmp     short loc_18000C47B
0x18000c4d0  cmp     rdi, 1
0x18000c4d4  jz      short loc_18000C4E0
0x18000c4d6  mov     ebx, 80004005h
0x18000c4db  jmp     loc_18000C40B
0x18000c4e0  mov     [rcx], r12w
0x18000c4e4  jmp     loc_18000C40B
0x18000c4e9  lea     rdx, aEtwactivityid; "ETWActivityID"
0x18000c4f0  mov     rcx, rdi; String1
0x18000c4f3  call    wcscmp_0
0x18000c4f8  test    eax, eax
0x18000c4fa  jnz     short loc_18000C51A
0x18000c4fc  mov     rcx, [r14+60h]
0x18000c500  mov     rax, [rcx]
0x18000c503  mov     r8, r13
0x18000c506  mov     rdx, rdi
0x18000c509  mov     rax, [rax+18h]
0x18000c50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c512  mov     ebx, eax
0x18000c514  test    eax, eax
0x18000c516  js      short loc_18000C54E
0x18000c518  jmp     short loc_18000C55C
0x18000c51a  mov     ebx, 1
0x18000c51f  lea     rdx, aEtwprovidergui; "ETWProviderGUID"
0x18000c526  mov     rcx, rdi; String1
0x18000c529  call    wcscmp_0
0x18000c52e  test    eax, eax
0x18000c530  jnz     short loc_18000C55C
0x18000c532  mov     rcx, [r14+60h]
0x18000c536  mov     rax, [rcx]
0x18000c539  mov     r8, r13
0x18000c53c  mov     rdx, rdi
0x18000c53f  mov     rax, [rax+18h]
0x18000c543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c548  mov     ebx, eax
0x18000c54a  test    ebx, ebx
0x18000c54c  jns     short loc_18000C55C
0x18000c54e  mov     rcx, [r13+0]; pv
0x18000c552  call    cs:__imp_CoTaskMemFree
0x18000c558  mov     [r13+0], r12
0x18000c55c  mov     eax, ebx
0x18000c55e  add     rsp, 98h
0x18000c565  pop     r15
0x18000c567  pop     r14
0x18000c569  pop     r13
0x18000c56b  pop     r12
0x18000c56d  pop     rdi
0x18000c56e  pop     rsi
0x18000c56f  pop     rbx
0x18000c570  pop     rbp
0x18000c571  retn
```
