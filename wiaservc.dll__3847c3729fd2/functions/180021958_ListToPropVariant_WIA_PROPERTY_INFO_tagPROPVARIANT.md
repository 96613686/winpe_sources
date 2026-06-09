# ListToPropVariant(_WIA_PROPERTY_INFO *,tagPROPVARIANT *)

- ea: `0x180021958`
- end: `0x180021fba`
- name: `?ListToPropVariant@@YAJPEAU_WIA_PROPERTY_INFO@@PEAUtagPROPVARIANT@@@Z`
- size: `1634`
- prototype: `int(struct _WIA_PROPERTY_INFO *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180018180`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180021958`
- `0x18002de18`
- `0x18002def8`
- `0x18003de6c`
- `0x180077608`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180021c6b`
- `OLEAUT32!__imp_SysAllocString` at `0x180021cbc`
- `OLEAUT32!__imp_SysAllocString` at `0x180021d1a`
- `OLEAUT32!__imp_SysAllocString` at `0x180021c6b`
- `OLEAUT32!__imp_SysAllocString` at `0x180021cbc`
- `OLEAUT32!__imp_SysAllocString` at `0x180021d1a`
- `ole32!PropVariantClear` at `0x180021f95`
- `ole32!PropVariantClear` at `0x180021f95`
- `ole32!CoTaskMemAlloc` at `0x180021a6f`
- `ole32!CoTaskMemAlloc` at `0x180021b30`
- `ole32!CoTaskMemAlloc` at `0x180021bcd`
- `ole32!CoTaskMemAlloc` at `0x180021c4e`
- `ole32!CoTaskMemAlloc` at `0x180021e66`
- `ole32!CoTaskMemAlloc` at `0x180021edd`
- `ole32!CoTaskMemAlloc` at `0x180021f58`
- `ole32!CoTaskMemAlloc` at `0x180021a6f`
- `ole32!CoTaskMemAlloc` at `0x180021b30`
- `ole32!CoTaskMemAlloc` at `0x180021bcd`
- `ole32!CoTaskMemAlloc` at `0x180021c4e`
- `ole32!CoTaskMemAlloc` at `0x180021e66`
- `ole32!CoTaskMemAlloc` at `0x180021edd`
- `ole32!CoTaskMemAlloc` at `0x180021f58`

## pseudocode

