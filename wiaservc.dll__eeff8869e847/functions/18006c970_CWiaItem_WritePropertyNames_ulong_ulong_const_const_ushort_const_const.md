# CWiaItem::WritePropertyNames(ulong,ulong const * const,ushort * const * const)

- ea: `0x18006c970`
- end: `0x18006cce8`
- name: `?WritePropertyNames@CWiaItem@@UEAAJKQEBKQEBQEAG@Z`
- size: `888`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, unsigned int, const unsigned int *const, unsigned __int16 *const *const)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180066110`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x1800649a0`
- `0x18006c970`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006cae8`
- `KERNEL32!LocalFree` at `0x18006cc6c`
- `KERNEL32!LocalFree` at `0x18006cc75`
- `KERNEL32!LocalFree` at `0x18006cae8`
- `KERNEL32!LocalFree` at `0x18006cc6c`
- `KERNEL32!LocalFree` at `0x18006cc75`
- `KERNEL32!LocalAlloc` at `0x18006ca35`
- `KERNEL32!LocalAlloc` at `0x18006ca90`
- `KERNEL32!LocalAlloc` at `0x18006ca35`
- `KERNEL32!LocalAlloc` at `0x18006ca90`

## string_xrefs

- `0x18006c989`: `CWiaItem::WritePropertyNames`
- `0x18006caad`: `CWiaItem::WritePropertyNames`
- `0x18006cad9`: `CWiaItem::WritePropertyNames`
- `0x18006cb85`: `CWiaItem::WritePropertyNames`
- `0x18006cbb7`: `CWiaItem::WritePropertyNames`
- `0x18006cc00`: `CWiaItem::WritePropertyNames`
- `0x18006cc2f`: `CWiaItem::WritePropertyNames`
- `0x18006cc5d`: `CWiaItem::WritePropertyNames`
- `0x18006cc20`: `Reading Access values failed`
- `0x18006cc46`: `Reading Access values failed`
- `0x18006cbf1`: `WritePropertyNames failed`
- `0x18006cc17`: `WritePropertyNames failed`
- `0x18006cb76`: `not allowed to write prop: %d.`
- `0x18006cba0`: `not allowed to write prop: %d.`

## pseudocode

```c
__int64 __fastcall CWiaItem::WritePropertyNames(
        CWiaItem *this,
        unsigned int a2,
        const unsigned int *a3,
        unsigned __int16 *const *a4)
{
  __int64 v5; // rsi
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  int inited; // edi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  HLOCAL v17; // rbp
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  _DWORD *v23; // r14
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  unsigned int v30; // r8d
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // eax
  unsigned int i; // ecx
  __int64 v35; // rdi
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  char *v46; // rbx
  void *v47; // rdx
  char *v48; // rbx
  void *v49; // rdx
  void **v50; // rax
  void *v51; // rdx
  __int64 v52; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  _BYTE v54[152]; // [rsp+30h] [rbp-98h] BYREF

  v5 = a2;
  v8 = (char ***)WiaTrace_Trace("CWiaItem::WritePropertyNames");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v54, v9, v10, (char **)"CWiaItem::WritePropertyNames", lpMem, v8);
  if ( (unsigned int)v5 <= 0xAAAAAAA )
  {
    inited = 0;
    if ( !(_DWORD)v5 )
    {
LABEL_11:
      CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v54);
      return (unsigned int)inited;
    }
    if ( !*((_DWORD *)this + 30) )
    {
      inited = CWiaItem::InitLazyProps((CWiaItem *)((char *)this - 8));
      if ( inited < 0 )
      {
        v12 = (char *)WiaTrace_TraceLog("InitLazyProps failed");
        WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v12);
        WiaTrcLib::Free((WiaTrcLib *)v12, v13);
        v14 = (void **)WiaTrace_Trace("InitLazyProps failed");
        WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CWiaItem::WritePropertyNames", 1, v14);
        goto LABEL_11;
      }
    }
    v17 = LocalAlloc(0x40u, 24 * v5);
    if ( !v17 )
    {
      v18 = (char *)WiaTrace_TraceLog("Out of memory");
      WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v18);
      WiaTrcLib::Free((WiaTrcLib *)v18, v19);
      v20 = (void **)WiaTrace_Trace("Out of memory");
      WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"CWiaItem::WritePropertyNames", 1, v20);
