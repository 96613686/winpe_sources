# CWiaItem::ApplyCurrentContextSettings(void)

- ea: `0x18005e2e8`
- end: `0x18005e710`
- name: `?ApplyCurrentContextSettings@CWiaItem@@QEAAJXZ`
- size: `1064`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006d5f0`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001e364`
- `0x18002de18`
- `0x18002def8`
- `0x180034658`
- `0x18005c7b0`
- `0x18005e2e8`
- `0x1800659c8`
- `0x18006b040`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005e6d6`
- `KERNEL32!LocalFree` at `0x18005e6e8`
- `KERNEL32!LocalFree` at `0x18005e6d6`
- `KERNEL32!LocalFree` at `0x18005e6e8`
- `KERNEL32!LocalAlloc` at `0x18005e4b9`
- `KERNEL32!LocalAlloc` at `0x18005e4cf`
- `KERNEL32!LocalAlloc` at `0x18005e4b9`
- `KERNEL32!LocalAlloc` at `0x18005e4cf`
- `ole32!CoTaskMemFree` at `0x18005e5c8`
- `ole32!CoTaskMemFree` at `0x18005e5c8`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18005e67b`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18005e67b`

## string_xrefs

- `0x18005e62a`: `Call to WriteMultipleToDAIT failed (0x%X)`
- `0x18005e652`: `Call to WriteMultipleToDAIT failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::ApplyCurrentContextSettings(CWiaItem *this)
{
  struct tagWiaTraceData_Type *v2; // rax
  char *v3; // rdx
  unsigned int v4; // r8d
  __int64 v5; // rax
  int v6; // edi
  char *v7; // rbx
  void *v8; // rdx
  void **v9; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  char *v13; // rbx
  void *v14; // rdx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  struct tagPROPSPEC *v21; // r12
  struct tagPROPVARIANT *v22; // rax
  struct tagPROPVARIANT *v23; // r14
  unsigned int v24; // r15d
  __int64 v25; // rcx
  PROPID v26; // edx
  signed int v27; // r8d
  CWiaPropStg *v28; // rcx
  PROPID v29; // eax
  __int64 v30; // rcx
  char *v31; // rbx
  void *v32; // rdx
  void **v33; // rax
  void *v34; // rdx
  __int64 v35; // rcx
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-69h]
  LPVOID pv[2]; // [rsp+30h] [rbp-59h] BYREF
  struct tagPROPSPEC v43; // [rsp+40h] [rbp-49h] BYREF
  __int128 v44; // [rsp+50h] [rbp-39h]
  _BYTE v45[128]; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v46; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v47; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v48; // [rsp+100h] [rbp+77h] BYREF

  v2 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::ApplyCurrentContextSettings");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v45, v3, v4, "CWiaItem::ApplyCurrentContextSettings", lpMem, v2);
  v5 = *((_QWORD *)this + 26);
  if ( *(_DWORD *)(v5 + 104) == 1 && *(_QWORD *)(v5 + 64) && (CWiaItem *)v5 != this )
  {
    v6 = CWiaItem::SetLegacyItemContext(this);
    if ( v6 >= 0 )
    {
      v12 = *((_QWORD *)this + 8);
      if ( v12 && *(_QWORD *)(v12 + 80) )
      {
LABEL_10:
        v46 = 0;
        v48 = 0;
        if ( v6 < 0 )
        {
LABEL_17:
          CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v45);
          return (unsigned int)v6;
        }
        v6 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 1) + 88LL))((char *)this + 8, &v48);
        if ( v6 < 0 )
          goto LABEL_14;
        if ( !v48 )
        {
          v6 = -2147024882;
LABEL_14:
          v15 = (char *)WiaTrace_TraceLog("failed to get property enumerator (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::ApplyCurrentContextSettings", v15);
          WiaTrcLib::Free((WiaTrcLib *)v15, v16);
          v17 = (void **)WiaTrace_Trace("failed to get property enumerator (0x%X)", v6);
          WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaItem::ApplyCurrentContextSettings", 1, v17);
          goto LABEL_15;
        }
        v6 = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 2) + 128LL))(
               (char *)this + 16,
               &v46);
        if ( v6 < 0 )
        {
LABEL_15:
          if ( v48 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            v48 = 0;
          }
          goto LABEL_17;
        }
        v21 = (struct tagPROPSPEC *)LocalAlloc(0x40u, 16LL * v46);
        v22 = (struct tagPROPVARIANT *)LocalAlloc(0x40u, 24LL * v46);
        v23 = v22;
        if ( v21 && v22 )
        {
          v24 = 0;
          memset_0(v21, 0, 16LL * v46);
          memset_0(v23, 0, 24LL * v46);
          v47 = 0;
          *(_OWORD *)pv = 0;
          while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v48 + 24LL))(
                     v48,
                     1,
                     pv,
                     &v47)
               && v47 == 1 )
          {
            v43 = 0;
            v44 = 0;
            if ( (unsigned int)CWiaItem::GetPropCompatCategory(v25, LODWORD(pv[1]), 1, 8, &v43) )
            {
              if ( !HIDWORD(v44) )
              {
                v28 = (CWiaPropStg *)*((_QWORD *)this + 27);
                v43 = 0;
                v43.propid = v26;
                v43.ulKind = 1;
                if ( (int)CWiaPropStg::CheckPropertyAccess(v28, 0, v27, &v43) >= 0 && v24 < v46 )
                {
                  v29 = (PROPID)pv[1];
                  v30 = v24++;
                  v21[v30].ulKind = 1;
                  v21[v30].propid = v29;
                }
              }
            }
            if ( pv[0] )
            {
              CoTaskMemFree(pv[0]);
              pv[0] = 0;
            }
          }
          v6 = (*(__int64 (__fastcall **)(char *, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *))(*((_QWORD *)this + 1) + 24LL))(
                 (char *)this + 8,
                 v24,
                 v21,
                 v23);
          if ( !v6 )
          {
            v47 = 0;
            v6 = CWiaItem::WriteMultipleToDAIT((CWiaItem **)this, v24, v21, v23, 0x1002u, &v47);
            if ( v6 < 0 )
            {
              v31 = (char *)WiaTrace_TraceLog("Call to WriteMultipleToDAIT failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::ApplyCurrentContextSettings", v31);
              WiaTrcLib::Free((WiaTrcLib *)v31, v32);
              v33 = (void **)WiaTrace_Trace("Call to WriteMultipleToDAIT failed (0x%X)", v6);
              WiaTrace_ProcessTrace_Ex(v35, v34, (void *)"CWiaItem::ApplyCurrentContextSettings", 1, v33);
            }
            FreePropVariantArray(v24, (PROPVARIANT *)v23);
          }
        }
        else
        {
          v36 = (char *)WiaTrace_TraceLog("memory allocation failed");
          WriteDbgTraceErrorWI("CWiaItem::ApplyCurrentContextSettings", v36);
          WiaTrcLib::Free((WiaTrcLib *)v36, v37);
          v38 = (void **)WiaTrace_Trace("memory allocation failed");
          WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"CWiaItem::ApplyCurrentContextSettings", 1, v38);
          v6 = -2147024882;
          if ( !v21 )
            goto LABEL_37;
        }
        LocalFree(v21);