```c
__int64 __fastcall ListToPropVariant(struct _WIA_PROPERTY_INFO *a1, PROPVARIANT *a2)
{
  struct tagWiaTraceData_Type *v4; // rax
  char *v5; // rdx
  unsigned int v6; // r8d
  unsigned __int64 v7; // rsi
  int v8; // ebx
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  BYTE *v14; // rax
  BYTE *v15; // r15
  void *v16; // rcx
  size_t v17; // r8
  const void *v18; // rdx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  BYTE *v24; // rax
  BYTE *v25; // rax
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // r12
  const OLECHAR *v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  BSTR v35; // rax
  char *v36; // rbx
  void *v37; // rdx
  unsigned int i; // r15d
  const OLECHAR *v39; // rcx
  BSTR v40; // rax
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  char *v46; // rbx
  void *v47; // rdx
  void **v48; // rax
  void *v49; // rdx
  __int64 v50; // rcx
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  BYTE *v56; // rax
  float *v57; // rax
  BYTE *v58; // rax
  unsigned int lpMem; // [rsp+20h] [rbp-49h]
  _BYTE v61[144]; // [rsp+30h] [rbp-39h] BYREF
  SIZE_T cb; // [rsp+D0h] [rbp+67h] BYREF

  v4 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::ListToPropVariant");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v61, v5, v6, "ListToPropVariant", lpMem, v4);
  v7 = *((unsigned int *)a1 + 2);
  v8 = 0;
  *(_WORD *)a2 = *((_WORD *)a1 + 2) | 0x1000;
  switch ( *((_WORD *)a1 + 2) )
  {
    case 2:
      goto LABEL_61;
    case 3:
      goto LABEL_59;
    case 4:
      if ( !*((_QWORD *)a1 + 3) )
        goto LABEL_12;
      if ( v7 + 2 < v7 )
        goto LABEL_66;
      cb = v7 + 2;
      if ( (int)ULongLongMult(v7 + 2, 4u, &cb) < 0 )
        goto LABEL_66;
      v57 = (float *)CoTaskMemAlloc(cb);
      v15 = (BYTE *)v57;
      if ( !v57 )
        goto LABEL_16;
      *((_DWORD *)a2 + 2) = v7 + 2;
      v17 = 4 * v7;
      v16 = v57 + 2;
      *v57 = (float)(int)v7;
      v57[1] = *((double *)a1 + 2);
      goto LABEL_53;
    case 5:
      if ( !*((_QWORD *)a1 + 3) )
        goto LABEL_12;
      if ( v7 + 2 < v7 )
        goto LABEL_66;
      cb = v7 + 2;
      if ( (int)ULongLongMult(v7 + 2, 8u, &cb) < 0 )
        goto LABEL_66;
      v56 = (BYTE *)CoTaskMemAlloc(cb);
      v15 = v56;
      if ( !v56 )
        goto LABEL_16;
      *((_DWORD *)a2 + 2) = v7 + 2;
      v17 = 8 * v7;
      *(double *)v56 = (double)(int)v7;
      *((_QWORD *)v56 + 1) = *((_QWORD *)a1 + 2);
      v16 = v56 + 16;
LABEL_53:
      v18 = (const void *)*((_QWORD *)a1 + 3);
      goto LABEL_15;
    case 8:
      if ( !*((_QWORD *)a1 + 3) )
      {
        v26 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST_BSTR), pList pointer is bad");
        WriteDbgTraceErrorWI("ListToPropVariant", v26);
        WiaTrcLib::Free((WiaTrcLib *)v26, v27);
        v28 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST_BSTR), pList pointer is bad");
LABEL_31:
        WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"ListToPropVariant", 1, v28);
        goto LABEL_12;
      }
      v31 = CoTaskMemAlloc(8LL * (unsigned int)(v7 + 2));
      if ( v31 )
      {
        *((_DWORD *)a2 + 2) = v7 + 2;
        *v31 = SysAllocString(&Class);
        v32 = (const OLECHAR *)*((_QWORD *)a1 + 2);
        if ( !v32 )
        {
          v33 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST_BSTR), Nom BSTR is bad");
          WriteDbgTraceErrorWI("ListToPropVariant", v33);
          WiaTrcLib::Free((WiaTrcLib *)v33, v34);
          v28 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST_BSTR), Nom BSTR is bad");
          goto LABEL_31;
        }
        v35 = SysAllocString(v32);
        v31[1] = v35;
        if ( !v35 )
        {
          v36 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST_BSTR), out of memory");
          WriteDbgTraceErrorWI("ListToPropVariant", v36);
          WiaTrcLib::Free((WiaTrcLib *)v36, v37);
          v21 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST_BSTR), out of memory");
          goto LABEL_17;
        }
        for ( i = 0; i < (unsigned int)v7; ++i )
        {
          v39 = *(const OLECHAR **)(*((_QWORD *)a1 + 3) + 8LL * i);
          if ( !v39 )
          {
            v46 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST_BSTR), Nom BSTR is bad");
            WriteDbgTraceErrorWI("ListToPropVariant", v46);
            WiaTrcLib::Free((WiaTrcLib *)v46, v47);
            v48 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST_BSTR), Nom BSTR is bad");
            WiaTrace_ProcessTrace_Ex(v50, v49, (void *)"ListToPropVariant", 1, v48);
            v8 = -2147467261;
            break;
          }
          v40 = SysAllocString(v39);
          v31[i + 2] = v40;
          if ( !v40 )
          {
            v41 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST_BSTR), out of memory");
            WriteDbgTraceErrorWI("ListToPropVariant", v41);
            WiaTrcLib::Free((WiaTrcLib *)v41, v42);
            v43 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST_BSTR), out of memory");
            WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"ListToPropVariant", 1, v43);
            v8 = -2147024882;
            break;
          }
        }
        a2[2] = v31;
      }
      else
      {
        v51 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST_BSTR), unable to allocate list");
        WriteDbgTraceErrorWI("ListToPropVariant", v51);
        WiaTrcLib::Free((WiaTrcLib *)v51, v52);
        v53 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST_BSTR), unable to allocate list");
        WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"ListToPropVariant", 1, v53);
        v8 = -2147024882;
      }
      if ( v8 >= 0 )
        goto LABEL_68;
      goto LABEL_67;
    case 0x11:
      if ( !*((_QWORD *)a1 + 2) )
        goto LABEL_12;
      if ( v7 + 2 >= v7 )
      {
        cb = v7 + 2;
        if ( (int)ULongLongMult(v7 + 2, 1u, &cb) >= 0 )
        {
          v25 = (BYTE *)CoTaskMemAlloc(cb);
          v15 = v25;
          if ( v25 )
          {
            v17 = v7;
            *((_DWORD *)a2 + 2) = v7 + 2;
            *v25 = v7;
            v25[1] = *((_BYTE *)a1 + 12);
            v16 = v25 + 2;
            goto LABEL_22;
          }
LABEL_16:
          v19 = (char *)WiaTrace_TraceLog("ListToPropVariant (MAKE_LIST), unable to allocate list");
          WriteDbgTraceErrorWI("ListToPropVariant", v19);
          WiaTrcLib::Free((WiaTrcLib *)v19, v20);
          v21 = (void **)WiaTrace_Trace("ListToPropVariant (MAKE_LIST), unable to allocate list");
LABEL_17:
          WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"ListToPropVariant", 1, v21);
          v8 = -2147024882;
          goto LABEL_67;
        }
      }
LABEL_66:
      v8 = -2147024362;
      goto LABEL_67;
    case 0x12:
LABEL_61:
      if ( !*((_QWORD *)a1 + 2) )
        goto LABEL_12;
      if ( v7 + 2 >= v7 )
      {
        cb = v7 + 2;
        if ( (int)ULongLongMult(v7 + 2, 2u, &cb) >= 0 )
        {
          v58 = (BYTE *)CoTaskMemAlloc(cb);
          v15 = v58;
          if ( v58 )
          {
            *((_DWORD *)a2 + 2) = v7 + 2;
            v17 = 2 * v7;
            *(_WORD *)v58 = v7;
            *((_WORD *)v58 + 1) = *((_WORD *)a1 + 6);
            v16 = v58 + 4;
            v18 = (const void *)*((_QWORD *)a1 + 2);
            goto LABEL_15;
          }
          goto LABEL_16;
        }
      }
      goto LABEL_66;
    case 0x13:
LABEL_59:
      if ( !*((_QWORD *)a1 + 2) )
        goto LABEL_12;
      if ( v7 + 2 >= v7 )
      {
        cb = v7 + 2;
        if ( (int)ULongLongMult(v7 + 2, 4u, &cb) >= 0 )
        {
          v24 = (BYTE *)CoTaskMemAlloc(cb);
          v15 = v24;
          if ( v24 )
          {
            *((_DWORD *)a2 + 2) = v7 + 2;
            v17 = 4 * v7;
            *(_DWORD *)v24 = v7;
            *((_DWORD *)v24 + 1) = *((_DWORD *)a1 + 3);
            v16 = v24 + 8;
LABEL_22:
            v18 = (const void *)*((_QWORD *)a1 + 2);
            goto LABEL_15;
          }
          goto LABEL_16;
        }
      }
      goto LABEL_66;
  }
  if ( *((_WORD *)a1 + 2) != 72 )
  {
    v9 = (char *)WiaTrace_TraceLog("ListToPropVariant, type (%d) not supported");
    WriteDbgTraceErrorWI("ListToPropVariant", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = (void **)WiaTrace_Trace("ListToPropVariant, type (%d) not supported", *((unsigned __int16 *)a1 + 2));
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"ListToPropVariant", 1, v11);
    v8 = -2147024809;
LABEL_67:
    PropVariantClear(a2);
    goto LABEL_68;
  }
  if ( !*((_QWORD *)a1 + 4) )
  {
LABEL_12:
    v8 = -2147467261;
    goto LABEL_67;
  }
  v14 = (BYTE *)CoTaskMemAlloc(16LL * (unsigned int)(v7 + 2));
  v15 = v14;
  if ( !v14 )
    goto LABEL_16;
  *((_DWORD *)a2 + 2) = v7 + 2;
  v16 = v14 + 32;
  *(GUID *)v14 = WiaImgFmt_UNDEFINED;
  v17 = 16 * v7;
  *((_OWORD *)v14 + 1) = *(_OWORD *)((char *)a1 + 12);
  v18 = (const void *)*((_QWORD *)a1 + 4);
LABEL_15:
  memcpy_0(v16, v18, v17);
  a2[2] = v15;
LABEL_68:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v61);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021958  push    rbp
0x18002195a  push    rbx
0x18002195b  push    rsi
0x18002195c  push    rdi
0x18002195d  push    r12
0x18002195f  push    r13
0x180021961  push    r14
0x180021963  push    r15
0x180021965  lea     rbp, [rsp-1Fh]
0x18002196a  sub     rsp, 88h
0x180021971  mov     rdi, rcx
0x180021974  mov     r14, rdx
0x180021977  lea     rcx, aListtopropvari_0; "::ListToPropVariant"
0x18002197e  call    WiaTrace_Trace
0x180021983  lea     r12, aListtopropvari_6; "ListToPropVariant"
0x18002198a  mov     [rsp+0C0h+var_98], rax; struct tagWiaTraceData_Type *
0x18002198f  mov     r9, r12; char *
0x180021992  lea     rcx, [rbp+57h+var_90]; this
0x180021996  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002199b  mov     esi, [rdi+8]
0x18002199e  xor     r13d, r13d
0x1800219a1  mov     eax, 1000h
0x1800219a6  mov     ebx, r13d
0x1800219a9  or      ax, [rdi+4]
0x1800219ad  mov     [r14], ax
0x1800219b1  movzx   edx, word ptr [rdi+4]
0x1800219b5  lea     eax, [r13+2]
0x1800219b9  mov     ecx, edx
0x1800219bb  sub     ecx, eax
0x1800219bd  jz      loc_180021F2D
0x1800219c3  sub     ecx, 1
0x1800219c6  jz      loc_180021F1E
0x1800219cc  sub     ecx, 1
0x1800219cf  jz      loc_180021EA8
0x1800219d5  sub     ecx, 1
0x1800219d8  jz      loc_180021E31
0x1800219de  sub     ecx, 3
0x1800219e1  jz      loc_180021BF7
0x1800219e7  sub     ecx, 9
0x1800219ea  jz      loc_180021B98
0x1800219f0  sub     ecx, 1
0x1800219f3  jz      loc_180021F2D
0x1800219f9  sub     ecx, 1
0x1800219fc  jz      loc_180021F1E
0x180021a02  cmp     ecx, 35h ; '5'
0x180021a05  jz      short loc_180021A54
0x180021a07  lea     rcx, aListtopropvari_3; "ListToPropVariant, type (%d) not suppor"...
0x180021a0e  call    WiaTrace_TraceLog
0x180021a13  mov     rdx, rax; char *
0x180021a16  mov     rcx, r12; char *
0x180021a19  mov     rbx, rax
0x180021a1c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021a21  mov     rcx, rbx; this
0x180021a24  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021a29  movzx   edx, word ptr [rdi+4]
0x180021a2d  lea     rcx, aListtopropvari_3; "ListToPropVariant, type (%d) not suppor"...
0x180021a34  call    WiaTrace_Trace
0x180021a39  lea     r9d, [r13+1]; int
0x180021a3d  mov     [rsp+0C0h+lpMem], rax; lpMem
0x180021a42  mov     r8, r12; int
0x180021a45  call    WiaTrace_ProcessTrace_Ex
0x180021a4a  mov     ebx, 80070057h
0x180021a4f  jmp     loc_180021F92
0x180021a54  cmp     [rdi+20h], r13
0x180021a58  jnz     short loc_180021A64
0x180021a5a  mov     ebx, 80004003h
0x180021a5f  jmp     loc_180021F92
0x180021a64  lea     r12d, [rsi+2]
0x180021a68  mov     ecx, r12d
0x180021a6b  shl     rcx, 4; cb
0x180021a6f  call    cs:__imp_CoTaskMemAlloc
0x180021a75  mov     r15, rax
0x180021a78  test    rax, rax
0x180021a7b  jz      short loc_180021AB2
0x180021a7d  movups  xmm0, xmmword ptr cs:WiaImgFmt_UNDEFINED.Data1
0x180021a84  mov     [r14+8], r12d
0x180021a88  lea     rcx, [rax+20h]; void *
0x180021a8c  mov     r8, rsi
0x180021a8f  movdqu  xmmword ptr [rax], xmm0
0x180021a93  shl     r8, 4; Size
0x180021a97  movups  xmm0, xmmword ptr [rdi+0Ch]
0x180021a9b  movdqu  xmmword ptr [rax+10h], xmm0
0x180021aa0  mov     rdx, [rdi+20h]; Src
0x180021aa4  call    memcpy_0
0x180021aa9  mov     [r14+10h], r15
0x180021aad  jmp     loc_180021F9B
0x180021ab2  lea     rcx, aListtopropvari; "ListToPropVariant (MAKE_LIST), unable t"...
0x180021ab9  call    WiaTrace_TraceLog
0x180021abe  mov     rdx, rax; char *
0x180021ac1  lea     rcx, aListtopropvari_6; "ListToPropVariant"
0x180021ac8  mov     rbx, rax
0x180021acb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021ad0  mov     rcx, rbx; this
0x180021ad3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021ad8  lea     rcx, aListtopropvari; "ListToPropVariant (MAKE_LIST), unable t"...
0x180021adf  call    WiaTrace_Trace
0x180021ae4  lea     r8, aListtopropvari_6; "ListToPropVariant"
0x180021aeb  mov     r9d, 1; int
0x180021af1  mov     [rsp+0C0h+lpMem], rax; lpMem
0x180021af6  call    WiaTrace_ProcessTrace_Ex
0x180021afb  mov     ebx, 8007000Eh
0x180021b00  jmp     loc_180021F92
0x180021b05  lea     rcx, [rsi+2]; unsigned __int64
0x180021b09  cmp     rcx, rsi
0x180021b0c  jb      loc_180021F8D
0x180021b12  lea     r8, [rbp+57h+cb]; unsigned __int64 *
0x180021b16  mov     [rbp+57h+cb], rcx
0x180021b1a  mov     edx, 4; unsigned __int64
0x180021b1f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180021b24  test    eax, eax
0x180021b26  js      loc_180021F8D
0x180021b2c  mov     rcx, [rbp+57h+cb]; cb
0x180021b30  call    cs:__imp_CoTaskMemAlloc
0x180021b36  mov     r15, rax
0x180021b39  test    rax, rax
0x180021b3c  jz      short loc_180021B62
0x180021b3e  lea     ecx, [rsi+2]
0x180021b41  mov     [r14+8], ecx
0x180021b45  lea     r8, ds:0[rsi*4]
0x180021b4d  mov     [rax], esi
0x180021b4f  mov     ecx, [rdi+0Ch]
0x180021b52  mov     [rax+4], ecx
0x180021b55  lea     rcx, [rax+8]
0x180021b59  mov     rdx, [rdi+10h]
0x180021b5d  jmp     loc_180021AA4
0x180021b62  lea     rcx, aListtopropvari; "ListToPropVariant (MAKE_LIST), unable t"...
0x180021b69  call    WiaTrace_TraceLog
0x180021b6e  mov     rdx, rax; char *
0x180021b71  mov     rcx, r12; char *
0x180021b74  mov     rbx, rax
0x180021b77  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021b7c  mov     rcx, rbx; this
0x180021b7f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021b84  lea     rcx, aListtopropvari; "ListToPropVariant (MAKE_LIST), unable t"...
0x180021b8b  call    WiaTrace_Trace
0x180021b90  mov     r8, r12
0x180021b93  jmp     loc_180021AEB
0x180021b98  cmp     [rdi+10h], r13
0x180021b9c  jz      loc_180021A5A
0x180021ba2  lea     rcx, [rsi+2]; unsigned __int64
0x180021ba6  cmp     rcx, rsi
0x180021ba9  jb      loc_180021F8D
0x180021baf  lea     r8, [rbp+57h+cb]; unsigned __int64 *
0x180021bb3  mov     [rbp+57h+cb], rcx
0x180021bb7  mov     edx, 1; unsigned __int64
0x180021bbc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180021bc1  test    eax, eax
0x180021bc3  js      loc_180021F8D
0x180021bc9  mov     rcx, [rbp+57h+cb]; cb
0x180021bcd  call    cs:__imp_CoTaskMemAlloc
0x180021bd3  mov     r15, rax
0x180021bd6  test    rax, rax
0x180021bd9  jz      short loc_180021B62
0x180021bdb  lea     ecx, [rsi+2]
0x180021bde  mov     r8, rsi
0x180021be1  mov     [r14+8], ecx
0x180021be5  mov     [rax], sil
0x180021be8  mov     cl, [rdi+0Ch]
0x180021beb  mov     [rax+1], cl
0x180021bee  lea     rcx, [rax+2]
0x180021bf2  jmp     loc_180021B59
0x180021bf7  cmp     [rdi+18h], r13
0x180021bfb  jnz     short loc_180021C43
0x180021bfd  lea     rcx, aListtopropvari_1; "ListToPropVariant (MAKE_LIST_BSTR), pLi"...
0x180021c04  call    WiaTrace_TraceLog
0x180021c09  mov     rdx, rax; char *
0x180021c0c  mov     rcx, r12; char *
0x180021c0f  mov     rbx, rax
0x180021c12  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021c17  mov     rcx, rbx; this
0x180021c1a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021c1f  lea     rcx, aListtopropvari_1; "ListToPropVariant (MAKE_LIST_BSTR), pLi"...
0x180021c26  call    WiaTrace_Trace
0x180021c2b  mov     r8, r12; int
0x180021c2e  mov     r9d, 1; int
0x180021c34  mov     [rsp+0C0h+lpMem], rax; lpMem
0x180021c39  call    WiaTrace_ProcessTrace_Ex
0x180021c3e  jmp     loc_180021A5A
0x180021c43  lea     r15d, [rsi+2]
0x180021c47  mov     ecx, r15d
0x180021c4a  shl     rcx, 3; cb
0x180021c4e  call    cs:__imp_CoTaskMemAlloc
0x180021c54  mov     r12, rax
0x180021c57  test    rax, rax
0x180021c5a  jz      loc_180021DD6
0x180021c60  lea     rcx, Class; psz
0x180021c67  mov     [r14+8], r15d
0x180021c6b  call    cs:__imp_SysAllocString
0x180021c71  mov     [r12], rax
0x180021c75  mov     rcx, [rdi+10h]; psz
0x180021c79  test    rcx, rcx
0x180021c7c  jnz     short loc_180021CBC
0x180021c7e  lea     rcx, aListtopropvari_5; "ListToPropVariant (MAKE_LIST_BSTR), Nom"...
0x180021c85  call    WiaTrace_TraceLog
0x180021c8a  mov     rdx, rax; char *
0x180021c8d  lea     rcx, aListtopropvari_6; "ListToPropVariant"
0x180021c94  mov     rbx, rax
0x180021c97  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021c9c  mov     rcx, rbx; this
0x180021c9f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021ca4  lea     rcx, aListtopropvari_5; "ListToPropVariant (MAKE_LIST_BSTR), Nom"...
0x180021cab  call    WiaTrace_Trace
0x180021cb0  lea     r8, aListtopropvari_6; "ListToPropVariant"
0x180021cb7  jmp     loc_180021C2E
0x180021cbc  call    cs:__imp_SysAllocString
0x180021cc2  mov     [r12+8], rax
0x180021cc7  test    rax, rax
0x180021cca  jnz     short loc_180021CFE
0x180021ccc  lea     rcx, aListtopropvari_4; "ListToPropVariant (MAKE_LIST_BSTR), out"...
0x180021cd3  call    WiaTrace_TraceLog
0x180021cd8  mov     rdx, rax; char *
0x180021cdb  lea     rcx, aListtopropvari_6; "ListToPropVariant"
0x180021ce2  mov     rbx, rax
0x180021ce5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021cea  mov     rcx, rbx; this
0x180021ced  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021cf2  lea     rcx, aListtopropvari_4; "ListToPropVariant (MAKE_LIST_BSTR), out"...
0x180021cf9  jmp     loc_180021ADF
0x180021cfe  mov     r15d, r13d
0x180021d01  cmp     r15d, esi
0x180021d04  jnb     loc_180021DD0
0x180021d0a  mov     rax, [rdi+18h]
0x180021d0e  mov     ecx, r15d
0x180021d11  mov     rcx, [rax+rcx*8]; psz
0x180021d15  test    rcx, rcx
0x180021d18  jz      short loc_180021D82
0x180021d1a  call    cs:__imp_SysAllocString
0x180021d20  lea     ecx, [r15+2]
0x180021d24  mov     [r12+rcx*8], rax
0x180021d28  test    rax, rax
0x180021d2b  jz      short loc_180021D32
0x180021d2d  inc     r15d
0x180021d30  jmp     short loc_180021D01
0x180021d32  lea     rcx, aListtopropvari_4; "ListToPropVariant (MAKE_LIST_BSTR), out"...
0x180021d39  call    WiaTrace_TraceLog
0x180021d3e  mov     rdx, rax; char *
0x180021d41  lea     rcx, aListtopropvari_6; "ListToPropVariant"
0x180021d48  mov     rbx, rax
0x180021d4b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021d50  mov     rcx, rbx; this
0x180021d53  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021d58  lea     rcx, aListtopropvari_4; "ListToPropVariant (MAKE_LIST_BSTR), out"...
0x180021d5f  call    WiaTrace_Trace
0x180021d64  mov     r9d, 1; int
0x180021d6a  mov     [rsp+0C0h+lpMem], rax; lpMem
0x180021d6f  lea     r8, aListtopropvari_6; "ListToPropVariant"
0x180021d76  call    WiaTrace_ProcessTrace_Ex
0x180021d7b  mov     ebx, 8007000Eh
0x180021d80  jmp     short loc_180021DD0
0x180021d82  lea     rcx, aListtopropvari_5; "ListToPropVariant (MAKE_LIST_BSTR), Nom"...
0x180021d89  call    WiaTrace_TraceLog
0x180021d8e  mov     rdx, rax; char *
0x180021d91  lea     rcx, aListtopropvari_6; "ListToPropVariant"
0x180021d98  mov     rbx, rax
0x180021d9b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021da0  mov     rcx, rbx; this
0x180021da3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021da8  lea     rcx, aListtopropvari_5; "ListToPropVariant (MAKE_LIST_BSTR), Nom"...
0x180021daf  call    WiaTrace_Trace
0x180021db4  mov     r9d, 1; int
0x180021dba  mov     [rsp+0C0h+lpMem], rax; lpMem
0x180021dbf  lea     r8, aListtopropvari_6; "ListToPropVariant"
0x180021dc6  call    WiaTrace_ProcessTrace_Ex
0x180021dcb  mov     ebx, 80004003h
0x180021dd0  mov     [r14+10h], r12
0x180021dd4  jmp     short loc_180021E24
0x180021dd6  lea     rcx, aListtopropvari_2; "ListToPropVariant (MAKE_LIST_BSTR), una"...
0x180021ddd  call    WiaTrace_TraceLog
0x180021de2  mov     rdx, rax; char *
0x180021de5  lea     rcx, aListtopropvari_6; "ListToPropVariant"
0x180021dec  mov     rbx, rax
0x180021def  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021df4  mov     rcx, rbx; this
0x180021df7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021dfc  lea     rcx, aListtopropvari_2; "ListToPropVariant (MAKE_LIST_BSTR), una"...
0x180021e03  call    WiaTrace_Trace
0x180021e08  mov     r9d, 1; int
0x180021e0e  mov     [rsp+0C0h+lpMem], rax; lpMem
0x180021e13  lea     r8, aListtopropvari_6; "ListToPropVariant"
0x180021e1a  call    WiaTrace_ProcessTrace_Ex
0x180021e1f  mov     ebx, 8007000Eh
0x180021e24  test    ebx, ebx
0x180021e26  js      loc_180021F92
0x180021e2c  jmp     loc_180021F9B
0x180021e31  cmp     [rdi+18h], r13
0x180021e35  jz      loc_180021A5A
0x180021e3b  lea     rcx, [rsi+2]; unsigned __int64
0x180021e3f  cmp     rcx, rsi
0x180021e42  jb      loc_180021F8D
0x180021e48  lea     r8, [rbp+57h+cb]; unsigned __int64 *
0x180021e4c  mov     [rbp+57h+cb], rcx
0x180021e50  mov     edx, 8; unsigned __int64
0x180021e55  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180021e5a  test    eax, eax
0x180021e5c  js      loc_180021F8D
0x180021e62  mov     rcx, [rbp+57h+cb]; cb
0x180021e66  call    cs:__imp_CoTaskMemAlloc
0x180021e6c  mov     r15, rax
0x180021e6f  test    rax, rax
0x180021e72  jz      loc_180021B62
  ... truncated ...
```