LABEL_10:
      inited = -2147024882;
      goto LABEL_11;
    }
    v23 = LocalAlloc(0x40u, 16 * v5);
    if ( !v23 )
    {
      v24 = (char *)WiaTrace_TraceLog("Out of memory");
      WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v24);
      WiaTrcLib::Free((WiaTrcLib *)v24, v25);
      v26 = (void **)WiaTrace_Trace("Out of memory");
      WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"CWiaItem::WritePropertyNames", 1, v26);
      LocalFree(v17);
      goto LABEL_10;
    }
    v30 = 0;
    v31 = 0;
    do
    {
      ++v30;
      v32 = 2 * v31;
      v23[2 * v32] = 1;
      v33 = a3[v31++];
      v23[2 * v32 + 2] = v33;
    }
    while ( v30 < (unsigned int)v5 );
    inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, HLOCAL))(**(_QWORD **)(*((_QWORD *)this + 26) + 16LL)
                                                                         + 24LL))(
               *(_QWORD *)(*((_QWORD *)this + 26) + 16LL),
               (unsigned int)v5,
               v23,
               v17);
    if ( inited < 0 )
    {
      v46 = (char *)WiaTrace_TraceLog("Reading Access values failed");
      WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v46);
      WiaTrcLib::Free((WiaTrcLib *)v46, v47);
      v43 = (void **)WiaTrace_Trace("Reading Access values failed");
    }
    else
    {
      for ( i = 0; i < (unsigned int)v5; ++i )
      {
        v35 = i;
        if ( *((_WORD *)v17 + 12 * i) )
        {
          v36 = (char *)WiaTrace_TraceLog("not allowed to write prop: %d.");
          WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v36);
          WiaTrcLib::Free((WiaTrcLib *)v36, v37);
          v38 = (void **)WiaTrace_Trace("not allowed to write prop: %d.", a3[v35]);
          WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"CWiaItem::WritePropertyNames", 1, v38);
          inited = -2147024891;
          goto LABEL_24;
        }
      }
      inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned int *, unsigned __int16 *const *))(***((_QWORD ***)this + 26) + 56LL))(
                 **((_QWORD **)this + 26),
                 (unsigned int)v5,
                 a3,
                 a4);
      if ( inited >= 0 )
        goto LABEL_24;
      v41 = (char *)WiaTrace_TraceLog("WritePropertyNames failed");
      WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v41);
      WiaTrcLib::Free((WiaTrcLib *)v41, v42);
      v43 = (void **)WiaTrace_Trace("WritePropertyNames failed");
    }
    WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"CWiaItem::WritePropertyNames", 1, v43);
LABEL_24:
    LocalFree(v23);
    LocalFree(v17);
    goto LABEL_11;
  }
  v48 = (char *)WiaTrace_TraceLog("Invalid cpropid argument (%u) (E_INVALIDARG)");
  WriteDbgTraceErrorWI("CWiaItem::WritePropertyNames", v48);
  WiaTrcLib::Free((WiaTrcLib *)v48, v49);
  v50 = (void **)WiaTrace_Trace("Invalid cpropid argument (%u) (E_INVALIDARG)", v5);
  WiaTrace_ProcessTrace_Ex(v52, v51, (void *)"CWiaItem::WritePropertyNames", 1, v50);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v54);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18006c970  push    rbx