LABEL_37:
        if ( v23 )
          LocalFree(v23);
        goto LABEL_15;
      }
      v6 = -2147467261;
      v13 = (char *)WiaTrace_TraceLog("NULL pointer to legacy D-AIT root or child item (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::ApplyCurrentContextSettings", v13);
      WiaTrcLib::Free((WiaTrcLib *)v13, v14);
      v9 = (void **)WiaTrace_Trace("NULL pointer to legacy D-AIT root or child item (0x%X)", 2147500035LL);
    }
    else
    {
      v7 = (char *)WiaTrace_TraceLog("cannot set the legacy D-AIT item context (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::ApplyCurrentContextSettings", v7);
      WiaTrcLib::Free((WiaTrcLib *)v7, v8);
      v9 = (void **)WiaTrace_Trace("cannot set the legacy D-AIT item context (0x%X)", (unsigned int)v6);
    }
    WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"CWiaItem::ApplyCurrentContextSettings", 1, v9);
    goto LABEL_10;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v45);
  return 0;
}

```

## disassembly

```asm
0x18005e2e8  push    rbp
0x18005e2ea  push    rbx
0x18005e2eb  push    rsi
0x18005e2ec  push    rdi
0x18005e2ed  push    r12
0x18005e2ef  push    r14
0x18005e2f1  push    r15
0x18005e2f3  lea     rbp, [rsp-27h]
0x18005e2f8  sub     rsp, 0B0h
0x18005e2ff  mov     rsi, rcx
0x18005e302  lea     r14, aCwiaitemApplyc; "CWiaItem::ApplyCurrentContextSettings"
0x18005e309  mov     rcx, r14
0x18005e30c  call    WiaTrace_Trace
0x18005e311  mov     r9, r14; char *
0x18005e314  mov     [rsp+0E0h+var_B8], rax; struct tagWiaTraceData_Type *
0x18005e319  lea     rcx, [rbp+57h+var_80]; this
0x18005e31d  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005e322  mov     rax, [rsi+0D0h]
0x18005e329  mov     r15d, 1
0x18005e32f  cmp     [rax+68h], r15d
0x18005e333  jnz     loc_18005E6F3
0x18005e339  cmp     qword ptr [rax+40h], 0
0x18005e33e  jz      loc_18005E6F3
0x18005e344  cmp     rax, rsi
0x18005e347  jz      loc_18005E6F3
0x18005e34d  mov     rcx, rsi; this
0x18005e350  call    ?SetLegacyItemContext@CWiaItem@@QEAAJXZ; CWiaItem::SetLegacyItemContext(void)
0x18005e355  mov     edi, eax
0x18005e357  test    eax, eax
0x18005e359  jns     short loc_18005E388
0x18005e35b  mov     edx, eax
0x18005e35d  lea     rcx, aCannotSetTheLe; "cannot set the legacy D-AIT item contex"...
0x18005e364  call    WiaTrace_TraceLog
0x18005e369  mov     rdx, rax; char *
0x18005e36c  mov     rcx, r14; char *
0x18005e36f  mov     rbx, rax
0x18005e372  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005e377  mov     rcx, rbx; this
0x18005e37a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005e37f  lea     rcx, aCannotSetTheLe; "cannot set the legacy D-AIT item contex"...
0x18005e386  jmp     short loc_18005E3C8
0x18005e388  mov     rax, [rsi+40h]
0x18005e38c  test    rax, rax
0x18005e38f  jz      short loc_18005E398
0x18005e391  cmp     qword ptr [rax+50h], 0
0x18005e396  jnz     short loc_18005E3DF
0x18005e398  mov     edi, 80004003h
0x18005e39d  lea     rcx, aNullPointerToL; "NULL pointer to legacy D-AIT root or ch"...
0x18005e3a4  mov     edx, edi
0x18005e3a6  call    WiaTrace_TraceLog
0x18005e3ab  mov     rdx, rax; char *
0x18005e3ae  mov     rcx, r14; char *
0x18005e3b1  mov     rbx, rax
0x18005e3b4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005e3b9  mov     rcx, rbx; this
0x18005e3bc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005e3c1  lea     rcx, aNullPointerToL; "NULL pointer to legacy D-AIT root or ch"...
0x18005e3c8  mov     edx, edi
0x18005e3ca  call    WiaTrace_Trace
0x18005e3cf  mov     r9d, r15d; int
0x18005e3d2  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005e3d7  mov     r8, r14; int
0x18005e3da  call    WiaTrace_ProcessTrace_Ex
0x18005e3df  mov     [rbp+57h+arg_0], 0
0x18005e3e6  mov     [rbp+57h+arg_10], 0
0x18005e3ee  test    edi, edi
0x18005e3f0  js      loc_18005E47E
0x18005e3f6  lea     rbx, [rsi+8]
0x18005e3fa  mov     rax, [rbx]
0x18005e3fd  lea     rdx, [rbp+57h+arg_10]
0x18005e401  mov     rcx, rbx
0x18005e404  mov     rax, [rax+58h]
0x18005e408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e40d  mov     edi, eax
0x18005e40f  test    eax, eax
0x18005e411  js      short loc_18005E41F
0x18005e413  cmp     [rbp+57h+arg_10], 0
0x18005e418  jnz     short loc_18005E48E
0x18005e41a  mov     edi, 8007000Eh
0x18005e41f  mov     edx, edi
0x18005e421  lea     rcx, aFailedToGetPro_0; "failed to get property enumerator (0x%X"...
0x18005e428  call    WiaTrace_TraceLog
0x18005e42d  mov     rdx, rax; char *
0x18005e430  mov     rcx, r14; char *
0x18005e433  mov     rbx, rax
0x18005e436  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005e43b  mov     rcx, rbx; this
0x18005e43e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005e443  mov     edx, edi
0x18005e445  lea     rcx, aFailedToGetPro_0; "failed to get property enumerator (0x%X"...
0x18005e44c  call    WiaTrace_Trace
0x18005e451  mov     r9d, r15d; int
0x18005e454  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005e459  mov     r8, r14; int
0x18005e45c  call    WiaTrace_ProcessTrace_Ex
0x18005e461  mov     rcx, [rbp+57h+arg_10]
0x18005e465  test    rcx, rcx
0x18005e468  jz      short loc_18005E47E
0x18005e46a  mov     rax, [rcx]
0x18005e46d  mov     rax, [rax+10h]
0x18005e471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e476  mov     [rbp+57h+arg_10], 0
0x18005e47e  lea     rcx, [rbp+57h+var_80]; this
0x18005e482  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18005e487  mov     eax, edi
0x18005e489  jmp     loc_18005E6FE
0x18005e48e  lea     rcx, [rsi+10h]
0x18005e492  mov     rax, [rcx]
0x18005e495  lea     rdx, [rbp+57h+arg_0]
0x18005e499  mov     rax, [rax+80h]
0x18005e4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4a5  mov     edi, eax
0x18005e4a7  test    eax, eax
0x18005e4a9  js      short loc_18005E461
0x18005e4ab  mov     edx, [rbp+57h+arg_0]
0x18005e4ae  mov     edi, 40h ; '@'
0x18005e4b3  shl     rdx, 4; uBytes
0x18005e4b7  mov     ecx, edi; uFlags
0x18005e4b9  call    cs:__imp_LocalAlloc
0x18005e4bf  mov     edx, [rbp+57h+arg_0]
0x18005e4c2  mov     ecx, edi; uFlags
0x18005e4c4  mov     r12, rax
0x18005e4c7  lea     rdx, [rdx+rdx*2]
0x18005e4cb  shl     rdx, 3; uBytes
0x18005e4cf  call    cs:__imp_LocalAlloc
0x18005e4d5  mov     r14, rax
0x18005e4d8  test    r12, r12
0x18005e4db  jz      loc_18005E683
0x18005e4e1  test    rax, rax
0x18005e4e4  jz      loc_18005E683
0x18005e4ea  mov     r8d, [rbp+57h+arg_0]
0x18005e4ee  xor     edx, edx; Val
0x18005e4f0  shl     r8, 4; Size
0x18005e4f4  mov     rcx, r12; void *
0x18005e4f7  xor     r15d, r15d
0x18005e4fa  call    memset_0
0x18005e4ff  mov     eax, [rbp+57h+arg_0]
0x18005e502  xor     edx, edx; Val
0x18005e504  mov     rcx, r14; void *
0x18005e507  lea     r8, [rax+rax*2]
0x18005e50b  shl     r8, 3; Size
0x18005e50f  call    memset_0
0x18005e514  xorps   xmm0, xmm0
0x18005e517  mov     [rbp+57h+arg_8], r15d
0x18005e51b  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18005e51f  lea     edi, [r15+1]
0x18005e523  mov     rcx, [rbp+57h+arg_10]
0x18005e527  lea     r9, [rbp+57h+arg_8]
0x18005e52b  lea     r8, [rbp+57h+pv]
0x18005e52f  mov     edx, edi
0x18005e531  mov     rax, [rcx]
0x18005e534  mov     rax, [rax+18h]
0x18005e538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e53d  test    eax, eax
0x18005e53f  jnz     loc_18005E5DB
0x18005e545  cmp     [rbp+57h+arg_8], edi
0x18005e548  jnz     loc_18005E5DB
0x18005e54e  mov     edx, dword ptr [rbp+57h+pv+8]
0x18005e551  lea     rax, [rbp+57h+var_A0]
0x18005e555  xorps   xmm0, xmm0
0x18005e558  mov     [rsp+0E0h+lpMem], rax
0x18005e55d  mov     r9d, 8
0x18005e563  mov     r8d, edi
0x18005e566  movups  xmmword ptr [rbp+57h+var_A0.ulKind], xmm0
0x18005e56a  movups  [rbp+57h+var_90], xmm0
0x18005e56e  call    ?GetPropCompatCategory@CWiaItem@@QEAAHKHW4_CL_ITEM@@AEAU_PROP_COMPAT_TABLE@@@Z; CWiaItem::GetPropCompatCategory(ulong,int,_CL_ITEM,_PROP_COMPAT_TABLE &)
0x18005e573  test    eax, eax
0x18005e575  jz      short loc_18005E5BB
0x18005e577  cmp     dword ptr [rbp+57h+var_90+0Ch], 0
0x18005e57b  jnz     short loc_18005E5BB
0x18005e57d  mov     rcx, [rsi+0D8h]; this
0x18005e584  lea     r9, [rbp+57h+var_A0]; struct tagPROPSPEC *
0x18005e588  xorps   xmm0, xmm0
0x18005e58b  movups  xmmword ptr [rbp+57h+var_A0.ulKind], xmm0
0x18005e58f  mov     dword ptr [rbp+57h+var_A0.8], edx
0x18005e592  xor     edx, edx; int
0x18005e594  mov     [rbp+57h+var_A0.ulKind], edi
0x18005e597  call    ?CheckPropertyAccess@CWiaPropStg@@QEAAJHJPEAUtagPROPSPEC@@@Z; CWiaPropStg::CheckPropertyAccess(int,long,tagPROPSPEC *)
0x18005e59c  test    eax, eax
0x18005e59e  js      short loc_18005E5BB
0x18005e5a0  cmp     r15d, [rbp+57h+arg_0]
0x18005e5a4  jnb     short loc_18005E5BB
0x18005e5a6  mov     eax, dword ptr [rbp+57h+pv+8]
0x18005e5a9  mov     ecx, r15d
0x18005e5ac  add     rcx, rcx
0x18005e5af  add     r15d, edi
0x18005e5b2  mov     [r12+rcx*8], edi
0x18005e5b6  mov     [r12+rcx*8+8], eax
0x18005e5bb  mov     rcx, [rbp+57h+pv]; pv
0x18005e5bf  test    rcx, rcx
0x18005e5c2  jz      loc_18005E523
0x18005e5c8  call    cs:__imp_CoTaskMemFree
0x18005e5ce  mov     [rbp+57h+pv], 0
0x18005e5d6  jmp     loc_18005E523
0x18005e5db  mov     rax, [rbx]
0x18005e5de  mov     r9, r14
0x18005e5e1  mov     r8, r12
0x18005e5e4  mov     edx, r15d
0x18005e5e7  mov     rcx, rbx
0x18005e5ea  mov     rax, [rax+18h]
0x18005e5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5f3  mov     edi, eax
0x18005e5f5  test    eax, eax
0x18005e5f7  jnz     loc_18005E6D3
0x18005e5fd  mov     [rbp+57h+arg_8], eax
0x18005e600  mov     r9, r14; struct tagPROPVARIANT *
0x18005e603  lea     rax, [rbp+57h+arg_8]
0x18005e607  mov     r8, r12; struct tagPROPSPEC *
0x18005e60a  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18005e60f  mov     edx, r15d; unsigned int
0x18005e612  mov     rcx, rsi; this
0x18005e615  mov     dword ptr [rsp+0E0h+lpMem], 1002h; unsigned int
0x18005e61d  call    ?WriteMultipleToDAIT@CWiaItem@@QEAAJKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@KAEAK@Z; CWiaItem::WriteMultipleToDAIT(ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ulong,ulong &)
0x18005e622  mov     edi, eax
0x18005e624  test    eax, eax
0x18005e626  jns     short loc_18005E675
0x18005e628  mov     edx, eax
0x18005e62a  lea     rcx, aCallToWritemul; "Call to WriteMultipleToDAIT failed (0x%"...
0x18005e631  call    WiaTrace_TraceLog
0x18005e636  mov     rdx, rax; char *
0x18005e639  lea     rcx, aCwiaitemApplyc; "CWiaItem::ApplyCurrentContextSettings"
0x18005e640  mov     rbx, rax
0x18005e643  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005e648  mov     rcx, rbx; this
0x18005e64b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005e650  mov     edx, edi
0x18005e652  lea     rcx, aCallToWritemul; "Call to WriteMultipleToDAIT failed (0x%"...
0x18005e659  call    WiaTrace_Trace
0x18005e65e  mov     r9d, 1; int
0x18005e664  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005e669  lea     r8, aCwiaitemApplyc; "CWiaItem::ApplyCurrentContextSettings"
0x18005e670  call    WiaTrace_ProcessTrace_Ex
0x18005e675  mov     rdx, r14; rgvars
0x18005e678  mov     ecx, r15d; cVariants
0x18005e67b  call    cs:__imp_FreePropVariantArray
0x18005e681  jmp     short loc_18005E6D3
0x18005e683  lea     rcx, aMemoryAllocati; "memory allocation failed"
0x18005e68a  call    WiaTrace_TraceLog
0x18005e68f  mov     rdx, rax; char *
0x18005e692  lea     rcx, aCwiaitemApplyc; "CWiaItem::ApplyCurrentContextSettings"
0x18005e699  mov     rbx, rax
0x18005e69c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005e6a1  mov     rcx, rbx; this
0x18005e6a4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005e6a9  lea     rcx, aMemoryAllocati; "memory allocation failed"
0x18005e6b0  call    WiaTrace_Trace
0x18005e6b5  mov     r9d, r15d; int
0x18005e6b8  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005e6bd  lea     r8, aCwiaitemApplyc; "CWiaItem::ApplyCurrentContextSettings"
0x18005e6c4  call    WiaTrace_ProcessTrace_Ex
0x18005e6c9  mov     edi, 8007000Eh
0x18005e6ce  test    r12, r12
0x18005e6d1  jz      short loc_18005E6DC
0x18005e6d3  mov     rcx, r12; hMem
0x18005e6d6  call    cs:__imp_LocalFree
0x18005e6dc  test    r14, r14
0x18005e6df  jz      loc_18005E461
0x18005e6e5  mov     rcx, r14; hMem
0x18005e6e8  call    cs:__imp_LocalFree
0x18005e6ee  jmp     loc_18005E461
0x18005e6f3  lea     rcx, [rbp+57h+var_80]; this
0x18005e6f7  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18005e6fc  xor     eax, eax
0x18005e6fe  add     rsp, 0B0h
0x18005e705  pop     r15
0x18005e707  pop     r14
0x18005e709  pop     r12
0x18005e70b  pop     rdi
0x18005e70c  pop     rsi
0x18005e70d  pop     rbx
0x18005e70e  pop     rbp
0x18005e70f  retn
```