0x18006c972  push    rbp
0x18006c973  push    rsi
0x18006c974  push    rdi
0x18006c975  push    r12
0x18006c977  push    r13
0x18006c979  push    r14
0x18006c97b  push    r15
0x18006c97d  sub     rsp, 88h
0x18006c984  mov     r15, rcx
0x18006c987  mov     esi, edx
0x18006c989  lea     r14, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006c990  mov     r13, r9
0x18006c993  mov     rcx, r14
0x18006c996  mov     r12, r8
0x18006c999  call    WiaTrace_Trace
0x18006c99e  mov     r9, r14; char *
0x18006c9a1  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x18006c9a6  lea     rcx, [rsp+0C8h+var_98]; this
0x18006c9ab  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18006c9b0  cmp     esi, 0AAAAAAAh
0x18006c9b6  ja      loc_18006CC80
0x18006c9bc  xor     edi, edi
0x18006c9be  test    esi, esi
0x18006c9c0  jz      loc_18006CAF3
0x18006c9c6  lea     rcx, [r15-8]; this
0x18006c9ca  cmp     [rcx+80h], edi
0x18006c9d0  jnz     short loc_18006CA25
0x18006c9d2  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x18006c9d7  mov     edi, eax
0x18006c9d9  test    eax, eax
0x18006c9db  jns     short loc_18006CA23
0x18006c9dd  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18006c9e4  call    WiaTrace_TraceLog
0x18006c9e9  mov     rdx, rax; char *
0x18006c9ec  mov     rcx, r14; char *
0x18006c9ef  mov     rbx, rax
0x18006c9f2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006c9f7  mov     rcx, rbx; this
0x18006c9fa  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006c9ff  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18006ca06  call    WiaTrace_Trace
0x18006ca0b  mov     r9d, 1; int
0x18006ca11  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006ca16  mov     r8, r14; int
0x18006ca19  call    WiaTrace_ProcessTrace_Ex
0x18006ca1e  jmp     loc_18006CAF3
0x18006ca23  xor     edi, edi
0x18006ca25  lea     rdx, [rsi+rsi*2]
0x18006ca29  mov     ecx, 40h ; '@'; uFlags
0x18006ca2e  shl     rdx, 3; uBytes
0x18006ca32  mov     rbx, rsi
0x18006ca35  call    cs:__imp_LocalAlloc
0x18006ca3b  mov     rbp, rax
0x18006ca3e  test    rax, rax
0x18006ca41  jnz     short loc_18006CA84
0x18006ca43  lea     rcx, aOutOfMemory_3; "Out of memory"
0x18006ca4a  call    WiaTrace_TraceLog
0x18006ca4f  mov     rdx, rax; char *
0x18006ca52  mov     rcx, r14; char *
0x18006ca55  mov     rbx, rax
0x18006ca58  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006ca5d  mov     rcx, rbx; this
0x18006ca60  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006ca65  lea     rcx, aOutOfMemory_3; "Out of memory"
0x18006ca6c  call    WiaTrace_Trace
0x18006ca71  lea     r9d, [rbp+1]; int
0x18006ca75  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006ca7a  mov     r8, r14; int
0x18006ca7d  call    WiaTrace_ProcessTrace_Ex
0x18006ca82  jmp     short loc_18006CAEE
0x18006ca84  shl     rbx, 4
0x18006ca88  mov     ecx, 40h ; '@'; uFlags
0x18006ca8d  mov     rdx, rbx; uBytes
0x18006ca90  call    cs:__imp_LocalAlloc
0x18006ca96  mov     r14, rax
0x18006ca99  test    rax, rax
0x18006ca9c  jnz     short loc_18006CB04
0x18006ca9e  lea     rcx, aOutOfMemory_3; "Out of memory"
0x18006caa5  call    WiaTrace_TraceLog
0x18006caaa  mov     rdx, rax; char *
0x18006caad  lea     rcx, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cab4  mov     rbx, rax
0x18006cab7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006cabc  mov     rcx, rbx; this
0x18006cabf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006cac4  lea     rcx, aOutOfMemory_3; "Out of memory"
0x18006cacb  call    WiaTrace_Trace
0x18006cad0  lea     r9d, [r14+1]; int
0x18006cad4  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006cad9  lea     r8, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cae0  call    WiaTrace_ProcessTrace_Ex
0x18006cae5  mov     rcx, rbp; hMem
0x18006cae8  call    cs:__imp_LocalFree
0x18006caee  mov     edi, 8007000Eh
0x18006caf3  lea     rcx, [rsp+0C8h+var_98]; this
0x18006caf8  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18006cafd  mov     eax, edi
0x18006caff  jmp     loc_18006CCD4
0x18006cb04  mov     r8d, edi
0x18006cb07  test    esi, esi
0x18006cb09  jz      short loc_18006CB30
0x18006cb0b  mov     rdx, rdi
0x18006cb0e  mov     rcx, rdx
0x18006cb11  inc     r8d
0x18006cb14  add     rcx, rcx
0x18006cb17  mov     dword ptr [r14+rcx*8], 1
0x18006cb1f  mov     eax, [r12+rdx*4]
0x18006cb23  inc     rdx
0x18006cb26  mov     [r14+rcx*8+8], eax
0x18006cb2b  cmp     r8d, esi
0x18006cb2e  jb      short loc_18006CB0E
0x18006cb30  mov     rax, [r15+0D0h]
0x18006cb37  mov     r9, rbp
0x18006cb3a  mov     r8, r14
0x18006cb3d  mov     edx, esi
0x18006cb3f  mov     rcx, [rax+10h]
0x18006cb43  mov     rax, [rcx]
0x18006cb46  mov     rax, [rax+18h]
0x18006cb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb4f  xor     ebx, ebx
0x18006cb51  mov     edi, eax
0x18006cb53  test    eax, eax
0x18006cb55  js      loc_18006CC20
0x18006cb5b  mov     ecx, ebx
0x18006cb5d  cmp     ecx, esi
0x18006cb5f  jnb     short loc_18006CBCD
0x18006cb61  mov     edi, ecx
0x18006cb63  lea     rax, [rdi+rdi*2]
0x18006cb67  cmp     [rbp+rax*8+0], bx
0x18006cb6c  jnz     short loc_18006CB72
0x18006cb6e  inc     ecx
0x18006cb70  jmp     short loc_18006CB5D
0x18006cb72  mov     edx, [r12+rdi*4]
0x18006cb76  lea     rcx, aNotAllowedToWr; "not allowed to write prop: %d."
0x18006cb7d  call    WiaTrace_TraceLog
0x18006cb82  mov     rdx, rax; char *
0x18006cb85  lea     rcx, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cb8c  mov     rbx, rax
0x18006cb8f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006cb94  mov     rcx, rbx; this
0x18006cb97  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006cb9c  mov     edx, [r12+rdi*4]
0x18006cba0  lea     rcx, aNotAllowedToWr; "not allowed to write prop: %d."
0x18006cba7  call    WiaTrace_Trace
0x18006cbac  mov     r9d, 1; int
0x18006cbb2  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006cbb7  lea     r8, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cbbe  call    WiaTrace_ProcessTrace_Ex
0x18006cbc3  mov     edi, 80070005h
0x18006cbc8  jmp     loc_18006CC69
0x18006cbcd  mov     rax, [r15+0D0h]
0x18006cbd4  mov     r9, r13
0x18006cbd7  mov     r8, r12
0x18006cbda  mov     edx, esi
0x18006cbdc  mov     rcx, [rax]
0x18006cbdf  mov     rax, [rcx]
0x18006cbe2  mov     rax, [rax+38h]
0x18006cbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbeb  mov     edi, eax
0x18006cbed  test    eax, eax
0x18006cbef  jns     short loc_18006CC69
0x18006cbf1  lea     rcx, aWritepropertyn_0; "WritePropertyNames failed"
0x18006cbf8  call    WiaTrace_TraceLog
0x18006cbfd  mov     rdx, rax; char *
0x18006cc00  lea     rcx, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cc07  mov     rbx, rax
0x18006cc0a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006cc0f  mov     rcx, rbx; this
0x18006cc12  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006cc17  lea     rcx, aWritepropertyn_0; "WritePropertyNames failed"
0x18006cc1e  jmp     short loc_18006CC4D
0x18006cc20  lea     rcx, aReadingAccessV; "Reading Access values failed"
0x18006cc27  call    WiaTrace_TraceLog
0x18006cc2c  mov     rdx, rax; char *
0x18006cc2f  lea     rcx, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cc36  mov     rbx, rax
0x18006cc39  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006cc3e  mov     rcx, rbx; this
0x18006cc41  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006cc46  lea     rcx, aReadingAccessV; "Reading Access values failed"
0x18006cc4d  call    WiaTrace_Trace
0x18006cc52  mov     r9d, 1; int
0x18006cc58  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006cc5d  lea     r8, aCwiaitemWritep; "CWiaItem::WritePropertyNames"
0x18006cc64  call    WiaTrace_ProcessTrace_Ex
0x18006cc69  mov     rcx, r14; hMem
0x18006cc6c  call    cs:__imp_LocalFree
0x18006cc72  mov     rcx, rbp; hMem
0x18006cc75  call    cs:__imp_LocalFree
0x18006cc7b  jmp     loc_18006CAF3
0x18006cc80  mov     edx, esi
0x18006cc82  lea     rcx, aInvalidCpropid; "Invalid cpropid argument (%u) (E_INVALI"...
0x18006cc89  call    WiaTrace_TraceLog
0x18006cc8e  mov     rdx, rax; char *
0x18006cc91  mov     rcx, r14; char *
0x18006cc94  mov     rbx, rax
0x18006cc97  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006cc9c  mov     rcx, rbx; this
0x18006cc9f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006cca4  mov     edx, esi
0x18006cca6  lea     rcx, aInvalidCpropid; "Invalid cpropid argument (%u) (E_INVALI"...
0x18006ccad  call    WiaTrace_Trace
0x18006ccb2  mov     r9d, 1; int
0x18006ccb8  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006ccbd  mov     r8, r14; int
0x18006ccc0  call    WiaTrace_ProcessTrace_Ex
0x18006ccc5  lea     rcx, [rsp+0C8h+var_98]; this
0x18006ccca  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18006cccf  mov     eax, 80070057h
0x18006ccd4  add     rsp, 88h
0x18006ccdb  pop     r15
0x18006ccdd  pop     r14
0x18006ccdf  pop     r13
0x18006cce1  pop     r12
0x18006cce3  pop     rdi
0x18006cce4  pop     rsi
0x18006cce5  pop     rbp
0x18006cce6  pop     rbx
0x18006cce7  retn
```
